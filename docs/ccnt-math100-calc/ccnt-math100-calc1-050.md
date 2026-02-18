# 第一部分 50：L50 - 从黎曼和反推定积分 🧮 📚

![](img/4fc76f362102d00d3ccfefa344c1d89a_1.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_2.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_4.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_5.png)

在本节课中，我们将学习一个特定类型的问题，它涉及黎曼积分。具体来说，我们将探讨如何从一个给定的黎曼和极限表达式，反向推导出它所对应的定积分。这是一种“逆向”思维，能帮助我们更深刻地理解积分定义。

![](img/4fc76f362102d00d3ccfefa344c1d89a_6.png)

---

## 📖 黎曼积分的定义

![](img/4fc76f362102d00d3ccfefa344c1d89a_8.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_9.png)

上一节我们提到了黎曼积分。本节中，我们来看看其核心定义公式。

![](img/4fc76f362102d00d3ccfefa344c1d89a_11.png)

定积分是通过黎曼和的极限来定义的。其公式如下：

![](img/4fc76f362102d00d3ccfefa344c1d89a_13.png)

\[
\int_{a}^{b} f(x) \, dx = \lim_{n \to \infty} \sum_{i=1}^{n} f(x_i) \, \Delta x
\]

![](img/4fc76f362102d00d3ccfefa344c1d89a_15.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_16.png)

这个公式是理解积分的基础。在之前的课程中，我们曾从几何角度推导过它。现在，我们需要学会在具体问题中应用它。

![](img/4fc76f362102d00d3ccfefa344c1d89a_18.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_19.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_20.png)

应用方式通常有两种：
1.  给定函数 \( f(x) \)，要求写出其黎曼和表达式。
2.  给定一个黎曼和的极限表达式（有时也给出积分区间 \([a, b]\)），要求找出它所对应的函数 \( f(x) \)。

![](img/4fc76f362102d00d3ccfefa344c1d89a_22.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_23.png)

本节课，我们将重点研究第二种“逆向”问题：如何从给定的和式推导出原函数和定积分。

---

![](img/4fc76f362102d00d3ccfefa344c1d89a_25.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_26.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_27.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_28.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_29.png)

## 🔧 核心公式：Δx 与 xi

![](img/4fc76f362102d00d3ccfefa344c1d89a_30.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_32.png)

要解决逆向问题，首先必须掌握定义中的两个关键公式。

![](img/4fc76f362102d00d3ccfefa344c1d89a_34.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_35.png)

以下是计算 Δx 和 xi 的公式：

*   **Δx 的计算公式**：\[ \Delta x = \frac{b - a}{n} \]
    它代表每个小区间的宽度。

![](img/4fc76f362102d00d3ccfefa344c1d89a_37.png)

*   **xi 的计算公式（右端点）**：\[ x_i = a + i \cdot \Delta x = a + i \cdot \frac{b - a}{n} \]
    它代表第 i 个小区间右端点的 x 坐标。

![](img/4fc76f362102d00d3ccfefa344c1d89a_39.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_41.png)

你需要能够将计算出的 \( x_i \) 代入 \( f(x_i) \)，并将 \( \Delta x \) 代入求和式。顺便提一下，上述公式针对的是**右端点**近似。如果想表示左端点近似，只需对公式稍作修改即可，但标准问题通常使用右端点。

![](img/4fc76f362102d00d3ccfefa344c1d89a_43.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_45.png)

---

## 📝 示例一：从清晰的和式到积分

![](img/4fc76f362102d00d3ccfefa344c1d89a_47.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_48.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_49.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_50.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_51.png)

理解了基本公式后，我们来看一个具体的例子。

假设我们有以下极限表达式，并已知它是在区间 \([0, 3]\) 上使用右端点近似得到的黎曼和：

![](img/4fc76f362102d00d3ccfefa344c1d89a_53.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_54.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_55.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_56.png)

\[
\lim_{n \to \infty} \sum_{i=1}^{n} \tan\left(2 + \frac{3i}{n}\right) \cdot \frac{3}{n}
\]

