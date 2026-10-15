

## 强规则不一定是有趣的

- 假设对分析涉及购买计算机游戏和录像的AllElectronics的事务感兴趣
- 设game表示包含计算机游戏的事务，而video表示包含录像的事务。在所分析的10000个事务中，数据显示6000个顾客事务包含计算机游戏，7500个事务包含录像，而4000个事务同时包含计算机游戏和录像
- 假设发现关联规则的数据挖掘程序在该数据上运行，使用最小支持度30%，最小置信度60%
  buys(X,"computer games") ⇒ buys(X,"videos")
  [ support = 40% , confidence = 66% ]
- 虽然满足最小支持度和最小置信度阈值，然而规则是误导，因为购买录像的概率是75%比66%还高。事实上，计算机游戏和录像是负相关的，因为买一种实际上降低购买另一种的可能性。不完全理解这种现象，容易根据规则做出不明的商务决定
- 表明规则的置信度有一定的欺骗性，它并不度量A与B之间相关和蕴涵的实际强度（或缺乏强度），寻求支持度—置信度框架的替代，对挖掘有趣的数据联系可能是有用的

## 从关联分析到相关分析

使用相关性度量来扩充关联规则的支持度-置信度框架

— 相关规则不仅用支持度和置信度度量，而且还用项集A和B之间的相关性度量：相关规则

A⇒B [support, confidence, correlation]

- • 有许多不同的相关性度量可供选择

## 第一种相关性度量：提升度lift

- *play basketball ⇒ eat cereal* [40%, 66.7%] is misleading
  — The overall % of students eating cereal is 75% > 66.7%.

- *play basketball ⇒ not eat cereal* [20%, 33.3%] is more accurate, although with lower support and confidence

- Measure of dependent/correlated events: lift

lift = P(A∪B) / P(A)P(B)

lift(B, C) = 2000/5000 / (3000/5000 * 3750/5000) = 0.89

lift(B, ¬C) = 1000/5000 / (3000/5000 * 1250/5000) = 1.33

| | Basketball | Not basketball | Sum (row) |
|---|---|---|---|
| Cereal | 2000 | 1750 | 3750 |
| Not cereal | 1000 | 250 | 1250 |
| Sum(col.) | 3000 | 2000 | 5000 |

## 第二种相关性度量：卡方计算

| | Play chess | Not play chess | Sum (row) |
|---|---|---|---|
| Like science fiction | 250(90) | 200(360) | 450 |
| Not like science fiction | 50(210) | 1000(840) | 1050 |
| Sum(col.) | 300 | 1200 | 1500 |

Play chess Like science fiction
$e_{11} = \frac{count(\ ) \times count(\ )}{n} = \frac{300 \times 450}{1500} = 90$

- $\chi^2$(卡方)卡方计算(括号中的数字是根据两类的数据分布预期的)

$\chi^2 = \frac{(250-90)^2}{90} + \frac{(50-210)^2}{210} + \frac{(200-360)^2}{360} + \frac{(1000-840)^2}{840} = 507.93$

- 对于自由度1，在0.001的置信水平下，拒绝假设的值是10.828（取自$\chi^2$分布上百分点表，参见统计学教科书），由于计算的值大于该值，因此我们可以拒绝Play chess与Like science fiction是独立的假设，并断言对于给定的人群，这两个属性是（强）相关的。

## 提升度和 χ² 是好的检测相关性的方法吗？

- 支持度和置信度不能说明相关性
- 超过20种度量兴趣度的方法被提出 (see Tan, Kumar, Sritastava @KDD’02)
- Which are good ones?

