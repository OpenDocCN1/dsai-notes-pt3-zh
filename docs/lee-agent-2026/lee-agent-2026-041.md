# 41：基于LangChain的Claude-3 XML Agent教程 🧠

![](img/eccecdbf3da5a6cd999968de627a3a6a_1.png)

在本节课中，我们将学习如何利用Claude-3模型的特性，构建一个基于LangChain的XML Agent。我们将从Agent的基本概念讲起，逐步深入到XML标签的应用、工具构建以及完整的Agent执行流程。

![](img/eccecdbf3da5a6cd999968de627a3a6a_3.png)

## 概述：什么是Agent与XML Agent？

在LangChain极简入门课程的第八课中，我们介绍了代理（Agent）的基本概念。Agent的核心理念是利用大语言模型来决定任务执行的顺序或决策该执行哪一个任务。

![](img/eccecdbf3da5a6cd999968de627a3a6a_5.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_7.png)

本节中，我们将在LangChain Agent的基础上，针对Claude-3模型的特性进行改进，构建一个XML Agent，以最大化发挥Claude模型在处理结构化提示词方面的优势。

![](img/eccecdbf3da5a6cd999968de627a3a6a_9.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_11.png)

## 为什么使用XML Agent？

要理解XML Agent，我们需要先回到Anthropic提供的开发者手册。在“提示词工程”章节中，有一个部分专门介绍了“使用XML文本”。

XML标签是Claude大模型世界中用于结构化提示词、指导模型如何响应的一种重要且强大的工具。Claude模型在训练过程中大量接触了这种格式的提示词，因此它能很好地理解包含XML标签的上下文，并生成更准确的输出。

![](img/eccecdbf3da5a6cd999968de627a3a6a_13.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_15.png)

以下是使用XML文本（XML-tags）的三大理由：
1.  **更高的精确度**：帮助模型更准确地理解指令和上下文边界。
2.  **更清晰的数据结构**：使文本、语言和数据的结构更加明确。
3.  **更容易的后处理**：输出的结构化格式便于程序进行后续解析和处理。

![](img/eccecdbf3da5a6cd999968de627a3a6a_17.png)

基于这些优势，在Claude模型的Agent实现中，推荐使用XML标签，这也是我们构建“XML Agent”的原因。

![](img/eccecdbf3da5a6cd999968de627a3a6a_19.png)

## 环境与工具准备 🛠️

在开始构建之前，我们需要准备以下工具和组件：
*   **模型**：Claude-3系列（Opus或Sonnet，前者功能更强，后者速度更快）。
*   **框架**：LangChain。
*   **向量存储**：FAISS（也可选择Chroma、Pinecone等方案）。
*   **文档处理**：PyPDF（用于演示的PDF文档解析）。

![](img/eccecdbf3da5a6cd999968de627a3a6a_21.png)

以下是具体的代码实现步骤。

### 第一步：安装依赖包

![](img/eccecdbf3da5a6cd999968de627a3a6a_23.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_25.png)

我们首先需要安装必要的Python库。

![](img/eccecdbf3da5a6cd999968de627a3a6a_27.png)

```python
!pip install langchain langchainhub langchain-anthropic langchain-openai pypdf
```

![](img/eccecdbf3da5a6cd999968de627a3a6a_29.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_31.png)

*   `langchain-anthropic`：提供了与Anthropic（Claude-3）模型集成的接口。
*   `langchain-openai`：这里用于使用OpenAI的嵌入模型（Embedding Model），你也可以替换成其他方案。
*   `pypdf`：用于加载和解析PDF文档。

![](img/eccecdbf3da5a6cd999968de627a3a6a_33.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_35.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_37.png)

### 第二步：加载文档并创建向量存储

![](img/eccecdbf3da5a6cd999968de627a3a6a_39.png)

我们将使用一份2024年发布的、关于ESOP Agent的学术论文PDF作为示例知识库。选择较新的论文是为了确保其内容不在大模型的通用训练数据中，从而验证Agent从知识库中检索信息的能力。

![](img/eccecdbf3da5a6cd999968de627a3a6a_41.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_43.png)

