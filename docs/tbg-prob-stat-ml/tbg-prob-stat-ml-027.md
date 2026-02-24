# 概率和统计机器学习：24：Boosting 🚀

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_0.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_2.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_4.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_6.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_7.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_9.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_10.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_11.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_12.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_13.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_15.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_16.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_18.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_19.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_20.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_21.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_23.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_24.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_26.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_27.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_28.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_29.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_31.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_33.png)

在本节课中，我们将要学习一种称为Boosting的学习范式。这是一种通过组合多个弱学习器来构建一个强学习器的集成学习方法。我们将探讨其核心思想、算法流程、理论保证以及实践应用。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_35.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_36.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_37.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_39.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_41.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_43.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_44.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_46.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_48.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_49.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_51.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_52.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_53.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_55.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_56.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_57.png)

## 概述

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_59.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_60.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_62.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_63.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_65.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_67.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_69.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_70.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_72.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_74.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_75.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_77.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_78.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_80.png)

Boosting是一种统计启发的学习范式，其核心思想是组合同一算法的多个版本，以期通过这种组合来改善最终结果。这与随机森林等集成方法不同，Boosting不通过随机化数据或特征来生成多样性，而是通过为训练数据点分配不同的权重，并迭代地训练弱学习器，最终将它们组合成一个强学习器。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_82.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_83.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_85.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_86.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_87.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_88.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_90.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_92.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_93.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_95.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_96.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_98.png)

## 强学习器与弱学习器

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_100.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_102.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_104.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_105.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_107.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_108.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_110.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_111.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_112.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_114.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_115.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_117.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_119.png)

上一节我们介绍了Boosting的基本目标。本节中，我们来看看其背后的核心哲学：强学习器与弱学习器的概念。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_121.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_122.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_124.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_126.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_127.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_128.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_130.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_131.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_133.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_134.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_136.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_138.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_139.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_141.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_142.png)

*   **强学习器**：这是我们最终希望得到的算法。它能够在有限的训练数据上学习到一个分类器，该分类器的误差非常小。直观地说，强学习器是一个能够以任意小的误差ε逼近真实解的算法。
*   **弱学习器**：这是指那些性能仅比随机猜测略好的算法。例如，在一个类别平衡的分类问题中，随机猜测的准确率是0.5。一个弱学习器的准确率可能是0.5 + ε，其中ε是一个很小的正数。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_143.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_145.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_147.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_148.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_149.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_151.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_153.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_154.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_155.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_156.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_158.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_160.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_161.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_162.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_163.png)

Boosting要解决的核心问题是：**给定一个弱学习器，能否通过组合多个这样的弱学习器，最终得到一个强学习器？** 答案是肯定的，而实现这一点的算法就是Boosting。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_165.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_166.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_167.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_169.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_171.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_172.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_174.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_176.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_177.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_178.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_179.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_181.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_183.png)

## Boosting算法流程

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_185.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_187.png)

理解了强学习器和弱学习器的概念后，本节我们来看看Boosting的具体算法是如何运作的。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_189.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_191.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_192.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_193.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_195.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_197.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_198.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_200.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_202.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_204.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_206.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_207.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_208.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_209.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_211.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_213.png)

Boosting算法（以AdaBoost为例）在T轮中迭代进行。在每一轮中，它基于当前的数据权重训练一个弱学习器，然后根据该弱学习器的表现更新数据点的权重，使得被错误分类的点在下一轮获得更高的关注度。最终，算法输出所有弱学习器的加权组合作为最终假设。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_215.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_217.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_219.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_220.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_222.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_223.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_225.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_227.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_228.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_229.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_230.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_232.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_233.png)

以下是AdaBoost算法的伪代码步骤：

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_235.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_236.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_237.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_239.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_240.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_241.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_242.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_243.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_245.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_246.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_248.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_249.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_251.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_253.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_254.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_255.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_256.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_258.png)

