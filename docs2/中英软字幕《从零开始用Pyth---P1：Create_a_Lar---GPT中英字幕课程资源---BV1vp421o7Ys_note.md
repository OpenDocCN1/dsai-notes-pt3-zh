# 大型语言模型从零开始：P1：使用Python创建大型语言模型 – 教程 🚀

![](img/6087c536d5acae0212b4dab7c9b2ea09_1.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_3.png)

## 概述

![](img/6087c536d5acae0212b4dab7c9b2ea09_5.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_7.png)

在本节课中，我们将学习如何从零开始，使用Python构建一个大型语言模型。我们将深入探讨数据处理、数学原理以及Transformer架构的核心概念。本课程旨在让初学者能够理解并实践，我们将从最基础的概念开始，逐步构建一个功能完整的语言模型。

![](img/6087c536d5acae0212b4dab7c9b2ea09_9.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_11.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_13.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_15.png)

---

![](img/6087c536d5acae0212b4dab7c9b2ea09_17.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_19.png)

## 课程简介

Elliot Arledge创建了这门课程，旨在帮助你深刻理解大型语言模型的工作原理及其在各种应用中的使用方式。

本课程将从零开始建立，不假设你有任何微积分或线性代数的经验。我们将采取循序渐进的步骤，确保每个新概念都清晰易懂。一旦基础概念变得清晰，我们将迈出更大的步伐，以高效地推进学习。

本课程受到Andrej Karpathy关于从零开始构建GPT的讲座的启发。我们假设你有一些Python基础，但最重要的是你愿意投入时间。由于课程内容涉及的材料通常不常见，持续的努力和坚持是关键。

课程将完全在本地计算环境中进行，无需付费数据集或云计算服务。我们将处理大约45GB的训练数据集。代码支持Mac OS和Windows操作系统。

![](img/6087c536d5acae0212b4dab7c9b2ea09_21.png)

---

## 环境设置与项目初始化

上一节我们介绍了课程的整体目标，本节中我们来看看如何设置开发环境并初始化项目。

为了逐步开发项目，我们将使用Jupyter Notebooks。Anaconda提示符非常适合任何与机器学习相关的工作，请确保已安装它。

首先，我们需要创建项目目录和虚拟环境。虚拟环境的作用是将项目的依赖项与系统全局库隔离开来。

以下是设置步骤：

1.  创建项目目录。
2.  创建并激活名为`cuda`的虚拟环境。
3.  在虚拟环境中安装必要的库，包括`matplotlib`、`numpy`、`pylzma`、`ipy kernel`和`jupyter`。
4.  安装支持CUDA的PyTorch，以便利用GPU加速训练过程。
5.  检查Python版本，确保在3.9到3.11之间。
6.  启动Jupyter Notebook，并确保我们的虚拟环境`cuda`可以作为内核使用。

完成这些步骤后，我们的开发环境就准备就绪了。

---

![](img/6087c536d5acae0212b4dab7c9b2ea09_23.png)

## 数据处理与基础概念

![](img/6087c536d5acae0212b4dab7c9b2ea09_25.png)

上一节我们完成了环境设置，本节中我们来看看如何处理数据并理解语言模型的一些基础概念。

我们将使用《绿野仙踪》的文本作为一个小型数据集来构建一个二元语言模型。首先，我们需要读取文本文件，并查看其基本属性。

```python
with open(‘wizard_of_oz.txt‘, ‘r‘, encoding=‘utf-8‘) as f:
    text = f.read()
print(len(text))
print(text[:200])
```

接下来，我们需要创建一个词汇表，即文本中所有唯一字符的集合。然后，我们将构建一个分词器，它由编码器和解码器组成，用于将字符转换为整数（编码），以及将整数转换回字符（解码）。

```python
chars = sorted(list(set(text)))
vocab_size = len(chars)
print(‘Vocabulary:‘, ‘‘.join(chars))
print(‘Vocabulary size:‘, vocab_size)

# 创建字符到整数和整数到字符的映射
stoi = {ch:i for i,ch in enumerate(chars)}
itos = {i:ch for i,ch in enumerate(chars)}
encode = lambda s: [stoi[c] for c in s] # 编码器
decode = lambda l: ‘‘.join([itos[i] for i in l]) # 解码器
```

