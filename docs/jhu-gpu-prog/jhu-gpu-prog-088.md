# 088：NPP图像处理代码演示 🖼️

![](img/bd36fc824af76502dbc9f58381847277_1.png)

![](img/bd36fc824af76502dbc9f58381847277_2.png)

在本节课中，我们将通过一个具体的代码示例，快速了解NVIDIA性能原语（NPP）库中核心的**方框滤波器（Box Filter）** 的语法和使用方法。我们将学习如何加载图像、在GPU上分配内存、配置滤波器参数、执行处理，并最终保存结果。

![](img/bd36fc824af76502dbc9f58381847277_4.png)

![](img/bd36fc824af76502dbc9f58381847277_6.png)

---

![](img/bd36fc824af76502dbc9f58381847277_7.png)

## 概述

![](img/bd36fc824af76502dbc9f58381847277_9.png)

![](img/bd36fc824af76502dbc9f58381847277_11.png)

我们将逐步解析一个使用NPP库进行图像滤波的完整流程。这个过程涵盖了从主机（CPU）内存准备到设备（GPU）内存操作，再到滤波执行和结果回传的各个环节。核心概念将通过**代码片段**进行说明。

---

![](img/bd36fc824af76502dbc9f58381847277_13.png)

![](img/bd36fc824af76502dbc9f58381847277_14.png)

![](img/bd36fc824af76502dbc9f58381847277_15.png)

## 主机内存准备与图像加载

![](img/bd36fc824af76502dbc9f58381847277_17.png)

首先，我们需要在主机端准备一个内存指针作为图像数据的源。由于我们处理的是灰度图像，因此数据格式应为**8位无符号整数（8-bit unsigned）**，并且只有一个通道。

![](img/bd36fc824af76502dbc9f58381847277_19.png)

以下是相关的代码概念：
```c
// 伪代码：声明一个指向8位无符号单通道数据的主机指针
unsigned char* host_src_ptr;
```

![](img/bd36fc824af76502dbc9f58381847277_20.png)

我使用了FreeImage库的能力来加载图像。该功能会根据需要处理图像，例如将RGB彩色图像转换为灰度图。

![](img/bd36fc824af76502dbc9f58381847277_22.png)

![](img/bd36fc824af76502dbc9f58381847277_23.png)

```c
// 伪代码：使用FreeImage加载图像并转换为灰度
LoadImageToHostMemory("input.jpg", &host_src_ptr, FORMAT_GRAYSCALE);
```

![](img/bd36fc824af76502dbc9f58381847277_25.png)

---

![](img/bd36fc824af76502dbc9f58381847277_27.png)

## 创建设备内存指针

接下来，我们需要在GPU设备上创建对应的内存指针。请注意，这里的API调用指定了`NPP`，而上一步的主机端操作可能涉及`CPU`。关键是要确保通道数和位深度与源图像一致。

![](img/bd36fc824af76502dbc9f58381847277_29.png)

![](img/bd36fc824af76502dbc9f58381847277_30.png)

```c
// 伪代码：在设备上分配内存并复制主机数据
Npp8u* device_src_ptr;
cudaMalloc(&device_src_ptr, image_size);
cudaMemcpy(device_src_ptr, host_src_ptr, image_size, cudaMemcpyHostToDevice);
```

![](img/bd36fc824af76502dbc9f58381847277_31.png)

![](img/bd36fc824af76502dbc9f58381847277_32.png)

![](img/bd36fc824af76502dbc9f58381847277_33.png)

这个步骤封装了内存管理的复杂性，你也可以选择手动管理，但NPP提供了便捷的接口。

![](img/bd36fc824af76502dbc9f58381847277_35.png)

---

![](img/bd36fc824af76502dbc9f58381847277_36.png)

## 配置方框滤波器

![](img/bd36fc824af76502dbc9f58381847277_38.png)

![](img/bd36fc824af76502dbc9f58381847277_39.png)

现在需要设置滤波器。方框滤波器在一个**核（Kernel）** 上操作，在经典的图像处理中，核是一个矩阵。这里我们使用一个5x5的核。

