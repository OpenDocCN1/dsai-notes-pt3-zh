# Multivariate Gaussian Distribution

• Expectation of a random vector x:

$$\mathcal{N}(x\mid\mu,\Sigma)=\frac{1}{(2\pi)^{D/2}|\Sigma|^{1/2}}\exp\left\{-\frac{1}{2}(x-\mu)^\mathrm{T}\Sigma^{-1}(x-\mu)\right\}$$

$$\mathbb{E}[x]=\frac{1}{(2\pi)^{D/2}|\Sigma|^{1/2}}\int \exp\left\{-\frac{1}{2}(x-\mu)^\mathrm{T}\Sigma^{-1}(x-\mu)\right\}x\,dx$$

Let $z=x-\mu$:

$$\mathbb{E}[x]=\frac{1}{(2\pi)^{D/2}|\Sigma|^{1/2}}\int \exp\left\{-\frac{1}{2}z^\mathrm{T}\Sigma^{-1}z\right\}(z+\mu)\,dz=\mu$$