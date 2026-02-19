# 32：L17.2 - XNOR网络详解 🧠

![](img/dcea48a3ac4055614224c1aca4422e5b_0.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_2.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_4.png)

在本节课中，我们将学习XNOR网络的核心思想。这是一种极端的神经网络压缩方法，通过将权重和输入二值化（即用1和-1表示），来大幅减少模型的内存占用和计算开销。我们将从宏观概念入手，逐步深入到数学推导，理解其如何实现高效推理。

![](img/dcea48a3ac4055614224c1aca4422e5b_6.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_8.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_10.png)

## 📊 概述与动机

![](img/dcea48a3ac4055614224c1aca4422e5b_12.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_14.png)

上一节我们讨论了神经网络权重的低位存储。本节我们将探讨一种更极端的压缩方式：XNOR网络。该方法的核心是将权重和输入二值化，从而用简单的逻辑运算替代复杂的乘加操作。

![](img/dcea48a3ac4055614224c1aca4422e5b_16.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_0.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_18.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_20.png)

有同学曾提问，能否将32位权重用更低的位数存储，例如16位或8位。这篇论文将这一思路推向极致：它提出将权重存储在单个比特中，即用二进制值（0/1或+1/-1）表示。

![](img/dcea48a3ac4055614224c1aca4422e5b_22.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_24.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_4.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_26.png)

这就是“XNOR”名称的由来。我们将在细节中看到，XNOR网络使用了二值化卷积，整个网络被二值化。

![](img/dcea48a3ac4055614224c1aca4422e5b_28.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_30.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_32.png)

## 🖼️ 网络二值化全景

![](img/dcea48a3ac4055614224c1aca4422e5b_34.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_36.png)

以下是XNOR网络的整体流程图示。

![](img/dcea48a3ac4055614224c1aca4422e5b_38.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_40.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_10.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_42.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_44.png)

你有一个输入图像和一系列卷积核。让我们关注网络的这一部分。

![](img/dcea48a3ac4055614224c1aca4422e5b_46.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_12.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_48.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_50.png)

这里有输入张量和权重张量。权重是卷积核，意味着你需要用标准的卷积操作在输入张量上滑动它们。

![](img/dcea48a3ac4055614224c1aca4422e5b_52.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_54.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_16.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_56.png)

假设所有数据都是32位浮点数：输入是32位，权重也用32位表示。

![](img/dcea48a3ac4055614224c1aca4422e5b_58.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_60.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_20.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_62.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_64.png)

此时的操作包括加法、减法和乘法。你需要将两个数相乘，然后将结果相加，因为你在计算滤波器与输入的点积。

![](img/dcea48a3ac4055614224c1aca4422e5b_66.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_68.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_26.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_70.png)

这将是我们的**基线模型**。在内存和计算量上，我们将其基准设为1。同时，这也是我们的**基线精度**。

![](img/dcea48a3ac4055614224c1aca4422e5b_72.png)

我们将进行两个步骤：
1.  **二值化权重**。
2.  **二值化输入**。

![](img/dcea48a3ac4055614224c1aca4422e5b_74.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_76.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_78.png)

### 步骤一：二值化权重

![](img/dcea48a3ac4055614224c1aca4422e5b_80.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_82.png)

二值化权重意味着最终值只能是**+1**或**-1**。

![](img/dcea48a3ac4055614224c1aca4422e5b_84.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_86.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_32.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_88.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_90.png)

当用这个二值权重与输入相乘时，你只需要进行**加法和减法**操作，而**不需要任何乘法**。因为你乘以的不是+1就是-1。

![](img/dcea48a3ac4055614224c1aca4422e5b_92.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_38.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_94.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_96.png)

例如，将-1乘以-0.21没有意义，你可以直接用加法替代乘法。这将在计算上带来**2倍的节省**，在内存上带来**32倍的节省**（因为1位替代了32位）。

