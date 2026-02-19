# 99：L46.2 - GloVe 词向量模型详解 🧤

![](img/369eb9be7244bddab38538212e5254e5_0.png)

![](img/369eb9be7244bddab38538212e5254e5_2.png)

![](img/369eb9be7244bddab38538212e5254e5_3.png)

![](img/369eb9be7244bddab38538212e5254e5_4.png)

![](img/369eb9be7244bddab38538212e5254e5_5.png)

![](img/369eb9be7244bddab38538212e5254e5_6.png)

![](img/369eb9be7244bddab38538212e5254e5_7.png)

![](img/369eb9be7244bddab38538212e5254e5_8.png)

![](img/369eb9be7244bddab38538212e5254e5_9.png)

![](img/369eb9be7244bddab38538212e5254e5_10.png)

![](img/369eb9be7244bddab38538212e5254e5_11.png)

![](img/369eb9be7244bddab38538212e5254e5_12.png)

在本节课中，我们将要学习一种强大的词向量模型——GloVe。我们将了解它的核心思想、如何将全局统计信息与局部上下文窗口方法相结合，以及它与其他模型（如Skip-gram）的关联。

![](img/369eb9be7244bddab38538212e5254e5_14.png)

![](img/369eb9be7244bddab38538212e5254e5_15.png)

## 概述

![](img/369eb9be7244bddab38538212e5254e5_16.png)

![](img/369eb9be7244bddab38538212e5254e5_17.png)

![](img/369eb9be7244bddab38538212e5254e5_18.png)

![](img/369eb9be7244bddab38538212e5254e5_19.png)

![](img/369eb9be7244bddab38538212e5254e5_20.png)

![](img/369eb9be7244bddab38538212e5254e5_21.png)

![](img/369eb9be7244bddab38538212e5254e5_22.png)

![](img/369eb9be7244bddab38538212e5254e5_23.png)

![](img/369eb9be7244bddab38538212e5254e5_24.png)

![](img/369eb9be7244bddab38538212e5254e5_25.png)

GloVe是Word2Vec的一个有力竞争者。它的核心思想非常简单，即通过最小化平方误差来学习词向量，但其效果却非常强大。GloVe旨在结合**全局矩阵分解方法**和**局部上下文窗口方法**的优点。

![](img/369eb9be7244bddab38538212e5254e5_27.png)

![](img/369eb9be7244bddab38538212e5254e5_28.png)

![](img/369eb9be7244bddab38538212e5254e5_29.png)

![](img/369eb9be7244bddab38538212e5254e5_30.png)

上一节我们介绍了基于局部上下文的Skip-gram模型，本节中我们来看看如何融入全局统计信息。

![](img/369eb9be7244bddab38538212e5254e5_32.png)

![](img/369eb9be7244bddab38538212e5254e5_33.png)

![](img/369eb9be7244bddab38538212e5254e5_34.png)

![](img/369eb9be7244bddab38538212e5254e5_35.png)

![](img/369eb9be7244bddab38538212e5254e5_36.png)

![](img/369eb9be7244bddab38538212e5254e5_37.png)

![](img/369eb9be7244bddab38538212e5254e5_38.png)

![](img/369eb9be7244bddab38538212e5254e5_39.png)

![](img/369eb9be7244bddab38538212e5254e5_40.png)

![](img/369eb9be7244bddab38538212e5254e5_42.png)

## GloVe的核心思想

![](img/369eb9be7244bddab38538212e5254e5_44.png)

![](img/369eb9be7244bddab38538212e5254e5_45.png)

GloVe的基本思路是创建一个**词-词共现计数矩阵**。这个矩阵的行和列都是词汇表中的单词，矩阵中的每个元素 `X_ij` 记录了单词 `j` 出现在单词 `i` 的上下文中的次数。这是一种统计方法，本质上就是计数。

![](img/369eb9be7244bddab38538212e5254e5_46.png)

![](img/369eb9be7244bddab38538212e5254e5_47.png)

