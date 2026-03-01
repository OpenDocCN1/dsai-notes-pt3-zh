# 课程7：《回归模型》｜P39：泊松回归第二部分 📊

![](img/844a271ad8eceedaad72828cd6ca3a2d_0.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_2.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_4.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_5.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_6.png)

在本节课中，我们将深入探讨泊松回归模型，重点比较其与线性回归的区别，学习如何处理计数数据中的速率和比例问题，并了解模型诊断与改进方法。

![](img/844a271ad8eceedaad72828cd6ca3a2d_7.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_8.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_9.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_10.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_11.png)

## 线性回归 vs. 泊松回归 🔄

![](img/844a271ad8eceedaad72828cd6ca3a2d_13.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_14.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_15.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_16.png)

上一节我们介绍了泊松回归的基本概念。本节中，我们来看看它与线性回归的核心区别。

![](img/844a271ad8eceedaad72828cd6ca3a2d_18.png)

在广义线性模型中，我们并非对结果变量本身进行变换，而是对其均值进行变换。

![](img/844a271ad8eceedaad72828cd6ca3a2d_19.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_20.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_21.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_22.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_23.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_24.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_25.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_26.png)

*   在线性模型中，结果变量等于线性部分加上误差项。其公式可表示为：`E(Y) = β₀ + β₁X`。
*   在泊松对数线性模型中，是结果变量期望值的对数等于线性部分。其公式为：`log[E(Y)] = β₀ + β₁X`。

![](img/844a271ad8eceedaad72828cd6ca3a2d_28.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_29.png)

我们可以通过对等式两边取指数来逆转这个过程，得到：`E(Y) = exp(β₀ + β₁X)`。

主要区别在于，我们假设数据服从泊松分布，其均值具有 `exp(β₀ + β₁X)` 的形式。这改变了系数的解释方式，为我们观察到的结果提供了更可信的分布，并且我们得到了相对性的解释（因为一切都在对数尺度上）。

![](img/844a271ad8eceedaad72828cd6ca3a2d_31.png)

## 对数变换与系数解释 📈

![](img/844a271ad8eceedaad72828cd6ca3a2d_33.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_34.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_35.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_36.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_37.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_39.png)

对结果变量进行对数变换通常是处理正数数据的一个好方法，它能使系数在对数尺度上保持甚至增强可解释性。

![](img/844a271ad8eceedaad72828cd6ca3a2d_40.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_42.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_43.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_44.png)

当我们把系数转换回原始尺度时，所看到的是乘性差异。

以下是理解系数的方法：
如果我们查看模型 `E(Y) = exp(β₀ + β₁ * JulianDate)`，那么下一天（JulianDate + 1）的期望均值为 `exp[β₀ + β₁ * (JulianDate + 1)]`。
用后者除以前者，我们得到 `exp(β₁)`。

![](img/844a271ad8eceedaad72828cd6ca3a2d_46.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_47.png)

因此，我们的斜率系数 `exp(β₁)` 可以解释为：预测变量每增加一个单位，结果变量均值相对增加或减少的倍数。在对数尺度上，我们关注系数是否接近零；在指数化后，我们关注其是否接近一。在多变量背景下，`exp(β₁)` 表示在保持其他预测变量不变的情况下，结果变量的相对变化。

## 模型拟合与诊断 🔍

![](img/844a271ad8eceedaad72828cd6ca3a2d_49.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_50.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_51.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_52.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_53.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_54.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_55.png)

将拟合的泊松回归模型叠加到数据上，可以看到它虽然与线性模型拟合得相当接近，但具有我们想要的曲线形态。一个更简单、系数更少的模型似乎能更好地拟合数据。

![](img/844a271ad8eceedaad72828cd6ca3a2d_57.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_58.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_59.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_60.png)

一个常见的担忧是泊松分布的方差必须等于均值。因此，随着均值上升，方差也应上升。然而，如果我们绘制拟合值与残差的散点图，可以清楚地看到对于较低的均值，方差反而更高。这是一个问题。

![](img/844a271ad8eceedaad72828cd6ca3a2d_62.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_63.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_64.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_65.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_66.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_67.png)

