# 4：鲁棒性 🛡️

![](img/5908a8422045a5f4b7dc83dccaedb4ad_1.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_3.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_5.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_7.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_9.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_11.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_13.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_14.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_16.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_18.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_20.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_22.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_24.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_25.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_27.png)

在本节课中，我们将要学习机器学习中的鲁棒性概念。我们将从数学基础回顾开始，然后探讨乘性权重算法，最后深入分析训练时和测试时的鲁棒性问题，包括数据投毒攻击、分布偏移和对抗性扰动。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_29.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_30.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_32.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_34.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_35.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_37.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_39.png)

## 数学基础回顾 📐

![](img/5908a8422045a5f4b7dc83dccaedb4ad_41.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_43.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_45.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_47.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_49.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_51.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_53.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_54.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_56.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_58.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_60.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_61.png)

上一节我们介绍了课程的整体框架，本节中我们来看看一些必要的数学工具，包括KL散度、集中不等式和矩阵代数。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_63.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_65.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_66.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_68.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_70.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_72.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_74.png)

### KL散度与交叉熵

![](img/5908a8422045a5f4b7dc83dccaedb4ad_76.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_78.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_80.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_82.png)

KL散度用于衡量两个概率分布P和Q之间的差异。其定义为：
```
KL(P||Q) = E_{x~P}[log(P(x)/Q(x))]
```
它可以分解为两部分：负熵 `-H(P)` 和交叉熵 `H(P, Q)`。交叉熵定义为 `E_{x~P}[-log Q(x)]`。KL散度总是非负的，这意味着对于任意两个分布P和Q，交叉熵 `H(P, Q)` 总是大于或等于熵 `H(P)`。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_84.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_86.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_88.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_90.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_92.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_93.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_94.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_95.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_97.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_99.png)

### 集中不等式

![](img/5908a8422045a5f4b7dc83dccaedb4ad_101.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_103.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_105.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_107.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_109.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_111.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_112.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_113.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_115.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_116.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_118.png)

集中现象描述了独立同分布随机变量的经验平均值会收敛到其期望值附近。对于一个有界随机变量Y，其期望为μ，经验平均值偏离ε的概率随ε²n呈指数级衰减。这意味着，当样本数量n大于1/ε²时，估计的准确性会变得非常好。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_120.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_122.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_124.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_125.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_127.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_129.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_131.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_133.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_134.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_136.png)

### 矩阵代数

![](img/5908a8422045a5f4b7dc83dccaedb4ad_138.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_139.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_141.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_143.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_145.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_146.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_148.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_150.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_152.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_154.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_156.png)

一个对称矩阵M是半正定的，如果它的所有特征值都是非负的。我们将其记为 `M ≽ 0`。这等价于对于所有向量v，有 `v^T M v ≥ 0`。我们可以将这个概念扩展到矩阵不等式：如果对于所有向量v，有 `v^T A v ≤ v^T B v`，则我们说 `A ≼ B`。矩阵的谱范数是其作为线性算子的最大放大倍数，对于对称矩阵，它等于最大特征值的绝对值。Frobenius范数是将矩阵视为向量时的欧几里得范数。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_158.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_159.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_160.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_162.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_164.png)

### 矩阵值随机变量

![](img/5908a8422045a5f4b7dc83dccaedb4ad_166.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_167.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_169.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_170.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_172.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_173.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_175.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_177.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_179.png)

我们可以将集中不等式的概念推广到矩阵值随机变量。如果Y₁, ..., Yₙ 是独立的有界对称矩阵，其谱范数以高概率满足类似标量情况的集中性，但会多出一个与维度d相关的对数因子。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_181.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_183.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_185.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_186.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_188.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_189.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_190.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_192.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_194.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_196.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_197.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_199.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_200.png)

### 随机矩阵

![](img/5908a8422045a5f4b7dc83dccaedb4ad_202.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_204.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_206.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_208.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_210.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_212.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_214.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_216.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_217.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_219.png)

