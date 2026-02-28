# 大规模数据科学：8：重抽样注意事项 📊

![](img/53e74e430ec38dd3cecb474bb1c4ec68_0.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_2.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_4.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_5.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_7.png)

在本节课中，我们将探讨重抽样方法（特别是置换检验和自助法）的注意事项。我们将理解为何需要区分显著性检验和置信区间估计，并了解自助法在特定情况下的局限性。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_9.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_10.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_11.png)

---

![](img/53e74e430ec38dd3cecb474bb1c4ec68_13.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_15.png)

上一节我们介绍了置换检验和自助法。本节中，我们来看看使用这些方法时需要注意的关键事项。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_17.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_18.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_19.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_20.png)

首先，一个核心问题是：为什么不能直接用置信区间来判断显著性？毕竟，如果置信区间不包含零值，似乎就表明差异显著。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_21.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_23.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_24.png)

原因是，计算置信区间时，我们**已经假设**所观察到的差异（例如均值差）是真实存在的。而显著性检验（如置换检验）的起点是**零假设**，即假设两组数据没有差异。两者逻辑起点不同。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_25.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_27.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_29.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_30.png)

以下是一个直观的例子来说明其重要性：
假设我们只有两个数据值：一个来自治疗组（生存36天），一个来自安慰剂组（生存27天）。两组均值差为 `9`。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_32.png)

*   **使用自助法计算95%置信区间**：由于样本极小，自助重抽样产生的差异值几乎总是 `9` 或 `-9`。因此，置信区间会非常窄，例如 `[9, 9]`，这似乎强烈表明差异显著。
*   **使用置换检验计算P值**：当我们随机打乱标签多次，大约一半的情况差异为 `9`，另一半为 `-9`。得到的P值约为 `0.5`，远高于通常的显著性阈值（如0.05），表明**观察到的差异并不显著**。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_33.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_34.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_35.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_36.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_38.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_40.png)

这个例子清晰地表明：
> **正确的流程是：首先基于零假设使用置换检验判断显著性；如果结果显著，再使用自助法估计置信区间。**

![](img/53e74e430ec38dd3cecb474bb1c4ec68_42.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_44.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_45.png)

---

![](img/53e74e430ec38dd3cecb474bb1c4ec68_46.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_48.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_49.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_51.png)

接下来，我们讨论自助法的一些注意事项和局限性。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_53.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_54.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_56.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_57.png)

自助法非常稳健，比许多经典方法假设更少。但在某些情况下需要谨慎使用。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_59.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_61.png)

以下是自助法的主要注意事项：

![](img/53e74e430ec38dd3cecb474bb1c4ec68_63.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_64.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_65.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_66.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_67.png)

1.  **小样本可能低估变异性**：对于非常小的样本，自助法可能无法充分捕捉总体变异性，从而导致置信区间过窄。不过，在大数据场景下，这通常不是主要问题。
2.  **不适用于估计极值**：自助法**不能**可靠地估计总体最小值或最大值等统计量。原因是极值对异常点极其敏感。自助抽样是**有放回**的，可能漏掉那个决定最大值的单一异常点，从而导致对极值分布的估计有偏。
3.  **需保持原始数据结构**：进行重抽样时，必须模拟原始实验的数据生成过程。例如，在比较两组数据时，应分别对每一组进行自助抽样，而不是混合所有数据后再抽样。如果数据结构更复杂（如分层抽样），抽样设计也需要在重抽样中复现。
4.  **数据需满足独立性假设**：标准自助法要求数据点是独立同分布的。如果数据存在自相关（如时间序列数据），直接应用自助法无效。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_69.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_70.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_72.png)

对于非独立数据（如时间序列），有时可以采用一些创造性技巧。例如，可以将一个长序列分割成多个**不重叠的区块**，将每个区块视为一个独立的“观测”，在区块级别计算统计量，然后对这些区块进行重抽样。这种方法被称为“区块自助法”。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_74.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_75.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_76.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_78.png)

---

![](img/53e74e430ec38dd3cecb474bb1c4ec68_80.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_81.png)

最后，我们必须认识到，任何统计方法，包括重抽样，都无法替代对数据本身的理解。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_83.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_84.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_86.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_87.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_88.png)

正如统计学家Nate Silver所言：“**数字无法为自己说话。**” 重抽样是一种强大的计算工具，但它不能消除数据中固有的偏差，也无法弥补拙劣的实验设计。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_90.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_91.png)

无论使用重抽样方法还是经典方法，理解**数据的来源、采集过程以及背后的实验设计**都至关重要。统计学的“帽子”要求我们始终对数据的背景保持敏感。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_93.png)

---

![](img/53e74e430ec38dd3cecb474bb1c4ec68_94.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_95.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_96.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_97.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_99.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_100.png)

**本节课总结**

![](img/53e74e430ec38dd3cecb474bb1c4ec68_102.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_103.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_104.png)

本节课我们一起学习了重抽样方法的注意事项：
1.  明确了**显著性检验（置换检验）** 和**置信区间估计（自助法）** 需分步进行，逻辑起点不同。
2.  探讨了自助法的局限性，包括对小样本、极值估计的谨慎态度，以及必须**保持数据结构**和**数据独立性**的要求。
3.  强调了无论方法多么强大，对**数据背景和生成过程的理解**始终是做出正确统计推断的基石。