| symbol | measure | range | formula |
|---|---|---|---|
| φ | φ-coefficient | -1 ... 1 | $\frac{P(A,B)-P(A)P(B)}{\sqrt{P(A)P(\bar A)(1-P(A))(1-P(B))}}$ |
| Q | Yule's Q | -1 ... 1 | $\frac{P(A,B)P(\bar A,\bar B)-P(A,\bar B)P(\bar A,B)}{P(A,B)P(\bar A,\bar B)+P(A,\bar B)P(\bar A,B)}$ |
| Y | Yule's Y | -1 ... 1 | $\frac{\sqrt{P(A,B)P(\bar A,\bar B)}-\sqrt{P(A,\bar B)P(\bar A,B)}}{\sqrt{P(A,B)P(\bar A,\bar B)}+\sqrt{P(A,\bar B)P(\bar A,B)}}$ |
| k | Cohen's | -1 ... 1 | $P(A,B)+P(\bar A,\bar B)-P(A)P(B)-P(\bar A)P(\bar B)$ |
| PS | Piatetsky-Shapiro's | -0.25 ... 0.25 | $P(A,B)-P(A)P(B)$ |
| F | Certainty factor | -1 ... 1 | $\max\left(\frac{P(B|A)-P(B)}{1-P(B)},\frac{P(A|B)-P(A)}{1-P(A)}\right)$ |
| AV | added value | -0.5 ... 1 | $\max(P(B|A)-P(B),P(A|B)-P(A))$ |
| K | Klosgen's Q | 0.33 ... 0.38 | $\sqrt{P(A,B)}\max(P(B|A),P(A|B))P(B),P(A|B)P(A))$ |
| g | Goodman-kruskal's | 0 ... 1 | $\frac{\sum_i \max_j P(A_j,B_i)+\sum_j \max_i P(A_j,B_i)-\max_i P(A_i)-\max_j P(B_j)}{2-\max_i P(A_i)-\max_j P(B_j)}$ |
| M | Mutual Information | 0 ... 1 | $\frac{\sum_{i,j} P(A_i,B_j)\log\frac{P(A_i,B_j)}{P(A_i)P(B_j)}}{\min(-\sum_i P(A_i)\log P(A_i),-\sum_j P(B_j)\log P(B_j))}$ |
| J | J-Measure | 0 ... 1 | $\max(P(A,B)\log\frac{P(A,B)}{P(A)P(B)}+P(A\bar B)\log\frac{P(A\bar B)}{P(A)P(\bar B)})$ |
| G | Gini index | 0 ... 1 | $\frac{P(A,B)\log\frac{P(A,B)}{P(A)P(B)}+P(\bar A,B)\log\frac{P(\bar A,B)}{P(\bar A)P(B)}}{...}$ |
| s | support | 0 ... 1 | $P(A,B)$ |
| c | confidence | 0 ... 1 | $\max(P(B|A),P(A|B))$ |
| L | Laplace | 0 ... 1 | $\frac{\max(NP(A,B)+1,2)}{N P(A)+1+2}$ |
| IS | Cosine | 0 ... 1 | $\frac{P(A,B)}{\sqrt{P(A)P(B)}}$ |
| γ | coherence(Jaccard) | 0 ... 1 | $\frac{P(A,B)}{P(A)+P(B)-P(A,B)}$ |
| α | all_confidence | 0 ... 1 | $\frac{P(A,B)}{\max(P(A),P(B))}$ |
| o | odds ratio | 0 ... ∞ | $\frac{P(A,B)P(\bar A,\bar B)}{P(A,\bar B)P(\bar A,B)}$ |
| V | Conviction | 0.5 ... ∞ | $\max\left(\frac{P(A)P(B)}{P(A,B)},\frac{P(B)P(\bar A)}{P(\bar A,B)}\right)$ |
| λ | lift | 0 ... ∞ | $\frac{P(A,B)}{P(A)P(B)}$ |
| S | Collective strength | 0 ... ∞ | $\frac{P(A,B)+P(\bar A,\bar B)}{P(A)P(B)+P(\bar A)P(\bar B)}\times\frac{1-P(A)P(B)-P(\bar A)P(\bar B)}{1-P(A,B)-P(\bar A,\bar B)}$ |
| χ² | χ² | 0 ... ∞ | $\frac{\sum_{i,j}\frac{(P(A_i,B_j)-P(A_i)P(B_j))^2}{P(A_i)P(B_j)}}{...}$ |