随机矩阵的特征值分布遵循特定的规律。例如，具有独立标准正态分布条目的随机矩阵的特征值遵循半圆律。而像 `X = A A^T` 这样的矩阵（其中A是随机矩阵）的特征值分布则遵循Marchenko-Pastur分布，该分布的形状取决于维度d和样本数n的关系。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_221.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_223.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_225.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_227.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_229.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_231.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_233.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_234.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_236.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_238.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_240.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_242.png)

## 乘性权重算法 ⚖️

![](img/5908a8422045a5f4b7dc83dccaedb4ad_244.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_246.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_248.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_250.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_252.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_253.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_255.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_257.png)

在介绍了必要的数学工具后，我们来看一个在在线优化和机器学习中非常重要的算法：乘性权重算法。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_259.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_261.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_263.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_265.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_267.png)

### 问题设定

![](img/5908a8422045a5f4b7dc83dccaedb4ad_269.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_271.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_273.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_275.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_277.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_279.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_280.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_282.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_284.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_286.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_287.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_289.png)

我们有一个包含n个可能动作的集合。在每一轮时间t，我们根据一个概率分布P_t选择一个动作，并遭受一个损失ℓ_{i,t}。我们处于“专家模型”中，这意味着在选择动作后，我们会了解到所有动作（包括未选择的动作）的损失。这与“赌博机模型”不同，在赌博机模型中，我们只了解所选动作的损失。

### 算法描述

![](img/5908a8422045a5f4b7dc83dccaedb4ad_291.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_293.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_295.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_297.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_298.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_299.png)

算法从一个初始概率分布P₀开始。在每一轮t，我们根据P_{t-1}选择动作，观察到损失ℓ_{t}，然后按以下方式更新概率分布：
```
P_{t}(i) ∝ P_{t-1}(i) * exp(-η * ℓ_{i, t-1})
```
其中η是学习率。损失越大，该动作的权重就被惩罚得越多。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_301.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_303.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_305.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_307.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_309.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_311.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_313.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_315.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_316.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_317.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_319.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_321.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_323.png)

### 目标与遗憾

![](img/5908a8422045a5f4b7dc83dccaedb4ad_325.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_326.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_328.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_330.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_332.png)

我们的目标是最小化累积损失，并与 hindsight 中最优的固定概率分布P*的损失进行比较。两者之间的差值称为遗憾。乘性权重算法的核心定理表明，遗憾可以被两个项所界定：初始分布P₀与最优分布P*之间的KL散度（代表初始无知），以及学习率η（代表每步的敏感性）。通过平衡这两项，例如设置 `η = O(√(log n / T))`，我们可以将遗憾控制在 `O(√(log n / T))`。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_334.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_336.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_338.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_340.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_342.png)

### 算法扩展

![](img/5908a8422045a5f4b7dc83dccaedb4ad_344.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_346.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_348.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_349.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_350.png)

乘性权重算法可以看作是“跟随正则化领导者”框架的一个特例，其中动作集合是离散动作上的所有概率分布（一个凸集），正则化器是负熵。这鼓励算法在最小化损失的同时，保持概率分布的平坦性（高熵）。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_352.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_353.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_354.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_355.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_357.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_359.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_360.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_362.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_364.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_366.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_368.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_370.png)

## 鲁棒性概述 🛡️

![](img/5908a8422045a5f4b7dc83dccaedb4ad_372.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_374.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_376.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_378.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_380.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_382.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_383.png)

现在，让我们转向本节课的核心主题：机器学习模型的鲁棒性。模型的流程通常包括训练阶段（使用数据生成模型）和测试阶段（使用模型对新数据进行预测）。这个过程可能在多个环节受到攻击或干扰。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_385.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_386.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_388.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_390.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_392.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_394.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_396.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_398.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_400.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_402.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_404.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_406.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_407.png)

以下是两种主要的干扰类型：
1.  **训练时鲁棒性问题**：例如数据投毒攻击，即训练数据被恶意篡改或包含错误。
2.  **测试时鲁棒性问题**：例如分布偏移（测试数据与训练数据分布不同）和对抗性扰动（对测试输入进行微小、人类难以察觉的修改，导致模型错误分类）。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_409.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_411.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_413.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_414.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_416.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_418.png)

