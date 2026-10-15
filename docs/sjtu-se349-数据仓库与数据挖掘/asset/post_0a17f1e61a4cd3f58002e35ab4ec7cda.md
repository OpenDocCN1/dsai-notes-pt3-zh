
## OPTICS: Some Extension from DBSCAN
从DBSCAN的扩充

- 对象p的核心距离是最小的 ε′值，使得p的 ε′-邻域内至少有 MinPts个对象
  - ε′是使得p成为核心对象的最小半径阈值
  - p不是关于 ε 和MinPts的核心对象，其核心距离无定义
- 从对象q到对象p的可达距离是使p从q密度可达的最小半径值
  - Max (core-distance (q), d (q, p))
  - 如果q不是核心对象则无定义

## Core Distance & Reachability Distance
核心距离 & 可达距离

![](img/6d25e92eb0bd56a22c311279c19b06b4_1264_0.png)

Figure 10.16: OPTICS terminology. Based on [ABKS99].

- 假设 ε =6mm MinPts=5

## Core Distance & Reachability Distance
核心距离 & 可达距离

- 为了同时构造不同的聚类，对象需要按特定次序处理，这个次序选择这样的对象，即关于最小的 ε - 值，它是密度可达的，以便较高密度（较低 ε 值）的簇优先完成。

- OPTICS计算给定数据库中所有对象的排序，并且存储每个对象核心距离和相应的可达距离。

- OPTICS维护称做OrderSeeds的表来产生输出排序，OrderSeeds表中的对象按到各自的最近核心对象的可达距离排序，即按每个对象的最小可达距离排序。

- 开始，OPTICS用输入数据库中的任意对象作为当前对象p，它检索p的 ε -邻域，确定核心距离并设置可达距离为未定义。然后，输出当前对象p。如果p不是核心对象，则OPTICS简单地转移到OrderSeeds表（或输入数据库，如果OrderSeeds为空）的下一个对象。

- 如果p是核心对象，则对于p的 ε -邻域中的每个对象q，OPTICS更新从p到q的可达距离，并且如果q尚未处理，则把q插入OrderSeeds。该迭代继续，直到输入完全耗尽并且OrderSeeds为空。

- 数据集的簇排序可以用图形描述，这有助于可视化和理解数据集中聚类结构。

## Core Distance & Reachability Distance
核心距离 & 可达距离

Reachability-distance

undefined

ε

ε'

Cluster-order of the objects

![](img/6d25e92eb0bd56a22c311279c19b06b4_1266_0.png)

一个简单的二维数据集的可达性图。数据对象连同它们各自的可达距离（纵轴）按簇次序（横轴）绘出。其中三个高斯“凸起”反映数据集中的三个簇。

## Density-Based Clustering Methods
基于密度的聚类方法

- DBSCAN: Ester, et al. (KDD’96)
- OPTICS: Ankerst, et al (SIGMOD’99)
- DENCLUE: Hinneburg & D. Keim (KDD’98)

## DENCLUE: Using Statistical Density Functions
DENCLUE算法

- DBSCAN和OPTICS中，密度通过统计被半径参数 ε 定义的邻域中的对象个数来计算
- —使用的半径值非常敏感

- 使用核密度估计
- —每个观测对象都看做周围区域中高概率的一个指示器
- —一个点上的概率密度依赖于从该点到观测对象的距离

设x1,...,xn是随机变量f的独立的、等分布样本。概率密度函数的近似核密度为：

```
f̂ₙ(x) = 1/(n h) Σᵢ₌₁ⁿ K( (x - xᵢ)/h )
```

- 其中K()是核

- DENCLUE使用高斯核估计基于给定的待聚类的对象集密度
- —x*称作密度吸引点，估计的密度函数的局部最大点

![](img/6d25e92eb0bd56a22c311279c19b06b4_1268_0.png)

## DENCLUE: Using Statistical Density Functions
DENCLUE算法

### 梯度

$f_{Gaussian}(x,y)=e^{-\frac{d(x,y)^2}{2\sigma^2}}$

