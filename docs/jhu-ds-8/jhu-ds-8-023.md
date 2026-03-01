# 023：基于模型的预测

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_1.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_2.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_3.png)

在本节课中，我们将要学习基于模型的预测方法。这种方法的核心思想是假设数据遵循特定的概率模型，然后利用贝叶斯定理，基于该概率模型来构建最优的分类器。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_5.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_6.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_7.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_8.png)

## 概述 📋

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_10.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_11.png)

基于模型的预测方法为数据假设了一个结构化的概率框架。这种方法能够利用数据中可能存在的特定结构（例如，某种分布），这不仅能带来计算上的便利，在实际问题中也可能获得相当高的准确率，特别是当实际问题符合我们所假设的底层数据分布时。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_13.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_15.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_16.png)

然而，这种方法也存在缺点。它需要对数据做出额外的假设。虽然这些假设不必被严格满足，预测算法也能工作得很好，但如果假设与实际情况偏差过大，算法可能会失效。当模型不正确时，预测的准确性确实会降低。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_17.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_19.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_20.png)

## 基于模型的方法框架 🏗️

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_22.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_24.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_25.png)

上一节我们概述了基于模型预测的基本思想，本节中我们来看看其具体的数学框架。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_27.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_28.png)

我们的目标是，为条件分布 `Pr(Y = k | X = x)` 建立一个参数化模型或基于概率分布的模型。其中，`Y` 是我们的结果（属于某个特定的类 `k`），`X` 是我们观测到的一组预测变量。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_30.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_31.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_32.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_33.png)

一个典型的方法是应用贝叶斯定理。我们想知道在观察到变量 `X` 的条件下，结果 `Y` 属于类别 `k` 的概率。根据贝叶斯定理，这可以写为：

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_35.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_36.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_37.png)

```
Pr(Y = k | X = x) = [ f_k(x) * π_k ] / [ Σ (f_l(x) * π_l) ]， 对所有类别 l 求和
```

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_39.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_40.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_41.png)

在这个公式中：
*   `f_k(x)` 是给定类别 `Y = k` 时，特征 `X` 的分布模型。
*   `π_k` 是类别 `k` 的先验概率，通常可以直接从数据中估计。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_43.png)

一种常见的选择是假设 `f_k(x)` 服从（多元）高斯分布。然后，我们可以从数据中估计出该分布的参数（例如均值 `μ_k` 和协方差矩阵 `Σ_k`）。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_45.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_46.png)

一旦估计出这些参数，当我们观察到新的预测变量时，就可以计算其属于任一类别的概率。我们将其分类到具有最高后验概率的类别。

## 常见的模型类型 📊

以下是几种基于此框架的流行模型：

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_48.png)

*   **线性判别分析 (LDA)**：假设每个类别内的特征服从多元高斯分布，且所有类别共享**同一个**协方差矩阵。这最终会在特征空间中产生线性的决策边界。
*   **二次判别分析 (QDA)**：与LDA类似，但允许每个类别有自己的协方差矩阵。这会产生二次的决策边界。
*   **朴素贝叶斯分类器**：在建模过程中假设所有预测变量（特征）之间是**相互独立**的。尽管这个“朴素”的假设在现实中往往不成立，但它简化了计算，并且在许多实际问题（如文本分类）中仍然非常有效。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_50.png)

## 深入理解：为什么是“线性”判别？ ➗

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_51.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_52.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_53.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_54.png)

上一节我们介绍了LDA和QDA，本节中我们来看看LDA的决策边界为何是线性的。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_56.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_57.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_58.png)

如果我们考虑两个类别 `k` 和 `j` 的后验概率之比，并对其取对数，我们会发现这个对数几率是预测变量 `x` 的一个**线性函数**。这意味着决策边界（即两个类别后验概率相等的点所构成的线）是一条直线。数据点落在直线的哪一侧，就决定了它被分到哪个类别。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_60.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_61.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_62.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_63.png)

在二维特征空间中，LDA的决策边界看起来像是一些直线，将空间划分成不同的区域，每个区域对应一个类别。

## 判别函数与预测 🔍

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_65.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_66.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_67.png)

在实践层面，我们通常使用一个**判别函数**来进行分类。对于LDA，判别函数的形式如下：

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_68.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_69.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_70.png)

```
δ_k(x) = x^T Σ^{-1} μ_k - (1/2) μ_k^T Σ^{-1} μ_k + log(π_k)
```

在这个公式中：
*   `μ_k` 是类别 `k` 中所有特征的均值向量。
*   `Σ` 是共享的协方差矩阵（所有类别相同）。
*   `π_k` 是类别 `k` 的先验概率。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_72.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_73.png)