## 训练时鲁棒性与均值估计 🎯

![](img/5908a8422045a5f4b7dc83dccaedb4ad_420.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_422.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_424.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_426.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_428.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_429.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_431.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_432.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_434.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_436.png)

我们首先关注训练时的鲁棒性，从一个基础问题开始：在存在异常值的情况下估计均值。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_438.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_440.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_442.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_443.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_445.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_447.png)

### 问题与朴素方法

![](img/5908a8422045a5f4b7dc83dccaedb4ad_449.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_450.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_451.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_453.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_454.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_456.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_458.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_459.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_461.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_463.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_465.png)

假设我们有n个数据点，其中 `(1-ε)n` 个是独立从某个分布X中采样的“好”点，另外 `εn` 个是任意选择的“坏”点（异常值）。我们的目标是估计分布X的均值μ。
如果没有异常值，最好的估计是经验均值。然而，即使存在少量异常值，经验均值也可能被严重扭曲。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_467.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_468.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_469.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_471.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_472.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_474.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_476.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_478.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_480.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_481.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_483.png)

### 一维情况：中位数

![](img/5908a8422045a5f4b7dc83dccaedb4ad_485.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_486.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_488.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_490.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_492.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_494.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_496.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_498.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_499.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_501.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_503.png)

在一维情况下，中位数是对异常值鲁棒的估计量。即使有ε比例的异常值，中位数也能保证位于真实分布的第 `(1/2 - ε)` 和 `(1/2 + ε)` 分位数之间，从而与真实均值的偏差在O(ε)量级。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_505.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_507.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_508.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_510.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_512.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_513.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_515.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_516.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_517.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_519.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_521.png)

### 高维挑战与Tukey中位数

![](img/5908a8422045a5f4b7dc83dccaedb4ad_522.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_524.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_526.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_528.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_530.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_532.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_534.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_536.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_538.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_540.png)

在高维情况下，一个自然的想法是计算每个坐标的中位数。然而，对手可以通过在少数点上添加一个全1向量，使得坐标中位数估计在每一个坐标上都产生ε的偏差，导致与真实均值的总偏差高达 `O(ε√d)`。这比我们希望的O(ε)要差。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_542.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_544.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_546.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_548.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_549.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_551.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_553.png)

Tukey中位数提供了一个更好的定义。一个点μ*被称为Tukey中位数，如果对于每一个方向向量v，投影到v上的点中，位于μ*两侧的点数大致平衡（例如，差值不超过3εn）。可以证明，对于从各向同性分布（如标准正态分布）中采样的“好”点，经验均值本身就是一个Tukey中位数。更重要的是，任何Tukey中位数μ*与真实均值μ的距离都在O(ε)以内。因此，找到Tukey中位数就能给出一个好的均值估计。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_555.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_557.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_559.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_560.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_561.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_562.png)

### 高效算法与认证

![](img/5908a8422045a5f4b7dc83dccaedb4ad_564.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_566.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_567.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_568.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_570.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_571.png)

然而，精确计算Tukey中位数是NP难的。实践中，我们使用高效的算法。一个关键思想是利用经验协方差矩阵进行“认证”。如果经验协方差矩阵的谱范数很小，那么经验均值就是一个好的估计量，其误差上界为 `O(√d/n + ε * ||Σ_hat||)`。如果谱范数很大，说明存在一个方向方差很大，我们可以利用乘性权重算法的思想，降低在该方向上投影值较大的数据点的权重，迭代地过滤异常值，最终得到一个平坦的权重分布和小的经验协方差谱范数，从而获得可靠的均值估计。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_573.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_574.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_576.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_578.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_580.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_581.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_583.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_585.png)

## 神经网络与数据投毒 🧠

![](img/5908a8422045a5f4b7dc83dccaedb4ad_587.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_588.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_590.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_592.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_594.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_596.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_598.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_600.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_602.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_604.png)

