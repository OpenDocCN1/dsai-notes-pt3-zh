#  062：马尔可夫定理实例分析 📊

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_0.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_2.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_3.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_5.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_7.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_9.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_10.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_11.png)

在本节课中，我们将通过几个具体的例子来学习如何应用马尔可夫定理。上一节我们介绍了马尔可夫定理的证明，本节中我们来看看如何在实际问题中使用它来估计罕见事件的概率上界。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_13.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_14.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_16.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_18.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_19.png)

马尔可夫定理的核心公式是：对于一个非负随机变量 **R** 和任意正数 **a**，有：
**P(R ≥ a) ≤ E[R] / a**

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_21.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_22.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_24.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_25.png)

---

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_27.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_29.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_31.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_33.png)

## 实例一：随机体重分析 🏋️

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_35.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_37.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_39.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_41.png)

假设随机变量 **R** 表示一个人的体重（单位：磅）。已知体重的期望值 **E[R] = 100**。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_42.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_44.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_46.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_47.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_48.png)

我们希望估计体重超过或等于 200 磅的概率。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_50.png)

根据马尔可夫定理，我们可以直接计算其上界：
**P(R ≥ 200) ≤ E[R] / 200 = 100 / 200 = 0.5**

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_51.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_52.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_54.png)

这意味着，体重超过200磅的概率**至多**为50%。

我们也可以使用马尔可夫定理的推论来理解这个结果。因为 200 = 2 * E[R]，所以常数 **c = 2**。根据推论 **P(R ≥ c * E[R]) ≤ 1/c**，我们同样得到：
**P(R ≥ 2 * E[R]) ≤ 1/2 = 0.5**

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_56.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_57.png)

---

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_58.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_59.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_60.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_61.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_62.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_63.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_64.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_65.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_66.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_67.png)

## 实例二：指数分布与到达时间 ⏳

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_69.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_70.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_72.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_74.png)

在某些场景中，数据服从指数分布，例如银行柜台的顾客到达间隔时间。这类数据通常具有**右偏**特性：大量值集中在较小的区间，但偶尔会出现非常大的值（即罕见的长等待时间）。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_76.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_78.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_80.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_82.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_84.png)

假设随机变量 **X** 服从参数 **λ = 1** 的指数分布，即 **X ~ Exp(1)**。对于指数分布，其期望值 **E[X] = 1/λ = 1**。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_86.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_87.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_88.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_89.png)

现在，我们想估计等待时间超过某个阈值 **a** 的概率。根据马尔可夫定理：
**P(X ≥ a) ≤ E[X] / a = 1 / a**

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_91.png)

例如，如果我们想知道等待时间超过15分钟的概率，其**上界**就是 **1/15**。这为我们评估“极端长等待”这种罕见事件的风险提供了一个快速的量化工具。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_93.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_94.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_95.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_96.png)

---

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_97.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_98.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_99.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_101.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_102.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_104.png)

## 实例三：均匀分布分析 📏

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_106.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_108.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_110.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_112.png)

假设随机变量 **X** 服从区间 **[-4, 4]** 上的均匀分布，即 **X ~ Uniform(-4, 4)**。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_114.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_116.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_117.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_118.png)

我们希望估计 **X ≥ 3** 的概率。注意，此时 **X** 可能取负值，我们需要应用马尔可夫定理的绝对值形式：
**P(|X| ≥ a) ≤ E[|X|] / a**

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_120.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_122.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_124.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_126.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_128.png)

首先计算 **E[|X|]**。由于分布对称，我们只需计算在 **[0, 4]** 区间上的期望，结果为 **2**。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_130.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_131.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_133.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_134.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_136.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_138.png)

因此，**P(|X| ≥ 3) ≤ 2 / 3**。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_140.png)

由于事件 **{X ≥ 3}** 是事件 **{|X| ≥ 3}** 的一部分（并且概率为其一半，因为分布对称），我们可以得到：
**P(X ≥ 3) = (1/2) * P(|X| ≥ 3) ≤ (1/2) * (2/3) = 1/3**

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_142.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_143.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_144.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_145.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_146.png)

所以，**X** 大于等于3的概率**至多**为 **1/3**。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_148.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_150.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_152.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_154.png)

---

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_155.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_157.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_159.png)

## 推论与实例四：学生成绩分析 📝

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_160.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_161.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_162.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_164.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_166.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_168.png)

马尔可夫定理还有一个有用的推论：如果随机变量 **R** 存在一个上界 **u**（即 **R ≤ u**），那么对于任意 **x < u**，有：
**P(R ≤ x) ≤ (u - E[R]) / (u - x)**

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_170.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_171.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_173.png)

这个推论允许我们估计随机变量取值很小的概率。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_175.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_176.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_177.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_179.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_181.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_182.png)

让我们看一个例子：设 **R** 表示一个随机学生的考试成绩，满分 **u = 100**。已知班级平均分 **E[R] = 75**。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_184.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_185.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_186.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_188.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_190.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_192.png)

我们想估计一个学生成绩低于或等于50分的概率。根据上述推论：
**P(R ≤ 50) ≤ (100 - 75) / (100 - 50) = 25 / 50 = 0.5**

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_194.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_196.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_198.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_200.png)

这意味着，成绩低于50分的概率**至多**为50%。这个上界帮助我们量化了出现“极低分”这种罕见事件的风险。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_202.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_204.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_206.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_208.png)

---

## 总结

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_210.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_211.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_212.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_213.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_214.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_215.png)

本节课中，我们一起学习了如何应用马尔可夫定理及其推论来分析不同场景下的罕见事件概率上界。

以下是本节课的核心要点回顾：
*   **核心公式**：对于非负随机变量 **R**，**P(R ≥ a) ≤ E[R] / a**。
*   **应用场景**：该定理特别适用于处理具有**偏态分布**（如指数分布）的数据，其中存在少数极端大值。
*   **主要作用**：它为估计“随机变量远超其平均值”这类事件的概率提供了一个简单而保守的**上界**，是风险评估和决策分析中的一个有用工具。
*   **灵活变体**：通过取绝对值或利用变量上界，我们可以将定理应用于更广泛的随机变量。

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_217.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_218.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_219.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_220.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_221.png)

![](img/194b4ffcaa8ac2f6d3c85bff1014aabd_222.png)

通过体重、等待时间、均匀分布变量和考试成绩这四个例子，我们看到了马尔可夫定理如何将抽象的数学公式转化为解决实际概率估计问题的有力手段。