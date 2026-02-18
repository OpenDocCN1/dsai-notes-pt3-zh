# 第一部分 8：L8 - 振荡函数的极限与夹逼定理 📊

![](img/ccca4617541bbba49a37db3e2dac8891_1.png)

在本节课中，我们将学习如何分析振荡函数的极限，并介绍一个强大的工具——夹逼定理。我们将通过具体的例子来理解这些概念。

![](img/ccca4617541bbba49a37db3e2dac8891_3.png)

![](img/ccca4617541bbba49a37db3e2dac8891_4.png)

## 🔍 探索一个有趣的极限

![](img/ccca4617541bbba49a37db3e2dac8891_6.png)

我们首先研究以下极限：

![](img/ccca4617541bbba49a37db3e2dac8891_1.png)

我们要求的是当 `x` 从右侧趋近于 `0` 时，函数 `sin(1/x)` 的极限。

![](img/ccca4617541bbba49a37db3e2dac8891_8.png)

![](img/ccca4617541bbba49a37db3e2dac8891_9.png)

![](img/ccca4617541bbba49a37db3e2dac8891_10.png)

![](img/ccca4617541bbba49a37db3e2dac8891_3.png)
![](img/ccca4617541bbba49a37db3e2dac8891_4.png)

因此，我们需要弄清楚函数 `sin(1/x)` 的图像到底是什么样子。

## 📈 理解 `sin(1/x)` 的图像

![](img/ccca4617541bbba49a37db3e2dac8891_12.png)

首先，回想一下 `sin(x)` 的图像。它是一条在 `-1` 和 `1` 之间上下波动的曲线，并且这种模式会无限重复。

![](img/ccca4617541bbba49a37db3e2dac8891_13.png)

![](img/ccca4617541bbba49a37db3e2dac8891_14.png)

![](img/ccca4617541bbba49a37db3e2dac8891_15.png)

![](img/ccca4617541bbba49a37db3e2dac8891_8.png)
![](img/ccca4617541bbba49a37db3e2dac8891_9.png)
![](img/ccca4617541bbba49a37db3e2dac8891_10.png)

![](img/ccca4617541bbba49a37db3e2dac8891_16.png)

![](img/ccca4617541bbba49a37db3e2dac8891_17.png)

现在考虑 `sin(1/x)`。当 `x` 非常接近 `0` 时，`1/x` 会变得非常大。例如，如果 `x = 0.01`，那么 `1/x = 100`。所以，当 `x` 越来越接近 `0` 时，正弦函数内部的 `1/x` 会变得极其巨大。

![](img/ccca4617541bbba49a37db3e2dac8891_12.png)
![](img/ccca4617541bbba49a37db3e2dac8891_13.png)
![](img/ccca4617541bbba49a37db3e2dac8891_14.png)
![](img/ccca4617541bbba49a37db3e2dac8891_15.png)
![](img/ccca4617541bbba49a37db3e2dac8891_16.png)
![](img/ccca4617541bbba49a37db3e2dac8891_17.png)

当 `x` 变得非常大时，`sin(x)` 本身（不是 `sin(1/x)`）仍然只是在 `-1` 和 `1` 之间上下波动。因此，`sin(1/x)` 的图像在 `x` 接近 `0` 的区域会以极快的速度在 `-1` 和 `1` 之间振荡。

![](img/ccca4617541bbba49a37db3e2dac8891_19.png)

![](img/ccca4617541bbba49a37db3e2dac8891_20.png)

![](img/ccca4617541bbba49a37db3e2dac8891_19.png)
![](img/ccca4617541bbba49a37db3e2dac8891_20.png)
![](img/ccca4617541bbba49a37db3e2dac8891_21.png)

![](img/ccca4617541bbba49a37db3e2dac8891_21.png)

![](img/ccca4617541bbba49a37db3e2dac8891_23.png)

这个图像看起来有些奇特，但这就是 `sin(1/x)` 的图形。

![](img/ccca4617541bbba49a37db3e2dac8891_23.png)

其原理是：在 `x` 从右侧无限接近 `0` 的一个极小区域内，输入到正弦函数中的值（即 `1/x`）会变得极其巨大（如一百万、十亿、一万亿）。而 `sin(一百万)`、`sin(十亿)` 等值会在 `-1` 和 `1` 之间极其快速地振荡。因此，当我们绘制 `sin(1/x)` 时，这种振荡被“压缩”在了 `x` 接近 `0` 的狭窄区域内。

