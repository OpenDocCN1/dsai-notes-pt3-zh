# # Expectation and Variance

+   • Some properties of Variance:

Definition and properties

+   • \(\mathbb{V}[X] = \sigma_X^2 = \mathbb{E}[(X - \mathbb{E}[X])^2] = \mathbb{E}[X^2] - \mathbb{E}[X]^2\)

+   • \(\mathbb{V}\left[\sum_{i=1}^n X_i\right] = \sum_{i=1}^n \mathbb{V}[X_i] + \sum_{i \neq j} \text{Cov}[X_i, X_j] = \sum_{i=1}^n \mathbb{V}[X_i] \quad \text{if } X_i \perp\!\!\perp X_j\)

Standard deviation \(\text{sd}[X] = \sqrt{\mathbb{V}[X]} = \sigma_X\)

Covariance

+   • \(\text{Cov}[X, Y] = \mathbb{E}[(X - \mathbb{E}[X])(Y - \mathbb{E}[Y])] = \mathbb{E}[XY] - \mathbb{E}[X]\mathbb{E}[Y]\)

+   • \(\text{Cov}[X, a] = 0\)

+   • \(\text{Cov}[X, X] = \mathbb{V}[X]\)

+   • \(\text{Cov}[X, Y] = \text{Cov}[Y, X]\)

+   • \(\text{Cov}[aX, bY] = ab\text{Cov}[X, Y] \Rightarrow V[aX] = \text{Cov}[aX, aX] = a^2V[X]\)

+   • \(\text{Cov}[X + a, Y + b] = \text{Cov}[X, Y]\)