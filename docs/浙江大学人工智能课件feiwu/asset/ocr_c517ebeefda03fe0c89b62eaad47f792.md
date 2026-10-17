# # Fisher’s discriminant for multiple classes

+   - Assume input space dimensionality \( D > K \) (number of classes, \( K > 2 \)):
+   
+     \( y = \mathbf{W}^T \mathbf{x} \quad y_k = \mathbf{w}_k^T \mathbf{x} \)

# ## covariance matrices defined in the projected y-space

+   - The generalization of the within-class and between-class covariance matrix:
+   
+     \( s_W = \sum_{k=1}^K \sum_{n \in C_k} (y_n - \mu_k)(y_n - \mu_k)^T \quad s_B = \sum_{k=1}^K N_k (\mu_k - \mu)(\mu_k - \mu)^T \quad \mu_k = \frac{1}{N_k} \sum_{n \in C_k} y_n \quad \mu = \frac{1}{N} \sum_{k=1}^K N_k \mu_k \)

+   - The Fisher’s criterion: \( J(\mathbf{W}) = \text{Tr} \left\{ s_W^{-1} s_B \right\} = \text{Tr} \left\{ (\mathbf{W}^T \mathbf{S}_W \mathbf{W})^{-1} (\mathbf{W}^T \mathbf{S}_B \mathbf{W}) \right\} \)

![](bbox=[0.031, 0.667, 0.438, 0.958])

+   - \( \mathbf{S}_W = \sum_{k=1}^K \sum_{n \in C_k} (\mathbf{x}_n - \mathbf{m}_k)(\mathbf{x}_n - \mathbf{m}_k)^T \quad \mathbf{S}_B = \sum_{k=1}^K N_k (\mathbf{m}_k - \mathbf{m})(\mathbf{m}_k - \mathbf{m})^T \)