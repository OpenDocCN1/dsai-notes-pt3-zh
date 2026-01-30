# 📚 课程 P103：Doc2vec 文档向量化教程

在本节课中，我们将学习如何将句子和文档表示为向量，以便用于分类任务。我们将从最简单的词袋模型开始，探讨其局限性，然后回顾词向量的核心思想，并最终扩展到文档向量（Doc2vec）的两种主要方法：分布式记忆模型和分布式词袋模型。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_1.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_2.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_3.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_4.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_5.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_6.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_7.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_8.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_9.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_10.png)

## 1. 词袋模型及其局限性

![](img/bbc67a3ffc9767c690fbfa07ac978cae_11.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_12.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_13.png)

上一节我们介绍了递归神经网络和卷积神经网络。本节中，我们来看看一种更基础的文本表示方法：词袋模型。

词袋模型是一种将句子表示为向量的简单方法。其核心思想是统计句子中每个词汇出现的次数。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_15.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_16.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_17.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_18.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_19.png)

以下是构建词袋向量的步骤：

![](img/bbc67a3ffc9767c690fbfa07ac978cae_20.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_21.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_22.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_23.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_24.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_25.png)

1.  定义一个包含所有词汇的词典。
2.  对于给定句子，遍历词典中的每个词。
3.  统计该词在句子中出现的次数。
4.  将所有统计结果组成一个向量，这个向量就是句子的词袋表示。

用公式描述，对于一个大小为 `V` 的词典，句子 `S` 的词袋向量 `BOW(S)` 可以表示为：
`BOW(S)[i] = count( word_i in S )`，其中 `i` 从 1 到 `V`。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_27.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_28.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_29.png)

然而，词袋模型存在明显的弱点。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_30.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_31.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_32.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_33.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_34.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_35.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_36.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_37.png)

以下是词袋模型的两个主要缺点：

*   **忽略词序**：模型完全丢失了词语在句子中的顺序信息。这会导致无法识别否定、双重否定等依赖语序的语义。
*   **忽略词语语义**：模型将每个词视为独立的符号，无法捕捉词语之间的语义关系。例如，“强大”和“强壮”在语义上应该比“强大”和“巴黎”更接近，但词袋模型无法体现这一点。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_39.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_40.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_41.png)

正因为这些局限性，我们需要寻找能更好地捕捉语义的表示方法，这就引出了词向量的概念。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_42.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_43.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_44.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_45.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_46.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_47.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_48.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_49.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_50.png)

## 2. 词向量核心思想回顾

既然词袋模型无法捕捉语义，我们为什么需要词向量呢？其背后的直觉是，语义相近的词语应该在向量空间中彼此靠近。

我们曾学习过连续词袋模型。接下来，我们快速回顾一下它的工作原理。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_52.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_53.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_54.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_55.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_56.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_57.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_58.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_59.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_60.png)

在CBOW模型中，我们有一个词矩阵 **W**，其行代表词汇表中的每个词，列代表该词的向量表示。给定一个大小为 `T` 的语料库和上下文窗口大小 `K`，模型的目标是通过上下文词预测中心词。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_61.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_62.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_63.png)

其计算过程可以描述为以下伪代码：
```python
# 假设 context_indices 是上下文词的索引列表
context_vectors = W[context_indices] # 从词矩阵中取出对应行的向量
average_vector = mean(context_vectors, axis=0) # 对上下文向量求平均
y = dot(average_vector, U) + b # 通过矩阵U和偏置b进行线性变换
probabilities = softmax(y) # 通过softmax得到预测每个词的概率
```
其中，**U** 是另一个权重矩阵，**b** 是偏置项。我们通过优化损失函数（如使用负采样技术）来训练模型，从而得到有意义的词向量 **W**。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_65.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_66.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_67.png)

有了词向量的基础，我们就可以将这个思想扩展到更大的文本单元，比如句子或段落。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_68.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_69.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_70.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_71.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_72.png)

## 3. 从词向量到文档向量

![](img/bbc67a3ffc9767c690fbfa07ac978cae_74.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_75.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_76.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_77.png)

我们可以将词向量的思想进行扩展，为每个段落或文档学习一个向量，就像我们为每个词学习一个向量一样。

这种方法被称为段落向量或文档向量。假设我们有一个包含百万个段落的数据集，我们可以为每个段落分配一个唯一的向量，并将这些向量存储在一个矩阵 **D** 中，就像词向量存储在矩阵 **W** 中一样。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_79.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_80.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_81.png)

那么如何训练得到这些段落向量呢？我们介绍第一种方法：分布式记忆模型。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_82.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_83.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_84.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_85.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_86.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_87.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_88.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_89.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_90.png)

