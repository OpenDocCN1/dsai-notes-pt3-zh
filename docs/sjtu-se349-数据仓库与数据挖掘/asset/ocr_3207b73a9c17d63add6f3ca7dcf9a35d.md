# 模糊聚类分析

则第j类的聚类中心为向量： $\bar{x}^{(j)} = (\bar{x}_1^{(j)}, \bar{x}_2^{(j)}, \cdots, \bar{x}_{n_j}^{(j)})$

其中，$\bar{x}_k^{(j)}$为第k个特征的平均值

$\bar{x}_k^{(j)} = \frac{1}{n_j} \sum_{i=1}^{n_j} x_{ik}^{(j)} \quad (k = 1,2,\cdots,m)$

作$F$ - 统计量

$F = \frac{\displaystyle \sum_{j=1}^{r} n_j \| \bar{x}^{(j)} - \bar{x} \|^2 / (r - 1)}{\displaystyle \sum_{j=1}^{r} \sum_{i=1}^{n_j} \| \bar{x}_i^{(j)} - \bar{x}^{(j)} \|^2 / (n - r)}$