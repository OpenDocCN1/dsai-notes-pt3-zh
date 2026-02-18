# 31：有监督与自监督迁移学习（使用 PyTorch Lightning）🚀

在本节课中，我们将学习迁移学习的概念，并分别在有监督和自监督的背景下，使用 PyTorch Lightning 和 PyTorch Lightning Bolts 库进行实践。迁移学习在数据不足或计算资源有限时非常有用，它能帮助我们利用预训练模型来加速新任务的训练过程。

![](img/f8f008e2808f19882aa25f551e7c2493_1.png)

## 概述 📋

迁移学习是指利用在一个任务上训练好的模型，来帮助解决另一个相关任务的技术。本节课将重点介绍两种迁移学习方式：有监督迁移学习和自监督迁移学习。我们将使用 PyTorch Lightning 来组织代码，并使用 PyTorch Lightning Bolts 库中提供的预训练模型和工具。

## 工具介绍 🛠️

![](img/f8f008e2808f19882aa25f551e7c2493_3.png)

![](img/f8f008e2808f19882aa25f551e7c2493_5.png)

在开始之前，我们先介绍两个核心工具：PyTorch Lightning 和 PyTorch Lightning Bolts。

![](img/f8f008e2808f19882aa25f551e7c2493_7.png)

![](img/f8f008e2808f19882aa25f551e7c2493_9.png)

![](img/f8f008e2808f19882aa25f551e7c2493_11.png)

PyTorch Lightning 是 PyTorch 的一个轻量级封装，旨在简化高性能研究代码的编写。它自动处理了多 GPU 训练、TPU 训练等复杂操作，让你能更专注于模型构建本身。

![](img/f8f008e2808f19882aa25f551e7c2493_13.png)

![](img/f8f008e2808f19882aa25f551e7c2493_15.png)

PyTorch Lightning Bolts 是一个研究工具包，它提供了许多最新的、经过测试和文档化的模型实现。当你开始一个新项目时，可以在这里寻找合适的基线模型，而无需花费数月时间从头实现。

![](img/f8f008e2808f19882aa25f551e7c2493_17.png)

![](img/f8f008e2808f19882aa25f551e7c2493_19.png)

