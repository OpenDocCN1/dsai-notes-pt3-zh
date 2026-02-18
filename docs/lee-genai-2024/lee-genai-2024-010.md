# 10：作业3：以 AI 搭建自己的应用 🛠️

![](img/ccada4827190405f00f3bf4b875a4480_0.png)

![](img/ccada4827190405f00f3bf4b875a4480_2.png)

![](img/ccada4827190405f00f3bf4b875a4480_4.png)

在本节课中，我们将学习如何利用 API 快速搭建自己的生成式 AI 应用。我们将了解什么是 API，如何使用 Google Colab 和 Gradio 来编写和可视化我们的程序，并完成三个具体的任务：文本摘要、角色扮演和自定义任务。

---

## 什么是 API？🔌

在上一节中，我们介绍了课程概述。本节中，我们来看看什么是 API。

![](img/ccada4827190405f00f3bf4b875a4480_6.png)

![](img/ccada4827190405f00f3bf4b875a4480_8.png)

想必大家在作业二时都使用过 ChatGPT 的网页版。网页版的具体操作是：将输入内容写在对话框中，发送给 ChatGPT，然后它将回复显示在网页上。

![](img/ccada4827190405f00f3bf4b875a4480_10.png)

如果我们想使用 ChatGPT 来构建一个应用程序会怎样呢？例如，我们想做一个添加 Emoji 表情的 App。它的功能是：我给它一段输入文本，它返回一个添加了大量 Emoji 的版本。

![](img/ccada4827190405f00f3bf4b875a4480_12.png)

如果使用网页版，操作可能是这样：我会写一段提示词，告诉它“请在这段文字里加上一大堆 Emoji”。然后在下面附上使用者想要处理的文章。ChatGPT 就会把输出结果返回给我。

![](img/ccada4827190405f00f3bf4b875a4480_14.png)

![](img/ccada4827190405f00f3bf4b875a4480_16.png)

但是，如果今天不止我要使用这个 App，还有我的朋友、同学等一大堆人都要使用呢？如果还用网页版，就会变得非常麻烦：你必须把每个人的输入一个一个复制到 ChatGPT 网页版里，拿到输出后再还给他们。

![](img/ccada4827190405f00f3bf4b875a4480_18.png)

![](img/ccada4827190405f00f3bf4b875a4480_20.png)

![](img/ccada4827190405f00f3bf4b875a4480_22.png)

为了解决这个问题，我们可以使用 **API**。API 的全称是 Application Programming Interface。可以把它理解为一种用编程方式调用 ChatGPT 的方法。

![](img/ccada4827190405f00f3bf4b875a4480_24.png)

![](img/ccada4827190405f00f3bf4b875a4480_26.png)

它的整个流程是这样的：我们编写一个程序，里面指定要使用哪个模型、使用怎样的提示词、以及输入的文章内容。程序将这个请求发送给 ChatGPT 后，它会返回响应，我们就可以用编程方式获取这个响应。

![](img/ccada4827190405f00f3bf4b875a4480_28.png)

这样做的好处是：当你的 App 有很多人想使用时，你可以让他们直接把输入信息发送给你的程序。程序调用 ChatGPT 后，就可以直接将响应返回给你的用户。在整个过程中，你不需要做任何手动操作。

![](img/ccada4827190405f00f3bf4b875a4480_30.png)

![](img/ccada4827190405f00f3bf4b875a4480_32.png)

所以，这次作业希望大家学习两件事：
1.  如何调用 ChatGPT 的 API。
2.  如何设计合理的提示词，让 ChatGPT 完成你想做的事情。

![](img/ccada4827190405f00f3bf4b875a4480_34.png)

![](img/ccada4827190405f00f3bf4b875a4480_36.png)

此外，因为这次作业需要调用 API，所以需要编写一点代码。我们将使用 **Google Colab** 作为编程平台。同时，为了让我们的 App 有一个可视化界面，我们会使用一个叫做 **Gradio** 的套件。

![](img/ccada4827190405f00f3bf4b875a4480_38.png)

以下是今天课程的主要内容：
1.  通过一个演示介绍 Colab 和 Gradio。
2.  介绍本次作业可以使用哪些 API，以及如何获取 API Key。
3.  讲解本次作业具体需要完成哪些应用程序。

