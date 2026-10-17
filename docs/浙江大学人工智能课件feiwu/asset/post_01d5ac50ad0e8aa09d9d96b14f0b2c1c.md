

## Curve Fitting Re-visited

We now use the training data {**x**_,_**t**} to determine the values of the unknown parameters **w** and \(\beta\) by maximum likelihood. If the data are assumed to be drawn independently from the distribution (1.60), then the likelihood function is given by

\(p(\mathbf{t}|\mathbf{x},\mathbf{w},\beta)=\prod_{n=1}^N\mathcal{N}\left(t_n|y(x_n,\mathbf{w}),\beta^{-1}\right).\) (1.61)

As we did in the case of the simple Gaussian distribution earlier, it is convenient to maximize the logarithm of the likelihood function. Substituting for the form of the Gaussian distribution, given by (1.46), we obtain the log likelihood function in the form

\(\mathrm{ln}p(\mathbf{t}|\mathbf{x},\mathbf{w},\beta)=-\frac{\beta}{2}\sum_{n=1}^N\{y(x_n,\mathbf{w})-t_n\}^2+\frac{N}{2}\mathrm{ln}\beta-\frac{N}{2}\mathrm{ln}(2\pi).\) (1.62)

Consider first the determination of the maximum likelihood solution for the polynomial coefficients, which will be denoted by **w**ML. These are determined by maximizing (1.62) with respect to **w**. For this purpose, we can omit the last two terms on the right-hand side of (1.62) because they do not depend on **w**. Also, we note that scaling the log likelihood by a positive constant coefficient does not alter the location of the maximum with respect to **w**, and so we can replace the coefficient \(\beta/2\) with 1_/_2. Finally, instead of maximizing the log likelihood, we can equivalently minimize the negative log likelihood. We therefore see that maximizing likelihood is equivalent, so far as determining **w** is concerned, to minimizing the _sum-of-squares error function_ defined by (1.2). Thus the sum-of-squares error function has arisen as a consequence of maximizing likelihood under the assumption of a Gaussian noise distribution.

Having determined the parameters **w** and \(\beta\), we can now make predictions for new values of \(x\). Because we now have a probabilistic model, these are expressed in terms of the predictive distribution that gives the probability distribution over \(t\), rather than simply a point estimate, and is obtained by substituting the maximum likelihood parameters into (1.60) to give

\(p(t|x,\mathbf{w}_\text{ML},\beta_\text{ML})=\mathcal{N}\left(t|y(x,\mathbf{w}_\text{ML}),\beta_\text{ML}^{-1}\right).\) (1.64)

Now let us take a step towards a more Bayesian approach and introduce a prior distribution over the polynomial coefficients \(\mathbf{w}\). For simplicity, let us consider a Gaussian distribution of the form

\(p(\mathbf{w}|\alpha)=\mathcal{N}(\mathbf{w}|\mathbf{0},\alpha^{-1}\mathbf{I})=\left(\frac{\alpha}{2\pi}\right)^{(M+1)/2}\mathrm{exp}\left\{-\frac{\alpha}{2}\mathbf{w}^\mathrm{T}\mathbf{w}\right\}\) (1.65)

where \(\alpha\) is the precision of the distribution, and \(M+1\) is the total number of elements in the vector \(\mathbf{w}\) for an \(M\)th order polynomial. Variables such as \(\alpha\), which control the distribution of model parameters, are called hyperparameters. Using Bayes’ theorem, the posterior distribution for \(\mathbf{w}\) is proportional to the product of the prior distribution and the likelihood function

\(p(\mathbf{w}|\mathbf{x},\mathbf{t},\alpha,\beta)\propto p(\mathbf{t}|\mathbf{x},\mathbf{w},\beta)p(\mathbf{w}|\alpha).\) (1.66)

We can now determine \(\mathbf{w}\) by finding the most probable value of \(\mathbf{w}\) given the data, in other words by maximizing the posterior distribution. This technique is called maximum posterior, or simply MAP. Taking the negative logarithm of (1.66) and combining with (1.62) and (1.65), we find that the maximum of the posterior is given by the minimum of

\(\frac{\beta}{2}\sum_{n=1}^N\{y(x_n,\mathbf{w})-t_n\}^2+\frac{\alpha}{2}\mathbf{w}^\mathrm{T}\mathbf{w}.\) (1.67)

Thus we see that maximizing the posterior distribution is equivalent to minimizing the regularized sum-of-squares error function encountered earlier in the form (1.4), with a regularization parameter given by \(\lambda = \alpha/\beta\).

## Bayesian curve fitting

Although we have included a prior distribution \(p(\mathbf{w}|\alpha)\), we are so far still making a point estimate of **w** and so this does not yet amount to a Bayesian treatment. In a fully Bayesian approach, we should consistently apply the sum and product rules of probability, which, as we shall see shortly, that we integrate over all values of **w**. Such marginalizations lie at the heart of Bayesian methods for pattern recognition.

In the curve fitting problem, we are given the training data **x** and **t**, along with a new test point \(x\), and our goal is to predict the value of \(t\). We therefore wish to evaluate the predictive distribution \(p(t|x,\mathbf{x},\mathbf{t})\). Here we shall assume that the parameters \(\alpha\) and \(\beta\) are fixed and known in advance (in later chapters we shall discuss how such parameters can be inferred from data in a Bayesian setting).

A Bayesian treatment simply corresponds to a consistent application of the sum and product rules of probability, which allow the predictive distribution to be written in the form

\(p(t|x,\mathbf{x},\mathbf{t})=\int p(t|x,\mathbf{w})p(\mathbf{w}|\mathbf{x},\mathbf{t})\mathrm{d}\mathbf{w}.\) (1.68)

Here \(p(t|x,\mathbf{w})\) is given by (1.60), and we have omitted the dependence on \(\alpha\) and \(\beta\) to simplify the notation. Here \(p(\mathbf{w}|\mathbf{x},\mathbf{t})\) is the posterior distribution over parameters, and can be found by normalizing the right-hand side of (1.66).

