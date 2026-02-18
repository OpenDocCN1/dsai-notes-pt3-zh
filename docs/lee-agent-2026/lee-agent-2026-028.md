![](img/050197f4c6b1dd6e0058c7976d8ea5ab_0.png)

# 28：RAG系统中的ReRank模型详解 🎯

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_2.png)

在本节课中，我们将要学习RAG（检索增强生成）系统中一个关键的组件——ReRank模型。我们将探讨它的定义、作用、与Embedding模型的区别，以及如何在实际应用中选择合适的ReRank模型。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_4.png)

---

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_6.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_8.png)

上一节我们介绍了Embedding模型在RAG中的作用，本节中我们来看看另一个对系统性能有重要影响的模型——ReRank模型。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_10.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_12.png)

### 什么是ReRank模型？🤔

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_14.png)

ReRank模型位于RAG流程的第一步检索与大语言模型生成之间，通常被称为“二次检索”模型。它的作用是对第一步检索出来的文本块（trunks）进行重新排序。重新排序后的、相关性更高的文本再被送入大语言模型进行处理，以生成更准确的回答。

---

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_16.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_18.png)

了解了ReRank模型的基本定位后，我们自然会问：为什么我们需要它？

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_20.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_22.png)

### 为什么需要ReRank模型？🔍

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_24.png)

RAG技术虽然容易上手，但要达到满意的性能并不简单。其核心目标之一是找到与用户问题最相关的文档。然而，传统的Embedding模型在将长文本压缩为定长向量时，不可避免地会丢失部分信息，这常常导致检索的召回率不尽如人意。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_26.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_28.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_30.png)

为了提高召回率，一个直观的做法是选择相似度得分最高的多个文本一起输入给大模型。但这会带来两个新问题：
1.  文本过长时，大语言模型难以有效利用其中的所有信息。
2.  过长的上下文会影响大模型对用户指令的遵从能力。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_32.png)

因此，结论是必须努力提高检索的准确度。这正是引入ReRank模型的主要原因。通过对初步检索结果进行精细化重排序，ReRank模型能筛选出最相关的文本，从而在提高召回率的同时，帮助大模型生成更高质量的回答。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_34.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_36.png)

---

既然ReRank模型能提升排序质量，那么它与Embedding模型的具体区别在哪里？

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_38.png)

### ReRank模型与Embedding模型的区别 ⚖️

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_40.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_42.png)

以下是两种模型工作方式的对比：

**Embedding模型的工作流程：**
1.  预处理阶段，将所有文档文本通过Embedding模型转换为向量并存储。
2.  用户查询时，将问题也转换为向量。
3.  通过计算问题向量与所有文档向量的相似度（如余弦相似度）进行快速检索。
    ```python
    # 伪代码示例：基于向量的相似度计算
    query_vector = embed(用户问题)
    for doc_vector in 所有文档向量:
        similarity = cosine_similarity(query_vector, doc_vector)
    ```
    这种方式检索速度极快，适合海量数据。但核心问题在于信息压缩导致的信息丢失，可能影响检索精度。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_44.png)

**ReRank模型的工作流程：**
1.  在接收到用户问题和初步检索出的一组候选文档后。
2.  将“问题-文档对”直接输入ReRank模型。
3.  模型直接计算该问题与每个候选文档之间的相关性得分。
    ```python
    # 伪代码示例：ReRank模型计算相关性
    for candidate_doc in 候选文档列表:
        relevance_score = rerank_model(用户问题, candidate_doc)
    ```
    这种方式是“一对一”的精细化计算，针对性更强，因此通常能得到准确度更高的排序结果。可以说，相比Embedding模型的“批量服务”，ReRank模型提供了“VIP服务”。

---

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_46.png)

理解了ReRank模型的优势后，接下来我们面临一个实际问题：如何选择？

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_48.png)

### 如何选择ReRank模型？📊

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_50.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_52.png)

选择模型时，我们可以参考社区热度（如下载量）和公开的性能评测结果。以下是一些参考信息：

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_54.png)

**基于下载量的热门模型（数据统计于近期）：**
*   BAAI（智源）的模型社区影响力较大，其 `bge-reranker-base` 和 `bge-reranker-large` 下载量均达到34万次。
*   其他支持多语言的模型，如 `BCE-embedding` 系列，也可用于中文任务。
*   QAnything项目中使用的 `BCE-rerank-base_v1` 模型下载量为15K。
*   BAAI的 `layer-wise` 模型也值得关注。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_56.png)

**基于性能评测的参考：**
根据QAnything网站的评测结果，在中文及中英混合任务上，`BCE-rerank-base_v1` 模型性能表现优异，超过了BAAI的同类型模型。智源研究院也提供了其模型的最佳实践推荐：

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_58.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_60.png)

以下是针对不同场景的模型选择建议：
*   **多语言任务**：推荐使用 `bge-reranker-base` 或 `bge-reranker-large`。
*   **中英文任务**：推荐使用 `bge-reranker-base` 或 `BCE-rerank-base_v1`。
*   **追求执行效率**：推荐使用较小的模型，如 `bge-reranker-base` 或 `BCE-rerank-base_v1`。
*   **追求极致性能**：推荐使用 `layer-wise` 模型或 `BCE-rerank-large`。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_62.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_64.png)

根据在中文数据集上的实际测试，性能排序大致为：`BCE-rerank-base_v1` > BAAI `layer-wise` > `BCE-rerank-large`。建议开发者在自己的具体任务上进行测试验证。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_66.png)

---

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_68.png)

### 总结与思考 💡

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_70.png)

本节课中我们一起学习了ReRank模型。我们明确了它在RAG系统中作为“二次检索”器的角色，理解了它通过精细化“问题-文档对”计算来提升排序准确度的必要性，并对比了其与Embedding模型在原理和适用场景上的核心差异。最后，我们探讨了如何根据下载量、评测结果和具体任务需求（如语言、效率、精度）来选择合适的ReRank模型。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_72.png)

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_74.png)

最后，留给大家一个思考题：既然ReRank模型效果更好，为什么RAG系统通常还需要Embedding模型呢？在什么情况下，可以绕过Embedding模型，直接使用ReRank模型进行文档检索？欢迎在评论区分享你的见解。

![](img/050197f4c6b1dd6e0058c7976d8ea5ab_76.png)

感谢收看本课程。