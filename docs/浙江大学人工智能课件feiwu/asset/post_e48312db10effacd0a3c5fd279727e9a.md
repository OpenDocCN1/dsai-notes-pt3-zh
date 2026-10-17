

## Multivariate Gaussian Distribution

- It's normalized!  
$$\int_{-\infty}^{\infty} \mathcal{N}(x|\mu, \sigma^2) \, dx = 1$$

$$\mathcal{N}(x|\mu, \Sigma) = \frac{1}{(2\pi)^{D/2}} \frac{1}{|\Sigma|^{1/2}} \exp \left\{ -\frac{1}{2}(x - \mu)^\mathrm{T} \Sigma^{-1} (x - \mu) \right\}$$

$$\Delta^2 = \sum_{i=1}^D \frac{y_i^2}{\lambda_i}$$  
$$|\mathbf{J}| = 1$$

$$\Sigma = \mathbf{U} \Lambda \mathbf{U}^\mathrm{T} \implies |\Sigma| = |\mathbf{U} \Lambda \mathbf{U}^\mathrm{T}| = |\mathbf{U}||\Lambda||\mathbf{U}^\mathrm{T}| = |\mathbf{U}||\mathbf{U}^\mathrm{T}||\Lambda| = |\Lambda| \implies |\Sigma|^{1/2} = \prod_{j=1}^D \lambda_j^{1/2}$$

$$p(y) = p(x)|\mathbf{J}| = \prod_{j=1}^D \frac{1}{(2\pi\lambda_j)^{1/2}} \exp \left\{ -\frac{y_j^2}{2\lambda_j} \right\}$$

$$\implies \int p(y) \, dy = \prod_{j=1}^D \int_{-\infty}^{\infty} \frac{1}{(2\pi\lambda_j)^{1/2}} \exp \left\{ -\frac{y_j^2}{2\lambda_j} \right\} dy_j = 1 \implies \int p(y) \, dy = 1$$

## Multivariate Gaussian Distribution

• Expectation of a random vector x:

$$\mathcal{N}(x\mid\mu,\Sigma)=\frac{1}{(2\pi)^{D/2}|\Sigma|^{1/2}}\exp\left\{-\frac{1}{2}(x-\mu)^\mathrm{T}\Sigma^{-1}(x-\mu)\right\}$$

$$\mathbb{E}[x]=\frac{1}{(2\pi)^{D/2}|\Sigma|^{1/2}}\int \exp\left\{-\frac{1}{2}(x-\mu)^\mathrm{T}\Sigma^{-1}(x-\mu)\right\}x\,dx$$

Let $z=x-\mu$:

$$\mathbb{E}[x]=\frac{1}{(2\pi)^{D/2}|\Sigma|^{1/2}}\int \exp\left\{-\frac{1}{2}z^\mathrm{T}\Sigma^{-1}z\right\}(z+\mu)\,dz=\mu$$

## Multivariate Gaussian Distribution

• The second order moments of the Gaussian

\(\mathbb{E}[\mathbf{x}\mathbf{x}^\mathrm{T}] = \frac{1}{(2\pi)^{D/2}} \frac{1}{|\Sigma|^{1/2}} \int \exp \left\{ -\frac{1}{2}(\mathbf{x} - \boldsymbol{\mu})^\mathrm{T} \Sigma^{-1} (\mathbf{x} - \boldsymbol{\mu}) \right\} \mathbf{x}\mathbf{x}^\mathrm{T} \, d\mathbf{x}\)

\(\underline{\mathbf{z} = \mathbf{x} - \boldsymbol{\mu}} \quad \frac{1}{(2\pi)^{D/2}} \frac{1}{|\Sigma|^{1/2}} \int \exp \left\{ -\frac{1}{2} \mathbf{z}^\mathrm{T} \Sigma^{-1} \mathbf{z} \right\} (\mathbf{z} + \boldsymbol{\mu})(\mathbf{z} + \boldsymbol{\mu})^\mathrm{T} \, d\mathbf{z}\)

