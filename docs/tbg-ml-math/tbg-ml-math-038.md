# 038：R上的微分

![](img/b59d2af2c319dd07fa661e577b9bd25b_0.png)

在本节课中，我们将开始学习函数的导数。我们将从一维情况入手，因为大多数同学可能已经接触过一维导数。一维导数是理解更复杂的多维导数的基础。通过回顾一维导数的核心概念和直觉，将有助于我们后续学习更高维度的微分。

![](img/b59d2af2c319dd07fa661e577b9bd25b_2.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_3.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_4.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_5.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_6.png)

## 可微性的定义

![](img/b59d2af2c319dd07fa661e577b9bd25b_7.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_9.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_10.png)

上一节我们介绍了讨论导数的背景，本节中我们来看看如何正式定义函数的可微性。

![](img/b59d2af2c319dd07fa661e577b9bd25b_12.png)

我们考虑一个定义在实数区间 **U** 上的函数 **f**。这里的核心是，我们目前讨论的是一维情况，即函数的定义域和值域都是实数 **R**。

![](img/b59d2af2c319dd07fa661e577b9bd25b_14.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_15.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_16.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_18.png)

函数 **f** 在点 **a**（属于区间 **U**）处被称为**可微的**，如果以下极限存在：

![](img/b59d2af2c319dd07fa661e577b9bd25b_20.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_22.png)

**f'(a) = lim (h -> 0) [ ( f(a + h) - f(a) ) / h ]**

![](img/b59d2af2c319dd07fa661e577b9bd25b_24.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_26.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_27.png)

如果这个极限存在，我们称该极限值为函数 **f** 在点 **a** 处的**导数**，记作 **f'(a)**。

![](img/b59d2af2c319dd07fa661e577b9bd25b_29.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_31.png)

## 总结

![](img/b59d2af2c319dd07fa661e577b9bd25b_33.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_35.png)

![](img/b59d2af2c319dd07fa661e577b9bd25b_37.png)

本节课中我们一起学习了函数在一维实数空间上的可微性定义。我们明确了函数在一点可微意味着其差商的极限存在，并将该极限值定义为该点的导数。这是理解所有微分概念的基石。