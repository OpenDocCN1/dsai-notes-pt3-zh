# 9：利用多张GPU训练大型语言模型 🚀

![](img/723e9c79ea07c23eb14c99280ea0a075_0.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_2.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_4.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_6.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_8.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_10.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_12.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_14.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_16.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_18.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_20.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_22.png)

在本节课中，我们将学习如何利用多张GPU来训练大型语言模型。我们将探讨训练大模型时面临的主要挑战，并介绍一系列实用的工具和技术，帮助你克服硬件限制，高效地进行模型训练。

![](img/723e9c79ea07c23eb14c99280ea0a075_24.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_26.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_28.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_30.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_32.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_34.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_36.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_38.png)

---

![](img/723e9c79ea07c23eb14c99280ea0a075_40.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_42.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_44.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_46.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_48.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_50.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_52.png)

## 概述

![](img/723e9c79ea07c23eb14c99280ea0a075_54.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_56.png)

训练大型语言模型通常需要巨大的计算资源和内存。一张GPU往往无法容纳整个模型及其训练所需的所有中间状态。本节课将系统地介绍如何通过软件工具，将模型和计算任务分布到多张GPU上，从而解决内存不足和计算效率低下的问题。

![](img/723e9c79ea07c23eb14c99280ea0a075_58.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_60.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_62.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_64.png)

---

![](img/723e9c79ea07c23eb14c99280ea0a075_66.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_68.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_70.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_72.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_74.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_76.png)

## 训练大型语言模型的挑战

![](img/723e9c79ea07c23eb14c99280ea0a075_78.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_80.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_82.png)

上一节我们概述了课程目标，本节中我们来看看训练大型语言模型具体面临哪些困难。

![](img/723e9c79ea07c23eb14c99280ea0a075_84.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_86.png)

一个标准的前向传播和反向传播流程如下：模型接收一个词元序列作为输入，并输出一个词元分布。通过计算损失函数（如交叉熵损失），并使用反向传播算法计算梯度，最终通过优化器（如Adam）更新模型参数。

![](img/723e9c79ea07c23eb14c99280ea0a075_88.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_90.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_92.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_94.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_96.png)

**核心公式：** 梯度下降更新规则可以表示为：
`θ = θ - η * ∇J(θ)`
其中 `θ` 是模型参数，`η` 是学习率，`∇J(θ)` 是损失函数 `J` 关于 `θ` 的梯度。

![](img/723e9c79ea07c23eb14c99280ea0a075_98.png)

对于大型语言模型，主要问题在于模型参数量极其庞大。例如，一个80亿参数（8B）的模型，仅存储FP32精度的参数就需要约32GB内存。而在实际训练中，我们还需要存储更多组件。

![](img/723e9c79ea07c23eb14c99280ea0a075_100.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_102.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_104.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_106.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_108.png)

以下是训练一个8B模型所需内存的粗略估算：

![](img/723e9c79ea07c23eb14c99280ea0a075_110.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_112.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_114.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_116.png)

1.  **模型参数 (FP32):** 32 GB
2.  **模型参数 (FP16，用于计算):** 16 GB
3.  **梯度 (与参数同大小):** 32 GB
4.  **优化器状态 (Adam):** 64 GB (包含动量和方差两个状态，各32GB)

![](img/723e9c79ea07c23eb14c99280ea0a075_118.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_120.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_122.png)

仅这些组件加起来就已达 **128GB**，这超过了大多数单张GPU的显存容量。

![](img/723e9c79ea07c23eb14c99280ea0a075_124.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_126.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_128.png)

此外，还有一个更严峻的挑战来自**激活值**。在反向传播过程中，需要保存每一层网络的前向传播输出（即激活值）来计算梯度。对于Transformer模型中的注意力机制，其空间复杂度与输入序列长度的平方（O(N²)）成正比。当输入序列很长时（例如16K或32K），激活值所占用的内存会变得极其巨大，甚至可能达到TB级别。

![](img/723e9c79ea07c23eb14c99280ea0a075_130.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_132.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_134.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_136.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_138.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_140.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_142.png)

为了解决激活值内存占用过高的问题，业界常用一种称为**激活重计算**（也称为梯度检查点）的技术。其核心思想是在前向传播时不保存所有中间激活值，只在反向传播需要时重新计算它们。这是一种用计算时间换取内存空间的方法。

![](img/723e9c79ea07c23eb14c99280ea0a075_144.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_146.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_148.png)

最后，为了训练的稳定性，大语言模型通常需要很大的**批次大小**。当单次无法处理如此大的批次时，我们会使用**梯度累积**技术：将一个大批次拆分成多个小批次，分别计算梯度并累加，累加达到指定步数后再一次性更新模型参数。

![](img/723e9c79ea07c23eb14c99280ea0a075_150.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_152.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_154.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_156.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_158.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_160.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_162.png)

---

![](img/723e9c79ea07c23eb14c99280ea0a075_164.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_166.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_168.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_170.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_172.png)

