# Multivariate Gaussian Distribution

The covariance of a random vector x (For single random variables, we subtracted the mean before taking second moments in order to define a variance):

$$\operatorname{cov}[\mathbf{x}] = \mathbb{E}\left[(\mathbf{x}-\mathbb{E}[\mathbf{x}])(\mathbf{x}-\mathbb{E}[\mathbf{x}])^T\right]$$

$$\mathbb{E}[\mathbf{x}] = \boldsymbol{\mu}$$

$$\mathbb{E}[\mathbf{x}\mathbf{x}^T] = \boldsymbol{\mu}\boldsymbol{\mu}^T + \boldsymbol{\Sigma}$$

$$\operatorname{cov}[\mathbf{x}] = \boldsymbol{\Sigma}$$

A general symmetric covariance matrix $\boldsymbol{\Sigma}$ will have D(D + 1)/2 independent parameters, and there are another D independent parameters in $\boldsymbol{\mu}$, giving D(D + 3)/2 parameters in total.

![](bbox=[0.414, 0.513, 0.997, 0.748])

$$\boldsymbol{\Sigma} = \operatorname{diag}(\sigma_i^2)$$  2D independent parameters

$$\boldsymbol{\Sigma} = \sigma^2\mathbf{I}$$  isotropic covariance, D + 1 independent parameters