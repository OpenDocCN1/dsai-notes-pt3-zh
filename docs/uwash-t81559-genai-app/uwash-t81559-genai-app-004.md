# 004：LangChain入门 🚀

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_1.png)

在本节课中，我们将学习LangChain的基础知识。LangChain是一个强大的Python和JavaScript库，它可以帮助我们更高效地利用大型语言模型。我们将从设置环境开始，逐步了解其核心概念，包括对话格式、提示模板和链式操作。

---

## 环境设置与API密钥 🔑

要使用LangChain，首先需要设置环境并获取OpenAI的API密钥。以下是具体步骤。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_3.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_4.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_5.png)

首先，我们需要安装必要的库并配置API密钥。在Google Colab等环境中，可以通过管理“Secrets”来安全地存储和使用密钥。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_6.png)


![](img/2c6443cb0cc17de9e47e3d2e85086a2e_8.png)

```python
# 安装必要的库
!pip install langchain langchain-openai

# 导入库并设置API密钥
import os
from google.colab import userdata
# 从Colab Secrets获取密钥
os.environ["OPENAI_API_KEY"] = userdata.get('OPENAI_API_KEY')
```

运行上述代码后，环境就配置好了。如果系统提示请求访问密钥，请授权。接下来，我们就可以开始使用LangChain了。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_10.png)

---

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_11.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_13.png)

## 理解对话格式 💬

上一节我们完成了环境设置，本节中我们来看看LangChain如何处理与大型语言模型的对话。理解对话格式是构建有效交互的基础。

在LangChain中，对话通常由三种类型的消息组成：
*   **系统消息**：定义对话的整体规则和AI的角色。例如，`你是一个乐于助人且简洁准确的助手。`
*   **人类消息**：代表用户向AI提出的问题或指令。
*   **AI消息**：代表AI模型给出的回复。

以下是一个简单的对话流程示例：


![](img/2c6443cb0cc17de9e47e3d2e85086a2e_15.png)

```python
from langchain_openai import ChatOpenAI
from langchain.schema import SystemMessage, HumanMessage, AIMessage
# 初始化模型，推荐使用成本效益高的 gpt-4o-mini
llm = ChatOpenAI(model="gpt-4o-mini")

# 构建消息列表
messages = [
    SystemMessage(content="你是一个乐于助人且简洁准确的助手。"),
    HumanMessage(content="法国的首都是哪里？")
]

# 获取模型回复
response = llm.invoke(messages)
print(response.content)
# 输出：法国的首都是巴黎。
print(f"使用的总令牌数：{response.response_metadata['token_usage']['total_tokens']}")
# 输出示例：使用的总令牌数：37
```

这段代码展示了如何发起一次简单的问答。系统消息设定了AI的角色，人类消息提出了问题，AI则给出了回答。响应中还包含了本次调用消耗的令牌数，这对于成本控制很重要。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_17.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_18.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_19.png)

---

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_21.png)

## 构建多轮对话 🔄

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_23.png)

我们已经学会了发起单轮对话，现在来看看如何让AI记住上下文，进行连续的多轮对话。这通过维护一个消息列表来实现。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_24.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_25.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_26.png)

以下是构建多轮对话的步骤：

1.  首先，像之前一样初始化模型并发送第一条消息。
2.  将AI的回复（`AIMessage`）添加到消息列表中。
3.  接着添加新的人类消息，然后再次调用模型。


![](img/2c6443cb0cc17de9e47e3d2e85086a2e_28.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_29.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_30.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_31.png)

```python
# 接上例，将AI的回复加入历史
messages.append(response)
# 添加新的人类消息，进行追问
messages.append(HumanMessage(content="你确定吗？我听说因为某些原因改名了，就像伊斯坦布尔和君士坦丁堡那样。"))

# 再次调用模型，它会基于完整的对话历史进行回复
response2 = llm.invoke(messages)
print(response2.content)
# 输出示例：不，巴黎没有被改名。它仍然是法国的首都...
```

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_33.png)

通过这种方式，AI能够理解对话的上下文，并给出连贯的回复。你可以不断追加消息，模拟真实的聊天过程。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_35.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_36.png)

