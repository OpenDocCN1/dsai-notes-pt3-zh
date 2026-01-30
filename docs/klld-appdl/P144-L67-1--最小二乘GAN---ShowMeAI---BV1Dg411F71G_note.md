# 🎓 课程 P144：L67.1 - 最小二乘GAN (LSGAN)

在本节课中，我们将学习一种生成对抗网络（GAN）的变体——最小二乘GAN。我们将回顾标准GAN的目标函数，理解其背后的数学原理，然后探讨如何通过改变损失函数来改进GAN的训练过程，特别是解决模式崩溃问题。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_1.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_2.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_3.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_4.png)

---

上一节我们介绍了一篇关于图像掩码预测的论文，其思想与BERT在语言领域的应用类似。本节中，我们来看看另一种生成对抗网络——最小二乘GAN。生成对抗网络的许多贡献都发生在损失函数层面，改变损失函数可能会带来更好的训练行为。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_6.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_7.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_8.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_9.png)

## 🔍 GAN 快速回顾

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_10.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_11.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_12.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_13.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_14.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_15.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_16.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_17.png)

首先，我们快速回顾一下标准GAN。GAN的目标函数如下：

**公式：**
```
min_G max_D V(D, G) = E_{x~p_data(x)}[log D(x)] + E_{z~p_z(z)}[log(1 - D(G(z)))]
```

其中，判别器D试图区分真实数据和生成数据，而生成器G则试图生成足以混淆判别器的“真实”图像。我们知道，固定G并最大化此目标函数，可以得到最优判别器D*。将D*代入目标函数后，经过数学推导，最终会得到真实数据分布 `p_data` 与生成数据分布 `p_g` 之间的**詹森-香农散度**。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_19.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_20.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_21.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_22.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_23.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_24.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_25.png)

**公式：**
```
C(G) = 2 * JSD(p_data || p_g) - 2log2
```

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_26.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_27.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_28.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_29.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_30.png)

詹森-香农散度总是大于或等于0，当且仅当 `p_data = p_g` 时为零。这表明，生成器和判别器之间的博弈背后，实质是在最小化两个分布之间的距离。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_32.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_33.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_34.png)

## 🧮 什么是最小二乘GAN？

最小二乘GAN的核心思想是改变损失函数，使用最小二乘损失代替对数损失。其判别器的目标是最小化以下函数：

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_36.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_37.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_38.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_39.png)

**公式：**
```
min_D V_{LSGAN}(D) = 0.5 * E_{x~p_data(x)}[(D(x) - b)^2] + 0.5 * E_{z~p_z(z)}[(D(G(z)) - a)^2]
```

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_40.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_41.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_42.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_43.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_44.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_45.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_46.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_47.png)

同时，生成器的目标是最小化：

**公式：**
```
min_G V_{LSGAN}(G) = 0.5 * E_{z~p_z(z)}[(D(G(z)) - c)^2]
```

在这里，`a`, `b`, `c` 是设定的标签值。`a` 是假数据的标签，`b` 是真数据的标签，`c` 是生成器希望判别器为假数据赋予的值。为了使生成样本看起来尽可能真实，我们通常希望 `c` 接近 `b`。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_49.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_50.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_51.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_52.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_53.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_54.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_55.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_56.png)

以下是关于标签值设定的常见选择：

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_57.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_58.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_59.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_60.png)

*   **选择一（理论推导常用）：** 设定 `a = 0`, `b = c = 1`。这意味着我们希望判别器对真实数据输出1，对生成数据输出0，而生成器则努力让判别器对生成数据也输出1。
*   **选择二（满足特定性质）：** 设定 `b - c = 1` 且 `b - a = 2`。例如，`a = -1`, `b = 1`, `c = 0`。这种设定在理论推导中能引出特定的散度形式。

与标准GAN不同，这里的判别器 `D(x)` 不再输出一个概率值（0到1之间），而是输出一个任意实数（分数）。因此，判别器网络的最后一层通常不再使用Sigmoid激活函数。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_62.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_63.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_64.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_65.png)

## 📐 LSGAN 背后的数学

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_66.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_67.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_68.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_69.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_70.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_71.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_72.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_73.png)

