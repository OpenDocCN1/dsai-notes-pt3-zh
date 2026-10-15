# The K-Means Clustering Method
K—均值算法

+   - 使用簇的均值代表该簇
+   - 簇Ci的均值可以用以下计算公式：
+     $$\bar{x}_i = \frac{1}{|C_i|} \sum_{x \in C_i} x$$
+   - 对象 $p \in C_i$ 与该簇的代表 $c_i$ 之差用 $dist(p, c_i)$ 度量
+   - 其中 $dist(x, y)$ 是两个点 x 和 y 之间的欧氏距离
+   - 簇Ci的质量可以用簇内变差度量
+     $$E = \sum_{i=1}^{k} \sum_{p \in C_i} dist(p, c_i)^2$$
+   - 其中 E 是数据集中所有对象的误差的平方和，p 是空间中的点，表示给定的数据对象，$c_i$ 是簇 Ci 的代表