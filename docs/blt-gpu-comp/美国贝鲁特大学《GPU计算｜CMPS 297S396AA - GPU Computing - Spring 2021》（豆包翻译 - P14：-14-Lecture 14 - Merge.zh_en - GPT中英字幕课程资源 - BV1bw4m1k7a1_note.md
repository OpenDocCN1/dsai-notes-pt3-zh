# GPU计算：第14讲：合并模式 🧩

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_0.png)

在本节课中，我们将要学习一个新的并行计算模式：**合并**。我们将探讨如何将两个已排序的数组合并成一个更大的有序数组，并学习如何在GPU上高效地并行实现这一操作。

---

## 概述

上一节课我们介绍了**直方图**模式，并引入了**原子操作**和**私有化**优化。直方图用于统计数据集中落入各个区间的值的数量。由于多个线程可能同时更新同一个区间，我们遇到了**数据竞争**问题。在CPU上，我们通常使用**互斥锁**来解决，但在GPU上，锁可能导致**死锁**。因此，CUDA提供了**原子操作**，如 `atomicAdd`，来确保内存操作的原子性。为了减少全局内存上的原子操作竞争，我们使用了**私有化**优化，即每个线程块拥有直方图的私有副本，最后再合并到全局副本中。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_2.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_4.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_5.png)

本节课，我们将学习**合并**模式。合并操作接收两个已排序的列表，并将它们组合成一个单一的、更大的有序列表。我们将从顺序合并算法开始，然后探讨如何将其并行化，并解决并行化过程中的关键挑战。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_7.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_9.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_11.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_12.png)

---

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_14.png)

## 顺序合并算法

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_16.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_18.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_19.png)

在讨论并行合并之前，我们先来实现一个顺序合并算法。这个算法将作为我们后续并行实现的基准。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_21.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_23.png)

顺序合并的思路是使用三个指针：`i` 指向数组A，`j` 指向数组B，`k` 指向输出数组C。我们比较 `A[i]` 和 `B[j]`，将较小的元素放入 `C[k]`，并移动相应的指针。当其中一个数组耗尽后，我们将另一个数组的剩余元素直接复制到C中。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_25.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_26.png)

以下是顺序合并的代码实现：

```cpp
void mergeSequential(int* A, int* B, int* C, unsigned int M, unsigned int N) {
    unsigned int i = 0; // 索引数组A
    unsigned int j = 0; // 索引数组B
    unsigned int k = 0; // 索引数组C

    // 合并两个数组，直到其中一个耗尽
    while (i < M && j < N) {
        if (A[i] <= B[j]) {
            C[k++] = A[i++];
        } else {
            C[k++] = B[j++];
        }
    }

    // 如果数组A还有剩余元素，复制到C
    while (i < M) {
        C[k++] = A[i++];
    }

    // 如果数组B还有剩余元素，复制到C
    while (j < N) {
        C[k++] = B[j++];
    }
}
```

这个算法的时间复杂度是 **O(M + N)**，其中M和N分别是两个输入数组的大小。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_28.png)

---

## 并行合并的挑战与思路

顺序合并算法本质上是串行的，因为每一步的输出都依赖于上一步的比较结果。那么，如何在GPU上并行化这个操作呢？

一个直观的想法是**对输出进行分区**，而不是对输入进行分区。我们将输出数组C划分为多个大小相等的段，并让每个GPU线程负责合并生成其中一个段。这样，每个线程的工作量大致相同，有利于负载均衡。

然而，关键挑战在于：**每个线程如何找到其负责的输出段所对应的输入段（即在数组A和B中的起始位置）？**

给定一个输出索引 `k`（线程负责段的起始位置），我们需要找到对应的输入索引 `i`（在A中）和 `j`（在B中）。我们称 `i` 和 `j` 为 `k` 的**协同秩**。

---

## 寻找协同秩

我们的目标是：给定 `k`，找到 `i` 和 `j`。

首先，我们观察到输出数组C中 `k` 之前的元素数量，等于输入数组A中 `i` 之前的元素数量加上输入数组B中 `j` 之前的元素数量。因此，我们有基本关系：

**k = i + j**

所以，如果我们能找到 `i`，就可以通过 `j = k - i` 计算出 `j`。

接下来，我们需要确定 `i` 的取值范围。`i` 是数组A的索引，因此：

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_30.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_31.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_32.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_34.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_36.png)

*   `i` 的下界：`i >= 0` 且 `i >= k - N`（因为 `j = k - i` 必须 `<= N`）。所以下界是 `max(0, k - N)`。
*   `i` 的上界：`i <= M` 且 `i <= k`（因为 `j = k - i` 必须 `>= 0`）。所以上界是 `min(M, k)`。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_38.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_40.png)

因此，`i` 的取值范围是：`[max(0, k - N), min(M, k)]`。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_42.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_44.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_46.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_48.png)

