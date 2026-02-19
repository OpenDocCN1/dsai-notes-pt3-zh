# 2：概率建模导论 🎲

![](img/27342d8931e3bed25b5e5902ca19afd6_1.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_3.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_4.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_6.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_8.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_10.png)

在本节课中，我们将深入学习概率建模的基础知识。我们将回顾概率论中的核心概念，定义生成建模任务，并探讨为什么需要先进的机器学习技术来解决高维数据建模的挑战。课程将从简单的概率分布示例开始，逐步深入到复杂的生成模型，并最终介绍如何将神经网络与概率模型结合，形成深度生成模型。

![](img/27342d8931e3bed25b5e5902ca19afd6_11.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_12.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_13.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_15.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_16.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_18.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_20.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_21.png)

---

![](img/27342d8931e3bed25b5e5902ca19afd6_23.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_24.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_26.png)

## 概率分布回顾 📊

![](img/27342d8931e3bed25b5e5902ca19afd6_28.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_29.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_31.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_32.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_34.png)

上一讲我们定义了生成建模的任务。本节中，我们首先回顾一些基本的概率分布，这些分布是构建更复杂模型的基石。

![](img/27342d8931e3bed25b5e5902ca19afd6_35.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_37.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_39.png)

### 伯努利分布

![](img/27342d8931e3bed25b5e5902ca19afd6_40.png)

伯努利分布是最简单的分布之一，它描述了只有两种可能结果的事件，例如抛硬币得到正面或反面。

![](img/27342d8931e3bed25b5e5902ca19afd6_42.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_44.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_46.png)

**公式**：
设随机变量 \( X \) 服从伯努利分布，其概率质量函数为：
\[
P(X = 1) = p, \quad P(X = 0) = 1 - p
\]
其中 \( p \) 是参数，表示事件发生的概率。我们记作 \( X \sim \text{Bernoulli}(p) \)。

![](img/27342d8931e3bed25b5e5902ca19afd6_48.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_49.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_51.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_52.png)

### 分类分布

![](img/27342d8931e3bed25b5e5902ca19afd6_54.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_56.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_58.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_60.png)

分类分布是伯努利分布的推广，它描述了具有 \( M \) 个可能结果的事件，例如掷一个 \( M \) 面的骰子。

![](img/27342d8931e3bed25b5e5902ca19afd6_62.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_64.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_65.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_67.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_69.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_70.png)

**公式**：
设随机变量 \( X \) 可以取 \( M \) 个值，其概率质量函数为：
\[
P(X = k) = p_k, \quad \text{其中} \quad \sum_{k=1}^{M} p_k = 1
\]
该分布有 \( M-1 \) 个独立参数。

![](img/27342d8931e3bed25b5e5902ca19afd6_72.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_73.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_75.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_76.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_78.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_80.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_82.png)

---

![](img/27342d8931e3bed25b5e5902ca19afd6_83.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_85.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_86.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_87.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_89.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_90.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_91.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_92.png)

## 从像素到图像：维数灾难 🚨

![](img/27342d8931e3bed25b5e5902ca19afd6_94.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_95.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_96.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_97.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_99.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_100.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_101.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_102.png)

现在，让我们将概率建模应用于更实际的问题，例如对图像像素进行建模。

![](img/27342d8931e3bed25b5e5902ca19afd6_104.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_105.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_106.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_107.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_108.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_110.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_112.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_113.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_114.png)

### 建模单个像素

![](img/27342d8931e3bed25b5e5902ca19afd6_116.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_117.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_118.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_119.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_120.png)

一个彩色像素由红、绿、蓝三个通道的强度值定义，每个通道通常有256个可能的整数值（0到255）。因此，一个像素的可能状态总数为 \( 256^3 \)。

![](img/27342d8931e3bed25b5e5902ca19afd6_122.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_124.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_126.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_128.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_129.png)

我们可以用一个分类分布来建模单个像素，这需要定义一个三维概率表，其大小为 \( 256 \times 256 \times 256 \)。这需要 \( 256^3 - 1 \) 个参数。

![](img/27342d8931e3bed25b5e5902ca19afd6_131.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_133.png)

### 建模整张图像

![](img/27342d8931e3bed25b5e5902ca19afd6_135.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_136.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_138.png)

现在考虑建模一张28x28的黑白图像（如MNIST手写数字）。每个像素是二进制的（0或1）。整张图像是一个包含 \( n = 28 \times 28 = 784 \) 个二进制变量的向量。

![](img/27342d8931e3bed25b5e5902ca19afd6_140.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_142.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_144.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_146.png)

