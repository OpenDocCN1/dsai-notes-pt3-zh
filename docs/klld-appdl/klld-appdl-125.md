# 125：XLNet 详解 🧠

![](img/febdb3415c12e7ec45618b5dc4aaced7_1.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_2.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_3.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_4.png)

在本节课中，我们将学习 XLNet 模型。XLNet 是一种基于 Transformer 架构的先进语言模型，它巧妙地融合了自回归模型（如 GPT）和自编码模型（如 BERT）的核心思想。我们将探讨其设计动机、核心原理以及它是如何克服现有模型局限性的。

![](img/febdb3415c12e7ec45618b5dc4aaced7_5.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_6.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_7.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_8.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_9.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_10.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_11.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_12.png)

---

![](img/febdb3415c12e7ec45618b5dc4aaced7_14.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_15.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_16.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_17.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_18.png)

## 1. 背景与动机

上一节我们介绍了 Transformer 及其变体。本节中，我们来看看 XLNet 如何整合两种主流语言建模思想。

![](img/febdb3415c12e7ec45618b5dc4aaced7_20.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_21.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_22.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_23.png)

我们有两种主要的语言模型：
*   **自回归模型**：例如 GPT，它基于上文预测下一个词。其目标是建模序列的联合概率，通常使用链式法则按顺序分解。
*   **自编码模型**：例如 BERT，它通过掩码部分输入词，然后基于上下文预测这些被掩码的词。这被称为“去噪自编码”。

![](img/febdb3415c12e7ec45618b5dc4aaced7_24.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_25.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_26.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_27.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_28.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_29.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_30.png)

这两种方法各有优缺点。

以下是自回归模型和自编码模型的核心目标公式：

![](img/febdb3415c12e7ec45618b5dc4aaced7_32.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_33.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_34.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_35.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_36.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_37.png)

**自回归模型目标**：
`P(句子) = ∏ P(词_t | 词_<t)`

![](img/febdb3415c12e7ec45618b5dc4aaced7_38.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_39.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_40.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_41.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_42.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_43.png)

**自编码模型目标**：
`最大化 log P(被掩码词 | 被破坏的句子)`

---

![](img/febdb3415c12e7ec45618b5dc4aaced7_45.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_46.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_47.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_48.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_49.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_50.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_51.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_52.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_53.png)

## 2. 现有模型的局限性

![](img/febdb3415c12e7ec45618b5dc4aaced7_54.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_55.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_56.png)

理解了两类模型的基本原理后，我们来看看它们各自存在的问题。

**自回归模型（如GPT）的缺点**：
*   在分解联合概率时，无论是前向分解（从左到右）还是后向分解（从右到左），都只是众多可能排列中的一种特定顺序，并无特殊优势。模型性能可能受限于这种固定的分解顺序。

![](img/febdb3415c12e7ec45618b5dc4aaced7_58.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_59.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_60.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_61.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_62.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_63.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_64.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_65.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_66.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_67.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_68.png)

**自编码模型（如BERT）的缺点**：
1.  **预训练与微调的不一致**：在预训练阶段，模型会看到特殊的 `[MASK]` 标记，但在下游任务微调时，这个标记不会出现，导致数据分布存在差异。
2.  **强独立性假设**：BERT 在预测多个被掩码的词时，假设这些预测在给定上下文条件下是相互独立的。这在实际语言中往往不成立。

![](img/febdb3415c12e7ec45618b5dc4aaced7_69.png)

---

![](img/febdb3415c12e7ec45618b5dc4aaced7_71.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_72.png)

## 3. XLNet 的核心思想：排列语言建模

![](img/febdb3415c12e7ec45618b5dc4aaced7_73.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_74.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_75.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_76.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_77.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_78.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_79.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_80.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_81.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_82.png)

为了解决上述问题，XLNet 提出了**排列语言建模** 的核心思想。

![](img/febdb3415c12e7ec45618b5dc4aaced7_84.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_85.png)