在这个范围内，我们需要找到正确的 `i`。由于数组A和B都是有序的，我们可以在这个区间内进行**二分查找**。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_50.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_52.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_54.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_56.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_58.png)

判断一个候选值 `i` 是否正确（以及对应的 `j = k - i`）的条件是：
1.  `A[i-1] <= B[j]`
2.  `B[j-1] <= A[i]`

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_60.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_62.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_63.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_65.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_66.png)

如果 `i` 的猜测值太高，我们会发现 `A[i-1] > B[j]`。
如果 `i` 的猜测值太低，我们会发现 `B[j-1] > A[i]`。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_68.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_70.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_72.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_74.png)

基于这些规则，我们可以实现一个二分查找函数来找到正确的协同秩 `i`。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_76.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_78.png)

---

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_80.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_82.png)

## 并行合并内核实现

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_84.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_86.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_88.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_90.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_92.png)

现在，我们可以实现并行的合并内核了。每个线程的执行步骤如下：

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_94.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_96.png)

1.  计算自己负责的输出段的起始索引 `k`。
2.  调用 `coRank` 函数，通过二分查找找到对应的输入索引 `i`。
3.  计算 `j = k - i`。
4.  为了进行合并，线程还需要知道其输入段的大小。这可以通过计算下一个线程的起始索引 `k_next`，并再次调用 `coRank` 找到 `i_next` 和 `j_next` 来获得。那么，该线程负责的A段大小就是 `i_next - i`，B段大小是 `j_next - j`。
5.  最后，线程调用顺序合并函数，将其负责的A和B的子段合并到输出数组C的对应位置。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_98.png)

以下是并行合并内核的伪代码框架：

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_100.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_102.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_103.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_105.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_107.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_108.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_110.png)

```cpp
__global__ void mergeParallel(int* A, int* B, int* C, unsigned int M, unsigned int N, unsigned int elementsPerThread) {
    unsigned int tid = blockIdx.x * blockDim.x + threadIdx.x;
    unsigned int k = tid * elementsPerThread; // 该线程负责段的起始位置

    if (k < M + N) { // 边界检查
        // 1. 找到本段起始的协同秩
        unsigned int i = coRank(A, B, M, N, k);
        unsigned int j = k - i;

        // 2. 找到下一段起始的协同秩，以确定本段大小
        unsigned int k_next = min(k + elementsPerThread, M + N);
        unsigned int i_next = coRank(A, B, M, N, k_next);
        unsigned int j_next = k_next - i_next;

        // 3. 执行顺序合并
        mergeSequential(&A[i], &B[j], &C[k], i_next - i, j_next - j);
    }
}
```

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_112.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_114.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_116.png)

---

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_118.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_119.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_120.png)

## 性能优化：使用共享内存

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_122.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_124.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_126.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_128.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_129.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_130.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_131.png)

我们实现的初始并行版本存在一个主要的性能问题：**内存访问不连续（非合并访问）**。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_133.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_134.png)

*   在 `coRank` 函数中，每个线程独立进行二分查找，会随机访问全局内存中的A和B数组。
*   在顺序合并阶段，不同线程访问的输入子段位置也各不相同。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_136.png)

这导致了大量低效的全局内存访问。优化方法是利用**共享内存**：

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_138.png)

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_140.png)

1.  **以线程块为单位查找协同秩**：每个线程块只计算一次其负责的整个输出大段的协同秩（`i_block`, `j_block`），而不是每个线程都算。这减少了全局内存上的二分查找次数。
2.  **协作加载到共享内存**：线程块内的所有线程协作，以**合并访问**的方式将A和B的对应大段从全局内存加载到共享内存中。
3.  **在共享内存中执行操作**：每个线程在共享内存的数组副本上进行二分查找（寻找其子段的协同秩）和顺序合并。共享内存的延迟远低于全局内存，且随机访问代价小。
4.  **协作写回全局内存**：所有线程协作，将共享内存中合并好的结果以合并访问的方式写回全局内存。

这种优化策略将耗时的、非合并的全局内存访问，转换为了快速的共享内存访问，并确保了进出全局内存的访问是高效的合并访问。

---

## 总结

本节课我们一起学习了**合并**模式。我们从基础的顺序合并算法出发，理解了其工作原理。然后，我们探讨了在GPU上并行化合并操作的核心思想：**对输出进行分区**，并让每个线程负责一个输出段。

实现并行合并的关键在于解决**如何为每个输出段找到对应的输入段**这一问题，我们引入了**协同秩**的概念，并利用二分查找在有序数组中高效地找到它。

最后，我们分析了初始并行实现的性能瓶颈——**非合并的全局内存访问**，并提出了使用**共享内存**进行优化的策略：以线程块为单位组织计算，协作加载数据，在共享内存中完成核心操作，再协作写回结果。

![](img/de8cb2b80b3ef21e834d4e9ce7f92bc9_142.png)

通过本节课的学习，你应该掌握了合并模式的基本原理、并行化方法以及针对GPU架构的性能优化思路。