#  041：累积分布函数详解 📊

![](img/e92d84b6d580aab8c8918718fbcdd4ef_0.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_2.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_4.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_6.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_8.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_10.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_12.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_14.png)

在本节课中，我们将要学习一个连接离散随机变量与连续随机变量的核心概念——累积分布函数。我们将探讨它的定义、直观含义、数学表达以及与概率质量函数和概率密度函数的关系。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_16.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_17.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_18.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_20.png)

## 概述

![](img/e92d84b6d580aab8c8918718fbcdd4ef_22.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_23.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_25.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_26.png)

累积分布函数是一个统一的概念，它允许我们在离散和连续随机变量之间进行比较。它通过“累积”概率的方式，为我们提供了一种描述随机变量取值小于或等于某个特定值的概率的工具。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_28.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_30.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_32.png)

## 从PMF和PDF到CDF

![](img/e92d84b6d580aab8c8918718fbcdd4ef_34.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_36.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_38.png)

上一节我们介绍了概率质量函数和概率密度函数。本节中我们来看看累积分布函数如何将它们联系起来。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_40.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_41.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_43.png)

对于离散随机变量，我们有一个概率质量函数。它看起来像一系列柱状图，每个柱子的高度代表该点对应的概率值。我们称之为PMF。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_44.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_46.png)

对于连续随机变量，我们有一个概率密度函数。以均匀分布为例，它在区间[a, b]上是一条水平的直线，我们称之为PDF。

累积分布函数的作用是随时间累积信息。它累积从最低的x值到当前x值的概率总和。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_48.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_50.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_51.png)

以下是离散随机变量的CDF形成过程：
*   在到达第一个概率质量点之前，累积概率为0。
*   当到达第一个概率质量点时，累积概率会瞬间“跳跃”到该点的概率值。
*   在到达下一个概率质量点之前，累积概率保持这个值不变。
*   当到达下一个点时，累积概率会再次跳跃，增加该点的概率值。
*   这个过程持续进行，直到最后一个点，累积概率最终达到1。

因此，离散随机变量的CDF是一个**阶梯函数**。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_53.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_55.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_57.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_59.png)

对于连续随机变量，其CDF的形成过程则不同：
*   在点a之前，累积概率为0。
*   从点a到点b，由于概率密度是常数，我们持续地“添加”概率切片。
*   累积概率以恒定的速率线性增长。
*   在点b之后，累积概率达到1并保持不变。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_61.png)

因此，对于均匀分布，其CDF是一条从0到1的**斜线**。如果概率密度不是常数，CDF的斜率就会变化，形成更复杂的曲线。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_63.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_64.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_65.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_66.png)

## CDF的核心定义与解释

![](img/e92d84b6d580aab8c8918718fbcdd4ef_68.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_69.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_70.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_71.png)

累积分布函数，用大写字母 **F(x)** 表示，其核心定义是：它给出了随机变量X取值小于或等于某个特定值x的概率。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_73.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_74.png)

对于连续随机变量，这一定义可以用积分公式精确描述：
**F(x) = P(X ≤ x) = ∫_{-∞}^{x} f(t) dt**

![](img/e92d84b6d580aab8c8918718fbcdd4ef_75.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_77.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_78.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_79.png)

这个公式是本节课最重要的概念。它意味着**F(x)的值等于概率密度函数f(t)曲线下，从负无穷到x点所围成的面积**。你需要仔细理解这一点：CDF在x点的值，直接对应着PDF曲线下左侧的总面积。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_80.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_82.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_83.png)

对于离散随机变量，其定义是类似的，但使用求和代替积分：
**F(x) = P(X ≤ x) = Σ_{k ≤ x} P(X = k)**

![](img/e92d84b6d580aab8c8918718fbcdd4ef_85.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_87.png)

即，对所有小于等于x的k值，将其对应的概率质量相加。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_89.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_90.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_91.png)

CDF的值域具有重要性质：无论对于离散还是连续随机变量，其累积分布函数**F(x)的取值范围总是在0和1之间**。这是因为概率的总和（或积分）为1。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_93.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_94.png)

## CDF与PDF/PMF的关系

![](img/e92d84b6d580aab8c8918718fbcdd4ef_96.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_97.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_99.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_100.png)

现在，让我们更深入地看看CDF与之前学过的函数之间的关系。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_102.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_103.png)

对于连续随机变量，CDF和PDF通过微积分基本定理紧密相连。我们刚刚看到，CDF是PDF的积分。反之，**PDF是CDF的导数**：
**f(x) = dF(x)/dx**

![](img/e92d84b6d580aab8c8918718fbcdd4ef_105.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_107.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_108.png)

导数的几何意义是斜率。这解释了为什么均匀分布的CDF是一条斜线（斜率恒定），而其PDF是一条水平线（导数为常数）。PDF描述了概率发生的“速率”，而CDF则累积了这些速率产生的“总量”。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_110.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_112.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_114.png)

对于离散随机变量，PMF与CDF的关系则体现在“跳跃”上。CDF在某个点x的“跳跃高度”，恰好等于PMF在该点x的概率值**P(X = x)**。而在连续情况下，在任意单点上的概率**P(X = x) = 0**。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_116.png)

## 总结

![](img/e92d84b6d580aab8c8918718fbcdd4ef_118.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_119.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_120.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_121.png)

本节课中我们一起学习了累积分布函数。我们了解到：
1.  **CDF** 是一个统一框架，用于描述离散和连续随机变量的概率累积行为。
2.  它的定义是 **F(x) = P(X ≤ x)**，表示随机变量小于等于x的概率。
3.  对于连续变量，CDF是PDF的积分（`F(x) = ∫_{-∞}^{x} f(t) dt`）；PDF是CDF的导数（`f(x) = dF(x)/dx`）。
4.  对于离散变量，CDF是PMF的累加和（`F(x) = Σ_{k ≤ x} P(X = k)`），其图形是阶梯函数。
5.  CDF的值域始终在 **[0, 1]** 区间内。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_123.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_124.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_125.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_126.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_127.png)

理解累积分布函数是掌握概率分布如何工作的关键一步，它为后续学习更多的统计方法和概率模型奠定了坚实的基础。