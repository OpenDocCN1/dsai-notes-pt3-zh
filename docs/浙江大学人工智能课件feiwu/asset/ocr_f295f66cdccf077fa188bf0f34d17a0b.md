# # Maximum Likelihood Estimator for Variance is Biased (i.e., underestimation)

Since the samples are drawn i.i.d.

\(\text{VAR}[\sum_{i=1}^N x_i] = \sum_{i=1}^N \text{VAR}[x] = N \cdot \text{VAR}[x]\)

Thus,

\(\sigma_x^2 = \frac{1}{N} \text{VAR}[x] = \frac{1}{N} \sigma_x^2\)

Plug back to the \(\mathbb{E}[s^2]\) derivation,

\(\mathbb{E}[s^2] = \frac{N-1}{N} \sigma_x^2\)

Therefore, \(\mathbb{E}[s^2] \neq \sigma_x^2\) and it is shown that we tend to underestimate the variance. In order to overcome this biased problem, the maximum likelihood estimator for variance can be slightly modified to take this into account:

\(s^2 = \frac{1}{N-1} \sum_{i=1}^N (x_i - \overline{x})^2\)

It is easy to show that this modified variance estimator is unbiased.