![](img/ccada4827190405f00f3bf4b875a4480_40.png)

![](img/ccada4827190405f00f3bf4b875a4480_42.png)

![](img/ccada4827190405f00f3bf4b875a4480_44.png)

![](img/ccada4827190405f00f3bf4b875a4480_46.png)

![](img/ccada4827190405f00f3bf4b875a4480_48.png)

---

![](img/ccada4827190405f00f3bf4b875a4480_50.png)

![](img/ccada4827190405f00f3bf4b875a4480_52.png)

## Google Colab 与 Gradio 教程 💻

![](img/ccada4827190405f00f3bf4b875a4480_54.png)

![](img/ccada4827190405f00f3bf4b875a4480_56.png)

![](img/ccada4827190405f00f3bf4b875a4480_58.png)

![](img/ccada4827190405f00f3bf4b875a4480_60.png)

上一节我们介绍了 API 的基本概念。本节中，我们来学习本次作业将使用的两个工具：Google Colab 和 Gradio。

![](img/ccada4827190405f00f3bf4b875a4480_62.png)

**Google Colab** 是 Google 提供的一个可以在网页上编写和运行代码的平台。它有几个好处：
*   即使你是完全的编程新手，也可以直接使用，无需任何环境配置。
*   它提供少量的免费 GPU 资源。本次作业虽然用不到 GPU，但之后的作业可能会用到。
*   它可以非常方便地将你的代码分享给朋友，类似于 Google Docs 的共享功能。

![](img/ccada4827190405f00f3bf4b875a4480_64.png)

**Gradio** 可以理解为将你的程序可视化的一个工具。它能把你的代码“搭建”成一个大家都能看懂的界面。例如，它可以搭建一个类似 ChatGPT 的聊天界面，我们可以把输入写进去，然后得到回复。

![](img/ccada4827190405f00f3bf4b875a4480_66.png)

![](img/ccada4827190405f00f3bf4b875a4480_68.png)

接下来，我们将运行一个 Colab 和 Gradio 的教程。

![](img/ccada4827190405f00f3bf4b875a4480_70.png)

![](img/ccada4827190405f00f3bf4b875a4480_72.png)

![](img/ccada4827190405f00f3bf4b875a4480_74.png)

![](img/ccada4827190405f00f3bf4b875a4480_76.png)

首先，打开教程链接后，你会看到这样一个界面。你要做的第一件事是点击“复制到云端硬盘”。因为当前这份代码是“仅供检视”的，你在上面做的任何更改都不会被保存，所以必须先存一份副本到自己的云端硬盘中。

![](img/ccada4827190405f00f3bf4b875a4480_77.png)

![](img/ccada4827190405f00f3bf4b875a4480_79.png)

![](img/ccada4827190405f00f3bf4b875a4480_81.png)

第二件事是，你可以修改这个笔记本的文件名，以便记忆。

![](img/ccada4827190405f00f3bf4b875a4480_83.png)

![](img/ccada4827190405f00f3bf4b875a4480_84.png)

第三件非常重要的事是，记得点击“连接”按钮。连接成功后，平台才会为你的代码分配计算资源，你才能执行代码。

![](img/ccada4827190405f00f3bf4b875a4480_86.png)

![](img/ccada4827190405f00f3bf4b875a4480_88.png)

![](img/ccada4827190405f00f3bf4b875a4480_90.png)

连接完成后，界面会显示“已连接”。确认连接成功后，就可以开始编写代码了。

![](img/ccada4827190405f00f3bf4b875a4480_92.png)

![](img/ccada4827190405f00f3bf4b875a4480_94.png)

![](img/ccada4827190405f00f3bf4b875a4480_96.png)

![](img/ccada4827190405f00f3bf4b875a4480_98.png)

接下来介绍 Colab 中最重要的单元：**单元格**。把鼠标移到单元格上方，你会看到“+ 代码”和“+ 文本”的选项。

![](img/ccada4827190405f00f3bf4b875a4480_100.png)

![](img/ccada4827190405f00f3bf4b875a4480_102.png)

