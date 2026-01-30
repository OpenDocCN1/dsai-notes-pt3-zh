# P107：L13.9.1 - PyTorch 中的 LeNet-5 实现教程 🧠

在本节课中，我们将学习如何使用 PyTorch 实现经典的 LeNet-5 卷积神经网络，并将其应用于 MNIST 手写数字分类任务。我们将从网络结构解析开始，逐步深入到代码的每一部分，并最终完成模型的训练与评估。

---

![](img/413981c97e7749afa7cd0c7e98bbfe1e_1.png)

## 概述

LeNet-5 是一个经典的卷积神经网络架构，最初设计用于手写字符识别。本节课我们将使用 PyTorch 框架，按照原始论文的结构，构建一个 LeNet-5 模型来对 MNIST 数据集中的手写数字进行分类。我们将涵盖数据预处理、模型定义、训练循环以及结果可视化等完整流程。

---

## LeNet-5 网络结构回顾

首先，我们来回顾一下 LeNet-5 的网络结构。下图展示了其经典设计：

![](img/413981c97e7749afa7cd0c7e98bbfe1e_1.png)

原始的 LeNet-5 输入是 32x32 的单通道图像。我们的 MNIST 数据集图像是 28x28，因此需要进行尺寸调整。

![](img/413981c97e7749afa7cd0c7e98bbfe1e_3.png)

网络结构遵循一个清晰的模式：
*   **卷积层**：通常用于增加通道数，同时保持特征图的高和宽大致不变（若使用填充）。
*   **池化层（下采样）**：通常用于将特征图的高和宽减半，同时保持通道数不变。

![](img/413981c97e7749afa7cd0c7e98bbfe1e_5.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_6.png)

在 LeNet-5 中，这个模式重复两次，形成特征提取器，之后连接全连接层作为分类器。

![](img/413981c97e7749afa7cd0c7e98bbfe1e_7.png)

---

![](img/413981c97e7749afa7cd0c7e98bbfe1e_9.png)

## 代码实现详解

![](img/413981c97e7749afa7cd0c7e98bbfe1e_11.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_13.png)

上一节我们回顾了网络结构，本节中我们来看看具体的代码实现。我将逐步解释每个部分。

![](img/413981c97e7749afa7cd0c7e98bbfe1e_14.png)

### 1. 环境准备与数据加载

首先，我们导入必要的库并设置环境。以下代码完成了随机种子设置、数据转换定义和数据加载器创建。

```python
import torch
import torch.nn as nn
import torch.optim as optim
from torchvision import datasets, transforms

![](img/413981c97e7749afa7cd0c7e98bbfe1e_16.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_17.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_18.png)

# 设置随机种子以保证CPU上的可重复性（GPU上某些算法可能非确定性）
torch.manual_seed(1)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_20.png)

# 定义数据转换
# 1. 将28x28的MNIST图像调整为32x32以匹配LeNet-5输入
# 2. 转换为张量
# 3. 标准化到[-1, 1]范围
transform = transforms.Compose([
    transforms.Resize((32, 32)),
    transforms.ToTensor(),
    transforms.Normalize((0.5,), (0.5,))
])

![](img/413981c97e7749afa7cd0c7e98bbfe1e_22.png)

# 加载MNIST数据集
train_dataset = datasets.MNIST(root='./data', train=True, download=True, transform=transform)
test_dataset = datasets.MNIST(root='./data', train=False, download=True, transform=transform)

train_loader = torch.utils.data.DataLoader(train_dataset, batch_size=64, shuffle=True)
test_loader = torch.utils.data.DataLoader(test_dataset, batch_size=1000, shuffle=False)
```

### 2. 定义 LeNet-5 模型

![](img/413981c97e7749afa7cd0c7e98bbfe1e_24.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_26.png)

接下来，我们定义 LeNet-5 模型类。为了使模型更通用（例如能处理彩色图像），我们添加了 `grayscale` 和 `num_classes` 参数。

以下是模型定义的核心部分：

![](img/413981c97e7749afa7cd0c7e98bbfe1e_28.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_29.png)

