# 生成函数的定义

同理，连续投掷 10 次，其和为 30 的方法数为

 $(x + x^2 + x^3 + x^4 + x^5 + x^6)^{10}$

中 $x^{30}$ 的系数，而

 $(x + x^2 + x^3 + x^4 + x^5 + x^6)^{10}$

 $= x^{10} (1 + x + x^2 + x^3 + x^4 + x^5)^{10} = x^{10} \left( \sum_{k=0}^{\infty} x^k - \sum_{k=6}^{\infty} x^k \right)^{10}$

 $= x^{10} \left( \sum_{k=0}^{\infty} x^k - x^6 \sum_{k=0}^{\infty} x^k \right)^{10} = x^{10} \left( \sum_{k=0}^{\infty} x^k \right)^{10} (1 - x^6)^{10}$

 $= x^{10} (1 - x)^{-10} (1 - x^6)^{10} = x^{10} \cdot \sum_{i=0}^{\infty} \binom{10 - 1 + i}{i} x^{i} \cdot \sum_{j=0}^{10} (-1)^j \binom{10}{j} x^{6j}$