

## 什么是迁移学习？

给定源域 $D_S$ 和学习任务 $T_S$，目标域 $D_T$ 和学习任务 $T_T$，迁移学习旨在利用 $D_S$ 和 $T_S$ 中的知识来帮助改进 $D_T$ 中目标预测函数 $f_T(\cdot)$ 的学习，其中 $D_S \neq D_T$，或 $T_S \neq T_T$。

![](img/a04b187c89c5018c5ef6132980e27196_236_0.png)

## 什么是域适应？

- **域适应：**
  - 源域：大量有标签数据。
  - 目标域：少量或没有有标签数据。
  - 任务相同，但数据分布不同。

![](img/a04b187c89c5018c5ef6132980e27196_237_0.png)

> [1] Pan S J, Yang Q. A survey on transfer learning[J]. IEEE Transactions on knowledge and data engineering, 2010, 22(10): 1345-1359.

## 什么是域适应？

由于多种因素（例如，光照、姿势和图像质量），两个域之间总会存在**分布变化或域偏移**，这会降低性能。

![](img/a04b187c89c5018c5ef6132980e27196_238_0.png)

[2] M. Wang and W. Deng. *Deep visual domain adaptation: A survey*. Neurocomputing, 312:135–153, 2018.

## 什么是域适应？

由于两个域之间存在分布变化或域偏移，为源域学习到的分类器无法应用于目标域。

![](img/a04b187c89c5018c5ef6132980e27196_239_0.png)

### SVHN→MNIST

![](img/a04b187c89c5018c5ef6132980e27196_239_1.png)

(a) non-adapted

### SVHN→MNIST

![](img/a04b187c89c5018c5ef6132980e27196_239_2.png)

(a) adapted

## 什么是域适应？

- **监督式 DA**，存在少量有标签的目标数据。然而，有标签数据通常不足以完成任务。
- **半监督式 DA**，在训练阶段目标域中同时存在有限的有标签数据和冗余的无标签数据，这使得网络能够学习目标域的结构信息。
- **无监督式 DA**，在训练网络时没有有标签但有足够无标签的目标域数据可观察。

![](img/a04b187c89c5018c5ef6132980e27196_240_0.png)

## 迁移学习的关键

迁移学习的关键要素是发现两个领域之间的共同点。一旦发现这种共同点，迁移学习就变得容易了。我们在机器学习中称这种共同点为共同特征。

![](img/a04b187c89c5018c5ef6132980e27196_241_0.png)

VS

![](img/a04b187c89c5018c5ef6132980e27196_241_1.png)

![](img/a04b187c89c5018c5ef6132980e27196_241_2.png)

## 浅层域适应

- **传统深度学习**
  
  min 1/n Σ_{i=1}^n L(x_i, y_i, θ)
- **特征适应**
  
  min 1/n Σ_{i=1}^n L(φ(x_i^s), y_i^s, θ)
- **实例适应**
  
  min 1/n Σ_{i=1}^n w_i L(x_i^s, y_i^s, θ)
- **模型适应**
  
  min 1/n Σ_{i=1}^n L(x_i^s, y_i^s, θ)

Slide credit: Meina Kan

> [1] Pan S J, Yang Q. A survey on transfer learning[J]. IEEE Transactions on knowledge and data engineering, 2010, 22(10): 1345-1359.

## Deep visual domain adaptation: A survey

使用有标签或无标签的目标数据微调深度网络以减小域偏移

使用域判别器通过对抗目标来鼓励域混淆

使用数据重建作为辅助任务以确保特征不变性

### 基于差异的 DA

### 基于对抗的 DA

### 基于重建的 DA

- class criterion
- architecture criterion
- statistic criterion
- geometric criterion

- generative models
- non-generative models

- encoder-decoder reconstruction
- adversarial reconstruction

![](img/a04b187c89c5018c5ef6132980e27196_243_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_243_1.png)

![](img/a04b187c89c5018c5ef6132980e27196_243_2.png)

![](img/a04b187c89c5018c5ef6132980e27196_243_3.png)

## 监督式 DA 方法：微调

它展示了迁移性如何受到两个不同问题的负面影响：与在脆弱协同适应的层中间分割网络相关的优化困难，以及高层特征对原始任务的专门化以牺牲目标任务上的性能为代价。

|  | The size of target dataset |  |  |
|  | Low | Medium | High |
| The distance between domains | Low | Freeze | freeze or tune | Tune |
|  | Medium | freeze or tune | Tune | Tune |
|  | High | freeze or tune | Tune | Tune |

![](img/a04b187c89c5018c5ef6132980e27196_245_0.png)

![](img/a04b187c89c5018c5ef6132980e27196_245_1.png)