![](img/369eb9be7244bddab38538212e5254e5_48.png)

![](img/369eb9be7244bddab38538212e5254e5_49.png)

![](img/369eb9be7244bddab38538212e5254e5_50.png)

![](img/369eb9be7244bddab38538212e5254e5_51.png)

![](img/369eb9be7244bddab38538212e5254e5_52.png)

![](img/369eb9be7244bddab38538212e5254e5_53.png)

![](img/369eb9be7244bddab38538212e5254e5_54.png)

![](img/369eb9be7244bddab38538212e5254e5_55.png)

**公式**：`X_ij` = 单词 `j` 出现在单词 `i` 上下文中的次数。

![](img/369eb9be7244bddab38538212e5254e5_57.png)

![](img/369eb9be7244bddab38538212e5254e5_58.png)

![](img/369eb9be7244bddab38538212e5254e5_59.png)

![](img/369eb9be7244bddab38538212e5254e5_60.png)

![](img/369eb9be7244bddab38538212e5254e5_61.png)

然后，GloVe模型做出一个关键假设：单词 `i` 和 `j` 的共现概率的对数，可以通过它们对应词向量的点积，再加上两个偏置项来近似表示。

![](img/369eb9be7244bddab38538212e5254e5_62.png)

![](img/369eb9be7244bddab38538212e5254e5_63.png)

![](img/369eb9be7244bddab38538212e5254e5_64.png)

![](img/369eb9be7244bddab38538212e5254e5_65.png)

![](img/369eb9be7244bddab38538212e5254e5_66.png)

![](img/369eb9be7244bddab38538212e5254e5_67.png)

![](img/369eb9be7244bddab38538212e5254e5_68.png)

![](img/369eb9be7244bddab38538212e5254e5_70.png)

![](img/369eb9be7244bddab38538212e5254e5_71.png)

**公式**：`log(X_ij) ≈ w_i^T · w̃_j + b_i + b̃_j`

![](img/369eb9be7244bddab38538212e5254e5_73.png)

![](img/369eb9be7244bddab38538212e5254e5_74.png)

![](img/369eb9be7244bddab38538212e5254e5_75.png)

其中：
*   `w_i` 是单词 `i` 的**输入词向量**。
*   `w̃_j` 是单词 `j` 的**上下文词向量**。
*   `b_i` 和 `b̃_j` 是偏置项，为模型提供更多灵活性，可以理解为处理对数共现计数的均值。

![](img/369eb9be7244bddab38538212e5254e5_76.png)

![](img/369eb9be7244bddab38538212e5254e5_77.png)

![](img/369eb9be7244bddab38538212e5254e5_78.png)

![](img/369eb9be7244bddab38538212e5254e5_79.png)

![](img/369eb9be7244bddab38538212e5254e5_80.png)

![](img/369eb9be7244bddab38538212e5254e5_81.png)

![](img/369eb9be7244bddab38538212e5254e5_82.png)

![](img/369eb9be7244bddab38538212e5254e5_84.png)

## 损失函数

![](img/369eb9be7244bddab38538212e5254e5_86.png)

![](img/369eb9be7244bddab38538212e5254e5_87.png)

![](img/369eb9be7244bddab38538212e5254e5_88.png)

![](img/369eb9be7244bddab38538212e5254e5_89.png)

![](img/369eb9be7244bddab38538212e5254e5_90.png)

![](img/369eb9be7244bddab38538212e5254e5_91.png)

基于上述假设，GloVe的损失函数旨在让公式左右两边尽可能接近。它使用**加权最小二乘**作为目标。

![](img/369eb9be7244bddab38538212e5254e5_92.png)

![](img/369eb9be7244bddab38538212e5254e5_93.png)

![](img/369eb9be7244bddab38538212e5254e5_94.png)

![](img/369eb9be7244bddab38538212e5254e5_95.png)

![](img/369eb9be7244bddab38538212e5254e5_96.png)

![](img/369eb9be7244bddab38538212e5254e5_97.png)

