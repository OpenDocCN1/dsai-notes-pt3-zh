# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p15 Lecture_15_PAC_Learning_MLE+MAP.zh_en -BV1Z2cUefE4A_p15-

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_1.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_3.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_4.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_6.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_7.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_9.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_10.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_12.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_14.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_16.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_18.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_19.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_21.png)

## 1. 课程概述

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_23.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_24.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_25.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_26.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_27.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_28.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_29.png)

在本节课中，我们将继续学习机器学习中的学习理论，重点关注假设集或假设空间无限的情况。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_31.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_33.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_35.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_36.png)

## 2. 学习理论

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_38.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_39.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_40.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_41.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_42.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_44.png)

### 2.1 有限假设集

在有限假设集的情况下，如果真实的目标生成函数 \( C^* \) 位于假设空间中，我们可以保证所有具有零训练误差的假设具有有界真实误差，概率至少为 \( 1-\delta \)。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_46.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_47.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_48.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_49.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_50.png)

### 2.2 无限假设集

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_52.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_54.png)

在无限假设集的情况下，我们可以使用 VC 维度来衡量假设集的复杂度。VC 维度是指假设集能够打碎的最大集合的大小。

### 2.3 VC 维度计算

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_56.png)

以下是计算 VC 维度的步骤：

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_58.png)

1. 找到一个可以被打碎的集合 \( S \)。
2. 找到一个不能被打碎的集合 \( S' \)，且 \( S' \) 的大小比 \( S \) 大 1。
3. 重复步骤 1 和 2，直到找不到可以被打碎的集合。

### 2.4 VC 维度与学习理论

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_60.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_62.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_63.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_65.png)

我们可以使用 VC 维度来改进学习理论中的结果，使其适用于无限假设集的情况。

## 3. 最大似然估计

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_67.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_69.png)

最大似然估计是一种参数估计方法，它通过最大化数据似然函数来估计参数。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_71.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_73.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_74.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_75.png)

### 3.1 伯努利分布

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_77.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_78.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_80.png)

伯努利分布是一种只有两个可能结果的概率分布。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_82.png)

### 3.2 伯努利分布的似然函数

伯努利分布的似然函数可以表示为：

\[ L(\phi) = \prod_{i=1}^n \phi^{x_i} (1-\phi)^{1-x_i} \]

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_84.png)

### 3.3 最大似然估计

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_86.png)

最大似然估计可以通过求解似然函数的导数等于零来找到最优参数。

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_88.png)

## 4. 最大后验估计

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_90.png)

最大后验估计是一种参数估计方法，它通过最大化后验概率来估计参数。

### 4.1 后验概率

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_92.png)

后验概率可以表示为：

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_94.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_96.png)

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_98.png)

\[ P(\theta | D) = \frac{P(D | \theta) P(\theta)}{P(D)} \]

### 4.2 最大后验估计

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_100.png)

最大后验估计可以通过求解后验概率的导数等于零来找到最优参数。

## 5. 总结

![](img/67da55c34ebbf0a4f5cf2f2803dff61d_102.png)

在本节课中，我们学习了学习理论、VC 维度、最大似然估计和最大后验估计。这些概念对于理解机器学习中的模型选择和参数估计非常重要。