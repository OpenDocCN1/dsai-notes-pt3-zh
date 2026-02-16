# 23：L3.4 - 使用 NumPy 和 PyTorch 实现感知器 🧠

在本节课中，我们将学习如何使用 Python 的 NumPy 库和 PyTorch 框架来构建一个感知器模型。我们将从数据加载和预处理开始，逐步实现感知器的核心算法，并最终评估其性能。本教程旨在让初学者能够清晰地理解每一步的实现细节。

所有代码文件都已在 GitHub 上提供。作业将基于 NumPy 版本，要求你用纯 Python 重新实现，以确保你理解其中的原理。从 NumPy 转换到纯 Python 对于初学者来说相对更容易。

---

![](img/1a656ff047ac6e99feba246a18f06448_1.png)

![](img/1a656ff047ac6e99feba246a18f06448_2.png)

## 1. 环境设置与数据加载

首先，我们需要导入必要的库并加载数据集。我们将使用 Jupyter Notebook 进行演示，因为它可以逐步执行代码，便于解释。

![](img/1a656ff047ac6e99feba246a18f06448_4.png)

```python
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
```

![](img/1a656ff047ac6e99feba246a18f06448_5.png)

![](img/1a656ff047ac6e99feba246a18f06448_7.png)

![](img/1a656ff047ac6e99feba246a18f06448_9.png)

![](img/1a656ff047ac6e99feba246a18f06448_11.png)

接下来，我们加载一个简单的玩具数据集。该数据集包含两个特征列和一个类别标签列（0 和 1）。

![](img/1a656ff047ac6e99feba246a18f06448_13.png)

```python
data = np.genfromtxt('perceptron_toydata.txt', delimiter='\t')
X = data[:, :2]  # 特征矩阵
y = data[:, 2]   # 类别标签数组
```

![](img/1a656ff047ac6e99feba246a18f06448_15.png)

![](img/1a656ff047ac6e99feba246a18f06448_17.png)

我们可以打印一些摘要信息来了解数据。

```python
print('Class label counts:', np.bincount(y.astype(int)))
print('X.shape:', X.shape)
print('y.shape:', y.shape)
```

![](img/1a656ff047ac6e99feba246a18f06448_19.png)

![](img/1a656ff047ac6e99feba246a18f06448_20.png)

![](img/1a656ff047ac6e99feba246a18f06448_21.png)

输出显示，我们有 100 个数据点，每个类别各 50 个样本，特征维度为 2。

![](img/1a656ff047ac6e99feba246a18f06448_23.png)

![](img/1a656ff047ac6e99feba246a18f06448_25.png)

---

![](img/1a656ff047ac6e99feba246a18f06448_27.png)

![](img/1a656ff047ac6e99feba246a18f06448_29.png)

## 2. 数据预处理

![](img/1a656ff047ac6e99feba246a18f06448_31.png)

![](img/1a656ff047ac6e99feba246a18f06448_32.png)

在训练模型之前，对数据进行适当的预处理是标准做法。这包括打乱数据顺序、划分训练集/测试集以及标准化特征。

![](img/1a656ff047ac6e99feba246a18f06448_33.png)

![](img/1a656ff047ac6e99feba246a18f06448_34.png)

![](img/1a656ff047ac6e99feba246a18f06448_36.png)

上一节我们加载了原始数据，本节中我们来看看如何进行预处理。

![](img/1a656ff047ac6e99feba246a18f06448_38.png)

![](img/1a656ff047ac6e99feba246a18f06448_40.png)

### 打乱数据顺序

![](img/1a656ff047ac6e99feba246a18f06448_42.png)

![](img/1a656ff047ac6e99feba246a18f06448_43.png)

![](img/1a656ff047ac6e99feba246a18f06448_44.png)

![](img/1a656ff047ac6e99feba246a18f06448_46.png)

打乱数据有助于模型学习，避免因数据顺序带来的偏差。

![](img/1a656ff047ac6e99feba246a18f06448_48.png)

![](img/1a656ff047ac6e99feba246a18f06448_49.png)

```python
shuffle_idx = np.arange(y.shape[0])
shuffle_rng = np.random.RandomState(123)
shuffle_rng.shuffle(shuffle_idx)
X, y = X[shuffle_idx], y[shuffle_idx]
```

![](img/1a656ff047ac6e99feba246a18f06448_51.png)

![](img/1a656ff047ac6e99feba246a18f06448_53.png)

### 划分训练集和测试集

