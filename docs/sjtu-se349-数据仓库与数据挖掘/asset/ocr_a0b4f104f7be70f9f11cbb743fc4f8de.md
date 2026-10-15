# Density-Based Local Outlier Detection

+   - M. M. Breunig, H.-P. Kriegel, R. Ng, J. Sander. LOF: Identifying Density-Based Local Outliers. SIGMOD 2000.
+   - Distance-based outlier detection is based on global distance distribution
+   - It encounters difficulties to identify outliers if data is not uniformly distributed
+   - Ex. C₁ contains 400 loosely distributed points, C₂ has 100 tightly condensed points, 2 outlier points o₁, o₂
+   - Distance-based method cannot identify o₂ as an outlier

+   - Need the concept of local outlier
+   - Local outlier factor (LOF)
+     - Assume outlier is not crisp
+     - Each point has a LOF

![](bbox=[0.62, 0.06, 0.92, 0.48])