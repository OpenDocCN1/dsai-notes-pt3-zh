# Bi-Clustering Methods

+   - Real-world data is noisy: Try to find approximate bi-clusters
+   - Methods: Optimization-based methods vs. enumeration methods
+   - Optimization-based methods基于最优的方法
+     - Try to find a submatrix at a time that achieves the best significance as a bi-cluster具有最高显著性得分的子矩阵被识别为双簇
+     - Due to the cost in computation, greedy search is employed to find local optimal bi-clusters
+     - Ex. δ-Cluster Algorithm (Cheng and Church, ISMB’2000)
+   - Enumeration methods枚举的方法
+     - Use a tolerance threshold to specify the degree of noise allowed in the bi-clusters to be mined使用一个容忍阈值指定被挖掘的双簇对噪声的容忍度
+     - Then try to enumerate all submatrices as bi-clusters that satisfy the requirements
+     - Ex. δ-pCluster Algorithm (H. Wang et al.’ SIGMOD’2002, MaPle: Pei et al., ICDM’2003)