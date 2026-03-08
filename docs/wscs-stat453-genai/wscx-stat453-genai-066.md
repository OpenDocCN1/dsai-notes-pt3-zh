# 66：L9.3.2 - 多层感知器实现（Jupyter Notebook） 🧠

在本节课中，我们将学习如何使用 PyTorch 实现一个多层感知器（MLP），并将其应用于 MNIST 手写数字分类任务。我们将重点关注 MLP 与之前学习的 Softmax 回归在代码结构上的关键区别，并理解如何构建包含隐藏层的神经网络。

![](img/6785be20b4e65afee85a3f103de7402c_1.png)

---

![](img/6785be20b4e65afee85a3f103de7402c_2.png)

## 📦 导入与超参数设置

![](img/6785be20b4e65afee85a3f103de7402c_4.png)

![](img/6785be20b4e65afee85a3f103de7402c_5.png)

首先，我们需要导入必要的库并设置一些超参数。以下是代码的初始部分。

```python
import torch
import torch.nn as nn
import torch.nn.functional as F
from torchvision import datasets, transforms

![](img/6785be20b4e65afee85a3f103de7402c_7.png)

![](img/6785be20b4e65afee85a3f103de7402c_8.png)

![](img/6785be20b4e65afee85a3f103de7402c_9.png)

![](img/6785be20b4e65afee85a3f103de7402c_10.png)

# 超参数设置
batch_size = 100
num_epochs = 100
```

![](img/6785be20b4e65afee85a3f103de7402c_12.png)

我们设置批量大小为 100，这是一个常用值，通常也使用 2 的幂次方，如 32、64 或 128。训练轮数设置为 100。

![](img/6785be20b4e65afee85a3f103de7402c_13.png)

![](img/6785be20b4e65afee85a3f103de7402c_15.png)

---

![](img/6785be20b4e65afee85a3f103de7402c_16.png)

## 📊 加载 MNIST 数据集

接下来，我们加载 MNIST 数据集。其加载方式与我们在 Softmax 回归课程中使用的方法相同。

```python
# 数据转换：将图像转换为张量并归一化
transform = transforms.Compose([
    transforms.ToTensor(),
    transforms.Normalize((0.1307,), (0.3081,))
])

# 下载并加载训练集和测试集
train_dataset = datasets.MNIST(root='./data', train=True, download=True, transform=transform)
test_dataset = datasets.MNIST(root='./data', train=False, download=True, transform=transform)

train_loader = torch.utils.data.DataLoader(dataset=train_dataset, batch_size=batch_size, shuffle=True)
test_loader = torch.utils.data.DataLoader(dataset=test_dataset, batch_size=batch_size, shuffle=False)
```

MNIST 数据集已包含在 `torchvision` 中。我们关注的重点是后续的多层感知器实现。

![](img/6785be20b4e65afee85a3f103de7402c_18.png)

---

![](img/6785be20b4e65afee85a3f103de7402c_19.png)

## 🏗️ 定义多层感知器模型

![](img/6785be20b4e65afee85a3f103de7402c_21.png)

![](img/6785be20b4e65afee85a3f103de7402c_22.png)

上一节我们介绍了数据准备，本节中我们来看看模型的核心部分。与 Softmax 回归相比，多层感知器的关键区别在于增加了一个隐藏层。

![](img/6785be20b4e65afee85a3f103de7402c_24.png)

以下是模型定义：

![](img/6785be20b4e65afee85a3f103de7402c_26.png)

```python
class MultilayerPerceptron(nn.Module):
    def __init__(self, input_size, hidden_size, num_classes):
        super(MultilayerPerceptron, self).__init__()
        # 第一个全连接层（输入层 -> 隐藏层）
        self.fc1 = nn.Linear(input_size, hidden_size)
        # Sigmoid 激活函数
        self.sigmoid = nn.Sigmoid()
        # 第二个全连接层（隐藏层 -> 输出层）
        self.fc2 = nn.Linear(hidden_size, num_classes)
        # 注意：我们不在输出层显式使用 Softmax

    def forward(self, x):
        # 将图像展平
        x = x.view(-1, 28*28)
        # 输入到隐藏层并应用激活函数
        out = self.sigmoid(self.fc1(x))
        # 隐藏层到输出层（输出为 logits）
        out = self.fc2(out)
        return out
```

![](img/6785be20b4e65afee85a3f103de7402c_28.png)

![](img/6785be20b4e65afee85a3f103de7402c_30.png)

**核心概念解析：**
*   **隐藏层**：`self.fc1` 是输入层和输出层之间的额外层，赋予模型学习非线性关系的能力。
*   **激活函数**：`nn.Sigmoid()` 为网络引入非线性。我们使用较小的随机权重初始化（均值为0，标准差为0.1），以防止 Sigmoid 函数饱和导致梯度消失。
*   **输出 Logits**：模型直接输出 `fc2` 的结果，即 logits（未归一化的分数）。我们不在前向传播中显式计算 Softmax。

![](img/6785be20b4e65afee85a3f103de7402c_32.png)

![](img/6785be20b4e65afee85a3f103de7402c_34.png)

如果移除这个隐藏层，模型就退化成了 Softmax 回归模型。

![](img/6785be20b4e65afee85a3f103de7402c_35.png)

---

## ⚙️ 模型初始化与训练设置

