
## 组合数的生成函数

+   - {x₁=1, x₂=7;}
+   - {x₁=3, x₂=6;}
+   - {x₁=5, x₂=5;}
+   - {x₁=7, x₂=4;}
+   - {x₁=9, x₂=3;}
+   - {x₁=11, x₂=2;}
+   - {x₁=13, x₂=1;}
+   - {x₁=15, x₂=0.}

一般说来，不定方程

p₁x₁ + p₂x₂ + ⋯ + pₖ · xₖ = r

(p₁,p₂,…,pₖ为正整数)

的非负整数解的个数设为 a_r, 考虑下面的函数

A(y)=[1+y^{p1}+(y^{p1})^2+⋯]·[1+y^{p2}+(y^{p2})^2+⋯]⋯[1+y^{pk}+(y^{pk})^2+⋯], A(y)的展开式的每一项是形式：

y^{p1·x1}·y^{p2·x2}⋯⋯y^{pk·xk}=y^{p1·x1+p2·x2+⋯+pk·xk}

其中x1,x2,…,xk为非负整数所以A(y)的展开式中y^r的系数就是方程p1x1+p2x2+⋯+pkxk=r的非负整数解的个数

把A(y)变形为

A(y) = 1 / [(1 - y^{p₁})(1 - y^{p₂})⋯(1 - y^{p_k})],
这就是{a_r}的生成函数

不难看出当 p₁ = p₂ = ⋯ = p_k = 1 时 A(y) = 1 / (1 - y)^k

就是方程 x₁ + x₂ + ⋯ x_k = r 的非负整数解个数 {a_r} 的生成函数.

方法二：用排列组合法。先从 *n* 双鞋中选取 *r* 双，共有 $C(n,r)$，再从此 *r* 双中每双取出一只，由乘法原理，即得

$C(n,r)\times 2\times 2\cdots\times 2 = C(n,r)2^{r}$

方法三：先取出 *k* 只左脚的鞋，再在其余 $n-k$ 双鞋中取出 $r-k$ 只右脚的鞋，用乘法原理得 $C(n,k)C(n-k,r-k)\,(k=0,1,\cdots,r)$，则总的取法为：

$C(n,0)C(n-0,r)+C(n,1)C(n-1,r-1)+C(n,2)C(n-2,r-2)+\cdots$
$+C(n,r)C(n-r,r-r)$
$=2^{r}C(n,r)$

例：设 $S = \{\infty\cdot e_1, \infty\cdot e_2, \cdots, \infty\cdot e_k\}$，求 $S$ 的每个元素只出现偶数次的 $r$−组合数 $a_r$。
解：令 $\{a_r\}$ 的生成函数是 $A(y)$，则
$A(y) = (1 + y^2 + y^4 + \cdots)^k = \frac{1}{(1 - y^2)^k}$
$= 1 + k y^2 + \binom{k+1}{2} y^4 + \cdots + \binom{k+n-1}{n} y^{2n} + \cdots$
$= \sum_{n=0}^{\infty} \binom{k+n-1}{n} y^{2n}$

A(y) = (1 + y² + y⁴ + ⋯)ᵏ = 1 / (1 - y²)ᵏ
= 1 + k y² + (k+1 choose 2) y⁴ + ⋯ + (k+n-1 choose n) y²ⁿ + ⋯
= Σₙ=0^∞ (k+n-1 choose n) y²ⁿ

所以有

aᵣ = { (k+n-1 choose n)  r = 2n,  (n = 0,1,⋯)
       0                r = 2n+1. }

用生成函数的方法也可以求解不定方程的整数解的个数。

## 排列数的指数型生成函数

$n$元集合的$k$组合数为$C(n,k)$，按5.5.1小节中方法构成的生成函数为：

$$\sum_{k=0}^{\infty}\binom{n}{k}x^k$$

如果把基底函数$x^k$改换成$\frac{x^k}{k!}$，则

$$\sum_{k=0}^{\infty}\binom{n}{k}x^k=\sum_{k=0}^{\infty}k!\cdot C(n,k)\cdot\frac{x^k}{k!}=\sum_{k=0}^{\infty}P(n,k)\cdot\frac{x^k}{k!}=(1+x)^n。$$

这启发人们引入指数型生成函数的概念。

数列{$a_0,a_1,a_2,\cdots$}的指数型生成函数定义为形式幂级数

$$\sum_{k=0}^{\infty}a_k\frac{x^k}{k!}$$

