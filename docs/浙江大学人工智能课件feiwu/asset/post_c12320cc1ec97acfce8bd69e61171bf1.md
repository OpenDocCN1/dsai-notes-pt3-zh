
## Maximum Likelihood for the Gaussian

- Estimate the parameters of the distribution by maximum likelihood:

$$\ln p(\mathbf{X}\mid\boldsymbol{\mu},\boldsymbol{\Sigma})=-\frac{ND}{2}\ln(2\pi)-\frac{N}{2}\ln\lvert\boldsymbol{\Sigma}\rvert-\frac{1}{2}\sum_{n=1}^{N}(\mathbf{x}_n-\boldsymbol{\mu})^T\boldsymbol{\Sigma}^{-1}(\mathbf{x}_n-\boldsymbol{\mu})$$

$$\boldsymbol{\mu}_{\mathrm{ML}}=\frac{1}{N}\sum_{n=1}^{N}\mathbf{x}_n,\qquad \boldsymbol{\Sigma}_{\mathrm{ML}}=\frac{1}{N}\sum_{n=1}^{N}(\mathbf{x}_n-\boldsymbol{\mu}_{\mathrm{ML}})(\mathbf{x}_n-\boldsymbol{\mu}_{\mathrm{ML}})^T$$

$$\mathbb{E}[\boldsymbol{\Sigma}_{\mathrm{ML}}]=\frac{1}{N}\sum_{n=1}^{N}\mathbb{E}\left[\left(\mathbf{x}_n-\frac{1}{N}\sum_{m=1}^{N}\mathbf{x}_m\right)\left(\mathbf{x}_n^T-\frac{1}{N}\sum_{l=1}^{N}\mathbf{x}_l^T\right)\right]$$

$$=\frac{1}{N}\sum_{n=1}^{N}\mathbb{E}\left[\mathbf{x}_n\mathbf{x}_n^T-\frac{2}{N}\mathbf{x}_n\sum_{m=1}^{N}\mathbf{x}_m^T+\frac{1}{N^2}\sum_{m=1}^{N}\sum_{l=1}^{N}\mathbf{x}_m\mathbf{x}_l^T\right]$$

$$=\left\{\boldsymbol{\mu}\boldsymbol{\mu}^T+\boldsymbol{\Sigma}-2\left(\boldsymbol{\mu}\boldsymbol{\mu}^T+\frac{1}{N}\boldsymbol{\Sigma}\right)+\boldsymbol{\mu}\boldsymbol{\mu}^T+\frac{1}{N}\boldsymbol{\Sigma}\right\}$$

$$=\left(\frac{N-1}{N}\right)\boldsymbol{\Sigma}$$

$$\mathbb{E}[\boldsymbol{\mu}_{\mathrm{ML}}]=\boldsymbol{\mu}$$

$$\mathbb{E}[\boldsymbol{\Sigma}_{\mathrm{ML}}]=\frac{N-1}{N}\boldsymbol{\Sigma}$$

$$\widetilde{\boldsymbol{\Sigma}}=\frac{1}{N-1}\sum_{n=1}^{N}(\mathbf{x}_n-\boldsymbol{\mu}_{\mathrm{ML}})(\mathbf{x}_n-\boldsymbol{\mu}_{\mathrm{ML}})^T$$

## Bayesian Inference for the Gaussian

### 1. Know the variance, to infer the mean:

Likelihood: $p(\mathbf{X}\mid\mu)=\prod_{n=1}^{N}p(x_n\mid\mu)=\frac{1}{(2\pi\sigma^2)^{N/2}}\exp\left\{-\frac{1}{2\sigma^2}\sum_{n=1}^{N}(x_n-\mu)^2\right\}$

Prior: $p(\mu)=\mathcal{N}(\mu\mid\mu_0,\sigma_0^2)$

Posterior: $p(\mu\mid\mathbf{X})\propto p(\mathbf{X}\mid\mu)p(\mu)$

$p(\mu\mid\mathbf{X})=\mathcal{N}(\mu\mid\mu_N,\sigma_N^2)$

$\mu_N=\frac{\sigma^2}{N\sigma_0^2+\sigma^2}\mu_0+\frac{N\sigma_0^2}{N\sigma_0^2+\sigma^2}\mu_{\mathrm{ML}}$

