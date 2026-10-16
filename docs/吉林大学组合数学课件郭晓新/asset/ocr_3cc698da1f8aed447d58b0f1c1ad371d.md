# 用迭代归纳法求解递推关系及其应用

将上式代入等式（6.5.1），得

$$h(n)=2h(1)h(n-1)+\frac{2(n-3)}{n}h(n-1)=\frac{4n-6}{n}h(n-1),$$

化简得

$$nh(n)=(4n-6)h(n-1).$$

令 $nh(n)=E(n)$，则有

$$\begin{cases}E(n)=(4n-6)\cdot\dfrac{E(n-1)}{n-1}\\E(1)=1.\end{cases}$$