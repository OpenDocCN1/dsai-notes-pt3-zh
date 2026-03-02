#  040：均匀分布实例解析 📊

![](img/b915f4b938c2f8047cfae1d857f9d60b_0.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_2.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_3.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_5.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_7.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_9.png)

在本节课中，我们将通过一个连续随机变量的例子来学习均匀分布。我们将推导其概率密度函数、期望值和方差，并理解其在实际场景中的应用。

![](img/b915f4b938c2f8047cfae1d857f9d60b_11.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_13.png)

## 概述

![](img/b915f4b938c2f8047cfae1d857f9d60b_15.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_16.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_17.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_19.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_21.png)

我们将分析一个连续随机变量，并使用均匀分布作为例子。均匀分布的特点是，在某个区间内的所有值出现的可能性均等。

![](img/b915f4b938c2f8047cfae1d857f9d60b_23.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_25.png)

## 均匀分布的定义

![](img/b915f4b938c2f8047cfae1d857f9d60b_27.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_28.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_29.png)

均匀分布的概率密度函数图像是一个矩形。它表示在区间 `[A, B]` 内的所有值都是等可能出现的。

![](img/b915f4b938c2f8047cfae1d857f9d60b_31.png)

## 推导概率密度函数

![](img/b915f4b938c2f8047cfae1d857f9d60b_33.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_34.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_35.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_36.png)

现在，我们面临一个挑战性问题：概率密度函数 `f(x)` 在区间 `A < x < B` 内等于什么？以下是几个选项：
*   A: `B`
*   B: `(B - A) / 2`
*   C: `1 / (B - A)`
*   D: 以上都不是

![](img/b915f4b938c2f8047cfae1d857f9d60b_38.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_39.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_41.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_42.png)

请暂停视频，根据你对概率密度函数性质的理解，尝试推导出正确答案。

---

![](img/b915f4b938c2f8047cfae1d857f9d60b_44.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_45.png)

（假设你已经思考完毕）

![](img/b915f4b938c2f8047cfae1d857f9d60b_47.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_49.png)

现在，我们使用一个“排除法”提示。选项A和B是不正确的。如果你选择了它们，请再思考一下。

![](img/b915f4b938c2f8047cfae1d857f9d60b_51.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_53.png)

正确答案是 **C**：`1 / (B - A)`。

![](img/b915f4b938c2f8047cfae1d857f9d60b_55.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_57.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_59.png)

我们是如何得到这个答案的呢？根据概率密度函数的性质，其在整个定义域上的积分（即曲线下的总面积）必须等于1。

![](img/b915f4b938c2f8047cfae1d857f9d60b_61.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_63.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_65.png)

对于均匀分布，这个面积是一个矩形：
*   **高度** 是概率密度函数值 `f(x)`。
*   **宽度** 是区间长度 `(B - A)`。

![](img/b915f4b938c2f8047cfae1d857f9d60b_67.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_68.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_70.png)

因此，面积公式为：
`f(x) * (B - A) = 1`

解这个方程，得到：
`f(x) = 1 / (B - A)`

![](img/b915f4b938c2f8047cfae1d857f9d60b_72.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_73.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_74.png)

这个推导过程展示了如何利用概率密度函数的基本性质（总面积为1、非负性、单点概率为0）来求解未知的分布参数。

![](img/b915f4b938c2f8047cfae1d857f9d60b_75.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_76.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_77.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_78.png)

## 计算期望值

![](img/b915f4b938c2f8047cfae1d857f9d60b_80.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_81.png)

上一节我们推导了均匀分布的概率密度函数，本节中我们来看看如何计算它的期望值（均值）。

![](img/b915f4b938c2f8047cfae1d857f9d60b_82.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_83.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_84.png)

随机变量 `X` 的期望值 `E[X]` 定义为：
`E[X] = ∫(从 A 到 B) x * f(x) dx`

![](img/b915f4b938c2f8047cfae1d857f9d60b_86.png)

其中 `f(x) = 1 / (B - A)`。

![](img/b915f4b938c2f8047cfae1d857f9d60b_88.png)

所以：
`E[X] = ∫(从 A 到 B) x * [1 / (B - A)] dx`

![](img/b915f4b938c2f8047cfae1d857f9d60b_90.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_92.png)

