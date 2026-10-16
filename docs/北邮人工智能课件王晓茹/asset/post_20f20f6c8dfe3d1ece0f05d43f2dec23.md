
## 向量的表示及基变换：内积和投影

- 两个维数相同的向量的内积被定义为：
- (a1,a2,...,an)^T·(b1,b2,...,bn)^T = a1b1 + a2b2 + ... + anbn
- 内积运算将两个向量映射为一个实数。

设A和B是两个n维向量，n维向量可以等价地表示为从原点出发的有向线段。 A = (x1,y1) B = (x2,y2)

## 基的数学含义

## 协方差矩阵及优化目标

## 协方差

## 基变换的矩阵表示

## 方差

## 协方差矩阵

## 协方差矩阵推广

设有m个n维的数据记录，将其列成m×n的矩阵X，设C = 1/m XXᵀ。

则C是一个协方差矩阵，其对角线分别是各自变量的方差，而第i行第j列则相同，表示两个变量的协方差。

1/m XXᵀ = ( 1/m Σxᵢ²   1/m Σaᵢbᵢ ; 1/m Σaᵢbᵢ   1/m Σbᵢ² )

- 1）实际的数据矩阵X通常不是在原点处，所以需要先做中心化处理。
- 2）协方差矩阵A是对称阵，实对称矩阵可以对角化为A = E Λ Eᵀ，其中E的列向量是标准正交。
- 3）...

E = (e₁ e₂ ... eₙ)

Eᵀ C E = Λ = ( λ₁ λ₂ ... ; ... λₙ )

P = Eᵀ

## 协方差矩阵对角化

- 目标：要求找到矩阵P使协方差矩阵对角化，即使新坐标轴相互正交且Σ=0，并且在对角线上将元素最大化。
- 设Y = P X, 则Y与X的协方差矩阵为D, 我们推导出Y与D的关系：

D = 1/m YYᵀ = 1/m (PX)(PX)ᵀ = 1/m PXXᵀPᵀ = P C Pᵀ

P是能让原始协方差矩阵对角化的矩阵。换句话说，优化目标变成了从一个k维子空间中挑选前K行，使投影后的数据满足优化条件。

## PCA算法

- 设有m条数据记录。
- 1）将原始数据整理成m×n矩阵X
- 2）对每一行（代表一个n维样本）进行均值化，即减去这一行的均值
- 3）求协方差矩阵 C = 1/m XXᵀ
- 4）求出协方差矩阵的特征值和特征向量
- 5）将特征值按对应特征值大小从上到下排列成矩阵，取前k行组成矩阵P
- 6）Y = P X 即为降维到k维后的数据

P = ( 1/√2 1/√2 ; -1/√2 1/√2 )

![](img/806dfb586cd1a39120c0a828715591b9_43_0.png)

## Boosting Classifier & AdaBoost

Weak classifier VS Strong classifier

## Outline

- Overview of Boosting classifier
- The AdaBoost Algorithm
- How and why AdaBoost works?
- AdaBoost for Face Detection

## PAC学习模型

- PAC学习模型
  - 机器学习中，训练样本再大也不能代表某类事物本身，所以从训练样本中学习得到“规则”不能对某类事物完全适用，都有失效的情况出现，所以机器学习的目标是概率逼近正确学习！
  - 1984年Valiant提出PAC（Probably Approximately Correct）学习模型，文中提出强学习和弱学习两个概念。

## 强学习 VS 弱学习

强学习：令ε为充分大的N个数据点(x₁,y₁), …, (xN,yN)的样本集，其中xᵢ是按照某种固定但未知的分布D(x)随机独立抽取的，yᵢ=f(xᵢ)，f属于某个已知的函数类F。如果对于任意的D，任意的ε、δ，任意的h∈F，学习算法生成一个满足Pr[h(x)≠f(x)]≤ε的估计h的概率大于1−δ，并且学习算法的运行时间与1/ε、1/δ成多项式关系，那么称这种学习算法为强学习算法。

弱学习：其定义与强学习算法类似，只是弱学习算法中只需存在某对ε、δ满足上述条件即可。

