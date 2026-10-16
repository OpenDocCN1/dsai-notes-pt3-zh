➢ **OPTICS算法是对DBSCAN算法的改进，**\n因为在DBSCAN算法中需要用户设定ε-邻域和MitPts，但是在实际应用中用户往往很难确定这些参数，而且这些参数设置的不同往往会导致聚类结果有很大差别。

# # OPTICS: Some Extension from DBSCAN

![](bbox=[0.531, 0.041, 0.978, 0.241])

# Density-Based Clustering: OPTICS & Its Applications

![](bbox=[0.068, 0.313, 0.436, 0.484])

➢ **DENCLUE算法的依据是某个数据点在邻域内的影响可以用一个数学函数来形式化地表达，这个函数为影响函数。所聚类数据空间的整体密度函数是所有数据点影响函数的总和。在聚类时就根据全局密度函数的局部最大值，即密度吸引子点来确定。**

# # DENCLUE: Using Statistical Density Functions

+   - DENsity-based CLUstEring by Hinneburg & Keim (KDD’98)\n- Using statistical density functions:\n  - 影响函数及整体密度函数公式\n- Major features\n  - Solid mathematical foundation\n  - Good for data sets with large amounts of noise\n  - Allows a compact mathematical description of arbitrarily shaped clusters in high-dimensional data sets\n  - Significant faster than existing algorithm (e.g., DBSCAN)\n  - But needs a large number of parameters

# # Denclue: Technical Essence

+   - Influence function: describes the impact of a data point within its neighborhood\n- Overall density of the data space can be calculated as the sum of the influence function of all data points\n- Clusters can be determined mathematically by identifying density attractors\n- Density attractors are local maximal of the overall density function

# # Density Attractor

![](bbox=[0.069, 0.815, 0.352, 0.971])

# # Center-Defined and Arbitrary

![](bbox=[0.529, 0.82, 0.961, 0.971])