# 约翰霍普金斯大学数据科学课程7：《回归模型》｜P33：模型选择（第三部分）🔍

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_0.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_2.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_4.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_6.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_8.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_10.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_12.png)

在本节课中，我们将要学习模型选择对回归模型中另一个关键参数——残差方差的影响，并探讨自动化模型选择、实验设计的作用，以及一种实用的嵌套模型检验方法。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_14.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_15.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_16.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_17.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_19.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_21.png)

## 残差方差的影响 📊

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_23.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_25.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_26.png)

上一节我们讨论了包含或遗漏变量对回归系数的影响。本节中，我们来看看这些操作对回归模型中另一个估计参数——残差方差 **σ²** 的影响。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_27.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_29.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_30.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_31.png)

在假设误差独立同分布且线性模型形式正确的前提下，我们可以从数学上描述遗漏必要变量或包含不必要变量的影响。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_33.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_34.png)

其规律与我们之前讨论的系数影响类似：
*   **如果模型欠拟合**（即遗漏了重要变量），那么方差估计是**有偏的**。这是因为我们将那些本可以由被遗漏的协变量系统解释的变异，错误地归因于随机误差。
*   **如果模型正确拟合或过拟合**（即包含了所有正确项或额外的不必要项），那么方差估计是**无偏的**。然而，**如果我们包含了不必要变量，方差估计值本身的方差会增大**，导致估计的可靠性下降。

简而言之，对于方差估计：**遗漏变量导致偏差，包含不必要变量导致估计可靠性降低**。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_36.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_37.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_38.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_39.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_40.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_41.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_42.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_43.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_44.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_45.png)

## 关于自动化模型选择 🤖

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_47.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_48.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_49.png)

现在让我们来谈谈广义的自动化模型选择。需要指出的是，自动化模型选择如今更多属于机器学习的范畴。即使对于相对简单的线性回归模型，当你开始考虑交互项、多项式项（如预测变量的平方）时，需要搜索的模型项空间也会迅速爆炸式增长。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_51.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_52.png)

如果你有大量预测变量并希望缩减这个空间，可以使用主成分分析等因子分析技术来降低协变量空间的维度。然而，这些方法也有代价：你得到的主成分或因子可能不如原始数据易于解释。这部分内容在多变量分析或机器学习课程中会有更深入的探讨。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_54.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_55.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_56.png)

在本课程中，我们主要考虑预测变量数量相对较少的情况，模型选择将是一个结合分析师、数据和科学背景的高度交互过程。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_57.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_58.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_59.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_60.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_61.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_62.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_63.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_64.png)

## 实验设计的作用 🧪

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_66.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_67.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_69.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_71.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_72.png)

我想提到的另一点是，良好的实验设计通常可以消除大量模型讨论的必要性。我们之前讨论过随机化如何能有效避免许多问题，例如使我们感兴趣的变量与那些我们不感兴趣甚至未知的干扰变量无关。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_74.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_76.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_78.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_79.png)

然而，设计还有其他方面可以达到相同目的。例如：
*   **分层与区组内随机化**：经典的例子是田间作物实验。如果你要试验不同的种子，你可能会根据田地的不同区域进行“区组”划分，然后将不同种子随机分配到这些区组中。
*   **交叉设计**：在生物统计学中非常常见。例如，比较两种阿司匹林时，不是让两组不同的人分别服用一种，而是让同一组人在不同时期先后服用两种阿司匹林（通常会随机化服药顺序），这样每个人都可以作为自身的对照，从而控制个体间的固有差异。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_80.png)

实验设计是一个相当广泛的领域。我想强调的更广泛的要点是：**深思熟虑的良好实验设计，通常可以消除在单纯观察性数据建模过程中必须考虑的许多主要问题。**

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_82.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_83.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_84.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_85.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_86.png)

## 一个实用的方法：嵌套模型检验 🔗

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_88.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_89.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_90.png)

最后，我想介绍一种我非常喜欢且觉得非常有用的自动化模型搜索技术：**查看嵌套模型**。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_91.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_92.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_93.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_95.png)

我通常对某个特定变量（例如某种处理效应）非常感兴趣，但又担心处理组在其他变量（如年龄、性别）上不平衡，这些变量可能会影响结果。这时，嵌套模型分析就很有用。

以下是进行嵌套模型检验的思路：
1.  拟合一个只包含核心变量（如“处理”）的模型。
2.  拟合一个包含核心变量和一个潜在混杂变量（如“年龄”）的模型。
3.  拟合一个包含核心变量和多个潜在混杂变量（如“年龄”和“性别”）的模型。
以此类推。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_97.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_98.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_99.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_100.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_101.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_102.png)

**嵌套模型**是指每一个后续模型都完全包含了前一个模型的所有项。这为检验每个新增的变量集是否必要提供了一种非常简便的方法。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_103.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_104.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_105.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_106.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_107.png)

以下是如何在R语言中进行嵌套模型检验的示例代码。我们使用`swiss`数据集，假设我们关注的核心变量是`Agriculture`（农业）。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_109.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_110.png)

```r
# 拟合三个嵌套线性模型
fit1 <- lm(Fertility ~ Agriculture, data = swiss)
fit3 <- lm(Fertility ~ Agriculture + Examination + Education, data = swiss)
fit5 <- lm(Fertility ~ Agriculture + Examination + Education + Catholic + Infant.Mortality, data = swiss)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_111.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_112.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_113.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_114.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_115.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_116.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_117.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_119.png)

# 使用anova函数进行嵌套模型比较
anova(fit1, fit3, fit5)
```

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_121.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_122.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_123.png)

`anova`函数会列出模型，并给出残差平方和、自由度等。通过计算F统计量和对应的P值，它可以检验新增的变量集是否提供了显著的额外解释力。

例如，输出可能会显示，在模型1（仅有`Agriculture`）基础上加入`Examination`和`Education`是必要的；同样，在模型3基础上再加入`Catholic`和`Infant.Mortality`也是必要的。

**要点**：当你感兴趣的分析思路自然形成一系列逐步复杂的嵌套模型时（尤其当你专注于某个特定变量时），嵌套模型检验是一个合理且有用的方法。**但这种方法仅适用于模型是嵌套的情况**。对于非嵌套模型的比较，你需要使用信息准则等其他方法，这通常在我们的预测课程中涉及。

## 总结 📝

本节课中我们一起学习了：
1.  **模型选择对残差方差的影响**：遗漏重要变量会使方差估计有偏，而包含不必要变量则会降低估计的精确性。
2.  **自动化模型选择的复杂性**：在变量较多时，模型空间巨大，需借助其他技术或依赖于具体情境的交互式选择。
3.  **实验设计的重要性**：良好的随机化、分层、交叉设计等可以从源头减少对复杂模型调整的依赖。
4.  **嵌套模型检验**：当分析围绕一个核心变量展开，并逐步控制其他变量时，这是一种检验变量必要性的有效且直观的方法。

最后，我们必须意识到，模型几乎总是不完美的。正如统计学家乔治·博克斯的名言：**“所有的模型都是错的，但有些是有用的。”** 我们的目标不是找到一个完全正确的模型，而是找到一个能帮助我们从中学习数据真相的有用透镜。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_125.png)

希望本讲座为你提供了一些可用的模型选择技巧，并加深了对模型构建后果的理解。我们下节课再见。