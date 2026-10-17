（3）对于一般的 多维正态密度 的情况，计算方法完全是类似的。最后的结果是：

$$\hat{\mu} = \frac{1}{N} \sum_{k=1}^{N} x_k$$

$$\hat{\Sigma} = \frac{1}{N} \sum_{k=1}^{N} (x_k - \hat{\mu})(x_k - \hat{\mu})^T$$

可以证明上式的均值是无偏估计，但协方差矩阵并不是无偏估计，无偏估计是：

$$\hat{\Sigma} = \frac{1}{N-1} \sum_{k=1}^{N} (x_k - \hat{\mu})(x_k - \hat{\mu})^T$$