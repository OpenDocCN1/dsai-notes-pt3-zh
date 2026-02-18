# 第一部分 7：L7 - 有理函数极限的计算基础 📘

在本节课中，我们将学习如何计算有理函数的极限。我们会从最简单的常数函数和线性函数开始，逐步引入极限法则，并展示如何利用这些法则快速计算多项式和有理函数的极限。

---

## 🧮 常数函数的极限

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_1.png)

首先，我们来看一个非常简单的例子：计算常数函数当 `x` 趋近于某个值 `a` 时的极限。

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_2.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_3.png)

例如，考虑常数函数 `f(x) = 1`。其图像是一条高度恒为 1 的水平直线。

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_4.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_5.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_1.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_2.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_3.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_4.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_5.png)

无论我们考虑图像上的哪个点，当 `x` 趋近于该点时，函数值始终是 1。因此，常数 `C` 的极限就是它本身。

我们可以用以下公式表示：
```
lim(x→a) C = C
```

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_7.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_8.png)

---

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_9.png)

## 📈 线性函数 `f(x) = x` 的极限

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_11.png)

接下来，我们看一个稍微复杂一点的函数：`f(x) = x`。这是一个线性函数，其图像是一条穿过原点的直线。

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_13.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_7.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_8.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_9.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_11.png)

例如，当 `x` 趋近于 0.5 时，函数值就是 0.5。

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_15.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_16.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_13.png)

同理，当 `x` 趋近于 1 时，函数值是 1；当 `x` 趋近于 2 时，函数值是 2。

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_15.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_16.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_18.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_19.png)

因此，对于函数 `f(x) = x`，当 `x` 趋近于任意值 `a` 时，其极限就是 `a`。

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_20.png)

我们可以用以下公式表示：
```
lim(x→a) x = a
```

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_22.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_18.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_19.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_20.png)

---

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_24.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_25.png)

## 🧩 应用极限法则计算多项式极限

现在，我们来看一个更复杂的例子：计算多项式 `3x³ + x - 1` 当 `x` 趋近于 `a` 时的极限。

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_27.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_22.png)

我们可以利用极限法则来快速求解。以下是计算步骤：

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_29.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_30.png)

首先，根据“和的极限等于极限的和”这一法则，我们可以将整个多项式的极限分解为各项极限之和。

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_24.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_25.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_27.png)

因此，原极限可以写为：
```
lim(x→a) (3x³ + x - 1) = lim(x→a) 3x³ + lim(x→a) x + lim(x→a) (-1)
```

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_29.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_30.png)

接下来，我们分别处理每一项：
1.  对于 `lim(x→a) 3x³`，根据“常数倍法则”和“乘积的极限等于极限的乘积”，可以进一步分解。
2.  对于 `lim(x→a) x`，根据上一节的结论，其极限为 `a`。
3.  对于 `lim(x→a) (-1)`，根据常数函数的极限，其值为 `-1`。

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_32.png)

以下是详细的推导过程：

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_33.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_34.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_32.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_33.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_34.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_35.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_36.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_37.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_38.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_35.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_36.png)

最终，我们得到：
```
lim(x→a) (3x³ + x - 1) = 3a³ + a - 1
```

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_37.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_38.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_40.png)

这个结果告诉我们，对于任何多项式 `P(x)`，计算其极限时，我们只需将 `x` 替换为趋近值 `a` 即可。
```
lim(x→a) P(x) = P(a)
```

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_40.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_42.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_43.png)
![](img/ddfe9c5139b904c492c76c2aaf5b61a1_44.png)

---

## 🔄 有理函数的极限

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_42.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_43.png)

![](img/ddfe9c5139b904c492c76c2aaf5b61a1_44.png)

上述结论可以推广到更广泛的一类函数：**有理函数**。有理函数是指分子和分母都是多项式的函数，其一般形式为：
```
R(x) = P(x) / Q(x)
```

对于有理函数 `R(x)`，只要分母 `Q(x)` 在 `x = a` 处的值不为零（即 `Q(a) ≠ 0`），计算其极限就非常简单：直接将 `x = a` 代入函数即可。
```
lim(x→a) R(x) = R(a) = P(a) / Q(a)， 前提是 Q(a) ≠ 0
```

这意味着，对于绝大多数没有“分母为零”问题的有理函数，极限计算就是直接的代入求值。

---

## 📝 总结

本节课中，我们一起学习了计算有理函数极限的基础方法。

1.  我们首先明确了常数函数和线性函数 `f(x) = x` 的极限。
2.  然后，我们利用极限法则（和、积、常数倍法则）将复杂多项式的极限分解为简单部分的极限。
3.  最终我们发现，对于多项式，极限计算就是直接代入。这个结论可以安全地推广到分母不为零的有理函数。

因此，核心要点是：**对于多项式函数，以及分母在趋近点处不为零的有理函数，计算极限时，只需将变量 `x` 替换为趋近值 `a` 并进行计算。**