# 机器学习导论：第15讲：PAC学习、MLE与MAP 🧠

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_1.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_3.png)

在本节课中，我们将继续学习机器学习中的学习理论，重点关注假设集或假设空间无限的情况。我们将介绍VC维度这一核心概念，并探讨两种重要的参数估计方法：最大似然估计和最大后验估计。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_4.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_6.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_7.png)

## 学习理论 📚

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_9.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_10.png)

上一节我们讨论了有限假设集下的学习理论。本节中，我们来看看当假设集无限时，如何分析学习算法的性能。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_12.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_14.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_16.png)

### 有限假设集

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_18.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_19.png)

在有限假设集的情况下，如果真实的目标生成函数 \( C^* \) 位于假设空间中，我们可以保证所有具有零训练误差的假设具有有界真实误差，概率至少为 \( 1-\delta \)。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_21.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_23.png)

### 无限假设集

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_24.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_25.png)

在无限假设集的情况下，我们可以使用 **VC维度** 来衡量假设集的复杂度。VC维度是指假设集能够**打碎**的最大集合的大小。所谓“打碎”，是指对于一组数据点，假设集能够产生所有可能的标记组合。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_26.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_27.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_28.png)

### VC维度计算

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_29.png)

以下是计算VC维度的步骤：

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_31.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_33.png)

1.  找到一个可以被打碎的集合 \( S \)。
2.  找到一个不能被打碎的集合 \( S' \)，且 \( S' \) 的大小比 \( S \) 大 1。
3.  重复步骤1和2，直到找不到可以被打碎的集合。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_35.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_36.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_38.png)

### VC维度与学习理论

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_39.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_40.png)

我们可以使用VC维度来改进学习理论中的结果，使其适用于无限假设集的情况。VC维度提供了一个衡量假设空间复杂度的有效工具，从而可以推导出更一般化的泛化误差界。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_41.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_42.png)

## 最大似然估计 🔍

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_44.png)

上一节我们介绍了学习理论，本节中我们来看看一种基础的参数估计方法——最大似然估计。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_46.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_47.png)

最大似然估计是一种参数估计方法，它通过最大化数据**似然函数**来估计参数。其核心思想是：在给定观测数据的情况下，寻找最有可能产生这些数据的参数值。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_48.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_49.png)

### 伯努利分布

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_50.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_52.png)

伯努利分布是一种只有两个可能结果的概率分布，例如抛硬币的正反面。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_54.png)

### 伯努利分布的似然函数

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_56.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_58.png)

假设我们有n个独立同分布的样本 \( x_1, x_2, ..., x_n \)，每个样本服从参数为 \( \phi \) 的伯努利分布。其似然函数可以表示为：

\[ L(\phi) = \prod_{i=1}^n \phi^{x_i} (1-\phi)^{1-x_i} \]

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_60.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_62.png)

### 最大似然估计

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_63.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_65.png)

最大似然估计可以通过求解似然函数的导数等于零来找到最优参数 \( \hat{\phi}_{MLE} \)。对于伯努利分布，其最大似然估计就是样本中“正面”出现的频率。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_67.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_69.png)

## 最大后验估计 ⚖️

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_71.png)

上一节我们介绍了最大似然估计，它完全依赖于观测数据。本节中，我们引入一种结合了先验知识的参数估计方法——最大后验估计。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_73.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_74.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_75.png)

最大后验估计是一种参数估计方法，它通过最大化**后验概率**来估计参数。它在最大似然估计的基础上，加入了我们对参数的先验信念。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_77.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_78.png)

### 后验概率

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_80.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_82.png)

根据贝叶斯定理，参数 \( \theta \) 在给定数据 \( D \) 下的后验概率可以表示为：

\[ P(\theta | D) = \frac{P(D | \theta) P(\theta)}{P(D)} \]

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_84.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_86.png)

其中：
*   \( P(D | \theta) \) 是似然函数。
*   \( P(\theta) \) 是参数的先验概率。
*   \( P(D) \) 是证据（或边缘似然），对于参数估计而言是常数。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_88.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_90.png)

### 最大后验估计

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_92.png)

最大后验估计的目标是找到使后验概率 \( P(\theta | D) \) 最大的参数 \( \hat{\theta}_{MAP} \)。由于 \( P(D) \) 是常数，这等价于最大化似然函数与先验概率的乘积：

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_94.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_96.png)

\[ \hat{\theta}_{MAP} = \arg\max_{\theta} P(D | \theta) P(\theta) \]

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_98.png)

## 总结 🎯

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_100.png)

在本节课中，我们一起学习了以下几个核心内容：
1.  **学习理论与VC维度**：了解了如何用VC维度分析无限假设空间的复杂度，并推导泛化误差界。
2.  **最大似然估计**：掌握了通过最大化似然函数来估计模型参数的基本方法。
3.  **最大后验估计**：学习了如何结合先验知识，通过最大化后验概率来进行参数估计。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_102.png)

这些概念是理解机器学习模型如何从数据中学习，以及如何进行模型选择和参数估计的基础。