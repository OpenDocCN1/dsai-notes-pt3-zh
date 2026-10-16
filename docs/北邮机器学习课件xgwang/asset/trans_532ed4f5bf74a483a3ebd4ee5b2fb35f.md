

## 马尔可夫模型

- 马尔可夫模型假设依赖最近的历史观测
- 一阶马尔可夫模型

![](img/a04b187c89c5018c5ef6132980e27196_133_0.png)

- 二阶马尔可夫模型

![](img/a04b187c89c5018c5ef6132980e27196_133_1.png)

## HMM 的参数

- 初始状态参数 $P(h_t = \omega_i) = \pi_i, \sum_i \pi_i = 1$
- 转移概率 $P(h_t = \omega_j | h_{t-1} = \omega_i) = a_{ij}, \sum_j a_{ij} = 1$。$A = [a_{ij}]$ 为转移矩阵
- 发射概率 $p(x_t | h_t)$
  - 若 $x_t$ 为单个离散变量，$x_t = v_i \in \{v_1, \ldots, v_m\}$，$P(x_t = v_k | z_t = \omega_j) = b_{jk}, \sum_k b_{jk} = 1$

![](img/a04b187c89c5018c5ef6132980e27196_135_0.png)

- **评估问题**：确定某一特定数据序列 $x_1, \ldots, x_T$ 由该模型生成的概率，

  $$P(x_1, \ldots, x_T)$$

- **解码问题**：给定一组观测 $x_1, \ldots, x_T$，确定导致这些观测的最可能的隐状态序列 $h_1, \ldots, h_T$

  $$(h_1^*, \ldots, h_T^*) = \arg\max_{h_1,\ldots,h_T} P(h_1, \ldots, h_T | x_1, \ldots, x_T)$$

- **学习问题**：给定一组可见变量的训练观测（不知道隐变量），确定 HMM 的参数。

  $$\theta^* = \arg\max_{\theta} P(x_1, \ldots, x_T; \theta)$$

## 循环神经网络（RNN）

- HMM 是生成模型，而 RNN 是判别模型
- 对由外部信号 $x_t$ 驱动的动态系统建模
- $h_t = F_\theta(h_{t-1}, x_t)$
- $h_t$ 包含整个过去序列的信息。上式隐式定义了一个函数，它将整个过去序列 $(x_1, \ldots, x_t)$ 映射到当前状态 $h_t = G_\theta(x_1, \ldots, x_t)$

![](img/a04b187c89c5018c5ef6132980e27196_137_0.png)

左图：RNN 的物理实现，可视为一个电路。黑色方块表示延迟 1 个时间步。右图：同一网络的展开流程图，此时每个节点都与特定的时间实例相关联。

- 这种概括是有损的，因为它将任意长度的序列 $(x_1, \ldots, x_t)$ 映射为固定长度的向量 $h_t$。取决于训练准则，$h_t$ 保留了过往序列的某些重要方面。
- 参数共享：在不同时间步，人工神经元的实例使用相同的权重
- 与 CNN 思想类似：用带参数共享的局部连接替代全连接网络
- 这使得网络可以应用于不同长度的输入序列，并预测不同长度的输出序列

![](img/a04b187c89c5018c5ef6132980e27196_138_0.png)

### 根据输入预测序列的原始 RNN

$$P(y_1, \ldots, y_T | x_1, \ldots, x_T)$$

- 前向传播方程，假设隐单元使用双曲正切非线性，对于分类问题输出使用 softmax

  $$h_t = \tanh(W_{in} x_t + W_{hh} h_{t-1} + b_h)$$

  $$z_t = \mathrm{softmax}(W_{hz} h_t + b_z)$$

  $$p(y_t = c) = z_{t,c}$$

![](img/a04b187c89c5018c5ef6132980e27196_140_0.png)

### RNN 的反向传播

- 回顾流程图上的 BP

![](img/a04b187c89c5018c5ef6132980e27196_142_0.png)

```
∂loss/∂w ← 1
for j = N − 1 down to 1 do
  ∂u_j/∂w ← Σ_{k∈parents(j)} (∂u_k/∂u_j) (∂u_k/∂w) / ∂u_j
end for
return (∂u_N/∂w)^M_{j=1}
```

> （Bengio 等人，《深度学习》，2014）

$$\partial u_j/\partial w_i = \partial u_j/\partial a_i \cdot \partial a_i/\partial net_i \cdot \partial net_i/\partial w_i$$

### 关于 W_hz 和 b_z 的梯度

$$\partial L/\partial L_t = 1, \quad \partial L/\partial z_t = \partial L/\partial L_t \, \partial L_t/\partial z_t = \partial L_t/\partial z_t$$

$$\partial L/\partial W_{hz} = \sum_t \partial L_t/\partial z_t \, \partial z_t/\partial W_{hz}$$

$$\partial L/\partial b_z = \sum_t \partial L_t/\partial z_t \, \partial z_t/\partial b_z$$

![](img/a04b187c89c5018c5ef6132980e27196_143_0.png)

### 关于 W_hh 和 W_xh 的梯度

$$\partial L/\partial W_{hh} = \sum_t \partial L/\partial h_t \, \partial h_t/\partial W_{hh}$$

$$\partial L/\partial h_t = \partial L/\partial h_{t+1} \, \partial h_{t+1}/\partial h_t + \partial L/\partial z_t \, \partial z_t/\partial h_t$$

![](img/a04b187c89c5018c5ef6132980e27196_144_0.png)

