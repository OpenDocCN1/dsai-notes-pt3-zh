# 生成函数的性质

例 5.2.2 已知\{a_n\}的生成函数为 $A(x)=\frac{2+3x-6x^2}{1-2x}$，求 $a_n$，

解 用部分分式的方法得

$A(x)=\frac{2+3x-6x^2}{1-2x}=\frac{2}{1-2x}+3x,$

$\frac{2}{1-2x}=2\sum_{n=0}^{\infty}2^n x^n=\sum_{n=0}^{\infty}2^{n+1}x^n,$

所以有

$\begin{cases}2^{n+1} & (n\neq1)\\ 2^{2}+3=7 & (n=1).\end{cases}$

$G\{a^n\}=\frac{1}{1-ax}$