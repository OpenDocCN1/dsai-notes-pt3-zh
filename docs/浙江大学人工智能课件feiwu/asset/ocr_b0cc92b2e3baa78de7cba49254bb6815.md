# # The Gaussian distribution

+   - independent and identically distributed (i.i.d)

\(p(\mathbf{x}|\mu, \sigma^2) = \prod_{n=1}^N \mathcal{N} \left(x_n|\mu, \sigma^2\right)\)

+   - Log likelihood:

\(\ln p \left(\mathbf{x}|\mu, \sigma^2\right) = -\frac{1}{2\sigma^2} \sum_{n=1}^N(x_n - \mu)^2 - \frac{N}{2} \ln \sigma^2 - \frac{N}{2} \ln(2\pi)\)

+   - The maximum likelihood solution:

\(\mu_\text{ML} = \frac{1}{N} \sum_{n=1}^N x_n \qquad \sigma_\text{ML}^2 = \frac{1}{N} \sum_{n=1}^N(x_n - \mu_\text{ML})^2\)

\(\widetilde{\sigma}^2 = \frac{N}{N-1} \sigma_\text{ML}^2 = \frac{1}{N-1} \sum_{n=1}^N(x_n - \mu_\text{ML})^2\)

\(\mathbb{E}[\mu_\text{ML}] = \mu\)

\(\mathbb{E}[\sigma_\text{ML}^2] = \left(\frac{N-1}{N}\right) \sigma^2\)

![](bbox=[0.65, 0.32, 0.99, 0.62])