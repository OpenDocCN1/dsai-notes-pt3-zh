# 166：WaveNet 语音生成模型 🎵

在本节课中，我们将要学习 WaveNet，一种用于语音合成的生成式深度学习模型。我们将探讨其核心思想、模型架构以及如何利用因果卷积和空洞卷积来处理音频信号。

![](img/5de85f53e24c9a3e69b42554ccc50d04_1.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_2.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_3.png)

---

## 📝 概述

之前我们主要研究判别式模型，例如将语音转换为文本。在生成式模型方面，我们曾见过一个例子。WaveNet 是另一个重要的生成式模型，用于语音合成。其核心思想是将连续的音频波形离散化处理，并使用 Softmax 进行分类预测，这与之前使用高斯混合模型处理连续信号的方法不同。

![](img/5de85f53e24c9a3e69b42554ccc50d04_5.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_6.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_7.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_8.png)

## 🎯 核心思想：离散化波形

![](img/5de85f53e24c9a3e69b42554ccc50d04_10.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_11.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_12.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_13.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_14.png)

你的波形在每个时间步 `t` 上是一个连续变量 `X_t`。传统上，人们认为高斯混合模型适合对此建模。但 WaveNet 提出：**我们能否将连续信号视为离散的，并使用 Softmax 呢？**

![](img/5de85f53e24c9a3e69b42554ccc50d04_15.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_16.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_17.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_18.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_19.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_20.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_21.png)

给定历史信息，生成下一个样本，这就是生成任务。

![](img/5de85f53e24c9a3e69b42554ccc50d04_22.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_23.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_24.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_25.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_26.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_27.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_28.png)

## 🧱 模型架构：因果卷积堆栈

![](img/5de85f53e24c9a3e69b42554ccc50d04_29.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_30.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_31.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_32.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_33.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_34.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_35.png)

我们将使用一堆卷积层来建模。`X_t` 是音频的一个样本，我们需要为下一个值建立一个分类分布。

![](img/5de85f53e24c9a3e69b42554ccc50d04_36.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_37.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_38.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_39.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_40.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_41.png)

你不能使用任何类型的卷积，因为这是“预测下一个样本”的任务。我们需要使用**因果卷积**，它不会“看到”未来的信息，只会查看过去的信息。

![](img/5de85f53e24c9a3e69b42554ccc50d04_42.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_43.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_44.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_45.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_46.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_47.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_48.png)

以下是一个具有 5 个样本感受野的因果卷积示例。为什么是 5？因为输入中的 1, 2, 3, 4, 5 号样本会影响你的输出。

![](img/5de85f53e24c9a3e69b42554ccc50d04_49.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_50.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_51.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_52.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_53.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_54.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_55.png)

这 5 的感受野从何而来？假设你有 4 层，每层的滤波器大小是 2，这样你就能得到 5 的感受野。

![](img/5de85f53e24c9a3e69b42554ccc50d04_56.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_57.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_58.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_59.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_60.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_61.png)

## 🔍 扩大感受野：空洞卷积

![](img/5de85f53e24c9a3e69b42554ccc50d04_62.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_63.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_64.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_65.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_66.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_67.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_68.png)

有没有办法看到更久远的过去？有没有办法增加感受野？

![](img/5de85f53e24c9a3e69b42554ccc50d04_69.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_70.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_71.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_72.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_73.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_74.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_75.png)

对于学过第一部分课程的同学，你们知道在语义分割中，我们使用了一种叫做**空洞卷积**（或 Atrous 卷积）的技术。

![](img/5de85f53e24c9a3e69b42554ccc50d04_76.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_77.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_78.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_79.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_80.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_81.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_82.png)

空洞卷积通过引入“空洞”来扩大滤波器的感受野，而不增加参数数量或计算量。这使得网络能够捕捉更长距离的依赖关系，这对于建模音频等长序列数据至关重要。

![](img/5de85f53e24c9a3e69b42554ccc50d04_83.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_84.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_85.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_86.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_87.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_88.png)

## 📊 总结

![](img/5de85f53e24c9a3e69b42554ccc50d04_89.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_90.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_91.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_92.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_93.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_94.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_95.png)

本节课中，我们一起学习了 WaveNet 模型。

![](img/5de85f53e24c9a3e69b42554ccc50d04_96.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_97.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_98.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_99.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_100.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_101.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_102.png)

1.  我们了解了 WaveNet 的核心思想：将连续的音频信号离散化，并使用 Softmax 进行生成预测。
2.  我们介绍了模型的基础架构——因果卷积堆栈，它确保了预测只依赖于过去的信息。
3.  我们探讨了如何使用空洞卷积来有效地扩大网络的感受野，以建模音频序列中的长程依赖。

![](img/5de85f53e24c9a3e69b42554ccc50d04_103.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_104.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_105.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_106.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_107.png)

![](img/5de85f53e24c9a3e69b42554ccc50d04_108.png)

通过结合因果卷积和空洞卷积，WaveNet 能够高效地生成高质量、逼真的语音波形。