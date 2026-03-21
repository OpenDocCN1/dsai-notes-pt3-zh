# GPU计算：第22讲：动态并行

![](img/d4537e5532734bbdad21de8bd7c07dd7_0.png)

在本节课中，我们将要学习CUDA编程中的动态并行技术。动态并行允许GPU上的线程启动新的内核网格，这对于处理具有嵌套并行性的应用程序非常有用。

上一节我们介绍了固定内存和流的概念，本节中我们来看看动态并行。

## 什么是动态并行？

动态并行指的是在GPU上执行的线程能够启动新的网格在GPU上运行的能力。这意味着，如果一个线程在执行过程中发现更多可以并行处理的工作，它可以动态地启动一个新的内核来处理这些工作。

## 为何使用动态并行？

使用动态并行主要有两个原因：
1.  **避免与CPU同步**：如果计算由多个内核组成，我们可以直接从GPU启动它们，无需CPU介入。
2.  **处理嵌套并行性**：许多应用程序具有多层次的并行性。例如，一个并行任务单元内部可能包含更多可并行的工作。当内部并行工作的数量在编译时未知时，动态并行尤其有用。

![](img/d4537e5532734bbdad21de8bd7c07dd7_2.png)

以下是两种典型的嵌套并行应用场景：

![](img/d4537e5532734bbdad21de8bd7c07dd7_4.png)

*   **不规则嵌套工作**：每个线程内部的并行工作量不同。例如，在图算法中，每个顶点（线程）的邻居数量不同，因此每个线程需要启动不同数量的子线程来并行访问其邻居。
*   **递归深度未知**：每个线程可能根据运行时信息决定是否进一步递归（即启动更多线程）。例如，在四叉树/八叉树空间划分或快速排序等分治算法中，是否进一步划分取决于当前分区数据的属性。

## 动态并行示例：优化广度优先搜索

![](img/d4537e5532734bbdad21de8bd7c07dd7_6.png)

我们将以广度优先搜索为例，展示如何使用动态并行进行优化。在传统的BFS实现中，每个线程负责处理一个顶点，并**顺序**遍历其所有邻居。

```cpp
// 传统BFS内核代码片段（顺序处理邻居）
__global__ void bfs_kernel(...) {
    int tid = ...; // 线程ID对应一个顶点
    int start = csr_graph.offsets[tid];
    int num_neighbors = csr_graph.offsets[tid+1] - start;

    for (int i = 0; i < num_neighbors; i++) { // 顺序循环
        int neighbor = csr_graph.edges[start + i];
        // 访问邻居并可能加入下一层前沿
        if (atomicCAS(&level[neighbor], -1, current_level) == -1) {
            int pos = atomicAdd(&current_frontier_size, 1);
            next_frontier[pos] = neighbor;
        }
    }
}
```

![](img/d4537e5532734bbdad21de8bd7c07dd7_8.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_9.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_11.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_12.png)

我们可以使用动态并行来**并行化**每个线程内部的邻居遍历循环。父线程根据其邻居数量启动一个子网格，每个子线程处理一个邻居。

![](img/d4537e5532734bbdad21de8bd7c07dd7_14.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_15.png)

```cpp
// 使用动态并行的BFS内核代码片段
__global__ void bfs_parent_kernel(...) {
    int tid = ...;
    int start = csr_graph.offsets[tid];
    int num_neighbors = csr_graph.offsets[tid+1] - start;

    if (num_neighbors > THRESHOLD) { // 仅当邻居数较多时启动子网格
        dim3 threads_per_block(1024);
        dim3 num_blocks((num_neighbors + threads_per_block.x - 1) / threads_per_block.x);
        bfs_child_kernel<<<num_blocks, threads_per_block>>>(..., start, num_neighbors, ...);
    } else {
        // 邻居数较少，仍顺序处理
        for (int i = 0; i < num_neighbors; i++) {
            // ... 处理邻居的代码 ...
        }
    }
}

![](img/d4537e5532734bbdad21de8bd7c07dd7_17.png)

// 子内核，每个线程处理一个邻居
__global__ void bfs_child_kernel(..., int start, int num_neighbors, ...) {
    int i = threadIdx.x + blockIdx.x * blockDim.x; // 子线程索引
    if (i < num_neighbors) {
        int neighbor = csr_graph.edges[start + i];
        // 访问邻居并可能加入下一层前沿
        if (atomicCAS(&level[neighbor], -1, current_level) == -1) {
            int pos = atomicAdd(&current_frontier_size, 1);
            next_frontier[pos] = neighbor;
        }
    }
}
```

