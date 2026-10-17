# 5.4 概密的窗函数估计法

# Parzen窗法

估计量 $\hat{p}_N(\vec{x})$ 是一随机变量，它依赖于随机的训练样本，所以估计量的性能只能用统计性质表示。

在满足下列条件下 $\hat{p}_N(\vec{x})$ 是渐近无偏估计、均方收敛、均方逼近($\vec{x}$)、且是渐近正态分布。

+   (1) 概密 $p(x)$ 在 $x$ 处连续

+   (2) 窗函数满足下列条件

+   ① $\varphi(\vec{u}) \ge 0$

+   ② $\int \varphi(\vec{u}) d\vec{u} = 1$

+   ③ $\sup_{\vec{u}} \varphi(\vec{u}) < \infty$

+   ④ $\lim_{\|\vec{u}\|\to\infty} \varphi(\vec{u}) \prod_{i=1}^{n} u_i = 0$