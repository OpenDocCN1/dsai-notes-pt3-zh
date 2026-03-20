# 033：连续线性泛函与算子范数 📐

![](img/f027bacb1917249a58a1deaecd7c03ff_0.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_2.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_3.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_4.png)

在本节课中，我们将要学习泛函分析中的一些核心概念，特别是连续线性泛函与算子范数。这些概念对于深入理解机器学习算法（尤其是核方法）背后的数学原理至关重要。

上一节我们介绍了线性映射的基本性质。本节中我们来看看当向量空间是无限维时，情况会发生哪些有趣的变化。

![](img/f027bacb1917249a58a1deaecd7c03ff_6.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_7.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_8.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_9.png)

## 从有限维到无限维的转变 🔄

![](img/f027bacb1917249a58a1deaecd7c03ff_10.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_11.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_13.png)

在有限维向量空间中，线性映射的性质非常良好。例如，任何线性映射都是连续的；如果一个线性映射是单射，那么它也是满射。这些性质使得有限维空间上的线性理论既优雅又强大。

然而，从数学角度看，这些性质也使得理论显得有些“平淡”。

![](img/f027bacb1917249a58a1deaecd7c03ff_15.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_16.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_17.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_18.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_19.png)

当研究的函数空间是无限维时，情况变得有趣起来。此时，许多在有限维空间中成立的良好性质会失效。例如：
*   线性映射不再自动连续。
*   单射的线性映射也不再自动是满射。

![](img/f027bacb1917249a58a1deaecd7c03ff_21.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_22.png)

## 泛函分析与机器学习的关联 🤖

![](img/f027bacb1917249a58a1deaecd7c03ff_23.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_25.png)

你可能会认为，对于机器学习应用而言，我们最终实现算法时使用的都是矩阵和有限维向量，因此无需关心无限维空间。这种观点在一定程度上有其道理。

![](img/f027bacb1917249a58a1deaecd7c03ff_27.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_28.png)

但是，当我们需要深入理解算法究竟在做什么，并希望证明关于算法的理论陈述时，泛函分析就变得至关重要。

![](img/f027bacb1917249a58a1deaecd7c03ff_30.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_31.png)

最突出的例子是**再生核希尔伯特空间**，它被用来分析机器学习中的核方法。核方法是一类非常简洁而强大的算法集合。要真正理解它们的工作原理，我们需要泛函分析的工具。

![](img/f027bacb1917249a58a1deaecd7c03ff_33.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_34.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_35.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_36.png)

类似地，在许多其他情况下，如果你想理解算法的本质并证明相关的理论，也需要涉足泛函分析。这背后的根本原因是：我们通常处理有限维算法，是因为我们只能观测到有限多个数据点；但如果你想做出一个关于“在数据点数量趋于无穷的极限情况下”的统计性陈述，就必须考虑无限维的背景。

![](img/f027bacb1917249a58a1deaecd7c03ff_38.png)

![](img/f027bacb1917249a58a1deaecd7c03ff_39.png)

本节课中我们一起学习了泛函分析在机器学习中的重要性，特别是无限维向量空间带来的性质变化，以及理解算法（如核方法）为何需要这些数学工具。