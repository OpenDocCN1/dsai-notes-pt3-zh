# 35：网络搜索检索器 (Web Search Retriever) 🔍

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_1.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_3.png)

在本节课中，我们将学习 LangChain 框架中的网络搜索检索器（Web Search Retriever）。这种检索器能够利用搜索引擎（如谷歌）从互联网上实时获取信息，并将其整合到智能体的知识库中，以回答用户的问题。

## 概述与工作流程

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_5.png)

上一节我们介绍了基础的检索器，本节中我们来看看如何利用网络搜索来扩展数据来源。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_7.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_9.png)

网络搜索检索器的核心目的是通过搜索引擎获取网络上的信息、资源和数据。其基本工作流程如下图所示：



![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_11.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_13.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_3.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_15.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_17.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_19.png)

以下是该流程的步骤分解：
1.  **用户提问**：用户提出一个问题。
2.  **生成搜索查询**：检索器基于用户问题，利用大语言模型（LLM）生成若干个（例如三个）用于谷歌搜索的查询。
3.  **执行网络搜索**：每个生成的查询被提交给谷歌搜索引擎。
4.  **获取与处理结果**：搜索引擎返回包含原始URL的搜索结果。这些URL被交给网络爬虫来抓取网页内容。
5.  **向量化存储与检索**：抓取到的文本数据被存入向量数据库，以便后续进行相似性查询。
6.  **生成最终响应**：查询得到的相关文档被提交给大语言模型，由模型综合这些信息构建出合理的回答，最终返回给用户。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_21.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_23.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_25.png)

## 基础使用示例

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_27.png)

了解了原理后，我们通过一个简单的 Python 示例来看看如何具体使用它。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_29.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_31.png)

在这个示例中，我们使用谷歌搜索引擎。LangChain 框架对谷歌搜索提供了 API 封装，即 `GoogleSearchAPIWrapper`。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_33.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_35.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_37.png)

使用它需要两个关键参数：
*   `google_cse_id`： 谷歌可编程搜索引擎 ID。
*   `google_api_key`： 谷歌 API 密钥。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_39.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_41.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_43.png)

你需要到谷歌云平台申请这两个凭证。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_45.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_47.png)

以下是核心代码步骤：

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_49.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_51.png)

首先，创建必要的组件：向量存储、大语言模型和搜索包装器。
```python
# 示例使用Chroma作为向量存储，OpenAI的模型作为LLM
vectorstore = Chroma(...)
llm = ChatOpenAI(...)
search = GoogleSearchAPIWrapper(google_cse_id=YOUR_CSE_ID, google_api_key=YOUR_API_KEY)
```
可以简单测试搜索包装器是否工作：
```python
search.run("查询内容")
```
接着，构建网络搜索检索器：
```python
web_research_retriever = WebResearchRetriever.from_llm(
    vectorstore=vectorstore,
    llm=llm,
    search=search
)
```
然后，构建一个问答链。这里使用 `RetrievalQAWithSourcesChain`，它会基于搜索结果的源URL来获取信息并回答问题。
```python
qa_chain = RetrievalQAWithSourcesChain.from_chain_type(llm, retriever=web_research_retriever)
result = qa_chain({"question": "哪个国家赢得了2002年世界杯？"})
print(result['answer'])
```
**注意**：此过程需要安装 `html2text` 包，用于将HTML内容转换为纯文本。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_53.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_55.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_57.png)

执行上述链时，你会看到日志显示LLM生成了多个搜索查询（例如：“2002年世界杯冠军是哪个国家？”，“谁是2002年世界杯冠军？”），然后进行搜索，最终整合信息给出答案（例如：“巴西是2002年世界杯冠军”，并附上维基百科的源链接）。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_59.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_61.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_63.png)

你也可以直接调用检索器获取相关文档：
```python
docs = web_research_retriever.get_relevant_documents("你的问题")
```

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_65.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_67.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_69.png)

## 进阶：定制搜索查询生成

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_71.png)

在基础示例中，我们直接将LLM提供给检索器，由模型自由发挥生成搜索查询。本节我们来看看如何通过提示词工程来引导模型生成更符合我们要求的查询。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_73.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_75.png)

我们可以构建一条LLM链（LLMChain），并提供一个特定的提示词模板。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_77.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_79.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_81.png)

以下是一个提示词模板示例，它要求模型生成5个与原始问题高度相似的谷歌搜索查询：
```python
prompt_template = """你是一个助手，负责将问题转化为高效的网络搜索查询。
基于以下用户问题，生成5个相关的谷歌搜索查询。
每个查询都应非常接近原始问题，并以问号结尾。
将结果以有序列表的形式返回。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_83.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_85.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_87.png)

问题：{question}
"""
```
定义输出解析器来解析这5个问题：
```python
class LineListOutputParser(BaseOutputParser):
    ... # 解析逻辑，将文本按行拆分为列表
```
使用提示词模板、LLM和输出解析器构建LLM链：
```python
llm_chain = LLMChain(llm=llm, prompt=PromptTemplate.from_template(prompt_template), output_parser=LineListOutputParser())
```
最后，使用这个定制化的LLM链来构建检索器：
```python
web_research_retriever = WebResearchRetriever.from_llm(
    vectorstore=vectorstore,
    llm_chain=llm_chain, # 使用定制的链替代原始的llm
    search=search
)
```
当我们提问“回收塑料的推荐方式是什么？”时，定制的LLM链会先生成5个相关的搜索查询（例如：“最好的塑料回收方法有哪些？”，“如何有效回收塑料？”等）。检索器基于这些查询进行搜索，获取并处理网页内容，最终为我们提供一系列来自网络的可信文档，作为生成答案的基础。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_89.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_91.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_93.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_95.png)

## 总结

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_97.png)

本节课中我们一起学习了 LangChain 中的网络搜索检索器（Web Search Retriever）。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_99.png)

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_101.png)

我们首先了解了它的核心工作流程：**用户提问 -> LLM生成搜索查询 -> 执行网络搜索 -> 抓取并处理网页内容 -> 向量化检索 -> LLM合成答案**。

接着，我们通过代码示例实践了其基础使用方法，并学习了如何通过定制提示词和LLM链来更精细地控制搜索查询的生成过程。

![](img/b7d0ed02ce37fb36494f54cb7b9c5c82_103.png)

这种检索器能够极大地扩展智能体的实时知识来源，利用丰富的网络信息来回答问题。在过去的几期课程中，我们介绍了LangChain支持的不同类型检索器，它们各有特点。在实际应用中，你应该根据具体的业务场景和数据特点，来选择最合适的检索器。