#  047：通过Copilot学习Python-DevOps关键技能 🚀

![](img/bfd702ce187956a203b8fc6cf146b1c7_0.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_2.png)

在本节课中，我们将学习如何从零开始构建一个完整的Python项目，涵盖从环境配置、库开发、命令行工具、Web微服务到云端部署的全过程。我们将利用GitHub Copilot等现代工具来加速开发，并实践DevOps中的持续集成与持续交付理念。

![](img/bfd702ce187956a203b8fc6cf146b1c7_4.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_6.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_8.png)

## 概述

![](img/bfd702ce187956a203b8fc6cf146b1c7_10.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_12.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_14.png)

Python函数是许多有趣任务的核心，它可以被视为一个中心枢纽，连接着库开发、GPU编程、数据科学、微服务、命令行工具和事件驱动编程等多个领域。本节课的目标是掌握围绕Python函数构建复杂系统的关键技能。

## 第一步：配置开发环境 ⚙️

![](img/bfd702ce187956a203b8fc6cf146b1c7_16.png)

上一节我们概述了Python函数的中心地位，本节中我们来看看如何搭建一个高效的开发环境。

![](img/bfd702ce187956a203b8fc6cf146b1c7_18.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_20.png)

一个配置良好的环境是快速开发的基础。我们将使用基于云的开发环境来确保一致性和可复现性。

![](img/bfd702ce187956a203b8fc6cf146b1c7_22.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_24.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_26.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_28.png)

以下是配置环境的核心步骤：

![](img/bfd702ce187956a203b8fc6cf146b1c7_30.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_32.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_34.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_36.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_38.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_40.png)

1.  **配置GitHub Codespaces（或等效环境）**：我们选择GitHub Codespaces作为开发环境。它可以提供强大的计算资源（如16核CPU、32GB内存），甚至支持NVIDIA GPU，非常适合需要处理复杂任务的项目。
2.  **创建项目脚手架**：初始化项目结构，包括必要的配置文件。
    *   `Makefile`：用于定义常见的开发命令（如安装、测试、格式化）。
    *   `requirements.txt`：列出项目依赖的Python包。
    *   `README.md`：项目说明文档。
3.  **（可选）设置虚拟环境**：即使在容器化环境中，使用虚拟环境也能进一步隔离依赖，减少潜在的冲突。可以通过在`.bashrc`中配置来自动激活。
4.  **（可选）在`requirements.txt`之外单独安装IPython**：IPython是一个强大的交互式Python shell，非常适合快速测试和调试。将其独立安装可以避免将其打包到最终部署中。

![](img/bfd702ce187956a203b8fc6cf146b1c7_42.png)

完成这些步骤后，我们就拥有了一个可以立即开始编码的基础项目结构。

![](img/bfd702ce187956a203b8fc6cf146b1c7_44.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_45.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_47.png)

## 第二步：掌握交互式调试 🐛

现在我们已经搭建好了项目脚手架，接下来需要掌握如何高效地测试和调试代码。交互式工具是关键。

利用IPython和IPDB（IPython调试器）可以极大地提升原型设计和调试效率。

以下是使用交互式工具的方法：

![](img/bfd702ce187956a203b8fc6cf146b1c7_49.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_51.png)

*   **使用IPython进行快速实验**：在IPython终端中，你可以像使用计算器一样执行Python语句，测试变量赋值、类型检查以及快速构建和测试函数。`who`命令可以显示当前内存中加载的所有对象，有助于理解代码状态。
*   **使用IPDB进行脚本调试**：在Python脚本中，你可以通过`import ipdb; ipdb.set_trace()`设置断点。当脚本运行到该行时，会进入一个交互式调试会话，允许你逐行执行代码、检查变量值，就像在IPython中一样。

![](img/bfd702ce187956a203b8fc6cf146b1c7_53.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_55.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_57.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_59.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_61.png)

掌握这些工具能让你在遇到问题时快速定位和解决。

![](img/bfd702ce187956a203b8fc6cf146b1c7_63.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_65.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_67.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_69.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_71.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_73.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_75.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_77.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_79.png)

## 第三步：构建库、CLI工具与测试 🧱

![](img/bfd702ce187956a203b8fc6cf146b1c7_81.png)

有了调试能力，我们就可以开始构建项目的核心逻辑了。最佳实践是先构建库，再基于库创建命令行工具，并同时编写测试。

![](img/bfd702ce187956a203b8fc6cf146b1c7_83.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_85.png)

将核心逻辑封装在库中，然后通过命令行工具进行调用和测试，这是一种高效且可维护的开发模式。

以下是构建库和CLI的流程：

