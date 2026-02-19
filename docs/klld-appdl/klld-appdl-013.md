# 13：L6.2 - Kaiming 参数初始化 🧠

![](img/2a83c3d6bd56a9e9b9fc12c277006098_0.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_2.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_4.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_6.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_8.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_10.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_11.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_13.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_15.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_17.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_19.png)

在本节课中，我们将要学习一篇关于神经网络参数初始化的经典论文。这篇论文的核心思想是，当使用 ReLU 及其变体作为激活函数时，如何正确地初始化网络权重，以确保信号在网络中传播时保持稳定的方差。这对于深度网络的训练至关重要。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_21.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_23.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_25.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_27.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_29.png)

---

![](img/2a83c3d6bd56a9e9b9fc12c277006098_31.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_33.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_35.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_37.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_39.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_41.png)

## 📄 论文背景与核心激活函数

![](img/2a83c3d6bd56a9e9b9fc12c277006098_43.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_45.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_47.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_49.png)

这篇论文假设你将使用修正线性单元（ReLU）作为激活函数。在此基础上，论文引入了一种新的激活函数，称为 **参数化修正线性单元**。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_51.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_53.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_55.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_57.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_59.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_61.png)

其函数形式如下：

![](img/2a83c3d6bd56a9e9b9fc12c277006098_63.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_65.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_67.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_68.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_70.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_72.png)

```
f(y_i) = max(0, y_i) + a_i * min(0, y_i)
```

![](img/2a83c3d6bd56a9e9b9fc12c277006098_74.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_75.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_77.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_79.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_80.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_82.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_84.png)

其中，`a_i` 是一个可以学习的参数。如果 `a_i` 是一个固定的、较小的常数（例如 0.01），并且不参与训练，那么这种激活函数被称为 **Leaky ReLU**。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_86.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_88.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_90.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_91.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_93.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_95.png)

在参数化 ReLU 中，`a_i` 可以针对不同的通道（channel）设置不同的值。这意味着每个通道都可以拥有自己独立的 `a_i` 参数。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_97.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_99.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_101.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_103.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_104.png)

---

![](img/2a83c3d6bd56a9e9b9fc12c277006098_106.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_108.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_110.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_112.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_114.png)

## 🔧 如何训练参数化 ReLU

![](img/2a83c3d6bd56a9e9b9fc12c277006098_116.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_117.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_119.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_121.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_122.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_124.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_126.png)

这些 `a_i` 参数是需要训练的。训练方法如下：

![](img/2a83c3d6bd56a9e9b9fc12c277006098_128.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_130.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_132.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_133.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_135.png)

1.  计算损失函数相对于参数 `a_i` 的梯度。
2.  使用动量（Momentum）等优化方法来更新 `a_i`。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_137.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_139.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_141.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_143.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_145.png)

实验结果表明，使用通道独立的参数化 ReLU（即每个通道学习自己的 `a_i`）可以将 Top-5 错误率从 13.34% 降低到 12.75%。如果所有通道共享同一个 `a_i` 参数，则性能会有所不同。对于固定 `a_i` 的 Leaky ReLU，Top-1 错误率有所改善，但 Top-5 错误率会变差。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_147.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_149.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_151.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_153.png)

这篇论文正是围绕这类激活函数展开的，并指出权重的初始化方式高度依赖于所使用的激活函数。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_155.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_157.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_159.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_161.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_163.png)

---

![](img/2a83c3d6bd56a9e9b9fc12c277006098_165.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_166.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_168.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_170.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_172.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_174.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_175.png)

## 🎯 初始化策略的核心思想

![](img/2a83c3d6bd56a9e9b9fc12c277006098_177.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_179.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_180.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_182.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_184.png)

一个良好的初始化策略，其核心指标应该是确保网络**每一层输出的方差**保持稳定。这是本篇论文的中心思想。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_186.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_188.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_190.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_192.png)

上一节我们介绍了参数化激活函数，本节中我们来看看如何将这个思想转化为具体的初始化公式。我们需要从卷积操作的基本形式开始分析。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_194.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_196.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_198.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_199.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_201.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_202.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_204.png)

---

![](img/2a83c3d6bd56a9e9b9fc12c277006098_206.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_208.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_210.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_212.png)

## 🧮 卷积层的矩阵化表示

![](img/2a83c3d6bd56a9e9b9fc12c277006098_214.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_215.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_217.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_218.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_220.png)

首先，我们将卷积操作表示为矩阵乘法的形式，以便进行方差分析。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_222.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_224.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_226.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_228.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_230.png)

假设在第 `l` 层：
*   `x_l` 是输入。对于卷积层，它不是一个完整的图像，而是滑动窗口中的一个局部块（patch）。
*   这个局部块的大小是 `k × k` 像素，并且有 `c` 个通道。
*   我们将这个三维块（`k × k × c`）展平（flatten）成一个一维向量，其长度为 `n = k * k * c`。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_232.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_234.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_236.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_238.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_240.png)

