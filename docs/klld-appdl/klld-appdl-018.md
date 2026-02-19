# 18：L9.1 - 恒等映射 🧠

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_1.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_3.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_5.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_7.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_9.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_11.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_13.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_15.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_17.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_19.png)

在本节课中，我们将要学习残差网络（ResNet）中恒等映射（Identity Mapping）的重要性。我们将深入探讨为何在残差块的捷径连接（shortcut connection）上保持线性操作至关重要，以及不同的操作顺序如何影响网络的训练效果和性能。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_21.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_23.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_25.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_27.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_29.png)

上一节我们介绍了残差网络及其捷径连接如何帮助训练更深的神经网络。本节中，我们来看看如何通过优化捷径连接的结构来进一步提升网络性能。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_31.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_33.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_35.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_37.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_39.png)

## 原始残差块结构

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_41.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_43.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_45.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_47.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_49.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_51.png)

原始的残差网络构建块结构如下：前一层的特征图输入后，依次经过卷积、批归一化（Batch Norm）、ReLU非线性激活，再进行一次卷积和批归一化，最后将结果与原始输入 `x_l` 相加，再经过一个ReLU激活得到输出 `x_{l+1}`。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_53.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_55.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_57.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_59.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_61.png)

其核心流程可以用以下伪代码表示：
```python
# 原始残差块结构
out = Conv(x_l)
out = BatchNorm(out)
out = ReLU(out)
out = Conv(out)
out = BatchNorm(out)
out = out + x_l  # 捷径连接
out = ReLU(out)  # 最后的非线性激活
x_{l+1} = out
```

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_63.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_65.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_67.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_69.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_71.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_73.png)

## 恒等映射的重要性

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_75.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_77.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_79.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_81.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_83.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_85.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_87.png)

同一批作者在后续论文中提出，为了训练极深的网络（例如1000层），捷径分支上不应有任何非线性操作或批归一化。信息应能通过捷径分支无阻碍地流动。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_89.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_91.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_93.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_95.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_97.png)

这意味着，在将残差分支的结果与输入 `x_l` 相加之前，**不应**在 `x_l` 上施加任何操作（如ReLU或BatchNorm）。同时，主分支（即残差计算路径）上操作的最佳顺序也被重新审视。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_99.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_101.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_103.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_105.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_107.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_109.png)

以下是关于操作顺序的核心发现：
*   原始顺序（卷积 -> BN -> ReLU -> 卷积 -> BN -> 相加 -> ReLU）并非最优。
*   将顺序调整为 **BN -> ReLU -> 卷积** 能显著降低测试误差，并让网络训练得更好。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_111.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_113.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_115.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_117.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_119.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_121.png)

## 理论分析：为什么捷径需要保持线性？

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_123.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_125.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_127.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_129.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_131.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_133.png)

为了理解原因，我们从一个更通用的残差块公式开始分析。设一个残差块的输出为：
`x_{l+1} = f( h(x_l) + F(x_l, W_l) )`
其中：
*   `h(x_l)` 是捷径分支的变换。
*   `F(x_l, W_l)` 是残差分支的变换。
*   `f` 是最后的激活函数（如ReLU）。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_135.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_137.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_139.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_141.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_143.png)

**理想情况：恒等映射**
当 `h` 和 `f` 都是恒等映射（即 `h(x)=x`, `f(x)=x`）时，公式简化为：
`x_{l+1} = x_l + F(x_l, W_l)`
此时，对于任意深层 `L` 和浅层 `l`，我们可以通过递归推导得到：
`x_L = x_l + Σ_{i=l}^{L-1} F(x_i, W_i)`
**公式表明，深层特征 `x_L` 可以直接表示为浅层特征 `x_l` 加上一系列残差函数之和。** 这确保了梯度可以从深层直接、无阻碍地传播到浅层，缓解了梯度消失/爆炸问题。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_145.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_147.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_149.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_151.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_153.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_155.png)

