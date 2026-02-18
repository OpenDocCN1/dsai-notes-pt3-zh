# 26：如何为RAG选择Embedding模型？ 🤔

在本节课中，我们将学习如何为检索增强生成（RAG）系统选择合适的Embedding模型。Embedding模型是RAG技术的核心，它负责将文本转换为向量表示，其质量直接影响信息检索的效果和最终生成文本的质量。我们将通过分析模型流行度、下载量以及性能评测结果，来探讨如何做出明智的选择。

![](img/2b99727d4ca74c721de3c6decc7547ad_1.png)

![](img/2b99727d4ca74c721de3c6decc7547ad_3.png)

## 引言：为何选择Embedding模型至关重要

![](img/2b99727d4ca74c721de3c6decc7547ad_5.png)

在构建RAG系统时，开发者会面临众多Embedding模型的选择。这些模型性能各异，处理速度、生成的向量维度也各不相同。一个合适的模型能显著提升检索的准确性和效率。

![](img/2b99727d4ca74c721de3c6decc7547ad_7.png)

## 模型选择的常见考量因素

![](img/2b99727d4ca74c721de3c6decc7547ad_9.png)

以下是开发者在选择Embedding模型时通常会考虑的几个关键标准：

![](img/2b99727d4ca74c721de3c6decc7547ad_11.png)

*   **模型性能**：在特定任务（如检索）上的准确度。
*   **处理速度**：模型编码文本的效率。
*   **向量维度**：Embedding向量的长度，影响存储和计算成本。
*   **通用性**：模型在不同类型文本和任务上的稳定表现。

![](img/2b99727d4ca74c721de3c6decc7547ad_13.png)

## 评估模型流行度：Hugging Face趋势与下载量

![](img/2b99727d4ca74c721de3c6decc7547ad_15.png)

上一节我们介绍了选择模型的一般标准，本节中我们来看看如何利用社区数据来评估模型的受关注程度。我们主要参考Hugging Face平台上的两个指标：最新趋势和月度下载量。

![](img/2b99727d4ca74c721de3c6decc7547ad_17.png)

### 最新趋势排名

在Hugging Face上搜索“embedding”关键词，按趋势排序（即近期下载量增长最快的模型），排名前五的模型如下：

![](img/2b99727d4ca74c721de3c6decc7547ad_19.png)

1.  **bce-embedding-base_v1**：随着QAnything项目流行而热度上升。
2.  **cs_roberta**：一款基于RoBERTa架构的模型。
3.  **acge_text_embedding**：在中文评测榜MTEB上排名靠前的模型，近期趋势显著。

### 月度下载量排名

月度下载量能反映模型当前受关注的程度。以下是部分高下载量的模型系列：

*   **BGE系列**：特别是`BAAI/bge-large-zh-v1.5`（中文优化版），月下载量接近200万，关注度极高。
*   **GTE系列**：如`thenlper/gte-base`（英文版）也有超过百万的下载量。
*   **E5系列**：`intfloat/multilingual-e5-large`（多语言版）下载量达81万。
*   **BCE系列**：`maidalun1020/bce-embedding-base_v1`（中英双语）下载量为46万。
*   **M3E系列**：`moka-ai/m3e-base`（中英双语）下载量为10万。

![](img/2b99727d4ca74c721de3c6decc7547ad_21.png)

根据以上数据，主流的模型系列包括**BGE、GTE、E5、BCE、M3E**等。对于中文任务，可以重点关注 `BAAI/bge-large-zh-v1.5`、`intfloat/multilingual-e5-large`、`maidalun1020/bce-embedding-base_v1`、`moka-ai/m3e-base` 以及 `acge_text_embedding`。

![](img/2b99727d4ca74c721de3c6decc7547ad_23.png)

## 评估模型性能：中英双语与中文任务对比

了解了模型的流行度后，我们还需要用性能数据说话。性能评估可以参考MTEB排行榜，但更可靠的方法是查看具体的评测结果。我们主要参考QAnything官方文档中的对比数据。

![](img/2b99727d4ca74c721de3c6decc7547ad_25.png)

### 中英双语任务性能

![](img/2b99727d4ca74c721de3c6decc7547ad_27.png)

![](img/2b99727d4ca74c721de3c6decc7547ad_29.png)

以下是部分模型在检索任务上的表现（得分越高越好）：

![](img/2b99727d4ca74c721de3c6decc7547ad_31.png)

*   **`bce-embedding-base_v1`**：性能最佳。
*   **`multilingual-e5-large`**：表现次之。
*   **`bge-large-zh`** 与 **`m3e-base`**：表现接近，但与前两名有约10个百分点的差距。

![](img/2b99727d4ca74c721de3c6decc7547ad_33.png)

### 纯中文任务性能

![](img/2b99727d4ca74c721de3c6decc7547ad_35.png)

在纯中文检索任务上，模型的排名发生了显著变化：

1.  **`gte-large-zh`**：表现最为出色，检索得分超过70。
2.  **`bge-large-zh`**：表现同样优秀。
3.  **`multilingual-e5-large`** 与 **`m3e-base`**：紧随其后。
4.  **`bce-embedding-base_v1`**：在此项排名中相对靠后。

![](img/2b99727d4ca74c721de3c6decc7547ad_37.png)

![](img/2b99727d4ca74c721de3c6decc7547ad_39.png)

这个对比说明，即使是通用的热门模型，在不同语言任务上的表现也可能差异很大。例如，`bge-large-zh`（中文版）在中文任务上远超其英文版本。因此，选择模型必须针对自己的具体任务（如主要处理中文还是多语言）进行评测。

![](img/2b99727d4ca74c721de3c6decc7547ad_41.png)

## 模型推荐清单 🏆

综合流行度、下载量及性能评测，以下是为**中文任务优先、追求性能**（暂不考虑计算成本）的开发者推荐的几个Embedding模型：

1.  **`maidalun1020/bce-embedding-base_v1`**
    *   **理由**：在中英双语检索任务上性能领先，是热门项目QAnything的选用模型，社区关注度高（下载量46万）。
2.  **`intfloat/multilingual-e5-large`**
    *   **理由**：强大的多语言模型，自然支持中文，下载量巨大（81万），性能经过广泛验证。
3.  **`thenlper/gte-large-zh`**
    *   **理由**：在纯中文检索任务上表现最佳，尽管总下载量相对较小，但针对中文场景效果突出。
4.  **`acge_text_embedding`**
    *   **理由**：新发布的模型，近期趋势上升非常快（月下载5万），值得保持关注以观察其长期性能。

![](img/2b99727d4ca74c721de3c6decc7547ad_43.png)

> **提示**：最终选择前，建议在您的实际业务数据上进行小规模测试，以确认模型效果。

![](img/2b99727d4ca74c721de3c6decc7547ad_45.png)

## 总结

![](img/2b99727d4ca74c721de3c6decc7547ad_47.png)

![](img/2b99727d4ca74c721de3c6decc7547ad_49.png)

本节课中我们一起学习了为RAG系统选择Embedding模型的方法。我们首先明确了模型性能、速度等选择标准，然后通过分析Hugging Face的流行趋势和下载量来了解社区选择，最后深入对比了不同模型在中英双语和纯中文任务上的性能差异。关键结论是：**没有“一刀切”的最佳模型，需要根据任务语言和具体需求进行评测**。希望推荐的模型清单能为您的项目提供一个可靠的起点。