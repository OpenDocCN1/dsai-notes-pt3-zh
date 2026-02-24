# 概率和统计机器学习：51：低秩矩阵补全算法 🧩

![](img/afd64bdb3310ca35511ef030f3b8e4b3_1.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_2.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_3.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_4.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_6.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_8.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_10.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_11.png)

在本节课中，我们将要学习低秩矩阵补全问题及其算法。这是一个在推荐系统（如Netflix电影推荐）中非常经典的问题，其核心目标是根据一个大型矩阵中少量已知的条目，来估计所有未知的条目。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_13.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_14.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_16.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_17.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_18.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_20.png)

## 问题引入：Netflix挑战赛

![](img/afd64bdb3310ca35511ef030f3b8e4b3_22.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_24.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_26.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_27.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_28.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_29.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_31.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_32.png)

上一节我们介绍了低秩矩阵补全的背景。本节中我们来看看一个著名的实际应用案例。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_34.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_36.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_38.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_39.png)

考虑Netflix的场景：你有许多用户和许多电影。某些用户观看了电影并给出了评分。你可以尝试将所有评分存储在一个矩阵中。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_41.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_42.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_43.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_44.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_45.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_47.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_49.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_51.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_52.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_54.png)

*   矩阵的行对应**用户**。
*   矩阵的列对应**电影**。
*   矩阵中的条目 `M[i, j]` 表示用户 `i` 对电影 `j` 的评分。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_56.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_58.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_59.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_60.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_61.png)

然而，这个矩阵的绝大部分是空的，因为大多数用户没有看过大多数电影。矩阵补全问题的目标就是**估计所有缺失的条目**。例如，为了向用户推荐一部新电影，我们需要预测该用户对所有未观看电影的潜在评分。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_63.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_64.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_65.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_66.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_67.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_68.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_70.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_71.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_73.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_74.png)

十多年前，机器学习社区有一个非常著名的挑战赛——Netflix挑战赛。其数据包含约2万部电影、50万用户和约10亿个评分。这意味着只有大约**1%** 的矩阵条目是已知的。比赛的目标是设计一个算法，其预测缺失条目的效果比Netflix自己的算法好至少10%，优胜者将获得100万美元的奖金。这成为了机器学习社区的一个历史性事件。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_75.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_76.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_77.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_79.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_81.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_83.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_84.png)

## 问题的一般形式化

![](img/afd64bdb3310ca35511ef030f3b8e4b3_86.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_87.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_88.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_89.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_91.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_92.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_94.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_95.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_96.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_97.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_99.png)

现在让我们回到矩阵补全的一般性问题设定。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_101.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_103.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_105.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_106.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_107.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_108.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_109.png)

我们有一个未知的 `m × n` 矩阵 `M`（例如，m个用户，n个电影）。我们只能观察到该矩阵的一部分条目。在后续讨论中，我们做一个重要假设：**被观测条目的位置是随机选取的**。这类似于标准分类任务中，我们假设训练样本是从底层分布中随机抽取的。这个假设排除了对抗性设置，使得问题有可能被解决。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_111.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_112.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_113.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_115.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_117.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_119.png)

我们的目标是**估计所有未知的条目**。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_121.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_122.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_123.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_125.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_127.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_128.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_129.png)

在深入算法之前，思考一下这个问题的可解性非常重要。如果我们对底层矩阵 `M` 不做任何假设，例如它的每个条目都是独立随机生成的（如抛硬币），那么无论我们观察到多少条目，都无法对未观察到的条目做出任何推断。因此，我们需要一个**归纳偏置**，即对矩阵 `M` 的结构做出假设，以限制解的搜索空间，防止过拟合。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_131.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_132.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_134.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_135.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_137.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_138.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_140.png)

## 核心假设：低秩性

![](img/afd64bdb3310ca35511ef030f3b8e4b3_142.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_143.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_145.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_147.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_148.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_149.png)

本节我们将介绍解决矩阵补全问题的核心假设。

该领域普遍使用的假设是：我们寻找的矩阵具有**低秩**。从理论角度看，低秩矩阵的集合比高阶矩阵的集合更小。从实践角度看，这个归纳偏置往往效果很好。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_151.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_153.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_155.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_156.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_157.png)

我们可以做一个合理性检查：随机生成的矩阵通常具有很高的秩（其特征值遵循半圆律），因此不会被低秩模型很好地近似。这与我们的直觉一致，即完全随机的矩阵无法被补全。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_159.png)

现在让我们形式化地定义矩阵补全问题。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_161.png)

