# 机器学习导论：1：卷积神经网络（CNN）基础 🧠

![](img/74f78ddb043deb17b7f3fc9a435697a6_1.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_2.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_4.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_5.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_6.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_7.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_9.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_11.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_12.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_13.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_15.png)

在本节课中，我们将要学习卷积神经网络（CNN）的基础知识。CNN是处理图像、语音等网格状数据的强大工具，其核心思想是通过卷积操作自动提取数据的特征。我们将从最基础的概念开始，逐步理解CNN的工作原理。

![](img/74f78ddb043deb17b7f3fc9a435697a6_17.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_19.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_21.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_23.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_25.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_27.png)

## 什么是卷积？🔍

![](img/74f78ddb043deb17b7f3fc9a435697a6_29.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_31.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_32.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_33.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_35.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_36.png)

上一节我们介绍了CNN的整体概念，本节中我们来看看其最核心的操作——卷积。

![](img/74f78ddb043deb17b7f3fc9a435697a6_38.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_40.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_42.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_44.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_46.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_48.png)

卷积是一种数学运算，它通过一个称为“滤波器”或“内核”的小矩阵，在输入数据（如图像）上滑动，计算局部区域的加权和。这个过程可以理解为让滤波器“扫描”整个图像，每次关注一个小区域，并输出一个代表该区域特征的数值。

![](img/74f78ddb043deb17b7f3fc9a435697a6_50.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_52.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_54.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_56.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_57.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_59.png)

**公式**：
对于一个二维输入图像 **I** 和一个滤波器 **K**，在位置 **(i, j)** 的卷积输出 **S(i, j)** 计算如下：
$$
S(i, j) = (I * K)(i, j) = \sum_{m} \sum_{n} I(i+m, j+n) K(m, n)
$$
其中，`*` 表示卷积操作，`m` 和 `n` 是滤波器内部的索引。

![](img/74f78ddb043deb17b7f3fc9a435697a6_61.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_62.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_64.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_66.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_68.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_70.png)

这个操作的目的在于检测输入中的特定模式，例如边缘、纹理或更复杂的形状。

![](img/74f78ddb043deb17b7f3fc9a435697a6_72.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_74.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_76.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_78.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_80.png)

## 卷积的关键参数 ⚙️

![](img/74f78ddb043deb17b7f3fc9a435697a6_82.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_84.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_86.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_88.png)

理解了卷积的基本运算后，我们需要掌握控制卷积行为的三个关键参数：步长、填充和滤波器尺寸。

![](img/74f78ddb043deb17b7f3fc9a435697a6_90.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_92.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_94.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_96.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_98.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_100.png)

以下是卷积操作中需要定义的三个主要参数：

![](img/74f78ddb043deb17b7f3fc9a435697a6_102.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_104.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_106.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_107.png)

*   **步长**：滤波器在输入上每次移动的像素数。步长为1意味着滤波器每次移动一个像素；步长为2则每次移动两个像素。步长越大，输出特征图的尺寸越小。
*   **填充**：在输入数据的边界周围添加额外的像素（通常是0）。这有助于控制输出特征图的大小，并防止边界信息过快丢失。
*   **滤波器尺寸**：滤波器的高度和宽度，常见的有3x3、5x5等。它决定了每次观察输入区域的感受野大小。

![](img/74f78ddb043deb17b7f3fc9a435697a6_109.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_110.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_112.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_114.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_116.png)

这些参数共同决定了卷积层输出特征图的大小。

![](img/74f78ddb043deb17b7f3fc9a435697a6_118.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_120.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_122.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_124.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_126.png)

## 计算输出尺寸 📏

![](img/74f78ddb043deb17b7f3fc9a435697a6_128.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_130.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_131.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_133.png)

知道了卷积参数，我们就可以精确计算出经过卷积层后，输出特征图的尺寸。

![](img/74f78ddb043deb17b7f3fc9a435697a6_134.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_136.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_138.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_140.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_142.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_144.png)

输出特征图尺寸的计算公式是理解CNN结构设计的基础。

![](img/74f78ddb043deb17b7f3fc9a435697a6_146.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_147.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_148.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_150.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_152.png)

