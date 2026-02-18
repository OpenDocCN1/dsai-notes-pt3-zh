# 67：作业四：成为AI催眠大师 🧙‍♂️

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_1.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_2.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_3.png)

在本节课中，我们将学习第四次作业“成为AI催眠大师”的具体内容与操作方法。本次作业的核心是学习如何通过设计有效的提示词（Prompt）来引导和“催眠”Gemini大语言模型，使其更擅长解决数学问题。我们将详细介绍作业目标、操作步骤、评分标准以及常见问题。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_5.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_7.png)

## 概述：作业目标与核心概念

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_9.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_11.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_13.png)

上一节我们介绍了大模型的基本应用。本节中，我们来看看如何通过“提示工程”来优化模型的输出。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_15.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_17.png)

本次作业的目标是设计一个提示词（Prompt），用以提升Gemini模型在解决特定数学问题集上的表现。其核心在于理解并应用“提示工程”的概念：通过精心设计的文本指令，引导大模型生成更符合我们期望的答案。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_19.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_21.png)

一个关键的实现细节是使用**占位符（Placeholder）**。在你的提示词中，必须包含 `{{QUESTION}}` 这个占位符。在运行时，系统会自动将具体的数学问题替换到这个位置。这允许你设计一个通用的提示词模板，用于所有问题。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_23.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_25.png)

**核心代码/公式描述：**
```
你的提示词 = “你设计的引导文本... {{QUESTION}} ...更多的引导文本”
实际发送给模型的文本 = 你的提示词.replace(“{{QUESTION}}”, 当前的具体数学问题)
```

## 作业内容详解：从问题到提示词

接下来，我们具体看看作业要求我们做什么。

我们将使用Google Colab环境，并调用Gemini API。你需要准备一个Gemini API Key。作业提供了30道公开的数学问题（Public Set）供你测试和优化提示词。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_27.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_29.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_31.png)

你的任务是：设计一个提示词，当它与任意一道数学问题结合后，能引导Gemini模型正确解题。例如，一个简单的提示词可以是：“请一步步仔细思考并解答以下数学问题：{{QUESTION}}”。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_33.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_35.png)

以下是作业的具体操作流程，分为几个主要步骤：

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_37.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_39.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_41.png)

1.  **环境准备**：在Colab中设置环境，安装必要套件，并配置你的Gemini API Key。
2.  **设计提示词**：在指定区域编写你的提示词，确保包含 `{{QUESTION}}` 占位符。
3.  **测试与评估**：使用提供的30道题目测试你的提示词，系统会给出一个在Public Set上的正确率（Accuracy）。
4.  **保存与提交**：将你认为效果最好的提示词保存为JSON文件，并提交到课程系统。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_43.png)

## 操作指南：Colab环境 step-by-step

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_45.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_46.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_48.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_50.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_52.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_54.png)

上一节我们了解了作业的抽象流程，本节中我们来看看在Colab中的具体操作步骤。作业提供了两种操作界面：Gradio网页界面和纯代码界面，功能完全相同。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_56.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_58.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_60.png)

以下是关键步骤的详细说明：

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_62.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_64.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_66.png)

*   **步骤一：环境设置**
    首先，你需要点击“在云端硬盘中保存副本”，以获得编辑权限。请务必在“更改运行时类型”中确保硬件加速器选择为“**CPU**”，本次作业不需要GPU。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_68.png)

*   **步骤二：配置API Key**
    在对应的代码单元格中，填入你的Gemini API Key并执行单元格。这是调用模型的基础。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_70.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_72.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_74.png)

*   **步骤三：设计你的提示词**
    这是作业的核心部分。你需要在指定的文本框中输入你的提示词。
    **重要规则**：提示词中必须包含 `{{QUESTION}}` 占位符，且总长度不能超过1024个token。

