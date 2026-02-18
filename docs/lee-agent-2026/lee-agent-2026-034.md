# 34：自查询检索器 🧠🔍

![](img/b0e47fb6e7d3e22a873f362445767ef9_1.png)

在本节课中，我们将学习 LangChain 中的第五种检索器——自查询检索器。我们将了解它的核心概念、工作原理，并通过一个简单的代码示例来演示其使用方法。

---

![](img/b0e47fb6e7d3e22a873f362445767ef9_3.png)

## 概述

![](img/b0e47fb6e7d3e22a873f362445767ef9_5.png)

自查询检索器是一种能够将自然语言查询转换为结构化查询，并结合向量存储中的元数据进行高效检索的组件。它的核心优势在于结合了语义相似性搜索和基于元数据的结构化过滤。

![](img/b0e47fb6e7d3e22a873f362445767ef9_7.png)

上一节我们介绍了其他类型的检索器，本节中我们来看看自查询检索器如何工作。

---

## 自查询检索器简介

自查询检索器具备自行发起查询的能力。当用户使用自然语言提问时，该检索器会利用一个大语言模型链来构建一个结构化查询。随后，它使用这个结构化查询与向量存储进行交互。

这使得它不仅能评估查询与文档之间的语义相似性，还能根据文档的元数据执行过滤操作。自查询检索器的核心竞争力在于**语义查询与结构化查询的结合**。

---

![](img/b0e47fb6e7d3e22a873f362445767ef9_9.png)

## 核心组件与工作流程

以下是自查询检索器的主要组件及其交互方式示意图：

![](img/b0e47fb6e7d3e22a873f362445767ef9_11.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_13.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_7.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_15.png)

1.  **文档处理**：原始文档被拆分为多个分块。每个分块可以附加元数据。
2.  **向量存储**：文档分块及其元数据经过文本嵌入后，存入向量数据库。
3.  **查询构建器**：基于用户查询和大语言模型，生成一个结构化的查询语句。
4.  **查询翻译器**：将结构化查询翻译成底层向量数据库支持的特定查询或过滤语句。

![](img/b0e47fb6e7d3e22a873f362445767ef9_17.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_19.png)

当用户查询发送给检索器时，流程如下：
*   查询构建器首先根据用户查询和已知的元数据字段生成结构化查询。
*   查询翻译器将此结构化查询转换为向量存储能理解的语句。
*   最终，检索器结合语义相似性和元数据过滤条件返回结果。

![](img/b0e47fb6e7d3e22a873f362445767ef9_21.png)

---

![](img/b0e47fb6e7d3e22a873f362445767ef9_23.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_25.png)

## 代码实践：构建自查询检索器

![](img/b0e47fb6e7d3e22a873f362445767ef9_27.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_29.png)

接下来，我们通过一个简单的 Python Notebook 来演示自查询检索器的使用。本节将重点展示两点：
1.  如何基于文档元数据进行查询。
2.  如何利用大语言模型链生成查询参数，并将其翻译为向量存储的查询语句。

![](img/b0e47fb6e7d3e22a873f362445767ef9_31.png)

### 环境准备

![](img/b0e47fb6e7d3e22a873f362445767ef9_33.png)

首先，需要安装必要的 Python 包。

![](img/b0e47fb6e7d3e22a873f362445767ef9_35.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_37.png)

```python
# 安装所需库
!pip install langchain openai chromadb tiktoken lark
```

![](img/b0e47fb6e7d3e22a873f362445767ef9_39.png)

**注意**：官方示例中使用的是 Pinecone 向量数据库。本教程使用 ChromaDB 进行演示，因此对示例数据进行了调整（例如，将元数据中的数组类型字段改为字符串），以确保兼容性。

![](img/b0e47fb6e7d3e22a873f362445767ef9_41.png)

### 准备数据与定义元数据

![](img/b0e47fb6e7d3e22a873f362445767ef9_43.png)

我们使用一组关于电影的硬编码数据。每份文档都包含内容及其元数据。

![](img/b0e47fb6e7d3e22a873f362445767ef9_45.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_47.png)

```python
from langchain.schema import Document

![](img/b0e47fb6e7d3e22a873f362445767ef9_49.png)

# 示例文档数据
docs = [
    Document(
        page_content="A movie about a robot learning to love.",
        metadata={"year": 2001, "rating": 8.2, "genre": "science fiction"}
    ),
    Document(
        page_content="A documentary about the ocean.",
        metadata={"year": 2010, "rating": 7.7, "genre": "documentary"}
    ),
    Document(
        page_content="A thriller about a hacker.",
        metadata={"year": 2015, "rating": 8.6, "genre": "thriller"}
    ),
    # ... 可以添加更多文档
]

![](img/b0e47fb6e7d3e22a873f362445767ef9_51.png)

# 定义元数据字段信息
metadata_field_info = [
    AttributeInfo(
        name="genre",
        description="The genre of the movie",
        type="string",
    ),
    AttributeInfo(
        name="year",
        description="The year the movie was released",
        type="integer",
    ),
    AttributeInfo(
        name="rating",
        description="A 1-10 rating for the movie",
        type="float",
    ),
]
```

![](img/b0e47fb6e7d3e22a873f362445767ef9_53.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_55.png)

