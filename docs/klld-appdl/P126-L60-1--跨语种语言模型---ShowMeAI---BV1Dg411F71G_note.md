# P126：L60.1- 跨语种语言模型 🌐

![](img/b7d1f8d51654c8bf6b23bb501eabac03_1.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_2.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_3.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_4.png)

在本节课中，我们将要学习如何将语言模型从单一语言（如英语）扩展到多种语言，即构建**跨语种语言模型**。我们将遵循“预训练-微调”的范式，并引入新的概念来处理多语言数据。

![](img/b7d1f8d51654c8bf6b23bb501eabac03_5.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_6.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_7.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_8.png)

## 概述

![](img/b7d1f8d51654c8bf6b23bb501eabac03_10.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_11.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_12.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_13.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_14.png)

之前我们学习的语言建模主要针对单一语言。本节我们将探讨如何利用多语言语料库进行预训练，并介绍跨语种语言模型（XLM）的核心思想与方法。

![](img/b7d1f8d51654c8bf6b23bb501eabac03_16.png)

## 数据准备：单语与平行语料库

![](img/b7d1f8d51654c8bf6b23bb501eabac03_17.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_18.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_19.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_20.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_21.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_22.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_23.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_24.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_25.png)

构建跨语种模型的第一步是准备数据。数据主要分为两类：

*   **单语数据**：包含N种不同语言的语料库。例如，C₁是英语语料库，C₂是法语语料库，C₃是西班牙语语料库等。每个语料库Cᵢ包含Nᵢ个句子。这种数据用于**无监督**学习任务。
*   **平行数据**：包含翻译对的数据，例如成对的英语和法语句子。这种数据用于**有监督**学习任务。

![](img/b7d1f8d51654c8bf6b23bb501eabac03_27.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_28.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_29.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_30.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_31.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_32.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_33.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_34.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_35.png)

## 构建共享词汇表

![](img/b7d1f8d51654c8bf6b23bb501eabac03_36.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_37.png)

为了处理多种语言，我们需要一个统一的词汇表。以下是构建步骤：

![](img/b7d1f8d51654c8bf6b23bb501eabac03_39.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_40.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_41.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_42.png)

1.  **句子采样**：我们从各个语言的语料库中采样句子，并将它们拼接起来，形成一个用于训练子词单元的大型混合语料。
2.  **采样概率**：为了避免数据量大的语言（如英语）主导词汇表学习，我们采用一种去偏的采样策略。首先计算每个语料库的原始比例 `pᵢ`，然后对其取平方根并进行归一化，得到最终的采样概率 `qᵢ`。

    其**公式**如下：
    `qᵢ = √pᵢ / Σⱼ √pⱼ`

![](img/b7d1f8d51654c8bf6b23bb501eabac03_43.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_44.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_45.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_46.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_47.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_48.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_49.png)

3.  **应用BPE**：在按上述概率采样并拼接好的混合句子上，应用**字节对编码（BPE）**算法，学习得到一个**共享的子词词汇表**。这个词汇表将服务于所有语言。

![](img/b7d1f8d51654c8bf6b23bb501eabac03_51.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_52.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_53.png)

## 跨语种预训练任务

![](img/b7d1f8d51654c8bf6b23bb501eabac03_54.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_55.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_56.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_57.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_58.png)

获得共享词汇表后，我们可以进行预训练。主要有三种预训练目标：

![](img/b7d1f8d51654c8bf6b23bb501eabac03_60.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_61.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_62.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_63.png)

1.  **因果语言建模（CLM）**：即自回归语言模型，类似于GPT，用于预测下一个词。这主要使用模型的**解码器**部分。
2.  **掩码语言建模（MLM）**：类似于BERT，随机掩码输入中的一些词，然后预测它们。为了区分不同语言，模型输入除了词嵌入和位置嵌入外，还增加了**语言嵌入**。例如，处理英语句子时加入英语对应的向量，处理法语句子时加入法语对应的向量。
3.  **翻译语言建模（TLM）**：这是一种有监督的预训练方法，需要平行语料。将一对翻译句子（如英-法）拼接后输入模型，随机掩码其中一些词（可能来自任一种语言），然后进行预测。这有助于模型学习语言间的对齐关系。

![](img/b7d1f8d51654c8bf6b23bb501eabac03_65.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_66.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_67.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_68.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_69.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_70.png)

![](img/b7d1f8d51654c8bf6b23bb501eabac03_71.png)

## 下游任务应用

预训练好的跨语种模型可以用于各种下游任务。例如，在自然语言推理（NLI）任务中：

![](img/b7d1f8d51654c8bf6b23bb501eabac03_73.png)

*   假设我们有一个法语NLI数据集（训练集），但模型主要在英语上预训练。
*   我们可以将法语训练集翻译成英语，然后在英语数据上微调模型，最后用于法语测试。
*   更直接的方法是，利用跨语种模型本身学到的语言间表示，直接在法语数据上进行微调和预测，实现**零样本**或**少样本**的跨语言迁移。

在机器翻译任务中，实验表明：
*   使用**MLM**目标在编码器侧进行迁移学习，对提升低资源语言的翻译质量效果显著。
*   拥有**平行数据（TLM）**进行有监督预训练，通常能获得最佳性能。
*   即使没有平行语料，仅通过单语数据（CLM/MLM）进行无监督预训练，也能实现不错的**无监督机器翻译**。

## 核心要点总结

本节课我们一起学习了跨语种语言模型（XLM）的关键技术：

1.  **共享子词词汇表**：通过去偏采样策略混合多语言数据，并应用BPE构建统一词汇表。
2.  **语言嵌入**：在模型输入中加入语言标识向量，帮助模型区分不同语言。
3.  **预训练目标**：包括无监督的CLM/MLM，以及有监督的TLM。MLM结合语言嵌入是核心方法。
4.  **迁移学习**：通过预训练，模型能够将高资源语言（如英语）学到的知识迁移到低资源语言的下游任务中。

本质上，XLM是将BERT/GPT式的“预训练-微调”范式扩展到了多语言场景。