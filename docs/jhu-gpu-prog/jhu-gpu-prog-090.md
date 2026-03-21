# 090：NPP信号处理语法演示 🚀

![](img/0a38a27738143eac88e8973622dbd6ba_0.png)

![](img/0a38a27738143eac88e8973622dbd6ba_2.png)

在本节课中，我们将学习如何使用NVIDIA性能原语（NPP）库中的信号处理模块，具体演示均值滤波操作的语法和流程。我们将通过一个基于真实论坛讨论的示例，了解如何初始化数据、分配设备内存、执行均值计算以及清理资源。

![](img/0a38a27738143eac88e8973622dbd6ba_4.png)

![](img/0a38a27738143eac88e8973622dbd6ba_5.png)

![](img/0a38a27738143eac88e8973622dbd6ba_6.png)

## 概述

![](img/0a38a27738143eac88e8973622dbd6ba_8.png)

与NPP下的MPPI模块类似，本节将快速介绍MPPS语法，并提供一个实际示例。该示例源自NVIDIA开发者工具包论坛中的一个讨论，涉及均值滤波器及其可能引发的问题。尽管滤波器工作正常，但信号可能存在轻微失真，这恰好是一个很好的教学案例。

![](img/0a38a27738143eac88e8973622dbd6ba_10.png)

![](img/0a38a27738143eac88e8973622dbd6ba_11.png)

## 详细步骤

![](img/0a38a27738143eac88e8973622dbd6ba_13.png)

![](img/0a38a27738143eac88e8973622dbd6ba_15.png)

上一节我们介绍了NPP库的概况，本节中我们来看看如何具体使用其信号处理功能进行均值滤波。

![](img/0a38a27738143eac88e8973622dbd6ba_17.png)

![](img/0a38a27738143eac88e8973622dbd6ba_18.png)

首先，我们需要一个指向信号的指针。在本例中，信号是32位浮点类型。

![](img/0a38a27738143eac88e8973622dbd6ba_20.png)

```c
float* hostSignal;
```

![](img/0a38a27738143eac88e8973622dbd6ba_22.png)

![](img/0a38a27738143eac88e8973622dbd6ba_24.png)

我们将随机生成信号数据，在本示例中，信号值全部设为1。然后，我们需要将主机（CPU）上的数据复制到设备（GPU）上。

![](img/0a38a27738143eac88e8973622dbd6ba_25.png)

![](img/0a38a27738143eac88e8973622dbd6ba_27.png)

以下是实现此过程的关键步骤：

![](img/0a38a27738143eac88e8973622dbd6ba_29.png)

![](img/0a38a27738143eac88e8973622dbd6ba_31.png)

1.  **分配设备内存**：使用 `cudaMalloc` 为信号数据分配GPU内存。
2.  **复制数据**：使用 `cudaMemcpy` 将主机上的信号数据复制到刚分配的GPU内存中。

![](img/0a38a27738143eac88e8973622dbd6ba_32.png)

![](img/0a38a27738143eac88e8973622dbd6ba_34.png)

```c
float* deviceSignal;
cudaMalloc((void**)&deviceSignal, signalSize * sizeof(float));
cudaMemcpy(deviceSignal, hostSignal, signalSize * sizeof(float), cudaMemcpyHostToDevice);
```

完成数据复制后，设备上的 `deviceSignal` 指针就包含了所需的浮点数据。

![](img/0a38a27738143eac88e8973622dbd6ba_36.png)

![](img/0a38a27738143eac88e8973622dbd6ba_37.png)

接下来，程序会获取CUDA的内存使用情况。然后，需要创建一个缓冲区（Buffer）来辅助计算。

![](img/0a38a27738143eac88e8973622dbd6ba_38.png)

![](img/0a38a27738143eac88e8973622dbd6ba_40.png)

以下是创建缓冲区所需的步骤：

![](img/0a38a27738143eac88e8973622dbd6ba_41.png)

*   调用 `nppsMeanGetBufferSize_32f` 函数。对于32位浮点复数类型，需要指定信号长度。函数将返回所需的缓冲区大小。在本例中，缓冲区大小与信号长度相同，以确保有足够的内存执行均值操作。缓冲区还有助于处理信号边缘的情况。

![](img/0a38a27738143eac88e8973622dbd6ba_43.png)

![](img/0a38a27738143eac88e8973622dbd6ba_44.png)

