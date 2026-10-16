# D-Separation

+   - Query: $X_i \perp\!\!\perp X_j | \{X_{k_1}, ..., X_{k_n}\}$ ?
+   - Check all (undirected!) paths between $X_i$ and $X_j$
+     - If one or more active, then independence not guaranteed
+       $X_i \not\!\perp\!\!\perp X_j | \{X_{k_1}, ..., X_{k_n}\}$
+     - Otherwise (i.e. if all paths are inactive), then independence is guaranteed
+       $X_i \perp\!\!\perp X_j | \{X_{k_1}, ..., X_{k_n}\}$

![](bbox=[0.6, 0.46, 0.99, 0.94])