关键洞察是：自回归模型中的链式法则，其因式分解顺序可以是任意的排列。如果我们能考虑所有可能的排列顺序，模型就能学习到更丰富的上下文依赖关系。

**XLNet 的目标函数**：
`最大化 E_{z∼所有排列} [ ∑_{t=1}^{T} log P(词_{z_t} | 词_{z_{<t}}) ]`

![](img/febdb3415c12e7ec45618b5dc4aaced7_87.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_88.png)

![](img/febdb3415c12e7ec45618b5dc4aaced7_89.png)

其中，`z` 代表句子索引的一个排列顺序，`z_t` 是排列中第 `t` 个位置的索引，`z_{<t}` 是排列中前 `t-1` 个位置的索引。

这意味着，对于一个句子，模型会学习在所有可能的词序排列下预测目标词。

---

## 4. 实现排列语言建模的双流注意力机制

直接将排列的想法应用于标准 Transformer 会遇到一个难题：模型需要知道当前要预测的词的位置（`z_t`），但在处理时如果打乱输入顺序，就会丢失位置信息。

XLNet 的解决方案是：**保持输入序列的原始顺序不变，但通过改变注意力掩码来实现不同的排列**。同时，为了在并行计算中避免“看到自己”（即信息泄露），引入了**双流注意力机制**。

以下是双流注意力机制的简要说明：

**1. 内容流注意力**：
*   **作用**：编码当前词的内容信息，供后续位置预测时使用。
*   **计算**：查询（Query）、键（Key）、值（Value）都来自对应位置的隐藏状态。
*   **代码示意**：`内容隐藏状态 = Attention(Query=H_{z_t}, Key=H_{z_{≤t}}, Value=H_{z_{≤t}})`

**2. 查询流注意力**：
*   **作用**：用于预测当前词，它只能获取位置信息，而不能获取当前词的内容信息，防止作弊。
*   **计算**：查询向量来自一个只包含位置信息的初始向量，键和值来自内容隐藏状态。
*   **代码示意**：`查询隐藏状态 = Attention(Query=G_{z_t}, Key=H_{z_{<t}}, Value=H_{z_{<t}})`

最终，预测词 `x_{z_t}` 的概率使用查询流的隐藏状态进行计算：`P(词_{z_t} | 词_{z_{<t}}) = Softmax(词嵌入 * 查询隐藏状态_{z_t})`

---

## 5. 部分预测与效率优化

考虑到所有排列的组合爆炸问题，XLNet 采用了**部分预测**策略来提升训练效率。

具体做法是：
*   从一个排列中，只预测最后一部分词（例如，排列顺序中靠后的约 15% 的词）。
*   这类似于 BERT 只预测被掩码的部分词，但不同之处在于，XLNet 预测的词是基于排列顺序的“后续”词，而非随机掩码的词。这放松了 BERT 的独立性假设，因为模型在预测靠后的词时，可以依赖于前面已预测出的词。

这种设计使得 XLNet：
1.  **泛化了自回归模型**：通过考虑多种排列顺序。
2.  **泛化了自编码模型**：通过部分预测，且去除了 `[MASK]` 标记和强独立性假设。
3.  **继承了 Transformer-XL**：使用了段循环机制和相对位置编码，能够处理更长的文本。

---

## 6. 总结与回顾

本节课中，我们一起学习了 XLNet 模型。

*   **动机**：为了克服传统自回归模型（固定顺序）和自编码模型（预训练-微调不一致、独立性假设）的缺陷。
*   **核心**：提出了**排列语言建模**目标，使模型能够从所有可能的词序中学习上下文依赖。
*   **关键实现**：通过**双流注意力机制**在保持输入顺序的同时实现排列，并解决并行计算中的信息泄露问题。
*   **效率与效果**：采用**部分预测**策略平衡计算成本与性能，并在多项自然语言理解任务上取得了当时领先的结果。

XLNet 的巧妙之处在于，它从一个统一的视角看待两种主流语言建模范式，并通过严谨的数学设计和工程实现，创造出了一个更强大、更通用的模型。