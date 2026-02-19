# 93：L42.2 - 组归一化 🧮

![](img/83ba17850318b0e304d7ea01fdccaf58_1.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_3.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_5.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_7.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_9.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_11.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_13.png)

在本节课中，我们将要学习一种名为**组归一化**的归一化技术。我们将了解它为何被提出，它与批归一化、层归一化等其他归一化方法有何不同，以及它在哪些场景下更具优势。

![](img/83ba17850318b0e304d7ea01fdccaf58_15.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_17.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_19.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_21.png)

## 概述

![](img/83ba17850318b0e304d7ea01fdccaf58_23.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_25.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_27.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_29.png)

我们之前在本学期很早就学习了批归一化。除了批归一化，还有其他类型的归一化方法。本节视频将**组归一化**作为最后一个主题进行介绍。

![](img/83ba17850318b0e304d7ea01fdccaf58_31.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_33.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_35.png)

批归一化非常强大，只要你的批大小合理（例如至少同时处理32张图像），它就能为你提供最先进的结果。然而，当你处理诸如**目标检测**、**图像分割**或**视频**等问题时，通常批大小会变得很小（例如大约为2），因为你无法在GPU上处理更多的数据。

![](img/83ba17850318b0e304d7ea01fdccaf58_37.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_39.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_41.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_43.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_45.png)

## 批归一化的局限性

![](img/83ba17850318b0e304d7ea01fdccaf58_47.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_49.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_51.png)

在目标检测等任务中，我们可能受限于GPU内存等约束，只能使用较小的批大小。例如，在进行目标检测时，我们通常一次只处理两张图像，但每张图像中又包含多个边界框提议区域。

![](img/83ba17850318b0e304d7ea01fdccaf58_53.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_55.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_57.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_59.png)

此外，当我们进行**迁移学习**时，如果预训练模型使用了批归一化层，那么在目标数据集（如PASCAL VOC或Microsoft COCO）上进行微调时，我们通常会**冻结**这些批归一化层的参数（gamma和beta）。这是因为目标数据集的批大小可能很小，导致统计量估计不准确。然而，在ImageNet上学习到的偏移和缩放参数，并不一定适用于新的数据集。

![](img/83ba17850318b0e304d7ea01fdccaf58_61.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_63.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_65.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_67.png)

因此，我们需要一种**与批大小无关**的归一化方法，使其统计量的计算不依赖于批次。组归一化正是这样一种方法。

![](img/83ba17850318b0e304d7ea01fdccaf58_69.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_71.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_73.png)

## 批大小对性能的影响

![](img/83ba17850318b0e304d7ea01fdccaf58_75.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_77.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_79.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_81.png)

实验表明，批归一化的性能对批大小非常敏感。当批大小为32时，错误率很低。当批大小降至16时，性能尚可。但随着批大小进一步减小（例如到2），错误率会显著上升（例如从24%升至35%左右）。

![](img/83ba17850318b0e304d7ea01fdccaf58_83.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_85.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_87.png)

相比之下，组归一化对批大小不那么敏感。当然，如果批大小足够大，批归一化的性能仍然优于组归一化。

![](img/83ba17850318b0e304d7ea01fdccaf58_89.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_91.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_93.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_95.png)

## 不同归一化方法对比

![](img/83ba17850318b0e304d7ea01fdccaf58_97.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_99.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_101.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_103.png)

为了理解组归一化，我们首先需要将其与其他归一化方法进行对比。考虑一个具有批（N）、通道（C）、高度（H）和宽度（W）维度的张量。

![](img/83ba17850318b0e304d7ea01fdccaf58_105.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_107.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_109.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_111.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_113.png)

以下是不同归一化方法计算统计量（均值和标准差）时所考虑的维度集合：

![](img/83ba17850318b0e304d7ea01fdccaf58_115.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_117.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_119.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_121.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_123.png)

*   **批归一化**：在批维度（N）、高度（H）和宽度（W）上计算统计量。公式表示为：`S_i = {k | k_C = i_C}`，即固定通道索引 `i_C`，在其他所有维度上计算。
*   **层归一化**：在通道（C）、高度（H）和宽度（W）上计算统计量。它对批大小不敏感，通常在循环神经网络中使用，在图像任务上表现不佳。
*   **实例归一化**：在单个样本（批大小为1）的高度（H）和宽度（W）上计算统计量。它主要用于生成对抗网络或风格迁移等任务。
*   **组归一化**：它介于层归一化和实例归一化之间。它将通道维度分成若干组（例如2组），然后在每个组内，沿着组内的通道、高度和宽度计算统计量。

