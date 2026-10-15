# The EM (Expectation Maximization) Algorithm

# 期望最大化模型

如何计算模糊聚类和基于概率模型的聚类？这里介绍一种原理性方法。从回顾k-均值聚类问题和k-均值算法开始。

The k-means algorithm has two steps at each iteration:

+   — **Expectation Step (E-step期望步)**: Given the current cluster centers, each object is assigned to the cluster whose center is closest to the object: An object is *expected to belong to the closest cluster*

+   — **Maximization Step (M-step最大化步)**: Given the cluster assignment, for each cluster, the algorithm *adjusts the center* so that *the sum of distance* from the objects assigned to this cluster and the new center is minimized对象到新中心的距离之和最小，即指派到一个簇的对象相似度最大化