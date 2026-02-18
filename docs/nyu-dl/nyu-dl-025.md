# 25：图卷积神经网络 (GCN) 实践教程 🧠

![](img/4e33b1d5559572f479b37419f9532505_1.png)

![](img/4e33b1d5559572f479b37419f9532505_3.png)

在本节课中，我们将学习图卷积神经网络 (GCN) 的核心概念，并将其与之前学过的自注意力机制联系起来。我们将通过一个具体的代码示例，学习如何实现一个门控图卷积网络 (Gated GCN) 来对不同类型的图结构进行分类。

---

## 概述

图卷积网络是处理图结构数据的一种强大神经网络架构。它利用图中节点之间的连接关系（邻接矩阵的稀疏性）来聚合信息，这与自注意力机制处理集合数据的思想有相似之处，但增加了结构先验。

上一节我们介绍了自注意力机制，本节中我们来看看如何将类似的思想应用于图结构数据。

## 从自注意力到图卷积

在自注意力中，我们有一组输入向量 \( X = \{x_1, x_2, ..., x_T\} \)。每个位置的隐藏表示 \( h_i \) 是所有输入向量的线性组合：

\[
h_i = \sum_{j=1}^{T} \alpha_{ij} x_j
\]

![](img/4e33b1d5559572f479b37419f9532505_5.png)

![](img/4e33b1d5559572f479b37419f9532505_7.png)

其中，系数 \( \alpha_{ij} \) 通过查询-键机制计算得出，并且通常满足 \( \sum_j \alpha_{ij} = 1 \)。这可以写成矩阵乘法形式 \( H = A X \)，其中 \( A \) 是注意力权重矩阵。

在图卷积网络中，我们同样有一组顶点（节点）\( V \)，每个顶点 \( v_i \) 有一个特征向量 \( x_i \)。关键区别在于，图中节点之间存在明确的连接关系，由邻接矩阵 \( A \) 定义。在基础的图卷积中，对于节点 \( v_i \)，其新的表示 \( h_i \) 是其所有邻居节点特征的聚合：

\[
h_i = \frac{1}{d_i} \sum_{j \in \mathcal{N}(i)} x_j
\]

这里，\( \mathcal{N}(i) \) 是节点 \( i \) 的邻居集合，\( d_i \) 是其度数（邻居数量）。这可以看作是注意力权重 \( \alpha_{ij} = 1/d_i \)（如果 \( j \) 是 \( i \) 的邻居）的一个特例。邻接矩阵 \( A \) 在这里充当了一个“硬”注意力机制，它预先定义了哪些节点之间应该交互。

为了引入可学习的参数并考虑节点自身特征，我们通常会加入自连接和线性变换：

\[
h_i = \sigma \left( W \cdot \left( \frac{1}{d_i} \sum_{j \in \mathcal{N}(i) \cup \{i\}} x_j \right) \right)
\]

其中 \( W \) 是可学习的权重矩阵，\( \sigma \) 是非线性激活函数。

## 门控图卷积网络 (Gated GCN)

![](img/4e33b1d5559572f479b37419f9532505_9.png)

我们将要实现的是一种更复杂的变体：残差门控图卷积网络。它不仅考虑节点特征，还考虑了边的特征，并使用一个门控机制来调制来自不同邻居的信息流。

![](img/4e33b1d5559572f479b37419f9532505_11.png)

![](img/4e33b1d5559572f479b37419f9532505_13.png)

以下是该模型的核心方程：

![](img/4e33b1d5559572f479b37419f9532505_15.png)

![](img/4e33b1d5559572f479b37419f9532505_17.png)

![](img/4e33b1d5559572f479b37419f9532505_19.png)

![](img/4e33b1d5559572f479b37419f9532505_21.png)

![](img/4e33b1d5559572f479b37419f9532505_23.png)

1.  **节点更新**：对于节点 \( v \)，其新表示 \( h_v \) 是自身特征和邻居特征的加权和。
    \[
    h_v = f\left( A x_v + \sum_{u \in \mathcal{N}(v)} \eta_{vu} \cdot B x_u \right)
    \]
    其中 \( A, B \) 是可学习的权重矩阵，\( f \) 是激活函数（如 ReLU），\( \eta_{vu} \) 是门控权重。

