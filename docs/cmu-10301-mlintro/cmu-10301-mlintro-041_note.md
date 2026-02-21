# 机器学习导论：1：基础算法入门 🌱

![](img/3cd47ee8bea92fc84c530ca184d83cfa_1.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_3.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_5.png)

在本节课中，我们将要学习几种基础的机器学习算法，包括决策树、K近邻、线性回归、梯度下降和感知机。这些算法是理解更复杂模型的重要基石。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_7.png)

## 机器学习导论：1.1：决策树分类 🌳

![](img/3cd47ee8bea92fc84c530ca184d83cfa_9.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_11.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_13.png)

在本节中，我们将学习如何使用决策树进行分类。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_15.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_17.png)

决策树是一种基于树形结构的分类算法。它通过一系列的规则将数据集划分为不同的类别。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_18.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_20.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_22.png)

### 决策树分类原理

![](img/3cd47ee8bea92fc84c530ca184d83cfa_24.png)

决策树分类的核心思想是通过一系列“是/否”问题对数据进行划分。其过程可以概括为以下公式：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_25.png)

**公式**：
`决策树分类 = 决策树(数据集)`

![](img/3cd47ee8bea92fc84c530ca184d83cfa_27.png)

### 决策树构建

![](img/3cd47ee8bea92fc84c530ca184d83cfa_29.png)

决策树的构建是一个递归分割数据的过程。以下是构建决策树的基本步骤：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_31.png)

1.  选择一个特征作为根节点。
2.  根据该特征将数据集划分为不同的子集。
3.  对每个子集重复步骤1和2，直到满足停止条件（例如，所有数据都属于同一类别，或达到预设的树深度）。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_33.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_35.png)

### 决策树应用

![](img/3cd47ee8bea92fc84c530ca184d83cfa_37.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_39.png)

决策树可以用于分类和回归任务。它直观易懂，但需要注意过拟合问题。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_40.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_42.png)

---

![](img/3cd47ee8bea92fc84c530ca184d83cfa_43.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_44.png)

上一节我们介绍了基于树形结构的决策树，本节中我们来看看另一种基于实例的分类方法。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_46.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_48.png)

## 机器学习导论：1.2：K近邻分类 👥

![](img/3cd47ee8bea92fc84c530ca184d83cfa_50.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_52.png)

在本节中，我们将学习如何使用K近邻算法进行分类。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_54.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_55.png)

### K近邻分类原理

![](img/3cd47ee8bea92fc84c530ca184d83cfa_57.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_59.png)

K近邻算法是一种基于距离的分类算法。对于一个新数据点，算法会找到训练数据中与其最接近的k个“邻居”，然后根据这k个邻居的类别来决定新数据点的类别。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_61.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_63.png)

**公式**：
`K近邻分类 = K近邻(数据点, 训练数据集, k)`

![](img/3cd47ee8bea92fc84c530ca184d83cfa_65.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_67.png)

### K近邻参数

![](img/3cd47ee8bea92fc84c530ca184d83cfa_68.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_70.png)

K近邻算法的性能主要受两个参数影响：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_72.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_74.png)

1.  **k**：邻居的数量。k值过小容易受噪声影响，k值过大会使分类边界模糊。
2.  **距离度量**：用于计算数据点之间距离的方法。常用的距离度量有欧几里得距离和曼哈顿距离。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_76.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_78.png)

### K近邻应用

![](img/3cd47ee8bea92fc84c530ca184d83cfa_80.png)

K近邻算法简单有效，可以用于分类和回归任务。但其计算成本较高，因为每次预测都需要计算与所有训练样本的距离。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_82.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_83.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_85.png)

---

![](img/3cd47ee8bea92fc84c530ca184d83cfa_87.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_89.png)

从基于距离的K近邻算法，我们转向预测连续值的模型。接下来，我们将探讨线性回归。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_91.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_93.png)

## 机器学习导论：1.3：线性回归 📈

![](img/3cd47ee8bea92fc84c530ca184d83cfa_95.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_97.png)

在本节中，我们将学习如何使用线性回归进行回归分析。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_98.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_100.png)

### 线性回归原理

![](img/3cd47ee8bea92fc84c530ca184d83cfa_102.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_103.png)

线性回归是一种基于线性模型的回归算法。它试图找到一条直线（或超平面），使得所有数据点到这条直线的距离之和最小，从而预测连续值。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_104.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_106.png)

**公式**：
`线性回归 = 线性模型(数据集)`

![](img/3cd47ee8bea92fc84c530ca184d83cfa_107.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_108.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_109.png)

### 线性回归参数

