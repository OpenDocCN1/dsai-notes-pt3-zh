+   1. 求样本均值 $\bar{X} = (\bar{x_1}, \bar{x_2}, ..., \bar{x_p})'$ 和样本协方差矩阵 S;
+   2. 求解特征方程 $|S - \lambda I| = 0$, 其中 I 是单位矩阵
+      解得 p 个特征根 $\lambda_1, \lambda_2, ..., \lambda_p$ ($\lambda_1 \ge \lambda_2 \ge ... \ge \lambda_p$)
+   3. 求 $\lambda_k$ 所对应的单位特征向量 $\alpha_k$ ($k = 1,2,...,p$)
+      解得 $\alpha_k = (a_{1k}, a_{2k}, ..., a_{pk})'$
+   4. 写出主成分的表达式
+      $F_k = a_{1k}(x_1 - \bar{x_1}) + a_{2k}(x_2 - \bar{x_2}) + ... + a_{pk}(x_p - \bar{x_p})$
+      或 $F_k = a_{1k}x_1 + a_{2k}x_2 + ... + a_{pk}x_p$