# 🧠 P182：L80.4 - 深度学习中的模型不确定性

在本节课中，我们将要学习深度学习中的模型不确定性。我们将探讨为什么需要量化模型的不确定性，如何通过贝叶斯视角理解Dropout技术，以及如何利用Dropout在推理阶段估计模型预测的不确定性。这对于强化学习中的探索、回归任务的外推以及分类任务中识别未知数据都至关重要。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_1.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_2.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_3.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_4.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_5.png)

---

![](img/9bb1da85b481d9b5a83045f7eedf4b79_6.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_7.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_8.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_9.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_10.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_11.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_12.png)

## 为什么需要模型不确定性？🤔

上一节我们介绍了模型不确定性的概念，本节中我们来看看为什么需要它。

一个常见的误解是，分类器输出的概率（例如0.7）就代表了模型对该预测的不确定性。实际上，神经网络输出的概率本身并不等同于模型对自身预测的置信度。模型还需要一种机制来表达“我从未见过这类数据，因此我不确定该分配什么概率”。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_14.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_15.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_16.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_17.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_18.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_19.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_20.png)

考虑一个回归任务的例子：你的训练数据集中在 `x ∈ [-3, 2.5]` 的区间内。即使你有无限多的训练数据，模型对这个区间内的预测会非常确定。但是，当你输入一个远超出此区间的测试数据（例如 `x = 10`）时，一个理想的模型应该能表达出高度的不确定性，因为它无法从训练数据中“插值”出这个结果。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_21.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_22.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_23.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_24.png)

在分类任务中，这种需求同样存在但更隐晦。你需要在Softmax输出的概率之上，再增加一层不确定性，用以建模“未见过此类数据”的情况。

---

![](img/9bb1da85b481d9b5a83045f7eedf4b79_26.png)

## 贝叶斯神经网络：理论基础 🧮

![](img/9bb1da85b481d9b5a83045f7eedf4b79_27.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_28.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_29.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_30.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_31.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_32.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_33.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_34.png)

为了从原理上理解不确定性估计，我们需要转向贝叶斯方法。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_35.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_36.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_37.png)

一个简单的神经网络可以表示为：
`输出 = softmax(W2 * relu(W1 * x))`
其中，`x` 的维度是 `D0`，`W1` 的维度是 `[D1, D0]`，`W2` 的维度是 `[D2, D1]`。

以贝叶斯的方式正确训练神经网络，意味着我们需要为参数 `W1` 和 `W2` 设置**先验分布**，然后根据观测到的数据 `D` 计算**后验分布**。当有新数据点 `x*` 需要预测时，我们需要根据后验分布对参数进行边际化（积分）：
`P(y* | x*, D) = ∫ P(y* | x*, W) P(W | D) dW`
这样，预测就条件依赖于我们已有的全部数据 `D`。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_39.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_40.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_41.png)

然而，真实的后验分布 `P(W | D)` 通常是难以处理的（intractable）。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_42.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_43.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_44.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_45.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_46.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_47.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_48.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_49.png)

---

![](img/9bb1da85b481d9b5a83045f7eedf4b79_50.png)

## 变分推断与Dropout的等价性 🔗

面对难以处理的后验分布，我们可以使用**变分推断**。我们引入一个由参数 `φ` 控制的近似分布 `Q(W; φ)`，并最小化其与真实后验 `P(W | D)` 之间的KL散度。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_52.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_53.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_54.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_55.png)

通过推导（利用ELBO，证据下界），我们可以将目标函数转化为两项：
`L(φ) = -E_{Q(W;φ)}[log P(D | W)] + KL(Q(W; φ) || P(W))`
第一项是期望负对数似然（即常见的损失函数），第二项是近似分布与先验分布的KL散度（起到正则化作用）。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_56.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_57.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_58.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_59.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_60.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_61.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_62.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_63.png)

现在，我们对近似分布 `Q` 做出具体假设：
1.  各层权重 `W_l` 相互独立。
2.  每个 `Q(W_l)` 是一个**二分量高斯混合分布**：以概率 `p` 采样自 `N(0, σ²I)`，以概率 `1-p` 采样自 `N(M_l, σ²I)`，其中 `σ` 是一个非常小的值（接近机器精度）。

