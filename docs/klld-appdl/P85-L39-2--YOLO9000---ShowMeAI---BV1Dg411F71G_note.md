# 📚 课程 P85：L39.2 - YOLO9000 详解 🚀

![](img/a0f07b058f18c9a979f28bfbe458d7ba_0.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_2.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_4.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_6.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_8.png)

在本节课中，我们将学习 YOLO9000 模型。YOLO9000 是 YOLO 系列的一个重要改进版本，它通过一系列小而有效的技术改进，显著提升了模型性能，并实现了对多达 9000 种物体类别的检测。我们将逐一解析这些改进点，并理解它们如何共同作用，使模型变得更强大。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_10.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_12.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_14.png)

---

![](img/a0f07b058f18c9a979f28bfbe458d7ba_16.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_18.png)

## 🎯 概述与核心亮点

![](img/a0f07b058f18c9a979f28bfbe458d7ba_20.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_22.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_24.png)

YOLO9000 包含了一系列对 YOLO 模型的改进。这些改进并非革命性的新思想，而是对已有技术的巧妙应用和优化。YOLO9000 最令人印象深刻的一点是其庞大的词汇量，能够检测超过 **9000 种物体类别**，这远超前代模型（如只能检测 20 或 80 类物体的模型）。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_26.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_28.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_30.png)

上一节我们介绍了 YOLO 的基本框架，本节中我们来看看 YOLO9000 是如何通过一系列“小改进”实现“大提升”的。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_32.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_34.png)

---

![](img/a0f07b058f18c9a979f28bfbe458d7ba_36.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_38.png)

## 🔧 主要改进点详解

![](img/a0f07b058f18c9a979f28bfbe458d7ba_40.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_42.png)

以下是 YOLO9000 引入的一系列关键技术改进。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_44.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_46.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_48.png)

### 1. 批归一化与高分辨率训练

![](img/a0f07b058f18c9a979f28bfbe458d7ba_50.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_52.png)

一个简单的改进是引入**批归一化**。这直接提升了模型的平均精度。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_54.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_56.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_58.png)

另一个观察是，分类网络通常在 `224x224` 分辨率的图像上预训练，但在测试时却应用于更高分辨率的图像。YOLO9000 的改进思想是：**直接在更高分辨率的图像上训练分类器**。这样做可以将平均精度提升至 **69.5**。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_60.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_62.png)

### 2. 引入锚框

![](img/a0f07b058f18c9a979f28bfbe458d7ba_64.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_66.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_68.png)

锚框技术曾成功帮助 Faster R-CNN 和 SSD 模型。YOLO9000 也采用了这一思想。然而，初始引入锚框时，模型的平均精度有所下降。随后，通过调整网络结构，精度恢复并提升至 **69.6**。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_70.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_72.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_74.png)

### 3. 维度先验与位置预测

![](img/a0f07b058f18c9a979f28bfbe458d7ba_76.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_78.png)

接下来，YOLO9000 提出以更智能的方式选择锚框，即使用 **K-Means 聚类** 来获得边界框的**维度先验**，并改进**位置预测**方法。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_80.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_82.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_84.png)

以下是具体步骤：
*   **维度聚类**：在训练数据的边界框坐标上进行聚类，得到的聚类中心将作为默认的边界框（即维度先验）。这比手动设置的锚框更优。
*   **距离度量**：聚类时使用的距离不是欧氏距离，而是基于**交并比** 的距离，公式为 `d(box, centroid) = 1 - IOU(box, centroid)`。因为交并比对目标检测至关重要。
*   **位置预测**：网络不再直接预测边界框中心的绝对坐标 `(b_x, b_y)`，而是预测相对于网格单元左上角 `(c_x, c_y)` 的偏移量 `(t_x, t_y)`，并通过 Sigmoid 函数约束在 0 到 1 之间。宽度和高度的预测 `(t_w, t_h)` 则相对于聚类得到的先验尺寸 `(p_w, p_h)`。置信度 `t_o` 的预测方式也类似。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_86.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_88.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_90.png)

