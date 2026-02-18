![](img/acf5e2bab5a9891154bea9f15595a69f_0.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_2.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_4.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_6.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_8.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_10.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_12.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_14.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_16.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_18.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_20.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_22.png)

# 6：Transformer架构及其潜在竞争者 🧠

![](img/acf5e2bab5a9891154bea9f15595a69f_24.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_26.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_28.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_30.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_32.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_34.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_36.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_38.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_40.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_42.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_44.png)

在本节课中，我们将要学习Transformer网络架构的核心原理，并探讨其潜在的竞争对手。我们将从理解不同神经网络架构的设计初衷开始，逐步分析自注意力机制如何取代循环神经网络，并最终了解一系列旨在改进或替代Transformer的新兴架构。

![](img/acf5e2bab5a9891154bea9f15595a69f_46.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_48.png)

---

![](img/acf5e2bab5a9891154bea9f15595a69f_50.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_52.png)

上一节我们介绍了神经网络架构各有其设计初衷。本节中我们来看看Transformer架构出现的理由。

![](img/acf5e2bab5a9891154bea9f15595a69f_54.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_56.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_58.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_60.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_62.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_64.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_66.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_68.png)

更精确地说，我们讨论的是Transformer中的一个核心层：自注意力层。在自注意力层出现之前，处理序列数据的常用架构是RNN或LSTM。理解自注意力如何取代它们，有助于我们想象为何其他架构（如Mamba）可能取代自注意力。

![](img/acf5e2bab5a9891154bea9f15595a69f_70.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_72.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_74.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_76.png)

这些架构（RNN、自注意力、Mamba）要解决的核心问题是：输入一个向量序列，输出另一个向量序列。对于语言模型，通常每个输出只能看到其左侧的输入。

![](img/acf5e2bab5a9891154bea9f15595a69f_78.png)

### RNN的工作原理

![](img/acf5e2bab5a9891154bea9f15595a69f_80.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_82.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_84.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_86.png)

RNN流派网络架构的基本精神如下：它通过一个称为隐藏状态的东西，将目前已看到的所有输入信息混合存储起来。输出时，只需根据隐藏状态即可决定当前输出。

![](img/acf5e2bab5a9891154bea9f15595a69f_88.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_90.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_92.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_94.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_96.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_98.png)

更具体地说，RNN流派的广义写法可以表示为：
```
H_t = F_A(H_{t-1}) + F_B(X_t)
Y_t = F_C(H_t)
```
其中，`H`代表隐藏状态中存储的信息，`F_A`、`F_B`、`F_C`是函数（通常包含可训练参数）。`H_t`由前一时间点的隐藏状态`H_{t-1}`和当前输入`X_t`共同决定。

![](img/acf5e2bab5a9891154bea9f15595a69f_100.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_102.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_104.png)

以下是RNN运作过程的可视化步骤：
1.  从初始隐藏状态`H_0`和输入`X_1`开始。
2.  根据`X_1`和`H_0`，通过`F_A`和`F_B`产生`H_1`。
3.  `H_1`通过`F_C`产生输出`Y_1`。
4.  输入`X_2`，`X_2`通过`F_B`，`H_1`通过`F_A`，相加得到`H_2`。
5.  `H_2`通过`F_C`产生`Y_2`。
6.  此过程反复进行，直到处理完所有输入。

![](img/acf5e2bab5a9891154bea9f15595a69f_106.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_108.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_110.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_112.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_114.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_116.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_118.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_120.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_122.png)

更泛化的写法是为`F_A`、`F_B`、`F_C`加上下标`t`，表示这些函数可以随时间变化（例如，根据输入`X_t`的不同而改变）。LSTM或GRU等带有门控机制的RNN，其实就是让这些函数与时间（即输入）相关。

![](img/acf5e2bab5a9891154bea9f15595a69f_124.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_126.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_128.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_130.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_132.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_134.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_136.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_138.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_140.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_142.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_144.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_146.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_148.png)

在推理时（例如使用训练好的语言模型生成句子），RNN的运作方式是自回归的：根据当前隐藏状态和输入生成一个输出词，然后将该输出词作为下一时间步的输入，如此循环。

![](img/acf5e2bab5a9891154bea9f15595a69f_150.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_152.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_154.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_156.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_158.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_160.png)

---

