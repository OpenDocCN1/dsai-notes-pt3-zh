# 109：L13.9.3 - PyTorch 中的 AlexNet 🧠



在本节课中，我们将学习如何在 PyTorch 中实现 AlexNet 架构，并将其应用于 CIFAR-10 数据集。我们将了解 AlexNet 的基本结构、针对小尺寸图像的调整方法、数据预处理技巧，并观察训练过程中的一些有趣现象。




## 📊 AlexNet 架构回顾




上一节我们介绍了 LeNet，本节中我们来看看更复杂的 AlexNet。AlexNet 是一个经典的卷积神经网络架构。


其输入图像尺寸为 **224 x 224 x 3**。经过第一层卷积后，通道数变为 96，随后是 256 通道。原论文中此处应为 384 通道，图中可能是个笔误，接着又是 384 通道，然后是 256 通道。最后是三个巨大的全连接层：**4096 -> 4096 -> 1000**（对应 ImageNet 的 1000 个类别）。


在本实现中，我们将第一层的通道数从 96 缩减到了 64，但总体上保持了相同的架构。请注意，我们并非在 ImageNet 上训练，而是在尺寸更小的 CIFAR-10 图像上训练。因此，我们对网络进行了一些小调整，以适应更小的输入图像尺寸。



## 🔧 针对 CIFAR-10 的调整



由于 CIFAR-10 原始图像尺寸为 32x32，直接输入 AlexNet 会导致特征图尺寸过早归零，网络无法工作。因此，我们需要对输入图像进行预处理。






以下是数据预处理的关键步骤：



*   **图像放大**：首先将 CIFAR-10 图像从 32x32 放大到 70x70。
*   **随机裁剪**：在训练时，从 70x70 的图像中随机裁剪出一个 64x64 的区域。这有助于增强模型对微小扰动的鲁棒性，防止过拟合。
*   **中心裁剪**：在验证和测试时，我们使用中心裁剪，而不是随机裁剪。因为评估模型在新数据上的性能时，不应引入随机性。
*   **归一化**：使用 `transforms.Normalize` 将像素值归一化到 [-1, 1] 的范围内。对于 RGB 三通道图像，每个通道的均值和标准差都设为 `(0.5, 0.5, 0.5)`。






```python
# 训练数据转换
train_transform = transforms.Compose([
    transforms.Resize(70),
    transforms.RandomCrop(64),
    transforms.ToTensor(),
    transforms.Normalize((0.5, 0.5, 0.5), (0.5, 0.5, 0.5))
])

# 测试数据转换
test_transform = transforms.Compose([
    transforms.Resize(70),
    transforms.CenterCrop(64),
    transforms.ToTensor(),
    transforms.Normalize((0.5, 0.5, 0.5), (0.5, 0.5, 0.5))
])
```



经过处理后，输入网络的批次数据维度为：`[256, 3, 64, 64]`，对应 `[批次大小, 通道数, 高, 宽]`。CIFAR-10 共有 10 个类别。



## 🏗️ PyTorch 实现 AlexNet




现在，我们来看看如何在 PyTorch 中定义 AlexNet 模型。整个网络可以分为特征提取器和分类器两部分。




特征提取器由多个卷积块组成。每个卷积块通常包含卷积层、激活函数和池化层。在 AlexNet 中，前两个卷积块后跟有最大池化层。