神经网络对训练数据的变化可能非常敏感。一种观点是，神经网络将数据嵌入到高维空间，在该空间中分类任务（例如区分猫和狗）变得简单（例如线性可分）。然而，这个嵌入表示的大部分范数可能存在于与分类无关的方向上，而与类别相关的信号只占一小部分。这使得模型容易受到攻击：通过在训练集中注入少量精心构造的样本（例如，在决策边界附近放置一些带有错误标签的样本），可以诱使模型学习到一个完全不同的、在干净数据上表现很差的决策边界。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_606.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_607.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_608.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_609.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_611.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_613.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_614.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_616.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_618.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_620.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_622.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_623.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_625.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_626.png)

## 测试时鲁棒性：分布偏移 🌍

![](img/5908a8422045a5f4b7dc83dccaedb4ad_628.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_629.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_631.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_633.png)

现在，我们来看测试时的鲁棒性问题，首先是分布偏移。

### 经验观察

![](img/5908a8422045a5f4b7dc83dccaedb4ad_635.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_637.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_639.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_640.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_642.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_644.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_646.png)

一个令人惊讶的经验观察是，当在一个分布D上训练模型，并在另一个相关但不同的分布D‘上测试时，模型在D’上的准确率与在D上的准确率常常呈现出强烈的线性关系。即使D和D‘在某些度量下相距甚远（例如，森林中狗的照片 vs. 海滩上狗的照片），这种线性关系仍然存在。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_648.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_650.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_652.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_654.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_656.png)

### 案例研究：CIFAR数据集

![](img/5908a8422045a5f4b7dc83dccaedb4ad_658.png)

以CIFAR-10及其变体CIFAR-10.1/10.2为例。CIFAR-10.1/10.2是使用与原始CIFAR-10相同的方法（从Tiny Images数据集中搜索、采样、人工标注）重新构建的数据集。测试发现，在CIFAR-10上表现不同的各种模型，其在CIFAR-10.1/10.2上的准确率与在CIFAR-10上的准确率呈线性关系。这种线性关系表明，模型在原始测试集上的性能可以预测其在来自相同“数据生成过程”的新数据上的性能。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_660.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_662.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_664.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_665.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_667.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_669.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_670.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_671.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_672.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_674.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_675.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_677.png)

### 一个理论模型

![](img/5908a8422045a5f4b7dc83dccaedb4ad_679.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_680.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_682.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_684.png)

我们可以用一个简单的理论模型来理解这种线性关系。假设数据表示向量由两部分组成：一个与类别相关的通用方向 `v_cat`，和一个与特定数据集相关的 idiosyncratic 方向 `I`。在数据集D中，一个样本被标记为“猫”的概率与 `β * (x·v_cat) + α * (x·I)` 相关。当我们用梯度下降在D上训练一个线性分类器C时，C会与 `v_cat + αI` 的方向对齐。在另一个数据集D‘上测试时，假设D’的 idiosyncratic 方向 `I‘` 与 `I` 正交，那么分类器在D‘上的表现就只与它在通用方向 `v_cat` 上的投影有关，而这个投影又与它在D上的表现成比例，从而导致了线性关系。这个模型还预测，由于 idiosyncratic 成分的存在，即使D‘不比D“更难”，斜率也可能小于1。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_686.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_687.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_688.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_690.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_692.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_693.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_695.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_697.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_698.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_700.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_702.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_704.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_706.png)

## 测试时鲁棒性：对抗性扰动 ⚔️

![](img/5908a8422045a5f4b7dc83dccaedb4ad_708.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_710.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_712.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_713.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_715.png)

另一个重要的测试时鲁棒性问题是对抗性扰动。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_717.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_719.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_721.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_723.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_725.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_727.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_729.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_731.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_733.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_735.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_736.png)

### 现象

![](img/5908a8422045a5f4b7dc83dccaedb4ad_738.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_740.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_742.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_744.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_746.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_747.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_748.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_749.png)

对抗性扰动是指向输入添加一个人类难以察觉的微小噪声δ，使得模型产生完全错误的分类。例如，一张被ResNet-50以99.6%置信度分类为“豪猪”的图片，在添加了微小的特定噪声后，被模型以高置信度分类为“食蚁兽”，而人眼几乎看不出区别。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_751.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_752.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_754.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_755.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_757.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_759.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_761.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_763.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_764.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_766.png)

