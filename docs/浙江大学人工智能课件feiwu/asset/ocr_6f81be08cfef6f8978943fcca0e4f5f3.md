# # Curve fitting re-visited

+   • Express uncertainty over the value of the target variable using a probability distribution:

\( p(t|x, \mathbf{w}, \beta) = \mathcal{N} \left( t|y(x, \mathbf{w}), \beta^{-1} \right) \)

training data \(\{ \mathbf{x}, \mathbf{t} \}\)

\( p(\mathbf{t}|\mathbf{x}, \mathbf{w}, \beta) = \prod_{n=1}^{N} \mathcal{N} \left( t_n|y(x_n, \mathbf{w}), \beta^{-1} \right) \)

\( \ln p(\mathbf{t}|\mathbf{x}, \mathbf{w}, \beta) = -\frac{\beta}{2} \sum_{n=1}^{N} \{ y(x_n, \mathbf{w}) - t_n \}^2 + \frac{N}{2} \ln \beta - \frac{N}{2} \ln(2\pi) \)

\( p(t|x, \mathbf{w}_{ML}, \beta_{ML}) = \mathcal{N} \left( t|y(x, \mathbf{w}_{ML}), \beta_{ML}^{-1} \right) \)

![](bbox=[0.586, 0.345, 0.979, 0.705])