## 第一部分：优化参数、梯度和优化器状态

![](img/723e9c79ea07c23eb14c99280ea0a075_174.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_176.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_178.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_180.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_182.png)

上一节我们分析了训练大模型的内存瓶颈，本节中我们来看看如何优化参数、梯度和优化器状态的内存占用。

![](img/723e9c79ea07c23eb14c99280ea0a075_184.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_186.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_188.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_190.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_192.png)

既然单张GPU无法容纳所有训练组件，最直观的思路就是使用多张GPU，将模型和状态“拆分”存放。这正是**DeepSpeed**库的核心功能，它实现了名为**ZeRO**的优化器。

![](img/723e9c79ea07c23eb14c99280ea0a075_194.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_196.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_198.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_200.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_202.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_204.png)

ZeRO有三个级别，级别越高，节省的内存越多，但GPU间的数据传输开销也相应增加。

![](img/723e9c79ea07c23eb14c99280ea0a075_206.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_208.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_210.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_212.png)

*   **ZeRO-1:** 仅对优化器状态进行分片。每个GPU只保存一部分优化器状态（如Adam的动量和方差）。
*   **ZeRO-2:** 在ZeRO-1的基础上，额外对梯度进行分片。
*   **ZeRO-3:** 在ZeRO-2的基础上，进一步对模型参数本身进行分片。这是最节省内存的模式。

![](img/723e9c79ea07c23eb14c99280ea0a075_214.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_216.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_218.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_220.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_222.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_224.png)

**核心概念图示：**
```
ZeRO-1: [GPU0: 1/4 Optim States] [GPU1: 1/4 Optim States] ...
ZeRO-2: [GPU0: 1/4 Optim States + 1/4 Grads] ...
ZeRO-3: [GPU0: 1/4 Optim States + 1/4 Grads + 1/4 Params] ...
```

![](img/723e9c79ea07c23eb14c99280ea0a075_226.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_228.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_230.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_232.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_234.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_236.png)

得益于NVIDIA GPU间高速的NVLink互联（传输速度可达900GB/s），以及DeepSpeed精心设计的数据传输调度，这些分片操作带来的通信开销是可控的。

![](img/723e9c79ea07c23eb14c99280ea0a075_238.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_240.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_242.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_244.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_246.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_248.png)

如果即使使用多张GPU和ZeRO技术，显存仍然不足，DeepSpeed还提供了**卸载**功能，可以将部分数据（如优化器状态）暂时存放到CPU内存中，需要时再加载回GPU。但需要注意的是，GPU与CPU之间的数据传输速度远慢于GPU间传输，这会导致训练速度显著下降，因此应尽量避免使用。

![](img/723e9c79ea07c23eb14c99280ea0a075_250.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_252.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_254.png)

**实验结论：**
*   使用8张32GB显存的V100 GPU，配合DeepSpeed ZeRO，可以成功全参数微调一个8B模型。
*   应优先通过增加GPU数量和使用ZeRO来解决问题，尽量避免使用CPU卸载功能。

![](img/723e9c79ea07c23eb14c99280ea0a075_256.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_258.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_260.png)

---

![](img/723e9c79ea07c23eb14c99280ea0a075_262.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_264.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_266.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_268.png)

## 第二部分：优化激活值内存

![](img/723e9c79ea07c23eb14c99280ea0a075_270.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_272.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_274.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_276.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_278.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_280.png)

解决了参数和优化器状态的内存问题后，本节我们聚焦于如何解决长序列输入带来的巨大激活值内存开销。

![](img/723e9c79ea07c23eb14c99280ea0a075_282.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_284.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_286.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_288.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_290.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_292.png)

问题的根源在于注意力机制的计算。我们需要重写其计算内核，使其更高效。**内核**是指在GPU上运行的底层函数。从高级到低级，常见的编写内核的方式有：
1.  PyTorch原生操作
2.  PyTorch的 `torch.compile` 装饰器
3.  Triton（一种用Python编写GPU内核的接口）
4.  CUDA（NVIDIA官方的C/C++套件）

![](img/723e9c79ea07c23eb14c99280ea0a075_294.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_296.png)

以下是两种流行的优化方案：

![](img/723e9c79ea07c23eb14c99280ea0a075_298.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_300.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_302.png)

**Flash Attention**
Flash Attention通过实现一个融合内核，将注意力计算中的矩阵乘法、缩放、Softmax等操作合并为一个高效的GPU函数。它不仅计算更快，还通过巧妙的内存管理（将中间结果暂存于高速但容量小的显存，或与CPU内存交换），将注意力机制的内存占用从O(N²)降低到接近O(N)。这使其能够处理非常长的输入序列。

![](img/723e9c79ea07c23eb14c99280ea0a075_304.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_306.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_308.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_310.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_312.png)