\(\boldsymbol{\mu}\boldsymbol{\mu}^\mathrm{T}\) is constant, \(\boldsymbol{\mu}\mathbf{z}^\mathrm{T}\) and \(\boldsymbol{\mu}^\mathrm{T}\mathbf{z}\) will again vanish by symmetry.

Consider the term involving \(\mathbf{z}\mathbf{z}^\mathrm{T}\)

\(\frac{1}{(2\pi)^{D/2}} \frac{1}{|\Sigma|^{1/2}} \int \exp \left\{ -\frac{1}{2} \mathbf{z}^\mathrm{T} \Sigma^{-1} \mathbf{z} \right\} \mathbf{z}\mathbf{z}^\mathrm{T} \, d\mathbf{z}\)

\(= \frac{1}{(2\pi)^{D/2}} \frac{1}{|\Sigma|^{1/2}} \sum_{i=1}^D \sum_{j=1}^D \mathbf{u}_i \mathbf{u}_j^\mathrm{T} \int \exp \left\{ -\sum_{k=1}^D \frac{y_k^2}{2\lambda_k} \right\} y_i y_j \, d\mathbf{y} = \sum_{i=1}^D \mathbf{u}_i \mathbf{u}_i^\mathrm{T} \lambda_i = \Sigma\)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1020_0.png)

\(\boxed{\mathbb{E}[\mathbf{x}\mathbf{x}^\mathrm{T}] = \boldsymbol{\mu}\boldsymbol{\mu}^\mathrm{T} + \Sigma}\)

## Multivariate Gaussian Distribution

- The covariance of a random vector x:

\(\text{cov}[\text{x}] = \mathbb{E}\left[(\text{x} - \mathbb{E}[\text{x}])(\text{x} - \mathbb{E}[\text{x}])^\text{T}\right]\)
\(\mathbb{E}[\text{x}] = \mu\)
\(\text{cov}[\text{x}] = \Sigma\)

A general symmetric covariance matrix \(\Sigma\) will have D(D + 1)/2 independent parameters, and there are another D independent parameters in \(\mu\), giving D(D + 3)/2 parameters in total.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1021_0.png)

\(\Sigma = \text{diag}(\sigma_i^2)\) 2D independent parameters

\(\Sigma = \sigma^2\mathbf{I}\) isotropic covariance, D + 1 independent parameters

## Partitioned Gaussians

### Partitioned Gaussians

Given a joint Gaussian distribution \(\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}, \boldsymbol{\Sigma})\) with \(\boldsymbol{\Lambda} \equiv \boldsymbol{\Sigma}^{-1}\) and

\(\mathbf{x} = \begin{pmatrix} \mathbf{x}_a \\ \mathbf{x}_b \end{pmatrix}, \quad \boldsymbol{\mu} = \begin{pmatrix} \boldsymbol{\mu}_a \\ \boldsymbol{\mu}_b \end{pmatrix}\)

\(\boldsymbol{\Sigma} = \begin{pmatrix} \boldsymbol{\Sigma}_{aa} & \boldsymbol{\Sigma}_{ab} \\ \boldsymbol{\Sigma}_{ba} & \boldsymbol{\Sigma}_{bb} \end{pmatrix}, \quad \boldsymbol{\Lambda} = \begin{pmatrix} \boldsymbol{\Lambda}_{aa} & \boldsymbol{\Lambda}_{ab} \\ \boldsymbol{\Lambda}_{ba} & \boldsymbol{\Lambda}_{bb} \end{pmatrix}.\)

### Conditional distribution:

\(p(\mathbf{x}_a|\mathbf{x}_b) = \mathcal{N}(\mathbf{x}|\boldsymbol{\mu}_{a|b}, \boldsymbol{\Lambda}_{aa}^{-1})\)
\(\boldsymbol{\mu}_{a|b} = \boldsymbol{\mu}_a - \boldsymbol{\Lambda}_{aa}^{-1} \boldsymbol{\Lambda}_{ab} (\mathbf{x}_b - \boldsymbol{\mu}_b).\)

### Marginal distribution:

\(p(\mathbf{x}_a) = \mathcal{N}(\mathbf{x}_a|\boldsymbol{\mu}_a, \boldsymbol{\Sigma}_{aa}).\)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1022_0.png)

