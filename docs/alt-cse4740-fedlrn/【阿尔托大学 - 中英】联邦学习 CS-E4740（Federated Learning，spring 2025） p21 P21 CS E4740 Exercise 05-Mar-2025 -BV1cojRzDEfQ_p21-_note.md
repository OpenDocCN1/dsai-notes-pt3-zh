# 联邦学习 CS-E4740：2：联邦学习网络构建与分析 🧠

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_0.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_2.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_3.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_5.png)

在本节课中，我们将学习如何从零开始构建一个联邦学习网络，并使用图论方法对其进行分析。我们将使用Python的`networkx`库来创建图结构，并计算节点度、拉普拉斯矩阵等关键指标，最后通过局部平均算法进行简单的预测。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_7.png)

## 概述

本次作业的目标是实现一个联邦学习网络。我们将从机器学习的基础概念过渡到联邦学习的网络构建。具体任务包括：使用`networkx`包创建图及其边，分析网络的节点度和拉普拉斯矩阵指标，并在该联邦学习网络中应用图学习网络和局部平均等距离度量方法。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_9.png)

## 任务详解

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_11.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_12.png)

### 1. 环境准备与数据理解

首先，我们需要导入必要的库和包。数据已经过预处理，例如，气象站的纬度范围在60到65之间，经度范围在284到30之间。同时，数据还包含了温度均值和温度标准差等信息。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_14.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_15.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_16.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_17.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_18.png)

以下是需要导入的核心库：
```python
import networkx as nx
import numpy as np
import matplotlib.pyplot as plt
```

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_19.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_21.png)

### 2. 构建联邦学习网络

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_23.png)

上一节我们介绍了作业的整体目标，本节中我们来看看第一个具体任务：构建两个联邦学习网络图。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_25.png)

任务要求创建两个图：一个基于地理坐标（`geo`），另一个基于统计属性（`sta`）。图中节点的数据（如模拟的温度值）需要由我们通过代码来初始化和填充。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_27.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_28.png)

以下是构建图结构的基本框架：
```python
# 初始化一个空图
G = nx.Graph()
# 在此处添加节点和模拟数据
# ...
```
完成代码并运行后，如果测试通过，则表明两个图已成功创建。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_29.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_30.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_31.png)

### 3. 为网络创建边

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_33.png)

在创建了图之后，我们需要为网络添加边。由于我们有两个不同的图（`geo`和`sta`），因此创建边的条件也不同。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_35.png)

在`construct_edges`函数中，我们需要根据`method`参数的值来决定如何连接节点：
*   如果方法是`geo`，则使用节点的经纬度坐标来计算距离。
*   如果方法是`sta`，则使用节点的温度均值和标准差等统计属性。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_36.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_37.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_38.png)

以下是创建边的逻辑分支：
```python
def construct_edges(graph, method='geo'):
    if method == 'geo':
        # 使用经纬度计算距离，为每个节点连接最近的5个邻居
        pass
    elif method == 'sta':
        # 使用温度统计属性计算相似度，为每个节点连接最近的5个邻居
        pass
```
运行此函数后，边将被创建。随后我们可以绘制网络图，将会看到两个节点位置相同但边结构不同的网络，这是因为它们的连接依据（地理属性 vs 统计属性）不同。

### 4. 分析网络连通性

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_40.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_41.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_42.png)

接下来，我们将分析网络的连通性。这涉及到计算图的拉普拉斯矩阵及其特征值和特征向量。

具体任务是计算拉普拉斯矩阵的第二小特征值（即代数连通度）及其对应的特征向量。这个值反映了网络的连通强度。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_44.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_45.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_46.png)

计算拉普拉斯矩阵的公式为：
**L = D - A**
其中，`D`是度矩阵，`A`是邻接矩阵。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_48.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_49.png)

完成计算后，我们可以通过可视化来观察两个网络的连通性差异。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_51.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_52.png)

### 5. 实现局部平均算法

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_53.png)

最后，我们将在构建的联邦学习网络上应用一个简单的图学习算法：局部平均。该算法用于根据邻居节点的数据来预测当前节点的温度值。

我们需要计算每个节点的预测误差。具体方法是计算节点自身温度与其所有邻居节点温度平均值之间的差值。

以下是计算预测误差的核心步骤：
```python
prediction_errors = {}
for node in graph.nodes():
    neighbors = list(graph.neighbors(node))
    if neighbors:
        # 计算邻居节点的平均温度
        neighbor_avg = np.mean([graph.nodes[n]['temperature'] for n in neighbors])
        # 计算预测误差（绝对值）
        error = abs(graph.nodes[node]['temperature'] - neighbor_avg)
        prediction_errors[node] = error
    else:
        # 处理没有邻居的罕见情况（本次作业中每个节点都有5个邻居）
        prediction_errors[node] = None
```
通过分析这些误差，我们可以评估局部平均算法在该网络上的表现。

## 总结

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_55.png)

本节课中，我们一起学习了如何从零构建一个联邦学习网络。我们使用`networkx`创建了基于不同属性（地理和统计）的图结构，为网络添加了边，并通过计算拉普拉斯矩阵分析了网络的连通性。最后，我们实现了一个简单的局部平均算法来在节点之间进行预测。本次作业没有使用现成的联邦学习框架（如FATE或TFF），而是专注于理解网络底层结构的构建与分析，为后续更复杂的学习任务打下基础。