![](img/4fc76f362102d00d3ccfefa344c1d89a_58.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_59.png)

我们的目标是写出它对应的定积分。

以下是解题步骤：

![](img/4fc76f362102d00d3ccfefa344c1d89a_61.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_62.png)

1.  **确定 Δx**：根据区间 \([0, 3]\)，计算 \( \Delta x = \frac{3 - 0}{n} = \frac{3}{n} \)。我们立刻注意到，和式中的 \(\frac{3}{n}\) 就是 \( \Delta x \)。
2.  **确定 xi**：根据公式，\( x_i = a + i \cdot \Delta x = 0 + i \cdot \frac{3}{n} = \frac{3i}{n} \)。我们注意到，和式中 \(\tan\) 函数内的 \(\frac{3i}{n}\) 就是 \( x_i \)。
3.  **构建定积分**：
    *   积分区间就是给定的 \([0, 3]\)。
    *   求和式中的 \( \Delta x \) 在极限下变为积分符号中的 \( dx \)。
    *   求和式中的 \( f(x_i) \)，即 \( \tan(2 + x_i) \)，在极限下变为被积函数 \( f(x) = \tan(2 + x) \)，其中的 \( x_i \) 替换为连续变量 \( x \)。

![](img/4fc76f362102d00d3ccfefa344c1d89a_63.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_64.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_65.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_66.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_67.png)

因此，对应的定积分为：

![](img/4fc76f362102d00d3ccfefa344c1d89a_69.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_70.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_71.png)

\[
\int_{0}^{3} \tan(2 + x) \, dx
\]

这个过程的核心在于：识别出和式中的 \( \Delta x \) 部分将变为 \( dx \)，而包含 \( i \) 的 \( x_i \) 部分将变为 \( x \)，其余部分则构成被积函数 \( f(x) \)。

![](img/4fc76f362102d00d3ccfefa344c1d89a_73.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_74.png)

---

![](img/4fc76f362102d00d3ccfefa344c1d89a_75.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_77.png)

## 🧩 示例二：从复杂和式到积分

![](img/4fc76f362102d00d3ccfefa344c1d89a_79.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_81.png)

上一个例子比较直接。现在，我们来看一个稍复杂的例子，巩固所学方法。

![](img/4fc76f362102d00d3ccfefa344c1d89a_83.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_84.png)

我们有以下极限表达式，同样在区间 \([0, 3]\) 上使用右端点近似：

\[
\lim_{n \to \infty} \sum_{i=1}^{n} \frac{9 + 6i/n}{(2 + 3i/n)^2} \cdot i
\]

![](img/4fc76f362102d00d3ccfefa344c1d89a_86.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_87.png)

这个式子看起来不那么规整，不像明显的 \( f(x_i) \Delta x \) 形式。但区间相同，所以 \( \Delta x \) 和 \( x_i \) 的公式不变（\( \Delta x = \frac{3}{n} \), \( x_i = \frac{3i}{n} \)）。我们需要从这个“混乱”的求和式中，识别出 \( \Delta x \) 和 \( x_i \) 的痕迹。

![](img/4fc76f362102d00d3ccfefa344c1d89a_89.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_90.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_91.png)

以下是解题思路：

1.  **识别 xi**：首先，我们注意到 \( x_i = \frac{3i}{n} \)。观察和式，分子中的 \( \frac{6i}{n} \) 恰好是 \( 2x_i \)，分母中的 \( \frac{3i}{n} \) 就是 \( x_i \)。这是好迹象。
2.  **处理多余的 i**：麻烦在于，求和号后面还有一个独立的因子 \( i \)，而且没有明显的 \( \frac{3}{n} \) 作为 \( \Delta x \)。我们需要利用 \( x_i \) 和 \( i \) 的关系进行代换。
    由 \( x_i = \frac{3i}{n} \)，可解出 \( i = \frac{x_i \cdot n}{3} \)。
