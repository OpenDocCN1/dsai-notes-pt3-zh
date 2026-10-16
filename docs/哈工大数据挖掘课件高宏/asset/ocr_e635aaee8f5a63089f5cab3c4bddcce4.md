# # How to Define Inter-Cluster Similarity

![](bbox=[0.073, 0.153, 0.565, 0.421])

|  | p1 | p2 | p3 | p4 | p5 | ... |
|---|---|---|---|---|---|---|
| p1 |  |  |  |  |  |  |
| p2 |  |  |  |  |  |  |
| p3 |  |  |  |  |  |  |
| p4 |  |  |  |  |  |  |
| p5 |  |  |  |  |  |  |
| ... |  |  |  |  |  |  |

**Proximity Matrix**

+   - MIN
+   - MAX
+   - **Group Average**
+   - Distance Between Centroids
+   - Other methods driven by an objective function
+     - Ward’s Method uses squared error