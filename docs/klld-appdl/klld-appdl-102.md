# 102：L49.1- 用于句子分类的CNN 🧠

![](img/d0f8a58de2c56043328b4698ed09c13b_1.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_2.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_3.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_4.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_5.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_6.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_7.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_8.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_9.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_10.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_11.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_12.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_14.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_15.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_16.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_17.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_18.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_19.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_20.png)

在本节课中，我们将学习如何将卷积神经网络应用于文本分类任务，特别是句子分类。我们将探讨其核心思想、具体操作步骤，并了解一个重要的正则化技术——Dropout。

![](img/d0f8a58de2c56043328b4698ed09c13b_21.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_22.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_23.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_25.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_26.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_28.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_29.png)

## 概述

![](img/d0f8a58de2c56043328b4698ed09c13b_30.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_31.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_32.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_33.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_34.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_35.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_36.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_37.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_38.png)

处理文本时，我们面临多种方法选择：循环神经网络、递归神经网络、卷积网络还是注意力机制。本节将重点介绍用于句子分类的卷积神经网络。卷积操作通常用于图像处理，但我们可以将句子视为一维图像，从而应用卷积。这种方法不需要像递归神经网络那样依赖句子的树状结构，简化了预处理步骤。

![](img/d0f8a58de2c56043328b4698ed09c13b_40.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_41.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_42.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_43.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_44.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_45.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_46.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_47.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_48.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_49.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_50.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_52.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_53.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_54.png)

## 句子作为一维图像

![](img/d0f8a58de2c56043328b4698ed09c13b_55.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_56.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_57.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_58.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_60.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_61.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_62.png)

在卷积神经网络框架中，我们将句子中的每个词视为一个“像素”。每个词由一个向量表示，因此一个句子就是一系列向量的序列。

![](img/d0f8a58de2c56043328b4698ed09c13b_63.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_64.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_65.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_66.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_67.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_68.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_69.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_71.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_72.png)

假设一个句子由 `n` 个词组成：`x1, x2, ..., xn`。每个词向量 `xi` 是 `k` 维的。因此，整个句子可以看作一个形状为 `n × k` 的矩阵，这类似于一个高度为 `n`、宽度为 `k` 的一维图像。

![](img/d0f8a58de2c56043328b4698ed09c13b_73.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_74.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_75.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_76.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_77.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_78.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_79.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_80.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_81.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_82.png)

## 一维卷积操作

![](img/d0f8a58de2c56043328b4698ed09c13b_84.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_85.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_86.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_87.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_88.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_89.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_90.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_91.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_92.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_93.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_95.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_96.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_98.png)

接下来，我们引入卷积操作。与图像处理中的二维卷积不同，这里我们使用一维卷积。

![](img/d0f8a58de2c56043328b4698ed09c13b_100.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_101.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_102.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_103.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_104.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_105.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_106.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_107.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_108.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_109.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_110.png)

我们定义一个卷积核（或过滤器），其窗口大小为 `h`。这意味着每次卷积操作会考虑连续的 `h` 个词。对于每个窗口内的词，我们都有一个对应的权重矩阵 `Wj`，用于将 `k` 维的词向量转换为 `m` 维的特征。

![](img/d0f8a58de2c56043328b4698ed09c13b_112.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_113.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_114.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_115.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_116.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_117.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_118.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_119.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_120.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_121.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_122.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_123.png)

**卷积操作的核心公式如下：**

![](img/d0f8a58de2c56043328b4698ed09c13b_125.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_126.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_128.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_129.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_130.png)

对于一个从位置 `i` 开始的窗口（包含词 `xi, xi+1, ..., xi+h-1`），其卷积输出 `ci` 的计算为：
`ci = f( Σ_{j=1}^{h} Wj * x_{i+j-1} + b )`
其中：
*   `Wj` 是第 `j` 个位置的权重矩阵（维度为 `m × k`）。
*   `b` 是偏置项（维度为 `m`），用于调整输出分布的均值。
*   `f` 是一个非线性激活函数，如 ReLU 或 tanh。

![](img/d0f8a58de2c56043328b4698ed09c13b_131.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_132.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_133.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_134.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_135.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_136.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_137.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_138.png)

