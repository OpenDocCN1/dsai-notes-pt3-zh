# 🧠 课程 P20：实现 Transformer 模型

在本节课中，我们将学习如何实现一个简化版的 Transformer 模型。我们将重点关注 Transformer 的核心优势——在训练时并行化计算自注意力机制。课程将通过两个具体的代码练习，从简单的分类任务到文本生成任务，逐步讲解如何高效地实现自注意力。

![](img/1bffdc57c2785e5647c824db2af3396b_1.png)

![](img/1bffdc57c2785e5647c824db2af3396b_3.png)

![](img/1bffdc57c2785e5647c824db2af3396b_5.png)

---

![](img/1bffdc57c2785e5647c824db2af3396b_6.png)

![](img/1bffdc57c2785e5647c824db2af3396b_7.png)

![](img/1bffdc57c2785e5647c824db2af3396b_9.png)

![](img/1bffdc57c2785e5647c824db2af3396b_10.png)

## 📖 概述与数据准备

![](img/1bffdc57c2785e5647c824db2af3396b_12.png)

![](img/1bffdc57c2785e5647c824db2af3396b_13.png)

![](img/1bffdc57c2785e5647c824db2af3396b_14.png)

![](img/1bffdc57c2785e5647c824db2af3396b_15.png)

![](img/1bffdc57c2785e5647c824db2af3396b_17.png)

![](img/1bffdc57c2785e5647c824db2af3396b_18.png)

![](img/1bffdc57c2785e5647c824db2af3396b_19.png)

首先，我们从一个简单的垃圾邮件分类任务开始。这个任务的目标是使用 Transformer 作为编码器，将句子分类为“垃圾邮件”或“非垃圾邮件”。我们使用一个包含四个句子的微型数据集进行演示。

![](img/1bffdc57c2785e5647c824db2af3396b_21.png)

![](img/1bffdc57c2785e5647c824db2af3396b_22.png)

![](img/1bffdc57c2785e5647c824db2af3396b_23.png)

![](img/1bffdc57c2785e5647c824db2af3396b_24.png)

![](img/1bffdc57c2785e5647c824db2af3396b_26.png)

以下是我们的数据：

![](img/1bffdc57c2785e5647c824db2af3396b_28.png)

![](img/1bffdc57c2785e5647c824db2af3396b_29.png)

![](img/1bffdc57c2785e5647c824db2af3396b_30.png)

![](img/1bffdc57c2785e5647c824db2af3396b_31.png)

![](img/1bffdc57c2785e5647c824db2af3396b_32.png)

![](img/1bffdc57c2785e5647c824db2af3396b_34.png)

![](img/1bffdc57c2785e5647c824db2af3396b_35.png)

![](img/1bffdc57c2785e5647c824db2af3396b_36.png)

![](img/1bffdc57c2785e5647c824db2af3396b_37.png)

```python
sentences = [
    "you want a billion dollars",
    "click here for midterm answers",
    "send me your bank account info",
    "read important CS685 news"
]
labels = [1, 1, 1, 0]  # 1代表垃圾邮件，0代表非垃圾邮件
```

![](img/1bffdc57c2785e5647c824db2af3396b_39.png)

![](img/1bffdc57c2785e5647c824db2af3396b_40.png)

![](img/1bffdc57c2785e5647c824db2af3396b_42.png)

![](img/1bffdc57c2785e5647c824db2af3396b_43.png)

![](img/1bffdc57c2785e5647c824db2af3396b_44.png)

![](img/1bffdc57c2785e5647c824db2af3396b_45.png)

![](img/1bffdc57c2785e5647c824db2af3396b_46.png)

我们需要将这些句子转换为模型可以处理的格式。以下代码将句子分割成单词（标记），并为每个唯一的单词类型分配一个索引，构建词汇表。

![](img/1bffdc57c2785e5647c824db2af3396b_48.png)

![](img/1bffdc57c2785e5647c824db2af3396b_49.png)

![](img/1bffdc57c2785e5647c824db2af3396b_50.png)

![](img/1bffdc57c2785e5647c824db2af3396b_52.png)

![](img/1bffdc57c2785e5647c824db2af3396b_53.png)

![](img/1bffdc57c2785e5647c824db2af3396b_54.png)

![](img/1bffdc57c2785e5647c824db2af3396b_55.png)

```python
# 构建词汇表
vocab = {}
idx = 0
inputs = []
for sent in sentences:
    tokens = sent.split()
    idxs = []
    for token in tokens:
        if token not in vocab:
            vocab[token] = idx
            idx += 1
        idxs.append(vocab[token])
    inputs.append(idxs)
```

![](img/1bffdc57c2785e5647c824db2af3396b_57.png)

![](img/1bffdc57c2785e5647c824db2af3396b_58.png)

![](img/1bffdc57c2785e5647c824db2af3396b_59.png)

![](img/1bffdc57c2785e5647c824db2af3396b_60.png)

