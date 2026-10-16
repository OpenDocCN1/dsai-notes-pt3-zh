# 冗余数据的处理

+   - 冗余数据 Redundant data（集成多个数据库时出现）
+   - 目标识别：同一个属性在不同的数据库中有不同的名称
+   - 衍生数据：一个属性值可由其他属性推导得出, e.g., 年收入
+   - 心中的集成多个来源的数据可以帮助检测和避免数据集中的冗余不一致，显示数据控制的准确度和质量

# 检测冗余数据：相关分析

+   - 相关分析 correlation analysis/协方差分析 covariance analysis
+   - 可用于检测冗余数据
+   - Correlation coefficient (also called Pearson's product moment coefficient)
+   - 相关系数（皮尔逊相关系数）
+     r_AB = Σ_i (a_i - Ā)(b_i - B̄) / (n-1)σ_A σ_B = Σ_i (a_i - Ā)(b_i - B̄) / (n-1)σ_A σ_B
+     *其中，Σ_i (a_i - Ā)(b_i - B̄) 是 A 和 B 的协方差，σ_A 和 σ_B 分别是标准差。 Σ(a_i - Ā)(b_i - B̄) 是 AB 的 cross-product (2)
+   - If r_AB > 0, A and B 随同增加 (A's values increase as B's). 值越大相关程度越高
+   - r_AB = 0: 不相关; r_AB < 0: 负相关

# 相关性的视觉评价

![](bbox=[0.05, 0.38, 0.45, 0.62])

# 相关(线性关系)

+   - 相关测量的是对象的线性关系
+   - To compute correlation, we standardize data objects, A and B, and then take their dot product
+   - a'_k = (a_k - mean(A)) / std(A)
+   - b'_k = (b_k - mean(B)) / std(B)
+   - correlation(A, B) = A' • B'

# 协方差 Covariance (Numeric Data)

+   - Covariance is similar to correlation
+     Cov(A, B) = E[(A - Ā)(B - B̄)] = Σ_{i=1}^n (a_i - Ā)(b_i - B̄) / n
+     Correlation coefficient: r_AB = Cov(A, B) / (σ_A σ_B)
+     *其中 A 和 B 分别为 A 和 B 上的均值。A 和 B 分别为各自标准差
+   - 正协方差: If Cov_AB > 0, 则 A 和 B 同时增加大于预期值.
+   - 负协方差: If Cov_AB < 0, 则如果 A 增加, B 则更可能小于其预期值.
+   - Independence: Cov_AB = 0 but the converse is not true:
+     Some pairs of random variables may have a covariance of 0 but are not independent. Only under some additional assumptions (e.g., the data follow multivariate normal distributions) does a covariance of 0 imply independence

# Co-Variance: An Example

+   - Cov(A, B) = E[(A - Ā)(B - B̄)] = Σ_{i=1}^n (a_i - Ā)(b_i - B̄) / n
+     It can be simplified in computation as
+     Cov(A, B) = E[A·B] - Ā B̄
+   - 两个股票 A 和 B 一周内的价格如下 (2, 5), (3, 8), (5, 10), (4, 11), (6, 14).
+   - 如果股票是由同行或同趋势影响, 它们的价值将一起上升或下降?
+   - E(A) = (2 + 3 + 5 + 4 + 6)/5 = 20/5 = 4
+   - E(B) = (5 + 8 + 10 + 11 + 14)/5 = 48/5 = 9.6
+   - Cov(A,B) = [(2×5 + 3×8 + 5×10 + 4×11 + 6×14)/5 - 4 × 9.6 = 4
+   - Thus, A and B rise together since Cov(A, B) > 0.

# 相关分析 (名义数据 Nominal Data)

+   - X2 (chi-square) test 开始检验
+   - σ_ij 是(a_i,b_j)的观察频度（实际计数）
+   - e_ij 是(a_i,b_j)的期望频度
+   - N 横截元素的个数
+     χ² = Σ_i Σ_j (σ_ij - e_ij)² / e_ij
+     e_ij = count(A = a_i) * count(B = b_j) / N
+   - X2 值越大和大的可能性大
+   - X2 值越小越接近零, 其实际值与期望值差异最大的相
+   - 相关不意味着因果关系

# Chi-Square 卡方值计算: 例子

| | Play chess | Not play chess | Sum (row) |
|---|---|---|---|
| 看看小说 | 250(90) | 200(360) | 450 |
| 不看小说 | 50(210) | 1000(840) | 1050 |
| Sum(col) | 300 | 1200 | 1500 |

e_ij = count(行小计)*count(下侧) / N = 450 * 300 / 1500 = 90
X² (chi-square) 计算中每个变量为期望值, 每个个别的实际值与期望值计算差异
χ² = (250-90)²/90 + (50-210)²/210 + (200-360)²/360 + (1000-840)²/840 = 507.93
结论表明 fiction #play chess 关联