![](img/1a656ff047ac6e99feba246a18f06448_55.png)

![](img/1a656ff047ac6e99feba246a18f06448_56.png)

![](img/1a656ff047ac6e99feba246a18f06448_57.png)

![](img/1a656ff047ac6e99feba246a18f06448_58.png)

我们将使用前 70 个样本作为训练集，后 30 个样本作为测试集。

![](img/1a656ff047ac6e99feba246a18f06448_60.png)

```python
X_train, X_test = X[:70], X[70:]
y_train, y_test = y[:70], y[70:]
```

![](img/1a656ff047ac6e99feba246a18f06448_62.png)

### 标准化特征

![](img/1a656ff047ac6e99feba246a18f06448_64.png)

![](img/1a656ff047ac6e99feba246a18f06448_66.png)

![](img/1a656ff047ac6e99feba246a18f06448_68.png)

标准化（或称为 Z-score 归一化）使每个特征的均值为 0，标准差为 1。这通常能加速后续优化算法的收敛。

```python
mu, sigma = X_train.mean(axis=0), X_train.std(axis=0)
X_train = (X_train - mu) / sigma
X_test = (X_test - mu) / sigma
```

标准化后，我们可以快速验证训练集特征的均值和标准差。

```python
print('Mean train:', X_train.mean(axis=0))
print('Std train:', X_train.std(axis=0))
```

![](img/1a656ff047ac6e99feba246a18f06448_70.png)

---

![](img/1a656ff047ac6e99feba246a18f06448_72.png)

![](img/1a656ff047ac6e99feba246a18f06448_73.png)

![](img/1a656ff047ac6e99feba246a18f06448_74.png)

## 3. 可视化数据集

![](img/1a656ff047ac6e99feba246a18f06448_76.png)

![](img/1a656ff047ac6e99feba246a18f06448_77.png)

![](img/1a656ff047ac6e99feba246a18f06448_79.png)

在实现模型之前，先可视化处理后的数据，了解其分布。

![](img/1a656ff047ac6e99feba246a18f06448_81.png)

![](img/1a656ff047ac6e99feba246a18f06448_82.png)

以下是训练集数据的散点图，其中圆形代表类别 0，方形代表类别 1。

```python
plt.scatter(X_train[y_train==0, 0], X_train[y_train==0, 1], label='class 0', marker='o')
plt.scatter(X_train[y_train==1, 0], X_train[y_train==1, 1], label='class 1', marker='s')
plt.xlabel('feature 1')
plt.ylabel('feature 2')
plt.legend()
plt.show()
```

![](img/1a656ff047ac6e99feba246a18f06448_84.png)

我们的目标是训练一个模型，使其能够在特征空间中画出一条直线（决策边界）来区分这两个类别。

![](img/1a656ff047ac6e99feba246a18f06448_86.png)

![](img/1a656ff047ac6e99feba246a18f06448_87.png)

![](img/1a656ff047ac6e99feba246a18f06448_89.png)

---

![](img/1a656ff047ac6e99feba246a18f06448_91.png)

![](img/1a656ff047ac6e99feba246a18f06448_93.png)

## 4. 实现感知器类

![](img/1a656ff047ac6e99feba246a18f06448_95.png)

现在，我们开始实现感知器算法。我们将它封装成一个 Python 类，模仿 PyTorch 的风格，包含 `forward` 和 `backward` 方法，为后续学习更复杂的神经网络打下基础。

### 初始化权重和偏置

![](img/1a656ff047ac6e99feba246a18f06448_97.png)

![](img/1a656ff047ac6e99feba246a18f06448_99.png)

在构造函数中，我们根据输入特征的数量初始化权重向量和偏置项。这里我们将权重和偏置分开存储，这样更清晰。

![](img/1a656ff047ac6e99feba246a18f06448_101.png)

![](img/1a656ff047ac6e99feba246a18f06448_103.png)

```python
class Perceptron:
    def __init__(self, num_features):
        self.num_features = num_features
        self.weights = np.zeros(num_features)
        self.bias = 0.0
```

![](img/1a656ff047ac6e99feba246a18f06448_105.png)

公式表示如下：
*   权重向量: **w** = [w₁, w₂, ..., wₙ]
*   偏置: *b*

![](img/1a656ff047ac6e99feba246a18f06448_107.png)

![](img/1a656ff047ac6e99feba246a18f06448_109.png)

### 前向传播方法

![](img/1a656ff047ac6e99feba246a18f06448_111.png)