与标准GAN类似，我们可以为LSGAN求解最优判别器 `D*`。固定生成器G，对判别器目标函数求导并令其为零，可以得到：

**公式：**
```
D*(x) = (b * p_data(x) + a * p_g(x)) / (p_data(x) + p_g(x))
```

这个形式与我们讨论标签平滑时出现的形式相似。将 `D*` 代入生成器的目标函数，经过一系列代数运算（具体证明可参考原论文），我们可以得到生成器最终要最小化的目标。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_75.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_76.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_77.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_78.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_79.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_80.png)

当满足 `b - c = 1` 且 `b - a = 2` 的条件时，该目标等价于最小化 **皮尔逊 χ² 散度**：

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_81.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_82.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_83.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_84.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_85.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_86.png)

**公式：**
```
C(G) = 0.5 * χ²_Pearson (p_data + p_g || 2 * p_g)
```

这也是一种衡量两个分布之间距离的方法。当 `p_g = p_data` 时，该散度为零。这表明，通过改变损失函数，我们实际上是在最小化另一种分布距离（而非詹森-香农散度）。这解释了为什么LSGAN可能具有不同的训练特性。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_88.png)

## 💡 为什么使用LSGAN？—— 实践意义

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_89.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_90.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_91.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_92.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_93.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_94.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_95.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_96.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_97.png)

LSGAN的提出主要有以下实践优势：

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_98.png)

1.  **缓解梯度消失问题：** 在标准GAN中，如果判别器训练得太好，对生成样本的梯度会趋近于零，导致生成器无法继续学习。LSGAN使用最小二乘损失，即使判别器能很好地区分，梯度也不会饱和，从而为生成器提供了更稳定的梯度信号。
2.  **可能改善模式崩溃：** 标准GAN训练中常见的“模式崩溃”问题，即生成器只生成多样性极低的少数几种样本。理论分析和实验表明，LSGAN有助于缓解这一问题。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_100.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_101.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_102.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_103.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_104.png)

以下是一个模式崩溃的简单示例图示：

> 假设目标分布是多模态的（多个高峰）。标准GAN（右列）在训练过程中，生成分布可能会依次“跳变”到不同的模式上，而不是同时覆盖所有模式，这就是模式崩溃。而LSGAN（左列）则能更稳定地逐渐逼近整个目标分布。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_106.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_107.png)

在实践中，对于某些数据集，标准GAN可能收敛良好；而对于另一些数据集，则可能需要尝试LSGAN等变体来获得更好的训练效果。并没有绝对的定论哪一种在所有情况下都更好。

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_108.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_109.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_110.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_111.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_112.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_113.png)

![](img/2eae3d885e20ff9a250ebd4b3d86fd5f_114.png)

## 🖼️ 实验结果与评估

LSGAN的网络结构（如生成器和判别器）可以与DCGAN等标准结构相同，仅改变损失函数。

从定性结果看，在LSUN卧室数据集上，LSGAN生成的图像在纹理细节上可能略优于DCGAN。然而，定性比较是主观的。

为了定量评估，我们引入**初始分数**。该分数通过将生成图像输入一个预训练的分类器（如Inception网络）来计算。它同时衡量生成图像的**清晰度**（属于某个类别的置信度高）和**多样性**（覆盖多个类别），分数越高越好。实验表明，LSGAN通常能获得比标准GAN更高的初始分数，这为其性能提供了客观依据。

## ✅ 总结

本节课我们一起学习了最小二乘GAN。

*   我们首先回顾了标准GAN的目标函数及其与詹森-香农散度的关联。
*   接着，我们介绍了LSGAN的损失函数形式，它用最小二乘损失替代了对数损失，并且判别器输出实数分数而非概率。
*   从数学角度看，优化LSGAN最终是在最小化真实分布与生成分布之间的皮尔逊χ²散度（在特定标签设定下）。
*   其实践意义在于能提供更稳定的梯度，有助于缓解梯度消失和模式崩溃问题。
*   最后，我们通过定性图像对比和定量的初始分数，了解了LSGAN的评估方式及其潜在优势。

LSGAN是GAN家族中通过修改损失函数来改善训练稳定性和结果质量的一个重要变体，为处理复杂数据分布提供了另一种有效的工具。