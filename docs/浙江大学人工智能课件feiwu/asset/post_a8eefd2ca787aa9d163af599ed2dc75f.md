

maximizing (1.54) with respect to \(\sigma^2\), we obtain the maximum likelihood solution for the variance in the form

\(\sigma_{\text{ML}}^2 = \frac{1}{N} \sum_{n=1}^N (x_n - \mu_{\text{ML}})^2\) (1.56)

which is the _sample variance_ measured with respect to the sample mean \(\mu_{\text{ML}}\). Note

\(\ln P(x | \mu, \sigma^2) = -\frac{1}{2\sigma^2} \sum_{n=1}^N (x_n - \mu)^2 - \frac{N}{2} \ln \sigma^2 - \frac{N}{2} \ln(2\pi)\)

Taking the partial derivative of the log likelihood with respect to \(\sigma^2\), and setting to 0, we have:

\(-\frac{N}{2\sigma^2} + \frac{1}{2\sigma^4} \sum_{n=1}^N (x_n - \mu)^2 \equiv 0\)

\(-N \cdot \sigma^2 + \sum_{n=1}^N (x_n - \mu)^2 = 0\)

\(\sigma^2 = \frac{1}{N} \sum_{n=1}^N (x_n - \mu)^2\)

\((\ln x)' = \frac{1}{x}\)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_978_0.png)

## Maximum Likelihood Estimator for Variance is Biased (i.e., underestimation)

In statistics, we evaluate the “goodness” of the estimation by checking if the estimation is “unbiased”. By saying “unbiased”, it means the expectation of the estimator equals to the true value, e.g. if E[x̄] = μ then the mean estimator is unbiased. Now we will show that the equation actually holds for mean estimator.

```
E[x̄] = E[1/N Σ xi] = 1/N Σ E[xi]

     = 1/N · N · E[x]

     = E[x] = μ
```

The first line makes use of the assumption that the samples are drawn i.i.d from the true distribution, thus E[xi] is actually E[x]. From the proof above, it is shown that the mean estimator is unbiased.

## Maximum Likelihood Estimator for Variance is Biased (i.e., underestimation)

Now we move to the variance estimator. At the first glance, the variance estimator \( s^2 = \frac{1}{N} \sum_{i=1}^N (x_i - \overline{x})^2 \) should follow because mean estimator \(\overline{x}\) is unbiased. However, it is not the

\(\mathbb{E}[s^2] = \mathbb{E}[\frac{1}{N} \sum_{i=1}^N (x_i - \overline{x})^2]\)
\(= \frac{1}{N} \mathbb{E}[\sum_{i=1}^N x_i^2 - 2 \sum_{i=1}^N x_i \overline{x} + \sum_{i=1}^N \overline{x}^2]\)

We know \(\sum_{i=1}^N x_i = N \cdot \overline{x}\) and \(\sum_{i=1}^N x^2 = N \cdot \overline{x^2}\). Plug these into the derivation:

\(\mathbb{E}[s^2] = \frac{1}{N} \mathbb{E}[\sum_{i=1}^N x_i^2 - 2N \cdot \overline{x}^2 + N \cdot \overline{x}^2]\)
\(= \frac{1}{N} \mathbb{E}[\sum_{i=1}^N x_i^2 - N \cdot \overline{x}^2]\)
\(= \frac{1}{N} \mathbb{E}[\sum_{i=1}^N x_i^2] - \mathbb{E}[\overline{x}^2]\)
\(= \mathbb{E}[x^2] - \mathbb{E}[\overline{x}^2]\)

According to the alternative definition of variance, \(\sigma_x^2 = \mathbb{E}[x^2] - \mathbb{E}[x]^2\) and similarly, \(\sigma_\overline{x}^2 = \mathbb{E}[\overline{x}^2] - \mathbb{E}[\overline{x}]^2\), where the random variable is \(\overline{x}\). Note that \(\mathbb{E}[x] = \mathbb{E}[\overline{x}] = \mu\). Plug the 2 equations to the derivation:

\(\mathbb{E}[s^2] = (\sigma_x^2 + \mu^2) - (\sigma_\overline{x}^2 + \mu^2)\)
\(= \sigma_x^2 - \sigma_\overline{x}^2\)
\(\sigma_\overline{x}^2 = \text{VAR}[\overline{x}] = \text{VAR}[\frac{1}{N} \sum_{i=1}^N x_i] = \frac{1}{N^2} \text{VAR}[\sum_{i=1}^N x_i]\)

## Maximum Likelihood Estimator for Variance is Biased (i.e., underestimation)

Since the samples are drawn i.i.d.

\(\text{VAR}[\sum_{i=1}^N x_i] = \sum_{i=1}^N \text{VAR}[x] = N \cdot \text{VAR}[x]\)

Thus,

\(\sigma_x^2 = \frac{1}{N} \text{VAR}[x] = \frac{1}{N} \sigma_x^2\)

Plug back to the \(\mathbb{E}[s^2]\) derivation,

\(\mathbb{E}[s^2] = \frac{N-1}{N} \sigma_x^2\)

Therefore, \(\mathbb{E}[s^2] \neq \sigma_x^2\) and it is shown that we tend to underestimate the variance. In order to overcome this biased problem, the maximum likelihood estimator for variance can be slightly modified to take this into account:

\(s^2 = \frac{1}{N-1} \sum_{i=1}^N (x_i - \overline{x})^2\)

It is easy to show that this modified variance estimator is unbiased.

## Introduction to Statistical Learning and Modeling
### Curve fitting: probabilistic perspective