图像的可能状态总数为 \( 2^n \)。如果我们天真地使用一个覆盖所有可能图像状态的分类分布来建模，将需要 \( 2^n - 1 \) 个参数。对于 \( n=784 \)，这个数字是天文数字，远超宇宙中的原子数量。这被称为**维数灾难**，是生成建模的核心挑战。

![](img/27342d8931e3bed25b5e5902ca19afd6_148.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_150.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_151.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_153.png)

---

![](img/27342d8931e3bed25b5e5902ca19afd6_155.png)

## 应对维数灾难：条件独立性假设 🔗

由于朴素的建模方法不可行，我们需要引入简化假设来构建可处理的模型。一种经典方法是假设变量之间存在条件独立性。

![](img/27342d8931e3bed25b5e5902ca19afd6_157.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_159.png)

### 链式法则与条件独立性

![](img/27342d8931e3bed25b5e5902ca19afd6_160.png)

任何联合概率分布都可以通过概率的链式法则分解：
\[
P(x_1, x_2, \ldots, x_n) = P(x_1) \cdot P(x_2 | x_1) \cdot P(x_3 | x_1, x_2) \cdots P(x_n | x_1, \ldots, x_{n-1})
\]
然而，这种分解本身并没有减少参数数量，每个条件概率项仍然可能是指数级的。

![](img/27342d8931e3bed25b5e5902ca19afd6_162.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_164.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_165.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_167.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_169.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_170.png)

为了减少参数，我们可以做出**条件独立性假设**。例如，假设每个变量 \( x_{i+1} \) 在给定前一个变量 \( x_i \) 的条件下，独立于所有更早的变量：
\[
P(x_{i+1} | x_1, \ldots, x_i) = P(x_{i+1} | x_i)
\]
这样，模型参数数量就从指数级减少到了线性级（\( 2n-1 \) 个参数）。通过调整条件依赖的变量数量，我们可以在模型复杂性和表达能力之间进行权衡。

![](img/27342d8931e3bed25b5e5902ca19afd6_172.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_174.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_176.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_178.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_180.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_182.png)

### 贝叶斯网络

上述思想可以形式化为**贝叶斯网络**。贝叶斯网络是一种用有向无环图表示变量间条件依赖关系的概率图模型。图中的每个节点代表一个随机变量，边表示条件依赖关系。联合概率分布可以分解为每个节点在其父节点条件下的概率的乘积。

**示例**：学生成绩模型。变量包括：课程难度、学生智力、SAT分数、课程成绩、推荐信质量。根据领域知识，我们可以构建一个贝叶斯网络，其中成绩依赖于难度和智力，SAT分数仅依赖于智力，推荐信仅依赖于成绩。这显著减少了所需参数。

![](img/27342d8931e3bed25b5e5902ca19afd6_184.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_186.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_188.png)

---

![](img/27342d8931e3bed25b5e5902ca19afd6_190.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_191.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_193.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_194.png)

## 生成式模型与判别式模型 🤖

![](img/27342d8931e3bed25b5e5902ca19afd6_196.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_198.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_200.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_201.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_203.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_205.png)

在机器学习中，我们有两种主要的方法来建模数据：生成式模型和判别式模型。

![](img/27342d8931e3bed25b5e5902ca19afd6_207.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_208.png)

### 生成式模型（如朴素贝叶斯）

![](img/27342d8931e3bed25b5e5902ca19afd6_210.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_211.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_212.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_213.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_214.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_216.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_218.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_220.png)

生成式模型试图对数据的完整联合概率分布 \( P(X, Y) \) 进行建模。以垃圾邮件分类为例，我们建模 \( P(Y) \)（邮件是垃圾邮件的先验概率）和 \( P(X|Y) \)（在给定标签下单词出现的概率）。朴素贝叶斯假设在给定标签 \( Y \) 的条件下，所有特征 \( X_i \) 相互独立。

![](img/27342d8931e3bed25b5e5902ca19afd6_222.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_223.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_225.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_226.png)

**模型**：
\[
P(Y, X_1, \ldots, X_n) = P(Y) \prod_{i=1}^{n} P(X_i | Y)
\]
学习到模型后，我们可以使用贝叶斯定理进行预测：
\[
P(Y | X) = \frac{P(Y) P(X | Y)}{P(X)}
\]
生成式模型的优势在于可以处理缺失数据、进行数据生成等任务。

![](img/27342d8931e3bed25b5e5902ca19afd6_228.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_229.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_230.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_232.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_234.png)

