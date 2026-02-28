#  043：在Cloud9中使用Python构建自然语言处理应用 🚀

![](img/49dbae96a6a51096a792e8e24e6b48f1_0.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_2.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_4.png)

在本节课中，我们将学习如何通过函数式编程构建一个可复用的自然语言处理（NLP）应用。我们将从核心逻辑开发开始，逐步将其封装为库，并最终映射到命令行工具和自动化工作流中。

![](img/49dbae96a6a51096a792e8e24e6b48f1_6.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_8.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_9.png)

## 核心概念：函数式逻辑与映射

使用函数构建应用的核心思想是：**将核心逻辑封装在函数内部**。这样，一段代码逻辑就可以被映射到多种不同的应用场景中。

![](img/49dbae96a6a51096a792e8e24e6b48f1_11.png)

例如，我们可以将一段NLP处理逻辑：
*   映射到命令行工具（最简单的方式之一）。
*   映射到交互式的IPython环境中。
*   映射到Web框架中。
*   映射到云函数（如AWS Lambda或GCP Cloud Functions）中。

![](img/49dbae96a6a51096a792e8e24e6b48f1_13.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_14.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_15.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_17.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_18.png)

这种“逻辑-映射”的脚手架结构，使我们能够灵活地适应不同的需求。

![](img/49dbae96a6a51096a792e8e24e6b48f1_20.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_22.png)

## 项目结构与环境搭建

上一节我们介绍了函数式逻辑的映射思想，本节中我们来看看如何搭建一个具体的项目。我们将回到Github Codespaces，开始构建一个项目结构。

首先，我们需要导入一个名为`textblob`的库，它是一个用于构建演示的简化文本处理库。

以下是安装所需库的步骤：
1.  在`requirements.txt`文件中添加`textblob`。
2.  运行`make install`命令来安装依赖。

安装完成后，我们可以使用IPython来快速测试这个库。通过查阅文档，我们可以学习其基本用法。

![](img/49dbae96a6a51096a792e8e24e6b48f1_24.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_26.png)

## 获取与处理文本数据

为了测试NLP功能，我们需要一些文本数据。一个高效的方法是使用`wikipedia`库来自动抓取文本，这样我们就不需要手动创建测试数据了。

以下是获取和处理文本的步骤：
1.  运行`make install`安装`wikipedia`库。
2.  在IPython中，使用`wikipedia.summary()`函数搜索并获取特定主题（例如“Golden State Warriors”）的摘要文本。
3.  将获取的文本传递给`textblob`库进行处理。

现在，我们可以尝试`textblob`提供的多种功能，例如情感分析（`blob.sentiment`）、词性标注（`blob.tags`）和名词短语提取（`blob.noun_phrases`）。首次使用某些功能时，可能需要下载必要的语料库。

## 构建可复用的NLP逻辑库

当我们拥有可以工作的代码后，下一步是将其构建成一个可复用的库。这是一个良好的实践，特别是对于功能相对独立和可重用的代码。

以下是创建NLP逻辑库的步骤：
1.  创建一个名为`nlp_logic`的目录，并在其中添加`__init__.py`文件，使其成为一个Python包。
2.  在该目录下创建核心逻辑文件，例如`core_nlp.py`。
3.  将之前在IPython中测试成功的逻辑提炼成多个函数。

![](img/49dbae96a6a51096a792e8e24e6b48f1_28.png)

我们将构建以下几个核心函数：
*   `search_wikipedia(name)`: 在维基百科中搜索指定名称。
*   `summarize_wikipedia(name)`: 获取指定名称的维基百科摘要。
*   `get_text_blob(text)`: 根据输入的文本创建一个TextBlob对象。
*   `get_phrases(name)`: 这是一个“主函数”，它封装了上述步骤：获取摘要、创建TextBlob对象，并最终返回名词短语列表。

![](img/49dbae96a6a51096a792e8e24e6b48f1_30.png)

在IPython中交互式地导入和测试这些函数，是验证逻辑正确性的强大方式。通过这种方式，我们可以在深入构建具体应用之前，就解决大部分棘手的错误和问题。

## 创建命令行工具

