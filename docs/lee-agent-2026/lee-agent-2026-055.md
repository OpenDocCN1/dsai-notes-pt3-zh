# 55：大型语言模型快速入门 🚀

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_1.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_3.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_5.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_7.png)

## 概述
在本节课中，我们将要学习大型语言模型（如ChatGPT）的基本原理、发展历程以及如何有效地使用它们。我们将从模型的核心运作机制开始，逐步了解其训练过程，并学习一些实用的使用技巧。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_9.png)

## 大型语言模型的能力展示

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_11.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_13.png)

上一节我们介绍了课程概述，本节中我们来看看大型语言模型在实际应用中的表现。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_15.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_17.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_19.png)

大型语言模型最知名的代表是ChatGPT。我们通过一个线性代数期中考试的是非题来测试它的能力。我们将五道题目原封不动地输入给GPT-4。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_21.png)

以下是测试结果：
*   第一题：题目询问矩阵方程的解。GPT-4的答案是“错误”，这是正确答案。但其推理过程存在误解，它默认了矩阵是可逆的方阵，而题目并未给出此条件。因此，这题答对有一定运气成分。
*   第二题：题目关于矩阵的列空间。GPT-4答对。
*   第三题：题目关于矩阵的秩。GPT-4答对。
*   第四题：题目关于行列式`det(AB) = det(BA)`。GPT-4判断为“正确”，但这是一个陷阱题。该性质仅在A和B均为方阵时成立，题目未说明。GPT-4答错。
*   第五题：一个基本概念题。GPT-4答对。

整体而言，GPT-4在五题中答对四题。其中三题它真正理解，另外两题陷阱题则一题猜对、一题猜错。这展示了当前人工智能的能力水平。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_23.png)

此外，GPT还能执行其他任务：
*   **出题**：可以要求它生成线性代数考题。
*   **创意写作**：可以提供范例（如“五条体”），让它用特定文体描述线性代数期中考。
*   **定制化应用**：利用OpenAI的GPTs功能，可以快速创建专属的AI助手。例如，上传课程讲义后，就能创建一个知道特定课程作业内容和截止日期的“线性代数AI助教”。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_25.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_27.png)

## 大型语言模型的原理

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_29.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_31.png)

上一节我们看到了模型的能力，本节中我们来看看这些能力背后的核心原理。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_33.png)

ChatGPT的名字揭示了其关键特征：
*   **Chat**：聊天，设计用于对话。
*   **G**：生成式，属于生成式AI。
*   **P**：预训练，是其成功的关键技术。
*   **T**：Transformer，是其背后的神经网络架构。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_35.png)

其核心运作原理可以用四个字概括：**文字接龙**。模型唯一做的事情就是预测一个不完整句子后面最可能接什么字（符号）。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_37.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_39.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_41.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_42.png)

**公式/代码描述核心概念**：
对于一个输入序列 `x1, x2, ..., xt`，语言模型计算下一个符号的概率分布：
`P(xt+1 | x1, x2, ..., xt)`
然后，模型根据这个分布“掷骰子”，选择下一个符号输出，并不断重复此过程，直到生成结束符。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_44.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_46.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_48.png)

具体回答问题的过程如下：
1.  用户输入问题：“台湾最高的山是哪座？”
2.  模型将此视为不完整句子，预测下一个最可能的字是“玉”，于是输出“玉”。
3.  模型将“玉”附加到输入后，新的输入变为“台湾最高的山是哪座？玉”，再预测下一个最可能的字是“山”，输出“山”。
4.  继续此过程，可能输出结束符，最终答案“玉山”生成完毕。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_50.png)

模型的实际输出是一个所有可能符号（称为**token**）的概率分布。Token是模型处理文本的基本单位，可能是一个字根、一个汉字或一个标点。模型根据概率分布随机采样（掷骰子）得到输出，这解释了为何同一问题每次回答可能不同。完全选择最高概率的词（贪婪解码）可能导致重复、不自然的文本，因此通常采用随机采样。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_52.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_54.png)

正因为模型只做文字接龙，不在意事实，所以它有时会“胡诌”或提供不存在的信息（如虚构一个“台大玫瑰花节”及其网址）。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_56.png)

模型能进行多轮对话，是因为它在做文字接龙时，会将同一对话历史中所有的用户输入和模型输出都作为上下文输入，从而“记住”之前的对话内容。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_58.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_60.png)

## 模型的学习与训练

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_62.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_64.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_66.png)

上一节我们了解了模型如何运作，本节中我们来看看它是如何获得这些能力的。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_68.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_70.png)

模型通过阅读海量文本学习文字接龙。每一句话都是教材。例如，从句子“人工智慧真神奇！”中，模型可以学到：
*   输入“人”，后面很可能接“工”。
*   输入“人工”，后面很可能接“智”。
*   以此类推。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_72.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_74.png)

互联网提供了近乎无限的训练资料。模型背后是一个极其复杂的函数（基于Transformer架构的神经网络），其参数数量高达百亿甚至千亿级。这些参数通过在海量数据上调整，最终学会了预测下一个token的概率分布。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_76.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_77.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_79.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_81.png)

**发展历程**：
*   **GPT (2018)**：参数量1.17亿，训练数据1GB。能力有限。
*   **GPT-2 (2019)**：参数量15亿，训练数据40GB。尝试多种任务（问答、摘要），但表现一般（正确率约55%），远低于人类（90%）。
*   **GPT-3 (2020)**：参数量1750亿，训练数据580GB（相当于阅读《哈利波特》全集30万遍）。能力显著提升，例如可以编写代码，但在许多任务上平均正确率仍仅约50%。
    *   问题在于，GPT-3像在“荒野中长大”，只从网络文本学习，不懂人类社会的规则和具体指令。例如，问它代码含义，它可能不直接回答，而是生成选择题选项。
