# 容斥原理

为了书写方便，引入如下的记号：

$$W(0)=|S|$$

$$W(1)=\sum_{i=1}^{m}|A_i|$$

$$W(2)=\sum_{1\le i<j\le m}|A_i\cap A_j|$$

$\cdots\cdots$

$$W(m)=\sum|A_1\cap A_2\cap\cdots\cap A_m|$$

则定理4.1.1的公式可写成：

$$|\overline{A_1}\cap\overline{A_2}\cap\cdots\cap\overline{A_m}|\models W(0)-W(1)+W(2)-W(3)+\cdots$$

$$\qquad\qquad\qquad\qquad\qquad\qquad\qquad\qquad +(-1)^mW(m)$$