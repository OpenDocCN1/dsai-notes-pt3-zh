# 冗余和相关分析

# 数值数据的相关系数

Cov(A, B) = E((A - Ā)(B - B̄)) = (∑_{i=1}^{n} (a_i - Ā)(b_i - B̄)) / n

+   它可被简化为

Cov(A, B) = E(A · B) - Ā B̄

+   Suppose two stocks A and B have the following values in one week: (2, 5), (3, 8), (5, 10), (4, 11), (6, 14).

+   Question: If the stocks are affected by the same industry trends, will their prices rise or fall together?

+   E(A) = (2 + 3 + 5 + 4 + 6) / 5 = 20/5 = 4

+   E(B) = (5 + 8 + 10 + 11 + 14) /5 = 48/5 = 9.6

+   Cov(A,B) = (2×5+3×8+5×10+4×11+6×14)/5 − 4 × 9.6 = 4

+   Thus, A and B rise together since Cov(A, B) > 0.