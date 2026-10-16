# Covariance Matrix of Principal Components

+   - The correlation between projections on $e_i$ and $e_j$ $(i \ne j)$ is
+   
+     $$\sum_{k=1}^{n} a_{ki}a_{kj}=\sum_{k=1}^{n}e_i^T(\mathbf{x}_k-\bar{\mathbf{x}})(\mathbf{x}_k-\bar{\mathbf{x}})^Te_j=e_i^TSe_j=\lambda_j e_i^Te_j=0$$

+   - The covariance matrix of samples in the PCA subspace is
+   
+     $\operatorname{diag}[\lambda_1,\ldots,\lambda_d]$