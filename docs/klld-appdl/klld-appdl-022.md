# 22：Inception-V4 架构详解 🧠

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_1.png)

在本节课中，我们将学习 Inception-V4 网络架构。Inception-V4 是 Inception 系列的第四个重要版本，它在 Inception-V3 的基础上进行了多项改进，并引入了残差连接（ResNet）的思想，以提升训练效率和模型性能。

---

## 📊 网络宏观结构

上一节我们回顾了 Inception 系列的发展历程，本节中我们来看看 Inception-V4 的整体架构。

Inception-V4 的宏观结构如下：

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_3.png)

*   输入图像尺寸为 **299×299×3**（高×宽×通道）。
*   首先经过一个 **Stem** 模块，输出尺寸变为 **35×35×384**。
*   随后是 **4 个 Inception-A** 模块。
*   接着是一个 **Reduction-A** 模块，将特征图尺寸从 35 降至 17。
*   然后是 **7 个 Inception-B** 模块。
*   再经过一个 **Reduction-B** 模块，将特征图尺寸从 17 降至 8。
*   之后是 **3 个 Inception-C** 模块。
*   最后进行全局平均池化，得到 **1536** 维的特征向量。
*   应用 **Dropout**（保留率为 80%）后，通过 **Softmax** 层输出分类结果。

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_5.png)

为了理解这个结构，我们需要明确几个核心模块：**Stem**、**Inception 模块** 和 **Reduction 模块**。

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_7.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_9.png)

---

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_11.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_13.png)

## 🌱 Stem 模块详解

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_15.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_17.png)

Stem 模块是网络的起始部分，负责对输入图像进行初步的特征提取和降维。Inception-V4 和 Inception-ResNet-V2 使用了相同的 Stem 结构。

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_19.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_21.png)

以下是 Stem 模块的主要操作流程：

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_23.png)

1.  输入图像经过一个步长为 2 的 **3×3 卷积**（使用 Valid Padding），通道数变为 32。
2.  再进行一次 **3×3 卷积**，通道数变为 64。
3.  将 **最大池化** 和另一个 **3×3 卷积** 的结果在通道维度上进行拼接。
4.  使用 **1×1 卷积** 降低通道数至 64。
5.  采用类似 Inception 的结构，使用 **7×1** 和 **1×7** 的卷积组合（等效于一个 7×7 的感受野）。
6.  再进行一次 **3×3 卷积**，并与池化结果拼接。
7.  最终输出尺寸为 **35×35×384**（对于 Inception-ResNet-V1，此处为 256 通道）。

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_25.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_27.png)

Stem 模块通过一系列卷积和池化操作，高效地将高分辨率输入转换为更紧凑的特征表示。

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_29.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_31.png)

---

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_33.png)

## 🧩 Inception 模块与残差连接

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_35.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_37.png)

在 Inception-V4 中，标准的 Inception 模块（如 Inception-A）延续了之前的设计思想，使用不同尺度的卷积核并行处理特征，例如包含 **平均池化**、**1×1 卷积** 等分支。

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_39.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_41.png)

然而，关键的改进在于引入了残差网络（ResNet）的思想，形成了 **Inception-ResNet** 变体。

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_43.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_45.png)

以下是 Inception-ResNet 模块的核心特点：

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_47.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_49.png)

*   在标准的 Inception 模块计算后，将输入通过一个 **1×1 卷积**（用于调整通道数）后，与模块的输出直接相加。
*   这个相加操作发生在 **ReLU 激活函数** 之前，构成了一个残差连接。
*   公式可以简化为：`输出 = ReLU(Inception(输入) + 1x1_Conv(输入))`。

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_51.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_53.png)

对于 Inception-ResNet-V2，其架构与 V1 类似，主要区别在于部分模块的通道数更多（例如 Stem 输出为 384 而非 256）。残差连接的引入使得网络训练更稳定、收敛更快。

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_55.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_57.png)

---

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_59.png)

## 📉 Reduction 模块

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_61.png)

![](img/9b4025d3b7645dbcbf5e8c5af24c99c4_63.png)

Reduction 模块（Reduction-A, Reduction-B）负责对特征图进行下采样，即降低其空间尺寸（高和宽），同时增加通道数。这是通过使用步长大于 1 的卷积或池化操作来实现的。由于幻灯片空间有限，具体的滤波器配置和分支结构请参考原始论文。

---

## 📈 性能对比与总结

在性能上，引入残差连接的 Inception 网络（如 Inception-ResNet-V2）相比之前的版本（如 Inception-V3 和 V4）具有优势：

*   **训练速度更快**：残差连接有助于梯度流动，使网络在训练初期就能快速收敛。
*   **最终精度更高**：在 ImageNet 等数据集上，Inception-ResNet-V2 通常能达到比 Inception-V4 和 V3 更低的 Top-1 错误率。

本节课中我们一起学习了 Inception-V4 及其残差版本的网络架构。我们了解了其宏观数据流，剖析了 Stem 模块的组成，明确了标准 Inception 模块与带残差连接的 Inception-ResNet 模块的区别，并认识了 Reduction 模块的作用。这些设计使得 Inception-V4 系列在保持模型强大表征能力的同时，提升了训练效率。

---

**关于超参数优化**：有同学问到这些先进网络中如何进行超参数优化。这是一个重要的研究方向，属于 **AutoML** 的范畴。在我们的课程大纲中，在介绍完这些网络架构后，将会专门讲解自动机器学习，其中就包括自动超参数优化技术。