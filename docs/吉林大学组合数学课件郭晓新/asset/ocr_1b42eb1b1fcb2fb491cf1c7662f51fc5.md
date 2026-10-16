# 递推关系

代入初值

$c + \lg 2 = 2 \lg 2$

得

$c = \lg 2$

所以

$f(n) = \lg 2 \cdot \left(\frac{1}{2}\right)^n + \lg 2 = \lg 2^{1+2^{-n}}$

从而得到

$a_n = 2^{1+2^{-n}}$