# （1）求解Fish准则函数

用\vec{u}表示待求的\vec{w}_0。

设给定n维训练模式 \vec{x}_1, \vec{x}_2, …, \vec{x}_N，其中有N_1和 N_2=N−N_1 个模式分属 w_1类和 w_2类，分别记为 {\vec{x}_j^{(1)}} 和 {\vec{x}_j^{(2)}}，各类模式均值矢量为

\vec{m}_i = \frac{1}{N_i} \sum_{j} \vec{x}_j^{(i)} \quad (i=1,2)

# 各类别内离差阵 S_{W_i} 和总的类内离差阵 S_W 分别为：

S_{W_i} = \sum_{j} (\vec{x}_j^{(i)} - \vec{m}_i)(\vec{x}_j^{(i)} - \vec{m}_i)' \quad S_W = S_{W_1} + S_{W_2}