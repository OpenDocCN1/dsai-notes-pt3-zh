# GPU计算：P3：多维网格与数据 🚀

在本节课中，我们将要学习如何在GPU上处理多维数据。我们将探讨如何创建多维线程网格，以及如何高效地存储和访问多维数据。通过三个具体的例子——RGB图像转灰度图、图像模糊和矩阵乘法——我们将掌握这些核心概念。

上一节我们介绍了数据并行编程的基本概念，并使用向量加法作为例子。本节中我们来看看如何处理更复杂的多维数据。

## 多维网格与数据布局

许多应用中的数据是多维的，例如图像（二维）或矩阵。为了高效地处理这类数据，CUDA支持创建多维的线程网格。这简化了线程索引的计算，使代码更直观。

### 创建多维网格

在CUDA中，我们使用 `dim3` 类型来定义网格和线程块的维度。`dim3` 是一个包含x、y、z三个整数的结构体。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_1.png)

以下是配置一个二维网格的示例代码：

```cpp
// 定义每个线程块的维度：32x32 个线程
dim3 numThreadsPerBlock(32, 32); // z维度默认为1

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_3.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_5.png)

// 计算网格中线程块的数量
int width = 1024; // 图像宽度
int height = 768; // 图像高度
dim3 numBlocks((width + numThreadsPerBlock.x - 1) / numThreadsPerBlock.x,
               (height + numThreadsPerBlock.y - 1) / numThreadsPerBlock.y);

// 启动内核
myKernel<<<numBlocks, numThreadsPerBlock>>>(...);
```

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_7.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_9.png)

**核心概念**：`dim3` 类型用于定义多维网格和线程块。`numBlocks` 和 `numThreadsPerBlock` 的x、y分量分别对应网格的宽度和高度。

### 线程索引计算

在内核函数中，每个线程可以通过内置变量确定自己在多维网格中的全局位置。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_11.png)

以下是计算线程对应行和列的代码：

```cpp
__global__ void myKernel(...) {
    // 计算线程对应的输出行和列
    unsigned int row = blockIdx.y * blockDim.y + threadIdx.y;
    unsigned int col = blockIdx.x * blockDim.x + threadIdx.x;
    // ... 后续处理
}
```

**核心概念**：`blockIdx` 和 `threadIdx` 是 `dim3` 类型，分别表示线程块在网格中的索引和线程在线程块中的索引。`blockDim` 表示线程块的维度。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_13.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_14.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_15.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_17.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_18.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_20.png)

### 多维数据的内存布局

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_22.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_24.png)

在C/C++中，动态分配的多维数组在内存中通常以**行主序**方式连续存储。这意味着数据的第一行先被存储，接着是第二行，依此类推。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_26.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_27.png)

给定行号 `row` 和列号 `col`，在一维数组中的索引计算公式为：

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_29.png)

**公式**：`index = row * width + col`

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_31.png)

其中 `width` 是二维数据的宽度（列数）。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_33.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_35.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_37.png)

## 示例一：RGB图像转灰度图 🖼️➡️⚫⚪

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_39.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_40.png)

在这个例子中，我们将彩色图像（每个像素包含红、绿、蓝三个通道）转换为灰度图像（每个像素一个强度值）。

### 并行化策略

一个直观的并行化方法是**为图像中的每个像素分配一个线程**。每个线程负责读取对应像素的RGB值，计算加权平均值，并将结果写入输出数组。

以下是RGB转灰度内核的实现：

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_42.png)

```cpp
__global__ void rgbToGrayKernel(unsigned char* red, unsigned char* green,
                                unsigned char* blue, unsigned char* gray,
                                int width, int height) {
    // 1. 计算线程对应的像素位置
    unsigned int row = blockIdx.y * blockDim.y + threadIdx.y;
    unsigned int col = blockIdx.x * blockDim.x + threadIdx.x;

    // 2. 边界检查：确保线程在图像范围内
    if (row < height && col < width) {
        // 3. 计算一维数组索引
        unsigned int idx = row * width + col;

        // 4. 执行RGB到灰度的转换（加权平均）
        // 常见权重：红色30%，绿色60%，蓝色10%
        gray[idx] = (unsigned char)(0.3f * red[idx] +
                                    0.6f * green[idx] +
                                    0.1f * blue[idx]);
    }
}
```

**核心概念**：边界检查至关重要，因为启动的线程总数可能略多于实际像素数（由于网格/块尺寸取整）。只有位于有效图像范围内的线程才应执行计算。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_44.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_46.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_47.png)

## 示例二：图像模糊 🔍➡️🌫️

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_49.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_50.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_51.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_52.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_54.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_55.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_57.png)

图像模糊操作中，每个输出像素是其周围一个区域（例如3x3、5x5）内输入像素的平均值。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_59.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_61.png)

### 并行化策略

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_63.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_65.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_67.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_69.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_71.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_72.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_73.png)