**公式**：`J = Σ_{i,j=1}^{V} f(X_ij) (w_i^T · w̃_j + b_i + b̃_j - log(X_ij))^2`

![](img/369eb9be7244bddab38538212e5254e5_99.png)

![](img/369eb9be7244bddab38538212e5254e5_100.png)

![](img/369eb9be7244bddab38538212e5254e5_101.png)

![](img/369eb9be7244bddab38538212e5254e5_102.png)

![](img/369eb9be7244bddab38538212e5254e5_103.png)

![](img/369eb9be7244bddab38538212e5254e5_104.png)

![](img/369eb9be7244bddab38538212e5254e5_105.png)

![](img/369eb9be7244bddab38538212e5254e5_106.png)

![](img/369eb9be7244bddab38538212e5254e5_107.png)

以下是该损失函数的关键组成部分：

![](img/369eb9be7244bddab38538212e5254e5_108.png)

![](img/369eb9be7244bddab38538212e5254e5_109.png)

![](img/369eb9be7244bddab38538212e5254e5_110.png)

*   **加权项 `f(X_ij)`**：这是一个权重函数，用于平衡不同频率词对的影响。词汇分布通常遵循幂律分布（长尾分布），即少数高频词出现次数极多。如果不加权重，模型会过度关注高频词，而忽略重要的低频词。
*   **求和范围**：对词汇表 `V` 中的所有单词对 `(i, j)` 进行求和。

![](img/369eb9be7244bddab38538212e5254e5_112.png)

![](img/369eb9be7244bddab38538212e5254e5_113.png)

![](img/369eb9be7244bddab38538212e5254e5_114.png)

![](img/369eb9be7244bddab38538212e5254e5_115.png)

![](img/369eb9be7244bddab38538212e5254e5_116.png)

![](img/369eb9be7244bddab38538212e5254e5_117.png)

![](img/369eb9be7244bddab38538212e5254e5_118.png)

![](img/369eb9be7244bddab38538212e5254e5_119.png)

![](img/369eb9be7244bddab38538212e5254e5_120.png)

![](img/369eb9be7244bddab38538212e5254e5_121.png)

![](img/369eb9be7244bddab38538212e5254e5_122.png)

![](img/369eb9be7244bddab38538212e5254e5_123.png)

### 权重函数的设计

权重函数 `f(x)` 的设计至关重要。其目的是为共现次数设定一个上限，避免高频词对主导训练过程。

![](img/369eb9be7244bddab38538212e5254e5_125.png)

![](img/369eb9be7244bddab38538212e5254e5_126.png)

![](img/369eb9be7244bddab38538212e5254e5_127.png)

![](img/369eb9be7244bddab38538212e5254e5_128.png)

![](img/369eb9be7244bddab38538212e5254e5_129.png)

![](img/369eb9be7244bddab38538212e5254e5_130.png)

![](img/369eb9be7244bddab38538212e5254e5_131.png)

![](img/369eb9be7244bddab38538212e5254e5_132.png)

![](img/369eb9be7244bddab38538212e5254e5_133.png)

![](img/369eb9be7244bddab38538212e5254e5_134.png)

![](img/369eb9be7244bddab38538212e5254e5_135.png)

![](img/369eb9be7244bddab38538212e5254e5_136.png)

**代码/公式描述**：
```
            (x / x_max)^α,   if x < x_max
f(x) = {
            1,               otherwise
```

![](img/369eb9be7244bddab38538212e5254e5_138.png)

![](img/369eb9be7244bddab38538212e5254e5_139.png)

![](img/369eb9be7244bddab38538212e5254e5_140.png)

![](img/369eb9be7244bddab38538212e5254e5_141.png)

![](img/369eb9be7244bddab38538212e5254e5_142.png)

其中 `x_max` 和 `α` 是超参数。经验表明，`α = 3/4` 通常能取得很好的效果。这个函数赋予低频词相对更高的权重，确保模型能充分学习到它们的信息。

