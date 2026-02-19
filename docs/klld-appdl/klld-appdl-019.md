# 19：L9.2 - 宽残差网络 🧠

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_1.png)

在本节课中，我们将学习宽残差网络（Wide Residual Networks, WRNs）的核心概念。我们将探讨如何通过增加网络的宽度而非深度来提升性能，并理解其背后的设计原理与实验验证。

---

## 概述

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_3.png)

上一节我们介绍了残差网络（ResNet）及其深度设计。本节中我们来看看如何通过增加网络的宽度来构建更高效的模型，即宽残差网络。

宽残差网络保留了残差连接，但通过增加卷积层的通道数（即“宽度”）来提升模型能力。其基本思想是：与其一味增加网络深度，不如在保持合理深度的同时增加宽度，这样通常能获得更好的性能与更快的训练速度。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_5.png)

## 核心概念与符号定义

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_7.png)

宽残差网络使用以下符号进行系统描述：

*   **`n`**：网络中的卷积层总数。
*   **`k`**：展宽因子（Widening Factor），用于乘以卷积层的通道数。
*   **`l`**：每个残差块内的卷积层数量。
*   网络记作 **`WRN-n-k`**。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_9.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_11.png)

一个基础的残差块包含两个 `3x3` 卷积，其结构可简化为：
```python
# 基础残差块结构示意
x_input = ...
x = Conv3x3(x_input)
x = Conv3x3(x)
output = x + x_input  # 残差连接
```

## 块结构（Microstructure）研究

以下是论文中研究的六种不同的残差块结构：

1.  **`B(3,3)`**：基础块，两个 `3x3` 卷积。
2.  **`B(3,1,3)`**：`3x3` 卷积 -> `1x1` 卷积 -> `3x3` 卷积。
3.  **`B(1,3,1)`**：`1x1` 卷积 -> `3x3` 卷积 -> `1x1` 卷积（瓶颈结构，但宽度一致）。
4.  **`B(1,3)`**：`1x1` 卷积 -> `3x3` 卷积。
5.  **`B(3,1)`**：`3x3` 卷积 -> `1x1` 卷积。
6.  **`B(1,1,3)`**：`1x1` 卷积 -> `1x1` 卷积 -> `3x3` 卷积（类 Network-in-Network 风格）。

## 确定每块卷积层数量 `l`

首先需要确定每个残差块内应包含多少卷积层。实验在 CIFAR-10 数据集上进行，固定其他参数，比较不同 `l` 值对应的错误率。

以下是实验结果：
*   `l = 1`：性能最差。
*   `l = 2`：性能最佳。
*   `l = 3` 和 `l = 4`：性能次于 `l=2`。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_13.png)

因此，后续研究将采用 **`l = 2`** 作为每个块的标准卷积层数。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_15.png)

## 确定最佳块结构与宏观结构

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_17.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_19.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_21.png)

在确定 `l=2` 后，需要从六种块结构中选出最佳者，并研究深度 `n` 和宽度因子 `k` 的影响。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_23.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_25.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_27.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_29.png)

实验表明，**`B(3,3)`** 块结构（即基础块）在 CIFAR-10 上表现最好。当网络深度 `n=28`，宽度因子 `k` 在一定范围内时，能取得优异的平衡。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_31.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_33.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_35.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_37.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_39.png)

## 跨数据集与 Dropout 的影响

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_41.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_43.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_45.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_47.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_49.png)

研究还对比了不同配置在 CIFAR-10 和 CIFAR-100 上的表现：

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_51.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_53.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_55.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_57.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_59.png)

*   在 CIFAR-10 上，`WRN-28-10`（深度 28，宽度因子 10）表现最佳。
*   在 CIFAR-100 上，`WRN-28-12`（宽度因子 12）表现更好。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_61.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_63.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_65.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_67.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_69.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_71.png)

这表明最优参数可能因数据集而异。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_73.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_75.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_77.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_79.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_81.png)

此外，在残差块的非线性路径中加入 **Dropout** 被证明是有益的。它鼓励网络在可能时利用捷径（恒等映射）路径，起到了正则化作用，提升了准确率。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_83.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_85.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_87.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_89.png)

## 性能与速度权衡

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_91.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_93.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_95.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_97.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_99.png)

宽残差网络在速度和精度上展现了优势：

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_101.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_103.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_105.png)

一个 `WRN-40-4`（40层深，4倍宽）的网络，其错误率与一个极深的 `1001` 层原始 ResNet 网络相当，但前者的处理速度（例如 68 毫秒/图像）远快于后者（512 毫秒/图像）。更宽的架构更易于并行计算，从而显著加速。

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_107.png)

![](img/23afc7fa5a9ddb9cd512265d9b7f1f0b_109.png)

## 关于维度匹配的说明

当残差块的输入与输出维度不匹配时，无法直接使用恒等捷径连接。但在整个网络中，这种维度变化通常只发生在少数几个块中（例如仅3处）。由于涉及的权重数量极少，其对整体训练的影响可以忽略不计，因此无需特别担忧。

---

## 总结

本节课中我们一起学习了宽残差网络。我们了解到，通过系统性地增加网络宽度（使用展宽因子 `k`），并采用合适的块结构（如 `B(3,3)`），可以在保持残差连接优点的同时，构建出比单纯加深网络更高效、训练更快的模型。实验指导我们选择了每块2个卷积层（`l=2`），并展示了宽度、深度、Dropout 以及不同数据集对最终性能的影响。宽残差网络的核心思想在于：**宽度与深度同样重要，且更宽的模型通常能带来更好的精度与速度的平衡**。