![](img/4e33b1d5559572f479b37419f9532505_25.png)

![](img/4e33b1d5559572f479b37419f9532505_27.png)

![](img/4e33b1d5559572f479b37419f9532505_29.png)

![](img/4e33b1d5559572f479b37419f9532505_31.png)

![](img/4e33b1d5559572f479b37419f9532505_33.png)

![](img/4e33b1d5559572f479b37419f9532505_35.png)

2.  **边表示与门控**：边 \( e_{vu} \) 的表示 \( e_{vu} \) 由其两端节点特征计算得出，并用于计算门控 \( \eta_{vu} \)。
    \[
    e_{vu} = C e_{vu}^{(input)} + D x_v + E x_u
    \]
    \[
    \eta_{vu} = \frac{\sigma(e_{vu})}{\sum_{k \in \mathcal{N}(v)} \sigma(e_{vk})}
    \]
    这里 \( C, D, E \) 是可学习的权重矩阵，\( \sigma \) 是 sigmoid 函数。门控 \( \eta_{vu} \) 是一个归一化的权重，决定了来自邻居 \( u \) 的信息对节点 \( v \) 的重要性。

![](img/4e33b1d5559572f479b37419f9532505_37.png)

![](img/4e33b1d5559572f479b37419f9532505_39.png)

![](img/4e33b1d5559572f479b37419f9532505_41.png)

![](img/4e33b1d5559572f479b37419f9532505_43.png)

3.  **边更新**：边的表示也会随着网络层数更新，通常包含一个残差连接。
    \[
    e_{vu}^{(new)} = e_{vu}^{(input)} + \text{ReLU}(e_{vu})
    \]

![](img/4e33b1d5559572f479b37419f9532505_45.png)

![](img/4e33b1d5559572f479b37419f9532505_47.png)

![](img/4e33b1d5559572f479b37419f9532505_49.png)

4.  **残差连接**：为了防止梯度消失和网络退化，通常在节点和边的更新中加入残差连接。
    \[
    h_v^{(l+1)} = h_v^{(l)} + \text{ReLU}(\text{LayerNorm}(h_v^{(new)}))
    \]

## 代码实践：图分类任务

![](img/4e33b1d5559572f479b37419f9532505_51.png)

现在，让我们通过代码来具体实现一个门控 GCN，并用于一个图分类任务。我们将使用 DGL (Deep Graph Library) 和 PyTorch。

### 1. 环境设置与数据准备

首先，我们导入必要的库并创建一个迷你图分类数据集。

![](img/4e33b1d5559572f479b37419f9532505_53.png)

![](img/4e33b1d5559572f479b37419f9532505_55.png)

![](img/4e33b1d5559572f479b37419f9532505_57.png)

![](img/4e33b1d5559572f479b37419f9532505_59.png)

```python
import os
os.environ['DGLBACKEND'] = 'pytorch'
import dgl
import torch
import torch.nn as nn
import torch.nn.functional as F
import networkx as nx
import matplotlib.pyplot as plt

![](img/4e33b1d5559572f479b37419f9532505_61.png)

![](img/4e33b1d5559572f479b37419f9532505_63.png)

![](img/4e33b1d5559572f479b37419f9532505_65.png)

![](img/4e33b1d5559572f479b37419f9532505_67.png)

# 创建一个迷你图分类数据集
from dgl.data import MiniGCDataset
dataset = MiniGCDataset(num_graphs=100, min_num_v=10, max_num_v=20)
```

![](img/4e33b1d5559572f479b37419f9532505_69.png)

![](img/4e33b1d5559572f479b37419f9532505_71.png)

这个数据集包含多种图结构（如环形、星形、车轮形等），我们的任务是训练一个模型来区分这些图类型。

![](img/4e33b1d5559572f479b37419f9532505_73.png)

![](img/4e33b1d5559572f479b37419f9532505_75.png)

### 2. 定义 Gated GCN 层

以下是 Gated GCN 层的 PyTorch 模块实现。

![](img/4e33b1d5559572f479b37419f9532505_77.png)

![](img/4e33b1d5559572f479b37419f9532505_79.png)

