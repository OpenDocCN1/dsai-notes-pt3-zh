# 斯坦福 CS236 深度生成模型课程笔记 📚

## 课程概述

在本课程中，我们将系统学习斯坦福大学 CS236《深度生成模型》的核心内容。课程涵盖了从基础概念到前沿模型的完整知识体系，包括自编码器、变分自编码器、生成对抗网络、归一化流以及扩散模型等。我们将深入探讨这些模型的数学原理、训练方法及其应用。

以下是本课程笔记的完整目录结构：

*   [斯坦福 CS236 深度生成模型笔记](README.md)
*   [P1： 第一讲 - 课程介绍](P1-p1-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-1---Intr---加加zero---BV1NjH4eYE1v.md)
*   [P2： 第二讲 - 背景知识](P2-p2-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-2---Back---加加zero---BV1NjH4eYE1v.md)
*   [P3： 第三讲 - 自编码器](P3-p3-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-3---Auto---加加zero---BV1NjH4eYE1v.md)
*   [P4： 第四讲 - 最大似然估计](P4-p4-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-4---Maxi---加加zero---BV1NjH4eYE1v.md)
*   [P5： 第五讲 - 变分自编码器（VAEs）](P5-p5-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-5---VAEs---加加zero---BV1NjH4eYE1v.md)
*   [P6： 第六讲 - 变分自编码器（续）](P6-p6-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-6---VAEs---加加zero---BV1NjH4eYE1v.md)
*   [P7： 第七讲 - 归一化流](P7-p7-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-7---Norm---加加zero---BV1NjH4eYE1v.md)
*   [P8： 第八讲 - 生成对抗网络（GANs）](P8-p8-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-8---GANs---加加zero---BV1NjH4eYE1v.md)
*   [P9： 第九讲 - 归一化流（续）](P9-p9-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-9---Norm---加加zero---BV1NjH4eYE1v.md)
*   [P10： 第十讲 - 生成对抗网络（续）](P10-p10-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-10---GA---加加zero---BV1NjH4eYE1v.md)
*   [P11： 第十一讲 - 能量模型](P11-p11-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-11---En---加加zero---BV1NjH4eYE1v.md)
*   [P12： 第十二讲 - 能量模型（续）](P12-p12-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-12---En---加加zero---BV1NjH4eYE1v.md)
*   [P13： 第十三讲 - 分数匹配](P13-p13-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-13---Sc---加加zero---BV1NjH4eYE1v.md)
*   [P14： 第十四讲 - 能量模型（续）](P14-p14-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-14---En---加加zero---BV1NjH4eYE1v.md)
*   [P15： 第十五讲 - 评估方法](P15-p15-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-15---Ev---加加zero---BV1NjH4eYE1v.md)
*   [P16： 第十六讲 - 分数匹配（续）](P16-p16-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-16---Sc---加加zero---BV1NjH4eYE1v.md)
*   [P17： 第十七讲 - 扩散模型](P17-p17-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-17---Di---加加zero---BV1NjH4eYE1v.md)
*   [P18： 第十八讲 - 扩散模型（续）](P18-p18-Stanford-CS236--Deep-Generative-Models-I-2023-I-Lecture-18---Di---加加zero---BV1NjH4eYE1v.md)

---

## 第一讲：课程介绍 🎯

在本节课中，我们将学习深度生成模型课程的整体框架和学习目标。课程旨在理解如何让机器学会创造新的、有意义的数据，如图像、文本或声音。

### 什么是生成模型？

生成模型是机器学习模型的一种，其核心目标是学习并模拟真实数据的分布。与判别模型（如图像分类器）不同，生成模型试图理解数据是如何“生成”的。给定一个训练数据集，生成模型学习其潜在的概率分布 **p(x)**，从而能够从中采样，创造出与训练数据相似的新样本。

### 课程主要内容

上一节我们定义了生成模型，本节中我们来看看本课程将涵盖哪些核心模型家族。

以下是本课程将要深入讲解的几种主要深度生成模型：

1.  **变分自编码器**：通过引入潜变量和变分推断来学习数据分布。
2.  **生成对抗网络**：通过一个生成器和一个判别器的对抗博弈来学习生成数据。
3.  **归一化流**：通过一系列可逆变换，将简单分布精确地转换为复杂的数据分布。
4.  **自回归模型**：按顺序生成数据的每个部分（如像素或单词），每一步都依赖于之前生成的部分。
5.  **基于能量的模型**：用一个标量能量函数来定义未归一化的概率分布。
6.  **扩散模型**：通过一个逐步添加噪声和去噪声的过程来学习数据分布，这是当前图像生成领域的领先方法。

### 学习目标

完成本课程后，你应该能够理解上述各类模型的原理、优缺点、数学基础及实现方式，并了解如何评估生成模型的质量。

---

## 第二讲：背景知识 📖

在深入具体模型之前，我们需要建立必要的数学和概率论基础。本节将回顾最大似然估计、潜变量模型以及表示学习等关键概念。

### 最大似然估计

最大似然估计是训练生成模型最基础且最重要的原则之一。其思想是：我们希望找到一组模型参数 **θ**，使得在这组参数下，观察到整个训练数据集 **D = {x₁, x₂, ..., x_N}** 的概率最大。

假设数据点独立同分布，其对数似然函数为：
**log p_θ(D) = Σ_{i=1}^N log p_θ(x_i)**

我们的目标是最大化这个对数似然：
**θ* = argmax_θ Σ_{i=1}^N log p_θ(x_i)**

### 潜变量模型

许多复杂的生成模型会引入**潜变量 z**。潜变量可以理解为数据背后未观察到的、解释性的因素。例如，在一张人脸图片中，潜变量可能对应着姿态、表情、光照等属性。

引入潜变量后，数据的边际似然通过对所有可能的潜变量求和（或积分）得到：
**p_θ(x) = ∫ p_θ(x, z) dz = ∫ p_θ(x|z) p(z) dz**

其中 **p(z)** 是先验分布（通常假设为简单的高斯分布），**p_θ(x|z)** 是给定潜变量后生成数据的条件分布。

### 表示学习

生成模型的一个关键副产品是学习到了数据的**有用表示**。通过编码器或将数据映射到潜空间，我们可以获得数据的低维、有意义的特征，这些特征可用于下游任务，如分类、检索或数据编辑。

---

## 总结

在本节课中，我们一起学习了深度生成模型课程的概览和必要的背景知识。我们了解了生成模型的目标是学习数据分布 **p(x)**，并回顾了最大似然估计这一核心训练准则。同时，我们认识了潜变量模型的基本框架，它通过引入隐藏变量 **z** 来构建更富有表达力的模型，并服务于表示学习。

从下一讲开始，我们将进入具体模型的学习，首先从自编码器及其与生成模型的联系开始。