如果你想了解更多关于这两个工具的信息，可以访问以下资源：
*   PyTorch Lightning: [https://www.pytorchlightning.ai](https://www.pytorchlightning.ai)
*   PyTorch Lightning Bolts: 在 PyTorch Lightning 官网可以找到相关链接。

## 何时进行微调？🤔

在决定是否使用迁移学习时，你可以问自己几个问题。

![](img/f8f008e2808f19882aa25f551e7c2493_21.png)

以下是帮助你决策的关键因素：
1.  **数据量**：如果你拥有大量数据，可能不需要微调预训练模型，可以直接从头训练。
2.  **时间和算力**：即使数据量大，如果训练成本过高，使用预训练模型仍然是更好的选择。
3.  **数据分布匹配度**：如果数据量小，你需要找到一个与你的数据分布相匹配的预训练模型。例如，在 ImageNet（包含自然物体图像）上训练的模型，可能不适用于医学 X 光图像分析。

![](img/f8f008e2808f19882aa25f551e7c2493_23.png)

迁移学习通常包含两部分：一个在其它任务上预训练的模型，以及你为了新任务而添加的顶层结构。然后你可以在自己的数据上对这个组合进行微调。

![](img/f8f008e2808f19882aa25f551e7c2493_25.png)

## 有监督迁移学习实践 🏁

![](img/f8f008e2808f19882aa25f551e7c2493_27.png)

![](img/f8f008e2808f19882aa25f551e7c2493_29.png)

上一节我们讨论了迁移学习的适用场景，本节中我们来看看最常见的情况：有监督迁移学习。我们假设你有一个小规模图像数据集和有限的算力。

我们将使用在 ImageNet 上预训练的 ResNet-50 模型。ImageNet 包含约1000个类别，每个类别约有1000张图像，总计约一百万张图像，这为模型提供了关于自然图像的强大先验知识。

首先，我们需要安装并导入必要的库，然后加载预训练的 ResNet-50 模型。

```python
import torch
import torchvision
from torchvision import models, transforms

# 加载预训练的 ResNet-50 模型
model = models.resnet50(pretrained=True)
```

![](img/f8f008e2808f19882aa25f551e7c2493_31.png)

![](img/f8f008e2808f19882aa25f551e7c2493_33.png)

![](img/f8f008e2808f19882aa25f551e7c2493_35.png)

接下来，我们准备数据集。这里使用 CIFAR-10 数据集作为示例，它包含10个类别的32x32像素小图像。虽然尺寸与 ImageNet 不同，但由于卷积神经网络的特性，这通常可以工作。

![](img/f8f008e2808f19882aa25f551e7c2493_37.png)

![](img/f8f008e2808f19882aa25f551e7c2493_39.png)

```python
# 定义数据转换
transform = transforms.Compose([
    transforms.ToTensor(),
    transforms.Normalize((0.5, 0.5, 0.5), (0.5, 0.5, 0.5)) # 归一化到[-1, 1]
])

![](img/f8f008e2808f19882aa25f551e7c2493_41.png)

# 加载 CIFAR-10 数据集
trainset = torchvision.datasets.CIFAR10(root='./data', train=True, download=True, transform=transform)
trainloader = torch.utils.data.DataLoader(trainset, batch_size=32, shuffle=True)
```

![](img/f8f008e2808f19882aa25f551e7c2493_43.png)

![](img/f8f008e2808f19882aa25f551e7c2493_45.png)

由于 ResNet-50 原本是为 ImageNet 的1000个类别设计的，而 CIFAR-10 只有10个类别，因此我们需要修改模型的最后一层全连接层。

![](img/f8f008e2808f19882aa25f551e7c2493_47.png)

![](img/f8f008e2808f19882aa25f551e7c2493_49.png)

![](img/f8f008e2808f19882aa25f551e7c2493_51.png)

```python
# 获取原模型最后一层输入特征数
num_ftrs = model.fc.in_features
# 替换全连接层，输出为10个类别
model.fc = torch.nn.Linear(num_ftrs, 10)
```

![](img/f8f008e2808f19882aa25f551e7c2493_53.png)

![](img/f8f008e2808f19882aa25f551e7c2493_55.png)

现在，如果我们直接用这个修改后的模型进行预测，效果会很差，因为新替换的全连接层是随机初始化的。因此，我们需要对这个模型进行微调。

![](img/f8f008e2808f19882aa25f551e7c2493_57.png)

微调有两种主要策略：
1.  **特征提取器**：冻结预训练模型的所有层，只训练新添加的顶层（如我们刚替换的全连接层）。这相当于用预训练模型提取特征，然后用一个简单的分类器（如线性层、SVM）基于这些特征进行分类。
2.  **整体微调**：解冻全部或部分预训练模型的层，与新层一起训练。通常，学习率需要设置得更低，以避免破坏预训练好的权重。

![](img/f8f008e2808f19882aa25f551e7c2493_59.png)

在本次实践中，我们将采用第二种策略，使用 PyTorch Lightning 来组织训练流程。

![](img/f8f008e2808f19882aa25f551e7c2493_61.png)

## 自监督迁移学习探索 🔬

上一节我们实践了有监督迁移学习，本节中我们来看看另一种前沿方法：自监督迁移学习。

与有监督学习需要大量标注数据不同，自监督学习让模型从无标签数据中自行学习有用的特征表示。这种表示可能比有监督学习获得的表示更具通用性，因为它不是针对特定分类任务优化的，因此在分割、检测等下游任务上可能迁移得更好。

![](img/f8f008e2808f19882aa25f551e7c2493_63.png)

![](img/f8f008e2808f19882aa25f551e7c2493_65.png)

目前有多种自监督学习方法，如 AMD、MoCo、CPC、SimCLR、BYOL 和 SwAV 等。其中 SwAV 是较新的方法。我们将使用 PyTorch Lightning Bolts 库中提供的 SwAV 预训练模型。

自监督迁移学习的流程与有监督类似：加载预训练模型，根据新任务修改输出层，然后进行微调。关键区别在于，预训练模型是通过自监督任务学习到的，其学到的特征可能对数据分布的变化更鲁棒。

![](img/f8f008e2808f19882aa25f551e7c2493_67.png)

![](img/f8f008e2808f19882aa25f551e7c2493_69.png)

![](img/f8f008e2808f19882aa25f551e7c2493_70.png)

![](img/f8f008e2808f19882aa25f551e7c2493_71.png)

## 总结 🎯

![](img/f8f008e2808f19882aa25f551e7c2493_72.png)

![](img/f8f008e2808f19882aa25f551e7c2493_73.png)

![](img/f8f008e2808f19882aa25f551e7c2493_74.png)

![](img/f8f008e2808f19882aa25f551e7c2493_75.png)

![](img/f8f008e2808f19882aa25f551e7c2493_76.png)

![](img/f8f008e2808f19882aa25f551e7c2493_77.png)

![](img/f8f008e2808f19882aa25f551e7c2493_78.png)

![](img/f8f008e2808f19882aa25f551e7c2493_79.png)

![](img/f8f008e2808f19882aa25f551e7c2493_80.png)

![](img/f8f008e2808f19882aa25f551e7c2493_81.png)

![](img/f8f008e2808f19882aa25f551e7c2493_82.png)

![](img/f8f008e2808f19882aa25f551e7c2493_83.png)

![](img/f8f008e2808f19882aa25f551e7c2493_84.png)

![](img/f8f008e2808f19882aa25f551e7c2493_85.png)

![](img/f8f008e2808f19882aa25f551e7c2493_86.png)

![](img/f8f008e2808f19882aa25f551e7c2493_87.png)

![](img/f8f008e2808f19882aa25f551e7c2493_88.png)

![](img/f8f008e2808f19882aa25f551e7c2493_89.png)

![](img/f8f008e2808f19882aa25f551e7c2493_90.png)

![](img/f8f008e2808f19882aa25f551e7c2493_91.png)

![](img/f8f008e2808f19882aa25f551e7c2493_92.png)

本节课我们一起学习了迁移学习的核心概念与实践。

![](img/f8f008e2808f19882aa25f551e7c2493_93.png)

![](img/f8f008e2808f19882aa25f551e7c2493_94.png)

![](img/f8f008e2808f19882aa25f551e7c2493_95.png)

![](img/f8f008e2808f19882aa25f551e7c2493_96.png)

![](img/f8f008e2808f19882aa25f551e7c2493_97.png)

![](img/f8f008e2808f19882aa25f551e7c2493_98.png)

![](img/f8f008e2808f19882aa25f551e7c2493_99.png)

![](img/f8f008e2808f19882aa25f551e7c2493_100.png)

![](img/f8f008e2808f19882aa25f551e7c2493_101.png)

![](img/f8f008e2808f19882aa25f551e7c2493_102.png)

![](img/f8f008e2808f19882aa25f551e7c2493_103.png)

![](img/f8f008e2808f19882aa25f551e7c2493_104.png)

![](img/f8f008e2808f19882aa25f551e7c2493_105.png)

![](img/f8f008e2808f19882aa25f551e7c2493_106.png)

![](img/f8f008e2808f19882aa25f551e7c2493_107.png)

![](img/f8f008e2808f19882aa25f551e7c2493_108.png)

![](img/f8f008e2808f19882aa25f551e7c2493_109.png)

![](img/f8f008e2808f19882aa25f551e7c2493_110.png)

![](img/f8f008e2808f19882aa25f551e7c2493_111.png)

![](img/f8f008e2808f19882aa25f551e7c2493_112.png)

![](img/f8f008e2808f19882aa25f551e7c2493_113.png)

我们首先了解了何时应该考虑使用迁移学习，关键因素包括数据量、计算资源以及预训练任务与目标任务的数据分布匹配度。

![](img/f8f008e2808f19882aa25f551e7c2493_114.png)

![](img/f8f008e2808f19882aa25f551e7c2493_115.png)

![](img/f8f008e2808f19882aa25f551e7c2493_116.png)

![](img/f8f008e2808f19882aa25f551e7c2493_117.png)

![](img/f8f008e2808f19882aa25f551e7c2493_118.png)

![](img/f8f008e2808f19882aa25f551e7c2493_119.png)

![](img/f8f008e2808f19882aa25f551e7c2493_120.png)

![](img/f8f008e2808f19882aa25f551e7c2493_121.png)

![](img/f8f008e2808f19882aa25f551e7c2493_122.png)

![](img/f8f008e2808f19882aa25f551e7c2493_123.png)

![](img/f8f008e2808f19882aa25f551e7c2493_124.png)

![](img/f8f008e2808f19882aa25f551e7c2493_125.png)

![](img/f8f008e2808f19882aa25f551e7c2493_126.png)

![](img/f8f008e2808f19882aa25f551e7c2493_127.png)

![](img/f8f008e2808f19882aa25f551e7c2493_128.png)

![](img/f8f008e2808f19882aa25f551e7c2493_129.png)

![](img/f8f008e2808f19882aa25f551e7c2493_130.png)

![](img/f8f008e2808f19882aa25f551e7c2493_131.png)

![](img/f8f008e2808f19882aa25f551e7c2493_132.png)

![](img/f8f008e2808f19882aa25f551e7c2493_133.png)

![](img/f8f008e2808f19882aa25f551e7c2493_134.png)

接着，我们深入实践了有监督迁移学习，使用在 ImageNet 上预训练的 ResNet-50 模型，通过修改并微调最后一层，使其适应 CIFAR-10 数据集。我们介绍了两种微调策略：将预训练模型作为固定的特征提取器，或对整个模型进行微调。

![](img/f8f008e2808f19882aa25f551e7c2493_135.png)

![](img/f8f008e2808f19882aa25f551e7c2493_136.png)

![](img/f8f008e2808f19882aa25f551e7c2493_137.png)

![](img/f8f008e2808f19882aa25f551e7c2493_138.png)

![](img/f8f008e2808f19882aa25f551e7c2493_139.png)

![](img/f8f008e2808f19882aa25f551e7c2493_140.png)

![](img/f8f008e2808f19882aa25f551e7c2493_141.png)

![](img/f8f008e2808f19882aa25f551e7c2493_142.png)

![](img/f8f008e2808f19882aa25f551e7c2493_143.png)

![](img/f8f008e2808f19882aa25f551e7c2493_144.png)

![](img/f8f008e2808f19882aa25f551e7c2493_145.png)

![](img/f8f008e2808f19882aa25f551e7c2493_146.png)

![](img/f8f008e2808f19882aa25f551e7c2493_147.png)

![](img/f8f008e2808f19882aa25f551e7c2493_148.png)

![](img/f8f008e2808f19882aa25f551e7c2493_149.png)

![](img/f8f008e2808f19882aa25f551e7c2493_150.png)

![](img/f8f008e2808f19882aa25f551e7c2493_151.png)

![](img/f8f008e2808f19882aa25f551e7c2493_152.png)

![](img/f8f008e2808f19882aa25f551e7c2493_153.png)

![](img/f8f008e2808f19882aa25f551e7c2493_154.png)

![](img/f8f008e2808f19882aa25f551e7c2493_155.png)

最后，我们探讨了自监督迁移学习这一新兴领域。自监督模型通过无标签数据学习通用特征，可能在下游任务中提供更好的迁移性能，并介绍了如何使用 PyTorch Lightning Bolts 库中的相关模型。

![](img/f8f008e2808f19882aa25f551e7c2493_156.png)

![](img/f8f008e2808f19882aa25f551e7c2493_157.png)

![](img/f8f008e2808f19882aa25f551e7c2493_158.png)

![](img/f8f008e2808f19882aa25f551e7c2493_159.png)

![](img/f8f008e2808f19882aa25f551e7c2493_160.png)

![](img/f8f008e2808f19882aa25f551e7c2493_161.png)

![](img/f8f008e2808f19882aa25f551e7c2493_162.png)

![](img/f8f008e2808f19882aa25f551e7c2493_163.png)

![](img/f8f008e2808f19882aa25f551e7c2493_164.png)

![](img/f8f008e2808f19882aa25f551e7c2493_165.png)

![](img/f8f008e2808f19882aa25f551e7c2493_166.png)

![](img/f8f008e2808f19882aa25f551e7c2493_167.png)

![](img/f8f008e2808f19882aa25f551e7c2493_168.png)

![](img/f8f008e2808f19882aa25f551e7c2493_169.png)

![](img/f8f008e2808f19882aa25f551e7c2493_170.png)

![](img/f8f008e2808f19882aa25f551e7c2493_171.png)

![](img/f8f008e2808f19882aa25f551e7c2493_172.png)

![](img/f8f008e2808f19882aa25f551e7c2493_173.png)

![](img/f8f008e2808f19882aa25f551e7c2493_174.png)

![](img/f8f008e2808f19882aa25f551e7c2493_175.png)

![](img/f8f008e2808f19882aa25f551e7c2493_176.png)

希望本教程能帮助你理解并开始在实际项目中应用迁移学习技术。