### 创建自查询检索器

![](img/b0e47fb6e7d3e22a873f362445767ef9_57.png)

现在，我们使用定义好的文档和元数据信息来构建自查询检索器。

![](img/b0e47fb6e7d3e22a873f362445767ef9_59.png)

```python
from langchain.vectorstores import Chroma
from langchain.embeddings import OpenAIEmbeddings
from langchain.retrievers.self_query.base import SelfQueryRetriever
from langchain.chat_models import ChatOpenAI

![](img/b0e47fb6e7d3e22a873f362445767ef9_61.png)

# 1. 创建向量存储
vectorstore = Chroma.from_documents(docs, OpenAIEmbeddings())

# 2. 定义大语言模型
llm = ChatOpenAI(temperature=0)

# 3. 创建自查询检索器
retriever = SelfQueryRetriever.from_llm(
    llm,
    vectorstore,
    document_contents="Descriptions of movies", # 文档内容描述
    metadata_field_info=metadata_field_info,    # 元数据字段信息
)
```

### 执行查询

构建好检索器后，我们可以用它来进行各种查询。

以下是几种查询示例：

![](img/b0e47fb6e7d3e22a873f362445767ef9_63.png)

**1. 基于主题的常规查询**
```python
# 查询与“爱情”相关的电影
docs_result = retriever.get_relevant_documents("movies about love")
```

**2. 基于元数据过滤的查询**
```python
# 查询评分低于8分的电影
docs_result = retriever.get_relevant_documents("I want to watch a movie rated lower than 8")
# 将返回评分7.7的纪录片
```

**3. 结合查询与过滤**
```python
# 查询某位导演执导的关于女性的电影
# 检索器会从内容中查找“女性”相关语义，并过滤导演元数据
docs_result = retriever.get_relevant_documents("Are there any movies directed by [Director Name] about women?")
```

**4. 组合过滤器**
```python
# 查询评分高于8.5的惊悚片
docs_result = retriever.get_relevant_documents("Find a thriller movie with rating above 8.5")
```

![](img/b0e47fb6e7d3e22a873f362445767ef9_65.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_67.png)

### 深入原理：查看生成的结构化查询

![](img/b0e47fb6e7d3e22a873f362445767ef9_69.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_71.png)

我们可以查看检索器内部将自然语言转换成的结构化查询是什么样子。

![](img/b0e47fb6e7d3e22a873f362445767ef9_73.png)

```python
# 提出一个复杂查询
question = "Show me animated movies about toys made after 1990"
# 获取生成的结构化查询
structured_query = retriever.query_constructor.invoke({"query": question})
print(structured_query)
```
可能的输出结构：
```python
{
    'query': 'toys',           # 语义搜索的关键词
    'filter': {
        'operator': 'and',
        'operands': [
            {'field': 'genre', 'operator': 'eq', 'value': 'animated'},
            {'field': 'year', 'operator': 'gte', 'value': 1990}
        ]
    },
    'limit': None
}
```
这个结构化查询表示：寻找**类型为动画**、**年份大于等于1990年**且内容与“玩具”语义相关的文档。

![](img/b0e47fb6e7d3e22a873f362445767ef9_75.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_77.png)

### 使用 Limit 参数

![](img/b0e47fb6e7d3e22a873f362445767ef9_79.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_81.png)

自查询检索器支持通过自然语言限制返回结果的数量。

![](img/b0e47fb6e7d3e22a873f362445767ef9_83.png)

```python
# 在创建检索器时启用 limit 功能
retriever_with_limit = SelfQueryRetriever.from_llm(
    llm,
    vectorstore,
    document_contents="Descriptions of movies",
    metadata_field_info=metadata_field_info,
    enable_limit=True, # 启用 limit 功能
)

![](img/b0e47fb6e7d3e22a873f362445767ef9_85.png)

# 查询评分高于8的电影，但只返回1个结果
docs_result = retriever_with_limit.get_relevant_documents("Show me one movie with rating above 8")
# 即使有多部电影评分高于8，也只会返回1份文档
```

![](img/b0e47fb6e7d3e22a873f362445767ef9_87.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_89.png)

---

![](img/b0e47fb6e7d3e22a873f362445767ef9_91.png)

## 总结

![](img/b0e47fb6e7d3e22a873f362445767ef9_93.png)

![](img/b0e47fb6e7d3e22a873f362445767ef9_95.png)

本节课中我们一起学习了 LangChain 的自查询检索器。

![](img/b0e47fb6e7d3e22a873f362445767ef9_97.png)

我们了解到：
*   **自查询检索器**能够将自然语言查询转换为结合语义和元数据过滤的结构化查询。
*   它的核心组件包括**查询构建器**和**查询翻译器**，前者利用大语言模型生成查询，后者将其适配到底层向量数据库。
*   通过定义清晰的**元数据字段信息**，检索器可以智能地理解并执行复杂的过滤条件。
*   该检索器支持通过自然语言控制返回结果的数量（Limit 功能）。

![](img/b0e47fb6e7d3e22a873f362445767ef9_99.png)

自查询检索器极大地增强了检索系统的灵活性和准确性，使其能够更好地理解用户的复杂意图。你可以尝试将其用于构建问答链等更复杂的应用。