# Distributed computation with CPU cores

+   - Model parallelism: Only those nodes with edges that cross partition boundaries will need to have their state transmitted between machines. Even in cases where a node has multiple edges crossing a partition boundary, its state is only sent to the machine on the other side of that boundary once.
+   - Within each partition, computation for individual nodes will the be parallelized across all available CPU cores
+   - It requires data synchronization and data transfer between machines during both training and inference

![](bbox=[0.28, 0.58, 0.72, 0.88])