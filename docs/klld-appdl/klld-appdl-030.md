# 30：L16 - 深度压缩 [续] 🗜️ 🧠

![](img/6551d0e6d3bbafb876cfbf10ae87a455_1.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_2.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_3.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_4.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_5.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_6.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_7.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_8.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_9.png)

在本节课中，我们将继续学习深度压缩技术。我们将详细探讨剪枝、量化和哈夫曼编码这三种核心方法，了解它们如何协同工作，以显著减少神经网络模型的大小，同时尽可能保持其预测精度。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_11.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_12.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_13.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_14.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_15.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_16.png)

上一节我们介绍了深度压缩的基本概念，本节中我们将深入探讨其具体实现细节。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_17.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_18.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_19.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_20.png)

## 1. 剪枝（Pruning）回顾与索引存储优化

![](img/6551d0e6d3bbafb876cfbf10ae87a455_22.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_23.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_24.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_25.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_26.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_27.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_28.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_29.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_30.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_31.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_32.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_33.png)

上一节我们介绍了剪枝，其核心思想是神经网络通常存在参数冗余，许多权重值接近零。我们可以将这些接近零的权重强制设置为零，这个过程称为剪枝。剪枝后，权重矩阵会变得稀疏。

对于稀疏矩阵，我们可以使用高效的稀疏线性代数进行计算，并使用压缩格式（如压缩稀疏行 CSR 或压缩稀疏列 CSC）进行存储。存储所需的数据量大致与非零元素的数量成正比，而非矩阵的总大小 `n²`。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_35.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_36.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_37.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_38.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_39.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_40.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_41.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_42.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_43.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_44.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_45.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_46.png)

然而，存储稀疏矩阵时，除了存储非零值本身，还需要存储它们的位置索引。为了进一步优化，我们可以存储索引的差值，而非绝对位置。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_48.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_49.png)

以下是存储索引差值的具体方法：

![](img/6551d0e6d3bbafb876cfbf10ae87a455_50.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_51.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_52.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_53.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_54.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_55.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_56.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_57.png)

*   对于卷积层，我们使用 8 位来存储索引差值。
*   对于全连接层，我们使用 5 位来存储索引差值。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_59.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_60.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_61.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_62.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_63.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_64.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_65.png)

这意味着索引差值必须小于 `2^8 = 256`（卷积层）或 `2^5 = 32`（全连接层）。如果两个非零元素之间的索引差值超过了这个限制，我们就在中间插入一个“填充零”，然后重新开始计算差值。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_66.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_67.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_68.png)

**示例**：
假设我们有一个数组，第一个非零元素在位置 0（值 3.4），下一个在位置 4。差值 4 小于 8，可以直接存储 4。
再下一个非零元素在位置 15。差值 15-4=11 大于 8。因此，我们在位置 4+8=12 处插入一个填充零，然后存储下一个非零元素（位置15）与这个填充零位置（位置12）的差值，即 3。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_70.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_71.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_72.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_73.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_74.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_75.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_76.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_77.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_78.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_79.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_80.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_81.png)

这样，我们通过存储索引差值而非绝对位置，更高效地利用了内存。解码时，每当遇到一个填充零，我们就知道下一个索引值是当前索引加上最大值（8或32）再加上存储的差值。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_83.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_84.png)

这种方法的效率取决于非零元素的分布。在最坏情况下可能效率不高，但在平均情况下能有效节省存储空间。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_85.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_86.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_87.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_88.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_89.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_90.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_91.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_92.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_93.png)

## 2. 量化（Quantization）与权重共享

![](img/6551d0e6d3bbafb876cfbf10ae87a455_95.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_96.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_97.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_98.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_99.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_100.png)

剪枝可以带来约 9 到 13 倍的压缩率。量化则能带来更显著的提升，其核心思想是**权重共享**。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_101.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_102.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_103.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_104.png)

![](img/6551d0e6d3bbafb876cfbf10ae87a455_105.png)

权重共享在深度学习中很常见，例如卷积操作就是在空间上共享权重。量化的权重共享是指：将数值相近的权重分组，并用一个共同的“中心值”来代表该组所有权重。