这是一个简单的积分计算。请暂停视频，尝试自己完成这个计算。

![](img/b915f4b938c2f8047cfae1d857f9d60b_93.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_94.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_96.png)

---

（计算过程）
`E[X] = 1/(B-A) * ∫(从 A 到 B) x dx = 1/(B-A) * [ (1/2)x^2 ] (从 A 到 B)`
`= 1/(B-A) * (1/2)(B^2 - A^2) = (B^2 - A^2) / [2(B-A)]`

![](img/b915f4b938c2f8047cfae1d857f9d60b_98.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_99.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_100.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_101.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_102.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_103.png)

利用平方差公式 `B^2 - A^2 = (B - A)(B + A)`，可得：
`E[X] = [(B - A)(B + A)] / [2(B - A)] = (A + B) / 2`

![](img/b915f4b938c2f8047cfae1d857f9d60b_104.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_106.png)

因此，均匀分布的期望值就是区间 `[A, B]` 的**中点**。这与我们的直观理解相符：所有值等可能出现，平均值自然落在正中间。

![](img/b915f4b938c2f8047cfae1d857f9d60b_108.png)

## 计算方差与标准差

![](img/b915f4b938c2f8047cfae1d857f9d60b_110.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_112.png)

知道了期望值，我们接下来计算均匀分布的方差，它衡量了数据的离散程度。

方差 `Var(X)` 的计算公式为：
`Var(X) = E[(X - E[X])^2] = ∫(从 A 到 B) (x - E[X])^2 * f(x) dx`

![](img/b915f4b938c2f8047cfae1d857f9d60b_114.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_115.png)

将 `E[X] = (A+B)/2` 和 `f(x) = 1/(B-A)` 代入公式。请暂停视频，尝试写出完整的积分表达式。

![](img/b915f4b938c2f8047cfae1d857f9d60b_116.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_117.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_118.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_119.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_120.png)

---

![](img/b915f4b938c2f8047cfae1d857f9d60b_122.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_123.png)

完整的积分表达式为：
`Var(X) = ∫(从 A 到 B) [x - (A+B)/2]^2 * [1/(B-A)] dx`

![](img/b915f4b938c2f8047cfae1d857f9d60b_125.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_126.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_127.png)

通过计算这个积分（过程略），我们可以得到方差的结果：
`Var(X) = (B - A)^2 / 12`

这个结果很有意思：方差与区间宽度 `(B-A)` 的平方成正比。区间越宽，数据越分散，方差越大；区间越窄，数据越集中，方差越小。这完全符合我们的直觉。至于为什么除以12，这是一个由积分计算得出的常数。

标准差 `σ` 是方差的平方根：
`σ = sqrt(Var(X)) = (B - A) / sqrt(12)`

![](img/b915f4b938c2f8047cfae1d857f9d60b_129.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_130.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_131.png)

## 总结与应用

![](img/b915f4b938c2f8047cfae1d857f9d60b_132.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_133.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_134.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_135.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_136.png)

本节课中，我们一起学习了连续均匀分布。我们不仅了解了它的形状，更重要的是，我们实践了如何运用概率密度函数的性质来：
1.  **推导**具体的密度函数 `f(x) = 1/(B-A)`。
2.  **计算**其期望值 `E[X] = (A+B)/2`。
3.  **计算**其方差 `Var(X) = (B-A)^2/12` 和标准差。

![](img/b915f4b938c2f8047cfae1d857f9d60b_138.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_139.png)

你应该能够将这种方法应用到其他更复杂的分布中去。

**为什么使用均匀分布？** 它很好地表达了“所有可能性均等”的概念。一个典型的例子是：如果你在某个公交站等一辆每15分钟一班的公交车，并且你没有看时间，那么你的等待时间 `X` 就服从区间 `[0, 15]` 分钟上的均匀分布。在0到15分钟之间的任意等待时长都是等可能的。

![](img/b915f4b938c2f8047cfae1d857f9d60b_141.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_142.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_143.png)

![](img/b915f4b938c2f8047cfae1d857f9d60b_144.png)

**关键要点**：对于连续随机变量，我们通过概率密度函数来描述它，并利用积分来计算其期望值和方差。这是处理任何连续分布的基础方法。