# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p29 Exam_2_Review.zh_en -BV1Z2cUefE4A_p29-

## 概述

在本节课中，我们将学习CMU《机器学习导论》课程中关于优化、最大似然估计、最大后验估计、朴素贝叶斯和逻辑回归等内容。

![](img/88a2a3f008fe3fc360db5d9a9064e930_1.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_3.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_5.png)

## 优化

![](img/88a2a3f008fe3fc360db5d9a9064e930_7.png)

### 1. 梯度下降法

![](img/88a2a3f008fe3fc360db5d9a9064e930_9.png)

**问题**： 考虑凸函数 $f(z) = z^2$ 和 $\alpha$ 为梯度下降法的学习率。对于哪些 $\alpha$ 值，我们的解序列的极限为 0，假设我们开始的初始值 $z$ 为 1。

![](img/88a2a3f008fe3fc360db5d9a9064e930_11.png)

**解答**：

![](img/88a2a3f008fe3fc360db5d9a9064e930_13.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_15.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_16.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_18.png)

*   梯度下降法的迭代公式为 $z_{t+1} = z_t - \alpha \frac{\partial f(z_t)}{\partial z_t}$。
*   对于 $f(z) = z^2$，其梯度为 $\frac{\partial f(z)}{\partial z} = 2z$。
*   将梯度代入迭代公式，得到 $z_{t+1} = z_t - 2\alpha z_t = (1 - 2\alpha)z_t$。
*   当 $1 - 2\alpha \neq 0$ 时，解序列的极限为 0。

## 最大似然估计和最大后验估计

![](img/88a2a3f008fe3fc360db5d9a9064e930_20.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_22.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_24.png)

### 2. 最大似然估计

![](img/88a2a3f008fe3fc360db5d9a9064e930_26.png)

**问题**： 设 $X_1, X_2, ..., X_n$ 是从正态分布中独立抽取的样本，其概率密度函数为 $f(x; \theta) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$，其中 $\mu$ 和 $\sigma^2$ 是未知参数。求 $\theta$ 的最大似然估计值。

**解答**：

![](img/88a2a3f008fe3fc360db5d9a9064e930_28.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_30.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_32.png)

*   似然函数为 $L(\theta) = \prod_{i=1}^n f(x_i; \theta) = \frac{1}{(2\pi\sigma^2)^{n/2}} e^{-\frac{1}{2\sigma^2} \sum_{i=1}^n (x_i - \mu)^2}$。
*   对似然函数取对数，得到对数似然函数 $\ln L(\theta) = -\frac{n}{2} \ln(2\pi\sigma^2) - \frac{1}{2\sigma^2} \sum_{i=1}^n (x_i - \mu)^2$。
*   对对数似然函数求导，得到 $\frac{\partial \ln L(\theta)}{\partial \theta} = -\frac{n}{\sigma^2} \frac{1}{\sigma^2} (x_i - \mu)^2$。
*   令导数等于 0，解得 $\mu = \frac{1}{n} \sum_{i=1}^n x_i$。
*   对 $\sigma^2$ 求导，得到 $\frac{\partial \ln L(\theta)}{\partial \sigma^2} = \frac{n}{\sigma^4} \sum_{i=1}^n (x_i - \mu)^2 - \frac{1}{\sigma^2}$。
*   令导数等于 0，解得 $\sigma^2 = \frac{1}{n} \sum_{i=1}^n (x_i - \mu)^2$。

### 3. 最大后验估计

![](img/88a2a3f008fe3fc360db5d9a9064e930_34.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_36.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_38.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_40.png)

**问题**： 设 $X_1, X_2, ..., X_n$ 是从正态分布中独立抽取的样本，其概率密度函数为 $f(x; \theta) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$，其中 $\mu$ 和 $\sigma^2$ 是未知参数，且 $\theta$ 的先验分布为正态分布 $p(\theta) = \frac{1}{\sqrt{2\pi\sigma_0^2}} e^{-\frac{(\theta-\mu_0)^2}{2\sigma_0^2}}$。求 $\theta$ 的最大后验估计值。

![](img/88a2a3f008fe3fc360db5d9a9064e930_42.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_44.png)

**解答**：

![](img/88a2a3f008fe3fc360db5d9a9064e930_46.png)

![](img/88a2a3f008fe3fc360db5d9a9064e930_48.png)

*   后验分布为 $p(\theta | X) = \frac{p(X | \theta) p(\theta)}{p(X)}$。
*   由于 $p(X)$ 与 $\theta$ 无关，可以忽略