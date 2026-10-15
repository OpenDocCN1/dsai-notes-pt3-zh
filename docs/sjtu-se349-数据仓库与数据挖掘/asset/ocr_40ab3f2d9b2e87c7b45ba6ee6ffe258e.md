# 卡方计算: 实例

| | Play chess | Not play chess | Sum (row) |
|---|---|---|---|
| Like science fiction | 250(90) | 200(360) | 450 |
| Not like science fiction | 50(210) | 1000(840) | 1050 |
| Sum(col.) | 300 | 1200 | 1500 |

Play chess Like science fiction
$e_{11} = \frac{count(\ ) \times count(\ )}{n} = \frac{300 \times 450}{1500} = 90$

+   - X²(卡方)卡方计算(括号中的数字是根据两类的数据分布预期的)

$\chi^2 = \frac{(250-90)^2}{90} + \frac{(50-210)^2}{210} + \frac{(200-360)^2}{360} + \frac{(1000-840)^2}{840} = 507.93$

+   - 对于自由度1，在0.001的置信水平下，拒绝假设的值是10.828（取自X²分布上百分点表，参见统计学教科书），由于计算的值大于该值，因此我们可以拒绝Play chess与Like science fiction是独立的假设，并断言对于给定的人群，这两个属性是（强）相关的。