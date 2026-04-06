# 017：对话缓冲窗口记忆 🧠

在本节课中，我们将学习如何在LangChain聊天应用中实现记忆功能，使大型语言模型能够记住并回顾之前的对话内容。

大型语言模型本身不会自动记住对话历史。在使用类似ChatGPT的工具时，我们常常认为它能记住信息是理所当然的。上一节中，我们通过维护一组提示和响应的数组来实现记忆。现在，我们将学习如何使用LangChain内置的缓冲区记忆功能。

让我们进入代码环节。以下是实现的基础设置。

![](img/80e87b75f632c1213742c31f7d3f48c8_1.png)

```python
# 基础设置代码
import os
from langchain.chat_models import ChatOpenAI
from langchain.prompts import ChatPromptTemplate
from langchain.schema import HumanMessage, AIMessage, SystemMessage
```

![](img/80e87b75f632c1213742c31f7d3f48c8_3.png)

![](img/80e87b75f632c1213742c31f7d3f48c8_4.png)

![](img/80e87b75f632c1213742c31f7d3f48c8_5.png)

## 构建简单对话类

我们将创建一个名为 `SimpleConversation` 的类，作为我们构建聊天应用的基础。

![](img/80e87b75f632c1213742c31f7d3f48c8_7.png)

```python
class SimpleConversation:
    def __init__(self, model_name="gpt-3.5-turbo", system_prompt="You are a helpful assistant.", temperature=0.3):
        self.model_name = model_name
        self.system_prompt = system_prompt
        self.temperature = temperature
        self.history = []
```

这个类初始化时接收模型名称、系统提示词和温度参数。我们使用LangChain的提示模板来组织对话历史，并以系统提示和初始人类消息开始。同时，我们创建了一个 `history` 列表来存储所有先前的消息。

![](img/80e87b75f632c1213742c31f7d3f48c8_9.png)

## 实现聊天与记忆功能

上一节我们介绍了类的结构，本节中我们来看看如何实现核心的聊天与记忆方法。

![](img/80e87b75f632c1213742c31f7d3f48c8_11.png)

以下是 `SimpleConversation` 类中 `chat` 方法的关键实现：

![](img/80e87b75f632c1213742c31f7d3f48c8_13.png)

![](img/80e87b75f632c1213742c31f7d3f48c8_14.png)

```python
    def chat(self, human_input):
        # 将人类输入添加到历史记录
        self.history.append(HumanMessage(content=human_input))
        
        # 构建包含完整历史的提示
        prompt = ChatPromptTemplate.from_messages([
            SystemMessage(content=self.system_prompt),
            *self.history
        ])
        
        # 调用模型获取响应
        llm = ChatOpenAI(model_name=self.model_name, temperature=self.temperature)
        ai_response = llm(prompt.format_messages())
        
        # 将AI响应添加到历史记录
        self.history.append(AIMessage(content=ai_response.content))
        
        return ai_response.content
```

`chat` 方法接收用户输入，将其作为 `HumanMessage` 存入历史列表。然后，它构建一个包含系统提示和整个对话历史的提示，发送给语言模型。获取AI响应后，再将其作为 `AIMessage` 存入历史。这样就实现了对话的连续性。

![](img/80e87b75f632c1213742c31f7d3f48c8_16.png)

## 历史记录的管理与查看

![](img/80e87b75f632c1213742c31f7d3f48c8_17.png)

为了便于调试和观察，我们还需要一些方法来查看和管理对话历史。

以下是相关的辅助方法：

![](img/80e87b75f632c1213742c31f7d3f48c8_19.png)

![](img/80e87b75f632c1213742c31f7d3f48c8_20.png)

![](img/80e87b75f632c1213742c31f7d3f48c8_21.png)

```python
    def get_history(self):
        """返回完整的历史记录列表"""
        return self.history
    
    def print_history(self):
        """以更易读的格式打印历史记录"""
        for msg in self.history:
            print(f"{type(msg).__name__}: {msg.content}")
    
    def clear_history(self):
        """清空对话历史"""
        self.history = []
```

`get_history` 方法返回原始的历史记录对象。`print_history` 方法以更清晰的格式打印每条消息及其类型。`clear_history` 方法则用于重置对话。

![](img/80e87b75f632c1213742c31f7d3f48c8_23.png)

![](img/80e87b75f632c1213742c31f7d3f48c8_25.png)

## 功能演示与应用

现在，让我们通过一个例子来看看这个简单对话类如何工作。

![](img/80e87b75f632c1213742c31f7d3f48c8_27.png)

![](img/80e87b75f632c1213742c31f7d3f48c8_28.png)

```python
# 创建一个对话实例
conv = SimpleConversation()

![](img/80e87b75f632c1213742c31f7d3f48c8_30.png)

# 第一轮对话
print(conv.chat("Hello"))
# 输出: Hello! How can I assist you today?

![](img/80e87b75f632c1213742c31f7d3f48c8_32.png)

# 第二轮对话
print(conv.chat("What is my name?"))
# 输出: I'm sorry, I don't have that information. You haven't told me your name yet.

# 第三轮对话：提供信息
print(conv.chat("Oh, sorry. My name is Jeff."))
# 输出: Nice to meet you, Jeff! How can I help you?

![](img/80e87b75f632c1213742c31f7d3f48c8_34.png)

# 第四轮对话：验证记忆
print(conv.chat("What is my name?"))
# 输出: Your name is Jeff.
```

如示例所示，模型在被告知名字后，能够在后续对话中正确回忆。我们也可以使用系统提示来约束对话主题。

```python
# 创建一个专注于华盛顿大学的对话助手
washu_bot = SimpleConversation(system_prompt="You are BearBot, a helpful assistant that only answers questions about Washington University.")

![](img/80e87b75f632c1213742c31f7d3f48c8_36.png)

![](img/80e87b75f632c1213742c31f7d3f48c8_37.png)

print(washu_bot.chat("What is my name?"))
# 模型可能不会回答名字问题，而是引导回华盛顿大学主题。

![](img/80e87b75f632c1213742c31f7d3f48c8_39.png)

print(washu_bot.chat("What's the tallest building in the world?"))
# 模型会将其理解为询问华盛顿大学校园内的建筑。
```

![](img/80e87b75f632c1213742c31f7d3f48c8_41.png)

## 当前实现的局限性

![](img/80e87b75f632c1213742c31f7d3f48c8_43.png)

我们目前实现的记忆系统是最基础的。`history` 列表会随着对话进行而不断增长。如果对话非常长，这个列表可能会超出模型上下文窗口的限制，导致错误。

![](img/80e87b75f632c1213742c31f7d3f48c8_45.png)

LangChain早期版本提供了多种记忆管理类（如可截断或可总结的记忆）。现在，这些高级功能更多地需要开发者自行构建。在后续章节中，我们将学习如何创建更高级的记忆策略，例如设置一个滑动窗口来丢弃旧消息，或者对历史对话进行动态总结。

本节课中我们一起学习了如何在LangChain中实现一个简单的对话缓冲记忆。我们创建了一个 `SimpleConversation` 类，它能够存储和调用完整的对话历史，从而使大型语言模型具备连续对话的能力。当前实现是基础的、无限制增长的记忆。在接下来的课程中，我们将探索如何优化记忆管理，以处理更长的对话并提升效率。