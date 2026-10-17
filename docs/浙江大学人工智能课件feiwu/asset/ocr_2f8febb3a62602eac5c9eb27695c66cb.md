# # Least squares for classification

+   - Problem:
+     - Each class \(\mathcal{C}_k\) is described by its own linear model :
+       
+       \( y_k(\mathbf{x}) = \mathbf{w}_k^\mathrm{T}\mathbf{x} + w_{k0} \quad \text{where } k = 1, \dots, K \)
+   
+     - group together:
+       
+       \( \mathbf{y}(\mathbf{x}) = \widetilde{\mathbf{W}}^\mathrm{T}\widetilde{\mathbf{x}} \quad \widetilde{\mathbf{w}}_k = (w_{k0}, \mathbf{w}_k^\mathrm{T})^\mathrm{T} \quad \widetilde{\mathbf{x}} = (1, \mathbf{x}^\mathrm{T})^\mathrm{T} \)
+   
+     - new input \(\mathbf{x}\) is then assigned to the class for which the output \( y_k = \widetilde{\mathbf{w}}_k^\mathrm{T}\widetilde{\mathbf{x}} \) is largest.

+   - Learning \(\widetilde{\mathbf{W}}\) with training data set: \(\{ \mathbf{x}_n, \mathbf{t}_n \}\) where \( n = 1, \dots, N \)
+   - minimizing a sum-of-squares error function:
+     
+     \( E_D(\widetilde{\mathbf{W}}) = \frac{1}{2} \mathrm{Tr} \left\{ (\widetilde{\mathbf{X}}\widetilde{\mathbf{W}} - \mathbf{T})^\mathrm{T}(\widetilde{\mathbf{X}}\widetilde{\mathbf{W}} - \mathbf{T}) \right\} \implies \widetilde{\mathbf{W}} = (\widetilde{\mathbf{X}}^\mathrm{T}\widetilde{\mathbf{X}})^{-1}\widetilde{\mathbf{X}}^\mathrm{T}\mathbf{T} = \widetilde{\mathbf{X}}^\dagger\mathbf{T} \)

+   - Discriminant function: \( \mathbf{y}(\mathbf{x}) = \widetilde{\mathbf{W}}^\mathrm{T}\widetilde{\mathbf{x}} = \mathbf{T}^\mathrm{T} \left( \widetilde{\mathbf{X}}^\dagger \right)^\mathrm{T} \widetilde{\mathbf{x}} \)

![](bbox=[0.218, 0.627, 0.779, 0.873])

**Figure 4.8** The left plot shows data from two classes, denoted by red crosses and blue circles, together with
the decision boundary found by least squares (magenta curve) and also by the logistic regression model (green
curve), which is discussed later in Section 4.3.2. The right-hand plot shows the corresponding results obtained
when outlier data points are added to the bottom left of the diagram, showing that least squares is highly sensitive
to outliers, unlike logistic regression.