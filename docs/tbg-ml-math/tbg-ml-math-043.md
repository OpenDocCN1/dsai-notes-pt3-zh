# 043：Sigma代数与测度论基础

![](img/a665feb99e6fc43567a02eebf8d9fbb5_0.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_0.png)

在本节课中，我们将要学习积分理论的一个更一般化的构造方法。我们将回顾黎曼积分的局限性，并理解为什么需要引入“测度”这一更基础的概念，以及与之相关的“Sigma代数”结构。这是理解现代概率论和机器学习中许多高级概念的关键一步。

## 黎曼积分的回顾与局限性

![](img/a665feb99e6fc43567a02eebf8d9fbb5_2.png)

上一节我们介绍了黎曼积分的基本思想，本节中我们来看看它的具体构造以及为何需要推广。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_4.png)

我们已经了解了黎曼积分的概念，这是一种定义函数积分或函数下方体积的直接方法。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_2.png)

积分或函数下方的体积。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_4.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_6.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_7.png)

我想非常简要地重复一下它的构造方式，以便指出为什么我们现在需要一个更一般的构造。

如果你有一个如下所示的函数。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_6.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_9.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_7.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_11.png)

我们所做的是，将函数定义域分割成许多小区间。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_9.png)

然后我们用如下所示的小矩形来近似函数。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_13.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_11.png)

接着，我们用所有这些小矩形的体积之和来近似函数下方的体积。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_13.png)

我们已经看到，虽然这种方法对于连续函数效果很好，但对于许多函数它并不适用，例如，有理数的特征函数。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_15.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_16.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_15.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_17.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_16.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_17.png)

直观地思考一下那里会发生什么。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_19.png)

## 黎曼积分构造的核心要素

![](img/a665feb99e6fc43567a02eebf8d9fbb5_20.png)

要定义积分概念，这里使用了什么？我们观察了这些小区间。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_19.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_20.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_22.png)

我们所做的是利用了我们直观上知道这样一个区间的体积应该是什么。我们称这个区间为 `[x_k, x_{k+1}]`。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_23.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_22.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_23.png)

这个体积的概念，直观上应该就是区间的长度。所以它是 `x_{k+1} - x_k`。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_25.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_26.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_25.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_26.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_28.png)

然后我们说，我们通过观察这个区间 `I` 的体积乘以某个函数值来近似 `F` 的积分。

所以我们说，`F` 从 `a` 到 `b` 的积分近似于一个和式。然后我们看这些小区间的体积 `V_k` 乘以函数在某个点 `m_k` 的值。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_30.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_31.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_32.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_30.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_33.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_31.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_34.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_32.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_33.png)

无论你称它为什么，它可以是区间起点、终点、最大值点，或者任何在该区间内的点，例如这里的 `m_k`。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_34.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_36.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_37.png)

通过这种方式，我们近似了函数。这就是它起作用的直观方式。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_36.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_39.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_37.png)

## 黎曼积分的不足与推广需求

现在我们说，黎曼积分存在很多缺陷，这些缺陷源于“体积”这个概念不够一般化。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_39.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_41.png)

因为我们已经看到，如果你想处理像观察有理数集合这样的情况。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_43.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_41.png)

![](img/a665feb99e6fc43567a02eebf8d9fbb5_44.png)

有理数集在实数轴上是“稠密”但“零长度”的。黎曼积分基于区间长度（即勒贝格测度）来定义体积，它无法给这样一个“奇怪”的集合赋予一个有意义的“大小”（测度）。为了给更广泛的集合（如有理数集、康托尔集等）定义“体积”，并进而对更广泛的函数（如特征函数）定义积分，我们需要一个更基础的“测度”理论。而为了精确定义“测度”在哪些集合上有定义，就需要引入 **Sigma代数** 作为可测集合的全体。

![](img/a665feb99e6fc43567a02eebf8d9fbb5_43.png)

---

![](img/a665feb99e6fc43567a02eebf8d9fbb5_44.png)

本节课中我们一起学习了黎曼积分的基本构造及其局限性。我们看到，其核心依赖于对区间“长度”这一直观概念的运用。然而，对于像有理数集这样的集合，这种基于区间长度的体积概念失效了。这引出了对更一般的“测度”概念的需求，而测度的精确定义又依赖于 **Sigma代数** 这一结构。在接下来的课程中，我们将深入探讨Sigma代数和测度的正式定义，为学习勒贝格积分打下基础。