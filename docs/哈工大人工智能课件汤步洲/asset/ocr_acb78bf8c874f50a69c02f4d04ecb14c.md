# Bayes’ Net Representation

+   - A directed, acyclic graph, one node per random variable
+   - A conditional probability table (CPT) for each node
+     - A collection of distributions over X, one for each combination of parents’ values
+     $P(X|a_1 \dots a_n)$
+   - Bayes’ nets implicitly encode joint distributions
+     - As a product of local conditional distributions
+     - To see what probability a BN gives to a full assignment, multiply all the relevant conditionals together:
+     $P(x_1, x_2, \dots x_n) = \prod_{i=1}^{n} P(x_i|parents(X_i))$

![](bbox=[0.68, 0.22, 0.99, 0.57])

![](bbox=[0.78, 0.6, 0.99, 0.98])