
## 位势函数图例

K(x, x_i)

x_2 ∈ ω_2

x_1 ∈ ω_1

![](img/d893b90ad57f036ece52d376593dc2c5_367_0.png)

### （一）下面介绍两类位势函数：

**第一类位势函数**

设 {φ_i(\vec{x}), i = 1, 2, …} 是 \vec{x} 定义域中的完备正交函数集，位势函数取为

$$K(\vec{x}, \vec{x}_j) = \sum_{i=1}^{m} \varphi_i(\vec{x}) \varphi_i(\vec{x}_j)$$

这是对称的有限项多项式。

**第二类位势函数**

取关于 \vec{x} 和 \vec{x}_j 的距离的对称函数作位势函数，例如

$$K(\vec{x}, \vec{x}_j) = \exp[-\alpha\|\vec{x} - \vec{x}_j\|^2]$$

$$K(\vec{x}, \vec{x}_j) = \frac{1}{1 + \alpha\|\vec{x} - \vec{x}_j\|^2}$$

![](img/d893b90ad57f036ece52d376593dc2c5_369_0.png)

ω_1、ω_2

### （二）由位势函数产生判别函数的训练算法及分类规则

设训练模式集为 { \vec{x}_1, \vec{x}_2, …, \vec{x}_N }，它们分属 ω_1 和 ω_2 类。定义一个位势函数 K(\vec{x}, \vec{x}_j)。

- (1) 初始化。令特征空间中各点处的初始积累位势函数 K_0(\vec{x}) = 0，判错计数 m = 0；
- (2) 令 j = 1，输入训练模式 \vec{x}_1，使积累位势函数

$$K_1(\vec{x}) = \begin{cases} K_0(\vec{x}) + K(\vec{x}, \vec{x}_1), & \text{若 } \vec{x}_1 \in \omega_1 \\ K_0(\vec{x}) - K(\vec{x}, \vec{x}_1), & \text{若 } \vec{x}_1 \in \omega_2 \end{cases}$$

![](img/d893b90ad57f036ece52d376593dc2c5_370_0.png)

- (3) 令 j = j + 1，输入 \vec{x}_j，计算积累位势函数

$$K_j(\vec{x}) = K_{j-1}(\vec{x}) + \alpha_j K(\vec{x}, \vec{x}_j)$$

积累位势函数的调整规则为

$$\alpha_j = \begin{cases} 0, & \text{若 } \vec{x}_j \in \omega_1 \text{ 且 } K_{j-1}(\vec{x}_j) > 0 \\ 0, & \text{若 } \vec{x}_j \in \omega_2 \text{ 且 } K_{j-1}(\vec{x}_j) < 0 \\ 1, & \text{若 } \vec{x}_j \in \omega_1 \text{ 且 } K_{j-1}(\vec{x}_j) \le 0 \\ -1, & \text{若 } \vec{x}_j \in \omega_2 \text{ 且 } K_{j-1}(\vec{x}_j) \ge 0 \end{cases}$$

m = m + |\alpha_j|

- (4) 如果 j < N，返至(3)。如果 j = N，检查是否有模式判错；若 m = 0，则结束 d(\vec{x}) = K_j(\vec{x})；若 m ≠ 0，令 j = 0，m = 0，返至(3)。

与感知器算法类似，位势函数训练算法也可以用于多类问题，其技术要点是：

- (1) 设初始积累位势函数 K_0^{(i)}(\vec{x}) = 0，这里 i 表示类别，i = 1, 2, …, c。
- (2) 当 \vec{x}_{j+1} ∈ ω_i 时，迭代规则是
  - 如果 K_j^{(i)}(\vec{x}_{j+1}) > K_j^{(l)}(\vec{x}_{j+1}) \quad (\forall l \neq i)，则 K_{j+1}^{(i)}(\vec{x}) = K_j^{(i)}(\vec{x}) \quad (\forall i)；
  - 如果 K_j^{(i)}(\vec{x}_{j+1}) < K_j^{(m)}(\vec{x}_{j+1}) \quad (m \neq i)，则
    - K_{j+1}^{(i)}(\vec{x}) = K_j^{(i)}(\vec{x}) + \alpha_j K(\vec{x}, \vec{x}_{j+1})
    - K_{j+1}^{(m)}(\vec{x}) = K_j^{(m)}(\vec{x}) - \alpha_j K(\vec{x}, \vec{x}_{j+1})
    - K_{j+1}^{(l)}(\vec{x}) = K_j^{(l)}(\vec{x}) \quad (\forall l \neq i, m)
- (3) 若全部训练模式均满足：当 \vec{x} ∈ ω_i 时，有

$$K_{j+1}^{(i)}(\vec{x}) > K_{j+1}^{(l)}(\vec{x}) \quad (\forall l \neq i)$$

则算法结束。这里 K_{j+1}^{(i)}(\vec{x}) 就是解多类问题第三个途径中的 d_i(\vec{x})。

### 例：已知如图（3-12-1）所示两类训练样本：

\vec{x}_1 = (0,0)'，\vec{x}_2 = (2,0)' ∈ ω_1；\vec{x}_3 = (1,1)'，\vec{x}_4 = (1,-1)' ∈ ω_2

试用势函数法进行分类器训练。

解：选用第三类位势函数，令 α = 1，在二维情况下，

$$K(\vec{x}, \vec{x}_j) = \exp[-\|\vec{x} - \vec{x}_j\|^2] = \exp[-( (x_1 - x_{j1})^2 + (x_2 - x_{j2})^2 )]$$

K(\vec{x}) 为积累势函数。

j = 0，K_0(\vec{x}) = 0

