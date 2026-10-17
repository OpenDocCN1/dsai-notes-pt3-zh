# 第三步：根据新分割的两类建立新的聚类中心

\(
\vec{z}_1(2) = \frac{1}{N_1} \sum_{i: \vec{x}_i \in G_1(1)} \vec{x}_i = \frac{1}{2}(\vec{x}_1 + \vec{x}_3) = \frac{1}{2} \begin{bmatrix} 0 \ 0 \end{bmatrix} + \begin{bmatrix} 0 \ 1 \end{bmatrix} = (0,0.5)^T
\)

\(
\vec{z}_2(2)= \frac{1}{N_2} \sum_{i: \vec{x}_i \in G_2(1)} \vec{x}_i = \frac{1}{18}(\vec{x}_2 + \vec{x}_4 + \vec{x}_5 + ... + \vec{x}_{20} )
 = (5.67,5.33)^T
\)

# 第四步：

因为 \(\vec{z}_j(2) \neq \vec{z}_j(1), j = 1,2\) (新旧聚类中心不等)
转第二步。

# 第二步：重新计算 \(\vec{x}_1, \vec{x}_2, ..., \vec{x}_{20}\) 到 \(\vec{z}_1(2), \vec{z}_2(2)\) 的距离，把它们归为最近聚类中心，重新分为两类，

重新计算 \(\vec{x}_1, \vec{x}_2, ..., \vec{x}_{20}\) 到 \(\vec{z}_1(2), \vec{z}_2(2)\) 的距离，把它们归为最近聚类中心，重新分为两类，