当我们从这个分布中采样时，过程等价于：首先从伯努利分布中采样一个掩码向量 `z_l`，然后计算 `W_l = diag(z_l) * M_l`。这正是**Dropout**的操作！`M_l` 对应学习到的权重矩阵，`z_l` 对应Dropout掩码。

将此形式代入目标函数 `L(φ)`，经过化简（并设 `σ → 0`），我们得到：
`L(φ) ≈ -1/N Σ log P(y_i | x_i, M, z_i) + λ Σ ||M_l||²`
这正是使用Dropout和权重衰减（L2正则化）训练神经网络的标准损失函数。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_65.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_66.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_67.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_68.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_69.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_70.png)

---

![](img/9bb1da85b481d9b5a83045f7eedf4b79_71.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_72.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_73.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_74.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_75.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_76.png)

## 实践：利用Dropout估计不确定性 🛠️

训练阶段与标准的Dropout训练完全相同。关键的区别在于**推理阶段**。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_78.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_79.png)

以下是标准Dropout推理与用于不确定性估计的Dropout推理的对比：

![](img/9bb1da85b481d9b5a83045f7eedf4b79_80.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_81.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_82.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_83.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_84.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_85.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_86.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_87.png)

**标准Dropout推理：**
1.  关闭Dropout，使用权重均值进行一次性预测。
2.  报告单一的预测结果（如类别概率或回归值）。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_88.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_89.png)

**用于不确定性估计的Dropout推理（蒙特卡洛Dropout）：**
1.  **保持Dropout开启**。
2.  对于同一个输入 `x*`，执行 `T` 次前向传播，每次使用不同的Dropout掩码，得到 `T` 个预测结果 `{y*_1, ..., y*_T}`。
3.  将这些预测结果视为来自预测后验分布的样本。
4.  计算这些样本的**均值**作为最终预测，计算**方差**作为不确定性的度量。

对于分类任务，你可以计算 `T` 个概率向量的均值和方差。对于回归任务，你可以计算 `T` 个标量预测的均值和方差。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_91.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_92.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_93.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_94.png)

---

![](img/9bb1da85b481d9b5a83045f7eedf4b79_95.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_96.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_97.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_98.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_99.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_100.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_101.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_102.png)

## 应用场景 🌍

掌握了蒙特卡洛Dropout方法后，我们来看看它的应用。

*   **分类中的未知数据检测**：当模型看到一个与训练数据差异很大的图像（如剧烈旋转的手写数字）时，虽然Softmax可能仍会给出一个高概率值，但多次Dropout采样产生的概率分布方差会很大，表明模型“不确定”。
*   **回归中的外推不确定性**：在时间序列预测中，对于远超历史数据的未来时间点，模型预测的方差会增大，合理反映外推的风险。
*   **强化学习中的探索**：在智能体决策时，可以依据其Q值预测的不确定性（方差）来引导探索。在不确定性高的状态-动作对上多尝试，而不是单纯依赖 `ε-greedy` 的随机探索。

![](img/9bb1da85b481d9b5a83045f7eedf4b79_104.png)

![](img/9bb1da85b481d9b5a83045f7eedf4b79_105.png)

---

## 总结 📚

本节课中我们一起学习了深度学习中的模型不确定性。

1.  **核心需求**：模型需要区分“预测的概率”和“对预测的信心”，尤其在面对分布外数据时。
2.  **理论基础**：将带有Dropout的神经网络训练，解释为对贝叶斯神经网络进行变分推断，其中Dropout等价于对权重使用特定的高斯混合先验。
3.  **实践方法**：在推理阶段使用**蒙特卡洛Dropout**——多次运行带有Dropout的模型，用预测结果的方差来量化不确定性。
4.  **应用价值**：该方法为分类、回归和强化学习任务提供了简单而有效的**不确定性估计**工具，无需改变模型训练过程，仅需调整推理方式。

这种方法计算复杂度较高，因为需要对每个输入进行多次前向传播，但它提供了一种理论坚实且易于实现的途径，让深度神经网络能够说“我不知道”。