$\frac{1}{\sigma_N^2}=\frac{1}{\sigma_0^2}+\frac{N}{\sigma^2}$

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1030_0.png)

Likelihood: $p(\mathbf{X}\mid\mu)=\prod_{n=1}^{N}p(x_n\mid\mu)=\frac{1}{(2\pi\sigma^2)^{N/2}}\exp\left\{-\frac{1}{2\sigma^2}\sum_{n=1}^{N}(x_n-\mu)^2\right\}$

Prior: $p(\mu)=\mathcal{N}(\mu\mid\mu_0,\sigma_0^2)$

Posterior: $p(\mu\mid\mathbf{X})\propto p(\mathbf{X}\mid\mu)p(\mu)\qquad p(\mu\mid\mathbf{X})=\mathcal{N}(\mu\mid\mu_N,\sigma_N^2)$

$$-\frac{1}{2}(\mathbf{x}-\boldsymbol{\mu})^{\mathsf{T}}\boldsymbol{\Sigma}^{-1}(\mathbf{x}-\boldsymbol{\mu})=-\frac{1}{2}\mathbf{x}^{\mathsf{T}}\boldsymbol{\Sigma}^{-1}\mathbf{x}+\mathbf{x}^{\mathsf{T}}\boldsymbol{\Sigma}^{-1}\boldsymbol{\mu}+\mathrm{const}$$

$$-\frac{1}{2\sigma_0^2}(\mu-\mu_0)^2-\frac{1}{2\sigma^2}\sum_{n=1}^{N}(x_n-\mu)^2$$

$$=-\frac{\mu^2}{2}\left(\frac{1}{\sigma_0^2}+\frac{N}{\sigma^2}\right)+\mu\left(\frac{\mu_0}{\sigma_0^2}+\frac{1}{\sigma^2}\sum_{n=1}^{N}x_n\right)+\mathrm{const}$$

$$\frac{1}{\sigma_N^2}=\frac{N}{\sigma^2}+\frac{1}{\sigma_0^2}\qquad \mu_N=\left(\frac{N}{\sigma^2}+\frac{1}{\sigma_0^2}\right)^{-1}\left(\frac{\mu_0}{\sigma_0^2}+\frac{1}{\sigma^2}\sum_{n=1}^{N}x_n\right)$$

$$\mu_{\mathrm{ML}}=\frac{1}{N}\sum_{n=1}^{N}x_n\qquad \mu_N=\frac{\sigma^2}{N\sigma_0^2+\sigma^2}\mu_0+\frac{N\sigma_0^2}{N\sigma_0^2+\sigma^2}\mu_{\mathrm{ML}}$$

### 2. Know the mean, to infer the variance:

$\lambda \equiv 1/\sigma^2$

Likelihood: $p(\mathbf{X}\mid\lambda)=\prod_{n=1}^{N}\mathcal{N}(x_n\mid\mu,\lambda^{-1})\propto \lambda^{N/2}\exp\left\{-\frac{\lambda}{2}\sum_{n=1}^{N}(x_n-\mu)^2\right\}$

Prior: $\mathrm{Gam}(\lambda\mid a_0,b_0)$ *gamma distribution*

Posterior: $p(\lambda\mid\mathbf{X})\propto p(\mathbf{X}\mid\lambda)\,\mathrm{Gam}(\lambda\mid a_0,b_0)$

$p(\lambda\mid\mathbf{X})\propto \lambda^{a_0-1+N/2}\exp\left\{-b_0\lambda-\frac{\lambda}{2}\sum_{n=1}^{N}(x_n-\mu)^2\right\}\ \rightarrow\ \mathrm{Gam}(\lambda\mid a_N,b_N)$

$a_N=a_0+\frac{N}{2}$

$b_N=b_0+\frac{1}{2}\sum_{n=1}^{N}(x_n-\mu)^2=b_0+\frac{N}{2}\sigma^2_{\mathrm{ML}}$

$\mathrm{Gam}(\lambda\mid a,b)=\frac{1}{\Gamma(a)}b^a\lambda^{a-1}\exp(-b\lambda)$
