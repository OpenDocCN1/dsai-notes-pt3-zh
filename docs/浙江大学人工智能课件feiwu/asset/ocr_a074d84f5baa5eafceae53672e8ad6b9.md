# # Polynomial Coefficients

Table of the coefficients w* for M = 9 polynomials with various values for the regularization parameter λ. Note that ln λ = −∞ corresponds to a model with no regularization, i.e., to the graph at the bottom right in Figure 1.4. We see that, as the value of λ increases, the typical magnitude of the coefficients gets smaller.

|    | ln λ = −∞ | ln λ = −18 | ln λ = 0 |
|---|---|---|---|
| w₀* | 0.35 | 0.35 | 0.13 |
| w₁* | 232.37 | 4.74 | -0.05 |
| w₂* | -5321.83 | -0.77 | -0.06 |
| w₃* | 48568.31 | -31.97 | -0.05 |
| w₄* | -231639.30 | -3.89 | -0.03 |
| w₅* | 640042.26 | 55.28 | -0.02 |
| w₆* | -1061800.52 | 41.32 | -0.01 |
| w₇* | 1042400.18 | -45.95 | -0.00 |
| w₈* | -557682.99 | -91.53 | 0.00 |
| w₉* | 125201.43 | 72.68 | 0.01 |

The impact of the regularization term on the generalization error can be seen by plotting the value of the RMS error (1.3) for both training and test sets against ln λ, as shown in Figure 1.8. We see that in effect λ now controls the effective complexity of the model and hence determines the degree of over-fitting.