![](img/1a656ff047ac6e99feba246a18f06448_113.png)

![](img/1a656ff047ac6e99feba246a18f06448_115.png)

`forward` 方法计算净输入 `z`（即线性组合），然后通过阶跃函数（阈值函数）将其转换为二元预测（0 或 1）。

![](img/1a656ff047ac6e99feba246a18f06448_117.png)

![](img/1a656ff047ac6e99feba246a18f06448_119.png)

![](img/1a656ff047ac6e99feba246a18f06448_121.png)

```python
    def forward(self, x):
        # 计算净输入 z = w·x + b
        linear = np.dot(x, self.weights) + self.bias
        # 应用阶跃函数作为激活函数
        predictions = np.where(linear > 0.0, 1, 0)
        return predictions
```

![](img/1a656ff047ac6e99feba246a18f06448_123.png)

![](img/1a656ff047ac6e99feba246a18f06448_125.png)

![](img/1a656ff047ac6e99feba246a18f06448_127.png)

其中，阶跃函数定义为：
**predictions** = 1 if **z** > 0 else 0

![](img/1a656ff047ac6e99feba246a18f06448_129.png)

### 后向传播方法

![](img/1a656ff047ac6e99feba246a18f06448_131.png)

`backward` 方法计算预测值与真实标签之间的误差。对于感知器，这就是简单的差值。

![](img/1a656ff047ac6e99feba246a18f06448_133.png)

![](img/1a656ff047ac6e99feba246a18f06448_134.png)

```python
    def backward(self, x, y):
        predictions = self.forward(x)
        errors = y - predictions
        return errors
```

![](img/1a656ff047ac6e99feba246a18f06448_136.png)

![](img/1a656ff047ac6e99feba246a18f06448_138.png)

![](img/1a656ff047ac6e99feba246a18f06448_139.png)

![](img/1a656ff047ac6e99feba246a18f06448_141.png)

---

![](img/1a656ff047ac6e99feba246a18f06448_143.png)

![](img/1a656ff047ac6e99feba246a18f06448_145.png)

## 5. 训练循环

我们将训练逻辑封装在 `train` 方法中。它遵循标准的感知器学习规则：遍历多个轮次（epoch），对每个训练样本进行预测，计算误差，并更新权重和偏置。

![](img/1a656ff047ac6e99feba246a18f06448_147.png)

![](img/1a656ff047ac6e99feba246a18f06448_149.png)

![](img/1a656ff047ac6e99feba246a18f06448_151.png)

上一节我们定义了感知器的核心计算，本节中我们来看看如何用这些计算来更新模型参数。

![](img/1a656ff047ac6e99feba246a18f06448_153.png)

![](img/1a656ff047ac6e99feba246a18f06448_155.png)

以下是训练过程的步骤：

![](img/1a656ff047ac6e99feba246a18f06448_157.png)

1.  **遍历训练轮次**：决定模型查看整个训练集的次数。
2.  **遍历每个样本**：在线学习，每次用一个样本更新模型。
3.  **前向与后向传播**：获取预测并计算误差。
4.  **参数更新**：根据误差更新权重和偏置。

![](img/1a656ff047ac6e99feba246a18f06448_159.png)

![](img/1a656ff047ac6e99feba246a18f06448_160.png)

更新规则如下：
*   **w** = **w** + η * error * **x**
*   *b* = *b* + η * error

![](img/1a656ff047ac6e99feba246a18f06448_162.png)

![](img/1a656ff047ac6e99feba246a18f06448_163.png)

![](img/1a656ff047ac6e99feba246a18f06448_165.png)

![](img/1a656ff047ac6e99feba246a18f06448_167.png)

其中 η 是学习率，这里我们设为 1。

![](img/1a656ff047ac6e99feba246a18f06448_169.png)

![](img/1a656ff047ac6e99feba246a18f06448_170.png)

![](img/1a656ff047ac6e99feba246a18f06448_171.png)

```python
    def train(self, X, y, epochs, learning_rate=1.0):
        for epoch in range(epochs):
            for i in range(y.shape[0]):
                # 获取单个样本，并调整维度以匹配权重向量
                x_i = X[i].reshape(1, -1)
                y_i = y[i].reshape(1,)

                # 计算误差
                errors = self.backward(x_i, y_i).reshape(-1)

                # 更新权重和偏置
                self.weights += learning_rate * errors * x_i.reshape(self.weights.shape)
                self.bias += learning_rate * errors
```

