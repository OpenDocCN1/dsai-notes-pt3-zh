# 🧠 课程 P6：L3.2 - Network in Network 详解

![](img/bfecd65cbcef25806c305b49184bf6df_1.png)

在本节课中，我们将学习一篇名为 **Network in Network** 的经典论文。这篇论文虽然不像其他一些网络那样广为人知，但它提出了许多现代神经网络仍在使用的核心思想。我们将重点探讨其核心概念：**1x1 卷积** 和 **全局平均池化**，并理解它们如何简化网络结构并提升性能。

![](img/bfecd65cbcef25806c305b49184bf6df_3.png)

![](img/bfecd65cbcef25806c305b49184bf6df_5.png)

![](img/bfecd65cbcef25806c305b49184bf6df_7.png)

---

![](img/bfecd65cbcef25806c305b49184bf6df_9.png)

## 📄 论文背景与核心思想

![](img/bfecd65cbcef25806c305b49184bf6df_11.png)

有一篇名为 **Network in Network** 的论文，我非常喜欢。它启发了现代神经网络的许多想法，但并未获得与其他网络同等的关注。这是因为当时计算机视觉领域存在一个基于 ImageNet 数据集的挑战赛，那些在该挑战赛中表现出色、击败其他神经网络的论文会获得大量引用，即使人们可能并未仔细阅读它们。

![](img/bfecd65cbcef25806c305b49184bf6df_13.png)

![](img/bfecd65cbcef25806c305b49184bf6df_15.png)

然而，这篇论文包含了许多非常出色的想法，后来被其他论文所采用。

![](img/bfecd65cbcef25806c305b49184bf6df_17.png)

![](img/bfecd65cbcef25806c305b49184bf6df_19.png)

## 🧩 核心概念：网络中的网络

![](img/bfecd65cbcef25806c305b49184bf6df_21.png)

![](img/bfecd65cbcef25806c305b49184bf6df_23.png)

![](img/bfecd65cbcef25806c305b49184bf6df_25.png)

他们的核心想法是，希望在另一个神经网络内部嵌入一个网络。他们从一个**线性卷积层**开始。线性卷积层的基本操作是：你有一个滤波器，将其与输入图像（或输入）的对应部分进行点积运算，最终会得到一个位于此处的神经元。

![](img/bfecd65cbcef25806c305b49184bf6df_27.png)

![](img/bfecd65cbcef25806c305b49184bf6df_29.png)

![](img/bfecd65cbcef25806c305b49184bf6df_31.png)

他们提出，在这一层和下一层之间，希望嵌入一个神经网络，具体来说是一个**多层感知机**，即一个全连接神经网络。这本身并没有什么特别之处，这是他们能找到的最基础的神经网络类型。

![](img/bfecd65cbcef25806c305b49184bf6df_33.png)

![](img/bfecd65cbcef25806c305b49184bf6df_35.png)

![](img/bfecd65cbcef25806c305b49184bf6df_37.png)

他们希望将其放在这里。后来他们意识到，他们所做的事情，正是许多现代网络出于各种原因所使用的 **1x1 卷积**。

![](img/bfecd65cbcef25806c305b49184bf6df_39.png)

![](img/bfecd65cbcef25806c305b49184bf6df_41.png)

## 🔍 1x1 卷积的工作原理

![](img/bfecd65cbcef25806c305b49184bf6df_43.png)

![](img/bfecd65cbcef25806c305b49184bf6df_45.png)

那么它是如何工作的呢？你有一个输入块，其中心位于位置 `(i, j)`。这就是你的输入块。然后，你将这个块中的所有元素放入一个向量中。这就是你的输入块向量。

![](img/bfecd65cbcef25806c305b49184bf6df_47.png)

![](img/bfecd65cbcef25806c305b49184bf6df_49.png)

