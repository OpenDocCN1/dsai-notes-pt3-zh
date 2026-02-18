# 18：李宏毅机器学习课程 - 作业七 (HW7) 教程 🧠

![](img/fcd5a1e4bceb5baed30332b9358a103c_1.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_3.png)

在本节课中，我们将学习如何完成作业七（HW7），其核心内容是使用**直接偏好优化 (DPO)** 方法对大语言模型进行价值观对齐。我们将了解DPO与监督微调的区别，并动手调整超参数来观察模型行为的变化。

---

## 概述：从监督微调到偏好对齐

![](img/fcd5a1e4bceb5baed30332b9358a103c_5.png)

上一节我们介绍了监督微调（SFT），它需要为模型提供标准答案进行学习。但在面对开放性问题时，往往没有唯一正确答案。

![](img/fcd5a1e4bceb5baed30332b9358a103c_7.png)

本节中我们来看看**偏好对齐**方法，例如本次作业使用的**RLHF** 和 **DPO**。与SFT不同，这些方法旨在让模型学习人类的偏好，而非单一答案。例如，对于道德性问题，模型可能产生多种回答。我们的目标就是使用有限的资源，将模型与特定的价值观（例如，对“使用AI生成吉卜力风格图像”的态度）进行对齐。

最原始的方法是RLHF，但它存在一些缺点，相关论文阅读部分会进行讨论。本次作业我们使用**DPO** 来完成对齐任务。

![](img/fcd5a1e4bceb5baed30332b9358a103c_9.png)

---

![](img/fcd5a1e4bceb5baed30332b9358a103c_11.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_13.png)

## 任务目标：让模型对特定议题表态 🎯

![](img/fcd5a1e4bceb5baed30332b9358a103c_15.png)

本次作业的具体任务是：对齐模型，使其能对“使用AI生成吉卜力风格图像是否道德”这一问题，明确表达“同意”或“不同意”的立场。

我们将使用 **Llama-3-8B** 模型。在对齐前，模型对此问题的回答可能模棱两可（例如，“这是一个有趣的问题，值得讨论”）。DPO方法通过直接提供**被选中的回答** 和**被拒绝的回答** 进行学习，从而提高选中回答的概率，降低拒绝回答的概率。

![](img/fcd5a1e4bceb5baed30332b9358a103c_17.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_19.png)

我们使用的数据集是基于 **ChatGPT-3.5** 生成的偏好数据。

![](img/fcd5a1e4bceb5baed30332b9358a103c_21.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_23.png)

---

![](img/fcd5a1e4bceb5baed30332b9358a103c_24.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_25.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_27.png)

## 作业内容与步骤 📝

![](img/fcd5a1e4bceb5baed30332b9358a103c_29.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_31.png)

以下是本次作业需要完成的三个主要部分：

![](img/fcd5a1e4bceb5baed30332b9358a103c_33.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_35.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_37.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_39.png)

1.  **运行与实验**：在Colab上运行示例代码，调整超参数并观察结果。
2.  **回答问题**：根据实验观察，回答指定问题（提交至Gradescope）。
3.  **提交文件**：按照格式生成并提交指定的输出文件（提交至NTU COOL）。

![](img/fcd5a1e4bceb5baed30332b9358a103c_41.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_43.png)

### 第一部分：运行实验与调整超参数

![](img/fcd5a1e4bceb5baed30332b9358a103c_45.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_47.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_49.png)

首先，你需要运行Colab笔记本中的示例代码。核心任务是调整以下三个超参数，并观察它们对10条测试集结果的影响：

![](img/fcd5a1e4bceb5baed30332b9358a103c_50.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_52.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_54.png)

*   **`support_ratio`**：支持度比例，范围在0到1之间。
    *   `1` 表示完全支持使用AI生成吉卜力图像。
    *   `0` 表示完全反对。
*   **`data_size`**：用于训练的偏好数据条数。
*   **`num_epochs`**：训练轮数。例如，设为`3`意味着模型会遍历整个训练集3次。