![](img/1a656ff047ac6e99feba246a18f06448_173.png)

![](img/1a656ff047ac6e99feba246a18f06448_175.png)

![](img/1a656ff047ac6e99feba246a18f06448_176.png)

在更新时需要注意数组维度的匹配，因此代码中做了一些 `reshape` 操作。

![](img/1a656ff047ac6e99feba246a18f06448_178.png)

![](img/1a656ff047ac6e99feba246a18f06448_179.png)

---

![](img/1a656ff047ac6e99feba246a18f06448_181.png)

![](img/1a656ff047ac6e99feba246a18f06448_182.png)

![](img/1a656ff047ac6e99feba246a18f06448_183.png)

## 6. 模型评估与决策边界

![](img/1a656ff047ac6e99feba246a18f06448_185.png)

训练完成后，我们需要评估模型在训练集和测试集上的性能，并可视化其学到的决策边界。

![](img/1a656ff047ac6e99feba246a18f06448_187.png)

![](img/1a656ff047ac6e99feba246a18f06448_189.png)

![](img/1a656ff047ac6e99feba246a18f06448_191.png)

### 计算准确率

我们实现一个 `evaluate` 方法来计算模型在给定数据集上的分类准确率。

![](img/1a656ff047ac6e99feba246a18f06448_193.png)

```python
    def evaluate(self, X, y):
        predictions = self.forward(X).reshape(-1)
        accuracy = np.sum(predictions == y) / y.shape[0]
        return accuracy
```

![](img/1a656ff047ac6e99feba246a18f06448_195.png)

### 训练与评估模型

![](img/1a656ff047ac6e99feba246a18f06448_196.png)

现在，让我们实例化感知器，在训练集上训练它，然后进行评估。

![](img/1a656ff047ac6e99feba246a18f06448_198.png)

![](img/1a656ff047ac6e99feba246a18f06448_199.png)

![](img/1a656ff047ac6e99feba246a18f06448_200.png)

![](img/1a656ff047ac6e99feba246a18f06448_201.png)

![](img/1a656ff047ac6e99feba246a18f06448_203.png)

```python
ppn = Perceptron(num_features=2)
ppn.train(X_train, y_train, epochs=5)

![](img/1a656ff047ac6e99feba246a18f06448_205.png)

![](img/1a656ff047ac6e99feba246a18f06448_207.png)

print('Model parameters:')
print('  Weights:', ppn.weights)
print('  Bias:', ppn.bias)

![](img/1a656ff047ac6e99feba246a18f06448_209.png)

train_acc = ppn.evaluate(X_train, y_train)
test_acc = ppn.evaluate(X_test, y_test)
print(f'Train accuracy: {train_acc*100:.2f}%')
print(f'Test accuracy: {test_acc*100:.2f}%')
```

![](img/1a656ff047ac6e99feba246a18f06448_211.png)

![](img/1a656ff047ac6e99feba246a18f06448_212.png)

对于线性可分的数据，感知器在训练集上应该能达到 100% 的准确率。在测试集上的准确率可能略低，这可能是过拟合的迹象。

![](img/1a656ff047ac6e99feba246a18f06448_213.png)

![](img/1a656ff047ac6e99feba246a18f06448_214.png)

### 可视化决策边界

决策边界是满足 **w·x + b = 0** 的点的集合。为了在二维平面上画出这条直线，我们可以固定 x₁（横轴）的范围，然后解出对应的 x₂（纵轴）的值。

![](img/1a656ff047ac6e99feba246a18f06448_216.png)

由 **w₁x₁ + w₂x₂ + b = 0**，可得：
**x₂ = (-w₁x₁ - b) / w₂**

![](img/1a656ff047ac6e99feba246a18f06448_217.png)

![](img/1a656ff047ac6e99feba246a18f06448_219.png)

![](img/1a656ff047ac6e99feba246a18f06448_220.png)

```python
# 计算决策边界线的两个端点
x_min = -2
x_max = 2
w1, w2 = ppn.weights
b = ppn.bias

![](img/1a656ff047ac6e99feba246a18f06448_221.png)

![](img/1a656ff047ac6e99feba246a18f06448_223.png)

![](img/1a656ff047ac6e99feba246a18f06448_224.png)

x1 = np.array([x_min, x_max])
x2 = -(w1 * x1 + b) / w2

![](img/1a656ff047ac6e99feba246a18f06448_226.png)

![](img/1a656ff047ac6e99feba246a18f06448_228.png)

# 绘图
plt.scatter(X_train[y_train==0, 0], X_train[y_train==0, 1], label='class 0', marker='o')
plt.scatter(X_train[y_train==1, 0], X_train[y_train==1, 1], label='class 1', marker='s')
plt.plot(x1, x2, color='red', linewidth=2, label='decision boundary')
plt.xlabel('feature 1')
plt.ylabel('feature 2')
plt.xlim([x_min, x_max])
plt.legend()
plt.show()
```

