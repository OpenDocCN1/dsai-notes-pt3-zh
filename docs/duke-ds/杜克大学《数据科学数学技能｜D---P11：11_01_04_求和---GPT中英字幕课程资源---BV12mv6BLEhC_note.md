# 课程11：求和符号与均值方差 📊

![](img/f2405cffbd8c303ade56ba446063a3cf_0.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_2.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_3.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_5.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_7.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_8.png)

在本节课中，我们将完成关于求和符号的系列讲解，并将其应用于统计学中的核心概念：均值与方差。我们将学习如何使用求和符号简洁地表达这些概念，并理解它们如何量化数据集的“中心”和“离散”程度。

![](img/f2405cffbd8c303ade56ba446063a3cf_10.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_11.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_13.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_15.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_17.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_19.png)

## 均值与求和符号

![](img/f2405cffbd8c303ade56ba446063a3cf_21.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_23.png)

上一节我们介绍了求和符号的基本用法。本节中，我们来看看如何用它来定义数据的均值。

![](img/f2405cffbd8c303ade56ba446063a3cf_25.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_26.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_28.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_30.png)

均值，即平均值，是数据集中所有数值之和除以数值的个数。假设我们有一个包含 `n` 个实数的集合 `X`，其元素为 `x1, x2, ..., xn`。

![](img/f2405cffbd8c303ade56ba446063a3cf_31.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_32.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_34.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_36.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_38.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_39.png)

那么，集合 `X` 的均值 `μ_x` 可以用求和符号表示为：

![](img/f2405cffbd8c303ade56ba446063a3cf_41.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_43.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_44.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_46.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_48.png)

**公式：**
`μ_x = (1/n) * Σ_{i=1}^{n} x_i`

![](img/f2405cffbd8c303ade56ba446063a3cf_50.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_51.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_53.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_55.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_57.png)

以下是计算均值的步骤：
1.  使用求和符号 `Σ_{i=1}^{n} x_i` 将所有元素 `x1` 到 `xn` 相加。
2.  将总和除以元素个数 `n`。

![](img/f2405cffbd8c303ade56ba446063a3cf_59.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_61.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_63.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_65.png)

例如，对于集合 `Z = {1, 5, 12}`，其均值为 `(1+5+12)/3 = 6`。

![](img/f2405cffbd8c303ade56ba446063a3cf_67.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_68.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_69.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_71.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_72.png)

在求和符号 `Σ_{i=1}^{n} x_i` 中，索引 `i` 是一个“哑变量”，它仅用于从 1 计数到 `n`。而 `n` 本身是一个变量，它决定了求和的范围。

![](img/f2405cffbd8c303ade56ba446063a3cf_74.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_75.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_77.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_78.png)

## 数据中心化

![](img/f2405cffbd8c303ade56ba446063a3cf_80.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_82.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_83.png)

在深入方差之前，我们先了解一个在数据科学中常用的技巧：数据中心化。

![](img/f2405cffbd8c303ade56ba446063a3cf_85.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_87.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_89.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_91.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_93.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_95.png)

数据中心化是指将数据集中的每个数值减去该数据集的均值，从而生成一个均值为零的新数据集。这样做有很多好处，例如可以简化后续的统计分析（在线性回归等模型中会经常用到）。

![](img/f2405cffbd8c303ade56ba446063a3cf_97.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_98.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_100.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_102.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_104.png)

其操作非常简单：
1.  计算原数据集的均值 `μ`。
2.  将原数据集中的每个数值 `x_i` 减去均值 `μ`，得到新的数值 `x'_i = x_i - μ`。

![](img/f2405cffbd8c303ade56ba446063a3cf_105.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_107.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_109.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_110.png)

新数据集的均值必然为零。从几何上看，这相当于将数轴上的数据整体平移，使得均值点与零点重合。

![](img/f2405cffbd8c303ade56ba446063a3cf_112.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_113.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_115.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_117.png)

## 方差与标准差

