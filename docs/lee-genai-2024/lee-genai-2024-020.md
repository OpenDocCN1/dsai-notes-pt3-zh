# 20：作业六：Learning from Human Preferences 👨‍🏫

![](img/47a75ac7a163c8ded7edfba7d91fb976_1.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_3.png)

在本节课中，我们将要学习如何让语言模型从人类的偏好中学习，即完成“价值观对齐”。我们将通过完成作业六，实践一种名为DPO的简化方法，来调整模型使其输出更符合我们期望的答案。

## 任务概述 🎯

本次作业的核心任务是**价值观对齐**。我们希望微调一个语言模型，使其输出的答案能够符合特定的人类偏好或价值观。例如，如果我们支持“动漫真人化”，那么经过调整的模型在回答相关问题时，应能输出支持该立场的回答，而不是中立或反对的答案。

## 核心概念：从监督学习到基于人类偏好的学习

上一节我们介绍了任务目标。本节中，我们来看看实现价值观对齐的两种主要方法及其区别。

![](img/47a75ac7a163c8ded7edfba7d91fb976_5.png)

**监督学习**适用于有标准答案的问题。其训练过程可以概括为：给定问题 `Q` 和标准答案 `A`，通过最小化损失函数来训练模型 `M`。

![](img/47a75ac7a163c8ded7edfba7d91fb976_7.png)

```
Loss = CrossEntropy(M(Q), A)
```

![](img/47a75ac7a163c8ded7edfba7d91fb976_9.png)

然而，对于许多开放式问题，答案没有绝对的对错，而是取决于个人价值观或立场。这时，我们需要**基于人类偏好的学习**方法。

**强化学习从人类反馈**是一种经典方法，但它需要额外训练一个奖励模型，且训练过程不稳定。因此，本次作业我们采用一种简化方法：**直接偏好优化**。

![](img/47a75ac7a163c8ded7edfba7d91fb976_11.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_13.png)

DPO的核心思想是，直接使用标注了人类偏好的数据来训练模型。对于每个问题，我们准备两种回答：一种是人类**偏好**的，另一种是**非偏好**的。模型的目标是学会提高输出偏好回答的概率，同时降低输出非偏好回答的概率。

## 作业具体内容与数据 📊

上一节我们了解了DPO的基本思想。本节中我们来看看本次作业要处理的具体问题和数据。

本次作业的主题是“同不同意动漫真人化”。我们将使用**联发科开发的Breeze-7B模型**，该模型能流利输出繁体中文。

![](img/47a75ac7a163c8ded7edfba7d91fb976_15.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_17.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_19.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_21.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_23.png)

以下是本次作业使用的数据说明：

![](img/47a75ac7a163c8ded7edfba7d91fb976_25.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_27.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_29.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_31.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_33.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_34.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_35.png)

*   **训练数据**：存储在 `labeled_data.json` 中，共50条。每条数据包含一个问题 `prompt`，以及两种立场的回答：`support`（支持）和 `oppose`（反对）。
*   **测试数据**：共10条，每条仅包含问题 `prompt`，用于评估训练后模型的输出。

![](img/47a75ac7a163c8ded7edfba7d91fb976_37.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_38.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_40.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_42.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_44.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_46.png)

## 操作流程与超参数调整 ⚙️

![](img/47a75ac7a163c8ded7edfba7d91fb976_48.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_50.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_52.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_54.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_56.png)

了解了任务和数据后，本节中我们将一步步完成作业。你需要遵循以下工作流程：

![](img/47a75ac7a163c8ded7edfba7d91fb976_58.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_60.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_62.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_64.png)

1.  运行助教提供的Colab示例代码。
2.  调整训练超参数，观察模型输出的变化。
3.  回答Report中的问题。
4.  使用“达哥”批改助教为自己的答案评分。
5.  提交评分记录和训练结果截图。

![](img/47a75ac7a163c8ded7edfba7d91fb976_66.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_68.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_70.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_72.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_74.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_76.png)

