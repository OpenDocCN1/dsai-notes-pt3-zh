# 排列数的指数型生成函数

推论 5.4.2 设 $m$ 元多重集 $S = \{r_1 \cdot e_1, r_2 \cdot e_2, \cdots, r_m \cdot e_m\}$，且 $r_1 + r_2 + \cdots + r_m = n$，则 $S$ 的 $k$ 可重排列数 $P_k$ 对应序列 $\{P_k\}$ 的指数型生成函数为

```
$G_e(x) = \prod_{i=1}^{m} \left( \sum_{j=0}^{r_i} \frac{x^{j}}{j!} \right)$
```

其中，$k$ 可重排列数 $P_k$ 为 $G_e(x')$ 展开式中 $x^k / k!$ 系数 $(k = 0,1,2,\cdots)$。

```
$G(x) = \prod_{i=1}^{m} \sum_{j \in \Gamma_i} \frac{x^{j}}{j!}$
```

$\Gamma_1 = \{1,2,\cdots,r_1\}, \Gamma_2 = \{1,2,\cdots,r_2\}, \cdots \Gamma_m = \{1,2,\cdots,r_m\}$