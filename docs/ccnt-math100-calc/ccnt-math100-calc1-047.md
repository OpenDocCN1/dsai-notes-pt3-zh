# 第一部分 47：定积分第一部分 - 用矩形逼近面积 📐

在本节课中，我们将要学习微积分中的第二个主要工具——积分。我们将从一个简单的几何问题开始：如何计算曲线下的面积？我们将通过使用矩形来逼近这个面积，并理解当矩形的数量趋于无穷时，这种逼近如何给出精确的面积值。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_1.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_2.png)

---

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_3.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_4.png)

## 🎯 从几何问题引入积分

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_6.png)

我们有一个曲线，其函数为 **y = x²**。我们关注的是该曲线在 **x = 0** 到 **x = 1** 区间内，与 x 轴所围成的面积。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_8.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_1.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f3.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f4.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_9.png)

这个形状不是标准的三角形、圆形或矩形，我们没有现成的公式来计算它的面积。积分将帮助我们回答这类问题，并且我们将用它来定义积分的概念。

![](img/ba906ad2c32bb4f3cdc77ecbd2f6.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f8.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f9.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_11.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_12.png)

---

## 📏 使用矩形进行粗略逼近

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_14.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_15.png)

首先，我们给出一个相对粗略的逼近方法。我们将区间 [0, 1] 分成五个等宽的子区间：0, 0.2, 0.4, 0.6, 0.8, 1。然后，我们在每个子区间上构造一个矩形。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_17.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f11.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f12.png)

这里，所有矩形的宽度都是 **0.2**。我们选择每个子区间的**右端点**来确定矩形的高度，即让矩形的右上角落在曲线 **y = x²** 上。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_19.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f14.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f15.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f17.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_20.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_21.png)

以下是计算这五个矩形总面积的过程：
*   第一个矩形：宽度 0.2，高度为 f(0.2) = (0.2)² = 0.04。
*   第二个矩形：宽度 0.2，高度为 f(0.4) = (0.4)² = 0.16。
*   第三个矩形：宽度 0.2，高度为 f(0.6) = (0.6)² = 0.36。
*   第四个矩形：宽度 0.2，高度为 f(0.8) = (0.8)² = 0.64。
*   第五个矩形：宽度 0.2，高度为 f(1) = (1)² = 1。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_23.png)

总面积 R₅ = 0.2 × (0.04 + 0.16 + 0.36 + 0.64 + 1) = 0.2 × 2.2 = **0.44**。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_25.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f19.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f20.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f21.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_26.png)

这个值 **0.44** 是对曲线下真实面积的一个**高估**，因为每个矩形都超出了曲线。但作为一个初步近似，这个结果看起来是合理的。

---

## 🔄 尝试左端点逼近

上一节我们使用了右端点来确定矩形高度。本节中，我们来看看如果使用**左端点**会发生什么。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_28.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f23.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f25.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f26.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_29.png)

以下是计算这五个矩形（使用左端点）总面积的过程：
*   第一个矩形：宽度 0.2，高度为 f(0) = (0)² = 0。
*   第二个矩形：宽度 0.2，高度为 f(0.2) = (0.2)² = 0.04。
*   第三个矩形：宽度 0.2，高度为 f(0.4) = (0.4)² = 0.16。
*   第四个矩形：宽度 0.2，高度为 f(0.6) = (0.6)² = 0.36。
*   第五个矩形：宽度 0.2，高度为 f(0.8) = (0.8)² = 0.64。

总面积 L₅ = 0.2 × (0 + 0.04 + 0.16 + 0.36 + 0.64) = 0.2 × 1.2 = **0.24**。

![](img/ba906ad2c32bb4f3cdc77ecbd2f28.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f29.png)

这个值 **0.24** 是对曲线下真实面积的一个**低估**。现在我们有了两个不同的近似值：0.44（右端点，高估）和 0.24（左端点，低估）。真实面积应该介于两者之间。

---

## 📈 增加矩形数量以改进逼近

我们之前只用了5个矩形。能否做得更好？本节中，我们来看看如果将区间分成更多份，例如10个矩形，逼近效果会如何改善。

![](img/ba906ad2c32bb4f3cdc77ecbd2f31.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f32.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_31.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_32.png)

使用10个矩形（宽度为0.1）和右端点法，逼近误差会变小。与5个矩形的情况相比，矩形与曲线之间的“空隙”明显减少了。

![](img/ba906ad2c32bb4f3cdc77ecbd2f34.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f35.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f37.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_34.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_35.png)

我们可以从中得出一个结论：当使用的矩形数量较少时，误差较大；当使用的矩形数量较多时，误差较小。

---

## ♾️ 核心思想：取极限得到精确面积

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_37.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_38.png)

让我们用 **Rₙ** 表示使用 **n** 个矩形（例如右端点法）得到的面积近似值。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_39.png)

那么，核心思想是：如果我们不是用10个、50个或100个矩形，而是让矩形的数量 **n** 趋向于无穷大会怎样？

![](img/ba906ad2c32bb4f3cdc77ecbd2f38.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f39.png)

我们定义，曲线 **y = f(x)** 在区间 **[a, b]** 下的**精确面积 A**，等于当矩形数量 **n** 趋于无穷时，矩形面积和的极限。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_41.png)

用公式表示为：
**A = lim (n→∞) Rₙ**

这意味着，随着矩形数量无限增加，每个矩形的宽度无限缩小，这些矩形面积的总和将无限逼近曲线下的真实面积。这个极限值就是我们将要定义的**定积分**。

![](img/ba906ad2c32bb4f3cdc77ecbd2f41.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f43.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f45.png)
![](img/ba906ad2c32bb4f3cdc77ecbd2f46.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_43.png)

---

## 📝 总结

本节课中我们一起学习了：
1.  积分可以解决的一个基本几何问题：计算曲线下的面积。
2.  使用矩形（右端点或左端点）来近似计算该面积的方法。
3.  增加矩形的数量可以改善近似的精度。
4.  通过取矩形数量趋于无穷的极限，可以得到面积的精确值，这引出了定积分的核心概念。

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_45.png)

![](img/ba906ad2c32bb4f3cdc77ecbd2f8404e_46.png)

这是理解积分概念的第一步。在接下来的课程中，我们将把这个思想形式化，并学习如何实际计算各种函数的定积分。