![](img/1bffdc57c2785e5647c824db2af3396b_61.png)

![](img/1bffdc57c2785e5647c824db2af3396b_63.png)

![](img/1bffdc57c2785e5647c824db2af3396b_64.png)

运行这段代码后，`inputs` 变量将包含每个句子对应的索引列表。例如，单词 “CS685” 出现在两个句子中，它在词汇表中的索引是相同的。

![](img/1bffdc57c2785e5647c824db2af3396b_66.png)

![](img/1bffdc57c2785e5647c824db2af3396b_68.png)

![](img/1bffdc57c2785e5647c824db2af3396b_70.png)

![](img/1bffdc57c2785e5647c824db2af3396b_71.png)

---

![](img/1bffdc57c2785e5647c824db2af3396b_73.png)

## 🏗️ 网络架构：SelfAttentionNN

![](img/1bffdc57c2785e5647c824db2af3396b_75.png)

![](img/1bffdc57c2785e5647c824db2af3396b_77.png)

![](img/1bffdc57c2785e5647c824db2af3396b_78.png)

![](img/1bffdc57c2785e5647c824db2af3396b_79.png)

![](img/1bffdc57c2785e5647c824db2af3396b_80.png)

接下来，我们定义神经网络架构，称为 `SelfAttentionNN`。它的目标是作为一个分类器。

![](img/1bffdc57c2785e5647c824db2af3396b_82.png)

![](img/1bffdc57c2785e5647c824db2af3396b_83.png)

![](img/1bffdc57c2785e5647c824db2af3396b_85.png)

![](img/1bffdc57c2785e5647c824db2af3396b_86.png)

![](img/1bffdc57c2785e5647c824db2af3396b_88.png)

![](img/1bffdc57c2785e5647c824db2af3396b_89.png)

![](img/1bffdc57c2785e5647c824db2af3396b_91.png)

![](img/1bffdc57c2785e5647c824db2af3396b_93.png)

![](img/1bffdc57c2785e5647c824db2af3396b_94.png)

在 `__init__` 函数中，我们初始化网络的所有参数：
*   **嵌入层 (`self.embeddings`)**：用于获取词嵌入。
*   **查询、键、值投影矩阵**：我们将使用一个单层的自注意力网络，因此需要将词嵌入投影到查询、键和值空间。
*   **输出前馈层 (`self.output_ff`)**：用于计算最终的分类预测（垃圾邮件或非垃圾邮件）。

![](img/1bffdc57c2785e5647c824db2af3396b_96.png)

![](img/1bffdc57c2785e5647c824db2af3396b_97.png)

![](img/1bffdc57c2785e5647c824db2af3396b_98.png)

![](img/1bffdc57c2785e5647c824db2af3396b_100.png)

```python
import torch
import torch.nn as nn

![](img/1bffdc57c2785e5647c824db2af3396b_102.png)

![](img/1bffdc57c2785e5647c824db2af3396b_104.png)

![](img/1bffdc57c2785e5647c824db2af3396b_106.png)

class SelfAttentionNN(nn.Module):
    def __init__(self, vocab_size, embed_dim, num_classes):
        super(SelfAttentionNN, self).__init__()
        self.embeddings = nn.Embedding(vocab_size, embed_dim)
        self.q_proj = nn.Linear(embed_dim, embed_dim)
        self.k_proj = nn.Linear(embed_dim, embed_dim)
        self.v_proj = nn.Linear(embed_dim, embed_dim)
        self.output_ff = nn.Linear(embed_dim, num_classes)
```

![](img/1bffdc57c2785e5647c824db2af3396b_108.png)

![](img/1bffdc57c2785e5647c824db2af3396b_109.png)

![](img/1bffdc57c2785e5647c824db2af3396b_111.png)

![](img/1bffdc57c2785e5647c824db2af3396b_112.png)

我们还定义了几种注意力函数，但本节课只实现最简单的点积注意力。Transformer 在实践中使用的是缩放点积注意力。

![](img/1bffdc57c2785e5647c824db2af3396b_114.png)

![](img/1bffdc57c2785e5647c824db2af3396b_116.png)

![](img/1bffdc57c2785e5647c824db2af3396b_118.png)

在 `forward` 函数中，模型接收一个句子（索引列表）作为输入。流程如下：
1.  获取输入序列的长度 `n`。
2.  通过嵌入层将索引转换为词嵌入矩阵 `M`，其形状为 `(n, embed_dim)`。
3.  将词嵌入投影到查询 (`Q`)、键 (`K`) 和值 (`V`) 空间。
4.  为序列中的每个词嵌入计算自注意力。
5.  将所有词的输出嵌入组合成一个单一的向量。
6.  将该向量传递给输出前馈层，得到最终的预测。

![](img/1bffdc57c2785e5647c824db2af3396b_120.png)

![](img/1bffdc57c2785e5647c824db2af3396b_121.png)

![](img/1bffdc57c2785e5647c824db2af3396b_122.png)

