# 028：词嵌入 📚

在本节课中，我们将要学习**词嵌入**。词嵌入是大型语言模型中非常重要的技术，它能将文本转换为向量，从而让我们能够比较不同文本之间的相似性。

## 概述

上一节我们介绍了大型语言模型的基础，本节中我们来看看**词嵌入**。词嵌入的核心作用是将文本（如单词、句子）转换为固定长度的数值向量。这使得计算机能够通过计算向量之间的距离或角度，来量化地衡量文本之间的语义相似性，而不仅仅是进行字面上的精确匹配。

![](img/b95a1272b3979f7081f949e084c8e015_1.png)

## 环境准备与安装

以下是开始使用词嵌入前需要完成的准备工作。

![](img/b95a1272b3979f7081f949e084c8e015_3.png)

首先，我们需要安装必要的库。这里我们将使用ChromaDB和OpenAI的API来生成词嵌入。

![](img/b95a1272b3979f7081f949e084c8e015_5.png)

```python
# 安装必要的包
!pip install chromadb openai langchain
```

使用OpenAI的API需要有效的API密钥。你可以在课程早期部分学习如何获取。请将密钥妥善保存在你的Google Colab环境变量中，以便代码访问。

## 选择嵌入模型

![](img/b95a1272b3979f7081f949e084c8e015_7.png)

目前，OpenAI提供了多种文本嵌入模型。本课程主要关注两个模型：`text-embedding-3-large`（大型）和`text-embedding-3-small`（小型）。选择模型时需要考虑几个因素：

![](img/b95a1272b3979f7081f949e084c8e015_8.png)

![](img/b95a1272b3979f7081f949e084c8e015_10.png)

*   **性能与精度**：大型模型通常能生成更精确的嵌入向量，使语义相似的句子在向量空间中也更接近。
*   **速度**：大型模型生成嵌入所需时间更长，不适合实时性要求高的场景。
*   **成本**：大型模型的计算成本更高。
*   **计算资源与吞吐量**：大型模型对资源的需求更大。

考虑到课程演示的目的，我们推荐使用`text-embedding-3-small`模型，并通过LangChain来调用它。这样做的好处是，如果未来需要切换服务提供商（例如从OpenAI切换到Google的Gemini），代码能保持较好的兼容性。

## 生成词嵌入

![](img/b95a1272b3979f7081f949e084c8e015_12.png)

现在，让我们实际生成两个文本的词嵌入，并观察其特点。

```python
from langchain.embeddings import OpenAIEmbeddings

![](img/b95a1272b3979f7081f949e084c8e015_14.png)

# 初始化嵌入模型
embedding_model = OpenAIEmbeddings(model="text-embedding-3-small")

![](img/b95a1272b3979f7081f949e084c8e015_15.png)

![](img/b95a1272b3979f7081f949e084c8e015_16.png)

![](img/b95a1272b3979f7081f949e084c8e015_17.png)

![](img/b95a1272b3979f7081f949e084c8e015_18.png)

# 创建两个文本
text1 = "dog"
text2 = "A machine that helps people cut grass."

# 生成嵌入向量
embedding1 = embedding_model.embed_query(text1)
embedding2 = embedding_model.embed_query(text2)

![](img/b95a1272b3979f7081f949e084c8e015_20.png)

# 打印嵌入向量的长度
print(f"‘{text1}’ 的嵌入向量长度: {len(embedding1)}")
print(f"‘{text2}’ 的嵌入向量长度: {len(embedding2)}")
```

运行上述代码，你会发现两个长度完全相同的向量。无论输入文本是一个单词还是一个长句，该嵌入模型都会输出一个固定长度的向量（例如1536维）。这是为了便于后续的向量比较运算。不同的嵌入模型可能产生不同长度的向量。

## 理解嵌入向量

![](img/b95a1272b3979f7081f949e084c8e015_22.png)

那么，这个嵌入向量具体是什么样子呢？它本质上是一个高维空间中的点，由一系列浮点数表示。

```python
# 查看‘dog’的嵌入向量（只显示前10个维度作为示例）
print(f"‘dog’的嵌入向量（前10维）: {embedding1[:10]}")
```