```python
from langchain_community.document_loaders import PyPDFLoader
from langchain_openai import OpenAIEmbeddings
from langchain_community.vectorstores import FAISS
from langchain.text_splitter import RecursiveCharacterTextSplitter

![](img/eccecdbf3da5a6cd999968de627a3a6a_45.png)

# 1. 加载并拆分PDF文档
loader = PyPDFLoader(“esop_agent.pdf”)
documents = loader.load_and_split()

![](img/eccecdbf3da5a6cd999968de627a3a6a_47.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_49.png)

# 2. 创建向量存储
embeddings = OpenAIEmbeddings()
vectorstore = FAISS.from_documents(documents, embeddings)
```
这段代码完成了文档的加载、文本拆分，并最终创建了一个向量存储索引，后续将用于相似性检索。

### 第三步：创建Agent工具

![](img/eccecdbf3da5a6cd999968de627a3a6a_51.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_53.png)

Agent需要通过工具（Tools）来执行具体任务。我们创建一个简单的搜索工具，用于在向量库中查找与问题相关的文档。

![](img/eccecdbf3da5a6cd999968de627a3a6a_55.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_57.png)

```python
from langchain.tools import tool

![](img/eccecdbf3da5a6cd999968de627a3a6a_59.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_61.png)

@tool
def esop_agent_search(query: str) -> str:
    """在ESOP Agent知识库中搜索相关信息。"""
    docs = vectorstore.similarity_search(query, k=3)
    content = “\n\n”.join([doc.page_content for doc in docs])
    return content

![](img/eccecdbf3da5a6cd999968de627a3a6a_63.png)

# 定义工具集
tools = [esop_agent_search]
```
`esop_agent_search` 工具接收一个查询字符串，在向量库中搜索最相关的3个文档片段，并将它们的内容用双换行符连接起来，作为检索到的上下文信息返回。

![](img/eccecdbf3da5a6cd999968de627a3a6a_65.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_67.png)

## 构建XML Agent 🤖

![](img/eccecdbf3da5a6cd999968de627a3a6a_69.png)

上一节我们准备好了工具，本节中我们来看看如何构建一个利用XML标签的Agent。

![](img/eccecdbf3da5a6cd999968de627a3a6a_71.png)

### 核心：XML提示词模板

构建Agent的关键是提示词模板。我们使用LangChain Hub中一个专为Claude模型设计的XML对话模板。

![](img/eccecdbf3da5a6cd999968de627a3a6a_73.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_75.png)

```python
from langchain import hub
from langchain.agents import XMLAgent

![](img/eccecdbf3da5a6cd999968de627a3a6a_77.png)

# 从LangChain Hub拉取XML Agent对话提示词模板
prompt = hub.pull(“hwchase17/xml-agent-convo”)
```
这个模板的核心特点是使用XML标签来结构化提示词。例如，它用 `<tool>` 标签描述工具信息，并规定模型的最终回答必须包裹在 `<final_answer>` 标签中。这与传统使用JSON格式示例的Agent提示词有所不同，更能契合Claude模型的训练模式。

![](img/eccecdbf3da5a6cd999968de627a3a6a_79.png)

### 初始化模型与辅助函数

![](img/eccecdbf3da5a6cd999968de627a3a6a_81.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_83.png)

接下来，我们初始化Claude模型，并定义一些辅助函数来处理Agent执行过程中的中间步骤和聊天历史。

![](img/eccecdbf3da5a6cd999968de627a3a6a_85.png)

```python
from langchain_anthropic import ChatAnthropic

![](img/eccecdbf3da5a6cd999968de627a3a6a_87.png)

# 初始化Claude模型（这里使用Sonnet，平衡速度与性能）
llm = ChatAnthropic(model=“claude-3-sonnet-20240229”)

![](img/eccecdbf3da5a6cd999968de627a3a6a_89.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_91.png)

# 辅助函数：将Agent的中间步骤转换为XML格式
def convert_intermediate_steps(intermediate_steps):
    log = “”
    for action, observation in intermediate_steps:
        log += f”<tool>{action.tool}</tool><tool_input>{action.tool_input}</tool_input><observation>{observation}</observation>”
    return log

![](img/eccecdbf3da5a6cd999968de627a3a6a_93.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_95.png)

# 辅助函数：将聊天记忆转换为字符串
def memory_to_string(memory):
    return “\n”.join([f”{‘Human’ if isinstance(msg, HumanMessage) else ‘AI’}: {msg.content}” for msg in memory])
```

### 创建Agent执行器

![](img/eccecdbf3da5a6cd999968de627a3a6a_97.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_99.png)

现在，我们将所有组件组合起来，创建Agent执行器。

![](img/eccecdbf3da5a6cd999968de627a3a6a_101.png)

