# # The Gaussian distribution

+   • Gaussian distribution (normal distribution)

\(\mathcal{N} \left(x|\mu, \sigma^{2}\right)=\frac{1}{\left(2 \pi \sigma^{2}\right)^{1 / 2}} \exp \left\{-\frac{1}{2 \sigma^{2}}(x-\mu)^{2}\right\}\)

\(\int_{-\infty}^{\infty} \mathcal{N}\left(x|\mu, \sigma^{2}\right) \mathrm{d} x=1\)

\(\mathbb{E}[x]=\int_{-\infty}^{\infty} \mathcal{N}\left(x|\mu, \sigma^{2}\right) x \mathrm{d} x=\mu\)

\(\mathbb{E}\left[x^{2}\right]=\int_{-\infty}^{\infty} \mathcal{N}\left(x|\mu, \sigma^{2}\right) x^{2} \mathrm{d} x=\mu^{2}+\sigma^{2}\)

\(\mathrm{var}[x]=\mathbb{E}\left[x^{2}\right]-\mathbb{E}[x]^{2}=\sigma^{2}\)

\(\mathcal{N}(\mathbf{x}|\mu, \Sigma)=\frac{1}{(2 \pi)^{D / 2}} \frac{1}{|\Sigma|^{1 / 2}} \exp \left\{-\frac{1}{2}(\mathbf{x}-\mu)^{\mathrm{T}} \Sigma^{-1}(\mathbf{x}-\mu)\right\}\)

![](bbox=[0.618, 0.39, 0.973, 0.727])