我们用 `Ω` 表示观测到的条目索引集合 `(i, j)`。对于这些索引，我们知道其值 `M[i, j]`。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_163.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_164.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_165.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_167.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_168.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_169.png)

我们想要找到一个矩阵 `X`，使得：
1.  `X` 在观测位置上的条目与已知值尽可能一致。
2.  `X` 的秩尽可能低。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_171.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_172.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_173.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_174.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_175.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_177.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_179.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_180.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_182.png)

这可以写成以下优化问题（精确恢复版本）：
```
最小化 rank(X)
约束条件：P_Ω(X) = P_Ω(M)
```
其中 `P_Ω` 是到观测条目集合 `Ω` 上的投影算子。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_183.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_184.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_186.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_187.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_189.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_190.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_191.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_192.png)

更常见的是考虑近似恢复的版本，例如正则化形式：
```
最小化 ||P_Ω(X) - P_Ω(M)||_F^2 + λ · rank(X)
```
其中 `||·||_F` 是Frobenius范数，`λ` 是正则化参数。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_193.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_194.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_196.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_197.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_199.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_200.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_201.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_203.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_204.png)

然而，**矩阵的秩函数是不连续且非凸的**，导致上述优化问题是NP难的。微小的扰动可能使矩阵的秩发生剧烈变化，这使得基于梯度的优化方法非常困难。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_206.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_207.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_208.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_209.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_210.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_211.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_213.png)

## 从硬阈值到软阈值

![](img/afd64bdb3310ca35511ef030f3b8e4b3_215.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_216.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_217.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_219.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_221.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_222.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_224.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_225.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_226.png)

由于直接优化秩是NP难问题，我们需要寻找高效的启发式算法。首先介绍一种简单方法。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_228.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_229.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_231.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_232.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_233.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_235.png)

**硬补全算法** 是一种迭代方法：
1.  初始化：对未知条目进行随机猜测，填充矩阵。
2.  迭代直至收敛：
    a.  对当前矩阵进行奇异值分解。
    b.  只保留前 `r` 个最大的奇异值及其对应的奇异向量，重构一个低秩矩阵 `X_k`。
    c.  将 `X_k` 在观测位置 `Ω` 上的值替换为真实观测值，得到新的填充矩阵，进入下一轮迭代。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_237.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_238.png)

这个方法有时有效，但并不完全令人满意。问题的核心在于秩约束太“硬”。我们需要找到一个更“软”的替代函数来度量矩阵的复杂性。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_240.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_242.png)

这让我们回想起在Lasso回归中处理稀疏性的方法。我们希望找到一个系数向量，其中大部分系数为零。衡量稀疏性最直接的方法是计算非零系数的数量（`l_0` 范数），但这导致非凸优化。实践中，我们使用 `l_1` 范数作为凸松弛，它通常能产生稀疏解。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_243.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_245.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_247.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_248.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_250.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_252.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_253.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_255.png)

类似地，对于矩阵的低秩性，我们可以进行类比。一个矩阵的秩等于其**奇异值向量中非零元素的个数**（即奇异值向量的 `l_0` 范数）。受Lasso启发，一个自然的凸松弛是使用奇异值向量的 `l_1` 范数。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_256.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_257.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_259.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_261.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_262.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_263.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_264.png)

## 核范数：秩的凸松弛

![](img/afd64bdb3310ca35511ef030f3b8e4b3_266.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_267.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_268.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_269.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_270.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_271.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_272.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_274.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_275.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_277.png)

本节我们引入核范数，作为矩阵秩的凸松弛。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_278.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_280.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_282.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_283.png)

给定矩阵 `X`，令 `σ(X) = [σ_1, σ_2, ..., σ_r]` 为其奇异值向量。矩阵的秩是 `||σ(X)||_0`。我们将其松弛为 `l_1` 范数，即所有奇异值之和：
```
||X||_* = σ_1 + σ_2 + ... + σ_r
```
这个范数被称为矩阵的**核范数** 或**迹范数**。可以证明，核范数是矩阵秩的**最紧凸松弛**。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_285.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_287.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_289.png)

利用核范数，我们将原来的NP难问题转化为凸优化问题：
```
最小化 ||P_Ω(X) - P_Ω(M)||_F^2 + λ ||X||_*
```
现在的问题是：我们能否为这个问题找到高效的算法？考虑到实际应用（如Netflix）中矩阵规模巨大（百万×百万），算法的效率至关重要。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_291.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_293.png)

## 软补全算法

现在，我们介绍一个高效且具有理论保证的算法——软补全算法。其核心组件是**软阈值**操作。