![](img/b95a1272b3979f7081f949e084c8e015_24.png)

输出将显示一个数值列表，这些数字通常集中在0附近。这个向量就是文本在高维语义空间中的“坐标”。

![](img/b95a1272b3979f7081f949e084c8e015_26.png)

![](img/b95a1272b3979f7081f949e084c8e015_28.png)

## 比较嵌入向量

生成了嵌入向量后，我们就可以比较它们的相似性了。有多种方法可以计算两个向量之间的相似度。

以下是几种常见的相似度度量方法：

![](img/b95a1272b3979f7081f949e084c8e015_30.png)

*   **余弦相似度**：这是OpenAI推荐的方法。它计算两个向量之间的夹角余弦值，值域为[-1, 1]，值越接近1表示越相似。公式为：`相似度 = (A·B) / (||A|| * ||B||)`。
*   **欧氏距离**：计算两个向量在空间中的直线距离。距离越近，表示越相似。
*   **点积**：两个向量的点积也可以反映其相似性，但通常需要先对向量进行归一化处理。

![](img/b95a1272b3979f7081f949e084c8e015_32.png)

让我们使用余弦相似度来比较之前生成的两个嵌入向量。

![](img/b95a1272b3979f7081f949e084c8e015_34.png)

```python
import numpy as np
from numpy.linalg import norm

![](img/b95a1272b3979f7081f949e084c8e015_36.png)

def cosine_similarity(vec_a, vec_b):
    """计算两个向量的余弦相似度"""
    vec_a = np.array(vec_a)
    vec_b = np.array(vec_b)
    return np.dot(vec_a, vec_b) / (norm(vec_a) * norm(vec_b))

![](img/b95a1272b3979f7081f949e084c8e015_38.png)

# 计算相似度
similarity = cosine_similarity(embedding1, embedding2)
print(f"‘dog’ 与 ‘A machine that helps people cut grass.’ 的余弦相似度: {similarity:.4f}")
```

由于“狗”和“帮助人们割草的机器”在语义上关联不大，它们的相似度得分会较低。

## 实际应用示例

![](img/b95a1272b3979f7081f949e084c8e015_40.png)

![](img/b95a1272b3979f7081f949e084c8e015_41.png)

为了更直观地理解，我们可以创建一个函数来比较任意两个字符串的语义相似度。

![](img/b95a1272b3979f7081f949e084c8e015_43.png)

![](img/b95a1272b3979f7081f949e084c8e015_44.png)

```python
def compare_strings(str1, str2, model):
    """比较两个字符串的语义相似度"""
    emb1 = model.embed_query(str1)
    emb2 = model.embed_query(str2)
    sim = cosine_similarity(emb1, emb2)
    return sim

# 示例比较
str_a = “A device with blades to cut plants.”
str_b = “A machine that helps people cut grass.”
str_c = “An airplane.”

![](img/b95a1272b3979f7081f949e084c8e015_46.png)

![](img/b95a1272b3979f7081f949e084c8e015_48.png)

sim_ab = compare_strings(str_a, str_b, embedding_model)
sim_ac = compare_strings(str_a, str_c, embedding_model)

![](img/b95a1272b3979f7081f949e084c8e015_50.png)

print(f"‘{str_a}’ 与 ‘{str_b}’ 的相似度: {sim_ab:.4f}”)
print(f"‘{str_a}’ 与 ‘{str_c}’ 的相似度: {sim_ac:.4f}”)
```

你会发现，描述相似事物（割草设备）的句子对会有较高的相似度得分（接近1），而描述不相关事物（割草设备和飞机）的句子对得分则低得多。

## 总结

![](img/b95a1272b3979f7081f949e084c8e015_52.png)

本节课中我们一起学习了**词嵌入**的核心概念与应用。我们了解到，词嵌入是将文本转化为数值向量的关键技术，它使得计算机能够理解和比较文本的语义。我们实践了如何安装环境、选择模型、生成嵌入向量，并使用**余弦相似度**来量化文本之间的语义关联。这项技术是后续学习**检索增强生成**等高级应用的重要基础。