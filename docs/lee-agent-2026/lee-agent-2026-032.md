# 32：LangChain 模板创建教程 🧠

![](img/ff9ffbc787426e2c98293e8087a26062_1.png)

在本节课中，我们将学习如何创建自己的 LangChain 模板。LangChain 的模板机制为开发者提供了快速构建产品级大模型应用的解决方案。通过本教程，你将掌握从零开始创建一个具备特定功能（如基于 PDF 的问答）的模板，并了解如何运行和测试它。

## 📁 模板项目结构与创建

![](img/ff9ffbc787426e2c98293e8087a26062_3.png)

![](img/ff9ffbc787426e2c98293e8087a26062_5.png)

![](img/ff9ffbc787426e2c98293e8087a26062_7.png)

在上一节中，我们介绍了如何利用现有的 LangChain 模板构建应用。本节中，我们来看看如何从零开始创建自己的模板。

创建模板需要使用 `langchain` CLI 工具。以下是创建新模板的步骤：

![](img/ff9ffbc787426e2c98293e8087a26062_9.png)

![](img/ff9ffbc787426e2c98293e8087a26062_11.png)

1.  使用 `langchain template new` 命令创建新模板。
2.  该命令会自动生成模板所需的文件夹和核心文件。

![](img/ff9ffbc787426e2c98293e8087a26062_13.png)

具体命令如下：
```bash
langchain template new <your-template-name>
```
执行此命令后，会生成一个以模板名命名的目录，其中包含核心代码文件 `chain.py` 和项目配置文件 `pyproject.toml`。

![](img/ff9ffbc787426e2c98293e8087a26062_15.png)

![](img/ff9ffbc787426e2c98293e8087a26062_17.png)

## 🔧 核心文件解析与开发

![](img/ff9ffbc787426e2c98293e8087a26062_19.png)

现在我们已经有了模板的基本骨架，接下来深入看看核心文件并开始功能开发。

![](img/ff9ffbc787426e2c98293e8087a26062_21.png)

![](img/ff9ffbc787426e2c98293e8087a26062_23.png)

`chain.py` 文件是模板的业务逻辑核心。初始生成的代码通常包含一个简单的提示词模板和链的构建。`pyproject.toml` 文件则定义了项目的依赖和 LangServe 的配置。

![](img/ff9ffbc787426e2c98293e8087a26062_25.png)

以下是初始 `chain.py` 可能包含的核心代码结构：
```python
from langchain.prompts import PromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.runnable import RunnableSequence

![](img/ff9ffbc787426e2c98293e8087a26062_27.png)

![](img/ff9ffbc787426e2c98293e8087a26062_29.png)

prompt = PromptTemplate.from_template("You are a helpful assistant. {text}")
model = ChatOpenAI()
chain = prompt | model
```
我们可以在此基础上添加 `main` 函数，以便通过命令行测试模板的基本功能。

![](img/ff9ffbc787426e2c98293e8087a26062_31.png)

![](img/ff9ffbc787426e2c98293e8087a26062_33.png)

## 🛠️ 实现自定义功能：基于 PDF 的问答

![](img/ff9ffbc787426e2c98293e8087a26062_35.png)

![](img/ff9ffbc787426e2c98293e8087a26062_36.png)

上一节我们解析了基础模板。本节中，我们将动手改造它，实现一个从 PDF 文件中检索并回答问题的功能。

![](img/ff9ffbc787426e2c98293e8087a26062_38.png)

![](img/ff9ffbc787426e2c98293e8087a26062_40.png)

我们需要改写 `chain.py` 的业务逻辑。目标是：通过环境变量指定 PDF 文件路径，使用 LangChain 的文档加载器、文本分割器、向量存储和 `MultiVectorRetriever` 来构建一个检索增强生成（RAG）链。

![](img/ff9ffbc787426e2c98293e8087a26062_42.png)

![](img/ff9ffbc787426e2c98293e8087a26062_44.png)

