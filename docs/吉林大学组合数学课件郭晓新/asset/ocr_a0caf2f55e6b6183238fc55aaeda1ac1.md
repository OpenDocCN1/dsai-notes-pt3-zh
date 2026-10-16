# 用生成函数求解递推关系

故 $a_n = K_1 r_1^n + K_2 r_2^n = K_1 + K_2 \left(\frac{1}{2}\right)^n$

利用整式除法

$\frac{1}{(1-x)(2-x)} = \frac{1}{2-3x+x^2} = \frac{1}{2} + \frac{3}{4}x + \frac{7}{8}x^2 + \cdots$

知 $a_0 = 1/2$, $a_1 = 3/4$ 解得

$K_1 = 1, K_2 = -\frac{1}{2}$

从而

$a_n = 1 - \left(\frac{1}{2}\right)^{n+1}$