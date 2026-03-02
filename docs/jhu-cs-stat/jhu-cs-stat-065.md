#  065：中心极限定理 📊

![](img/511a29769a399fef2d4cfe07a48ee66e_1.png)

在本节课中，我们将要学习中心极限定理。这是概率论与统计学中最重要的定理之一，它解释了为什么许多独立随机变量之和的分布会趋近于正态分布。

![](img/511a29769a399fef2d4cfe07a48ee66e_3.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_4.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_5.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_6.png)

## 概述

![](img/511a29769a399fef2d4cfe07a48ee66e_8.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_9.png)

在本模块中，我们已经讨论了多个极限定理。我们介绍了马尔可夫定理，探讨了墨菲定律及其启示，并学习了切比雪夫不等式。现在，我们将探讨一个可能最重要、也最常用的定理——中心极限定理。

![](img/511a29769a399fef2d4cfe07a48ee66e_11.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_13.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_15.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_17.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_19.png)

## 中心极限定理的定义

![](img/511a29769a399fef2d4cfe07a48ee66e_21.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_23.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_25.png)

中心极限定理的表述如下：

![](img/511a29769a399fef2d4cfe07a48ee66e_27.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_29.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_31.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_33.png)

设 **X₁, X₂, ...** 是一系列独立同分布的随机变量。

![](img/511a29769a399fef2d4cfe07a48ee66e_35.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_36.png)

每个变量具有均值 **μ** 和方差 **σ²**。

那么，以下标准化和式的分布：

![](img/511a29769a399fef2d4cfe07a48ee66e_38.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_39.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_40.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_41.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_42.png)

**Zₙ = (X₁ + X₂ + ... + Xₙ - nμ) / (σ√n)**

![](img/511a29769a399fef2d4cfe07a48ee66e_44.png)

当 **n** 趋近于无穷大时，会趋近于标准正态分布。

![](img/511a29769a399fef2d4cfe07a48ee66e_46.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_47.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_48.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_49.png)

标准正态分布是指均值为 **0**、方差为 **1** 的正态分布。我们不会在此证明该定理，因为它在任何统计学教材中都有详细记载。我们将通过一个示例问题来解释其应用。

![](img/511a29769a399fef2d4cfe07a48ee66e_51.png)

## 应用示例：天文学家的测量问题

假设一位天文学家正在测量一个距离。由于环境因素，每次测量结果都会有所不同。她将进行一系列测量，然后计算这些测量值的平均值，以获得该距离的中心趋势。

![](img/511a29769a399fef2d4cfe07a48ee66e_53.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_54.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_55.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_56.png)

我们假设这些测量值是独立同分布的。这意味着每次观测不依赖于前一次观测，并且所有观测都来自同一个分布。

![](img/511a29769a399fef2d4cfe07a48ee66e_58.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_60.png)

我们进一步假设这些观测值具有共同的均值 **μ** 和共同的方差 **σ²**。为了具体说明，我们设方差 **σ² = 4**。

![](img/511a29769a399fef2d4cfe07a48ee66e_62.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_63.png)

现在的问题是：这位天文学家需要进行多少次测量，才能以95%的置信度确保其样本平均值与真实均值 **μ** 的误差在 **±0.5** 光年之内？

![](img/511a29769a399fef2d4cfe07a48ee66e_65.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_66.png)

## 问题求解过程

![](img/511a29769a399fef2d4cfe07a48ee66e_68.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_70.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_71.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_73.png)

首先，我们定义标准化变量 **Zₙ**：

![](img/511a29769a399fef2d4cfe07a48ee66e_74.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_76.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_78.png)

**Zₙ = (Σᵢ Xᵢ - nμ) / (σ√n)**

![](img/511a29769a399fef2d4cfe07a48ee66e_80.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_82.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_84.png)

我们的目标是求解概率：

![](img/511a29769a399fef2d4cfe07a48ee66e_86.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_87.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_89.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_91.png)

**P( -0.5 ≤ (Σᵢ Xᵢ / n) - μ ≤ 0.5 ) ≥ 0.95**

![](img/511a29769a399fef2d4cfe07a48ee66e_93.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_94.png)

为了应用中心极限定理，我们对不等式进行变换。将不等式两边同时乘以 **√n / σ**（其中 σ = 2），得到：

![](img/511a29769a399fef2d4cfe07a48ee66e_96.png)

**P( -0.5 * (√n / 2) ≤ Zₙ ≤ 0.5 * (√n / 2) ) ≥ 0.95**

![](img/511a29769a399fef2d4cfe07a48ee66e_98.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_100.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_102.png)

根据中心极限定理，当 **n** 足够大时，**Zₙ** 近似服从标准正态分布 **N(0, 1)**。因此，上述概率可以表示为标准正态分布的累积分布函数 **Φ**：

![](img/511a29769a399fef2d4cfe07a48ee66e_104.png)

**Φ(0.5√n / 2) - Φ(-0.5√n / 2) ≥ 0.95**

![](img/511a29769a399fef2d4cfe07a48ee66e_106.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_108.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_110.png)

由于标准正态分布是对称的，**Φ(-a) = 1 - Φ(a)**，因此上式可简化为：

![](img/511a29769a399fef2d4cfe07a48ee66e_112.png)

**2Φ(√n / 4) - 1 ≥ 0.95**

![](img/511a29769a399fef2d4cfe07a48ee66e_114.png)

**Φ(√n / 4) ≥ 0.975**

![](img/511a29769a399fef2d4cfe07a48ee66e_115.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_117.png)

接下来，我们查找标准正态分布表，找到使得 **Φ(z) = 0.975** 的 **z** 值。该值约为 **1.96**。

![](img/511a29769a399fef2d4cfe07a48ee66e_119.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_120.png)

因此，我们建立方程：

![](img/511a29769a399fef2d4cfe07a48ee66e_122.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_124.png)

**√n / 4 ≈ 1.96**

![](img/511a29769a399fef2d4cfe07a48ee66e_126.png)

解这个方程求 **n**：

![](img/511a29769a399fef2d4cfe07a48ee66e_128.png)

**√n ≈ 1.96 * 4 = 7.84**

![](img/511a29769a399fef2d4cfe07a48ee66e_130.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_131.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_133.png)

**n ≈ (7.84)² ≈ 61.47**

![](img/511a29769a399fef2d4cfe07a48ee66e_135.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_137.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_139.png)

## 结论

![](img/511a29769a399fef2d4cfe07a48ee66e_141.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_142.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_144.png)

本节课中我们一起学习了中心极限定理及其应用。

![](img/511a29769a399fef2d4cfe07a48ee66e_146.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_148.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_149.png)

中心极限定理指出，无论原始随机变量服从何种分布（只要其具有有限的均值和方差），大量独立同分布随机变量之和的标准化形式，其分布都会趋近于标准正态分布。

![](img/511a29769a399fef2d4cfe07a48ee66e_151.png)

通过天文学家测量距离的示例，我们展示了如何利用该定理来确定所需的样本量，以达到特定的精度和置信水平。计算结果表明，大约需要 **62** 次测量，才能以95%的置信度将误差控制在 ±0.5 光年之内。

![](img/511a29769a399fef2d4cfe07a48ee66e_153.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_154.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_155.png)

![](img/511a29769a399fef2d4cfe07a48ee66e_157.png)

这个定理是统计学中许多推断方法（如置信区间和假设检验）的理论基础，理解它对于掌握更高级的统计概念至关重要。