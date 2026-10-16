# 5.1 基本概念

+   - 项(item)
+     - 一个字符串序列，描述一个有意义的对象
+   - 项集I(itemset): 项的集合
+     - I={i1, i2, ......, im}，其中i为一个item。
+   - 任务相关的数据D是数据库事务(交易)的集合，其中每个事务T是项的集合，使得T⊆I。
+     - 每一个事务有一个标识符，称作TID。
+   - 设A是一个项集，事务T包含A，当且仅当 A⊆ T。

|  |  |  |  |  |
|---|---|---|---|---|
| T1 | Milk | bread | apple |  |
| T2 | Milk | bread | sugar | eggs |
| T3 | milk | bread | butter |  |
| T4 | sugar | eggs |  |  |
| ... | .... |  |  |  |