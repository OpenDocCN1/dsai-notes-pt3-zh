# 2：02_01_02：课程介绍

在本节课中，我们将学习Azure OpenAI服务，并了解如何开始与之交互。我们将从获取服务访问权限开始，介绍创建Azure OpenAI服务资源的最简单方法，并尝试在Playground中部署一个模型。我们将了解Playground是什么、如何使用它以及如何与之交互。这是一种非常直接的方式，让你能够部署Azure OpenAI服务中托管的OpenAI模型。

---

上一节我们介绍了课程的整体目标，本节中我们来看看Azure OpenAI服务的具体入门步骤。

## 访问Azure OpenAI服务

要开始使用Azure OpenAI服务，首先需要获取访问权限。这通常涉及在Azure门户中申请并创建相应的服务资源。

## 创建服务资源

创建Azure OpenAI服务资源是部署模型的第一步。这个过程在Azure门户中完成，只需几个简单的配置步骤。

以下是创建资源的关键步骤：

1.  登录到Azure门户。
2.  在市场中搜索“Azure OpenAI”。
3.  点击“创建”按钮，开始配置新的资源实例。
4.  填写必要的信息，如订阅、资源组、区域和资源名称。
5.  选择定价层，然后查看并创建资源。

## 部署模型与使用Playground

资源创建成功后，下一步就是在Playground中部署一个模型。Playground是一个基于Web的交互式环境，允许你测试和调整模型而无需编写代码。

我们将看到Playground的界面，并学习如何通过它来与部署的模型进行交互。你可以输入提示（prompt），模型会生成相应的补全（completion）。

例如，一个简单的交互代码如下：

```python
# 这是一个概念性示例，实际调用需使用Azure OpenAI SDK
response = openai.Completion.create(
    engine="your-deployment-name",
    prompt="Translate the following English text to French: 'Hello, world.'",
    max_tokens=60
)
print(response.choices[0].text.strip())
```

通过Playground，你可以快速测试不同提示和参数设置对模型输出的影响。

![](img/b758b694394add08901fe9eddd229f5a_1.png)

---

本节课中我们一起学习了Azure OpenAI服务的入门知识。我们了解了如何获取服务访问权限、创建服务资源，以及如何在Playground中部署并交互式地测试模型。这为后续更深入的应用开发奠定了实践基础。