![](img/3cd47ee8bea92fc84c530ca184d83cfa_110.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_112.png)

线性回归模型的核心是找到最优的参数：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_113.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_115.png)

1.  **权重**：用于控制每个特征对预测结果的影响程度。
2.  **偏置**：用于调整预测结果的基准线。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_117.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_118.png)

### 线性回归应用

![](img/3cd47ee8bea92fc84c530ca184d83cfa_120.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_121.png)

线性回归是回归分析中最基础、最常用的方法之一，广泛应用于经济学、社会科学和工程学等领域。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_122.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_123.png)

---

![](img/3cd47ee8bea92fc84c530ca184d83cfa_125.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_127.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_128.png)

为了找到线性回归模型中的最优参数，我们需要一种优化方法。下面，我们将介绍梯度下降算法。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_129.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_131.png)

## 机器学习导论：1.4：梯度下降 ⬇️

![](img/3cd47ee8bea92fc84c530ca184d83cfa_133.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_134.png)

在本节中，我们将学习如何使用梯度下降算法优化线性回归模型。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_136.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_138.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_139.png)

### 梯度下降原理

![](img/3cd47ee8bea92fc84c530ca184d83cfa_140.png)

梯度下降是一种优化算法，用于寻找函数的最小值。它通过计算目标函数（如损失函数）的梯度（导数），并沿着梯度下降的方向迭代更新模型参数，直到找到最优解或满足停止条件。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_142.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_144.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_146.png)

**公式**：
`梯度下降 = 梯度下降(参数, 目标函数)`

![](img/3cd47ee8bea92fc84c530ca184d83cfa_148.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_150.png)

### 梯度下降参数

![](img/3cd47ee8bea92fc84c530ca184d83cfa_152.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_154.png)

梯度下降算法的效果取决于以下关键参数：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_156.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_158.png)

1.  **学习率（步长）**：用于控制每次参数更新的幅度。学习率过大会导致震荡，过小则收敛缓慢。
2.  **停止条件**：用于控制梯度下降的迭代次数，例如达到最大迭代次数或损失值变化小于某个阈值。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_159.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_161.png)

### 梯度下降应用

![](img/3cd47ee8bea92fc84c530ca184d83cfa_163.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_164.png)

梯度下降算法是训练许多机器学习模型（包括线性回归、神经网络）的核心优化器。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_165.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_167.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_169.png)

---

![](img/3cd47ee8bea92fc84c530ca184d83cfa_171.png)

最后，我们将介绍一个经典的线性分类模型——感知机，它也是神经网络的基础。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_173.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_175.png)

## 机器学习导论：1.5：感知机 🧠

![](img/3cd47ee8bea92fc84c530ca184d83cfa_177.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_179.png)

在本节中，我们将学习如何使用感知机算法进行二分类。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_181.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_183.png)

### 感知机原理

![](img/3cd47ee8bea92fc84c530ca184d83cfa_185.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_187.png)

感知机是一种基于线性模型的二分类算法。它通过寻找一个超平面来将两类数据点分开。对于给定的输入，感知机会计算一个加权和，然后通过一个激活函数（如符号函数）输出分类结果。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_189.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_190.png)

**公式**：
`感知机 = 感知机(数据集)`

![](img/3cd47ee8bea92fc84c530ca184d83cfa_192.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_193.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_195.png)

### 感知机参数

![](img/3cd47ee8bea92fc84c530ca184d83cfa_197.png)

与线性回归类似，感知机模型也需要学习参数：

![](img/3cd47ee8bea92fc84c530ca184d83cfa_199.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_200.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_202.png)

1.  **权重**：用于控制每个特征对决策边界的影响。
2.  **偏置**：用于调整决策边界的位置。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_203.png)

### 感知机应用

![](img/3cd47ee8bea92fc84c530ca184d83cfa_205.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_207.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_209.png)

感知机是神经网络和支持向量机等更复杂模型的基础，适用于线性可分的二分类任务。

![](img/3cd47ee8bea92fc84c530ca184d83cfa_211.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_212.png)

---

![](img/3cd47ee8bea92fc84c530ca184d83cfa_214.png)

![](img/3cd47ee8bea92fc84c530ca184d83cfa_216.png)

## 总结 🎯

![](img/3cd47ee8bea92fc84c530ca184d83cfa_218.png)

本节课中，我们一起学习了五种基础的机器学习算法。**决策树**通过树形规则进行分类；**K近邻**根据最近邻居的类别进行预测；**线性回归**用于预测连续值；**梯度下降**是优化模型参数的通用方法；**感知机**则是简单的线性分类器。理解这些算法是迈向更复杂机器学习世界的第一步。