

## K-means clustering

- The procedure of k-means algorithm:

\( J = \sum_{n=1}^N \sum_{k=1}^K r_{nk} \| \mathbf{x}_n - \boldsymbol{\mu}_k \|^2 \)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1078_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_0.png)

- The convergence of J:

$$J=\sum_{n=1}^{N}\sum_{k=1}^{K}r_{nk}\lVert x_n-\mu_k\rVert^2$$

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_1.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_2.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_3.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_4.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_5.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_6.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_7.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_8.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1079_9.png)

- Online k-means algorithm (sequential k-means):

$$J=\sum_{n=1}^{N}\sum_{k=1}^{K}r_{nk}\lVert x_n-\mu_k\rVert^2$$

$$\mu_k=\frac{\sum_n r_{nk}x_n}{\sum_n r_{nk}}\quad\rightarrow\quad \mu_k^{\mathrm{new}}=\mu_k^{\mathrm{old}}+\eta_n(x_n-\mu_k^{\mathrm{old}})$$

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1080_0.png)

- K-medoids algorithm:
  - Chooses input data points as centers;
  - Works with an arbitrary matrix of distances between data points instead of Euclidean distance.
    - E.g. Manhattan distance or Minkowski distance

$$J=\sum_{n=1}^{N}\sum_{k=1}^{K}r_{nk}\lVert x_n-\mu_k\rVert^2\quad\rightarrow\quad \tilde{J}=\sum_{n=1}^{N}\sum_{k=1}^{K}r_{nk}\mathcal{V}(x_n,\mu_k)$$

## The limitation of K-means clustering

- The K-means algorithm often convergence to a local minimum.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1082_0.png)

- The K-means algorithm adopts the hard assignment and doesn’t consider the data density and probabilistic distribution.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1083_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1083_1.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1084_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1084_1.png)

## Gaussian mixture distribution

- **Definition:**

$$p(x)=\sum_{k=1}^{K}\pi_k\mathcal{N}(x\mid\mu_k,\Sigma_k)$$

$$\sum_{k=1}^{K}\pi_k=1,\qquad 0\leq\pi_k\leq1$$

- Introduce a $K$-dimensional binary random variable $z=(z_1,z_2,\ldots,z_K)^T$

$$z_k\in\{0,1\},\qquad\sum_k z_k=1,\qquad p(z_k=1)=\pi_k$$

$$p(z)=\prod_{k=1}^{K}\pi_k^{z_k}$$

- If $p(x\mid z_k=1)=\mathcal{N}(x\mid\mu_k,\Sigma_k)$, then $$p(x\mid z)=\prod_{k=1}^{K}\mathcal{N}(x\mid\mu_k,\Sigma_k)^{z_k}$$

> Latent variable

- **Equivalent formulation of the Gaussian mixture:**

$$p(x)=\sum_z p(x\mid z)p(z)=\sum_z\prod_{k=1}^{K}\left(\pi_k\mathcal{N}(x\mid\mu_k,\Sigma_k)\right)^{z_k}$$

$$=\sum_{j=1}^{K}\prod_{k=1}^{K}\left(\pi_k\mathcal{N}(x\mid\mu_k,\Sigma_k)\right)^{I_{kj}}=\sum_{j=1}^{K}\pi_j\mathcal{N}(x\mid\mu_j,\Sigma_j)$$

$$I_{kj}=\begin{cases}1&\text{if }k=j\\0&\text{otherwise.}\end{cases}$$

$$\gamma(z_k)=p(z_k=1\mid x)=\frac{p(z_k=1)p(x\mid z_k=1)}{\sum_{j=1}^{K}p(z_j=1)p(x\mid z_j=1)}=\frac{\pi_k\mathcal{N}(x\mid\mu_k,\Sigma_k)}{\sum_{j=1}^{K}\pi_j\mathcal{N}(x\mid\mu_j,\Sigma_j)}$$

*responsibility*

$$p(\mathbf{x})=\sum_z p(\mathbf{x}|z)p(z)=\sum_{j=1}^{K}\pi_j\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}_j,\boldsymbol{\Sigma}_j)$$

$$\gamma(z_k)\equiv p(z_k=1|\mathbf{x})=\frac{p(z_k=1)p(\mathbf{x}|z_k=1)}{\sum_{j=1}^{K}p(z_j=1)p(\mathbf{x}|z_j=1)}=\frac{\pi_k\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}_k,\boldsymbol{\Sigma}_k)}{\sum_{j=1}^{K}\pi_j\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}_j,\boldsymbol{\Sigma}_j)}$$

*responsibility*

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1087_0.png)

**Figure 9.5** Example of 500 points drawn from the mixture of 3 Gaussians shown in Figure 2.23. (a) Samples from the joint distribution $p(\mathbf{x},z)p(\mathbf{x}|z)$ in which the three states of $z$, corresponding to the three components of the mixture, are depicted in red, green, and blue, and (b) the corresponding samples from the marginal distribution $p(\mathbf{x})$, which is obtained by simply ignoring the values of $z$ and just plotting the $\mathbf{x}$ values. The data set in (a) is said to be complete, whereas that in (b) is incomplete. (c) The same samples in which the colours represent the value of the responsibilities $\gamma(z_{nk})$ associated with data point $\mathbf{x}_n$, obtained by plotting the corresponding point using proportions of red, blue, and green ink given by $\gamma(z_{nk})$ for $k=1,2,3$, respectively.