![](img/1bffdc57c2785e5647c824db2af3396b_123.png)

![](img/1bffdc57c2785e5647c824db2af3396b_124.png)

![](img/1bffdc57c2785e5647c824db2af3396b_126.png)

![](img/1bffdc57c2785e5647c824db2af3396b_128.png)

![](img/1bffdc57c2785e5647c824db2af3396b_130.png)

![](img/1bffdc57c2785e5647c824db2af3396b_132.png)

我们使用标准的训练循环，使用交叉熵损失和随机梯度下降优化器，期望损失能下降到接近零，这表明网络至少可以在这个微型训练集上过拟合。

![](img/1bffdc57c2785e5647c824db2af3396b_133.png)

![](img/1bffdc57c2785e5647c824db2af3396b_135.png)

![](img/1bffdc57c2785e5647c824db2af3396b_137.png)

![](img/1bffdc57c2785e5647c824db2af3396b_138.png)

![](img/1bffdc57c2785e5647c824db2af3396b_139.png)

---

![](img/1bffdc57c2785e5647c824db2af3396b_141.png)

![](img/1bffdc57c2785e5647c824db2af3396b_142.png)

![](img/1bffdc57c2785e5647c824db2af3396b_143.png)

![](img/1bffdc57c2785e5647c824db2af3396b_144.png)

## ⏳ 方法一：低效循环实现

![](img/1bffdc57c2785e5647c824db2af3396b_146.png)

![](img/1bffdc57c2785e5647c824db2af3396b_147.png)

![](img/1bffdc57c2785e5647c824db2af3396b_148.png)

![](img/1bffdc57c2785e5647c824db2af3396b_149.png)

![](img/1bffdc57c2785e5647c824db2af3396b_151.png)

![](img/1bffdc57c2785e5647c824db2af3396b_153.png)

![](img/1bffdc57c2785e5647c824db2af3396b_155.png)

![](img/1bffdc57c2785e5647c824db2af3396b_157.png)

为了理解自注意力的核心计算，我们首先用一种简单但低效的方式实现它。这种方法使用循环，易于理解但速度慢。

![](img/1bffdc57c2785e5647c824db2af3396b_158.png)

![](img/1bffdc57c2785e5647c824db2af3396b_160.png)

![](img/1bffdc57c2785e5647c824db2af3396b_162.png)

![](img/1bffdc57c2785e5647c824db2af3396b_164.png)

![](img/1bffdc57c2785e5647c824db2af3396b_165.png)

![](img/1bffdc57c2785e5647c824db2af3396b_166.png)

![](img/1bffdc57c2785e5647c824db2af3396b_167.png)

**核心思想**：对于序列中的每个位置 `i`（作为查询），计算其查询向量 `Q[i]` 与所有键向量 `K` 的点积，得到未归一化的分数。然后应用 softmax 函数将这些分数转换为概率分布。最后，使用这些概率作为权重，计算值向量 `V` 的加权平均，得到该位置的输出表示。

![](img/1bffdc57c2785e5647c824db2af3396b_169.png)

![](img/1bffdc57c2785e5647c824db2af3396b_171.png)

![](img/1bffdc57c2785e5647c824db2af3396b_173.png)

![](img/1bffdc57c2785e5647c824db2af3396b_174.png)

![](img/1bffdc57c2785e5647c824db2af3396b_176.png)

![](img/1bffdc57c2785e5647c824db2af3396b_177.png)

![](img/1bffdc57c2785e5647c824db2af3396b_178.png)

以下是实现步骤：

![](img/1bffdc57c2785e5647c824db2af3396b_179.png)

![](img/1bffdc57c2785e5647c824db2af3396b_180.png)

![](img/1bffdc57c2785e5647c824db2af3396b_182.png)

![](img/1bffdc57c2785e5647c824db2af3396b_184.png)

![](img/1bffdc57c2785e5647c824db2af3396b_186.png)

![](img/1bffdc57c2785e5647c824db2af3396b_188.png)

1.  **投影**：首先，将嵌入矩阵 `M` 投影到查询、键和值空间。
    ```python
    Q = self.q_proj(M)  # 形状: (n, embed_dim)
    K = self.k_proj(M)  # 形状: (n, embed_dim)
    V = self.v_proj(M)  # 形状: (n, embed_dim)
    ```

![](img/1bffdc57c2785e5647c824db2af3396b_190.png)

![](img/1bffdc57c2785e5647c824db2af3396b_192.png)

![](img/1bffdc57c2785e5647c824db2af3396b_194.png)

2.  **初始化输出矩阵**：创建一个与嵌入矩阵相同大小的矩阵 `attention_reps` 来存储每个位置的注意力输出。
    ```python
    attention_reps = torch.zeros_like(M)  # 形状: (n, embed_dim)
    ```

![](img/1bffdc57c2785e5647c824db2af3396b_196.png)

![](img/1bffdc57c2785e5647c824db2af3396b_198.png)