![](img/bd36fc824af76502dbc9f58381847277_41.png)

首先，需要定义核的尺寸（即掩码大小）：
```c
// 定义滤波器掩码（核）大小为5x5
NppiSize kernelSize = {5, 5};
```

![](img/bd36fc824af76502dbc9f58381847277_42.png)

接着，需要指定源图像的尺寸。你可以根据输入图像动态获取，也可以硬编码。
```c
// 获取或定义源图像尺寸
NppiSize srcSize = {width, height};
```

![](img/bd36fc824af76502dbc9f58381847277_44.png)

![](img/bd36fc824af76502dbc9f58381847277_45.png)

然后，定义操作的起始点（`oSrcOffset`）。如果你不希望从图像的左上角像素开始滤波，可以在这里指定不同的X和Y坐标值。
```c
// 定义操作起始偏移量（例如从(0,0)开始）
NppiPoint oSrcOffset = {0, 0};
```

![](img/bd36fc824af76502dbc9f58381847277_47.png)

---

![](img/bd36fc824af76502dbc9f58381847277_48.png)

## 定义感兴趣区域（ROI）

![](img/bd36fc824af76502dbc9f58381847277_50.png)

![](img/bd36fc824af76502dbc9f58381847277_51.png)

除了源图像，还需要定义**感兴趣区域（Region of Interest, ROI）**。这允许你只处理大图像中的一个子区域。

![](img/bd36fc824af76502dbc9f58381847277_52.png)

![](img/bd36fc824af76502dbc9f58381847277_54.png)

```c
// 定义ROI的大小，它不能大于源图像
NppiSize oSizeROI = {roi_width, roi_height};
```

---

![](img/bd36fc824af76502dbc9f58381847277_56.png)

![](img/bd36fc824af76502dbc9f58381847277_57.png)

## 指定输出目标

你必须告诉滤波器将处理结果存放在哪里。因此，需要提供指向另一块设备内存的指针，并且这块内存的大小应与上面定义的`oSizeROI`一致。

![](img/bd36fc824af76502dbc9f58381847277_59.png)

```c
// 为输出结果分配设备内存
Npp8u* device_dst_ptr;
cudaMalloc(&device_dst_ptr, roi_size);
```

![](img/bd36fc824af76502dbc9f58381847277_60.png)

![](img/bd36fc824af76502dbc9f58381847277_61.png)

![](img/bd36fc824af76502dbc9f58381847277_62.png)

---

![](img/bd36fc824af76502dbc9f58381847277_64.png)

## 设置锚点

![](img/bd36fc824af76502dbc9f58381847277_66.png)

![](img/bd36fc824af76502dbc9f58381847277_68.png)

最后，你需要提供一个**锚点（Anchor）**。锚点是核内所有操作的参考中心点。

![](img/bd36fc824af76502dbc9f58381847277_70.png)

例如，如果你希望在整个ROI上执行操作，通常会将锚点设置为核的中心像素（对于5x5核，锚点可能是(2,2)），并将ROI的大小设置为整个图像的尺寸。

```c
// 定义锚点（通常为核的中心）
NppiPoint anchor = {kernelSize.width / 2, kernelSize.height / 2};
```

![](img/bd36fc824af76502dbc9f58381847277_72.png)

![](img/bd36fc824af76502dbc9f58381847277_73.png)

---

![](img/bd36fc824af76502dbc9f58381847277_75.png)

## 执行滤波与边界处理

![](img/bd36fc824af76502dbc9f58381847277_77.png)

![](img/bd36fc824af76502dbc9f58381847277_78.png)

![](img/bd36fc824af76502dbc9f58381847277_80.png)

完成所有配置后，可以进行错误检查，并运行NPP的方框滤波器函数。这里我们处理的是**8位无符号、单通道**的数据。

```c
// 执行带边界处理的方框滤波
nppiFilterBoxBorder_8u_C1R(device_src_ptr, srcPitch, srcSize, oSrcOffset,
                           device_dst_ptr, dstPitch, oSizeROI,
                           kernelSize, anchor, NPP_BORDER_REPLICATE);
```

