# P118：L14.3.2.2 - PyTorch 中的 ResNet-34 实现 🧠

![](img/6fc0b4c4fba26a77a100c96c79d18809_1.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_2.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_3.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_4.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_5.png)

在本节课中，我们将学习如何在 PyTorch 中实现残差网络。我们将从零开始构建一个简单的残差块，理解其核心思想，然后介绍 PyTorch 官方社区提供的、更成熟的 ResNet-34 实现。通过对比，你将掌握残差网络的基本原理和实际应用方法。

![](img/6fc0b4c4fba26a77a100c96c79d18809_7.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_8.png)

## 概述：两种实现路径

![](img/6fc0b4c4fba26a77a100c96c79d18809_10.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_11.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_13.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_14.png)

我们将展示两个不同的实现。首先是一个我亲手编写的、较为简单的实现，用于演示上一节视频中讨论的两种残差块。然后，我们将展示 PyTorch 社区提供的、更复杂的 ResNet-34 实现。

![](img/6fc0b4c4fba26a77a100c96c79d18809_16.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_18.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_20.png)

我不会重新运行这个简单的笔记本，因为它耗时不多，且没有必要等待。我将直接展示其结果。

![](img/6fc0b4c4fba26a77a100c96c79d18809_21.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_22.png)

## 第一部分：简单的残差块实现

上一节我们介绍了残差网络的基本概念，本节中我们来看看如何用代码实现一个基础的残差块。这个实现旨在概念验证，因此使用了简单的 MNIST 数据集。

### 数据准备与模型结构

![](img/6fc0b4c4fba26a77a100c96c79d18809_24.png)

以下是导入必要库和准备数据的代码：

```python
import torch
import torch.nn as nn
import torch.nn.functional as F
from torchvision import datasets, transforms

![](img/6fc0b4c4fba26a77a100c96c79d18809_26.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_27.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_28.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_29.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_30.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_31.png)

# 使用 MNIST 数据集，因其简单，适合作为概念验证
transform = transforms.Compose([transforms.ToTensor()])
train_dataset = datasets.MNIST(root='./data', train=True, download=True, transform=transform)
```

![](img/6fc0b4c4fba26a77a100c96c79d18809_33.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_35.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_37.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_39.png)

接下来，我们实现第一种残差块，即输入与残差部分输出维度相同的情况。

![](img/6fc0b4c4fba26a77a100c96c79d18809_41.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_43.png)

### 残差块代码解析

![](img/6fc0b4c4fba26a77a100c96c79d18809_45.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_46.png)

我们使用 `torch.nn.Module` 类来实现一个残差块。该块包含两个卷积层，每个卷积层后接批归一化和 ReLU 激活。

![](img/6fc0b4c4fba26a77a100c96c79d18809_48.png)

```python
class ResidualBlock(nn.Module):
    def __init__(self, in_channels, out_channels, stride=1):
        super(ResidualBlock, self).__init__()
        # 第一个卷积层：in_channels -> out_channels
        self.conv1 = nn.Conv2d(in_channels, out_channels, kernel_size=3, stride=stride, padding=1, bias=False)
        self.bn1 = nn.BatchNorm2d(out_channels)
        self.relu = nn.ReLU(inplace=True)  # inplace=True 表示原地操作，节省内存
        # 第二个卷积层：out_channels -> out_channels
        self.conv2 = nn.Conv2d(out_channels, out_channels, kernel_size=3, stride=1, padding=1, bias=False)
        self.bn2 = nn.BatchNorm2d(out_channels)

        # 捷径连接：如果输入输出维度或步长不同，需要1x1卷积调整
        self.shortcut = nn.Sequential()
        if stride != 1 or in_channels != out_channels:
            self.shortcut = nn.Sequential(
                nn.Conv2d(in_channels, out_channels, kernel_size=1, stride=stride, bias=False),
                nn.BatchNorm2d(out_channels)
            )

    def forward(self, x):
        identity = x  # 保存输入作为捷径
        out = self.conv1(x)
        out = self.bn1(out)
        out = self.relu(out)
        out = self.conv2(out)
        out = self.bn2(out)
        out += self.shortcut(identity)  # 加入捷径连接
        out = self.relu(out)  # 相加后再激活
        return out
```