![](img/ccada4827190405f00f3bf4b875a4480_104.png)

“+ 文本”单元格让你可以在里面输入文字，用于说明这段代码在做什么，或者告诉别人如何使用接下来的代码。

![](img/ccada4827190405f00f3bf4b875a4480_106.png)

![](img/ccada4827190405f00f3bf4b875a4480_108.png)

![](img/ccada4827190405f00f3bf4b875a4480_110.png)

“+ 代码”单元格让你可以在里面编写和运行代码。例如，我们打一个非常简单的代码 `print(“hello”)`，然后点击单元格左侧的“执行”按钮，下方就会输出“hello”。

![](img/ccada4827190405f00f3bf4b875a4480_112.png)

![](img/ccada4827190405f00f3bf4b875a4480_114.png)

![](img/ccada4827190405f00f3bf4b875a4480_116.png)

所以，单元格分为两种：让你打文字的“文本单元格”，和让你打代码的“代码单元格”。

![](img/ccada4827190405f00f3bf4b875a4480_118.png)

![](img/ccada4827190405f00f3bf4b875a4480_120.png)

![](img/ccada4827190405f00f3bf4b875a4480_122.png)

接下来介绍如何在 Colab 中上传和下载文件。点击左侧的“文件”图标，然后点击“上传”按钮，就可以上传一个文件到当前环境。上传后，双击文件名可以查看内容。要下载文件，则点击文件右侧的三个点，选择“下载”即可。

![](img/ccada4827190405f00f3bf4b875a4480_124.png)

第一次使用 Colab 可能会不小心点击左侧的“目录”图标，界面会变成只显示文件目录。这时你只需要再点击“内容”图标，就能回到原来的代码界面。

![](img/ccada4827190405f00f3bf4b875a4480_126.png)

另外需要注意：如果你把 Colab 页面放在网页上一段时间没有操作，它会自动断开连接。断开连接意味着两件事：第一，你刚运行过的代码需要全部重新运行；第二，你在这里记录的文件可能会全部消失。所以，如果这里有非常重要的答案，一定要记得及时下载到自己的电脑里。

![](img/ccada4827190405f00f3bf4b875a4480_128.png)

![](img/ccada4827190405f00f3bf4b875a4480_130.png)

---

![](img/ccada4827190405f00f3bf4b875a4480_132.png)

## 使用 Gradio 构建界面 🎨

![](img/ccada4827190405f00f3bf4b875a4480_134.png)

![](img/ccada4827190405f00f3bf4b875a4480_136.png)

上一节我们学习了 Colab 的基本操作。本节中，我们来看看如何使用 Gradio 为程序添加可视化界面。

![](img/ccada4827190405f00f3bf4b875a4480_138.png)

![](img/ccada4827190405f00f3bf4b875a4480_140.png)

首先需要做的第一件事是安装 Gradio 包。在代码单元格中输入安装命令并执行。当它正在运行时，“执行”按钮会变成旋转图标，代表正在执行。等它结束后会变成绿色的对勾，代表执行成功且没有出错。

![](img/ccada4827190405f00f3bf4b875a4480_142.png)

![](img/ccada4827190405f00f3bf4b875a4480_144.png)

安装完成后，我们运行一段创建 Gradio 界面的代码。运行后，Gradio 会在你的 Colab 中打开一个交互界面。你也可以点击生成的链接，在一个更大的、更好交互的页面中查看。

![](img/ccada4827190405f00f3bf4b875a4480_146.png)

在这个界面中，你可以输入信息，然后看到程序的回复。可以点击“Clear”按钮清空对话。

![](img/ccada4827190405f00f3bf4b875a4480_148.png)

![](img/ccada4827190405f00f3bf4b875a4480_150.png)

记得在结束使用后，要关闭这个 Gradio 界面。

![](img/ccada4827190405f00f3bf4b875a4480_152.png)

![](img/ccada4827190405f00f3bf4b875a4480_154.png)

那么，Gradio 的原理到底是什么呢？我们可以把构建 Gradio 界面想象成搭积木。我们在代码中像搭积木一样定义界面的各个组件（如输入框、按钮），然后 Gradio 就会渲染出对应的可视化界面。