现在，我们获得了创建缓冲区所需的统计信息。之前操作的是主机指针，现在需要创建一个设备指针。

![](img/0a38a27738143eac88e8973622dbd6ba_46.png)

![](img/0a38a27738143eac88e8973622dbd6ba_48.png)

```c
size_t bufferSize;
nppsMeanGetBufferSize_32f(signalLength, &bufferSize);
void* deviceBuffer;
cudaMalloc(&deviceBuffer, bufferSize);
```

![](img/0a38a27738143eac88e8973622dbd6ba_50.png)

这就是为什么需要再次使用 `cudaMemcpy`，将主机上为缓冲区分配的内存指针复制到设备指针。这个过程与创建信号本身是并行的：你同时准备了实际信号数据和计算缓冲区。

![](img/0a38a27738143eac88e8973622dbd6ba_52.png)

![](img/0a38a27738143eac88e8973622dbd6ba_54.png)

接下来，我们将执行均值计算操作。

![](img/0a38a27738143eac88e8973622dbd6ba_56.png)

![](img/0a38a27738143eac88e8973622dbd6ba_58.png)

你需要指定相同的数据类型：32位浮点复数。复数对象可以用一个整数部分和一个表示小数位数的数字来指定，例如 `(whole, decimal)`。这类似于浮点数，但能表示更复杂的数值，其可表示的有效数字位数更多。这一点很重要，因为均值结果可能包含多位小数。

![](img/0a38a27738143eac88e8973622dbd6ba_60.png)

![](img/0a38a27738143eac88e8973622dbd6ba_61.png)

调用 `nppsMean_32f` 函数执行计算：

```c
Npp32f meanResult;
nppsMean_32f(deviceSignal, signalLength, &meanResult, (Npp8u*)deviceBuffer);
```

![](img/0a38a27738143eac88e8973622dbd6ba_63.png)

![](img/0a38a27738143eac88e8973622dbd6ba_65.png)

![](img/0a38a27738143eac88e8973622dbd6ba_67.png)

函数参数包括：设备上的信号指针、信号长度、指向输出结果（`meanResult`）的指针，以及你创建的缓冲区。

![](img/0a38a27738143eac88e8973622dbd6ba_69.png)

![](img/0a38a27738143eac88e8973622dbd6ba_71.png)

启动计算后，为了确保操作完成（因为数据量可能导致计算耗时），最好添加 `cudaDeviceSynchronize()` 进行同步。

```c
cudaDeviceSynchronize();
```

![](img/0a38a27738143eac88e8973622dbd6ba_73.png)

![](img/0a38a27738143eac88e8973622dbd6ba_74.png)

![](img/0a38a27738143eac88e8973622dbd6ba_75.png)

之后，可以查看显卡上的可用内存和总内存信息。你还可以打印一些关于操作是否失败的信息。在本例中结果应为成功，之后你可以将结果输出到某种可视化工具或文件中。

![](img/0a38a27738143eac88e8973622dbd6ba_77.png)

最后，需要进行资源清理。

![](img/0a38a27738143eac88e8973622dbd6ba_79.png)

以下是清理步骤：

![](img/0a38a27738143eac88e8973622dbd6ba_80.png)

![](img/0a38a27738143eac88e8973622dbd6ba_81.png)

![](img/0a38a27738143eac88e8973622dbd6ba_83.png)

*   删除主机上的信号指针。
*   释放设备上为信号和缓冲区分配的内存。
*   可以再次获取内存信息。如果这是GPU上唯一运行的任务，释放后的可用内存值与总内存值应该相同。

![](img/0a38a27738143eac88e8973622dbd6ba_85.png)

```c
delete[] hostSignal;
cudaFree(deviceSignal);
cudaFree(deviceBuffer);
```

![](img/0a38a27738143eac88e8973622dbd6ba_86.png)

## 总结

![](img/0a38a27738143eac88e8973622dbd6ba_88.png)

![](img/0a38a27738143eac88e8973622dbd6ba_89.png)

![](img/0a38a27738143eac88e8973622dbd6ba_91.png)

本节课中我们一起学习了使用NPP库进行信号处理的基本流程。我们重点演示了如何为均值滤波操作准备设备内存、创建必要的计算缓冲区、调用NPP函数执行计算，并在最后妥善管理内存资源。通过这个具体的例子，你应该对在GPU上利用NPP进行高效信号处理有了初步的认识。