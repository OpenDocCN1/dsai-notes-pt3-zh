# FP Growth算法

算法：FP-Growth。
使用 FP 树，通过模式增长挖掘频繁模式。
输入：最小化
■ D：事务数据库。
■ min_sup：最小支持度阈值。
输出：频繁模式的完备集。
方法：
1. 按照以下步骤构造 FP 树：
(a) 扫描事务数据库 D 一次，收集频繁项的集合 F 和它们的支持度计数。对 F 按支持度计数降序排序，结果为频繁项头部表 L。
(b) 创建 FP 树的根节点，以 "null" 标记它。对子 D 中每个事务 Trans，执行：
选择 Trans 中的频繁项，并按 L 中的次序排序。设 Trans 排序后的频繁项序列为 [p|P]，其中 p 是第一个元素，而 P 是剩余元素的列表。调用 insert_tree([p|P], T)。该过程执行情况如下：如果是 T 有子节点 N 使得 N.item_name = p.item_name，则 N 的计数增加 1；否则，创建一新节点 N，将其计数设置为 1，并连接它到父节点 T，并且通过节点链接将 N 连接到具有相同 item_name 的节点。如果 P 非空，则递归地调用 insert_tree(P, N)。
2. FP 树的挖掘通过调用 FP_growth(FP_tree, null) 实现。该过程实现如下。
procedure FP_growth(Tree, α)
(1) if Tree 包含单个节点 P then
(2) for 随着 P 中结点的每个组合 (记作 β)
(3) 产生模式 β∪α，其支持度计数 support_count 等于 β 中结点的最小支持度计数；
(4) else for Tree 的头表中的每个 αi
(5) 产生一个模式 β = αi ∪ α，其支持度计数 support_count = αi.support_count；
(6) 构造 β 的条件模式基，然后构造 β 的条件 FP 树 Treeβ；
(7) if Treeβ ≠ ∅ then
(8) 调用 FP_growth(Treeβ, β);