![](img/fcd5a1e4bceb5baed30332b9358a103c_56.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_58.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_60.png)

代码已预设好LoRA等训练配置，你只需调整上述参数即可。**重要提示**：每次调整超参数重新训练前，务必重新加载原始的Llama-3-8B模型，否则会基于已对齐的模型继续训练，导致结果异常。

![](img/fcd5a1e4bceb5baed30332b9358a103c_62.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_64.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_66.png)

### 第二部分：观察与回答开放式问题

![](img/fcd5a1e4bceb5baed30332b9358a103c_68.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_70.png)

除了调整超参数，还需要探索以下问题并提交答案：

![](img/fcd5a1e4bceb5baed30332b9358a103c_72.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_74.png)

1.  **系统提示词长度的影响**：默认系统提示词限制回答在100字符内。如果延长系统提示词，模型的输出行为会如何变化？
2.  **不同动漫风格**：如果询问生成其他动漫风格（如《海贼王》、迪士尼）的图像，模型会如何回应？
3.  **不同艺术形式**：如果询问模仿其他艺术形式（如巴赫的音乐、大师画作），模型会如何回应？
4.  **中文提问**：用中文提问（例如，“生成吉卜力风格的艺术作品是否是道德的？”），并要求模型用中文回答，观察其表现。

![](img/fcd5a1e4bceb5baed30332b9358a103c_76.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_78.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_80.png)

### 第三部分：论文阅读 📚

![](img/fcd5a1e4bceb5baed30332b9358a103c_82.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_83.png)

需要阅读三篇论文并回答相关问题：

1.  **《Training language models to follow instructions with human feedback》**：了解ChatGPT前身InstructGPT中RLHF的部分。
2.  **《Direct Preference Optimization: Your Language Model is Secretly a Reward Model》**：DPO方法的原始论文。
3.  **《GRPO: Gradient-Free Preference Optimization for Learning Human Preferences》**：了解GRPO方法，这是一种公开了完整配方的方法。

问题主要涉及对论文中方法、论述和公式的理解与判断。

---

## 提交要求与注意事项 ⚠️

以下是具体的提交格式与规则：

![](img/fcd5a1e4bceb5baed30332b9358a103c_85.png)

**文件提交 (NTU COOL):**
*   将生成的四个输出文件打包成ZIP文件。
*   文件名格式必须为：`hw7_{student_id}_{support_ratio}_{data_size}_{num_epochs}.json`。
*   `student_id` 需使用小写字母。
*   请勿手动修改输出文件的内容。

![](img/fcd5a1e4bceb5baed30332b9358a103c_87.png)

**答案提交 (Gradescope):**
*   将所有观察结果、开放式问题答案及选择题答案提交至Gradescope。

![](img/fcd5a1e4bceb5baed30332b9358a103c_89.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_91.png)

**截止时间与规则:**
*   截止日期：5月23日 23:59。
*   不接受任何形式的补交或迟交。
*   **严禁抄袭**：保护好自己的答案，不要与他人分享，包括与ChatGPT的对话内容。抄袭与被抄袭者将同受处罚。初犯者作业计零分且总成绩乘以0.9，再犯者直接不及格。

![](img/fcd5a1e4bceb5baed30332b9358a103c_93.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_95.png)

如有问题，请优先在NTU COOL作业讨论区提问。如需私下联系，请发送邮件至助教邮箱，并在标题中注明“HW7”。

---

## 总结

本节课中，我们一起学习了如何使用DPO方法对大语言模型进行价值观对齐。我们明确了本次作业的目标是让模型对“AI生成吉卜力图像”的议题明确表态，并详细介绍了完成作业的三个步骤：调整超参数实验、回答观察性问题、阅读相关论文。最后，请务必遵守提交格式和学术诚信规则，按时完成作业。

![](img/fcd5a1e4bceb5baed30332b9358a103c_97.png)

祝你作业顺利！