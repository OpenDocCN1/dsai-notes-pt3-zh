

## Probability densities

- Probability density function:
  \( p(x \in (a, b)) = \int_a^b p(x) \, dx \)

- \( p(x) \) must satisfy the two conditions:
  \( p(x) \geqslant 0 \)
  \( \int_{-\infty}^{\infty} p(x) \, dx = 1 \)

- Cumulative distribution function
  – The probability density can be expressed as the derivative of a CDF.
  \( P(z) = \int_{-\infty}^z p(x) \, dx \qquad P'(x) = p(x) \)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_965_0.png)

## Expectation and Variance

- Expectation of \( f(x) \) under a probability distribution \( p(x) \)
  \[\mathbb{E}[f] = \sum_x p(x)f(x) \qquad \mathbb{E}[f] = \int p(x)f(x) \, dx \qquad \mathbb{E}[f] \simeq \frac{1}{N} \sum_{n=1}^N f(x_n)\]

- Multiple variables:
  \[\mathbb{E}_x[f(x, y)] = \int p(x)f(x, y) \, dx\]

- Conditional expectation: \(\mathbb{E}_x[f|y] = \sum_x p(x|y)f(x)\)

- Variance of \( f(x) \): \(\boxed{\text{var}[f] = \mathbb{E}\left[(f(x) - \mathbb{E}[f(x)])^2\right] = \mathbb{E}[f(x)^2] - \mathbb{E}[f(x)]^2}\)

- Covariance:
  \[\begin{aligned}
  \text{cov}[x, y] &= \mathbb{E}_{x,y}\left[\{x - \mathbb{E}[x]\}\{y - \mathbb{E}[y]\}\right] \\
  &= \mathbb{E}_{x,y}[xy] - \mathbb{E}[x]\mathbb{E}[y] \\
  \text{cov}[\mathbf{x}, \mathbf{y}] &= \mathbb{E}_{\mathbf{x}, \mathbf{y}}\left[\{\mathbf{x} - \mathbb{E}[\mathbf{x}]\}\{\mathbf{y}^T - \mathbb{E}[\mathbf{y}^T]\}\right] \\
  &= \mathbb{E}_{\mathbf{x}, \mathbf{y}}[\mathbf{x}\mathbf{y}^T] - \mathbb{E}[\mathbf{x}]\mathbb{E}[\mathbf{y}^T].
  \end{aligned}\]

## Expectation and Variance

- Some properties of Expectation:

- \(\mathbb{P} [X = c] = 1 \implies \mathbb{E} [X] = c\)

- \(\mathbb{E} [cX] = c\mathbb{E} [X]\)

- \(\mathbb{E} [X + Y] = \mathbb{E} [X] + \mathbb{E} [Y]\)

- \(\mathbb{P} [X \ge Y] = 1 \implies \mathbb{E} [X] \ge \mathbb{E} [Y]\)

- \(\mathbb{P} [X = Y] = 1 \implies \mathbb{E} [X] = \mathbb{E} [Y]\)

- \(\mathbb{E} [X] = \mathbb{E} [\mathbb{E} [X | Y]]\)

- \(\mathbb{E} [Y + Z | X] = \mathbb{E} [Y | X] + \mathbb{E} [Z | X]\)

- \(\mathbb{E} [Y | X] = c \implies \text{Cov} [X, Y] = 0\)

\(\mathbb{E}[X + c] = \mathbb{E}[X] + c\)
\(\mathbb{E}[X + Y] = \mathbb{E}[X] + \mathbb{E}[Y]\)
\(\mathbb{E}[aX] = a\mathbb{E}[X]\)
\(\mathbb{E}[aX + bY + c] = a\mathbb{E}[X] + b\mathbb{E}[Y] + c\)

## Expectation and Variance

- Some properties of Variance:

Definition and properties

- \(\mathbb{V}[X] = \sigma_X^2 = \mathbb{E}[(X - \mathbb{E}[X])^2] = \mathbb{E}[X^2] - \mathbb{E}[X]^2\)

- \(\mathbb{V}\left[\sum_{i=1}^n X_i\right] = \sum_{i=1}^n \mathbb{V}[X_i] + \sum_{i \neq j} \text{Cov}[X_i, X_j] = \sum_{i=1}^n \mathbb{V}[X_i] \quad \text{if } X_i \perp\!\!\perp X_j\)

Standard deviation \(\text{sd}[X] = \sqrt{\mathbb{V}[X]} = \sigma_X\)

Covariance

- \(\text{Cov}[X, Y] = \mathbb{E}[(X - \mathbb{E}[X])(Y - \mathbb{E}[Y])] = \mathbb{E}[XY] - \mathbb{E}[X]\mathbb{E}[Y]\)

- \(\text{Cov}[X, a] = 0\)

- \(\text{Cov}[X, X] = \mathbb{V}[X]\)

- \(\text{Cov}[X, Y] = \text{Cov}[Y, X]\)

- \(\text{Cov}[aX, bY] = ab\text{Cov}[X, Y] \Rightarrow V[aX] = \text{Cov}[aX, aX] = a^2V[X]\)

- \(\text{Cov}[X + a, Y + b] = \text{Cov}[X, Y]\)

## Expectation and Variance

### the Variance of the Sum of Two Independent Random Variables is the Sum of the Variances

Imagine two such random variables _X_ and _Y_.

| X   | probability   |
|-----|---------------|
| x₁  | p₁            |
| x₂  | p₂            |
| ... | ...           |
| xₙ  | pₙ            |

| Y   | probability   |
|-----|---------------|
| y₁  | q₁            |
| y₂  | q₂            |
| ... | ...           |
| yₘ  | qₘ            |

Since _X_ and _Y_ are independent random variables, the probability of _X_
taking on the value _x<sub>i</sub>_ and _Y_ the value _y<sub>j</sub>_ is simply the product _p<sub>i</sub>q<sub>j</sub>_.

\(Var(X+Y)=\sum_{i,j}p_iq_j(x_i+y_j-\mu_X-\mu_Y)^2=\sum_{i,j}p_iq_j(x_i-\mu_X)^2+\sum_{i,j}p_iq_j(y_j-\mu_Y)^2+2\sum_{i,j}p_iq_j(x_i-\mu_X)(y_j-\mu_Y)=(\sum_jq_j)Var(X)+(\sum_ip_i)Var(Y)+2(\sum_ip_i(x_i-\mu_X))(\sum_jq_j(y_j-\mu_Y))=1\cdot Var(X)+1\cdot Var(Y)+2\cdot 0\cdot 0=Var(X)+Var(Y).\)

