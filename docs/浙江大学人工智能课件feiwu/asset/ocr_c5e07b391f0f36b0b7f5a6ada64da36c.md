# # Expectation and Variance

+   - Expectation of \( f(x) \) under a probability distribution \( p(x) \)
+   
+   \[\mathbb{E}[f] = \sum_x p(x)f(x) \qquad \mathbb{E}[f] = \int p(x)f(x) \, dx \qquad \mathbb{E}[f] \simeq \frac{1}{N} \sum_{n=1}^N f(x_n)\]

+   - Multiple variables:
+   
+   \[\mathbb{E}_x[f(x, y)] = \int p(x)f(x, y) \, dx\)

+   - Conditional expectation: \(\mathbb{E}_x[f|y] = \sum_x p(x|y)f(x)\)

+   - Variance of \( f(x) \): \(\boxed{\text{var}[f] = \mathbb{E}\left[(f(x) - \mathbb{E}[f(x)])^2\right] = \mathbb{E}[f(x)^2] - \mathbb{E}[f(x)]^2}\)

+   - Covariance:
+   
+   \[\begin{aligned}
+   \text{cov}[x, y] &= \mathbb{E}_{x,y}\left[\{x - \mathbb{E}[x]\}\{y - \mathbb{E}[y]\}\right] \\
+   &= \mathbb{E}_{x,y}[xy] - \mathbb{E}[x]\mathbb{E}[y] \\
+   \text{cov}[\mathbf{x}, \mathbf{y}] &= \mathbb{E}_{\mathbf{x}, \mathbf{y}}\left[\{\mathbf{x} - \mathbb{E}[\mathbf{x}]\}\{\mathbf{y}^T - \mathbb{E}[\mathbf{y}^T]\}\right] \\
+   &= \mathbb{E}_{\mathbf{x}, \mathbf{y}}[\mathbf{x}\mathbf{y}^T] - \mathbb{E}[\mathbf{x}]\mathbb{E}[\mathbf{y}^T].
+   \end{aligned}\)