# 课程6：《统计推断》｜P2：概率简介 🎲

![](img/c5ddf585786be6eebe896dff61cb25ef_0.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_2.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_3.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_4.png)

在本节课中，我们将学习概率的基本概念。概率是统计推断和数据科学的基础，它帮助我们理解和量化随机现象。我们将从最基础的定义和规则开始，确保内容简单易懂，适合初学者。

![](img/c5ddf585786be6eebe896dff61cb25ef_6.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_8.png)

---

![](img/c5ddf585786be6eebe896dff61cb25ef_10.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_11.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_12.png)

## 概率是什么？

![](img/c5ddf585786be6eebe896dff61cb25ef_14.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_15.png)

给定一个随机实验，例如掷骰子，概率是一种度量，用于总结随机性的总体特征。

![](img/c5ddf585786be6eebe896dff61cb25ef_17.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_18.png)

这里需要强调“总体”这个词。在掷骰子的情境中，概率被视为骰子固有的属性，而不是基于有限次投掷结果的函数。因此，概率不是我们已有数据中的某个值，而是一个存在于总体中的概念性事物，我们希望通过数据来估计它。

![](img/c5ddf585786be6eebe896dff61cb25ef_19.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_20.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_22.png)

---

![](img/c5ddf585786be6eebe896dff61cb25ef_24.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_25.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_26.png)

## 概率的规则（概率演算）

![](img/c5ddf585786be6eebe896dff61cb25ef_28.png)

为了让概率有意义，它必须遵循一些特定的规则，这被称为概率演算。

![](img/c5ddf585786be6eebe896dff61cb25ef_30.png)

首先，概率作用于实验的所有可能结果集合。例如，掷骰子时，可能的结果是得到一个“1”，或者结果属于集合 {1, 2}，或者结果是偶数 {2, 4, 6}，或者结果是奇数 {1, 3, 5}，等等。

![](img/c5ddf585786be6eebe896dff61cb25ef_32.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_33.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_34.png)

概率是一个函数，它将任何这样的可能结果集合映射到一个介于0和1之间的数字。

以下是概率必须遵循的核心规则：

![](img/c5ddf585786be6eebe896dff61cb25ef_36.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_37.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_38.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_39.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_40.png)

*   **必然事件的概率为1**：掷骰子必定会得到一个数字，所以这个事件的概率是1。
*   **不可能事件的概率为0**：掷骰子不可能什么结果都没有，所以这个事件的概率是0。
*   **互斥事件的加法规则**：任何两个没有共同结果的集合（称为互斥事件），它们至少有一个发生的概率等于各自概率的和。例如，掷骰子得到 {1, 2} 的概率加上得到 {3, 4} 的概率，就等于得到 {1, 2, 3, 4} 的概率。

![](img/c5ddf585786be6eebe896dff61cb25ef_42.png)

俄罗斯数学家柯尔莫哥洛夫发现，这些简单的规则足以推导出所有我们认为概率应该遵循的规则。

![](img/c5ddf585786be6eebe896dff61cb25ef_44.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_45.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_46.png)

---

![](img/c5ddf585786be6eebe896dff61cb25ef_48.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_49.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_50.png)

## 概率的其他重要规则

![](img/c5ddf585786be6eebe896dff61cb25ef_52.png)

上一节我们介绍了概率的基本公理，本节中我们来看看由这些公理推导出的一些常用规则。

![](img/c5ddf585786be6eebe896dff61cb25ef_53.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_54.png)

*   **对立事件的概率**：一个事件发生的概率等于1减去其对立事件发生的概率。例如，掷骰子得到偶数的概率是 `1 - P(得到奇数)`。
*   **事件的包含关系**：如果事件A的发生意味着事件B一定发生（即A是B的子集），那么事件A的概率小于或等于事件B的概率。例如，`P(得到1) ≤ P(得到1或2)`。
*   **任意两个事件的加法规则（通用公式）**：对于任意两个事件A和B，它们至少有一个发生的概率公式为：
    **`P(A ∪ B) = P(A) + P(B) - P(A ∩ B)`**
    这个规则非常重要，因为它适用于所有情况，而不仅仅是互斥事件。公式中减去 `P(A ∩ B)` 是因为在 `P(A) + P(B)` 中，A和B交集部分的概率被重复计算了两次。

---

![](img/c5ddf585786be6eebe896dff61cb25ef_56.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_57.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_58.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_59.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_60.png)

## 一个实际例子：睡眠问题

![](img/c5ddf585786be6eebe896dff61cb25ef_62.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_63.png)

现在，让我们通过一个实际例子来应用通用加法规则。

美国国家睡眠基金会报告称，约3%的美国人口患有睡眠呼吸暂停症。同时，约10%的北美和欧洲人口患有不安腿综合征。

![](img/c5ddf585786be6eebe896dff61cb25ef_65.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_66.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_67.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_68.png)

假设这些百分比来自同一总体，我们能否简单地将这两个概率相加，得出结论说约有13%的人至少患有其中一种睡眠问题？

![](img/c5ddf585786be6eebe896dff61cb25ef_70.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_71.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_73.png)

**答案是否定的。** 因为这两个事件（患睡眠呼吸暂停症和患不安腿综合征）可能同时发生在同一个人身上，它们不是互斥事件。我们认为有一部分人群同时患有这两种疾病。

![](img/c5ddf585786be6eebe896dff61cb25ef_75.png)

具体来说，设事件A为“一个人患有睡眠呼吸暂停症”，事件B为“一个人患有不安腿综合征”。这里的交集 `A ∩ B`（即同时患有两种病）是非空的。因此，如果我们直接将两个概率相加，就会重复计算这部分交集人群的概率。要得到至少患有一种病的概率 `P(A ∪ B)`，我们必须使用通用加法规则：`P(A) + P(B) - P(A ∩ B)`。由于我们不知道 `P(A ∩ B)` 是多少，所以不能简单地说结果是13%。

![](img/c5ddf585786be6eebe896dff61cb25ef_77.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_78.png)

---

![](img/c5ddf585786be6eebe896dff61cb25ef_80.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_82.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_83.png)

## 总结

![](img/c5ddf585786be6eebe896dff61cb25ef_85.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_86.png)

本节课中我们一起学习了概率的基础知识。我们了解到概率是描述随机实验总体特性的度量，并学习了其必须遵循的核心规则（概率演算），包括概率的取值范围、必然与不可能事件、以及互斥事件的加法规则。我们还推导并理解了通用加法公式 **`P(A ∪ B) = P(A) + P(B) - P(A ∩ B)`**，并通过睡眠问题的例子明白了为什么不能随意将概率相加。这些概念是后续学习更复杂统计推断方法的基石。