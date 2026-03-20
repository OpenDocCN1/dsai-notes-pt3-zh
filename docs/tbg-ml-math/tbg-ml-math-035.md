# 035：序列与收敛 🧮

![](img/fa8f674d4613cf1e7bed69abe7769f6d_0.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_2.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_4.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_6.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_7.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_8.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_10.png)

在本节课中，我们将开始学习微积分，这是机器学习中至关重要的数学工具。我们将从一维空间开始，回顾其核心直觉，并探讨如何在多维空间中应用导数和积分。微积分对于理解梯度下降等优化算法以及概率方法中的积分计算至关重要。为了定义导数和积分，我们首先需要理解序列及其极限的概念。

![](img/fa8f674d4613cf1e7bed69abe7769f6d_12.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_13.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_14.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_15.png)

## 序列的定义

![](img/fa8f674d4613cf1e7bed69abe7769f6d_17.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_19.png)

上一节我们介绍了微积分的重要性，本节中我们来看看序列这一基础概念。

![](img/fa8f674d4613cf1e7bed69abe7769f6d_21.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_22.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_24.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_25.png)

我们考虑一个序列 `(x_n)_{n \in \mathbb{N}}`，它是实数集 `\mathbb{R}^d` 的一个子集。

![](img/fa8f674d4613cf1e7bed69abe7769f6d_27.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_28.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_29.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_31.png)

> **备注**：在后续内容中，我们通常会将序列简写为 `(x_n)`，并默认 `n` 属于自然数集 `\mathbb{N}`。这始终表示一个数字序列。序列中的元素存在于 `\mathbb{R}^d` 空间中，而序列本身是 `\mathbb{R}^d` 的一个子集，这就是为什么使用子集符号 `\subset` 而非元素符号 `\in`。

![](img/fa8f674d4613cf1e7bed69abe7769f6d_33.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_35.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_36.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_37.png)

我们考虑这样一个序列，并给出以下定义。

![](img/fa8f674d4613cf1e7bed69abe7769f6d_39.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_40.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_42.png)

![](img/fa8f674d4613cf1e7bed69abe7769f6d_44.png)

这样的序列被称为一个**序列**。