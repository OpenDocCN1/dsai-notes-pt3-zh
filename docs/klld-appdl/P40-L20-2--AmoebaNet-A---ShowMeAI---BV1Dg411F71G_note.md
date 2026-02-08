# 神经网络架构搜索 (NAS) 课程 P40：L20.2 - AmoebaNet-A 🧬

![](img/0d67faca807dfaf500a3d3e6f905ed13_0.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_2.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_4.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_6.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_8.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_10.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_12.png)

在本节课中，我们将学习如何使用**进化算法**进行神经网络架构搜索。我们将重点介绍AmoebaNet-A论文中提出的“正则化进化”方法，该方法结合了随机搜索和选择机制，以高效地发现高性能的神经网络架构。

![](img/0d67faca807dfaf500a3d3e6f905ed13_14.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_16.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_18.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_20.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_22.png)

上一节我们介绍了使用强化学习（策略梯度）进行架构搜索。本节中，我们来看看另一种无需梯度的优化方法：进化算法。

![](img/0d67faca807dfaf500a3d3e6f905ed13_24.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_26.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_28.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_30.png)

## 优化器选择与搜索空间

![](img/0d67faca807dfaf500a3d3e6f905ed13_32.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_34.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_36.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_38.png)

首先需要注意的是，架构搜索的优化器必须是**无梯度**的。因此，无法使用基于梯度的优化方法。

![](img/0d67faca807dfaf500a3d3e6f905ed13_40.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_42.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_44.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_46.png)

以下是几种可行的无梯度优化策略：
*   **随机搜索**
*   **强化学习**
*   **进化算法**

![](img/0d67faca807dfaf500a3d3e6f905ed13_48.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_50.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_52.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_54.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_56.png)

网格搜索不适用，因为它会遭遇**维度灾难**。

![](img/0d67faca807dfaf500a3d3e6f905ed13_58.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_60.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_62.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_64.png)

我们将沿用之前定义的搜索空间，该空间包含**普通单元**和**缩减单元**。我们的目标是寻找最佳的单元结构，这与之前的目标一致。

![](img/0d67faca807dfaf500a3d3e6f905ed13_66.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_68.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_70.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_72.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_74.png)

## 架构决策与进化算法原理

![](img/0d67faca807dfaf500a3d3e6f905ed13_76.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_78.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_80.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_82.png)

现在的问题是，如何优化这些架构？我们需要做的决策包括：
*   连接来自哪里
*   使用何种操作
*   选择拼接还是相加操作

![](img/0d67faca807dfaf500a3d3e6f905ed13_84.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_86.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_88.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_90.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_92.png)

这些决策是按顺序做出的。例如，必须先为第二个模块做出选择，第三个模块的输入才可能来自第二个操作的结果。

![](img/0d67faca807dfaf500a3d3e6f905ed13_94.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_96.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_98.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_100.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_102.png)

**进化**的本质非常简单：**随机搜索 + 选择**。先进行随机搜索，然后选择表现最好的个体保留下来，淘汰或替换表现最差的个体。表现最佳的个体被选中，这就是进化的工作方式。

![](img/0d67faca807dfaf500a3d3e6f905ed13_104.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_106.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_108.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_110.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_112.png)

## 正则化进化算法详解

![](img/0d67faca807dfaf500a3d3e6f905ed13_114.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_116.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_118.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_120.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_122.png)

我们将使用**正则化进化**算法。该算法并不复杂。

![](img/0d67faca807dfaf500a3d3e6f905ed13_124.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_126.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_128.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_130.png)

算法开始时，在时间0有一个空的**种群**和一个**历史记录**列表。在代码中，它们可以被实现为列表或队列。

![](img/0d67faca807dfaf500a3d3e6f905ed13_132.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_134.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_136.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_138.png)

![](img/0d67faca807dfaf500a3d3e6f905ed13_140.png)

以下是算法的具体步骤：

![](img/0d67faca807dfaf500a3d3e6f905ed13_142.png)

1.  **初始化**：随机选择一些架构，训练并评估它们，然后将这些模型加入初始种群（种群大小为 `P`）和历史记录中。
2.  **进化循环**：进行 `C` 个周期的进化（即 `C` 代）。
    *   **采样**：从当前种群中随机采样 `S` 个模型作为候选。
    *   **选择**：从这 `S` 个候选样本中，选择**准确率最高**的模型作为**父代**。这是选择机制的核心。
    *   **变异**：对父代架构进行轻微的**变异**，以产生**子代**架构。
    *   **评估**：训练并评估子代架构。
    *   **更新**：将子代加入种群和历史记录。
    *   **正则化（老化）**：移除种群中**最旧**的模型（即队列最左侧的模型）。无论其性能好坏，都将其丢弃。这作为一种正则化手段，防止算法过早收敛于局部最优解。
3.  **返回结果**：当所有 `C` 代进化完成后，从整个历史记录中返回**性能最佳**的模型。

## 变异操作

之前欠大家一个解释：什么是**变异**？除了随机搜索、训练和评估，变异是关键的步骤。

在架构搜索的上下文中，变异主要有两种类型：
*   **隐藏状态突变**：改变连接的来源。例如，将指向“操作6”的箭头来源，从原来的“操作3”随机改为来自“操作4”、“操作5”、“操作2”、“操作1”或输入“0”。
*   **操作突变**：随机改变节点所执行的操作。例如，将某个操作随机替换为“恒等映射”、“卷积”等候选操作列表中的其他操作。

## 算法性能与总结

进化算法与强化学习和随机搜索的对比表明，进化算法能以更少的时间找到良好的模型。不过，如果有足够的时间，强化学习也能达到与进化算法相当的性能。

最终，我们将得到类似 `N*W^2` 的模型（`N` 是普通单元的数量，`W` 是特征图尺寸），并在准确率方面获得非常好的结果。

**老化机制**（正则化）的效果是显著的。实验表明，使用老化（移除最旧模型）的模型测试准确率，普遍高于不使用老化（仅移除最差候选）的模型。大多数经过正则化的模型性能都更优，说明老化机制确实有帮助。

本节课中，我们一起学习了如何使用正则化进化算法进行神经网络架构搜索。我们了解了算法的核心步骤：初始化、采样、选择、变异、评估和基于老化的正则化。这种方法结合了随机探索和适者生存的选择机制，是自动化机器学习中一种强大且直观的架构搜索策略。