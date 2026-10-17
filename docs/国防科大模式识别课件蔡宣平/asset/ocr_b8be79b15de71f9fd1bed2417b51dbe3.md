# 5.2 参数估计

# 最大似然估计 (MLE) (Maximum Likelihood Estimate)

# 最大似然估计:

最大似然估计的思想是：如果对总体的独立观测中得样本 X^{(N)} = \{ar{x}_1, ar{x}_2, \cdots, ar{x}_N\}, 则认为 p(X^{(N)}|\hat{	heta}) 在点 X^{(N)} 处最可能取得最大值，不同的\hat{	heta} 使 p(X^{(N)}|\hat{	heta}) 是同一概型而不是同一概密，从而它的最大值点 X^{(N)} 也不同，于是有理由选取满足 p(X^{(N)}|\hat{	heta}) = \max_{\hat{	heta}} [p(X^{(N)}|\hat{	heta})] 的 \hat{	heta} 作为未知参数集的估计值。