1.  **创建库结构**：在项目下创建`mylib/`目录，并添加`__init__.py`文件，使其成为一个Python包。
2.  **使用Copilot编写库代码**：在库模块（如`mylib/calc.py`）中，通过编写清晰的注释（提示）来引导Copilot生成函数代码，例如计算器功能（加、减、乘、除、乘方）。
3.  **创建命令行工具**：使用`click`库创建CLI。Copilot可以根据库中的函数和注释，快速生成对应的`click`命令和参数解析逻辑。
4.  **编写并运行测试**：为库函数和CLI命令编写单元测试和集成测试。Copilot同样可以辅助生成测试用例。使用`pytest`运行测试，确保代码质量。

![](img/bfd702ce187956a203b8fc6cf146b1c7_87.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_89.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_91.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_93.png)

通过这个流程，我们得到了一个经过测试的、功能完整的库及其对应的命令行接口。

![](img/bfd702ce187956a203b8fc6cf146b1c7_95.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_97.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_99.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_101.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_103.png)

## 第四步：构建Web微服务 🌐

![](img/bfd702ce187956a203b8fc6cf146b1c7_105.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_107.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_109.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_111.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_113.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_115.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_117.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_119.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_121.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_122.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_124.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_126.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_128.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_130.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_132.png)

库和CLI工具在本地运行良好，接下来我们需要将其能力通过Web API暴露出来，构建一个微服务。

![](img/bfd702ce187956a203b8fc6cf146b1c7_134.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_136.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_138.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_140.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_142.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_144.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_145.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_147.png)

使用FastAPI框架，我们可以轻松地将库中的函数转换为RESTful API端点。

以下是构建微服务的步骤：

1.  **创建主应用文件**：创建`main.py`，导入FastAPI和我们的库（如`mylib.logistics`）。
2.  **定义API端点**：为库中的功能创建对应的HTTP端点（如`GET /cities`， `POST /distance`， `POST /travel_time`）。Copilot可以帮助生成端点函数和Pydantic模型。
3.  **运行和测试API**：在开发环境中运行服务，并通过FastAPI自动生成的交互式文档（`/docs`）来测试各个端点。
4.  **编写Web服务测试**：使用`TestClient`为API端点编写测试，确保HTTP层面的功能正确。

![](img/bfd702ce187956a203b8fc6cf146b1c7_149.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_151.png)

现在，我们的逻辑不仅可以通过库和CLI访问，还可以通过网络API提供服务。

![](img/bfd702ce187956a203b8fc6cf146b1c7_153.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_155.png)

## 第五步：容器化与云端部署 ☁️

![](img/bfd702ce187956a203b8fc6cf146b1c7_157.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_159.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_161.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_163.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_165.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_167.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_169.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_171.png)

为了使微服务能够在生产环境中运行，我们需要将其容器化并部署到云平台。

![](img/bfd702ce187956a203b8fc6cf146b1c7_173.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_175.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_177.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_179.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_181.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_183.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_185.png)

我们将使用Docker进行容器化，并部署到AWS的托管服务上。

![](img/bfd702ce187956a203b8fc6cf146b1c7_187.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_189.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_191.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_193.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_195.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_196.png)

以下是部署流程：

![](img/bfd702ce187956a203b8fc6cf146b1c7_198.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_200.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_202.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_204.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_206.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_208.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_210.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_212.png)

1.  **创建Dockerfile**：定义构建容器镜像的步骤，包括基础镜像、依赖安装和启动命令。
2.  **构建和本地测试镜像**：使用`docker build`构建镜像，并用`docker run`在本地运行测试，确保容器内应用正常工作。
3.  **推送镜像到容器仓库**：将构建好的镜像推送到AWS Elastic Container Registry (ECR)。
4.  **使用AWS App Runner部署服务**：在AWS控制台创建App Runner服务，选择来自ECR的容器镜像，配置端口和资源，即可完成部署。App Runner会自动处理负载均衡、扩缩容和HTTPS。
5.  **设置持续交付**：通过AWS CodeBuild配置构建项目，监听GitHub仓库的变更。每当代码更新时，CodeBuild会自动执行构建、测试、打包和部署到ECR的流程，从而实现持续交付。

![](img/bfd702ce187956a203b8fc6cf146b1c7_214.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_215.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_217.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_218.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_220.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_222.png)

至此，我们实现了一个从代码提交到服务自动更新的完整CI/CD流水线。

![](img/bfd702ce187956a203b8fc6cf146b1c7_224.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_226.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_228.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_230.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_231.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_232.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_233.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_235.png)

## 总结

![](img/bfd702ce187956a203b8fc6cf146b1c7_237.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_239.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_241.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_243.png)

![](img/bfd702ce187956a203b8fc6cf146b1c7_245.png)

本节课中我们一起学习了如何以Python函数为核心，从零开始构建一个完整的应用。我们涵盖了环境配置、交互式调试、库开发、命令行工具构建、Web微服务创建，以及最终的容器化与云端部署。整个过程充分利用了GitHub Copilot等现代AI辅助编程工具和云原生服务，展示了高效、现代的DevOps开发流程。通过这个实践，你不仅掌握了Python编程的关键技能，也了解了如何将代码转化为可运维的生产级服务。