# 124：L14.6.2 - PyTorch 中的迁移学习 🚀

![](img/61c6df0b6f418da1af685e9b610e3dd0_1.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_3.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_5.png)

在本节课中，我们将要学习如何在 PyTorch 中实现迁移学习。具体来说，我们将使用一个在 ImageNet 数据集上预训练好的 VGG16 模型，并在 CIFAR-10 目标数据集上对其进行微调。

![](img/61c6df0b6f418da1af685e9b610e3dd0_7.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_8.png)

迁移学习的核心思想是，利用在大规模数据集（如 ImageNet）上训练好的模型所学习到的通用特征，来加速和提升我们在较小目标数据集上的模型训练效果。在本例中，我们将冻结 VGG16 的所有卷积层，只训练最后的全连接层，并替换输出层以适应 CIFAR-10 的 10 个类别。

![](img/61c6df0b6f418da1af685e9b610e3dd0_10.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_12.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_14.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_15.png)

## 1. 数据准备与标准化 📊

![](img/61c6df0b6f418da1af685e9b610e3dd0_16.png)

上一节我们介绍了迁移学习的基本概念，本节中我们来看看如何准备数据。代码的大部分内容与我们之前讨论的 VGG16 实现相同，但有两个关键行需要注意。

以下是数据标准化时使用的均值和标准差参数：
```python
mean = [0.485, 0.456, 0.406]
std = [0.229, 0.224, 0.225]
```
这些数值并非随意设定，而是来源于 ImageNet 数据集。因为我们将使用在 ImageNet 上预训练的模型，所以需要确保输入数据与模型训练时使用的数据处于相同的尺度。

![](img/61c6df0b6f418da1af685e9b610e3dd0_18.png)

> 有时也建议根据你自己的数据集重新计算这些参数。这是因为你的图像可能在亮度、色彩等方面与 ImageNet 存在系统性差异。你可以尝试两种方法，如果结果差异显著，则两种都值得尝试。

![](img/61c6df0b6f418da1af685e9b610e3dd0_20.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_21.png)

## 2. 加载预训练模型 🧠

![](img/61c6df0b6f418da1af685e9b610e3dd0_23.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_24.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_25.png)

现在，我们进入更有趣的部分——迁移学习本身。我们将从 `torchvision` 库中加载预训练的 VGG16 模型。

![](img/61c6df0b6f418da1af685e9b610e3dd0_27.png)

以下是加载模型的代码：
```python
import torchvision.models as models
model = models.vgg16(pretrained=True)
```
`torchvision` 提供了多种预训练模型，如 DenseNet、MobileNet、ResNet、Inception 等。它们都在 ImageNet 上进行了预训练，你可以根据项目需求选择。VGG16 因其结构经典而被我们选用。

![](img/61c6df0b6f418da1af685e9b610e3dd0_29.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_31.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_32.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_33.png)

打印模型结构 `print(model)` 可以看到，它主要分为两部分：`features`（卷积层，用于特征提取）和 `classifier`（全连接层，用于分类）。

![](img/61c6df0b6f418da1af685e9b610e3dd0_35.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_37.png)

## 3. 冻结模型与微调特定层 🔒

我们计划冻结所有卷积层，只微调最后的全连接层。首先，我们需要冻结整个模型的所有参数。

![](img/61c6df0b6f418da1af685e9b610e3dd0_39.png)

以下是冻结模型的代码：
```python
for param in model.parameters():
    param.requires_grad = False
```
这行代码遍历模型的所有参数，并将 `requires_grad` 属性设置为 `False`。这意味着在反向传播时，这些参数不会被更新，但前向和反向传播仍可正常进行。

![](img/61c6df0b6f418da1af685e9b610e3dd0_41.png)

接下来，我们需要“解冻”并微调 `classifier` 部分中的特定层。查看模型结构可知，`classifier` 包含多个层（如 Linear、Dropout、ReLU）。我们只训练那些包含可学习参数的线性层。

