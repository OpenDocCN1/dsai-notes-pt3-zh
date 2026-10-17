

## The perceptron algorithm

- Analogue hardware implementations:

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_581_0.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_581_1.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_581_2.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_581_3.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_581_4.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_581_5.png)

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_581_6.png)

Figure 4.7 Illustration of the convergence of the perceptron learning algorithm, showing data points from two classes (red and blue) in a two-dimensional feature space \((\phi_1, \phi_2)\). The top left plot shows the initial parameter vector **w** shown as a black arrow together with the corresponding decision boundary (black line), in which the arrow points towards the decision region which classified as belonging to the red class. The data point circled in green is misclassified and so its feature vector is added to the current weight vector, giving the new decision boundary shown in the top right plot. The bottom left plot shows the next misclassified point to be considered, indicated by the green circle, and its feature vector is again added to the weight vector giving the decision boundary shown in the bottom right plot for which all data points are correctly classified.

## Probabilistic Generative Models

We turn next to a probabilistic view of classification and show how models with linear decision boundaries arise from simple assumptions about the distribution of the data. In Section 1.5.4, we discussed the distinction between the discriminative and the generative approaches to classification. Here we shall adopt a generative approach in which we model the class-conditional densities _p_(**x**|_C<sub>k</sub>_), as well as the class priors _p_(_C<sub>k</sub>_), and then use these to compute the posterior probabilities _p_(_C<sub>k</sub>_|**x**) through Bayes’ theorem.

Consider first of all the case of two classes. The posterior probability for class _C_<sub>1</sub> can be written as

\(p(C_1|\mathbf{x})=\frac{p(\mathbf{x}|C_1)p(C_1)}{p(\mathbf{x}|C_1)p(C_1)+p(\mathbf{x}|C_2)p(C_2)}\)

\(=\frac{1}{1+\exp(-a)}=\sigma(a)\) (4.57)

where we have defined

\(a=\mathrm{ln}\frac{p(\mathbf{x}|C_1)p(C_1)}{p(\mathbf{x}|C_2)p(C_2)}\) (4.58)

and \(\sigma(a)\) is the _logistic sigmoid_ function defined by

\(\sigma(a)=\frac{1}{1+\exp(-a)}\) (4.59)

## Probabilistic Generative Models

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_584_0.png)

Figure 4.9 Plot of the logistic sigmoid function \(\sigma(a)\) defined by (4.59), shown in red, together with the scaled probit function \(\Phi(\lambda a)\), for \(\lambda^2 = \pi/8\), shown in dashed blue, where \(\Phi(a)\) is defined by (4.114). The scaling factor \(\tau/8\) is chosen so that the derivatives of the two curves are equal for \(a = 0\).

\(\sigma(a) = \frac{1}{1 + \exp(-a)}\) (4.59)

\(\sigma(-a) = 1 - \sigma(a)\) (4.60)

as is easily verified. The inverse of the logistic sigmoid is given by

\(a = \ln \left( \frac{\sigma}{1 - \sigma} \right)\) (4.61)

and is known as the _logit_ function. It represents the log of the ratio of probabilities \(\ln \left[ p(C_1|\mathbf{x}) / p(C_2|\mathbf{x}) \right]\) for the two classes, also known as the _log odds_.

## Probabilistic Generative Models: softmax function

- For case of K>2 classes, we have the following multi-class generalization:

\(p(C_k|\mathbf{x}) = \frac{p(\mathbf{x}|C_k)p(C_k)}{\sum_j p(\mathbf{x}|C_j)p(C_j)} = \frac{\exp(a_k)}{\sum_j \exp(a_j)}, \quad a_k = \ln[p(\mathbf{x}|C_k)p(C_k)].\)

- This normalized exponential is also known as the softmax function, as it represents a smoothed version of the max function:

\(\text{if } a_k \gg a_j, \forall j \neq k, \text{ then } p(C_k|\mathbf{x}) \approx 1, \quad p(C_j|\mathbf{x}) \approx 0.\)

- We now look at some specific forms of class conditional distributions.

