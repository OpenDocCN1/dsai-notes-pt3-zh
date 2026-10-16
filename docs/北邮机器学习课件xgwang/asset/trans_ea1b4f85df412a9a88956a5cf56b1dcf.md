

![](img/a04b187c89c5018c5ef6132980e27196_190_0.png)

## Hessian matrix

梯度下降未能利用 Hessian 中包含的曲率信息。这里我们对一个二次函数使用梯度下降，其 Hessian 矩阵的条件数为 5。红色线条表示梯度下降所遵循的路径。这个非常细长的二次函数类似于一条长峡谷。梯度下降会浪费时间反复下降峡谷壁，因为它们是最陡峭的特征。由于步长有些过大，它有一种超出函数底部的趋势，因此需要在下一次迭代中下降相反的峡谷壁。对应于指向该方向的特征向量的 Hessian 的大正特征值表明该方向导数正在迅速增加，因此基于 Hessian 的优化算法可以预测在这种情况下最陡的方向实际上并不是一个有希望的搜索方向。

## Second-order optimization methods

- 梯度下降仅使用梯度，被称为一阶优化。像牛顿法这样也使用 Hessian 矩阵的优化算法被称为二阶优化算法。

- 使用牛顿法更新

  $\mathbf{x}^* = \mathbf{x}_0 - H(f)(\mathbf{x}_0)^{-1} \nabla_x f(\mathbf{x}_0)$

  当函数可以局部近似为二次函数时，迭代更新近似并跳到近似的最小值可以比梯度下降更快地达到临界点。

- 在许多其他领域，优化的主导方法是为有限的函数族设计优化算法。

- 深度学习中使用的函数族相当复杂和复杂

## Stochastic gradient descent

- 给定 $n$ 个训练样本，我们的目标函数可以表示为

  $$J(w) = \sum_{p=1}^{n} J_p(w)$$

- 批量梯度下降

  $$w \leftarrow w - \eta \sum_{p=1}^{n} \nabla J_p(w)$$

- 在某些情况下，计算和梯度可能在计算上很昂贵。随机梯度下降在每一步采样一部分被加和函数。这在大规模机器学习问题中非常有效。在随机梯度下降中，$J(w)$ 的真实梯度被单个样本（或一个小批量样本）的梯度近似：

  $$w \leftarrow w - \eta \nabla J_p(w)$$

## Stochastic backpropagation

### Algorithm 1 (Stochastic backpropagation)

```
1 begin initialize network topology (# hidden units), w, criterion θ, η, m ← 0
2 do m ← m + 1
3 x^m ← randomly chosen pattern
4 w_ij ← w_ij + η ∂J/∂w_ij; w_jk ← w_jk + η ∂J/∂w_jk
5 until ∇J(w) < θ
6 return w
7 end
```

在随机训练中，权重更新可能会降低正在呈现的单个模式的误差，却增加整个训练集的误差。

## Mini-batch based stochastic gradient descent

- 将训练集划分为小批量。
- 在每个 epoch 中，随机排列小批量并依次取一个小批量来近似梯度
  - 一个 epoch 对应于训练集中所有模式的一次呈现
- 每次迭代的估计梯度更可靠
- 从较小的批量大小开始，并在训练过程中增加大小

## Batch backpropagation

### Algorithm 2 (Batch backpropagation)

```
1 begin initialize network topology (# hidden units), w, criterion θ, η, r ← 0
2 do r ← r + 1 (increment epoch)
3 m ← 0; Δwij ← 0; Δwjk ← 0
4 do m ← m + 1
5 x^m ← select pattern
6 Δwij ← Δwij + ηδj x_i; Δwjk ← Δwjk + ηδk y_j
7 until m = n
8 wij ← wij + Δwij; wjk ← wjk + Δwjk
9 until ∇J[w] < θ
10 return w
11 end
```

## Summary

- **Stochastic learning**
  - 梯度估计是噪声的，权重可能不会在每次迭代中精确地沿梯度移动
  - 比批量学习更快，尤其是在训练数据具有冗余时
  - 噪声通常会导致更好的解
  - 权重会波动，可能不会完全收敛到局部最小值
- **Batch learning**
  - 收敛条件是众所周知的
  - 一些加速技术仅在批量学习中运行
  - 权重动力学和收敛速率的理论分析更简单

