

## EM algorithm for GMM: experiment

### The Old Faithful data set:

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_441_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_441_1.png)

The Old Faithful geyser in Yellowstone National Park. ©Bruce T. Gourley www.brucegourley.com.

Plot of the time to the next eruption in minutes (vertical axis) versus the duration of the eruption in minutes (horizontal axis) for the Old Faithful data set.

### The Old Faithful data set:

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_442_0.png)

Illustration of the EM algorithm using the Old Faithful set as used for the illustration of the K-means algorithm

## An Alternative View of EM

## The general EM algorithm

- The log likelihood of a discrete latent variables model:

\(\ln p(X|\theta) = \ln \left\{ \sum_Z p(X, Z|\theta) \right\}\)

- The goal of EM algorithm is to find maximum likelihood solution for models having latent variables.

- For the complete data set {X, Z}, the log likelihood function:

\(\ln p(X|\theta) \longrightarrow \ln p(X, Z|\theta)\)

- For the incomplete data set {X}, we adopt the following steps to find maximum likelihood solution:

\(\theta^{old} \longleftarrow \theta^{new} = \arg \max_\theta Q(\theta, \theta^{old})\)

\(\downarrow\)

\(p(Z|X, \theta^{old}) \longrightarrow E_Z[\ln p(X, Z|\theta)] = \sum_Z p(Z|X, \theta^{old}) \ln p(X, Z|\theta) = Q(\theta, \theta^{old})\)

## The General EM Algorithm

Given a joint distribution $p(X,Z|\theta)$ over observed variables $X$ and latent variables $Z$, governed by parameters $\theta$, the goal is to maximize the likelihood function $p(X|\theta)$ with respect to $\theta$.

1. Choose an initial setting for the parameters $\theta^{\mathrm{old}}$.

2. **E step** Evaluate $p(Z|X,\theta^{\mathrm{old}})$.

3. **M step** Evaluate $\theta^{\mathrm{new}}$ given by
   $$\theta^{\mathrm{new}} = \arg\max_{\theta} Q(\theta,\theta^{\mathrm{old}})$$
   where
   $$Q(\theta,\theta^{\mathrm{old}})=\sum_Z p(Z|X,\theta^{\mathrm{old}})\ln p(X,Z|\theta).$$

4. Check for convergence of either the log likelihood or the parameter values. If the convergence criterion is not satisfied, then let
   $$\theta^{\mathrm{old}} \leftarrow \theta^{\mathrm{new}}$$
   and return to step 2.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_445_0.png)

> EM algorithm can be used to find MAP solution

## Gaussian mixtures revisited

$$\ln p(\mathbf{X}|\theta)=\ln\left\{\sum_{\mathbf{Z}}p(\mathbf{X},\mathbf{Z}|\theta)\right\}\;\Rightarrow\;\ln p(\mathbf{X}|\pi,\mu,\Sigma)=\sum_{n=1}^{N}\ln\left\{\sum_{k=1}^{K}\pi_k\mathcal{N}(x_n|\mu_k,\Sigma_k)\right\}$$

- *For the complete data set {X, Z}, the log likelihood function:*

$$p(\mathbf{X},\mathbf{Z}|\mu,\Sigma,\pi)=\prod_{n=1}^{N}\prod_{k=1}^{K}\pi_k^{z_{nk}}\mathcal{N}(x_n|\mu_k,\Sigma_k)^{z_{nk}},\qquad \sum_{k=1}^{K}\pi_k=1,\quad 0\leq\pi_k\leq1$$

$$\ln p(\mathbf{X},\mathbf{Z}|\mu,\Sigma,\pi)=\sum_{n=1}^{N}\sum_{k=1}^{K}z_{nk}\{\ln\pi_k+\ln\mathcal{N}(x_n|\mu_k,\Sigma_k)\}$$

$$\frac{\partial}{\partial\pi_k}\left\{\ln p(\mathbf{X},\mathbf{Z}|\mu,\Sigma,\pi)+\lambda\left(\sum_{k=1}^{K}\pi_k-1\right)\right\}=0\;\Rightarrow\;\pi_k=\frac{1}{N}\sum_{n=1}^{N}z_{nk}$$

## Gaussian mixtures revisited

\(\ln p(\mathbf{X}|\theta)=\ln \left\{\sum_{\mathbf{Z}} p(\mathbf{X}, \mathbf{Z}|\theta) \right\} \Longrightarrow \ln p(\mathbf{X}|\pi, \mu, \Sigma)=\sum_{n=1}^N \ln \left\{\sum_{k=1}^K \pi_k \mathcal{N}(\mathbf{x}_n|\mu_k, \Sigma_k) \right\}\)

- *For the incomplete data set {X}, the posterior distribution of the latent variables:*

\(p(\mathbf{x}|\mathbf{z})=\prod_{k=1}^K \mathcal{N}(\mathbf{x}|\mu_k, \Sigma_k)^{z_k} \quad p(\mathbf{z})=\prod_{k=1}^K \pi_k^{z_k} \Longrightarrow p(\mathbf{z}|\mathbf{x}) \propto p(\mathbf{x}|\mathbf{z})p(\mathbf{z})=\prod_{k=1}^K \left(\pi_k \mathcal{N}(\mathbf{x}|\mu_k, \Sigma_k)\right)^{z_k}\)

\(\Longrightarrow p(\mathbf{Z}|\mathbf{X}, \mu, \Sigma, \pi) \propto \prod_{n=1}^N \prod_{k=1}^K \left[\pi_k \mathcal{N}(\mathbf{x}_n|\mu_k, \Sigma_k)\right]^{z_{nk}}\)

- *Expectation:*

\(\mathbb{E}[z_{nk}] = \frac{\sum_{z_n} z_{nk} \prod_{k'} \left[\pi_{k'} \mathcal{N}(\mathbf{x}_n|\mu_{k'}, \Sigma_{k'})\right]^{z_{nk'}}}{\sum_{z_n} \prod_j \left[\pi_j \mathcal{N}(\mathbf{x}_n|\mu_j, \Sigma_j)\right]^{z_{nj}}} = \frac{\pi_k \mathcal{N}(\mathbf{x}_n|\mu_k, \Sigma_k)}{\sum_{j=1}^K \pi_j \mathcal{N}(\mathbf{x}_n|\mu_j, \Sigma_j)} = \gamma(z_{nk})\)

- *We have:* \(\ln p(\mathbf{X}, \mathbf{Z}|\mu, \Sigma, \pi) = \sum_{n=1}^N \sum_{k=1}^K z_{nk} \left\{\ln \pi_k + \ln \mathcal{N}(\mathbf{x}_n|\mu_k, \Sigma_k) \right\}\)

\(\mathbb{E}_\mathbf{Z}[\ln p(\mathbf{X}, \mathbf{Z}|\mu, \Sigma, \pi)] = \sum_{n=1}^N \sum_{k=1}^K \gamma(z_{nk}) \left\{\ln \pi_k + \ln \mathcal{N}(\mathbf{x}_n|\mu_k, \Sigma_k) \right\}\)

\(\mu^\text{old}, \Sigma^\text{old} \text{and } \pi^\text{old} \Longrightarrow \gamma(z_{nk}) \Longrightarrow \arg \max_{\mu, \Sigma, \pi} \mathbb{E}_\mathbf{Z}[\ln p(\mathbf{X}, \mathbf{Z}|\mu, \Sigma, \pi)] \Longrightarrow \mu^\text{new}, \Sigma^\text{new} \text{and } \pi^\text{new}\)