![](img/ccada4827190405f00f3bf4b875a4480_156.png)

![](img/ccada4827190405f00f3bf4b875a4480_158.png)

它是如何将界面操作与后端代码连接起来的呢？当我们点击界面上的“Send”按钮时，输入的内容就会被传递到后端定义的处理函数中。这个函数决定要返回怎样的输出。等它决定好后，就把输出内容丢回给 Gradio 界面显示出来。

![](img/ccada4827190405f00f3bf4b875a4480_160.png)

![](img/ccada4827190405f00f3bf4b875a4480_162.png)

所以，Gradio 的背后是靠代码逻辑来支撑的。当后端代码执行完毕时，Gradio 界面也就无法再使用了。

![](img/ccada4827190405f00f3bf4b875a4480_164.png)

![](img/ccada4827190405f00f3bf4b875a4480_166.png)

---

![](img/ccada4827190405f00f3bf4b875a4480_168.png)

![](img/ccada4827190405f00f3bf4b875a4480_170.png)

![](img/ccada4827190405f00f3bf4b875a4480_172.png)

## 可用的 API 及如何获取密钥 🔑

![](img/ccada4827190405f00f3bf4b875a4480_174.png)

![](img/ccada4827190405f00f3bf4b875a4480_176.png)

![](img/ccada4827190405f00f3bf4b875a4480_178.png)

![](img/ccada4827190405f00f3bf4b875a4480_180.png)

上一节我们完成了工具的学习。本节中，我们来看看本次作业可以使用哪些 API，以及如何获取使用它们的“钥匙”——API Key。

![](img/ccada4827190405f00f3bf4b875a4480_182.png)

![](img/ccada4827190405f00f3bf4b875a4480_184.png)

本次作业可以使用两种 API：
1.  **Google Gemini API**
2.  **OpenAI ChatGPT API**

![](img/ccada4827190405f00f3bf4b875a4480_186.png)

![](img/ccada4827190405f00f3bf4b875a4480_188.png)

![](img/ccada4827190405f00f3bf4b875a4480_190.png)

你只需要选择其中一种使用即可。提供两种选择的主要原因是：**Google Gemini API 目前是完全免费的**，而 **ChatGPT API 是收费的**。你可能会问，网页版 ChatGPT 不是免费吗？这是因为 API 的收费标准和网页版是不同的。不过，ChatGPT API 对你来说**可能也是免费的**，这一点我们稍后说明。

![](img/ccada4827190405f00f3bf4b875a4480_192.png)

![](img/ccada4827190405f00f3bf4b875a4480_194.png)

![](img/ccada4827190405f00f3bf4b875a4480_196.png)

### 获取 Google Gemini API Key

![](img/ccada4827190405f00f3bf4b875a4480_198.png)

![](img/ccada4827190405f00f3bf4b875a4480_200.png)

![](img/ccada4827190405f00f3bf4b875a4480_202.png)

![](img/ccada4827190405f00f3bf4b875a4480_204.png)

以下是获取 Google Gemini API Key 的步骤：
1.  打开提供的 Gemini API 获取网页。
2.  点击“Get API Key”按钮。
3.  勾选服务条款并继续。
4.  点击“Create API Key”。
5.  选择“Create API key in new project”。
6.  生成后，你会看到你的 API Key。

![](img/ccada4827190405f00f3bf4b875a4480_206.png)

**请务必将这个 Key 保存到一个安全且不会给别人看到的地方。** 千万不要分享给任何人。因为这个 Key 代表着你使用该模型的权限。如果别人拿到了你的 Key，就等于获得了用你的账号使用模型的权限。最糟的情况下，别人可能用你的 Key 乱搞，导致你的账号出问题。

![](img/ccada4827190405f00f3bf4b875a4480_208.png)

![](img/ccada4827190405f00f3bf4b875a4480_210.png)

![](img/ccada4827190405f00f3bf4b875a4480_212.png)

如果你不小心关掉了窗口，没有存下 Key，可以回到 API 管理页面，在那里可以再次查看和复制，无需重新创建。

![](img/ccada4827190405f00f3bf4b875a4480_214.png)

