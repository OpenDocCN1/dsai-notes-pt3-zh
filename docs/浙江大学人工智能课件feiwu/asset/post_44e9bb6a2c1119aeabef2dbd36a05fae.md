

## Marginal Gaussian Distributions

\(p(\mathbf{x}_a, \mathbf{x}_b) := -\frac{1}{2}(\mathbf{x}_a - \mu_a)^\mathrm{T} \Lambda_{aa} (\mathbf{x}_a - \mu_a) - \frac{1}{2}(\mathbf{x}_a - \mu_a)^\mathrm{T} \Lambda_{ab} (\mathbf{x}_b - \mu_b) - \frac{1}{2}(\mathbf{x}_b - \mu_b)^\mathrm{T} \Lambda_{ba} (\mathbf{x}_a - \mu_a) - \frac{1}{2}(\mathbf{x}_b - \mu_b)^\mathrm{T} \Lambda_{bb} (\mathbf{x}_b - \mu_b)\)

\(p(\mathbf{x}_a) = \int p(\mathbf{x}_a, \mathbf{x}_b) \, \mathrm{d}\mathbf{x}_b\)

1. considering the terms involving \(\mathbf{x}_b\) and then completing the square:

\(-\frac{1}{2} \mathbf{x}_b^\mathrm{T} \Lambda_{bb} \mathbf{x}_b + \mathbf{x}_b^\mathrm{T} \mathbf{m} = -\frac{1}{2} (\mathbf{x}_b - \Lambda_{bb}^{-1} \mathbf{m})^\mathrm{T} \Lambda_{bb} (\mathbf{x}_b - \Lambda_{bb}^{-1} \mathbf{m}) + \frac{1}{2} \mathbf{m}^\mathrm{T} \Lambda_{bb}^{-1} \mathbf{m}\)

\(\int \exp \left\{ -\frac{1}{2} (\mathbf{x}_b - \Lambda_{bb}^{-1} \mathbf{m})^\mathrm{T} \Lambda_{bb} (\mathbf{x}_b - \Lambda_{bb}^{-1} \mathbf{m}) \right\} \, \mathrm{d}\mathbf{x}_b \qquad \mathbf{m} = \Lambda_{bb} \mu_b - \Lambda_{ba} (\mathbf{x}_a - \mu_a)\)

2. considering the remaining terms that depend on \(\mathbf{x}_a\):

\(\frac{1}{2} [\Lambda_{bb} \mu_b - \Lambda_{ba} (\mathbf{x}_a - \mu_a)]^\mathrm{T} \Lambda_{bb}^{-1} [\Lambda_{bb} \mu_b - \Lambda_{ba} (\mathbf{x}_a - \mu_a)] - \frac{1}{2} \mathbf{x}_a^\mathrm{T} \Lambda_{aa} \mathbf{x}_a + \mathbf{x}_a^\mathrm{T} (\Lambda_{aa} \mu_a + \Lambda_{ab} \mu_b) + \text{const}\)

\(= -\frac{1}{2} \mathbf{x}_a^\mathrm{T} (\Lambda_{aa} - \Lambda_{ab} \Lambda_{bb}^{-1} \Lambda_{ba}) \mathbf{x}_a + \mathbf{x}_a^\mathrm{T} (\Lambda_{aa} - \Lambda_{ab} \Lambda_{bb}^{-1} \Lambda_{ba})^{-1} \mu_a + \text{const}\)

\(\begin{pmatrix} \Lambda_{aa} & \Lambda_{ab} \\ \Lambda_{ba} & \Lambda_{bb} \end{pmatrix}^{-1} = \begin{pmatrix} \Sigma_{aa} & \Sigma_{ab} \\ \Sigma_{ba} & \Sigma_{bb} \end{pmatrix}\)

\((\Lambda_{aa} - \Lambda_{ab} \Lambda_{bb}^{-1} \Lambda_{ba})^{-1} = \Sigma_{aa}\)