1.  **输入**：训练集 S = {(x₁, y₁), ..., (xₘ, yₘ)}，弱学习器 WL，迭代轮数 T。
2.  **初始化权重**：对于每个训练点 i，设置初始权重 D₁(i) = 1/m。
3.  **For t = 1 to T**：
    *   使用当前权重分布 D_t 训练弱学习器，得到假设 h_t。
    *   计算 h_t 的加权误差：ε_t = Σ_{i=1}^{m} D_t(i) * [y_i ≠ h_t(x_i)]。
    *   计算该轮假设的权重：w_t = 0.5 * ln((1 - ε_t) / ε_t)。
    *   更新数据点权重：对于每个 i，D_{t+1}(i) = (D_t(i) * exp(-w_t * y_i * h_t(x_i))) / Z_t，其中 Z_t 是归一化因子，确保所有权重之和为1。
4.  **输出最终假设**：H(x) = sign( Σ_{t=1}^{T} w_t * h_t(x) )。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_260.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_262.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_263.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_265.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_267.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_269.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_271.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_272.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_273.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_274.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_276.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_277.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_278.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_279.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_280.png)

## 算法直观理解与示例

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_282.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_284.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_285.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_286.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_288.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_290.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_291.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_292.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_294.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_295.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_297.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_298.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_299.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_301.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_302.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_304.png)

上一节我们介绍了算法的形式化步骤。本节中，我们通过一个具体的例子来直观理解Boosting是如何工作的。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_306.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_308.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_310.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_311.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_312.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_314.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_316.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_317.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_319.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_320.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_321.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_323.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_324.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_326.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_327.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_329.png)

假设我们有一个二维数据集，包含正例（+）和负例（-）。弱学习器是平行于坐标轴的决策树桩（单层决策树）。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_331.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_332.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_334.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_335.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_336.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_338.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_339.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_341.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_342.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_343.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_345.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_346.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_348.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_349.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_350.png)

*   **第一轮**：所有数据点权重相同。弱学习器产生一个分类边界（例如一条垂直线），它正确分类了大部分点，但错误分类了三个点（被圈出）。算法增加这三个错误分类点的权重。
*   **第二轮**：权重更新后，被错误分类的点显得更大（权重更高）。弱学习器在新的权重分布下训练，产生另一个分类边界（例如一条水平线）。它可能又错误分类了另外几个点（同样是之前难以分类的）。算法再次更新权重，增加新错误点的权重，同时降低正确分类点的权重。
*   **第三轮**：权重进一步调整。弱学习器训练后产生第三个分类边界。
*   **最终组合**：将三轮得到的三个弱分类器进行加权投票（权重 w_t 反映了该轮分类器的可靠性），得到一个复杂的非线性决策边界。在这个例子中，最终的组合分类器能够正确分类所有训练点。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_352.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_354.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_356.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_357.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_359.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_360.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_361.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_363.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_365.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_366.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_367.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_369.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_370.png)

这个例子展示了Boosting如何通过关注“困难”样本，并组合简单的决策规则，来构建一个强大的分类器。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_372.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_374.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_376.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_377.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_379.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_380.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_382.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_384.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_385.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_386.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_388.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_390.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_391.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_392.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_394.png)

## 理论保证：训练误差界

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_396.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_398.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_399.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_400.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_401.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_402.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_403.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_405.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_406.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_408.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_409.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_411.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_413.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_414.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_416.png)

看到Boosting在示例中有效后，我们自然会问：它在理论上是否可靠？本节我们探讨其关于训练误差的理论保证。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_418.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_419.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_420.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_422.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_423.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_424.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_426.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_427.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_429.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_431.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_433.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_434.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_436.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_437.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_438.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_440.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_442.png)

有一个重要定理保证了AdaBoost的训练误差会快速下降：

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_444.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_446.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_448.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_449.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_451.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_453.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_455.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_457.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_458.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_459.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_460.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_461.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_462.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_463.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_465.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_466.png)

**定理**：假设在AdaBoost的每一轮迭代t中，弱学习器都返回一个假设h_t，其加权分类误差 ε_t < 1/2 - γ（其中γ > 0）。那么，经过T轮迭代后，最终假设H的训练误差满足：
LS(H) ≤ exp(-2 γ² T)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_468.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_470.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_471.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_473.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_475.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_477.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_478.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_479.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_481.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_482.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_484.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_486.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_487.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_489.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_490.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_491.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_493.png)