### 判别式模型（如逻辑回归）

![](img/27342d8931e3bed25b5e5902ca19afd6_236.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_238.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_240.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_242.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_244.png)

判别式模型直接对条件概率 \( P(Y | X) \) 进行建模，而不关心 \( X \) 本身的分布。对于二分类问题，逻辑回归假设：
\[
P(Y=1 | X) = \sigma(\alpha^T X)
\]
其中 \( \sigma(z) = 1/(1+e^{-z}) \) 是sigmoid函数，\( \alpha \) 是参数。

![](img/27342d8931e3bed25b5e5902ca19afd6_246.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_247.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_249.png)

判别式模型通常在现代机器学习中用于预测任务，并且在有大量数据时往往表现更好。深度神经网络（如卷积神经网络）就是强大的判别式模型。

![](img/27342d8931e3bed25b5e5902ca19afd6_251.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_253.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_254.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_255.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_256.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_258.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_259.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_261.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_262.png)

---

![](img/27342d8931e3bed25b5e5902ca19afd6_264.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_266.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_267.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_268.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_270.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_272.png)

## 结合两者：神经概率模型 🧠

![](img/27342d8931e3bed25b5e5902ca19afd6_274.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_275.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_276.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_278.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_279.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_281.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_283.png)

我们可以将判别式模型（尤其是神经网络）的灵活性与生成式模型的框架结合起来，以构建强大的深度生成模型。

![](img/27342d8931e3bed25b5e5902ca19afd6_285.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_286.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_287.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_289.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_290.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_291.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_293.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_295.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_297.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_298.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_299.png)

核心思想是：在链式法则分解中，我们不通过删除依赖项来简化每个条件概率 \( P(x_i | x_1, \ldots, x_{i-1}) \)，而是用一个参数化的函数（如神经网络）来近似这个复杂的条件分布。

![](img/27342d8931e3bed25b5e5902ca19afd6_301.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_303.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_304.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_306.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_308.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_310.png)

**例如**，对于图像像素，我们可以用神经网络来建模：
\[
P(x_i | x_1, \ldots, x_{i-1}) \approx f_\theta(x_1, \ldots, x_{i-1})
\]
这里，\( f_\theta \) 是一个神经网络，输入是前面的所有像素，输出是当前像素 \( x_i \) 取某个值的概率。这样，即使保留所有依赖关系，模型的参数数量也由神经网络的架构决定，而不再是数据维度的指数函数。

![](img/27342d8931e3bed25b5e5902ca19afd6_312.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_313.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_315.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_317.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_319.png)

这种方法可以自然地扩展到连续变量。对于连续变量，我们使用概率密度函数，并用神经网络来参数化条件密度（例如，输出高斯分布的均值和方差）。

![](img/27342d8931e3bed25b5e5902ca19afd6_320.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_321.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_323.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_325.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_327.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_328.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_330.png)

### 深度生成模型示例

![](img/27342d8931e3bed25b5e5902ca19afd6_332.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_333.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_335.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_336.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_337.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_339.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_340.png)

这种“用神经网络建模条件分布”的思路引出了本课程将要学习的第一类**自回归模型**。在下一讲中，我们将深入探讨自回归生成模型。

此外，还有其他类型的深度生成模型，例如：
*   **变分自编码器**：引入潜变量 \( Z \)，并建模 \( P(Z) \) 和 \( P(X|Z) \)，其中 \( P(X|Z) \) 由神经网络参数化。
*   **生成对抗网络**：使用一种间接的、对抗性的训练方式来学习生成分布。

![](img/27342d8931e3bed25b5e5902ca19afd6_342.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_344.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_346.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_347.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_349.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_351.png)

---

![](img/27342d8931e3bed25b5e5902ca19afd6_353.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_355.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_357.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_359.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_361.png)

## 总结 📝

![](img/27342d8931e3bed25b5e5902ca19afd6_363.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_364.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_365.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_367.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_369.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_370.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_372.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_374.png)

本节课我们一起学习了概率建模的基础知识。我们从简单的伯努利分布和分类分布开始，认识到直接建模高维数据（如图像）会面临维数灾难。为了应对这一挑战，我们探讨了通过条件独立性假设构建贝叶斯网络的方法。接着，我们回顾了生成式模型与判别式模型的区别与联系。最后，我们看到了将神经网络的强大函数逼近能力与概率生成模型框架相结合的巨大潜力，这为我们引出了深度生成模型的核心思想。在接下来的课程中，我们将具体学习这些先进的深度生成建模算法。