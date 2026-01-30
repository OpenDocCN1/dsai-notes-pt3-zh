# 🧠 课程 P122：GPT-2 模型详解

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_1.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_2.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_3.png)

在本节课中，我们将学习 GPT-2 模型的核心思想。GPT-2 是 GPT-1 的后续版本，它提出了一种全新的任务处理范式，无需针对特定下游任务进行微调，仅通过语言模型本身和任务提示就能完成多种任务。我们将重点解析这一“零样本学习”的巧妙思路。

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_4.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_5.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_6.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_7.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_9.png)

## 🏗️ 模型架构与规模

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_10.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_11.png)

上一节我们介绍了 GPT-1，本节我们来看看 GPT-2。GPT-2 的模型架构基于 Transformer 的**解码器**部分。这与 BERT（基于编码器）不同。GPT-2 模型参数量巨大，达到了 **15 亿**参数。

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_13.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_14.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_15.png)

以下是其核心架构的示意：
```python
# GPT-2 基于 Transformer Decoder 堆叠
model = TransformerDecoder(num_layers=48, d_model=1600, num_heads=25)
```

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_16.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_17.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_18.png)

## 📊 数据与训练目标

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_20.png)

我们首先回顾语言模型的基本训练方式。假设我们的语料库包含 `n` 个句子，每个句子是可变长度的序列。语言模型的训练目标是进行下一个词（或符号）的预测。

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_21.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_22.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_23.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_24.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_25.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_26.png)

对于一个句子 `s = (w1, w2, ..., wk)`，其概率可以分解为：
**P(s) = P(w1) * P(w2|w1) * ... * P(wk|w1, w2, ..., w_{k-1})**

这本质上就是链式法则。我们可以将此目标从预测下一个词，泛化到预测后续的多个词或符号。这对于需要生成序列输出的任务（如翻译、摘要）是必要的。

## 🔄 任务处理范式的演变

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_28.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_29.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_30.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_31.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_32.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_33.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_34.png)

在传统的监督学习范式中，我们需要为不同任务（如问答、翻译）设计特定的模型头部，并进行微调。这是 GPT-1 和 BERT 采用的方法。

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_35.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_36.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_37.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_38.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_40.png)

然而，GPT-2 提出了一种更简洁的思路：**将任务描述直接作为输入文本的一部分**。因为我们的任务本身（如翻译、问答）可以用自然语言描述，所以我们可以通过修改输入数据的格式，让同一个语言模型学会执行多种指令。

以下是具体做法：

对于机器翻译任务，我们将训练样本从 `(英文句子，法文句子)` 的配对格式，改为一个拼接的序列：
`“translate to French: [英文句子] = [法文句子]”`

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_42.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_43.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_44.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_45.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_46.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_47.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_48.png)

对于阅读理解任务，我们可以构造如下序列：
`“answer the question: [文档] question: [问题] answer: [答案]”`

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_49.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_50.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_51.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_52.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_53.png)

通过这种方式，我们在预训练阶段就让模型接触了大量带有“任务指令”的文本。模型在预测下一个词时，实际上也学会了在特定指令下应该生成什么样的内容。

## 🛠️ 数据预处理

为了实现上述目标，我们需要对数据进行预处理，这与我们之前学过的技术一致：

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_55.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_56.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_57.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_58.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_59.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_60.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_61.png)

*   **文本规范化**：包括小写化等操作。
*   **分词与子词表示**：使用 **Byte Pair Encoding (BPE)** 来处理词汇表外的问题。BPE 是一种介于字符和单词之间的表示方法，能有效处理未登录词。
*   **符号化**：最终我们将文本转化为一系列子词符号（subword tokens）序列。

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_62.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_63.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_64.png)

## ✨ 核心思想：零样本任务执行

GPT-2 论文最精妙的核心思想在于：**一个在庞大、多样化互联网文本上训练的语言模型，本身就蕴含了执行多种任务的能力**。

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_66.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_67.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_68.png)

模型在训练过程中，已经“见过”无数自然出现的任务示例，例如：
*   网络上出现的双语对照句子（隐含了翻译任务）。
*   问答形式的论坛帖子（隐含了问答任务）。
*   带有总结性开头的文章（隐含了摘要任务）。

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_69.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_70.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_71.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_72.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_73.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_74.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_75.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_76.png)

因此，当我们在推理时给出一个明确的任务提示（如 `“translate to French: ‘Hello world’”`），模型就能根据其在训练时见过的类似模式，生成符合任务要求的文本。

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_77.png)

这种方法被称为**零样本学习**。你不需要为任何下游任务准备标注数据或进行微调，只需给出正确的“提示”，模型就能尝试完成任务。

## ⚖️ 性能与意义

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_79.png)

![](img/5b145e3ef9a2f84abc0217b6fb82b4a7_80.png)

当然，这种零样本方法的性能通常低于针对特定任务精心设计和微调的模型。但它展示了一种强大的通用性和简洁性。

GPT-2 的成功主要归功于两个因素：
1.  **精妙的核心思想**：利用自然语言提示来统一任务格式。
2.  **巨大的模型规模与数据量**：让模型能够从海量数据中学习到丰富的任务模式。

本节课中，我们一起学习了 GPT-2 模型的核心突破。它不再依赖传统的“预训练-微调”范式，而是通过将任务指令作为输入的一部分，让一个大规模语言模型具备了**零样本**解决多种下游任务的能力。这一思想为后续更强大的大语言模型（如 GPT-3）奠定了基础。