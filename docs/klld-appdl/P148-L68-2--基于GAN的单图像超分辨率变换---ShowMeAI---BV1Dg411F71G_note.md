# 🖼️ 课程 P148：L68.2 - 基于GAN的单图像超分辨率变换

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_1.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_2.png)

在本节课中，我们将学习如何利用生成对抗网络（GAN）来实现单图像超分辨率（Super-Resolution， SR）变换。我们将探讨该任务的问题设定、数据准备、网络架构设计以及核心的损失函数构成。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_3.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_4.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_5.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_6.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_7.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_8.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_9.png)

## 问题设定与应用背景

上一节我们介绍了GAN的基本原理，本节中我们来看看GAN的一个具体应用：单图像超分辨率。

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_11.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_12.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_13.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_14.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_15.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_16.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_17.png)

假设你有一张低分辨率图像，目标是将其转换为高分辨率图像。这是一个“一对多”的问题，因为一张低分辨率图像可能对应多个合理的高分辨率版本。这是一个不适定问题，没有唯一正确答案。一旦图像被下采样，信息就永久丢失了。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_18.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_19.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_20.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_21.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_22.png)

以下是几种传统方法的对比：

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_24.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_25.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_26.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_27.png)

*   **双三次插值**：会产生模糊的图像。
*   **普通神经网络（无GAN）**：性能有所提升，但仍不完美。
*   **超分辨率生成对抗网络（SRGAN）**：能够“想象”并生成精细的细节，虽然不一定是原始图像的确切细节，但视觉效果更好。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_28.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_29.png)

## 数据与数学表示

超分辨率任务的一个优势是可以轻松生成大量训练数据。

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_31.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_32.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_33.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_34.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_35.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_36.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_37.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_38.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_39.png)

以下是数据生成流程：

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_40.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_41.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_42.png)

1.  获取一张原始高分辨率图像 `I_HR`（真实值）。
2.  使用高斯滤波器对图像进行模糊处理。
3.  以因子 `R`（如2、3、4）对模糊后的图像进行下采样，得到低分辨率图像 `I_LR`。
4.  这样，我们就得到了一个配对数据 `(I_LR, I_HR)`。

在数学上，我们的目标是训练一个生成器 `G`，它以低分辨率图像 `I_LR` 为条件输入，输出一张高分辨率图像 `I_SR`。公式表示为：
`I_SR = G(I_LR)`

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_44.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_45.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_46.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_47.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_48.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_49.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_50.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_51.png)

其中：
*   `I_LR` 的尺寸为 `W × H × C`（宽、高、通道数，例如RGB三通道）。
*   `I_SR` 和 `I_HR` 的尺寸为 `(s*W) × (s*H) × C`，`s` 是放大倍数。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_52.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_53.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_54.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_55.png)

## 网络架构与训练目标

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_57.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_58.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_59.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_60.png)

生成器 `G` 是一个条件生成网络，其结构通常包含一系列卷积层和残差连接。我们不过多讨论网络结构细节，只需知道它是一个包含卷积、批归一化和激活函数的深度网络。

训练的核心在于损失函数的设计。如果使用原始GAN框架，判别器 `D` 用于区分真实高分辨率图像 `I_HR` 和生成的高分辨率图像 `I_SR`。生成器的目标是生成能“欺骗”判别器的图像。

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_62.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_63.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_64.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_65.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_66.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_67.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_68.png)

对于SRGAN，其总损失函数是多种损失的加权组合：
`L_total = L_GAN + λ * L_content`

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_69.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_70.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_71.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_72.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_73.png)

其中：
*   `L_GAN` 是对抗损失，来自判别器。
*   `L_content` 是内容损失，用于保证生成图像的内容保真度。
*   `λ` 是一个超参数，用于平衡两项损失。



## 内容损失详解

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_75.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_76.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_77.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_78.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_79.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_80.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_81.png)

内容损失 `L_content` 有多种设计方式，目的是让生成图像在感知上与真实图像相似，而不仅仅是像素级相似。

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_82.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_83.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_84.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_85.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_86.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_88.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_89.png)

以下是两种常见的内容损失形式：

1.  **基于像素的均方误差（MSE）**：
    计算生成图像 `I_SR` 与真实图像 `I_HR` 之间每个像素的差异平方和。公式为：
    `L_MSE = 1/(W*H*C) * Σ (I_SR - I_HR)^2`
    这种方法倾向于生成平滑但可能缺乏纹理细节的结果。

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_91.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_92.png)

![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_93.png)

2.  **基于感知的特征重建损失（VGG损失）**：
    使用一个预训练的图像分类网络（如VGG）。将 `I_SR` 和 `I_HR` 分别输入该网络，提取某一中间层（例如第j层卷积后、第i层池化前）的特征图 `φ_{i,j}`。然后计算这两个特征图之间的MSE。公式为：
    `L_VGG = 1/(W_j*H_j*C_j) * Σ (φ_{i,j}(I_SR) - φ_{i,j}(I_HR))^2`
    这种方法鼓励生成图像在“语义”或“感知”层面与真实图像相似，能产生视觉上更逼真的纹理。



![](img/08d407c8bb74fbd9d3cc805aea8cb2fe_94.png)

## 模型评估与总结

本节课中我们一起学习了基于GAN的单图像超分辨率方法。

我们定义了数据集（通过下采样高分辨率图像获得配对数据），设定了模型先验（生成器和判别器神经网络），并设计了复合损失函数（结合对抗损失和内容损失）来优化模型。

在评估方面，超分辨率任务缺乏完美的客观评价指标。常用的指标包括：

*   **峰值信噪比（PSNR）**：与MSE损失高度相关。
*   **结构相似性指数（SSIM）**：衡量图像结构相似性。
*   **平均意见得分（MOS）**：通过人类主观评价来评估图像视觉质量。

一个重要的洞见是，我们可以利用预训练的神经网络（如用于Inception Score的Inception网络，或用于感知损失的VGG网络）来构建评估指标或损失函数本身，这极大地提升了生成模型的性能。