Kearns和Valiant提出了弱学习算法与强学习算法间的等价问题，即是否能把弱学习算法转化为强学习算法？如果答案为是，那么只要找到一个比随机猜测好的弱学习算法就可以直接将其提升为强学习算法，而不必直接去找很难获得的强学习算法。在文献[4]中Kearns和Valiant证明只要有足够的数据，弱学习算法就能通过集成的方式生成低偏离度的估计。

## 弱学习 -> 强学习

- Valiant的贡献：Valiant指出弱学习转换为强学习的可行性。实际运用中，人们根据生产经验可以较为容易的找到弱学习方法，但是很少情况下要找到强学习方法是不容易的。有时候人们倾向于通过对弱学习进行组合的方式得到强学习方法，而Valiant证明了这种方式的可行性。

## 怎样实现弱学习转换为强学习

- 核心思想：通过组合使弱学习互补。
- 学习是不适定问题，在有限的样本上，不同的学习方法得到不同的“规则”，并在不同的情况下失效，没有一种学习算法总是在任何领域产生最好的分类效果。

## 例子

学习算法A在a情况下失效，学习算法B在b情况下失效，那么在a情况下可以用B算法，在b情况下可以用A算法解决。这说明通过某种合适的方式把各种算法组合起来，可以提高准确率。

为实现弱学习互补，面临两个问题：
1. 怎样获得不同的弱分类器？
2. 怎样组合弱分类器？

## 怎样获得不同的弱分类器？

- 使用不同的弱学习算法得到不同基学习器参数估计、非参数估计……
- 使用相同的弱学习算法，但用不同的超参数：K-Mean不同的K，神经网络不同的隐含层……
- 相同输入对象的不同表示：不同的表示可以显现物体的特征
- 使用不同的训练集：装袋（bagging）、提升（boosting）

## 怎样组合弱分类器

- 多专家组合：一种并行结构，所有的弱分类器结合出各自的预测结果，通过“组合器”把这些预测结果转换为最终结果。eg. 投票（voting）及其变种、混合专家模型
- 多级组合：一种串行结构，其中下一个分类器只在前一个分类器预测不够优（不够自信）的实例上进行训练或检测。eg. 级联算法（cascading）

## 弱学习小结

- bagging在给定样本上随机抽取（有放回）训练子集，每个训练子集上用不稳定的学习算法训练分类器
- boosting在前一个弱分类器错分的实例在后续的弱分类器上得到更大权重
- 从训练子集的获取方式上看：bagging常靠“运气”，boosting有“依据”

## AdaBoost的先验知识

1990年，Schapire最先将弱学习算法通过一种多项式复杂度的算法提升为强学习算法，明显优于Boosting算法。这样带来的弱分类器可以逐步聚焦难以被正确分类的数据集。一年后，Freund提出了一种效率更高的Boosting算法。1993年，Drucker和Schapire等人以构造网络的方式为弱学习器建立多个分类器的ORC问题。由于Boosting算法最终能够构造出强分类器，因此AdaBoost算法在实际应用中表现良好。

## 原理

- AdaBoost的核心思想：“关注”被错分的样本，“聚重”性能好的弱分类器
- 怎么实现：
  1. 不同的训练集→调整样本权重
  2. “关注”→增加错分样本权重
  3. “聚重”→好的分类器权重大
  4. 样本权重间接影响分类器权重

## AdaBoost & Its Applications

## Overview

## Introduction

## AdaBoost

Adaptive Boosting  
A learning algorithm  
Building a strong classifier from a lot of weaker ones

## AdaBoost Concept

![](img/806dfb586cd1a39120c0a828715591b9_45_0.png)

## Weaker Classifiers

$h_1(x)\in\{-1,+1\}$  
$h_2(x)\in\{-1,+1\}$  
$\cdots$  
$h_T(x)\in\{-1,+1\}$

weak classifiers

slightly better than random

- Each weak classifier learns by considering one simple feature.
- Most beneficial features for classification should be selected.
- How to:
  - define features?
  - select beneficial features?
  - train weak classifiers?
  - manage (weight) training samples?
  - associate weight to each weak classifier?

## The Strong Classifiers

