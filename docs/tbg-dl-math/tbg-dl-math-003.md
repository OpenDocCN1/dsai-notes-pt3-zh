# 003：矩阵与向量的加法与乘法 📊

![](img/6ba8c968c7eb820e4c14d12daf792bf0_0.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_2.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_4.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_6.png)

在本节课中，我们将学习如何对矩阵和向量进行加法与乘法运算。这些运算是线性代数的基础，也是理解深度学习模型内部计算的关键。

## 矩阵与向量的加法 ➕

上一节我们介绍了矩阵和向量的基本概念，本节中我们来看看如何对它们进行加法运算。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_8.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_9.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_11.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_12.png)

矩阵或向量的加法与减法是通过逐元素相加或相减来完成的。对于向量，其运算公式为：
\[
c_i = a_i + b_i
\]
其中 \( i \) 是向量中元素的索引。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_14.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_15.png)

对于矩阵，其运算公式为：
\[
C_{ij} = A_{ij} + B_{ij}
\]
其中 \( i \) 和 \( j \) 分别是矩阵的行索引和列索引。

以下是向量加法的数字示例：
假设有列向量 \( \mathbf{a} = \begin{bmatrix} 1 \\ 3 \end{bmatrix} \) 和 \( \mathbf{b} = \begin{bmatrix} 4 \\ 2 \end{bmatrix} \)，它们的和为：
\[
\mathbf{a} + \mathbf{b} = \begin{bmatrix} 1+4 \\ 3+2 \end{bmatrix} = \begin{bmatrix} 5 \\ 5 \end{bmatrix}
\]

以下是矩阵加法的数字示例：
假设有矩阵 \( A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} \) 和 \( B = \begin{bmatrix} 4 & 3 \\ 2 & 1 \end{bmatrix} \)，它们的和为：
\[
A + B = \begin{bmatrix} 1+4 & 2+3 \\ 3+2 & 4+1 \end{bmatrix} = \begin{bmatrix} 5 & 5 \\ 5 & 5 \end{bmatrix}
\]

![](img/6ba8c968c7eb820e4c14d12daf792bf0_17.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_19.png)

**注意**：要进行加法或减法运算，向量或矩阵必须具有相同的形状。例如，一个 2x3 的矩阵不能与一个 3x2 的矩阵相加。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_21.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_23.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_25.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_27.png)

## 标量与矩阵的运算 🔢

![](img/6ba8c968c7eb820e4c14d12daf792bf0_29.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_31.png)

我们也可以将一个标量与矩阵相加，或者用一个标量乘以矩阵。这在数学上是明确定义的。

例如，如果我们有一个矩阵 \( B \)，我们可以用标量 \( a \) 乘以它，然后用标量 \( c \) 加上它，得到结果矩阵 \( D \)：
\[
D = a \cdot B + c
\]
这相当于对 \( B \) 中的每个元素 \( B_{ij} \) 执行以下操作：
\[
D_{ij} = a \cdot B_{ij} + c
\]

## 广播机制 📡

![](img/6ba8c968c7eb820e4c14d12daf792bf0_33.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_34.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_36.png)

在深度学习中，我们有时也允许矩阵和向量相加。这仅在矩阵在其中一个维度上与向量具有相同形状（相同的行数或列数）时才可行。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_38.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_40.png)

这个过程称为**广播**。其原理是将向量复制，以匹配矩阵的维度。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_42.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_44.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_46.png)

假设我们有一个列向量 \( \mathbf{b} \)，我们想将其加到矩阵 \( A \) 上以得到矩阵 \( C \)。我们将向量 \( \mathbf{b} \) 复制到矩阵 \( A \) 的所有列上，然后逐列相加。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_48.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_49.png)

用元素方式可以写为：
\[
C_{ij} = A_{ij} + b_i
\]
注意，\( b \) 的索引只有 \( i \)，没有 \( j \)，因为它是列向量。这意味着对于所有列索引 \( j \)，我们都加上相同的 \( b_i \)。

以下是广播的示例：
*   **列向量广播**：向量 \( \begin{bmatrix} 1 \\ 3 \end{bmatrix} \) 被加到矩阵 \( \begin{bmatrix} 1 & 2 \\ 0 & 1 \end{bmatrix} \) 的每一列，结果为 \( \begin{bmatrix} 2 & 3 \\ 3 & 4 \end{bmatrix} \)。
*   **行向量广播**：行向量 \( \begin{bmatrix} 1 & 3 \end{bmatrix} \) 被加到矩阵 \( \begin{bmatrix} 2 & 0 \\ 2 & 0 \end{bmatrix} \) 的每一行，结果为 \( \begin{bmatrix} 3 & 3 \\ 3 & 3 \end{bmatrix} \)。

如果你使用 Python 的 NumPy 库，你会发现它原生支持这种广播机制，深度学习框架也广泛使用它。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_51.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_52.png)

## 矩阵与向量的乘法 ✖️

![](img/6ba8c968c7eb820e4c14d12daf792bf0_54.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_55.png)

现在让我们进入乘法运算。两个矩阵 \( A \) 和 \( B \) 可以相乘，当且仅当 \( A \) 的列数等于 \( B \) 的行数。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_57.png)

