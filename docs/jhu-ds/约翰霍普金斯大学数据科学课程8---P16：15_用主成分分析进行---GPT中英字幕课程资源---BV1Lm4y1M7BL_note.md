# 课程8：实际机器学习 🧠 - P16：使用主成分分析进行预处理 📊

![](img/54a0afeacb9aa1217b6b76714dcb63a2_1.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_2.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_4.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_5.png)

在本节课中，我们将要学习一种重要的数据预处理技术——主成分分析。当数据集中存在多个高度相关的定量变量时，主成分分析可以帮助我们提取核心信息，减少变量数量，并可能提升模型的性能。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_7.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_8.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_9.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_10.png)

## 概述与核心思想 💡

![](img/54a0afeacb9aa1217b6b76714dcb63a2_12.png)

在机器学习中，我们常常会遇到多个定量变量，并且这些变量之间可能存在高度相关性。换句话说，它们可能非常相似，几乎等同于同一个变量。在这种情况下，将每个变量都纳入模型并不一定有益。我们可能希望纳入一些能够捕捉这些定量变量中大部分信息的“摘要”。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_13.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_14.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_15.png)

主成分分析的核心思想是：找到原始变量的一个加权组合，这个新组合能够解释数据中尽可能多的变异性。这样做的好处是减少了模型中需要包含的预测变量数量，并且通过合并变量来降低噪声。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_17.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_18.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_20.png)

## 一个简单的例子：垃圾邮件数据集 📧

![](img/54a0afeacb9aa1217b6b76714dcb63a2_22.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_23.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_24.png)

为了具体说明，我们将再次使用垃圾邮件数据集。首先加载必要的R包和数据，并创建训练集与测试集。所有探索、模型创建和特征构建都必须在训练集上进行。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_26.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_27.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_28.png)

以下是初始步骤：
1.  加载 `caret` 和 `kernlab` 包。
2.  加载 `spam` 数据集。
3.  划分训练集和测试集。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_29.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_30.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_31.png)

## 识别高度相关的变量 🔍

![](img/54a0afeacb9aa1217b6b76714dcb63a2_33.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_34.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_35.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_36.png)

第一步是检查预测变量之间的相关性。我们排除结果变量（第58列），计算所有其他预测变量之间的相关性矩阵，并取其绝对值。我们关注的是彼此之间相关性非常高的变量。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_38.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_39.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_40.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_41.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_43.png)

每个变量与自身的相关性都是1，这不属于我们的兴趣范围。因此，我们将相关性矩阵的对角线设置为0，然后找出哪些变量之间的相关性大于0.8。

结果发现，变量 `num415` 和 `num857`（即电子邮件中数字415和857出现的频率）具有极高的相关性。这很可能是因为它们属于同一个电话号码的一部分。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_45.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_46.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_47.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_48.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_49.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_50.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_51.png)

如果我们绘制这两个变量，会发现它们几乎完全落在一条直线上：随着数字415出现频率的增加，数字857的出现频率也同步增加。在模型中同时包含这两个预测变量可能并不十分有用。

## 主成分分析的直观理解 🧩

![](img/54a0afeacb9aa1217b6b76714dcb63a2_53.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_54.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_55.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_56.png)

基本思路是：我们能否将这些变量转化为一个单一的、可能更好的变量？一个想法是将其视为这些预测变量的加权组合，该组合能够解释数据中的大部分情况。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_57.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_58.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_59.png)

我们的目标是选择能够捕获最多信息的组合。这不仅减少了预测变量数量，还通过“平均”或合并变量来降低噪声。如果方法得当，主成分分析能带来显著收益。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_61.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_62.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_63.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_64.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_65.png)

我们可以这样思考：我们试图找出这些变量的一个组合，以解释大部分的变异性。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_67.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_68.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_69.png)

例如，对于两个高度相关的变量 `num415` (X1) 和 `num857` (X2)，我们可以创建两个新变量：
*   **新变量X（第一主成分）**：`PC1 = 0.71 * X1 + 0.71 * X2` （基本上是两者之和）
*   **新变量Y（第二主成分）**：`PC2 = 0.71 * X1 - 0.71 * X2` （基本上是两者之差）