![](img/f2405cffbd8c303ade56ba446063a3cf_119.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_120.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_121.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_123.png)

均值描述了数据的“中心”位置，但仅凭均值无法区分数据分布的“离散”程度。例如，集合 `Z = {1, 5, 12}` 和 `W = {5, 6, 7}` 的均值都是 6，但 `Z` 中的数据显然比 `W` 中的数据更分散。

![](img/f2405cffbd8c303ade56ba446063a3cf_124.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_126.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_127.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_129.png)

为了量化这种“离散”程度，我们引入方差的概念。

![](img/f2405cffbd8c303ade56ba446063a3cf_131.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_133.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_135.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_137.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_139.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_140.png)

对于包含 `n` 个元素的集合 `X`，其方差 `σ_x²` 定义为每个元素与均值之差的平方的平均值。

![](img/f2405cffbd8c303ade56ba446063a3cf_142.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_143.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_144.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_146.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_148.png)

**公式：**
`σ_x² = (1/n) * Σ_{i=1}^{n} (x_i - μ_x)²`

![](img/f2405cffbd8c303ade56ba446063a3cf_150.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_152.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_154.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_156.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_158.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_160.png)

以下是理解方差的要点：
*   `(x_i - μ_x)` 衡量了每个数据点偏离均值的距离。
*   我们对其**平方**，是为了消除正负偏差相互抵消的影响，只关心偏差的大小。
*   最后对所有平方偏差求**平均**（除以 `n`），就得到了方差。

![](img/f2405cffbd8c303ade56ba446063a3cf_162.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_164.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_166.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_168.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_170.png)

方差的平方根称为**标准差**，记作 `σ_x`。

![](img/f2405cffbd8c303ade56ba446063a3cf_172.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_173.png)

**公式：**
`σ_x = √(σ_x²)`

![](img/f2405cffbd8c303ade56ba446063a3cf_174.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_175.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_176.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_177.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_179.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_180.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_182.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_184.png)

标准差与原始数据具有相同的量纲，更便于解释。

![](img/f2405cffbd8c303ade56ba446063a3cf_186.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_187.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_189.png)

让我们计算之前两个例子中的方差：
*   对于 `W = {5, 6, 7}`，均值 `μ_w = 6`。
    *   方差 `σ_w² = [(5-6)² + (6-6)² + (7-6)²] / 3 = (1+0+1)/3 = 2/3`
    *   标准差 `σ_w = √(2/3)`
*   对于 `Z = {1, 5, 12}`，均值 `μ_z = 6`。
    *   方差 `σ_z² = [(1-6)² + (5-6)² + (12-6)²] / 3 = (25+1+36)/3 = 62/3`
    *   标准差 `σ_z = √(62/3)`

![](img/f2405cffbd8c303ade56ba446063a3cf_191.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_193.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_195.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_197.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_199.png)

正如我们所料，`Z` 的方差（和标准差）远大于 `W` 的方差，这准确地反映了 `Z` 的数据比 `W` 更分散的直观感受。

![](img/f2405cffbd8c303ade56ba446063a3cf_201.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_202.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_204.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_206.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_208.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_210.png)

## 总结

![](img/f2405cffbd8c303ade56ba446063a3cf_212.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_214.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_216.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_218.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_220.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_222.png)

本节课中我们一起学习了如何将求和符号应用于统计学。
1.  我们使用求和符号 `Σ` 简洁地定义了数据集的**均值** `μ`。
2.  我们介绍了**数据中心化**的方法，即通过减去均值得到一个均值为零的新数据集。
3.  为了衡量数据围绕均值的离散程度，我们定义了**方差** `σ²` 和**标准差** `σ`，它们同样可以用求和符号优雅地表示。

![](img/f2405cffbd8c303ade56ba446063a3cf_224.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_225.png)

![](img/f2405cffbd8c303ade56ba446063a3cf_226.png)

理解这些概念及其数学表达是后续学习更复杂数据科学模型的基础。