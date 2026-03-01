# 高级统计：14：编程示例 🧮

![](img/71446122301a99671edf94032ddd2f7d_0.png)

![](img/71446122301a99671edf94032ddd2f7d_2.png)

在本节课中，我们将通过一个编程示例，手动复现线性回归模型（`lm`函数）的核心计算过程。我们将从加载数据、拟合模型开始，逐步计算回归系数、标准误、t统计量、p值以及F统计量，并验证这些结果与R内置`lm`函数输出的一致性。

![](img/71446122301a99671edf94032ddd2f7d_4.png)

![](img/71446122301a99671edf94032ddd2f7d_6.png)

![](img/71446122301a99671edf94032ddd2f7d_7.png)

上一节我们介绍了线性回归的分布理论结果，本节中我们来看看如何通过编程手动实现这些计算。

![](img/71446122301a99671edf94032ddd2f7d_9.png)

## 数据加载与模型拟合

![](img/71446122301a99671edf94032ddd2f7d_11.png)

首先，我们加载数据集并拟合一个线性回归模型。我们将以`Fertility`（生育率）作为因变量，数据集中其他所有变量作为自变量。

![](img/71446122301a99671edf94032ddd2f7d_12.png)

```r
# 加载数据
data(swiss)

![](img/71446122301a99671edf94032ddd2f7d_14.png)

# 使用lm函数拟合模型
fit <- lm(Fertility ~ ., data = swiss)

![](img/71446122301a99671edf94032ddd2f7d_16.png)

# 查看模型摘要
summary(fit)
```

![](img/71446122301a99671edf94032ddd2f7d_18.png)

![](img/71446122301a99671edf94032ddd2f7d_20.png)

查看`summary(fit)`的输出，我们可以看到几个关键列：估计值（`Estimate`）、标准误（`Std. Error`）、t值（`t value`）和p值（`Pr(>|t|)`）。p值表示获得一个绝对值大于当前t统计量的t值的概率。

![](img/71446122301a99671edf94032ddd2f7d_22.png)

## 手动计算回归系数与残差

现在，我们手动重现上述所有计算。第一步是创建设计矩阵`X`和响应向量`y`。

![](img/71446122301a99671edf94032ddd2f7d_24.png)

```r
# 创建设计矩阵X：第一列为1（截距项），其余列为自变量
X <- as.matrix(cbind(1, swiss[, -1]))
# 创建响应向量y：生育率变量
y <- swiss$Fertility
```

![](img/71446122301a99671edf94032ddd2f7d_26.png)

![](img/71446122301a99671edf94032ddd2f7d_27.png)

接下来，我们通过求解正规方程来计算回归系数β。

![](img/71446122301a99671edf94032ddd2f7d_29.png)

```r
# 通过公式 β = (X'X)^(-1) X'y 求解回归系数
beta <- solve(t(X) %*% X) %*% t(X) %*% y
```

![](img/71446122301a99671edf94032ddd2f7d_31.png)

然后，我们计算拟合值和残差。

```r
# 计算拟合值
y_hat <- X %*% beta
# 计算残差
residuals <- y - y_hat
```

定义样本量`n`和预测变量数量`p`。

![](img/71446122301a99671edf94032ddd2f7d_33.png)

![](img/71446122301a99671edf94032ddd2f7d_34.png)

```r
n <- nrow(X)
p <- ncol(X)
```

## 计算残差标准差与标准误

![](img/71446122301a99671edf94032ddd2f7d_36.png)

我们可以估计残差平方和（RSS）以及残差标准差`s`。

![](img/71446122301a99671edf94032ddd2f7d_38.png)

![](img/71446122301a99671edf94032ddd2f7d_39.png)

```r
# 计算残差平方和
RSS <- sum(residuals^2)
# 计算残差标准差估计值 s = sqrt(RSS / (n-p))
s <- sqrt(RSS / (n - p))
```

![](img/71446122301a99671edf94032ddd2f7d_41.png)

将我们手动计算的`s`与`lm`模型的输出进行比较，两者应完全相同。

```r
# 比较手动计算的s与lm输出的残差标准差
s
summary(fit)$sigma
```

