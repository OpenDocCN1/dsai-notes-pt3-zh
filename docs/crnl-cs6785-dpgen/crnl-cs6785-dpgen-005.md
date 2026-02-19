# 5：隐变量模型 🧠

![](img/e51bd05be4909e30eb0d7e777afa7dd1_1.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_2.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_3.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_4.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_5.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_7.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_8.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_10.png)

在本节课中，我们将要学习一种新的生成模型家族——隐变量模型。我们将重点介绍一种非常重要的模型：变分自编码器。我们将从回顾之前的内容开始，然后深入探讨隐变量模型的概念、动机以及如何学习它们。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_12.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_13.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_15.png)

## 回顾：生成建模与自回归模型

上一节我们介绍了生成建模的基本任务，即从数据中学习一个概率分布模型。我们之前主要关注的是自回归模型。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_17.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_18.png)

自回归模型的核心思想是，对于一个高维向量 **x**（如图像），其联合概率分布可以分解为一系列条件概率的乘积：

![](img/e51bd05be4909e30eb0d7e777afa7dd1_20.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_22.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_23.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_25.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_27.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_29.png)

**P(x) = ∏ P(x_i | x_<i)**

![](img/e51bd05be4909e30eb0d7e777afa7dd1_31.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_33.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_34.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_36.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_38.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_40.png)

其中，每个条件概率 **P(x_i | x_<i)** 由一个神经网络参数化。这种模型非常适合进行密度估计和序列生成。然而，它也存在一些局限性：

![](img/e51bd05be4909e30eb0d7e777afa7dd1_42.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_44.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_45.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_46.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_47.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_49.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_50.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_51.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_52.png)

*   **采样速度慢**：由于需要逐个像素或单词地顺序生成，对于高维数据（如高清音频）来说非常耗时。
*   **难以进行表示学习**：自回归模型主要专注于生成和密度估计，并不自然地提供关于数据内部结构（如潜在因素或聚类）的新见解。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_54.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_56.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_57.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_59.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_61.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_63.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_64.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_66.png)

为了克服这些限制，特别是为了进行表示学习，本节我们将引入一种新的生成模型。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_68.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_70.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_72.png)

## 引入隐变量模型 🎯

![](img/e51bd05be4909e30eb0d7e777afa7dd1_74.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_76.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_77.png)

本节中，我们来看看什么是隐变量模型，以及为什么它们对表示学习至关重要。

表示学习的目标是让算法能够自动发现数据中潜在的变化因素。例如，在人脸数据集中，这些因素可能包括性别、年龄、发型、姿势等。这些信息是“潜在”的，并没有在数据中明确标注。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_79.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_81.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_82.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_83.png)

隐变量模型通过引入一个额外的、未观测到的变量 **z** 来解决这个问题。**z** 代表了数据的潜在表示或特征。我们的目标是学习一个关于观测变量 **x**（如图像）和隐变量 **z** 的联合概率分布 **P(x, z)**。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_85.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_87.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_89.png)

### 隐变量模型的优势

与自回归模型相比，隐变量模型具有以下优势：
*   **快速采样**：一旦学习到模型，可以通过先采样 **z**，再根据 **z** 采样 **x** 来快速生成数据。
*   **强大的表示能力**：通过 **z**，模型可以学习到数据丰富的、连续的潜在表示。
*   **支持表示学习**：我们可以计算后验概率 **P(z | x)**，从而将数据点 **x** 映射到其潜在表示 **z** 上。这允许我们进行数据插值、属性操作和发现数据中的聚类结构。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_91.png)

### 从浅层到深层：隐变量模型示例

![](img/e51bd05be4909e30eb0d7e777afa7dd1_93.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_95.png)

以下是隐变量模型的两个关键示例：

![](img/e51bd05be4909e30eb0d7e777afa7dd1_97.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_98.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_99.png)

**1. 高斯混合模型 (GMM)**
这是一个经典的浅层隐变量模型。其中，隐变量 **z** 是一个离散的类别变量（例如，代表K个聚类中的哪一个）。条件分布 **P(x | z)** 是一个高斯分布，其参数（均值、方差）依赖于 **z** 的值。GMM 可以进行简单的表示学习（将数据点分配到某个聚类），但其表示能力有限。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_101.png)

**2. 深度隐高斯模型 / 变分自编码器 (VAE) 核心**
这是一种更强大的深度隐变量模型。在这里，隐变量 **z** 是一个连续的向量（例如，服从标准高斯先验 **P(z) = N(0, I)**）。条件分布 **P(x | z)** 的参数（例如，高斯分布的均值 **μ** 和方差 **σ²**）由一个神经网络生成，该网络以 **z** 为输入。

**P(x | z) = N( μ_θ(z), σ_θ(z) )**

![](img/e51bd05be4909e30eb0d7e777afa7dd1_103.png)

其中，**μ_θ(z)** 和 **σ_θ(z)** 是神经网络的输出。这种结构就像一个“无限混合高斯模型”，具有极强的灵活性，能够学习复杂的连续潜在表示。

## 学习隐变量模型的挑战与变分推断 🧩