## 4. 方法一：分布式记忆模型

分布式记忆模型（PV-DM）的训练方式与CBOW类似，但增加了一个段落向量作为额外的上下文信息。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_92.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_93.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_94.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_95.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_96.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_97.png)

其核心思想是：对于一个段落，我们将其对应的段落向量与段落中抽样出的上下文词向量进行拼接或平均，然后用这个综合向量来预测段落中的一个目标词（通常是中心词）。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_99.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_100.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_101.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_102.png)

以下是PV-DM的简化工作流程：

![](img/bbc67a3ffc9767c690fbfa07ac978cae_103.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_104.png)

1.  输入段落ID，从矩阵 **D** 中取出对应的段落向量 `d`。
2.  从该段落中抽样一个上下文窗口（例如，目标词前后的几个词），从矩阵 **W** 中取出这些词的向量。
3.  将段落向量 `d` 与上下文词向量进行平均或拼接，形成一个联合特征向量。
4.  将该联合向量通过一个softmax分类器（涉及矩阵 **U** 和偏置 **b**），来预测目标词。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_106.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_107.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_108.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_109.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_110.png)

模型通过最大化正确预测目标词的概率来训练，需要优化的参数包括词矩阵 **W**、段落矩阵 **D** 以及分类器的参数 **U** 和 **b**。

训练完成后，**D** 矩阵中的行向量就是我们学到的段落表示。对于新的段落，我们可以将其输入到一个简单的分类器（如逻辑回归或支持向量机）中进行分类任务。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_112.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_113.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_114.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_115.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_116.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_117.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_118.png)

然而，PV-DM 方法存在一个缺点：推理速度较慢。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_119.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_120.png)

**推理阶段的挑战**：当遇到一个全新的、未在训练集中出现的段落时，我们需要通过额外的优化步骤来推断出它的段落向量 `d`（而 **W**， **U**， **b** 保持固定）。这个步骤虽然比训练快，但仍会增加推理时间。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_122.png)

## 5. 方法二：分布式词袋模型

![](img/bbc67a3ffc9767c690fbfa07ac978cae_123.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_124.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_125.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_126.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_127.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_128.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_129.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_130.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_131.png)

为了解决PV-DM推理较慢的问题，并简化模型，我们引入了第二种方法：分布式词袋模型。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_132.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_133.png)

分布式词袋模型（PV-DBOW）的思想更接近Skip-gram模型。它忽略上下文词，只使用段落向量来预测段落中随机抽样的词。

以下是PV-DBOW的工作流程：

![](img/bbc67a3ffc9767c690fbfa07ac978cae_135.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_136.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_137.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_138.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_139.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_140.png)

![](img/bbc67a3ffc9767c690fbfa07ac978cae_141.png)

1.  输入段落ID，得到其段落向量 `d`。
2.  模型的任务是：给定这个段落向量 `d`，预测该段落中可能出现哪些词。
3.  在训练时，我们从段落中随机采样几个词作为正样本，并采样一些不在段落中的词作为负样本，然后让模型学会区分它们。

![](img/bbc67a3ffc9767c690fbfa07ac978cae_142.png)

PV-DBOW的优势在于参数效率更高，因为在推理时我们只需要保留和优化段落矩阵 **D**，而不需要像PV-DM那样在推理时还涉及词向量 **W** 和分类器参数 **U**， **b** 的交互。

## 6. 方法对比与应用总结

本节课中我们一起学习了两种文档向量化方法。现在我们来对比一下它们的性能。

在实际任务中，例如斯坦福情感树库的情感分类（二分类或五分类）或IMDB影评分类，PV-DM和PV-DBOW方法通常表现出色。它们的效果优于简单的词向量平均方法、传统的机器学习方法（如朴素贝叶斯、SVM），有时甚至能与更复杂的递归神经网络及其变体相媲美。此外，在信息检索（如文档搜索）任务中，文档向量也显示出强大的性能。

总的来说，我们学习了三种将句子转换为向量的主流方法：
1.  **基于树结构的方法**（如递归神经网络）：通过合并词语对来构建句子表示，但需要预处理得到句法树。
2.  **基于卷积的方法**：使用卷积操作捕捉局部特征，其性能受网络深度和序列长度影响。
3.  **基于段落向量的方法**（本节课重点）：为每个文档学习一个分布式向量。其中PV-DM功能强大但推理稍慢，PV-DBOW参数效率更高。

这些方法的共同目标是**将文本数据转化为固定长度的向量**，一旦获得向量表示，后续就可以轻松应用各种经典的机器学习算法进行处理。选择哪种方法取决于具体的任务需求、对推理速度的要求以及对模型性能的期望。