![](img/dcea48a3ac4055614224c1aca4422e5b_98.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_100.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_102.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_104.png)

### 步骤二：二值化输入

![](img/dcea48a3ac4055614224c1aca4422e5b_106.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_108.png)

接下来，我们同样二值化输入。

![](img/dcea48a3ac4055614224c1aca4422e5b_110.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_112.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_50.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_114.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_116.png)

可以预见，这会损失一些精度，但会带来巨大的计算节省。因为此时的操作不再是加法和减法，而是更快的**XNOR运算**。

![](img/dcea48a3ac4055614224c1aca4422e5b_118.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_56.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_120.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_122.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_124.png)

## 🔍 深入细节与疑问

![](img/dcea48a3ac4055614224c1aca4422e5b_126.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_128.png)

以上是宏观图景。但中间那行（指二值化后精度变化）看起来有些可疑，因为我们之前在讨论深度压缩时曾展示，量化过度会导致精度损失。

![](img/dcea48a3ac4055614224c1aca4422e5b_130.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_132.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_60.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_134.png)

这似乎是比量化更极端的版本，只是根据正负号重新映射数值。但当我们深入细节后，你会发现方法完全不同。在深度压缩中，你先进行剪枝，然后进行参数共享（寻找质心）。而这里的方法是直接二值化。

![](img/dcea48a3ac4055614224c1aca4422e5b_136.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_138.png)

有同学（Cooper）提问：这是从第一层就开始二值化吗？

![](img/dcea48a3ac4055614224c1aca4422e5b_140.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_142.png)

**是的**，从第一层开始。但注意，我们**不二值化原始的输入图像**。当我们二值化输入时，实际上会对输入进行归一化（例如减去均值），使其包含正负值。

![](img/dcea48a3ac4055614224c1aca4422e5b_144.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_146.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_148.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_150.png)

## 🎯 应用场景

![](img/dcea48a3ac4055614224c1aca4422e5b_152.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_154.png)

XNOR网络在以下领域有应用前景：
*   **虚拟现实（VR）**
*   **增强现实（AR）**
*   **智能可穿戴设备**

![](img/dcea48a3ac4055614224c1aca4422e5b_156.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_158.png)

因为这些应用场景需要网络模型非常轻量。

![](img/dcea48a3ac4055614224c1aca4422e5b_160.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_162.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_164.png)

## 📐 数学推导

![](img/dcea48a3ac4055614224c1aca4422e5b_166.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_168.png)

现在让我们看看背后的数学原理。

![](img/dcea48a3ac4055614224c1aca4422e5b_170.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_172.png)

我们的输入张量有 `C` 个通道，宽为 `W_in`，高为 `H_in`。权重（单个滤波器）具有相同的输入通道数，以及滤波器尺寸 `w` 和 `h`。

![](img/dcea48a3ac4055614224c1aca4422e5b_174.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_176.png)

我们将权重 `W` 近似为一个标量 `α` 乘以一个二值权重矩阵 `B`：

![](img/dcea48a3ac4055614224c1aca4422e5b_178.png)

**公式：** `W ≈ α * B`

![](img/dcea48a3ac4055614224c1aca4422e5b_180.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_182.png)

这是一个近似，因为我们对 `B` 有约束：它必须是二值矩阵（元素为+1或-1）。`α` 可以仍然是一个32位浮点数，作为缩放因子。

![](img/dcea48a3ac4055614224c1aca4422e5b_184.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_186.png)

对于卷积操作，正如之前解释的，由于 `B` 的值是+1或-1，因此不需要乘法，只需要加法和减法。

![](img/dcea48a3ac4055614224c1aca4422e5b_188.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_190.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_192.png)

### 目标函数

![](img/dcea48a3ac4055614224c1aca4422e5b_194.png)

为了形式化，我们将张量展平为N维数组。这里的维度 `n = c * w * h`。

![](img/dcea48a3ac4055614224c1aca4422e5b_196.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_198.png)

