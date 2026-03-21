# GPU计算：第20讲：线程束内同步

![](img/b17390aa01e11fb74fe6515c4514fc08_0.png)

在本节课中，我们将学习一种高级的GPU编程技术：线程束内同步。我们将探讨如何利用同一线程束内线程的特殊关系，通过数据洗牌和投票指令，实现比传统的共享内存和块内同步更高效的线程间协作。

## 概述

上一节我们回顾了课程至今的内容，从GPU计算基础到各种并行模式的应用。从本节开始，我们将进入课程的新阶段，探讨一些高级编程特性，这些特性可以帮助你进一步优化项目中的应用程序。今天，我们将重点讨论线程束内同步。

线程束是SM中的基本调度单位，通常包含32个线程。由于线程束内的线程遵循SIMD模型，它们几乎同时执行相同的指令，这使得它们之间的同步比跨整个线程块的同步（如 `__syncthreads()`）更加高效。CUDA为此提供了两类内置函数：用于在线程间直接共享寄存器数据的洗牌指令，以及用于让线程就某个条件进行集体表决的投票指令。

## 线程束洗牌指令

![](img/b17390aa01e11fb74fe6515c4514fc08_2.png)

线程束洗牌指令允许同一线程束内的线程直接共享寄存器中的数据，而无需通过共享内存。这比使用共享内存和 `__syncthreads()` 更快，因为它避免了全局同步的开销，并且寄存器访问速度远快于共享内存。

![](img/b17390aa01e11fb74fe6515c4514fc08_4.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_5.png)

CUDA提供了几种洗牌指令变体：
*   `__shfl_sync`：从线程束中指定的通道（即线程）复制数据。
*   `__shfl_up_sync`：从ID较低的线程复制数据。
*   `__shfl_down_sync`：从ID较高的线程复制数据。
*   `__shfl_xor_sync`：通过按位异或操作确定源线程。

![](img/b17390aa01e11fb74fe6515c4514fc08_7.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_8.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_10.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_11.png)

### 应用示例：归约优化

我们曾在归约模式中看到，线程需要读取其他线程在前一次迭代中产生的值。当迭代进行到只剩下一个线程束时，所有读写操作都发生在这个线程束内部。此时，我们可以用洗牌指令替代共享内存和同步操作。

以下是优化后的归约核函数代码片段，展示了如何结合使用共享内存和洗牌指令：

```c
// 第一部分：在共享内存中进行归约树操作，直到步长等于线程束大小
for (int stride = blockDim.x / 2; stride >= WARP_SIZE; stride >>= 1) {
    if (threadIdx.x < stride) {
        sdata[threadIdx.x] += sdata[threadIdx.x + stride];
    }
    __syncthreads();
}

// 第二部分：将数据加载到寄存器，然后使用洗牌指令在单个线程束内完成归约
if (threadIdx.x < WARP_SIZE) {
    // 加载最后两个值到寄存器
    int sum = sdata[threadIdx.x] + sdata[threadIdx.x + WARP_SIZE];
    // 使用洗牌指令继续归约
    for (int stride = WARP_SIZE / 2; stride > 0; stride >>= 1) {
        sum += __shfl_down_sync(0xffffffff, sum, stride);
    }
    // 线程0存储最终结果
    if (threadIdx.x == 0) {
        output[blockIdx.x] = sum;
    }
}
```

![](img/b17390aa01e11fb74fe6515c4514fc08_13.png)

通过这种优化，我们显著提升了归约操作的性能，因为它减少了耗时的全局同步操作，并利用了更快的寄存器间通信。

## 线程束投票指令

![](img/b17390aa01e11fb74fe6515c4514fc08_15.png)

线程束投票指令使得线程束内的线程能够就某个条件进行集体表决。这在需要根据线程的局部状态做出集体决策时非常有用。

![](img/b17390aa01e11fb74fe6515c4514fc08_17.png)

