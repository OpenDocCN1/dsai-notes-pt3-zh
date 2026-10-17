

## Probabilistic Discriminative Models

### Fixed basis functions

Classification models work on feature space instead of original input space by nonlinear basis functions:

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_592_0.png)

**Figure 4.12** Illustration of the role of nonlinear basis functions in linear classification models. The left plot shows the original input space \((x_1, x_2)\) together with data points from two classes labelled red and blue. Two ‘Gaussian’ basis functions \(\phi_1(x)\) and \(\phi_2(x)\) are defined in this space with centres shown by the green circles and with contours shown by the green circles. The right-hand plot shows the corresponding feature space \((\phi_1, \phi_2)\) together with the linear decision boundary obtained given by a logistic regression model of the form discussed in Section 4.3.2. This corresponds to a nonlinear decision boundary in the original input space, shown by the black curve in the left-hand plot.

### Logistic regression

- Consider the problem of two-class classification.

- We have seen that the posterior probability of class C<sub>1</sub> can be written as a logistic sigmoid function:

\( p(C_1|\mathbf{x}) = \frac{1}{1 + \exp(-\mathbf{w}^T\mathbf{x})} = \sigma(\mathbf{w}^T\mathbf{x}), \)

where \( p(C_2|\mathbf{x}) = 1 - p(C_1|\mathbf{x}) \), and we omit the bias term for clarity.

- This model is known as logistic regression (although this is a model for classification rather than regression).

Note that for generative models, we would first determine the class conditional densities and class-specific priors, and then use Bayes' rule to obtain the posterior probabilities.

Here we model \( p(C_k|\mathbf{x}) \) directly.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_593_0.png)

### Maximum Likelihood for Logistic regression

- We observed a training dataset \(\{ \mathbf{x}_n, t_n \}, n = 1, .., N; t_n \in \{0, 1\}\).

- Maximize the probability of getting the label right, so the likelihood function takes form:

\( p(\mathbf{t}|\mathbf{X}, \mathbf{w}) = \prod_{n=1}^N \left[ y_n^{t_n} (1 - y_n)^{1 - t_n} \right], \quad y_n = \sigma(\mathbf{w}^T \mathbf{x}_n). \)

- Taking the negative log of the likelihood, we can define cross-entropy error function (that we want to minimize):

\( E(\mathbf{w}) = - \ln p(\mathbf{t}|\mathbf{X}, \mathbf{w}) = - \sum_{n=1}^N \left[ t_n \ln y_n + (1 - t_n) \ln(1 - y_n) \right] = \sum_{n=1}^N E_n. \)

- Differentiating and using the chain rule:

\( \frac{\mathrm{d}}{\mathrm{d}y_n} E_n = \frac{y_n - t_n}{y_n(1 - y_n)}, \quad \frac{\mathrm{d}}{\mathrm{d}\mathbf{w}} y_n = y_n(1 - y_n)\mathbf{x}_n, \quad \frac{\mathrm{d}}{\mathrm{d}a}\sigma(a) = \sigma(a)(1 - \sigma(a)). \)

\( \frac{\mathrm{d}}{\mathrm{d}\mathbf{w}} E_n = \frac{\mathrm{d}E_n}{\mathrm{d}y_n} \frac{\mathrm{d}y_n}{\mathrm{d}\mathbf{w}} = (y_n - t_n)\mathbf{x}_n. \)

Note that the factor involving the derivative of the logistic function cancelled.

### Multi-class for Logistic regression

- For the multiclass case, we represent posterior probabilities by a softmax transformation of linear functions of input variables :

\( p(C_k|\mathbf{x}) = y_k(\mathbf{x}) = \frac{\exp(\mathbf{w}_k^T\mathbf{x})}{\sum_j \exp(\mathbf{w}_j^T\mathbf{x})} \)

- Unlike in generative models, here we will use maximum likelihood to determine parameters of this discriminative model directly.

- As usual, we observed a dataset \(\{ \mathbf{x}_n, t_n \}, n = 1, ..., N\), where we use 1-of-K encoding for the target vector \(\mathbf{t}_n\).

- So if \(\mathbf{x}_n\) belongs to class \(C_k\), then **t** is a binary vector of length K containing a single 1 for element k (the correct class) and 0 elsewhere.

- For example, if we have K=5 classes, then an input that belongs to class 2 would be given a target vector:

\( t = (0, 1, 0, 0, 0)^T \)

- We can write down the likelihood function:

\( p(\mathbf{T}|\mathbf{X}, \mathbf{w}_1, ..., \mathbf{w}_K) = \prod_{n=1}^N \left[ \prod_{k=1}^K p(C_k|\mathbf{x}_n)^{t_{nk}} \right] = \prod_{n=1}^N \left[ \prod_{k=1}^K y_{nk}^{t_{nk}} \right] \)

N × K binary matrix of target variables.

Only one term corresponding to correct class contributes.

where \( y_{nk} = p(C_k|\mathbf{x}_n) = \frac{\exp(\mathbf{w}_k^T\mathbf{x}_n)}{\sum_j \exp(\mathbf{w}_j^T\mathbf{x}_n)} \).

- Taking the negative logarithm gives the cross-entropy entropy function for multi-class classification problem:

\( E(\mathbf{w}_1, ..., \mathbf{w}_K) = -\ln p(\mathbf{T}|\mathbf{X}, \mathbf{w}_1, ..., \mathbf{w}_K) = -\sum_{n=1}^N \left[ \sum_{k=1}^K t_{nk} \ln y_{nk} \right] \).

- Taking the gradient:

\( \nabla E_{\mathbf{w}_j}(\mathbf{w}_1, ...\mathbf{w}_K) = \sum_{n=1}^N (y_{nj} - t_{nj})\mathbf{x}_n \).

