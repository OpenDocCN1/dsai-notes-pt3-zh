# 5.2 参数估计

# 最大似然估计(MLE) (Maximum Likelihood Estimate)

在似然函数可微的条件下，
求下面微分方程组的解：

\dfrac{\partial p(X^{(N)} | \tilde{\theta})}{\partial \tilde{\theta}} = 0

或等价地求

\dfrac{\partial [\ln p(X^{(N)} | \tilde{\theta}) ] }{\partial \tilde{\theta}} = \sum_{j=1}^{N} \dfrac{\partial }{\partial \tilde{\theta}} \ln p(\tilde{x}_{j} | \tilde{\theta}) = 0

作为极值的必要条件。

![](bbox=[0.4, 0.2, 0.95, 0.55])

对数似然方程组