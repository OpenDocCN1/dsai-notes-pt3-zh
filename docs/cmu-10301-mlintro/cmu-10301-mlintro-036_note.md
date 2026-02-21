# 机器学习导论：1：NumPy入门教程 🐍

![](img/a35a8cd140052c25b68a637ef74e6e63_1.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_2.png)

在本节课中，我们将要学习Python中一个非常重要的科学计算库——NumPy。NumPy是进行机器学习、数据分析和科学计算的基础，它提供了高效的多维数组对象和一系列操作这些数组的工具。掌握NumPy是学习后续机器学习算法的关键一步。

![](img/a35a8cd140052c25b68a637ef74e6e63_4.png)

## 概述 📋

![](img/a35a8cd140052c25b68a637ef74e6e63_6.png)

NumPy是一个Python库，它允许我们方便且高效地操作矩阵和向量。在进行线性代数运算时，NumPy非常有用。

![](img/a35a8cd140052c25b68a637ef74e6e63_8.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_10.png)

## 安装与导入 🔧

![](img/a35a8cd140052c25b68a637ef74e6e63_12.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_14.png)

要在Mac或其他机器上安装NumPy，只需在虚拟环境中像安装任何其他包一样使用 `pip install numpy`。

以下是安装NumPy的示例代码：

![](img/a35a8cd140052c25b68a637ef74e6e63_16.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_17.png)

```python
!pip install numpy
```

![](img/a35a8cd140052c25b68a637ef74e6e63_19.png)

安装完成后，我们需要在Python脚本或交互式环境中导入NumPy。通常我们将其导入为 `np`。

![](img/a35a8cd140052c25b68a637ef74e6e63_21.png)

以下是导入NumPy的示例代码：

![](img/a35a8cd140052c25b68a637ef74e6e63_23.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_25.png)

```python
import numpy as np
```

![](img/a35a8cd140052c25b68a637ef74e6e63_27.png)

导入后，我们可以设置随机种子以确保代码的可重复性。

![](img/a35a8cd140052c25b68a637ef74e6e63_29.png)

```python
np.random.seed(0)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_31.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_33.png)

为了确认安装成功，可以打印NumPy的版本信息。

![](img/a35a8cd140052c25b68a637ef74e6e63_35.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_37.png)

```python
print(np.__version__)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_39.png)

## 数据加载与基础操作 📂

![](img/a35a8cd140052c25b68a637ef74e6e63_41.png)

上一节我们介绍了如何安装和导入NumPy，本节中我们来看看如何加载数据并进行一些基础操作。

![](img/a35a8cd140052c25b68a637ef74e6e63_43.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_45.png)

### 加载数据文件

![](img/a35a8cd140052c25b68a637ef74e6e63_46.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_48.png)

NumPy可以方便地从文本文件中加载数据。假设我们有一个名为 `data.tsv` 的文件，数据以制表符分隔。

以下是加载数据的示例代码：

![](img/a35a8cd140052c25b68a637ef74e6e63_50.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_52.png)

```python
data = np.loadtxt(“data.tsv”, delimiter=“\t”)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_54.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_56.png)

加载数据后，我们可以使用 `print` 函数查看数组的内容。

![](img/a35a8cd140052c25b68a637ef74e6e63_57.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_58.png)

```python
print(data)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_59.png)

### 理解数组形状

![](img/a35a8cd140052c25b68a637ef74e6e63_61.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_62.png)

在处理数组之前，了解其维度（形状）非常重要。我们可以使用 `.shape` 属性来获取数组的大小。

![](img/a35a8cd140052c25b68a637ef74e6e63_64.png)

```python
data.shape
```

![](img/a35a8cd140052c25b68a637ef74e6e63_66.png)

这个属性会返回一个元组，例如 `(m, n)`，表示数组有 `m` 行和 `n` 列。

![](img/a35a8cd140052c25b68a637ef74e6e63_67.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_68.png)

## 数组索引与切片 🔪

![](img/a35a8cd140052c25b68a637ef74e6e63_69.png)

理解了如何加载数据后，接下来我们需要学习如何访问和操作数组中的特定元素或子集。这通过索引和切片来实现。

![](img/a35a8cd140052c25b68a637ef74e6e63_71.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_72.png)

### 索引

![](img/a35a8cd140052c25b68a637ef74e6e63_74.png)

索引用于访问数组中的单个元素。NumPy数组的索引从0开始。

![](img/a35a8cd140052c25b68a637ef74e6e63_76.png)

以下是NumPy索引的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_78.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_80.png)

```python
data[0, 0]  # 访问第0行第0列的元素（第一个元素）
data[0, :]  # 访问第0行的所有元素（第一行）
data[:, 0]  # 访问第0列的所有元素（第一列）
data[0:2, 0:2]  # 访问第0到1行，第0到1列的子矩阵
```

![](img/a35a8cd140052c25b68a637ef74e6e63_82.png)

### 切片

![](img/a35a8cd140052c25b68a637ef74e6e63_84.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_86.png)

切片用于访问数组中的连续子序列。其语法为 `start:stop:step`。

![](img/a35a8cd140052c25b68a637ef74e6e63_88.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_89.png)

