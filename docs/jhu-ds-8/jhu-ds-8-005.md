# 005：预测研究设计 📊

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_0.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_2.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_3.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_5.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_6.png)

在本节课中，我们将学习如何设计一个稳健的预测研究，以最小化样本内误差与样本外误差带来的问题。我们将重点介绍数据分割、基准测试以及避免过拟合的关键原则。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_8.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_9.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_10.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_11.png)

上一节我们介绍了样本内误差、样本外误差以及过拟合的概念。本节中，我们来看看如何通过合理的预测研究设计来缓解这些问题。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_13.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_14.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_15.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_16.png)

## 定义误差率 📈

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_18.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_19.png)

在预测研究设计中，首要步骤是定义误差率。本节我们将使用一个通用的误差率概念。在下一讲中，我们将详细探讨可供选择的不同误差率类型。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_20.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_21.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_22.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_23.png)

## 数据分割 📂

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_25.png)

接下来，需要将用于构建和验证模型的数据分割成几个部分。以下是数据分割的核心组成部分：

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_26.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_27.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_28.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_29.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_30.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_31.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_32.png)

*   **训练集**：必须创建，用于构建模型。
*   **测试集**：用于评估模型性能。
*   **验证集**：可选，也用于验证模型。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_34.png)

## 模型构建流程 🔄

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_35.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_36.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_37.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_38.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_39.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_40.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_41.png)

在训练集上，我们进行特征选择和模型构建。例如，可以使用交叉验证等技术来挑选对模型最重要的特征，并确定预测函数及其参数。整个过程可以概括为：**在训练集上构建模型**。

## 应用模型至测试集 ⚠️

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_43.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_44.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_45.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_46.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_47.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_48.png)

如果没有验证集，我们需要将得到的最佳模型**仅应用一次**于测试集。原因在于，如果在测试集上尝试多个模型并选择表现最好的一个，就相当于在某种程度上用测试集“训练”了模型，这会导致对模型在新数据上的误差产生过于乐观的估计。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_49.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_50.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_51.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_52.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_53.png)

## 包含验证集的情况 🔍

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_55.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_56.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_57.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_58.png)

如果同时存在验证集和测试集，流程会略有不同。你可以将多个最佳预测模型应用于测试集，并根据结果进行微调。例如，你可能会发现某些特征在样本外预测中效果不佳，从而调整模型。但同样，此时测试集误差对于真实的样本外误差来说仍然是偏乐观的。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_59.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_60.png)

因此，我们最终需要将**仅一个**最佳模型**仅应用一次**于验证集，以获得对样本外误差率的良好估计。核心思想是：从一开始就预留一个数据集，你只对其应用一个最终模型，且不进行任何训练、调优或测试。

## 了解基准线 📊

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_62.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_63.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_64.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_65.png)

在进行预测时，了解基准线非常重要。例如，在Kaggle竞赛的排行榜上，通常会提供基准线（如图表中灰色标记所示），比如“将所有预测值设为零”的结果。了解这些基准线有助于判断你的预测算法是表现异常出色还是存在明显问题。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_67.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_68.png)

## 实例：Netflix竞赛 🎬

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_69.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_70.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_71.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_72.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_73.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_74.png)

Netflix竞赛的研究设计是一个经典案例。他们拥有1亿条用户-电影评分数据，并将其分割为：
1.  **训练集**：提供给参赛者构建模型。
2.  **探测集**：参赛者可用其评估模型在提交前的样本外误差。
3.  **测验集**：参赛者不可见，但可多次提交预测结果以调整模型。
4.  **测试集**：在竞赛最终阶段，**仅应用一次**最佳模型，以获得对全新数据的无偏性能估计。

这个设计至关重要。事实证明，一些在测验集上表现优异的团队，在最终测试集上反而表现不佳，这正是因为他们对测验集产生了过拟合。这个案例给我们的重要启示是：构建预测模型时，必须始终预留一个完全独立的数据集。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_76.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_77.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_78.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_79.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_80.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_81.png)

## 注意样本量问题 🎯

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_82.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_83.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_84.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_85.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_86.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_87.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_89.png)

将数据分割为训练集、测试集和验证集时，需注意避免子集过小，尤其是测试集。假设我们预测一个二分类结果（如患病/健康），一个极端简单的分类器是抛硬币。

*   对于单个测试样本，即使模型预测准确率达到100%，你也有50%的概率仅凭抛硬币就达到这个结果。
*   公式：`P(完美分类) = (1/2)^n`，其中 `n` 是测试集样本量。
*   当 `n=2` 时，100%准确率的概率为25%。
*   当 `n=10` 时，100%准确率的概率仅为约0.1%。

这表明，我们必须确保测试集等子集有足够大的样本量，才能确信观察到的良好预测性能不是偶然获得的。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_91.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_92.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_93.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_94.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_95.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_96.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_97.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_98.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_99.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_100.png)

## 数据分割的经验法则 📝

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_101.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_102.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_103.png)

以下是一些常用的经验法则（并非绝对）：
*   **大样本量**：60% 训练集，20% 测试集，20% 验证集。
*   **中等样本量**：60% 训练集，40% 测试集（此时可能没有独立的验证集进行最终评估）。
*   **小样本量**：可能需要重新考虑是否足以构建预测模型。如果坚持构建，则通常使用交叉验证，并需明确指出样本量小且未在独立测试集上进行评估的局限性。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_105.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_106.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_107.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_108.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_109.png)

## 核心原则总结 ✅

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_110.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_111.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_113.png)

最后，我们总结一些预测研究设计的核心原则：
1.  **测试集/验证集隔离原则**：测试集或最终的验证集必须被预留，在模型构建过程中**绝不能**查看或使用。你只能将最终选定的一个模型应用其上**一次**。
2.  **随机抽样**：训练集和测试集应通过随机抽样获得。对于时间序列等具有依赖结构的数据，抽样时需保持数据块（如时间段）的完整性，这称为“回测”。
3.  **数据代表性**：所有数据子集应尽可能反映数据的整体多样性。随机分配通常能做到这一点，有时也可以考虑按特征进行平衡抽样。

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_114.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_115.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_116.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_117.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_119.png)

![](img/f60e2c7e1b47952715fc1bd35d1aa6bb_120.png)

本节课中，我们一起学习了预测研究设计的关键步骤：从定义误差率、合理分割数据（训练集、测试集、验证集），到在独立数据集上单次评估模型的重要性。我们还通过Netflix竞赛的实例和样本量影响的讨论，理解了避免过拟合和获得可靠样本外误差估计的核心原则。记住这些设计原则，是构建有效、稳健机器学习模型的基础。