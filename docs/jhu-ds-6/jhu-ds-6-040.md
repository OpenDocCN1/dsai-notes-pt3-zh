# 040：置换检验 🔄

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_0.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_2.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_4.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_6.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_7.png)

在本节课中，我们将学习一种对数据科学家极其有用的工具——置换检验。我们将通过一个具体的例子来理解其原理和操作步骤。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_9.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_10.png)

## 概述

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_12.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_14.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_15.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_16.png)

置换检验是一种用于组间比较的非参数统计方法。它不依赖于数据的具体分布假设，而是通过随机打乱组别标签来构建一个在原假设下的统计量分布，从而进行假设检验。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_18.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_19.png)

## 一个动机示例：杀虫剂效果比较

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_21.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_22.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_24.png)

上一节我们介绍了置换检验的基本概念，本节中我们来看看一个具体的应用场景。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_26.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_27.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_28.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_30.png)

研究人员对多批昆虫施用不同的杀虫剂（标记为不同的喷雾类型），并统计了每批中死亡的昆虫数量。这些计数数据代表了每种杀虫剂的效果。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_32.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_34.png)

现在，我们考虑比较杀虫剂B和杀虫剂C的效果。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_36.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_37.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_38.png)

## 原假设与检验思路

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_40.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_41.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_42.png)

考虑原假设：两个组的观测值来自相同的分布。换句话说，每个计数数据被分配到哪个组别标签是无关紧要的。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_44.png)

操作上，可以想象一个数据框：一列是死亡昆虫的计数，另一列是喷雾组别的标签。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_46.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_47.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_48.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_49.png)

我们将计算一个统计量，例如两组平均死亡昆虫数量的差值：`mean(B) - mean(C)`。这是我们观察到的检验统计量。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_51.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_52.png)

## 置换检验的核心步骤

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_54.png)

接下来，我们看看如何通过置换来构建原假设下的分布。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_55.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_56.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_57.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_58.png)

核心思想是：在原假设成立（即组别标签与结果无关）的前提下，随机打乱组别标签，然后重新计算统计量。重复此过程多次，就能得到统计量在原假设下的经验分布。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_60.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_61.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_62.png)

以下是执行置换检验的关键步骤：

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_64.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_65.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_66.png)

1.  **计算观察到的统计量**：基于原始数据（标签与结果正确对应）计算你关心的统计量，例如均值差。
2.  **生成置换分布**：随机打乱组别标签，使标签与结果之间的原始对应关系被破坏。用打乱后的标签和原始结果重新计算统计量。将此过程重复大量次数（例如10,000次），得到一系列“置换统计量”。
3.  **计算P值**：P值等于在置换分布中，那些比观察到的统计量更极端（更支持备择假设）的置换统计量所占的比例。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_68.png)

## 统计量的选择与相关概念

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_70.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_71.png)

你可以根据研究问题选择任何你感兴趣的统计量。例如：
*   两组均值的差值。
*   两组的几何均值差。
*   甚至t统计量。你可以计算t统计量，但不与t分布比较，而是与基于置换的零分布进行比较。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_73.png)

置换检验非常强大，以至于它在不同场景下被不断重新发现。例如：
*   **秩和检验**（如著名的Wilcoxon检验）本质上是一种置换检验，只是先将原始数据转换为其秩次。
*   **Fisher精确检验**也是一种基于置换的检验，适用于数据类型为二分类的情况。
*   在**回归分析**中，你也可以使用置换策略，例如通过随机置换某个预测变量来获得其系数的零分布，这为不依赖正态假设的推断提供了另一种途径。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_75.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_76.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_77.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_78.png)

此外，还有一种称为**随机化检验**的方法。如果你的组别标签本身就是通过随机化分配得到的（例如在实验中），那么你进行的检验可以称为随机化检验。其操作方式与置换检验相同，但由于随机化的设计，你可能可以得出更强的因果推论。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_80.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_81.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_83.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_84.png)

## R语言实例演示

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_86.png)

现在，让我们通过一个R语言实例来具体演示置换检验的过程。我们将使用昆虫喷雾数据，比较喷雾B和C。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_88.png)

首先，我们准备数据并计算观察到的统计量（均值差）。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_90.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_91.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_92.png)

```r
# 假设数据已加载，我们提取喷雾B和C的数据
# y: 死亡昆虫计数
# group: 喷雾标签（B或C）
# 计算观察到的统计量：B组均值 - C组均值
observed_stat <- mean(y[group == "B"]) - mean(y[group == "C"])
```

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_94.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_95.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_97.png)

接下来，我们通过置换生成零分布。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_98.png)

```r
# 设置置换次数
n_perm <- 10000
# 初始化一个向量来存储每次置换的统计量
perm_stats <- numeric(n_perm)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_100.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_101.png)

# 进行置换
for(i in 1:n_perm) {
  # 随机打乱组别标签
  perm_group <- sample(group)
  # 用打乱后的标签计算统计量
  perm_stats[i] <- mean(y[perm_group == "B"]) - mean(y[perm_group == "C"])
}
```

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_102.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_103.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_105.png)

最后，我们计算P值并可视化结果。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_107.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_108.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_110.png)

```r
# 计算P值：置换统计量中，绝对值大于等于观察统计量绝对值的比例
# (此处假设备择假设为“均值不相等”，即双尾检验)
p_value <- mean(abs(perm_stats) >= abs(observed_stat))

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_111.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_113.png)

# 绘制置换分布直方图
hist(perm_stats, main = "Permutation Null Distribution", xlab = "Difference in Means (B - C)")
# 在图上添加观察到的统计量位置
abline(v = observed_stat, col = "red", lwd = 2)
```

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_115.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_116.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_118.png)

在这个数据集的例子中，观察到的统计量（B组平均比C组多杀死约13.25只昆虫）远在置换分布的尾部之外。在10,000次置换中，没有一次产生的统计量比观察到的更极端，因此P值非常小（接近0）。这使我们能够在任何合理的显著性水平（如α=0.05）下拒绝原假设，认为杀虫剂B和C的效果存在显著差异。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_119.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_121.png)

## 总结

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_123.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_124.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_125.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_126.png)

本节课中我们一起学习了置换检验。我们了解到，置换检验是一种通过随机重排数据标签来构建原假设下统计量分布的非参数检验方法。它的核心优势在于不依赖于总体分布的具体形式。我们通过一个杀虫剂比较的例子，详细讲解了其步骤：定义原假设、选择统计量、随机置换标签生成零分布、计算P值。最后，我们用R语言代码演示了完整的分析流程，并解读了结果。无论是自助法（关注统计量的抽样分布）还是置换检验（基于组别标签的可交换性进行正式推断），绘制重采样分布的直方图或密度图以直观理解其形态都是非常重要的。