![](img/6fc0b4c4fba26a77a100c96c79d18809_50.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_51.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_52.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_54.png)

**代码要点说明：**
*   `inplace=True`：这是一个优化选项，意味着 ReLU 激活函数会直接修改输入张量，而不是创建新的张量副本，从而节省内存。虽然结果相同，但效率稍高。
*   **捷径连接**：这是残差网络的核心。在 `forward` 函数中，我们将原始输入 `identity` 与经过两个卷积层处理后的输出 `out` 相加。
*   **维度匹配**：如果输入和输出的通道数或空间尺寸（通过 `stride` 改变）不同，则不能直接相加。我们通过一个包含 1x1 卷积和批归一化的 `shortcut` 序列来调整 `identity` 的维度，使其与 `out` 匹配。

![](img/6fc0b4c4fba26a77a100c96c79d18809_56.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_58.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_59.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_61.png)

### 构建简单网络并训练

![](img/6fc0b4c4fba26a77a100c96c79d18809_63.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_64.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_66.png)

使用上述残差块构建一个包含两个块的小网络，并添加一个全连接层作为分类器。

![](img/6fc0b4c4fba26a77a100c96c79d18809_68.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_70.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_72.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_74.png)

```python
class SimpleResNet(nn.Module):
    def __init__(self, num_classes=10):
        super(SimpleResNet, self).__init__()
        self.in_channels = 1  # MNIST 是单通道图像
        # 第一个残差块：1 -> 4 通道
        self.layer1 = self._make_layer(4, stride=1)
        # 第二个残差块：4 -> 8 通道
        self.layer2 = self._make_layer(8, stride=2)
        self.linear = nn.Linear(8 * 7 * 7, num_classes)  # 经过两次下采样后尺寸为 7x7

    def _make_layer(self, out_channels, stride):
        return ResidualBlock(self.in_channels, out_channels, stride)

    def forward(self, x):
        x = self.layer1(x)
        x = self.layer2(x)
        x = x.view(x.size(0), -1)  # 展平
        x = self.linear(x)
        return x

![](img/6fc0b4c4fba26a77a100c96c79d18809_76.png)

# 训练模型（此处省略训练循环细节）
model = SimpleResNet()
# ... 训练代码 ...
```
训练后，该简单模型在测试集上达到了约 92% 的准确率。这验证了残差块的基本功能。

![](img/6fc0b4c4fba26a77a100c96c79d18809_78.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_79.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_80.png)

**调试技巧**：在确定全连接层输入大小时，如果不确定张量经过卷积层后的尺寸，一个实用的方法是在 `forward` 函数中临时添加 `print(x.size())` 语句来查看。

![](img/6fc0b4c4fba26a77a100c96c79d18809_82.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_84.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_85.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_87.png)

## 第二部分：可复用的残差块与维度变化

![](img/6fc0b4c4fba26a77a100c96c79d18809_89.png)

现在，我们聚焦于更一般化的情况，即残差块中可能改变特征图尺寸和通道数。我们将实现一个更通用的、可复用的残差块单元。

![](img/6fc0b4c4fba26a77a100c96c79d18809_90.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_91.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_93.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_94.png)

### 通用残差块实现

![](img/6fc0b4c4fba26a77a100c96c79d18809_96.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_97.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_98.png)

这个实现允许我们指定中间通道数（例如实现“瓶颈”结构）和步长。

![](img/6fc0b4c4fba26a77a100c96c79d18809_100.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_101.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_103.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_105.png)

