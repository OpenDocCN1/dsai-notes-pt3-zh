# # Multivariate Gaussian Distribution

\(\mathcal{N}(\mathbf{x}|\mu, \Sigma) = \frac{1}{(2\pi)^{D/2}} \frac{1}{|\Sigma|^{1/2}} \exp \left\{ -\frac{1}{2}(\mathbf{x} - \mu)^\mathrm{T}\Sigma^{-1}(\mathbf{x} - \mu) \right\}\)

\(\Delta^2 = (\mathbf{x} - \mu)^\mathrm{T}\Sigma^{-1}(\mathbf{x} - \mu) = \mathbf{y}^\mathrm{T}\Lambda^{-1}\mathbf{y} \qquad \Sigma^{-1} = \mathbf{U}\Lambda^{-1}\mathbf{U}^\mathrm{T}\)

\(\Delta^2 = \sum_{i=1}^D \frac{y_i^2}{\lambda_i} \qquad y_i = \mathbf{u}_i^\mathrm{T}(\mathbf{x} - \mu) \qquad \mathbf{y} = \mathbf{U}^\mathrm{T}(\mathbf{x} - \mu)\)

![](bbox=[0.724, 0.309, 0.967, 0.585])

![](bbox=[0.703, 0.645, 0.986, 0.964])

**Figure 2.8** Contours of constant probability density for a Gaussian distribution in two dimensions in which the covariance matrix is (a) in general form, (b) diagonal, in which the elliptical contours are aligned with the coordinate axes, and (c) proportional to the identity matrix, in which the contours are concentric circles.

![](bbox=[0.279, 0.645, 0.694, 0.964])