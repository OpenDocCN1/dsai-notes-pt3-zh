# 课程6：统计推断 - P6：贝叶斯规则 🧮

![](img/aa1aee68378eed9c9328c7cc054ae49a_0.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_2.png)

在本节课中，我们将要学习条件概率中最著名的应用之一：**贝叶斯规则**。我们将通过诊断测试的例子，理解如何利用该规则“反转”条件概率，并学习如何计算阳性预测值、阴性预测值以及诊断似然比等核心概念。

![](img/aa1aee68378eed9c9328c7cc054ae49a_4.png)

---

![](img/aa1aee68378eed9c9328c7cc054ae49a_6.png)

## 贝叶斯规则简介

![](img/aa1aee68378eed9c9328c7cc054ae49a_7.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_8.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_9.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_10.png)

贝叶斯规则以长老会牧师托马斯·贝叶斯命名，其著作在其去世后才得以发表。

贝叶斯规则允许我们交换条件概率中条件集与目标事件集的位置。例如，当我们想求 **P(B|A)**（在A发生的条件下B发生的概率），但已知或容易计算的是 **P(A|B)** 时，贝叶斯规则提供了解决方案。

![](img/aa1aee68378eed9c9328c7cc054ae49a_12.png)

**公式**：
`P(B|A) = [P(A|B) * P(B)] / P(A)`

![](img/aa1aee68378eed9c9328c7cc054ae49a_13.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_14.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_15.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_16.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_17.png)

其中，`P(A)` 是事件A的边际概率（即A在所有情况下的总概率）。这在诊断测试等场景中非常有用。

![](img/aa1aee68378eed9c9328c7cc054ae49a_19.png)

---

![](img/aa1aee68378eed9c9328c7cc054ae49a_20.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_22.png)

## 诊断测试中的条件概率

![](img/aa1aee68378eed9c9328c7cc054ae49a_24.png)

上一节我们介绍了贝叶斯规则的基本形式，本节中我们来看看它在诊断测试这一重要领域的应用。

让我们定义以下事件：
*   `+` 和 `-`：分别表示检测结果为**阳性**和**阴性**。
*   `D` 和 `D^c`：分别表示受试者**患有**疾病和**未患有**疾病。

![](img/aa1aee68378eed9c9328c7cc054ae49a_26.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_27.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_28.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_29.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_30.png)

以下是评估诊断测试质量的两个关键指标：

![](img/aa1aee68378eed9c9328c7cc054ae49a_32.png)

**灵敏度**：指实际患病者检测结果为阳性的概率，即 **P(+|D)**。一个好的测试需要高灵敏度。

![](img/aa1aee68378eed9c9328c7cc054ae49a_34.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_35.png)

**特异性**：指实际未患病者检测结果为阴性的概率，即 **P(-|D^c)**。一个好的测试同样需要高特异性。

![](img/aa1aee68378eed9c9328c7cc054ae49a_37.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_38.png)

在开发诊断测试时，这些指标在概念上是可获得的。例如，对于HIV血液检测，可以对已知患病和已知未患病的人群样本进行测试来估计这些值。

![](img/aa1aee68378eed9c9328c7cc054ae49a_40.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_41.png)

对于接受检测的个人，最关心的两个指标是：

*   **阳性预测值**：在检测结果为阳性的条件下，实际患病的概率，即 **P(D|+)**。
*   **阴性预测值**：在检测结果为阴性的条件下，实际未患病的概率，即 **P(D^c|-)**。

![](img/aa1aee68378eed9c9328c7cc054ae49a_43.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_44.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_45.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_46.png)

在没有检测信息时，一个人患病的概率称为疾病的**患病率**，即 **P(D)**。

![](img/aa1aee68378eed9c9328c7cc054ae49a_48.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_50.png)

---

![](img/aa1aee68378eed9c9328c7cc054ae49a_52.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_53.png)

## 计算示例：HIV检测

![](img/aa1aee68378eed9c9328c7cc054ae49a_55.png)

现在，我们通过一个具体的HIV检测例子，来应用贝叶斯规则进行计算。

![](img/aa1aee68378eed9c9328c7cc054ae49a_56.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_57.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_58.png)

假设一项研究报告某种HIV抗体检测的**灵敏度为99.7%**，**特异性为98.5%**。同时，假设受试者来自一个HIV**患病率为0.1%**的人群。如果某人检测结果为阳性，其阳性预测值是多少？

**数学上，我们要求的是 P(D|+)**。

![](img/aa1aee68378eed9c9328c7cc054ae49a_60.png)

根据贝叶斯规则：
`P(D|+) = [P(+|D) * P(D)] / P(+)`

![](img/aa1aee68378eed9c9328c7cc054ae49a_61.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_62.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_63.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_64.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_65.png)

其中，分母 `P(+)` 可以进一步分解为：
`P(+) = P(+|D)*P(D) + P(+|D^c)*P(D^c)`

![](img/aa1aee68378eed9c9328c7cc054ae49a_66.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_68.png)

请注意：
*   `P(+|D)` 就是灵敏度 (0.997)。
*   `P(D)` 就是患病率 (0.001)。
*   `P(+|D^c)` 等于 1 - 特异性 (1 - 0.985 = 0.015)。
*   `P(D^c)` 等于 1 - 患病率 (1 - 0.001 = 0.999)。

