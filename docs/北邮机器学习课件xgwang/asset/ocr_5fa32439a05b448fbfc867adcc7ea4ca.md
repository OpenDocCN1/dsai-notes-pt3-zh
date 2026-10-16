# Summary of PCA

+   - The principal subspace is spanned by $d'$ orthonormal vectors $\mathbf{e}_1,\ldots,\mathbf{e}_{d'}$, which are computed as the $d'$ eigenvectors of the scatter matrix $\mathbf{S}$ with the largest eigenvalues $\lambda_1,\ldots,\lambda_{d'}$.
+   - The principal components $a_{ki}$ of the samples are computed as $a_{ki}=\mathbf{e}_i^T(\mathbf{x}_k-\bar{\mathbf{x}})$.
+   - The variance of the projected samples onto this principal subspace is $\sum_{i=1}^{d'}\lambda_i$.
+   - The mean squared distance between the samples and their projections are $\sum_{i=d'+1}^{d}\lambda_i$.
+   - PCA disentangles the factors of variation underlying the data, assuming such variation is a Gaussian distribution.
+   - We are interested in learning representations that disentangle more complicated forms of feature dependencies