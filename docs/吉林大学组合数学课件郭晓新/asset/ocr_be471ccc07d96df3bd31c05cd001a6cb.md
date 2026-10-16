# 用生成函数求解递推关系

例 6.4.3 求如下递推关系的生成函数：

$$egin{cases}F_n = F_{n-1} + F_{n-2}\F_0 = F_1 = 1\end{cases}$$

解 设生成函数为

$$G(x)=a_0 + a_1 x + a_2 x^2 + a_3 x^3 + a_4 x^4 + \cdots$$

则

$$-x G(x)=\quad -a_0 x - a_1 x^2 - a_2 x^3 - a_3 x^4 - \cdots$$

$$-x^2 G(x)=\quad\quad -a_0 x^2 - a_1 x^3 - \cdots$$

三式相加并利用递推关系，有

$$(1 - x - x^2) G(x) = a_0 + (a_1 - a_0) x$$