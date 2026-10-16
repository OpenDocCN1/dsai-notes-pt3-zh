# 聚类中的属性类型

+   - **Ordinal Variables 序数型变量**
+     - 一个序数型变量即可以是离散的、也可以是连续的
+     - Order is important, e.g., rank
+     - Can be treated like interval-scaled
+       - replace $x_{if}$ by their rank $r_{if} \in \{1, ......, M_f\}$
+       - map the range of each variable onto [0, 1] by replacing $i$-th object in the $f$-th variable by $z_{if} = \frac{r_{if} - 1}{M_f - 1}$
+       - compute the dissimilarity using methods for interval-scaled variables