![](img/aa1aee68378eed9c9328c7cc054ae49a_70.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_72.png)

将数字代入公式计算，得到 **P(D|+) ≈ 0.06，即6%**。

![](img/aa1aee68378eed9c9328c7cc054ae49a_74.png)

这意味着，在此人群中，一次阳性检测结果仅提示该受试者有**6%的概率**真正感染HIV。阳性预测值较低，主要原因是疾病的患病率很低。

![](img/aa1aee68378eed9c9328c7cc054ae49a_76.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_77.png)

然而，如果在咨询过程中，得知该受试者是静脉吸毒者，并经常与HIV感染者发生性关系，那么适用于他的“患病率”会高得多，其阳性预测值也会相应大幅提高。

![](img/aa1aee68378eed9c9328c7cc054ae49a_79.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_81.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_82.png)

---

![](img/aa1aee68378eed9c9328c7cc054ae49a_84.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_85.png)

## 诊断似然比

上一节的计算揭示了阳性预测值依赖于患病率。本节中，我们将从中分离出代表检测结果本身提供的客观证据强度的部分，即**诊断似然比**。

![](img/aa1aee68378eed9c9328c7cc054ae49a_87.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_88.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_89.png)

以下是阳性预测值的公式（来自贝叶斯规则）：
`P(D|+) = [sens * prev] / [sens * prev + (1 - spec) * (1 - prev)]`

![](img/aa1aee68378eed9c9328c7cc054ae49a_91.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_92.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_93.png)

类似地，可以得到 **P(D^c|+)** 的公式。注意到两个公式的分母相同。

![](img/aa1aee68378eed9c9328c7cc054ae49a_95.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_97.png)

如果将 `P(D|+)` 与 `P(D^c|+)` 相除，我们得到：
`[P(D|+)] / [P(D^c|+)] = [sens / (1 - spec)] * [prev / (1 - prev)]`

![](img/aa1aee68378eed9c9328c7cc054ae49a_99.png)

一个概率除以其补概率，得到的是**比值**。
*   等式左边是获得阳性结果后的**后验比值**。
*   等式右边第一个因子 `sens / (1 - spec)` 是**阳性结果的诊断似然比**。
*   等式右边第二个因子 `prev / (1 - prev)` 是获得检测结果前的**先验比值**。

**核心公式**：
`后验比值 = 诊断似然比 * 先验比值`

![](img/aa1aee68378eed9c9328c7cc054ae49a_101.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_102.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_103.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_104.png)

诊断似然比（DLR+）表示，在获得阳性检测结果后，**支持“患病”假设相对于“未患病”假设的证据强度放大了多少倍**。

---

![](img/aa1aee68378eed9c9328c7cc054ae49a_106.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_107.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_108.png)

### 计算示例

![](img/aa1aee68378eed9c9328c7cc054ae49a_109.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_110.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_111.png)

使用之前的灵敏度(0.997)和特异性(0.985)：
`DLR+ = 0.997 / (1 - 0.985) ≈ 66`

![](img/aa1aee68378eed9c9328c7cc054ae49a_113.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_114.png)

这意味着，无论你的先验比值是多少，在得到阳性结果后，支持患病的证据强度都增强了**66倍**。

![](img/aa1aee68378eed9c9328c7cc054ae49a_115.png)

如果先验概率本身极低（如患病率为0.1%时，先验比值=0.001/0.999≈0.001），即使乘以66，后验比值仍然较小（≈0.066），对应的后验概率约为6.2%，这与我们之前的直接计算结果一致。

![](img/aa1aee68378eed9c9328c7cc054ae49a_117.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_118.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_119.png)

对于阴性结果，我们使用**阴性结果的诊断似然比**：
`DLR- = (1 - sens) / spec = (1 - 0.997) / 0.985 ≈ 0.003`

![](img/aa1aee68378eed9c9328c7cc054ae49a_121.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_122.png)

这意味着，在得到阴性结果后，支持患病的证据强度减弱到先验水平的**0.3%**。

![](img/aa1aee68378eed9c9328c7cc054ae49a_124.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_125.png)

---

## 总结

![](img/aa1aee68378eed9c9328c7cc054ae49a_127.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_128.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_129.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_130.png)

本节课中我们一起学习了：
1.  **贝叶斯规则**：一个用于“反转”条件概率的强大工具，其公式为 `P(B|A) = [P(A|B) * P(B)] / P(A)`。
2.  **在诊断测试中的应用**：我们定义了**灵敏度**、**特异性**、**阳性/阴性预测值**和**患病率**等关键概念。
3.  **计算实践**：通过一个HIV检测的例子，我们演示了如何利用贝叶斯规则计算阳性预测值，并发现即使测试本身很准确，在低患病率人群中，阳性结果的预测价值也可能很低。
4.  **诊断似然比**：我们学习了如何将先验信息（患病率）与检测结果提供的客观证据分离开来。诊断似然比（DLR+ 和 DLR-）是一个不依赖于患病率的指标，它量化了检测结果对支持或反对患病假设的证据强度的影响倍数，遵循 `后验比值 = 诊断似然比 * 先验比值` 的关系。