# 163：L73.3 - 期望转录损失 📝

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_1.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_2.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_3.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_4.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_5.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_6.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_7.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_8.png)

在本节课中，我们将要学习一种用于语音识别和手写识别等序列任务的特殊损失函数——期望转录损失。我们将从连接时序分类的基本概念出发，探讨如何将不可微的评价指标（如词错误率）融入模型训练，并推导出期望转录损失的梯度计算方法。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_9.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_10.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_11.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_12.png)

## 概述：从 CTC 到期望转录损失

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_14.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_15.png)

上一节我们介绍了连接时序分类，它解决了输入与输出序列不对齐的问题。本节中，我们来看看如何进一步优化 CTC 损失，使其更贴近我们最终的评价指标。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_16.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_17.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_18.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_19.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_20.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_21.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_22.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_23.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_24.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_25.png)

CTC 损失基于一个观察：一个手写单词如果不被分割就无法识别，而如果不被识别就无法分割，这是一个悖论。因此，CTC 不要求输入和输出严格对齐，而是允许模型输出包含空白符和重复标签的“路径”，再通过一个映射函数 **B** 将其转换为最终的标签序列。

**公式：** `B(a) = z`，其中 `a` 是模型输出的路径（包含标签和空白），`z` 是去除重复标签和空白后的最终标签序列。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_27.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_28.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_29.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_30.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_31.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_32.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_33.png)

## CTC 路径与标签映射

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_34.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_35.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_36.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_37.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_38.png)

以下是 CTC 工作原理的核心步骤：

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_40.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_41.png)

1.  **模型输出路径**：给定输入 `x`（如频谱图），双向 RNN 模型会输出一个序列 `a`，其中每个时间步可以是标签或空白符。
2.  **定义映射操作**：我们定义一个操作符 **B**，它首先移除路径 `a` 中连续的重复标签，然后移除所有的空白符。
3.  **得到最终标签**：应用 **B** 操作后，我们得到最终的标签序列 `z`。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_42.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_43.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_44.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_45.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_46.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_47.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_48.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_49.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_50.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_51.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_53.png)

一个关键点是，**多条不同的路径 `a` 可能映射到同一个最终标签序列 `z`**。例如，路径 `“-A-B-B--C”` 和 `“A-A-B--C-”` 经过 **B** 操作后，都可能得到 `“ABC”`。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_55.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_56.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_57.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_58.png)

因此，给定目标标签 `z`，其概率是所有能映射到 `z` 的路径 `a` 的概率之和：
**公式：** `P(z|x) = Σ_{a∈B^{-1}(z)} P(a|x)`

这个概率可以通过动态规划高效计算，并作为 CTC 损失函数来优化模型参数。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_60.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_61.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_62.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_63.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_64.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_65.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_66.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_67.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_68.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_69.png)

## 引入期望转录损失

在谷歌神经机器翻译系统中，我们了解到让目标函数更接近最终的评价指标（如 BLEU 分数）有助于提升模型性能。CTC 损失也存在类似问题：它最大化正确标签的似然，但并未直接优化词错误率。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_71.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_72.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_73.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_74.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_75.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_76.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_77.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_78.png)

词错误率衡量的是将模型预测序列转换为真实序列所需的最小编辑操作（插入、删除、替换）次数。它是一个**不可微**的离散函数，无法直接用于梯度下降。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_79.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_80.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_81.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_82.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_84.png)

期望转录损失的核心思想是：**我们不直接最小化词错误率，而是最小化词错误率的期望值**。这样，模型不仅能从完全错误中学习，也能从“接近正确”的预测中学习，因为不同的错误其“严重程度”不同。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_85.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_86.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_87.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_88.png)

期望转录损失的定义如下：
**公式：** `L = E_{z~P(·|x)} [WER(z, z*)]`
其中，`WER` 是词错误率函数，`z*` 是真实标签序列，期望是对模型预测的所有可能标签序列 `z` 取的。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_90.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_91.png)

## 损失函数的推导与梯度计算

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_92.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_93.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_94.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_95.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_96.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_97.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_98.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_99.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_100.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_101.png)

我们的目标是计算损失 `L` 对模型参数 `θ` 的梯度。首先，利用 CTC 中 `P(z|x)` 的定义，将求和从 `z` 转换到路径 `a`：

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_103.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_104.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_105.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_106.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_107.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_108.png)

`L = Σ_z P(z|x) * WER(z, z*) = Σ_a P(a|x) * WER(B(a), z*)`

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_110.png)

现在，损失是路径概率 `P(a|x)` 和该路径对应词错误率的加权和。我们需要计算 `∂L/∂P(a|x)`。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_112.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_113.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_114.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_115.png)

这里使用一个重要的数学技巧：对于函数 `f(p)`，其导数可以写成 `f(p) * ∂log f(p)/∂p`。我们将这个技巧应用于 `L` 对每个时间步输出概率 `P(k, t|x)`（即模型在时间 `t` 输出标签 `k` 的概率）的导数。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_116.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_117.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_118.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_119.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_120.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_121.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_122.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_123.png)

经过推导（中间涉及指示函数和概率的抵消），我们得到梯度的关键表达式：

`∂L/∂P(k, t|x) = E_{a~P(·|x)} [ WER(B(a), z*) | a_t = k ]`

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_125.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_126.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_127.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_128.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_129.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_130.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_131.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_132.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_133.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_134.png)

这个公式的含义是：**损失对“在时间t预测标签k”的概率的梯度，等于在“强制时间t的预测为k”的条件下，所有路径词错误率的期望值**。

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_135.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_136.png)

## 蒙特卡洛估计与训练过程

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_138.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_139.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_140.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_141.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_142.png)

上述期望值在实际中无法精确计算。我们可以使用蒙特卡洛方法进行估计：

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_143.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_144.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_145.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_146.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_147.png)

![](img/52d4d5888bf7b17853ab1bd50fc8e34e_148.png)

1.  从当前模型分布 `P(a|x)` 中采样若干条路径 `a`。
2.  对于每个样本路径 `a` 和每个时间步 `t`，我们“干预”这个样本，将其在时间 `t` 的预测固定为某个标签 `k`，得到一条新路径 `a'`（仅该时间步被修改）。
3.  计算原路径 `a` 和新路径 `a'` 对应的词错误率 `WER(B(a), z*)` 和 `WER(B(a‘), z*)`。根据公式，这有助于估计梯度。
4.  利用这些采样估计出的梯度，结合链式法则，我们可以进一步计算损失对模型原始输出 logits `y_tk` 的梯度，最终通过反向传播更新模型参数。

剩下的步骤是标准的神经网络训练：计算 `∂L/∂y_tk`（涉及 softmax 函数的导数），然后通过反向传播更新 RNN 的参数。

## 总结

本节课中我们一起学习了期望转录损失。我们从 CTC 损失出发，指出了其与最终评价指标（词错误率）的差异。为了弥补这一差距，我们引入了期望转录损失，它通过最小化词错误率的期望值，使模型训练目标与评估标准更一致。

我们详细推导了该损失的梯度，其核心在于计算在特定时间步强制输出特定标签的条件下，词错误率的期望。由于该期望难以精确求解，我们介绍了使用蒙特卡洛采样进行估计的实用方法。期望转录损失是强化学习中策略梯度方法在序列预测任务中的一个重要应用，它让模型能够从不同“质量”的预测中更细致地进行学习。