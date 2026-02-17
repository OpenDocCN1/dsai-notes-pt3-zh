# 大型语言模型实践：P93：16_01_01_引言_3

## 📖 概述
在本节课中，我们将学习在Azure平台上部署大型语言模型（LLM）的多种不同方式。我们将探索并评估Azure上的相关服务，包括Azure Machine Learning和OpenAI服务。我们不仅会了解部署选项，还会深入分析Azure Machine Learning Studio与Azure OpenAI服务之间的具体区别，以及在不同场景下如何选择使用它们。

![](img/1b4402348a4e02759b4232922d905fb3_0.png)

---

## 🚀 在Azure上部署大型语言模型
我们可以在Azure上通过多种不同的方式来部署大型语言模型，接下来我们将看到其中一些选项。

我们将探索并评估Azure上的大型语言模型。

我们将使用不同的服务，例如Azure Machine Learning以及OpenAI。

我们不仅会了解部署选项，还会尝试明确Azure Machine Learning Studio与OpenAI服务之间的具体区别。

我们将分析Azure OpenAI服务，明确其具体差异，并探讨在何种情况下你可能希望选择使用其中一种而非另一种。

---

## 🔍 核心服务对比
上一节我们介绍了Azure上部署LLM的多种途径，本节中我们来看看两个核心服务：Azure Machine Learning Studio 和 Azure OpenAI Service。理解它们的区别对于选择合适的部署方案至关重要。

以下是Azure Machine Learning Studio与Azure OpenAI Service的主要区别点：

*   **服务定位**：Azure Machine Learning是一个全面的机器学习平台，支持从数据准备到模型训练、部署和管理的全生命周期。而Azure OpenAI Service则是一个专门为访问和部署OpenAI强大模型（如GPT系列）而设计的托管服务。
*   **核心功能**：Azure Machine Learning Studio侧重于提供工具和环境，让用户能够构建和部署**自定义的**机器学习模型。Azure OpenAI Service则侧重于提供对**预训练好**的、业界领先的大型语言模型的API访问。
*   **使用场景**：当你需要基于自有数据训练定制化模型，或管理复杂的ML工作流时，Azure Machine Learning是更合适的选择。当你希望快速集成和使用如文本生成、代码补全、内容摘要等开箱即用的高级AI能力时，应选择Azure OpenAI Service。
*   **管理复杂度**：使用Azure Machine Learning通常需要更多的机器学习专业知识来配置和管理训练管道及计算资源。Azure OpenAI Service作为托管服务，简化了底层基础设施的管理，让开发者能更专注于应用开发。

---

## ✅ 总结
本节课中，我们一起学习了在Azure云平台上部署大型语言模型的概况。我们了解到存在多种部署路径，并重点对比分析了两个核心服务——**Azure Machine Learning Studio** 与 **Azure OpenAI Service**。关键点在于：前者是一个用于构建和部署自定义模型的综合性ML平台，而后者是一个用于快速集成预训练大语言模型的专用托管服务。根据你的具体需求是模型定制开发还是快速能力集成，你可以做出更合适的选择。