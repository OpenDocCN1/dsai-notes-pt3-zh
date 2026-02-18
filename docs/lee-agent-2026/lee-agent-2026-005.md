# 5：理解Transformer模型 - 作业三详解 📚

![](img/118b53e1858e091eb8d7a8cfd19fad62_1.png)

## 概述

![](img/118b53e1858e091eb8d7a8cfd19fad62_3.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_5.png)

在本节课中，我们将详细讲解李宏毅老师机器学习课程第三次作业“理解Transformer模型”的全部内容。本次作业旨在帮助大家深入理解大型语言模型和Transformer架构，核心是使用Google发布的Gemma 2B模型进行一系列实验和观念题回答。

---

![](img/118b53e1858e091eb8d7a8cfd19fad62_7.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_9.png)

## 作业概览与截止日期 📅

![](img/118b53e1858e091eb8d7a8cfd19fad62_11.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_13.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_15.png)

本次作业的截止日期是**4月4日23:59**。

作业主要分为两大部分：
1.  **Coding与问题回答**：包含四个主要实验，代码部分用于辅助回答观念题。
2.  **论文阅读**：需要阅读三篇指定论文并回答八个相关问题。

![](img/118b53e1858e091eb8d7a8cfd19fad62_17.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_19.png)

所有相关链接已在课程资料中提供。

![](img/118b53e1858e091eb8d7a8cfd19fad62_21.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_23.png)

---

## 第一部分：Coding与问题回答

这部分我们将通过实践来理解模型的不同方面。以下是四个主要实验环节。

![](img/118b53e1858e091eb8d7a8cfd19fad62_25.png)

### 1. Chat Template 对比实验 💬

![](img/118b53e1858e091eb8d7a8cfd19fad62_27.png)

上一节我们介绍了作业的整体结构，本节中我们来看看第一个实验：Chat Template对比。这个实验的主要目的是观察**有无使用Chat Template对模型回答质量的影响**。

![](img/118b53e1858e091eb8d7a8cfd19fad62_29.png)

我们将使用助教提供的Prompt，在示例代码中执行并回答问题。

![](img/118b53e1858e091eb8d7a8cfd19fad62_31.png)

以下是需要回答的三个子问题：
1.  分别填写有/无Chat Template时的Coherence Score（填空题，误差±0.5内均接受）。
2.  比较哪个分数更高（选择题）。
3.  解释实验并选出正确答案（多选题）。

![](img/118b53e1858e091eb8d7a8cfd19fad62_33.png)

**核心概念：Coherence Score**
我们使用 `cross-encoder` 模型作为开源的评分模型来计算模型回答的连贯性分数。其调用方式类似于以下代码：
```python
from sentence_transformers import CrossEncoder
model = CrossEncoder(‘model_name’)
scores = model.predict([(text1, text2)])
```

![](img/118b53e1858e091eb8d7a8cfd19fad62_35.png)

### 2. 多轮对话实验 🔄

![](img/118b53e1858e091eb8d7a8cfd19fad62_37.png)

理解了单轮对话的格式影响后，我们进入多轮对话实验。这部分邀请大家与模型进行多轮（大于一轮）的对话。

我们将提供对话历史记录，共进行三轮。每输入一次，模型会回应一个输出，然后可继续输入。

![](img/118b53e1858e091eb8d7a8cfd19fad62_39.png)

**请注意**：不要更改提供的对话历史，否则可能导致输出与预期不符。

![](img/118b53e1858e091eb8d7a8cfd19fad62_41.png)

以下是该部分的问题：
1.  提供在第三轮时，经过Chat Template格式化后的Prompt（注意：是输入被包装后的形式，不是模型输出）。
2.  回答在第一轮中，概率最高的token是什么（填空题）。
3.  选出关于多轮对话的错误叙述（选择题）。

![](img/118b53e1858e091eb8d7a8cfd19fad62_43.png)

### 3. Tokenization 与 Embedding 实验 🔤

![](img/118b53e1858e091eb8d7a8cfd19fad62_45.png)

接下来，我们将探讨模型如何处理文本输入。这部分是关于Tokenization（分词）的实验。

![](img/118b53e1858e091eb8d7a8cfd19fad62_47.png)

助教提供了一个希望被分词的Prompt，请大家不要更改。这是一个填空题，需要大家实际编写代码将一个句子进行分词。

![](img/118b53e1858e091eb8d7a8cfd19fad62_49.png)

实作完成后，你会得到类似下面的形式，并需要回答表格中挖空的1、2、3、4处对应的 `token id` 和 `token` 分别是什么。
```
Tokens: [‘<bos>‘, ‘Hello’, ‘,’, ‘ world’, ‘!’]
Token IDs: [2, 12345, 6, 23456, 8]
```