![](img/369eb9be7244bddab38538212e5254e5_143.png)

![](img/369eb9be7244bddab38538212e5254e5_144.png)

![](img/369eb9be7244bddab38538212e5254e5_145.png)

![](img/369eb9be7244bddab38538212e5254e5_146.png)

![](img/369eb9be7244bddab38538212e5254e5_147.png)

![](img/369eb9be7244bddab38538212e5254e5_148.png)

![](img/369eb9be7244bddab38538212e5254e5_149.png)

## 与Skip-gram模型的关联

![](img/369eb9be7244bddab38538212e5254e5_151.png)

![](img/369eb9be7244bddab38538212e5254e5_152.png)

![](img/369eb9be7244bddab38538212e5254e5_153.png)

![](img/369eb9be7244bddab38538212e5254e5_154.png)

![](img/369eb9be7244bddab38538212e5254e5_155.png)

![](img/369eb9be7244bddab38538212e5254e5_156.png)

![](img/369eb9be7244bddab38538212e5254e5_157.png)

为了理解GloVe，我们可以将其与熟悉的Skip-gram模型联系起来。Skip-gram的损失函数（经过简化）可以重写为以下形式：

![](img/369eb9be7244bddab38538212e5254e5_159.png)

![](img/369eb9be7244bddab38538212e5254e5_160.png)

![](img/369eb9be7244bddab38538212e5254e5_161.png)

![](img/369eb9be7244bddab38538212e5254e5_162.png)

![](img/369eb9be7244bddab38538212e5254e5_163.png)

**公式**：`J = -Σ_{i,j} X_ij log(Q_ij)`

![](img/369eb9be7244bddab38538212e5254e5_164.png)

![](img/369eb9be7244bddab38538212e5254e5_165.png)

![](img/369eb9be7244bddab38538212e5254e5_166.png)

![](img/369eb9be7244bddab38538212e5254e5_167.png)

![](img/369eb9be7244bddab38538212e5254e5_168.png)

![](img/369eb9be7244bddab38538212e5254e5_169.png)

![](img/369eb9be7244bddab38538212e5254e5_170.png)

其中 `Q_ij` 是Skip-gram中通过softmax计算得到的单词 `j` 出现在单词 `i` 上下文中的预测概率。

![](img/369eb9be7244bddab38538212e5254e5_172.png)

![](img/369eb9be7244bddab38538212e5254e5_173.png)

![](img/369eb9be7244bddab38538212e5254e5_174.png)

![](img/369eb9be7244bddab38538212e5254e5_175.png)

![](img/369eb9be7244bddab38538212e5254e5_176.png)

![](img/369eb9be7244bddab38538212e5254e5_177.png)

![](img/369eb9be7244bddab38538212e5254e5_178.png)

![](img/369eb9be7244bddab38538212e5254e5_179.png)

![](img/369eb9be7244bddab38538212e5254e5_180.png)

如果我们定义 `P_ij = X_ij / X_i` 为实际的共现概率（`X_i` 是单词 `i` 的所有上下文词频次总和），那么Skip-gram的损失函数可以看作是**加权交叉熵**：

![](img/369eb9be7244bddab38538212e5254e5_181.png)

![](img/369eb9be7244bddab38538212e5254e5_182.png)

![](img/369eb9be7244bddab38538212e5254e5_183.png)

![](img/369eb9be7244bddab38538212e5254e5_185.png)

![](img/369eb9be7244bddab38538212e5254e5_186.png)

![](img/369eb9be7244bddab38538212e5254e5_187.png)

![](img/369eb9be7244bddab38538212e5254e5_189.png)

![](img/369eb9be7244bddab38538212e5254e5_190.png)

**公式**：`J = -Σ_{i,j} X_ij log(Q_ij) = Σ_i X_i * H(P_i, Q_i)`

这里 `H(P_i, Q_i)` 是分布 `P_i` 和 `Q_i` 的交叉熵，`X_i` 是权重。

