# # Multivariate Gaussian Distribution

+   - The covariance of a random vector x:

\(\text{cov}[\text{x}] = \mathbb{E}\left[(\text{x} - \mathbb{E}[\text{x}])(\text{x} - \mathbb{E}[\text{x}])^\text{T}\right]\)
\(\mathbb{E}[\text{x}] = \mu\)
\(\text{cov}[\text{x}] = \Sigma\)

A general symmetric covariance matrix \(\Sigma\) will have D(D + 1)/2 independent parameters, and there are another D independent parameters in \(\mu\), giving D(D + 3)/2 parameters in total.

![](bbox=[0.414, 0.512, 0.973, 0.752])

\(\Sigma = \text{diag}(\sigma_i^2)\) 2D independent parameters

\(\Sigma = \sigma^2\mathbf{I}\) isotropic covariance, D + 1 independent parameters