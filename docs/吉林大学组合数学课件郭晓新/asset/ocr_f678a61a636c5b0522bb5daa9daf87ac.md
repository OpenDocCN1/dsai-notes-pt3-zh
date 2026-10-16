# 用生成函数求解递推关系

得 $G(x)=\frac{x}{(1-2x)(1-x)}=\frac{1}{1-2x}-\frac{1}{1-x}$

即有

$G(x)=\sum_{i=1}^{\infty}h_i x^i=\sum_{i=0}^{\infty}(2x)^i-\sum_{i=0}^{\infty}x^i=\sum_{i=0}^{\infty}(2^i-1)x^i$

从而 $h_n=2^n-1$