![](img/83ba17850318b0e304d7ea01fdccaf58_125.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_127.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_129.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_131.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_133.png)

## 组归一化的原理

![](img/83ba17850318b0e304d7ea01fdccaf58_135.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_137.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_139.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_141.png)

所有归一化方法的核心操作都是相同的：对于输入特征 `x_i`，减去均值并除以标准差。

![](img/83ba17850318b0e304d7ea01fdccaf58_143.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_145.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_147.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_149.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_151.png)

`x_i` 是一个多维索引，包含 `(i_N, i_C, i_H, i_W)`。不同方法的区别在于计算均值和标准差时所使用的索引集合 `S_i` 不同。

![](img/83ba17850318b0e304d7ea01fdccaf58_153.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_155.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_157.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_159.png)

对于组归一化，其索引集合 `S_i` 定义为：
`S_i = {k | k_N = i_N, floor(k_C / (C/G)) = floor(i_C / (C/G))}`

![](img/83ba17850318b0e304d7ea01fdccaf58_161.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_163.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_165.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_167.png)

其中：
*   `G` 是分组数量（例如32）。
*   `C/G` 是每组包含的通道数。
*   这个公式意味着，我们固定批索引 `i_N`，并且确保索引 `k` 和 `i` 属于同一个通道组。

![](img/83ba17850318b0e304d7ea01fdccaf58_169.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_171.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_173.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_175.png)

简单来说，组归一化的计算方式是：**在同一个批样本内，将通道分成组，然后在每个组内，跨该组的所有通道以及空间维度（H和W）计算均值和方差。**

![](img/83ba17850318b0e304d7ea01fdccaf58_177.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_179.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_181.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_183.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_185.png)

与批归一化类似，组归一化在归一化后也会引入可学习的缩放参数 `gamma` 和偏移参数 `beta`，它们都是针对每个通道的向量。这确保了网络仍能学习到适合数据的特征分布。

![](img/83ba17850318b0e304d7ea01fdccaf58_187.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_189.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_191.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_193.png)

## 代码实现思路

![](img/83ba17850318b0e304d7ea01fdccaf58_195.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_197.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_199.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_201.png)

在代码层面（如PyTorch、MXNet），组归一化的实现可以遵循以下思路：

![](img/83ba17850318b0e304d7ea01fdccaf58_203.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_205.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_207.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_209.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_211.png)

1.  接收输入 `x` 以及参数 `gamma`、`beta` 和一个小常数 `epsilon`（防止除零）。
2.  根据分组数 `G` 对输入进行重塑，增加一个组维度。
3.  在组维度、高度和宽度维度上计算均值和方差。
4.  使用计算出的均值和方差对输入进行归一化。
5.  应用缩放 `gamma` 和偏移 `beta`。
6.  将输出重塑回原始形状。

![](img/83ba17850318b0e304d7ea01fdccaf58_213.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_215.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_217.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_219.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_221.png)

核心在于通过重塑张量，将组归一化的统计量计算转化为在特定维度上的规约操作。

![](img/83ba17850318b0e304d7ea01fdccaf58_223.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_225.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_227.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_229.png)

## 性能对比

![](img/83ba17850318b0e304d7ea01fdccaf58_231.png)

![](img/83ba17850318b0e304d7ea01fdccaf58_233.png)

在ImageNet分类任务上的实验显示了不同归一化方法的性能：
*   批归一化错误率最低。
*   实例归一化错误率最高。
*   层归一化表现不佳。
*   组归一化性能损失很小（仅比批归一化高约0.5%）。

**关键优势体现在批大小变小时**：当批大小从32降至16再到8时，组归一化的优势开始显现。对于小批量任务（如检测、分割），你可以使用组归一化并让 `gamma` 和 `beta` 在新数据集上继续学习，而无需像批归一化那样冻结它们。

在视频分类任务（如Kinetics数据集）上，当每个GPU处理的视频片段数量（即有效批大小）很小时，使用批归一化会导致性能显著下降，而组归一化的性能曲线则保持稳定。

## 总结

本节课我们一起学习了两种强大的技术：
1.  非局部操作（非局部块）。
2.  **组归一化**：它并非在所有情况下都取代批归一化，但其性能对批大小不敏感。当你的设备限制导致批大小较小，并且处理的任务是**图像检测、分割或视频分析**时，选择组归一化可能是比批归一化更好的选择。

最后需要说明，更大的批大小通常有利于并行化以加速训练，并能提供更准确的梯度估计。但这是一种权衡，因为过大的批大小可能会减少梯度中的噪声，而这些噪声有时有助于模型找到泛化能力更好的局部最优解。