j = 1，\vec{x}_1 ∈ ω_1，

$$K_1(\vec{x}) = K(\vec{x}, \vec{x}_1) = \exp[-( (x_1 - 0)^2 + (x_2 - 0)^2 )] = \exp[-(x_1^2 + x_2^2)]$$

j = 2，\vec{x}_2 ∈ ω_1，K_1(\vec{x}_2) = \exp[-(2^2 + 0^2)] = e^{-4} > 0

$$K_2(\vec{x}) = K_1(\vec{x}) = \exp[-(x_1^2 + x_2^2)]$$

![](img/d893b90ad57f036ece52d376593dc2c5_374_0.png)

j = 3，\vec{x}_3 ∈ ω_2，K_2(\vec{x}_3) = \exp[-(1^2 + 1^2)] = e^{-2} > 0

$$K_3(\vec{x}) = K_2(\vec{x}) - K(\vec{x}, \vec{x}_3) = \exp[-(x_1^2 + x_2^2)] - \exp[-((x_1 - 1)^2 + (x_2 - 1)^2)]$$

j = 4，\vec{x}_4 ∈ ω_2，K_3(\vec{x}_4) = e^{-2} - e^{-4} > 0

$$K_4(\vec{x}) = K_3(\vec{x}) - K(\vec{x}, \vec{x}_4) = \exp[-(x_1^2 + x_2^2)] - \exp[-((x_1 - 1)^2 + (x_2 - 1)^2)] - \exp[-((x_1 - 1)^2 + (x_2 + 1)^2)]$$

j = 5，\vec{x}_1 ∈ ω_1，K_4(\vec{x}_1) = \exp[0] - e^{-2} - e^{-2} = e^0 - 2e^{-2} > 0

$$K_5(\vec{x}) = K_4(\vec{x}) = \exp[-(x_1^2 + x_2^2)] - \exp[-((x_1 - 1)^2 + (x_2 - 1)^2)] - \exp[-((x_1 - 1)^2 + (x_2 + 1)^2)]$$

j = 6，\vec{x}_2 ∈ ω_1，K_5(\vec{x}_2) = e^{-4} - e^{-2} - e^{-2} = e^{-4} - 2e^{-2} < 0

$$K_6(\vec{x}) = K_5(\vec{x}) + K(\vec{x}, \vec{x}_2) = K_5(\vec{x}) + \exp[-((x_1 - 2)^2 + x_2^2)]$$

$$= \exp[-(x_1^2 + x_2^2)] - \exp[-((x_1 - 1)^2 + (x_2 - 1)^2)] - \exp[-((x_1 - 1)^2 + (x_2 + 1)^2)] + \exp[-((x_1 - 2)^2 + x_2^2)]$$

j = 7，\vec{x}_3 ∈ ω_2，K_6(\vec{x}_3) = e^{-2} - e^0 - e^{-4} + e^{-2} < 0

$$K_7(\vec{x}) = K_6(\vec{x})$$

j = 8，\vec{x}_4 ∈ ω_2，K_7(\vec{x}_4) = e^{-2} - e^{-4} - e^0 + e^{-2} < 0

$$K_8(\vec{x}) = K_6(\vec{x})$$

j = 9，\vec{x}_1 ∈ ω_1，K_8(\vec{x}_1) = e^0 - e^{-2} - e^{-2} + e^{-4} > 0

$$K_9(\vec{x}) = K_6(\vec{x})$$

j = 10，\vec{x}_2 ∈ ω_1，K_9(\vec{x}_2) = e^{-4} - e^{-2} - e^{-2} + e^0 > 0

$$K_{10}(\vec{x}) = K_6(\vec{x})$$

$$d(\vec{x}) = K_6(\vec{x})$$

$$d(\vec{x}) = \exp[-(x_1^2 + x_2^2)] - \exp[-((x_1 - 1)^2 + (x_2 - 1)^2)] - \exp[-((x_1 - 1)^2 + (x_2 + 1)^2)] + \exp[-((x_1 - 2)^2 + x_2^2)]$$

令 d(\vec{x}) = 0，则

$$\exp[-(x_1^2 + x_2^2)] - \exp[-((x_1 - 1)^2 + (x_2 - 1)^2)] - \exp[-((x_1 - 1)^2 + (x_2 + 1)^2)] + \exp[-((x_1 - 2)^2 + x_2^2)]$$

$$= \exp[-(x_1^2 + x_2^2)]\left\{1 - \exp[-2(1 - x_1 - x_2)] - \exp[-2(1 - x_1 + x_2)] + \exp[-4(1 - x_1)]\right\}$$

$$= \exp[-(x_1^2 + x_2^2)] \exp[-2(1 - x_1)]\left\{\exp[2(1 - x_1)] + \exp[-2(1 - x_1)] - \exp[2x_2] - \exp[-2x_2]\right\} = 0$$

因为 \exp[-(x_1^2 + x_2^2)] ≠ 0，\exp[-2(1 - x_1)] ≠ 0，

所以

$$\exp[2x_2] + \exp[-2x_2] = \exp[2(1 - x_1)] + \exp[-2(1 - x_1)]$$

即 \operatorname{ch}(2x_2) = \operatorname{ch}(2 - 2x_1)，（双曲余弦函数：\operatorname{ch}(x) = \cosh(x) = (e^x + e^{-x})/2）

$$\begin{cases} 2x_2 = 2 - 2x_1 \\ 2x_2 = -(2 - 2x_1) \end{cases}$$

$$\begin{cases} x_2 = 1 - x_1 \\ x_2 = x_1 - 1 \end{cases}$$

判别界面
