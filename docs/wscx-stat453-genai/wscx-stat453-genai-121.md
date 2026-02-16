# 121：L14.4.2 - PyTorch 中的全卷积网络 🧠

![](img/01aeb81254f41e05749e6dc46c33a23a_1.png)

在本节课中，我们将学习如何在 PyTorch 中实现一个全卷积网络。这个网络架构移除了传统的最大池化层和全连接层，仅使用卷积层、ReLU激活层和批归一化层来构建。我们将通过代码示例来理解其设计原理和实现细节。

---

## 📋 概述与背景

上一节我们讨论了全卷积网络的理论概念。本节中，我们将通过具体的 PyTorch 代码来实现它。

全卷积网络的核心思想是简化网络结构。它使用步长为2的卷积层来替代最大池化层进行下采样，并使用全局平均池化层来替代最后的全连接层进行分类。

以下是实现该网络的关键代码结构：

![](img/01aeb81254f41e05749e6dc46c33a23a_3.png)

![](img/01aeb81254f41e05749e6dc46c33a23a_4.png)

![](img/01aeb81254f41e05749e6dc46c33a23a_5.png)

```python
import torch.nn as nn

![](img/01aeb81254f41e05749e6dc46c33a23a_6.png)

class AllConvNet(nn.Module):
    def __init__(self, num_classes=10):
        super(AllConvNet, self).__init__()
        # 网络层定义将在这里
        ...
```

---

## 🏗️ 网络架构详解

网络由多个卷积块堆叠而成。每个块通常包含一个增加通道数的卷积层和一个保持通道数但进行空间下采样的卷积层。

### 卷积层设计

以下是网络中的两种主要卷积操作：

1.  **保持空间尺寸的卷积**：使用 `kernel_size=3, stride=1, padding=1`。其**公式**可表示为：
    `输出尺寸 = (输入尺寸 - kernel_size + 2*padding) / stride + 1`
    当参数如上设置时，输出尺寸与输入尺寸相同。

![](img/01aeb81254f41e05749e6dc46c33a23a_8.png)

2.  **进行下采样的卷积**：使用 `kernel_size=3, stride=2, padding=1`。这会将特征图的高度和宽度减半，替代了最大池化的功能。

### 全局平均池化

在网络的末端，我们使用全局平均池化层替代全连接层。在 PyTorch 中，这可以通过 `nn.AdaptiveAvgPool2d(1)` 实现。该操作对每个通道的所有空间位置（高度和宽度）取平均值，最终得到一个 `1x1` 的特征图。

```python
self.global_avg_pool = nn.AdaptiveAvgPool2d((1, 1))
```

---

## 🔧 代码实现解析

![](img/01aeb81254f41e05749e6dc46c33a23a_10.png)

![](img/01aeb81254f41e05749e6dc46c33a23a_11.png)

以下是构建网络核心部分的一个示例。请注意，为了简化，当卷积核的高度和宽度相同时，我们可以用一个整数（如3）来同时指定两者。

![](img/01aeb81254f41e05749e6dc46c33a23a_13.png)

```python
self.features = nn.Sequential(
    # 第一个卷积块：增加通道数，保持尺寸
    nn.Conv2d(3, 96, kernel_size=3, stride=1, padding=1),
    nn.BatchNorm2d(96),
    nn.ReLU(inplace=True),
    # 下采样卷积：保持通道数，尺寸减半
    nn.Conv2d(96, 96, kernel_size=3, stride=2, padding=1),
    nn.BatchNorm2d(96),
    nn.ReLU(inplace=True),
    # ... 后续可以重复此模式
    # 最后一层卷积：输出通道数等于类别数
    nn.Conv2d(256, num_classes, kernel_size=3, stride=1, padding=1),
)
```

在训练设置方面，我们使用与 VGG16 相同的简单配置（如优化器、学习率等）。由于模型参数更少，结构更简单，其训练时间通常比 VGG16 更短。

![](img/01aeb81254f41e05749e6dc46c33a23a_15.png)

---

![](img/01aeb81254f41e05749e6dc46c33a23a_16.png)

![](img/01aeb81254f41e05749e6dc46c33a23a_17.png)

![](img/01aeb81254f41e05749e6dc46c33a23a_18.png)

## ⏱️ 训练时间与性能

深度学习的训练通常需要较长时间，这与传统处理小型表格数据的统计学方法不同。复杂模型和大数据集可能需要数天甚至数周的训练。

![](img/01aeb81254f41e05749e6dc46c33a23a_20.png)

![](img/01aeb81254f41e05749e6dc46c33a23a_21.png)

对于我们的全卷积网络在 CIFAR-10 数据集上的训练：
*   训练耗时约为 **41 分钟**（作为对比，VGG16 约需90分钟）。
*   最终测试准确率约为 **80%**（VGG16 可达84-85%）。

![](img/01aeb81254f41e05749e6dc46c33a23a_22.png)

![](img/01aeb81254f41e05749e6dc46c33a23a_23.png)

![](img/01aeb81254f41e05749e6dc46c33a23a_24.png)

这个结果表明，全卷积网络在牺牲少量精度的情况下，获得了更高的训练效率。

![](img/01aeb81254f41e05749e6dc46c33a23a_26.png)

---

## 🎯 总结

![](img/01aeb81254f41e05749e6dc46c33a23a_28.png)

![](img/01aeb81254f41e05749e6dc46c33a23a_29.png)

本节课中，我们一起学习了全卷积网络在 PyTorch 中的实现。我们了解到如何仅用卷积层构建网络，用步长为2的卷积替代池化层，以及用全局平均池化替代全连接层。这种设计使网络更简洁，参数更少，训练更快。

![](img/01aeb81254f41e05749e6dc46c33a23a_31.png)

下一节，我们将探讨另一种替代全连接层的方法——使用 `1x1` 卷积，这将是一种参数化的替代方案。