![](img/ccada4827190405f00f3bf4b875a4480_216.png)

![](img/ccada4827190405f00f3bf4b875a4480_218.png)

**注意**：有时你可能会遇到一个未知原因的 Bug，提示你没有权限生成 API Key。如果遇到这种情况，请尝试选择“Create API key in existing project”，然后选择列表中的第一个项目（例如“Gemini API”），再点击“Create new API key”，后续步骤就和上面一样了。

![](img/ccada4827190405f00f3bf4b875a4480_220.png)

### 获取 OpenAI ChatGPT API Key

![](img/ccada4827190405f00f3bf4b875a4480_222.png)

![](img/ccada4827190405f00f3bf4b875a4480_224.png)

以下是获取 OpenAI ChatGPT API Key 的步骤：
1.  打开 OpenAI 平台网站。
2.  点击“Log in”登录。注意，这里有两个入口：“ChatGPT”和“API”。我们这次要点击的是右边的“API”。
3.  登录后，点击左侧边栏的“API Keys”。
4.  点击“Create new secret key”。
5.  为它起一个名字（例如“hw3”），然后点击“Create”。
6.  弹出的窗口里就是你的 API Key。

![](img/ccada4827190405f00f3bf4b875a4480_226.png)

![](img/ccada4827190405f00f3bf4b875a4480_227.png)

![](img/ccada4827190405f00f3bf4b875a4480_229.png)

![](img/ccada4827190405f00f3bf4b875a4480_231.png)

**同样，请立即复制并妥善保存这个 Key，不要分享给任何人。**

![](img/ccada4827190405f00f3bf4b875a4480_232.png)

![](img/ccada4827190405f00f3bf4b875a4480_234.png)

![](img/ccada4827190405f00f3bf4b875a4480_236.png)

![](img/ccada4827190405f00f3bf4b875a4480_238.png)

![](img/ccada4827190405f00f3bf4b875a4480_240.png)

**与 Gemini 不同的一点是：一旦你关闭了生成 Key 的弹窗，就再也无法看到这个 Key 的完整内容了。** 如果发生这种情况，你只能重新创建一个新的 Key。

![](img/ccada4827190405f00f3bf4b875a4480_242.png)

![](img/ccada4827190405f00f3bf4b875a4480_244.png)

![](img/ccada4827190405f00f3bf4b875a4480_246.png)

之前提到 ChatGPT API 收费但可能免费，这是为什么呢？点击左侧边栏的“Usage”，你可以看到“$5.00 limit”。这是因为当你新创建一个 OpenAI 账号时，平台会给你 5 美元的免费额度来体验其 API。**但这个额度会过期。** 如果你的 OpenAI 账号是在这堂课之前创建的，那么你的免费额度可能已经过期了。如果你是这堂课之后才创建的账号，那么你应该还有免费额度，可以用来免费完成这次作业。

![](img/ccada4827190405f00f3bf4b875a4480_248.png)

![](img/ccada4827190405f00f3bf4b875a4480_250.png)

![](img/ccada4827190405f00f3bf4b875a4480_252.png)

![](img/ccada4827190405f00f3bf4b875a4480_254.png)

**另外值得注意的是**：如果你是第一次点进“API Keys”页面，可能会看到要求验证手机号的提示，请按照指引一步步完成验证即可。

![](img/ccada4827190405f00f3bf4b875a4480_256.png)

![](img/ccada4827190405f00f3bf4b875a4480_258.png)

---

![](img/ccada4827190405f00f3bf4b875a4480_260.png)

![](img/ccada4827190405f00f3bf4b875a4480_262.png)

## 作业任务详解 📝

![](img/ccada4827190405f00f3bf4b875a4480_264.png)

![](img/ccada4827190405f00f3bf4b875a4480_266.png)

上一节我们学习了如何获取 API 密钥。本节中，我们来看看本次作业具体需要完成哪些任务。

![](img/ccada4827190405f00f3bf4b875a4480_268.png)

![](img/ccada4827190405f00f3bf4b875a4480_270.png)

![](img/ccada4827190405f00f3bf4b875a4480_272.png)

![](img/ccada4827190405f00f3bf4b875a4480_274.png)