![](img/ccca4617541bbba49a37db3e2dac8891_25.png)
![](img/ccca4617541bbba49a37db3e2dac8891_26.png)
![](img/ccca4617541bbba49a37db3e2dac8891_27.png)
![](img/ccca4617541bbba49a37db3e2dac8891_28.png)
![](img/ccca4617541bbba49a37db3e2dac8891_29.png)
![](img/ccca4617541bbba49a37db3e2dac8891_30.png)

## ❓ 极限存在吗？

![](img/ccca4617541bbba49a37db3e2dac8891_25.png)

![](img/ccca4617541bbba49a37db3e2dac8891_26.png)

现在我们已经了解了这个函数的图像，那么当 `x` 从右侧趋近于 `0` 时，它的极限到底是什么呢？

![](img/ccca4617541bbba49a37db3e2dac8891_27.png)

![](img/ccca4617541bbba49a37db3e2dac8891_28.png)

![](img/ccca4617541bbba49a37db3e2dac8891_32.png)
![](img/ccca4617541bbba49a37db3e2dac8891_33.png)

![](img/ccca4617541bbba49a37db3e2dac8891_29.png)

![](img/ccca4617541bbba49a37db3e2dac8891_30.png)

我们无法趋近于任何一个单一的值。在 `x` 接近 `0` 时，函数值有时在 `1`，有时在 `-1`，有时在中间某个位置。随着我们从右侧无限接近 `0`，函数振荡得越来越快，但并没有稳定地趋向于某个特定的数值。

![](img/ccca4617541bbba49a37db3e2dac8891_35.png)
![](img/ccca4617541bbba49a37db3e2dac8891_36.png)

![](img/ccca4617541bbba49a37db3e2dac8891_32.png)

![](img/ccca4617541bbba49a37db3e2dac8891_33.png)

因此，我们说这个极限**不存在**（DNE）。

## ➕ 一个稍作修改的极限

接下来，我们研究一个非常相似但略有不同的极限。我们仍然考虑 `x` 从右侧趋近于 `0`，函数中仍然包含 `sin(1/x)`，但现在它被额外乘以了一个因子 `x`。

![](img/ccca4617541bbba49a37db3e2dac8891_35.png)

![](img/ccca4617541bbba49a37db3e2dac8891_36.png)

![](img/ccca4617541bbba49a37db3e2dac8891_38.png)
![](img/ccca4617541bbba49a37db3e2dac8891_39.png)
![](img/ccca4617541bbba49a37db3e2dac8891_40.png)
![](img/ccca4617541bbba49a37db3e2dac8891_41.png)
![](img/ccca4617541bbba49a37db3e2dac8891_42.png)

关键区别在于：当 `x` 趋近于 `0` 时，因子 `x` 本身也趋近于 `0`。虽然 `sin(1/x)` 仍在 `-1` 和 `1` 之间振荡，并且随着 `x` 趋近于 `0` 振荡得越来越快，但现在它被乘以了 `x`，这个因子会将其“拉向” `0`。

![](img/ccca4617541bbba49a37db3e2dac8891_44.png)
![](img/ccca4617541bbba49a37db3e2dac8891_45.png)
![](img/ccca4617541bbba49a37db3e2dac8891_46.png)
![](img/ccca4617541bbba49a37db3e2dac8891_47.png)

![](img/ccca4617541bbba49a37db3e2dac8891_38.png)

## 📊 `x * sin(1/x)` 的图像

![](img/ccca4617541bbba49a37db3e2dac8891_39.png)

![](img/ccca4617541bbba49a37db3e2dac8891_40.png)

![](img/ccca4617541bbba49a37db3e2dac8891_41.png)

函数 `x * sin(1/x)` 的图像如下所示。它仍然试图进行那种振荡，但它被两个函数“包裹”住了。我在这里用蓝色画出了两条“包络线”函数：一条是 `y = x`，另一条是 `y = -x`。

![](img/ccca4617541bbba49a37db3e2dac8891_42.png)

![](img/ccca4617541bbba49a37db3e2dac8891_49.png)
![](img/ccca4617541bbba49a37db3e2dac8891_50.png)

因为 `sin(1/x)` 的值始终在 `-1` 和 `1` 之间，所以 `x * sin(1/x)` 的值始终在 `x` 和 `-x` 之间。这就是为什么我画出 `y = x` 和 `y = -x` 这两条线作为包络线。函数 `x * sin(1/x)` 在其中进行它想要的振荡行为，但始终被限制在这两条线之间。