我们同样**为每个输出像素分配一个线程**。每个线程需要读取其对应输入像素及其周围多个像素的值，计算平均值，然后写入输出。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_75.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_76.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_78.png)

以下是图像模糊内核的实现：

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_79.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_81.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_82.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_84.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_85.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_87.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_89.png)

```cpp
#define BLUR_SIZE 1 // 模糊半径，例如1表示3x3区域

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_91.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_93.png)

__global__ void blurKernel(unsigned char* image, unsigned char* blurred,
                           int width, int height) {
    // 计算线程对应的输出像素位置
    int outRow = blockIdx.y * blockDim.y + threadIdx.y;
    int outCol = blockIdx.x * blockDim.x + threadIdx.x;

    // 边界检查：输出位置必须在图像内
    if (outRow < height && outCol < width) {
        int sum = 0;
        int pixelCount = 0;

        // 遍历以(outRow, outCol)为中心的模糊区域
        for (int inRow = outRow - BLUR_SIZE; inRow <= outRow + BLUR_SIZE; ++inRow) {
            for (int inCol = outCol - BLUR_SIZE; inCol <= outCol + BLUR_SIZE; ++inCol) {
                // 关键：对每次输入访问进行边界检查！
                if (inRow >= 0 && inRow < height && inCol >= 0 && inCol < width) {
                    int idx = inRow * width + inCol;
                    sum += image[idx];
                    pixelCount++;
                }
            }
        }
        // 计算平均值并写入输出
        int outIdx = outRow * width + outCol;
        blurred[outIdx] = (unsigned char)(sum / pixelCount);
    }
}
```

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_95.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_97.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_98.png)

**重要规则**：在并行编程中，**每次内存访问都应有对应的边界检查**。对于模糊操作，即使输出像素在边界内，其读取的周围输入像素也可能越界，必须进行检查。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_100.png)

## 示例三：矩阵乘法 ➕✖️➡️📈

矩阵乘法 C = A × B 中，输出矩阵C的每个元素是矩阵A的一行与矩阵B的一列的点积。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_102.png)

### 并行化策略

最直接的并行化方法是**为输出矩阵C的每个元素分配一个线程**。每个线程负责计算一个点积。

以下是矩阵乘法内核的实现（假设A、B、C都是N x N矩阵）：

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_104.png)

```cpp
__global__ void matrixMulKernel(float* A, float* B, float* C, int N) {
    // 计算线程对应的输出元素位置
    unsigned int row = blockIdx.y * blockDim.y + threadIdx.y;
    unsigned int col = blockIdx.x * blockDim.x + threadIdx.x;

    // 边界检查
    if (row < N && col < N) {
        float sum = 0.0f;
        // 执行点积计算
        for (int i = 0; i < N; ++i) {
            sum += A[row * N + i] * B[i * N + col];
        }
        // 将结果写入输出矩阵
        C[row * N + col] = sum;
    }
}
```

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_106.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_107.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_109.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_110.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_112.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_114.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_115.png)

**性能提示**：这个基础实现（通常称为“朴素”矩阵乘法）在GPU上已经能带来显著加速（例如数十到上百倍），因为它暴露了巨大的数据并行性（N²个独立的点积计算）。后续课程将介绍如何通过共享内存等技术进一步优化。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_117.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_119.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_120.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_122.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_124.png)

## 总结与关键要点 🎯

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_126.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_128.png)

本节课中我们一起学习了GPU上处理多维数据的核心方法。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_130.png)

以下是关键知识点总结：

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_132.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_133.png)

1.  **多维网格**：使用 `dim3` 类型定义网格(`numBlocks`)和线程块(`numThreadsPerBlock`)的维度，简化了多维数据的处理。
2.  **索引计算**：线程通过 `blockIdx`, `threadIdx`, `blockDim` 等内置变量计算其在多维数据中的全局位置（行、列）。
3.  **数据布局**：理解C语言中多维数据以行主序连续存储至关重要，索引转换公式为 `index = row * width + col`。
4.  **边界检查**：这是并行编程中最容易出错的部分之一。必须确保每个线程的内存读写操作都在数组有效范围内。**规则是：每次内存访问都应有对应的索引边界检查。**
5.  **并行策略**：对于像图像处理（像素级操作）和矩阵乘法（元素级操作）这类问题，常见的模式是“一个输出元素一个线程”。
6.  **性能**：即使使用这些基础的多维网格技术，也能在GPU上获得相对于CPU的显著性能提升，因为GPU能够同时启动成千上万个线程来利用数据并行性。

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_135.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_136.png)

![](img/efca0f9f3448fd2be3ffe506fa0fb9d9_138.png)

通过RGB转灰度、图像模糊和矩阵乘法这三个例子，我们实践了从问题分析、并行策略制定到CUDA内核实现的全过程。掌握这些基础是进行更复杂GPU编程的基石。