这个操作在句子序列上滑动进行。对于长度为 `n` 的句子，使用窗口大小为 `h` 的卷积核，我们将得到一个长度为 `n - h + 1` 的新序列 `c1, c2, ..., c_{n-h+1}`。新序列中的每个元素 `ci` 都是一个 `m` 维向量。

![](img/d0f8a58de2c56043328b4698ed09c13b_140.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_141.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_142.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_143.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_144.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_145.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_146.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_147.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_148.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_149.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_151.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_152.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_153.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_154.png)

## 全局最大池化与分类

![](img/d0f8a58de2c56043328b4698ed09c13b_156.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_157.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_158.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_159.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_160.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_161.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_162.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_163.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_164.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_165.png)

卷积层输出仍是一个序列，但分类任务通常需要一个固定长度的向量作为输入。因此，我们使用**全局最大池化**操作。

![](img/d0f8a58de2c56043328b4698ed09c13b_167.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_168.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_170.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_171.png)

具体来说，对于卷积输出的 `m` 维特征序列，我们在每个特征维度上独立地取最大值。假设卷积输出序列长度为 `L`，对于第 `j` 个特征维度（`j` 从 1 到 `m`），我们计算：
`z_j = max(c1[j], c2[j], ..., cL[j])`
这样，我们就将一个变长的序列压缩成了一个固定的 `m` 维向量 `z`。

![](img/d0f8a58de2c56043328b4698ed09c13b_172.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_173.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_174.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_175.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_176.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_177.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_178.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_180.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_182.png)

最后，为了进行具体的分类（例如情感分析分为5类），我们需要将 `m` 维的向量 `z` 投影到目标类别维度。这通过一个全连接层实现：
`y = softmax(W_y * z + b_y)`
其中 `W_y` 是权重矩阵，`b_y` 是偏置项。

![](img/d0f8a58de2c56043328b4698ed09c13b_183.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_184.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_185.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_186.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_187.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_188.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_189.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_190.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_191.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_192.png)

## 网络深度与参数共享

![](img/d0f8a58de2c56043328b4698ed09c13b_194.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_195.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_196.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_197.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_198.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_199.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_200.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_201.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_202.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_203.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_204.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_205.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_207.png)

与图像CNN类似，我们可以堆叠多个卷积层和池化层来构建更深的网络，以捕捉更复杂的特征。然而，句子的长度有限，因此可堆叠的层数也受到限制。

![](img/d0f8a58de2c56043328b4698ed09c13b_208.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_209.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_210.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_211.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_212.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_213.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_215.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_216.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_217.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_218.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_219.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_220.png)

卷积操作的一个关键优势是**参数共享**。同一个卷积核（`W1, W2, ..., Wh`）会滑动应用于句子的所有位置，这大大减少了模型参数，并让模型能够学习到与位置无关的特征。

![](img/d0f8a58de2c56043328b4698ed09c13b_221.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_222.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_224.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_225.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_226.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_227.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_228.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_229.png)

## Dropout 正则化技术

![](img/d0f8a58de2c56043328b4698ed09c13b_231.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_232.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_233.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_234.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_235.png)

深度神经网络参数众多，容易在训练数据上过拟合。Dropout 是一种有效的正则化技术，旨在提高模型的泛化能力。

![](img/d0f8a58de2c56043328b4698ed09c13b_236.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_237.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_239.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_240.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_241.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_242.png)

Dropout 在训练阶段随机“丢弃”一部分神经元。其操作如下：

![](img/d0f8a58de2c56043328b4698ed09c13b_243.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_244.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_245.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_246.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_247.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_248.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_249.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_250.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_252.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_253.png)

对于网络中的某个层（例如池化后得到的向量 `z`，它有 `m` 个神经元），在每次训练迭代中，每个神经元都以概率 `p` 被临时设置为0（即被丢弃），以概率 `1-p` 被保留。

![](img/d0f8a58de2c56043328b4698ed09c13b_255.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_256.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_257.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_258.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_259.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_260.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_261.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_262.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_263.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_264.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_265.png)

**Dropout 的代码描述如下（训练阶段）：**
```python
# r 是一个与 z 形状相同的掩码向量，元素服从伯努利分布 (1-p, p)
r = np.random.binomial(1, 1-p, size=z.shape)
z_dropped = z * r  # 应用 Dropout
```

![](img/d0f8a58de2c56043328b4698ed09c13b_267.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_268.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_269.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_270.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_271.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_272.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_273.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_274.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_275.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_276.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_277.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_278.png)

