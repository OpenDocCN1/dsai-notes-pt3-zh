# 018：实际机器学习 - P18 📊 使用多元协变量进行回归预测

![](img/8ff3b8acf043449b9d3e0111a661c235_1.png)

在本节课中，我们将学习如何使用多元协变量进行回归预测。更重要的是，我们将探索一个数据集，并尝试识别哪些预测变量对于构建预测模型最为关键。

我们将再次使用工资数据，来预测一组来自美国中大西洋地区的男性的工资。该数据集来自《统计学习导论》一书，可在ISLR包中找到。

## 数据加载与初步探索

首先，我们需要加载数据集和必要的R包。

```r
# 加载数据集和包
library(ISLR)
library(ggplot2)
library(caret)

![](img/8ff3b8acf043449b9d3e0111a661c235_3.png)

# 加载工资数据，并排除我们试图预测的变量（log wage）以进行探索
data(Wage)
Wage <- subset(Wage, select = -logwage)
```

我们可以查看数据的摘要信息，以了解其基本特征。例如，数据集中只包含男性，且所有人都来自中大西洋地区。

![](img/8ff3b8acf043449b9d3e0111a661c235_5.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_6.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_7.png)

为了进行更深入的探索，我们首先需要将数据划分为训练集和测试集。我们使用`createDataPartition`函数来完成此操作，并将在训练集上进行所有探索性分析，因为构建模型时不应使用测试集中的任何信息。

```r
# 划分训练集和测试集
set.seed(123)
trainIndex <- createDataPartition(Wage$wage, p = .8, list = FALSE)
training <- Wage[trainIndex, ]
testing <- Wage[-trainIndex, ]
```

![](img/8ff3b8acf043449b9d3e0111a661c235_9.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_10.png)

## 探索性数据分析

![](img/8ff3b8acf043449b9d3e0111a661c235_11.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_12.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_14.png)

上一节我们介绍了数据的基本情况，本节中我们来看看如何通过可视化来探索变量之间的关系。

![](img/8ff3b8acf043449b9d3e0111a661c235_15.png)

以下是进行特征绘图的代码，它可以帮助我们初步了解变量间的关联。

![](img/8ff3b8acf043449b9d3e0111a661c235_17.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_18.png)

```r
# 特征绘图
featurePlot(x = training[, c("age", "jobclass", "education")],
            y = training$wage,
            plot = "pairs")
```

![](img/8ff3b8acf043449b9d3e0111a661c235_19.png)

有时这个图很有用，但有时因为点过于密集而难以看清。如果你自己运行这段代码，可能会看得更清楚一些。例如，从图中可以看出，不同工作类别（job class）的工资似乎存在差异，年龄与工资之间也存在某种趋势，并且存在一些离群点。

### 识别重要预测变量

![](img/8ff3b8acf043449b9d3e0111a661c235_21.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_22.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_23.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_24.png)

为了更深入地理解这些关系，我们可以绘制单个预测变量与结果变量的关系图。

![](img/8ff3b8acf043449b9d3e0111a661c235_26.png)

首先，我们绘制年龄与工资的关系图。

![](img/8ff3b8acf043449b9d3e0111a661c235_27.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_28.png)

```r
# 绘制年龄与工资的关系
qplot(age, wage, data = training)
```

![](img/8ff3b8acf043449b9d3e0111a661c235_30.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_31.png)

从图中可以看到一个总体趋势，但也存在一组明显偏高的离群点。我们的目标是找出是哪个变量导致了这组高工资群体。

![](img/8ff3b8acf043449b9d3e0111a661c235_32.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_33.png)

一种方法是在散点图上用颜色区分另一个变量。例如，我们用工作类别来着色。

```r
# 用工作类别着色
qplot(age, wage, colour = jobclass, data = training)
```

可以看到，大部分高工资点（图中上方的点）是蓝色的，代表“信息类”工作。这表明“工作类别”这个变量可能能够解释顶部群体的部分工资差异。

我们也可以用教育水平来着色。

![](img/8ff3b8acf043449b9d3e0111a661c235_35.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_36.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_37.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_38.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_39.png)

```r
# 用教育水平着色
qplot(age, wage, colour = education, data = training)
```

![](img/8ff3b8acf043449b9d3e0111a661c235_40.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_41.png)

同样，高级学位（advanced degree）也解释了顶部群体的许多差异。因此，学位和工作类别的某种组合可以解释为什么年龄和工资之间的关系不是简单的单一趋势。

## 构建多元线性回归模型

![](img/8ff3b8acf043449b9d3e0111a661c235_43.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_44.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_45.png)

在探索了数据之后，我们现在来构建一个包含多个变量的线性回归模型。其核心思想是拟合一条线（或一个超平面），但现在我们使用多个预测变量。

模型的基本形式如下：

![](img/8ff3b8acf043449b9d3e0111a661c235_47.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_48.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_49.png)

**公式：** `wage ≈ β₀ + β₁ * age + β₂ * jobclass_information + ...`

其中，`jobclass_information` 是一个**指示变量**（或虚拟变量）。其数学表示为：

![](img/8ff3b8acf043449b9d3e0111a661c235_51.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_52.png)

**公式：** `I(jobclass_i = "Information") = {1 if true, 0 if false}`

![](img/8ff3b8acf043449b9d3e0111a661c235_53.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_54.png)

这个变量表示，在固定回归模型中所有其他变量的情况下，工作类别为“信息类”与“非信息类”人群的工资差异。

对于教育水平这种多分类变量，我们需要为每个类别（除一个基准类别外）创建一个指示变量。

![](img/8ff3b8acf043449b9d3e0111a661c235_56.png)

