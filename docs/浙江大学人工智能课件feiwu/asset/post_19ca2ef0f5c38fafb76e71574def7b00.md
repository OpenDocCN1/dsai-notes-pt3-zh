

## Continuous inputs

- Assume: \( p(x|C_k) = \frac{1}{(2\pi)^{D/2} |\Sigma|^{1/2}} \exp \left\{ -\frac{1}{2} (x - \mu_k)^T \Sigma^{-1} (x - \mu_k) \right\} \)

- 2 classes: \( p(C_1|x) = \sigma(w^T x + w_0) \quad w = \Sigma^{-1}(\mu_1 - \mu_2) \quad w_0 = -\frac{1}{2} \mu_1^T \Sigma^{-1} \mu_1 + \frac{1}{2} \mu_2^T \Sigma^{-1} \mu_2 + \ln \frac{p(C_1)}{p(C_2)} \)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_586_0.png)

- K classes: \( a_k(x) = w_k^T x + w_{k0} \quad w_k = \Sigma^{-1} \mu_k \quad w_{k0} = -\frac{1}{2} \mu_k^T \Sigma^{-1} \mu_k + \ln p(C_k) \)

## Continuous inputs

- **Assume:** \( p(\mathbf{x}|\mathcal{C}_k) = \frac{1}{(2\pi)^{D/2}|\boldsymbol{\Sigma}|^{1/2}} \exp \left\{ -\frac{1}{2}(\mathbf{x} - \boldsymbol{\mu}_k)^\mathrm{T} \boldsymbol{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu}_k) \right\} \)

- **_K_ classes with its own covariance matrix (quadratic discriminant):**

\( a_k(\mathbf{x}) = \mathbf{w}_k^\mathrm{T} \mathbf{x} + w_{k0} \qquad \mathbf{w}_k = \boldsymbol{\Sigma}_k^{-1} \boldsymbol{\mu}_k \qquad w_{k0} = -\frac{1}{2} \boldsymbol{\mu}_k^\mathrm{T} \boldsymbol{\Sigma}_k^{-1} \boldsymbol{\mu}_k + \ln p(\mathcal{C}_k) \)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_587_0.png)

**Figure 4.11** The left-hand plot shows the class-conditional densities for three classes each having a Gaussian distribution, coloured red, green, and blue, in which the red and green classes have the same covariance matrix. The right-hand plot shows the corresponding posterior probabilities, in which the RGB colour vector represents the posterior probabilities for the respective three classes. The decision boundaries are also shown. Notice that the boundary between the red and green classes, which have the same covariance matrix, is linear, whereas those between the other pairs of classes are quadratic.

## Maximum likelihood solution for two classes

\(\ln p(\mathbf{t}|\pi,\mu_1,\mu_2,\Sigma)=\sum_{n=1}^N\{t_n\ln\pi+(1-t_n)\ln(1-\pi)+t_n\ln\mathcal{N}(\mathbf{x}_n|\mu_1,\Sigma)+(1-t_n)\ln\mathcal{N}(\mathbf{x}_n|\mu_2,\Sigma)\}\)

- **Solve** \(\pi\):

\(\sum_{n=1}^N\{t_n\ln\pi+(1-t_n)\ln(1-\pi)\} \implies \pi=\frac{1}{N}\sum_{n=1}^N t_n=\frac{N_1}{N}=\frac{N_1}{N_1+N_2}\)

- **Solve** \(\mu_1, \mu_2\):

\(\sum_{n=1}^N t_n \ln \mathcal{N}(\mathbf{x}_n|\mu_1, \Sigma) = -\frac{1}{2}\sum_{n=1}^N t_n(\mathbf{x}_n-\mu_1)^\mathrm{T}\Sigma^{-1}(\mathbf{x}_n-\mu_1) + \text{const}\)

\(\implies \mu_1 = \frac{1}{N_1}\sum_{n=1}^N t_n \mathbf{x}_n \qquad \mu_2 = \frac{1}{N_2}\sum_{n=1}^N (1-t_n)\mathbf{x}_n\)

- **Solve** \(\Sigma\):

\(-\frac{1}{2}\sum_{n=1}^N t_n \ln |\Sigma| - \frac{1}{2}\sum_{n=1}^N t_n(\mathbf{x}_n-\mu_1)^\mathrm{T}\Sigma^{-1}(\mathbf{x}_n-\mu_1)\)

\(-\frac{1}{2}\sum_{n=1}^N (1-t_n) \ln |\Sigma| - \frac{1}{2}\sum_{n=1}^N (1-t_n)(\mathbf{x}_n-\mu_2)^\mathrm{T}\Sigma^{-1}(\mathbf{x}_n-\mu_2) = -\frac{N}{2} \ln |\Sigma| - \frac{N}{2} \text{Tr}\{\Sigma^{-1}\mathbf{S}\}\)

\(\mathbf{S} = \frac{N_1}{N}\left[\frac{1}{N_1}\sum_{n \in \mathcal{C}_1} (\mathbf{x}_n-\mu_1)(\mathbf{x}_n-\mu_1)^\mathrm{T}\right] + \frac{N_2}{N}\left[\frac{1}{N_2}\sum_{n \in \mathcal{C}_2} (\mathbf{x}_n-\mu_2)(\mathbf{x}_n-\mu_2)^\mathrm{T}\right] \implies \Sigma = \mathbf{S}\)

## Maximum likelihood solution for K-classes

- The likelihood function: \( p \left( \left\{ \phi_n, \mathbf{t}_n \right\} \mid \left\{ \pi_k \right\} \right) = \prod_{n=1}^N \prod_{k=1}^K \left\{ p(\phi_n|C_k)\pi_k \right\}^{t_{nk}} \qquad \sum_k \pi_k = 1 \)

- The log likelihood: \( \ln p \left( \left\{ \phi_n, \mathbf{t}_n \right\} \mid \left\{ \pi_k \right\} \right) = \sum_{n=1}^N \sum_{k=1}^K t_{nk} \left\{ \ln p(\phi_n|C_k) + \ln \pi_k \right\} \)

- Introduce a Lagrange multiplier \(\lambda\): \( \ln p \left( \left\{ \phi_n, \mathbf{t}_n \right\} \mid \left\{ \pi_k \right\} \right) + \lambda \left( \sum_{k=1}^K \pi_k - 1 \right) \)

- Solve \(\pi_k\): \( \pi_k = \frac{N_k}{N} \)

- Solve \(\mu_k\): \( \mu_k = \frac{1}{N_k} \sum_{n=1}^N t_{nk} \phi_n \)

- Solve \(\Sigma\): \( \Sigma = \sum_{k=1}^K \frac{N_k}{N} \mathbf{S}_k \qquad \mathbf{S}_k = \frac{1}{N_k} \sum_{n=1}^N t_{nk}(\phi_n - \mu_k)(\phi_n - \mu_k)^\mathrm{T} \)

**Assumption**: Each class-conditional density is Gaussian with a shared covariance matrix.

