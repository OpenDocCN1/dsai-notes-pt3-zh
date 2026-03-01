# 大型语言模型实践：P111：34_02_01：引言 🚀

![](img/277f912196e9df2381236ba44520a64f_0.png)

在本节课中，我们将学习如何超越Azure OpenAI服务的Playground界面，开始通过编程方式与大型语言模型进行交互。我们将介绍Azure OpenAI服务的API、如何通过Python代码调用它们，以及如何管理资源的使用配额与清理。

## 从Playground到API

上一节我们介绍了如何在Azure OpenAI服务的Playground中部署和使用模型。本节中，我们来看看如何通过编程接口与这些模型进行交互。

超越Playground界面，超越仅仅在Playground中部署和使用Azure OpenAI模型，下一步是了解Azure OpenAI服务的API。我们将探讨这意味着什么，以及我们如何实际与这些API进行交互。这些API本质上是HTTP API。

我们将使用不同类型的策略与这些模型进行通信。我们会稍微关注这方面的编码实现，并将使用Python创建一个简单的示例，尝试与部署在Azure OpenAI服务上的大型语言模型进行交互。

## 核心概念与交互策略

我们将通过HTTP请求与模型通信。核心的交互通常涉及向特定的API端点发送一个包含提示（prompt）和其他参数的POST请求，并接收模型生成的响应。

以下是一个基础API调用的伪代码结构：
```python
import requests

response = requests.post(
    url=ENDPOINT_URL,
    headers={"Authorization": "Bearer YOUR_API_KEY"},
    json={
        "prompt": "你的问题或指令",
        "max_tokens": 100
    }
)
generated_text = response.json()["choices"][0]["text"]
```

## 资源管理与清理

最后，我们将了解使用量和配额管理，这对于尝试消费Azure OpenAI服务上的资源非常重要。我们还将学习如何清理这些资源，并了解一些可以采取的措施，以确保在使用完这些大型语言模型后，资源能被正确清理和销毁。

以下是资源管理的关键步骤列表：
*   **监控使用量**：在Azure门户中跟踪令牌消耗和API调用次数。
*   **设置预算与警报**：配置支出上限，在接近限额时接收通知。
*   **删除未使用的资源**：完成实验或项目后，删除相关的Azure OpenAI资源组或特定实例。

## 总结

本节课中，我们一起学习了如何从Azure OpenAI的图形化Playground过渡到通过API编程调用模型。我们了解了API交互的基本原理，预览了使用Python进行调用的方法，并强调了管理使用配额和及时清理资源的重要性。这是将大型语言模型集成到实际应用程序中的关键一步。