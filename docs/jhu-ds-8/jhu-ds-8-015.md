# 015：14_协变量创造

![](img/b2c9d15ae237c9bca184edbbf70d0a05_0.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_2.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_3.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_5.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_6.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_7.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_8.png)

在本节课中，我们将要学习机器学习中的一个关键步骤：**协变量创造**。协变量有时也被称为**预测变量**或**特征**，它们是模型中用于预测结果的实际变量。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_10.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_11.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_12.png)

## 概述：什么是协变量创造？ 🧩

![](img/b2c9d15ae237c9bca184edbbf70d0a05_14.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_15.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_16.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_17.png)

协变量创造分为两个层面。第一个层面是将原始数据转化为可用的预测变量。第二个层面是对已创建的协变量进行转换，以生成新的、可能更有用的协变量。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_19.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_20.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_21.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_22.png)

上一节我们介绍了协变量的基本概念，本节中我们来看看这两个层面的具体内容。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_24.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_25.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_26.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_27.png)

## 第一层面：从原始数据到协变量 📊

![](img/b2c9d15ae237c9bca184edbbf70d0a05_28.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_30.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_31.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_32.png)

原始数据通常以图像、文本文件或网页等形式存在。这类信息很难直接用于构建预测模型，除非我们将其总结为有用的定量或定性变量。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_34.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_35.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_36.png)

我们的目标是将原始数据转化为**特征**或**协变量**。这些变量应尽可能描述数据，同时进行一定压缩，以便更容易应用标准的机器学习算法。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_37.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_38.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_39.png)

### 示例：电子邮件数据

假设你有一封电子邮件。直接将邮件文本输入预测函数非常困难，因为大多数预测函数基于少量变量构建定量模型，不适用于自由文本。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_41.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_42.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_43.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_44.png)

因此，你需要创建一些描述原始数据的特征。以下是针对电子邮件可能创建的特征示例：

*   **大写字母平均比例**：计算邮件中大写字母的比例。例如，一封邮件可能100%的字母都是大写。
*   **特定词频**：计算特定单词（如“you”）在邮件中出现的次数。例如，“you”出现了两次。
*   **特殊符号数量**：计算美元符号“$”的数量。这可能是一个预测邮件是否为垃圾邮件的有效特征。例如，一封邮件中可能有8个美元符号。

从原始数据创建协变量通常需要深入思考数据结构，以及如何用最少的变量提取最有用的信息。

## 第二层面：转换现有协变量 🔄

上一节我们介绍了如何从原始数据提取特征，本节中我们来看看如何对这些特征进行转换。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_46.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_47.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_48.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_49.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_50.png)

有时，我们计算出的协变量（如大写字母平均比例）与我们所关心的结果关联性不强。可能其平方、立方或其他函数形式更有效。因此，第二阶段是对变量进行转换，使其更有用。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_51.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_52.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_53.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_55.png)

例如，我们可以加载垃圾邮件数据集，将大写字母比例这个变量平方，创建一个名为“大写比例平方”的新变量，这可能在后续的预测算法中更有用。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_57.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_58.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_59.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_60.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_61.png)

### 核心考量：平衡与自动化

![](img/b2c9d15ae237c9bca184edbbf70d0a05_63.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_64.png)

创建协变量时，需要在**信息概括**和**信息损失**之间取得平衡。最佳特征是那些仅捕获相关信息的特征。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_66.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_67.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_68.png)

通常，**倾向于创建更多特征**是更好的选择，因为这样信息损失更少，你可以在模型构建过程中过滤掉一些特征。这个过程可以自动化，但需要谨慎，因为某些特征可能在训练集中非常有用，但在新数据或测试集中效果不佳，导致泛化能力差。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_70.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_71.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_72.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_73.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_74.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_75.png)

## 创建新协变量的注意事项 ⚠️

### 1. 仅在训练集上进行

![](img/b2c9d15ae237c9bca184edbbf70d0a05_77.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_78.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_79.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_80.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_81.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_82.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_83.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_84.png)

创建新协变量或决定使用哪些函数时，**必须仅在训练集上进行**。这是机器学习的核心原则。特征构建不能发生在测试集。当你将预测函数应用于测试集时，可以对协变量应用相同的函数，但最初的协变量构建思考必须仅限于训练集，否则会导致过拟合。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_85.png)

### 2. 通过探索性分析寻找思路

![](img/b2c9d15ae237c9bca184edbbf70d0a05_87.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_88.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_89.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_90.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_91.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_92.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_93.png)

我发现的最佳方法是通过**探索性分析**。即绘制图表、制作数据表格，尝试理解数据中的变异模式，以及它们如何与结果相关联。

