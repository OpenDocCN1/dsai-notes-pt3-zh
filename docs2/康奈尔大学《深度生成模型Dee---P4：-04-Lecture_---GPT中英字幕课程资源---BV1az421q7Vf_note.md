# 深度生成模型：04：最大似然学习 📈

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_1.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_3.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_5.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_7.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_8.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_9.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_11.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_13.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_15.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_17.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_19.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_20.png)

在本节课中，我们将要学习如何训练一个生成模型。具体来说，我们将探讨一个核心的学习目标——**最大似然**，了解它的来源，并学习如何基于训练集来优化它。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_22.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_23.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_24.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_25.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_27.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_28.png)

---

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_30.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_31.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_32.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_33.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_35.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_36.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_38.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_40.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_42.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_43.png)

## 概述：生成模型算法的结构

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_45.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_46.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_47.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_48.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_49.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_50.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_51.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_52.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_53.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_54.png)

在之前的课程中，我们介绍了生成模型算法的结构。与大多数机器学习算法类似，一个生成模型算法包含三个核心组件：

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_56.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_57.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_58.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_59.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_60.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_61.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_62.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_63.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_64.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_66.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_68.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_69.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_70.png)

1.  **模型族**：这是我们准备用来拟合数据的概率分布的形式或类型。更精确地说，它是算法可能输出的所有可能分布的集合。
2.  **学习目标**：这是一种量化模型对数据拟合好坏的方法。
3.  **优化过程**：根据我们的学习目标，选择最佳模型的方法。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_72.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_74.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_75.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_77.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_78.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_80.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_82.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_84.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_85.png)

在前几讲中，我们重点讨论了第一部分——模型族，即如何表示概率模型。本节课，我们将聚焦于**学习目标**和**优化器**，探讨一旦我们指定了一个带有参数的模型，如何学习这些参数。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_87.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_89.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_90.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_91.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_93.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_94.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_96.png)

---

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_98.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_99.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_100.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_102.png)

## 最大似然学习目标

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_104.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_106.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_108.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_109.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_111.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_113.png)

### 从KL散度推导

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_115.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_116.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_118.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_120.png)

我们的目标是找到一个模型分布 \( p_{\theta}(x) \)，使其尽可能接近真实的数据分布 \( p_{\text{data}}(x) \)。为此，我们需要一个衡量两个分布之间“距离”的指标。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_122.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_123.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_124.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_125.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_126.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_128.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_130.png)

一个常用且自然的指标是 **KL散度**。对于两个分布 \( P \) 和 \( Q \)，其KL散度定义为：

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_131.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_133.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_134.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_135.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_137.png)

\[
D_{KL}(P \parallel Q) = \mathbb{E}_{x \sim P} \left[ \log \frac{P(x)}{Q(x)} \right]
\]

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_139.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_140.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_141.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_142.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_143.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_145.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_147.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_149.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_150.png)

KL散度具有两个关键性质：它总是非负的，并且当且仅当 \( P \) 和 \( Q \) 完全相同时等于零。因此，最小化 \( D_{KL}(p_{\text{data}} \parallel p_{\theta}) \) 是一个理想的学习目标。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_152.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_154.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_155.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_157.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_159.png)

让我们展开这个公式：

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_161.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_163.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_165.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_166.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_167.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_169.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_170.png)

\[
D_{KL}(p_{\text{data}} \parallel p_{\theta}) = \mathbb{E}_{x \sim p_{\text{data}}} [\log p_{\text{data}}(x)] - \mathbb{E}_{x \sim p_{\text{data}}} [\log p_{\theta}(x)]
\]

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_172.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_173.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_175.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_177.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_179.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_181.png)

在上式中，第一项 \( \mathbb{E}_{x \sim p_{\text{data}}} [\log p_{\text{data}}(x)] \) 是一个常数，与模型参数 \( \theta \) 无关。因此，**最小化 KL 散度等价于最大化第二项**：

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_183.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_184.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_185.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_186.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_187.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_188.png)

\[
\max_{\theta} \mathbb{E}_{x \sim p_{\text{data}}} [\log p_{\theta}(x)]
\]

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_190.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_191.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_193.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_194.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_196.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_197.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_198.png)

这个第二项被称为 **期望对数似然**。直观地理解，它要求模型 \( p_{\theta} \) 给那些来自真实数据分布 \( p_{\text{data}} \) 的样本 \( x \) 赋予高的概率。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_199.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_201.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_202.png)

---

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_204.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_206.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_208.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_210.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_212.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_214.png)

