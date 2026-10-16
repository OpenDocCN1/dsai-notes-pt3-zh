

## 求主成分 $a_{k1}$

$$
J_1(a_{11},\dots,a_{n1},\mathbf{e}_1)
= \sum_{k=1}^{n} \|\bar{\mathbf{x}} + a_{k1}\mathbf{e}_1 - \mathbf{x}_k\|^2
= \sum_{k=1}^{n} \|a_{k1}\mathbf{e}_1 - (\mathbf{x}_k - \bar{\mathbf{x}})\|^2
$$

$$
= \sum_{k=1}^{n} a_{k1}^2 \|\mathbf{e}_1\|^2
- 2 \sum_{k=1}^{n} a_{k1}\mathbf{e}_1^t(\mathbf{x}_k - \bar{\mathbf{x}})
+ \sum_{k=1}^{n} \|\mathbf{x}_k - \bar{\mathbf{x}}\|^2
$$

由于 $\mathbf{e}_1$ 是单位向量，$\|\mathbf{e}_1\| = 1$。为最小化 $J_1$，令 $\frac{\partial J_1}{\partial a_{k1}} = 0$ 并得到

$$
a_{k1} = \mathbf{e}_1^t(\mathbf{x}_k - \bar{\mathbf{x}})
$$

- 我们通过将向量 $\mathbf{x}_k$ 投影到通过均值且方向为 $\mathbf{e}_1$ 的直线上得到最小二乘解。

## 求最优投影方向 $\mathbf{e}_1$

$$
J_1(\mathbf{e}_1)
= \sum_{k=1}^{n} a_{k1}^2
- 2 \sum_{k=1}^{n} a_{k1}^2
+ \sum_{k=1}^{n} \|\mathbf{x}_k - \bar{\mathbf{x}}\|^2
$$

$$
= -\sum_{k=1}^{n} \left[\mathbf{e}_1^t(\mathbf{x}_k - \bar{\mathbf{x}})\right]^2
+ \sum_{k=1}^{n} \|\mathbf{x}_k - \bar{\mathbf{x}}\|^2
$$

$$
= -\sum_{k=1}^{n} \mathbf{e}_1^t(\mathbf{x}_k - \bar{\mathbf{x}})(\mathbf{x}_k - \bar{\mathbf{x}})^t\mathbf{e}_1
+ \sum_{k=1}^{n} \|\mathbf{x}_k - \bar{\mathbf{x}}\|^2
$$

$$
= -\mathbf{e}_1^t S \mathbf{e}_1
+ \sum_{k=1}^{n} \|\mathbf{x}_k - \bar{\mathbf{x}}\|^2
$$

- $S = \sum_{k=1}^{n}(\mathbf{x}_k-\bar{\mathbf{x}})(\mathbf{x}_k-\bar{\mathbf{x}})^t$ 是散布矩阵。
- $\mathbf{e}_1^t S \mathbf{e}_1 = \sum_{k=1}^{n} a_{k1}^2 \left(\sum_{k=1}^{n} a_{k1}=0\right)$ 是投影数据的方差。
- 使 $J_1$ 最小的向量 $\mathbf{e}_1$ 也在约束 $\|\mathbf{e}_1\| = 1$ 下最大化 $\mathbf{e}_1^t S \mathbf{e}_1$。
- 使用拉格朗日乘数法在约束 $\|\mathbf{e}_1\|=1$ 下最大化 $\mathbf{e}_1^t S \mathbf{e}_1$：

$$
u = \mathbf{e}_1^t S \mathbf{e}_1 - \lambda(\mathbf{e}_1^t\mathbf{e}_1 - 1)
$$

$$
\frac{\partial u}{\partial \mathbf{e}_1} = 2S\mathbf{e}_1 - 2\lambda\mathbf{e}_1 = 0
$$

- 将梯度向量设为零，我们看到 $\mathbf{e}_1$ 必须是散布矩阵的特征向量：

