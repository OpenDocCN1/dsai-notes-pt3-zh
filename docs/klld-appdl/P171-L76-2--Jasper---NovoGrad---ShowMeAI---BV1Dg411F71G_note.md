# 🧠 P171：Jasper & NovoGrad 架构与优化器详解

在本节课中，我们将学习一个名为 **Jasper** 的端到端语音识别模型架构，以及一个名为 **NovoGrad** 的优化器。我们将了解Jasper如何通过精心设计的卷积神经网络和CTC损失函数来处理语音识别任务，并探讨当标准优化器（如Adam）效果不佳时，如何使用NovoGrad来稳定和加速训练。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_1.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_2.png)

---

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_3.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_4.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_5.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_6.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_7.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_8.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_9.png)

## 📊 概述：从数据与损失到网络设计

上一节我们讨论了数据和损失函数。本节我们将回到CTC损失，并重点研究卷积神经网络（或广义上的神经网络）的设计。这是一篇工程导向的论文，因此会涉及大量实验和试错，最终目标是在词错误率（WER）上获得更好的性能。这意味着需要进行大量实验，其最终架构并非凭空想象，而是投入了大量时间和GPU计算资源才得出的结果。

## 🏗️ Jasper 网络架构详解

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_11.png)

Jasper是一个纯粹的前馈网络架构，没有编码器-解码器结构。其核心流程如下：输入频谱图，经过一系列卷积和残差块处理，最后通过CTC损失进行优化。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_12.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_13.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_14.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_15.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_16.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_17.png)

以下是Jasper架构的核心组件：

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_18.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_19.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_20.png)

### 1. 初始卷积层（Prologue）
首先，对输入的频谱图进行第一次卷积操作。具体配置如下：
*   **卷积核宽度**：`11`
*   **滤波器数量**：`256`
*   **激活函数**：`ReLU`

这构成了网络的起点。

### 2. 残差块（Residual Blocks）
在初始卷积之后，网络由多个**残差块**堆叠而成。一个残差块会被重复 **B** 次。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_22.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_23.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_24.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_25.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_26.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_27.png)

每个残差块内部又包含 **R** 个**子块**。每个子块的结构如下：
1.  一维卷积
2.  批归一化（Batch Norm）
3.  ReLU激活
4.  丢弃法（Dropout）

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_28.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_29.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_30.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_31.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_32.png)

在重复R次子块后，特征的通道维度可能会发生变化。为了确保残差连接能够顺利进行，需要使用一个 **1x1 卷积** 配合批归一化来调整维度，然后将调整后的输入与子块的输出相加。这是一种类似ResNet的残差连接方式。

### 3. 密集残差网络（Dense Residual）
Jasper还融合了DenseNet的思想，形成了“密集残差”网络。
*   在**DenseNet**中，会将前面所有层的输出在通道维度上进行**拼接（Concatenate）**，然后乘以权重。
*   在Jasper的密集残差设计中，则是将前面层的输出**相加（Add）** 在一起。

这种结合旨在同时利用残差连接和密集连接的优势。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_34.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_35.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_36.png)

### 4. 尾声与输出（Epilogue）
在所有的残差块之后，网络进入尾声部分：
1.  进行额外的卷积操作。
2.  使用一个 **1x1 卷积** 将通道数映射到**词汇表大小**。
3.  最后连接 **CTC损失函数** 进行计算。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_37.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_38.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_39.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_40.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_41.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_42.png)

整个架构可以概括为：**1个Prologue块 + B个主块（每个主块包含R个子块） + 1个Epilogue块**。因此，模型深度可以表示为 **Jasper BxR**。

---

## ⚙️ NovoGrad 优化器

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_44.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_45.png)

当我们设计好架构、准备好数据并定义好损失函数后，就可以开始训练了。通常我们会使用Adam优化器，但有时训练可能无法收敛。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_46.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_47.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_48.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_49.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_50.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_51.png)

此时，可以考虑改变优化策略。**NovoGrad** 与Adam类似，但有一个关键区别：
*   **Adam**：为网络中的**每一个权重**单独计算自适应学习率。
*   **NovoGrad**：为**每一层权重**计算一个**共享的**自适应学习率。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_52.png)

### NovoGrad 的工作原理
自适应性的来源是梯度的二阶矩估计。
*   在Adam中，对每个权重的梯度取平方：`grad²`
*   在NovoGrad中，将一层内所有权重的梯度视为一个**向量**，计算该梯度向量的**L2范数**，并以此为基础计算该层共享的自适应率。

其核心公式可以表示为：
`adaptive_rate_per_layer ∝ 1 / sqrt(||grad_vector||² + ε)`

其余部分（如动量）与标准的Adam优化器相似。同时，可以很方便地加入权重衰减（Weight Decay），权重衰减等价于对权重的L2范数进行惩罚。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_54.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_55.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_56.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_57.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_58.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_59.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_60.png)

这种**按层共享自适应学习率**的方式，有助于稳定深层网络（如Jasper BxR这样很深的模型）的训练。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_61.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_62.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_63.png)

---

## 📈 性能对比与讨论

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_65.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_66.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_67.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_68.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_69.png)

在LibriSpeech等语音数据集上，我们可以比较不同模型的词错误率（WER）。一些模型是端到端训练的，而另一些则需要将训练分为多个部分。

### 语言模型的影响
在解码阶段，使用不同的语言模型会对结果产生显著影响：
*   **N-gram**：最简单的语言模型。
*   **卷积语言模型/RNN**：更复杂的传统神经网络模型。
*   **Transformer-XL**：现代更强大的语言模型。

使用更好的语言模型可以降低**困惑度（Perplexity）**，而更低的困惑度通常与更低的词错误率高度相关。语言模型越好，模型犯的错误就越少。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_71.png)

### 架构对比：残差 vs. 密集残差
为了公平比较DenseNet、ResNet和Dense Residual（Jasper）的性能，需要在参数量相近的条件下进行。实验表明，在多个数据集上，**密集残差（Dense Residual）** 架构通常表现最佳，尽管不同架构之间的性能差距可能很小。

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_72.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_73.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_74.png)

![](img/6b5a3fdad65b9332b4b1adf66cbc4050_75.png)

---

## ❓ 问答环节

**问**：在对比表格中，LAS（Listen, Attend and Spell）模型似乎表现最好，我的理解正确吗？即使它没有在所有数据上都报告结果。
**答**：是的，你指的是我们之前讲过的LAS模型。表格中显示它在某些数据集上取得了2.5和5.8的WER。但需要注意的是，LAS使用了不同的框架（编码器-解码器）和损失函数，并且同时应用了数据增强技术。CTC模型和编码器-解码器模型是两种相互竞争的框架，性能上的优势可能部分源于数据增强。两者都很有用，了解这两种方法非常重要。

---

## 🎯 总结

本节课我们一起深入学习了**Jasper语音识别模型**和**NovoGrad优化器**。

我们了解到：
1.  **Jasper** 是一个基于CTC损失的、深度卷积神经网络，它采用了“密集残差”块的设计，通过大量实验得到优化。
2.  **NovoGrad** 是一种改进的自适应优化器，它通过为每一层（而非每一个权重）计算共享的自适应学习率，来稳定深层网络的训练。
3.  在语音识别系统中，**语言模型**的质量对最终词错误率有重大影响，更好的语言模型（如Transformer-XL）能显著提升性能。
4.  不同的网络架构（如ResNet, DenseNet, Dense Residual）在参数量公平的条件下进行比较，密集残差架构展现了其优势。

理解这些工程化的模型设计和优化技巧，对于构建高效的语音识别系统至关重要。