### 使用蒙特卡洛估计

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_216.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_218.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_220.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_222.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_223.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_225.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_226.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_228.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_230.png)

然而，我们无法直接计算期望值 \( \mathbb{E}_{x \sim p_{\text{data}}} [\log p_{\theta}(x)] \)，因为我们并不知道 \( p_{\text{data}} \) 的具体形式。我们拥有的只是一个由 \( N \) 个独立同分布样本组成的训练集 \( \mathcal{D} = \{x^{(1)}, x^{(2)}, ..., x^{(N)}\} \)。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_232.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_233.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_235.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_237.png)

这时，我们可以使用 **蒙特卡洛估计**。蒙特卡洛估计的核心思想是：用样本的平均值来近似期望值。对于一个函数 \( g(x) \)，其期望的蒙特卡洛估计为：

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_239.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_241.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_242.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_244.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_245.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_247.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_249.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_250.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_252.png)

\[
\mathbb{E}_{x \sim p}[g(x)] \approx \frac{1}{T} \sum_{t=1}^{T} g(x^{(t)}), \quad x^{(t)} \sim p
\]

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_254.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_255.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_257.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_259.png)

这个估计是无偏的（即期望值等于真实期望），并且随着样本数 \( T \) 的增加，其方差会减小，估计会越来越准确。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_261.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_262.png)

将蒙特卡洛估计应用到我们的期望对数似然上，我们得到：

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_264.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_266.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_267.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_268.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_270.png)

\[
\mathbb{E}_{x \sim p_{\text{data}}} [\log p_{\theta}(x)] \approx \frac{1}{N} \sum_{i=1}^{N} \log p_{\theta}(x^{(i)})
\]

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_272.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_273.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_275.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_277.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_278.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_280.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_282.png)

这个近似值被称为 **经验对数似然**。因此，我们的最终学习目标——**最大似然估计**——就是最大化这个经验对数似然：

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_284.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_286.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_288.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_290.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_292.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_293.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_295.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_297.png)

\[
\max_{\theta} \frac{1}{N} \sum_{i=1}^{N} \log p_{\theta}(x^{(i)})
\]

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_299.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_301.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_303.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_305.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_306.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_307.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_309.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_311.png)

这非常直观：我们希望找到模型参数 \( \theta \)，使得模型对整个训练集中所有数据点的出现概率的乘积（或对数概率的和）最大。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_313.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_315.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_316.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_318.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_320.png)

---

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_322.png)

## 优化最大似然目标

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_324.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_326.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_328.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_330.png)

上一节我们定义了最大似然目标，本节我们来看看如何优化它。对于不同的模型族，优化方法也不同。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_332.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_334.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_336.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_338.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_339.png)

### 简单模型：解析解

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_341.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_343.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_344.png)

对于一些简单的模型，我们可以直接通过求导并令导数为零来得到最大似然估计的解析解。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_346.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_347.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_349.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_351.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_353.png)

**以伯努利分布为例**：
假设我们有一个抛硬币的数据集，包含3次正面和2次反面。我们想用伯努利分布 \( p_{\theta}(x) = \theta^x (1-\theta)^{1-x} \) 来建模，其中 \( \theta \) 是正面的概率。
对数似然为：
\[
L(\theta) = 3 \log \theta + 2 \log (1-\theta)
\]
通过求导并令其为零，可以解得最优的 \( \theta^* = 3/(3+2) = 0.6 \)。这与直觉相符：正面出现的频率就是最大似然估计。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_355.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_356.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_358.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_359.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_361.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_363.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_365.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_366.png)

**对于贝叶斯网络**：
如果模型是一个贝叶斯网络，且每个条件概率分布的参数是独立的（没有参数共享），那么整个网络的对数似然可以分解为多个独立项的和。这意味着我们可以独立地优化每个条件概率表的参数，通常也可以通过计数等简单方式得到解析解。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_368.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_369.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_371.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_372.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_374.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_376.png)

### 复杂模型：梯度下降

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_378.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_380.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_382.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_384.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_385.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_387.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_389.png)

对于参数化的神经网络模型（如神经自回归模型），条件概率分布由神经网络表示，参数之间存在共享（例如使用相同的权重矩阵或卷积核）。此时，最大似然目标没有封闭形式的解析解。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_391.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_393.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_395.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_397.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_399.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_400.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_402.png)

