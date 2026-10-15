# # Outlier Detection I: Supervised Methods

+   - **Two ways to categorize outlier detection methods:**
+     - Based on *whether user-labeled examples of outliers can be obtained:*
+       - Supervised, semi-supervised vs. unsupervised methods
+     - Based on *assumptions about normal data and outliers 正常对象和离群点的假定:*
+       - Statistical, proximity-based, and clustering-based methods

+   - **Outlier Detection I: Supervised Methods**
+     - Modeling outlier detection as a classification problem
+       - Samples examined by domain experts used for training & testing
+     - Methods for Learning a classifier for outlier detection effectively:
+       - Model normal objects & report those not matching the model as outliers, or
+       - Model outliers and treat those not matching the model as normal
+     - Challenges
+       - **Imbalanced classes 两个类（正常对象和离群点）比例，i.e., outliers are rare会限制构建的分类器的能力: Boost the outlier class 离群点过抽样（即复制） and make up some artificial outliers**
+       - Catch as many outliers as possible, i.e., recall is more important than accuracy (i.e., not mislabeling normal objects as outliers)