这些“维度先验”本质上成为了更优的锚框，因此 YOLO9000 移除了传统的锚框机制。这一改进带来了巨大的性能提升。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_92.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_94.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_96.png)

### 4. 直通层

![](img/a0f07b058f18c9a979f28bfbe458d7ba_98.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_100.png)

为了更好地检测小尺度物体，YOLO9000 引入了**直通层**。其操作如下：
*   取一个来自较浅层的特征图（例如尺寸为 `26x26x512`）。
*   通过重排操作，将其转换为 `13x13x2048`（相当于将空间尺寸减半，通道数变为四倍）。
*   将此特征图与深层特征图（例如 `13x13x1024`）进行拼接，从而融合了更精细的浅层特征信息。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_102.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_104.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_106.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_108.png)

### 5. 多尺度训练

![](img/a0f07b058f18c9a979f28bfbe458d7ba_110.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_112.png)

与 SSD 类似，YOLO9000 也采用了**多尺度训练**策略，使模型能适应不同尺寸的输入图像，提升鲁棒性。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_114.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_116.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_118.png)

### 6. 高分辨率检测器

![](img/a0f07b058f18c9a979f28bfbe458d7ba_120.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_122.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_124.png)

最终，模型作为一个高分辨率检测器进行训练和测试，将平均精度推至 **78.6**。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_126.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_128.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_130.png)

这些改进表明，虽然 SSD 性能优异，但通过对网络和框架进行一系列精细调整，可以获得更好的效果。这些调整单独看都很小，但叠加起来能产生巨大的收益。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_132.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_134.png)

---

![](img/a0f07b058f18c9a979f28bfbe458d7ba_136.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_138.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_140.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_142.png)

## 🌳 层次化分类

![](img/a0f07b058f18c9a979f28bfbe458d7ba_144.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_146.png)

YOLO9000 的一个核心创新是**层次化分类**方法，这使得模型能够处理庞大的 9000 类别。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_148.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_150.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_152.png)

其思想是构建一个**视觉概念树**。例如，要预测“诺福克梗犬”的概率，可以分解为：
`P(诺福克梗犬) = P(诺福克梗犬 | 梗犬) * P(梗犬 | 犬) * P(犬 | 哺乳动物) * P(哺乳动物 | 物体)`

![](img/a0f07b058f18c9a979f28bfbe458d7ba_154.png)

![](img/a0f07b058f18c9a979f28bfbe458d7ba_156.png)

具体实现如下：
*   为树中的每个节点都设置一个 **Softmax** 分类器。
*   从“物理物体”这个根节点开始，逐层向下细分。
*   当模型对某个细分类别不确定时（例如数据不足），它至少可以预测到上一层的类别（例如“犬”）。
*   通过合并 COCO（包含“狗”、“车”等大类）和 ImageNet（包含“波斯猫”、“喷气式飞机”等细粒度类别）数据集，并进行联合分类与检测训练，最终实现了对 9000 个类别的预测。

![](img/a0f07b058f18c9a979f28bfbe458d7ba_158.png)

这使得模型不仅能检测常见物体，还能识别非常细粒度的类别，例如特定品种的狗或特定型号的飞机，这是传统检测数据集无法覆盖的。

---

## 🎓 课程总结

本节课我们一起学习了 YOLO9000 模型。我们了解到，YOLO9000 通过集成批归一化、高分辨率训练、基于 K-Means 聚类的维度先验、改进的位置预测、直通层、多尺度训练等一系列渐进式改进，显著提升了检测精度。更重要的是，其创新的层次化分类结构，通过合并数据集和构建概念树，成功地将可检测类别扩展到了惊人的 9000 种，在保持实时性的同时，大大增强了模型的实用性和泛化能力。