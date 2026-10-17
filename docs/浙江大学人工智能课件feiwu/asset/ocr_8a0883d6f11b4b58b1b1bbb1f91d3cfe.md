# # The perceptron algorithm

We now apply the stochastic gradient descent algorithm to this error function.
The change in the weight vector w is then given by

w<sup>(τ+1)</sup> = w<sup>(τ)</sup> − η∇E<sub>P</sub>(w) = w<sup>(τ)</sup> + ηφ<sub>n</sub>t<sub>n</sub> (4.55)

where η is the learning rate parameter and τ is an integer that indexes the steps of
the algorithm. Because the perceptron function y(x, w) is unchanged if we multiply
w by a constant, we can set the learning rate parameter η equal to 1 without of
generality. Note that, as the weight vector evolves during training, the set of patterns
that are misclassified will change.

+   - Stochastic gradient descent algorithm:
+   η = 1
+   w<sup>(τ+1)</sup> = w<sup>(τ)</sup> − η∇E<sub>P</sub>(w) = w<sup>(τ)</sup> + ηφ<sub>n</sub>t<sub>n</sub>
+   −w<sup>(τ+1)T</sup>φ<sub>n</sub>t<sub>n</sub> = −w<sup>(τ)T</sup>φ<sub>n</sub>t<sub>n</sub> − (φ<sub>n</sub>t<sub>n</sub>)<sup>T</sup>φ<sub>n</sub>t<sub>n</sub> < −w<sup>(τ)T</sup>φ<sub>n</sub>t<sub>n</sub>

+   - Perceptron convergence theorem:
+   – If there exists an exact solution (in other words, if the training data set is linearly
+   separable), then the perceptron learning algorithm is guaranteed to find an exact
+   solution in a finite number of steps.