```python
class LeNet5(nn.Module):
    def __init__(self, grayscale=True, num_classes=10):
        super(LeNet5, self).__init__()
        self.grayscale = grayscale
        self.num_classes = num_classes

        # 特征提取器 (Feature Extractor)
        in_channels = 1 if grayscale else 3
        self.features = nn.Sequential(
            # 第一个卷积块: Conv -> ReLU -> Pool
            nn.Conv2d(in_channels, 6, kernel_size=5),  # 公式: 输出尺寸 = (输入尺寸 - 核尺寸 + 1)
            nn.ReLU(),
            nn.AvgPool2d(kernel_size=2, stride=2),     # 公式: 输出尺寸 = 输入尺寸 / 步长
            # 第二个卷积块: Conv -> ReLU -> Pool
            nn.Conv2d(6, 16, kernel_size=5),
            nn.ReLU(),
            nn.AvgPool2d(kernel_size=2, stride=2),
        )

        # 分类器 (Classifier) - 相当于一个多层感知机
        self.classifier = nn.Sequential(
            nn.Linear(16 * 5 * 5, 120),  # 全连接层，输入维度需根据特征图尺寸计算
            nn.ReLU(),
            nn.Linear(120, 84),
            nn.ReLU(),
            nn.Linear(84, num_classes)
            # 注意：这里没有Softmax，因为CrossEntropyLoss内部包含了它
        )

    def forward(self, x):
        # 通过特征提取器
        x = self.features(x)
        # 将特征图展平为一维向量，以输入全连接层
        # 输入x的形状: (batch_size, channels, height, width)
        # 展平后形状: (batch_size, channels * height * width)
        x = torch.flatten(x, 1)
        # 通过分类器
        x = self.classifier(x)
        return x
```

![](img/413981c97e7749afa7cd0c7e98bbfe1e_31.png)

**关键点解释**：
*   `nn.Sequential` 用于按顺序组合网络层，使代码更清晰。
*   第一个全连接层 `nn.Linear(16 * 5 * 5, 120)` 的输入维度 `16 * 5 * 5` 需要根据卷积和池化后的特征图尺寸计算得出。可以通过打印 `x` 在 `flatten` 前的形状来验证。
*   在 `forward` 方法中，`torch.flatten(x, 1)` 将除批次维度外的所有维度展平。

### 3. 模型初始化与设备设置

定义好模型后，我们需要实例化它，并将其移动到可用的计算设备（GPU或CPU）上。

```python
# 实例化模型
model = LeNet5(grayscale=True, num_classes=10)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_33.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_35.png)

# 检查是否有可用的GPU，并设置设备
device = torch.device('cuda:0' if torch.cuda.is_available() else 'cpu')
model.to(device)
print(f‘Using device: {device}’)
```

### 4. 定义损失函数与优化器

![](img/413981c97e7749afa7cd0c7e98bbfe1e_37.png)

为了训练模型，我们需要定义损失函数来衡量预测误差，以及优化器来更新模型参数。

![](img/413981c97e7749afa7cd0c7e98bbfe1e_39.png)

```python
criterion = nn.CrossEntropyLoss()  # 交叉熵损失函数，适用于多分类
optimizer = optim.SGD(model.parameters(), lr=0.01, momentum=0.9)  # 带动量的随机梯度下降

![](img/413981c97e7749afa7cd0c7e98bbfe1e_41.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_42.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_43.png)

# 可选：学习率调度器，用于在训练过程中动态调整学习率
scheduler = optim.lr_scheduler.StepLR(optimizer, step_size=5, gamma=0.1)
```

![](img/413981c97e7749afa7cd0c7e98bbfe1e_44.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_45.png)

### 5. 训练模型

![](img/413981c97e7749afa7cd0c7e98bbfe1e_47.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_48.png)

现在，我们进入核心的训练循环。以下是训练函数的关键步骤：

![](img/413981c97e7749afa7cd0c7e98bbfe1e_50.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_51.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_53.png)

```python
def train_model(model, train_loader, criterion, optimizer, scheduler=None, num_epochs=10):
    model.train()  # 将模型设置为训练模式
    for epoch in range(num_epochs):
        running_loss = 0.0
        correct = 0
        total = 0

        for batch_idx, (inputs, labels) in enumerate(train_loader):
            # 将数据移动到指定设备
            inputs, labels = inputs.to(device), labels.to(device)

            # 前向传播
            outputs = model(inputs)
            loss = criterion(outputs, labels)

            # 反向传播与优化
            optimizer.zero_grad()  # 清空过往梯度
            loss.backward()        # 反向传播计算梯度
            optimizer.step()       # 更新模型参数

            # 统计信息
            running_loss += loss.item()
            _, predicted = outputs.max(1)
            total += labels.size(0)
            correct += predicted.eq(labels).sum().item()

        # 每个epoch结束后打印统计信息
        epoch_loss = running_loss / len(train_loader)
        epoch_acc = 100. * correct / total
        print(f‘Epoch [{epoch+1}/{num_epochs}], Loss: {epoch_loss:.4f}, Acc: {epoch_acc:.2f}%’)

        # 更新学习率（如果使用了调度器）
        if scheduler:
            scheduler.step()

![](img/413981c97e7749afa7cd0c7e98bbfe1e_55.png)

# 开始训练
train_model(model, train_loader, criterion, optimizer, scheduler, num_epochs=10)
```