### 为何可能发生？

这或许并不完全令人意外。考虑神经网络的表示：输入图像x被映射为高维表示向量R(x)。最终分类通常基于R(x)与某个类别向量（如 `v_hog`）的点积。假设“豪猪”类别的信号强度（即 `R(x)·v_hog`）为3（对应99.6%的置信度），而表示向量的总范数约为√d（d为表示维度，例如2048）。这意味着“豪猪”信号只占表示向量总能量的很小一部分（例如 ~1/25）。因此，存在一个扰动方向，可以显著降低 `R(x)` 在 `v_hog` 方向上的投影，同时只引起R(x)的微小变化（如果模型的Lipschitz常数不是特别小）。由于深度学习模型的高度非线性，其表示空间可能存在许多这样的脆弱方向，使得寻找对抗性扰动成为可能。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_768.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_770.png)

### 对抗训练

![](img/5908a8422045a5f4b7dc83dccaedb4ad_772.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_773.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_775.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_777.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_779.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_781.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_783.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_785.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_787.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_788.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_790.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_791.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_792.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_794.png)

为了提高模型对对抗性扰动的鲁棒性，最常用的方法是**对抗训练**。其核心思想是最小化“鲁棒损失”。定义一组允许的扰动变换T（例如，所有L∞范数小于ε的扰动）。对于分类器f和数据点(x, y)，其鲁棒损失是 worst-case 的损失：
```
L_robust(f, x, y) = max_{τ in T} L(f(τ(x)), y)
```
对抗训练就是最小化训练集上的平均鲁棒损失。这是一个 min-max 优化问题。根据 Danskin 定理，在内部最大化问题可以（近似）求解的情况下，我们可以计算外层最小化问题的梯度并进行训练。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_796.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_797.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_799.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_801.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_803.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_805.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_807.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_809.png)

### 准确率-鲁棒性权衡

![](img/5908a8422045a5f4b7dc83dccaedb4ad_811.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_813.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_815.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_817.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_818.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_820.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_822.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_823.png)

在实践中，对抗训练往往会在提高对抗鲁棒性的同时，降低模型在干净数据上的标准准确率，形成一种权衡。目前尚不完全清楚这种权衡在多大程度上是问题本身固有的，还是当前算法和扰动模型（如L∞球）所导致的。一个有趣的对比是**数据增强**：数据增强也是对输入应用不改变标签的变换（如旋转、裁剪），但它是随机采样变换而不是取最坏情况，并且通常能提高标准准确率。探索这两种方法之间的深刻区别，以及是否存在一种方法能同时提升干净准确率和鲁棒性，是一个开放的研究问题。

![](img/5908a8422045a5f4b7dc83dccaedb4ad_825.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_827.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_829.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_831.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_833.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_834.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_836.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_838.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_840.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_841.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_842.png)

## 总结 📝

![](img/5908a8422045a5f4b7dc83dccaedb4ad_844.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_846.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_848.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_849.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_851.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_853.png)

![](img/5908a8422045a5f4b7dc83dccaedb4ad_855.png)

本节课中我们一起学习了机器学习鲁棒性的核心概念。
我们首先回顾了KL散度、集中不等式和矩阵值随机变量等数学基础。
接着，我们探讨了乘性权重算法，它是许多在线学习和优化算法的基础。
然后，我们深入分析了训练时鲁棒性，特别是在数据投毒下的均值估计问题，介绍了Tukey中位数的概念和高效的滤波算法。
对于测试时鲁棒性，我们讨论了分布偏移中观察到的模型性能线性相关现象，并给出了一个理论解释模型；我们还分析了对抗性扰动的成因以及通过对抗训练进行防御的方法，并指出了当前存在的准确率-鲁棒性权衡问题。
鲁棒性是构建可靠、安全机器学习系统的关键，这一领域仍然存在许多有趣的开放问题和挑战。