![](img/4e33b1d5559572f479b37419f9532505_81.png)

```python
class GatedGCNLayer(nn.Module):
    def __init__(self, input_dim, output_dim):
        super().__init__()
        self.A = nn.Linear(input_dim, output_dim) # 用于自身节点变换
        self.B = nn.Linear(input_dim, output_dim) # 用于邻居节点变换
        self.C = nn.Linear(input_dim, output_dim) # 用于边变换
        self.D = nn.Linear(input_dim, output_dim) # 用于边计算中的源节点
        self.E = nn.Linear(input_dim, output_dim) # 用于边计算中的目标节点
        self.bn_node = nn.BatchNorm1d(output_dim)
        self.bn_edge = nn.BatchNorm1d(output_dim)

    def message_func(self, edges):
        # 计算边的表示 ej
        Bj = self.B(edges.src['h']) # B * x_j
        e = self.C(edges.data['e']) + self.D(edges.dst['h']) + self.E(edges.src['h'])
        # 存储边的表示用于后续门控计算
        edges.data['e'] = e
        return {'Bj': Bj, 'e': e}

    def reduce_func(self, nodes):
        # 聚合所有传入的消息
        Ax = self.A(nodes.data['h']) # A * x_i
        Bj = nodes.mailbox['Bj'] # 来自各邻居的 B*x_j
        e = nodes.mailbox['e']   # 来自各边的表示

        # 计算门控权重 eta (sigma(e) / sum(sigma(e)))
        sigma = torch.sigmoid(e)
        sum_sigma = torch.sum(sigma, dim=1, keepdim=True)
        eta = sigma / (sum_sigma + 1e-6)

        # 用门控权重加权邻居信息
        weighted_Bj = eta * Bj
        h = Ax + torch.sum(weighted_Bj, dim=1)

        # 应用批归一化和非线性激活
        h = F.relu(self.bn_node(h))
        e = F.relu(self.bn_edge(e.view(-1, e.size(-1)))).view(e.size())

        return {'h': h, 'e_agg': e}

    def forward(self, g, h, e):
        with g.local_scope():
            g.ndata['h'] = h
            g.edata['e'] = e
            # 消息传递与聚合
            g.update_all(self.message_func, self.reduce_func)
            h = g.ndata['h']
            e = g.edata['e_agg'].view(e.shape) # 获取更新后的边表示
            # 残差连接
            h = h + F.relu(self.bn_node(self.A(h)))
            e = e + F.relu(self.bn_edge(self.C(e)))
            return h, e
```

![](img/4e33b1d5559572f479b37419f9532505_83.png)

### 3. 构建完整的 Gated GCN 模型

我们将堆叠多个 Gated GCN 层，并在最后使用一个多层感知机 (MLP) 对整个图进行分类。

![](img/4e33b1d5559572f479b37419f9532505_85.png)

![](img/4e33b1d5559572f479b37419f9532505_87.png)

![](img/4e33b1d5559572f479b37419f9532505_89.png)

```python
class GatedGCN(nn.Module):
    def __init__(self, input_dim, hidden_dim, output_dim, num_layers):
        super().__init__()
        self.embed = nn.Linear(input_dim, hidden_dim)
        self.layers = nn.ModuleList([
            GatedGCNLayer(hidden_dim, hidden_dim) for _ in range(num_layers)
        ])
        # 读出函数：对所有节点特征取平均，然后通过MLP得到图级别表示
        self.readout = nn.Sequential(
            nn.Linear(hidden_dim, hidden_dim),
            nn.ReLU(),
            nn.Linear(hidden_dim, output_dim)
        )

    def forward(self, g, h, e):
        h = self.embed(h)
        for layer in self.layers:
            h, e = layer(g, h, e)
        with g.local_scope():
            g.ndata['h'] = h
            # 图读出：平均所有节点特征
            hg = dgl.mean_nodes(g, 'h')
            return self.readout(hg)
```

![](img/4e33b1d5559572f479b37419f9532505_91.png)

![](img/4e33b1d5559572f479b37419f9532505_93.png)

![](img/4e33b1d5559572f479b37419f9532505_95.png)

### 4. 训练与评估循环

![](img/4e33b1d5559572f479b37419f9532505_97.png)

