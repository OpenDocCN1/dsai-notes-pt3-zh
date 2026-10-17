# Gaussian mixture distribution

+   - **Definition:**

$$p(x)=\sum_{k=1}^{K}\pi_k\mathcal{N}(x\mid\mu_k,\Sigma_k)$$

$$\sum_{k=1}^{K}\pi_k=1,\qquad 0\leq\pi_k\leq1$$

+   - Introduce a $K$-dimensional binary random variable $z=(z_1,z_2,\ldots,z_K)^T$

$$z_k\in\{0,1\},\qquad\sum_k z_k=1,\qquad p(z_k=1)=\pi_k$$

$$p(z)=\prod_{k=1}^{K}\pi_k^{z_k}$$

+   - If $p(x\mid z_k=1)=\mathcal{N}(x\mid\mu_k,\Sigma_k)$, then $$p(x\mid z)=\prod_{k=1}^{K}\mathcal{N}(x\mid\mu_k,\Sigma_k)^{z_k}$$

> Latent variable

+   - **Equivalent formulation of the Gaussian mixture:**

$$p(x)=\sum_z p(x\mid z)p(z)=\sum_z\prod_{k=1}^{K}\left(\pi_k\mathcal{N}(x\mid\mu_k,\Sigma_k)\right)^{z_k}$$

$$=\sum_{j=1}^{K}\prod_{k=1}^{K}\left(\pi_k\mathcal{N}(x\mid\mu_k,\Sigma_k)\right)^{I_{kj}}=\sum_{j=1}^{K}\pi_j\mathcal{N}(x\mid\mu_j,\Sigma_j)$$

$$I_{kj}=\begin{cases}1&\text{if }k=j\\0&\text{otherwise.}\end{cases}$$

$$\gamma(z_k)=p(z_k=1\mid x)=\frac{p(z_k=1)p(x\mid z_k=1)}{\sum_{j=1}^{K}p(z_j=1)p(x\mid z_j=1)}=\frac{\pi_k\mathcal{N}(x\mid\mu_k,\Sigma_k)}{\sum_{j=1}^{K}\pi_j\mathcal{N}(x\mid\mu_j,\Sigma_j)}$$

*responsibility*