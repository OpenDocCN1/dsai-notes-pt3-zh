（4）若

\[
d_l=\max_i\left[\min(d_{i1},d_{i2})\right]>\theta\left\|\vec{z}_1-\vec{z}_2\right\|
\]

则相应的特征矢量 $\vec{x}_l$ 作为第三个聚类中心，$\vec{z}_3=\vec{x}_l$，然后转至（5）；否则，转至最后一步（6）。

（5）设存在 $k$ 个聚类中心，计算未被作为聚类中心的各特征矢量到各聚类中心的距离 $d_{ij}$，并算出

\[
d_l=\max_i\left[\min\left(d_{i1},d_{i2},\cdots,d_{ik}\right)\right]
\]

如果

\[
d_l>\theta\left\|\vec{z}_1-\vec{z}_2\right\|，则\vec{z}_{k+1}=\vec{x}_l
\]

并转至（5）；否则，转至最后一步（6）。