```python
class GeneralResidualBlock(nn.Module):
    def __init__(self, in_channels, mid_channels, out_channels, stride=1):
        super(GeneralResidualBlock, self).__init__()
        # 第一个卷积层，可能改变尺寸
        self.conv1 = nn.Conv2d(in_channels, mid_channels, kernel_size=3, stride=stride, padding=1, bias=False)
        self.bn1 = nn.BatchNorm2d(mid_channels)
        self.relu = nn.ReLU(inplace=True)
        # 第二个卷积层
        self.conv2 = nn.Conv2d(mid_channels, out_channels, kernel_size=3, stride=1, padding=1, bias=False)
        self.bn2 = nn.BatchNorm2d(out_channels)

        # 捷径连接
        self.shortcut = nn.Sequential()
        if stride != 1 or in_channels != out_channels:
            self.shortcut = nn.Sequential(
                nn.Conv2d(in_channels, out_channels, kernel_size=1, stride=stride, bias=False),
                nn.BatchNorm2d(out_channels)
            )

    def forward(self, x):
        identity = x
        out = self.conv1(x)
        out = self.bn1(out)
        out = self.relu(out)
        out = self.conv2(out)
        out = self.bn2(out)
        out += self.shortcut(identity)
        out = self.relu(out)
        return out
```

![](img/6fc0b4c4fba26a77a100c96c79d18809_107.png)

### 使用通用块构建网络

![](img/6fc0b4c4fba26a77a100c96c79d18809_108.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_109.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_110.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_111.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_112.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_113.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_115.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_117.png)

我们可以用这个通用块轻松构建更深的网络。例如，构建一个从 1 通道到 8 通道再到 32 通道的网络，并伴随两次下采样。

![](img/6fc0b4c4fba26a77a100c96c79d18809_119.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_120.png)

```python
class DeeperResNet(nn.Module):
    def __init__(self, num_classes=10):
        super(DeeperResNet, self).__init__()
        # 块1: 1 -> 8 通道，步长2下采样 (28x28 -> 14x14)
        self.block1 = GeneralResidualBlock(1, 4, 8, stride=2)
        # 块2: 8 -> 32 通道，步长2下采样 (14x14 -> 7x7)
        self.block2 = GeneralResidualBlock(8, 16, 32, stride=2)
        self.linear = nn.Linear(32 * 7 * 7, num_classes)

    def forward(self, x):
        x = self.block1(x)
        x = self.block2(x)
        x = x.view(x.size(0), -1)
        x = self.linear(x)
        return x
```
这个网络的性能优于之前的简单实现。但残差网络的真正优势在于构建非常深的网络（如34层、50层）。

![](img/6fc0b4c4fba26a77a100c96c79d18809_122.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_123.png)

## 第三部分：PyTorch 官方的 ResNet-34 实现 🏗️

![](img/6fc0b4c4fba26a77a100c96c79d18809_124.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_125.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_126.png)

对于像 ResNet-34 这样的深层网络，从零开始实现既复杂又容易出错。在实践中，我们通常直接使用经过充分测试的官方或社区实现。

![](img/6fc0b4c4fba26a77a100c96c79d18809_128.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_129.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_130.png)

### 使用现有实现

![](img/6fc0b4c4fba26a77a100c96c79d18809_132.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_133.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_134.png)

PyTorch 的 `torchvision.models` 模块提供了 ResNet 的各种版本（如18、34、50、101层）。我们也可以参考其源码来学习。以下是如何使用和简要分析：

![](img/6fc0b4c4fba26a77a100c96c79d18809_136.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_137.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_138.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_139.png)

```python
import torchvision.models as models
# 直接加载预训练模型
resnet34 = models.resnet34(pretrained=True)
# 或者，查看和调整其结构以适应CIFAR-10（32x32图像）
# 通常需要修改第一层卷积和最后的全连接层
```

![](img/6fc0b4c4fba26a77a100c96c79d18809_141.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_143.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_145.png)

在配套的笔记本中，我复制并简化了 PyTorch 官方的 ResNet 构建代码。它定义了 `Bottleneck` 块（用于更深的 ResNet-50/101等）和基本的 `BasicBlock`（用于 ResNet-18/34），并通过一个 `_make_layer` 函数来堆叠多个块。