3.  **循环计算**：对序列中的每个位置 `i` 进行循环。
    ```python
    for i in range(n):
        # 获取当前查询向量
        q_i = Q[i]  # 形状: (embed_dim,)
        # 计算与所有键的点积（未归一化分数）
        unnorm_scores = torch.mv(K, q_i)  # 矩阵-向量乘法，结果形状: (n,)
        # 应用 softmax 得到概率分布
        probs = torch.nn.functional.softmax(unnorm_scores, dim=0)  # 形状: (n,)
        # 计算值向量的加权平均
        # 方法A: 使用矩阵-向量乘法
        weighted_avg = torch.mv(V.t(), probs)  # V.t() 形状 (embed_dim, n), 结果形状 (embed_dim,)
        # 方法B: 使用广播和元素乘法 (解释概念)
        # weighted_avg = (V * probs[:, None]).sum(dim=0) # 利用广播
        # 存储结果
        attention_reps[i] = weighted_avg
    ```

![](img/1bffdc57c2785e5647c824db2af3396b_199.png)

![](img/1bffdc57c2785e5647c824db2af3396b_200.png)

![](img/1bffdc57c2785e5647c824db2af3396b_201.png)

![](img/1bffdc57c2785e5647c824db2af3396b_203.png)

![](img/1bffdc57c2785e5647c824db2af3396b_205.png)

![](img/1bffdc57c2785e5647c824db2af3396b_207.png)

4.  **组合与分类**：获得每个位置的注意力表示后，我们需要将它们组合成一个代表整个句子的向量。这里我们简单地计算所有位置表示的平均值。
    ```python
    composed_vector = torch.mean(attention_reps, dim=0)  # 形状: (embed_dim,)
    # 将组合后的向量输入分类器
    output = self.output_ff(composed_vector)  # 形状: (num_classes,)
    return output
    ```

![](img/1bffdc57c2785e5647c824db2af3396b_208.png)

![](img/1bffdc57c2785e5647c824db2af3396b_209.png)

![](img/1bffdc57c2785e5647c824db2af3396b_211.png)

![](img/1bffdc57c2785e5647c824db2af3396b_212.png)

![](img/1bffdc57c2785e5647c824db2af3396b_213.png)

![](img/1bffdc57c2785e5647c824db2af3396b_214.png)

![](img/1bffdc57c2785e5647c824db2af3396b_215.png)

**关于广播的说明**：在方法B中，`probs[:, None]` 将形状为 `(n,)` 的概率向量转换为形状为 `(n, 1)` 的列向量。当与形状为 `(n, embed_dim)` 的值矩阵 `V` 相乘时，PyTorch 会自动将概率向量广播到 `embed_dim` 列，实现每行元素与对应概率相乘，然后沿行方向求和得到加权平均。这是一种高效且常见的张量操作。

![](img/1bffdc57c2785e5647c824db2af3396b_217.png)

![](img/1bffdc57c2785e5647c824db2af3396b_219.png)

![](img/1bffdc57c2785e5647c824db2af3396b_221.png)

![](img/1bffdc57c2785e5647c824db2af3396b_223.png)

![](img/1bffdc57c2785e5647c824db2af3396b_224.png)

运行此代码，损失会下降，证明网络能够学习。然而，这种循环实现无法充分利用 GPU 的并行计算能力。

![](img/1bffdc57c2785e5647c824db2af3396b_226.png)

![](img/1bffdc57c2785e5647c824db2af3396b_227.png)

![](img/1bffdc57c2785e5647c824db2af3396b_228.png)

![](img/1bffdc57c2785e5647c824db2af3396b_229.png)

![](img/1bffdc57c2785e5647c824db2af3396b_230.png)

![](img/1bffdc57c2785e5647c824db2af3396b_231.png)

![](img/1bffdc57c2785e5647c824db2af3396b_233.png)

![](img/1bffdc57c2785e5647c824db2af3396b_234.png)

![](img/1bffdc57c2785e5647c824db2af3396b_236.png)

---

![](img/1bffdc57c2785e5647c824db2af3396b_238.png)

![](img/1bffdc57c2785e5647c824db2af3396b_240.png)

![](img/1bffdc57c2785e5647c824db2af3396b_242.png)

![](img/1bffdc57c2785e5647c824db2af3396b_243.png)

![](img/1bffdc57c2785e5647c824db2af3396b_245.png)

![](img/1bffdc57c2785e5647c824db2af3396b_246.png)

## ⚡ 方法二：高效向量化实现

![](img/1bffdc57c2785e5647c824db2af3396b_248.png)

![](img/1bffdc57c2785e5647c824db2af3396b_249.png)

![](img/1bffdc57c2785e5647c824db2af3396b_251.png)

![](img/1bffdc57c2785e5647c824db2af3396b_252.png)

![](img/1bffdc57c2785e5647c824db2af3396b_254.png)

