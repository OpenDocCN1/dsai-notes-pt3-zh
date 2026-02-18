# P33： LLM应用高效开发利器 - LangChain命令行工具与模版 🚀

在本节课中，我们将学习如何利用LangChain的命令行工具（CLI）和预置模板（Template）来高效地开发大语言模型应用。我们将通过两个具体示例，手把手演示如何安装工具、创建应用、集成模板并运行。

---

## 📦 概述

LangChain CLI是LangChain的命令行工具，它能帮助我们快速创建和管理LangChain应用、安装开发包以及管理本地运行环境。LangChain模板则为开发者提供了快速构建生产级别大模型应用的能力，覆盖了主流应用场景，实现了标准化和模板化。开发者可以基于模板一键生成功能，极大提升开发效率，并能将自己的实现以模板形式发布供他人复用。

![](img/917d757caffc013da86eb71b74acdb16_1.png)

上一节我们介绍了LangChain的基本概念，本节中我们来看看如何利用其官方工具链来加速开发。

![](img/917d757caffc013da86eb71b74acdb16_3.png)

---

![](img/917d757caffc013da86eb71b74acdb16_5.png)

## 🛠️ 安装LangChain命令行工具

首先，我们需要安装LangChain命令行工具。以下是安装步骤：

![](img/917d757caffc013da86eb71b74acdb16_7.png)

![](img/917d757caffc013da86eb71b74acdb16_9.png)

1.  打开终端或命令提示符。
2.  执行以下pip安装命令：

![](img/917d757caffc013da86eb71b74acdb16_11.png)

```bash
pip install langchain-cli
```

![](img/917d757caffc013da86eb71b74acdb16_13.png)

安装完成后，可以通过运行 `langchain --help` 命令来查看工具支持的功能，例如管理应用、启动服务或基于模板创建工作。

---

## 🏗️ 创建第一个LangChain应用

安装好CLI后，我们可以开始创建应用。以下是创建应用的步骤：

![](img/917d757caffc013da86eb71b74acdb16_15.png)

![](img/917d757caffc013da86eb71b74acdb16_17.png)

1.  使用 `langchain app` 命令创建一个新应用。我们将应用命名为 `my_app`：

![](img/917d757caffc013da86eb71b74acdb16_19.png)

```bash
langchain app my_app
```

![](img/917d757caffc013da86eb71b74acdb16_21.png)

2.  创建过程中，CLI会询问是否要添加额外的包（即模板）。初次创建时可以选择跳过。
3.  创建完成后，进入应用目录查看结构：

![](img/917d757caffc013da86eb71b74acdb16_23.png)

```bash
cd my_app
```

![](img/917d757caffc013da86eb71b74acdb16_25.png)

![](img/917d757caffc013da86eb71b74acdb16_27.png)

一个标准的LangChain应用目录包含以下核心部分：
*   `app/`：存放应用主逻辑的Python脚本。
*   `packages/`：存放后续安装的模板包。
*   `pyproject.toml`：用于管理Python依赖。
*   `Dockerfile`：用于构建Docker镜像。

![](img/917d757caffc013da86eb71b74acdb16_29.png)

---

## 📝 添加并使用第一个模板：Paris Speak

我们将通过添加 `paris-speak` 模板来演示模板的使用。这个模板的功能是将用户输入转换成海盗风格的语言。

以下是具体操作步骤：

![](img/917d757caffc013da86eb71b74acdb16_31.png)

1.  **添加模板**：在应用根目录下，运行以下命令来添加模板。根据环境管理方式，可能需要使用 `poetry run` 前缀。

```bash
poetry run langchain app add paris-speak
```

2.  **确认安装**：执行命令后确认安装。模板会被下载并安装到 `packages/` 目录下。
3.  **集成模板代码**：安装完成后，CLI会提示需要将一段代码添加到应用的主文件中。复制该段代码。
4.  **修改应用文件**：打开 `app/server.py` 文件。这是一个标准的FastAPI应用文件。找到被注释掉的示例路由，将复制的代码粘贴进去，从而添加一个名为 `/paris-speak` 的新路由。
5.  **配置环境变量**：该模板默认使用OpenAI模型，因此需要设置 `OPENAI_API_KEY` 环境变量。在终端中执行：

![](img/917d757caffc013da86eb71b74acdb16_33.png)

```bash
export OPENAI_API_KEY="你的OpenAI API密钥"
```

![](img/917d757caffc013da86eb71b74acdb16_35.png)

6.  **启动应用**：配置好环境变量后，使用以下命令启动应用：

```bash
poetry run langchain serve
```

7.  **测试应用**：应用启动后，在浏览器中访问 `http://127.0.0.1:8000/paris-speak/playground`。在此界面输入文本（例如 “How are you”），即可看到模型将其转换成的海盗风格回复。你还可以通过 `http://127.0.0.1:8000/docs` 查看自动生成的API文档。

---

## 🔄 添加第二个模板：CSV Agent

接下来，我们为同一个应用添加第二个模板 `csv-agent`。这个模板能够基于CSV文件（示例数据为泰坦尼克号乘客名单）进行智能问答。

![](img/917d757caffc013da86eb71b74acdb16_37.png)

![](img/917d757caffc013da86eb71b74acdb16_39.png)

以下是添加第二个模板的步骤：

![](img/917d757caffc013da86eb71b74acdb16_41.png)

![](img/917d757caffc013da86eb71b74acdb16_43.png)

1.  **停止当前应用**：在终端中按 `Ctrl+C` 停止正在运行的应用服务。
2.  **添加新模板**：运行以下命令添加 `csv-agent` 模板：

```bash
poetry run langchain app add csv-agent
```

![](img/917d757caffc013da86eb71b74acdb16_45.png)

3.  **集成代码**：同样，复制CLI提示的代码段，并将其添加到 `app/server.py` 文件中，为应用增加一个新的 `/csv-agent` 路由。
4.  **重启应用**：再次运行启动命令：

![](img/917d757caffc013da86eb71b74acdb16_47.png)

```bash
poetry run langchain serve
```

![](img/917d757caffc013da86eb71b74acdb16_49.png)

5.  **测试新功能**：应用重启后，访问 `http://127.0.0.1:8000/csv-agent/playground`。你可以针对泰坦尼克号数据提问，例如：“谁在Cabin E46？”。界面会展示智能体思考的中间步骤和最终答案，验证基于数据的检索与问答功能。

---

## 💡 总结与扩展

本节课中我们一起学习了LangChain两大高效开发利器的使用：
1.  **LangChain CLI**：用于快速搭建应用框架和管理依赖。
2.  **LangChain 模板**：提供了开箱即用的场景化解决方案，如风格转换(`paris-speak`)和基于文档的问答(`csv-agent`)。

通过以上流程，你可以将不同的模板（如RAG、对话机器人等）像积木一样组合到同一个应用中。每个模板可能需要不同的环境变量或依赖，使用时需参考其文档进行相应配置。

> **提示**：LangChain官方仓库提供了大量模板，涵盖了检索增强生成（RAG）、多索引融合、路由等热门场景，开发者可以根据需求选用。

本节课我们聚焦于本地开发与测试。关于如何使用LangSmith进行应用发布、监控，以及如何使用RemoteRunnable远程调用本地LangChain应用，我们将在后续的课程中详细介绍。

---

![](img/917d757caffc013da86eb71b74acdb16_51.png)

**本节课中我们一起学习了**：如何安装和利用LangChain CLI创建应用，以及如何通过添加预置模板来快速实现风格转换和基于CSV数据的问答功能，从而显著提升LLM应用的开发效率。