
## The reject option

We have seen that classification errors arise from the regions of input space where the largest of the posterior probabilities \(p(C_k|x)\) is significantly less than unity, or equivalently where the joint distributions \(p(x, C_k)\) have comparable values. These are the regions where we are relatively uncertain about class membership. In some applications, it will be appropriate to avoid making decisions on the difficult cases in anticipation of a lower error rate on those examples for which a classification decision is made. This is known as the **reject option**. For example, in our hypothetical medical illustration, it may be appropriate to use an automatic system to classify those X-ray images for which there is little doubt as to the correct class, while leaving a human expert to classify the more ambiguous cases. We can achieve this by introducing a threshold \(\theta\) such that we reject inputs for which the largest of the posterior probabilities \(p(C_k|x)\) is less than or equal to \(\theta\). This is illustrated for the case of two classes, and a single continuous input variable \(x\), in Figure 1.26. Note that setting \(\theta = 1\) will ensure that all examples are rejected, whereas if there are \(K\) classes then setting \(\theta < 1/K\) will ensure that no examples are rejected. The fraction of examples that get rejected is controlled by the value of \(\theta\).

We can easily extend the reject criterion to minimize the expected loss, when a loss matrix is given, taking account of the loss incurred when a reject decision is made.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_997_0.png)

## Inference and decision

We have broken the classification problem down into two separate stages, the *inference stage* in which we use training data to learn a model for \(p(C_k \mid x)\), and the subsequent *decision stage* in which we use these posterior probabilities to make optimal class assignments. An alternative possibility would be to solve both problems together and simply learn a function that maps inputs \(x\) directly into decisions. Such a function is called a *discriminant function*.

## three distinct approaches to solving decision problems

- (a) First solve the inference problem of determining the class-conditional densities \(p(x|C_k)\) for each class \(C_k\) individually. Also separately infer the prior class probabilities \(p(C_k)\). Then use Bayes’ theorem in the form

  \(p(C_k|x) = \frac{p(x|C_k)p(C_k)}{p(x)}\) (1.82)

  to find the posterior class probabilities \(p(C_k|x)\). As usual, the denominator in Bayes’ theorem can be found in terms of the quantities appearing in the numerator, because

  \(p(x) = \sum_k p(x|C_k)p(C_k)\) (1.83)

  Equivalently, we can model the joint distribution \(p(x, C_k)\) directly and then normalize to obtain the posterior probabilities. Having found the posterior probabilities, we use decision theory to determine class membership for each new input \(x\). Approaches that explicitly or implicitly model the distribution of inputs as well as outputs are known as **generative models**, because by sampling from them it is possible to generate synthetic data points in the input space.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1001_0.png)

Input x is 1000*1000 pixels

1000 semantic gap

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_1001_1.png)

Let us consider the relative merits of these three alternatives. Approach (a) is the most demanding because it involves finding the joint distribution over both \(x\) and \(C_k\). For many applications, \(x\) will have high dimensionality, and consequently we may need a large training set in order to be able to determine the class-conditional densities to reasonable accuracy. Note that the class priors \(p(C_k)\) can often be estimated simply from the fractions of the training set data points in each of the classes. One advantage of approach (a), however, is that it also allows the marginal density of data \(p(x)\) to be determined from (1.83). This can be useful for detecting new data points that have low probability under the model and for which the predictions may be of low accuracy, which is known as outlier detection or novelty detection (Bishop, 1994; Tarassenko, 1995).

However, if we only wish to make classification decisions, then it can be wasteful of computational resources, and excessively demanding of data, to find the joint distribution \(p(x, C_k)\) when in fact we only really need the posterior probabilities \(p(C_k|x)\), which can be obtained directly through approach (b). Indeed, the class-conditional densities may contain a lot of structure that has little effect on the posterior probabilities, as illustrated in Figure 1.27. There has been much interest in exploring the relative merits of generative and discriminative approaches to machine learning, and in finding ways to combine them (Jebara, 2004; Lasserre et al., 2006).

An even simpler approach is (c) in which we use the training data to find a discriminant function \(f(x)\) that maps each \(x\) directly onto a class label, thereby combining the inference and decision stages into a single learning problem. In the example of Figure 1.27, this would correspond to finding the value of \(x\) shown by the vertical green line, because this is the decision boundary giving the minimum probability of misclassification.
