# 62：作业3：使用AI API搭建应用 🛠️

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_0.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_2.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_4.png)

在本节课中，我们将学习如何利用AI模型的API（应用程序编程接口）来快速搭建自己的应用程序。我们将从理解API的概念开始，逐步学习如何使用Google Colab编写代码、使用Gradio创建可视化界面，并最终完成三个具体的AI应用任务。

---

## 概述：什么是API？ 🤔

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_6.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_8.png)

在之前的作业中，大家可能使用过网页版的ChatGPT。其流程是：将输入（Input）写在网页上，发送给ChatGPT，然后将返回的响应（Response）显示在网页上。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_10.png)

假设我们现在想用ChatGPT构建一个应用程序，例如一个“表情包生成器”。它的功能是：用户输入一段文字，程序将其发送给ChatGPT，并返回一个添加了大量表情符号的版本。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_12.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_14.png)

如果使用网页版，你需要手动将每个用户的输入复制粘贴到ChatGPT网页中，获取输出后再返回给用户。当用户数量很多时，这种方法非常低效。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_16.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_18.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_20.png)

为了解决这个问题，我们可以使用 **API**。API的全称是 **Application Programming Interface**（应用程序编程接口）。你可以将其理解为一种通过编程方式调用ChatGPT等模型服务的方法。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_22.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_24.png)

整个API调用流程如下：你的程序（例如一段Python代码）会将请求发送给模型。这个请求中包含了要使用的模型名称、设定的提示词（Prompt）以及用户的输入文本。模型处理后会返回响应，你的程序就能以编程方式获取到这个响应。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_26.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_28.png)

这样做的好处是：当你的应用有很多用户时，你可以让用户直接将输入发送给你的程序，程序自动调用API并将结果返回给用户，整个过程无需你手动干预。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_30.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_32.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_34.png)

因此，本次作业的目标是学习使用ChatGPT（或类似模型）的API来构建简单的应用程序。我们预期大家将学会两件事：
1.  如何调用AI模型的API。
2.  如何设计合理的提示词（Prompt）来让AI完成你想要的任务。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_36.png)

由于本次作业需要调用API，因此会涉及少量代码编写。我们将使用 **Google Colab** 作为编程平台。同时，为了让我们的应用拥有可视化界面，我们将使用一个名为 **Gradio** 的工具包。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_38.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_40.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_42.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_44.png)

---

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_46.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_48.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_50.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_52.png)

## 第一部分：工具介绍 - Colab与Gradio 🧰

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_54.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_56.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_58.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_60.png)

上一节我们介绍了本次作业的核心目标是使用API构建应用。本节中，我们来看看完成作业所需的两个重要工具：Google Colab和Gradio。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_62.png)

### Google Colab 简介

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_64.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_66.png)

Google Colab 是Google提供的一个在线编程平台。它有几个显著优点：
*   **无需配置**：即使是编程新手，也可以直接打开使用，无需在本地安装任何复杂的开发环境。
*   **免费GPU**：它提供少量的免费GPU资源。虽然本次作业用不到，但在后续作业中可能会派上用场。
*   **易于分享**：和Google Docs或Slides一样，Colab笔记本可以轻松地分享给他人，你可以设置他人是只能查看还是可以编辑。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_68.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_70.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_72.png)

### Gradio 简介

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_74.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_76.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_77.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_79.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_81.png)

Gradio 是一个可以将你的代码快速可视化为Web界面的工具。你可以把它想象成“搭积木”，用简单的代码构建出用户友好的交互界面。例如，你可以构建一个类似ChatGPT的聊天界面，用户可以在输入框中打字，然后看到模型的回复。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_83.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_84.png)

接下来，我们将通过一个简短的教程来熟悉Colab和Gradio的基本操作。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_86.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_88.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_90.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_92.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_94.png)

#### Colab & Gradio 快速教程

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_96.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_98.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_100.png)

以下是使用Colab和Gradio的基本步骤：

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_102.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_104.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_106.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_108.png)

