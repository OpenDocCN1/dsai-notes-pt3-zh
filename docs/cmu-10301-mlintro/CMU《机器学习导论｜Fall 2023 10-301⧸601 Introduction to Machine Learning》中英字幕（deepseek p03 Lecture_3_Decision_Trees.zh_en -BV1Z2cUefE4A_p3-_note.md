# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p03 Lecture_3_Decision_Trees.zh_en [BV1Z2cUefE4A_p3]

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_1.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_2.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_3.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_5.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_7.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_9.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_10.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_12.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_14.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_15.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_17.png)

## 1. 课程概述

在本节课中，我们将继续讨论决策树，并深入了解其构建和预测过程。

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_19.png)

## 2. 课程内容

### 2.1 决策树简介

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_21.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_23.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_25.png)

决策树是一种常用的机器学习模型，它通过一系列的规则来对数据进行分类或回归。

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_27.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_29.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_31.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_33.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_34.png)

### 2.2 决策树构建

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_36.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_37.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_39.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_40.png)

决策树的构建过程包括以下步骤：

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_42.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_44.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_46.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_48.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_50.png)

1. **选择特征**：选择一个特征进行分割，通常使用信息增益或基尼不纯度作为选择标准。
2. **分割数据**：根据选择的特征将数据分割成两个子集。
3. **递归构建**：对每个子集重复步骤1和2，直到满足停止条件。

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_52.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_54.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_56.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_58.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_59.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_61.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_62.png)

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_63.png)

### 2.3 决策树预测

决策树的预测过程如下：

1. 从根节点开始，根据特征值选择分支。
2. 重复步骤1，直到到达叶节点。
3. 返回叶节点对应的标签。

### 2.4 信息增益

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_65.png)

信息增益是衡量特征选择好坏的一个指标，它表示选择该特征后数据的不确定性减少程度。

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_67.png)

### 2.5 基尼不纯度

基尼不纯度是衡量数据集纯度的指标，它表示数据集中不同类别的比例差异。

### 2.6 决策树示例

以下是一个简单的决策树示例，用于预测是否喜欢猫或狗：

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_69.png)

```
是否喜欢温暖天气？
是 -> 是否是早起的人？
是 -> 猫
否 -> 狗
否 -> 狗
```

### 2.7 决策树应用

决策树可以用于各种应用，例如：

* **分类**：例如，预测客户是否会购买产品。
* **回归**：例如，预测房价。

## 3. 总结

![](img/a1e5ccf52cd6990c8635cc9a617ab47f_71.png)

本节课中，我们学习了决策树的基本概念、构建过程和预测方法。在下一节课中，我们将继续讨论决策树的优缺点以及如何改进决策树模型。