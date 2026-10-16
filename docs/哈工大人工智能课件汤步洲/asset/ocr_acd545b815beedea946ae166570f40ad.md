(1) 综合数据库： (m, c, b) (2) 初始状态： (3, 3, 1)

其中， 0≤m≤3， 0≤c≤3， b∈{ 0, 1 } (3) 目标状态： (0, 0, 0)

# (4) 规则集

+   r1: IF (m, c, 1) THEN (m-1, c, 0)
+   r2: IF (m, c, 1) THEN (m, c-1, 0)
+   r3: IF (m, c, 1) THEN (m-1, c-1, 0)
+   r4: IF (m, c, 1) THEN (m-2, c, 0)
+   r5: IF (m, c, 1) THEN (m, c-2, 0)

+   r6: IF (m, c, 0) THEN (m+1, c, 1)
+   r7: IF (m, c, 0) THEN (m, c+1, 1)
+   r8: IF (m, c, 0) THEN (m+1, c+1, 1)
+   r9: IF (m, c, 0) THEN (m+2, c, 1)
+   r10: IF (m, c, 0) THEN (m, c+2, 1)