1.  **复制笔记本**：打开提供的Colab链接后，首先点击“复制到云端硬盘”。这是因为原始笔记本是“只读”的，必须创建自己的副本才能保存修改。
2.  **重命名与连接**：可以将笔记本名称改为你自己的标识（例如`hw3_你的名字`）。然后，点击顶部的“连接”按钮，以启动运行时环境。只有连接成功后，才能执行代码。
3.  **认识单元（Cell）**：Colab笔记本由“单元”构成。主要分为两种：
    *   **文本单元**：用于添加说明文字、笔记。
    *   **代码单元**：用于编写和执行Python代码。编写代码后，点击单元左侧的“播放”按钮即可运行。
4.  **文件上传与下载**：点击左侧边栏的“文件”图标，可以上传本地文件到Colab环境。点击文件旁的“更多”选项（三个点），可以选择下载文件到本地电脑。
5.  **重要提醒**：
    *   如果误点了左侧边栏的其他图标（如“表格”），找不到文件了，只需点击“目录”图标即可回到文件列表。
    *   Colab在网页闲置一段时间后会**自动断开连接**。这意味着：1) 所有已运行的代码需要重新执行；2) 生成的文件可能会丢失。因此，请务必及时将重要结果下载到本地。
6.  **安装与使用Gradio**：
    *   在代码单元中，运行 `!pip install gradio` 来安装Gradio包。执行时，“运行”按钮会变成旋转状态，完成后会显示绿色对勾。
    *   安装后，导入Gradio并运行一个简单的界面创建代码。运行后，Colab会生成一个可交互的链接，点击即可打开应用界面进行测试。
    *   使用完毕后，记得在Colab中停止Gradio界面的运行（通常通过中断代码执行来实现），以免影响后续操作。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_110.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_112.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_114.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_116.png)

#### Gradio 的工作原理

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_118.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_120.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_122.png)

我们可以把Gradio理解为连接用户界面和后台代码的“桥梁”。其工作原理如下：
*   你在代码中定义输入组件（如文本框）、输出组件（如聊天框）和一个处理函数。
*   用户在Gradio界面上输入内容并点击“提交”。
*   Gradio将输入内容传递给后台你定义的处理函数。
*   处理函数（通常包含调用AI模型的代码）进行计算，并返回结果。
*   Gradio将结果呈现在输出组件中，展示给用户。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_124.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_126.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_128.png)

因此，Gradio界面的运行依赖于背后的代码。当代码停止执行时，界面也就无法使用了。

---

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_130.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_132.png)

## 第二部分：可用的API及密钥获取 🔑

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_134.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_136.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_138.png)

上一节我们熟悉了开发工具，本节中我们来看看本次作业可以调用的AI模型API以及如何获取使用它们的“钥匙”——API密钥。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_140.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_142.png)

本次作业提供两种API可选，任选其一即可：
1.  **Google Gemini API**：目前完全免费。
2.  **OpenAI ChatGPT API**：需要付费，但新账号通常有5美元的免费额度。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_144.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_146.png)

提供两种选择的主要原因是考虑到费用问题。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_148.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_150.png)

### 获取 Google Gemini API 密钥

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_152.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_154.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_156.png)

以下是获取Gemini API密钥的步骤：
1.  访问 [AI Studio](https://aistudio.google.com/)。
2.  点击“Get API key”。
3.  勾选同意条款，点击“Continue”。
4.  点击“Create API key”。
5.  选择“Create API key in new project”。
6.  密钥生成后，请立即将其复制并保存到安全的地方。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_158.png)

**重要安全提示**：API密钥相当于访问模型的密码，**绝对不能分享给任何人**。否则他人可能滥用你的密钥，导致你的账户出现问题。如果不慎遗失，可以在同一页面重新复制。如果遇到权限错误，可以尝试选择“Create API key in existing project”并选择已有项目来创建。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_160.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_162.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_164.png)

### 获取 OpenAI ChatGPT API 密钥

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_166.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_168.png)

以下是获取ChatGPT API密钥的步骤：
1.  访问 [OpenAI平台](https://platform.openai.com/)。
2.  登录后，在左侧边栏点击“API keys”。
3.  点击“Create new secret key”。
4.  为密钥命名（例如`hw3`），然后点击“Create”。
5.  密钥生成后，请立即将其复制并保存到安全的地方。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_170.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_172.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_174.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_176.png)