本次作业的工作流程是：首先，使用代码方式调用 API 来完成一些任务（可选择 ChatGPT API 或 Gemini API）。任务完成后，我们将结果提交到达芬奇平台进行自动评分（与作业二类似）。最后，将评分结果提交到 NTU COOL 系统。

![](img/ccada4827190405f00f3bf4b875a4480_276.png)

![](img/ccada4827190405f00f3bf4b875a4480_277.png)

![](img/ccada4827190405f00f3bf4b875a4480_279.png)

![](img/ccada4827190405f00f3bf4b875a4480_281.png)

本次作业希望大家完成三个任务：
1.  **文本摘要**：占 3 分。
2.  **角色扮演**：占 3 分。
3.  **自定义任务**：占 4 分。

![](img/ccada4827190405f00f3bf4b875a4480_283.png)

![](img/ccada4827190405f00f3bf4b875a4480_285.png)

![](img/ccada4827190405f00f3bf4b875a4480_287.png)

![](img/ccada4827190405f00f3bf4b875a4480_289.png)

我们将使用提供的 Colab 链接来完成这些任务。

![](img/ccada4827190405f00f3bf4b875a4480_291.png)

![](img/ccada4827190405f00f3bf4b875a4480_293.png)

![](img/ccada4827190405f00f3bf4b875a4480_295.png)

![](img/ccada4827190405f00f3bf4b875a4480_297.png)

### 任务一：文本摘要

![](img/ccada4827190405f00f3bf4b875a4480_299.png)

![](img/ccada4827190405f00f3bf4b875a4480_301.png)

文本摘要的任务是：当你有一篇很长的文章，自己懒得看，希望 AI 先帮你总结好，你直接看总结版本。我们希望语言模型拿到一篇文章后，能帮我们重新整理并总结。

![](img/ccada4827190405f00f3bf4b875a4480_303.png)

![](img/ccada4827190405f00f3bf4b875a4480_305.png)

![](img/ccada4827190405f00f3bf4b875a4480_307.png)

如果使用网页版 ChatGPT，我们会这样做：先想一个提示词，例如“Please summarize this for me”。然后把文章内容贴在下面。发送后，ChatGPT 就会把摘要结果放在这里。

![](img/ccada4827190405f00f3bf4b875a4480_309.png)

![](img/ccada4827190405f00f3bf4b875a4480_311.png)

网页版 ChatGPT 和 API 版在代码中的对应关系如下：
*   网页版的提示词对应代码中 `prompt` 变量的内容。
*   网页版的文章对应代码中 `article` 变量的内容。
*   我们将这两者组合后，通过一个函数调用发送给 ChatGPT API。
*   函数返回的响应，就对应着网页版显示的摘要结果。

![](img/ccada4827190405f00f3bf4b875a4480_313.png)

![](img/ccada4827190405f00f3bf4b875a4480_315.png)

在作业 Colab 中，你需要做的事情是：
1.  **选择一个要使用的 API**。我个人推荐，如果你有免费额度，使用 ChatGPT API 更好，因为 Gemini API 相对较慢且效果可能稍差。接下来的演示我们都会使用 ChatGPT API 版本。
2.  在 Colab 中，展开你选择的 API 对应的代码区块（例如“unfold”）。
3.  运行 `install package` 的代码单元格。
4.  在指定位置填入你的 ChatGPT API Key。**注意：填入时 Key 两边的引号要保留。** 格式如 `"your-api-key-here"`。
5.  运行设置 API Key 的单元格。如果看到“Set ChatGPT API successfully”代表成功；如果报错，请检查 Key 是否正确。
6.  找到“Part One: Summarization”部分。这里有详细的教学。
7.  在 `prompt = “”` 中填入你的摘要提示词。例如 `prompt = “Please summarize this for me.”`。
8.  运行这个代码单元格。
9.  运行后，会出现一个 Gradio 界面。其中“Article”框可以填入任何你想总结的文章（我们提供了默认文本供测试）。
10. 界面上还有一个 `temperature` 参数。这是一个可以控制模型输出的参数。原则上，数值越大，模型的输出越有创造性；数值越小，输出越严谨。做作业时可以自己调整试试效果。
11. 在界面输入文章并调整参数后，点击“Send”。
12. 你可以在界面中看到 ChatGPT 返回的摘要结果。
13. 如果觉得结果不错，点击界面上的“Export”按钮。它会把这次对话记录保存成一个 JSON 文件。
14. **重要**：为了避免断开连接后文件丢失，请记得及时将生成的 `part_one.json` 文件下载到本地电脑。
15. 另外，下面还有“Check Prior Result”和“Copy Part for Grading System”的代码块，前者用于验证你保存的文件内容是否正确，后者用于准备提交给评分系统的内容，我们稍后会一起讲解。

