\(\frac{\partial}{\partial \Sigma} \ln p(X|\mu, \Sigma) = -\frac{N}{2} \frac{\partial}{\partial \Sigma} \ln |\Sigma| - \frac{1}{2} \frac{\partial}{\partial \Sigma} \sum_{n=1}^N (x_n - \mu)^T \Sigma^{-1} (x_n - \mu)\)

\(\frac{\partial}{\partial A} \ln |A| = (A^{-1})^T\)

\(-\frac{N}{2} \frac{\partial}{\partial \Sigma} \ln |\Sigma| = -\frac{N}{2} (\Sigma^{-1})^T = -\frac{N}{2} \Sigma^{-1}\)

\(\sum_{n=1}^N (x_n - \mu)^T \Sigma^{-1} (x_n - \mu) = N \text{Tr} \left[ \Sigma^{-1} S \right]\)

\(S = \frac{1}{N} \sum_{n=1}^N (x_n - \mu)(x_n - \mu)^T\)

\(\frac{\partial}{\partial \Sigma_{ij}} \sum_{n=1}^N (x_n - \mu)^T \Sigma^{-1} (x_n - \mu) = N \frac{\partial}{\partial \Sigma_{ij}} \text{Tr} \left[ \Sigma^{-1} S \right]\)

\(= N \text{Tr} \left[ \frac{\partial}{\partial \Sigma_{ij}} \Sigma^{-1} S \right] = -N \text{Tr} \left[ \Sigma^{-1} \frac{\partial \Sigma}{\partial \Sigma_{ij}} \Sigma^{-1} S \right]\)

\(= -N \text{Tr} \left[ \frac{\partial \Sigma}{\partial \Sigma_{ij}} \Sigma^{-1} S \Sigma^{-1} \right] = -N \left( \Sigma^{-1} S \Sigma^{-1} \right)_{ij}\)

\(-\frac{1}{2} \frac{\partial}{\partial \Sigma} \sum_{n=1}^N (x_n - \mu)^T \Sigma^{-1} (x_n - \mu) = \frac{N}{2} \Sigma^{-1} S \Sigma^{-1}\)

\(\frac{N}{2} \Sigma^{-1} = \frac{N}{2} \Sigma^{-1} S \Sigma^{-1}\)

\(\Sigma = S\)

\(\Sigma_{\text{ML}} = \frac{1}{N} \sum_{n=1}^N (x_n - \mu_{\text{ML}})(x_n - \mu_{\text{ML}})^T\)