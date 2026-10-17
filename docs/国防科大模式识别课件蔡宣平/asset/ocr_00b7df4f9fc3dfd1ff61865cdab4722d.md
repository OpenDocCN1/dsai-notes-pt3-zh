# 第二章 聚类分析

# 2.2 模式相似性测度

# 5. 马氏(Mahalanobis)距离

设n维向量\(\vec{x}_i\)和\(\vec{x}_j\)是向量集\(\{\vec{x}_1,\vec{x}_2,\cdots,\vec{x}_m\}\)中的两个向量，马氏距离\(d\)定义为

```
d²(\vec{x}_i,\vec{x}_j) = (\vec{x}_i - \vec{x}_j)' V^{-1} (\vec{x}_i - \vec{x}_j)    (2-2-5)
```

其中

```
V = \frac{1}{m-1} \sum_{i=1}^{m} (\vec{x}_i - \vec{\bar{x}})(\vec{x}_i - \vec{\bar{x}})'    (2-2-6)
```

```
\vec{\bar{x}} = \frac{1}{m} \sum_{i=1}^{m} \vec{x}_i    (2-2-7)
```