![](img/e51bd05be4909e30eb0d7e777afa7dd1_105.png)

上一节我们定义了隐变量模型，本节中我们来看看学习这类模型时遇到的核心挑战以及解决方案。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_107.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_109.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_111.png)

学习隐变量模型的目标通常是最大化数据的边际似然 **P(x)**。然而，对于隐变量模型，边际似然需要对所有可能的 **z** 进行求和或积分：

![](img/e51bd05be4909e30eb0d7e777afa7dd1_113.png)

**P(x) = ∫ P(x, z) dz = ∫ P(z) P(x | z) dz**

![](img/e51bd05be4909e30eb0d7e777afa7dd1_115.png)

当 **z** 是高维连续变量时，这个积分通常是难以直接计算的（计算上不可行）。因此，我们无法直接使用最大似然估计来优化模型参数 **θ**。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_117.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_119.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_121.png)

### 引入证据下界 (ELBO)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_123.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_125.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_127.png)

为了解决这个问题，我们引入**变分推断**。其核心思想是，我们不去直接优化难以处理的边际似然 **log P(x)**，而是优化它的一个可计算的下界，称为**证据下界**。

通过一些代数变换和詹森不等式的应用，我们可以得到：

![](img/e51bd05be4909e30eb0d7e777afa7dd1_129.png)

**log P(x) ≥ ELBO = E_{z∼Q(z)} [ log P(x, z) - log Q(z) ]**

![](img/e51bd05be4909e30eb0d7e777afa7dd1_131.png)

其中，**Q(z)** 是我们引入的一个新的概率分布，称为**变分分布**，它用于近似真实的后验分布 **P(z | x)**。

### 变分推断的步骤

![](img/e51bd05be4909e30eb0d7e777afa7dd1_133.png)

变分推断的目标是让 ELBO 尽可能紧地逼近 **log P(x)**。这通过以下两步完成：

![](img/e51bd05be4909e30eb0d7e777afa7dd1_135.png)

1.  **优化变分分布 Q**：对于固定的模型参数 **θ**，我们寻找一个 **Q(z)**（通常来自一个参数化族，例如高斯分布），使得 ELBO 最大化。这等价于最小化 **Q(z)** 与真实后验 **P(z | x)** 之间的 KL 散度。
2.  **优化模型参数 θ**：在找到（或同时优化）一个较好的 **Q** 后，我们利用 ELBO 关于 **θ** 的梯度来更新模型参数，从而提升边际似然。

**关键点**：最优的 **Q(z)** 就是真实后验 **P(z | x)**，但后者同样难以计算。因此，我们通常选择一个简单的分布族（如对角高斯分布）来近似它。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_137.png)

### 变分推断示例

![](img/e51bd05be4909e30eb0d7e777afa7dd1_139.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_141.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_143.png)

以下是两个理解变分推断的简单示例：

![](img/e51bd05be4909e30eb0d7e777afa7dd1_145.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_146.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_147.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_149.png)

**示例一：近似复杂后验**
假设真实后验 **P(z | x)** 是一个复杂的非高斯分布（蓝色曲线）。我们选择高斯分布族作为 **Q(z)**。通过优化 ELBO，我们可以找到一个高斯分布（黄色曲线），使其尽可能接近真实后验，尽管无法完全匹配。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_151.png)

**示例二：图像补全任务**
假设我们有一个数字数据集，但每张图片的上半部分被隐藏了。观测部分 **x** 是下半部分，隐变量 **z** 是上半部分。一个糟糕的 **Q(z)** 可能为每个缺失像素随机赋值（如 0.5）。一个好的 **Q(z)** 则会学习到，对于给定的下半部分数字“9”，上半部分应该以高概率是“9”的顶部笔画。变分推断的目标就是学习到这个好的 **Q**。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_153.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_154.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_156.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_157.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_159.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_160.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_162.png)

## 总结与展望 📚

![](img/e51bd05be4909e30eb0d7e777afa7dd1_164.png)

本节课中我们一起学习了隐变量模型的基本概念。我们了解到：

![](img/e51bd05be4909e30eb0d7e777afa7dd1_166.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_168.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_170.png)

*   **动机**：隐变量模型（如 VAE）非常适合进行表示学习，能够自动发现数据中的潜在因素和结构。
*   **模型定义**：它们通过引入隐变量 **z** 并建模联合分布 **P(x, z)** 来工作，其中 **P(x | z)** 通常由神经网络参数化。
*   **核心挑战**：直接最大化边际似然 **P(x)** 是计算不可行的。
*   **解决方案**：变分推断通过优化证据下界 (ELBO) 来近似学习模型。这涉及同时优化变分分布 **Q(z)**（以近似后验）和生成模型参数 **θ**。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_172.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_174.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_176.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_177.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_179.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_180.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_182.png)

我们已经为隐变量模型搭建了理论框架，并理解了学习它们需要变分推断。在下一讲中，我们将把这些概念具体化，推导出变分自编码器 (VAE) 的完整算法，并展示如何同时优化 **Q** 和 **θ** 来训练一个强大的深度生成模型。