# 量化基础：P5：量化理论 🧠

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_1.png)

## 概述
在本节课中，我们将学习量化技术的基础理论，特别是**线性量化**。我们将了解如何将高精度（如FP32）的张量转换为低精度（如INT8）表示，从而显著减少模型大小。随后，我们将使用Hugging Face的**Quanto**工具库，对一个真实的PyTorch模型进行量化实践。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_3.png)

---

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_5.png)

## 量化简介
量化是将一个大的数值集合映射到一个更小的数值集合的过程。有多种量化技术，本节课我们将专注于最流行且在许多先进方法中应用的**线性量化**。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_7.png)

为了理解其工作原理，让我们看一个将FP32张量转换为INT8的简单示例。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_9.png)

## 线性量化示例
假设我们有一个FP32数值的随机矩阵。我们的目标是将这些值转换为INT8，同时尽量减少信息损失。

**核心思想**是建立一个线性映射：
- 将矩阵中的**最大正数**映射到INT8能表示的最大值（127）。
- 将矩阵中的**最小负数**映射到INT8能表示的最小值（-128）。
- 矩阵中的其余值则按照这个线性比例进行映射。

这个过程可以概括为以下公式：
`量化值 Q = round( (原始值 R - Z) / S )`
其中，`S`是**缩放因子（scale）**，`Z`是**零点（zero point）**。

通过这种映射，我们得到了一个量化的INT8张量，以及用于后续反量化的参数`S`和`Z`。原始的张量可以被删除以释放存储空间。

## 反量化与信息损失
量化后的张量如何变回近似原始的值呢？我们使用量化时建立的线性关系进行**反量化**。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_11.png)

反量化的公式是：
`反量化值 R' = S * Q + Z`

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_13.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_15.png)

需要注意的是，由于量化是**有损压缩**，反量化后的张量`R'`不会与原始张量`R`完全相同。两者之间的差异称为**量化误差**。不过，在精心设计的线性量化中，这个误差通常很小，对模型性能影响有限。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_17.png)

## 使用Quanto进行模型量化
理论理解后，我们将在实践中使用Hugging Face的**Quanto**库来量化一个真实的模型。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_19.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_21.png)

首先，确保环境已安装必要的库：
```python
# 安装命令（课程环境中已预装）
# pip install transformers
# pip install quanto
# pip install torch
```

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_23.png)

### 加载模型与分词器
我们将使用Transformers库加载一个模型及其对应的分词器。
```python
from transformers import AutoModelForCausalLM, AutoTokenizer

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_25.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_26.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_28.png)

model_name = "EleutherAI/pythia-410m"
model = AutoModelForCausalLM.from_pretrained(model_name, low_cpu_mem_usage=True)
tokenizer = AutoTokenizer.from_pretrained(model_name)
```

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_30.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_31.png)

加载的Pythia模型约有4.1亿参数。以FP32格式存储时，每个参数占4字节，因此模型大小约为**1.6 GB**。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_33.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_35.png)

### 执行量化
使用Quanto库对模型进行量化非常简单。我们主要量化模型中的线性层（`nn.Linear`）的权重。
```python
import torch
from quanto import quantize, freeze

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_37.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_39.png)

# 量化模型：将权重量化为INT8，激活保持原样（不量化）
quantized_model = quantize(model, weights=torch.int8, activations=None)
# 冻结量化状态，完成量化过程
quantized_model = freeze(quantized_model)
```
量化后，模型中的线性层会被替换为`QLinear`（量化线性层）。检查权重会发现它们已从FP32转换为INT8，并附带了缩放因子`S`。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_40.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_42.png)

### 验证结果
量化后，我们检查两点：
1.  **模型大小**：计算量化后的模型大小，理论上应为原大小的约1/4（INT8是32位的1/4）。
2.  **模型性能**：使用相同的输入让原始模型和量化模型生成文本，观察输出是否一致。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_44.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_46.png)

实践表明，在本次示例中，模型大小显著减小，而生成的文本结果保持不变，说明量化在减小模型的同时，成功保持了其核心功能。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_48.png)

---

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_50.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_52.png)

## 线性量化的数学原理（可选）
对于希望深入理解的同学，这里简要介绍线性映射的数学推导。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_54.png)

给定原始值范围 `[R_min, R_max]` 和目标量化值范围 `[Q_min, Q_max]`（例如INT8的[-128, 127]）。
线性映射关系为：
`R = S * (Q - Z)`

我们需要求解缩放因子`S`和零点`Z`：
- `S = (R_max - R_min) / (Q_max - Q_min)`
- `Z = Q_min - R_min / S`

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_56.png)

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_58.png)

通过这两个参数，我们可以在量化和反量化之间进行准确的转换。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_60.png)

## Quanto的中间状态（可选）
在调用`quantize()`后、`freeze()`前，模型处于一个**中间状态**。这个状态有两个主要用途：
1.  **校准（Calibration）**：如果计划对模型的激活（而不仅仅是权重）进行量化，可以通过输入一些样本数据（校准集）来运行模型，从而统计激活值的动态范围，为激活量化计算更合适的`S`和`Z`参数。
2.  **量化感知训练（Quantization-Aware Training, QAT）**：在此状态下训练模型。在前向传播中使用量化后的权重，但在反向传播中更新的是原始的、未量化的权重。这有助于模型在最终被“冻结”为完全量化状态时，保持更好的性能。

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_62.png)

---

![](img/ceb43ac1c783f8b91ab86c485c7a15bc_64.png)

## 总结
本节课我们一起学习了量化的核心概念。我们了解到**线性量化**通过建立`R = S * (Q - Z)`的映射关系，在FP32和INT8数值之间进行转换，从而大幅压缩模型体积。我们使用**Hugging Face Quanto**库实践了完整的模型量化流程，包括加载模型、执行量化以及验证结果。虽然量化会引入微小的信息损失，但通过合理的方案，我们可以在显著减小模型大小的同时，最大限度地保持其性能。在接下来的课程中，我们将探索量化技术如何应用于更复杂的大型语言模型。