![](img/6551d0e6d3bbafb876cfbf10ae87a455_107.png)

**具体步骤如下**：

1.  **聚类**：对所有权重值运行 K-Means 聚类算法。例如，将所有权重聚合成 K 个簇。
2.  **存储**：我们只需存储：
    *   **K 个中心值**（Centroids）：每个中心值是一个浮点数。
    *   **权重索引表**：一个查找表，记录每个原始权重属于哪个簇（用 `log₂K` 位表示）。

**示例**：
假设有 16 个权重，聚类为 4 个中心值：2.0, 1.5, 0.0, -1.0。
原本需要存储 16 个浮点数（每个 32 位）。
现在只需存储：
*   4 个中心值（4 * 32 位）。
*   16 个簇索引（16 * `log₂4` 位 = 16 * 2 位）。

压缩率计算公式为：
`压缩率 = (n * b) / (n * log₂k + k * b)`
其中，`n` 是权重数量，`b` 是原始位数（如32），`k` 是中心数量。

在实际应用中：
*   对卷积层，使用 `k=256`（8位索引）。
*   对全连接层，使用 `k=32`（5位索引）。

为什么要区别对待？因为全连接层通常参数更多、更密集，对存储成本更敏感；同时，其参数可能承载更多信息，需要更精细的区分度。量化后，模型整体可达到 27 到 31 倍的压缩率。

## 3. 量化网络的微调（Fine-tuning）

仅仅进行量化会损失模型精度。为了保持精度，我们需要对量化后的网络进行微调。

微调的关键是计算损失函数相对于**中心值**的梯度，而非原始权重。我们使用聚类索引将原始权重的梯度分组求和，用于更新对应的中心值。

梯度计算公式如下：
`∂L/∂C_k = Σ ∂L/∂W_i * I(W_i ∈ Cluster_k)`
其中，`I(·)` 是指示函数，当权重 `W_i` 属于第 `k` 个簇时为 1。

通过这种方式，我们可以在保持量化结构（共享权重）的同时，利用训练数据来调整中心值，从而恢复模型的准确率。

## 4. 哈夫曼编码（Huffman Encoding）

在量化的基础上，我们可以进一步应用哈夫曼编码进行无损压缩。

其原理是：统计所有**中心值索引**在权重索引表中出现的频率。出现频率高的索引，用较短的二进制码表示；出现频率低的索引，用较长的二进制码表示。这类似于为整个网络的所有权重索引建立一个全局的压缩字典。

**注意**：哈夫曼编码作用于存储阶段，是对“中心值索引”这种符号的压缩，而不是直接压缩浮点数值本身。它利用了权重分布的统计特性，如果索引分布均匀，则收益较小；如果某些索引出现频率很高，则能显著节省存储空间。

结合剪枝、量化和哈夫曼编码，最终可以将模型压缩 35 到 49 倍。

## 5. 效果总结与思考

下图展示了压缩率与模型精度之间的关系。仅使用剪枝时，当压缩率过高（如仅保留原模型6%的参数），精度会大幅下降。但当结合量化与微调后，即使压缩到原模型的3%-4%（如AlexNet），也能保持与原始模型相近的精度。

**需要思考的问题**：
*   这种压缩方法与**Dropout**有何不同？（Dropout随机丢弃激活，而剪枝是永久移除不重要的权重连接。）
*   压缩是否会改变模型的**错误模式**？（可能。评估时除了看整体精度，还可以分析混淆矩阵的变化。）
*   不同网络架构（如ResNet、VGG）和数据集上的压缩效果是否一致？（这是一个值得研究的开放性问题。）

---

本节课中我们一起学习了深度压缩的完整流程：通过**剪枝**移除冗余连接，通过**量化与权重共享**减少权重的唯一值数量，通过**微调**恢复模型精度，最后利用**哈夫曼编码**对存储进行进一步优化。这套组合拳能极大地压缩神经网络模型，使其更适合部署在存储和计算资源受限的设备上。