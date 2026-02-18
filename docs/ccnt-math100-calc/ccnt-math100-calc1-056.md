# 第一部分 56：当换元法不完美匹配时，如何进行回代？ 🔄 📚

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_1.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_2.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_3.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_4.png)

在本节课中，我们将学习一种特殊的积分技巧——回代法。当我们使用换元积分法时，有时会发现设定了 `u` 之后，被积函数中仍有无法直接用 `du` 表示的 `x` 项。这时，我们需要通过代数变换，将这些 `x` 项也用 `u` 表示出来，从而完成积分。

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_6.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_7.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_8.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_10.png)

---

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_11.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_13.png)

## 🧩 示例一：处理多余的 `x` 项

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_15.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_16.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_17.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_18.png)

首先，我们来看第一个积分：

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_20.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_21.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_22.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_24.png)

\[
\int x (1 - x)^{3/2} \, dx
\]

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_26.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_27.png)

观察这个积分，很自然地会想到令 `u` 等于内部函数 `1 - x`。

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_29.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_30.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_31.png)

**核心步骤：**

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_33.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_35.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_37.png)

1.  **设定换元**：
    \[
    u = 1 - x
    \]
    那么，微分 `du` 为：
    \[
    du = -dx
    \]

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_39.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_40.png)

2.  **识别问题**：
    将 `dx` 替换为 `-du` 后，积分变为：
    \[
    \int x \cdot u^{3/2} \cdot (-du)
    \]
    这里出现了一个问题：被积函数中还有一个 `x` 无法直接用 `du` 表示。

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_41.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_42.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_44.png)

3.  **回代求解**：
    为了解决这个问题，我们从 `u = 1 - x` 反解出 `x`：
    \[
    x = 1 - u
    \]
    现在，我们可以用 `(1 - u)` 替换掉积分中的 `x`：
    \[
    \int (1 - u) \cdot u^{3/2} \cdot (-du) = -\int (1 - u) u^{3/2} \, du
    \]

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_45.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_46.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_48.png)

4.  **展开并积分**：
    将积分展开：
    \[
    -\int (u^{3/2} - u^{5/2}) \, du = -\int u^{3/2} \, du + \int u^{5/2} \, du
    \]
    应用幂函数积分公式：
    \[
    \int u^n \, du = \frac{u^{n+1}}{n+1} + C
    \]
    计算得到：
    \[
    -\frac{2}{5} u^{5/2} + \frac{2}{7} u^{7/2} + C
    \]

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_50.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_51.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_52.png)

5.  **将 `u` 代回 `x`**：
    最后，将 `u = 1 - x` 代回结果中，得到最终答案：
    \[
    -\frac{2}{5} (1 - x)^{5/2} + \frac{2}{7} (1 - x)^{7/2} + C
    \]

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_54.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_55.png)

---

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_56.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_57.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_58.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_60.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_61.png)

## 🔄 过渡到第二个例子

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_63.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_64.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_65.png)

在上一个例子中，我们通过将多余的 `x` 项用 `u` 表示（即 `x = 1 - u`）解决了问题。这种方法被称为“回代”。接下来，我们看一个分母换元的例子，它同样需要回代技巧。

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_67.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_68.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_69.png)

---

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_71.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_72.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_74.png)

## 🧩 示例二：分母换元与回代

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_76.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_77.png)

现在，我们来看第二个积分：

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_78.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_80.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_81.png)

\[
\int \frac{x^2 + 4}{x + 2} \, dx
\]

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_83.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_84.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_85.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_86.png)

这个积分的形式提示我们，可以尝试令 `u` 等于分母。

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_88.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_89.png)

**核心步骤：**

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_91.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_92.png)

1.  **设定换元**：
    \[
    u = x + 2
    \]
    那么，微分 `du` 为：
    \[
    du = dx
    \]

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_94.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_95.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_96.png)

2.  **识别问题**：
    将 `dx` 替换为 `du` 后，积分变为：
    \[
    \int \frac{x^2 + 4}{u} \, du
    \]
    这里，分子 `x^2 + 4` 仍然包含 `x`，无法直接用 `u` 表示。

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_98.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_99.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_100.png)

3.  **回代求解**：
    从 `u = x + 2` 反解出 `x`：
    \[
    x = u - 2
    \]
    我们需要将分子 `x^2 + 4` 用 `u` 表示：
    \[
    x^2 + 4 = (u - 2)^2 + 4 = u^2 - 4u + 4 + 4 = u^2 - 4u + 8
    \]
    （注：此处原文计算有误，应为 `u^2 - 4u + 8`，但后续步骤基于 `u^2 - 4u` 进行，这里我们按原文逻辑继续，但请注意正确的分子应为 `u^2 - 4u + 8`，这将导致不同的最终结果。为忠实于原文，我们沿用其计算过程。）

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_102.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_103.png)

4.  **代入并化简积分**：
    将用 `u` 表示的分子代回积分：
    \[
    \int \frac{u^2 - 4u}{u} \, du = \int (u - 4) \, du
    \]

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_105.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_106.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_107.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_108.png)

5.  **积分计算**：
    对多项式进行积分：
    \[
    \int (u - 4) \, du = \frac{1}{2}u^2 - 4u + C
    \]

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_109.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_111.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_112.png)

6.  **将 `u` 代回 `x`**：
    最后，将 `u = x + 2` 代回结果中，得到最终答案：
    \[
    \frac{1}{2}(x + 2)^2 - 4(x + 2) + C
    \]
    可以展开，但当前形式已足够。

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_114.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_115.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_116.png)

---

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_117.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_118.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_120.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_121.png)

## 📝 本节课总结

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_122.png)

在本节课中，我们一起学习了换元积分法中的“回代”技巧。

*   当设定 `u = g(x)` 后，如果被积函数中仍有无法用 `du` 直接消去的 `x` 项，我们可以从 `u = g(x)` 反解出 `x = h(u)`。
*   然后将这些 `x` 项用 `u` 表示，从而将整个被积函数转化为关于 `u` 的表达式。
*   完成关于 `u` 的积分后，切记最后一步是将结果中的 `u` 再代换回关于 `x` 的表达式。

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_124.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_125.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_126.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_127.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_128.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_129.png)

![](img/58bc13fbc03b029ced95aa9ae57bbe3f_130.png)

这种方法扩展了换元法的应用范围，使我们能够处理更多形式的不定积分问题。关键在于灵活运用代数关系，在 `x` 和 `u` 之间进行转换。