```python
from langchain.agents import AgentExecutor, create_xml_agent
from langchain.memory import ConversationBufferWindowMemory
from langchain.schema import HumanMessage, AIMessage

![](img/eccecdbf3da5a6cd999968de627a3a6a_103.png)

# 1. 创建Agent
agent = create_xml_agent(llm, tools, prompt)

![](img/eccecdbf3da5a6cd999968de627a3a6a_105.png)

# 2. 创建记忆组件（只保留最近5轮对话）
memory = ConversationBufferWindowMemory(k=5, return_messages=True)

# 3. 创建Agent执行器
agent_executor = AgentExecutor(
    agent=agent,
    tools=tools,
    memory=memory,
    verbose=True, # 打印详细执行过程
    return_intermediate_steps=True, # 返回中间步骤，便于调试
    handle_parsing_errors=True
)

![](img/eccecdbf3da5a6cd999968de627a3a6a_107.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_109.png)

# 4. 封装聊天函数
def chat(question: str):
    # 将记忆转换为字符串，以便嵌入提示词
    chat_history_str = memory_to_string(memory.load_memory_variables({})[‘history’])
    # 调用Agent
    result = agent_executor.invoke({“input”: question, “chat_history”: chat_history_str})
    # 更新记忆
    memory.save_context({“input”: question}, {“output”: result[“output”]})
    return result
```
`agent_executor` 是核心执行引擎，它负责接收用户输入，协调大模型决策、工具调用，并管理记忆。我们将 `verbose` 设为 `True`，以便在控制台观察详细的推理过程。

![](img/eccecdbf3da5a6cd999968de627a3a6a_111.png)

## 运行与测试 🚀

![](img/eccecdbf3da5a6cd999968de627a3a6a_113.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_114.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_116.png)

现在，我们的XML Agent已经构建完成。让我们提出一个问题来测试它：“谁开发了ESOP Agent？”

![](img/eccecdbf3da5a6cd999968de627a3a6a_118.png)

执行 `chat(“谁开发了ESOP Agent？”)` 后，你将在控制台看到类似以下的详细输出：

![](img/eccecdbf3da5a6cd999968de627a3a6a_120.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_122.png)

```
> 进入新的Agent执行链...
思考：我需要查询知识库来找到ESOP Agent的开发者信息。
<tool>esop_agent_search</tool>
<tool_input>谁开发了ESOP Agent</tool_input>
<observation>（此处是从向量库检索到的相关文档文本内容）...</observation>
思考：根据检索到的信息，我可以回答这个问题了。
<final_answer>ESOP Agent是由阿里巴巴集团的达摩学院的研究员提出的一个故事到视频生成系统。</final_answer>
> 链结束。
```
输出显示，Agent首先决定调用 `esop_agent_search` 工具，并将问题作为查询输入。工具返回了从PDF中检索到的相关文本。接着，Agent根据这些上下文信息，将最终答案包裹在 `<final_answer>` 标签中输出。

![](img/eccecdbf3da5a6cd999968de627a3a6a_124.png)

通过检查返回结果中的 `intermediate_steps`，我们可以清晰地看到工具调用的具体输入和观察结果，这对于调试Agent的行为非常有帮助。

![](img/eccecdbf3da5a6cd999968de627a3a6a_126.png)

## 总结与扩展

![](img/eccecdbf3da5a6cd999968de627a3a6a_128.png)

本节课中，我们一起学习了如何构建一个基于LangChain和Claude-3的XML Agent。

![](img/eccecdbf3da5a6cd999968de627a3a6a_130.png)

我们首先了解了**XML Agent**的概念，它利用Claude模型对XML标签的良好理解能力，通过结构化的提示词获得更精确的响应。接着，我们逐步实现了**文档加载、向量检索、工具创建**，并利用**LangChain Hub的XML模板**构建了Agent。最后，我们通过测试验证了Agent能够成功利用工具从知识库中获取信息并回答问题。

需要指出的是，虽然XML标签是Anthropic推荐的高效方式，但Claude-3模型同样支持JSON、HTML、Markdown等多种结构化格式。在实际应用中，你可以根据具体场景测试不同格式，选择表现最佳的一种。

![](img/eccecdbf3da5a6cd999968de627a3a6a_132.png)

希望本教程能帮助你入门Claude-3 XML Agent的开发。如果你在测试中有任何发现或疑问，欢迎交流讨论。