在语言模型的背景下，高效处理数据非常重要。我们将使用PyTorch框架，它可以帮助我们处理大量的数学运算和线性代数操作。我们将所有数据放入张量中，以便PyTorch更容易处理。

```python
import torch
data = torch.tensor(encode(text), dtype=torch.long)
print(data.shape, data.dtype)
print(data[:100])
```

![](img/6087c536d5acae0212b4dab7c9b2ea09_27.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_29.png)

---

## 训练集与验证集拆分

上一节我们介绍了如何编码文本数据，本节中我们来看看为什么需要将数据拆分为训练集和验证集。

如果我们使用整个文本文档进行训练，模型可能会简单地记住整个文本，而无法生成新的、类似训练数据的文本。语言建模的目的是生成类似训练数据的文本，而不是精确复制。

因此，我们将数据分为训练集和验证集。通常，我们使用80%的数据作为训练集，20%作为验证集。训练集用于训练模型，验证集用于评估模型在未见过的数据上的表现，确保生成的文本是独特的，而不是原始文档的精确副本。

---

## 二元语言模型原理

上一节我们讨论了数据拆分，本节中我们来看看什么是二元语言模型及其工作原理。

“二元”前缀意味着“两个”。在二元语言模型中，我们只考虑前一个字符来预测下一个字符。例如，对于单词“hello”，模型会基于‘h‘预测‘e‘，基于‘e‘预测‘l‘，依此类推。

为了训练二元语言模型，我们需要从文本中提取小的数据块。我们定义一个`块大小`，它表示每个数据块的长度。对于每个数据块，我们将其作为输入（预测），并将其向右偏移一个位置作为目标。

![](img/6087c536d5acae0212b4dab7c9b2ea09_31.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_32.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_33.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_34.png)

```python
block_size = 8 # 每个数据块的长度
x = data[:block_size] # 输入
y = data[1:block_size+1] # 目标（偏移一位）
for t in range(block_size):
    context = x[:t+1]
    target = y[t]
    print(f“When input is {context}, the target is {target}“)
```

![](img/6087c536d5acae0212b4dab7c9b2ea09_36.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_38.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_40.png)

为了加速训练过程，我们可以并行处理多个这样的数据块。我们引入`批量大小`这个超参数，它表示我们同时处理的数据块数量。通过将多个数据块堆叠在一起，我们可以利用GPU进行并行计算，从而大幅扩展训练效率。

![](img/6087c536d5acae0212b4dab7c9b2ea09_42.png)

```python
batch_size = 4 # 同时处理的数据块数量
def get_batch(split):
    # 从训练集或验证集中随机获取一批数据
    data = train_data if split == ‘train‘ else val_data
    ix = torch.randint(len(data) - block_size, (batch_size,))
    x = torch.stack([data[i:i+block_size] for i in ix])
    y = torch.stack([data[i+1:i+block_size+1] for i in ix])
    x, y = x.to(device), y.to(device)
    return x, y
```

---

![](img/6087c536d5acae0212b4dab7c9b2ea09_44.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_46.png)

## PyTorch基础与GPU加速

上一节我们介绍了批次处理的概念，本节中我们来看看一些PyTorch基础操作以及为什么GPU对训练如此重要。

PyTorch的核心数据结构是张量，我们可以将其视为多维数组。以下是一些基本的张量操作：

```python
import torch
# 创建随机整数张量
rand_ints = torch.randint(-100, 100, (6,))
# 创建特定值的张量
tensor = torch.tensor([[0.1, 1.2], [2.2, 3.1], [4.9, 5.2]])
# 创建全零张量
zeros = torch.zeros((2, 3))
# 创建全一张量
ones = torch.ones((3, 4))
# 创建范围张量
range_tensor = torch.arange(5)
# 创建线性间隔张量
linspace = torch.linspace(3, 10, steps=5)
# 创建对数间隔张量
logspace = torch.logspace(start=-10, end=10, steps=5)
# 创建单位矩阵
identity = torch.eye(5)
```