$f^D_{Gaussian}(x)=\sum_{i=1}^{N}e^{-\frac{d(x,x_i)^2}{2\sigma^2}}$

$\nabla f^D_{Gaussian}(x,x_i)=\sum_{i=1}^{N}(x_i-x)\cdot e^{-\frac{d(x,x_i)^2}{2\sigma^2}}$

influence of y on x

total influence on x

gradient of x in the direction of x_i

### 主要特征

- 坚实的数学基础
- 对有巨大噪声的数据集有良好的聚类特性
- 允许对高维数据集中的任意形状的聚类给出简洁的数学描述
- 比现存的算法快的多（如DBSCAN）
- 但是需要大量的参数

## Denclue: Technical Essence
Denclue: 技术本质

- 使用网格单元，但只是保存那些关于实际包含数据点的网格单元的信息，它以一个基于树的存取结构来管理这些单元
- 影响函数: 描述一个数据点在邻域内的影响
- 数据空间的整体密度可以被模型化为所有数据点的影响函数的总和
- 聚类可以通过确定密度吸引点来得到
- 密度吸引点是全局密度函数的局部最大

## Density Attractor  密度吸引点

![](img/6d25e92eb0bd56a22c311279c19b06b4_1271_0.png)

## Chapter 1. Cluster Analysis 聚类

- Cluster Analysis: Basic Concepts 基本概念
- Partitioning Methods 划分方法
- Hierarchical Methods 分层方法
- Density-Based Methods 基于密度的方法
- Grid-Based Methods 基于网格的方法
- Evaluation of Clustering 聚类方法的评估

## Grid-Based Clustering Method
基于网格的聚类方法基本原理

- 网格是一种组织数据集的有效方法，至少在低维空间中如此。

- 基本思想
  - 将每个属性的可能值分割成许多相邻的区间，创建网格单元的集合（我们假定属性值是序数的、区间的或连续的）。
  - 每个对象落入一个网格单元，网格单元对应的属性区间包含该对象的价值。
  - 扫描一遍数据就可以把对象指派到网格单元中，并且还可以同时收集关于每个单元的信息，如单元中的点数。

## Grid-Based Clustering Method
基于网格的聚类方法基本算法

- 1： 定义一个网格单元集
- 2： 将对象指派到合适的单元，并计算每个单元的密度
- 3： 删除密度低于指定的阈值的单元
- 4： 由邻近的稠密单元组形成簇

## Grid-Based Clustering Method
基于网格的聚类方法基本算法

- 1、定义网格单元
  - —这是过程的关键步骤，但是定义也最不严格，因为存在许多方法将每个属性的可能值分割成许多相邻的区间。
  - —对于连续属性，一种常用的方法是将值划分成等宽的区间。如果该方法用于所有的属性，则结果网格单元都具有相同的体积，而单元的密度可以方便地定义为单元中点的个数。
  - —然而，也可以可以使用更复杂的方法。

- 2、网格单元的密度
  - —定义网格单元密度的一种自然方法是：定义网格单元（或更一般形状的区域）的密度为该区域中的点数除以区域的体积。换言之，密度是每单位空间中的点数，而不管空间的维度。

## Grid-Based Clustering Method
基于网格的聚类方法基本算法

- 显示了两个二维点的集合，使用7乘7的网格划分成49个单元。第一个集合包含200个点，由圆心在（2,3）、半径为2的圆上的均匀分布产生。而第二个集合包含100个点，由圆心在（6,3）、半径为1的圆上均匀分布产生。
- 由于单元具有相等的体积（面积），可以将这些值看作单元的密度。

![](img/6d25e92eb0bd56a22c311279c19b06b4_1276_0.png)

| 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 4 | 17 | 18 | 6 | 0 | 0 | 0 |
| 14 | 14 | 13 | 13 | 0 | 18 | 27 |
| 11 | 18 | 10 | 21 | 0 | 24 | 31 |
| 3 | 20 | 14 | 4 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 |

网格单元的点计数

基于网格的密度