![](img/6fc0b4c4fba26a77a100c96c79d18809_147.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_148.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_150.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_151.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_152.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_154.png)

**核心结构要点：**
*   **初始层**：一个卷积层接批归一化和 ReLU，以及一个最大池化层。
*   **四个主要阶段**：每个阶段包含若干残差块，逐步降低空间分辨率并增加通道数（例如，通道数从64增加到512）。
*   **分类器**：全局平均池化层后接一个全连接层。

![](img/6fc0b4c4fba26a77a100c96c79d18809_156.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_157.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_159.png)

### 在 CIFAR-10 上训练 ResNet-34

![](img/6fc0b4c4fba26a77a100c96c79d18809_161.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_162.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_164.png)

我们将图像大小调整为 70x70 以适应 ResNet 的输入习惯（原设计用于 ImageNet 的 224x224）。使用与 VGG16 相同的训练流程。

![](img/6fc0b4c4fba26a77a100c96c79d18809_166.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_167.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_169.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_170.png)

```python
# 示例：修改第一层以适应 CIFAR-10（3通道，较小卷积核和步长）
resnet34.conv1 = nn.Conv2d(3, 64, kernel_size=3, stride=1, padding=1, bias=False)
resnet34.maxpool = nn.Identity()  # 移除初始的最大池化，因为图像已很小
num_ftrs = resnet34.fc.in_features
resnet34.fc = nn.Linear(num_ftrs, 10)  # CIFAR-10 有10类
```
训练后，ResNet-34 在 CIFAR-10 上获得了约 48% 的准确率。虽然与 VGG16 结果相近，但请注意，即使在图像更大的情况下，其训练时间（62分钟）也短于 VGG16（90分钟），这体现了残差连接在优化深度网络时的效率。模型也存在过拟合，可以考虑添加 Dropout 等正则化方法。

![](img/6fc0b4c4fba26a77a100c96c79d18809_172.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_174.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_176.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_177.png)

分析混淆矩阵可以发现，模型主要在动物类别（如鹿、狗、猫、鸟）之间产生混淆，这是细粒度图像分类的常见挑战。

![](img/6fc0b4c4fba26a77a100c96c79d18809_179.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_181.png)

## 总结与实践建议

![](img/6fc0b4c4fba26a77a100c96c79d18809_183.png)

本节课中我们一起学习了残差网络在 PyTorch 中的实现。

![](img/6fc0b4c4fba26a77a100c96c79d18809_185.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_186.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_187.png)

我们从零开始构建了简单的残差块，理解了其核心公式 **`输出 = F(x) + x`** 以及如何通过 `shortcut` 处理维度变化。然后，我们探讨了如何构建更通用的残差块。最后，我们介绍了如何利用 PyTorch 官方实现来使用成熟的 ResNet-34 模型，并在 CIFAR-10 数据集上进行了训练评估。

![](img/6fc0b4c4fba26a77a100c96c79d18809_188.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_189.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_190.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_191.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_192.png)

**给初学者的实践建议：**
*   **学习目的**：为了理解原理，可以从头实现简单的残差块（如2-4层）。
*   **实际项目**：当需要 ResNet-34 或更深的网络时，强烈建议直接使用 `torchvision.models` 中的现有实现或从论文作者的官方 GitHub 代码库进行适配。这可以节省大量时间，并避免因自己实现复杂网络而引入的错误。
*   **调整网络**：使用现有模型时，通常需要修改第一层（输入通道、卷积核）和最后一层（输出类别数）以适应你的数据集。

![](img/6fc0b4c4fba26a77a100c96c79d18809_194.png)

![](img/6fc0b4c4fba26a77a100c96c79d18809_196.png)

通过本教程，你应该已经掌握了残差网络的基本实现逻辑，并知道了在实战中如何高效地利用强大的现有模型。