Transformer 的核心优势在于其并行化能力。现在，我们来看如何去掉循环，实现高效的自注意力计算。

![](img/1bffdc57c2785e5647c824db2af3396b_256.png)

![](img/1bffdc57c2785e5647c824db2af3396b_257.png)

![](img/1bffdc57c2785e5647c824db2af3396b_258.png)

![](img/1bffdc57c2785e5647c824db2af3396b_259.png)

![](img/1bffdc57c2785e5647c824db2af3396b_261.png)

![](img/1bffdc57c2785e5647c824db2af3396b_263.png)

**核心思想**：将循环中的矩阵-向量乘法替换为单个矩阵-矩阵乘法。我们可以一次性计算所有查询与所有键的点积。

![](img/1bffdc57c2785e5647c824db2af3396b_265.png)

我们将在 `dot_product_attention` 函数中实现这个高效版本。该函数接收整个查询矩阵 `Q`、键矩阵 `K` 和值矩阵 `V`。

![](img/1bffdc57c2785e5647c824db2af3396b_267.png)

![](img/1bffdc57c2785e5647c824db2af3396b_268.png)

![](img/1bffdc57c2785e5647c824db2af3396b_269.png)

实现步骤如下：

![](img/1bffdc57c2785e5647c824db2af3396b_271.png)

![](img/1bffdc57c2785e5647c824db2af3396b_272.png)

![](img/1bffdc57c2785e5647c824db2af3396b_274.png)

![](img/1bffdc57c2785e5647c824db2af3396b_275.png)

![](img/1bffdc57c2785e5647c824db2af3396b_276.png)

![](img/1bffdc57c2785e5647c824db2af3396b_278.png)

![](img/1bffdc57c2785e5647c824db2af3396b_279.png)

![](img/1bffdc57c2785e5647c824db2af3396b_280.png)

1.  **计算注意力分数**：通过查询矩阵和键矩阵的转置进行矩阵乘法，一次性得到所有配对分数。
    ```python
    # Q: (n, d_k), K: (n, d_k), 我们想要分数矩阵 S: (n, n)
    # S[i, j] = Q[i] 和 K[j] 的点积
    scores = torch.mm(Q, K.t())  # 矩阵乘法，形状: (n, n)
    ```
    这行代码是关键，它高效地计算了所有查询-键对之间的点积。

![](img/1bffdc57c2785e5647c824db2af3396b_282.png)

2.  **应用 softmax**：对分数矩阵的每一行应用 softmax，将其转换为概率分布。
    ```python
    probs = torch.nn.functional.softmax(scores, dim=1)  # 形状: (n, n)
    # probs[i] 是第 i 个查询对所有键的注意力分布
    ```

![](img/1bffdc57c2785e5647c824db2af3396b_284.png)

![](img/1bffdc57c2785e5647c824db2af3396b_285.png)

![](img/1bffdc57c2785e5647c824db2af3396b_287.png)

![](img/1bffdc57c2785e5647c824db2af3396b_288.png)

![](img/1bffdc57c2785e5647c824db2af3396b_290.png)

![](img/1bffdc57c2785e5647c824db2af3396b_291.png)

![](img/1bffdc57c2785e5647c824db2af3396b_292.png)

![](img/1bffdc57c2785e5647c824db2af3396b_294.png)

3.  **计算加权和**：使用概率矩阵和值矩阵的矩阵乘法，一次性得到所有位置的输出。
    ```python
    # probs: (n, n), V: (n, d_v)
    # attention_outputs[i] = sum_j(probs[i, j] * V[j])
    attention_outputs = torch.mm(probs, V)  # 形状: (n, d_v)
    ```
    这个矩阵乘法等价于为每个查询位置并行计算其值向量的加权和。

![](img/1bffdc57c2785e5647c824db2af3396b_296.png)

![](img/1bffdc57c2785e5647c824db2af3396b_298.png)

![](img/1bffdc57c2785e5647c824db2af3396b_300.png)

![](img/1bffdc57c2785e5647c824db2af3396b_301.png)

![](img/1bffdc57c2785e5647c824db2af3396b_302.png)

![](img/1bffdc57c2785e5647c824db2af3396b_304.png)

![](img/1bffdc57c2785e5647c824db2af3396b_305.png)

4.  **在模型中使用**：在 `forward` 函数中，我们调用这个高效的注意力函数。
    ```python
    attention_reps = self.dot_product_attention(Q, K, V)  # 替换循环
    ```

![](img/1bffdc57c2785e5647c824db2af3396b_307.png)

![](img/1bffdc57c2785e5647c824db2af3396b_308.png)

![](img/1bffdc57c2785e5647c824db2af3396b_310.png)

![](img/1bffdc57c2785e5647c824db2af3396b_311.png)

![](img/1bffdc57c2785e5647c824db2af3396b_312.png)

![](img/1bffdc57c2785e5647c824db2af3396b_313.png)

