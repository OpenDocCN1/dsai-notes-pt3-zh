# # The difficulty of estimating parameters in GMM by ML

\(p(x)=\sum_z p(x|z)p(z)=\sum_{j=1}^K \pi_j \mathcal{N}(x|\mu_j, \Sigma_j)\)

+   - The log of the likelihood function of GMM:
+   
+   \(\ln p(X|\pi, \mu, \Sigma)=\sum_{n=1}^N \ln \left\{\sum_{k=1}^K \pi_k \mathcal{N}(x_n|\mu_k, \Sigma_k)\right\}\)

+   - Issue #1: singularities
+     - Collapses onto a specific data point

+   - Issue #2: identifiability
+     - Total K! equivalent solutions

+   - Issue #3: no closed form solution
+     - The derivatives of the log likelihood
+       are complex.

![](bbox=[0.5293, 0.5281, 0.9785, 0.9156])