---

## 使用提示模板 📝

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_38.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_39.png)

上一节我们手动构建了对话，但对于结构化的任务，使用提示模板会更高效。提示模板允许我们定义带有变量的文本，然后动态地填充这些变量。

例如，我们可以创建一个生成博客文章标题的模板。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_41.png)


![](img/2c6443cb0cc17de9e47e3d2e85086a2e_42.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_43.png)


![](img/2c6443cb0cc17de9e47e3d2e85086a2e_45.png)

```python
from langchain.prompts import PromptTemplate
# 定义一个提示模板，其中 {topic} 和 {language} 是占位符
title_template = PromptTemplate.from_template(
    "请为关于{topic}的博客文章生成一个标题，使用{language}语言。"
)
# 使用具体值填充模板
filled_prompt = title_template.format(topic="数据科学家的宠物", language="英语")
print(filled_prompt)
# 输出：请为关于数据科学家的宠物的博客文章生成一个标题，使用英语语言。

# 将填充后的提示发送给模型
response = llm.invoke([HumanMessage(content=filled_prompt)])
print(response.content)
# 输出示例：《数据科学家的毛茸茸伙伴：宠物如何激发创新》
```

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_47.png)

提示模板让重复性的提示构造变得简单且一致，是进行提示工程的基础工具。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_49.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_50.png)

---

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_52.png)

## 创建链式操作 ⛓️

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_54.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_55.png)

提示模板本身很有用，但LangChain真正的威力在于将多个步骤连接成“链”。链允许我们将一个任务的输出作为另一个任务的输入，实现复杂的自动化流程。

假设我们想先让AI生成一个博客标题，然后根据这个标题撰写完整的文章。

以下是创建和运行一个简单链的步骤：

1.  定义两个提示模板：一个用于生成标题，一个用于撰写文章。
2.  使用`LLMChain`将模型和提示模板连接起来。
3.  按顺序运行这些链。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_57.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_58.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_59.png)


![](img/2c6443cb0cc17de9e47e3d2e85086a2e_60.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_61.png)


![](img/2c6443cb0cc17de9e47e3d2e85086a2e_63.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_64.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_65.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_66.png)

```python
from langchain.chains import LLMChain
# 第一步：生成标题的链
title_prompt = PromptTemplate.from_template("为关于{topic}的博客文章想一个吸引人的标题。")
title_chain = LLMChain(llm=llm, prompt=title_prompt)

# 第二步：撰写文章的链（假设我们拿到了上一步生成的标题）
# 注意：这里为了演示，我们手动模拟了标题。实际应用中，上一步的输出会作为这里的输入。
blog_prompt = PromptTemplate.from_template("根据这个标题写一篇简短的博客文章：{title}")
blog_chain = LLMChain(llm=llm, prompt=blog_prompt)

# 运行链：先生成标题，再根据标题写文章
generated_title = title_chain.run(topic="摄影")
print(f"生成的标题：{generated_title}")
blog_post = blog_chain.run(title=generated_title)
print(f"撰写的文章：\n{blog_post}")
```

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_67.png)

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_68.png)

在实际的`SequentialChain`中，这个过程会自动衔接。这个例子展示了链的核心思想：将大型语言模型整合到可重复、多步骤的工作流中。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_70.png)

---

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_71.png)

## 总结 📚

本节课我们一起学习了LangChain的入门知识。

![](img/2c6443cb0cc17de9e47e3d2e85086a2e_73.png)

我们首先完成了环境和API密钥的设置。接着，我们理解了与大型语言模型交互的基本对话格式，包括系统消息、人类消息和AI消息。然后，我们通过维护消息列表实现了多轮对话。之后，我们引入了提示模板，使提示的构建更加灵活和可复用。最后，我们探索了LangChain的核心功能——链，它能够将多个操作（如生成标题和撰写文章）串联起来，构建自动化的工作流。

通过掌握这些基础概念，你已经可以开始使用LangChain来创建更结构化、更强大的生成式AI应用了。在后续课程中，我们将深入探讨更高级的功能。