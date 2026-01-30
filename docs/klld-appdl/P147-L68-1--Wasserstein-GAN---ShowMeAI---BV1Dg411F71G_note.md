# 课程 P147：L68.1 - Wasserstein GAN 🧠

在本节课中，我们将要学习Wasserstein GAN（WGAN）的基本概念。我们将从回顾传统GAN及其面临的挑战开始，然后深入探讨Wasserstein距离（又称推土机距离）的数学定义和直观理解，最后介绍如何通过Kantorovich-Rubinstein对偶定理将其转化为一个可计算、可优化的目标函数。

![](img/9171ef7bcd6d287f2cdf09910c236e51_1.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_2.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_3.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_4.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_5.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_6.png)

---

## 从参数化密度到生成模型

![](img/9171ef7bcd6d287f2cdf09910c236e51_8.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_9.png)

上一节我们介绍了常规GAN和最小二乘GAN，它们分别对应不同的分布距离或散度。本节中我们来看看另一种重要的方法——Wasserstein GAN。

![](img/9171ef7bcd6d287f2cdf09910c236e51_10.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_11.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_12.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_13.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_14.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_15.png)

在经典统计学中，如果我们想学习数据的底层分布，一个常见的方法是使用**参数化密度族**。这意味着我们假设密度函数具有已知的数学形式（例如正态分布），并由参数θ控制。

![](img/9171ef7bcd6d287f2cdf09910c236e51_17.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_18.png)

**公式**：`P_θ(x)`

![](img/9171ef7bcd6d287f2cdf09910c236e51_20.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_21.png)

在这种情况下，我们可以直接写出似然函数，并通过**最大似然估计**来找到最优参数θ。具体做法是，取数据，通过我们设定的分布计算其似然值，然后最大化这个似然值或其对数。

**公式**：`max_θ Σ log P_θ(x_i)`

![](img/9171ef7bcd6d287f2cdf09910c236e51_23.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_24.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_25.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_26.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_27.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_28.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_29.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_30.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_31.png)

人们喜欢这种方法，因为只要有了似然函数，问题就会变得非常简单。

从数学上看，如果我们写下KL散度的定义并去掉与参数无关的常数项，那么最大化上述似然目标就等价于最小化真实数据分布`P_r`与参数化分布`P_θ`之间的KL散度。

![](img/9171ef7bcd6d287f2cdf09910c236e51_33.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_34.png)

**公式**：`arg max_θ Σ log P_θ(x_i) = arg min_θ KL(P_r || P_θ)`

![](img/9171ef7bcd6d287f2cdf09910c236e51_35.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_36.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_37.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_38.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_39.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_40.png)

因此，在进行最大似然估计时，我们实际上是在最小化KL散度。但这种方法的前提是，我们能够写出分布`P_θ`的具体形式。

---

![](img/9171ef7bcd6d287f2cdf09910c236e51_42.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_43.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_44.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_45.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_46.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_47.png)

## 生成对抗网络（GAN）的困境

![](img/9171ef7bcd6d287f2cdf09910c236e51_48.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_49.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_50.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_51.png)

对于生成对抗网络，我们没有参数化密度族这种“奢侈”的条件。我们拥有的是：
1.  一个简单的噪声分布（例如标准正态分布`N(0, I)`）。
2.  一个由神经网络参数化的复杂函数`G`（生成器）。

![](img/9171ef7bcd6d287f2cdf09910c236e51_53.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_54.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_55.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_56.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_57.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_58.png)

**过程**：我们从噪声分布中采样一个向量`z`，将其输入生成器`G`，得到生成的样本（如图像）。这样就得到了一个生成分布`P_g`。

**关键问题**：我们无法写出`P_g`的密度函数公式，只能从中采样。`P_g`是一个抽象对象，它存在，但我们无法用公式描述它。

![](img/9171ef7bcd6d287f2cdf09910c236e51_60.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_61.png)

我们的目标是在真实数据分布`P_r`和生成分布`P_g`之间定义一个距离，并最小化它。但`P_g`没有显式表达式，这给直接使用传统距离（如KL散度）带来了困难。

![](img/9171ef7bcd6d287f2cdf09910c236e51_62.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_63.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_64.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_65.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_66.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_67.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_68.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_69.png)

---

![](img/9171ef7bcd6d287f2cdf09910c236e51_71.png)

