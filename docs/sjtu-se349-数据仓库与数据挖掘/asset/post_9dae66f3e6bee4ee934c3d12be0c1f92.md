
## Heuristic Search for Pertinent Features

### Overall procedure
- 1. Start from the user-specified feature
- 2. Search in neighborhood of existing pertinent features
- 3. Expand search range gradually

User hint

Target of clustering
- Tuple ID propagation is used to create multi-relational features
- IDs of target tuples can be propagated along any join path, from which we can find tuples joinable with each target tuple

![](img/6d25e92eb0bd56a22c311279c19b06b4_1380_0.png)

## Clustering with Multi-Relational Features

Given a set of L pertinent features $f_1, ..., f_L$, similarity between two tuples

$$\operatorname{sim}(t_1, t_2) = \sum_{i=1}^{L} \operatorname{sim}_{f_i}(t_1, t_2) \cdot f_i.weight$$

- Weight of a feature is determined in feature search by its similarity with other pertinent features

Clustering methods
- CLARANS [Ng & Han 94], a scalable clustering algorithm for non-Euclidean space
- K-means
- Agglomerative hierarchical clustering

## Experiments: Compare CrossClus with
- Baseline: Only use the user specified feature
- PROCLUS [Aggarwal, et al. 99]: a state-of-the-art subspace clustering algorithm
  - Use a subset of features for each cluster
  - We convert relational database to a table by propositionalization
  - User-specified feature is forced to be used in every cluster
- RDBC [Kirsten and Wrobel’00]
  - A representative ILP clustering algorithm
  - Use neighbor information of objects for clustering
  - User-specified feature is forced to be used

## Measure of Clustering Accuracy
- Accuracy
  - Measured by manually labeled data
  - We manually assign tuples into clusters according to their properties (e.g., professors in different research areas)
  - Accuracy of clustering: Percentage of pairs of tuples in the same cluster that share common label
  - This measure favors many small clusters
  - We let each approach generate the same number of clusters

## DBLP Dataset

Clustering Accuracy - DBLP

![](img/6d25e92eb0bd56a22c311279c19b06b4_1384_0.png)

## Chapter 11. Advanced Cluster Analysis
- Probability Model-Based Clustering
  基于概率模型的聚类
- Clustering High-Dimensional Data
  聚类高维数据
- Clustering Graphs and Network Data
  聚类图和网络数据
- Clustering with Constraints Grid-Based Methods
  具有约束的聚类
- Summary
  小结

## Summary
- Probability Model-Based Clustering
  - Fuzzy clustering
  - Probability-model-based clustering
  - The EM algorithm
- Clustering High-Dimensional Data
  - Subspace clustering: bi-clustering methods
  - Dimensionality reduction: Spectral clustering
- Clustering Graphs and Network Data
  - Graph clustering: min-cut vs. sparsest cut
  - High-dimensional clustering methods
  - Graph-specific clustering methods, e.g., SCAN
- Clustering with Constraints
  - Constraints on instance objects, e.g., Must link vs. Cannot Link
  - Constraint-based clustering algorithms

## References (I)
- R. Agrawal, J. Gehrke, D. Gunopulos, and P. Raghavan. Automatic subspace clustering of high dimensional data for data mining applications. *SIGMOD'98*
- C. C. Aggarwal, C. Procopiuc, J. Wolf, P. S. Yu, and J.-S. Park. Fast algorithms for projected clustering. *SIGMOD'99*
- S. Arora, S. Rao, and U. Vazirani. Expander flows, geometric embeddings and graph partitioning. *J. ACM*, 56:5:1–5:37, 2009.
- J. C. Bezdek. *Pattern Recognition with Fuzzy Objective Function Algorithms*. Plenum Press, 1981.
- K. S. Beyer, J. Goldstein, R. Ramakrishnan, and U. Shaft. When is "nearest neighbor" meaningful? *ICDT'99*
- Y. Cheng and G. Church. Biclustering of expression data. *ISMB'00*
- I. Davidson and S. S. Ravi. Clustering with constraints: Feasibility issues and the k-means algorithm. *SDM'05*
- I. Davidson, K. L. Wagstaff, and S. Basu. Measuring constraint-set utility for partitional clustering algorithms. *PKDD'06*
- C. Fraley and A. E. Raftery. Model-based clustering, discriminant analysis, and density estimation. *J. American Stat. Assoc.*, 97:611–631, 2002.
- F. H. Höppner, F. Klawonn, R. Kruse, and T. Runkler. *Fuzzy Cluster Analysis: Methods for Classification, Data Analysis and Image Recognition*. Wiley, 1999.
- G. Jeh and J. Widom. SimRank: a measure of structural-context similarity. *KDD'02*
- H.-P. Kriegel, P. Kroeger, and A. Zimek. Clustering high dimensional data: A survey on subspace clustering, pattern-based clustering, and correlation clustering. *ACM Trans. Knowledge Discovery from Data (TKDD)*, 3, 2009.
- U. Luxburg. A tutorial on spectral clustering. *Statistics and Computing*, 17:395–416, 2007