**重要提示**：
*   与Gemini不同，OpenAI的密钥**一旦关闭弹窗就无法再次查看完整内容**，只能重新创建。请务必第一次就保存好。
*   关于费用：新注册的OpenAI账号通常有**5美元的免费额度**（可能有过期时间）。你可以在左侧“Usage”页面查看余额。如果额度已过期，则需要付费。本次作业消耗的额度极少，通常免费额度足够完成。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_178.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_180.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_182.png)

---

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_184.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_186.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_188.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_190.png)

## 第三部分：作业任务详解 🎯

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_192.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_194.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_196.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_198.png)

上一节我们获取了调用AI模型的“钥匙”，本节中我们来看看本次作业具体需要完成的三个任务。我们的目标是：使用Colab调用API，设计合理的提示词，构建语言模型应用，并通过达芬奇平台进行自动评分。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_200.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_202.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_204.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_206.png)

作业流程如下：
1.  在Colab中使用API完成任务。
2.  将结果提交到达芬奇平台获取分数。
3.  将评分结果提交到NTU COOL系统。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_208.png)

本次作业包含三个任务，总分为10分：
*   **任务一：文本摘要** - 3分
*   **任务二：角色扮演** - 3分
*   **任务三：自定义任务** - 4分

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_210.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_212.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_214.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_216.png)

我们将使用统一的作业Colab笔记本进行开发。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_218.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_220.png)

### 任务一：文本摘要

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_222.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_224.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_226.png)

**目标**：设计一个提示词，让语言模型能够对一篇长文章进行总结。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_227.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_229.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_231.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_233.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_235.png)

**网页版对比**：在网页版中，你可能会输入提示词“Please summarize this article for me”，然后在下面粘贴文章内容。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_237.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_239.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_241.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_243.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_245.png)

**API实现**：在代码中，你需要将提示词和文章内容组合成一个请求发送给API。对应的代码结构如下：
```python
# 伪代码示意
prompt = “你设计的摘要提示词”
article = “需要被总结的长文章”
response = call_api(model, prompt, article) # 调用API
summary = response # 获取摘要结果
```

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_247.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_249.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_251.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_253.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_255.png)

**在Colab中的操作步骤**：
1.  在对应部分（Part One）填入你设计的摘要提示词（例如：“Please summarize the following article concisely.”）。
2.  运行代码，会启动一个Gradio界面。
3.  在界面的“article”框中输入或使用默认文章。
4.  调整“temperature”参数（此参数影响输出创造性，值越大越随机，值越小越稳定）。
5.  点击“Send”，模型生成的摘要会显示在界面上。
6.  如果结果满意，点击“Export”将对话保存为一个JSON文件（如`part_one.json`）。**务必及时将该文件下载到本地**，以防Colab断开连接后丢失。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_257.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_259.png)

### 任务二：角色扮演

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_261.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_263.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_265.png)

**目标**：设计一个提示词，让语言模型扮演某个角色（如海盗），并与之进行至少两轮对话。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_267.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_269.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_271.png)

**网页版对比**：你首先发送“请你扮演一个海盗”，模型回应后，你再发送新的对话内容，模型会结合历史记录进行回复。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_273.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_275.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_277.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_279.png)

**API实现**：与单轮对话不同，多轮对话需要在API请求中维护一个“消息历史”列表。每次请求都需要包含之前所有的对话记录。
```python
# 伪代码示意
messages = [
    {"role": "user", "content": "请你扮演一个海盗。"},
    {"role": "assistant", "content": "（模型的首次回应）"},
    {"role": "user", "content": "（你的第一轮对话）"},
    {"role": "assistant", "content": "（模型的第二轮回应）"},
    {"role": "user", "content": "（你的第二轮对话）"}
]
# 下一次请求需要将整个messages列表发送给API
```

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_281.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_283.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_285.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_286.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_288.png)

**在Colab中的操作步骤**：
1.  在对应部分（Part Two）填入角色名称（如“pirate”）和让模型扮演该角色的提示词。
2.  运行代码，启动Gradio界面。
3.  与扮演成该角色的模型进行至少两轮有意义的对话。
4.  点击“Export”保存对话记录为JSON文件（如`part_two.json`）。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_290.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_292.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_294.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_296.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_298.png)

### 任务三：自定义任务

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_300.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_302.png)