这迫使网络不能过度依赖某些特定的神经元，而必须让所有神经元都尽可能独立地发挥作用，从而增强了模型的鲁棒性。

![](img/d0f8a58de2c56043328b4698ed09c13b_280.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_281.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_282.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_283.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_284.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_285.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_286.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_287.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_288.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_289.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_290.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_291.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_293.png)

在测试或生产阶段，我们需要一个确定性的预测。此时，我们不再随机丢弃神经元，而是对权重进行缩放。具体做法是，将训练好的权重 `W` 乘以保留概率 `(1-p)`，作为测试时使用的权重。这近似模拟了在训练时平均多个不同子网络的效果。

![](img/d0f8a58de2c56043328b4698ed09c13b_294.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_295.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_296.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_297.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_298.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_300.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_301.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_302.png)

## 模型变体与实验分析

![](img/d0f8a58de2c56043328b4698ed09c13b_303.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_304.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_305.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_306.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_307.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_308.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_309.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_310.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_312.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_313.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_314.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_315.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_316.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_317.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_318.png)

在实际应用中，我们可以尝试不同的策略来初始化词向量，并观察其对性能的影响：

![](img/d0f8a58de2c56043328b4698ed09c13b_320.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_321.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_322.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_323.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_324.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_325.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_326.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_327.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_328.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_329.png)

以下是常见的几种词向量处理方式：
*   **随机初始化**：词向量随机初始化，并在训练中学习。
*   **静态预训练**：使用预训练模型（如 Word2Vec 或 GloVe）初始化词向量，并在整个训练过程中保持固定。
*   **非静态预训练**：使用预训练模型初始化词向量，但在训练过程中允许对其进行微调。
*   **多通道**：使用两组词向量，一组保持静态，一组进行微调，然后将它们拼接起来作为输入，这相当于增加了输入的“通道”数。

![](img/d0f8a58de2c56043328b4698ed09c13b_330.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_331.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_333.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_334.png)

实验表明，使用预训练词向量通常能带来性能提升，而多通道策略在一些数据集上能取得最佳或接近最佳的效果。

![](img/d0f8a58de2c56043328b4698ed09c13b_336.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_337.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_338.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_339.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_340.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_341.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_342.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_343.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_344.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_345.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_346.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_347.png)

## 方法特点与局限性

![](img/d0f8a58de2c56043328b4698ed09c13b_349.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_350.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_351.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_352.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_353.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_354.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_355.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_356.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_357.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_358.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_359.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_360.png)

与之前介绍的递归神经网络相比，用于句子分类的CNN具有以下特点：
*   **无需句法树**：不依赖于句子的树状结构，省去了句法解析的预处理步骤。
*   **可并行计算**：卷积操作可以高度并行化，训练速度更快。
*   **局部特征提取**：通过不同大小的卷积核，可以捕捉句子中不同范围的局部依赖关系（如二元词组、三元词组等）。

![](img/d0f8a58de2c56043328b4698ed09c13b_362.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_363.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_364.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_365.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_366.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_367.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_368.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_369.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_370.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_371.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_372.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_373.png)

其局限性在于：
*   **长距离依赖**：由于卷积和池化操作主要关注局部特征，对于理解需要长距离依赖的句子结构可能存在不足。
*   **位置不敏感性**：全局最大池化可能会丢失词序的细微信息，尽管卷积操作本身在一定程度上保留了局部顺序。

![](img/d0f8a58de2c56043328b4698ed09c13b_375.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_376.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_377.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_378.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_379.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_380.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_381.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_382.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_383.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_384.png)

## 总结

![](img/d0f8a58de2c56043328b4698ed09c13b_386.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_387.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_388.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_389.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_390.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_391.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_392.png)

![](img/d0f8a58de2c56043328b4698ed09c13b_393.png)

本节课我们一起学习了用于句子分类的卷积神经网络。我们将句子视为一维图像，通过一维卷积操作提取局部特征，再通过全局最大池化得到句子的固定长度表示，最后进行分类。我们还介绍了Dropout这一重要的正则化技术，它通过在训练中随机丢弃神经元来防止过拟合，提升模型泛化能力。这种方法结构简单、易于并行，是文本分类任务中一个强大且高效的基线模型。