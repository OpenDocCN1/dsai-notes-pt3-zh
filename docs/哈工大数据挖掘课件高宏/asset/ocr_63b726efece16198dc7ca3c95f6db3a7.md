# How to construct a decision tree?

+   - a tree is constructed in a top-down recursive divide-and-conquer manner
+     - 首先，所有训练实例位于根节点
+     - 所有属性都是可分类的属性（若为连续值，则事先离散化）
+     - 根据选择的属性，对实例进行划分
+       - a selected attribute is also called a split or a test
+     - 可以用基于启发式或统计的方法来选择划分属性 (e.g. information gain)