**公式**：
对于输入尺寸 `input_size`、滤波器尺寸 `filter_size`、步长 `stride` 和填充 `padding`，输出尺寸 `output_size` 的计算公式为：
$$
\text{output\_size} = \frac{\text{input\_size} + 2 \times \text{padding} - \text{filter\_size}}{\text{stride}} + 1
$$

![](img/74f78ddb043deb17b7f3fc9a435697a6_153.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_154.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_156.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_158.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_160.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_162.png)

这个公式适用于高度和宽度方向上的独立计算。如果结果不是整数，通常意味着参数设置不合理，需要进行调整。

![](img/74f78ddb043deb17b7f3fc9a435697a6_163.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_164.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_165.png)

**代码**：
你也可以通过以下Python函数来计算：
```python
def calculate_output_size(input_size, filter_size, stride, padding):
    return (input_size + 2 * padding - filter_size) // stride + 1
```

![](img/74f78ddb043deb17b7f3fc9a435697a6_167.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_168.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_169.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_171.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_173.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_175.png)

## 特征图与通道 🎨

![](img/74f78ddb043deb17b7f3fc9a435697a6_177.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_178.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_180.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_182.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_183.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_184.png)

卷积操作不仅处理空间维度，还处理深度维度，即通道。

![](img/74f78ddb043deb17b7f3fc9a435697a6_186.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_187.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_189.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_191.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_193.png)

上一节我们学习了如何计算单通道输出的尺寸，本节中我们来看看多通道输入和输出的情况。

![](img/74f78ddb043deb17b7f3fc9a435697a6_195.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_197.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_198.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_200.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_202.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_203.png)

一张彩色图像通常有红、绿、蓝三个颜色通道。卷积层可以同时处理所有这些通道的信息。每个滤波器实际上是一个三维张量，其深度与输入数据的通道数相同。滤波器在每个通道上进行卷积，然后将所有通道的结果相加，再加上一个偏置项，最终生成输出特征图的一个通道。

![](img/74f78ddb043deb17b7f3fc9a435697a6_205.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_207.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_209.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_210.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_212.png)

*   **输入通道**：输入数据的深度，如图像的RGB三通道。
*   **输出通道**：卷积层中滤波器的数量。每个滤波器会生成一个独立的二维特征图，所有滤波器的输出堆叠起来就构成了具有多个通道的输出特征图。

![](img/74f78ddb043deb17b7f3fc9a435697a6_214.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_216.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_218.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_220.png)

因此，一个卷积层可以将 `C_in` 通道的输入，转换为 `C_out` 通道的输出，每个输出通道都代表了由特定滤波器检测到的一种特征。

![](img/74f78ddb043deb17b7f3fc9a435697a6_222.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_223.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_225.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_227.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_228.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_230.png)

## 池化层：下采样 📉

![](img/74f78ddb043deb17b7f3fc9a435697a6_232.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_233.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_235.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_237.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_238.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_239.png)

卷积层之后，CNN通常会使用池化层来降低特征图的空间尺寸。

![](img/74f78ddb043deb17b7f3fc9a435697a6_240.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_242.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_244.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_245.png)

池化是一种下采样操作，它能够减少参数数量、计算量，并赋予模型一定的平移不变性。最常见的池化方式是最大池化。

![](img/74f78ddb043deb17b7f3fc9a435697a6_247.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_248.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_250.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_252.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_253.png)

以下是池化操作的两种主要类型：

![](img/74f78ddb043deb17b7f3fc9a435697a6_254.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_256.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_257.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_259.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_261.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_262.png)

*   **最大池化**：在滤波器覆盖的区域内取最大值。它能保留最显著的特征。
*   **平均池化**：在滤波器覆盖的区域内取平均值。它更平滑，但可能弱化强特征。

![](img/74f78ddb043deb17b7f3fc9a435697a6_264.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_266.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_268.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_270.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_272.png)

池化操作也有自己的滤波器尺寸和步长，但没有需要学习的参数（权重）。它独立地在每个输入通道上进行操作，因此不会改变通道数。

![](img/74f78ddb043deb17b7f3fc9a435697a6_274.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_275.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_277.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_278.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_279.png)

## 从全连接到卷积 🧩

![](img/74f78ddb043deb17b7f3fc9a435697a6_281.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_282.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_284.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_286.png)

