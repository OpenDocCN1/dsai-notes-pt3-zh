# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕教程

## 1. 决策树分类

在本节中，我们将学习如何使用决策树进行分类。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_1.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_3.png)

### 1.1 决策树分类原理

![](img/3cd47ee8bea92fc84c530ca184d83cfa_5.png)

决策树是一种基于树形结构的分类算法。它通过一系列的规则将数据集划分为不同的类别。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_7.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_9.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_11.png)

**公式**：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_13.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_15.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_17.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_18.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_20.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_22.png)

```
决策树分类 = 决策树(数据集)
```

### 1.2 决策树构建

决策树的构建过程如下：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_24.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_25.png)

1. 选择一个特征作为根节点。
2. 根据该特征将数据集划分为不同的子集。
3. 对每个子集重复步骤1和2，直到满足停止条件。

### 1.3 决策树应用

![](img/3cd47ee8bea92fc84c530ca184d83cfa_27.png)

决策树可以用于分类和回归任务。

## 2. K近邻分类

在本节中，我们将学习如何使用K近邻算法进行分类。

### 2.1 K近邻分类原理

K近邻算法是一种基于距离的分类算法。它通过计算数据点到训练数据点的距离，并将数据点分配到距离最近的类别。

**公式**：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_29.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_31.png)

```
K近邻分类 = K近邻(数据点, 训练数据集, k)
```

### 2.2 K近邻参数

![](img/3cd47ee8bea92fc84c530ca184d83cfa_33.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_35.png)

K近邻算法有两个参数：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_37.png)

1. k：邻居的数量。
2. 距离度量：常用的距离度量有欧几里得距离和曼哈顿距离。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_39.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_40.png)

### 2.3 K近邻应用

![](img/3cd47ee8bea92fc84c530ca184d83cfa_42.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_43.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_44.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_46.png)

K近邻算法可以用于分类和回归任务。

## 3. 线性回归

![](img/3cd47ee8bea92fc84c530ca184d83cfa_48.png)

在本节中，我们将学习如何使用线性回归进行回归分析。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_50.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_52.png)

### 3.1 线性回归原理

![](img/3cd47ee8bea92fc84c530ca184d83cfa_54.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_55.png)

线性回归是一种基于线性模型的回归算法。它通过拟合数据点到一条直线，来预测连续值。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_57.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_59.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_61.png)

**公式**：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_63.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_65.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_67.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_68.png)

```
线性回归 = 线性模型(数据集)
```

![](img/3cd47ee8bea92fc84c530ca184d83cfa_70.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_72.png)

### 3.2 线性回归参数

![](img/3cd47ee8bea92fc84c530ca184d83cfa_74.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_76.png)

线性回归模型有两个参数：

1. 权重：用于控制特征对预测结果的影响。
2. 偏置：用于调整预测结果。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_78.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_80.png)

### 3.3 线性回归应用

线性回归可以用于回归分析。

## 4. 梯度下降

![](img/3cd47ee8bea92fc84c530ca184d83cfa_82.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_83.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_85.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_87.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_89.png)

在本节中，我们将学习如何使用梯度下降算法优化线性回归模型。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_91.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_93.png)

### 4.1 梯度下降原理

![](img/3cd47ee8bea92fc84c530ca184d83cfa_95.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_97.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_98.png)

梯度下降算法是一种优化算法。它通过计算目标函数的梯度，并沿着梯度方向更新参数，来优化模型。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_100.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_102.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_103.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_104.png)

**公式**：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_106.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_107.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_108.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_109.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_110.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_112.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_113.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_115.png)

```
梯度下降 = 梯度下降(参数, 目标函数)
```

![](img/3cd47ee8bea92fc84c530ca184d83cfa_117.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_118.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_120.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_121.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_122.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_123.png)

### 4.2 梯度下降参数

![](img/3cd47ee8bea92fc84c530ca184d83cfa_125.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_127.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_128.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_129.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_131.png)

梯度下降算法有两个参数：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_133.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_134.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_136.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_138.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_139.png)

1. 步长：用于控制参数更新的幅度。
2. 停止条件：用于控制梯度下降的迭代次数。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_140.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_142.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_144.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_146.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_148.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_150.png)

### 4.3 梯度下降应用

![](img/3cd47ee8bea92fc84c530ca184d83cfa_152.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_154.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_156.png)

梯度下降算法可以用于优化线性回归模型。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_158.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_159.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_161.png)

## 5. 感知机

![](img/3cd47ee8bea92fc84c530ca184d83cfa_163.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_164.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_165.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_167.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_169.png)

在本节中，我们将学习如何使用感知机算法进行二分类。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_171.png)

### 5.1 感知机原理

感知机是一种基于线性模型的二分类算法。它通过拟合数据点到一条直线，来区分两个类别。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_173.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_175.png)

**公式**：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_177.png)

```
感知机 = 感知机(数据集)
```

![](img/3cd47ee8bea92fc84c530ca184d83cfa_179.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_181.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_183.png)

### 5.2 感知机参数

![](img/3cd47ee8bea92fc84c530ca184d83cfa_185.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_187.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_189.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_190.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_192.png)

感知机算法有两个参数：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_193.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_195.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_197.png)

1. 权重：用于控制特征对预测结果的影响。
2. 偏置：用于调整预测结果。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_199.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_200.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_202.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_203.png)

### 5.3 感知机应用

感知机可以用于二分类任务。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_205.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_207.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_209.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_211.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_212.png)

## 总结

![](img/3cd47ee8bea92fc84c530ca184d83cfa_214.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_216.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_218.png)

本节课中，我们一起学习了决策树、K近邻、线性回归、梯度下降和感知机等机器学习算法。希望这些知识能够帮助你更好地理解机器学习。