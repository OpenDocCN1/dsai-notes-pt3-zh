# GPU计算：P9：模板计算 🧮

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_0.png)

在本节课中，我们将要学习一种新的并行模式——模板计算。我们将探讨其基本概念、与卷积运算的异同，并学习如何利用CUDA的3D线程网格、共享内存和寄存器平铺等技术来高效地实现和优化3D模板计算。

---

## 概述

上一节我们介绍了卷积运算，它引入了常量内存的使用，并且每个输出元素都是对应输入元素及其周围元素的加权和。本节中我们来看看模板计算，它是卷积运算的一个特例，通常用于结构化网格上的计算，其中每个网格点的值基于其邻居子集的值来计算。

## 什么是模板计算？

模板计算模式指的是一类在结构化网格上进行的计算，其中网格点的值基于该点邻居的一个子集来计算。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_2.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_4.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_6.png)

例如，在2D网格中，一个五点模板意味着某个输出网格点的值是其自身输入值以及上下左右四个邻居输入值的组合。在3D中，一个七点模板则包含在X、Y、Z三个维度上的邻居。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_8.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_10.png)

为了便于说明，我们将在2D和3D示例之间切换。通常，这些网格点被方便地存储为多维数组。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_12.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_14.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_15.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_16.png)

### 与卷积的异同

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_18.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_20.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_22.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_24.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_25.png)

模板计算与卷积非常相似，实际上是卷积的一个特例。主要区别在于：
*   卷积通常访问输入元素周围的整个块（例如3x3的卷积核）。
*   模板通常只访问特定方向的直接邻居（例如上下左右），这为某些优化提供了可能，而这些优化在通用卷积中可能无法实现。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_27.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_29.png)

## 并行化策略

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_31.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_32.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_34.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_36.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_37.png)

最细粒度和直观的并行化方式是为每个输出网格点分配一个线程，这与卷积类似。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_39.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_41.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_43.png)

对于2D模板，我们使用2D线程网格。对于3D模板，我们自然需要使用3D线程网格。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_45.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_47.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_49.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_51.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_52.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_54.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_56.png)

### 边界条件简化

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_58.png)

为了简化边界条件的处理，我们做一个贯穿课程的假设：**只计算内部的输出值，不计算边界上的值**。这确保了我们在访问邻居输入值时，这些值始终在有效范围内。这个假设通常是合理的，因为在许多实际应用中，边界元素可能由其他GPU或进程负责计算。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_60.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_62.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_64.png)

## 基础3D模板实现

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_66.png)

现在，让我们使用3D线程网格来实现一个基础的3D模板计算。

### 内核配置

我们配置一个3D的线程块（例如 8x8x8，共512个线程），并计算一个3D的网格块数量来覆盖整个输出空间。输出和输入都是 N x N x N 的立方体。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_68.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_70.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_72.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_74.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_75.png)

```c
dim3 blockDim(BLOCK_SIZE, BLOCK_SIZE, BLOCK_SIZE);
dim3 gridDim((N + BLOCK_SIZE - 1) / BLOCK_SIZE,
             (N + BLOCK_SIZE - 1) / BLOCK_SIZE,
             (N + BLOCK_SIZE - 1) / BLOCK_SIZE);
stencil_kernel<<<gridDim, blockDim>>>(d_in, d_out, N);
```

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_77.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_78.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_79.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_81.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_83.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_85.png)

### 内核函数步骤

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_87.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_89.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_91.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_93.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_94.png)

以下是内核函数的主要步骤：

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_96.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_98.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_100.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_102.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_104.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_105.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_106.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_107.png)

1.  **计算线程对应的输出索引**：每个线程根据其3D的块索引和线程索引，计算出它负责的3D输出数组中的位置 (i, j, k)。
    ```c
    int i = blockIdx.z * blockDim.z + threadIdx.z;
    int j = blockIdx.y * blockDim.y + threadIdx.y;
    int k = blockIdx.x * blockDim.x + threadIdx.x;
    ```
2.  **边界检查**：确保只计算内部的输出元素（忽略 i, j, k 为 0 或 N-1 的边界）。
    ```c
    if (i >= 1 && i < N-1 && j >= 1 && j < N-1 && k >= 1 && k < N-1) {
        // 进行计算
    }
    ```
3.  **执行模板计算**：对于内部的每个输出元素，计算其值为对应输入元素及其六个邻居（X、Y、Z方向各两个）的线性组合。这里使用常量 `C0` 和 `C1` 作为权重。
    ```c
    int idx = i * N * N + j * N + k; // 3D数组转1D线性索引
    out[idx] = C0 * in[idx]
               + C1 * (in[idx - 1] + in[idx + 1]     // X方向邻居
                     + in[idx - N] + in[idx + N]     // Y方向邻居
                     + in[idx - N*N] + in[idx + N*N]); // Z方向邻居
    ```

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_109.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_110.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_112.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_113.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_114.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_116.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_118.png)

这个基础版本直接访问全局内存，性能有提升空间。接下来，我们探讨如何优化。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_120.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_122.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_123.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_125.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_127.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_129.png)

## 优化：共享内存平铺

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_131.png)