*   **从GPT-3到ChatGPT (GPT-3.5)**：关键突破在于引入了**人类反馈**。
    *   **监督微调**：人类提供“问题-标准答案”对，直接教模型如何正确回答。这只需要数万条数据，效果显著。有监督学习的小模型性能可超越无监督学习的大模型。
    *   **从人类反馈中强化学习**：人类不再提供标准答案，而是对模型的多个回答进行排序（哪个更好）。模型根据这种偏好反馈进行学习，进一步提升回答质量。
    *   整个让模型对齐人类意图的过程称为 **Alignment**。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_82.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_84.png)

**预训练** 让模型拥有了广泛的知识和语言能力（“天资”），而**监督微调**和**RLHF**则是画龙点睛，教会模型如何将这些能力用于服务人类需求。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_86.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_88.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_89.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_90.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_91.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_93.png)

## 有效使用大型语言模型的技巧

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_95.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_97.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_98.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_100.png)

上一节我们介绍了模型的训练，本节中我们来看看如何更好地使用它们。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_102.png)

模型能力强大，但需要用户有效引导才能发挥最大效用。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_104.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_106.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_108.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_110.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_111.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_113.png)

以下是激发模型潜力的关键技巧：

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_114.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_116.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_118.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_120.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_122.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_124.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_125.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_126.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_128.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_130.png)

**1. 明确需求**
模型表现不佳有时是因为指令模糊。你需要清晰说明要求。
*   **润色文本**：不要说“润色以下段落”，而应说“修正以下段落的文法错误”或“将以下文字改写得更加正式”。
*   **控制输出**：指定语言、格式、长度（如“用英文扩写至300字以上”）。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_132.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_134.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_136.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_138.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_139.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_140.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_141.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_143.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_145.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_147.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_148.png)

**2. 提供背景信息**
不要让模型凭空创造，应提供相关材料。
*   **撰写游记**：先告诉它你早上、下午、晚上去了哪里，再让它据此撰写。
*   **指定风格**：进一步要求“用IG网红的口吻撰写，加入表情符号”。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_150.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_151.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_153.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_155.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_157.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_159.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_161.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_163.png)

**3. 提供范例**
对于复杂或特定格式要求，提供例子最有效。
*   **生成特定文体**：如“五条体”或“晶晶体”（中英夹杂），先给一两个例子，模型就能模仿。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_165.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_166.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_167.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_168.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_169.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_170.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_171.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_172.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_174.png)

**4. 鼓励逐步思考**
在解决推理问题时，要求模型“一步一步思考”能大幅提升准确性。
*   **数学问题**：直接问“鸡兔同笼”问题，正确率可能为0；加上“请详细列出计算过程”，正确率可升至80%。
*   **魔法提示词**：诸如“Let‘s think step by step.”或“请深呼吸，然后一步步解答。”等提示词被证明能有效提升模型表现。甚至可以用一个AI来为另一个AI优化这些提示词。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_176.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_178.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_179.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_181.png)

**5. 利用文件上传功能**
GPT-4支持上传文件（如PDF、Word），可让其处理文档内容。
*   **阅读论文**：上传论文后，可让其总结、解释各章节内容，甚至生成报告大纲或幻灯片要点。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_183.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_184.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_185.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_187.png)

**6. 使用外部工具/插件**
模型可以调用外部工具来弥补自身不足（如无法获取实时信息、无法计算）。
*   **搜索信息**：启用联网搜索或学术搜索插件，让模型基于真实资料回答，减少“胡诌”。但需注意，它仍是对搜索结果进行文字接龙，并非绝对可靠。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_189.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_191.png)

**7. 分解复杂任务**
将大任务拆解为模型能处理的小步骤。
*   **撰写小说**：先让模型规划故事背景、人物设定、章节大纲，再分章节撰写，可保持情节和人物一致性。
*   **让模型自己规划**：你可以要求模型“将[某个复杂任务]拆解为易于执行的步骤”。例如，让GPT-4规划如何将YouTube频道的影片构建成“学习地图”，它能列出收集数据、内容摘要、分类等步骤。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_193.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_194.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_196.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_197.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_198.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_200.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_201.png)

**8. 利用其反省能力**
高级模型（如GPT-4）具备一定的自我验证能力。
*   **检查事实**：当模型给出一个可能错误的答案（如介绍“台大玫瑰花节”）后，你可以要求它“检查上述资讯是否正确”。GPT-4有时能发现自己的错误并更正。而GPT-3.5则可能只是机械地道歉而不真正修正。

**9. 与环境互动（前沿研究）**
通过将视觉信息转化为文字描述，并将模型的文字输出转化为具体动作指令，大型语言模型有望与物理世界互动（如指挥机械臂完成“把桌上的东西放进背包”的任务）。这仍是活跃的研究领域。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_203.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_204.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_206.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_208.png)

## 总结
本节课中我们一起学习了大型语言模型的核心知识。我们了解到以ChatGPT为代表的模型，其本质是**基于海量数据预训练、并通过人类反馈进行对齐的、从事文字接龙任务的复杂函数**。它的强大能力源于**巨量参数**、**海量文本预训练**以及关键的**监督微调**和**从人类反馈中强化学习**。最后，我们学习了一系列实用技巧，包括**明确指令、提供信息与范例、鼓励逐步思考、分解任务**等，以帮助我们更有效地与这些AI工具协作，激发其最大潜力。

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_210.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_212.png)

![](img/b97a77aa061fee1bda93e5a24d0e9eb7_214.png)

---
**注**：本教程根据李宏毅教授课程内容整理，聚焦于核心原理与使用逻辑的阐述，已删除原视频中的语气词、互动及具体演示操作细节，并按照要求进行了结构化重组和简化表述。