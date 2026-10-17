

## The Gaussian Distribution

- Central limit theorem:

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_610_0.png)

Figure 2.6 Histogram plots of the mean of _N_ uniformly distributed numbers for various values of _N_. We observe that as _N_ increases, the distribution tends towards a Gaussian.

\(\mathcal{N}(x|\mu, \sigma^2) = \frac{1}{(2\pi\sigma^2)^{1/2}} \exp \left\{ -\frac{1}{2\sigma^2}(x - \mu)^2 \right\}\)

\(\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}, \boldsymbol{\Sigma}) = \frac{1}{(2\pi)^{D/2}} \frac{1}{|\boldsymbol{\Sigma}|^{1/2}} \exp \left\{ -\frac{1}{2}(\mathbf{x} - \boldsymbol{\mu})^\mathrm{T} \boldsymbol{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu}) \right\}\)

## Multivariate Gaussian Distribution

$$\mathcal{N}(\mathbf{x}|\boldsymbol{\mu},\mathbf{\Sigma})=\frac{1}{(2\pi)^{D/2}|\mathbf{\Sigma}|^{1/2}}\exp\left\{-\frac{1}{2}(\mathbf{x}-\boldsymbol{\mu})^\mathrm{T}\mathbf{\Sigma}^{-1}(\mathbf{x}-\boldsymbol{\mu})\right\}$$

The functional dependence of the Gaussian on **x** is through the quadratic form

$$\Delta^2=(\mathbf{x}-\boldsymbol{\mu})^\mathrm{T}\mathbf{\Sigma}^{-1}(\mathbf{x}-\boldsymbol{\mu})$$

- Mahalanobis distance $\Delta$ → Euclidean distance (when $\Delta$ is identity matrix)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_611_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_611_1.png)

```
mu = [0 0];
Sigma = [.25 .3; .3 1];
%Sigma = [.25 0; 0 1];
%Sigma = [0.5 0; 0 0.5];
x1 = -3:1:3;
x2 = -3:1:3;
[X1,X2] = meshgrid(x1,x2);
F = mvnpdf([X1(:) X2(:)],mu,Sigma);

F = reshape(F,length(x2),length(x1));
surf(x1,x2,F);
caxis([min(F(:))-5*range(F(:)),max(F(:))]);
axis([-3 3 -3 3 0 .4])
xlabel('x1'); ylabel('x2');
zlabel('Probability Density');
```

## Multivariate Gaussian Distribution

First of all, we note that the matrix \(\Sigma\) can be taken to be symmetric, without loss of generality, because any antisymmetric component would disappear from the exponent. Now consider the eigenvector equation for the covariance matrix

\(\Sigma \mathbf{u}_i = \lambda_i \mathbf{u}_i\) (2.45)

where \(i = 1, \ldots, D\). Because \(\Sigma\) is a real, symmetric matrix its eigenvalues will be real, and its eigenvectors can be chosen to form an orthonormal set, so that

\(\mathbf{u}_i^T \mathbf{u}_j = I_{ij}\) (2.46)

where \(I_{ij}\) is the \(i,j\) element of the identity matrix and satisfies

\(I_{ij} = \begin{cases} 1, & \text{if } i = j \\ 0, & \text{otherwise.} \end{cases}\) (2.47)

The covariance matrix \(\Sigma\) can be expressed as an expansion in terms of its eigenvectors in the form

\(\Sigma = \sum_{i=1}^D \lambda_i \mathbf{u}_i \mathbf{u}_i^T\) (2.48)

and similarly the inverse covariance matrix \(\Sigma^{-1}\) can be expressed as

\(\Sigma^{-1} = \sum_{i=1}^D \frac{1}{\lambda_i} \mathbf{u}_i \mathbf{u}_i^T.\) (2.49)

## Multivariate Gaussian Distribution

Substituting (2.49) into (2.44), the quadratic form becomes

\(\Delta^2 = \sum_{i=1}^D \frac{y_i^2}{\lambda_i}\) (2.50)

where we have defined

\(y_i = \mathbf{u}_i^\mathrm{T}(\mathbf{x} - \mu).\) (2.51)

We can interpret \(\{y_i\}\) as a new coordinate system defined by the orthonormal vectors \(\mathbf{u}_i\) that are shifted and rotated with respect to the original \(x_i\) coordinates. Forming the vector \(\mathbf{y} = (y_1, \dots, y_D)^\mathrm{T}\), we have

\(\mathbf{y} = \mathbf{U}(\mathbf{x} - \mu)\) (2.52)

where **U** is a matrix whose rows are given by \(\mathbf{u}_i^\mathrm{T}\). From (2.46) it follows that **U** is an _orthogonal_ matrix, i.e., it satisfies \(\mathbf{U}\mathbf{U}^\mathrm{T} = \mathbf{I}\), and hence also \(\mathbf{U}^\mathrm{T}\mathbf{U} = \mathbf{I}\), where **I** is the identity matrix.

## Multivariate Gaussian Distribution

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_614_0.png)

The quadratic form, and hence the Gaussian density, will be constant on surfaces for which (2.51) is constant. If all of the eigenvalues \(\lambda_i\) are positive, then these surfaces represent ellipsoids, with their centres at \(\mu\) and their axes oriented along \(\mathbf{u}_i\), and with scaling factors in the directions of the axes given by \(\lambda_i^{1/2}\), as illustrated in Figure 2.7.

For the Gaussian distribution to be well defined, it is necessary for all of the eigenvalues \(\lambda_i\) of the covariance matrix to be strictly positive, otherwise the distribution cannot be properly normalized. A matrix whose eigenvalues are strictly positive is said to be _positive definite_.

