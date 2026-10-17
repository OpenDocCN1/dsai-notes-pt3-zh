
## Multivariate Gaussian Distribution

The covariance of a random vector \(\mathbf{x}\) (For single random variables, we subtracted the mean before taking second moments in order to define a variance):

\[
\operatorname{cov}[\mathbf{x}] = \mathbb{E}\left[(\mathbf{x}-\mathbb{E}[\mathbf{x}])(\mathbf{x}-\mathbb{E}[\mathbf{x}])^\mathrm{T}\right]
\]

\[
\mathbb{E}[\mathbf{x}] = \boldsymbol{\mu}
\]

\[
\mathbb{E}[\mathbf{x}\mathbf{x}^\mathrm{T}] = \boldsymbol{\mu}\boldsymbol{\mu}^\mathrm{T} + \boldsymbol{\Sigma}
\]

\[
\operatorname{cov}[\mathbf{x}] = \boldsymbol{\Sigma}
\]

A general symmetric covariance matrix \(\boldsymbol{\Sigma}\) will have \(D(D+1)/2\) independent parameters, and there are another \(D\) independent parameters in \(\boldsymbol{\mu}\), giving \(D(D+3)/2\) parameters in total.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_626_0.png)

- \(\boldsymbol{\Sigma} = \operatorname{diag}(\sigma_i^2)\) — \(2D\) independent parameters
- \(\boldsymbol{\Sigma} = \sigma^2\mathbf{I}\) — isotropic covariance, \(D+1\) independent parameters

### Conditional Gaussian Distributions

\[
\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}, \boldsymbol{\Sigma}) = \frac{1}{(2\pi)^{D/2}} \frac{1}{|\boldsymbol{\Sigma}|^{1/2}} \exp \left\{ -\frac{1}{2}(\mathbf{x} - \boldsymbol{\mu})^\mathrm{T} \boldsymbol{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu}) \right\}
\]

\[
p(\mathbf{x}) = p(\mathbf{x}_a, \mathbf{x}_b) = p(\mathbf{x}_a|\mathbf{x}_b)p(\mathbf{x}_b)
\]

- If two sets of variables are jointly Gaussian, then the conditional distribution of one set conditioned on the other is again Gaussian.

\[
\mathbf{x} = \begin{pmatrix} \mathbf{x}_a \\ \mathbf{x}_b \end{pmatrix}, \quad
\boldsymbol{\mu} = \begin{pmatrix} \boldsymbol{\mu}_a \\ \boldsymbol{\mu}_b \end{pmatrix}, \quad
\boldsymbol{\Sigma} = \begin{pmatrix} \boldsymbol{\Sigma}_{aa} & \boldsymbol{\Sigma}_{ab} \\ \boldsymbol{\Sigma}_{ba} & \boldsymbol{\Sigma}_{bb} \end{pmatrix} \; \text{(covariance matrix)}, \quad
\boldsymbol{\Lambda} \equiv \boldsymbol{\Sigma}^{-1} = \begin{pmatrix} \boldsymbol{\Lambda}_{aa} & \boldsymbol{\Lambda}_{ab} \\ \boldsymbol{\Lambda}_{ba} & \boldsymbol{\Lambda}_{bb} \end{pmatrix} \; \text{(precision matrix)}.
\]

Both \(\boldsymbol{\Sigma}\) and \(\boldsymbol{\Lambda}\) can be taken to be symmetric, without loss of generality.

\[
p(\mathbf{x}_a|\mathbf{x}_b) \quad\longrightarrow\quad -\frac{1}{2}(\mathbf{x} - \boldsymbol{\mu})^\mathrm{T} \boldsymbol{\Sigma}^{-1}(\mathbf{x} - \boldsymbol{\mu}) = -\frac{1}{2}\mathbf{x}^\mathrm{T} \boldsymbol{\Sigma}^{-1}\mathbf{x} + \mathbf{x}^\mathrm{T} \boldsymbol{\Sigma}^{-1}\boldsymbol{\mu} + \mathrm{const}
\]

\[
= -\frac{1}{2}(\mathbf{x}_a - \boldsymbol{\mu}_a)^\mathrm{T} \boldsymbol{\Lambda}_{aa}(\mathbf{x}_a - \boldsymbol{\mu}_a) - \frac{1}{2}(\mathbf{x}_a - \boldsymbol{\mu}_a)^\mathrm{T} \boldsymbol{\Lambda}_{ab}(\mathbf{x}_b - \boldsymbol{\mu}_b)
\]

Completing the square:

\[
-\frac{1}{2}(\mathbf{x}_b - \boldsymbol{\mu}_b)^\mathrm{T} \boldsymbol{\Lambda}_{ba}(\mathbf{x}_a - \boldsymbol{\mu}_a) - \frac{1}{2}(\mathbf{x}_b - \boldsymbol{\mu}_b)^\mathrm{T} \boldsymbol{\Lambda}_{bb}(\mathbf{x}_b - \boldsymbol{\mu}_b).
\]

### Completing the square

\[
\mu_{a|b}\quad \Sigma_{a|b}\quad p(\mathbf{x}_a|\mathbf{x}_b)\quad\Rightarrow\quad -\frac{1}{2}\mathbf{x}^\mathrm{T}\boldsymbol{\Sigma}^{-1}\mathbf{x} + \mathbf{x}^\mathrm{T}\boldsymbol{\Sigma}^{-1}\boldsymbol{\mu} + \mathrm{const}
\]

