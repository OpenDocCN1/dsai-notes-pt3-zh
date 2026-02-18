# 27：RAG中的查询转换方法 🧠

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_1.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_3.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_5.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_7.png)

在本节课中，我们将学习检索增强生成（RAG）中的一个关键技术——查询转换。我们将探讨为什么需要对用户查询进行转换，并详细介绍四种核心的查询转换方法及其背后的“三个臭皮匠，顶个诸葛亮”的协作思想。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_9.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_11.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_13.png)

## 概述

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_15.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_17.png)

RAG系统通过检索外部知识库中的信息来辅助大语言模型生成更准确的回答。然而，直接使用原始用户查询进行检索，可能会因为措辞、表达方式或问题复杂度的影响，导致检索到的文档不相关或召回率低。查询转换就是为了解决这个问题而设计的一系列方法，其核心思想是将原始查询“换个说法”，以更好地匹配知识库中的信息。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_19.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_21.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_23.png)

上一节我们介绍了RAG的基本概念，本节中我们来看看如何通过查询转换来优化检索效果。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_25.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_27.png)

## 什么是查询转换？

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_29.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_31.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_33.png)

查询转换是为了更好地检索信息，对原始检索问题进行重写或修改的一系列方法。简单来说，就是将用户提出的问题，用不同的方式重新表达，再进行检索。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_35.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_37.png)

根据LangChain官方的技术解释，RAG检索通常先将文本向量化，然后进行相似度搜索。这种检索方式容易受到具体措辞和表达的影响，难以捕捉问题真实的语义，从而导致检索效果不佳，文档召回率较低。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_39.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_41.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_43.png)

为了解决这个问题，我们可以借鉴“三个臭皮匠，顶个诸葛亮”的原理。单一角度的查询可能不全面，但通过多个不同角度或不同表达方式的查询进行协作和互补，就能获得比单一查询更好的检索结果。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_45.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_47.png)

## 四种查询转换方法

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_49.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_51.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_53.png)

以下是四种主要的查询转换方法，它们之间的关系可以通过一个概念图来理解：以原始用户查询为中心，横向生成相似的查询，向上生成更抽象的查询，向下生成更具体的子问题。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_55.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_57.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_59.png)

### 1. 多查询生成 (Multi Query)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_61.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_63.png)

这种方法通过重写或改写原始问题，生成多个语义相似的查询。其原理是，从多个略微不同的角度提问，可以克服单一查询在向量相似度搜索中的局限性，提高检索到相关文档的概率。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_65.png)

以下是该方法的典型提示词示例，它清晰地说明了任务、场景和目的：

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_67.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_69.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_71.png)

```text
你是一个人工智能语言模型助手。你的任务是生成五个不同版本的用户问题，用于从向量数据库中检索相关的文档。通过从多个角度生成用户问题，你的目标是帮助用户克服基于距离相似度搜索的一些限制。请提供这些替代问题，并用换行符分割。
原始问题：{原始问题}
```

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_73.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_75.png)

### 2. 问题分解 (Decomposition)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_77.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_79.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_81.png)

对于复杂或抽象的问题，可以将其分解为多个更具体、更容易检索的子问题。这种方法主要也是一个提示词工程。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_83.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_85.png)

处理子问题检索结果时，通常有两种策略：
*   **递归回答**：按顺序解答子问题，并将前一个问题的答案作为上下文，输入到下一个问题的解答过程中。
*   **独立回答后合并**：并行地独立解答所有子问题，然后将所有答案整合，最后用大语言模型进行一次综合性的最终回答。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_87.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_89.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_91.png)

### 3. 退一步提问 (Step Back Prompting)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_93.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_95.png)

与分解相反，这种方法是将具体问题总结、概括为一个更抽象、更本质的问题。先使用抽象后的问题进行检索，可以获得更通用、更原理性的背景知识。在生成最终答案时，需要结合抽象问题检索到的文档和原始问题检索到的具体文档。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_97.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_99.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_101.png)

### 4. 假设文档嵌入 (HyDE)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_103.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_105.png)

这种方法先让大语言模型根据原始问题“假设”一个答案（即使这个答案可能不准确），然后基于这个生成的假设答案文本来进行检索。其思想是，生成的答案在语言风格和语义上可能与知识库中的相关文档更接近，从而能检索到更匹配的文档。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_107.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_109.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_111.png)

下图对比了标准RAG与HyDE的流程差异：
*   **标准RAG**：`用户问题 -> 检索 -> 相关文档`
*   **HyDE**：`用户问题 -> LLM生成假设答案 -> 基于假设答案检索 -> 相关文档`

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_113.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_115.png)

## 结果融合策略

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_117.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_119.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_121.png)

当我们通过上述方法获得了多组检索结果后，需要一种策略将它们合并，以生成最终答案。这就是结果融合。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_123.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_125.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_127.png)

### 简单去重合并

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_129.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_131.png)

最简单直接的方法是将所有检索到的文档进行去重，然后全部输入给大语言模型来生成答案。这种方法简单粗暴，但最终答案的质量完全依赖于大语言模型从海量文本中提取和整合信息的能力。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_133.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_135.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_137.png)

### RAG-Fusion 重排序

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_139.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_141.png)

这是一种更精细的融合算法。它根据同一篇文档在多个子查询检索结果列表中的排名位置，对其进行重新打分和排序。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_143.png)

其核心公式可以理解为对文档 `d` 计算一个新的相关性分数 `S_new`：
`S_new(d) = f( rank_1(d), rank_2(d), ..., rank_n(d) )`
其中，`rank_i(d)` 表示文档 `d` 在第 `i` 个子查询检索结果中的排名，`f` 是一个融合函数（如倒数排名融合）。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_145.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_147.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_149.png)

这样做的优点是，那些在多个查询结果中都排名靠前的文档，其综合相关性更高。当只需要选择前K个文档进行生成时，这种方法能确保选出的文档质量更优。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_151.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_153.png)

## 总结

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_155.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_157.png)

本节课我们一起学习了RAG中查询转换的四种核心方法：**多查询生成**、**问题分解**、**退一步提问**和**假设文档嵌入**。这些方法本质上都是通过设计不同的提示词，引导大语言模型对原始查询进行再表达，从而提升检索效果。此外，我们还了解了**简单去重合并**和**RAG-Fusion重排序**这两种结果融合策略，用于整合多路检索的成果。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_159.png)

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_161.png)

理解这些方法后，你可以尝试在实践组合使用它们，例如先用“退一步提问”获取背景知识，再用“问题分解”处理具体细节，最后用RAG-Fusion合并结果，观察是否能获得更精准、更全面的答案。