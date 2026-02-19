# 160：L72.2 - CTC算法详解 🧠

![](img/f82f906f1a4affba647cce4cb17d818a_1.png)

![](img/f82f906f1a4affba647cce4cb17d818a_2.png)

![](img/f82f906f1a4affba647cce4cb17d818a_3.png)

![](img/f82f906f1a4affba647cce4cb17d818a_4.png)

![](img/f82f906f1a4affba647cce4cb17d818a_5.png)

![](img/f82f906f1a4affba647cce4cb17d818a_6.png)

在本节课中，我们将要学习连接时序分类（CTC）算法。CTC是一种用于处理未分段序列数据（如语音、手写识别）的损失函数和训练方法。我们将从基本概念入手，逐步理解其工作原理、数学公式以及如何通过动态编程高效计算。

## 什么是语音识别？ 🎤

![](img/f82f906f1a4affba647cce4cb17d818a_8.png)

![](img/f82f906f1a4affba647cce4cb17d818a_9.png)

![](img/f82f906f1a4affba647cce4cb17d818a_10.png)

![](img/f82f906f1a4affba647cce4cb17d818a_11.png)

![](img/f82f906f1a4affba647cce4cb17d818a_12.png)

![](img/f82f906f1a4affba647cce4cb17d818a_13.png)

![](img/f82f906f1a4affba647cce4cb17d818a_14.png)

![](img/f82f906f1a4affba647cce4cb17d818a_15.png)

![](img/f82f906f1a4affba647cce4cb17d818a_16.png)

![](img/f82f906f1a4affba647cce4cb17d818a_17.png)

语音识别的目标是，当有人给你一段音频信号时，你需要将其转录成单词、子词、字母或音素等形式。

![](img/f82f906f1a4affba647cce4cb17d818a_18.png)

![](img/f82f906f1a4affba647cce4cb17d818a_19.png)

输入是一个嘈杂的实值流（原始音频），并带有一些标注（例如某人朗读文本产生的数据）。CTC算法不仅可用于语音识别，还可用于手写识别、手势识别等任务。

![](img/f82f906f1a4affba647cce4cb17d818a_21.png)

![](img/f82f906f1a4affba647cce4cb17d818a_22.png)

## 什么是时序分类？ ⏱️

![](img/f82f906f1a4affba647cce4cb17d818a_23.png)

![](img/f82f906f1a4affba647cce4cb17d818a_24.png)

![](img/f82f906f1a4affba647cce4cb17d818a_25.png)

![](img/f82f906f1a4affba647cce4cb17d818a_26.png)

![](img/f82f906f1a4affba647cce4cb17d818a_27.png)

![](img/f82f906f1a4affba647cce4cb17d818a_28.png)

![](img/f82f906f1a4affba647cce4cb17d818a_29.png)

![](img/f82f906f1a4affba647cce4cb17d818a_30.png)

![](img/f82f906f1a4affba647cce4cb17d818a_31.png)

时序分类的定义是为未分段的序列数据打标签。语音数据不像文本那样是预先分割好的，它是一个连续的信号。因此，为这种未分段的序列数据分配标签的任务就称为时序分类。

“连接主义”一词源于深度学习曾被称为连接主义，这里特指使用RNN或神经网络。因此，CTC是使用神经网络进行时序分类的方法。

![](img/f82f906f1a4affba647cce4cb17d818a_33.png)

![](img/f82f906f1a4affba647cce4cb17d818a_34.png)

![](img/f82f906f1a4affba647cce4cb17d818a_35.png)

![](img/f82f906f1a4affba647cce4cb17d818a_36.png)

![](img/f82f906f1a4affba647cce4cb17d818a_37.png)

![](img/f82f906f1a4affba647cce4cb17d818a_38.png)

![](img/f82f906f1a4affba647cce4cb17d818a_39.png)

与之相对的是逐帧分类，即独立地对每一帧进行分类。逐帧分类是迈向连接时序分类的一步。

![](img/f82f906f1a4affba647cce4cb17d818a_40.png)

![](img/f82f906f1a4affba647cce4cb17d818a_41.png)

![](img/f82f906f1a4affba647cce4cb17d818a_42.png)

![](img/f82f906f1a4affba647cce4cb17d818a_43.png)

![](img/f82f906f1a4affba647cce4cb17d818a_44.png)

上一节我们介绍了时序分类的基本概念，本节中我们来看看CTC如何形式化地定义和解决这个问题。

## CTC问题形式化 📝

![](img/f82f906f1a4affba647cce4cb17d818a_46.png)

![](img/f82f906f1a4affba647cce4cb17d818a_47.png)

![](img/f82f906f1a4affba647cce4cb17d818a_48.png)

![](img/f82f906f1a4affba647cce4cb17d818a_49.png)

![](img/f82f906f1a4affba647cce4cb17d818a_50.png)

