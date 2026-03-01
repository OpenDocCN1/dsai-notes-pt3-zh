# 024：正则化回归 📈

在本节课中，我们将要学习正则化回归。这是一种通过惩罚或“收缩”回归模型中预测变量系数来改进模型性能的技术。我们将探讨其背后的动机、核心思想、具体方法以及如何在实际中应用。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_1.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_2.png)

---

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_3.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_4.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_5.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_6.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_7.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_8.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_9.png)

## 概述

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_10.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_12.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_13.png)

上一节我们介绍了线性回归和广义线性回归。本节中，我们来看看正则化回归。其基本思想是拟合一个回归模型，然后惩罚或收缩与某些预测变量相关的大系数。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_15.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_16.png)

我们这样做的原因是为了在偏差-方差权衡中取得优势。例如，如果某些变量高度相关，将它们同时纳入线性模型可能会导致很高的方差。此时，舍弃其中一个变量可能会轻微增加模型的偏差，但能显著降低方差，从而可能改善整体预测误差。正则化技术（如Lasso）在某些情况下也有助于模型选择。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_17.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_19.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_20.png)

然而，正则化回归在大数据集上计算量可能很大。并且，在现实预测任务（如Kaggle竞赛）中，其表现通常不如随机森林或提升方法。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_22.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_23.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_24.png)

---

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_26.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_27.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_29.png)

## 一个动机示例

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_31.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_32.png)

为了理解正则化的动机，我们来看一个简单的例子。

假设我们拟合一个非常简单的回归模型：有一个结果变量 **y**，我们试图用两个协变量 **x1** 和 **x2** 来预测它。模型包含截距项，形式如下：

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_34.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_35.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_36.png)

`y = β₀ + β₁*x₁ + β₂*x₂`

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_37.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_38.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_39.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_40.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_41.png)

现在，假设 **x1** 和 **x2** 几乎完全相关，也就是说它们几乎是同一个变量。在线性建模中，这种情况通常被称为**共线性**。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_43.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_44.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_45.png)

那么，我们可以用一个更简单的模型来近似这个复杂模型：只包含 **x1**，并将其系数设为 **β₁** 和 **β₂** 的和。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_47.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_48.png)

`y ≈ β₀ + (β₁ + β₂)*x₁`

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_49.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_50.png)

由于 **x1** 和 **x2** 并不完全相同，这个近似不会完全准确，但如果它们非常相似，结果将非常接近。这样做的结果是，你仍然能得到对 **y** 的非常好的估计，几乎与将两个预测变量都纳入模型一样好。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_52.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_53.png)

虽然因为舍弃了一个预测变量而引入了一点偏差，但如果这两个变量高度相关，我们可能会显著降低方差。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_54.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_55.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_56.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_57.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_58.png)

---

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_60.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_61.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_62.png)

## 偏差-方差分解

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_64.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_65.png)

上一节我们通过一个例子看到了模型复杂度的影响。本节中，我们更深入地看看预测误差的构成。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_67.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_68.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_69.png)

假设变量 **y** 可以表示为 **x** 的函数加上一个误差项：`y = f(x) + ε`。

那么，对于一个使用特定调优参数 **λ** 在训练集上得到的估计模型 `f̂_λ(x)`，其在新数据点上的期望预测误差（均方误差）可以分解为：

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_71.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_72.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_73.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_74.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_75.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_76.png)

`E[ (y - f̂_λ(x))² ] = Var(ε) + [Bias(f̂_λ(x))]² + Var(f̂_λ(x))`

以下是各项的含义：
*   **不可约误差 (σ²)**：数据中固有的噪声，通常无法减少。
*   **偏差²**：模型预测的期望值与真实值之间的差异。简单模型通常偏差高。
*   **方差**：模型估计值自身的波动程度。复杂模型通常方差高。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_78.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_79.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_80.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_81.png)

构建预测模型的目标是减少这个整体误差。不可约误差通常无法降低，但我们可以权衡**偏差**和**方差**。正则化回归的核心思想正是通过引入惩罚项来进行这种权衡，以在测试集上获得更好的预测性能。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_82.png)

---

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_84.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_85.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_86.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_87.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_88.png)

## 高维数据问题

另一个促使我们使用正则化回归的问题是**高维数据**。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_90.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_91.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_92.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_93.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_94.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_95.png)

设想一个简单情况：你的训练集只有5个观测样本，但预测变量超过5个。如果你拟合一个包含所有预测变量的线性模型，某些系数的估计值将是 `NA`（无法估计）。这是因为你的预测变量数量超过了样本数量，导致设计矩阵不可逆。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_97.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_98.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_99.png)

