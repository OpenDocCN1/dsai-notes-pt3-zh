
## Special case of softmax

- If we consider a softmax function for two classes:

\[
p(C_1 \mid \mathbf{x}) = \frac{\exp(a_1)}{\exp(a_1)+\exp(a_2)} = \frac{1}{1+\exp(-(a_1-a_2))} = \sigma(a_1-a_2).
\]

- So the **logistic sigmoid** is just a special case of the **softmax function** that avoids using redundant parameters:
  - Adding the same constant to both \(a_1\) and \(a_2\) has no effect.
  - The over-parameterization of the softmax is because probabilities must add up to one.

## Logistic regression

- Logistic regression model:

- Only \(M\) parameters need to be estimated.

logistic sigmoid function

\[
p(C_1|\phi) = y(\phi) = \sigma \left( \mathbf{w}^T \phi \right) \qquad p(C_2|\phi) = 1 - p(C_1|\phi) \qquad \sigma(a) = \frac{1}{1 + \exp(-a)}
\]

- For a data set \(\{\phi_n, t_n\}\), where \(t_n \in \{0, 1\}\) and \(\phi_n = \phi(\mathbf{x}_n)\), \(n=1, \dots, N\), the likelihood function can be written

\[
p(\mathbf{t}|\mathbf{w}) = \prod_{n=1}^N y_n^{t_n} \{1 - y_n\}^{1-t_n} \quad \text{where } \mathbf{t} = (t_1, \dots, t_N)^T \text{ and } y_n = p(C_1|\phi_n).
\]

- Cross-entropy error function:

\[
E(\mathbf{w}) = - \ln p(\mathbf{t}|\mathbf{w}) = - \sum_{n=1}^N \{t_n \ln y_n + (1 - t_n) \ln(1 - y_n)\}
\]

\[
y_n = \sigma(a_n)
\]

\[
a_n = \mathbf{w}^T \phi_n
\]

\[
\frac{d\sigma}{da} = \sigma(1 - \sigma)
\]

\[
\frac{\partial E}{\partial y_n} = \frac{1 - t_n}{1 - y_n} - \frac{t_n}{y_n} = \frac{y_n(1 - t_n) - t_n(1 - y_n)}{y_n(1 - y_n)} = \frac{y_n - t_n}{y_n(1 - y_n)}
\]

\[
\frac{\partial y_n}{\partial a_n} = \frac{\partial \sigma(a_n)}{\partial a_n} = \sigma(a_n)(1 - \sigma(a_n)) = y_n(1 - y_n)
\]

No closed-form solution

\[
\nabla E(\mathbf{w}) = \sum_{n=1}^N \frac{\partial E}{\partial y_n} \frac{\partial y_n}{\partial a_n} \nabla a_n = \sum_{n=1}^N (y_n - t_n) \phi_n = \sum_{n=1}^N (\sigma(\mathbf{w}^T \phi_n) - t_n) \phi_n
\]

## Iterative reweighted least squares (IRLS) algorithm

- *Newton-Raphson iterative optimization scheme:*

\[
\mathbf{w}^{(\mathrm{new})} = \mathbf{w}^{(\mathrm{old})} - \mathbf{H}^{-1} \nabla E(\mathbf{w})
\]

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_600_0.png)

- For linear regression model with the sum-of-squares error function:

\[
\nabla E(\mathbf{w})=\sum_{n=1}^{N}(\mathbf{w}^{T}\boldsymbol{\phi}_n-t_n)\boldsymbol{\phi}_n=\mathbf{\Phi}^{T}\mathbf{\Phi}\mathbf{w}-\mathbf{\Phi}^{T}\mathbf{t}
\]

\[
\mathbf{H}=\nabla\nabla E(\mathbf{w})=\sum_{n=1}^{N}\boldsymbol{\phi}_n\boldsymbol{\phi}_n^{T}=\mathbf{\Phi}^{T}\mathbf{\Phi}
\]

\[
\mathbf{w}^{(\mathrm{new})}=\mathbf{w}^{(\mathrm{old})}-(\mathbf{\Phi}^{T}\mathbf{\Phi})^{-1}\{\mathbf{\Phi}^{T}\mathbf{\Phi}\mathbf{w}^{(\mathrm{old})}-\mathbf{\Phi}^{T}\mathbf{t}\}=(\mathbf{\Phi}^{T}\mathbf{\Phi})^{-1}\mathbf{\Phi}^{T}\mathbf{t}
\]

- For logistic regression model with cross-entropy error function:

\[
\nabla E(\mathbf{w})=\sum_{n=1}^{N}(y_n-t_n)\boldsymbol{\phi}_n=\mathbf{\Phi}^{T}(\mathbf{y}-\mathbf{t})
\]

\[
\mathbf{H}=\nabla\nabla E(\mathbf{w})=\sum_{n=1}^{N}y_n(1-y_n)\boldsymbol{\phi}_n\boldsymbol{\phi}_n^{T}=\mathbf{\Phi}^{T}\mathbf{R}\mathbf{\Phi}
\]

\[
\mathbf{w}^{(\mathrm{new})}=\mathbf{w}^{(\mathrm{old})}-(\mathbf{\Phi}^{T}\mathbf{R}\mathbf{\Phi})^{-1}\mathbf{\Phi}^{T}(\mathbf{y}-\mathbf{t})=(\mathbf{\Phi}^{T}\mathbf{R}\mathbf{\Phi})^{-1}\{\mathbf{\Phi}^{T}\mathbf{R}\mathbf{\Phi}\mathbf{w}^{(\mathrm{old})}-\mathbf{\Phi}^{T}(\mathbf{y}-\mathbf{t})\}
\]

\[
=(\mathbf{\Phi}^{T}\mathbf{R}\mathbf{\Phi})^{-1}\mathbf{\Phi}^{T}\mathbf{R}\mathbf{z}
\]

\[
\mathbf{z}=\mathbf{\Phi}\mathbf{w}^{(\mathrm{old})}-\mathbf{R}^{-1}(\mathbf{y}-\mathbf{t})
\]

\[
a_n(\mathbf{w})\simeq a_n(\mathbf{w}^{(\mathrm{old})})+\left.\frac{da_n}{dy_n}\right|_{\mathbf{w}^{(\mathrm{old})}}(t_n-y_n)
\]

\[
=\boldsymbol{\phi}_n^{T}\mathbf{w}^{(\mathrm{old})}-\frac{(y_n-t_n)}{y_n(1-y_n)}=z_n
\]

*local linear approximation to the logistic sigmoid function around the current operating point* \(\mathbf{w}^{(\mathrm{old})}\)