![](img/acf5e2bab5a9891154bea9f15595a69f_162.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_164.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_166.png)

上一节我们介绍了RNN如何处理序列数据。本节中我们来看看自注意力机制是如何运作的，以及它相较于RNN的优势。

![](img/acf5e2bab5a9891154bea9f15595a69f_168.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_170.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_172.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_174.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_176.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_178.png)

自注意力机制运作如下：输入是一个序列`X_1`到`X_T`。每个输入向量通过三个不同的变换，产生三个向量：查询`Q`、键`K`和值`V`。例如，`X_1`产生`Q_1`、`K_1`、`V_1`。

![](img/acf5e2bab5a9891154bea9f15595a69f_180.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_182.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_184.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_186.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_188.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_190.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_192.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_194.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_196.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_198.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_200.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_202.png)

计算第`t`个位置的输出`Y_t`时：
1.  将`Q_t`与所有位置的`K`（`K_1`到`K_T`）计算内积，得到一组数值`α`（称为注意力权重）。
2.  对这组`α`值进行Softmax操作，使其和为1。
3.  将这些归一化后的注意力权重与对应位置的`V`向量进行加权求和，得到`Y_t`。

![](img/acf5e2bab5a9891154bea9f15595a69f_204.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_206.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_208.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_210.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_211.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_213.png)

在推理生成句子时，自注意力机制也是自回归的。但不同于RNN的是，生成第`t`个输出时，自注意力需要查看前面所有`t-1`个位置的输入信息。

![](img/acf5e2bab5a9891154bea9f15595a69f_215.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_217.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_219.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_221.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_223.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_225.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_227.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_229.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_231.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_233.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_235.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_237.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_239.png)

### RNN与自注意力的比较

![](img/acf5e2bab5a9891154bea9f15595a69f_241.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_243.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_245.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_247.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_249.png)

以下是两者在推理时的关键区别：

![](img/acf5e2bab5a9891154bea9f15595a69f_251.png)

**计算量与内存需求**
*   **RNN**：每一步的运算量和内存需求是固定的，只需维护当前的隐藏状态。
*   **自注意力**：运算量和内存需求随序列长度增加而增加，因为需要存储和计算之前所有位置的信息。

![](img/acf5e2bab5a9891154bea9f15595a69f_253.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_255.png)

**训练并行化**
*   **自注意力**：给定完整输入序列，可以并行计算出所有位置的输出，这极大地利用了GPU的并行计算能力，加快了训练速度。其计算过程可转化为一系列矩阵运算（如`Q * K^T`，再与`V`相乘），非常适合GPU处理。
*   **RNN**：计算存在序列依赖性（需先算`H_1`才能算`H_2`），难以并行化，训练速度较慢。

![](img/acf5e2bab5a9891154bea9f15595a69f_257.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_259.png)

因此，自注意力的核心优势在于**训练时的高效并行化能力**，而非其存储无限长信息的能力（这在实际中受维度限制，只是一种假象）。然而，随着模型需要处理的序列越来越长（如长文档、多模态数据），自注意力在推理时的计算和内存开销成为瓶颈，这促使人们重新审视RNN类架构的价值。

![](img/acf5e2bab5a9891154bea9f15595a69f_261.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_263.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_265.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_267.png)

---

![](img/acf5e2bab5a9891154bea9f15595a69f_269.png)

上一节我们分析了自注意力在长序列推理时的劣势。本节中我们探讨RNN是否能在训练时实现并行化，从而结合两者的优点。

![](img/acf5e2bab5a9891154bea9f15595a69f_271.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_273.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_275.png)

我们从一个简化的RNN开始：移除其反思部分（即`F_A`函数），令`H_t = H_{t-1} + F_B(X_t)`。展开后，`H_t`变为从`X_1`到`X_T`所有输入经过`F_B`变换后的和。

![](img/acf5e2bab5a9891154bea9f15595a69f_277.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_279.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_281.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_283.png)

进一步简化，假设`H`是一个矩阵，`F_B(X_t)`写作`D_t`，且`D_t`可以分解为`V_t * K_t^T`（`V`和`K`是向量）。输出`Y_t`是`H_t`与查询向量`Q_t`的乘积。

![](img/acf5e2bab5a9891154bea9f15595a69f_285.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_287.png)