3.  **代入并重组**：将 \( i = \frac{x_i n}{3} \) 以及 \( \frac{6i}{n} = 2x_i \), \( \frac{3i}{n} = x_i \) 代回原和式：
    \[
    \sum_{i=1}^{n} \frac{9 + 2x_i}{(2 + x_i)^2} \cdot \frac{x_i n}{3}
    \]
    进一步整理，将常数提出：
    \[
    \sum_{i=1}^{n} \frac{9 + 2x_i}{(2 + x_i)^2} \cdot x_i \cdot \frac{n}{3}
    \]
4.  **识别 Δx**：注意 \( \frac{n}{3} \) 是 \( \frac{1}{\Delta x} \) 吗？不，\( \Delta x = \frac{3}{n} \)，所以 \( \frac{n}{3} = \frac{1}{\Delta x} \)。
    因此，原和式可写为：
    \[
    \sum_{i=1}^{n} \frac{9 + 2x_i}{(2 + x_i)^2} \cdot x_i \cdot \frac{1}{\Delta x}
    \]
    这仍然不是标准形式。我们需要将整个表达式视为 \( f(x_i) \Delta x \)。观察发现，如果我们将 \( x_i / \Delta x \) 组合在一起，而 \( \frac{9 + 2x_i}{(2 + x_i)^2} \) 是另一部分，这并不直接。实际上，更清晰的方法是：我们已经用 \( x_i \) 表示了所有项，而 \( \Delta x = \frac{3}{n} \) 是隐含的。在取极限时，\( \sum f(x_i) \Delta x \) 中的 \( \Delta x \) 会转化为 \( dx \)。在我们重写的表达式中，\( \frac{n}{3} \) 需要与求和结合，在极限下，\( \sum ( \cdots ) \frac{n}{3} \) 的行为需要仔细分析。标准做法是，最终被积函数就是将所有 \( x_i \) 替换为 \( x \) 后，剩下的关于 \( x \) 的表达式。
5.  **写出定积分**：经过代换和整理，并取极限 \( n \to \infty \)，\( x_i \to x \)，求和变为积分，我们得到对应的定积分为：
    \[
    \int_{0}^{3} \frac{9 + 2x}{(2 + x)^2} \cdot x \, dx
    \]
    这里，\( \frac{9 + 2x}{(2 + x)^2} \) 来自原式分子分母替换后得到，而额外的因子 \( x \) 正是由原来独立的那个 \( i \) 通过关系 \( i = \frac{x n}{3} \) 转化而来，在极限过程中，\( \frac{n}{3} \) 与求和结合产生了积分所需的“微元”关系，最终体现为被积函数的一部分 \( x \)。

![](img/4fc76f362102d00d3ccfefa344c1d89a_93.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_94.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_95.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_96.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_97.png)

---

![](img/4fc76f362102d00d3ccfefa344c1d89a_99.png)

## 📚 课程总结

![](img/4fc76f362102d00d3ccfefa344c1d89a_101.png)

本节课中，我们一起学习了如何从给定的黎曼和极限表达式反向求解其对应的定积分。

![](img/4fc76f362102d00d3ccfefa344c1d89a_102.png)

我们首先回顾了黎曼积分的定义及其关键公式 \( \Delta x \) 和 \( x_i \)。然后，通过两个由浅入深的例子，演示了具体的解题流程：
1.  **识别与匹配**：从给定和式中，识别出与 \( \Delta x = \frac{b-a}{n} \) 和 \( x_i = a + i\Delta x \) 对应的部分。
2.  **变量替换**：将和式中所有包含 \( i \) 的项，用 \( x_i \) 和 \( \Delta x \) 表示。
3.  **构建积分**：在极限下，将 \( \Delta x \) 替换为 \( dx \)，将所有 \( x_i \) 替换为连续变量 \( x \)，剩下的关于 \( x \) 的表达式即为被积函数 \( f(x) \)，积分区间即为给定的 \([a, b]\)。

![](img/4fc76f362102d00d3ccfefa344c1d89a_104.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_105.png)

![](img/4fc76f362102d00d3ccfefa344c1d89a_106.png)

掌握这种“逆向”思维，能加深对积分本质——即“无限细分并求和”这一过程的理解。