我们希望 `W` 尽可能接近 `αB`，因此定义目标函数：

![](img/dcea48a3ac4055614224c1aca4422e5b_200.png)

**公式：** `J(B, α) = ||W - αB||²`

![](img/dcea48a3ac4055614224c1aca4422e5b_202.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_204.png)

将其展开：
`J(B, α) = α²BᵀB - 2αWᵀB + WᵀW`

![](img/dcea48a3ac4055614224c1aca4422e5b_206.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_208.png)

*   `BᵀB`：由于 `B` 中每个元素是+1或-1，其平方总是1，求和后等于 `n`。
*   `WᵀW`：已知权重 `W`，这是一个常数，记为 `C`。

![](img/dcea48a3ac4055614224c1aca4422e5b_210.png)

因此，目标函数简化为：
`J(B, α) = α²n - 2αWᵀB + C`

![](img/dcea48a3ac4055614224c1aca4422e5b_212.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_214.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_216.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_218.png)

### 求解最优 B 和 α

![](img/dcea48a3ac4055614224c1aca4422e5b_220.png)

我们的目标是找到使 `J` 最小的 `B` 和 `α`。

![](img/dcea48a3ac4055614224c1aca4422e5b_222.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_224.png)

**首先，求解最优 B (`B*`)：**

![](img/dcea48a3ac4055614224c1aca4422e5b_226.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_228.png)

在 `J` 的表达式中，与 `B` 相关的项是 `-2αWᵀB`。由于我们假设 `α > 0`，**最小化 `J` 等价于最大化 `WᵀB`**。

![](img/dcea48a3ac4055614224c1aca4422e5b_230.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_232.png)

`B` 的每个元素 `B_i` 只能是 +1 或 -1。为了使 `WᵀB` 最大，一个简单的策略是：
*   当 `W_i` 为正时，令 `B_i = +1`。
*   当 `W_i` 为负时，令 `B_i = -1`。

![](img/dcea48a3ac4055614224c1aca4422e5b_234.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_236.png)

这样，每一项 `W_i * B_i` 都变为正数，求和后得到最大值。

![](img/dcea48a3ac4055614224c1aca4422e5b_238.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_240.png)

因此，最优二值权重为：
**公式：** `B* = sign(W)`
其中 `sign(·)` 是符号函数。

![](img/dcea48a3ac4055614224c1aca4422e5b_242.png)

---

![](img/dcea48a3ac4055614224c1aca4422e5b_244.png)

## 💡 训练过程与总结

![](img/dcea48a3ac4055614224c1aca4422e5b_246.png)

**关于训练：** 有同学问，这是直接对一个预训练模型（如AlexNet）的权重进行二值化吗？实际上，**这里有训练步骤**。

![](img/dcea48a3ac4055614224c1aca4422e5b_248.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_250.png)

在训练过程中：
1.  **前向传播**：使用计算得到的 `α*` 和 `B*` 进行。
2.  **反向传播**：更新的是全精度的权重 `W`（而不是 `B`）。每次反向传播后，会根据更新后的 `W` 重新计算 `B*` 和 `α*`。

![](img/dcea48a3ac4055614224c1aca4422e5b_252.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_254.png)

如果只是简单地将预训练模型的权重二值化而不进行微调训练，模型精度会严重下降。最终部署到设备上的模型，使用的是训练收敛后的 `α*` 和 `B*`。

![](img/dcea48a3ac4055614224c1aca4422e5b_256.png)

![](img/dcea48a3ac4055614224c1aca4422e5b_258.png)

**本节课总结：**
我们一起学习了XNOR网络，一种通过将权重和输入二值化来极致压缩神经网络的方法。我们了解了其动机、宏观流程、数学推导（如何求解最优二值权重 `B* = sign(W)`）以及大致的训练过程。这种方法牺牲了一定精度，但换来了内存和计算效率的极大提升，非常适合部署在资源受限的边缘设备上。