\(\Sigma_a = (\Lambda_{aa} - \Lambda_{ab} \Lambda_{bb}^{-1} \Lambda_{ba})^{-1}\)

\(\Sigma_a (\Lambda_{aa} - \Lambda_{ab} \Lambda_{bb}^{-1} \Lambda_{ba}) \mu_a = \mu_a\)

\(\mathbb{E}[\mathbf{x}_a] = \mu_a\)

\(\text{cov}[\mathbf{x}_a] = \Sigma_{aa}\)

## Partitioned Gaussians

### the marginal and conditional distributions of a partitioned Gaussian are summarized below

### Partitioned Gaussians

Given a joint Gaussian distribution \(\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}, \boldsymbol{\Sigma})\) with \(\boldsymbol{\Lambda} \equiv \boldsymbol{\Sigma}^{-1}\) and

\(\mathbf{x} = \left(\begin{array}{ c }
\mathbf{x}_a \\
\mathbf{x}_b
\end{array}\right), \quad \boldsymbol{\mu} = \left(\begin{array}{ c }
\boldsymbol{\mu}_a \\
\boldsymbol{\mu}_b
\end{array}\right)\)

\(\boldsymbol{\Sigma} = \left(\begin{array}{ c c }
\boldsymbol{\Sigma}_{aa} & \boldsymbol{\Sigma}_{ab} \\
\boldsymbol{\Sigma}_{ba} & \boldsymbol{\Sigma}_{bb}
\end{array}\right), \quad \boldsymbol{\Lambda} = \left(\begin{array}{ c c }
\boldsymbol{\Lambda}_{aa} & \boldsymbol{\Lambda}_{ab} \\
\boldsymbol{\Lambda}_{ba} & \boldsymbol{\Lambda}_{bb}
\end{array}\right).\)

### Conditional distribution:

\(p(\mathbf{x}_a|\mathbf{x}_b) = \mathcal{N}(\mathbf{x}|\boldsymbol{\mu}_{a|b}, \boldsymbol{\Lambda}_{aa}^{-1})\)

\(\boldsymbol{\mu}_{a|b} = \boldsymbol{\mu}_a - \boldsymbol{\Lambda}_{aa}^{-1} \boldsymbol{\Lambda}_{ab} (\mathbf{x}_b - \boldsymbol{\mu}_b).\)

### Marginal distribution:

\(p(\mathbf{x}_a) = \mathcal{N}(\mathbf{x}_a|\boldsymbol{\mu}_a, \boldsymbol{\Sigma}_{aa}).\)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_630_0.png)

## Bayes' Theorem for Gaussian Variables

ln p(z) = ln p(x) + ln p(y|x) = -1/2(x - μ)^TΛ(x - μ) - 1/2(y - Ax - b)^TL(y - Ax - b) + const

-1/2(x - μ)^TΣ^-1(x - μ) = -1/2x^TΣ^-1x + x^TΣ^-1μ + const

-1/2x^T(Λ + A^TLA)x - 1/2y^TLy + 1/2y^TLAx + 1/2x^TA^TLy = -1/2 (x y)^T (Λ + A^TLA -A^TL -LA L) (x y) = -1/2z^TRz

R = (Λ + A^TLA -A^TL -LA L) cov[z] = R^-1 = (Λ^-1 Λ^-1A^T AA^-1 L^-1 + AA^-1A^T)

x^TΛμ - x^TA^TLb + y^TLb = (x y)^T (Λμ - A^TLb Lb)

E[z] = R^-1 (Λμ - A^TLb Lb) = (μ Aμ + b)

Conditional distribution: p(xa|xb) = N(x|μa|b, Λaa^-1) μa|b = μa - Λaa^-1Λab(xb - μb) Marginal distribution: p(xa) = N(xa|μa, Σaa)

E[y] = Aμ + b cov[y] = L^-1 + AA^-1A^T E[x|y] = (Λ + A^TLA)^-1 {A^TL(y - b) + Λμ} cov[x|y] = (Λ + A^TLA)^-1.