![](img/f82f906f1a4affba647cce4cb17d818a_51.png)

![](img/f82f906f1a4affba647cce4cb17d818a_52.png)

![](img/f82f906f1a4affba647cce4cb17d818a_53.png)

![](img/f82f906f1a4affba647cce4cb17d818a_54.png)

![](img/f82f906f1a4affba647cce4cb17d818a_55.png)

处理时序分类时，我们有一个数据集 **S**，它是训练数据，包含输入语音和输出文本的配对。

![](img/f82f906f1a4affba647cce4cb17d818a_56.png)

![](img/f82f906f1a4affba647cce4cb17d818a_57.png)

*   **x** 是输入序列，属于所有M维序列的空间，其长度是未知且可变的。这通常就是我们看到的梅尔频谱图序列。
*   **z** 是输出序列，是一个标签序列。你有一个大小为L的词汇表，输出就是这个词汇表中标签的序列。

![](img/f82f906f1a4affba647cce4cb17d818a_59.png)

![](img/f82f906f1a4affba647cce4cb17d818a_60.png)

![](img/f82f906f1a4affba647cce4cb17d818a_61.png)

在你的数据中，有 **(x, z)** 对。**x** 是语音输入序列，**z** 是目标标签序列。这里存在一个问题：我们说话时间很长，输入序列长度 **T** 通常远大于输出标签序列的长度 **U**。CTC算法正是要帮助我们解决这个对齐问题。

![](img/f82f906f1a4affba647cce4cb17d818a_62.png)

![](img/f82f906f1a4affba647cce4cb17d818a_63.png)

![](img/f82f906f1a4affba647cce4cb17d818a_64.png)

![](img/f82f906f1a4affba647cce4cb17d818a_65.png)

![](img/f82f906f1a4affba647cce4cb17d818a_66.png)

![](img/f82f906f1a4affba647cce4cb17d818a_67.png)

![](img/f82f906f1a4affba647cce4cb17d818a_68.png)

![](img/f82f906f1a4affba647cce4cb17d818a_69.png)

![](img/f82f906f1a4affba647cce4cb17d818a_70.png)

## 如何评估模型性能？ 📊

假设我们有一个分类器，它输入一个序列，输出另一个序列。我们希望在测试数据上评估其性能。

![](img/f82f906f1a4affba647cce4cb17d818a_72.png)

![](img/f82f906f1a4affba647cce4cb17d818a_73.png)

![](img/f82f906f1a4affba647cce4cb17d818a_74.png)

![](img/f82f906f1a4affba647cce4cb17d818a_75.png)

![](img/f82f906f1a4affba647cce4cb17d818a_76.png)

![](img/f82f906f1a4affba647cce4cb17d818a_77.png)

以下是评估模型性能的指标：

![](img/f82f906f1a4affba647cce4cb17d818a_78.png)

![](img/f82f906f1a4affba647cce4cb17d818a_79.png)

![](img/f82f906f1a4affba647cce4cb17d818a_80.png)

![](img/f82f906f1a4affba647cce4cb17d818a_81.png)

![](img/f82f906f1a4affba647cce4cb17d818a_82.png)

![](img/f82f906f1a4affba647cce4cb17d818a_83.png)

*   模型预测结果为 **h(x)**。
*   真实标签为 **z**。
*   **ED** 是编辑距离，即将模型预测 **h(x)** 转换为正确标签 **z** 所需的最少插入、替换和删除操作次数。
*   然后，我们需要用序列长度 **|z|** 对其进行归一化，使其相对于目标大小。
*   最后，在所有数据上取平均值。

这个指标称为**标签错误率**，可以是词错误率、字符错误率或音素错误率等。

![](img/f82f906f1a4affba647cce4cb17d818a_85.png)

![](img/f82f906f1a4affba647cce4cb17d818a_86.png)

![](img/f82f906f1a4affba647cce4cb17d818a_87.png)

![](img/f82f906f1a4affba647cce4cb17d818a_88.png)

![](img/f82f906f1a4affba647cce4cb17d818a_89.png)

![](img/f82f906f1a4affba647cce4cb17d818a_90.png)

![](img/f82f906f1a4affba647cce4cb17d818a_91.png)

![](img/f82f906f1a4affba647cce4cb17d818a_92.png)

![](img/f82f906f1a4affba647cce4cb17d818a_93.png)

![](img/f82f906f1a4affba647cce4cb17d818a_94.png)

## CTC的核心思想：对齐与映射 🔄

![](img/f82f906f1a4affba647cce4cb17d818a_95.png)

现在回到核心问题：如何对齐长度不同的 **x** 和 **z**？通常，神经网络输入一个序列，输出另一个序列，且输入输出序列长度相同（均为 **T**）。

![](img/f82f906f1a4affba647cce4cb17d818a_97.png)

