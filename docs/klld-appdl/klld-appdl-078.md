# 🚀 课程 P78：Faster R-CNN 详解

在本节课中，我们将学习 Faster R-CNN 这一经典目标检测算法。我们将回顾目标检测的发展历程，理解 Faster R-CNN 如何通过引入**区域提议网络**来统一和加速整个检测流程，并详细解析其核心组件、工作原理和训练步骤。

---

## 📚 内容回顾与问题引入

上一节我们介绍了 Fast R-CNN，它通过共享卷积计算和端到端的多任务损失函数，显著提升了检测速度。然而，其区域提议步骤仍然依赖于与深度学习无关的**选择性搜索**算法，这成为了计算上的瓶颈。

本节中，我们来看看 Faster R-CNN 如何解决这个问题。它的核心思想是：**用一个神经网络来生成区域提议**，从而将整个目标检测流程完全纳入深度学习框架，实现更高的速度和更好的性能。

---

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_1.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_2.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_3.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_4.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_5.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_6.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_7.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_8.png)

## 🧠 Faster R-CNN 核心思想

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_9.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_10.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_11.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_13.png)

Faster R-CNN 提出使用一个**区域提议网络**来替代选择性搜索。这个网络是一个全卷积神经网络，它能够预测边界框，并为每个框给出一个“目标性”分数，即判断框内是否存在物体。

为了实现高速推理，Faster R-CNN 的关键在于**最大化区域提议网络与 Fast R-CNN 检测网络之间的参数共享**。训练过程可能稍复杂，但一旦网络训练完成，推理速度会非常快。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_15.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_16.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_17.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_18.png)

其训练采用一种**交替优化方案**。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_19.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_20.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_21.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_22.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_23.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_24.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_25.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_26.png)

---

## 🎯 区域提议网络详解

### 网络工作流程

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_28.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_29.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_30.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_31.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_32.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_33.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_34.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_35.png)

1.  **输入与特征提取**：将图像输入共享的卷积网络，得到一个卷积特征图。这个特征图是一个三维张量，具有高度 `H`、宽度 `W` 和通道数 `C`。
2.  **滑动窗口与锚点框**：在特征图上使用一个滑动窗口。特征图上的每个空间位置（每个像素点）会对应原始图像上的多个预定义框，这些框称为**锚点框**。
3.  **锚点框的生成**：每个位置会生成 `k` 个锚点框，它们具有不同的尺度和长宽比。例如，常见的设置是3种尺度（如128x128, 256x256, 512x512）和3种长宽比（1:1, 1:2, 2:1），总共 `k=9` 个锚点框。
4.  **预测与调整**：对于每个锚点框，RPN 会进行两项预测：
    *   **分类**：预测该框是“前景”（包含物体）还是“背景”。
    *   **回归**：预测4个坐标偏移量，用于微调锚点框的位置和大小，使其更贴合真实物体。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_36.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_37.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_38.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_39.png)

以下是锚点框数量的计算公式：
```
总锚点框数量 = W * H * k
```

### 网络实现

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_41.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_42.png)

这些预测操作可以通过卷积层高效实现：
*   滑动窗口本身可以通过一个 **3x3 卷积层** 来模拟。
*   随后的分类和回归分支可以分别用 **1x1 卷积层** 实现。
*   这种全卷积结构使得计算可以高度共享和并行。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_43.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_44.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_45.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_46.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_47.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_48.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_49.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_50.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_51.png)

---

## ⚖️ RPN 的损失函数

RPN 的损失函数由两部分组成：分类损失和回归损失。它定义在一个小批量的锚点框上。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_53.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_54.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_55.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_56.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_57.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_58.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_59.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_60.png)

以下是损失函数的公式：
```
L({p_i}, {t_i}) = (1/N_cls) * Σ_i L_cls(p_i, p_i*) + λ * (1/N_reg) * Σ_i p_i* * L_reg(t_i, t_i*)
```

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_61.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_62.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_63.png)

公式中各部分的含义如下：

*   `i`：一个小批量数据中锚点框的索引。
*   `p_i`：神经网络预测的锚点框 `i` 包含物体的概率。
*   `p_i*`：锚点框 `i` 的真实标签。`p_i* = 1` 表示正样本（包含物体），`p_i* = 0` 表示负样本（不包含物体）。
*   `t_i`：预测的边界框坐标偏移量。
*   `t_i*`：与真实边界框对应的坐标偏移量。
*   `L_cls`：分类损失（如二分类交叉熵损失）。
*   `L_reg`：回归损失（如 Smooth L1 损失）。
*   `N_cls`：归一化参数，通常是分类任务的小批量大小。
*   `N_reg`：归一化参数，通常是锚点位置的数量（约等于 `H*W`）。
*   `λ`：平衡分类和回归损失权重的参数。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_65.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_66.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_67.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_68.png)

