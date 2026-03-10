# 015：批处理与图神经网络采样方法 🧠

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_0.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_2.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_3.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_5.png)

在本节课中，我们将学习如何将基于批次的训练方法应用于图神经网络。我们将探讨在单个大图上进行训练时面临的挑战，并介绍几种关键的采样策略，以高效地构建训练批次，从而加速训练并降低内存消耗。

---

## 从单点训练到批次训练

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_7.png)

上一节我们介绍了图神经网络的基本训练流程。本节中我们来看看，如何将传统的随机梯度下降和迷你批次梯度下降方法应用到图神经网络中。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_9.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_11.png)

在随机梯度下降中，我们为每个数据点（节点）单独计算损失梯度并更新网络参数。在图神经网络中，要更新一个节点在第 `k` 层的嵌入 `H_i^(k)`，我们需要聚合其邻居节点的信息。这个过程是递归的：要计算第 `k` 层的嵌入，需要第 `k-1` 层其邻居的嵌入，而计算第 `k-1` 层的嵌入又需要第 `k-2` 层其邻居的嵌入，依此类推。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_13.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_15.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_17.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_19.png)

因此，更新单个节点 `i` 的嵌入，实际上需要访问一个由该节点的 `k` 跳邻居构成的**计算子图**。这个子图被称为该节点的**感受野**。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_21.png)

**公式表示**：对于 `L` 层 GNN，节点 `i` 的感受野是其 `L` 跳内的所有邻居节点集合。

如果对图中的每个节点都独立进行这种计算，会产生大量冗余，因为相邻节点的感受野会有很大重叠。这导致计算效率低下。

---

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_23.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_24.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_26.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_28.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_30.png)

## 随机节点采样与迷你批次

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_31.png)

为了解决单点训练的冗余问题，一个自然的想法是使用迷你批次梯度下降。我们随机采样一组节点构成一个批次 `B`，然后计算该批次内所有节点的平均梯度来更新参数。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_33.png)

然而，即使使用迷你批次，问题依然存在。批次 `B` 中每个节点 `i` 都有自己的计算子图。在计算批次梯度时，我们需要取所有节点计算子图的**并集**。如果图非常稠密或GNN层数很深，这个并集可能会迅速膨胀，几乎覆盖整个图。这被称为**图扩展问题**，它会导致巨大的内存和计算开销，使得在大型稠密图上训练深层GNN变得不可行。

---

## 更智能的采样策略

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_35.png)

为了克服图扩展问题，我们需要更智能地构建批次，减少冗余计算并控制子图大小。以下是三种主流的采样策略。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_37.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_38.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_39.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_41.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_43.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_44.png)

### 1. 节点采样：随机邻居采样 (GraphSAGE)

这种方法的核心思想是：在构建每个节点的计算子图时，并不使用其所有邻居，而是在每一层随机采样固定数量的邻居。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_46.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_47.png)

**算法步骤**：
1.  随机选择一批目标节点 `B`。
2.  对于批次中的每个节点，为了计算其第 `k` 层的嵌入，从其第 `k-1` 层的邻居中**随机采样** `S` 个节点。
3.  递归地对这些采样到的邻居节点重复步骤2，直到第1层。

**代码示意**：
```python
# 伪代码：GraphSAGE 前向传播采样
def forward_sample(node, current_layer, num_samples):
    if current_layer == 0:
        return [node] # 输入层，返回节点自身
    neighbors = get_neighbors(node) # 获取邻居
    sampled_neighbors = random.sample(neighbors, min(num_samples, len(neighbors))) # 随机采样
    # 递归采样邻居的邻居
    lower_layer_nodes = []
    for neighbor in sampled_neighbors:
        lower_layer_nodes.extend(forward_sample(neighbor, current_layer-1, num_samples))
    return list(set([node] + lower_layer_nodes)) # 返回去重后的子图节点
```

**优点**：通过控制每层采样数 `S`，有效限制了计算子图的大小，避免了指数级扩展。
**注意点**：由于采样是随机的，即使同一批次被采样两次，其计算子图和最终节点嵌入也可能不同，这为训练过程引入了随机性，起到了正则化的作用。

---

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_49.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_50.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_51.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_52.png)

### 2. 子图采样：聚类采样 (Cluster-GCN)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_54.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_56.png)

这种方法不是以节点为中心进行采样，而是先将整个图分割成多个密集的子图（簇），然后将每个簇（或多个簇的组合）直接作为一个训练批次。

**算法步骤**：
1.  使用图聚类算法（如Metis）将图节点划分为 `C` 个互不相交的簇 `{V1, V2, ..., Vc}`。
2.  每个簇 `Vc` 内的节点及其之间的边构成一个子图。
3.  将每个子图作为一个迷你批次进行训练。在批次内进行消息传递时，只考虑该子图内部的边。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_58.png)

**优点**：
*   **极大提升效率**：完全消除了跨簇的邻居搜索，每个批次的计算被限制在一个小的子图内。
*   **易于并行**：不同的簇可以分配给不同的GPU或机器进行并行训练。
*   **内存友好**：只需加载当前子图的数据到内存。

**挑战**：切割边（位于不同簇之间的边）的信息在批次训练中被忽略，可能会影响模型性能。可以通过随机组合多个簇作为一个批次来部分恢复这些连接。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_60.png)

---

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_62.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_63.png)

### 3. 层采样：层依赖重要性采样 (LADIES)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_65.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_67.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_69.png)

层采样方法试图在节点采样和子图采样之间取得平衡。它在每一层独立地采样节点来构建一个近似的、更小的计算图。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_71.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_72.png)

**早期方法 (FastGCN)**：基于节点度等全局信息，为每一层独立计算采样概率，然后采样固定数量的节点。但这种方法可能导致相邻层采样的节点之间没有边相连，破坏了图结构。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_74.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_75.png)

**改进方法 (LADIES)**：为了保持层间连接性，LADIES采用了一种层依赖的重要性采样策略。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_77.png)

**算法核心思想**：
1.  从顶层（输出层）的批次节点开始。
2.  为了采样下一层的节点，首先收集当前层所有批次节点的**所有邻居**，形成一个二分图。
3.  在这个候选邻居集合中，根据节点的重要性（例如，与其相连的上一层节点数）计算采样概率。
4.  根据此概率采样固定数量的节点，作为下一层的节点。
5.  递归进行，直到输入层。

**优点**：既控制了每层的节点数量，又确保了被采样的节点之间更有可能存在连接，从而更好地保留了图的结构信息，通常能获得比FastGCN更好的性能。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_79.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_81.png)

---

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_83.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_84.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_85.png)

## 总结

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_87.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_88.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_89.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_90.png)

本节课中我们一起学习了图神经网络中批处理的关键技术与采样方法。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_92.png)

*   我们首先分析了在单个大图上进行传统SGD训练时面临的**计算冗余**和**图扩展问题**。
*   接着，我们介绍了三种核心的采样策略来高效构建训练批次：
    1.  **节点采样 (如GraphSAGE)**：递归地随机采样固定数量的邻居，控制感受野大小。
    2.  **子图采样 (如Cluster-GCN)**：先将图聚类，再以子图为单位进行训练，极大提升效率和并行性。
    3.  **层采样 (如LADIES)**：在每一层进行重要性采样，在控制计算成本的同时尽量保持层间连接性。

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_94.png)

![](img/7bfb1a7f1003f06f8f5d623f9eaca4ba_96.png)

这些采样方法是使GNN能够应用于大规模现实图数据的关键。选择哪种方法取决于具体的图结构、模型深度和可用的计算资源。理解它们的原理有助于我们在实践中根据需求选择和设计合适的训练策略。