![](img/f82f906f1a4affba647cce4cb17d818a_98.png)

**y** 是输出序列，给出了概率。**y_t^k** 给出了在时间步 **t** 观察到标签 **k**（可以是词、字母等）的概率。这些概率来自循环神经网络。

![](img/f82f906f1a4affba647cce4cb17d818a_99.png)

![](img/f82f906f1a4affba647cce4cb17d818a_100.png)

![](img/f82f906f1a4affba647cce4cb17d818a_101.png)

![](img/f82f906f1a4affba647cce4cb17d818a_102.png)

![](img/f82f906f1a4affba647cce4cb17d818a_103.png)

![](img/f82f906f1a4affba647cce4cb17d818a_104.png)

![](img/f82f906f1a4affba647cce4cb17d818a_105.png)

![](img/f82f906f1a4affba647cce4cb17d818a_106.png)

![](img/f82f906f1a4affba647cce4cb17d818a_107.png)

但问题是我们有 **T** 个时间步的输出，太多了。技巧在于，除了词汇表中的所有标签外，我们额外添加一个**空白标签（blank）**。这样，对于输入中的某些向量，网络可以输出“空白”，表示没有有效标签（例如停顿、静音）。

因此，可能的输出路径 **π** 是长度为 **T** 的序列，每个元素来自扩展后的标签集（原标签+空白）。给定输入 **x**，我们可以从RNN读出路径 **π** 的概率，CTC在这里做了一个条件独立性假设。

![](img/f82f906f1a4affba647cce4cb17d818a_109.png)

但我们的标注数据是针对 **z** 的，而不是 **π**。因此，我们需要将标签 **z** 映射到路径 **π** 的空间。我们定义一个**多对一映射函数 B**，它通过**移除重复的标签**和**所有的空白标签**，将路径 **π** 压缩成最终的标签序列 **z**。

例如，路径 `-aa-b--`（`-`代表空白）经过映射 **B** 后，会变成 `ab`。这样，同一个最终标签 **z** 可能对应许多不同的路径 **π**。

## CTC的目标函数 🎯

我们的目标是，给定输入 **x**，最大化得到正确标签 **z** 的概率。由于一个 **z** 对应多个 **π**，我们需要将所有能映射到 **z** 的路径 **π** 的概率相加。

因此，CTC的目标函数（负对数似然）是：
`Loss = -log( P(z|x) ) = -log( ∑_{π∈B^{-1}(z)} P(π|x) )`

其中，`P(π|x)` 可以根据RNN输出的概率，在条件独立性假设下计算为每个时间步对应标签概率的乘积。

## 解码：从输出到文本 ➡️

训练好模型后，我们需要进行解码，即将网络输出转换为最终文本。一种简单的方法是**最佳路径解码**：
1.  选择概率最高的路径：`π* = argmax_π P(π|x)`
2.  然后应用映射函数去除重复和空白：`z* = B(π*)`

这种方法虽然简单，但效果通常不错。

## 动态编程：高效计算损失函数 ⚙️

直接计算所有可能路径 **π** 的概率之和是不可行的，因为路径数量随序列长度指数增长。解决方案是使用**动态编程**。

我们引入一个中间变量 **α_t(s)**，表示在时间步 **t**，已经生成了标签序列 **z** 的前 **s** 个字符（考虑空白插入后的序列 **z'**）的所有可能路径的概率之和。

动态编程的关键在于找到递推关系。**α_t(s)** 可以根据 **α_{t-1}(s)**、**α_{t-1}(s-1)** 和 **α_{t-1}(s-2)** 计算出来，具体规则取决于当前字符是空白还是重复标签。

初始化时，**α_1(1)** 设为空白概率，**α_1(2)** 设为第一个标签的概率。

最终，在最后一个时间步 **T**，标签 **z** 的概率为：`P(z|x) = α_T(|z'|) + α_T(|z'|-1)`，其中 **z'** 是在原标签 **z** 的每个字符之间以及首尾插入空白后形成的序列。

通过这种动态编程方法，我们可以高效地计算出CTC损失函数，从而能够训练模型。

## 总结 📚

本节课中我们一起学习了连接时序分类（CTC）算法。

*   CTC用于解决输入输出序列长度不一致的对齐问题，常见于语音识别、手写识别等任务。
*   其核心思想是引入**空白标签**，并定义一个**多对一映射**来移除输出路径中的空白和重复字符，从而得到最终的标签序列。
*   CTC的目标是最大化正确标签序列的**边缘概率**，即对所有能映射到该标签的路径概率求和。
*   直接求和计算量巨大，因此采用**动态编程**（前向算法）来高效计算损失函数。
*   解码时，可采用**最佳路径解码**等方法来从网络输出得到最终文本。

理解CTC需要掌握其对于序列对齐的巧妙处理以及动态编程的实现细节，它是序列建模领域的一个重要基础。