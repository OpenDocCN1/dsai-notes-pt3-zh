# # Maximum Likelihood for the Gaussian

+   - Given a data set \(\mathbf{X} = (x_1, \dots, x_N)^\text{T}\) in which the observations \(\{x_n\}\) are assumed to be drawn independently from a multivariate Gaussian distribution, how to estimate the parameters of the distribution by maximum likelihood?

\(\mathcal{N}(x|\mu, \Sigma) = \frac{1}{(2\pi)^{D/2}} \frac{1}{|\Sigma|^{1/2}} \exp \left\{ -\frac{1}{2}(x - \mu)^\text{T} \Sigma^{-1} (x - \mu) \right\}\)

\(\ln p(\mathbf{X}|\mu, \Sigma) = -\frac{ND}{2} \ln(2\pi) - \frac{N}{2} \ln |\Sigma| - \frac{1}{2} \sum_{n=1}^N (x_n - \mu)^\text{T} \Sigma^{-1} (x_n - \mu)\)