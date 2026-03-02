#  055：平均故障时间 🕰️

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_0.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_2.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_3.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_5.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_7.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_9.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_11.png)

在本节课中，我们将要学习如何利用期望值的概念来解决一个经典问题——平均故障时间问题。理解期望值可以帮助我们更轻松地处理一些概率问题。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_13.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_15.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_17.png)

## 概述

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_19.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_21.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_23.png)

上一节我们介绍了期望值的基本概念。本节中，我们来看看如何应用期望值来解决一个具体的、在计算机系统和概率分析中常见的问题：计算一个系统首次出现故障的平均时间。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_25.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_27.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_29.png)

## 平均故障时间问题

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_31.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_32.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_34.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_36.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_38.png)

考虑一个系统，它在每一步（或每一次观察）都可能以某个概率 **p** 发生故障。每一步的故障事件是**相互独立**的，这意味着第一步是否故障不会影响第二步是否故障。我们关心的是，系统**首次发生故障**是在哪一步。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_40.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_42.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_43.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_44.png)

我们定义随机变量 **R** 为首次故障发生的步数。那么，**R 的期望值 E[R]** 就是平均故障时间。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_46.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_47.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_49.png)

## 期望值的推导

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_51.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_53.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_55.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_57.png)

以下是计算 E[R] 的步骤：

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_59.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_61.png)

首先，根据期望值的定义，对于取值为正整数的随机变量 R，其期望值可以表示为：
`E[R] = Σ_{i=0}^{∞} P(R > i)`

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_63.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_64.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_65.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_66.png)

这里的 `P(R > i)` 表示前 i 步都没有发生故障的概率。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_68.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_69.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_70.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_71.png)

由于每一步是否故障是独立的，前 i 步都没有故障的概率等于每一步都不故障的概率的乘积。如果每一步的故障概率是 p，那么每一步不故障的概率就是 `(1-p)`。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_73.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_75.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_76.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_77.png)

因此，`P(R > i) = (1-p)^i`。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_79.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_81.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_82.png)

将这个结果代入期望值公式：
`E[R] = Σ_{i=0}^{∞} (1-p)^i`

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_84.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_86.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_88.png)

这是一个无穷几何级数求和。因为 `(1-p) < 1`，我们可以使用几何级数求和公式：
`Σ_{i=0}^{∞} x^i = 1 / (1 - x)`，其中 `|x| < 1`。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_90.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_91.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_93.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_95.png)

在这里，`x = (1-p)`。所以：
`E[R] = 1 / (1 - (1-p)) = 1 / p`

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_96.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_98.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_100.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_102.png)

**核心公式**：
`平均故障时间 E[R] = 1 / p`

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_104.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_105.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_107.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_109.png)

这个公式非常简洁：**平均故障时间等于故障概率的倒数**。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_111.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_113.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_115.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_117.png)

## 应用示例

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_119.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_120.png)

现在，我们通过两个例子来应用这个公式。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_121.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_123.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_125.png)

### 示例一：系统故障
假设一个系统每次运行的故障概率 `p = 0.01`（即1%）。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_127.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_128.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_129.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_131.png)

根据公式，平均故障时间为：
`E[R] = 1 / 0.01 = 100`

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_133.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_134.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_135.png)

这意味着，平均而言，我们需要运行这个系统 **100次** 才会观察到第一次故障。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_137.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_138.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_140.png)

### 示例二：亨利八世的继承人问题 👑
这是一个经典的概率趣题。亨利八世想要一个儿子（继承人），他会一直生孩子直到得到一个男孩为止。假设生男生女的概率各为 `1/2`，且每次生育性别独立。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_142.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_144.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_145.png)

我们可以把“生到男孩”视为“故障”事件。那么，故障概率 `p = 0.5`。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_147.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_148.png)

根据平均故障时间公式，得到第一个男孩所需的平均孩子数量为：
`E[R] = 1 / 0.5 = 2`

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_150.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_151.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_152.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_154.png)

所以，亨利八世**平均需要生2个孩子**才能得到他的继承人。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_156.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_158.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_160.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_162.png)

进一步思考：
*   在得到第一个男孩之前，他平均会有 `E[R] - 1 = 1` 个女孩。
*   那么，如果他想**至少拥有一个男孩和一个女孩**（即“一儿一女”），平均需要生多少个孩子呢？

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_164.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_165.png)

我们可以这样分析：
1.  第一个孩子可能是男孩或女孩，概率各半。
2.  无论第一个孩子是男是女，接下来要得到另一个性别的孩子，其平均等待时间同样是 `1/p = 2`（因为 `p` 仍是 `0.5`）。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_167.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_168.png)

因此，总的孩子数量的期望值是：
`第一个孩子 + 等待另一个性别的平均时间 = 1 + 2 = 3`

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_169.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_170.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_172.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_173.png)

所以，要至少拥有一儿一女，**平均需要生3个孩子**。

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_175.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_176.png)

## 总结

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_178.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_179.png)

![](img/2c7c4a5ae7066667a3f16b3ed7bafe26_181.png)

本节课中我们一起学习了平均故障时间问题。我们推导出了核心公式 **`E[R] = 1 / p`**，它表示在每次尝试独立且成功（此处指故障）概率为 p 的情况下，首次成功所需尝试次数的平均值。我们通过系统故障和生育计划两个例子演示了这个公式的应用。理解这个模型有助于我们分析各种需要等待特定事件首次发生的场景，是概率论在计算机科学和日常推理中的一个有力工具。