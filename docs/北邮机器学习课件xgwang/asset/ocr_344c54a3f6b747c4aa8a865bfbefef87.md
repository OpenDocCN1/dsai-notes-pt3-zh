# Find the Optimal Projection Direction $e_1$

+   - Use the method of Lagrange multipliers to maximize the $e_1^tSe_1$ subject to the constraint that $\|e_1\|=1$,\n\n  $u=e_1^tSe_1-\lambda(e_1^te_1-1)$,\n\n  $\frac{\partial u}{\partial e_1}=2Se_1-2\lambda e_1=0$.

+   - Setting the gradient vector equal to zero, we see that $e_1$ must be an eigenvector of the scatter matrix\n\n  $Se_1=\lambda e_1$

+   - Since $e_1^tSe_1=\lambda e_1^te_1=\lambda$, to maximize $e_1^tSe_1$, we select the eigenvector with the largest eigenvalue