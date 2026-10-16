+   * Sorted data for price (in dollars): 4, 8, 9, 15, 21, 21, 24, 25, 26, 28, 29, 34
+   * Partition into (equi-depth) bins:
+     - Bin 1: 4, 8, 9, 15
+     - Bin 2: 21, 21, 24, 25
+     - Bin 3: 26, 28, 29, 34
+   * Smoothing by bin means:
+     - Bin 1: 9, 9, 9, 9
+     - Bin 2: 23, 23, 23, 23
+     - Bin 3: 29, 29, 29, 29
+   * Smoothing by bin boundaries:
+     - Bin 1: 4, 4, 4, 15
+     - Bin 2: 21, 21, 25, 25
+     - Bin 3: 26, 26, 26, 34