# 38：L19.4 - ShuffleNet 详解 🃏

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_1.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_3.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_5.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_7.png)

在本节课中，我们将要学习 ShuffleNet 的核心思想与实现。这是一种专为计算资源受限环境（如移动设备、机器人）设计的高效网络结构，其核心在于通过**通道混洗**操作，在保持分组卷积计算效率的同时，促进不同通道组间的信息交流。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_9.png)

---

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_11.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_13.png)

## 分组卷积的信息隔离问题

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_15.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_17.png)

上一节我们介绍了分组卷积，本节中我们来看看其潜在问题。分组卷积将输入通道分成独立的组进行处理。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_19.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_21.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_23.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_1.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_25.png)

假设输入有若干通道。如果进行分组卷积，卷积操作将在不同的通道组上独立进行。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_27.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_29.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_3.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_31.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_33.png)

这样得到的特征图与输入是独立的。如果再进行一次分组卷积，特征图之间依然没有信息交流。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_35.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_37.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_5.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_39.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_41.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_43.png)

这会导致不同组的通道之间完全不“沟通”。虽然这在多GPU并行计算时有益，但从数学角度看，这会丢失信息。因为某一组输入中的重要信息，可能对另一组输出的特征至关重要。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_45.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_47.png)

---

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_49.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_51.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_53.png)

## 通道混洗的解决方案

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_55.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_57.png)

为了解决信息隔离问题，需要在分组卷积后混合通道信息。一种直观的方法是在第一次分组卷积后，手动将不同组的通道重新排列组合，再进行下一次分组卷积。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_59.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_61.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_7.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_63.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_65.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_67.png)

例如，将第一组的部分通道分配到第二组，第二组的分配到第三组，以此类推。这样，第二次分组卷积的输入就包含了来自之前不同组的混合信息。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_69.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_71.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_9.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_73.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_75.png)

然而，这种手动分配在实现上并不高效。更高效的做法是引入一个固定的**通道混洗**操作。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_77.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_79.png)

---

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_81.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_83.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_85.png)

## 通道混洗的高效实现

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_87.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_89.png)

高效的实现方式是：先进行一次常规的分组卷积，然后对输出的通道进行“混洗”，再进行下一次分组卷积。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_91.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_93.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_11.png)

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_95.png)

混洗操作在数学上等价于之前描述的复杂手动分配，但实现起来非常简单且计算代价极低。

以下是通道混洗操作的具体代码实现步骤：

1.  假设分组数为 `g`，每组通道数为 `n`，总通道数为 `g * n`。
2.  将形状为 `(g * n, ...)` 的张量**重塑**为 `(g, n, ...)`。
3.  对重塑后的张量进行**转置**，维度变为 `(n, g, ...)`。
4.  最后，将转置后的张量**展平**回 `(g * n, ...)` 的形状。

用伪代码表示如下：
```python
# 假设输入张量 x 的形状为 (batch_size, g*n, height, width)
batch_size, C, h, w = x.shape
# 1. 重塑
x = x.view(batch_size, g, n, h, w)
# 2. 转置
x = x.permute(0, 2, 1, 3, 4)  # 维度变为 (batch_size, n, g, h, w)
# 3. 展平
x = x.reshape(batch_size, g*n, h, w)
```
这个操作只是数据的重新排列，不涉及任何可学习参数，计算开销非常小。

---

## ShuffleNet 的单元结构

了解了核心的混洗操作后，我们来看 ShuffleNet 的具体构建块。其基本单元借鉴了残差连接的思想。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_13.png)

以下是 ShuffleNet 单元的结构步骤：

1.  首先进行一个 **1x1 分组卷积**，用于降维或升维。
2.  接着执行**通道混洗**操作。
3.  然后进行一个 **3x3 深度可分离卷积**（Depthwise Separable Convolution）。
4.  最后再使用一个 **1x1 分组卷积**恢复通道数。
5.  将输出与捷径分支相加。

当需要降低特征图分辨率时（如下采样），单元结构会略有调整：

1.  在主干路径上，对 **3x3 深度卷积**使用步长为2。
2.  在捷径分支上，使用一个步长为2的 **3x3 平均池化**层。
3.  不再使用相加，而是将两个分支的结果在通道维度上进行**拼接**。

---

## 性能比较与应用

ShuffleNet 的设计目标是在保持精度的同时大幅降低计算复杂度。通过调整分组数 `g`，可以在精度和效率之间进行权衡。

![](img/c7cbc2eaf9a47d6f2348cc75e773b4a5_15.png)

与 AlexNet、VGG、GoogleNet 等经典网络相比，在达到相近分类错误率的情况下，ShuffleNet 的计算复杂度和参数量要低得多。例如，ShuffleNet 的复杂度可能仅为 AlexNet 的 1/38，但性能却相当。

ShuffleNet 主要应用于对计算效率和功耗敏感的场景，例如：
*   智能手机上的实时视觉应用
*   嵌入式设备和机器人
*   无人机

---

## 总结与问答要点

本节课中我们一起学习了 ShuffleNet。其核心创新在于**通道混洗**操作，它巧妙地解决了分组卷积造成的信息隔离问题，使得网络在保持高计算效率的同时，也能实现跨通道的信息融合。

回顾一下关键点：
*   **核心思想**：通过固定的、无参数的通道重排，促进分组卷积间的信息交换。
*   **高效实现**：通过 `重塑 -> 转置 -> 展平` 三步操作即可完成。
*   **结构单元**：结合了 **1x1分组卷积**、**通道混洗** 和 **深度可分离卷积**。
*   **主要优势**：在精度损失很小的情况下，显著降低了模型的**计算复杂度**和**参数量**。

关于 ShuffleNet 的常见问题：
*   **混洗是随机的吗？** 不是，它是确定性的、固定的操作。
*   **为什么不用普通卷积？** 普通卷积虽然能混合信息，但计算量和参数量更大。ShuffleNet 的目标是极致的高效。
*   **能用于迁移学习吗？** 可以。但在研究领域，为了与现有大量基于 VGG 等网络的文献进行公平比较，人们可能仍倾向于使用更经典的骨干网络。
*   **与 MobileNet 的区别？** 两者都是高效网络，但 ShuffleNet 的核心机制是通道混洗，而 MobileNet 的核心是深度可分离卷积。它们可以结合使用。