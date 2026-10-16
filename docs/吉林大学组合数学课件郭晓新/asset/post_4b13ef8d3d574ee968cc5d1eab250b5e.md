
## 有禁区的排列问题

例 4.5.3 错位排列问题也可以看作是有禁区的排列问题，其禁区在主对角线上。下面使用定理 4.5.1 来求 \(D_n\)。

解：禁区的棋盘多项式是

\[
R(\square \square \cdots \square)
= \overbrace{R(\square)\cdot R(\square)\cdots R(\square)}^{n}
= (1+x)^n
= 1+\binom{n}{1}x+\binom{n}{2}x^2+\cdots+\binom{n}{n}x^n.
\]

从而得到 \(r_1 = n,\ r_2 = \binom{n}{2},\ \ldots,\ r_n = \binom{n}{n}\)，代入定理 4.5.1 得

\[
D_n = n! - n(n-1)! + \binom{n}{2}(n-2)! - \cdots + (-1)^n\binom{n}{n}\,0!
\]

\[
= n!\left[1-\frac{1}{1!}+\frac{1}{2!}-\cdots+(-1)^n\frac{1}{n!}\right].
\]

定理 4.5.1 的一般形式为

\[
n!-r_1(n-1)!+r_2(n-2)!-\cdots+(-1)^n r_n\cdot0!.
\]

## 作业

- 4.10 和 4.11

## Möbius 反演

- 德国数学家、天文学家 Möbius 于 1832 年发现的经典数论结果。
- 是研究两个整值函数 \(f(n)\) 和 \(g(n)\) 互相表示的问题。

### Möbius 函数

根据数论的知识，对于大于 1 的自然数 \(n\)，有标准的分解形式，即

\[
n=p_1^{\alpha_1}p_2^{\alpha_2}\cdots p_k^{\alpha_k}, \tag{4.6.1}
\]

其中 \(p_1,p_2,\ldots,p_k\) 为 \(k\) 个互不相同的质数。依此为基础，有下面的定义。

**定义 4.6.1**（Möbius 函数 \(\mu(n)\)）定义为

\[
\mu(n)=
\begin{cases}
1, & n=1,\\
0, & \text{若式 (4.6.1) 中存在 } \alpha_i>1,\\
(-1)^k, & \text{若式 (4.6.1) 中 } \alpha_1=\alpha_2=\cdots=\alpha_k=1.
\end{cases}
\]

例如，

\[
\mu(2)=(-1)^1=-1,\quad \mu(9)=\mu(3^2)=0,\quad \mu(10)=\mu(2\times5)=(-1)^2=1.
\]

**定理 4.6.1.** 对任意正整数 \(n\)，有

\[
\sum_{d\mid n}\mu(d)=
\begin{cases}
1, & n=1,\\
0, & n>1.
\end{cases}
\]

其中 \(\sum_{d\mid n}\mu(d)\) 表示让 \(d\) 取遍 \(n\) 的所有正因子而对 \(\mu(d)\) 求和，其中包括因子 \(1\) 和 \(n\)。

**证明：** 当 \(n=1\) 时，由定义知 \(\mu(1)=1\)。

当 \(n>1\) 时，设 \(n\) 的标准质因数分解为 \(n=p_1^{a_1}p_2^{a_2}\cdots p_k^{a_k}\)，并令

\[
n^*=p_1p_2\cdots p_k.
\]

若 \(d\mid n^*\)，则 \(d\mid n\)；若 \(d\mid n\)，但 \(d\nmid n^*\)，则 \(d\) 能被某个质数的平方整除，从而 \(\mu(d)=0\)。

于是，在求和式 \(\sum_{d\mid n}\mu(d)\) 中只要考虑 \(n^*=p_1p_2\cdots p_k\) 的因子。对于那些是 \(n\) 的因子而又不是 \(n^*\) 的因子的数 \(d\)，由于 \(\mu(d)=0\)，就不用考虑了。

\[
\sum_{d\mid n}\mu(d)
= \sum_{\substack{d\mid n\\ d\mid n^*}}\mu(d)+\sum_{\substack{d\mid n\\ d\nmid n^*}}\mu(d)
= \sum_{d\mid n^*}\mu(d).
\]

所以，问题化简为

\[
\sum_{d\mid n}\mu(d)=\sum_{d\mid n^*}\mu(d)
\]

\[
= \mu(1)+\sum_{i=1}^k\mu(p_i)+\sum_{1\le i<j\le k}\mu(p_ip_j)+\cdots+\mu(p_1p_2\cdots p_k)
\]

\[
=1+C_k^1(-1)+C_k^2(-1)^2+\cdots+C_k^k(-1)^k
\]

\[
=(1-1)^k=0.
\]

**例 4.6.1** 关于 Euler 函数 \(\varphi(n)\) 的一个公式如下：

\[
\varphi(n)=n\sum_{d\mid n}\frac{\mu(d)}{d} \tag{4.6.2}
\]

**证明：** 如果 \(n=1\)，

\[
\text{左式}=\varphi(1)=1,\qquad
\text{右式}=\sum_{d\mid 1}\frac{\mu(d)}{d}=\frac{\mu(1)}{1}=1,
\]

等式成立。

