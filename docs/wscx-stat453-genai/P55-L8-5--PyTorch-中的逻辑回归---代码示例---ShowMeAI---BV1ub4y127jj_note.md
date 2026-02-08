# 课程 P55：L8.5 - PyTorch 中的逻辑回归 - 代码示例 📝

![](img/eb410a541f0e309c0b9d6e6b05498cf9_1.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_3.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_5.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_7.png)

在本节课中，我们将通过一个完整的代码示例，来回顾并实践之前四节视频中讨论的逻辑回归核心概念。我们将从零开始实现一个逻辑回归模型，然后使用 PyTorch 的高级 API 来实现相同的功能，以加深对算法原理和实际应用的理解。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_8.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_10.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_12.png)

---

![](img/eb410a541f0e309c0b9d6e6b05498cf9_14.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_15.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_17.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_19.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_21.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_22.png)

## 概述与准备工作

在开始编写代码之前，我们需要导入必要的库并准备一个简单的二分类数据集。这个数据集与我们作业中使用的类似，非常适合用于演示。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_24.png)

以下是导入库和加载数据的代码：

![](img/eb410a541f0e309c0b9d6e6b05498cf9_26.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_28.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_30.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_31.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_32.png)

```python
import numpy as np
import matplotlib.pyplot as plt
import torch
import torch.nn as nn

![](img/eb410a541f0e309c0b9d6e6b05498cf9_34.png)

# 加载一个简单的二分类玩具数据集
# 这里使用 numpy 生成数据，实际中可以从文件加载
X_train, y_train = ... # 训练数据
X_test, y_test = ...   # 测试数据
```

![](img/eb410a541f0e309c0b9d6e6b05498cf9_36.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_38.png)

---

![](img/eb410a541f0e309c0b9d6e6b05498cf9_40.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_41.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_43.png)

## 从零开始实现逻辑回归 🔨

![](img/eb410a541f0e309c0b9d6e6b05498cf9_45.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_46.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_48.png)

上一节我们讨论了逻辑回归的数学原理，本节中我们来看看如何用代码实现它。我们将手动实现前向传播、反向传播（梯度计算）和参数更新。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_50.png)

以下是我们将实现的 `LogisticRegression` 类的核心方法：

![](img/eb410a541f0e309c0b9d6e6b05498cf9_52.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_54.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_56.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_58.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_60.png)

*   **`__init__`**: 初始化权重和偏置，这里我们将权重初始化为零向量。
*   **`forward`**: 计算净输入 `z` 和经过 Sigmoid 激活后的概率 `a`。
*   **`backward`**: 根据损失函数计算关于权重和偏置的梯度。
*   **`predict`**: 根据概率进行阈值判断（如 >0.5 为类别1），得到预测标签。
*   **`train`**: 整合上述步骤，执行多轮训练。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_62.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_64.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_66.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_68.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_70.png)

以下是 `LogisticRegression` 类的关键代码框架：

![](img/eb410a541f0e309c0b9d6e6b05498cf9_72.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_74.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_75.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_77.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_79.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_81.png)

```python
class LogisticRegression:
    def __init__(self, num_features):
        self.weights = torch.zeros(1, num_features)
        self.bias = torch.zeros(1)

    def forward(self, x):
        # 计算净输入 z = w*x + b
        z = torch.mm(x, self.weights.t()) + self.bias
        # 应用Sigmoid激活函数得到概率 a = σ(z)
        a = self._sigmoid(z)
        return a

    def backward(self, x, a, y):
        # 计算损失关于输出的梯度：∂L/∂a = (a - y)
        grad_a = a - y
        # 计算损失关于权重的梯度：∂L/∂w = (∂L/∂a) * (∂a/∂z) * x^T ≈ (a - y) * x^T
        grad_w = torch.mm(grad_a.t(), x)
        # 计算损失关于偏置的梯度：∂L/∂b = sum(a - y)
        grad_b = torch.sum(grad_a)
        return grad_w, grad_b

    def _sigmoid(self, z):
        return 1. / (1. + torch.exp(-z))

    def predict(self, x):
        # 获取概率
        a = self.forward(x)
        # 应用阈值函数
        y_pred = (a > 0.5).float()
        return y_pred
```

![](img/eb410a541f0e309c0b9d6e6b05498cf9_83.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_85.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_86.png)

训练循环的代码如下，它整合了前向传播、损失计算、反向传播和参数更新：

![](img/eb410a541f0e309c0b9d6e6b05498cf9_88.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_90.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_92.png)