![](img/ccca4617541bbba49a37db3e2dac8891_52.png)
![](img/ccca4617541bbba49a37db3e2dac8891_53.png)
![](img/ccca4617541bbba49a37db3e2dac8891_54.png)
![](img/ccca4617541bbba49a37db3e2dac8891_55.png)

![](img/ccca4617541bbba49a37db3e2dac8891_44.png)

![](img/ccca4617541bbba49a37db3e2dac8891_45.png)

现在，如果我们观察极限，函数 `x * sin(1/x)` 看起来越来越接近 `0`。因此，我们可以得出结论：

![](img/ccca4617541bbba49a37db3e2dac8891_46.png)

![](img/ccca4617541bbba49a37db3e2dac8891_47.png)

![](img/ccca4617541bbba49a37db3e2dac8891_57.png)
![](img/ccca4617541bbba49a37db3e2dac8891_58.png)

## 🧮 引入夹逼定理

我们在上面这个例子中使用的基本逻辑，可以推广成一个独立的定理——**夹逼定理**。

![](img/ccca4617541bbba49a37db3e2dac8891_49.png)

![](img/ccca4617541bbba49a37db3e2dac8891_50.png)

夹逼定理的运作方式如下：假设我们有三个函数 `f(x)`， `g(x)`， 和 `h(x)`。

![](img/ccca4617541bbba49a37db3e2dac8891_60.png)
![](img/ccca4617541bbba49a37db3e2dac8891_61.png)
![](img/ccca4617541bbba49a37db3e2dac8891_62.png)

其中，`f(x)` 是最小的函数，`h(x)` 是最大的函数，而 `g(x)` 被夹在它们中间。也就是说，在某个区间内（除了可能点 `a` 本身），有：

![](img/ccca4617541bbba49a37db3e2dac8891_52.png)

![](img/ccca4617541bbba49a37db3e2dac8891_53.png)

**`f(x) ≤ g(x) ≤ h(x)`**

![](img/ccca4617541bbba49a37db3e2dac8891_54.png)

![](img/ccca4617541bbba49a37db3e2dac8891_55.png)

我们关心的是函数 `g(x)` 在 `x` 趋近于 `a` 时的极限。

![](img/ccca4617541bbba49a37db3e2dac8891_64.png)
![](img/ccca4617541bbba49a37db3e2dac8891_65.png)
![](img/ccca4617541bbba49a37db3e2dac8891_66.png)

如果当 `x` 趋近于 `a` 时，较小的函数 `f(x)` 和较大的函数 `h(x)` 的极限都等于同一个数 `L`：

![](img/ccca4617541bbba49a37db3e2dac8891_57.png)

![](img/ccca4617541bbba49a37db3e2dac8891_58.png)

**`lim (x→a) f(x) = L` 且 `lim (x→a) h(x) = L`**

那么，被夹在中间的 `g(x)` 也别无选择，它的极限也必须等于同一个数 `L`：

![](img/ccca4617541bbba49a37db3e2dac8891_60.png)

![](img/ccca4617541bbba49a37db3e2dac8891_61.png)

**`lim (x→a) g(x) = L`**

![](img/ccca4617541bbba49a37db3e2dac8891_62.png)

![](img/ccca4617541bbba49a37db3e2dac8891_68.png)
![](img/ccca4617541bbba49a37db3e2dac8891_69.png)
![](img/ccca4617541bbba49a37db3e2dac8891_70.png)
![](img/ccca4617541bbba49a37db3e2dac8891_71.png)

## 🔄 用夹逼定理解释之前的例子

![](img/ccca4617541bbba49a37db3e2dac8891_64.png)

在我们之前的例子中，我们感兴趣的函数是 `g(x) = x * sin(1/x)`。

![](img/ccca4617541bbba49a37db3e2dac8891_65.png)

![](img/ccca4617541bbba49a37db3e2dac8891_66.png)

![](img/ccca4617541bbba49a37db3e2dac8891_73.png)

我们将其夹在两个函数之间：`f(x) = -x` 和 `h(x) = x`。当 `x` 从右侧趋近于 `0` 时，`f(x)` 和 `h(x)` 的极限都是 `0`。

![](img/ccca4617541bbba49a37db3e2dac8891_68.png)

