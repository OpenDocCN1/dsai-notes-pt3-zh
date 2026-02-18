# 第一部分 35：线性近似 - 使用切线近似函数 📐

![](img/2694cb3fa34c976014edc2d4ab21e978_1.png)

在本节课中，我们将学习如何使用函数的切线来近似计算函数值。这是一种非常实用的数学工具，尤其在处理复杂函数或需要快速估算时。

![](img/2694cb3fa34c976014edc2d4ab21e978_2.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_3.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_4.png)

## 概述

导数的一个重要应用是求函数在某一点的切线斜率。我们发现，在切点附近，切线本身是原函数的一个非常好的近似。这个观察构成了**线性近似**的基础。

## 切线为何是好的近似？

![](img/2694cb3fa34c976014edc2d4ab21e978_6.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_7.png)

上一节我们提到了导数的几何意义。本节中，我们来看看为什么切线能作为函数的近似。

![](img/2694cb3fa34c976014edc2d4ab21e978_8.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_9.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_10.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_11.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_12.png)

以函数 **f(x) = sin(x)** 为例。下图展示了其在 x=0 处的图像和切线。

![](img/2694cb3fa34c976014edc2d4ab21e978_1.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_2.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_3.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_4.png)

在 x=0 处，切线的斜率由导数给出。从图中可以直观地看到，在零点附近，正弦曲线和它的切线几乎重合。然而，当远离零点时，两者就分道扬镳了。这说明，切线仅在切点附近是一个良好的近似。

![](img/2694cb3fa34c976014edc2d4ab21e978_14.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_15.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_16.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_6.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_7.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_8.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_9.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_10.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_11.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_12.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_17.png)

如果我们放大观察窗口，例如将窗口缩小到 [-0.2, 0.2]，会发现红色（切线）和绿色（正弦函数）的线条几乎完全重叠。

![](img/2694cb3fa34c976014edc2d4ab21e978_19.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_20.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_14.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_15.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_16.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_17.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_22.png)

因此，当我们足够靠近切点时，切线可以成为原函数一个极好的近似，至少在 sin(x) 这个例子中是这样。

![](img/2694cb3fa34c976014edc2d4ab21e978_19.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_20.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_24.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_25.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_26.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_27.png)

## 一个实际应用：估算平方根

理解了原理后，我们来看一个更具体的例子：估算 **√1.5** 的值。

![](img/2694cb3fa34c976014edc2d4ab21e978_29.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_30.png)

考虑函数 **f(x) = √x**。下图展示了其在 x=1 处的图像和切线。

![](img/2694cb3fa34c976014edc2d4ab21e978_22.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_32.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_33.png)

我们选择在 x=1 处作切线，因为 √1 = 1 是一个容易计算的精确值。同样，在 x=1 附近，切线是函数的一个良好近似。

![](img/2694cb3fa34c976014edc2d4ab21e978_34.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_35.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_36.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_37.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_24.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_25.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_26.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_27.png)

现在，我们想估算 √1.5。虽然 1.5 处的函数值（绿色曲线高度）我们不知道，但我们可以找到 1.5 处切线的值（红色直线高度）。

![](img/2694cb3fa34c976014edc2d4ab21e978_29.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_30.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_39.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_40.png)

从图中可以看出，在 x=1.5 处，切线的值（红色）与函数的真实值（绿色）非常接近，误差很小。

![](img/2694cb3fa34c976014edc2d4ab21e978_41.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_32.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_33.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_34.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_35.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_36.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_37.png)

我们的策略是：在已知点（x=1）计算切线方程，然后用这条切线在目标点（x=1.5）的值来近似函数值。

![](img/2694cb3fa34c976014edc2d4ab21e978_43.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_44.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_39.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_40.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_41.png)

换句话说，我们可以认为：
**√1.5 ≈ L(1.5)**，其中 L(x) 是函数在 x=1 处的切线。

![](img/2694cb3fa34c976014edc2d4ab21e978_46.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_43.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_44.png)

## 推导切线方程

现在，我们来具体计算这条切线 L(x)。

![](img/2694cb3fa34c976014edc2d4ab21e978_48.png)

首先，回忆直线的**点斜式**方程：
`y - y₀ = m (x - x₀)`
其中 `(x₀, y₀)` 是直线上已知的一点，`m` 是斜率。

![](img/2694cb3fa34c976014edc2d4ab21e978_50.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_46.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_52.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_53.png)

对于我们的情况：
*   切点：`(x₀, y₀) = (1, √1) = (1, 1)`
*   斜率 `m`：由导数 `f'(x)` 在 x=1 处的值给出。

![](img/2694cb3fa34c976014edc2d4ab21e978_55.png)

