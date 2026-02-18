# 21：第10讲：今日的语言模型是如何做文字接龙的 — 浅谈Transformer 🧠

![](img/67d96403610f98c8a68f6e516235a3ce_1.png)

![](img/67d96403610f98c8a68f6e516235a3ce_3.png)

在本节课中，我们将深入语言模型的内部，了解其核心神经网络——Transformer——是如何工作的。理解Transformer的运作机制，是后续探讨大型语言模型“内心想法”的基础。本节课将分步解析一个句子从输入到输出概率分布的全过程。

![](img/67d96403610f98c8a68f6e516235a3ce_5.png)

---

![](img/67d96403610f98c8a68f6e516235a3ce_7.png)

![](img/67d96403610f98c8a68f6e516235a3ce_9.png)

## 课程概述 📋

![](img/67d96403610f98c8a68f6e516235a3ce_11.png)

今天的课程分为两部分。前半部分将深入语言模型内部，解析其核心神经网络Transformer的运作机制。这部分内容是为下半部分课程做铺垫，因为要探讨大型语言模型的“心理活动”，必须先了解其运作机制。我们将从语言模型的基本任务——文字接龙——开始，逐步拆解Transformer的每个步骤。

![](img/67d96403610f98c8a68f6e516235a3ce_13.png)

---

![](img/67d96403610f98c8a68f6e516235a3ce_15.png)

## 第一部分：语言模型与Transformer简介

我们已经多次强调，语言模型的核心任务是**文字接龙**。它通过海量训练数据学习，其内部是一个包含许多未知参数的函数。本节课的目标，就是揭示这个函数——即Transformer神经网络——的内部运作过程。

今天的语言模型普遍采用**Transformer**这一神经网络架构。ChatGPT中的“T”指的就是Transformer，可见其重要性。本节将介绍一个简化版本，如需深入了解，可参考课程提供的额外资料。

![](img/67d96403610f98c8a68f6e516235a3ce_17.png)

---

## 第二部分：Transformer运作流程总览

![](img/67d96403610f98c8a68f6e516235a3ce_19.png)

当一个句子输入语言模型后，需要经过一系列步骤才能得到输出的概率分布。以下是整体流程的概述：

![](img/67d96403610f98c8a68f6e516235a3ce_21.png)

1.  **Tokenization（分词）**：将文字转换为Token序列。
2.  **Input Embedding（输入嵌入）**：将每个Token转换为一个向量，以理解其语义。
3.  **Positional Encoding（位置编码）**：为每个Token的向量添加位置信息。
4.  **Transformer Blocks（Transformer块）**：核心处理模块，反复对信息进行加工。
    *   **Attention（注意力机制）**：理解Token之间的上下文关系。
    *   **Feedforward Network（前馈网络）**：对注意力机制的输出进行整合与进一步思考。
5.  **Output Layer（输出层）**：将最终输出转换为下一个Token的概率分布。

接下来，我们将详细解析每一个步骤。

![](img/67d96403610f98c8a68f6e516235a3ce_23.png)

---

![](img/67d96403610f98c8a68f6e516235a3ce_25.png)

## 第三部分：详解Transformer各步骤

### 1. Tokenization（分词）🔡

语言模型处理的基本单位是**Token**。因此，输入句子的第一步是将其切分成Token序列。

![](img/67d96403610f98c8a68f6e516235a3ce_27.png)

例如，句子 “introduction of generative AI” 可能被切分为：`[“int”, “roduction”, “of”, “gener”, “ative”, “AI”]`。

![](img/67d96403610f98c8a68f6e516235a3ce_29.png)

如何切分取决于预先定义的**Token列表**。不同语言模型的Token列表不同。例如，许多中文模型将一个汉字作为一个Token，而ChatGPT可能将多个Token组合成一个汉字。Token列表可以通过算法（如Byte Pair Encoding, BPE）从大量文本中自动学习得到，也可以由人工定义。这是一个无需训练的参数模块。

