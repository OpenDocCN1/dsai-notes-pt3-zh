# 011：数据切片 📊

![](img/67de3d55d7e82eff355ac3da2c771807_0.png)

![](img/67de3d55d7e82eff355ac3da2c771807_2.png)

![](img/67de3d55d7e82eff355ac3da2c771807_3.png)

在本节课中，我们将要学习数据切片技术。数据切片是机器学习工作流程中的关键步骤，主要用于在创建预测函数之初划分训练集和测试集，或在训练集内部进行交叉验证或自助法重采样以评估模型性能。

![](img/67de3d55d7e82eff355ac3da2c771807_4.png)

我们将使用 `caret` 包中的函数，并以经典的垃圾邮件数据集为例进行演示。

## 1. 划分训练集与测试集 🎯

上一节我们介绍了数据切片的基本概念，本节中我们来看看如何使用 `caret` 包将数据集划分为训练集和测试集。

首先，我们加载必要的包和数据。我们使用 `spam` 数据集，该数据集的目标是预测电子邮件是否为垃圾邮件，其特征包括特定单词的出现频率和大写字母的出现情况。

![](img/67de3d55d7e82eff355ac3da2c771807_6.png)

![](img/67de3d55d7e82eff355ac3da2c771807_7.png)

![](img/67de3d55d7e82eff355ac3da2c771807_8.png)

![](img/67de3d55d7e82eff355ac3da2c771807_9.png)

以下是使用 `createDataPartition` 函数进行数据划分的步骤：

![](img/67de3d55d7e82eff355ac3da2c771807_10.png)

![](img/67de3d55d7e82eff355ac3da2c771807_11.png)

![](img/67de3d55d7e82eff355ac3da2c771807_12.png)

![](img/67de3d55d7e82eff355ac3da2c771807_13.png)

![](img/67de3d55d7e82eff355ac3da2c771807_14.png)

![](img/67de3d55d7e82eff355ac3da2c771807_15.png)

```r
library(caret)
data(spam)

![](img/67de3d55d7e82eff355ac3da2c771807_16.png)

![](img/67de3d55d7e82eff355ac3da2c771807_17.png)

# 基于结果变量 type 进行划分，75% 数据用于训练，25% 用于测试
intrain <- createDataPartition(y = spam$type, p = 0.75, list = FALSE)

![](img/67de3d55d7e82eff355ac3da2c771807_19.png)

# 创建训练集和测试集
training <- spam[intrain, ]
testing <- spam[-intrain, ]
```

*   `y`：指定用于分层抽样的结果变量。
*   `p`：指定分配给训练集的数据比例。
*   `list`：设置为 `FALSE` 会返回一个索引向量，用于直接子集化数据框。
*   训练集由索引 `intrain` 对应的样本组成。
*   测试集由**不**在 `intrain` 索引中的样本组成，在 R 中使用 `-` 号实现。

## 2. 创建K折交叉验证集 🔄

![](img/67de3d55d7e82eff355ac3da2c771807_21.png)

![](img/67de3d55d7e82eff355ac3da2c771807_22.png)

![](img/67de3d55d7e82eff355ac3da2c771807_23.png)

![](img/67de3d55d7e82eff355ac3da2c771807_24.png)

![](img/67de3d55d7e82eff355ac3da2c771807_25.png)

![](img/67de3d55d7e82eff355ac3da2c771807_26.png)

在模型评估阶段，我们经常需要将训练集进一步细分为多个子集进行交叉验证。`caret` 包提供了 `createFolds` 函数来实现这一目的。

![](img/67de3d55d7e82eff355ac3da2c771807_27.png)

![](img/67de3d55d7e82eff355ac3da2c771807_28.png)

![](img/67de3d55d7e82eff355ac3da2c771807_29.png)

以下是创建 K 折交叉验证索引的方法：

![](img/67de3d55d7e82eff355ac3da2c771807_31.png)

```r
# 创建10折交叉验证的索引，以列表形式返回
folds <- createFolds(y = spam$type, k = 10, list = TRUE, returnTrain = TRUE)

![](img/67de3d55d7e82eff355ac3da2c771807_33.png)

![](img/67de3d55d7e82eff355ac3da2c771807_34.png)

![](img/67de3d55d7e82eff355ac3da2c771807_35.png)

# 检查第一折的样本数量
length(folds[[1]])
```

![](img/67de3d55d7e82eff355ac3da2c771807_36.png)

![](img/67de3d55d7e82eff355ac3da2c771807_37.png)

*   `k`：指定折数。
*   `list`：设置为 `TRUE` 会返回一个列表，每个元素对应一折的样本索引。
*   `returnTrain`：设置为 `TRUE` 时，返回的是每折中**训练部分**的索引；设置为 `FALSE` 时，则返回**测试部分**的索引。
*   函数会尽量保证每一折的样本数量大致相等。

通过查看 `folds[[1]]`，我们可以获得第一折训练集的具体样本索引。默认情况下，数据是按顺序分割的。

![](img/67de3d55d7e82eff355ac3da2c771807_39.png)

![](img/67de3d55d7e82eff355ac3da2c771807_40.png)