通过对比两种方法输出的 `attention_reps`，可以验证它们是相同的，但向量化版本的速度要快得多。这种实现方式正是 Transformer 能够并行处理整个序列的基础。

![](img/1bffdc57c2785e5647c824db2af3396b_315.png)

![](img/1bffdc57c2785e5647c824db2af3396b_316.png)

![](img/1bffdc57c2785e5647c824db2af3396b_317.png)

![](img/1bffdc57c2785e5647c824db2af3396b_318.png)

![](img/1bffdc57c2785e5647c824db2af3396b_319.png)

![](img/1bffdc57c2785e5647c824db2af3396b_320.png)

![](img/1bffdc57c2785e5647c824db2af3396b_321.png)

![](img/1bffdc57c2785e5647c824db2af3396b_322.png)

![](img/1bffdc57c2785e5647c824db2af3396b_324.png)

---

![](img/1bffdc57c2785e5647c824db2af3396b_326.png)

![](img/1bffdc57c2785e5647c824db2af3396b_328.png)

![](img/1bffdc57c2785e5647c824db2af3396b_330.png)

## 🔄 过渡到文本生成与掩码自注意力

![](img/1bffdc57c2785e5647c824db2af3396b_332.png)

![](img/1bffdc57c2785e5647c824db2af3396b_334.png)

![](img/1bffdc57c2785e5647c824db2af3396b_336.png)

![](img/1bffdc57c2785e5647c824db2af3396b_338.png)

![](img/1bffdc57c2785e5647c824db2af3396b_339.png)

上一节我们介绍了在编码器或普通分类任务中高效计算自注意力的方法。本节中，我们将看看在文本生成任务的解码器中，如何实现**掩码自注意力**。

![](img/1bffdc57c2785e5647c824db2af3396b_341.png)

![](img/1bffdc57c2785e5647c824db2af3396b_343.png)

![](img/1bffdc57c2785e5647c824db2af3396b_344.png)

我们切换到第二个练习，任务是将一个字符序列（如 “A B B C C D D”）反向生成。这需要用到编码器-解码器架构，并且解码器的自注意力必须被掩码，以防止“偷看”未来信息。

![](img/1bffdc57c2785e5647c824db2af3396b_346.png)

![](img/1bffdc57c2785e5647c824db2af3396b_348.png)

![](img/1bffdc57c2785e5647c824db2af3396b_350.png)

![](img/1bffdc57c2785e5647c824db2af3396b_351.png)

![](img/1bffdc57c2785e5647c824db2af3396b_352.png)

![](img/1bffdc57c2785e5647c824db2af3396b_353.png)

数据准备中需要注意，对于生成任务，我们需要序列的开始符号 `<SOS>` 和结束符号 `<EOS>`。解码器的输入是目标序列向右移动一位（在开头加上 `<SOS>`），而解码器的目标是原始的目标序列。

![](img/1bffdc57c2785e5647c824db2af3396b_355.png)

![](img/1bffdc57c2785e5647c824db2af3396b_357.png)

![](img/1bffdc57c2785e5647c824db2af3396b_358.png)

---

![](img/1bffdc57c2785e5647c824db2af3396b_360.png)

![](img/1bffdc57c2785e5647c824db2af3396b_361.png)

![](img/1bffdc57c2785e5647c824db2af3396b_363.png)

![](img/1bffdc57c2785e5647c824db2af3396b_365.png)

![](img/1bffdc57c2785e5647c824db2af3396b_367.png)

![](img/1bffdc57c2785e5647c824db2af3396b_369.png)

## 🎭 解码器中的掩码自注意力

![](img/1bffdc57c2785e5647c824db2af3396b_371.png)

![](img/1bffdc57c2785e5647c824db2af3396b_373.png)

![](img/1bffdc57c2785e5647c824db2af3396b_374.png)

![](img/1bffdc57c2785e5647c824db2af3396b_375.png)

![](img/1bffdc57c2785e5647c824db2af3396b_376.png)

在解码器进行文本生成时，在时间步 `t`，模型只能依赖于时间步 `1` 到 `t` 的已知输出（即历史信息），而不能依赖于未来的时间步 `t+1, t+2, ...`。否则，训练时会“作弊”，模型可以直接看到要预测的答案。

![](img/1bffdc57c2785e5647c824db2af3396b_378.png)

![](img/1bffdc57c2785e5647c824db2af3396b_380.png)

![](img/1bffdc57c2785e5647c824db2af3396b_381.png)

因此，解码器的自注意力需要被掩码。我们首先用一种低效但清晰的方式实现。

![](img/1bffdc57c2785e5647c824db2af3396b_383.png)

![](img/1bffdc57c2785e5647c824db2af3396b_385.png)

![](img/1bffdc57c2785e5647c824db2af3396b_387.png)

![](img/1bffdc57c2785e5647c824db2af3396b_388.png)