主要的投票指令包括：
*   `__all_sync`：检查参与的所有线程是否都满足某个条件（谓词非零）。
*   `__any_sync`：检查是否有至少一个参与线程满足条件。
*   `__ballot_sync`：返回一个掩码，指示哪些参与线程满足条件。
*   `__activemask`：返回当前执行点上活跃线程的掩码。

![](img/b17390aa01e11fb74fe6515c4514fc08_19.png)

### 应用示例：队列插入优化

![](img/b17390aa01e11fb74fe6515c4514fc08_21.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_23.png)

考虑一个内核，其中多个线程根据条件判断是否要将数据插入一个全局队列。原始实现中，每个满足条件的线程都会原子性地递增全局队列计数器，这会造成严重的竞争。

![](img/b17390aa01e11fb74fe6515c4514fc08_25.png)

我们可以优化为：让一个线程束内的线程协作，只进行一次原子操作来为该线程束所有需要插入的线程预留空间。

![](img/b17390aa01e11fb74fe6515c4514fc08_27.png)

以下是优化步骤和关键代码：

![](img/b17390aa01e11fb74fe6515c4514fc08_29.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_31.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_33.png)

1.  **确定活跃线程和领导者**：使用 `__activemask()` 找出当前条件分支中活跃的线程，并选择第一个活跃线程作为领导者。
    ```c
    unsigned int active = __activemask();
    unsigned int leader = __ffs(active) - 1; // __ffs 返回从1开始的索引
    ```

![](img/b17390aa01e11fb74fe6515c4514fc08_35.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_37.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_38.png)

2.  **计算需要插入的元素数量**：使用 `__popc` 计算活跃掩码中置位比特的数量。
    ```c
    unsigned int num_active = __popc(active);
    ```

![](img/b17390aa01e11fb74fe6515c4514fc08_40.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_42.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_44.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_46.png)

3.  **领导者线程执行原子操作**：只有领导者线程执行一次原子加操作，为整个线程束预留空间。
    ```c
    unsigned int queue_index;
    if ((threadIdx.x % WARP_SIZE) == leader) {
        queue_index = atomicAdd(&queue_size, num_active);
    }
    ```

![](img/b17390aa01e11fb74fe6515c4514fc08_48.png)

4.  **广播起始索引**：领导者线程将其获得的队列起始索引广播给线程束内的所有其他活跃线程。
    ```c
    queue_index = __shfl_sync(active, queue_index, leader);
    ```

5.  **计算每个线程的偏移并存储**：每个线程计算在已预留空间内的个人偏移量（即它前面有多少个活跃线程），然后进行存储。
    ```c
    unsigned int thread_mask = 1 << (threadIdx.x % WARP_SIZE);
    unsigned int prev_mask = thread_mask - 1;
    unsigned int prev_active = active & prev_mask;
    unsigned int offset = __popc(prev_active);
    
    queue[queue_index + offset] = my_value;
    ```

![](img/b17390aa01e11fb74fe6515c4514fc08_50.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_52.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_54.png)

在这个特定例子中，由于操作本身很简单，额外的协作开销可能抵消了减少原子操作带来的收益。然而，在更复杂的、包含更多计算上下文的场景中，这种线程束级别的协作可以显著减少全局原子操作的竞争，从而提升性能。

![](img/b17390aa01e11fb74fe6515c4514fc08_56.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_57.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_59.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_61.png)

## 总结

![](img/b17390aa01e11fb74fe6515c4514fc08_63.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_65.png)

本节课我们一起学习了GPU编程中的线程束内同步技术。我们首先介绍了线程束洗牌指令，它允许线程直接共享寄存器值，并以归约优化为例展示了其应用。接着，我们探讨了线程束投票指令，它支持线程进行集体表决，并以优化队列插入为例说明了其使用方法和协作流程。

![](img/b17390aa01e11fb74fe6515c4514fc08_67.png)

![](img/b17390aa01e11fb74fe6515c4514fc08_69.png)

这些高级特性允许程序员更精细地控制线程间的协作，特别是在线程束内部，从而有可能实现更高的性能。理解并恰当应用这些指令，是进行高性能GPU编程的重要技能。