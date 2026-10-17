

## Maximum Likelihood Estimator for Variance is Biased (i.e., underestimation)

In statistics, we evaluate the “goodness” of the estimation by checking if the estimation is “unbiased”. By saying “unbiased”, it means the expectation of the estimator equals to the true value, e.g. if $E[\bar{x}] = \mu$ then the mean estimator is unbiased. Now we will show that the equation actually holds for mean estimator.

$$E[\bar{x}] = E\left[\frac{1}{N}\sum_{i=1}^{N}x_i\right] = \frac{1}{N}\sum_{i=1}^{N}E[x_i]$$

$$= \frac{1}{N}\cdot N\cdot E[x]$$

$$= E[x] = \mu$$

The first line makes use of the assumption that the samples are drawn i.i.d from the true distribution, thus $E[x_i]$ is actually $E[x]$. From the proof above, it is shown that the mean estimator is unbiased.

## Maximum Likelihood Estimator for Variance is Biased (i.e., underestimation)

Now we move to the variance estimator. At the first glance, the variance estimator \(s^2 = \frac{1}{N} \sum_{i=1}^N (x_i - \overline{x})^2\) should follow because mean estimator \(\overline{x}\) is unbiased. However, it is not the

\(\mathbb{E}[s^2] = \mathbb{E}[\frac{1}{N} \sum_{i=1}^N (x_i - \overline{x})^2]\)
\(= \frac{1}{N} \mathbb{E}[\sum_{i=1}^N x_i^2 - 2 \sum_{i=1}^N x_i \overline{x} + \sum_{i=1}^N \overline{x}^2]\)

We know \(\sum_{i=1}^N x_i = N \cdot \overline{x}\) and \(\sum_{i=1}^N x_i^2 = N \cdot \overline{x^2}\). Plug these into the derivation:

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

## Maximum Likelihood Estimator for Variance is Biased (i.e., underestimation)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_694_0.png)

respect to the data set values, which themselves come from a Gaussian distribution with parameters μ and σ². It is straightforward to show that

$$E[\mu_{ML}] = \mu$$  (1.57)

$$E[\sigma^2_{ML}] = \left(\frac{N-1}{N}\right)\sigma^2$$  (1.58)

so that on average the maximum likelihood estimate will obtain the correct mean but will underestimate the true variance by a factor $(N-1)/N$. The intuition behind this result is given by Figure 1.15.

From (1.58) it follows that the following estimate for the variance parameter is unbiased

$$\tilde{\sigma}^2 = \frac{N}{N-1}\hat{\sigma}^2_{ML} = \frac{1}{N-1}\sum_{n=1}^{N}(x_n-\mu_{ML})^2.$$  (1.59)

## Curve Fitting Re-visited

The goal in the curve fitting problem is to be able to make predictions for the target variable _t_ given some new value of the input variable _x_ on the basis of a set of training data comprising _N_ input values **x** = (_x_<sub>1</sub>, ..., _x<sub>N</sub>_)<sup>T</sup> and their corresponding target values **t** = (_t_<sub>1</sub>, ..., _t<sub>N</sub>_)<sup>T</sup>. We can express our uncertainty over the value of the target variable using a probability distribution. For this purpose, we shall assume that, given the value of _x_, the corresponding value of _t_ has a Gaussian distribution with a mean equal to the value _y_(_x_, **w**) of the polynomial curve given by (1.61). Thus we have

p(t|_x_, **w**, β) = N (_t_|_y_(_x_, **w**), β<sup>-1</sup>) (1.60)

where, for consistency with the notation in later chapters, we have defined a precision parameter β corresponding to the inverse variance of the distribution. This is illustrated schematically in Figure 1.16.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_695_0.png)