$h_1(x)\in\{-1,+1\}$  
$h_2(x)\in\{-1,+1\}$  
$\cdots$  
$h_T(x)\in\{-1,+1\}$

weak classifiers

slightly better than random

How good the strong one will be?

$H_T(x)=\operatorname{sign}\left[\sum_{t=1}^{T}\alpha_t h_t(x)\right]$

strong classifier

## AdaBoost & Its Applications

The AdaBoost Algorithm

1995年Freund提出AdaBoost算法，1999年Schapire在一篇会议论文上对Freund的AdaBoost重新表述，基本原理不变但更易理解，下面以Schapire的版本介绍AdaBoost。

## The AdaBoost Algorithm

Given: $(x_1,y_1),\ldots,(x_m,y_m)$ where $x_i\in X,y_i\in\{-1,+1\}$

Initialization: $D_1(i)=1/m,\ i=1,\ldots,m$

For $t=1,\ldots,T$:

- Find classifier $h_t:X\rightarrow\{-1,+1\}$ which minimizes error with respect to $D_t$, i.e. $h_t=\arg\min_h\sum_iD_t(i)\mathbb{I}[h(x_i)\ne y_i]$.
- Weight classifier: $\alpha_t=\frac{1}{2}\ln\frac{1-\epsilon_t}{\epsilon_t}$
- Update distribution: $D_{t+1}(i)=\frac{D_t(i)\exp(-\alpha_t y_i h_t(x_i))}{Z_t}$, where $Z_t$ is for normalization.

Output final classifier: $\operatorname{sign}[\sum_{t=1}^{T}\alpha_t h_t(x)]$

Freund 等在 1995 年提出了 Discrete AdaBoost 算法，其具体算法如下：
1. 对于训练样本 $(x_i,y_i)$，初始化权重 $D_1(i)=1/m$。
2. 初始化弱分类器 $h_t(x)$。
3. 对于 $t=1,\ldots,T$：
   - 训练弱分类器 $h_t$，使其在当前权重分布下的分类误差最小。
   - 计算分类器权重 $\alpha_t=\frac{1}{2}\ln\frac{1-\epsilon_t}{\epsilon_t}$。
   - 更新样本权重 $D_{t+1}(i)=\frac{D_t(i)\exp(-\alpha_t y_i h_t(x_i))}{Z_t}$。
4. 最终得到分类器 $H(x)=\operatorname{sign}[\sum_{t=1}^{T}\alpha_t h_t(x)]$。

## Schapire AdaBoost Algorithm

```
Given: m examples $(x_1,y_1),\ldots,(x_m,y_m)$ where $x_i\in X,y_i\in\{-1,+1\}$
Initialize $D_1(i)=1/m$
For $t=1$ to $T$
  1. Train learner $h_t$ with error $\epsilon_t=\Pr_{x\sim D_t}[h_t(x)\ne y]$
  2. Compute the hypothesis weight $\alpha_t=\frac{1}{2}\ln\left(\frac{1-\epsilon_t}{\epsilon_t}\right)$
  3. For each example $(x_i,y_i)$:
     $D_{t+1}(i)=\frac{D_t(i)}{Z_t}\exp(-\alpha_t y_i h_t(x_i))$
Output: $H(x)=\operatorname{sign}\left(\sum_t\alpha_t h_t(x)\right)$
```

## The AdaBoost Algorithm

Given: $(x_1,y_1),\ldots,(x_m,y_m)$ where $x_i\in X,y_i\in\{-1,+1\}$

Initialization: $D_1(i)=1/m,\ i=1,\ldots,m$

For $t=1,\ldots,T$:

- Find classifier $h_t:X\rightarrow\{-1,+1\}$ which minimizes error with respect to $D_t$.
- Weight classifier: $\alpha_t=\frac{1}{2}\ln\frac{1-\epsilon_t}{\epsilon_t}$
- Update distribution: $D_{t+1}(i)=\frac{D_t(i)\exp(-\alpha_t y_i h_t(x_i))}{Z_t}$

Output final classifier: $\operatorname{sign}[\sum_{t=1}^{T}\alpha_t h_t(x)]$