我们需要使用 **梯度下降** 来优化。梯度下降的过程如下：
1.  初始化模型参数 \( \theta \)。
2.  重复以下步骤：
    a.  **前向传播**：计算当前参数下，整个训练集（或一个批次）的对数似然 \( L(\theta) \)。
    b.  **反向传播**：计算对数似然相对于参数 \( \theta \) 的梯度 \( \nabla_{\theta} L(\theta) \)。
    c.  **参数更新**：沿着梯度方向更新参数：\( \theta \leftarrow \theta + \eta \nabla_{\theta} L(\theta) \)，其中 \( \eta \) 是学习率。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_404.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_406.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_407.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_409.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_411.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_412.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_413.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_415.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_417.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_419.png)

当训练集很大时，计算整个数据集的梯度（批量梯度下降）计算成本很高。因此，在实践中我们几乎总是使用 **随机梯度下降**。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_421.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_423.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_425.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_427.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_429.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_431.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_432.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_434.png)

**随机梯度下降与蒙特卡洛**：
注意到完整数据集的梯度可以写成一个期望形式：
\[
\nabla_{\theta} L(\theta) = \frac{1}{N} \sum_{i=1}^{N} \nabla_{\theta} \log p_{\theta}(x^{(i)}) = \mathbb{E}_{x \sim \text{Uniform}(\mathcal{D})} [\nabla_{\theta} \log p_{\theta}(x)]
\]
这里，期望是在训练集上均匀采样一个数据点。因此，我们可以使用蒙特卡洛估计来近似这个梯度——即随机采样一个**小批量**的数据，计算该批次的平均梯度，并用它来更新参数。这就是随机梯度下降，它同样是蒙特卡洛思想的应用。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_436.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_438.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_440.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_442.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_443.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_445.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_447.png)

---

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_449.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_451.png)

## 注意事项与总结

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_453.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_455.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_457.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_459.png)

### 过拟合与欠拟合

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_461.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_462.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_463.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_464.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_466.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_467.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_469.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_470.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_472.png)

在训练生成模型时，我们也会遇到经典的机器学习问题：
*   **欠拟合**：模型族过于简单，无法捕捉数据分布的结构（高偏差）。表现为模型在训练集和测试集上表现都差。
*   **过拟合**：模型族过于复杂，或者数据量太少，导致模型“记住”了训练数据而非学习其规律（高方差）。表现为模型在训练集上表现很好，但在测试集上表现差。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_474.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_475.png)

需要在模型复杂度和数据量之间取得平衡。技术如**正则化**、**权重共享**（本身也是一种降低参数空间复杂度的方式）和**使用更多数据**有助于缓解这些问题。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_477.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_478.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_480.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_481.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_483.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_485.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_487.png)

### 条件生成模型

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_489.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_491.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_492.png)

上述所有理论也适用于**条件生成模型**，即建模 \( p(y|x) \) 的模型（例如，给定文本描述生成图像）。此时，学习目标变为最大化**条件对数似然**：
\[
\max_{\theta} \frac{1}{N} \sum_{i=1}^{N} \log p_{\theta}(y^{(i)} | x^{(i)})
\]

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_494.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_495.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_496.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_497.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_499.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_501.png)

---

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_503.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_504.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_505.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_507.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_509.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_511.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_513.png)

### 本节课总结

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_514.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_516.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_518.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_520.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_521.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_523.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_524.png)

在本节课中，我们一起学习了生成模型的核心训练方法——**最大似然学习**。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_525.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_527.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_529.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_531.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_532.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_533.png)

1.  我们从衡量分布间距离的 **KL散度** 出发，推导出最大化**期望对数似然**的学习目标。
2.  由于无法直接计算真实数据分布的期望，我们利用训练集样本，通过 **蒙特卡洛估计** 得到了可优化的**经验对数似然**目标。
3.  对于不同复杂度的模型，我们讨论了两种优化方式：
    *   对于简单模型（如伯努利分布、朴素贝叶斯），可以直接求得**解析解**。
    *   对于复杂的神经网络模型（如神经自回归模型），我们使用**梯度下降**，特别是基于蒙特卡洛思想的**随机梯度下降**来进行优化。
4.  最后，我们简要提及了训练中需要注意的**过拟合与欠拟合**问题，以及最大似然框架如何扩展到**条件生成模型**。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_535.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_536.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_537.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_538.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_540.png)

最大似然是生成模型中应用最广泛的学习目标，它直接优化密度估计，并与生成、预测等任务有良好的关联。在接下来的课程中，我们将引入**潜变量模型**，在最大似然的框架下扩展模型家族，以实现更强大的生成和表征学习能力。