**vLLM / PagedAttention**
（注：虽然讲稿中提到了“Lego Kernel”，但根据上下文描述的特性——由台湾开发者编写、通过替换`AutoModel`为`AutoLiKernel`来加速——这很可能指的是类似vLLM或PagedAttention的技术。这类技术通过为注意力机制中的键值缓存实现分页管理，就像操作系统管理内存一样，极大地提高了长序列生成的吞吐量和内存使用效率。）

![](img/723e9c79ea07c23eb14c99280ea0a075_314.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_316.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_318.png)

**核心优势：**
*   **速度更快：** 融合内核减少了内存访问次数，提升了计算效率。
*   **内存更省：** 优化了注意力矩阵的存储和计算方式。
*   **支持更长上下文：** 使得训练或推理超长文本序列成为可能。

![](img/723e9c79ea07c23eb14c99280ea0a075_320.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_322.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_324.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_326.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_327.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_329.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_331.png)

如今，许多流行的Transformer库（如Hugging Face `transformers`）已原生集成或支持这些优化内核，通常只需安装相应依赖即可自动启用。

![](img/723e9c79ea07c23eb14c99280ea0a075_333.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_335.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_337.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_339.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_341.png)

---

![](img/723e9c79ea07c23eb14c99280ea0a075_343.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_345.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_347.png)

## 第三部分：模型量化

![](img/723e9c79ea07c23eb14c99280ea0a075_349.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_351.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_353.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_355.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_357.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_359.png)

到目前为止，我们讨论的工具主要针对模型训练。本节我们介绍一个主要用于模型推理部署的技术：**量化**。

![](img/723e9c79ea07c23eb14c99280ea0a075_361.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_363.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_365.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_367.png)

量化是一种有损压缩技术。其核心思想是使用更低精度的数据类型（如8位整数INT8、4位整数INT4）来存储和计算模型参数，从而大幅减少模型占用的内存和提升推理速度。

![](img/723e9c79ea07c23eb14c99280ea0a075_369.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_371.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_373.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_375.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_377.png)

**核心过程：**
`FP32 权重 -> 量化 -> INT8/INT4 权重 -> 反量化 -> 近似 FP32 权重用于计算`

![](img/723e9c79ea07c23eb14c99280ea0a075_379.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_381.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_383.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_385.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_387.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_389.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_391.png)

常见的量化算法有很多，例如GPTQ、AWQ、GGUF等。例如，一个名为`Llama-3-8B-Q8`的模型，表示它是8B参数的Llama 3模型，并且其权重被量化为8位整数。这样，原本需要约16GB（FP16）显存加载的模型，现在只需要约8GB，使得在消费级GPU（如15GB显存的T4）上运行大模型成为可能。

![](img/723e9c79ea07c23eb14c99280ea0a075_393.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_395.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_397.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_399.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_401.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_403.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_405.png)

**注意：** 量化通常会导致模型精度轻微下降，并且主要用于推理阶段。虽然也存在用于训练的量化技术，但其应用更为复杂。

![](img/723e9c79ea07c23eb14c99280ea0a075_407.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_409.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_411.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_413.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_415.png)

---

![](img/723e9c79ea07c23eb14c99280ea0a075_417.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_419.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_421.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_423.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_425.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_427.png)

## 总结与推荐阅读

![](img/723e9c79ea07c23eb14c99280ea0a075_429.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_431.png)

本节课我们一起学习了利用多张GPU训练大型语言模型所需的关键工具和技术。

![](img/723e9c79ea07c23eb14c99280ea0a075_433.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_435.png)

我们首先分析了训练大模型在内存和计算上面临的三大挑战：庞大的参数与优化器状态、长序列产生的巨大激活值、以及大批次需求。接着，我们介绍了对应的解决方案：
1.  使用 **DeepSpeed** 及其 **ZeRO** 优化器，将模型参数、梯度和优化器状态分片到多张GPU上。
2.  使用 **Flash Attention** 或类似的高效注意力内核，优化长序列计算的内存和速度。
3.  使用 **量化** 技术，降低模型存储和推理时的资源消耗。

![](img/723e9c79ea07c23eb14c99280ea0a075_437.png)

通过组合使用这些工具，我们可以最大限度地利用现有硬件资源，成功训练和部署大型语言模型。

![](img/723e9c79ea07c23eb14c99280ea0a075_439.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_441.png)

**推荐延伸阅读：**
1.  Hugging Face 发布的《使用GPU集群进行高效训练》指南，内容非常详尽。
2.  Hugging Face `transformers` 库中关于如何集成并使用 DeepSpeed 的官方文档，通常只需配置一个JSON文件即可启用。

![](img/723e9c79ea07c23eb14c99280ea0a075_443.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_445.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_447.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_449.png)

---
**请注意：** 本教程根据提供的视频讲稿内容整理，部分工具名称（如“Lego Kernel”）的描述可能基于讲稿当时的语境或口误，在实际应用中建议以主流开源项目（如vLLM、FlashAttention）的名称为准进行搜索和学习。