![](img/ccada4827190405f00f3bf4b875a4480_317.png)

![](img/ccada4827190405f00f3bf4b875a4480_319.png)

![](img/ccada4827190405f00f3bf4b875a4480_321.png)

### 任务二：角色扮演

![](img/ccada4827190405f00f3bf4b875a4480_323.png)

![](img/ccada4827190405f00f3bf4b875a4480_325.png)

![](img/ccada4827190405f00f3bf4b875a4480_327.png)

角色扮演任务的基本思路是：我们希望可以和 ChatGPT 玩一个角色扮演游戏。你需要通过提示词让语言模型扮演某个角色（例如海盗），然后它会全心投入角色与你互动。

![](img/ccada4827190405f00f3bf4b875a4480_329.png)

![](img/ccada4827190405f00f3bf4b875a4480_330.png)

![](img/ccada4827190405f00f3bf4b875a4480_332.png)

我们希望你与模型进行**两轮**互动（即模型扮演角色后，你与它对话两个来回）。

![](img/ccada4827190405f00f3bf4b875a4480_334.png)

![](img/ccada4827190405f00f3bf4b875a4480_336.png)

![](img/ccada4827190405f00f3bf4b875a4480_338.png)

如果使用网页版 ChatGPT，操作是：先给它一个提示词，例如“扮演一个海盗”。发送后，它回复说现在是个海盗了。接下来你再说新的话（比如“你好”），这时你之前说的话会成为对话历史，ChatGPT 会结合历史和你的新输入，给出新的回复。

![](img/ccada4827190405f00f3bf4b875a4480_340.png)

![](img/ccada4827190405f00f3bf4b875a4480_342.png)

在 API 实现中，我们需要**手动记录对话历史**。代码中会用列表来存储历史消息，每条消息都标明是“用户”说的还是“助手”说的。新的输入会被添加到这个历史中，然后一起发送给 API 以获取具有上下文连贯性的回复。

![](img/ccada4827190405f00f3bf4b875a4480_344.png)

![](img/ccada4827190405f00f3bf4b875a4480_346.png)

![](img/ccada4827190405f00f3bf4b875a4480_348.png)

![](img/ccada4827190405f00f3bf4b875a4480_350.png)

在作业 Colab 的“Part Two: Role Play”部分，你需要：
1.  在 `character = “”` 中填入你想让模型扮演的角色（如“a pirate”）。
2.  在 `prompt = “”` 中填入你的角色扮演提示词（如“You are a pirate.”）。
3.  运行代码，打开 Gradio 界面。
4.  在界面中，模型会先根据提示词扮演角色并打招呼。
5.  然后，你与它进行两轮对话（例如，你先说“Hello”，它回复后，你再说一句“OK”）。
6.  满意后，点击“Export”保存对话记录为 `part_two.json`，并下载到本地。

![](img/ccada4827190405f00f3bf4b875a4480_352.png)

![](img/ccada4827190405f00f3bf4b875a4480_354.png)

![](img/ccada4827190405f00f3bf4b875a4480_356.png)

### 任务三：自定义任务

![](img/ccada4827190405f00f3bf4b875a4480_358.png)

![](img/ccada4827190405f00f3bf4b875a4480_360.png)

![](img/ccada4827190405f00f3bf4b875a4480_362.png)

自定义任务就是希望大家自己想一个想让 ChatGPT 完成的事情。基本上什么都可以，例如让它解数学题，或者为每个输入的词想一个反义词。

![](img/ccada4827190405f00f3bf4b875a4480_364.png)