```python
def train(model, X, y, epochs=30, lr=0.1):
    cost_list = []
    for epoch in range(epochs):
        # 1. 前向传播，计算输出概率 a
        a = model.forward(X)
        # 2. 计算损失（负对数似然）
        cost = -torch.sum(y * torch.log(a) + (1 - y) * torch.log(1 - a))
        cost_list.append(cost.item())
        # 3. 反向传播，计算梯度
        grad_w, grad_b = model.backward(X, a, y)
        # 4. 更新参数：w = w - lr * ∂L/∂w
        model.weights -= lr * grad_w
        model.bias -= lr * grad_b
    return cost_list
```

![](img/eb410a541f0e309c0b9d6e6b05498cf9_93.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_94.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_95.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_97.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_98.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_100.png)

运行这个从零开始的模型，我们可以看到它在训练集上快速收敛，并绘制出损失下降曲线和决策边界。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_102.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_104.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_105.png)

---

![](img/eb410a541f0e309c0b9d6e6b05498cf9_107.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_108.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_109.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_111.png)

## 使用 PyTorch 模块 API 实现逻辑回归 ⚙️

![](img/eb410a541f0e309c0b9d6e6b05498cf9_112.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_114.png)

手动实现有助于理解原理，但在实际项目中，我们更常使用深度学习框架提供的高级API。上一节我们手动计算了梯度，本节中我们来看看如何利用 PyTorch 的自动微分功能来简化这一过程。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_116.png)

使用 PyTorch 的 `nn.Module` 可以极大地简化代码。我们只需要定义网络结构，梯度计算和参数更新将由框架自动处理。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_118.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_119.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_120.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_121.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_122.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_124.png)

以下是使用 PyTorch API 实现的等效逻辑回归模型：

![](img/eb410a541f0e309c0b9d6e6b05498cf9_125.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_127.png)

```python
class LogisticRegressionPyTorch(nn.Module):
    def __init__(self, num_features):
        super().__init__()
        # 定义一个线性层：y = xA^T + b
        self.linear = nn.Linear(num_features, 1)
        # 为了与手动实现对比，将权重和偏置初始化为0
        self.linear.weight.data.fill_(0.0)
        self.linear.bias.data.fill_(0.0)

    def forward(self, x):
        # 线性层输出后接Sigmoid激活函数
        logits = self.linear(x)
        outputs = torch.sigmoid(logits)
        return outputs
```

![](img/eb410a541f0e309c0b9d6e6b05498cf9_129.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_131.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_133.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_135.png)

使用 PyTorch 进行训练的流程更加简洁和标准化：

![](img/eb410a541f0e309c0b9d6e6b05498cf9_136.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_138.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_139.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_141.png)

```python
# 初始化模型、损失函数和优化器
model = LogisticRegressionPyTorch(num_features)
criterion = nn.BCELoss(reduction='sum')  # 二元交叉熵损失，等价于负对数似然
optimizer = torch.optim.SGD(model.parameters(), lr=0.1)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_143.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_145.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_146.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_148.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_150.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_152.png)

# 训练循环
for epoch in range(epochs):
    # 前向传播
    outputs = model(X_train_tensor)
    # 计算损失
    loss = criterion(outputs, y_train_tensor)
    # 反向传播和优化
    optimizer.zero_grad()  # 清空过往梯度
    loss.backward()        # 自动计算梯度
    optimizer.step()       # 更新参数
```

![](img/eb410a541f0e309c0b9d6e6b05498cf9_154.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_156.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_158.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_160.png)

运行 PyTorch 版本的模型，我们会发现其学习到的权重和偏置与手动实现的版本完全相同，这验证了我们手动实现的正确性，并且测试准确率也保持一致。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_162.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_163.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_165.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_166.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_168.png)

---

![](img/eb410a541f0e309c0b9d6e6b05498cf9_170.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_172.png)

## 总结

![](img/eb410a541f0e309c0b9d6e6b05498cf9_174.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_175.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_176.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_178.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_180.png)

本节课中我们一起学习了逻辑回归的两种代码实现方式。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_182.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_183.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_185.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_187.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_189.png)

*   我们首先**从零开始**实现了逻辑回归模型，手动编写了前向传播、梯度计算（反向传播）和参数更新的代码。这个过程帮助我们深入理解了逻辑回归的**核心公式**，例如梯度 `∂L/∂w = (a - y) * x^T`。
*   接着，我们使用了 **PyTorch 的高级模块 API** 来构建相同的模型。利用 `nn.Linear`、`nn.BCELoss` 和 `torch.optim.SGD`，我们以更简洁、更高效的方式完成了模型的构建和训练，并且依赖 PyTorch 的自动微分机制自动计算梯度。

![](img/eb410a541f0e309c0b9d6e6b05498cf9_190.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_192.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_193.png)

![](img/eb410a541f0e309c0b9d6e6b05498cf9_194.png)

通过对比两种方法，我们不仅巩固了理论知识，也掌握了在实际项目中使用专业工具进行开发的技能。在接下来的课程中，我们将把这些概念推广到多类别分类问题，即 Softmax 回归。