与卷积类似，处理相邻输出元素的线程块会加载许多相同的输入元素，存在数据复用。因此，第一个优化思路是使用共享内存平铺。

### 平铺的挑战

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_133.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_135.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_137.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_139.png)

输入瓦片和输出瓦片的尺寸不同。对于3D七点模板，输入瓦片在每个维度上都比输出瓦片大2（多一层“边界”）。因此，我们需要启动足够多的线程来加载整个输入瓦片，但在计算时，只使用其中一部分线程来计算内部的输出瓦片。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_141.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_143.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_145.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_147.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_148.png)

### 实现思路

1.  **定义瓦片尺寸**：`BLOCK_SIZE` 对应输入瓦片尺寸。输出瓦片尺寸则为 `BLOCK_SIZE - 2`。
2.  **调整网格配置**：计算网格大小时，使用输出瓦片尺寸，以确保有足够的块覆盖所有输出元素。
3.  **加载输入瓦片到共享内存**：
    *   每个线程负责将全局内存中的一个输入元素加载到共享内存的3D数组中。
    *   加载时需要检查该输入索引是否在全局数组边界内。
4.  **同步线程**：确保所有线程完成数据加载。
5.  **计算输出**：
    *   只有位于线程块内部（非边界）的线程才参与计算。
    *   计算时，从共享内存中读取数据，而不是全局内存。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_150.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_152.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_154.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_156.png)

然而，初步测试可能发现性能提升并不明显，甚至可能更慢。这是因为对于较小的瓦片尺寸（如8x8x8），边界元素的比例较高，数据复用的收益被共享内存同步和索引计算的开销所抵消。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_158.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_160.png)

**计算与内存访问比分析**：
*   基础版本：每个线程进行8次操作（2次乘法，6次加法），加载7个浮点数（28字节）。计算内存访问比约为 8 ops / 28 bytes ≈ 0.29 ops/byte。
*   平铺版本（瓦片尺寸T）：每个线程块进行 `8 * (T-2)^3` 次操作，加载 `T^3 * 4` 字节数据。比值约为 `(T-2)^3 / T^3`。当 T=8 时，比值约为 0.84 ops/byte，虽有提升但不显著。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_162.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_164.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_166.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_168.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_170.png)

**结论**：增大瓦片尺寸 `T` 可以提高内部元素的比例，从而提升计算内存访问比。但直接增大 `T` 会受到两个硬件限制：
1.  线程块最大线程数（通常为1024）。
2.  共享内存容量有限，大瓦片会降低占用率（Occupancy）。

## 进一步优化：线程协作与寄存器平铺

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_172.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_174.png)

为了处理更大的输出瓦片而不增加线程数或共享内存使用，我们引入两种技术：线程协作和寄存器平铺。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_176.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_178.png)

### 线程协作

线程协作允许一个线程处理输出瓦片中的多个元素。这样，我们可以用固定数量的线程（例如32x32）处理一个更大的3D输出瓦片（例如32x32x32），只需让每个线程在Z维度上循环处理多个平面。这减少了对边界元素的冗余加载。

### 寄存器平铺

观察3D七点模板的计算特点：当处理一个输出平面时，每个线程需要：
*   **当前平面**的数据：被该平面内多个相邻线程共享。
*   **前一个平面**和**后一个平面**的数据：每个线程只需要自己对应的那个元素，不被其他线程共享。

因此，我们可以优化内存层次的使用：
*   将**当前平面**的数据块放入**共享内存**，供线程间共享访问。
*   将**前一个**和**后一个平面**中每个线程需要的那一个数据元素，保存在该线程的**寄存器**中。
*   随着计算在Z维度上推进，寄存器中的数据在迭代间移动和更新（例如，后一个平面变成当前平面，当前平面变成前一个平面），仅在需要被共享时才写入共享内存。

这种方法被称为**寄存器平铺**，它显著减少了对共享内存的需求，从而允许使用更大的瓦片尺寸或提高占用率。

**寄存器平铺的启示**：我们之前在矩阵乘法中已经无形中使用了寄存器平铺——每个线程将累加结果（C矩阵的一个元素）存储在自己的寄存器中。模板计算中的显式应用加深了我们对这一优化技术的理解。

## 总结

本节课中我们一起学习了模板计算这一重要的并行模式。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_180.png)

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_181.png)

1.  **核心概念**：模板计算是卷积的特例，用于基于邻居更新网格点。我们以实现3D七点模板为例。
2.  **基础实现**：使用3D线程网格，每个线程处理一个输出点，并直接访问全局内存。
3.  **共享内存平铺**：利用数据复用，将输入瓦片加载到共享内存。但受限于瓦片尺寸和硬件限制，收益可能有限。
4.  **高级优化**：
    *   **线程协作**：让一个线程处理多个元素，以增大有效瓦片尺寸，减少边界开销。
    *   **寄存器平铺**：根据数据访问模式，将仅限线程私有的数据保存在寄存器中，将需要线程间共享的数据保存在共享内存中，优化内存层次使用，提升性能。

![](img/9025e0ff3334b83e3b4dc2ec94ddacf2_183.png)

通过结合共享内存平铺、线程协作和寄存器平铺，我们可以构建出高性能的模板计算内核，充分挖掘GPU的并行计算潜力。