## 分布距离的多种定义

假设我们的数据空间`X`（例如所有可能图像的集合）是一个紧致度量空间。我们可以在这个空间上定义各种概率分布之间的距离。

以下是几种常见的距离或散度定义：

**1. 全变差距离**
衡量两个分布在所有可测子集上概率差的最大值。
**公式**：`δ(P_r, P_g) = sup_A |P_r(A) - P_g(A)|`

**2. KL散度**
最大似然估计对应的距离。
**公式**：`KL(P_r || P_g) = ∫ P_r(x) log(P_r(x)/P_g(x)) dx`

![](img/9171ef7bcd6d287f2cdf09910c236e51_73.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_74.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_75.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_76.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_77.png)

**3. Jensen-Shannon散度**
原始GAN目标函数对应的散度。
**公式**：`JS(P_r || P_g) = 1/2 KL(P_r || M) + 1/2 KL(P_g || M)， 其中 M = (P_r+P_g)/2`

![](img/9171ef7bcd6d287f2cdf09910c236e51_79.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_80.png)

**4. Pearson χ²散度**
最小二乘GAN对应的散度。

![](img/9171ef7bcd6d287f2cdf09910c236e51_82.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_83.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_84.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_85.png)

**5. 推土机距离 / Wasserstein-1距离**
这是我们本节关注的重点。

---

![](img/9171ef7bcd6d287f2cdf09910c236e51_87.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_88.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_89.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_90.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_91.png)

## 理解Wasserstein距离 🚜

![](img/9171ef7bcd6d287f2cdf09910c236e51_93.png)

Wasserstein距离（又称推土机距离）提供了另一种衡量分布差异的方式。它的直观解释是：将分布`P_r`（看作一堆土）搬运成分布`P_g`（另一堆土）所需的最小“工作量”或成本。

![](img/9171ef7bcd6d287f2cdf09910c236e51_94.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_95.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_97.png)

**成本取决于两点**：
1.  **搬运的质量**：需要移动多少概率质量。
2.  **搬运的距离**：在数据空间`X`中需要移动多远。

其数学定义如下：

![](img/9171ef7bcd6d287f2cdf09910c236e51_99.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_100.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_101.png)

**公式**：`W(P_r, P_g) = inf_{γ ∈ Π(P_r, P_g)} E_{(x,y)~γ} [ ||x - y|| ]`

![](img/9171ef7bcd6d287f2cdf09910c236e51_102.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_103.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_104.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_105.png)

让我们来解析这个公式：
*   `inf`：表示取“下确界”，类似于最小值。
*   `Π(P_r, P_g)`：这是**所有联合分布γ(x, y)的集合**，并且这些联合分布的边缘分布必须分别是`P_r`和`P_g`。也就是说，如果你对γ积分掉`y`，就得到`P_r`；积分掉`x`，就得到`P_g`。
*   `E_{(x,y)~γ} [ ||x - y|| ]`：对于任意一个符合条件的联合分布γ，计算从`x`搬运到`y`的期望距离。

因此，Wasserstein距离就是在所有可能的“搬运方案”（联合分布）中，找到期望搬运成本最小的那个方案的成本。

![](img/9171ef7bcd6d287f2cdf09910c236e51_107.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_108.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_109.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_110.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_111.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_112.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_113.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_114.png)

---

![](img/9171ef7bcd6d287f2cdf09910c236e51_116.png)

## 从定义到实践：Kantorovich-Rubinstein对偶 🔄

![](img/9171ef7bcd6d287f2cdf09910c236e51_117.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_118.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_119.png)

虽然Wasserstein距离的定义很直观，但它同样不实用，原因有二：
1.  我们不知道`P_g`的显式形式。
2.  在所有可能的联合分布`Π(P_r, P_g)`中寻找下确界是极其困难的。

![](img/9171ef7bcd6d287f2cdf09910c236e51_121.png)

幸运的是，数学上的**Kantorovich-Rubinstein对偶定理**为我们提供了一种等价且更易处理的形式：

![](img/9171ef7bcd6d287f2cdf09910c236e51_122.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_123.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_124.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_125.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_126.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_127.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_128.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_129.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_130.png)

**公式**：`W(P_r, P_g) = sup_{||f||_L ≤ 1} [ E_{x~P_r}[f(x)] - E_{x~P_g}[f(x)] ]`