**低效实现思路**：在解码的每个时间步 `i`，我们只使用截至当前步的键和值（`K[:i+1]` 和 `V[:i+1]`）来计算注意力。这意味着随着 `i` 增大，用于计算的键值对数量也增加。

![](img/1bffdc57c2785e5647c824db2af3396b_389.png)

![](img/1bffdc57c2785e5647c824db2af3396b_390.png)

![](img/1bffdc57c2785e5647c824db2af3396b_392.png)

![](img/1bffdc57c2785e5647c824db2af3396b_393.png)

![](img/1bffdc57c2785e5647c824db2af3396b_394.png)

```python
decoder_states = torch.zeros(n, hidden_dim)  # 存储每个解码器时间步的输出
for i in range(n):
    # 获取当前查询
    q_i = decoder_queries[i]  # 形状: (hidden_dim,)
    # 只使用当前步及之前的键和值
    prev_keys = decoder_keys[:i+1]    # 形状: (i+1, hidden_dim)
    prev_vals = decoder_values[:i+1]  # 形状: (i+1, hidden_dim)
    # 使用之前实现的“慢速注意力”函数计算当前步输出
    decoder_states[i] = self.do_slow_attention(q_i, prev_keys, prev_vals)
```

![](img/1bffdc57c2785e5647c824db2af3396b_396.png)

![](img/1bffdc57c2785e5647c824db2af3396b_398.png)

![](img/1bffdc57c2785e5647c824db2af3396b_400.png)

![](img/1bffdc57c2785e5647c824db2af3396b_401.png)

![](img/1bffdc57c2785e5647c824db2af3396b_402.png)

![](img/1bffdc57c2785e5647c824db2af3396b_404.png)

![](img/1bffdc57c2785e5647c824db2af3396b_405.png)

这种方法在循环中不断切片，无法并行化。

![](img/1bffdc57c2785e5647c824db2af3396b_407.png)

![](img/1bffdc57c2785e5647c824db2af3396b_408.png)

![](img/1bffdc57c2785e5647c824db2af3396b_409.png)

![](img/1bffdc57c2785e5647c824db2af3396b_411.png)

---

![](img/1bffdc57c2785e5647c824db2af3396b_413.png)

## 🚀 高效掩码自注意力实现

![](img/1bffdc57c2785e5647c824db2af3396b_415.png)

![](img/1bffdc57c2785e5647c824db2af3396b_417.png)

为了实现高效的并行计算，我们需要一次性计算所有时间步的注意力，但同时用一个掩码矩阵将未来时间步的信息屏蔽掉。

![](img/1bffdc57c2785e5647c824db2af3396b_419.png)

![](img/1bffdc57c2785e5647c824db2af3396b_420.png)

![](img/1bffdc57c2785e5647c824db2af3396b_422.png)

![](img/1bffdc57c2785e5647c824db2af3396b_424.png)

**核心思想**：我们仍然计算所有查询和所有键的点积矩阵（`n x n`），然后通过一个下三角掩码矩阵，将矩阵中上三角部分（代表未来信息）在 softmax 之前设置为一个非常大的负数（如 `-1e9`），这样经过 softmax 后，这些位置的权重就会接近零。

![](img/1bffdc57c2785e5647c824db2af3396b_426.png)

![](img/1bffdc57c2785e5647c824db2af3396b_427.png)

![](img/1bffdc57c2785e5647c824db2af3396b_428.png)

实现步骤如下：

![](img/1bffdc57c2785e5647c824db2af3396b_430.png)

1.  **创建掩码矩阵**：使用 `torch.tril` 生成一个下三角矩阵，下三角部分为1，上三角部分为0。
    ```python
    max_len = queries.size(0)
    # 创建一个下三角矩阵，对角线及以下为1，以上为0
    mask = torch.tril(torch.ones(max_len, max_len))  # 形状: (n, n)
    # mask[i, j] = 1 如果 j <= i (允许关注), 否则为 0 (屏蔽)
    ```

![](img/1bffdc57c2785e5647c824db2af3396b_432.png)

![](img/1bffdc57c2785e5647c824db2af3396b_434.png)

2.  **计算原始分数并应用掩码**：计算分数矩阵，然后将掩码为0的位置填充一个极小的值。
    ```python
    scores = torch.mm(queries, keys.t())  # 形状: (n, n)
    # 将掩码中为0的位置（未来信息）的分数设置为一个非常大的负数
    scores = scores.masked_fill(mask == 0, -1e9)
    ```
    在 softmax 之前进行掩码至关重要。如果在 softmax 之后才用0相乘，会破坏概率分布的总和为1的性质。

![](img/1bffdc57c2785e5647c824db2af3396b_436.png)

![](img/1bffdc57c2785e5647c824db2af3396b_438.png)

![](img/1bffdc57c2785e5647c824db2af3396b_440.png)

![](img/1bffdc57c2785e5647c824db2af3396b_442.png)

![](img/1bffdc57c2785e5647c824db2af3396b_443.png)