```python
import torch.nn as nn
class AlexNet(nn.Module):
    def __init__(self, num_classes=10):
        super(AlexNet, self).__init__()
        # 特征提取器
        self.features = nn.Sequential(
            nn.Conv2d(3, 64, kernel_size=11, stride=4, padding=2),
            nn.ReLU(inplace=True),
            nn.MaxPool2d(kernel_size=3, stride=2),
            nn.Conv2d(64, 192, kernel_size=5, padding=2),
            nn.ReLU(inplace=True),
            nn.MaxPool2d(kernel_size=3, stride=2),
            nn.Conv2d(192, 384, kernel_size=3, padding=1),
            nn.ReLU(inplace=True),
            nn.Conv2d(384, 256, kernel_size=3, padding=1),
            nn.ReLU(inplace=True),
            nn.Conv2d(256, 256, kernel_size=3, padding=1),
            nn.ReLU(inplace=True),
            nn.MaxPool2d(kernel_size=3, stride=2),
        )
        # 自适应平均池化
        self.avgpool = nn.AdaptiveAvgPool2d((6, 6))
        # 分类器
        self.classifier = nn.Sequential(
            nn.Dropout(),
            nn.Linear(256 * 6 * 6, 4096),
            nn.ReLU(inplace=True),
            nn.Dropout(),
            nn.Linear(4096, 4096),
            nn.ReLU(inplace=True),
            nn.Linear(4096, num_classes),
        )

    def forward(self, x):
        x = self.features(x)
        x = self.avgpool(x)
        x = torch.flatten(x, 1) # 展平特征图
        x = self.classifier(x)
        return x
```




**核心概念解析**：
*   **自适应平均池化 (`nn.AdaptiveAvgPool2d`)**：无论输入特征图的尺寸如何，该层都会将其池化到指定的输出尺寸（这里是 6x6）。这使得网络能够接受比训练时尺寸更大的输入图像，增加了灵活性。但如果输入图像过小，导致特征图尺寸小于 6x6，此操作会失败。
*   **Dropout**：原论文可能未使用 Dropout。本实现中添加了 Dropout 层以缓解严重的过拟合问题。
*   **展平操作**：在将特征图输入全连接层之前，需要使用 `torch.flatten` 将其从多维张量转换为一维向量。



## 🚀 模型训练与观察




我们使用随机梯度下降（SGD）优化器配合动量（Momentum）和学习率调度器来训练模型。在 GPU 上训练 200 个周期大约需要 3 小时。



在训练过程中，我们观察到一个有趣的现象：**双下降现象**。损失率先下降，然后上升，接着再次下降。验证准确率也呈现出先提升、后下降、再提升的趋势。这体现了模型复杂度与训练周期之间的复杂关系。


尽管如此，模型仍然表现出明显的过拟合，训练准确率远高于验证准确率，差距约 20%。为了进一步减少过拟合，可以考虑以下方法：






*   增加 Dropout 的比例。
*   添加更多的数据增强手段，如色彩抖动、随机旋转等。



## 📈 结果可视化与分析






训练完成后，我们可以可视化一些预测结果。在显示图像前，需要将归一化的像素值反归一化回原始范围。


```python
def unnormalize(img, mean, std):
    for t, m, s in zip(img, mean, std):
        t.mul_(s).add_(m)
    return img
```



通过可视化，我们发现模型在区分“猫”和“狗”这两个类别时错误率较高，这说明了该分类任务本身的挑战性。混淆矩阵也进一步揭示了模型容易混淆的类别对，例如“船”和“飞机”，“青蛙”和“猫”。





## 💡 总结与扩展





本节课中我们一起学习了如何在 PyTorch 中实现并训练 AlexNet 网络。我们回顾了 AlexNet 的架构，针对 CIFAR-10 数据集调整了输入预处理，实现了网络模型，并观察了训练过程中的双下降和过拟合现象。




AlexNet 和之前学习的 LeNet 都属于基础的卷积神经网络架构。为了获得更好的性能，可以尝试更现代的架构，如使用批归一化、Leaky ReLU 等技巧的网络。实验表明，一个加入了批归一化和 Leaky ReLU 的 CNN 能在更短的训练时间（30分钟）内取得相近甚至略好的准确率，但过拟合问题依然存在。



![](img/eafc166425d5eda00acc7c3a2db181bf_134.png)

在下一讲中，我们将更深入地探讨其他更强大的神经网络架构。