在R中，我们可以使用`caret`包的`train`函数方便地拟合模型。当公式中包含因子变量（如`jobclass`和`education`）时，R会自动为我们创建这些指示变量。

![](img/8ff3b8acf043449b9d3e0111a661c235_57.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_58.png)

```r
# 使用训练集拟合多元线性回归模型
set.seed(123)
modelFit <- train(wage ~ age + jobclass + education,
                  data = training,
                  method = "lm")
# 查看最终模型
modelFit$finalModel
```

![](img/8ff3b8acf043449b9d3e0111a661c235_60.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_61.png)

尽管我们在公式中只写了三个变量名，但最终模型可能包含多个预测变量，这是因为R为因子变量的每个水平都创建了指示变量。

![](img/8ff3b8acf043449b9d3e0111a661c235_63.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_64.png)

## 模型诊断与进一步探索

拟合模型后，进行诊断至关重要。我们可以绘制拟合值与残差的关系图。

![](img/8ff3b8acf043449b9d3e0111a661c235_66.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_67.png)

```r
# 绘制拟合值与残差图
qplot(predict(modelFit, training), residuals(modelFit, training),
      xlab = "Fitted Values", ylab = "Residuals")
```

![](img/8ff3b8acf043449b9d3e0111a661c235_68.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_69.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_70.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_71.png)

理想情况下，残差应随机分布在0附近。图中若存在明显的模式或离群点（例如某些点残差特别高），则表明模型可能遗漏了重要的预测变量。

![](img/8ff3b8acf043449b9d3e0111a661c235_73.png)

我们可以通过用未包含在模型中的变量（如种族`race`）为残差图着色，来进一步探索。

![](img/8ff3b8acf043449b9d3e0111a661c235_74.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_75.png)

```r
# 用种族变量为残差图着色
qplot(predict(modelFit, training), residuals(modelFit, training),
      colour = race, data = training)
```

如果某些离群点明显与特定种族相关，则表明`race`可能是一个有用的预测变量。

另一种有用的诊断方法是绘制残差与数据索引（即数据行的顺序）的关系图。

![](img/8ff3b8acf043449b9d3e0111a661c235_77.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_78.png)

```r
# 绘制残差与索引的关系图
qplot(seq_along(residuals(modelFit, training)), residuals(modelFit, training),
      xlab = "Index", ylab = "Residuals")
```

![](img/8ff3b8acf043449b9d3e0111a661c235_79.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_80.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_81.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_82.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_83.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_84.png)

如果残差随着索引呈现趋势或聚集，这可能意味着数据收集顺序中存在时间效应或其他连续变量效应，而该变量未被包含在模型中。

![](img/8ff3b8acf043449b9d3e0111a661c235_85.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_86.png)

## 在测试集上评估模型

最后，我们在测试集上评估模型的性能，并做最后的探索。

![](img/8ff3b8acf043449b9d3e0111a661c235_88.png)

```r
# 在测试集上预测并绘图
testPred <- predict(modelFit, testing)
qplot(wage, testPred, colour = year, data = testing) +
  geom_abline(intercept = 0, slope = 1)
```

![](img/8ff3b8acf043449b9d3e0111a661c235_89.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_90.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_91.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_92.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_93.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_94.png)

我们绘制测试集中真实工资与预测工资的散点图，并用数据收集年份着色。理想情况下，点应紧密分布在45度对角线上。通过观察不同年份点的分布，我们可以评估模型在不同时期的表现是否稳定。

**重要提示：** 在测试集上进行这种探索性分析后，**不能**再根据发现回到训练集重新调整或构建模型，否则就相当于使用了测试集信息，会导致对模型性能的乐观估计。这更像是一种“事后分析”，用于判断模型是否有效。

![](img/8ff3b8acf043449b9d3e0111a661c235_96.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_97.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_98.png)

## 使用所有变量进行预测

![](img/8ff3b8acf043449b9d3e0111a661c235_99.png)

如果你希望将所有可用的协变量都纳入模型，可以在`train`函数的公式中使用点号`.`。

```r
# 使用所有变量拟合模型
set.seed(123)
modelFitAll <- train(wage ~ ., data = training, method = "lm")
```

![](img/8ff3b8acf043449b9d3e0111a661c235_101.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_102.png)

这表示使用数据集中除结果变量外的所有变量进行预测。通常，包含更多相关变量会提升模型性能，尤其是在你没有进行前期变量筛选的情况下。

![](img/8ff3b8acf043449b9d3e0111a661c235_103.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_104.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_105.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_106.png)

![](img/8ff3b8acf043449b9d3e0111a661c235_107.png)

## 总结

本节课中我们一起学习了以下内容：

1.  **多元线性回归**：学习了如何使用多个预测变量（协变量）构建回归模型，包括如何处理分类变量（通过创建指示变量）。
2.  **探索性数据分析**：掌握了通过可视化（如特征图、着色散点图）来探索数据、识别重要预测变量和模型潜在问题的方法。
3.  **模型诊断**：学会了使用残差图等工具来评估模型拟合效果，并发现可能被遗漏的预测变量。
4.  **测试集验证**：理解了在独立测试集上评估模型性能的重要性，以及进行事后探索的注意事项。
5.  **全变量模型**：了解了如何快速构建包含所有可用变量的模型。

![](img/8ff3b8acf043449b9d3e0111a661c235_109.png)

线性回归是一个简单而强大的工具，当预测变量与结果之间存在线性关系时非常有效。它可以与其他更复杂的模型结合使用，我们将在后续课程中讨论模型融合。通过本节介绍的探索性数据分析技巧，你可以更好地理解数据，从而构建出更精准的预测模型。