相应地，你会有一组权重，这就是你的滤波器。然后你将这两者相乘并求和，加上偏置，进行激活函数计算（例如 **ReLU**，即修正线性单元）。ReLU 的操作很简单：取该值与零的最大值。如果该值为正，则保留；如果为负，则忽略。这将得到你的第一个层的输出值。

![](img/bfecd65cbcef25806c305b49184bf6df_51.png)

![](img/bfecd65cbcef25806c305b49184bf6df_53.png)

这里的 `k` 是什么？`k` 是索引**通道**的。这是你的一个滤波器，你可以有多个滤波器。所以这是一个滤波器。如果你添加另一个滤波器，它将在通道维度上给你另一个维度，从而增加通道维度。`k` 就是用来计数通道的。

![](img/bfecd65cbcef25806c305b49184bf6df_55.png)

![](img/bfecd65cbcef25806c305b49184bf6df_57.png)

现在，你可以将所有通道方向的值放入一个向量中，这将得到例如 `f1` 向量。然后你将其乘以一组权重，加上偏置，进行激活，得到下一层，依此类推。这就是他们想要做的。

![](img/bfecd65cbcef25806c305b49184bf6df_59.png)

![](img/bfecd65cbcef25806c305b49184bf6df_61.png)

![](img/bfecd65cbcef25806c305b49184bf6df_63.png)

但最终，这实际上就变成了一个 **1x1 卷积**。因此，**1x1 卷积** 的概念最早是在 **Network in Network** 这篇论文中提出的。

![](img/bfecd65cbcef25806c305b49184bf6df_65.png)

![](img/bfecd65cbcef25806c305b49184bf6df_67.png)

## 🎯 另一个核心思想：全局平均池化

![](img/bfecd65cbcef25806c305b49184bf6df_69.png)

![](img/bfecd65cbcef25806c305b49184bf6df_70.png)

![](img/bfecd65cbcef25806c305b49184bf6df_72.png)

那么另一个重要思想是什么呢？这就是他们的网络：一系列“网络中的网络”。在网络的末端，我们通常会有全连接层。他们提出，这些全连接层并非必需。

![](img/bfecd65cbcef25806c305b49184bf6df_74.png)

![](img/bfecd65cbcef25806c305b49184bf6df_76.png)

![](img/bfecd65cbcef25806c305b49184bf6df_78.png)

你可以直接对特征图进行**平均池化**。假设这些是你的滤波器输出（特征图）。你对第一个通道的所有值进行平均，得到一个数字，放在这里；对第二个通道进行平均，得到另一个数字，放在这里；第三个通道放在这里，最后一个通道放在这里。

![](img/bfecd65cbcef25806c305b49184bf6df_80.png)

![](img/bfecd65cbcef25806c305b49184bf6df_82.png)

![](img/bfecd65cbcef25806c305b49184bf6df_84.png)

这样，你就不再需要将卷积层的输出展平，而是直接进行平均池化，然后将结果放入不同的维度中。之后，只需要一个 **Softmax** 层来输出各类别的概率，即可完成分类任务。

![](img/bfecd65cbcef25806c305b49184bf6df_85.png)

![](img/bfecd65cbcef25806c305b49184bf6df_87.png)

![](img/bfecd65cbcef25806c305b49184bf6df_89.png)

因此，**全局平均池化** 和 **1x1 卷积** 的概念都是由这篇论文引入的。

![](img/bfecd65cbcef25806c305b49184bf6df_91.png)

![](img/bfecd65cbcef25806c305b49184bf6df_93.png)

## 💡 全局平均池化的优势

![](img/bfecd65cbcef25806c305b49184bf6df_95.png)

![](img/bfecd65cbcef25806c305b49184bf6df_97.png)

![](img/bfecd65cbcef25806c305b49184bf6df_99.png)

关于全局平均池化，一个很酷的地方在于，它去掉了网络末端的那些全连接层。这带来了另一个好处：它有助于**正则化**，可以为我们起到正则化的作用。

