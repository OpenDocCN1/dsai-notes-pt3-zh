# 第一部分 37：相对与绝对极值（第一部分）🔍 📘

在本节课中，我们将学习微积分中的一个核心概念：如何寻找函数的最大值和最小值。优化问题在各学科中普遍存在，例如最大化利润或最小化成本。微积分为我们提供了寻找这些极值的系统方法。

---

## 📈 极值问题的图形化理解

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_1.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_2.png)

上一节我们介绍了优化问题的普遍性，本节中我们来看看如何从图形上理解最大值和最小值。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_3.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_4.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_5.png)

观察下图中的抛物线，其最大值点非常明显：

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_6.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_7.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_8.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_1.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_2.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_3.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_4.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_5.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_6.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_7.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_8.png)

最大值体现在函数的高度上，并发生在特定的输入点。例如，在点 `x = 1` 处，函数达到一个局部最大值 `f(x) = 0.4`。

之所以称为“局部”最大值，是因为我们尚未看到整个函数图像。也许函数在后续会下降并再次升高。但至少在 `x = 1` 附近，该点确实是一个最大值。

虽然从图形上可以直观看出，但我们需要一个精确的数学定义。

---

## 📐 局部极值的数学定义

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_10.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_11.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_12.png)

为了精确描述，我们聚焦于 `x = 1` 这个点，其高度为 `0.4`。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_13.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_14.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_15.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_16.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_10.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_11.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_12.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_13.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_14.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_15.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_16.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_17.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_18.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_19.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_17.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_18.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_19.png)

如果我们移动到其他点，例如 `x ≈ 1.3`：

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_21.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_22.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_23.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_21.png)

无论移动到何处，新的高度都低于 `0.4`。在 `x = 1` 附近（不考虑远处奇怪的区域），该点的函数值高于任何邻近点的函数值。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_22.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_23.png)

我们可以将此概念编码为更精确的定义：

**局部最大值**：如果存在一个输入值 `c`，使得函数在 `c` 点的输出值 `f(c)` 大于所有邻近点 `x` 的输出值 `f(x)`，则 `f(c)` 是一个局部最大值。

用公式表示即：存在一个区间 `I` 包含 `c`，使得对于所有 `x ∈ I`，有 `f(c) ≥ f(x)`。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_25.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_26.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_27.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_31.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_32.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_28.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_29.png)

同理，我们可以定义**局部最小值**，只需将不等号方向反转：`f(c) ≤ f(x)`。例如，一个开口向上的抛物线顶点就是一个局部最小值。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_31.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_34.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_35.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_36.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_37.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_32.png)

---

## 🔄 局部极值与绝对极值的区别

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_34.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_35.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_36.png)

理解了局部极值后，我们来看一个更复杂的图形，以区分局部极值和绝对极值。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_37.png)

观察下面这个在区间 `[0, 2]` 上的函数：

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_39.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_39.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_41.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_42.png)

函数先上升后下降。图中有一个**局部最大值**（峰顶）和一个**局部最小值**（谷底）。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_41.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_42.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_44.png)

但请注意，这个局部最大值并不是整个区间 `[0, 2]` 上的最高点，这个局部最小值也不是整个区间上的最低点。它们只是“相对”的极值。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_44.png)

如果我们讨论**绝对最大值**（即整个区间上实际的最大值），它会出现在区间的端点或内部的最高点。在下图中，绝对最大值出现在右侧端点。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_46.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_47.png)

**绝对最小值**则是整个区间上实际的最小值，出现在左侧端点。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_46.png)

因此，我们有了明确的区分：
*   **局部（相对）极值**：在某个小邻域内是最高或最低点。
*   **绝对（全局）极值**：在整个给定的区间或定义域内是最高或最低点。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_47.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_49.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_50.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_51.png)
![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_52.png)

我们可以正式定义绝对最大值：对于定义在某个区间（例如 `[0, 2]`）上的函数 `f`，如果存在一点 `c`，使得对于该区间内的所有其他 `x`，都有 `f(c) ≥ f(x)`，则 `f(c)` 是绝对最大值。

同理，将不等号方向反转即可定义绝对最小值：`f(c) ≤ f(x)`。

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_49.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_50.png)

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_51.png)

---

![](img/804d6e6df1a6af27a4b2edb3b0e09e7b_52.png)

## 📝 总结

本节课中，我们一起学习了微积分中极值的基本概念：
1.  **局部极值**：函数在某个点附近（邻域内）达到的最大值或最小值。其数学定义依赖于与邻近点的比较。
2.  **绝对极值**：函数在整个给定区间上达到的最大值或最小值。它关注的是整个定义域范围内的最值。
3.  理解局部极值与绝对极值的区别至关重要，局部极值不一定是整体最优解，而绝对极值代表了在整个考虑范围内的最优值。

在接下来的课程中，我们将学习如何利用导数这一强大工具，来系统地寻找函数的这些极值点。