在核心逻辑函数构建并测试无误后，我们可以轻松地将其映射到不同的接口。首先，我们来创建一个命令行工具。

![](img/49dbae96a6a51096a792e8e24e6b48f1_32.png)

创建命令行工具最简单的方法之一是使用`Python Fire`库。它能够自动将函数转换为命令行接口，过程令人惊讶地简单。

![](img/49dbae96a6a51096a792e8e24e6b48f1_34.png)

以下是创建命令行工具的步骤：
1.  安装`fire`库：`make install`。
2.  创建一个新的Python文件，例如`wiki_phrases.py`。
3.  在该文件中，导入我们之前构建的逻辑函数（例如`get_phrases`）。
4.  使用`fire.Fire(get_phrases)`将函数暴露为命令行工具。
5.  添加`#!/usr/bin/env python`作为文件首行（shebang），使其可直接执行。

现在，运行`python wiki_phrases.py --help`就能看到自动生成的帮助信息。通过命令行传递名称参数，如`python wiki_phrases.py “Golden State Warriors”`，即可运行整个流程。这展示了先构建函数逻辑，再使用工具（如Fire）进行封装所能带来的强大威力。

## 完善项目：代码质量与自动化

为了使项目更加专业，我们需要建立开发运维（DevOps）结构，包括代码风格检查、测试和自动化集成。

![](img/49dbae96a6a51096a792e8e24e6b48f1_36.png)

我们将引入以下几个工具：
*   `pytest`: 用于运行测试。
*   `pytest-cov`: 用于生成测试覆盖率报告。
*   `pylint`: 用于代码风格和静态检查。
*   `black`: 用于自动格式化代码。

![](img/49dbae96a6a51096a792e8e24e6b48f1_38.png)

以下是完善项目的步骤：
1.  在`requirements.txt`中添加这些开发依赖。
2.  在`Makefile`中添加相应的命令，例如`make lint`（运行pylint）、`make format`（运行black格式化）、`make test`（运行pytest并生成覆盖率报告）。
3.  创建测试文件，例如`test_core_nlp.py`，并编写至少一个功能测试（例如，断言`get_phrases(“Golden State Warriors”)`的返回结果中包含预期的短语）。
4.  运行`make lint`、`make format`和`make test`来确保一切正常。

![](img/49dbae96a6a51096a792e8e24e6b48f1_40.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_42.png)

## 设置持续集成（CI）

![](img/49dbae96a6a51096a792e8e24e6b48f1_44.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_46.png)

最后，我们可以使用Github Actions为项目设置持续集成（CI）流水线。这样，每次代码推送都会自动运行代码检查、测试和格式化验证。

![](img/49dbae96a6a51096a792e8e24e6b48f1_48.png)

以下是设置CI的步骤：
1.  在项目根目录的`.github/workflows/`路径下创建一个YAML文件（例如`ci.yml`）。
2.  在YAML文件中定义工作流，通常包括以下步骤：
    *   设置指定版本的Python环境。
    *   安装项目依赖（`make install`）。
    *   运行代码检查（`make lint`）。
    *   运行测试（`make test`）。
    *   运行代码格式化检查（`make format`，此步骤通常用于验证代码风格，而非直接修改）。
3.  将配置文件推送到Github仓库，Actions将自动开始运行。
4.  根据CI运行的反馈（例如Python版本不匹配、未使用的导入等）调整代码和配置。
5.  CI通过后，可以创建一个状态徽章（Status Badge），添加到项目的README文件中，直观地展示构建状态。

![](img/49dbae96a6a51096a792e8e24e6b48f1_50.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_52.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_54.png)

![](img/49dbae96a6a51096a792e8e24e6b48f1_56.png)

本节课中我们一起学习了如何从零开始构建一个NLP应用。我们首先在IPython中交互式地探索了`textblob`和`wikipedia`库，然后将核心逻辑封装成可复用的函数库。接着，我们使用`Python Fire`快速创建了命令行工具。最后，我们通过引入`pytest`、`pylint`、`black`等工具和设置Github Actions CI流水线，完善了项目的代码质量和自动化流程。这种“先构建核心函数逻辑，再映射到不同接口”的开发模式，是构建灵活、可维护应用的有效方法。