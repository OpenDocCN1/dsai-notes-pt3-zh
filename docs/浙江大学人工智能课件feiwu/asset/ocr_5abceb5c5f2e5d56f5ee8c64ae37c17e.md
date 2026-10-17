# # Geometry of least squares

+   - The geometrical interpretation of the least-squares solution

$$\ln p(\mathbf{t}|\mathbf{w},\beta)=\sum_{n=1}^{N}\ln\mathcal{N}(t_n|\mathbf{w}^{\mathrm{T}}\boldsymbol{\phi}(\mathbf{x}_n),\beta^{-1})=\frac{N}{2}\ln\beta-\frac{N}{2}\ln(2\pi)-\beta E_D(\mathbf{w})$$

$$E_D(\mathbf{w})=\frac{1}{2}\sum_{n=1}^{N}\{t_n-\mathbf{w}^{\mathrm{T}}\boldsymbol{\phi}(\mathbf{x}_n)\}^2=\frac{1}{2}\|\mathbf{t}-\Phi\mathbf{w}\|^2\qquad \mathbf{w}_{\mathrm{ML}}=(\Phi^{\mathrm{T}}\Phi)^{-1}\Phi^{\mathrm{T}}\mathbf{t}$$

$$\Phi=\begin{pmatrix}\phi_0(\mathbf{x}_1)&\phi_1(\mathbf{x}_1)&\cdots&\phi_{M-1}(\mathbf{x}_1)\\\phi_0(\mathbf{x}_2)&\phi_1(\mathbf{x}_2)&\cdots&\phi_{M-1}(\mathbf{x}_2)\\\vdots&\vdots&\ddots&\vdots\\\phi_0(\mathbf{x}_N)&\phi_1(\mathbf{x}_N)&\cdots&\phi_{M-1}(\mathbf{x}_N)\end{pmatrix}=\begin{pmatrix}\boldsymbol{\phi}_0&\boldsymbol{\phi}_1&\cdots&\boldsymbol{\phi}_{M-1}\end{pmatrix},\qquad \boldsymbol{\phi}_j=\begin{pmatrix}\phi_j(\mathbf{x}_1)\\\phi_j(\mathbf{x}_2)\\\vdots\\\phi_j(\mathbf{x}_N)\end{pmatrix}$$

$$\mathbf{w}=(w_0,\ldots,w_{M-1})^{\mathrm{T}}$$

Geometrical interpretation of the least-squares solution, in an $N$-dimensional space whose axes are the values of $t_1,\ldots,t_N$. The least-squares regression function is obtained by finding the orthogonal projection of the data vector onto the subspace spanned by the basis functions $\phi_j(\mathbf{x})$ in which each basis function is viewed as a vector $\boldsymbol{\phi}_j$ of length $N$ with elements $\phi_j(\mathbf{x}_n)$.

![](bbox=[0.536, 0.675, 0.915, 0.999])