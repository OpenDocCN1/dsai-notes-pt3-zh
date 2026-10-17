# # Minimizing the misclassification rate

For the more general case of _K_ classes, it is slightly easier to maximize the probability of being correct, which is given by

```
\(p(\text{correct})=\sum_{k=1}^Kp\left(\mathbf{x}\in\mathcal{R}_k,C_k\right)\)
\(=\sum_{k=1}^K\int_{\mathcal{R}_k}p\left(\mathbf{x},C_k\right)\mathrm{d}\mathbf{x}\) (1.79)
```

which is maximized when the regions R_<sub>k</sub>_ are chosen such that each **x** is assigned to the class for which _p_(**x**_,C<sub>k</sub>_) is largest. Again, using the product rule _p_(**x**_,C<sub>k</sub>_)=_p_(_C<sub>k</sub>_|**x**)_p_(**x**), and noting that the factor of _p_(**x**) is common to all terms, we see that each **x** should be assigned to the class having the largest posterior probability _p_(_C<sub>k</sub>_|**x**).