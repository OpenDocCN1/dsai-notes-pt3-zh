# Bayesian Inference for the Gaussian

2. Know the mean, to infer the variance: \(\lambda \equiv 1/\sigma^2\)

Likelihood: \(p(\mathbf{X}\mid\lambda)=\prod_{n=1}^{N}\mathcal{N}(x_n\mid\mu,\lambda^{-1})\propto \lambda^{N/2}\exp\left\{-\frac{\lambda}{2}\sum_{n=1}^{N}(x_n-\mu)^2\right\}\)

Prior: \(\mathrm{Gam}(\lambda\mid a_0,b_0)\)  *gamma distribution*

Posterior: \(p(\lambda\mid\mathbf{X})\propto p(\mathbf{X}\mid\lambda)\,\mathrm{Gam}(\lambda\mid a_0,b_0)\)

\(p(\lambda\mid\mathbf{X})\propto \lambda^{a_0-1+N/2}\exp\left\{-b_0\lambda-\frac{\lambda}{2}\sum_{n=1}^{N}(x_n-\mu)^2\right\}\ \rightarrow\ \mathrm{Gam}(\lambda\mid a_N,b_N)\)

\(a_N=a_0+\frac{N}{2}\)

\(b_N=b_0+\frac{1}{2}\sum_{n=1}^{N}(x_n-\mu)^2=b_0+\frac{N}{2}\sigma^2_{\mathrm{ML}}\)

\(\mathrm{Gam}(\lambda\mid a,b)=\frac{1}{\Gamma(a)}b^a\lambda^{a-1}\exp(-b\lambda)\)