![](img/d4537e5532734bbdad21de8bd7c07dd7_19.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_21.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_23.png)

## 性能考量与优化

![](img/d4537e5532734bbdad21de8bd7c07dd7_25.png)

直接让每个线程都启动子网格可能导致性能下降，原因包括：
1.  **启动队列溢出**：GPU有未决启动数量的限制（默认2048）。超过此限制可能导致错误或程序挂起。可以使用 `cudaDeviceSetLimit(cudaLimitDevRuntimePendingLaunchCount, new_limit)` 提高限制。
2.  **流竞争**：默认情况下，同一线程块内的线程共享一个默认流，它们发起的网格会串行执行。可以通过编译器标志 `--default-stream per-thread` 为每个线程创建独立的流，以增加并行性。
3.  **小网格开销**：启动一个只有少量线程的网格，其开销可能超过并行带来的收益，并且会降低SM的利用率。

针对以上问题，我们可以进行优化：

![](img/d4537e5532734bbdad21de8bd7c07dd7_27.png)

*   **设置启动阈值**：仅为拥有大量邻居（例如超过1200个）的顶点启动动态并行。对于邻居数少的顶点，仍在父线程中顺序处理。这能显著减少启动数量并避免小网格。
*   **聚合启动**（高级优化）：让一个线程（如一个Warp或一个块的主线程）收集多个线程的工作，然后代表它们发起一个更大的、合并后的网格。这能进一步减少启动次数和调度开销。

## 其他应用：卸载驱动代码

![](img/d4537e5532734bbdad21de8bd7c07dd7_29.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_31.png)

动态并行另一个用途是将控制循环从CPU卸载到GPU。例如，在BFS中，原本由CPU循环调用每一层的内核。现在，可以启动一个单独的GPU线程来执行这个循环，逐层启动内核。

![](img/d4537e5532734bbdad21de8bd7c07dd7_33.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_35.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_36.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_38.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_39.png)

```cpp
// 在GPU上驱动BFS各层计算的内核
__global__ void bfs_driver_kernel(...) {
    *current_frontier_size = 0; // GPU上直接初始化
    while (*previous_frontier_size > 0) {
        // 动态启动处理当前层的内核
        bfs_parent_kernel<<<...>>>(...);
        cudaDeviceSynchronize(); // 等待当前层内核完成
        // 准备下一层迭代
        *previous_frontier_size = *current_frontier_size;
        *current_frontier_size = 0;
        swap(previous_frontier, next_frontier);
        current_level++;
    }
}
```

这样做的好处是释放了CPU，使其可以同时执行其他任务。但需要注意的是，单个控制线程在CPU上可能运行得更快，因此除非需要CPU同时处理其他工作，否则此优化可能不会提升整体性能。

## 重要注意事项

![](img/d4537e5532734bbdad21de8bd7c07dd7_41.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_43.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_45.png)

1.  **内存可见性**：
    *   父线程在启动子网格前对全局内存的写入，对子网格中的线程是可见的。
    *   子网格对全局内存的写入，只有在父线程调用 `cudaDeviceSynchronize()` 等待子网格完成后，才对父线程可见。
2.  **共享内存和本地内存**：**不要**将指向共享内存或线程本地内存的指针传递给动态启动的子内核。因为子网格可能在不同的SM上执行，无法访问父线程所在块的共享内存或父线程的本地内存。
3.  **嵌套深度限制**：硬件对动态并行的嵌套深度有限制（当前硬件通常为24层）。即一个网格启动另一个网格，后者再启动一个网格……这样的链不能超过24层。

![](img/d4537e5532734bbdad21de8bd7c07dd7_47.png)

本节课中我们一起学习了CUDA动态并行的概念、应用场景、实现方法以及关键的优化技术和注意事项。动态并行是处理不规则和递归并行模式的强大工具，但需要谨慎使用以避免性能陷阱。