现在我们来初始化模型并设置训练所需的损失函数和优化器。

![](img/6785be20b4e65afee85a3f103de7402c_37.png)

```python
# 初始化模型
input_size = 28 * 28  # MNIST 图像尺寸
hidden_size = 100     # 隐藏层神经元数量，这是一个可调整的超参数
num_classes = 10      # 输出类别数（数字0-9）

model = MultilayerPerceptron(input_size, hidden_size, num_classes)

![](img/6785be20b4e65afee85a3f103de7402c_39.png)

![](img/6785be20b4e65afee85a3f103de7402c_40.png)

# 定义损失函数和优化器
criterion = nn.CrossEntropyLoss()  # 内部已包含 LogSoftmax
optimizer = torch.optim.SGD(model.parameters(), lr=0.1)
```

![](img/6785be20b4e65afee85a3f103de7402c_42.png)

![](img/6785be20b4e65afee85a3f103de7402c_43.png)

**关键点说明：**
1.  **损失函数**：使用 `nn.CrossEntropyLoss()`。**这是推荐的做法**，因为它将 `LogSoftmax` 和负对数似然损失 (`NLLLoss`) 组合在一起，比手动计算更稳定高效。
2.  **优化器**：使用随机梯度下降（SGD）。

![](img/6785be20b4e65afee85a3f103de7402c_45.png)

---

![](img/6785be20b4e65afee85a3f103de7402c_46.png)

![](img/6785be20b4e65afee85a3f103de7402c_48.png)

## 🔄 训练循环与损失计算

![](img/6785be20b4e65afee85a3f103de7402c_50.png)

训练循环的结构与 Softmax 回归相似。我们额外实现一个函数来计算整个训练集上的损失，用于监控训练过程。

![](img/6785be20b4e65afee85a3f103de7402c_52.png)

以下是计算整个数据集损失的工具函数：

![](img/6785be20b4e65afee85a3f103de7402c_54.png)

![](img/6785be20b4e65afee85a3f103de7402c_55.png)

```python
def compute_loss(data_loader, model):
    total_loss = 0.0
    # 禁用梯度计算以节省内存和计算资源
    with torch.no_grad():
        for images, labels in data_loader:
            outputs = model(images)
            loss = criterion(outputs, labels)
            total_loss += loss.item()
    return total_loss / len(data_loader)
```

使用 `with torch.no_grad():` 上下文管理器是因为我们只进行前向传播计算损失，不需要构建计算图进行反向传播，这样可以提升效率。

![](img/6785be20b4e65afee85a3f103de7402c_57.png)

![](img/6785be20b4e65afee85a3f103de7402c_59.png)

以下是主要的训练循环：

![](img/6785be20b4e65afee85a3f103de7402c_61.png)

```python
train_losses = []

![](img/6785be20b4e65afee85a3f103de7402c_63.png)

![](img/6785be20b4e65afee85a3f103de7402c_64.png)

for epoch in range(num_epochs):
    for i, (images, labels) in enumerate(train_loader):
        # 前向传播
        outputs = model(images)
        loss = criterion(outputs, labels)

        # 反向传播与优化
        optimizer.zero_grad()  # 清空过往梯度
        loss.backward()        # 反向传播计算梯度
        optimizer.step()       # 更新模型参数

        # 记录日志（可选）
        if (i+1) % 100 == 0:
            print(f'Epoch [{epoch+1}/{num_epochs}], Step [{i+1}/{len(train_loader)}], Loss: {loss.item():.4f}')

    # 每个 epoch 结束后，计算整个训练集的平均损失
    epoch_loss = compute_loss(train_loader, model)
    train_losses.append(epoch_loss)
    print(f'Epoch [{epoch+1}/{num_epochs}] completed. Average Training Loss: {epoch_loss:.4f}')
```

![](img/6785be20b4e65afee85a3f103de7402c_66.png)

![](img/6785be20b4e65afee85a3f103de7402c_68.png)

训练过程在 CPU 上执行。对于 MNIST 这样的数据集，这已经足够。代码运行后，我们可以绘制 `train_losses` 列表来观察训练损失随轮数下降的趋势。

![](img/6785be20b4e65afee85a3f103de7402c_70.png)

![](img/6785be20b4e65afee85a3f103de7402c_71.png)

---

![](img/6785be20b4e65afee85a3f103de7402c_73.png)

## 📝 总结

![](img/6785be20b4e65afee85a3f103de7402c_75.png)

本节课中我们一起学习了如何使用 PyTorch 实现一个基础的多层感知器。

我们主要涵盖了以下内容：
1.  **模型结构**：在 Softmax 回归的基础上增加了**隐藏层**和 **Sigmoid 激活函数**，构成了基本的 MLP。
2.  **代码实现**：定义了 `MultilayerPerceptron` 类，并解释了前向传播过程。
3.  **训练流程**：使用了 `CrossEntropyLoss` 损失函数和 SGD 优化器，并实现了完整的训练循环。
4.  **实用技巧**：介绍了使用 `torch.no_grad()` 来高效计算验证损失的方法。

![](img/6785be20b4e65afee85a3f103de7402c_77.png)

这个实现虽然简单，但包含了神经网络训练的核心要素。通过调整隐藏层大小、激活函数或优化器等超参数，你可以进一步探索并提升模型性能。