# 错位排列

对任意的整数 $k$, $1 \le k \le n$, 有

$|A_{i_1} \cap A_{i_2} \cap \cdots \cap A_{i_k}| = (n - k)!,$

其中 $i_1, i_2, \cdots i_k$ 是 $\{1,2,\cdots,n\}$ 的一个 $k$ 一组合。

由容斥原理得

$D_n = n! - \binom{n}{1}(n-1)! + \binom{n}{2}(n-2)! - \cdots + (-1)^n \binom{n}{n} \cdot 0!$

$= n! - \frac{n!}{1!} + \frac{n!}{2!} - \cdots + (-1)^n \frac{n!}{n!} = n!\left(1 - \frac{1}{1!} + \frac{1}{2!} - \cdots + (-1)^n \frac{1}{n!}\right)$

例如 $D_4 = 4!\left[1 - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \frac{1}{4!}\right] = 12 - 4 + 1 = 9$。