GPU可以并行执行大量简单的计算任务，而CPU则是顺序执行复杂任务。在语言模型中，我们涉及大量的矩阵乘法等简单但数量巨大的运算，因此GPU可以显著加速训练过程。

我们可以通过以下代码比较GPU和CPU的执行时间：

```python
import torch
import time

# 检查GPU是否可用
device = ‘cuda‘ if torch.cuda.is_available() else ‘cpu‘
print(f“Using device: {device}“)

# 创建两个大矩阵
size = 10000
a_cpu = torch.randn(size, size)
b_cpu = torch.randn(size, size)
a_gpu = a_cpu.to(device)
b_gpu = b_cpu.to(device)

# 在CPU上计时
start = time.time()
c_cpu = a_cpu @ b_cpu
cpu_time = time.time() - start

![](img/6087c536d5acae0212b4dab7c9b2ea09_48.png)

# 在GPU上计时
start = time.time()
c_gpu = a_gpu @ b_gpu
torch.cuda.synchronize() # 等待GPU操作完成
gpu_time = time.time() - start

![](img/6087c536d5acae0212b4dab7c9b2ea09_50.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_52.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_54.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_56.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_58.png)

print(f“CPU time: {cpu_time:.2f}s“)
print(f“GPU time: {gpu_time:.2f}s“)
print(f“Speedup: {cpu_time/gpu_time:.2f}x“)
```

![](img/6087c536d5acae0212b4dab7c9b2ea09_60.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_62.png)

---

![](img/6087c536d5acae0212b4dab7c9b2ea09_64.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_66.png)

## 关键PyTorch函数与概念

![](img/6087c536d5acae0212b4dab7c9b2ea09_68.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_70.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_72.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_74.png)

上一节我们对比了GPU与CPU的性能，本节中我们来看看构建语言模型所需的一些关键PyTorch函数和概念。

![](img/6087c536d5acae0212b4dab7c9b2ea09_76.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_78.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_79.png)

以下是几个重要的函数：

![](img/6087c536d5acae0212b4dab7c9b2ea09_81.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_83.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_85.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_87.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_89.png)

1.  **`torch.multinomial`**：基于概率分布进行采样。
    ```python
    probs = torch.tensor([0.1, 0.9])
    samples = torch.multinomial(probs, num_samples=10, replacement=True)
    ```
2.  **`torch.cat`**：连接张量。
    ```python
    a = torch.tensor([1, 2, 3, 4])
    b = torch.tensor([5])
    c = torch.cat((a, b))
    ```
3.  **`torch.tril`**：生成下三角矩阵，用于在注意力机制中屏蔽未来信息。
    ```python
    mask = torch.tril(torch.ones(3, 3))
    ```
4.  **`torch.softmax`**：将输入转换为概率分布。
    ```python
    import torch.nn.functional as F
    x = torch.tensor([1.0, 2.0, 3.0])
    probs = F.softmax(x, dim=0)
    ```
5.  **`torch.transpose`**：转置张量的维度。
    ```python
    x = torch.zeros(2, 3, 4)
    y = torch.transpose(x, 0, 2) # 形状变为 (4, 3, 2)
    ```
6.  **`torch.stack`**：堆叠张量以创建新维度，用于创建批次。
    ```python
    a = torch.tensor([1, 2, 3])
    b = torch.tensor([4, 5, 6])
    stacked = torch.stack([a, b]) # 形状为 (2, 3)
    ```
7.  **`nn.Linear`**：线性变换层，包含可学习的权重和偏置。
    ```python
    import torch.nn as nn
    linear_layer = nn.Linear(in_features=10, out_features=5)
    ```
8.  **`nn.Embedding`**：嵌入层，将离散的标记索引映射为密集的向量表示。
    ```python
    embedding_layer = nn.Embedding(num_embeddings=1000, embedding_dim=50)
    ```

![](img/6087c536d5acae0212b4dab7c9b2ea09_91.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_93.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_95.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_97.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_99.png)

**嵌入**是语言模型中的核心概念。它将每个字符（或单词）表示为一个向量，这个向量包含了关于该字符的语义信息。这些向量是可学习的参数，模型在训练过程中会调整它们。