![](img/118b53e1858e091eb8d7a8cfd19fad62_51.png)

### 4. 自回归生成与采样策略实验 🎲

![](img/118b53e1858e091eb8d7a8cfd19fad62_53.png)

在学会了基础的分词后，我们来看看模型如何生成文本。这部分主要涉及使用**自回归生成**方式生成20个句子。

![](img/118b53e1858e091eb8d7a8cfd19fad62_55.png)

我们的评分标准是 **Self-BLEU Score**，用于衡量生成文本的多样性。自回归生成有两种主要采样方式：`top-k` 和 `top-p`，调整K和P的值会影响生成句子的多样性。

![](img/118b53e1858e091eb8d7a8cfd19fad62_57.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_59.png)

以下是需要完成的步骤和问题：
1.  使用助教提供的Prompt进行自回归生成。
2.  回答什么是Self-BLEU Score（参考文档）。
3.  理解 `top-k` 和 `top-p` 采样的区别（多选题）。
4.  调整参数，回答当 `K=1` 和 `P=0.0` 时生成的句子（填充题）。
5.  调整参数，比较 `K=2` 与 `K=200` 哪个Self-BLEU分数更高；比较 `P=0.6` 与 `P=0.999` 哪个分数更高（选择题）。

![](img/118b53e1858e091eb8d7a8cfd19fad62_61.png)

**核心概念：采样策略**
*   **Top-k采样**：从概率最高的k个token中随机选择。`model.generate(..., do_sample=True, top_k=50)`
*   **Top-p（核采样）**：从累积概率超过p的最小token集合中随机选择。`model.generate(..., do_sample=True, top_p=0.9)`

---

![](img/118b53e1858e091eb8d7a8cfd19fad62_63.png)

## 第二部分：模型内部机制可视化

![](img/118b53e1858e091eb8d7a8cfd19fad62_65.png)

我们将进一步深入模型内部，通过可视化工具理解其工作原理。

![](img/118b53e1858e091eb8d7a8cfd19fad62_67.png)

### 5. T-SNE 可视化实验 🗺️

首先，我们通过T-SNE降维来观察句子表示的分布。我们将可视化函数的代码写在示例中，同学直接执行并观察图片即可回答。

![](img/118b53e1858e091eb8d7a8cfd19fad62_69.png)

这部分问题分为：
1.  关于T-SNE的观念题（多选题，选出正确选项）。
2.  根据生成的T-SNE图进行观察回答（多选题，第2题选正确选项，第3题选不正确选项）。

![](img/118b53e1858e091eb8d7a8cfd19fad62_71.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_73.png)

### 6. Attention Map 可视化实验 👁️

![](img/118b53e1858e091eb8d7a8cfd19fad62_75.png)

注意力机制是Transformer的核心。这部分请大家绘制并观察**Attention Map**，它展示了句子中token与token之间的关联强度。

![](img/118b53e1858e091eb8d7a8cfd19fad62_77.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_79.png)

我们提供需要观察的Prompt、层号（layer index）和头索引（head index）。执行代码后，你可以生成对应的注意力热力图。

![](img/118b53e1858e091eb8d7a8cfd19fad62_81.png)

以下是相关问题：
1.  关于Attention Map的单选观念题。
2.  关于Attention Map的多选观念题。
3.  两道关于注意力机制的是非题（True/False）。

![](img/118b53e1858e091eb8d7a8cfd19fad62_83.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_85.png)

### 7. 稀疏自编码器（SAE）分析实验 🔍

![](img/118b53e1858e091eb8d7a8cfd19fad62_87.png)

最后，我们使用 **GemmaScope** 工具来分析模型的稀疏自编码器特征。这部分旨在理解模型内部激活的稀疏表示。

![](img/118b53e1858e091eb8d7a8cfd19fad62_89.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_91.png)

我们需要观察 `feature 10004` 所代表的意义及其激活密度（Activation Density）。这是一个多选题。

![](img/118b53e1858e091eb8d7a8cfd19fad62_93.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_95.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_97.png)

**实验对比分析：**
*   **问题 7.2 & 7.3**：比较两个不同Prompt（Prompt A, Prompt B）在 `feature 10004` 上的最大激活值（Max Activation）哪个更大，并解释原因。**提示**：可参考激活分布图。
*   **问题 7.4 – 7.6**：针对同一Prompt，在固定的第24层，观察不同token的激活分布图并回答问题。
*   **问题 7.7 – 7.9**：针对同一Prompt和同一token，观察不同层的激活分布。**提示**：你可以调整token索引，观察在浅层和深层，激活值的变化趋势。

![](img/118b53e1858e091eb8d7a8cfd19fad62_99.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_101.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_103.png)

