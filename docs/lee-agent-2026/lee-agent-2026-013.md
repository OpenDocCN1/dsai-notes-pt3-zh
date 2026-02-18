# 13：Hugging Face Llama模型下载指南 📥

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_1.png)

在本节课中，我们将学习如何获取Llama模型的下载授权，以便完成作业。整个过程分为四个主要步骤：注册Hugging Face账号、向Meta申请模型使用许可、创建访问令牌以及在代码环境中登录并下载模型。

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_3.png)

---

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_5.png)

## 第一步：注册Hugging Face账号

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_7.png)

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_9.png)

首先，我们需要创建一个Hugging Face账号，这是访问其模型库的基础。

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_11.png)

以下是注册账号的具体步骤：

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_13.png)

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_15.png)

1.  在搜索引擎中查找“Hugging Face”并进入其官网。
2.  点击页面右上角的“Sign Up”按钮。
3.  输入你的电子邮箱地址并设置密码。
4.  填写用户名及其他必要信息。
5.  点击“Create Account”完成账号创建。
6.  账号创建后，请点击“Resend confirmation email”验证你的邮箱地址。

---

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_17.png)

## 第二步：向Meta申请Llama模型使用许可

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_19.png)

上一节我们完成了账号注册，本节中我们来看看如何申请Llama模型的官方使用许可。

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_21.png)

以下是申请模型使用许可的步骤：

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_23.png)

1.  在Hugging Face网站左上角的搜索栏中，输入本次作业需要微调的模型名称：`meta-llama/Meta-Llama-3.1-8B-Instruct`。
2.  在搜索结果中，找到并点击该模型卡片。
3.  进入模型页面后，系统会提示你需要向Meta提交联系信息以获取使用授权。
4.  仔细阅读页面显示的许可协议（License Agreement），点击“Expand”展开并完整阅读。
5.  填写你的个人信息，包括姓名、出生日期、国家/地区、所属机构及职位。
6.  勾选同意条款，并点击“Submit”提交申请。

提交申请后，你的请求状态将显示为“Under Review”。你需要等待Meta的审核结果，授权通知将通过你注册Hugging Face时使用的邮箱发送。通常会在一天内收到回复。如果长时间未收到邮件，请联系助教寻求帮助。

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_25.png)

---

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_27.png)

## 第三步：创建访问令牌（Access Token）

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_29.png)

成功获得模型授权后，我们需要创建一个访问令牌。这个令牌相当于一把钥匙，允许我们的代码安全地登录Hugging Face并下载模型。

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_31.png)

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_33.png)

以下是创建访问令牌的步骤：

1.  在Hugging Face页面，点击右上角的个人头像图标。
2.  在下拉菜单中，选择“Access Tokens”。
3.  在访问令牌页面，点击右上角的“Create new token”按钮。
4.  为新令牌设置一个你喜欢的名称（Token name）。
5.  在权限设置部分，找到“Repository permissions”。
6.  在搜索框中输入模型名称 `meta-llama/Meta-Llama-3.1-8B-Instruct` 并选中它，这确保该令牌有权下载此特定模型。
7.  其他设置保持默认，点击“Create token”完成创建。

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_35.png)

**重要提示**：创建成功后，页面会显示令牌的密钥（Value）。请务必立即点击“Copy”复制并妥善保存此密钥。此密钥一旦关闭页面将无法再次查看，且不应与他人共享，以免他人以你的名义下载模型。

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_37.png)

---

## 第四步：在代码环境中登录并下载模型

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_39.png)

最后一步，我们将使用创建好的访问令牌，在代码环境中登录Hugging Face并下载Llama模型。

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_41.png)

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_43.png)

操作步骤如下：

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_45.png)

1.  在你的代码环境（例如Colab笔记本）中，找到需要输入令牌进行登录的部分。
2.  在相应的 `token` 参数中，粘贴你之前复制的访问令牌密钥。
3.  执行登录命令，成功后通常会显示你为令牌设置的名字。
4.  继续执行导入必要包和下载模型的代码。

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_47.png)

如果访问令牌有效，你将看到模型开始下载的进度条，其中包括模型参数、分词器（Tokenizer）和配置文件等。出现下载进度条即表示你已成功完成所有步骤：注册账号、获得授权、创建令牌并登录下载。

---

![](img/c4ffcaea7f2f1e3d8762052e4dfeee4b_49.png)

本节课中我们一起学习了从零开始获取并下载Hugging Face上Llama模型的完整流程。如果你对任何步骤有疑问或在下载过程中遇到困难，可以随时联系助教。