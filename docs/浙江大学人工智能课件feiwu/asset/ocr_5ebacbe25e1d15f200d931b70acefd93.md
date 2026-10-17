# Backward computation

![](bbox=[0.281, 0.223, 0.952, 0.608])

+   - **Goal:** Fill value $d_a$ at each node $a$
+   - $d_a = \frac{\partial l}{\partial a}$: derivative of loss with respect to $a$
+   - In general: $d_a = \sum_{c_i \in \pi_a^{-1}} d_{c_i} \cdot \frac{\partial f_{c_i}}{\partial a}$
+   - In this case:
+     $$d_a = d_{c_1}\frac{\partial f_{c_1}}{\partial a} + d_{c_2}\frac{\partial f_{c_2}}{\partial a}$$