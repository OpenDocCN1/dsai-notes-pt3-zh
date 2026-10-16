# 其它兴趣度度量

+   提升度(lift): A和B两个项集的出现之间的提升度

+   Measure of dependent/correlated events

+   the lift of the association rule A⇒B is defined as

lift(A ⇒ B) = P(A and B) / [P(A)P(B)] = P(B|A) / P(B)

+   lift= 1 A and B are independent

+   lift> 1 the occurrence of A encourages the occurrence of B(正相关)

+   lift< 1 the occurrence of A discourages the occurrence of B (负相关)

the bigger the value of lift,
the stronger the correlation between A and B