处理这个问题的一种方法是进行模型选择。例如，我们可以假设模型是线性形式，然后约束只有 **λ** 个系数非零。但接下来我们需要尝试所有可能的非零系数组合，这在计算上仍然非常耗时。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_101.png)

---

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_102.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_103.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_105.png)

## 正则化回归方法

为了解决上述问题，我们可以使用正则化回归。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_107.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_108.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_109.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_110.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_111.png)

如果线性模型中的系数 **βⱼ** 不受约束，当使用高度相关的变量进行预测时，它们可能会“爆炸”，导致估计值非常不稳定（高方差），从而降低预测准确性。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_112.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_113.png)

为了控制方差，我们可以对系数进行**正则化**或**收缩**。我们最小化的目标函数通常包含两部分：

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_115.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_116.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_117.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_118.png)

`Minimize: Σ(y_i - Σβ_j*x_ij)² + Penalty(β)`

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_119.png)

第一部分是残差平方和，衡量模型拟合程度。第二部分是惩罚项，如果系数 **βⱼ** 过大，惩罚项会将其“拉回”。惩罚项通常用于降低模型复杂度、减少方差，如果设置得当，还能尊重问题的某些结构。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_121.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_122.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_123.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_124.png)

以下是两种主要的正则化回归方法：

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_125.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_126.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_127.png)

### 岭回归 (Ridge Regression)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_129.png)

岭回归使用的惩罚项是系数平方和（L2范数）。其优化问题为：

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_131.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_132.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_133.png)

`Minimize: Σ(y_i - Σβ_j*x_ij)² + λ * Σβ_j²`

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_134.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_135.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_136.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_137.png)

这等价于在约束条件 `Σβ_j² ≤ s` 下最小化残差平方和。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_139.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_140.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_141.png)

*   **λ** 是调优参数，控制惩罚力度。
*   当 **λ = 0** 时，退化为普通最小二乘回归。
*   当 **λ → ∞** 时，所有系数 **βⱼ** 被压缩至接近0。
*   即使预测变量数多于样本数（`XᵀX` 不可逆），岭回归模型仍然可以拟合。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_143.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_144.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_145.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_146.png)

随着 **λ** 增大，惩罚力度增强，所有系数路径都会逐渐向零收缩。选择最佳的 **λ** 可以通过交叉验证等技术完成，目的是找到偏差和方差之间的最佳平衡点。

### Lasso 回归

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_148.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_149.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_150.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_151.png)

Lasso回归使用的惩罚项是系数绝对值之和（L1范数）。其优化问题为：

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_152.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_153.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_154.png)

`Minimize: Σ(y_i - Σβ_j*x_ij)² + λ * Σ|β_j|`

这等价于在约束条件 `Σ|β_j| ≤ s` 下最小化残差平方和。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_156.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_157.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_158.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_159.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_160.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_161.png)

对于正交设计矩阵，Lasso的解有一个闭合形式，称为“软阈值”：

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_162.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_163.png)

`β̂_j^lasso = sign(β̂_j^LS) * (|β̂_j^LS| - γ)₊`

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_165.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_166.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_167.png)

其中 `(x)₊` 表示 `max(x, 0)`，`β̂_j^LS` 是最小二乘估计，`γ` 是与 **λ** 相关的参数。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_169.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_170.png)

Lasso的特点在于：
*   它会收缩所有系数。
*   **它能够将某些系数精确地设置为零**。
*   正因为能将系数设为零，Lasso在收缩系数的同时，自动进行了**变量选择**。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_172.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_173.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_174.png)

---

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_175.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_176.png)

## 总结

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_178.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_179.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_180.png)

本节课中，我们一起学习了正则化回归。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_182.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_183.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_184.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_185.png)

我们首先了解了使用正则化的动机：处理共线性数据、在偏差-方差权衡中取得优势，以及应对高维数据中预测变量多于样本量的情况。接着，我们学习了预测误差的偏差-方差分解，理解了正则化如何通过惩罚项来权衡两者以降低总误差。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_187.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_188.png)

最后，我们重点介绍了两种核心的正则化回归方法：**岭回归**（使用L2惩罚，收缩系数但不置零）和**Lasso回归**（使用L1惩罚，收缩系数并可将其置零以实现变量选择）。调优参数 **λ** 控制着正则化的强度，其最优值通常通过交叉验证来确定。

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_190.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_191.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_192.png)

![](img/0b90ec97a43a3e6133d0fabbe8fc37fd_193.png)

如果你想进一步学习，可以参考Hector Corrada Bravo的讲义或《统计学习基础》一书。在R语言的`caret`包中，可以通过设置`method`参数为`ridge`、`lasso`或`relaxo`来拟合这些模型。