以下是NumPy切片的示例：

```python
data[0:2, 0:2]  # 访问第0到1行，第0到1列
data[0:2, 2:]   # 访问第0到1行，第2列到最后一列
data[:, 0:2]    # 访问所有行，第0到1列
```

![](img/a35a8cd140052c25b68a637ef74e6e63_91.png)

## 创建与操作数组 🏗️

![](img/a35a8cd140052c25b68a637ef74e6e63_93.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_94.png)

我们已经学会了如何访问现有数组，现在让我们看看如何从头开始创建数组，并对其进行变形和组合。

![](img/a35a8cd140052c25b68a637ef74e6e63_95.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_96.png)

### 初始化数组

![](img/a35a8cd140052c25b68a637ef74e6e63_98.png)

NumPy提供了多种函数来创建具有特定内容的数组。

![](img/a35a8cd140052c25b68a637ef74e6e63_100.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_102.png)

以下是NumPy初始化的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_104.png)

```python
np.eye(4)                     # 创建一个4x4的单位矩阵
np.zeros((2, 2))              # 创建一个2x2的全零矩阵
np.ones((2, 2))               # 创建一个2x2的全一矩阵
np.random.rand(2, 2)          # 创建一个2x2的随机矩阵（元素在[0,1)均匀分布）
np.random.randint(0, 10, (2, 2)) # 创建一个2x2的随机整数矩阵（元素在[0,10)）
```

![](img/a35a8cd140052c25b68a637ef74e6e63_106.png)

### 调整数组形状

![](img/a35a8cd140052c25b68a637ef74e6e63_107.png)

我们可以使用 `.reshape()` 方法来改变数组的维度，而不改变其数据。

![](img/a35a8cd140052c25b68a637ef74e6e63_109.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_111.png)

以下是调整形状的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_113.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_114.png)

```python
x = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])
x.reshape(2, 8)  # 将2x4的数组重塑为2x8
x.reshape(8, 1)  # 将2x4的数组重塑为8x1（一个列向量）
```

### 拼接数组

![](img/a35a8cd140052c25b68a637ef74e6e63_116.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_118.png)

有时我们需要将多个数组合并在一起。NumPy提供了水平拼接 (`hstack`) 和垂直拼接 (`vstack`) 的功能。

![](img/a35a8cd140052c25b68a637ef74e6e63_120.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_122.png)

以下是NumPy拼接的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_124.png)

```python
x = np.array([[1, 2], [3, 4]])
y = np.array([[5, 6], [7, 8]])
np.hstack((x, y))  # 水平拼接，结果形状为 (2, 4)
np.vstack((x, y))  # 垂直拼接，结果形状为 (4, 2)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_125.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_127.png)

## 矩阵运算 ➕➖✖️

创建和组合数组是基础，但NumPy真正的威力在于其强大的数学运算能力。本节我们将学习基本的矩阵和元素级运算。

![](img/a35a8cd140052c25b68a637ef74e6e63_129.png)

以下是NumPy矩阵运算的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_131.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_133.png)

```python
x = np.array([[1, 2], [3, 4]])
y = np.array([[5, 6], [7, 8]])

![](img/a35a8cd140052c25b68a637ef74e6e63_135.png)

# 基本算术运算
x + y          # 矩阵加法（对应元素相加）
x - y          # 矩阵减法（对应元素相减）
x * 4          # 标量乘法（每个元素乘以4）
x @ y          # 矩阵乘法（线性代数中的点积）
x * y          # 逐元素乘法（哈达玛积）

# 数学函数（逐元素应用）
np.exp(x)      # 计算每个元素的指数 e^x
np.log(x)      # 计算每个元素的自然对数 ln(x)

# 聚合函数
np.max(x)      # 返回整个数组的最大值
np.min(x)      # 返回整个数组的最小值
np.sum(x)      # 返回整个数组所有元素的和

# 沿指定轴进行聚合
np.max(x, axis=0)   # 返回每一列的最大值（沿行方向压缩）
np.min(x, axis=1)   # 返回每一行的最小值（沿列方向压缩）
np.sum(x, axis=0)   # 返回每一列的和
np.sum(x, axis=1)   # 返回每一行的和

# 保持维度
np.max(x, axis=0, keepdims=True) # 返回每一列的最大值，但保持二维形状
np.min(x, axis=1, keepdims=True) # 返回每一行的最小值，但保持二维形状
```

![](img/a35a8cd140052c25b68a637ef74e6e63_137.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_139.png)

## 总结 🎯

本节课中我们一起学习了NumPy的基本操作。我们从安装和导入NumPy开始，然后学习了如何从文件加载数据。接着，我们深入探讨了数组的索引和切片，这是访问数据的基础。之后，我们掌握了创建各种数组（如零矩阵、单位矩阵、随机矩阵）的方法，以及如何调整数组形状和拼接多个数组。最后，我们学习了NumPy强大的数学运算功能，包括基本的算术运算、矩阵乘法、数学函数应用以及沿不同轴进行聚合计算（如求和、求最大值/最小值）。这些操作是后续进行数据预处理、特征工程和实现机器学习算法的基石。