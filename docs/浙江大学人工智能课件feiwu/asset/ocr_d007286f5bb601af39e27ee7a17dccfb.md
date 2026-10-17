# # Nearest-neighbor methods

+   - KNN density estimation
+     - K-nearest-neighbor
+     - Fix K, determine the value of V from the data
+     - K govern the radius of the sphere

Illustration of _K_-nearest-neighbour density estimation using the same data set as in Figures 2.25 and 2.24. We see that the parameter _K_ governs the degree of smoothing, so that a small value of _K_ leads to a very noisy density model (top panel), whereas a large value (bottom panel) smoothes out the bimodal nature of the true distribution (shown by the green curve) from which the data set was generated.

![](bbox=[0.682, 0.514, 0.977, 0.922])

```
p(x) = K / NV
```