为了更好地理解CNN的优越性，我们可以将其与传统的全连接神经网络进行对比。

![](img/74f78ddb043deb17b7f3fc9a435697a6_288.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_290.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_291.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_293.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_295.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_296.png)

对于图像数据，如果使用全连接层，需要将图像展平成一个很长的向量。这会导致两个主要问题：参数数量巨大，以及忽略了像素间的空间结构关系。卷积层通过两个关键思想解决了这些问题：局部连接和参数共享。

![](img/74f78ddb043deb17b7f3fc9a435697a6_298.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_299.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_301.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_303.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_305.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_307.png)

*   **局部连接**：每个神经元只与输入数据的一个局部区域（感受野）连接，而不是全部输入。这大幅减少了连接数。
*   **参数共享**：同一个滤波器在整个输入上滑动使用，即在不同位置检测相同的特征。这极大地减少了需要学习的参数数量。

![](img/74f78ddb043deb17b7f3fc9a435697a6_309.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_311.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_313.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_315.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_316.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_318.png)

正是这些特性，使得CNN能够高效地处理图像等高维数据。

![](img/74f78ddb043deb17b7f3fc9a435697a6_320.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_322.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_323.png)

## 构建一个简单的CNN 🏗️

![](img/74f78ddb043deb17b7f3fc9a435697a6_325.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_327.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_328.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_330.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_332.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_334.png)

现在，让我们把前面学到的所有组件组合起来，构建一个简单的卷积神经网络模型。

![](img/74f78ddb043deb17b7f3fc9a435697a6_336.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_338.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_340.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_341.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_342.png)

一个典型的用于图像分类的CNN结构遵循“卷积-激活-池化”的模块化堆叠模式，最后连接全连接层进行分类。

![](img/74f78ddb043deb17b7f3fc9a435697a6_344.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_345.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_346.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_348.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_350.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_352.png)

以下是构建一个简单CNN的典型步骤序列：

![](img/74f78ddb043deb17b7f3fc9a435697a6_354.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_355.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_356.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_358.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_360.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_362.png)

1.  **输入层**：接收原始图像数据（例如，32x32像素的RGB图像）。
2.  **卷积层1**：使用多个滤波器（如32个3x3滤波器）提取初级特征（如边缘、角点）。后接ReLU激活函数引入非线性。
3.  **池化层1**：进行下采样（如2x2最大池化），缩小特征图尺寸。
4.  **卷积层2**：使用更多滤波器（如64个3x3滤波器）提取更高级、更复杂的特征。
5.  **池化层2**：再次下采样。
6.  **展平层**：将最后的二维特征图展平成一维向量。
7.  **全连接层**：一个或多个全连接层，用于整合特征。
8.  **输出层**：通常是一个Softmax层，输出每个类别的概率。

![](img/74f78ddb043deb17b7f3fc9a435697a6_364.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_366.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_368.png)

通过堆叠这样的层，网络能够从低级特征逐步构建出高级的、具有判别性的特征表示。

![](img/74f78ddb043deb17b7f3fc9a435697a6_370.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_372.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_374.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_375.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_376.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_378.png)

## 总结 📚

![](img/74f78ddb043deb17b7f3fc9a435697a6_380.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_382.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_384.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_385.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_387.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_389.png)

本节课中我们一起学习了卷积神经网络的基础知识。

![](img/74f78ddb043deb17b7f3fc9a435697a6_390.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_392.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_394.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_396.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_398.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_400.png)

我们首先了解了**卷积**这一核心数学操作及其在特征提取中的作用。接着，我们掌握了控制卷积行为的三个关键**参数**：步长、填充和滤波器尺寸，并学会了使用**公式**计算输出特征图的尺寸。我们探讨了多**通道**输入输出的处理方式，认识了用于下采样的**池化层**。通过对比**全连接网络**，我们深刻理解了CNN**局部连接**和**参数共享**的优势。最后，我们将这些组件组合起来，概述了如何**构建**一个完整的简单CNN模型。

![](img/74f78ddb043deb17b7f3fc9a435697a6_402.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_404.png)

掌握这些基础概念是理解更复杂现代CNN架构（如ResNet, Transformer）的基石。