![](img/67de3d55d7e82eff355ac3da2c771807_41.png)

## 3. 自助法重采样 🔁

![](img/67de3d55d7e82eff355ac3da2c771807_42.png)

![](img/67de3d55d7e82eff355ac3da2c771807_43.png)

![](img/67de3d55d7e82eff355ac3da2c771807_44.png)

除了交叉验证，自助法也是一种常用的重采样技术。`caret` 包中的 `createResample` 函数可以用于此目的。

以下是进行自助法重采样的方法：

![](img/67de3d55d7e82eff355ac3da2c771807_46.png)

![](img/67de3d55d7e82eff355ac3da2c771807_47.png)

```r
# 进行10次自助法重采样，返回列表
resamples <- createResample(y = spam$type, times = 10, list = TRUE)
```

![](img/67de3d55d7e82eff355ac3da2c771807_48.png)

![](img/67de3d55d7e82eff355ac3da2c771807_49.png)

![](img/67de3d55d7e82eff355ac3da2c771807_50.png)

![](img/67de3d55d7e82eff355ac3da2c771807_51.png)

*   `times`：指定重采样次数。
*   由于自助法是**有放回**抽样，因此在生成的索引中，同一个样本可能会多次出现。例如，在 `resamples[[1]]` 中，某个索引可能重复出现三次。

## 4. 时间序列数据切片 ⏳

对于时间序列或具有顺序依赖关系的数据，我们需要特殊的切片方法来保持时间连续性。`caret` 包中的 `createTimeSlices` 函数专门用于此场景。

![](img/67de3d55d7e82eff355ac3da2c771807_53.png)

![](img/67de3d55d7e82eff355ac3da2c771807_54.png)

![](img/67de3d55d7e82eff355ac3da2c771807_55.png)

![](img/67de3d55d7e82eff355ac3da2c771807_56.png)

假设我们有一个从1到1000的时间索引向量，我们希望使用一个长度为20的窗口来预测接下来的10个值。

![](img/67de3d55d7e82eff355ac3da2c771807_57.png)

![](img/67de3d55d7e82eff355ac3da2c771807_58.png)

![](img/67de3d55d7e82eff355ac3da2c771807_59.png)

![](img/67de3d55d7e82eff355ac3da2c771807_60.png)

以下是创建时间切片的方法：

```r
# 创建时间索引
time <- 1:1000

# 创建时间切片：初始窗口=20，预测 horizon=10，固定窗口
time_slices <- createTimeSlices(y = time, initialWindow = 20, horizon = 10, fixedWindow = TRUE)

# 查看第一个训练窗口和测试窗口
training_window1 <- time_slices$train[[1]]
testing_window1 <- time_slices$test[[1]]
```

![](img/67de3d55d7e82eff355ac3da2c771807_62.png)

![](img/67de3d55d7e82eff355ac3da2c771807_63.png)

![](img/67de3d55d7e82eff355ac3da2c771807_64.png)

*   `initialWindow`：用于训练/拟合的初始观测值数量。
*   `horizon`：要预测的未来观测值数量。
*   `fixedWindow`：设置为 `TRUE` 时，使用固定大小的训练窗口；设置为 `FALSE` 时，训练窗口会随着时间增长。
*   第一个训练窗口包含样本 1 到 20。
*   对应的第一个测试窗口则包含样本 21 到 30。
*   随后的切片会依次滑动，生成连续的时间块，从而在预测中利用数据的时间依赖性。

![](img/67de3d55d7e82eff355ac3da2c771807_65.png)

![](img/67de3d55d7e82eff355ac3da2c771807_66.png)

![](img/67de3d55d7e82eff355ac3da2c771807_67.png)

![](img/67de3d55d7e82eff355ac3da2c771807_68.png)

![](img/67de3d55d7e82eff355ac3da2c771807_69.png)

![](img/67de3d55d7e82eff355ac3da2c771807_70.png)

关于时间切片的更多高级用法和示例，可以参考 `caret` 包的教程和介绍该包的原始论文，其中包含了丰富的信息。

![](img/67de3d55d7e82eff355ac3da2c771807_71.png)

![](img/67de3d55d7e82eff355ac3da2c771807_72.png)

## 总结 📝

本节课中我们一起学习了数据切片的核心技术。我们掌握了：
1.  使用 `createDataPartition` 划分初始的训练集和测试集。
2.  使用 `createFolds` 为 K 折交叉验证创建数据折。
3.  使用 `createResample` 执行自助法重采样。
4.  使用 `createTimeSlices` 为时间序列数据创建具有连续性的训练和测试窗口。

![](img/67de3d55d7e82eff355ac3da2c771807_74.png)

![](img/67de3d55d7e82eff355ac3da2c771807_75.png)

![](img/67de3d55d7e82eff355ac3da2c771807_76.png)

![](img/67de3d55d7e82eff355ac3da2c771807_77.png)

![](img/67de3d55d7e82eff355ac3da2c771807_78.png)

这些技术是构建可靠机器学习模型评估流程的基础，在后续的课程和作业中将会反复应用。