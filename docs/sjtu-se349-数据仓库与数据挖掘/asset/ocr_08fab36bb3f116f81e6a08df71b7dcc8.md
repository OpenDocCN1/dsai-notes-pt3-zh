# 支持向量机原理——线性不可分

max  $W(α)=\sum_{i}^{n}α_i - \frac{1}{2}\sum_{i}^{n}\sum_{j}^{n} y_i y_j α_i α_j k(x_i, x_j)$

s.t.  $\sum_{i=1}^{n} y_i α_i = 0$

$\forall i: 0 \le α_i \le C,\ i=1,2,...,n$

$k(x, y)=φ(x)·φ(y)$