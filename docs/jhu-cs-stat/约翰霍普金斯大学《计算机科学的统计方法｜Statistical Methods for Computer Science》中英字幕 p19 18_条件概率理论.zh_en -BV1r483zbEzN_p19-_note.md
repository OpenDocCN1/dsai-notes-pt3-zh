# 计算机科学的统计方法：19：条件概率理论 🎲

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_1.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_3.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_5.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_7.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_9.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_11.png)

在本节课中，我们将要学习**条件概率**。条件概率是概率论中的一个核心概念，它描述了在已知某个事件发生的情况下，另一个事件发生的概率。我们将通过几个抛硬币的例子，直观地理解如何计算条件概率。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_13.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_15.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_17.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_19.png)

---

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_21.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_23.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_25.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_27.png)

## 示例一：两枚硬币的选择

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_29.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_31.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_33.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_35.png)

假设鲍勃从一个袋子中选择一枚硬币。袋子里有两枚硬币：一枚是**公平硬币**，另一枚是**两面都是正面的硬币**。

公平硬币意味着出现正面或反面的概率各为50%。两面都是正面的硬币则意味着抛掷结果永远是正面。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_37.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_38.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_39.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_41.png)

我们的问题是：**在鲍勃抛掷一次硬币并观察到正面的条件下，他选到公平硬币的概率是多少？**

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_43.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_44.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_46.png)

为了解答这个问题，我们使用一种强大的工具——**概率树**来分析所有可能的结果。

以下是构建概率树的步骤：
1.  首先，鲍勃有两种选择：公平硬币或两面都是正面的硬币。
2.  如果选择公平硬币，抛掷结果可能是正面或反面。
3.  如果选择两面都是正面的硬币，抛掷结果只能是正面。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_48.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_49.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_50.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_51.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_52.png)

现在，我们已知观察到的结果是正面。因此，所有导致反面的分支（即公平硬币抛掷出反面的情况）都不在我们的考虑范围内。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_54.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_55.png)

在剩余的样本空间中，总共有三种可能得到正面：
1.  选择公平硬币并抛出正面。
2.  选择两面都是正面的硬币并抛出正面（第一种情况）。
3.  选择两面都是正面的硬币并抛出正面（第二种情况，虽然结果相同，但在计数上视为不同的可能性路径）。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_57.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_58.png)

在这三种可能中，只有第一种情况（选择公平硬币并抛出正面）符合“选到公平硬币”的条件。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_60.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_61.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_62.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_63.png)

因此，概率计算如下：
`P(公平硬币 | 观察到正面) = 1 / 3`

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_65.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_66.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_67.png)

---

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_69.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_71.png)

## 示例延伸：观察到两次正面

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_73.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_74.png)

上一节我们介绍了在观察到一次正面的情况下计算条件概率。本节中我们来看看，如果鲍勃抛掷**两次**硬币并都观察到正面，那么他选到公平硬币的概率是多少。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_76.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_77.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_78.png)

我们继续扩展概率树：
1.  如果第一次抛掷公平硬币得到正面，第二次抛掷可能是正面或反面。
2.  如果第一次抛掷两面都是正面的硬币得到正面，第二次抛掷仍然是正面。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_80.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_82.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_84.png)

现在，我们已知观察到的结果是**两次正面**。因此，所有包含反面的分支（例如，公平硬币在第二次抛掷出现反面）都不在考虑范围内。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_86.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_87.png)

在剩余的样本空间中，总共有五种可能得到两次正面：
1.  选择公平硬币，第一次正面，第二次正面。
2.  选择两面都是正面的硬币，第一次正面，第二次正面（情况A）。
3.  选择两面都是正面的硬币，第一次正面，第二次正面（情况B）。
4.  选择两面都是正面的硬币，第一次正面，第二次正面（情况C）。
5.  选择两面都是正面的硬币，第一次正面，第二次正面（情况D）。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_89.png)

在这五种可能中，只有第一种情况符合“选到公平硬币”的条件。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_90.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_91.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_92.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_94.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_96.png)

因此，概率计算如下：
`P(公平硬币 | 观察到两次正面) = 1 / 5`

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_98.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_100.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_102.png)

---

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_104.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_105.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_107.png)

## 示例二：三枚硬币与有偏硬币

现在让我们看一个更复杂的例子。假设鲍勃从三枚硬币中选择一枚：其中两枚是**公平硬币**，一枚是**有偏硬币**。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_109.png)

这枚有偏硬币被设计为抛出正面的概率是 `2/3`，抛出反面的概率是 `1/3`。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_110.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_111.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_112.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_113.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_114.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_115.png)

我们的问题是：**在鲍勃抛掷一次硬币并观察到正面的条件下，他选到公平硬币的概率是多少？**

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_117.png)

我们再次使用概率树。但这里有一个关键点：公平硬币的结果（正/反）概率相等，而有偏硬币的结果概率不相等。为了在同一个样本空间中公平地比较和计数，我们需要找到一个**共同的分母**。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_118.png)

公平硬币有两种等可能结果，有偏硬币有三种可能结果（但概率权重不同）。为了平衡，我们将每个结果“拆分”以确保每条路径的权重一致。最小公倍数是6。
*   对于公平硬币：我们将“正面”拆分为3条等价的路径，将“反面”也拆分为3条等价的路径。
*   对于有偏硬币：根据其 `2/3` 对 `1/3` 的概率，我们将“正面”拆分为2条路径，将“反面”拆分为1条路径。

经过这样的调整，每枚硬币在树状图中都对应6条等可能的基本结果路径。

现在，我们已知观察到的结果是正面。因此，所有导致反面的分支都不在考虑范围内。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_120.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_121.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_122.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_123.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_124.png)

在剩余的样本空间中，总共有10条可能得到正面的路径：
*   来自第一枚公平硬币：3条路径。
*   来自第二枚公平硬币：3条路径。
*   来自有偏硬币：2条路径。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_126.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_128.png)

在这10条路径中，有6条（来自两枚公平硬币）符合“选到公平硬币”的条件。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_130.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_131.png)

因此，概率计算如下：
`P(公平硬币 | 观察到正面) = 6 / 10 = 3 / 5`

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_132.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_133.png)

---

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_135.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_136.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_137.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_138.png)

## 总结

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_139.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_141.png)

本节课中我们一起学习了**条件概率**的计算方法。我们通过构建**概率树**来枚举所有可能的结果，并在已知某个事件（条件）发生的情况下，通过**计数**满足条件的结果总数以及其中符合目标事件的结果数，来求得条件概率。

核心步骤可以总结为：
1.  列出所有可能的结果（样本空间）。
2.  根据已知条件，排除不满足条件的结果。
3.  在剩余的结果中，计数满足目标事件的结果数量。
4.  计算概率：`P(目标事件 | 已知条件) = (满足条件且满足目标的结果数) / (满足条件的结果总数)`。

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_143.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_144.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_145.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_146.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_147.png)

![](img/3e26cb07a53b55b17eed9b58ef52f8dc_148.png)

这种方法直观且强大，是理解更复杂概率问题的基础。