![](img/1bffdc57c2785e5647c824db2af3396b_445.png)

3.  **计算 softmax 和输出**：对掩码后的分数矩阵按行应用 softmax，然后与值矩阵相乘。
    ```python
    probs = torch.nn.functional.softmax(scores, dim=1)  # 形状: (n, n)
    # 此时，probs 中未来时间步对应的权重几乎为0
    attention_outputs = torch.mm(probs, values)  # 形状: (n, d_v)
    return attention_outputs
    ```

![](img/1bffdc57c2785e5647c824db2af3396b_447.png)

![](img/1bffdc57c2785e5647c824db2af3396b_449.png)

![](img/1bffdc57c2785e5647c824db2af3396b_450.png)

通过这种方式，我们实现了在训练时**并行计算整个解码器序列**的自注意力，同时严格遵守了自回归生成的性质。这是 Transformer 相比 RNN 在训练效率上的巨大优势。

![](img/1bffdc57c2785e5647c824db2af3396b_452.png)

![](img/1bffdc57c2785e5647c824db2af3396b_453.png)

![](img/1bffdc57c2785e5647c824db2af3396b_454.png)

![](img/1bffdc57c2785e5647c824db2af3396b_456.png)

![](img/1bffdc57c2785e5647c824db2af3396b_458.png)

![](img/1bffdc57c2785e5647c824db2af3396b_460.png)

![](img/1bffdc57c2785e5647c824db2af3396b_462.png)

![](img/1bffdc57c2785e5647c824db2af3396b_463.png)

![](img/1bffdc57c2785e5647c824db2af3396b_464.png)

---

![](img/1bffdc57c2785e5647c824db2af3396b_466.png)

![](img/1bffdc57c2785e5647c824db2af3396b_467.png)

![](img/1bffdc57c2785e5647c824db2af3396b_468.png)

![](img/1bffdc57c2785e5647c824db2af3396b_469.png)

![](img/1bffdc57c2785e5647c824db2af3396b_471.png)

![](img/1bffdc57c2785e5647c824db2af3396b_473.png)

![](img/1bffdc57c2785e5647c824db2af3396b_474.png)

![](img/1bffdc57c2785e5647c824db2af3396b_475.png)

![](img/1bffdc57c2785e5647c824db2af3396b_476.png)

## 📝 总结与扩展

![](img/1bffdc57c2785e5647c824db2af3396b_478.png)

![](img/1bffdc57c2785e5647c824db2af3396b_480.png)

![](img/1bffdc57c2785e5647c824db2af3396b_482.png)

![](img/1bffdc57c2785e5647c824db2af3396b_483.png)

![](img/1bffdc57c2785e5647c824db2af3396b_484.png)

本节课中，我们一起学习了 Transformer 模型的核心——自注意力机制的高效实现。

![](img/1bffdc57c2785e5647c824db2af3396b_486.png)

![](img/1bffdc57c2785e5647c824db2af3396b_488.png)

![](img/1bffdc57c2785e5647c824db2af3396b_490.png)

![](img/1bffdc57c2785e5647c824db2af3396b_492.png)

*   我们从最简单的**点积注意力**开始，理解了其计算过程。
*   我们首先用**循环实现**来明确每一步的计算逻辑，这种方法直观但效率低下。
*   然后，我们将其改进为**向量化实现**，利用矩阵乘法一次性计算所有注意力，这是 Transformer 并行化的基础。
*   最后，我们深入探讨了在**解码器**中必需的**掩码自注意力**，学会了如何通过下三角掩码矩阵在并行计算中屏蔽未来信息，并比较了高效与低效实现的性能差异。

![](img/1bffdc57c2785e5647c824db2af3396b_494.png)

![](img/1bffdc57c2785e5647c824db2af3396b_495.png)

要构建一个完整的 Transformer，你还需要在此基础上添加：
*   使编码器成为真正的多层自注意力网络。
*   实现**多头注意力**（可通过额外的投影和矩阵操作实现，无需循环）。
*   添加 Transformer 块中的**前馈神经网络**、**层归一化**、**残差连接**和**Dropout**等组件。

![](img/1bffdc57c2785e5647c824db2af3396b_497.png)

![](img/1bffdc57c2785e5647c824db2af3396b_498.png)

![](img/1bffdc57c2785e5647c824db2af3396b_499.png)

![](img/1bffdc57c2785e5647c824db2af3396b_500.png)

![](img/1bffdc57c2785e5647c824db2af3396b_501.png)

![](img/1bffdc57c2785e5647c824db2af3396b_502.png)

![](img/1bffdc57c2785e5647c824db2af3396b_503.png)

![](img/1bffdc57c2785e5647c824db2af3396b_505.png)

![](img/1bffdc57c2785e5647c824db2af3396b_506.png)

![](img/1bffdc57c2785e5647c824db2af3396b_508.png)

理解掩码自注意力在解码器中的工作原理及其高效实现方式，是掌握 Transformer 架构的关键。