# 第二部分 6：L6 - 三角换元法：如何选择换元及处理不定积分 📚

在本节课中，我们将学习三角换元法的第二个例子。我们将重点关注两个关键变化：如何处理不定积分，以及如何系统地选择恰当的三角换元策略。

---

## 🔍 概述与问题引入

上一节我们介绍了定积分的三角换元法，并学习了如何相应地改变积分上下限。本节中，我们将处理一个不定积分，并深入探讨如何根据被积函数的形式，选择正确的三角换元。

我们面临的积分是：
\[
\int \frac{1}{(x^2 + 4)^2} \, dx
\]

---

## 🤔 如何选择三角换元

选择换元的核心在于识别被积函数的形式，并匹配相应的三角恒等式。我们主要依赖以下两个毕达哥拉斯恒等式：

1.  \(\sin^2 \theta + \cos^2 \theta = 1\)
2.  \(\tan^2 \theta + 1 = \sec^2 \theta\)

以下是选择换元策略的思考过程：

观察积分中的表达式 \(x^2 + 4\)。它类似于恒等式 \(\tan^2 \theta + 1 = \sec^2 \theta\) 中的结构，但多了一个系数 4。

为了匹配这个形式，我们设：
\[
x = 2 \tan \theta
\]
这样，\(x^2 = 4 \tan^2 \theta\)，代入原式可得 \(4 \tan^2 \theta + 4 = 4(\tan^2 \theta + 1)\)，完美地应用了第二个恒等式。

同时，我们需要限制 \(\theta\) 的定义域，通常选择 \(-\frac{\pi}{2} < \theta < \frac{\pi}{2}\)，以确保 \(\tan \theta\) 是单调的，便于后续回代。

---

## 📝 执行换元与积分计算

确定了换元 \(x = 2 \tan \theta\) 后，我们计算微分 \(dx\)：
\[
dx = 2 \sec^2 \theta \, d\theta
\]

将 \(x\) 和 \(dx\) 代入原积分：
\[
\int \frac{1}{(x^2 + 4)^2} \, dx = \int \frac{2 \sec^2 \theta}{( (2 \tan \theta)^2 + 4 )^2} \, d\theta
\]

化简分母：
\[
( (2 \tan \theta)^2 + 4 )^2 = (4 \tan^2 \theta + 4)^2 = (4(\tan^2 \theta + 1))^2 = (4 \sec^2 \theta)^2 = 16 \sec^4 \theta
\]

因此，积分变为：
\[
\int \frac{2 \sec^2 \theta}{16 \sec^4 \theta} \, d\theta = \frac{1}{8} \int \frac{1}{\sec^2 \theta} \, d\theta = \frac{1}{8} \int \cos^2 \theta \, d\theta
\]

现在，我们处理一个纯三角函数的积分。利用半角公式 \(\cos^2 \theta = \frac{1}{2}(1 + \cos 2\theta)\)：
\[
\frac{1}{8} \int \cos^2 \theta \, d\theta = \frac{1}{8} \int \frac{1}{2}(1 + \cos 2\theta) \, d\theta = \frac{1}{16} \int (1 + \cos 2\theta) \, d\theta
\]

计算积分：
\[
\frac{1}{16} \left( \theta + \frac{1}{2} \sin 2\theta \right) + C
\]

为了便于后续回代，我们使用倍角公式 \(\sin 2\theta = 2 \sin \theta \cos \theta\) 展开 \(\sin 2\theta\) 项：
\[
\frac{1}{16} \theta + \frac{1}{16} \cdot \frac{1}{2} \cdot 2 \sin \theta \cos \theta + C = \frac{1}{16} \theta + \frac{1}{16} \sin \theta \cos \theta + C
\]

---

## 🔄 将结果从 \(\theta\) 回代为 \(x\)

我们的最终答案需要用变量 \(x\) 表示。根据换元 \(x = 2 \tan \theta\)，我们有：
\[
\tan \theta = \frac{x}{2}
\]

直接反解 \(\theta\) 是可行的：\(\theta = \arctan(\frac{x}{2})\)。但对于 \(\sin \theta\) 和 \(\cos \theta\)，直接计算反三角函数的值并不直观。更好的方法是构造一个直角三角形。

以下是构造直角三角形的步骤：

1.  由 \(\tan \theta = \frac{x}{2}\)，可设对边为 \(x\)，邻边为 \(2\)。
2.  根据勾股定理，斜边为 \(\sqrt{x^2 + 2^2} = \sqrt{x^2 + 4}\)。

由此，我们可以直接读出：
\[
\sin \theta = \frac{\text{对边}}{\text{斜边}} = \frac{x}{\sqrt{x^2 + 4}}
\]
\[
\cos \theta = \frac{\text{邻边}}{\text{斜边}} = \frac{2}{\sqrt{x^2 + 4}}
\]

现在，将 \(\theta, \sin \theta, \cos \theta\) 的表达式代回积分结果：
\[
\frac{1}{16} \arctan\left(\frac{x}{2}\right) + \frac{1}{16} \left( \frac{x}{\sqrt{x^2 + 4}} \cdot \frac{2}{\sqrt{x^2 + 4}} \right) + C
\]

化简第二项：
\[
\frac{1}{16} \cdot \frac{2x}{x^2 + 4} = \frac{x}{8(x^2 + 4)}
\]

因此，最终答案为：
\[
\int \frac{1}{(x^2 + 4)^2} \, dx = \frac{1}{16} \arctan\left(\frac{x}{2}\right) + \frac{x}{8(x^2 + 4)} + C
\]

---

## 📌 本节总结

本节课中，我们一起学习了三角换元法在处理不定积分时的完整流程：

1.  **选择换元**：通过匹配被积函数与三角恒等式（如 \(\tan^2 \theta + 1 = \sec^2 \theta\)）来决定换元形式，并注意调整系数。
2.  **执行积分**：进行换元、简化表达式，并完成纯三角函数的积分计算。
3.  **回代变量**：这是不定积分特有的关键步骤。我们利用初始换元关系构造直角三角形，将 \(\sin \theta, \cos \theta\) 等三角函数值用原始变量 \(x\) 表示，从而得到最终答案。

与定积分不同，不定积分的三角换元法在最后需要多一步“回代”工作，将关于 \(\theta\) 的结果转换回关于 \(x\) 的表达式。掌握这个流程和构造直角三角形的技巧至关重要。