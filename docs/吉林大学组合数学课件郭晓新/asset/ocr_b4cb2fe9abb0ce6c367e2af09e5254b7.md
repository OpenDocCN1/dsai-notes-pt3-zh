# 无序分解

还可以这样证明: $B(n,k)=B_k(n)-B_{k-1}(n)$, 所以

$$\sum_{n=0}^{\infty} B(n,k)x^n = \sum_{n=0}^{\infty} (B_k(n)-B_{k-1}(n))x^n$$

$$= \prod_{i=1}^k \frac{1}{1-x^i} - \prod_{i=1}^{k-1} \frac{1}{1-x^i}$$

$$= \frac{1}{(1-x)(1-x^2)\cdots(1-x^k)} - \frac{1-x^k}{(1-x)(1-x^2)\cdots(1-x^k)}$$

$$= \frac{x^k}{(1-x)(1-x^2)\cdots(1-x^k)} \quad (5.7.6)$$

若$n<k$, 则$B(n,k)=0$, 因此当$n=0,1,2,...,k-1$, 它们对应的生成函数的系数为零, 所以

$$\sum_{n=k}^{\infty} B(n,k)x^n = \sum_{n=0}^{\infty} B(n,k)x^n$$