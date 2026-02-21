# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p36 Recitation_HW1_NumPy.zh_en -BV1Z2cUefE4A_p36-

![](img/a35a8cd140052c25b68a637ef74e6e63_1.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_2.png)

## Python包Numpy简介

![](img/a35a8cd140052c25b68a637ef74e6e63_4.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_6.png)

Numpy是一个Python库，允许我们方便且高效地操作矩阵和向量。在进行线性代数运算时，Numpy非常有用。

![](img/a35a8cd140052c25b68a637ef74e6e63_8.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_10.png)

### 安装Numpy

![](img/a35a8cd140052c25b68a637ef74e6e63_12.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_14.png)

要在Mac或其他机器上安装Numpy，只需在虚拟环境中像安装任何其他包一样使用`pip install Numpy`，并将Numpy导入为`NP`。

![](img/a35a8cd140052c25b68a637ef74e6e63_16.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_17.png)

```python
import numpy as NP
```

![](img/a35a8cd140052c25b68a637ef74e6e63_19.png)

### 加载数据

![](img/a35a8cd140052c25b68a637ef74e6e63_21.png)

以下是如何在Mac或其他机器上安装Numpy的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_23.png)

```python
!pip install numpy
```

![](img/a35a8cd140052c25b68a637ef74e6e63_25.png)

### 加载数据文件

以下是如何导入Numpy的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_27.png)

```python
import numpy as NP
NP.random.seed(0)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_29.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_31.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_33.png)

### 打印版本信息

![](img/a35a8cd140052c25b68a637ef74e6e63_35.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_37.png)

```python
print(NP.__version__)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_39.png)

### 加载数据

![](img/a35a8cd140052c25b68a637ef74e6e63_41.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_43.png)

以下是如何加载数据的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_45.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_46.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_48.png)

```python
data = NP.loadtxt("data.tsv", delimiter="\t")
```

### 打印数据

![](img/a35a8cd140052c25b68a637ef74e6e63_50.png)

```python
print(data)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_52.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_54.png)

### 索引

![](img/a35a8cd140052c25b68a637ef74e6e63_56.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_57.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_58.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_59.png)

以下是Numpy索引的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_61.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_62.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_64.png)

```python
data[0, 0]  # 第一个元素
data[0, :]  # 第一行
data[:, 0]  # 第一列
data[0:2, 0:2]  # 第一行和第一列
```

![](img/a35a8cd140052c25b68a637ef74e6e63_66.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_67.png)

### 切片

![](img/a35a8cd140052c25b68a637ef74e6e63_68.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_69.png)

以下是Numpy切片的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_71.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_72.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_74.png)

```python
data[0:2, 0:2]  # 第一行和第一列
data[0:2, 2:]  # 第一行和第三列到最后一列
data[:, 0:2]  # 第一列和第二列
```

![](img/a35a8cd140052c25b68a637ef74e6e63_76.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_78.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_80.png)

### 获取数组大小

![](img/a35a8cd140052c25b68a637ef74e6e63_82.png)

```python
data.shape
```

### 向量和数组

![](img/a35a8cd140052c25b68a637ef74e6e63_84.png)

以下是Numpy向量和数组的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_86.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_88.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_89.png)

```python
x = NP.array([[1, 2, 3], [4, 5, 6]])
y = x[0, :]
y1 = x[:, 0]
```

### 转置

![](img/a35a8cd140052c25b68a637ef74e6e63_91.png)

```python
y2 = NP.reshape(y, (1, 4))
y2.T
```

![](img/a35a8cd140052c25b68a637ef74e6e63_93.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_94.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_95.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_96.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_98.png)

### 初始化

![](img/a35a8cd140052c25b68a637ef74e6e63_100.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_102.png)

以下是Numpy初始化的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_104.png)

```python
NP.eye(4)
NP.zeros((2, 2))
NP.ones((2, 2))
NP.random.rand(2, 2)
NP.random.randint(0, 10, (2, 2))
```

![](img/a35a8cd140052c25b68a637ef74e6e63_106.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_107.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_109.png)

### 调整形状

![](img/a35a8cd140052c25b68a637ef74e6e63_111.png)

以下是Numpy调整形状的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_113.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_114.png)

```python
x = NP.array([[1, 2, 3, 4], [5, 6, 7, 8]])
x.reshape(2, 8)
x.reshape(8, 1)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_116.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_118.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_120.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_122.png)

### 拼接

![](img/a35a8cd140052c25b68a637ef74e6e63_124.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_125.png)

以下是Numpy拼接的示例：

![](img/a35a8cd140052c25b68a637ef74e6e63_127.png)

```python
x = NP.array([[1, 2], [3, 4]])
y = NP.array([[5, 6], [7, 8]])
NP.hstack((x, y))
NP.vstack((x, y))
```

![](img/a35a8cd140052c25b68a637ef74e6e63_129.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_131.png)

### 矩阵运算

![](img/a35a8cd140052c25b68a637ef74e6e63_133.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_135.png)

以下是Numpy矩阵运算的示例：

```python
x = NP.array([[1, 2], [3, 4]])
y = NP.array([[5, 6], [7, 8]])
x + y
x - y
x * 4
x @ y
x * y
NP.exp(x)
NP.log(x)
NP.max(x)
NP.min(x)
NP.max(x, axis=0)
NP.min(x, axis=1)
NP.max(x, axis=0, keepdims=True)
NP.min(x, axis=1, keepdims=True)
NP.max(x, axis=0, out=y)
NP.min(x, axis=1, out=y)
NP.max(x, axis=0, out=y, keepdims=True)
NP.min(x, axis=1, out=y, keepdims=True)
NP.sum(x)
NP.sum(x, axis=0)
NP.sum(x, axis=1)
```

![](img/a35a8cd140052c25b68a637ef74e6e63_137.png)

![](img/a35a8cd140052c25b68a637ef74e6e63_139.png)

本节课中我们一起学习了Numpy的基本操作，包括安装、加载数据、索引、切片、初始化、调整形状、拼接、矩阵运算等。