![](img/ccada4827190405f00f3bf4b875a4480_366.png)

![](img/ccada4827190405f00f3bf4b875a4480_367.png)

![](img/ccada4827190405f00f3bf4b875a4480_369.png)

你需要做的是：
1.  想一个提示词，让 ChatGPT 能完成你的任务。**为了批改方便，请不要设计会让 ChatGPT 输出极长文本的任务。**
2.  设计一个或多个测试输入。例如，对于“反义词”任务，输入“big”，它应输出“small”。你可以设计单轮或多轮任务，但**为了批改方便，请不要超过三轮交互**。

![](img/ccada4827190405f00f3bf4b875a4480_371.png)

![](img/ccada4827190405f00f3bf4b875a4480_373.png)

在作业 Colab 的“Part Three: Custom Task”部分，你需要：
1.  在 `task = “”` 中简单描述你的任务（如“find the antonym”）。
2.  在 `prompt = “”` 中填入你实现该任务的详细提示词（如“Please output the antonym of the word I give you.”）。
3.  运行代码，打开 Gradio 界面进行测试。
4.  测试成功后，点击“Export”保存对话记录为 `part_three.json`，并下载到本地。

![](img/ccada4827190405f00f3bf4b875a4480_375.png)

**完成所有任务后，一个重要的安全步骤是：考虑删除你的 API Key。** 如果你怀疑 Key 可能泄露，建议立即删除。在 OpenAI 平台 API Keys 页面，每个 Key 右侧都有垃圾桶图标，点击即可删除。Google Gemini API Key 也可以在相应管理页面删除。删除后，你可以随时按流程创建一个新的。

![](img/ccada4827190405f00f3bf4b875a4480_377.png)

![](img/ccada4827190405f00f3bf4b875a4480_379.png)

---

## 提交作业与评分流程 📤

![](img/ccada4827190405f00f3bf4b875a4480_381.png)

![](img/ccada4827190405f00f3bf4b875a4480_383.png)

上一节我们完成了三个任务。本节中，我们学习如何将结果提交到达芬奇平台进行评分，并最终提交到 NTU COOL。

本次评分使用的模型是 GPT-4，助手名叫“HW3 Assistant”。它内部包含了三个评分提示词，分别对应摘要、角色扮演和自定义任务。

你需要将 Colab 中产生的结果复制到达芬奇平台进行评分。以下是具体步骤：

1.  打开达芬奇平台，点击“Chat”，然后选择“Assistant”，找到名为“HW3 Assistant”的助手，点击“Init”初始化。
2.  初始化后，你会看到三个选项：“Summarization Grader”, “Role Play Grader”, “Custom Task Grader”。
3.  点击“Summarization Grader”，会出现需要你填写“article”和“summarization”的空格。
4.  如何获取这些内容？回到 Colab 的“Part One: Summarization”部分，找到“Copy Part for Grading System”代码块。
5.  确保左边文件栏里有 `part_one.json` 文件。
6.  运行“Copy Part for Grading System”这个代码单元格。运行后，它会输出两段文本，分别标记为“ARTICLE”和“SUMMARIZATION”。
7.  将“ARTICLE”后面的内容复制，粘贴到达芬奇平台对应的“article”框中。
8.  将“SUMMARIZATION”后面的内容复制，粘贴到达芬奇平台对应的“summarization”框中。
9.  点击“Submit”。系统会告诉你得了多少分（满分3分）。因为使用 GPT-4，可能需要稍等片刻。
10. 对于“Role Play Grader”，操作类似：
    *   在 Colab 的“Part Two”部分运行“Copy Part for Grading System”。
    *   将输出的“PROMPT”和“DIALOGUE”内容分别复制粘贴到达芬奇平台对应的位置并提交。
11. 对于“Custom Task Grader”，操作也类似：
    *   在 Colab 的“Part Three”部分运行“Copy Part for Grading System”。
    *   将输出的“DESCRIPTION”和“DIALOGUE”内容分别复制粘贴到达芬奇平台对应的位置并提交。

![](img/ccada4827190405f00f3bf4b875a4480_385.png)

**重要**：在达芬奇平台提交并获得评分