以下是实现该功能的核心代码逻辑：
```python
import os
from langchain.document_loaders import PyPDFLoader
from langchain.text_splitter import RecursiveCharacterTextSplitter
from langchain.vectorstores import Chroma
from langchain.embeddings import OpenAIEmbeddings
from langchain.retrievers.multi_vector import MultiVectorRetriever
from langchain.chat_models import ChatOpenAI
from langchain.prompts import ChatPromptTemplate
from langchain.schema.output_parser import StrOutputParser
from langchain.schema.runnable import RunnablePassthrough

![](img/ff9ffbc787426e2c98293e8087a26062_46.png)

# 1. 加载并处理PDF
pdf_path = os.getenv("PDF_PATH")
loader = PyPDFLoader(pdf_path)
documents = loader.load()
text_splitter = RecursiveCharacterTextSplitter(chunk_size=1000, chunk_overlap=200)
splits = text_splitter.split_documents(documents)

![](img/ff9ffbc787426e2c98293e8087a26062_48.png)

![](img/ff9ffbc787426e2c98293e8087a26062_50.png)

# 2. 创建向量存储和检索器
vectorstore = Chroma.from_documents(documents=splits, embedding=OpenAIEmbeddings())
retriever = MultiVectorRetriever(vectorstore=vectorstore)

![](img/ff9ffbc787426e2c98293e8087a26062_52.png)

![](img/ff9ffbc787426e2c98293e8087a26062_54.png)

# 3. 构建提示词和链
template = """基于以下上下文信息回答问题：
{context}
问题：{question}
"""
prompt = ChatPromptTemplate.from_template(template)
model = ChatOpenAI()

![](img/ff9ffbc787426e2c98293e8087a26062_56.png)

![](img/ff9ffbc787426e2c98293e8087a26062_58.png)

chain = (
    {"context": retriever, "question": RunnablePassthrough()}
    | prompt
    | model
    | StrOutputParser()
)
```
这段代码完成了从文档加载到检索问答链的构建。链的输入是一个 `question` 字段，输出是模型生成的回答。

![](img/ff9ffbc787426e2c98293e8087a26062_60.png)

## 🚀 测试与运行模板

![](img/ff9ffbc787426e2c98293e8087a26062_62.png)

功能开发完成后，我们需要验证模板是否能正常工作。本节将介绍如何通过命令行和 LangServe 的 Playground 来测试模板。

![](img/ff9ffbc787426e2c98293e8087a26062_64.png)

首先，确保已安装所有必要的依赖包（如 `pypdf`, `chromadb`, `tiktoken`）。然后，通过设置环境变量并运行 `main` 函数来测试核心逻辑。

![](img/ff9ffbc787426e2c98293e8087a26062_66.png)

在命令行中，可以按以下步骤测试：
```bash
# 设置环境变量
export PDF_PATH="/path/to/your/document.pdf"
export OPENAI_API_KEY="your-api-key"

# 运行模板的 main 函数进行测试
python chain.py
```
如果一切正常，程序会加载 PDF 并输出对预设问题的回答。

![](img/ff9ffbc787426e2c98293e8087a26062_68.png)

![](img/ff9ffbc787426e2c98293e8087a26062_70.png)

## 🌐 使用 LangServe 部署与交互

![](img/ff9ffbc787426e2c98293e8087a26062_72.png)

![](img/ff9ffbc787426e2c98293e8087a26062_74.png)

本地测试通过后，我们可以使用 LangServe 将模板部署为一个服务，并通过 Web Playground 进行交互。

![](img/ff9ffbc787426e2c98293e8087a26062_76.png)

![](img/ff9ffbc787426e2c98293e8087a26062_78.png)

使用 `langchain serve` 命令可以启动一个本地服务器。启动后，可以通过浏览器访问 Playground 界面（通常是 `http://localhost:8000`）来与你的模板应用进行交互。

![](img/ff9ffbc787426e2c98293e8087a26062_80.png)

![](img/ff9ffbc787426e2c98293e8087a26062_82.png)

在 Playground 中，你可以输入问题并实时看到链的执行步骤和最终输出。通过浏览器的开发者工具（Network 标签页），你可以观察到前端与后端 API (`/stream_log` 端点) 的交互是使用 Server-Sent Events (SSE) 实现的流式响应。

![](img/ff9ffbc787426e2c98293e8087a26062_84.png)

## 📝 总结

![](img/ff9ffbc787426e2c98293e8087a26062_86.png)

![](img/ff9ffbc787426e2c98293e8087a26062_88.png)

本节课中我们一起学习了如何创建自定义的 LangChain 模板。我们从使用 CLI 工具生成模板骨架开始，逐步解析了核心文件，并动手实现了一个基于 PDF 文件的问答功能。最后，我们学习了如何测试模板逻辑以及通过 LangServe 部署和交互。

![](img/ff9ffbc787426e2c98293e8087a26062_90.png)

这个示例虽然简单，但它清晰地展示了模板创建的完整流程。你可以通过增加参数、环境变量或更复杂的业务逻辑，让模板变得更加强大和可定制。希望你能利用这个基础，创建出更多有趣、实用的模板，从而更高效地构建和复用大模型应用组件。