所以，我们需要先求 `f(x) = √x` 的导数。
将 `√x` 写作 `x^(1/2)`，应用幂法则：
`f'(x) = d/dx [x^(1/2)] = (1/2) * x^(-1/2) = 1 / (2√x)`

![](img/2694cb3fa34c976014edc2d4ab21e978_48.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_50.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_52.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_53.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_55.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_57.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_58.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_59.png)

在 x=1 处，斜率为：
`m = f'(1) = 1 / (2√1) = 1/2`

![](img/2694cb3fa34c976014edc2d4ab21e978_60.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_61.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_57.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_58.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_59.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_60.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_61.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_63.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_64.png)

将点 `(1, 1)` 和斜率 `m=1/2` 代入点斜式方程：
`y - 1 = (1/2)(x - 1)`

![](img/2694cb3fa34c976014edc2d4ab21e978_66.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_63.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_64.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_68.png)

整理成更常见的斜截式 `y = mx + b`：
`y = (1/2)x + 1/2`
这就是我们的切线方程 `L(x)`。

![](img/2694cb3fa34c976014edc2d4ab21e978_66.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_68.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_70.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_71.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_72.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_73.png)

## 进行近似计算

![](img/2694cb3fa34c976014edc2d4ab21e978_70.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_71.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_72.png)

现在，我们用 `L(1.5)` 来近似 `√1.5`：
`L(1.5) = (1/2)*1.5 + 1/2 = 0.75 + 0.5 = 1.25`

![](img/2694cb3fa34c976014edc2d4ab21e978_73.png)

因此，我们的近似结果是：**√1.5 ≈ 1.25**

![](img/2694cb3fa34c976014edc2d4ab21e978_75.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_75.png)

用计算器验证真实值：
`√1.5 ≈ 1.2247`

我们的近似值 1.25 与真实值 1.2247 非常接近，误差很小。这证实了线性近似的有效性。

![](img/2694cb3fa34c976014edc2d4ab21e978_77.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_78.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_79.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_80.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_81.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_83.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_84.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_85.png)

## 线性近似通用公式

![](img/2694cb3fa34c976014edc2d4ab21e978_77.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_78.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_79.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_80.png)

从上面的例子，我们可以总结出线性近似的通用公式。

![](img/2694cb3fa34c976014edc2d4ab21e978_81.png)

如果我们想近似计算函数 `f(x)` 在 `x` 点的值，而 `x` 靠近一个我们已知其函数值和导数值的点 `a`，那么近似公式为：

![](img/2694cb3fa34c976014edc2d4ab21e978_83.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_84.png)

**`f(x) ≈ f(a) + f'(a) * (x - a)`**

![](img/2694cb3fa34c976014edc2d4ab21e978_85.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_87.png)

这个公式的组成部分是：
*   `f(a)`：函数在已知点 `a` 的精确值（相当于直线方程中的 `y₀`）。
*   `f'(a)`：函数在点 `a` 的导数，即切线的斜率 `m`。
*   `(x - a)`：目标点 `x` 与已知点 `a` 的距离（相当于直线方程中的 `(x - x₀)`）。

![](img/2694cb3fa34c976014edc2d4ab21e978_87.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_89.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_90.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_91.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_92.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_93.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_89.png)

实际上，这个公式就是直线点斜式方程 `y - y₀ = m (x - x₀)` 的另一种写法，其中：
`y = f(x)`, `y₀ = f(a)`, `m = f'(a)`, `x₀ = a`。

![](img/2694cb3fa34c976014edc2d4ab21e978_90.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_91.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_92.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_93.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_95.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_96.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_98.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_100.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_101.png)
![](img/2694cb3fa34c976014edc2d4ab21e978_102.png)

**线性近似公式本质上就是在点 `a` 处的切线方程，并将其在点 `x` 处求值。**

![](img/2694cb3fa34c976014edc2d4ab21e978_95.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_96.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_104.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_98.png)

## 总结

本节课中，我们一起学习了**线性近似**的核心思想与方法。

![](img/2694cb3fa34c976014edc2d4ab21e978_100.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_101.png)

1.  **核心观察**：在函数图像上某一点附近，该点的切线可以很好地近似原函数。
2.  **核心方法**：要估算 `f(x)`，选择一个靠近 `x` 且易于计算的点 `a`，利用公式 **`f(x) ≈ f(a) + f'(a) * (x - a)`** 进行计算。
3.  **核心公式**：上述公式是线性近制的通用表达式，它直接来源于切线的点斜式方程。

![](img/2694cb3fa34c976014edc2d4ab21e978_102.png)

![](img/2694cb3fa34c976014edc2d4ab21e978_104.png)

线性近似是微积分中连接导数理论与实际应用的一座重要桥梁，它使得我们能够用简单的线性关系（直线）来理解和估算复杂的非线性函数在局部区域的行为。