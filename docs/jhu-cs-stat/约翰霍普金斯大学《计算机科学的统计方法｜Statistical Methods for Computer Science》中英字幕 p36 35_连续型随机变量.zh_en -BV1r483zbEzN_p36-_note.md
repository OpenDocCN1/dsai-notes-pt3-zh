# 计算机科学的统计方法：35：连续型随机变量 📊

![](img/71bb99ad405d45458e778fbb867beffc_1.png)

在本节课中，我们将要学习连续型随机变量的概念。我们将探讨它与之前学过的离散型随机变量有何不同，并介绍其核心的数学描述工具——概率密度函数。

![](img/71bb99ad405d45458e778fbb867beffc_3.png)

![](img/71bb99ad405d45458e778fbb867beffc_5.png)

![](img/71bb99ad405d45458e778fbb867beffc_7.png)

![](img/71bb99ad405d45458e778fbb867beffc_9.png)

上一节我们介绍了离散型随机变量，本节中我们来看看**连续型随机变量**。

![](img/71bb99ad405d45458e778fbb867beffc_10.png)

离散型随机变量的取值是可数的，例如掷骰子的点数。但现实世界中存在许多不可数的数值，例如时间。如果你跑完2英里用时12分钟，这个“12分钟”是精确的12分钟，还是12分0.1秒，或是12分0.0001毫秒？时间是连续的，其周围有无限多个可能的取值，无法一一计数。因此，对于时间这类连续的量，我们需要使用连续型随机变量来描述。

![](img/71bb99ad405d45458e778fbb867beffc_12.png)

## 从样本空间到实数轴

![](img/71bb99ad405d45458e778fbb867beffc_13.png)

![](img/71bb99ad405d45458e778fbb867beffc_14.png)

![](img/71bb99ad405d45458e778fbb867beffc_15.png)

![](img/71bb99ad405d45458e778fbb867beffc_16.png)

![](img/71bb99ad405d45458e778fbb867beffc_18.png)

![](img/71bb99ad405d45458e778fbb867beffc_19.png)

![](img/71bb99ad405d45458e778fbb867beffc_21.png)

随机变量是将样本空间中的事件映射到实数轴上的函数。例如，我女儿小时候为了够到高处的玩具，会叠放豆袋椅和凳子。这个事件本身没有数字，直到我们用“叠放的高度”这个规则将其映射为一个数值。

![](img/71bb99ad405d45458e778fbb867beffc_23.png)

同样，对于跑步事件，我们通过“用时”这个规则，将其映射到时间轴上的一个数值。我们可以用一个函数 **f(x)** 来描述这个数值出现的频率或可能性。在图中，x轴可能代表时间，函数曲线的高低则表示该时间出现的可能性大小。

![](img/71bb99ad405d45458e778fbb867beffc_25.png)

![](img/71bb99ad405d45458e778fbb867beffc_26.png)

![](img/71bb99ad405d45458e778fbb867beffc_27.png)

![](img/71bb99ad405d45458e778fbb867beffc_28.png)

![](img/71bb99ad405d45458e778fbb867beffc_29.png)

![](img/71bb99ad405d45458e778fbb867beffc_31.png)

![](img/71bb99ad405d45458e778fbb867beffc_32.png)

![](img/71bb99ad405d45458e778fbb867beffc_34.png)

## 概率密度函数

![](img/71bb99ad405d45458e778fbb867beffc_36.png)

![](img/71bb99ad405d45458e778fbb867beffc_38.png)

![](img/71bb99ad405d45458e778fbb867beffc_39.png)

![](img/71bb99ad405d45458e778fbb867beffc_41.png)

![](img/71bb99ad405d45458e778fbb867beffc_43.png)

我们称这个描述连续随机变量频率的函数为**概率密度函数**，简称 **PDF**。它与离散随机变量的概率质量函数类似，但存在关键差异。

![](img/71bb99ad405d45458e778fbb867beffc_44.png)

![](img/71bb99ad405d45458e778fbb867beffc_46.png)

首先需要理解的是，对于一个连续随机变量 **X**，取到**某一个精确值**的概率是多少？例如，概率 **P(X = a)** 是多少？

答案是 **0**。因为连续随机变量的取值有无限多种可能，取到其中某一个特定点的概率，在数学上等于无穷分之一，其极限为0。就像你永远无法通过“每次前进剩余距离的一半”这种方式精确到达终点一样。

![](img/71bb99ad405d45458e778fbb867beffc_48.png)

![](img/71bb99ad405d45458e778fbb867beffc_49.png)

![](img/71bb99ad405d45458e778fbb867beffc_50.png)

