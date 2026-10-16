# Incorporation of momentum

+   - Error surfaces often have plateaus where there are "to many" weights (especially when the number of layers is large) and thus the error depends only weakly upon any one of them.

+   - Include some fraction α of the previous weight update in stochastic backpropagation
+   
+   **w(m + 1) = w(m) + (1 − α)Δw_bp(m) + αΔw(m − 1)**
+   
+   where Δw_bp(m) is the change in w(m) that would be called for by the backpropagation algorithm
+   
+   **Δw(m) = w(m) − w(m − 1)**

+   - Allow the network to learn more quickly when plateaus in the error surface exists