换句话说，如果 \( A \in \mathbb{R}^{m \times n} \)，\( B \in \mathbb{R}^{n \times l} \)，那么它们的乘积 \( C = AB \) 是一个 \( m \times l \) 的矩阵。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_59.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_61.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_63.png)

矩阵乘积的元素定义如下：
\[
C_{ij} = \sum_{k=1}^{n} A_{ik} \cdot B_{kj}
\]
我们取矩阵 \( A \) 的第 \( i \) 行和矩阵 \( B \) 的第 \( j \) 列，将对应元素相乘后求和。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_65.png)

**注意**：矩阵乘积**不是**逐元素相乘。逐元素相乘被称为**哈达玛积**，用符号 \( A \odot B \) 表示，但要求 \( A \) 和 \( B \) 形状完全相同。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_67.png)

以下是矩阵乘积的示例：
\[
\begin{bmatrix} 3 & 1 \\ 2 & 1 \end{bmatrix} \times \begin{bmatrix} 1 & 2 \\ 3 & 1 \end{bmatrix} = \begin{bmatrix} (3*1+1*3) & (3*2+1*1) \\ (2*1+1*3) & (2*2+1*1) \end{bmatrix} = \begin{bmatrix} 6 & 7 \\ 5 & 5 \end{bmatrix}
\]

![](img/6ba8c968c7eb820e4c14d12daf792bf0_69.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_71.png)

## 向量的内积与外积

![](img/6ba8c968c7eb820e4c14d12daf792bf0_73.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_75.png)

向量本质上是维度为1的矩阵，因此也有两种乘法方式。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_77.png)

**内积（点积）**：两个向量的内积得到一个标量。
假设有列向量 \( \mathbf{x} = \begin{bmatrix} 3 \\ 2 \end{bmatrix} \) 和 \( \mathbf{y} = \begin{bmatrix} 1 \\ 3 \end{bmatrix} \)，将 \( \mathbf{x} \) 转置为行向量后相乘：
\[
\mathbf{x}^T \mathbf{y} = \begin{bmatrix} 3 & 2 \end{bmatrix} \begin{bmatrix} 1 \\ 3 \end{bmatrix} = 3*1 + 2*3 = 9
\]

**外积**：两个向量的外积得到一个矩阵（秩为1的矩阵）。
使用相同的向量，但转置 \( \mathbf{y} \)：
\[
\mathbf{x} \mathbf{y}^T = \begin{bmatrix} 3 \\ 2 \end{bmatrix} \begin{bmatrix} 1 & 3 \end{bmatrix} = \begin{bmatrix} 3*1 & 3*3 \\ 2*1 & 2*3 \end{bmatrix} = \begin{bmatrix} 3 & 9 \\ 2 & 6 \end{bmatrix}
\]

![](img/6ba8c968c7eb820e4c14d12daf792bf0_79.png)

有趣的是，我们可以用外积来显式地定义之前的广播操作。例如，将向量 \( \begin{bmatrix} 1 \\ 3 \end{bmatrix} \) 广播到 2x2 矩阵，可以看作是该向量与全1向量 \( \begin{bmatrix} 1 \\ 1 \end{bmatrix} \) 的外积，生成一个复制后的矩阵，然后再与目标矩阵相加。

## 矩阵运算的性质 📝

![](img/6ba8c968c7eb820e4c14d12daf792bf0_81.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_82.png)

了解矩阵运算的一些基本性质非常重要：

![](img/6ba8c968c7eb820e4c14d12daf792bf0_84.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_86.png)

1.  **分配律**：\( A(B + C) = AB + AC \)
2.  **结合律**：\( A(BC) = (AB)C \)
3.  **非交换律**：一般情况下，\( AB \neq BA \)。这从维度要求上就可以看出。
4.  **转置的性质**：\( (AB)^T = B^T A^T \)
5.  **向量点积的交换律**：虽然矩阵乘法不满足交换律，但向量的点积是满足的，即 \( \mathbf{x}^T \mathbf{y} = \mathbf{y}^T \mathbf{x} \)。这可以通过上述转置性质推导出来。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_88.png)

## 矩阵向量积与线性方程组

![](img/6ba8c968c7eb820e4c14d12daf792bf0_90.png)

矩阵向量积允许我们紧凑地表示线性方程组，这在最小二乘法等问题中经常遇到。

假设我们有一系列线性方程：\( \mathbf{a}_1^T \mathbf{x} = b_1, \mathbf{a}_2^T \mathbf{x} = b_2, ..., \mathbf{a}_m^T \mathbf{x} = b_m \)。
我们可以将其写成一个紧凑的矩阵向量乘积形式：
\[
A\mathbf{x} = \mathbf{b}
\]
其中，矩阵 \( A \) 的每一行 \( A_i \) 就是方程中的行向量 \( \mathbf{a}_i^T \)，\( \mathbf{b} \) 是由所有 \( b_i \) 组成的列向量。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_92.png)

---

![](img/6ba8c968c7eb820e4c14d12daf792bf0_94.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_96.png)

本节课中我们一起学习了矩阵与向量的基本运算：加法和乘法。我们掌握了逐元素相加、标量运算、广播机制，以及关键的矩阵乘法规则和性质。理解这些运算是后续学习更复杂的线性代数概念和深度学习模型的基础。