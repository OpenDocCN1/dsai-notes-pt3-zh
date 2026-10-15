# Challenges for Outlier Detection in High-Dimensional Data

+   - **Interpretation of outliers** 离群点的解释
+     - Detecting outliers without saying why they are outliers is not very useful in high-D due to many features (or dimensions) are involved in a high-dimensional data set
+     - E.g., which subspaces that manifest the outliers or an assessment regarding the “outlier-ness” of the objects

+   - **Data sparsity** 数据的稀疏性
+     - Data in high-D spaces are often sparse
+     - The distance between objects becomes heavily dominated by noise as the dimensionality increases

+   - **Data subspaces** 数据子空间
+     - Adaptive to the subspaces signifying the outliers
+     - Capturing the local behavior of data

+   - **Scalable with respect to dimensionality** 关于维度的可伸缩性
+     - # of subspaces increases exponentially