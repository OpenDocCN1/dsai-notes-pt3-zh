# 由训练元组归约决策树的基本算法

**算法：** `Generate_decision_tree`：由数据分区中的训练元组产生决策树。

**输入：**

+   - 数据分区 $D$，训练元组和它们对应类标号的集合。
+   - `attribute_list`，候选属性的集合。
+   - `Attribute_selection_method`，一个确定“最好地”划分数据元组为个体类的分裂准则的过程。这个准则的分裂属性（`splitting_attribute`）和分裂点或划分子集组成。

**输出：** 一棵决策树。

**方法：**

```
（1）创建一个结点 N；
（2）if D 中的元组都在同一类 C 中 then
（3）　返回 N 作为叶结点，标类 C；
（4）else if attribute_list 为空 then
（5）　返回 N 作为叶结点，标记为 D 中的多数类；
（6）使用 Attribute_selection_method(D, attribute_list)，找出“最好”的 splitting_criterion；
（7）用 splitting_criterion 标记结点 N；
（8）if splitting_attribute 是离散值的，并且允许多路划分 then
（9）　attribute_list ← attribute_list − splitting_attribute;
（10）for splitting_criterion 的每个输出 j
　　　// 划分元组并对每个分区产生子树
（11）　设 D_j 是由满足输出 j 的数据元组的集合；
（12）　if D_j 为空 then
（13）　　加一个树叶结点，标记为 D 中的多数类；
（14）　else 加一个由 Generate_decision_tree(D_j, attribute_list) 返回的结点到 N；
　　　endif
（15）返回 N；
```