![](img/4e33b1d5559572f479b37419f9532505_99.png)

以下是标准的训练和评估函数。

```python
def train(model, optimizer, g, h, e, labels):
    model.train()
    logits = model(g, h, e)
    loss = F.cross_entropy(logits, labels)
    optimizer.zero_grad()
    loss.backward()
    optimizer.step()
    return loss.item()

def evaluate(model, g, h, e, labels):
    model.eval()
    with torch.no_grad():
        logits = model(g, h, e)
        _, predicted = torch.max(logits, 1)
        correct = (predicted == labels).sum().item()
        return correct / labels.size(0)

![](img/4e33b1d5559572f479b37419f9532505_101.png)

![](img/4e33b1d5559572f479b37419f9532505_103.png)

![](img/4e33b1d5559572f479b37419f9532505_105.png)

![](img/4e33b1d5559572f479b37419f9532505_107.png)

![](img/4e33b1d5559572f479b37419f9532505_109.png)

# 初始化模型、优化器
model = GatedGCN(input_dim=1, hidden_dim=64, output_dim=8, num_layers=3)
optimizer = torch.optim.Adam(model.parameters(), lr=0.001)

![](img/4e33b1d5559572f479b37419f9532505_111.png)

![](img/4e33b1d5559572f479b37419f9532505_113.png)

![](img/4e33b1d5559572f479b37419f9532505_115.png)

![](img/4e33b1d5559572f479b37419f9532505_117.png)

# 假设 dataloader 能提供批处理后的图数据 (batched_graph), 节点特征 h, 边特征 e, 标签 labels
for epoch in range(50):
    total_loss = 0
    for batched_graph, h, e, labels in train_dataloader:
        loss = train(model, optimizer, batched_graph, h, e, labels)
        total_loss += loss
    train_acc = evaluate(model, ...) # 在训练集上评估
    test_acc = evaluate(model, ...)  # 在测试集上评估
    print(f'Epoch {epoch}, Loss: {total_loss:.4f}, Train Acc: {train_acc:.4f}, Test Acc: {test_acc:.4f}')
```

![](img/4e33b1d5559572f479b37419f9532505_119.png)

![](img/4e33b1d5559572f479b37419f9532505_121.png)

![](img/4e33b1d5559572f479b37419f9532505_123.png)

![](img/4e33b1d5559572f479b37419f9532505_125.png)

## 核心概念总结

![](img/4e33b1d5559572f479b37419f9532505_127.png)

本节课中我们一起学习了：

1.  **图卷积网络 (GCN) 的本质**：它是一种利用图结构稀疏性（邻接矩阵）的神经网络，通过对邻居节点特征进行聚合来更新节点表示。可以看作是具有**预定义稀疏注意力模式**的自注意力机制。
2.  **与自注意力的联系与区别**：
    *   **联系**：两者都通过对一组输入元素（节点/词元）进行加权聚合来计算新的表示。
    *   **区别**：自注意力的注意力权重 \( A \) 是通过数据动态计算（如 `softmax(QK^T)`）的完全矩阵。而 GCN 中的“注意力”权重由**给定的图结构（邻接矩阵 \( A \)）** 预先定义，通常是二元的或简单的归一化形式（如 \( D^{-1}A \)）。GCN 利用了**领域特定的稀疏性先验**。
3.  **门控图卷积网络 (Gated GCN)**：一种高级变体，它引入了**边特征**和一个**可学习的门控机制**。门控权重由边的表示计算，用于调制来自不同邻居的信息流，使得模型能够更灵活地决定哪些邻居信息更重要。
4.  **实践应用**：我们实现了一个 Gated GCN 模型，用于**图分类任务**。该任务要求模型根据图的整体结构（即节点之间的连接方式）来判断其所属类别。代码展示了如何使用 DGL 库定义消息传递函数、实现节点与边的更新，以及如何构建包含残差连接和批归一化的完整网络。

![](img/4e33b1d5559572f479b37419f9532505_129.png)

通过本课程，你应该理解了图神经网络的基本思想，并能够将其与熟悉的序列模型（如 Transformer）进行类比，同时也掌握了使用现代图深度学习库进行开发的基本流程。