# 课程 P79：泊松回归（第二部分）📊

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_0.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_2.png)

在本节课中，我们将深入学习泊松回归，重点探讨其与线性回归的核心区别、模型解释、如何处理方差问题，以及如何对计数率或比例进行建模。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_4.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_5.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_6.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_7.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_8.png)

## 线性回归 vs. 泊松回归 🔄

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_10.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_11.png)

上一节我们介绍了泊松回归的基本概念。本节中我们来看看它与线性回归的核心区别。

在广义线性模型中，我们不是对结果变量本身进行变换，而是对其均值进行变换。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_13.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_14.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_15.png)

*   在线性模型中，结果变量等于线性部分加上误差项。其期望值就是线性部分本身。
*   在泊松对数线性模型中，**结果变量期望值的对数**才是线性部分。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_16.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_17.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_18.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_19.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_21.png)

具体来说，对于“每日网站点击量”这个例子，泊松回归模型可以表示为：
`log(E(每日点击量)) = β₀ + β₁ × 日期`

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_22.png)

我们可以通过对等式两边取指数，将其转换回原始尺度：
`E(每日点击量) = exp(β₀ + β₁ × 日期)`

主要区别在于，我们假设数据服从泊松分布，其均值具有 `exp(β₀ + β₁ × 预测变量)` 的形式。这改变了系数的解释方式，并且为计数数据提供了更可信的分布假设。

## 泊松回归的系数解释 📈

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_24.png)

由于模型是在对数尺度上建立的，系数的解释是相对的、乘性的。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_25.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_26.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_27.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_29.png)

考虑我们的模型：`E(结果) = exp(β₀ + β₁ × 日期)`。
根据期望值的性质，我们可以分解出 `β₀` 和 `β₁ × 日期`。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_31.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_32.png)

如果我们看下一天（日期+1）的期望均值，它是 `exp(β₀ + β₁ × (日期+1))`。
用下一天的期望除以当天的期望，我们得到 `exp(β₁)`。

因此，**`exp(β₁)` 被解释为预测变量每增加一个单位，结果变量均值相对增加或减少的倍数**。
*   如果我们将系数保持在原始的对数尺度上，我们关注它是否接近0。
*   如果将其取指数，我们关注它是否接近1（因为1表示没有变化）。
*   在多元回归中，`exp(β₁)` 表示在保持其他预测变量不变的情况下，结果变量的相对变化。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_34.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_35.png)

## 模型拟合与诊断 🔍

以下是拟合的泊松回归模型叠加在数据上的图示。可以看到它实际上与线性模型拟合得相当接近，但具有我们期望的曲线形态。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_37.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_38.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_39.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_40.png)

当然，我们也可以通过在线性模型中添加日期平方项来实现这种曲线，但值得注意的是，一个系数更少的简单模型似乎能更好地拟合数据。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_42.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_43.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_44.png)

一个常见的担忧是泊松分布要求方差等于均值。因此，在这个案例中，方差需要随着均值的增加而增加。

然而，如果我们绘制拟合值对残差的图，可以清楚地看到，对于较低的均值，方差反而更高。这是一个问题。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_46.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_47.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_48.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_49.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_50.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_52.png)

我们需要至少用某种方法来解释方差并非恒定这一事实。有很多方法可以做到这一点。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_53.png)

以下是处理此问题的一些方法：
*   **拟泊松模型**：该模型将方差视为均值的常数倍，而不是严格等于均值。但在本例中，这似乎也不成立，因为问题表现为低拟合值时方差更大，而泊松模型的预期恰恰相反。
*   **模型无关的标准误**：可以使用“三明治”方差估计量等方法。这是一个更高级的话题，但在实际应用中非常重要。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_55.png)

主要要点是进行一些残差图分析，以了解你的模型假设是否成立。尝试拟泊松模型，因为这在R中很容易实现。如果像本例这样模型假设明显不成立，则需要深入研究其他解决方案。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_57.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_58.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_59.png)

在本例中，如果不做任何处理（顶部）和使用模型无关置信区间（底部），两者差异实际上并不大。当然，这些都是未取指数的系数。如果取指数，对于像这样的小系数，基本上只是加1。估计值可能显示每天约有0.2%到0.3%的增长。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_61.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_62.png)

## 处理比率和比例 📉

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_63.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_64.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_65.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_66.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_67.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_69.png)

接下来，我们看看如何处理比率和比例。当计数数据有一个“偏移量”时，我们需要使用这种方法。偏移量决定了计数应有的规模。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_71.png)

例如：
*   统计核泵故障次数：监控时间越长，故障次数可能越多。
*   统计流感病例数：城市人口越多，病例数可能越多。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_73.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_74.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_75.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_76.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_77.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_78.png)

在这些情况下，我们感兴趣的计数需要相对于某个基准（如单位时间、风险人时、总样本量）来解释。我们想要建模的不是结果变量的期望值，而是结果变量期望值除以这个相对项（偏移量）。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_80.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_81.png)

在Jeff的例子中，他想建模来自Simply Statistics的网站点击量占总点击量的比例，模型为：
`E(来自Simply Statistics的点击量 / 总点击量) = exp(β₀ + β₁ × 日期)`

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_83.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_84.png)

通过对等式两边取对数并稍作整理，我们得到一个与之前类似的模型，但多了一个没有系数的对数偏移项。事实证明，这就是在泊松GLM中加入比率或比例项所需做的全部：只需将作为分母的计数、时间等项的对数作为偏移量加入线性模型。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_86.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_87.png)

在R中，可以很容易地通过 `offset = log(总点击量 + 1)` 参数将此偏移量加入模型。记住要加1，因为不能对0取对数。同时，在模型设定中指定 `family = poisson`，默认使用我们需要的对数连接函数。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_89.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_90.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_91.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_92.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_93.png)

下图展示了GLM1（建模点击量）的拟合比率与GLM2（建模相对点击量，即调整后的）拟合比率之间的差异。蓝线是拟合模型，灰点是实际数据点。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_95.png)

## 其他注意事项与总结 🎯

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_97.png)

关于对数线性模型和多维列联表，你可以获取更多信息。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_99.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_100.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_102.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_103.png)

泊松数据中另一个常见问题是“零膨胀”，即数据中零的出现频率远高于泊松模型在拟合其他计数的同时所允许的频率。处理零膨胀有很多不同的方法。在本例中，早期的零很多，且存在时间成分，这使得建模更具挑战性。有专门的R包可以帮助处理零膨胀。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_105.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_106.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_107.png)

本节课我们一起学习了泊松回归的核心内容。希望你能够运用从二项逻辑回归、线性回归及多元回归中学到的技能，并将其直接应用到泊松回归的例子中。

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_109.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_110.png)

![](img/4064af725e2c2aac7bd2a5d8b0f92beb_111.png)

下一讲是本系列的最后一讲，它将介绍一些使用线性模型可以完成的、我认为很酷的技巧，内容比较有趣。期待下次再见，感谢学习本课程。