![](img/9171ef7bcd6d287f2cdf09910c236e51_131.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_133.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_134.png)

这个公式的含义发生了转变：
*   `sup`：表示取“上确界”，类似于最大值。
*   `||f||_L ≤ 1`：表示函数`f`是一个**1-Lipschitz连续函数**。简单理解，这类函数的变化不会太剧烈，其斜率（或梯度）的绝对值被限制在1以内。
*   目标变成了：寻找一个Lipschitz函数`f`，使得它对真实样本的期望输出与对生成样本的期望输出之差最大。

![](img/9171ef7bcd6d287f2cdf09910c236e51_135.png)

这个形式与原始GAN的目标非常相似！在原始GAN中，我们有一个判别器`D`来区分真假；在这里，我们有一个**评论家（Critic）** `f`，它不输出概率，而是输出一个分数，并试图最大化这个分数差。

![](img/9171ef7bcd6d287f2cdf09910c236e51_137.png)

---

![](img/9171ef7bcd6d287f2cdf09910c236e51_138.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_139.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_140.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_141.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_142.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_143.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_144.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_145.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_146.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_147.png)

## 用神经网络实现WGAN 🧠➡️🔧

自然地，我们用神经网络来参数化这个评论家函数`f`，记其参数为`w`，即`f_w`。

![](img/9171ef7bcd6d287f2cdf09910c236e51_149.png)

**优化过程变为一个极小极大博弈**：
1.  **评论家（Critic）**：通过优化参数`w`来**最大化** `E_{x~P_r}[f_w(x)] - E_{z~噪声}[f_w(G(z))]`，以更准确地区分真实数据和生成数据。
2.  **生成器（Generator）**：通过优化参数`θ`来**最小化** `-E_{z~噪声}[f_w(G(z))]`，这等价于最小化Wasserstein距离，使生成数据尽可能骗过评论家。

![](img/9171ef7bcd6d287f2cdf09910c236e51_150.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_151.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_152.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_153.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_154.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_155.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_156.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_157.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_158.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_159.png)

**关键技巧：强制执行Lipschitz约束**
为了满足`f_w`是1-Lipschitz函数的要求，WGAN原论文采用了一个简单的启发式方法：**将评论家网络的权重`w`裁剪到一个固定的区间（如[-0.01, 0.01]）**。在训练中，如果权重超出这个范围，就将其截断回区间边界。这可以保证`f_w`是K-Lipschitz的（K为某个常数），虽然不严格是1，但并不影响优化。

![](img/9171ef7bcd6d287f2cdf09910c236e51_160.png)

---

![](img/9171ef7bcd6d287f2cdf09910c236e51_162.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_163.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_164.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_165.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_166.png)

![](img/9171ef7bcd6d287f2cdf09910c236e51_167.png)

## WGAN的优势与意义 ✨

![](img/9171ef7bcd6d287f2cdf09910c236e51_168.png)

与原始GAN相比，WGAN具有以下显著优势：

1.  **训练稳定性**：Wasserstein距离几乎处处可微，为生成器提供了更有意义的梯度。即使真实分布与生成分布没有重叠（此时JS散度是常数），Wasserstein距离仍然能提供有效的梯度，从而缓解了**梯度消失**问题。
2.  **有意义的损失曲线**：在训练过程中，评论家的损失值（即Wasserstein距离的估计值）**与生成样本的质量高度相关**。损失下降通常意味着生成质量提高。这解决了原始GAN中判别器损失波动大、无法指示训练进程的问题。
3.  **模式崩溃缓解**：由于梯度更稳定，WGAN在一定程度上减轻了模式崩溃（生成器只产生少数几种样本）的问题。

WGAN属于更广泛的**积分概率度量**家族。通过选择不同的函数空间来约束评论家`f`，可以得到不同的距离度量，Wasserstein距离是其中一种优秀的选择。

---

## 总结 📚

本节课中我们一起学习了Wasserstein GAN的核心思想。我们从传统基于似然的方法出发，指出了在隐式生成模型中直接计算分布距离的困难。随后，我们深入探讨了Wasserstein距离的直观定义（推土机距离）及其优雅的对偶形式。通过将对偶形式中的函数用权重裁剪的神经网络（评论家）来近似，我们得到了一个可优化、训练稳定且损失指标有意义的生成对抗网络框架——WGAN。这为生成模型提供了一种强大的新工具。