# Catalan数列的生成函数

解 $G^2(x)-G(x)+x=0$，得 $G(x)=\dfrac{1\pm\sqrt{1-4x}}{2}$，则 $G(0)=1,G(0)=0$。

$G(x)=h_0+h_1x+h_2x^2+\cdots=\displaystyle\sum_{i=1}^{\infty}h_i x^i$

因为 $h_0=0$，所以 $G(0)=0$ 满足条件，故舍去 $G(x)=\dfrac{1+\sqrt{1-4x}}{2}$，保留 $G(x)=\dfrac{1-\sqrt{1-4x}}{2}$，利用牛顿二项式定理（定理 3.4.2 pp. 32），有

$\sqrt{1-4x}=1+\displaystyle\sum_{n=1}^{\infty}\frac{\frac12\left(\frac12-1\right)\cdots\left(\frac12-n+1\right)}{n!}(-4)^n x^n$

$=1+\displaystyle\sum_{n=1}^{\infty}\binom{-2}{n}\binom{2n-2}{n-1}x^n$。