![](img/54a0afeacb9aa1217b6b76714dcb63a2_70.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_71.png)

如果我们绘制X轴为PC1（求和）、Y轴为PC2（求差）的散点图，会发现大多数点沿着X轴（PC1）广泛分布，而在Y轴（PC2）上则紧密聚集在0附近。这意味着将两个变量相加（PC1）捕获了这两个变量中的大部分信息，而相减（PC2）包含的信息则少得多。因此，我们可能希望使用两个变量的和作为预测变量，从而减少预测变量数量并降低噪声。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_73.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_74.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_75.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_76.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_77.png)

## 主成分分析的正式定义与目标 🎯

![](img/54a0afeacb9aa1217b6b76714dcb63a2_79.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_80.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_81.png)

在更普遍的意义上，主成分分析要解决两个相关问题：
1.  **统计目标**：基于现有变量找出一组新的、互不相关的变量，并且这些新变量能解释尽可能多的变异性。从之前的图中看，我们寻找的是具有大量变异的X变量，而不是几乎总为零的Y变量。
2.  **数据压缩目标**：如果我们把所有变量放在一个矩阵中，能否创建一个变量更少（数学上称为更低秩）的矩阵来近似解释原始数据？

![](img/54a0afeacb9aa1217b6b76714dcb63a2_82.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_84.png)

这两个目标紧密相关，核心思想都是：我们能否用更少的变量来解释几乎所有的数据变化？第一个是统计目标，第二个是数据压缩目标，两者对机器学习都非常有用。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_86.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_87.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_88.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_89.png)

## 解决方案：奇异值分解与主成分 📐

有两个相关的解决方案，它们彼此非常相似。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_91.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_92.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_93.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_94.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_95.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_96.png)

如果 **X** 是一个矩阵，每列是一个变量，每行是一个观测值（就像R中的数据框），那么**奇异值分解** 是一种矩阵分解方法。它将数据框 **X** 分解为三个矩阵：

![](img/54a0afeacb9aa1217b6b76714dcb63a2_97.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_98.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_99.png)

`X = U * D * V^T`

其中：
*   **U** 的列称为**左奇异向量**。
*   **V** 的列称为**右奇异向量**。
*   **D** 是一个对角矩阵，其元素称为**奇异值**。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_101.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_102.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_103.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_104.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_105.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_106.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_107.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_108.png)

**主成分** 在数据经过适当缩放后，等于右奇异向量 **V**。换句话说，如果进行正确的缩放，上一张幻灯片中提到的两个问题的解决方案是相同的。**V** 中的变量被构造为能够解释数据中的最大变异量。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_110.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_111.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_112.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_113.png)

## 在垃圾邮件数据上实践PCA 🛠️

为了展示其工作原理，我们以垃圾邮件数据集中两个高度相关的变量（第34和32列）为例，对仅包含这两个变量的数据子集进行主成分分析。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_115.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_116.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_117.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_118.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_119.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_120.png)

如果我们绘制第一主成分与第二主成分的散点图，会看到一个与之前非常相似的图：第一主成分很像将两个变量相加，第二主成分很像将两个变量相减。

那么，为什么我们要使用主成分而不仅仅是加减法呢？因为主成分分析允许你在拥有两个以上变量时执行此操作。你可能能够将所有变量缩减为非常少量的组合，这些组合是观测变量的加权和与差。因此，使用主成分分析可以让你审视大量定量变量并大幅缩减其数量。

我们还可以查看主成分对象中的**旋转矩阵**，它基本上显示了如何将原始变量相加以获得每个主成分。在本例中，第一主成分（解释最多变异性的成分）只是将两个变量相加，第二主成分（解释第二多变异性的成分）则是将两个变量相减。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_122.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_123.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_124.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_125.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_126.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_127.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_128.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_129.png)

## 在整个数据集上应用PCA 🌐

![](img/54a0afeacb9aa1217b6b76714dcb63a2_130.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_131.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_132.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_133.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_135.png)

在垃圾邮件数据上，我们可以对超过两个变量进行主成分分析，这体现了PCA的实用性。

首先，我们创建一个颜色变量用于绘图：非垃圾邮件（ham）标为黑色，垃圾邮件（spam）标为红色。

