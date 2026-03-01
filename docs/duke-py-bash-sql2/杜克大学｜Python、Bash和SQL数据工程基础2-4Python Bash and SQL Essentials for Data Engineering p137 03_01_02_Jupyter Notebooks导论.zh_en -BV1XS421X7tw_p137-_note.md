# 数据工程基础：2-4：Jupyter Notebooks导论 🧪

在本节课中，我们将要学习如何使用Jupyter Notebooks。Jupyter Notebook是一个强大的交互式开发环境，广泛应用于数据分析、机器学习和科学计算。我们将从Jupyter Notebook的基础开始，逐步探索其高级功能和云端版本。

## 概述

首先，我们将介绍Jupyter Notebook及其增强版本JupyterLab。接下来，我们会深入了解CoLab，这是一个由Google托管的Jupyter Notebook服务。最后，我们将介绍AWS机器学习套件中的SageMaker服务。让我们开始吧。

---

## Jupyter与JupyterLab

![](img/58456819fb895822718cdc9a115de7a5_0.png)

上一节我们概述了课程内容，本节中我们来看看Jupyter Notebook的核心组件。Jupyter Notebook是一个开源的Web应用程序，允许你创建和共享包含实时代码、公式、可视化和叙述性文本的文档。

JupyterLab是Jupyter Notebook的下一代用户界面。它提供了更灵活的工作区，允许你在一个标签页中并排排列Notebook、终端、文本编辑器和控制台。

以下是Jupyter Notebook的一些核心功能：

*   **交互式代码执行**：你可以逐个单元地运行代码，并立即看到结果。
*   **支持多种语言**：虽然最初是为Python（`IPython`）设计的，但现在通过内核支持Julia、R等语言。
*   **数据可视化**：可以直接在Notebook中生成图表和图形。
*   **Markdown支持**：可以使用Markdown语法编写格式化的文本、添加标题、列表和链接。
*   **易于分享**：Notebook文件（`.ipynb`）可以轻松导出为HTML、PDF等多种格式，便于分享和展示。

## 探索CoLab

在了解了本地Jupyter环境后，本节我们来看看一个流行的云端解决方案。CoLab（Colaboratory）是由Google提供的免费Jupyter Notebook服务。它完全在云端运行，无需任何设置，并且提供了免费的GPU和TPU资源，非常适合机器学习和深度学习项目。

CoLab的核心优势在于其便捷性和强大的计算资源。你只需要一个Google账户，就可以通过浏览器直接访问和运行Notebook。所有的代码执行都在Google的服务器上完成。

以下是使用CoLab的主要步骤：

1.  访问 [colab.research.google.com](https://colab.research.google.com)。
2.  点击“新建笔记本”或上传已有的`.ipynb`文件。
3.  在代码单元中编写Python代码，例如：`print("Hello, Colab!")`。
4.  使用快捷键 **Shift + Enter** 或点击单元左侧的播放按钮来运行代码。
5.  CoLab会自动将你的工作保存到Google Drive。

## AWS SageMaker简介

最后，我们将介绍一个企业级的机器学习平台。Amazon SageMaker是亚马逊云科技（AWS）提供的一项完全托管的服务，它包含了构建、训练和部署机器学习模型的完整工具链。SageMaker Studio提供了一个基于Jupyter的集成开发环境（IDE）。

SageMaker的优势在于它简化了机器学习工作流的每一步，从数据准备到模型部署，并且可以轻松地与其他AWS服务集成，实现大规模、生产级的机器学习应用。

SageMaker Notebook实例是一个完全托管的ML计算实例，预装了Jupyter和常用的数据科学库。你可以通过以下步骤启动一个Notebook实例：

1.  登录AWS管理控制台，导航到SageMaker服务。
2.  在左侧导航栏中，选择“Notebook实例”。
3.  点击“创建Notebook实例”。
4.  配置实例名称、实例类型（如`ml.t3.medium`）、IAM角色等设置。
5.  点击“创建实例”，等待状态变为“InService”。
6.  点击“打开JupyterLab”或“打开Jupyter”，开始使用。

---

![](img/58456819fb895822718cdc9a115de7a5_2.png)

## 总结

本节课中我们一起学习了Jupyter Notebooks生态系统。我们从基础的Jupyter和JupyterLab开始，了解了它们作为交互式计算环境的核心价值。接着，我们探索了Google CoLab，这是一个免配置、提供免费计算资源的云端Notebook服务，极大地方便了协作与实验。最后，我们介绍了AWS SageMaker，这是一个为企业级机器学习项目设计的强大平台，它将Jupyter环境与完整的ML工作流工具深度集成。

掌握这些工具，将帮助你在数据工程和机器学习项目中更高效地进行探索、开发和协作。