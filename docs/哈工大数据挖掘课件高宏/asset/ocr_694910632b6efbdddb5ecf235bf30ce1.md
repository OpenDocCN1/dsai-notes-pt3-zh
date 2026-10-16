# How to construct a decision tree?(cont.)

+   - 当下列条件之一成立时，划分过程结束：
+     - 所有落入一个节点的实例属于相同的一个类
+       - 该节点成为叶节点，并标注上类标识
+     - 再没有其它属性来划分实例
+       - 该节点成为叶节点，其类标识为落入该节点的多数实例的类标识
+     - There are no samples left