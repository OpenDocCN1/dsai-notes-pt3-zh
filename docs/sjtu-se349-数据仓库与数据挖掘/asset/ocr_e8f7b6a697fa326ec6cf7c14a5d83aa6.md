# Categorization of Constraints

+   聚类分析涉及三个基本方面：作为簇实例的对象、作为对象群的簇和对象之间的相似性。因此，根据约束作用于何处对约束分类，有三种类型：
+   — 实例上的约束
+   — 簇上的约束
+   — 相似性度量上的约束

+   Constraints on instances: specifies how a pair or a set of instances should be grouped in the cluster analysis
+   — Must-link vs. cannot link constraints
+     • must-link(x, y): x and y should be grouped into one cluster
+   — Constraints can be defined using variables, e.g.,
+     • cannot-link(x, y) if dist(x, y) > d

+   Constraints on clusters: specifies a requirement on the clusters
+   — E.g., specify the min # of objects in a cluster, the max diameter of a cluster, the shape of a cluster (e.g., a convex凸面的), # of clusters (e.g., k)

+   Constraints on similarity measurements: specifies a requirement that the similarity calculation must respect
+   — E.g., driving on roads, obstacles (e.g., rivers, lakes)

+   Issues: Hard vs. soft constraints; conflicting or redundant constraints