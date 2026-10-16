或 $H[X^*(\sigma),\lambda(\sigma),U^*(\sigma)] \le H[X^*(\sigma),\lambda(\sigma),\bar{U}(\sigma)]$  (3.2-20)

考虑到 $\sigma$, $\bar{U}$ 的任意性，故有

$H[X^*(t),\lambda(t),U^*(t)] = \min_{U(t)\in\Omega} H[X^*(t),\lambda(t),U(t)]$  (3.2-21)

# 5. $\Delta t_f$ 的考虑

以上假设 $t_f$ 固定，令 $t_f = t_f^* + \Delta t_f$, $\Delta t_f = \varepsilon T_1$, $T_1$ 为任意实数。

![](bbox=[0.2, 0.48, 0.82, 0.75])

由式(3.2-1)

$\Delta J = \frac{\partial S[X^*(t_f^*)]}{\partial X^T(t_f)} \Delta X(t_f) + o(\vert \Delta X(t_f)\vert )$

$\Delta X(t_f) = \Delta X(t_f^*) + \dot{X}^*(t_f^*)\Delta t_f$

可得出

$\Delta J = \frac{\partial S[X^*(t_f^*)]}{\partial X^T(t_f)}[\Delta X(t_f^*) + \dot{X}^*(t_f^*)\Delta t_f] + o(\varepsilon)$
$= \frac{\partial S[X^*(t_f^*)]}{\partial X^T(t_f)} f[X^*(t_f^*)U^*(t_f^*)]\varepsilon T_1$
$+ \frac{\partial S[X^*(t_f^*)]}{\partial X^T(t_f)}\cdot\Delta X(t_f^*) + o(\varepsilon) \ge 0$  (3.2-22)

考虑到 $T_1$ 的任意性（可正可负）

$\frac{\partial S[X^*(t_f^*)]}{\partial X^T(t_f)} f[X^*(t_f^*)U^*(t_f^*)]$