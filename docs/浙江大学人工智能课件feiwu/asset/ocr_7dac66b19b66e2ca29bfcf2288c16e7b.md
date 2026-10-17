# # Multivariate Gaussian Distribution

+   - It's normalized!

\(\int_{-\infty}^{\infty} \mathcal{N} \left(x|\mu, \sigma^{2}ight) \mathrm{d} x=1\)

\(\mathcal{N}(\mathbf{x}|\boldsymbol{\mu}, \boldsymbol{\Sigma})=\frac{1}{(2 \pi)^{D / 2}} \frac{1}{|\boldsymbol{\Sigma}|^{1 / 2}} \exp \left\{-\frac{1}{2}(\mathbf{x}-\boldsymbol{\mu})^{\mathrm{T}} \boldsymbol{\Sigma}^{-1}(\mathbf{x}-\boldsymbol{\mu})\right\}\)

\(\Delta^{2}=\sum_{i=1}^{D} \frac{y_{i}^{2}}{\lambda_{i}}\)
\(|\mathbf{J}|=1\)

\(\boldsymbol{\Sigma}=\mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{\mathrm{T}} \Longrightarrow|\boldsymbol{\Sigma}|=|\mathbf{U} \boldsymbol{\Lambda} \mathbf{U}^{\mathrm{T}}|=|\mathbf{U}||\boldsymbol{\Lambda}||\mathbf{U}^{\mathrm{T}}|=|\mathbf{U}||\mathbf{U}^{\mathrm{T}}||\boldsymbol{\Lambda}|=|\boldsymbol{\Lambda}| \Longrightarrow|\boldsymbol{\Sigma}|^{1 / 2}=\prod_{j=1}^{D} \lambda_{j}^{1 / 2}\)

\(p(\mathbf{y})=p(\mathbf{x})|\mathbf{J}|=\prod_{j=1}^{D} \frac{1}{(2 \pi \lambda_{j})^{1 / 2}} \exp \left\{-\frac{y_{j}^{2}}{2 \lambda_{j}}\right\}\)

\(\Longrightarrow \int p(\mathbf{y}) \mathrm{d} \mathbf{y}=\prod_{j=1}^{D} \int_{-\infty}^{\infty} \frac{1}{(2 \pi \lambda_{j})^{1 / 2}} \exp \left\{-\frac{y_{j}^{2}}{2 \lambda_{j}}\right\} \mathrm{d} y_{j}=1 \Longrightarrow \int p(\mathbf{y}) \mathrm{d} \mathbf{y}=1\)