# Shallow domain adaptation

+   - **Traditional deep learning**
+   
+     min 1/n Σ_{i=1}^n L(x_i, y_i, θ)
+   - **Feature adaptation**
+   
+     min 1/n Σ_{i=1}^n L(φ(x_i^s), y_i^s, θ)
+   - **Instance adaptation**
+   
+     min 1/n Σ_{i=1}^n w_i L(x_i^s, y_i^s, θ)
+   - **Model adaptation**
+   
+     min 1/n Σ_{i=1}^n L(x_i^s, y_i^s, θ)

Slide credit: Meina Kan

> [1] Pan S J, Yang Q. A survey on transfer learning[J]. IEEE Transactions on knowledge and data engineering, 2010, 22(10): 1345-1359.