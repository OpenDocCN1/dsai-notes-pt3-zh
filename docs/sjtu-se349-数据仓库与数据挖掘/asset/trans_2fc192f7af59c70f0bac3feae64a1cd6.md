

## 第11章 高级聚类分析

- Probability Model-Based Clustering  基于概率模型的聚类
- Clustering High-Dimensional Data  聚类高维数据
- Clustering Graphs and Network Data  聚类图和网络数据
- Clustering with Constraints, Grid-Based Methods  具有约束的聚类
- Summary  小结

### 传统距离度量在高维数据上可能无效

- 传统距离度量在许多维度上可能被噪声主导

- 例：哪些客户对更相似？

| Customer | P1 | P2 | P3 | P4 | P5 | P6 | P7 | P8 | P9 | P10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Ada | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| Bob | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 |
| Cathy | 1 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 1 |

- 按欧几里得距离，我们得到，dist(Ada, Bob) = dist(Bob, Cathy) = dist(Ada, Cathy) = √2 — 尽管 Ada 和 Cathy 看起来更相似

- 聚类不仅应考虑维度，还应考虑属性（特征）

- 特征变换：当大多数维度相关时有效（PCA 主成份分析 useful when features are highly correlated/redundant）

- 特征选择：有助于找到数据具有良好聚类的子空间

### 维度灾难

(graphs adapted from Parsons et al. KDD Explorations 2004)

- 一维数据相对集中

- 增加一个维度会“拉伸”点，使它们更远

- 增加更多维度会使点更远——高维数据极其稀疏

- 距离度量变得毫无意义——由于 equi-distance等距离

![](img/6d25e92eb0bd56a22c311279c19b06b4_1317_0.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1317_1.png)

(b) 6 Objects in One Unit Bin

![](img/6d25e92eb0bd56a22c311279c19b06b4_1317_2.png)

(c) 4 Objects in One Unit Bin

### 聚类高维数据

- **Clustering high-dimensional data (How high is high-D in clustering?)**
  - Many applications: text documents, DNA micro-array data
  - Major challenges:
    - Many irrelevant dimensions may mask clusters
    - Distance measure becomes meaningless—due to equi-distance
    - Clusters may exist only in some subspaces

- **Methods**
  - **Subspace-clustering子空间聚类方法**: Search for clusters existing in subspaces of the given high dimensional data space
    - CLIQUE, ProClus, and bi-clustering approaches
  - **Dimensionality reduction approaches维归约方法**: Construct a much lower dimensional space and search for clusters there (may construct new dimensions by combining some dimensions in the original data)
    - Dimensionality reduction methods and spectral clustering
    - 维归约和谱聚类

### 为什么子空间聚类？

(adapted from Parsons et al. SIGKDD Explorations 2004)

- Clusters may exist only in some subspaces
- Subspace-clustering: find clusters in all the subspaces

![](img/6d25e92eb0bd56a22c311279c19b06b4_1319_0.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1319_1.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1319_2.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1319_3.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1319_4.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1319_5.png)

![](img/6d25e92eb0bd56a22c311279c19b06b4_1319_6.png)

### 子空间聚类方法 子空间聚类方法

- **Subspace search methods子空间搜索方法**: Search various subspaces to find clusters
  - Bottom-up approaches
  - Top-down approaches

- **Correlation-based clustering methods基于相关性的聚类方法**
  - E.g., PCA based approaches

- **Bi-clustering methods双聚类**
  - Optimization-based methods
  - Enumeration methods

### 子空间聚类方法 (I)：子空间搜索方法

- Search various subspaces to find clusters
- *Bottom-up approaches*
  - Start from low-D subspaces and search higher-D subspaces only when there may be clusters in such subspaces
  - Various pruning techniques to reduce the number of higher-D subspaces to be searched
  - Ex. CLIQUE (Agrawal et al. 1998)
- *Top-down approaches*
  - Start from full space and search smaller subspaces recursively
  - Effective only if the locality assumption holds局部性假定有效:
    - *restricts that the subspace of a cluster can be determined by the local neighborhood*
    - 限制簇的子空间可以被局部邻域确定
  - Ex. PROCLUS (Aggarwal et al. 1999): a k-medoid-like method