**关键点**：回归损失 `L_reg` 只对正样本锚点框（`p_i* = 1`）进行计算，因为背景框没有对应的边界框需要回归。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_69.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_70.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_71.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_72.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_73.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_74.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_75.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_76.png)

---

## 🏷️ 如何为锚点框分配标签？

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_78.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_79.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_80.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_81.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_82.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_83.png)

我们需要定义哪些锚点框是正样本，哪些是负样本，以用于训练。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_84.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_85.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_86.png)

以下是分配规则：

1.  **正样本**：
    *   与任何真实边界框的**交并比**最高的锚点框。
    *   与某个真实边界框的 IoU 大于 **0.7** 的锚点框。
2.  **负样本**：
    *   与所有真实边界框的 IoU 都小于 **0.3** 的锚点框。
3.  **忽略样本**：
    *   IoU 在 0.3 到 0.7 之间的锚点框不参与训练，既不用来计算损失，也不用于更新梯度。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_88.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_89.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_90.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_91.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_92.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_93.png)

**关于边界锚点框的处理**：当锚点框的中心位于特征图边缘时，其部分区域可能超出图像范围。对于超出的部分，通常用零填充处理。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_94.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_95.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_96.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_97.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_98.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_99.png)

**关于锚点框数量 `k`**：`k` 是一个可以调整的超参数。增加尺度或长宽比的数量（即增大 `k`）可能会提高检测精度，但也会增加计算成本，需要在精度和速度之间进行权衡。

---

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_101.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_102.png)

## 🔄 训练步骤：交替优化

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_103.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_104.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_105.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_106.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_107.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_108.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_109.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_110.png)

Faster R-CNN 的训练是一个多步骤的过程，旨在让 RPN 和 Fast R-CNN 共享卷积层参数。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_111.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_112.png)

以下是四步训练法的具体步骤：

1.  **训练 RPN**：使用 ImageNet 预训练模型初始化 RPN，并针对区域提议任务进行端到端的微调。此时使用上文所述的 RPN 损失函数。
2.  **训练 Fast R-CNN**：使用第一步训练好的 RPN 生成区域提议，并用这些提议来训练一个独立的 Fast R-CNN 检测网络。该网络也用 ImageNet 预训练模型初始化。
3.  **再次训练 RPN**：用第二步训练好的 Fast R-CNN 的权重来初始化 RPN。**固定共享的卷积层**，只对 RPN 独有的层（即“头部”）进行微调。此时，两个网络开始共享卷积特征。
4.  **再次训练 Fast R-CNN**：保持共享卷积层的权重不变，使用第三步的 RPN 生成区域提议，并仅对 Fast R-CNN 独有的“头部”进行微调。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_114.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_115.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_116.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_117.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_118.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_119.png)

经过这四个步骤，我们得到了两个网络：一个负责提议区域，一个负责检测物体。它们共享绝大部分的卷积计算，只有各自任务特定的“头部”是独立的。这正是推理时的结构，因此效率极高。

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_120.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_121.png)

![](img/6eb9ca9f7eb91923b0e6550d163fd20a_122.png)

---

## 💡 总结与问答

本节课中，我们一起学习了 Faster R-CNN。它通过引入**区域提议网络**，将区域提议这一步骤也纳入了深度学习框架，实现了真正意义上的端到端目标检测，并大幅提升了速度。

**核心要点总结**：
*   **动机**：解决 Fast R-CNN 中选择性搜索的计算瓶颈。
*   **核心**：**区域提议网络**，一个全卷积网络，用于生成高质量的候选区域。
*   **关键**：**锚点框机制** 和 **参数共享**，通过交替优化训练实现 RPN 与 Fast R-CNN 的特征共享。
*   **结果**：整个检测流程完全由神经网络构成，速度更快，为实时视频检测奠定了基础。

**关于网络架构**：RPN 的具体架构（例如使用 ResNet 还是 VGG）并不是关键，重要的是在获得共享的卷积特征图之后添加的预测层。任何在 ImageNet 上预训练好的特征提取网络都可以作为共享的主干网络。

Faster R-CNN 是一个集大成的复杂系统，它融合了此前多项工作的精华，是目标检测发展史上的一个里程碑。