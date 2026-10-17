# The Bias-Variance Trade-off

$$\mathbb{E}[L] = \int \{\mathbb{E}_D[y(x;D)] - h(x)\}^2 p(x)\,dx + \int \mathbb{E}_D\left[\{y(x;D)-\mathbb{E}_D[y(x;D)]\}^2\right]p(x)\,dx + \int \{h(x)-t\}^2p(x,t)\,dx\,dt$$

*(bias)$^2$*

*variance*

*noise*

**Figure 3.6** Plot of squared bias and variance, together with their sum, corresponding to the results shown in Figure 3.5. Also shown is the average test set error for a test data set size of 10000 points. The minimum value of (bias)$^2$ + variance occurs around ln λ = −0.31, which is close to the value that gives the minimum error on the test data.

![](bbox=[0.502, 0.305, 0.967, 0.638])