因此，`x_l` 是一个 `n × 1` 的向量。权重矩阵 `W_l` 的维度是 `d × n`，其中 `d` 是这一层滤波器的数量（即输出通道数）。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_241.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_243.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_244.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_246.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_247.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_249.png)

那么，该层在输出特征图某个位置上的响应 `y_l`（一个 `d × 1` 的向量）可以通过以下公式计算：

![](img/2a83c3d6bd56a9e9b9fc12c277006098_251.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_253.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_255.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_257.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_258.png)

```
y_l = W_l * x_l + b_l
```

![](img/2a83c3d6bd56a9e9b9fc12c277006098_260.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_262.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_264.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_266.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_268.png)

这里的 `*` 表示矩阵乘法。`b_l` 是偏置，也是一个 `d × 1` 的向量。这个操作本质上就是用一个 `d × n` 的矩阵乘以一个 `n × 1` 的向量，得到一个 `d × 1` 的向量。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_270.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_272.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_274.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_276.png)

**关键点**：网络层与层之间通过非线性激活函数连接。上一层的输出 `y_{l-1}` 经过激活函数（如 ReLU）后，成为当前层的输入 `x_l`。同时，当前层的输出 `y_l` 也将经过激活函数，成为下一层的输入。在维度上，上一层的输出通道数 `d_{l-1}` 等于当前层的输入通道数 `c_l`。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_278.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_280.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_282.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_284.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_286.png)

---

![](img/2a83c3d6bd56a9e9b9fc12c277006098_288.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_290.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_292.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_294.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_296.png)

## 📊 响应方差的推导

![](img/2a83c3d6bd56a9e9b9fc12c277006098_298.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_299.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_301.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_303.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_305.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_306.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_308.png)

现在，我们来分析输出响应 `y_l` 的方差。我们的目标是让 `y_l` 的方差在网络各层间保持稳定。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_310.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_312.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_314.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_316.png)

我们做出以下假设：
1.  权重 `W_l` 和输入 `x_l` 是相互独立的随机变量。
2.  权重初始化的均值为 0，即 `E[W_l] = 0`。
3.  偏置 `b_l` 初始化为 0。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_318.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_319.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_321.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_323.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_325.png)

根据方差公式，对于 `y_l` 中的任意一个元素（标量），其方差可以推导为：

![](img/2a83c3d6bd56a9e9b9fc12c277006098_327.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_328.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_330.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_332.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_333.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_334.png)

```
Var[y_l] = n_l * Var[W_l] * E[(x_l)^2]
```

![](img/2a83c3d6bd56a9e9b9fc12c277006098_336.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_338.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_340.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_342.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_344.png)

其中，`n_l = k * k * c_l`，是第 `l` 层一个输入向量的长度（连接数）。`Var[W_l]` 是权重分布的方差。`E[(x_l)^2]` 是输入 `x_l` 的二阶矩。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_345.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_346.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_348.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_350.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_352.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_354.png)

**请注意**：由于 `x_l` 是上一层输出经过 ReLU 激活后的结果，它的均值不一定为 0。因此，`E[(x_l)^2]` 并不等于 `Var[x_l]`（除非均值为 0）。这是 ReLU 族激活函数带来的一个重要特性。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_356.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_358.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_359.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_361.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_363.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_365.png)

---

![](img/2a83c3d6bd56a9e9b9fc12c277006098_367.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_369.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_371.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_373.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_375.png)

## 🧪 方差的向前传播

![](img/2a83c3d6bd56a9e9b9fc12c277006098_377.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_379.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_381.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_383.png)

为了保持各层激活值的尺度，我们希望每一层输出的方差 `Var[y_l]` 都大致相等。从上面的公式可以看出，`Var[y_l]` 依赖于 `n_l`（当前层的“扇入”连接数）和 `E[(x_l)^2]`（上一层激活值的二阶矩）。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_385.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_387.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_389.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_390.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_392.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_394.png)

通过精心设计权重初始化的方差 `Var[W_l]`，我们可以补偿 `n_l` 的变化，从而让 `Var[y_l]` 保持恒定。这就是 Kaiming 初始化方法的核心推导过程。

![](img/2a83c3d6bd56a9e9b9fc12c277006098_396.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_398.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_400.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_402.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_403.png)

---

![](img/2a83c3d6bd56a9e9b9fc12c277006098_405.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_407.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_409.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_411.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_413.png)

## 💎 课程总结

![](img/2a83c3d6bd56a9e9b9fc12c277006098_415.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_417.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_419.png)

![](img/2a83c3d6bd56a9e9b9fc12c277006098_421.png)

本节课中我们一起学习了 Kaiming 初始化方法背后的原理。我们首先了解了论文针对 ReLU 族激活函数的背景，然后通过将卷积操作矩阵化，推导了网络层响应方差的传播公式。关键结论是，权重的初始化方差需要根据前一层的连接数 `n_l` 和激活函数的二阶矩进行调整，以确保信号在深度网络中的稳定流动。这为训练非常深的神经网络提供了重要的理论基础。