**这个结论的意义**：
*   只要弱学习器在每一轮的表现都稳定地比随机猜测好一点（误差小于1/2），那么最终分类器的训练误差就会以**指数级速度**下降。
*   迭代轮数T越大，训练误差的上界就越小。这从理论上解释了Boosting如何将弱学习器提升为强学习器（至少在训练集上）。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_494.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_496.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_497.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_499.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_500.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_501.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_503.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_504.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_506.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_508.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_509.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_510.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_512.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_513.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_515.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_517.png)

**证明思路（简述）**：
1.  定义一个辅助变量 Z_T = Σ_{i=1}^{m} exp(-y_i F_T(x_i))，其中 F_T 是最终加权组合函数。可以证明，01训练误差 L_S(H) ≤ Z_T。
2.  通过巧妙的 telescoping product（叠乘分解），将 Z_T 表示为 Z_T = Π_{t=1}^{T} (Z_t / Z_{t-1})。
3.  核心步骤是证明每一轮的比值 Z_t / Z_{t-1} ≤ √(4 ε_t (1-ε_t))。
4.  利用条件 ε_t ≤ 1/2 - γ，可以推导出 √(4 ε_t (1-ε_t)) ≤ exp(-2 γ²)。
5.  因此，Z_T ≤ (exp(-2 γ²))^T = exp(-2 γ² T)，从而定理得证。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_519.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_521.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_522.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_524.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_525.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_527.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_528.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_529.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_531.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_532.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_533.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_535.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_536.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_538.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_539.png)

这个证明优雅地展示了算法设计（权重更新公式 w_t = 0.5 * ln((1-ε_t)/ε_t)）与理论保证之间的内在联系。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_540.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_542.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_544.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_545.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_546.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_547.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_549.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_551.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_553.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_555.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_557.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_558.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_559.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_560.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_561.png)

## 实践考量与总结

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_563.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_564.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_565.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_566.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_568.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_569.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_570.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_571.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_573.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_574.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_575.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_576.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_578.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_579.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_580.png)

上一节我们看到了Boosting强大的理论保证。本节中，我们来看看它在实践中的应用和一些重要注意事项。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_582.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_583.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_585.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_586.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_587.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_589.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_590.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_592.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_594.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_596.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_598.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_599.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_601.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_603.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_604.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_606.png)

**实践要点**：
*   **弱学习器的选择**：常用的弱学习器是**决策树桩**（深度为1的决策树），它简单、快速，并且能产生可解释的规则。理论上，任何能处理加权样本且性能略优于随机猜测的算法都可作为弱学习器。
*   **泛化能力**：上述定理只针对训练误差。在实践中，Boosting也表现出良好的泛化能力。其泛化误差的理论分析通常涉及**间隔理论**和**函数类复杂度**，相关结果可以在专门文献中找到。过度增加迭代轮数T可能导致过拟合，因此T常作为一个需要通过验证集调节的超参数。
*   **与随机森林对比**：
    *   **随机森林**：通过自助采样和随机特征子集引入多样性，各基学习器独立训练，最终进行平等投票。
    *   **Boosting**：使用全部数据但赋予不同权重，基学习器顺序训练，每个都试图修正前一个的错误，最终进行加权投票。
*   **优点**：理论清晰、实践效果好、对于许多问题可以作为强大的基准模型。最终模型是简单模型的加权和，具有一定的可解释性。
*   **扩展**：AdaBoost是Boosting家族的基础算法，后续发展出了如Gradient Boosting、XGBoost、LightGBM等更强大的变体，它们在效率和性能上做了诸多优化。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_608.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_609.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_611.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_613.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_614.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_616.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_618.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_620.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_621.png)

**总结**：
本节课我们一起学习了Boosting集成学习方法。我们从强学习器和弱学习器的概念出发，详细讲解了AdaBoost算法的流程、直观工作原理以及其训练误差指数下降的理论保证。Boosting通过迭代地调整数据权重，迫使弱学习器专注于之前被错误分类的样本，并将这些弱学习器的结果进行加权组合，从而构建出一个强大的最终模型。该算法在理论和实践上都得到了充分验证，是机器学习工具箱中一个重要且有效的工具。