![](img/71446122301a99671edf94032ddd2f7d_43.png)

![](img/71446122301a99671edf94032ddd2f7d_45.png)

回归系数β的方差-协方差矩阵计算公式为 **Var(β̂) = (X'X)^(-1) σ²**。其估计值为 **Var(β̂) = (X'X)^(-1) s²**。

![](img/71446122301a99671edf94032ddd2f7d_47.png)

```r
# 计算回归系数的方差-协方差矩阵
beta_var <- solve(t(X) %*% X) * s^2
# 计算标准误：方差-协方差矩阵对角线的平方根
se_manual <- sqrt(diag(beta_var))
```

![](img/71446122301a99671edf94032ddd2f7d_49.png)

以下是验证手动计算的标准误与`lm`输出是否一致的方法。

![](img/71446122301a99671edf94032ddd2f7d_51.png)

```r
# 提取lm模型摘要中的标准误
se_lm <- summary(fit)$coefficients[, 2]
# 比较两者
se_manual
se_lm
```

## 计算t统计量与p值

t统计量是估计的回归系数除以其标准误。

![](img/71446122301a99671edf94032ddd2f7d_53.png)

```r
# 计算t统计量
t_stats_manual <- beta / se_manual
```

验证手动计算的t统计量与`lm`输出的第三列是否一致。

![](img/71446122301a99671edf94032ddd2f7d_55.png)

![](img/71446122301a99671edf94032ddd2f7d_56.png)

```r
# 提取lm模型摘要中的t值
t_stats_lm <- summary(fit)$coefficients[, 3]
# 比较两者
t_stats_manual
t_stats_lm
```

![](img/71446122301a99671edf94032ddd2f7d_58.png)

p值的计算基于t分布。对于双侧检验，p值计算公式为：**p = 2 * P(T > |t|)**，其中T服从自由度为`n-p`的t分布。

![](img/71446122301a99671edf94032ddd2f7d_60.png)

```r
# 手动计算p值
p_values_manual <- 2 * pt(-abs(t_stats_manual), df = n - p)
# 提取lm模型摘要中的p值
p_values_lm <- summary(fit)$coefficients[, 4]
# 比较两者
p_values_manual
p_values_lm
```

![](img/71446122301a99671edf94032ddd2f7d_62.png)

## 计算整体模型的F统计量

![](img/71446122301a99671edf94032ddd2f7d_63.png)

最后，我们手动计算用于检验所有斜率系数（除截距外）是否同时为零的F统计量。这需要构造一个对比矩阵`K`。

![](img/71446122301a99671edf94032ddd2f7d_65.png)

![](img/71446122301a99671edf94032ddd2f7d_66.png)

```r
# 创建对比矩阵K，用于选取除截距外的所有系数
K <- cbind(0, diag(p - 1))
# 计算F统计量涉及的中间量
K_var <- K %*% solve(t(X) %*% X) %*% t(K)
# 根据公式手动计算F统计量
f_stat_manual <- (t(K %*% beta) %*% solve(K_var) %*% (K %*% beta)) / ((p - 1) * s^2)
```

验证手动计算的F统计量及其p值与`lm`模型摘要末尾的输出是否一致。

```r
# 查看手动计算的F统计量
f_stat_manual
# 查看lm模型摘要中的F统计量（位于摘要末尾）
summary(fit)$fstatistic

# 计算F统计量对应的p值
p_f_manual <- pf(f_stat_manual, df1 = p - 1, df2 = n - p, lower.tail = FALSE)
p_f_manual
```

![](img/71446122301a99671edf94032ddd2f7d_68.png)

本节课中我们一起学习了如何从最基础的矩阵运算出发，手动推导并计算线性回归模型的全部核心统计量。我们验证了每一步的结果都与R语言`lm`函数的输出完全一致。这揭示了`lm`函数并非“黑箱”，其所有输出都源于我们之前讨论过的基本分布理论结果——包括二次型导出的卡方分布、残差与系数估计的独立性，以及由此衍生的t分布和F分布。掌握这些计算过程后，对于任何感兴趣的系数对比（例如检验β₁是否等于β₂），你都可以直接进行推导和计算。