![](img/ccca4617541bbba49a37db3e2dac8891_75.png)
![](img/ccca4617541bbba49a37db3e2dac8891_76.png)
![](img/ccca4617541bbba49a37db3e2dac8891_77.png)
![](img/ccca4617541bbba49a37db3e2dac8891_78.png)

![](img/ccca4617541bbba49a37db3e2dac8891_69.png)

![](img/ccca4617541bbba49a37db3e2dac8891_70.png)

![](img/ccca4617541bbba49a37db3e2dac8891_71.png)

因此，根据夹逼定理，被夹在中间的 `g(x) = x * sin(1/x)` 的极限也必须是 `0`。

![](img/ccca4617541bbba49a37db3e2dac8891_73.png)

## 📝 代数推导

如果我们想用代数方式验证这个例子，可以按以下步骤进行：

首先，观察到正弦函数的一个基本性质：对于任何输入，其值都在 `-1` 和 `1` 之间。

![](img/ccca4617541bbba49a37db3e2dac8891_75.png)

**`-1 ≤ sin(1/x) ≤ 1`**

![](img/ccca4617541bbba49a37db3e2dac8891_76.png)

![](img/ccca4617541bbba49a37db3e2dac8891_77.png)

![](img/ccca4617541bbba49a37db3e2dac8891_78.png)

![](img/ccca4617541bbba49a37db3e2dac8891_80.png)
![](img/ccca4617541bbba49a37db3e2dac8891_81.png)
![](img/ccca4617541bbba49a37db3e2dac8891_83.png)

然后，在 `x > 0` 的范围内，将不等式两边同时乘以 `x`（注意乘以正数不改变不等号方向），得到：

![](img/ccca4617541bbba49a37db3e2dac8891_80.png)

![](img/ccca4617541bbba49a37db3e2dac8891_81.png)

**`-x ≤ x * sin(1/x) ≤ x`**

![](img/ccca4617541bbba49a37db3e2dac8891_83.png)

![](img/ccca4617541bbba49a37db3e2dac8891_85.png)
![](img/ccca4617541bbba49a37db3e2dac8891_86.png)
![](img/ccca4617541bbba49a37db3e2dac8891_87.png)

现在，应用夹逼定理。我们令：
*   `f(x) = -x`
*   `g(x) = x * sin(1/x)`
*   `h(x) = x`

![](img/ccca4617541bbba49a37db3e2dac8891_85.png)

我们知道：
**`lim (x→0⁺) f(x) = lim (x→0⁺) (-x) = 0`**
**`lim (x→0⁺) h(x) = lim (x→0⁺) x = 0`**

![](img/ccca4617541bbba49a37db3e2dac8891_86.png)

![](img/ccca4617541bbba49a37db3e2dac8891_87.png)

![](img/ccca4617541bbba49a37db3e2dac8891_89.png)
![](img/ccca4617541bbba49a37db3e2dac8891_90.png)

由于 `g(x)` 被夹在 `f(x)` 和 `h(x)` 之间，并且这两个函数的极限相同（都是 `0`），因此根据夹逼定理，我们可以推导出：

![](img/ccca4617541bbba49a37db3e2dac8891_89.png)

![](img/ccca4617541bbba49a37db3e2dac8891_90.png)

**`lim (x→0⁺) g(x) = lim (x→0⁺) [x * sin(1/x)] = 0`**

![](img/ccca4617541bbba49a37db3e2dac8891_92.png)

## 🎯 总结

在本节课中，我们一起学习了：
1.  **振荡函数的极限**：以 `sin(1/x)` 为例，当 `x` 趋近于 `0` 时，函数值在 `-1` 和 `1` 之间无限快速地振荡，导致极限不存在（DNE）。
2.  **夹逼定理**：如果一个函数 `g(x)` 被两个函数 `f(x)` 和 `h(x)` 夹在中间（即 `f(x) ≤ g(x) ≤ h(x)`），并且当 `x` 趋近于某点 `a` 时，`f(x)` 和 `h(x)` 的极限都等于 `L`，那么 `g(x)` 在该点的极限也必然等于 `L`。
3.  **定理的应用**：我们使用夹逼定理成功求出了 `lim (x→0⁺) x * sin(1/x) = 0`。通过将目标函数夹在 `y = x` 和 `y = -x` 之间，利用这两个简单函数的极限推导出了复杂振荡函数的极限。

![](img/ccca4617541bbba49a37db3e2dac8891_92.png)

夹逼定理是处理那些难以直接计算极限的函数的强大工具，特别是当函数表现出振荡行为时。