---

![](img/118b53e1858e091eb8d7a8cfd19fad62_105.png)

## 第三部分：论文阅读与回答 📖

![](img/118b53e1858e091eb8d7a8cfd19fad62_107.png)

这部分要求大家阅读三篇指定的学术论文，并根据理解回答八个相关问题。所有问题均发布在Gradescope系统上。

![](img/118b53e1858e091eb8d7a8cfd19fad62_109.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_111.png)

---

![](img/118b53e1858e091eb8d7a8cfd19fad62_113.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_115.png)

## 作业提交与评分 📝

![](img/118b53e1858e091eb8d7a8cfd19fad62_117.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_119.png)

### 代码提交
虽然作业以观念题为主，但仍需提交可执行的代码以供复核。
*   **格式**：学号_hw3.zip 压缩包，内含Python Notebook文件。
*   **要求**：必须是一个可以重新运行并复现结果的文档。
*   **注意**：NTU COOL系统只接受最后一次提交。若代码无法运行或复现，分数将受影响。

![](img/118b53e1858e091eb8d7a8cfd19fad62_121.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_123.png)

### 答题平台（Gradescope）
所有观念题均在Gradescope上作答。
*   **登录**：使用学校账号（NTU COOL）登录。
*   **评分**：本次作业满分均基于Gradescope上的答案。
*   **重要**：**即使Gradescope答题满分，若未在NTU COOL上提交代码，仍无法获得分数。**

![](img/118b53e1858e091eb8d7a8cfd19fad62_125.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_127.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_129.png)

### 截止日期与学术规范
*   **截止日期**：**4月10日 23:59**（NTU COOL 与 Gradescope 同步）。
*   **学术诚信**：严禁作弊、抄袭或分享代码。引用外部资源需在代码中注明。违规将导致分数折扣、作业零分甚至课程不及格。

![](img/118b53e1858e091eb8d7a8cfd19fad62_131.png)

### 问题咨询
*   **优先使用讨论区**：请在课程讨论区（Homework 3板块）公开提问，助教会优先回复，利于其他同学参考。
*   **邮件咨询**：个别问题可邮件助教，**标题请务必加上“[Homework 3]”**。
*   **线下答疑**：时间为周五课前（13:20-14:00）或课后（17:20-18:00）。

![](img/118b53e1858e091eb8d7a8cfd19fad62_133.png)

---

![](img/118b53e1858e091eb8d7a8cfd19fad62_135.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_137.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_139.png)

## 代码执行指南 💻

以下是运行示例代码的关键步骤指引：

![](img/118b53e1858e091eb8d7a8cfd19fad62_141.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_143.png)

1.  **创建副本**：首先在Colab中创建笔记本副本。
2.  **检查环境**：检查并确保有GPU可用。
3.  **安装依赖**：安装指定版本的 `transformers` 库（建议使用 `4.47.0` 以保证稳定性）。
    ```bash
    pip install transformers==4.47.0
    ```
4.  **配置令牌**：将你在Hugging Face获取的 `access token` 填入代码指定位置，用于下载模型。
5.  **下载模型**：运行单元格下载Gemma 2B模型。**注意**：回答任何独立问题前，都需要先运行此步骤下载模型。
6.  **按部分执行**：依次执行各问题对应的代码单元格，观察输出结果，并在Gradescope上作答。
    *   **Q1**：生成模型回复并计算Coherence Score。
    *   **Q2**：观察多轮对话中Chat Template的格式化结果。
    *   **Q3**：实作分词功能，获取 `token ids` 和 `tokens`。
    *   **Q4**：调整 `top_k` 和 `top_p` 参数生成文本，并计算Self-BLEU分数。
    *   **Q5**：执行T-SNE可视化代码，观察图表。
    *   **Q6**：从模型输出中提取 `attention scores` 并可视化Attention Map。
    *   **Q7**：安装SAE分析工具包，下载GemmaScope，运行可视化函数观察特征激活。

![](img/118b53e1858e091eb8d7a8cfd19fad62_145.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_147.png)

---

![](img/118b53e1858e091eb8d7a8cfd19fad62_149.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_151.png)

## 总结

![](img/118b53e1858e091eb8d7a8cfd19fad62_153.png)

![](img/118b53e1858e091eb8d7a8cfd19fad62_155.png)

本节课中我们一起学习了第三次作业“理解Transformer模型”的完整内容。我们从Chat Template的影响、多轮对话、分词基础，深入到自回归生成、注意力机制可视化和稀疏特征分析，完成了一次对LLM内部运作机制的全面探索。请大家按照指南完成实验、阅读论文，并在截止日期前提交代码和答案。祝大家学习顺利！