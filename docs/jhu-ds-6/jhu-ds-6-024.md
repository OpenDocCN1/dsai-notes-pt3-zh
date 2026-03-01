# 024：关于方差不等的说明 📊

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_0.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_2.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_3.png)

在本节课中，我们将学习如何处理两组数据方差不等情况下的置信区间构建问题。我们将探讨其公式、背后的统计原理，并通过一个具体示例演示计算过程。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_5.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_6.png)

## 方差不等的置信区间公式 📝

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_8.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_9.png)

上一节我们介绍了方差相等情况下的t区间。本节中我们来看看当两组数据方差不等时，置信区间的构建方法。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_11.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_12.png)

方差不等的置信区间公式与之前的形式相似。其核心是均值的差值，加上或减去一个t分位数乘以标准误。这里的标准误计算假设两组数据具有不同的方差。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_14.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_15.png)

**公式**如下：
`均值差 ± t分位数 × 标准误`
其中，标准误的计算考虑了两组各自不同的方差。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_17.png)

## 统计原理与自由度 🔬

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_18.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_19.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_21.png)

如果X观测值和Y观测值都服从独立同分布的正态分布，但可能具有不同的均值和不同的方差，那么相关的标准化统计量并不严格遵循t分布。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_22.png)

实际上，它可以被一个t分布近似，但需要选择一个相当复杂的公式来计算自由度。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_24.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_25.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_26.png)

以下是自由度的计算公式：
`自由度 = (s1²/n1 + s2²/n2)² / [ (s1²/n1)²/(n1-1) + (s2²/n2)²/(n2-1) ]`
其中，`s1²`和`s2²`分别是两组的样本方差，`n1`和`n2`是样本量。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_28.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_29.png)

这个自由度计算很复杂，因为它不仅涉及样本量，还涉及两组数据的估计标准差和方差。通常没有人会记住这个公式。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_31.png)

尽管如此，如果代入这个可能为分数的自由度，得到的t计算可以很好地近似真实的分布（该分布本身并非真正的t分布）。事实证明，这种近似效果足够好。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_33.png)

## 实践建议与示例计算 💡

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_35.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_36.png)

基于上述原理，可以给出一个实用的建议：当你不确定两组方差是否相等时，直接使用方差不等的区间方法。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_37.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_38.png)

本页通过之前的口服避孕药例子来演示整个计算过程。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_40.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_41.png)

你可能需要跟着计算一遍，以确信自己能够代入标准差公式，特别是自由度公式。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_43.png)

在这个例子中，计算得到的自由度是15.04。

然而，在实践中，当我们想要进行方差不等的t检验时，通常只需使用R语言的`t.test()`命令，并设置参数`var.equal = FALSE`。这会执行相关的方差不等的t检验，并生成基于不等方差计算的相应t分位数。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_45.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_46.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_47.png)

## 课程总结 🎯

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_48.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_49.png)

本节课我们一起学习了使用t分布构建置信区间，这是统计学中最便捷的区间之一。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_51.png)

我们讨论了在拥有单次观测或配对观测（已计算差值）的情况下，如何使用t区间来构建对数据分布的基本假设具有高度稳健性的区间。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_52.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_53.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_54.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_56.png)

然而，我们也谈到了几种可能更适合使用t分布和t区间以外方法的情况：
*   当数据高度偏斜时，你可能需要对数转换或寻找不同的程序。
*   当数据是二元的，你可以考虑使用比值比等方法，这将在回归课程中的广义线性模型部分涉及。
*   对于计数数据也是如此，我们将讨论泊松模型和比率的广义线性模型，同样在回归课程中。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_58.png)

对于其他一些两组比较的特殊情况，Coursera上的“数学统计训练营2”课程涵盖了许多内容。