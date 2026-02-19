# 104：L49.3- 基于CNNs的文本分类 📚

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_1.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_2.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_3.png)

在本节课中，我们将学习如何将卷积神经网络（CNNs）应用于文本分类任务。与之前使用词向量的方法不同，这次我们将使用独热编码向量来表示文本，并理解CNN如何在文本序列上进行滑动窗口操作以提取特征。

---

## 从图像卷积到文本卷积 🔄

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_5.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_6.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_7.png)

上一节我们介绍了卷积神经网络的基本概念。本节中我们来看看如何将图像处理中的卷积思想迁移到文本上。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_8.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_9.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_10.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_11.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_12.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_13.png)

在图像处理中，卷积操作使用一个滑动窗口在图像上移动。对于窗口内的像素，我们使用相同的参数（权重W和偏置b）进行计算，公式可以表示为：

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_14.png)

**h = ReLU(W · X_window + b)**

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_16.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_17.png)

其中，`X_window` 是当前窗口内的像素值向量。经过卷积后，通常会进行池化操作以降低分辨率，这个过程可以重复多次，最终用于预测类别（例如，类别3或类别10）。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_18.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_19.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_20.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_21.png)

那么，如何将这一过程应用于文本呢？

---

## 文本的独热编码表示 🔤

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_23.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_24.png)

以下是处理文本的第一步：将单词转换为向量。我们使用独热编码，而不是词向量。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_25.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_26.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_27.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_28.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_29.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_30.png)

假设我们的词汇表是：`[“don’t”, “hate”, “I”, “eat”, “love”]`。
对于一个示例文档 “I love it”，我们将其中的每个单词转换为独热向量：

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_31.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_32.png)

*   **“I”** 是词汇表中的第三个词，因此其向量为：`[0, 0, 1, 0, 0]`
*   **“love”** 是词汇表中的最后一个词，因此其向量为：`[0, 0, 0, 0, 1]`
*   **“it”** 是词汇表中的第四个词，因此其向量为：`[0, 0, 0, 1, 0]`

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_34.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_35.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_36.png)

这样，整个文档 “I love it” 就被表示为一个由三个独热向量组成的序列。这就是我们的输入 `X`。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_37.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_38.png)

---

## 在文本序列上应用滑动窗口 🪟

与图像中的滑动窗口类似，我们在文本序列上定义窗口。例如，我们可以设置窗口大小为2（即每次看两个连续的单词）。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_40.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_41.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_42.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_43.png)

对于文档 “I love it”：
1.  第一个窗口包含 “I love”，对应的向量是 `r0 = [[0,0,1,0,0], [0,0,0,0,1]]`。
2.  将窗口滑动一步，第二个窗口包含 “love it”，对应的向量是 `r1 = [[0,0,0,0,1], [0,0,0,1,0]]`。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_44.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_45.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_46.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_47.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_48.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_49.png)

这些窗口 `r0`, `r1`... 就是我们要进行卷积操作的局部区域。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_50.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_51.png)

---

## 文本卷积的具体计算 🧮

现在，我们对每个窗口进行卷积操作。我们有一组可学习的参数 `W`（权重矩阵）和 `b`（偏置）。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_53.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_54.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_55.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_56.png)

以第一个窗口 `r0` 为例，计算过程如下：
1.  将窗口向量 `r0` 展平（如果需要）。
2.  与权重 `W` 进行点积运算，加上偏置 `b`。
3.  将结果通过一个非线性激活函数（如ReLU）。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_57.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_58.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_59.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_60.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_61.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_62.png)

由于 `r0` 是稀疏的独热向量，点积运算中实际上只有对应位置为1的权重会被激活。例如，对于 `r0`，只有 `W` 中对应 “I” 和 “love” 位置的权重（假设为 `w13` 和 `w25`）会参与计算并产生输出 `h0`。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_63.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_65.png)

对每个窗口重复此操作，我们会得到一系列输出向量 `[h0, h1, h2, ...]`。输出向量的数量取决于输入文本的长度和窗口滑动的方式。

为了减少参数量，有时可以忽略窗口内单词的顺序，直接将窗口内的向量元素相加后再进行卷积计算，这是一种权衡策略。

---

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_67.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_68.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_69.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_70.png)

## 文本序列的池化操作 📉

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_71.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_72.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_73.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_74.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_75.png)

卷积之后，我们通常需要进行池化来降低序列长度，并整合特征。对于文本，我们需要处理可变长度的序列。

池化策略如下：
1.  首先，固定你希望池化后得到的输出向量数量（例如，2个）。
2.  然后，根据输入序列的长度动态计算池化窗口的大小。公式为：**池化窗口大小 = 输入序列长度 / 期望输出长度**。
3.  最后，在每个池化窗口内（例如，对窗口内的所有向量）取最大值或平均值，得到一个池化后的向量。

通过这种方式，无论输入句子多长，我们都能将其转换为固定长度的特征表示，以便输入到后续的全连接层进行分类。

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_77.png)

---

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_78.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_79.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_80.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_81.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_82.png)

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_83.png)

## 模型表现与感受野分析 📊

![](img/c9fccec2ae021cc45ce8a733d70e3bd0_84.png)

在IMDB电影评论数据集上的实验表明，这种序列CNN模型的表现优于简单的词袋模型，这可能是因为CNN拥有更多的参数并能捕捉局部上下文信息。

卷积网络的一个优点是我们可以分析其“感受野”，即对于最终的分类决策（如“负面评价”），模型主要关注了输入文本中的哪些词。通过回溯网络中重要的权重，我们可以找出对预测贡献最大的单词序列。

例如，对于一个被预测为“负面”的评论，模型可能主要关注了“completely”、“useless”、“won‘t”、“work”、“poor”等词汇。这为我们提供了一种解释模型内部决策机制的方式。

---

## 总结 ✨

本节课中我们一起学习了基于CNN的文本分类方法。我们回顾了卷积操作，并将其从图像领域迁移到文本领域，使用独热编码表示单词。我们详细讲解了如何在文本序列上定义滑动窗口、进行卷积计算以及实施池化操作以得到固定长度的特征。最后，我们了解了通过分析感受野来解释模型预测结果的方法。这种方法为处理文本分类任务提供了一种强大且可解释的深度学习工具。