若 \(n>1\)，设 \(n=p_1^{\alpha_1}p_2^{\alpha_2}\cdots p_k^{\alpha_k}\)，并令 \(n^*=p_1p_2\cdots p_k\)，则

\[
n\sum_{d\mid n}\frac{\mu(d)}{d}
= n\sum_{d\mid n^*}\frac{\mu(d)}{d}
+ n\sum_{\substack{d\mid n\\ d\nmid n^*}}\frac{\mu(d)}{d}
= n\sum_{d\mid n^*}\frac{\mu(d)}{d}+0
= n\sum_{d\mid n^*}\frac{\mu(d)}{d}.
\]

\[
\begin{aligned}
&= n\left(\mu(1)+\sum_{i=1}^k\frac{\mu(p_i)}{p_i}
+\sum_{1\le i<j\le k}\frac{\mu(p_ip_j)}{p_ip_j}
+\cdots+\frac{\mu(p_1p_2\cdots p_k)}{p_1p_2\cdots p_k}\right)\\
&= n\left(1+\sum_{i=1}^k\frac{(-1)}{p_i}
+\sum_{1\le i<j\le k}\frac{(-1)^2}{p_ip_j}
+\cdots+\frac{(-1)^k}{p_1p_2\cdots p_k}\right)\\
&= n\left(1-\sum_{i=1}^k\frac{1}{p_i}
+\sum_{1\le i<j\le k}\frac{1}{p_ip_j}
-\cdots+\frac{(-1)^k}{p_1p_2\cdots p_k}\right)\\
&= n\left(1-\frac{1}{p_1}\right)\left(1-\frac{1}{p_2}\right)\cdots\left(1-\frac{1}{p_k}\right)
=\varphi(n).
\end{aligned}
\]

**定理 4.6.2（Möbius 反演公式）**：设 \(f(n)\)、\(g(n)\) 是自然数集上的两个函数，则

\[
f(n)=\sum_{d\mid n}g(d) \iff g(n)=\sum_{d\mid n}\mu(d)f\left(\frac nd\right) \tag{4.6.3}
\]

**证明：** 先证必要性。若式 (4.6.3) 左端的等式对自然数 \(n\) 成立，那么它对自然数 \(n/d\) 也应该成立，即将式 \(f(n)=\sum_{d\mid n}g(d)\) 中的 \(n\) 换成 \(n/d\)，有

\[
f(n/d)=\sum_{d_1\mid n/d}g(d_1),
\]

从而有

\[
\sum_{d\mid n}\mu(d)f(n/d)
=\sum_{d\mid n}\mu(d)\left(\sum_{d_1\mid n/d}g(d_1)\right)
=\sum_{d\mid n}\sum_{d_1\mid n/d}\mu(d)g(d_1)
\]

\[
=\sum_{d_1\mid n}\sum_{d\mid n/d_1}\mu(d)g(d_1)
=\sum_{d_1\mid n}g(d_1)\left(\sum_{d\mid n/d_1}\mu(d)\right).
\]

由定理 4.6.1，内层和 \(\sum_{d\mid n/d_1}\mu(d)\) 只有当 \(n/d_1=1\)（即 \(d_1=n\)）时为 1，否则为 0，故原式等于 \(g(n)\)。

### Möbius 反演的应用

**例 4.6.2** 利用 Möbius 反演公式，将 \(n\) 用 Euler 函数 \(\varphi(d)\) 表示。

解：因为

\[
\varphi(n)=n\sum_{d\mid n}\frac{\mu(d)}{d}=\sum_{d\mid n}\mu(d)\frac nd.
\]

Möbius 反演公式：

\[
f(n)=\sum_{d\mid n}g(d)\iff g(n)=\sum_{d\mid n}\mu(d)f\left(\frac nd\right).
\]

令 \(g(n)=\varphi(n)\)，\(f(n)=n\)（从而 \(f(n/d)=n/d\)），那么，由定理 4.6.2 知

\[
f(n)=\sum_{d\mid n}g(d),
\]

故

\[
n=\sum_{d\mid n}\varphi(d). \tag{4.6.4}
\]

式 (4.6.2) 和 (4.6.4) 构成了 \(n\) 与 \(\varphi(n)\) 之间的互为逆变换的关系，即满足 Möbius 反演。

**例 4.6.3** 可重圆排列问题：\(m\) 个相异元素的不重圆排列数为 \((m-1)!\)。

这 \(m\) 个相异元素的可重圆排列数是多少？问题将复杂得多，即从 \(m\) 个相异元素中可重复地取 \(n\) 个构成的圆排列的个数并不能简单地直接推广为 \(m^n/n\)。

例如，设集合 \(A=\{a_1,a_2,\cdots,a_m\}\) 有 \(m\) 个相异元素，当 \(d\mid n\) 时，取 \(d\) 个不同的元素 \(a_1,a_2,\cdots,a_d\) 重复 \(n/d\) 次构成的 \(n\) 个元素的圆排列

\[
\odot\ \underbrace{a_1a_2\cdots a_d\ a_1a_2\cdots a_d\ \cdots\ a_1a_2\cdots a_d}_{\frac nd\text{ 组}}
\]

只能形成 \(d\) 个不同的线排列（\(\odot\) 为上述 \(n\) 个元素首尾相接形成一个圆排列）。
