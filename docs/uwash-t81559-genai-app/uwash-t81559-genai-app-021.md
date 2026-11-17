# 021：结构化输出解析器 🧩

在本节课中，我们将学习如何使用 LangChain 来解析从大型语言模型查询中返回的数据。大型语言模型可以回答各种问题，但其返回结果通常是未经结构化的文本。我们将看到 LangChain 如何提供工具，帮助我们以结构化的格式（如 JSON）提取和解析这些信息，使数据更易于程序化处理。

---

![](img/45c4163eb91d4d3d2bea901415075ca4_1.png)

上一节我们介绍了解析大模型输出的需求，本节中我们来看看具体的实现步骤。

首先，我们需要设置环境并导入必要的库。以下代码展示了如何安装 LangChain 并配置 OpenAI API 密钥。

```python
# 安装 LangChain
!pip install langchain openai

# 设置 OpenAI API 密钥（示例中从环境变量获取）
import os
os.environ['OPENAI_API_KEY'] = 'your-api-key-here'
```

![](img/45c4163eb91d4d3d2bea901415075ca4_3.png)

---

![](img/45c4163eb91d4d3d2bea901415075ca4_5.png)

接下来，我们将定义一个响应模式。这本质上是一个蓝图，用于指定我们希望从大模型获得的结构化输出格式。

![](img/45c4163eb91d4d3d2bea901415075ca4_7.png)

以下是定义响应模式的代码示例：

```python
from langchain.output_parsers import ResponseSchema, StructuredOutputParser

# 定义期望的响应结构
answer_schema = ResponseSchema(name="answer", description="对用户问题的回答")
source_schema = ResponseSchema(name="source", description="信息的来源或引用")

response_schemas = [answer_schema, source_schema]
output_parser = StructuredOutputParser.from_response_schemas(response_schemas)
```

![](img/45c4163eb91d4d3d2bea901415075ca4_9.png)

![](img/45c4163eb91d4d3d2bea901415075ca4_10.png)

![](img/45c4163eb91d4d3d2bea901415075ca4_11.png)

---

定义了期望的格式后，我们需要构建一个提示模板。这个模板会指导大模型按照我们指定的格式返回数据。

以下是设置提示模板的步骤：

![](img/45c4163eb91d4d3d2bea901415075ca4_13.png)


![](img/45c4163eb91d4d3d2bea901415075ca4_15.png)

```python
from langchain.prompts import PromptTemplate

# 获取格式指令字符串，它会被自动插入到提示中
format_instructions = output_parser.get_format_instructions()
# 创建提示模板
prompt_template = PromptTemplate(
    template="请尽可能准确地回答问题。\n{format_instructions}\n问题：{question}",
    input_variables=["question"],
    partial_variables={"format_instructions": format_instructions}
)
```

现在，让我们剖析一下这个完整的提示。当我们提出一个问题时，LangChain 会将格式指令填充到提示中。这些指令明确要求输出必须是 JSON 格式，并包含 `answer` 和 `source` 字段。

![](img/45c4163eb91d4d3d2bea901415075ca4_17.png)

---

有了提示模板，我们就可以将其与大模型链接起来，形成一个处理链。这个链将处理输入、调用模型并解析输出。

以下是构建和运行处理链的代码：


![](img/45c4163eb91d4d3d2bea901415075ca4_19.png)

![](img/45c4163eb91d4d3d2bea901415075ca4_20.png)


![](img/45c4163eb91d4d3d2bea901415075ca4_21.png)

```python
from langchain.chat_models import ChatOpenAI
from langchain.chains import LLMChain
# 初始化大模型（这里使用 OpenAI 的 GPT-4）
llm = ChatOpenAI(model_name="gpt-4", temperature=0)
# 构建处理链
chain = LLMChain(llm=llm, prompt=prompt_template, output_parser=output_parser)

# 运行链并提问
question = "Python 编程语言是什么时候推出的？"
result = chain.run(question)
parsed_result = output_parser.parse(result)

print(f"答案：{parsed_result['answer']}")
print(f"来源：{parsed_result['source']}")
```

运行上述代码，我们将得到结构化的输出，例如：
- **答案**：Python 编程语言于 1991 年推出。
- **来源**：维基百科关于 Python 编程语言的条目。

![](img/45c4163eb91d4d3d2bea901415075ca4_23.png)

---

除了简单的问答，我们还可以定义更复杂的模式。例如，我们可以要求模型检测输入文本的语言，并将其翻译成多种语言。

以下是实现多语言翻译的示例：

![](img/45c4163eb91d4d3d2bea901415075ca4_25.png)

首先，定义包含检测语言和多个翻译字段的响应模式：

```python
translation_schemas = [
    ResponseSchema(name="detected_language", description="检测到的输入语言"),
    ResponseSchema(name="spanish", description="西班牙语翻译"),
    ResponseSchema(name="french", description="法语翻译"),
    ResponseSchema(name="chinese", description="中文翻译")
]
translation_parser = StructuredOutputParser.from_response_schemas(translation_schemas)
```

然后，创建相应的提示模板和处理链：

![](img/45c4163eb91d4d3d2bea901415075ca4_27.png)


![](img/45c4163eb91d4d3d2bea901415075ca4_29.png)


![](img/45c4163eb91d4d3d2bea901415075ca4_31.png)

```python
translation_format_instructions = translation_parser.get_format_instructions()
translation_prompt = PromptTemplate(
    template="请检测以下文本的语言，并将其翻译成指定的语言。\n{format_instructions}\n文本：{text}",
    input_variables=["text"],
    partial_variables={"format_instructions": translation_format_instructions}
)
translation_chain = LLMChain(llm=llm, prompt=translation_prompt, output_parser=translation_parser)
```

现在，我们可以用不同语言提问：

![](img/45c4163eb91d4d3d2bea901415075ca4_33.png)

```python
# 示例 1：英语输入
result1 = translation_chain.run("When was the Python programming language introduced?")
print(translation_parser.parse(result1))

# 示例 2：斯瓦希里语输入
result2 = translation_chain.run("Lugha ya programu ya Python ilianzishwa lini?")
print(translation_parser.parse(result2))
```

![](img/45c4163eb91d4d3d2bea901415075ca4_35.png)

模型将检测输入语言，并提供西班牙语、法语和中文的翻译。

---

本节课中我们一起学习了如何使用 LangChain 的结构化输出解析器。我们掌握了如何定义响应模式来指定期望的输出格式，如何构建提示模板来指导大模型，以及如何创建处理链来获取并解析结构化的 JSON 结果。这套工具能有效地将大模型返回的非结构化文本转化为程序易于处理的数据，为构建更复杂的 AI 应用奠定了基础。