定理 5.4.1 若元素 e₁ 可重复 α₁, α₂, … 次，元素 e₂ 可重复 β₁, β₂, … 次，元素 eₘ 可重复 λ₁, λ₂, … 次，则 m 元集的这种 k 可重排列数 Pₖ 对应序列 {Pₖ} 的生成函数为

G(x) = Σₖ Pₖ xᵏ/k! = Σᵢ₌₁^∞ (x^{αᵢ}/αᵢ!) Σᵢ₌₁^∞ (x^{βᵢ}/βᵢ!) … Σᵢ₌₁^∞ (x^{λᵢ}/λᵢ!)

上式右端等于 Σₖ Pₖ xᵏ/k! = Σₖ ( Σ_{αᵢ₁+βᵢ₂+⋯+λᵢₘ=k} k! / (αᵢ₁! βᵢ₂! ⋯ λᵢₘ!) ) xᵏ/k!

定理 3.2.3 多重集合 M = {αᵢ₁·a₁, βᵢ₂·a₂, …, λᵢₘ·aₙ} 的全排列数为

(αᵢ₁ + βᵢ₂ + ⋯ + λᵢₘ)! / (αᵢ₁! βᵢ₂! ⋯ λᵢₘ!) = k! / (αᵢ₁! βᵢ₂! ⋯ λᵢₘ!).
(pp.20)

由多项式系数的组合学意义知，$k!/(\alpha_{i_1}!+\beta_{i_2}!+\cdots+\lambda_{i_m}!)$  正是元素$e_1$出现$\alpha_{i_1}$次，元素$e_2$出现$\beta_{i_2}$次，元素$e_m$出现$\lambda_{i_m}$次的 $k$ 可重排列数。故按所有可能的$(\alpha_{i_1}+\beta_{i_2}+\cdots+\lambda_{i_m}=k)$求和，即得总的 $k$ 排列数$P_k$。

证明 将和积式展开，得到形如

\frac{x^{\alpha_{i1}}}{\alpha_{i1}!}\cdot\frac{x^{\beta_{i2}}}{\beta_{i2}!}\cdots\frac{x^{\lambda_{im}}}{\lambda_{im}!}=\frac{x^{\alpha_{i1}+\beta_{i2}+\cdots+\lambda_{im}}}{\alpha_{i1}!\beta_{i2}!\cdots\lambda_{im}!}

的项，令 $\alpha_{i1}+\beta_{i2}+\cdots+\lambda_{im}=k\quad(i=1,2,\cdots,n)$，故有

\frac{x^{k}}{\alpha_{i1}!\beta_{i2}!\cdots\lambda_{im}!}=\frac{k!}{\alpha_{i1}!\beta_{i2}!\cdots\lambda_{im}!}\cdot\frac{x^{k}}{k!}

若从第一个括号取出 $\frac{x^{\alpha_{i1}}}{\alpha_{i1}!}$ 项，从第二个括号中取出 $\frac{x^{\beta_{i2}}}{\beta_{i2}!}$ 项，...，从第 k 个括号

号中取出 $\frac{x^{\lambda_{im}}}{\lambda_{im}!}$，且恰有 $\alpha_{i1}+\beta_{i2}+\cdots+\lambda_{im}=k\quad(i=1,2,\cdots,n)$，则它们的乘积形式

\frac{x^{\alpha_{i1}}}{\alpha_{i1}!}\cdot\frac{x^{\beta_{i2}}}{\beta_{i2}!}\cdots\frac{x^{\lambda_{im}}}{\lambda_{im}!}=\frac{x^{\alpha_{i1}+\beta_{i2}+\cdots+\lambda_{im}}}{\alpha_{i1}!\beta_{i2}!\cdots\lambda_{im}!}

满足 α_{i1} + β_{i2} + ⋯ + λ_{im} = k (i=1,2,⋯,n) 此方程的解有多个，这些解都将成为 x^k / k! 的系数。

的系数。根据加法原则， x^k / k! 的系数应为

\left( \sum_{\alpha_{i_1} + \beta_{i_2} + \cdots + \lambda_{i_m} = k} \frac{k!}{\alpha_{i_1}! \beta_{i_2}! \cdots \lambda_{i_m}!} \right)

下面只要证明展开式中 x^k / k! 的系数就是满足限定条件的 k 可重排列数即可。

首先，对于满足限定条件的每个 k 可重排列，设其中元素 e1 出现 α_i 次，元素 e2 可重复 β_i 次，元素 e_m 可重复 λ_i_m 次(i=1, 2, ...), 则 (α_i, β_i, ..., λ_i_m) 就是方程 α_i + β_i + ⋯ + λ_i_m = k (i=1,2,⋯,n) 的一个解。
