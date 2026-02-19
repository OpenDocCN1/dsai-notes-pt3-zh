# 课程 P162：L73.2 - GRU模型 🧠

在本节课中，我们将学习一篇关于循环神经网络的论文，这篇论文首次提出了门控循环单元。我们将把GRU与LSTM进行比较，并探讨它们在语音和音乐建模任务上的表现差异。

![](img/dd7c95da2c27c8dca958d10beedffb79_1.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_2.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_3.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_4.png)

## 概述 📋

![](img/dd7c95da2c27c8dca958d10beedffb79_5.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_6.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_7.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_8.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_9.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_10.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_11.png)

我们将使用两个数据集进行实验：一个用于复调音乐建模，另一个用于语音信号建模。请注意，这里的语音建模任务不同于语音识别，你可以将其理解为一种语言模型，核心任务是预测序列中的下一个输出。我们将在此任务上比较GRU、LSTM和基础RNN的性能。

![](img/dd7c95da2c27c8dca958d10beedffb79_12.png)

## 模型回顾 🔄

上一节我们介绍了序列建模的基本概念。本节中，我们来看看我们将要比较的几种具体模型。

![](img/dd7c95da2c27c8dca958d10beedffb79_14.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_15.png)

### 基础RNN

![](img/dd7c95da2c27c8dca958d10beedffb79_16.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_17.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_18.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_19.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_20.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_21.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_22.png)

对于生成式RNN，我们的目标是建模整个序列的概率。我们使用概率链式法则展开每一项。建模 `P(Xt | 历史)` 的方法是，将历史信息总结在一个隐藏状态 `H` 中，并以此作为条件。

![](img/dd7c95da2c27c8dca958d10beedffb79_23.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_24.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_25.png)

基础RNN的隐藏状态更新公式为：
`H_t = tanh(W * X_t + U * H_{t-1})`
其中，`tanh` 是激活函数，`W` 和 `U` 是权重矩阵。

### LSTM

![](img/dd7c95da2c27c8dca958d10beedffb79_27.png)

LSTM的结构更为复杂。它包含三个门：输入门、遗忘门和输出门。每个门都使用 `sigmoid` 激活函数，其权重矩阵通常是对角矩阵。

![](img/dd7c95da2c27c8dca958d10beedffb79_28.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_29.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_30.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_31.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_32.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_33.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_34.png)

以下是LSTM的核心公式：
*   遗忘门：`f_t = sigmoid(W_f * [H_{t-1}, X_t] + b_f)`
*   输入门：`i_t = sigmoid(W_i * [H_{t-1}, X_t] + b_i)`
*   候选记忆细胞：`\tilde{C}_t = tanh(W_C * [H_{t-1}, X_t] + b_C)`
*   记忆细胞更新：`C_t = f_t * C_{t-1} + i_t * \tilde{C}_t`
*   输出门：`o_t = sigmoid(W_o * [H_{t-1}, X_t] + b_o)`
*   隐藏状态输出：`H_t = o_t * tanh(C_t)`

![](img/dd7c95da2c27c8dca958d10beedffb79_35.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_36.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_37.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_38.png)

记忆细胞 `C_t` 通过遗忘部分旧信息和输入部分新信息来更新。

### GRU

![](img/dd7c95da2c27c8dca958d10beedffb79_40.png)

GRU是本文介绍的重点模型。它比LSTM更简单，只包含两个门：更新门和重置门。

![](img/dd7c95da2c27c8dca958d10beedffb79_41.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_42.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_43.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_44.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_45.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_46.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_47.png)

以下是GRU的核心公式：
*   更新门：`z_t = sigmoid(W_z * [H_{t-1}, X_t] + b_z)`
*   重置门：`r_t = sigmoid(W_r * [H_{t-1}, X_t] + b_r)`
*   候选隐藏状态：`\tilde{H}_t = tanh(W * X_t + U * (r_t * H_{t-1}))`
*   隐藏状态更新：`H_t = (1 - z_t) * H_{t-1} + z_t * \tilde{H}_t`

![](img/dd7c95da2c27c8dca958d10beedffb79_48.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_49.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_50.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_51.png)

为了直观理解，我们可以考虑两种特殊情况：
*   如果 `z_t = 1` 且 `r_t = 1`，则 `H_t = tanh(W * X_t + U * H_{t-1})`，这退化为基础RNN。
*   如果 `z_t = 0`，则 `H_t = H_{t-1}`，隐藏状态保持不变。
*   如果 `z_t = 1` 且 `r_t = 0`，则 `H_t = tanh(W * X_t)`，此时输出仅依赖于当前输入，与历史无关。

## 任务与数据集 🎵🎤

现在我们已经了解了模型结构，接下来看看它们将被应用在什么任务和数据上。

![](img/dd7c95da2c27c8dca958d10beedffb79_53.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_54.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_55.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_56.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_57.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_58.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_59.png)

我们的目标是写下序列的似然函数，取对数，然后进行最大似然估计。这个概率将由RNN、LSTM或GRU来建模，我们将比较它们的性能。

![](img/dd7c95da2c27c8dca958d10beedffb79_60.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_61.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_62.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_63.png)