![](img/bfecd65cbcef25806c305b49184bf6df_101.png)

![](img/bfecd65cbcef25806c305b49184bf6df_103.png)

![](img/bfecd65cbcef25806c305b49184bf6df_105.png)

另一个应用是，这种平均操作消除了图像尺寸的影响。因此，图像的尺寸不再那么重要了。

![](img/bfecd65cbcef25806c305b49184bf6df_107.png)

![](img/bfecd65cbcef25806c305b49184bf6df_109.png)

![](img/bfecd65cbcef25806c305b49184bf6df_111.png)

## ❓ 常见问题解答

![](img/bfecd65cbcef25806c305b49184bf6df_113.png)

![](img/bfecd65cbcef25806c305b49184bf6df_115.png)

如果大家对 **Dropout**、**1x1 卷积** 或 **全局平均池化** 有任何问题，我很乐意回答。

![](img/bfecd65cbcef25806c305b49184bf6df_117.png)

![](img/bfecd65cbcef25806c305b49184bf6df_119.png)

![](img/bfecd65cbcef25806c305b49184bf6df_121.png)

**学生提问**：您能再解释一下全局平均池化吗？
**教授回答**：当然可以。在完成所有操作后，你最终会得到一个张量。这个张量会有高度、宽度和通道数。全局平均池化的做法是：你取出其中一个通道，然后平均该通道内所有的数值，并将这个平均值放在这里。平均操作就是 `1/(H*W) * 求和(所有像素值)`。明白了吗？

![](img/bfecd65cbcef25806c305b49184bf6df_123.png)

![](img/bfecd65cbcef25806c305b49184bf6df_125.png)

![](img/bfecd65cbcef25806c305b49184bf6df_127.png)

**学生提问**：所以，在整个网络中您都使用这些 1x1 卷积，而全局平均池化只是最后的一个步骤？
**教授回答**：完全正确。你的网络结构可能是：常规卷积层，然后是 1x1 卷积层，接着又是常规卷积层，再是 1x1 卷积层，最后进行平均池化。

![](img/bfecd65cbcef25806c305b49184bf6df_129.png)

![](img/bfecd65cbcef25806c305b49184bf6df_131.png)

![](img/bfecd65cbcef25806c305b49184bf6df_132.png)

---

![](img/bfecd65cbcef25806c305b49184bf6df_134.png)

![](img/bfecd65cbcef25806c305b49184bf6df_136.png)

![](img/bfecd65cbcef25806c305b49184bf6df_138.png)

![](img/bfecd65cbcef25806c305b49184bf6df_139.png)

## 📝 课程总结

![](img/bfecd65cbcef25806c305b49184bf6df_141.png)

![](img/bfecd65cbcef25806c305b49184bf6df_143.png)

在本节课中，我们一起深入学习了 **Network in Network** 这篇论文。我们重点探讨了它的两个核心贡献：

![](img/bfecd65cbcef25806c305b49184bf6df_145.png)

![](img/bfecd65cbcef25806c305b49184bf6df_147.png)

1.  **1x1 卷积**：它本质上是跨通道的线性组合，能够灵活地增加或减少特征图的通道数，并引入非线性。其操作可以视为对输入向量 `x` 进行线性变换并激活：`output = ReLU(W * x + b)`。
2.  **全局平均池化**：它用对每个特征图求平均并直接送入分类器的操作，替代了传统网络中末端的全连接层。这不仅减少了大量参数，防止过拟合（起到正则化作用），还使网络对输入图像尺寸的变化更加鲁棒。

![](img/bfecd65cbcef25806c305b49184bf6df_149.png)

![](img/bfecd65cbcef25806c305b49184bf6df_151.png)

![](img/bfecd65cbcef25806c305b49184bf6df_153.png)

这两个简洁而强大的思想，对后续的神经网络架构（如 GoogLeNet 的 Inception 模块、ResNet 等）产生了深远的影响。