![](img/67d96403610f98c8a68f6e516235a3ce_31.png)

### 2. Input Embedding（输入嵌入）🧩

此步骤将每个Token（符号）转换为一个**向量**（一串数字），这个过程称为**Embedding**。

![](img/67d96403610f98c8a68f6e516235a3ce_33.png)

这样做的好处是能将语义信息编码进向量。语义相近的Token（如“run”和“jump”），其向量在空间中的距离也更接近。这使后续神经网络能理解Token之间的关联。

具体实现是通过一个**查表**过程：模型有一个存储了所有Token及其对应向量的表格。输入一个Token，就取出对应的向量。这个表格（即每个Token的向量）是模型需要从训练数据中学习的**参数**。

![](img/67d96403610f98c8a68f6e516235a3ce_35.png)

然而，此时的Embedding有一个局限：它没有考虑上下文。同一个Token（如“bank”）无论语境如何，其向量都是固定的。

![](img/67d96403610f98c8a68f6e516235a3ce_37.png)

### 3. Positional Encoding（位置编码）📍

![](img/67d96403610f98c8a68f6e516235a3ce_39.png)

我们需要让模型知道每个Token在句子中的位置，因为位置可能影响语义。方法是为每个位置也设置一个向量（Positional Embedding），然后将其加到对应Token的Embedding上。

![](img/67d96403610f98c8a68f6e516235a3ce_41.png)

![](img/67d96403610f98c8a68f6e516235a3ce_43.png)

这样，最终的向量就同时包含了**语义信息**和**位置信息**。位置向量可以是人工设计的，也可以作为模型参数从数据中学习。

![](img/67d96403610f98c8a68f6e516235a3ce_45.png)

### 4. Transformer Block：Attention（注意力机制）🎯

![](img/67d96403610f98c8a68f6e516235a3ce_47.png)

![](img/67d96403610f98c8a68f6e516235a3ce_49.png)

这是考虑上下文信息的核心模块。Attention模块会读取整个句子，根据上下文为每个Token生成新的、包含上下文信息的向量，称为 **Contextualized Embedding**。

![](img/67d96403610f98c8a68f6e516235a3ce_51.png)

例如，“苹果电脑”的“果”和“吃苹果”的“果”，经过Attention处理后，它们的向量就会变得不同，以反映其不同的含义。

![](img/67d96403610f98c8a68f6e516235a3ce_53.png)

**Attention的基本原理**：
Attention模块输入一排向量（每个代表一个Token），输出另一排长度相同的向量。对于输出序列中的每一个向量，其计算过程如下：
1.  **计算相关性**：用一个可学习的函数 `F`，计算当前Token向量与句子中**每一个**Token向量（包括自身）的关联分数，即 **Attention Weight**。
2.  **加权求和**：用上一步计算出的所有Attention Weight作为权重，对句子中所有的Token向量进行加权求和，结果即为当前Token的输出向量。

![](img/67d96403610f98c8a68f6e516235a3ce_55.png)

![](img/67d96403610f98c8a68f6e516235a3ce_57.png)

简单来说，Attention就是“看看哪些信息是相关的，再把相关的信息集合起来”。

**多头注意力（Multi-head Attention）**：
因为“相关性”可以有多种类型（例如，“狗”和“猫”在“动物”层面相关，“狗”和“叫”在“动作”层面相关），所以通常使用多个独立的“计算相关性”模块（即多个“头”），并行计算多组Attention Weight，从而得到多组输出向量，以捕捉不同层面的关联信息。

![](img/67d96403610f98c8a68f6e516235a3ce_59.png)

**自注意力与因果注意力**：
理论上需要计算所有Token两两之间的Attention Weight。但在语言模型中，我们通常使用 **Causal Attention（因果注意力）**，即每个Token只与它**之前（左边）**的Token计算相关性。这符合文字接龙“根据上文预测下文”的特性，并且能带来计算上的优化。

![](img/67d96403610f98c8a68f6e516235a3ce_61.png)

