# 19：模型编辑 (Model Editing) 作业详解 📝

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_1.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_3.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_5.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_7.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_9.png)

在本节课中，我们将详细介绍李宏毅老师机器学习课程（2025）的第八次作业——模型编辑。我们将学习如何通过修改模型参数来更新或修正大型语言模型中的知识。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_11.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_13.png)

## 概述

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_15.png)

模型编辑技术旨在改变预训练模型的输出，以反映新的知识或修正错误的知识。上节课我们介绍了模型编辑的概念，本节课我们将通过实践作业，深入理解并应用三种主流的参数编辑方法：MEND、ROME 和 MEMIT。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_17.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_19.png)

## 作业核心任务

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_21.png)

本次作业包含三个主要部分：
1.  阅读 MEND、ROME 和 MEMIT 三篇论文并完成相关测验。
2.  应用这些方法到 GPT-2 XL 模型上，尝试改变其参数。
3.  通过修改代码，帮助模型编辑方法获得更好的性能。

请注意，本作业仅涉及修改模型参数的方法，不包含 IKE（不修改参数）的方法。

## 关键概念定义

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_23.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_25.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_27.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_29.png)

在开始实践前，我们需要明确定义几个核心概念。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_31.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_33.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_35.png)

### 编辑请求

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_37.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_39.png)

一个编辑请求用于描述我们希望更改的知识，它包含以下四个部分：
*   **提示词**：用于表述知识的句子。其格式通常包含主语、关系和宾语，但主语会用 `{}` 占位符表示，宾语会出现在句末。
    *   公式：`{subject} relation`
*   **主语**：知识陈述中的主体。
*   **新目标**：我们希望将该知识更改成的目标内容。
*   **真实目标**：模型在未编辑时，对给定提示词最可能生成的输出。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_41.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_43.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_45.png)

例如，若想将知识改为“史蒂夫·乔布斯是微软的创办人”：
*   提示词: `{} was the founder of`
*   主语: `Steve Jobs`
*   新目标: `Microsoft`
*   真实目标: `Apple` (因为模型原知识是“乔布斯创办了苹果”)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_47.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_49.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_51.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_53.png)

### 生成提示词与评估

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_55.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_57.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_59.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_61.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_63.png)

为了测试编辑效果，我们需要定义测试句子和评估指标。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_65.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_67.png)

以下是用于测试的五类生成提示词，每类对应一个句子：
1.  **原始提示词**：将编辑请求中的提示词主语 `{}` 替换为实际主语。
2.  **复述提示词**：表达与原提示词相同含义但措辞不同的句子。
3.  **邻近提示词**：与原提示词相似但语义无关的句子。
4.  **反转提示词**：将原提示词的主语和新目标互换位置。
5.  **推理提示词**：与原提示词有逻辑关联的句子。

评估指标采用准确率。一个预测结果被视为正确，当且仅当模型生成的文本以“提示词 + 真实目标（或新目标）”开头。

## 作业实践步骤

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_69.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_71.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_73.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_75.png)

上一节我们定义了作业的核心概念，本节中我们来看看具体的实践操作步骤。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_77.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_79.png)

### 第一部分：论文阅读测验

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_81.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_82.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_84.png)

首先，你需要完成论文阅读测验。
*   测验共有15题，每题0.4分，总计6分。
*   测验内容基于 MEND、ROME 和 MEMIT 三篇论文。
*   请在课程指定的在线平台（如 Gradescope）上找到并完成 “Homework 8 Model Editing Paper Reading” 部分。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_86.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_88.png)

### 第二部分：代码实践与单次编辑

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_90.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_92.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_94.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_96.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_98.png)

完成测验后，进入代码实践环节。作业提供了基础代码，默认使用微调方法，你需要将其改为 ROME 方法。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_100.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_102.png)

以下是需要完成的具体步骤：

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_104.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_106.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_108.png)

首先，修改主函数以启用 ROME 方法。
1.  在 `rome_function` 中，找到 `update_matrix = ...` 这行代码。
2.  根据 ROME 论文中的公式，此更新矩阵应是两个向量的外积。
3.  由于 GPT-2 XL 的权重矩阵经过转置，实际代码实现时需要注意维度。正确的实现形式类似于两个张量的外积。
    *   代码提示：`update_matrix = tensor1 @ tensor2.T`
4.  修改完成后，注释掉调用微调方法的代码，并取消注释调用 ROME 方法的代码。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_110.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_112.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_114.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_116.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_118.png)

接下来，定义你自己的编辑请求和生成提示词。
1.  在代码的 `request` 部分，根据之前的概念定义，填写你自己的 `prompt`, `subject`, `target_new`, `target_true`。
2.  在 `generation_prompts` 部分，为你定义的知识编写上述五类测试句子。
3.  **重要**：请使用自己构思的知识和句子，不要抄袭示例或其他同学的答案。

运行代码并报告结果。
1.  运行修改后的代码，模型会输出编辑前和编辑后对每个生成提示词的补全结果。
2.  在 Gradescope 的实验报告部分，提交你的编辑请求、五个生成提示词以及编辑后的生成结果。
3.  最后，根据结果判断五类生成提示词中哪些被成功编辑，并完成对应的选择题。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_120.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_122.png)

### 第三部分：多次编辑与不同方法

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_124.png)

在完成单次编辑后，我们将进行多次编辑实验，并尝试另一种方法。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_126.png)

首先，使用 ROME 方法编辑一个数据集中的前10条知识。
1.  代码中已预设使用一个从 COUNTERFACT 数据集中抽取的子集。
2.  运行代码后，系统会输出编辑前后的多项分数，包括：效能分数、复述分数、邻近分数和推理分数。
3.  在 Gradescope 上报告编辑后的这四项分数。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_128.png)

接着，使用 ROME 方法编辑数据集中的全部知识。
1.  修改代码中关于数据范围的设置，从编辑前10条改为编辑全部数据。
2.  再次运行代码，并报告编辑后的四项分数。

最后，使用 MEMIT 方法进行编辑。
1.  参考 MEMIT 论文和提供的代码提示，修改代码以使用 MEMIT 方法。
2.  对全部数据运行 MEMIT 编辑，并报告编辑后的四项分数。

## 作业提交与评分

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_130.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_132.png)

本节课我们一起学习了模型编辑的实践操作，最后来了解作业的提交方式和评分规则。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_134.png)

*   **提交方式**：将你的代码文件打包，以 `学号_homework8.zip` 的格式提交。解压后应包含一个以你学号命名的文件夹，里面是所有相关文件。
*   **评分构成**：
    *   论文阅读测验：15题，共6分。
    *   实验报告：共4分。
        *   单次编辑报告：1分。
        *   多次编辑报告（ROME前10条、ROME全部、MEMIT全部）：每次1分，共3分。
*   **重要规则**：
    *   必须使用指定的 GPT-2 XL 模型。
    *   严禁抄袭、分享自己的提示词、代码或答案。
    *   迟交的作业将不被接受。

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_136.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_138.png)

## 总结

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_140.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_142.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_144.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_146.png)

![](img/c0b7c90900b8f80ddc9de5827bfa0faf_148.png)

在本节课中，我们一起学习了模型编辑作业的完整流程。我们从定义编辑请求和评估方法开始，逐步完成了论文阅读、代码修改（实现 ROME 方法）、设计并测试单条知识编辑，最后扩展到对数据集的多次编辑并尝试了 MEMIT 方法。通过本次实践，你应该对如何直接修改大语言模型内部参数以更新知识有了更深入的理解。