*   **步骤四：测试提示词**
    你可以选择用全部30题或部分题目进行测试。点击“Evaluate”后，系统会将你的提示词逐一应用于每道题目，调用Gemini模型并评估答案是否正确。这个过程可能需要一些时间。

*   **步骤五：查看结果与保存**
    测试完成后，你可以查看每道题目的详细解题过程和最终的正确率。如果对结果满意，点击“Save Prompt”按钮，你的提示词就会被保存到名为 `prompt.json` 的文件中。你可以下载这个文件用于提交。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_76.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_77.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_79.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_81.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_83.png)

## 评分标准与提交须知

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_85.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_87.png)

设计好提示词后，我们需要了解如何评分以及如何提交。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_89.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_91.png)

最终成绩基于两个数据集：
1.  **Public Set**：你们用于测试的30道题。正确率 **>= 60%** 即可获得该部分基础分（5分）。
2.  **Private Set**：助教持有的100道未公开题目。最终评分主要依据模型在此数据集上的表现，设有不同正确率阈值对应不同加分（最高5分）。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_93.png)

**评分逻辑**：对于每道题，模型会生成3次答案。只有当至少2次答案正确时，该题才计为正确。最终正确率 = 正确题数 / 总题数。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_95.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_97.png)

**提交规则**：
*   你需要提交**两个**不同的提示词。
*   请将两个提示词分别保存为 `prompt.json`，并提交到系统中**两个不同的作业提交区域**。
*   最终成绩取你两个提示词中在 **Private Set** 上得分较高的那个进行计算。
*   **请勿**将两个提示词提交到同一个区域。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_99.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_101.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_103.png)

**重要提醒**：Public Set和Private Set是**完全不同**的题目。在Public Set上表现好，不代表在Private Set上也能获得高分。这模拟了机器学习中训练集和测试集分布不同的真实情况。

## 常见问题与故障排除

在操作过程中，你可能会遇到一些错误。以下是常见问题及其解决方法：

以下是可能遇到的错误列表：

*   **错误：`cast content must not be empty`**
    **原因与解决**：这是因为你在提示词文本框为空的情况下点击了“Set Prompt”。请先输入有效的提示词。

*   **错误：`Timeout` 或 `None returned`**
    **原因与解决**：这通常是因为Gemini API响应过长或无响应。首先尝试**重启整个Colab运行时**（Runtime -> Restart runtime）。如果问题依旧，可能是你的提示词导致模型生成长文本卡住，请尝试简化你的提示词。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_105.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_107.png)

*   **频繁出现 `Connection aborted` 日志**
    **原因与解决**：这是网络波动的常见提示，通常**可以忽略**，评估过程会继续执行，一般不影响最终结果。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_109.png)

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_111.png)

如果遇到未列出的错误，请首先查看Colab单元格执行输出下方的错误信息，并优先在课程讨论区提问。

## 技巧提示与总结

最后，我们提供一些设计提示词的思路，并总结本节课的内容。

如果你不知从何下手，可以参考以下提示词设计策略：

*   **零样本思维链（Zero-shot Chain of Thought）**：在提示词中鼓励模型逐步推理，例如：“让我们一步步思考这个问题：{{QUESTION}}”。
*   **上下文学习（In-Context Learning）**：在提示词中提供一个或几个解题示例，让模型模仿。
*   **角色扮演与情绪激励**：为模型设定一个角色（如“数学专家”），或使用激励性语言，可能影响其输出质量。

![](img/a3b933f3a350e6d9b03fdbacae1e89f1_113.png)

**本节课总结**
在本节课中，我们一起学习了如何通过提示工程来优化大语言模型在特定任务（数学解题）上的表现。我们掌握了作业的核心——设计包含 `{{QUESTION}}` 占位符的提示词，并在Colab环境中完成了从配置、测试到保存的完整流程。同时，我们明确了作业的评分规则和提交要求。请记住，探索不同提示词带来的效果变化，是本次作业最重要的学习目标。祝你成为出色的“AI催眠大师”！