**矩阵乘法**是神经网络中的基础操作。两个矩阵可以相乘的条件是第一个矩阵的列数等于第二个矩阵的行数。结果矩阵的行数等于第一个矩阵的行数，列数等于第二个矩阵的列数。

```python
# 矩阵 A 形状为 (3, 2)
A = torch.tensor([[1, 2], [3, 4], [5, 6]])
# 矩阵 B 形状为 (2, 3)
B = torch.tensor([[7, 8, 9], [10, 11, 12]])
# 矩阵乘法 C = A @ B，形状为 (3, 3)
C = A @ B
```

![](img/6087c536d5acae0212b4dab7c9b2ea09_101.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_103.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_105.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_107.png)

---

![](img/6087c536d5acae0212b4dab7c9b2ea09_109.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_111.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_113.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_115.png)

## 构建二元语言模型

![](img/6087c536d5acae0212b4dab7c9b2ea09_117.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_119.png)

上一节我们介绍了关键的函数和概念，本节中我们开始实际构建一个二元语言模型。

首先，我们定义一个简单的二元语言模型类。它本质上是一个查找表，对于词汇表中的每个字符，它预测下一个字符的概率分布。

![](img/6087c536d5acae0212b4dab7c9b2ea09_121.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_123.png)

```python
import torch
import torch.nn as nn
from torch.nn import functional as F

![](img/6087c536d5acae0212b4dab7c9b2ea09_125.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_127.png)

class BigramLanguageModel(nn.Module):
    def __init__(self, vocab_size):
        super().__init__()
        # 每个标记直接映射到下一个标记的概率分布
        self.token_embedding_table = nn.Embedding(vocab_size, vocab_size)

    def forward(self, idx, targets=None):
        # idx 和 targets 都是形状为 (B, T) 的整数张量
        logits = self.token_embedding_table(idx) # (B, T, C)

        if targets is None:
            loss = None
        else:
            B, T, C = logits.shape
            logits = logits.view(B*T, C)
            targets = targets.view(B*T)
            loss = F.cross_entropy(logits, targets)

        return logits, loss

    def generate(self, idx, max_new_tokens):
        # idx 是当前上下文，形状为 (B, T)
        for _ in range(max_new_tokens):
            # 获取预测
            logits, loss = self(idx)
            # 只关注最后一个时间步
            logits = logits[:, -1, :] # (B, C)
            # 应用softmax获取概率
            probs = F.softmax(logits, dim=-1) # (B, C)
            # 从分布中采样
            idx_next = torch.multinomial(probs, num_samples=1) # (B, 1)
            # 将采样到的索引附加到序列中
            idx = torch.cat((idx, idx_next), dim=1) # (B, T+1)
        return idx
```

接下来，我们设置优化器和训练循环。优化器（如AdamW）根据损失函数的梯度更新模型参数，以最小化损失。

![](img/6087c536d5acae0212b4dab7c9b2ea09_129.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_131.png)

```python
model = BigramLanguageModel(vocab_size)
model = model.to(device)

![](img/6087c536d5acae0212b4dab7c9b2ea09_133.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_135.png)

# 创建优化器
optimizer = torch.optim.AdamW(model.parameters(), lr=1e-3)

![](img/6087c536d5acae0212b4dab7c9b2ea09_137.png)

batch_size = 32
for steps in range(10000):
    # 获取一小批数据
    xb, yb = get_batch(‘train‘)

    # 评估损失
    logits, loss = model(xb, yb)
    optimizer.zero_grad(set_to_none=True)
    loss.backward()
    optimizer.step()

![](img/6087c536d5acae0212b4dab7c9b2ea09_139.png)

print(loss.item())
```

![](img/6087c536d5acae0212b4dab7c9b2ea09_141.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_143.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_145.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_147.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_149.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_151.png)

为了监控训练过程，我们可以定期估算并打印训练集和验证集上的损失。

```python
@torch.no_grad()
def estimate_loss():
    out = {}
    model.eval()
    for split in [‘train‘, ‘val‘]:
        losses = torch.zeros(eval_iters)
        for k in range(eval_iters):
            X, Y = get_batch(split)
            logits, loss = model(X, Y)
            losses[k] = loss.item()
        out[split] = losses.mean()
    model.train()
    return out

# 在训练循环中
for steps in range(max_iters):
    # ... 训练步骤 ...
    if steps % eval_interval == 0:
        losses = estimate_loss()
        print(f“Step {steps}: train loss {losses[‘train‘]:.4f}, val loss {losses[‘val‘]:.4f}“)
```