对于一个新的数据点 `x`，我们将其代入每个类别 `k` 的判别函数 `δ_k(x)`，然后选择使 `δ_k(x)` 值最大的那个类别作为预测结果。这些参数通常可以通过最大似然估计法从训练数据中获得。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_74.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_75.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_76.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_77.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_78.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_79.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_80.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_81.png)

## 朴素贝叶斯分类器的简化 🎯

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_83.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_84.png)

朴素贝叶斯分类器通过一个关键的简化假设使得计算变得非常容易。回顾贝叶斯公式，后验概率与先验概率和特征的条件概率的乘积成正比：

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_86.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_87.png)

```
Pr(Y = k | X) ∝ π_k * Pr(X | Y = k)
```

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_88.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_89.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_90.png)

特征 `X` 的联合条件概率 `Pr(X | Y = k)` 可以分解为每个特征条件概率的乘积。如果不做简化，每个特征的概率都可能依赖于其他特征，计算会非常复杂。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_92.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_93.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_94.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_95.png)

朴素贝叶斯做出了“朴素”的假设：**所有预测变量在给定类别的条件下是相互独立的**。于是，复杂的联合概率就简化为了单个特征概率的乘积：

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_97.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_98.png)

```
Pr(X | Y = k) ≈ Pr(X1 | Y = k) * Pr(X2 | Y = k) * ... * Pr(Xp | Y = k)
```

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_100.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_101.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_102.png)

尽管这个独立性假设通常不成立，但朴素贝叶斯分类器在许多应用（尤其是特征维度很高或特征是分类/二元变量时，如文本分类）中表现依然出色。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_104.png)

## 实战示例：鸢尾花数据集 🌸

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_105.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_106.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_107.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_108.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_109.png)

让我们在鸢尾花数据集上实际应用LDA和朴素贝叶斯分类器。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_111.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_112.png)

首先，我们加载必要的库并准备数据，将数据划分为训练集和测试集。

```r
library(ggplot2)
library(caret)
data(iris)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_114.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_115.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_116.png)

# 创建训练集和测试集
set.seed(123)
inTrain <- createDataPartition(y=iris$Species, p=0.7, list=FALSE)
training <- iris[inTrain,]
testing <- iris[-inTrain,]
```

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_117.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_118.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_119.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_120.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_121.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_122.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_123.png)

接着，我们使用 `caret` 包的 `train` 函数来训练模型。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_125.png)

```r
# 训练LDA模型
modLda <- train(Species ~ ., data=training, method="lda")
# 训练朴素贝叶斯模型
modNb <- train(Species ~ ., data=training, method="nb")
```

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_126.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_127.png)

然后，我们在测试集上进行预测并比较结果。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_129.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_130.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_131.png)

```r
# 预测
predLda <- predict(modLda, testing)
predNb <- predict(modNb, testing)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_132.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_133.png)

# 比较两个模型的预测结果
table(predLda, predNb)
```

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_135.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_136.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_137.png)

在这个例子中，尽管我们知道鸢尾花的特征（如花瓣长度和宽度）是相关的，但朴素贝叶斯分类器的预测结果与LDA的预测结果几乎完全相同，只有一个数据点的分类存在分歧。这表明即使独立性假设不严格成立，朴素贝叶斯仍然可以是一个有效的分类工具。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_139.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_140.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_141.png)

## 总结与延伸阅读 📚

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_143.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_144.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_145.png)

本节课中我们一起学习了基于模型的预测方法。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_147.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_148.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_149.png)

我们首先了解了其核心思想：为数据假设一个概率模型（通常是高斯分布），并利用贝叶斯定理进行分类。我们探讨了这种方法的优势（能利用数据结构、计算高效）和劣势（依赖模型假设）。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_150.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_152.png)

接着，我们详细学习了三种具体算法：
1.  **线性判别分析 (LDA)**：假设各类别协方差矩阵相同，产生线性边界。
2.  **二次判别分析 (QDA)**：允许各类别有不同协方差矩阵，产生二次边界。
3.  **朴素贝叶斯分类器**：假设特征条件独立，大大简化计算，特别适用于高维或文本数据。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_153.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_154.png)

最后，我们通过鸢尾花数据集的实例，演示了如何使用 `caret` 包快速实现和比较这些模型。

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_156.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_157.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_158.png)

![](img/e71a0e51ccbbfdf9785ca9f5c2dc8558_159.png)

若想深入了解，可以参考以下资源：
*   《统计学习导论》或《统计学习基础》中关于朴素贝叶斯和模型分类的章节。
*   关于模型聚类的学术论文。
*   维基百科上关于**线性判别分析**和**二次判别分析**的页面，它们是非常好的参考资料。