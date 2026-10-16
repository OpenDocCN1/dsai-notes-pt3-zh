# 定理3.5 设 $U(t)\in U$ 是一容许控制，指定末值型性能指标泛函为 $J[U(\cdot)]=S[X(t_f),t_f]$

$X(t)$ 是非定常系统 $\dot X = f(X,U,t),\ X(t_0)=X_0,\ t\in[t_0,t_f]$

对应于 $U(t)$ 的轨线。$t_f$ 是状态轨线 $X(t)$ 与运动目标集 $M:$ $g_i[X(t_f),t_f]=0$ $g_2[X(t_f),t_f]\le 0$

首次相遇的末时刻。则当 $U^*(t)$ 和 $t_f^*$ 为性能指标泛函最小的最优解，$X^*(t)$ 是对应的最优轨线。必存在不同时为零的常向量 $u$, $v$ 及 $n$ 维向量函数 $\lambda(t)$，使得 $U^*(t)$, $t_f^*$, $X^*(t)$ 和 $\lambda(t)$ 满足下列必要条件：

(i) $X(t)$, $\lambda(t)$ 是规范方程 $\begin{cases} \dot X = \dfrac{\partial H}{\partial \lambda}=f(X,U,t), X(t_0)=X_0 \\ \dot \lambda = -\dfrac{\partial H}{\partial X} \end{cases}$ 的解，其中，$H(X,\lambda,U,t)\triangleq \lambda^T f(X,U,t)$

(ii) 在最优轨线的末端状态变量 $\lambda(t_f)$ 横截于目标集，即 $\lambda(t_f)=\dfrac{\partial S[X(t_f),t_f]}{\partial X(t_f)}+\dfrac{\partial g_i[X(t_f),t_f]}{\partial X(t_f)}u+\dfrac{\partial g_2^T[X(t_f),t_f]}{\partial X(t_f)}v$ 其中，$v_i\ge0$, $v_i g_{2i}[X(t_f),t_f]=0$, $i=1,2,\dots,q$ 并且，末态 $X(t_f)$ 要落在目标集上，即满足 $\begin{cases} g_1[X(t_f),t_f]=0 \\ g_2[X(t_f),t_f]\le0 \end{cases}$

(iii) $H$ 作为 $U(t)\in U$ 的函数，在 $U(t)=U^*(t)$ 时取绝对极小、即 $H[X^*(t),\lambda(t),U^*(t),t]=\min_{U(t)\in U} H[X^*(t),\lambda(t),U(t),t]$

(iv) 在最优轨线的末端 $H$ 应满足 $H[X^*(t_f^*),\lambda(t_f^*),U^*(t_f^*),t_f^*]= -\dfrac{\partial S[X^*(t_f^*),t_f^*]}{\partial t_f}-u^T\dfrac{\partial g_i[X^*(t_f^*),t_f^*]}{\partial t_f}-v^T\dfrac{\partial g_2[X^*(t_f^*),t_f^*]}{\partial t_f}$

(v) 沿最优轨线 $H$ 满足 $H[X(t_f),\lambda(t_f),U(t_f),t_f]=H[X(t_f),\lambda(t_f),U(t_f),t_f]+\int_{t_f}^{\tau}\dfrac{\partial H(X(\tau),\lambda(\tau),U(\tau),\tau)}{\partial \tau}d\tau$

# 二 有积分限制的问题