通过变换计算顺序，先计算`K^T * Q`得到标量权重`α`，再对`V`向量进行加权求和，我们得到了一个熟悉的表达式：
```
Y_t = α_{t,1} * V_1 + α_{t,2} * V_2 + ... + α_{t,t} * V_t
```
这正是**自注意力机制，只是缺少了Softmax**。这种架构被称为**线性注意力**。

线性注意力的意义在于：
*   **训练时**：它可以像标准自注意力一样展开，进行高效的并行化训练。
*   **推理时**：它像RNN一样，只需维护一个固定大小的隐藏状态`H_t`进行更新，计算量和内存需求恒定。

![](img/acf5e2bab5a9891154bea9f15595a69f_289.png)

然而，线性注意力在实践中性能通常不如标准的（带Softmax的）自注意力。一个关键原因是其记忆永远不会被遗忘或修改（只是不断累加）。Softmax的作用是让注意力权重动态归一化，使模型能够根据当前上下文，**相对地**决定哪些过去信息更重要，从而实现动态的“记忆管理”。

![](img/acf5e2bab5a9891154bea9f15595a69f_291.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_293.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_295.png)

---

![](img/acf5e2bab5a9891154bea9f15595a69f_297.png)

上一节我们看到了线性注意力的局限性。本节中我们介绍如何为其引入“反思”机制，以及一系列基于此思想的改进架构。

![](img/acf5e2bab5a9891154bea9f15595a69f_299.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_301.png)

为了让线性注意力具备动态记忆能力，研究者们引入了可学习的门控机制。例如：
*   **Retention Network**：在隐藏状态更新时乘以一个衰减因子`γ`（0到1之间），让旧记忆逐渐淡忘。
*   **Gated Retention**：使衰减因子`γ_t`随时间变化并由网络学习，让模型根据输入决定遗忘程度。
*   **更复杂的门控**：使用一个矩阵`G_t`与隐藏状态进行逐元素相乘，以控制每个记忆单元的保留、减弱或清除。当`G_t`具有特定结构（如`1 * s_t^T`）时，仍能保持训练的可并行性。

![](img/acf5e2bab5a9891154bea9f15595a69f_303.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_305.png)

在这一系列类似线性注意力的架构中，最著名的是**Mamba**。它在论文中展示了在多种模型规模下，其性能可以超越改进后的Transformer，并且在**推理速度上具有显著优势**，尤其适合处理长序列。

除了Mamba，还有其他变体如**DeltaNet**，它将记忆更新过程解释为针对特定损失函数的梯度下降步骤，为记忆更新提供了新的理论视角。

这些架构（统称为状态空间模型或SSM）已被用于训练大型语言模型（如Jamba、MiniMax-01），并在图像生成等领域（如模型Sina）得到应用，以加速推理。当前的一个研究趋势是：在现有大型Transformer模型（如LLaMA）的基础上，将其中的自注意力层替换为Mamba等线性注意力变体进行微调，以快速验证新架构的有效性。

![](img/acf5e2bab5a9891154bea9f15595a69f_307.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_309.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_311.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_313.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_315.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_317.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_319.png)

---

![](img/acf5e2bab5a9891154bea9f15595a69f_321.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_323.png)

本节课中我们一起学习了：
1.  **架构的设计初衷**：CNN为图像特性设计以减少过拟合；残差连接为优化深度网络而设计；自注意力则为训练并行化而设计。
2.  **自注意力与RNN的对比**：自注意力训练并行化效率高，但推理时资源消耗随序列长度增长；RNN推理效率高且资源恒定，但训练难以并行。
3.  **线性注意力**：揭示了自注意力与RNN在数学上的紧密联系（仅差一个Softmax），并提供了结合两者优点的思路。
4.  **Transformer的竞争者**：以Mamba为代表的一系列线性注意力变体，通过引入可学习的门控反思机制，在保持训练并行化的同时，实现了RNN般高效的推理，成为处理长序列任务的有力竞争者。

![](img/acf5e2bab5a9891154bea9f15595a69f_325.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_327.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_329.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_331.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_333.png)

![](img/acf5e2bab5a9891154bea9f15595a69f_335.png)

最终，关于“注意力是否一切所需”的争论仍在继续，新的架构探索旨在结合不同范式的优点，以应对下一代AI模型对效率和处理超长序列能力的挑战。