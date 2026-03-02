#  057：帽子检查问题 🎩

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_0.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_2.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_3.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_5.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_7.png)

在本节课中，我们将学习一个经典的概率论问题——帽子检查问题。我们将通过这个例子，深入理解如何利用期望值的线性性质来简化复杂的概率计算。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_9.png)

## 问题描述

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_11.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_12.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_13.png)

有 **N** 位男士进入一家餐厅，并将他们的帽子交给寄存处。寄存处的工作人员会**随机地**将帽子发还给这些男士。每位男士都**随机地**得到一顶帽子。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_15.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_17.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_19.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_21.png)

核心问题是：**平均有多少位男士能拿回自己的帽子？**

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_23.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_25.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_27.png)

## 问题建模与初步分析

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_29.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_31.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_32.png)

我们首先定义随机变量 **R**，它表示拿到自己帽子的男士人数。我们的目标是计算 **R 的期望值**，即 **E[R]**。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_34.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_36.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_38.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_40.png)

根据期望值的定义，我们可以写出：
**E[R] = Σ (k=1 到 n) [ k × P(R = k) ]**

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_42.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_44.png)

然而，直接计算这个求和会非常复杂，因为我们需要知道 **P(R = k)** 的精确表达式。经过复杂的数学推导（此处省略），我们可以得到概率分布：

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_45.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_47.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_48.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_50.png)

*   当 **k ≤ n-2** 时，**P(R = k) = 1 / (k! × (n-k)!)**
*   当 **k = n-1** 或 **k = n** 时，**P(R = k) = 1 / n!**

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_52.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_54.png)

这个表达式看起来并不直观，而且计算起来也很繁琐。幸运的是，我们可以采用一种更巧妙、更简单的方法。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_56.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_58.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_60.png)

## 利用指示变量简化问题

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_61.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_63.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_65.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_67.png)

上一节我们介绍了直接计算期望值的复杂性。本节中，我们来看看如何通过分解随机变量来简化问题。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_69.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_71.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_73.png)

我们可以将总人数 **R** 表示为一系列更简单的随机变量之和。具体做法是，为每一位男士定义一个**指示变量**。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_75.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_77.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_79.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_81.png)

以下是定义指示变量的方法：
我们定义 **n** 个随机变量 **R₁, R₂, ..., Rₙ**，其中对于第 **i** 位男士：
*   **Rᵢ = 1**， 如果第 **i** 位男士拿回了自己的帽子。
*   **Rᵢ = 0**， 如果第 **i** 位男士拿错了帽子。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_83.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_85.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_87.png)

这样，拿到正确帽子的人数总和 **R** 就可以表示为：
**R = R₁ + R₂ + ... + Rₙ**

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_89.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_91.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_93.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_95.png)

这个和式精确地统计了拿到自己帽子的人数。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_97.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_99.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_101.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_102.png)

## 计算期望值

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_104.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_106.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_108.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_110.png)

现在，我们来计算 **R** 的期望值 **E[R]**。利用期望值的**线性性质**，无论这些随机变量是否独立，和的期望值都等于期望值的和：

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_112.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_114.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_116.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_118.png)

**E[R] = E[R₁ + R₂ + ... + Rₙ] = E[R₁] + E[R₂] + ... + E[Rₙ]**

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_120.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_122.png)

对于任何一个指示变量 **Rᵢ**，它的期望值 **E[Rᵢ]** 就等于 **Rᵢ = 1** 的概率，即第 **i** 位男士拿到自己帽子的概率。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_124.png)

由于帽子是**随机分配**的，对于任何一位特定的男士来说，从 **n** 顶帽子中恰好拿到自己那顶的概率是：
**P(第 i 位男士拿到自己的帽子) = 1 / n**

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_125.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_126.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_127.png)

因此，对于每一个 **i**，都有：
**E[Rᵢ] = 1 × (1/n) + 0 × (1 - 1/n) = 1/n**

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_129.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_130.png)

现在，我们将所有 **n** 位男士的期望值相加：
**E[R] = E[R₁] + E[R₂] + ... + E[Rₙ] = (1/n) + (1/n) + ... + (1/n) = n × (1/n) = 1**

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_131.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_132.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_134.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_136.png)

## 结论与总结

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_138.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_139.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_141.png)

本节课中我们一起学习了帽子检查问题及其巧妙的解法。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_143.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_145.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_147.png)

我们得到的最终结果是：**无论总共有多少位男士（n 是多少），平均而言，只有 1 位男士能拿回自己的帽子。**

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_149.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_151.png)

这个结论非常反直觉，但它清晰地展示了概率的奇妙之处。更重要的是，我们通过将复杂的随机变量 **R** 分解为简单的指示变量之和，并利用期望值的线性性质，避免了繁琐的概率计算，优雅地得到了答案。这种方法在解决许多涉及计数的概率问题时非常强大。

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_153.png)

![](img/3a9a0d99775dfc9b35ea5dc3d14a4851_154.png)

值得注意的是，在整个计算过程中，我们**没有**对帽子的随机排列方式做任何特殊的独立性假设，仅仅利用了“随机分配”这一条件，这使得结论具有普遍性。