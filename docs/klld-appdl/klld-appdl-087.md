# 课程 P87：L40.2 - YOLOv3 详解 🎯

![](img/b4f0ba3d39440d8992c42a0e923ba579_0.png)

![](img/b4f0ba3d39440d8992c42a0e923ba579_2.png)

![](img/b4f0ba3d39440d8992c42a0e923ba579_4.png)

在本节课中，我们将学习目标检测模型 YOLOv3 的核心概念、网络架构及其性能评估方法。我们将重点理解其多尺度预测机制和损失函数的设计。

![](img/b4f0ba3d39440d8992c42a0e923ba579_6.png)

![](img/b4f0ba3d39440d8992c42a0e923ba579_8.png)

---

![](img/b4f0ba3d39440d8992c42a0e923ba579_10.png)

## 概述

![](img/b4f0ba3d39440d8992c42a0e923ba579_12.png)

![](img/b4f0ba3d39440d8992c42a0e923ba579_14.png)

YOLOv3 是一个高效的单阶段目标检测模型。它基于 Darknet-53 主干网络，能够在保持较快速度的同时，实现较高的检测精度。本节课将解析其关键设计思想。

![](img/b4f0ba3d39440d8992c42a0e923ba579_16.png)

## 网络架构：Darknet-53

![](img/b4f0ba3d39440d8992c42a0e923ba579_18.png)

上一节我们介绍了目标检测的基础，本节中我们来看看 YOLOv3 使用的特征提取网络。

![](img/b4f0ba3d39440d8992c42a0e923ba579_20.png)

YOLOv3 使用 **Darknet-53** 作为其主干特征提取网络。它是一个包含 53 个卷积层的深度网络，借鉴了 ResNet 的残差连接思想，以缓解深层网络中的梯度消失问题。

![](img/b4f0ba3d39440d8992c42a0e923ba579_22.png)

以下是其核心结构的一个简化表示：

![](img/b4f0ba3d39440d8992c42a0e923ba579_24.png)

![](img/b4f0ba3d39440d8992c42a0e923ba579_26.png)

```python
# 简化的 Darknet-53 模块结构示意
def darknet_block(x, filters):
    # 残差块结构
    shortcut = x
    x = Conv2D(filters, (1,1))(x)
    x = BatchNormalization()(x)
    x = LeakyReLU()(x)
    x = Conv2D(filters*2, (3,3), padding='same')(x)
    x = BatchNormalization()(x)
    x = LeakyReLU()(x)
    return Add()([x, shortcut]) # 残差连接
```

![](img/b4f0ba3d39440d8992c42a0e923ba579_28.png)

该网络通过多个下采样阶段，逐步提取不同尺度的特征图。

![](img/b4f0ba3d39440d8992c42a0e923ba579_30.png)

## 多尺度预测

![](img/b4f0ba3d39440d8992c42a0e923ba579_32.png)

![](img/b4f0ba3d39440d8992c42a0e923ba579_34.png)

YOLOv3 的一个关键创新是引入了多尺度预测机制，以更好地检测不同大小的物体。

![](img/b4f0ba3d39440d8992c42a0e923ba579_36.png)

网络在三个不同尺度的特征图上进行预测：
*   **深层特征图**：感受野大，用于预测大物体。
*   **中层特征图**：用于预测中等大小的物体。
*   **浅层特征图**：细节丰富，用于预测小物体。

![](img/b4f0ba3d39440d8992c42a0e923ba579_38.png)

这种设计通过特征金字塔网络（FPN）的思想实现，将深层语义信息与浅层细节信息相结合。

![](img/b4f0ba3d39440d8992c42a0e923ba579_40.png)

![](img/b4f0ba3d39440d8992c42a0e923ba579_42.png)

## 边界框预测与损失函数

![](img/b4f0ba3d39440d8992c42a0e923ba579_44.png)

YOLOv3 的每个预测单元会预测多个边界框。每个边界框的预测包含以下内容：

![](img/b4f0ba3d39440d8992c42a0e923ba579_46.png)

![](img/b4f0ba3d39440d8992c42a0e923ba579_48.png)

以下是边界框预测的核心参数：
1.  边界框中心坐标偏移量 **(tx, ty)**
2.  边界框的宽度和高度缩放 **(tw, th)**
3.  目标置信度分数 **（Objectness Score）**
4.  类别概率 **（Class Probabilities）**

![](img/b4f0ba3d39440d8992c42a0e923ba579_50.png)

其损失函数由多个部分组成，确保模型同时优化定位和分类精度。

![](img/b4f0ba3d39440d8992c42a0e923ba579_52.png)

损失函数 **L** 可以概括为以下公式的加权和：

![](img/b4f0ba3d39440d8992c42a0e923ba579_54.png)

**L = λ_coord * L_coord + L_obj + λ_noobj * L_noobj + L_class**

其中：
*   **L_coord** 是边界框坐标（中心点、宽高）的均方误差损失。
*   **L_obj** 和 **L_noobj** 是包含物体与不包含物体的置信度损失，使用二元交叉熵。
*   **L_class** 是类别预测的交叉熵损失。

## 性能评估指标

为了衡量目标检测模型的性能，我们需要使用特定的评估指标。

以下是两个最核心的评估指标：
*   **交并比（IoU）**：用于衡量预测框与真实框的重合程度。公式为：**IoU = (Area of Overlap) / (Area of Union)**。
*   **平均精度（mAP）**：在不同 IoU 阈值下，计算各类别的平均精度（AP），然后对所有类别的 AP 取平均值。这是评估检测精度的主流指标。

## 总结

本节课中我们一起学习了 YOLOv3 模型。我们了解了其主干网络 Darknet-53 的结构，分析了多尺度预测如何提升对不同大小物体的检测能力，并解析了其边界框预测机制与复合损失函数。最后，我们介绍了用于评估检测模型性能的关键指标 IoU 和 mAP。YOLOv3 在速度与精度之间取得了良好平衡，是目标检测领域的一个重要里程碑。