**软阈值操作** 定义如下：对于矩阵 `Z`，进行奇异值分解 `Z = U diag(d) V^T`，其中 `d = [d_1, d_2, ...]` 是奇异值向量。给定阈值参数 `λ > 0`，软阈值操作 `S_λ(Z)` 生成一个新矩阵，其奇异值为 `[s_λ(d_1), s_λ(d_2), ...]`，其中软阈值函数为：
```
s_λ(x) = sign(x) · max(|x| - λ, 0)
```
这意味着：
*   所有绝对值小于 `λ` 的奇异值被置为0。
*   所有绝对值大于 `λ` 的奇异值向零收缩 `λ`。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_295.png)

软阈值操作总是降低矩阵的核范数，并且通常会降低矩阵的秩（通过将小奇异值置零）。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_297.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_299.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_300.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_301.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_303.png)

一个关键结论是：对于**完全已知**的矩阵 `Z`，优化问题 `最小化 ||X - Z||_F^2 + λ ||X||_*` 的全局最优解恰好就是一次软阈值操作的结果：`X^* = S_λ(Z)`。

基于这个结论，我们可以设计处理部分观测矩阵的算法。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_305.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_307.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_309.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_310.png)

**软补全算法** 流程如下：
输入：部分观测矩阵 `P_Ω(M)`，一组递减的阈值参数 `λ_1 > λ_2 > ... > λ_K`。
1.  初始化 `X^old = 0`。
2.  对于每个 `λ_k` (从大到小):
    a.  重复：
        i.   构造矩阵 `Z = P_Ω(M) + P_{Ω^⊥}(X^old)`。即将观测值固定在正确位置，未知位置用当前估计 `X^old` 填充。
        ii.  对 `Z` 应用软阈值操作：`X^new = S_{λ_k}(Z)`。
        iii. 如果 `X^new` 与 `X^old` 足够接近，则跳出内循环；否则令 `X^old = X^new`，继续迭代。
    b.  得到对应于 `λ_k` 的解。
3.  输出一系列对应于不同 `λ_k` 的解。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_312.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_314.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_316.png)

**算法解释**：
*   **内循环（固定λ）**：在每次迭代中，它将观测值“钉”在正确位置，然后对当前完整矩阵进行软阈值降秩估计，并迭代此过程直至收敛。这可以看作是在强制满足观测约束和追求低核范数之间进行迭代权衡。
*   **外循环（递减λ）**：从一个较大的 `λ`（对应更强的低秩约束，更容易优化）开始，然后逐渐减小 `λ`（放松约束，追求更精确的拟合）。这是一种路径追踪策略，提高了算法的稳定性和效率。

该算法可以证明，对于合适的参数选择序列，其解会收敛到全局最优解。更重要的是，该算法可以高效实现，即使对于像Netflix那样大规模（亿级条目）的矩阵，也只需数小时即可完成。实现的关键在于利用矩阵的结构：`P_Ω(M)` 是稀疏的（仅少数观测值），而中间估计矩阵 `X` 是低秩的，可以利用高效的稀疏+低秩矩阵运算。

## 实践表现与总结

![](img/afd64bdb3310ca35511ef030f3b8e4b3_318.png)

最后，我们来看看软补全算法在实践中的表现，特别是Netflix数据上的结果。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_320.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_322.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_324.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_325.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_327.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_329.png)

下图展示了在Netflix数据上，硬补全与软补全算法的比较：
*   **左图**：横轴是所用模型的秩（或对应的复杂度），纵轴是均方根误差。实线表示测试误差，虚线表示训练误差。可以看到，两种方法都能显著降低误差（随机猜测的误差约为2，而算法能达到约0.95）。软补全（红色）的测试误差略优于硬补全（绿色）。
*   **右图**：展示了训练误差与测试误差的关系。虚线表示Netflix官方算法的性能。软补全算法可以达到甚至略微超越这个基准性能。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_331.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_332.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_334.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_336.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_337.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_339.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_341.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_342.png)

本节课中我们一起学习了低秩矩阵补全问题及其核心算法。我们从Netflix挑战赛的实际问题出发，形式化了矩阵补全任务，并指出其需要低秩假设才可求解。由于直接优化矩阵秩是NP难问题，我们引入了核范数作为其最紧凸松弛。在此基础上，详细介绍了**软补全算法**，该算法基于**软阈值**操作，通过迭代地在观测约束和低核范数目标之间进行优化，能够高效地求解大规模矩阵补全问题，并具有理论收敛保证。实践表明，该算法在真实数据集上表现优异。