# 15：L12 - 文本生成解码与评估 📝

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_1.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_3.png)

在本节课中，我们将要学习文本生成流程中的两个关键组成部分：**解码**与**评估**。我们将以机器翻译为主要示例，探讨如何从训练好的模型中生成文本，以及如何衡量生成文本的质量。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_5.png)

---

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_7.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_9.png)

## 🧠 解码：从模型获取文本

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_11.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_13.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_15.png)

上一节我们介绍了如何训练文本生成模型。本节中我们来看看在测试时如何从模型中获取输出文本，这个过程称为**解码**。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_17.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_19.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_21.png)

在机器翻译等任务中，我们的目标是找到给定输入句子条件下，概率最高的目标语言句子。这可以表示为寻找 `argmax P(E|F)`，其中 `E` 是目标语句，`F` 是源语句。然而，枚举所有可能的句子在计算上是不可行的，因此我们需要近似方法。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_23.png)

以下是几种常见的解码策略：

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_25.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_26.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_28.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_30.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_31.png)

### 贪婪解码
这是最简单的方法。在每个时间步，模型预测一个词汇表上的概率分布，我们直接选择概率最高的词作为输出，并将其作为下一个时间步的输入。此方法简单快速，但存在明显问题：早期的错误决策无法修正，且容易导致重复或不连贯的输出。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_33.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_34.png)

### 束搜索
为了克服贪婪解码的局限性，束搜索允许我们同时考虑多个候选序列。它维护一个大小为 `k` 的“束”，其中包含当前概率最高的 `k` 个部分翻译。在每个时间步，它为束中的每个候选扩展下一个可能的词，然后仅保留总概率最高的 `k` 个新候选。这个过程持续进行，直到所有候选都生成了序列结束符。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_36.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_38.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_40.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_41.png)

**核心公式**：束搜索的目标是近似最大化序列概率 `P(y1, y2, ..., yT | x) = ∏ P(yt | y<t, x)`，同时通过束宽 `k` 控制搜索空间。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_43.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_44.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_45.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_46.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_48.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_49.png)

束搜索通常能产生比贪婪解码质量更高的输出，尤其适用于机器翻译等需要准确性的任务。但它也存在偏向生成较短序列的问题，且增大束宽并不总是能提升最终评估指标。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_51.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_53.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_55.png)

### 基于采样的解码
对于故事生成、对话等需要创造性和多样性的任务，我们可能不希望总是选择最可能的词。此时可以采用采样策略。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_57.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_59.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_60.png)

*   **纯采样**：在每个时间步，根据模型输出的概率分布随机采样下一个词。这能产生多样化的输出，但也可能生成低概率或不连贯的序列。
*   **Top-k 采样**：仅从模型认为最可能的 `k` 个词中采样。这平衡了多样性与质量。
*   **核采样（Top-p 采样）**：从一个最小候选集合中采样，使得这些候选的累计概率达到 `p`。候选词数量动态变化，能更好地适应不同时间步的概率分布。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_62.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_63.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_65.png)

**核心总结**：贪婪解码很少使用；束搜索适用于翻译等约束性强的任务；采样方法更适合开放性的创意生成任务。

---

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_67.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_69.png)

## 📊 评估：衡量生成文本的质量

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_71.png)

上一节我们探讨了如何生成文本，本节中我们来看看如何评估生成文本的质量。我们将重点讨论机器翻译的评估，但其思想也适用于其他生成任务。

评估生成文本主要关注两个维度：
1.  **充分性**：输出是否传达了输入的全部含义？
2.  **流畅性**：输出是否语法正确、读起来自然？

最可靠的评估方法是**人工评估**，但成本高昂、耗时长且主观。因此，我们通常依赖**自动评估指标**。

### BLEU 分数
BLEU 是机器翻译中最常用的自动评估指标。它通过比较模型输出与一个或多个参考翻译之间的 **n-gram 重叠度** 来打分。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_73.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_75.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_77.png)

**核心公式**：
`BLEU = BP * exp( ∑ wn * log pn )`
其中：
*   `pn` 是 n-gram 精度（n 通常取 1 到 4）。
*   `wn` 是权重。
*   `BP` 是简短惩罚因子，用于惩罚过短的输出。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_79.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_81.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_83.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_85.png)

BLEU 计算简单快捷，并且与人工判断有一定相关性。但它也存在局限：它主要基于表面形式的匹配，无法深入理解语义；在只有单个参考翻译时效果会打折扣；并且人类翻译的 BLEU 分数也可能不高。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_87.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_89.png)

### 其他评估趋势
近年来，研究者开始探索利用 BERT 等大型预训练语言模型进行更深入的评估，例如通过计算生成文本与参考文本在语义空间中的相似度。这些方法有望更好地捕捉语义充分性。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_91.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_93.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_95.png)

---

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_97.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_99.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_100.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_102.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_103.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_104.png)

## 🎯 课程总结

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_106.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_108.png)

本节课中我们一起学习了文本生成流程的解码与评估环节。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_109.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_110.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_111.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_113.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_115.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_117.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_119.png)

*   在**解码**部分，我们比较了贪婪解码、束搜索和基于采样的方法，了解了它们各自的适用场景。
*   在**评估**部分，我们介绍了以 BLEU 分数为代表的自动评估指标，理解了其工作原理与局限性。

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_121.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_123.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_125.png)

![](img/dda44bca5d0acc4c45dc4ac3368e0d35_127.png)

选择合适的解码策略和评估指标对于构建高质量的文本生成系统至关重要，需要根据具体任务的目标和数据特点进行权衡。