![](img/61c6df0b6f418da1af685e9b610e3dd0_43.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_44.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_46.png)

以下是解冻并替换输出层的代码：
```python
# 解冻最后两个全连接层（索引1和3）
model.classifier[1].requires_grad = True
model.classifier[3].requires_grad = True

![](img/61c6df0b6f418da1af685e9b610e3dd0_48.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_50.png)

# 替换最后的输出层，因为ImageNet有1000类，而CIFAR-10只有10类
model.classifier[6] = torch.nn.Linear(4096, 10)
```
我们解冻了索引为 1 和 3 的线性层，并将最后的输出层替换为一个新的线性层，其输出特征数从 1000 改为 10。

![](img/61c6df0b6f418da1af685e9b610e3dd0_52.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_53.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_55.png)

## 4. 模型训练与性能分析 📈

![](img/61c6df0b6f418da1af685e9b610e3dd0_56.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_57.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_59.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_60.png)

模型设置完成后，训练过程与之前完全相同。但使用预训练模型的一个显著优势是，模型在训练初期就具有较高的准确率，因为它已经具备从 ImageNet 学习到的特征提取能力。

![](img/61c6df0b6f418da1af685e9b610e3dd0_62.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_63.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_64.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_66.png)

然而，在最初的尝试中，当使用 CIFAR-10 原始的小尺寸图像（如 32x32）进行训练时，模型性能可能并不理想（例如仅达到 77% 的准确率）。一个可能的原因是，预训练的 VGG16 期望输入图像的最小尺寸为 224x224。虽然网络中的自适应平均池化层（AdaptiveAvgPool2d）能处理不同尺寸的输入，但卷积层本身是在特定尺度特征上进行训练的。

![](img/61c6df0b6f418da1af685e9b610e3dd0_68.png)

为了解决这个问题，我们可以将输入图像的大小调整为 224x224。虽然这会使 CIFAR-10 的图像显得像素化，但能更好地匹配预训练模型所期望的输入尺度。实验表明，调整尺寸后，模型的性能得到了显著提升（例如达到约 85% 的准确率）。

![](img/61c6df0b6f418da1af685e9b610e3dd0_70.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_72.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_74.png)

此外，由于我们冻结了大部分参数，只训练少数全连接层，训练时间也大大缩短。例如，微调模型可能只需 38 分钟，而从零开始训练一个类似的 VGG16 可能需要 90 分钟。

![](img/61c6df0b6f418da1af685e9b610e3dd0_76.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_78.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_80.png)

## 5. 迁移学习的策略与总结 🎯

![](img/61c6df0b6f418da1af685e9b610e3dd0_82.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_84.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_86.png)

关于微调多少层，并没有固定的答案。根据相关研究，微调最后三个全连接层通常能取得不错的效果，但这完全取决于具体任务和数据。有时只训练最后一层效果更好，有时则需要微调所有层。最佳策略需要通过实验来确定。

![](img/61c6df0b6f418da1af685e9b610e3dd0_88.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_89.png)

本节课中我们一起学习了在 PyTorch 中实现迁移学习的完整流程：
1.  使用与预训练模型匹配的参数对数据进行标准化。
2.  加载预训练模型并理解其结构。
3.  冻结模型的大部分参数，只解冻并准备微调目标层。
4.  替换模型的输出层以适应新任务的类别数。
5.  进行训练，并注意输入尺寸与预训练模型的匹配问题。

![](img/61c6df0b6f418da1af685e9b610e3dd0_91.png)

![](img/61c6df0b6f418da1af685e9b610e3dd0_93.png)

迁移学习是一种强大的技术，它能让我们在数据有限的情况下，快速构建出高性能的模型。希望本教程对你有所帮助。接下来，我们将开始一个全新的主题——用于处理文本数据的循环神经网络（RNN）。