![](img/413981c97e7749afa7cd0c7e98bbfe1e_56.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_57.png)

训练过程中，你会看到损失逐渐下降，准确率逐渐上升。

![](img/413981c97e7749afa7cd0c7e98bbfe1e_59.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_60.png)

### 6. 模型评估与结果展示

![](img/413981c97e7749afa7cd0c7e98bbfe1e_61.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_63.png)

训练完成后，我们需要在测试集上评估模型的性能，并可视化一些预测结果。

![](img/413981c97e7749afa7cd0c7e98bbfe1e_65.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_67.png)

以下是评估和展示的函数：

![](img/413981c97e7749afa7cd0c7e98bbfe1e_69.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_71.png)

```python
def evaluate_model(model, test_loader):
    model.eval()  # 将模型设置为评估模式
    correct = 0
    total = 0
    with torch.no_grad():  # 评估时不计算梯度，节省内存和计算
        for inputs, labels in test_loader:
            inputs, labels = inputs.to(device), labels.to(device)
            outputs = model(inputs)
            _, predicted = outputs.max(1)
            total += labels.size(0)
            correct += predicted.eq(labels).sum().item()
    test_acc = 100. * correct / total
    print(f‘Test Accuracy: {test_acc:.2f}%’)
    return test_acc

![](img/413981c97e7749afa7cd0c7e98bbfe1e_73.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_75.png)

# 评估模型
test_accuracy = evaluate_model(model, test_loader)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_77.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_79.png)

# 可视化一些预测结果
import matplotlib.pyplot as plt
def show_examples(model, test_loader, num_examples=10):
    model.eval()
    dataiter = iter(test_loader)
    images, labels = next(dataiter)
    images, labels = images.to(device), labels.to(device)

    with torch.no_grad():
        outputs = model(images[:num_examples])
        _, preds = outputs.max(1)

    fig, axes = plt.subplots(1, num_examples, figsize=(15, 3))
    for idx in range(num_examples):
        ax = axes[idx]
        # 将图像从[-1,1]反标准化回[0,1]以便显示
        img = images[idx].cpu().squeeze().numpy() * 0.5 + 0.5
        ax.imshow(img, cmap='gray')
        ax.set_title(f‘P:{preds[idx].item()} T:{labels[idx].item()}’)
        ax.axis('off')
    plt.show()

![](img/413981c97e7749afa7cd0c7e98bbfe1e_81.png)

show_examples(model, test_loader)
```

![](img/413981c97e7749afa7cd0c7e98bbfe1e_83.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_85.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_87.png)

运行后，你将看到模型在测试集上的准确率，以及一些样例图片及其预测（P）和真实（T）标签。

![](img/413981c97e7749afa7cd0c7e98bbfe1e_89.png)

---

![](img/413981c97e7749afa7cd0c7e98bbfe1e_91.png)

## 总结

![](img/413981c97e7749afa7cd0c7e98bbfe1e_92.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_94.png)

本节课中，我们一起学习了如何使用 PyTorch 实现并训练 LeNet-5 卷积神经网络。我们完成了以下关键步骤：

![](img/413981c97e7749afa7cd0c7e98bbfe1e_96.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_98.png)

1.  **回顾了 LeNet-5 的网络结构**，理解了卷积层增加通道、池化层缩减尺寸的设计模式。
2.  **进行了数据预处理**，将 MNIST 图像调整尺寸并标准化。
3.  **使用 `nn.Module` 和 `nn.Sequential` 定义了 LeNet-5 模型**，清晰地分离了特征提取器和分类器。
4.  **设置了训练环境**，包括损失函数（交叉熵）、优化器（带动量的SGD）和学习率调度器。
5.  **编写了完整的训练循环**，包含了前向传播、损失计算、反向传播和参数更新。
6.  **评估了模型性能并可视化预测结果**，验证了模型的有效性。

![](img/413981c97e7749afa7cd0c7e98bbfe1e_100.png)

![](img/413981c97e7749afa7cd0c7e98bbfe1e_101.png)

通过这个实践，你不仅掌握了实现一个经典 CNN 的方法，也熟悉了 PyTorch 训练神经网络的标准流程。在接下来的课程中，我们将探索更复杂的网络结构，如 AlexNet。