![](img/67d96403610f98c8a68f6e516235a3ce_63.png)

### 5. Transformer Block：Feedforward Network（前馈网络）🔄

Attention模块输出了多组向量（对应多个注意力头）。前馈网络的作用是将这些多组向量**整合**起来，通过一个多层神经网络进行综合处理，最终为每个Token输出一个单一的、经过深思熟虑的向量。

![](img/67d96403610f98c8a68f6e516235a3ce_65.png)

**Attention模块 + Feedforward Network模块 = 一个Transformer Block（或称为一个Layer）**。

![](img/67d96403610f98c8a68f6e516235a3ce_67.png)

### 6. 堆叠Transformer Blocks 🧱

![](img/67d96403610f98c8a68f6e516235a3ce_69.png)

![](img/67d96403610f98c8a68f6e516235a3ce_71.png)

一个Transformer模型不会只有一个Block，而是会堆叠很多个（例如12层、24层）。输入向量会依次通过所有这些Block，进行反复、逐层的信息加工和提炼。

![](img/67d96403610f98c8a68f6e516235a3ce_73.png)

### 7. Output Layer（输出层）📤

通过最后一个Transformer Block后，我们取句子**最后一个位置**的输出向量，将其输入输出层。输出层通常包含一个线性变换和一个Softmax函数，最终输出一个**概率分布**，表示下一个可能出现的Token是词汇表中每一个Token的概率。

![](img/67d96403610f98c8a68f6e516235a3ce_75.png)

---

![](img/67d96403610f98c8a68f6e516235a3ce_77.png)

## 第四部分：核心问题与前沿探讨

![](img/67d96403610f98c8a68f6e516235a3ce_79.png)

![](img/67d96403610f98c8a68f6e516235a3ce_81.png)

### 为什么使用Causal Attention？

![](img/67d96403610f98c8a68f6e516235a3ce_83.png)

![](img/67d96403610f98c8a68f6e516235a3ce_85.png)

这源于语言模型**文字接龙**的生成方式。模型在生成每一个新Token时，只能基于已生成的左侧上文。使用Causal Attention：
1.  **符合任务逻辑**：预测未来时无法看到未来。
2.  **计算优化**：在生成式解码过程中，可以缓存之前计算过的Attention结果，避免重复计算，极大提升效率。实验也表明，完整的Attention并不比Causal Attention带来显著性能提升。

![](img/67d96403610f98c8a68f6e516235a3ce_87.png)

### 处理长文本的挑战是什么？

![](img/67d96403610f98c8a68f6e516235a3ce_89.png)

主要挑战在于**Attention的计算复杂度**。对于长度为 `N` 的输入，需要计算 `N x N` 的Attention Weight矩阵，其计算量随文本长度**平方级增长**。因此，处理超长文本需要巨大的算力。

![](img/67d96403610f98c8a68f6e516235a3ce_91.png)

### 相关研究方向

1.  **高效Attention**：如何降低Attention的计算复杂度（如线性Attention）。
2.  **无限长上下文**：让模型能够处理任意长度的输入。
3.  **Train Short, Test Long**：如何在短文本上训练，却能理解长文本。
4.  **Transformer的替代架构**：如Mamba（一种现代RNN变体）等，试图解决Attention的固有瓶颈。

---

## 课程总结 🎓

![](img/67d96403610f98c8a68f6e516235a3ce_93.png)

![](img/67d96403610f98c8a68f6e516235a3ce_95.png)

![](img/67d96403610f98c8a68f6e516235a3ce_97.png)

本节课我们一起学习了Transformer的基本运作机制。我们了解到，一个句子输入语言模型后，会经历**分词 -> 词嵌入 -> 位置编码 -> 多层Transformer Block（注意力+前馈网络）处理 -> 输出概率分布**的完整流程。其中，**注意力机制**是模型理解上下文的关键，而**因果注意力**和**多头注意力**是其重要设计。理解这些机制，为我们后续深入探索大语言模型的能力与原理奠定了坚实基础。