![](img/71bb99ad405d45458e778fbb867beffc_51.png)

![](img/71bb99ad405d45458e778fbb867beffc_52.png)

![](img/71bb99ad405d45458e778fbb867beffc_53.png)

![](img/71bb99ad405d45458e778fbb867beffc_55.png)

![](img/71bb99ad405d45458e778fbb867beffc_56.png)

既然无法计算单点的概率，我们就需要通过**区间**来评估概率。

![](img/71bb99ad405d45458e778fbb867beffc_58.png)

![](img/71bb99ad405d45458e778fbb867beffc_59.png)

![](img/71bb99ad405d45458e778fbb867beffc_61.png)

## 概率即面积

![](img/71bb99ad405d45458e778fbb867beffc_63.png)

![](img/71bb99ad405d45458e778fbb867beffc_64.png)

![](img/71bb99ad405d45458e778fbb867beffc_66.png)

![](img/71bb99ad405d45458e778fbb867beffc_67.png)

![](img/71bb99ad405d45458e778fbb867beffc_68.png)

![](img/71bb99ad405d45458e778fbb867beffc_70.png)

对于连续随机变量，我们计算的是它落在某个区间 **[a, b]** 内的概率。这个概率在几何上等于概率密度函数曲线下，从 **a** 到 **b** 所围成的**面积**。

![](img/71bb99ad405d45458e778fbb867beffc_72.png)

![](img/71bb99ad405d45458e778fbb867beffc_73.png)

![](img/71bb99ad405d45458e778fbb867beffc_75.png)

![](img/71bb99ad405d45458e778fbb867beffc_76.png)

![](img/71bb99ad405d45458e778fbb867beffc_77.png)

因此，概率的计算公式为：
**P(a ≤ X ≤ b) = ∫[a, b] f(x) dx**

![](img/71bb99ad405d45458e778fbb867beffc_79.png)

![](img/71bb99ad405d45458e778fbb867beffc_81.png)

![](img/71bb99ad405d45458e778fbb867beffc_83.png)

![](img/71bb99ad405d45458e778fbb867beffc_85.png)

这与离散随机变量形成对比。对于离散变量，概率质量函数像一系列“质量块”，区间概率是这些质量块的**求和**。而对于连续变量，概率密度函数是一条连续的曲线，区间概率是曲线下的**积分**（面积）。

![](img/71bb99ad405d45458e778fbb867beffc_87.png)

![](img/71bb99ad405d45458e778fbb867beffc_88.png)

![](img/71bb99ad405d45458e778fbb867beffc_89.png)

![](img/71bb99ad405d45458e778fbb867beffc_91.png)

![](img/71bb99ad405d45458e778fbb867beffc_92.png)

## 概率密度函数的条件

![](img/71bb99ad405d45458e778fbb867beffc_93.png)

![](img/71bb99ad405d45458e778fbb867beffc_95.png)

![](img/71bb99ad405d45458e778fbb867beffc_97.png)

![](img/71bb99ad405d45458e778fbb867beffc_99.png)

![](img/71bb99ad405d45458e778fbb867beffc_101.png)

一个函数 **f(x)** 要成为有效的概率密度函数，必须满足以下三个条件：

![](img/71bb99ad405d45458e778fbb867beffc_102.png)

![](img/71bb99ad405d45458e778fbb867beffc_103.png)

![](img/71bb99ad405d45458e778fbb867beffc_105.png)

![](img/71bb99ad405d45458e778fbb867beffc_106.png)

![](img/71bb99ad405d45458e778fbb867beffc_108.png)

以下是三个必要条件：
1.  **总概率为1**：函数曲线下的总面积必须等于1。这表示所有可能事件发生的总概率为100%。
    **∫[-∞, ∞] f(x) dx = 1**
2.  **单点概率为零**：如前所述，取任何特定值的概率为0。
    **P(X = a) = ∫[a, a] f(x) dx = 0**
3.  **非负性**：概率密度函数值必须永远大于或等于0，不能为负。
    **f(x) ≥ 0， 对所有 x 成立**

![](img/71bb99ad405d45458e778fbb867beffc_110.png)

![](img/71bb99ad405d45458e778fbb867beffc_112.png)

![](img/71bb99ad405d45458e778fbb867beffc_114.png)

本节课中我们一起学习了连续型随机变量的核心概念。我们了解到它与离散型随机变量的根本区别在于取值不可数，且单点概率为零。我们引入了**概率密度函数**作为描述工具，并知道概率通过计算PDF曲线下的面积（即积分）来获得。最后，我们明确了PDF必须满足的三个数学条件。理解这些是学习后续连续分布（如正态分布）的基础。