**非理想情况：捷径上的缩放**
如果捷径分支 `h` 是一个简单的线性缩放，例如 `h(x_l) = λ_l * x_l`，那么递归公式变为：
`x_L = (Π_{i=l}^{L-1} λ_i) * x_l + Σ_{i=l}^{L-1} (Π_{j=i+1}^{L-1} λ_j) * F(x_i, W_i)`
此时，`x_l` 前面乘上了一连串的系数乘积 `Πλ_i`。当层数很深时，如果 `λ_i > 1`，这个乘积会指数级爆炸；如果 `λ_i < 1`，则会指数级消失。这破坏了信息的直接传播。反向传播的梯度也会遇到同样的问题。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_157.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_159.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_161.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_163.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_165.png)

因此，**保持 `h(x)` 为恒等映射是确保信息在极深网络中顺畅流动的关键**。任何在捷径分支上的操作（即使是线性缩放）都可能阻碍这种流动。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_167.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_169.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_171.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_173.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_175.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_177.png)

## 不同变体的实验研究

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_179.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_181.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_183.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_185.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_187.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_189.png)

论文研究了多种对捷径连接或操作顺序的修改方案，以下是部分变体及其设计思路：

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_191.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_193.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_195.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_197.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_199.png)

*   **常数缩放**：将捷径分支和残差分支的输出都乘以0.5后再相加。
*   **卷积捷径**：使用1x1卷积来匹配 `x_l` 与残差分支的维度（这是原始ResNet中维度不匹配时的标准做法）。
*   **随机丢弃**：在捷径连接上应用Dropout，随机阻断捷径，迫使网络更多利用残差分支。
*   **门控机制**：引入可学习的参数（通过Sigmoid产生0到1之间的门控值），动态调整捷径和残差分支的权重。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_201.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_203.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_205.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_207.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_209.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_211.png)

实验结果表明，所有这些引入了额外操作的变体，其性能**均不如**保持捷径为纯净的恒等映射。这从实证上支持了理论分析。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_213.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_215.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_217.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_219.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_221.png)

## 操作顺序的优化

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_223.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_225.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_227.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_229.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_231.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_233.png)

除了保持捷径纯净，主分支上操作顺序也至关重要。论文比较了多种顺序配置：

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_235.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_237.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_239.png)

以下是几种主要的操作顺序配置：
1.  **原始顺序**：卷积 -> BN -> ReLU -> 卷积 -> BN -> 相加 -> ReLU
2.  **调整顺序A**：BN -> ReLU -> 卷积 -> BN -> ReLU -> 卷积 -> 相加
3.  **调整顺序B（最优）**：BN -> ReLU -> 卷积 -> BN -> ReLU -> 卷积 -> 相加（**注意：这是对两个卷积层都采用了“预激活”模式**）

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_241.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_243.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_245.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_247.png)

实际上，性能最佳的配置被称为“预激活”残差块，其结构可简化为：
```python
# 改进的预激活残差块结构
out = BatchNorm(x_l)
out = ReLU(out)
out = Conv(out)
out = BatchNorm(out)
out = ReLU(out)
out = Conv(out)
x_{l+1} = out + x_l  # 相加后不再有ReLU
```
这种将BN和ReLU置于卷积之前的顺序，被证明能带来更低的训练误差和测试误差。

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_249.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_251.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_253.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_255.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_257.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_259.png)

## 总结

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_261.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_263.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_265.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_267.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_269.png)

![](img/4a4d024a0a4b499b4e7a7301d81e6acf_271.png)

本节课中我们一起学习了残差网络中恒等映射的核心原理。关键要点在于：为了训练成百上千层的极深网络，必须**保持捷径连接是一个纯净的恒等映射**，避免在其上施加任何操作（包括线性缩放）。同时，在主分支上采用 **BN -> ReLU -> 卷积** 的“预激活”顺序能进一步优化训练动态和最终性能。这些改进确保了梯度与信息可以在网络的任意深度之间直接、高效地流动，这是成功训练深度残差网络的基石。