在Colab代码中，你需要调整以下三个关键超参数：

![](img/47a75ac7a163c8ded7edfba7d91fb976_78.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_80.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_82.png)

以下是需要调整的超参数及其说明：

![](img/47a75ac7a163c8ded7edfba7d91fb976_84.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_86.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_88.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_90.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_92.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_94.png)

1.  **支持比例**：一个介于0.0到1.0之间的值，用于决定有多少比例的训练数据用于训练模型“支持”的立场。例如，总数据50条，`support_ratio=0.6`，则前30条数据中的 `support` 回答被视为“偏好回答”，后20条数据中的 `oppose` 回答被视为“偏好回答”。
2.  **数据量**：用于训练的数据条数，取值范围在10到50之间。
3.  **训练轮数**：模型完整遍历训练数据集的次数。例如，`num_epochs=3` 表示模型会将50条数据看3遍。

![](img/47a75ac7a163c8ded7edfba7d91fb976_96.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_98.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_100.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_102.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_104.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_106.png)

## Report问题与评分 📝

![](img/47a75ac7a163c8ded7edfba7d91fb976_108.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_110.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_112.png)

上一节我们完成了模型训练。本节中我们来看看如何通过回答Report问题来总结你的观察。

你需要训练模型四次，以回答以下三个问题（每题3分）：

![](img/47a75ac7a163c8ded7edfba7d91fb976_114.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_116.png)

1.  **支持比例的影响**：固定 `data_size=50`, `num_epochs=3`，分别设置 `support_ratio=0` 和 `support_ratio=1`，观察模型在测试集上的输出有何不同。
2.  **训练轮数的影响**：固定 `data_size=50`, `support_ratio=1`，分别设置 `num_epochs=1` 和 `num_epochs=3`，观察模型在测试集上的输出有何不同。
3.  **数据量的影响**：固定 `num_epochs=3`, `support_ratio=1`，分别使用较少（如20条）和全部（50条）训练数据，观察模型在测试集上的输出有何不同。

![](img/47a75ac7a163c8ded7edfba7d91fb976_117.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_119.png)

**注意**：请聚焦于模型**输出内容立场**的变化，而非回答格式或长度。

![](img/47a75ac7a163c8ded7edfba7d91fb976_121.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_123.png)

回答完毕后，请使用“达哥”批改助教进行评分。**务必提交与达哥第一轮对话产生的JSON记录文件**，此文件包含你的Report得分（9分）。此外，还需从任意一次训练结果中，截图模型在测试集上的输出（1-2条即可），并保存为PDF提交。作业总分为10分。

![](img/47a75ac7a163c8ded7edfba7d91fb976_125.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_127.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_129.png)

## 重要规则与提交须知 ⚠️

在提交作业前，请务必仔细阅读以下规则：

以下是必须遵守的作业规定：

![](img/47a75ac7a163c8ded7edfba7d91fb976_131.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_133.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_135.png)

*   禁止任何形式的作弊，包括分享答案、修改评分记录文件等。
*   必须提交从“达哥”平台下载的**对话记录JSON文件**，手动创建或修改的文件将导致Report部分得零分。
*   截图文件必须为PDF格式，文件名需按要求命名。
*   作业提交截止时间为**4月25日 23:59:59**，逾期不候。

![](img/47a75ac7a163c8ded7edfba7d91fb976_137.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_139.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_140.png)

## 总结

![](img/47a75ac7a163c8ded7edfba7d91fb976_142.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_144.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_146.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_147.png)

![](img/47a75ac7a163c8ded7edfba7d91fb976_149.png)

本节课中我们一起学习了生成式AI中的“价值观对齐”概念。我们了解了DPO这种直接从人类偏好数据中学习的方法，并通过实践作业，调整了语言模型在“动漫真人化”议题上的输出立场。你学会了如何设置关键超参数，并观察它们对模型行为的影响。请按照流程完成训练、回答问题和提交，祝你作业顺利！