$$
S\mathbf{e}_1 = \lambda \mathbf{e}_1
$$

- 由于 $\mathbf{e}_1^t S \mathbf{e}_1 = \lambda \mathbf{e}_1^t\mathbf{e}_1 = \lambda$，为最大化 $\mathbf{e}_1^t S \mathbf{e}_1$，我们选择具有最大特征值的特征向量。

## PCA 的 $d'$-维表示

- $d'$-维表示：$\tilde{\mathbf{x}}_k = \bar{\mathbf{x}} + \sum_{i=1}^{d'} a_{ki}\mathbf{e}_i$
- 均方准则函数：

$$
J_{d'} = \sum_{k=1}^{n} \left\| \left( \bar{\mathbf{x}} + \sum_{i=1}^{d'} a_{ki}\mathbf{e}_i \right) - \mathbf{x}_k \right\|^2
$$

- 通过在所有与已考虑方向正交的可能方向中选择使 $J$ 最小的每个新方向，以增量的方式定义额外的主成分。
- 为最小化 $J_{d'}$，$\mathbf{e}_1, \dots, \mathbf{e}_{d'}$ 是散布矩阵的 $d'$ 个具有最大特征值的特征向量。$a_{ki}$ 是样本的主成分。
- 由于散布矩阵是实对称的，其特征向量正交且特征值非负。
- 平方误差：

$$
J_{d'} = -\sum_{i=1}^{d'} \lambda_i + \sum_{k=1}^{n} \|\mathbf{x}_k - \bar{\mathbf{x}}\|^2
$$

$$
J_d = 0 \Rightarrow \sum_{k=1}^{n} \|\mathbf{x}_k - \bar{\mathbf{x}}\|^2 = \sum_{i=1}^{d} \lambda_i
$$

$$
J_{d'} = \sum_{i=d'+1}^{d} \lambda_i
$$

## PCA 子空间捕获的数据方差

- 数据投影到前 $d'$ 个特征向量上的方差为 $\sum_{i=1}^{d'} \lambda_i$。
- 衡量前 $d'$ 个特征向量捕获的方差比例：

$$
\frac{\sum_{i=1}^{d'} \lambda_i}{\sum_{j=1}^{d} \lambda_j}
$$

## 主成分的协方差矩阵

- 投影在 $e_i$ 和 $e_j$ $(i \neq j)$ 上的相关性为

$$
\sum_{k=1}^{n} a_{ki}a_{kj}
= \sum_{k=1}^{n} \mathbf{e}_i^t(\mathbf{x}_k-\bar{\mathbf{x}})(\mathbf{x}_k-\bar{\mathbf{x}})^t\mathbf{e}_j
= \mathbf{e}_i^t S \mathbf{e}_j
= \lambda_j \mathbf{e}_i^t\mathbf{e}_j
= 0
$$

- 样本在 PCA 子空间中的协方差矩阵为

$$
\operatorname{diag}[\lambda_1,\ldots,\lambda_d]
$$

## PCA 总结

- 主子空间由 $d'$ 个标准正交向量 $\mathbf{e}_1,\ldots,\mathbf{e}_{d'}$ 张成，它们是散布矩阵 $\mathbf{S}$ 的 $d'$ 个具有最大特征值 $\lambda_1,\ldots,\lambda_{d'}$ 的特征向量。
- 样本的主成分 $a_{ki}$ 计算为 $a_{ki}=\mathbf{e}_i^t(\mathbf{x}_k-\bar{\mathbf{x}})$。
- 投影到该主子空间的样本的方差为 $\sum_{i=1}^{d'}\lambda_i$。
- 样本与其投影之间的均方距离为 $\sum_{i=d'+1}^{d}\lambda_i$。
- PCA 在假设这种变化为高斯分布的前提下，解耦了数据底层变化的因素。
- 我们感兴趣的是学习能够解耦更复杂特征依赖形式的表示。

