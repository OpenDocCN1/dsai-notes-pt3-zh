# 课程03：集合论在医学测试中的应用 🧪

在本节课中，我们将学习如何运用集合论的基本概念来分析一个现实世界的问题：医学测试的准确性。我们将通过定义不同的集合，来理解真阳性、假阳性、真阴性、假阴性等核心概念及其计算方式。

![](img/cb459d0e93601f77706ebe0dca6cbab8_1.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_3.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_5.png)

上一节我们介绍了集合论的基本运算，本节中我们来看看如何将这些抽象概念应用于具体的医学测试场景。

![](img/cb459d0e93601f77706ebe0dca6cbab8_7.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_9.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_11.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_12.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_14.png)

## 定义基本集合

![](img/cb459d0e93601f77706ebe0dca6cbab8_16.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_17.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_19.png)

首先，我们设定一个临床试验的场景。令集合 **X** 代表所有参与某项疾病（我们称之为“非常糟糕综合征”，VBS）检测试验的人。

我们可以将 **X** 划分为两个互斥的集合：
*   **S**： 真正患有 VBS 的人的集合。
*   **H**： 未患有 VBS（健康）的人的集合。

![](img/cb459d0e93601f77706ebe0dca6cbab8_21.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_23.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_25.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_27.png)

根据定义，我们有：
*   **X = S ∪ H** （所有人要么患病，要么健康）
*   **S ∩ H = ∅** （没有人既患病又健康）

![](img/cb459d0e93601f77706ebe0dca6cbab8_29.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_30.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_32.png)

## 定义测试结果集合

![](img/cb459d0e93601f77706ebe0dca6cbab8_34.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_36.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_38.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_40.png)

医学测试的目的是判断一个人属于 **S** 还是 **H**。测试会给出“阳性”或“阴性”的结果。我们定义：
*   **P**： 检测结果为阳性（即测试显示患有 VBS）的人的集合。
*   **N**： 检测结果为阴性（即测试显示未患有 VBS）的人的集合。

![](img/cb459d0e93601f77706ebe0dca6cbab8_42.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_44.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_46.png)

同样，对于测试结果，我们有：
*   **X = P ∪ N** （每个人的测试结果非阳即阴）
*   **P ∩ N = ∅** （没有人同时得到阳性和阴性结果）

![](img/cb459d0e93601f77706ebe0dca6cbab8_48.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_50.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_52.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_53.png)

在理想情况下，测试是完美的：**S = P** 且 **H = N**。但现实中，测试总存在误差。

![](img/cb459d0e93601f77706ebe0dca6cbab8_55.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_57.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_58.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_60.png)

## 分析四种关键交集

![](img/cb459d0e93601f77706ebe0dca6cbab8_62.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_64.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_65.png)

为了量化测试的误差，我们需要分析以下四个关键的交集。以下是这四种情况的含义：

![](img/cb459d0e93601f77706ebe0dca6cbab8_66.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_67.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_69.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_71.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_72.png)

1.  **S ∩ P**： **真阳性**。此人确实患病，且测试正确识别为阳性。
2.  **H ∩ N**： **真阴性**。此人确实健康，且测试正确识别为阴性。
3.  **S ∩ N**： **假阴性**。此人确实患病，但测试错误地给出了阴性结果。
4.  **H ∩ P**： **假阳性**。此人确实健康，但测试错误地给出了阳性结果。

![](img/cb459d0e93601f77706ebe0dca6cbab8_74.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_75.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_76.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_77.png)

显然，我们希望真阳性和真阴性的集合尽可能大，而假阳性和假阴性的集合尽可能小。

## 计算关键比率

![](img/cb459d0e93601f77706ebe0dca6cbab8_79.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_81.png)

通过比较这些集合的大小（即集合的**基数**），我们可以计算出评估测试性能的关键指标。

![](img/cb459d0e93601f77706ebe0dca6cbab8_82.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_84.png)

以下是几个基础比例：
*   **|S| / |X|**： 研究人群中真实患病者的**比例**。
*   **|H| / |X|**： 研究人群中真实健康者的**比例**。这两个比例之和为1。

![](img/cb459d0e93601f77706ebe0dca6cbab8_86.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_88.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_89.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_91.png)

以下是评估测试准确性的核心比率：

![](img/cb459d0e93601f77706ebe0dca6cbab8_93.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_95.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_97.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_99.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_101.png)

1.  **真阳性率**： 在所有真实患病者中，被测试正确识别出来的比例。
    *   **公式**： `TPR = |S ∩ P| / |S|`
    *   我们希望这个值接近1。

![](img/cb459d0e93601f77706ebe0dca6cbab8_103.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_105.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_106.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_108.png)

2.  **假阳性率**： 在所有真实健康者中，被测试错误判为阳性的比例。
    *   **公式**： `FPR = |H ∩ P| / |H|`
    *   我们希望这个值接近0。

![](img/cb459d0e93601f77706ebe0dca6cbab8_110.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_112.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_113.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_115.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_117.png)

3.  **假阴性率**： 在所有真实患病者中，被测试错误判为阴性的比例。
    *   **公式**： `FNR = |S ∩ N| / |S|`
    *   我们希望这个值接近0。

![](img/cb459d0e93601f77706ebe0dca6cbab8_118.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_120.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_122.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_124.png)

4.  **真阴性率**： 在所有真实健康者中，被测试正确识别出来的比例。
    *   **公式**： `TNR = |H ∩ N| / |H|`
    *   我们希望这个值接近1。

![](img/cb459d0e93601f77706ebe0dca6cbab8_126.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_127.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_129.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_130.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_132.png)

## 总结与应用延伸

![](img/cb459d0e93601f77706ebe0dca6cbab8_134.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_135.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_136.png)

本节课中我们一起学习了如何用集合论框架分析医学测试。一个完美的测试应具备**真阳性率和真阴性率接近1**，同时**假阳性率和假阴性率接近0**的特性。虽然这在现实中难以实现，但这些概念为我们量化比较不同测试方法的优劣提供了精确的工具。

![](img/cb459d0e93601f77706ebe0dca6cbab8_138.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_139.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_140.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_141.png)

更重要的是，这套“真实情况 vs. 预测结果”的分析框架并不仅限于医学领域。在未来的机器学习（尤其是监督学习）、商业分析等场景中，只要存在一个真实的分类（如垃圾邮件/非垃圾邮件、欺诈交易/正常交易）和一个用于预测的模型或测试，我们都可以沿用**真阳性、假阳性、真阳性率、假阳性率**等完全相同的概念和词汇来评估系统的性能。