# 5·5 有限项正交函数级数逼近法——最小积分平方逼近法

对于 $c$ 类问题，设类概密和类概率分别为 $p(\vec{x}|\omega_i)$ 和 $P(\omega_i)$（$i=1,2,\cdots,c$），则混合概密为

$$p(\vec{x})=\sum_{i=1}^{c}P(\omega_i)p(\vec{x}|\omega_i)$$

设对每类的概密 $p(\vec{x}|\omega_i)$ 的估计 $\hat{p}(\vec{x}|\omega_i)$ 用正交函数有限项表示为

$$\hat{p}(\vec{x}|\omega_i)=\sum_{j=1}^{R}C_j^{(i)}\varphi_j(\vec{x})$$