\[
-\frac{1}{2}(\mathbf{x}_a - \boldsymbol{\mu}_a)^\mathrm{T}\boldsymbol{\Lambda}_{aa}(\mathbf{x}_a - \boldsymbol{\mu}_a) - \frac{1}{2}(\mathbf{x}_a - \boldsymbol{\mu}_a)^\mathrm{T}\boldsymbol{\Lambda}_{ab}(\mathbf{x}_b - \boldsymbol{\mu}_b) - \frac{1}{2}(\mathbf{x}_b - \boldsymbol{\mu}_b)^\mathrm{T}\boldsymbol{\Lambda}_{ba}(\mathbf{x}_a - \boldsymbol{\mu}_a) - \frac{1}{2}(\mathbf{x}_b - \boldsymbol{\mu}_b)^\mathrm{T}\boldsymbol{\Lambda}_{bb}(\mathbf{x}_b - \boldsymbol{\mu}_b)
\]

\[
-\frac{1}{2}\mathbf{x}_a^\mathrm{T}\boldsymbol{\Lambda}_{aa}\mathbf{x}_a \quad\Rightarrow\quad \boxed{\boldsymbol{\Sigma}_{a|b} = \boldsymbol{\Lambda}_{aa}^{-1}}
\]

\[
\mathbf{x}_a^\mathrm{T}\{\boldsymbol{\Lambda}_{aa}\boldsymbol{\mu}_a - \boldsymbol{\Lambda}_{ab}(\mathbf{x}_b - \boldsymbol{\mu}_b)\} = \mathbf{x}_a^\mathrm{T}\boldsymbol{\Sigma}_{a|b}^{-1}\boldsymbol{\mu}_{a|b} \quad\Rightarrow\quad \boldsymbol{\Sigma}_{a|b}^{-1}\boldsymbol{\mu}_{a|b} = \boldsymbol{\Lambda}_{aa}\boldsymbol{\mu}_a - \boldsymbol{\Lambda}_{ab}(\mathbf{x}_b - \boldsymbol{\mu}_b)
\]

\[
\Rightarrow\quad \boldsymbol{\mu}_{a|b} = \boldsymbol{\Sigma}_{a|b}\{\boldsymbol{\Lambda}_{aa}\boldsymbol{\mu}_a - \boldsymbol{\Lambda}_{ab}(\mathbf{x}_b - \boldsymbol{\mu}_b)\} = \boxed{\boldsymbol{\mu}_a - \boldsymbol{\Lambda}_{aa}^{-1}\boldsymbol{\Lambda}_{ab}(\mathbf{x}_b - \boldsymbol{\mu}_b)}
\]

\[
\boxed{\begin{pmatrix} \mathbf{A} & \mathbf{B} \\ \mathbf{C} & \mathbf{D} \end{pmatrix}^{-1} = \begin{pmatrix} \mathbf{M} & -\mathbf{M}\mathbf{B}\mathbf{D}^{-1} \\ -\mathbf{D}^{-1}\mathbf{C}\mathbf{M} & \mathbf{D}^{-1} + \mathbf{D}^{-1}\mathbf{C}\mathbf{M}\mathbf{B}\mathbf{D}^{-1} \end{pmatrix}}
\]

\[
\mathbf{M} = (\mathbf{A} - \mathbf{B}\mathbf{D}^{-1}\mathbf{C})^{-1}
\]

\[
\begin{pmatrix} \boldsymbol{\Sigma}_{aa} & \boldsymbol{\Sigma}_{ab} \\ \boldsymbol{\Sigma}_{ba} & \boldsymbol{\Sigma}_{bb} \end{pmatrix}^{-1} = \begin{pmatrix} \boldsymbol{\Lambda}_{aa} & \boldsymbol{\Lambda}_{ab} \\ \boldsymbol{\Lambda}_{ba} & \boldsymbol{\Lambda}_{bb} \end{pmatrix}
\]

\[
\boldsymbol{\Lambda}_{aa} = (\boldsymbol{\Sigma}_{aa} - \boldsymbol{\Sigma}_{ab}\boldsymbol{\Sigma}_{bb}^{-1}\boldsymbol{\Sigma}_{ba})^{-1}
\]

\[
\boldsymbol{\Lambda}_{ab} = -(\boldsymbol{\Sigma}_{aa} - \boldsymbol{\Sigma}_{ab}\boldsymbol{\Sigma}_{bb}^{-1}\boldsymbol{\Sigma}_{ba})^{-1}\boldsymbol{\Sigma}_{ab}\boldsymbol{\Sigma}_{bb}^{-1}
\]

\[
\boxed{\begin{aligned} \boldsymbol{\mu}_{a|b} &= \boldsymbol{\mu}_a + \boldsymbol{\Sigma}_{ab}\boldsymbol{\Sigma}_{bb}^{-1}(\mathbf{x}_b - \boldsymbol{\mu}_b) \\ \boldsymbol{\Sigma}_{a|b} &= \boldsymbol{\Sigma}_{aa} - \boldsymbol{\Sigma}_{ab}\boldsymbol{\Sigma}_{bb}^{-1}\boldsymbol{\Sigma}_{ba}. \end{aligned}}
\]

The mean of the conditional distribution \(p(\mathbf{x}_a|\mathbf{x}_b)\) is a linear function of \(\mathbf{x}_b\), and the covariance is independent of \(\mathbf{x}_a\).