![](img/369eb9be7244bddab38538212e5254e5_192.png)

![](img/369eb9be7244bddab38538212e5254e5_193.png)

![](img/369eb9be7244bddab38538212e5254e5_194.png)

![](img/369eb9be7244bddab38538212e5254e5_195.png)

![](img/369eb9be7244bddab38538212e5254e5_196.png)

![](img/369eb9be7244bddab38538212e5254e5_197.png)

![](img/369eb9be7244bddab38538212e5254e5_198.png)

![](img/369eb9be7244bddab38538212e5254e5_199.png)

![](img/369eb9be7244bddab38538212e5254e5_200.png)

![](img/369eb9be7244bddab38538212e5254e5_201.png)

![](img/369eb9be7244bddab38538212e5254e5_202.png)

![](img/369eb9be7244bddab38538212e5254e5_203.png)

由此可见，GloVe（加权最小二乘）和Skip-gram（加权交叉熵）在思想上是相似的。它们都试图让模型预测的“关系”与实际的统计量（GloVe用对数共现次数，Skip-gram用概率分布）相匹配，并且都使用了加权策略来处理词频不平衡问题。主要区别在于它们衡量“差距”的方式不同（平方误差 vs 交叉熵）。

![](img/369eb9be7244bddab38538212e5254e5_205.png)

![](img/369eb9be7244bddab38538212e5254e5_206.png)

![](img/369eb9be7244bddab38538212e5254e5_207.png)

![](img/369eb9be7244bddab38538212e5254e5_208.png)

![](img/369eb9be7244bddab38538212e5254e5_209.png)

## 模型表现与选择

![](img/369eb9be7244bddab38538212e5254e5_210.png)

![](img/369eb9be7244bddab38538212e5254e5_211.png)

![](img/369eb9be7244bddab38538212e5254e5_212.png)

![](img/369eb9be7244bddab38538212e5254e5_213.png)

![](img/369eb9be7244bddab38538212e5254e5_214.png)

![](img/369eb9be7244bddab38538212e5254e5_215.png)

![](img/369eb9be7244bddab38538212e5254e5_216.png)

GloVe、Skip-gram和CBOW在不同任务上各有优劣：

![](img/369eb9be7244bddab38538212e5254e5_218.png)

![](img/369eb9be7244bddab38538212e5254e5_219.png)

![](img/369eb9be7244bddab38538212e5254e5_220.png)

![](img/369eb9be7244bddab38538212e5254e5_221.png)

![](img/369eb9be7244bddab38538212e5254e5_222.png)

![](img/369eb9be7244bddab38538212e5254e5_223.png)

*   **语义任务**：GloVe通常表现最佳。
*   **句法任务**：CBOW可能表现更好。
*   **综合表现**：GloVe总体上有优势。

在实际应用中，需要根据下游任务的需求（更注重语义还是句法）来选择合适的模型。例如，自动补全可能更关注句法，而情感分析可能更关注语义。

关于模型训练，还有一些重要的考量因素：

*   **词向量维度**：随着维度增加，模型性能会提升并逐渐饱和。通常维度设置在300-600之间是常见的，超过600后收益可能不明显。
*   **上下文窗口**：可以使用对称窗口（考虑左右两侧的单词）或非对称窗口（例如只考虑右侧单词）。更大的窗口通常对学习语义信息更有帮助。
*   **训练时间**：更长的训练时间通常会带来更好的词向量质量。研究表明，在相同训练时间下，GloVe往往能获得比CBOW和Skip-gram更好的词向量。

## 总结

本节课中我们一起学习了GloVe词向量模型。我们了解到GloVe通过构建全局的词-词共现矩阵，并利用加权最小二乘损失函数，将单词的共现统计信息有效地编码到低维词向量中。它的核心思想简洁而有力，并且与Skip-gram模型在目标上存在深刻的联系。GloVe在多项任务上，尤其是语义相关任务上，展现了优异的性能，是自然语言处理中一个非常重要的基础工具。