![](img/bd36fc824af76502dbc9f58381847277_82.png)

![](img/bd36fc824af76502dbc9f58381847277_83.png)

方框滤波器会产生平滑效果。但是，当核在图像边缘操作时，可能会访问到不存在的像素。为了避免这种情况，我们使用**边界（Border）** 处理模式（如`NPP_BORDER_REPLICATE`）。这样，对于边缘像素，滤波器会复制最近的边界像素值，而不是用零填充，这在灰度图像中能产生更好的视觉效果。

![](img/bd36fc824af76502dbc9f58381847277_85.png)

---

![](img/bd36fc824af76502dbc9f58381847277_87.png)

![](img/bd36fc824af76502dbc9f58381847277_89.png)

## 将结果复制回主机并保存

![](img/bd36fc824af76502dbc9f58381847277_91.png)

滤波完成后，结果存储在设备内存的`device_dst_ptr`中。我们需要在主机上创建对应的内存对象来接收它。

![](img/bd36fc824af76502dbc9f58381847277_93.png)

![](img/bd36fc824af76502dbc9f58381847277_94.png)

```c
// 在主机上分配内存用于接收结果
unsigned char* host_dst_ptr = (unsigned char*)malloc(roi_size);
```

![](img/bd36fc824af76502dbc9f58381847277_96.png)

![](img/bd36fc824af76502dbc9f58381847277_98.png)

然后，使用CUDA的内存复制功能将数据从设备传回主机。这里可以指定`pitch`（步长）来控制复制图像的区域，在我们的例子中，从(0,0)像素开始。

![](img/bd36fc824af76502dbc9f58381847277_100.png)

```c
// 将结果从设备内存复制回主机内存
cudaMemcpy2D(host_dst_ptr, dstPitch,
             device_dst_ptr, deviceDstPitch,
             roi_width, roi_height,
             cudaMemcpyDeviceToHost);
```

![](img/bd36fc824af76502dbc9f58381847277_101.png)

![](img/bd36fc824af76502dbc9f58381847277_103.png)

最后，再次利用FreeImage等工具库将处理后的图像数据保存为文件，并打印保存成功的消息。

![](img/bd36fc824af76502dbc9f58381847277_105.png)

---

## 释放资源

![](img/bd36fc824af76502dbc9f58381847277_107.png)

![](img/bd36fc824af76502dbc9f58381847277_108.png)

作为良好的编程实践，需要释放之前分配的**设备内存指针**。

```c
// 释放设备内存
cudaFree(device_src_ptr);
cudaFree(device_dst_ptr);
```

![](img/bd36fc824af76502dbc9f58381847277_110.png)

![](img/bd36fc824af76502dbc9f58381847277_111.png)

你通常不需要手动释放主机指针（如果它们由FreeImage管理），但需要注意，如果你在其他地方（例如另一个内核或NPP进程）定义了指向设备内存的指针并分配了内存，就必须确保在适当的时候释放它们，否则其他进程将无法访问这些资源。

![](img/bd36fc824af76502dbc9f58381847277_112.png)

![](img/bd36fc824af76502dbc9f58381847277_113.png)

---

## 总结

![](img/bd36fc824af76502dbc9f58381847277_115.png)

![](img/bd36fc824af76502dbc9f58381847277_116.png)

![](img/bd36fc824af76502dbc9f58381847277_117.png)

本节课我们一起学习了使用NPP库执行图像方框滤波的完整流程。我们从**加载图像到主机内存**开始，然后**在GPU上分配内存**并传输数据。接着，我们详细配置了滤波器的**核大小、ROI、锚点和边界处理模式**。之后，我们**执行了滤波操作**，并探讨了边界处理的重要性。最后，我们**将结果复制回主机、保存图像，并释放了设备内存**。通过这个示例，你应该对如何利用NPP进行高效的GPU图像处理有了一个直观的认识。