以下是处理方差异质性的一些方法：
*   **拟泊松模型**：该模型将方差视为均值的常数倍，而非严格等于均值。
*   **模型无关的标准误**：例如使用“三明治”方差估计量（源自广义估计方程）。这是一个更高级但非常重要的应用主题。

![](img/844a271ad8eceedaad72828cd6ca3a2d_69.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_70.png)

主要要点是进行残差图分析以判断模型假设是否成立。可以尝试拟泊松模型，这在R中很容易实现。如果问题依然存在（如本例），则需要探索其他解决方案。

![](img/844a271ad8eceedaad72828cd6ca3a2d_72.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_73.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_74.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_75.png)

在本例中，使用模型无关的置信区间与常规置信区间相比，差异并不大。对于像本例这样的小系数，取指数后结果大约为1.002，意味着每天估计约有0.2%的增长。

![](img/844a271ad8eceedaad72828cd6ca3a2d_77.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_78.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_79.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_80.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_81.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_83.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_84.png)

## 处理速率与比例数据 ⚖️

![](img/844a271ad8eceedaad72828cd6ca3a2d_86.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_87.png)

当计数数据有一个“偏移量”时，我们需要处理速率或比例。例如，核泵故障次数应随监控时间变长而增加，流感病例数应随城市人口增多而增加。

![](img/844a271ad8eceedaad72828cd6ca3a2d_88.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_89.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_90.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_91.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_93.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_95.png)

我们希望解释的不是结果变量的期望值，而是结果变量除以某个相对项（如监控时间、风险人时等）后的期望值。

![](img/844a271ad8eceedaad72828cd6ca3a2d_97.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_98.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_99.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_100.png)

假设我们想将比例 `E(Y)/T` 建模为 `exp(β₀ + β₁X)`。通过对两边取对数并重新整理，我们得到：`log[E(Y)] = β₀ + β₁X + log(T)`。

![](img/844a271ad8eceedaad72828cd6ca3a2d_101.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_102.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_103.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_105.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_106.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_107.png)

在R中，只需将 `log(T)` 作为一个没有系数的**偏移量**项加入线性模型即可。简单的方法是在 `glm` 函数中使用 `offset = log(visits + 1)` 参数（加1是为了避免对零取对数）。默认的 `family = poisson` 即假定为对数连接函数，这正是我们需要的。

![](img/844a271ad8eceedaad72828cd6ca3a2d_109.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_110.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_112.png)

通过比较调整偏移量前后的拟合速率，可以直观看到模型如何根据总访问量来调整来自特定来源的访问量比例。

![](img/844a271ad8eceedaad72828cd6ca3a2d_113.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_115.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_116.png)

## 零膨胀与其他问题 ⚠️

![](img/844a271ad8eceedaad72828cd6ca3a2d_118.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_119.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_120.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_121.png)

泊松数据中另一个常见问题是零值出现得过于频繁，这被称为**零膨胀**。泊松模型在试图拟合其他计数值时，可能无法很好地处理过多的零值。

![](img/844a271ad8eceedaad72828cd6ca3a2d_123.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_124.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_126.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_127.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_128.png)

在本例早期存在大量零值，且具有时间成分，这使得建模更具挑战性。有专门的R包（如 `pscl`）可以帮助处理零膨胀泊松数据。

![](img/844a271ad8eceedaad72828cd6ca3a2d_130.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_131.png)

## 总结 🎯

![](img/844a271ad8eceedaad72828cd6ca3a2d_133.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_134.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_136.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_137.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_138.png)

本节课我们一起学习了泊松回归的核心内容。我们比较了泊松回归与线性回归在模型设定和解释上的根本区别，理解了如何通过对数连接函数处理计数数据。我们探讨了模型诊断的重要性，特别是对方差等于均值这一假设的检验，并介绍了拟泊松模型和稳健标准误等解决方案。最后，我们学习了如何在泊松回归中通过引入偏移量来处理速率或比例数据，并简要提及了零膨胀问题及其处理思路。

![](img/844a271ad8eceedaad72828cd6ca3a2d_139.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_141.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_142.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_143.png)

希望你能将二元逻辑回归、线性回归及多元回归中的技能，直接应用到泊松回归的实例中。下一讲将是本系列的最后一课，我们将介绍一些使用线性模型的实用技巧。