然后，我们对整个数据集计算主成分。注意，在计算前我们对数据应用了 `log10(x+1)` 变换，以使数据看起来更接近正态分布（因为有些变量是偏态的），这通常能让主成分分析的结果更合理。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_137.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_138.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_139.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_140.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_141.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_142.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_143.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_144.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_145.png)

现在，我们可以再次绘制第一主成分与第二主成分的散点图，并按垃圾邮件指示器着色。每个点对应一个观测值，红点对应垃圾邮件，黑点对应正常邮件。可以看到，在第一主成分（PC1）方向上，正常邮件和垃圾邮件有一定程度的分离：垃圾邮件往往具有稍高的PC1值。这是一种在保留大量变异性的同时缩减数据规模的方法，也是特征创建的核心思想。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_146.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_147.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_148.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_150.png)

## 使用 `caret` 包进行PCA预处理 📦

![](img/54a0afeacb9aa1217b6b76714dcb63a2_152.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_153.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_154.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_155.png)

在 `caret` 包中也可以进行主成分分析预处理。使用 `preProcess` 函数，指定方法为 `"pca"`，并告知要计算的主成分数量。然后，你可以使用 `predict` 函数基于这个预处理对象和原始数据来计算每个样本的主成分得分。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_156.png)

这些新的主成分变量（如PC1和PC2）本质上是一个拟合到数据的模型。如果你获得一个新的观测值，你需要预测该新观测值的主成分会是什么样子。我们将预处理对象和新数据传递给 `predict` 函数，即可得到新数据的主成分。绘制这些主成分，我们再次看到正常邮件和垃圾邮件在PC1和PC2上有一定的分离。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_158.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_159.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_160.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_161.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_162.png)

## 在建模流程中整合PCA 🔄

![](img/54a0afeacb9aa1217b6b76714dcb63a2_164.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_165.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_166.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_167.png)

你可以将PCA直接构建到训练流程中。如果你使用 `caret` 包的 `train` 函数，并传入训练集，同时指定使用主成分分析进行预处理，它将在训练过程中完成该预处理。然后，在对新数据进行预测时，你只需传入测试数据，`caret` 会自动为你计算主成分。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_168.png)

之前展示的更详细的计算主成分并传递给模型的方法，是为了让你了解当向 `caret` 包的 `train` 函数传递类似指令时，其内部是如何运作的。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_170.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_171.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_172.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_173.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_174.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_175.png)

## 注意事项与总结 📝

![](img/54a0afeacb9aa1217b6b76714dcb63a2_177.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_178.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_179.png)

主成分分析对于线性模型（包括线性判别分析、线性和广义线性回归等）最为有用。然而，它可能使预测变量的解释变得困难。在只有两个变量的简单情况下，主成分只是变量的和与差，很容易解释。但在一般情况下，如果你对大量定量变量进行主成分分析，每个主成分都可能是你所观测变量的相当复杂的加权和，因此可能非常难以解释。

此外，需要注意**异常值**，它们会严重干扰主成分的计算。你应该首先通过探索性分析识别异常值，并进行适当的变换（如之前做的对数变换或Box-Cox变换）。绘制预测变量以识别问题是判断PCA是否有效的关键。

关于主成分分析和奇异值分解的更多详细信息，可以参考探索性数据分析课程。书籍《The Elements of Statistical Learning》也对主成分分析在机器学习中的应用给出了技术性概述。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_181.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_182.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_183.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_184.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_185.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_186.png)

## 本节课总结 🎓

![](img/54a0afeacb9aa1217b6b76714dcb63a2_187.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_188.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_189.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_190.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_191.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_192.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_194.png)

本节课我们一起学习了主成分分析这种强大的数据预处理技术。我们了解了其核心思想：通过寻找原始变量的线性组合来创建新的、不相关的变量（主成分），这些新变量能够解释数据中的最大变异性。我们通过垃圾邮件数据集的实例，演示了如何识别高度相关的变量、直观理解PCA、使用R语言执行PCA分析、将PCA整合到`caret`包的建模流程中，并讨论了其适用场景和注意事项。掌握PCA有助于我们在处理高维或共线性数据时，有效降维、去除噪声并可能提升模型性能。