**目标**：自由设计一个任务，并设计相应的提示词让模型完成。例如：让模型输出词语的反义词、重复你的话、解简单数学题等。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_304.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_306.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_308.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_310.png)

**要求**：为了便于评分，请避免设计会导致模型输出极长文本的任务，并且对话轮数建议不要超过三轮。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_312.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_314.png)

**在Colab中的操作步骤**：
1.  在对应部分（Part Three）描述你的自定义任务（如“输出反义词”），并填入实现该任务的详细提示词（如“For the word I provide, output its antonym.”）。
2.  运行代码，启动Gradio界面。
3.  测试你的任务（例如：输入“big”，模型应输出“small”）。
4.  进行几轮测试后，点击“Export”保存记录为JSON文件（如`part_three.json`）。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_316.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_318.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_320.png)

**完成所有任务后**：请记得妥善处理你的API密钥。如果怀疑密钥可能泄露，应尽快在对应平台（OpenAI或Google AI Studio）上删除旧密钥并创建新的。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_322.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_324.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_326.png)

---

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_328.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_330.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_332.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_334.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_336.png)

## 第四部分：提交与评分 📤

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_338.png)

上一节我们完成了三个应用任务，本节中我们学习如何通过达芬奇平台进行自动评分并最终提交作业。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_340.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_342.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_344.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_346.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_348.png)

### 在达芬奇平台进行评分

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_350.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_352.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_354.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_356.png)

达芬奇平台使用一个名为“HW3 Grading Assistant”的助手来评分。以下是评分步骤：

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_358.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_360.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_362.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_364.png)

1.  **打开评分助手**：进入达芬奇平台，在“Assistant”中找到并安装“HW3 Grading Assistant”。
2.  **获取评分数据**：回到你的Colab笔记本。在每个任务部分下方，都有一个名为“Copy part to grading system”的代码单元。运行该单元，它会读取你之前导出的JSON文件，并生成一段用于评分的文本。
3.  **提交评分**：
    *   对于**任务一（摘要）**：将生成的文本复制，粘贴到达芬奇平台“Summarization Grader”助手的对应输入框中，点击提交。稍等片刻，助手会返回你的得分（例如“Grade: 2 points”）。
    *   对于**任务二（角色扮演）**和**任务三（自定义任务）**：重复上述过程，分别使用“Role Play Grader”和“Custom Task Grader”助手进行评分。
4.  **保存评分结果**：在达芬奇平台每次评分后，点击对话旁的“Export”按钮，将包含评分结果的对话保存为JSON文件。请将文件命名为：`你的学号_part_one_hw3.json`（以此类推）。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_366.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_367.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_369.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_371.png)

**重要提醒**：
*   每日评分有次数限制（摘要约5次，角色扮演约10次，自定义任务约15次），请合理使用。
*   **必须提交从达芬奇平台Export出来的JSON文件**，而不是直接从Colab生成的`part_x.json`文件。
*   评分结果中必须包含“Grade: x points”字样，这是我们判断分数的依据。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_373.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_375.png)

### 最终提交到NTU COOL

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_377.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_379.png)

1.  将三个从达芬奇平台导出的、正确命名的JSON文件（例如`b12345678_part_one_hw3.json`）准备好。
2.  登录NTU COOL，在作业三的提交页面，上传这三个文件。
3.  你可以多次提交，系统会以最后一次提交为准。

**注意事项与规则**：
*   **截止日期**：请关注课程公告，逾期不候。
*   **禁止行为**：严禁抄袭、分享自己的提示词或结果文件、手动篡改评分JSON文件的内容。一经发现，将按课程规定严肃处理（本次作业零分或课程不及格）。
*   **问题求助**：如有问题，请优先在NTU COOL作业讨论区提问。若涉及隐私，可联系助教邮箱。询问代码错误时，请附上完整的错误信息。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_381.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_383.png)

---

## 总结 📝

本节课中，我们一起学习了如何利用AI模型的API来构建应用程序。我们从理解API的概念出发，熟悉了Google Colab和Gradio这两个强大的工具，并逐步完成了文本摘要、角色扮演和自定义任务三个实践练习。最后，我们掌握了通过达芬奇平台进行自动评分以及向NTU COOL提交作业的完整流程。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_385.png)

希望本教程能帮助你顺利入门AI应用开发，并成功完成本次作业！