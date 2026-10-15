# Experiments: Compare CrossClus with

+   - Baseline: Only use the user specified feature
+   - PROCLUS [Aggarwal, et al. 99]: a state-of-the-art subspace clustering algorithm
+     - Use a subset of features for each cluster
+     - We convert relational database to a table by propositionalization
+     - User-specified feature is forced to be used in every cluster
+   - RDBC [Kirsten and Wrobel’00]
+     - A representative ILP clustering algorithm
+     - Use neighbor information of objects for clustering
+     - User-specified feature is forced to be used