实验使用两类数据集：

![](img/dd7c95da2c27c8dca958d10beedffb79_65.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_66.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_68.png)

### 1. 音乐建模数据集

![](img/dd7c95da2c27c8dca958d10beedffb79_70.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_71.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_72.png)

以下是用于音乐建模的数据集：
*   Nottingham
*   JSB Chorales
*   MuseData
*   Piano-midi.de

![](img/dd7c95da2c27c8dca958d10beedffb79_73.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_74.png)

这些数据集中的音乐符号可以看作是字符或单词。它们具有不同的维度（如93维、96维、105维、108维），并且是二进制向量。这正是“复调”的含义所在。

对于单声道音乐，输出概率向量的元素之和必须为1。但在复调音乐中，多个音符可能同时发声，因此不能保证这一点。所以，我们不再使用Softmax，而是对每个输出单元使用Sigmoid函数。Sigmoid输出0到1之间的值，但这些值之和不一定为1。然后我们写出损失函数并进行预测。这些是离散数据集。

### 2. 语音建模数据集

![](img/dd7c95da2c27c8dca958d10beedffb79_76.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_77.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_78.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_79.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_80.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_81.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_82.png)

语音数据是连续的。任务流程如下：
1.  获取原始音频。
2.  观察连续的20个样本作为上下文。
3.  基于这20个样本，预测接下来的10个样本。
4.  这是一个在一维原始音频信号上的预测任务。

![](img/dd7c95da2c27c8dca958d10beedffb79_83.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_84.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_85.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_86.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_87.png)

由于原始音频是连续变化的波形，我们需要为其建模一个连续分布。我们不再使用Softmax。一种方法是使用高斯分布，但它是单峰的。为了建模更复杂的多峰分布，我们可以使用混合高斯分布（多个高斯分布的混合）。这将给出序列的似然值。

![](img/dd7c95da2c27c8dca958d10beedffb79_89.png)

> **应用提示**：此类生成过程的应用包括文本转语音。之前我们学习的是语音转文本，而这里的方法可以实现反向过程。像Alexa、Siri等系统都在使用类似技术。在实际的文本转语音中，你不仅会以之前的音频样本为条件，还会以文本内容为额外条件信息。我们将在后续课程中看到相关例子。

![](img/dd7c95da2c27c8dca958d10beedffb79_90.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_91.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_92.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_93.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_94.png)

## 实验设置与公平比较 ⚖️

![](img/dd7c95da2c27c8dca958d10beedffb79_96.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_97.png)

为了公平地比较GRU和LSTM，我们需要控制变量。本论文的核心是比较它们在两种数据上的表现。

![](img/dd7c95da2c27c8dca958d10beedffb79_98.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_99.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_100.png)

为了进行公平比较，我们需要选择模型的隐藏单元数（即隐藏层维度），使得基础的tanh RNN、GRU和LSTM三者拥有大致相同数量的参数。这样，任何性能提升都将归因于模型架构的优劣，而非参数量的差异。

对于音乐数据，各模型参数量接近。对于语音数据，各模型参数量也几乎相同。

## 实验结果与分析 📊

![](img/dd7c95da2c27c8dca958d10beedffb79_102.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_103.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_104.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_105.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_106.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_107.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_108.png)

我们将报告模型在训练集和测试集上的平均负对数概率。在训练集上报告是为了确保没有过拟合，同时测试集上的结果可以看作是模型的“困惑度”。

![](img/dd7c95da2c27c8dca958d10beedffb79_109.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_110.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_111.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_112.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_113.png)

以下是主要发现：
*   在大多数数据上，GRU和LSTM的表现都优于基础的RNN（除了第一个数据集）。
*   有时GRU更好，有时LSTM更好。

一个更公平的衡量标准是观察“墙上时钟时间”（即实际训练时间），而不是迭代轮数。下图展示了在训练过程中，不同时间点下各模型在训练和测试集上的性能。

![](img/dd7c95da2c27c8dca958d10beedffb79_115.png)

![](img/dd7c95da2c27c8dca958d10beedffb79_116.png)

> （此处应插入展示训练时间与性能关系的图表描述）
> 图表显示，在某个数据集上，LSTM（可能用特定颜色表示）表现更好。而在另一个数据集（语音数据）上，GRU的表现优于LSTM。在另一个音乐数据集上，结果则不那么清晰。

最终，实验结果并非结论性的，无法明确断定LSTM和GRU哪个更好。这也解释了为什么在实践中，有些人使用LSTM，而有些人使用GRU——至少它们彼此相当。

## 总结 🎯

本节课我们一起学习了GRU模型的提出及其与LSTM、基础RNN的比较。
*   我们回顾了RNN、LSTM和GRU的基本原理与公式。
*   我们了解了在复调音乐建模和连续语音信号建模两种任务上的实验设置。
*   我们认识到，为了公平比较，需要控制模型的参数量。
*   实验结果表明，GRU和LSTM的性能在不同数据集上互有胜负，没有绝对的赢家，但两者都显著优于基础RNN。

因此，在选择序列模型时，可以根据具体任务和数据进行实验，以确定最适合的架构。