### 3. 在R中整合新协变量

![](img/b2c9d15ae237c9bca184edbbf70d0a05_95.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_96.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_97.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_98.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_99.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_100.png)

当使用`caret`包或在R中进行此分析时，需要将新协变量添加到数据框中，以便在下游预测中使用。确保新变量的名称可识别非常重要，这样你才能在测试数据集上使用相同的名称。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_101.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_102.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_103.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_104.png)

## 实践示例：工资数据 💰

让我们通过一个示例数据集来实践。我们加载`ISLR`包中的工资数据，并使用`caret`包创建训练集和测试集，以便所有协变量创建都在训练集上进行。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_106.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_107.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_108.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_109.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_110.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_111.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_112.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_113.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_114.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_115.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_116.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_117.png)

### 创建虚拟变量

构建机器学习算法时，一个常见的做法是将**定性变量**或**因子变量**转化为**虚拟变量**。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_119.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_120.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_121.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_122.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_123.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_124.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_125.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_126.png)

假设我们查看训练集中名为`jobclass`的变量，它有两个水平：“工业”和“信息”。我们可以使用`caret`包中的`dummyVars`函数将其转化为定量变量。

以下是相关代码：
```r
# 创建虚拟变量
dummies <- dummyVars(wage ~ jobclass, data = training)
# 应用到训练集（或测试集）以生成新变量
new_vars <- predict(dummies, newdata = training)
```
这将生成两个新变量：一个指示是否为“工业”工作，另一个指示是否为“信息”工作。每个变量取值0或1。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_128.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_129.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_130.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_131.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_132.png)

### 识别低方差变量

![](img/b2c9d15ae237c9bca184edbbf70d0a05_133.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_134.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_135.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_136.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_137.png)

有些变量几乎没有变异性，可能不是有用的协变量。例如，一个“邮件是否包含字母”的特征，几乎所有邮件都包含字母，因此该变量总是为真，没有变异性。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_139.png)

你可以使用`caret`包中的`nearZeroVar`函数来识别这些变量，并将它们从预测算法中剔除。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_140.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_141.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_142.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_143.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_144.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_145.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_146.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_147.png)

### 使用基函数增加模型灵活性

![](img/b2c9d15ae237c9bca184edbbf70d0a05_149.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_150.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_151.png)

如果你使用线性回归作为预测算法，有时你希望拟合曲线而非直线。一种方法是使用**基函数**，例如`splines`包中的`bs`函数可以创建多项式变量。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_153.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_154.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_155.png)

以下是相关代码：
```r
# 创建年龄的三次多项式基函数
library(splines)
bsBasis <- bs(training$age, df=3)
# 将生成的新变量用于线性模型拟合
lm1 <- lm(wage ~ bsBasis, data=training)
```
这将生成三个新列，分别对应年龄、年龄的平方和年龄的立方，从而允许模型拟合年龄与结果之间的曲线关系。

![](img/b2c9d15ae237c9bca184edbbf70d0a05_157.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_158.png)

### 在测试集上应用相同转换

![](img/b2c9d15ae237c9bca184edbbf70d0a05_159.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_160.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_161.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_162.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_163.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_164.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_165.png)

![](img/b2c9d15ae237c9bca184edbbf70d0a05_166.png)

在测试集上，你必须使用与训练集**完全相同的程序**来创建这些协变量。这意味着你应该使用从训练集创建的`bs`函数对象来预测测试集的新值，而不是直接在测试集上重新应用`bs`函数。

## 总结与延伸阅读 📚

本节课中我们一起学习了协变量创造的两个层面。

*   **第一层面特征创造**高度依赖于具体科学或应用领域的知识。最好的学习方法是针对你正在分析的数据类型（如图像、语音）搜索“特征提取”。通常，倾向于创建更多特征是安全的，因为你可以在后续过程中过滤它们。对于图像和语音，自动特征创造（如深度学习）非常常见且必要。
*   **第二层面特征创造**可以利用`caret`包的预处理组件完成。关键仍然是绘制大量图表并进行探索性分析。你可以创建你认为能改进模型拟合的新协变量，但需注意避免过拟合。

关于特征创造和数据整理的更多内容，可以参考数据科学专项课程中的《数据获取与清理》课程。

---
**核心概念回顾**：
*   **协变量/特征**：`特征 = f(原始数据)` 或 `新特征 = g(现有特征)`
*   **核心原则**：特征工程**必须**仅在训练集上进行。
*   **实用工具**：`dummyVars()`, `nearZeroVar()`, `bs()`。