![](img/1a656ff047ac6e99feba246a18f06448_230.png)

![](img/1a656ff047ac6e99feba246a18f06448_231.png)

左图展示了模型在训练集上的决策边界，它完美地分开了两类数据。右图（测试集）显示，由于过拟合，模型在未见过的数据上分类效果稍差。

---

![](img/1a656ff047ac6e99feba246a18f06448_233.png)

![](img/1a656ff047ac6e99feba246a18f06448_234.png)

![](img/1a656ff047ac6e99feba246a18f06448_236.png)

## 7. NumPy 与 PyTorch 实现对比

![](img/1a656ff047ac6e99feba246a18f06448_238.png)

![](img/1a656ff047ac6e99feba246a18f06448_240.png)

![](img/1a656ff047ac6e99feba246a18f06448_242.png)

感知器也可以用 PyTorch 实现，其代码结构与 NumPy 版本非常相似，这体现了 PyTorch 设计上对 NumPy 的友好性。主要区别在于数据结构和一些函数调用上。

以下是核心部分的主要对比：

| 操作 | NumPy 实现 | PyTorch 实现 |
| :--- | :--- | :--- |
| **数组创建** | `np.zeros(num_features)` | `torch.zeros(num_features, dtype=torch.float32)` |
| **矩阵乘法** | `np.dot(x, weights)` | `torch.mm(x, weights.view(1, -1).t())` 或 `x @ weights` |
| **条件赋值** | `np.where(linear > 0.0, 1, 0)` | `torch.where(linear > 0.0, torch.tensor(1), torch.tensor(0))` |
| **求和** | `np.sum(predictions == y)` | `(predictions == y).sum().float()` |

PyTorch 版本的优势在于可以轻松利用 GPU 加速，并且为构建更复杂的神经网络提供了自动微分等强大功能。我们将在后续课程中详细探讨 PyTorch。

![](img/1a656ff047ac6e99feba246a18f06448_244.png)

---

## 8. 关于感知器收敛定理

![](img/1a656ff047ac6e99feba246a18f06448_246.png)

![](img/1a656ff047ac6e99feba246a18f06448_247.png)

感知器算法有一个重要的理论性质：**如果训练数据是线性可分的，那么感知器保证在有限次迭代内收敛到一个解（即能够完美分类所有训练样本的权重）**。反之，如果数据不是线性可分的，算法将永远不会收敛，权重会持续振荡。

![](img/1a656ff047ac6e99feba246a18f06448_249.png)

相关的数学证明涉及为权重的范数设定上下界。虽然理解这个证明有助于深入理解算法，但对于入门深度学习而言，记住上述结论即可。在实践中，你可以通过尝试分类非线性可分的数据来直观观察算法无法收敛的现象。

![](img/1a656ff047ac6e99feba246a18f06448_250.png)

---

![](img/1a656ff047ac6e99feba246a18f06448_252.png)

![](img/1a656ff047ac6e99feba246a18f06448_254.png)

## 总结

![](img/1a656ff047ac6e99feba246a18f06448_256.png)

本节课中我们一起学习了感知器算法的完整实现流程。

1.  我们使用 NumPy 进行了数据加载、打乱、划分和标准化。
2.  我们实现了一个 `Perceptron` 类，包含 `forward`（计算预测）、`backward`（计算误差）和 `train`（更新参数）方法。
3.  我们训练了模型，评估了其准确率，并可视化出决策边界，直观理解了模型的分类原理。
4.  我们简要对比了 NumPy 和 PyTorch 在实现上的异同。
5.  我们提到了感知器收敛定理的核心结论。

![](img/1a656ff047ac6e99feba246a18f06448_258.png)

![](img/1a656ff047ac6e99feba246a18f06448_259.png)

![](img/1a656ff047ac6e99feba246a18f06448_261.png)

通过本教程，你应该对感知器如何工作以及如何在代码中实现它有了扎实的理解。在作业中，你将有机会通过用纯 Python 重写这个模型来进一步巩固这些概念。