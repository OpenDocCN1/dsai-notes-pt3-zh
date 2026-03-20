# 084：非参数检验（秩检验与置换检验，Kolmogorov-Smirnov检验）

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_0.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_0.png)

在本节课中，我们将要学习非参数检验。到目前为止，在之前所有关于假设检验的章节中，我们研究的都是参数检验。

## 参数检验回顾

上一节我们介绍了参数检验的基本框架。本节中，我们来看看参数检验的核心假设。

在参数检验中，我们假设所考虑的分布族来自某个已知的分布族，例如由一个特定参数θ索引的正态分布族。然后，我们观察某个检验统计量，其核心假设是：我们能够评估该检验统计量的分布，并最终定义用于拒绝零假设H0的拒绝域。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_2.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_3.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_4.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_5.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_6.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_7.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_8.png)

我将再次绘制一些图像来说明这一点，但主要观点是：这种场景在少数应用或科学某些领域中定义明确的应用中可能是现实的。然而，在机器学习等许多领域，这通常行不通，因为我们无法对分布做出这些强假设。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_2.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_3.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_10.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_11.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_12.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_13.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_4.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_5.png)

因此，我们需要不同的方法，这就是非参数检验所要解决的问题。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_6.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_15.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_7.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_8.png)

## 标准参数检验场景

让我尝试构建一个标准场景。首先，我们写出参数检验的场景。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_19.png)

**场景**：

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_21.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_10.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_11.png)

我们有一个统计模型。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_12.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_13.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_23.png)

该模型称为 **F(θ)**，它由一组关于θ的函数组成，其中θ属于某个参数集合 **Θ**。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_15.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_25.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_17.png)

例如，正态分布。我们可能知道所有数据集都来自一个可能是正态分布的分布，但我们可能不知道中心的位置，也可能不知道方差。然而，我们知道：

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_19.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_27.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_28.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_29.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_21.png)

所有数据都来自这样一个正态分布。当然，这是一个很强的假设。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_23.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_31.png)

## 参数检验的流程

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_25.png)

那么，我们如何进行呢？我们提出检验统计量。

我们设计如何评估观察到的数据。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_33.png)
![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_34.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_27.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_28.png)

**数据** 并计算检验统计量。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_29.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_36.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_31.png)

检验统计量。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_38.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_33.png)

例如，数据的均值。例如，数据点的均值 **x̄**。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_34.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_40.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_36.png)

而这就是关键点。

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_38.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_42.png)

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_40.png)

---

![](img/c327fd0d3fa56b2ca3a70a7ffbfdfb9a_42.png)

本节课中我们一起学习了参数检验的基本框架及其核心假设，并引出了当数据不满足强分布假设（如正态性）时，需要采用非参数检验的必要性。下一节我们将深入探讨非参数检验的具体方法。