![](img/6087c536d5acae0212b4dab7c9b2ea09_153.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_155.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_157.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_159.png)

---

## 从二元模型到Transformer/GPT架构

![](img/6087c536d5acae0212b4dab7c9b2ea09_161.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_163.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_165.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_167.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_169.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_171.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_173.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_175.png)

上一节我们构建并训练了一个简单的二元模型，本节中我们将探讨更强大的Transformer架构，并着手构建一个GPT模型。

Transformer模型使用了一种称为**自注意力**的机制，它允许模型在处理一个标记时，关注输入序列中的所有其他标记，从而更好地理解上下文。

一个完整的Transformer包含编码器和解码器。然而，像GPT这样的模型只使用了解码器堆栈。每个解码器块主要由两部分组成：
1.  **多头自注意力机制**：多个“注意力头”并行工作，从不同角度学习序列中标记之间的关系。
2.  **前馈神经网络**：一个简单的全连接网络，对每个位置的特征进行独立变换。

此外，每个子层（自注意力和前馈网络）周围都使用了**残差连接**和**层归一化**，这有助于训练非常深的网络。

![](img/6087c536d5acae0212b4dab7c9b2ea09_177.png)

**缩放点积注意力**是自注意力的核心。其公式为：
\[ \text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right) V \]
其中，\( Q \) (查询)、\( K \) (键)、\( V \) (值) 都是输入线性变换后的产物。缩放因子 \( \sqrt{d_k} \) 用于防止点积结果过大导致梯度消失。

![](img/6087c536d5acae0212b4dab7c9b2ea09_179.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_181.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_183.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_185.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_187.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_189.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_191.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_193.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_195.png)

在GPT的解码器中，我们使用**掩码自注意力**，确保在预测某个位置时，只能看到它之前的标记，而不能看到未来的标记。这是通过一个下三角掩码矩阵实现的。

![](img/6087c536d5acae0212b4dab7c9b2ea09_197.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_199.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_200.png)

---

## 构建GPT模型

![](img/6087c536d5acae0212b4dab7c9b2ea09_202.png)

上一节我们介绍了Transformer/GPT的架构原理，本节中我们开始用代码实现一个GPT模型。

![](img/6087c536d5acae0212b4dab7c9b2ea09_204.png)

我们将逐步构建以下组件：
1.  **GPT语言模型**：顶层类，包含标记嵌入、位置嵌入和解码器块堆栈。
2.  **解码器块**：包含多头注意力、前馈网络、层归一化和残差连接。
3.  **多头注意力**：并行运行多个注意力头并将结果连接。
4.  **注意力头**：实现缩放点积注意力机制。

![](img/6087c536d5acae0212b4dab7c9b2ea09_206.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_208.png)

以下是GPT模型的主要代码结构概览：

![](img/6087c536d5acae0212b4dab7c9b2ea09_210.png)

```python
import torch
import torch.nn as nn
from torch.nn import functional as F

![](img/6087c536d5acae0212b4dab7c9b2ea09_212.png)

![](img/6087c536d5acae0212b4dab7c9b2ea09_214.png)

class GPTLanguageModel(nn.Module):
    def __init__(self, vocab_size, block_size, n_embed, n_head, n_layer, dropout):
        super().__init__()
        self.block_size = block_size
        # 标记嵌入和位置嵌入
        self.token_embedding_table = nn.Embedding(vocab_size, n_embed)
        self.position_embedding_table = nn.Embedding(block_size, n_embed)
        # 解码器块堆栈
        self.blocks = nn.Sequential(*[Block(n_embed, n_head, dropout) for _ in range(n_layer)])
        # 最终的层归一化和线性投影层
        self.ln_f = nn.LayerNorm(n_embed)
        self.lm_head = nn.Linear(n_embed, vocab_size)
        # ... 权重初始化 ...

    def forward(self, idx, targets=None):
        B, T =