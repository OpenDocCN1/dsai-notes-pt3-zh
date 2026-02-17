# 本地RAG：1：从零构建本地检索增强生成（RAG）管道

## 概述

![](img/9bf8e9b233650e311443169d7109ebae_1.png)

![](img/9bf8e9b233650e311443169d7109ebae_3.png)

![](img/9bf8e9b233650e311443169d7109ebae_5.png)

![](img/9bf8e9b233650e311443169d7109ebae_7.png)

![](img/9bf8e9b233650e311443169d7109ebae_9.png)

![](img/9bf8e9b233650e311443169d7109ebae_10.png)

![](img/9bf8e9b233650e311443169d7109ebae_12.png)

![](img/9bf8e9b233650e311443169d7109ebae_14.png)

在本课程中，我们将从零开始，构建一个完整的本地检索增强生成（RAG）管道。我们将从导入一个PDF文档开始，逐步完成文本预处理、嵌入创建、语义搜索，最终使用本地运行的大型语言模型（LLM）生成基于检索内容的答案。整个过程将在您自己的计算机上运行，无需依赖外部API。

---

## 什么是RAG？

RAG代表**检索增强生成**。其核心目标是：**获取信息，并将其传递给LLM，以便LLM能够基于该信息生成输出**。

让我们分解这个流程：

1.  **检索**：即搜索。根据查询找到相关信息。例如，在本项目中，我们将构建一个“营养聊天”应用，与一本1200页的营养学教科书进行对话。查询可能是：“什么是宏量营养素？它们有什么作用？”。检索步骤会从教科书中找到与“宏量营养素”相关的文本段落。
2.  **增强**：将检索到的相关信息**增强**到我们的输入提示中。通常，输入给LLM的文本称为“提示”。我们将用检索到的相关信息来增强这个提示。
3.  **生成**：将前两步的结果（增强后的提示）传递给LLM，由其生成输出。

简而言之：**检索 -> 增强 -> 生成**。

## 为什么需要RAG？

![](img/9bf8e9b233650e311443169d7109ebae_16.png)

![](img/9bf8e9b233650e311443169d7109ebae_18.png)

![](img/9bf8e9b233650e311443169d7109ebae_20.png)

![](img/9bf8e9b233650e311443169d7109ebae_22.png)

![](img/9bf8e9b233650e311443169d7109ebae_23.png)

RAG的主要目标是**提高LLM生成输出的质量**，尤其是在以下方面：

![](img/9bf8e9b233650e311443169d7109ebae_25.png)

1.  **减少幻觉**：LLM非常擅长生成看起来通顺的文本，但这些文本不一定符合事实。RAG通过为LLM提供事实性信息（如您的公司文档、教科书内容），使其生成基于这些真实内容的答案，从而减少“胡编乱造”。
2.  **处理定制数据**：许多基础LLM是在互联网规模的通用数据上训练的，其回答可能比较泛泛。RAG允许您将LLM与您自己的特定文档（如客户支持文档、内部资料、电子邮件链）结合起来，从而获得针对您特定领域和问题的具体答案。

![](img/9bf8e9b233650e311443169d7109ebae_27.png)

![](img/9bf8e9b233650e311443169d7109ebae_29.png)

## RAG的应用场景

![](img/9bf8e9b233650e311443169d7109ebae_30.png)

![](img/9bf8e9b233650e311443169d7109ebae_32.png)

![](img/9bf8e9b233650e311443169d7109ebae_34.png)

![](img/9bf8e9b233650e311443169d7109ebae_36.png)

*   **客户支持问答聊天**：将现有的客户支持文档作为资源库。当客户提问时，系统检索相关文档片段，并由LLM将这些片段整合成一个清晰的答案。
*   **电子邮件链分析**：例如，大型保险公司有大量客户索赔邮件。可以使用RAG管道从这些邮件链中查找相关信息，并使用LLM将其处理成结构化数据（如JSON或电子表格）。
*   **公司内部文档聊天**：类似于客户支持，但用于公司内部的知识库或文档集。
*   **教科书问答**：这正是我们将在本教程中构建的。学生可以与一本厚重的教科书进行对话，快速获取相关知识点。

## 为什么选择本地运行？

1.  **隐私**：如果您的公司有敏感或私有信息，您可能不希望将其发送到外部API（如OpenAI、Anthropic）。在本地硬件上运行LLM可以保护数据隐私。
2.  **速度**：使用API需要通过网络传输数据，会产生延迟。本地运行意味着数据在您桌面下的机器上直接处理，速度更快。
3.  **成本**：虽然购买硬件有前期成本，但长期来看，无需持续支付API调用费用。
4.  **无供应商锁定**：如果您依赖ChatGPT等外部服务来运营业务，一旦服务提供商出现问题，您的业务可能会受到影响。拥有自己的硬件和软件则不受此限制。

![](img/9bf8e9b233650e311443169d7109ebae_38.png)

![](img/9bf8e9b233650e311443169d7109ebae_40.png)

## 我们将要构建什么

![](img/9bf8e9b233650e311443169d7109ebae_42.png)

![](img/9bf8e9b233650e311443169d7109ebae_43.png)

我们将构建一个名为 **NutriChat** 的应用，用于与一本营养学教科书进行对话。

![](img/9bf8e9b233650e311443169d7109ebae_45.png)

![](img/9bf8e9b233650e311443169d7109ebae_46.png)

整个流程分为两个主要部分：

![](img/9bf8e9b233650e311443169d7109ebae_48.png)

![](img/9bf8e9b233650e311443169d7109ebae_50.png)

![](img/9bf8e9b233650e311443169d7109ebae_52.png)

### 第一部分：文档预处理与嵌入创建
1.  导入PDF文档。
2.  将文本处理成适合嵌入模型的小块（例如，每组10个句子）。
3.  使用嵌入模型将这些文本块转换为数值表示（嵌入向量）。
4.  将嵌入向量保存到文件以备后用。

![](img/9bf8e9b233650e311443169d7109ebae_54.png)

![](img/9bf8e9b233650e311443169d7109ebae_56.png)

![](img/9bf8e9b233650e311443169d7109ebae_58.png)

### 第二部分：搜索与回答
1.  用户提出查询（例如，“什么是宏量营养素？”）。
2.  使用**相同的嵌入模型**将查询转换为嵌入向量。
3.  在存储的文档嵌入向量中执行**向量搜索**（语义搜索），找到与查询最相似的文本块。
4.  **增强**：将查询与检索到的相关文本段落组合，形成一个增强的提示。
5.  **生成**：将增强后的提示传递给本地LLM，生成最终答案，并附带答案来源的引用。

![](img/9bf8e9b233650e311443169d7109ebae_60.png)

---

![](img/9bf8e9b233650e311443169d7109ebae_62.png)

## 第一部分：文档预处理与嵌入创建

上一节我们介绍了RAG的基本概念和项目概览，本节我们将开始动手实现第一部分：文档的预处理和嵌入向量的创建。

### 步骤1：导入PDF文档

![](img/9bf8e9b233650e311443169d7109ebae_64.png)

![](img/9bf8e9b233650e311443169d7109ebae_66.png)

首先，我们需要获取并加载PDF文档。我们将使用`requests`库下载PDF（如果需要），并使用`PyMuPDF`（`fitz`）库来读取PDF内容。

以下是导入PDF文档的代码：

```python
import os
import requests
import fitz  # PyMuPDF
from tqdm import tqdm

# 定义PDF路径
pdf_path = "human_nutrition_text.pdf"

# 如果PDF不存在，则下载
if not os.path.exists(pdf_path):
    print(f"文件不存在，正在下载...")
    url = "https://pressbooks.oer.hawaii.edu/humannutrition2/open/download?type=pdf"
    response = requests.get(url)
    if response.status_code == 200:
        with open(pdf_path, 'wb') as file:
            file.write(response.content)
        print(f"文件已下载并保存为: {pdf_path}")
    else:
        print(f"下载失败，状态码: {response.status_code}")
else:
    print(f"文件已存在: {pdf_path}")
```

### 步骤2：文本格式化与分页读取

接下来，我们定义一个辅助函数来对文本进行简单的格式化（例如，替换换行符），然后读取PDF的每一页，提取文本并收集相关元数据（如页码、字符数、词数等）。

```python
def text_formatter(text: str) -> str:
    """对文本进行简单的格式化。"""
    cleaned_text = text.replace("\n", " ").strip()
    # 可以在此处添加更多文本格式化逻辑
    return cleaned_text

def open_and_read_pdf(pdf_path: str) -> list[dict]:
    """打开PDF文件，读取每一页的文本和元数据。"""
    doc = fitz.open(pdf_path)
    pages_and_text = []
    for page_number, page in tqdm(enumerate(doc), desc="读取页面"):
        text = page.get_text()
        text = text_formatter(text)
        pages_and_text.append({
            "page_number": page_number - 41,  # 根据PDF实际情况调整页码偏移
            "page_char_count": len(text),
            "page_word_count": len(text.split(" ")),
            "page_sentence_count_raw": len(text.split(". ")),
            "page_token_count": len(text) / 4,  # 粗略估算：1个token约等于4个字符
            "text": text
        })
    return pages_and_text

![](img/9bf8e9b233650e311443169d7109ebae_68.png)

![](img/9bf8e9b233650e311443169d7109ebae_69.png)

# 读取PDF
pages_and_text = open_and_read_pdf(pdf_path)

# 随机查看几页内容
import random
print(random.sample(pages_and_text, k=2))
```

### 步骤3：使用spaCy将页面拆分为句子

为了更精细地处理文本，我们使用`spaCy`库将每页文本拆分成句子。这比简单地按句号分割更稳健。

```python
import spacy
from spacy.lang.en import English

![](img/9bf8e9b233650e311443169d7109ebae_71.png)

![](img/9bf8e9b233650e311443169d7109ebae_72.png)

# 加载英语模型并添加句子分割器
nlp = English()
nlp.add_pipe("sentencizer")

# 将每页文本拆分为句子
for item in tqdm(pages_and_text, desc="拆分句子"):
    item["sentences"] = list(nlp(item["text"]).sents)
    item["sentences"] = [str(sentence) for sentence in item["sentences"]]  # 转换为字符串
    item["page_sentence_count_spacy"] = len(item["sentences"])

# 查看一个随机样本
print(random.sample(pages_and_text, k=1))
```

### 步骤4：将句子分组为块

由于嵌入模型有输入长度限制（例如，我们即将使用的模型限制为384个token），我们需要将句子分组为更小的块（例如，每组10个句子）。这个过程也称为“分块”。

```python
def split_list(input_list: list, slice_size: int) -> list[list[str]]:
    """将列表递归地分割成指定大小的子列表。"""
    return [input_list[i:i + slice_size] for i in range(0, len(input_list), slice_size)]

![](img/9bf8e9b233650e311443169d7109ebae_74.png)

![](img/9bf8e9b233650e311443169d7109ebae_76.png)

# 定义每个块包含的句子数量
num_sentence_chunk_size = 10

# 将每页的句子分组为块
for item in tqdm(pages_and_text, desc="分块句子"):
    item["sentence_chunks"] = split_list(item["sentences"], num_sentence_chunk_size)
    item["num_chunks"] = len(item["sentence_chunks"])

# 查看一个随机样本
print(random.sample(pages_and_text, k=1))
```

### 步骤5：将每个块作为独立项处理

为了便于后续嵌入和检索，我们将每个句子块作为数据集中一个独立的项。

```python
import re

![](img/9bf8e9b233650e311443169d7109ebae_78.png)

![](img/9bf8e9b233650e311443169d7109ebae_80.png)

pages_and_chunks = []
for item in tqdm(pages_and_text, desc="处理每个块"):
    for sentence_chunk in item["sentence_chunks"]:
        # 将句子列表连接成段落
        joined_sentence_chunk = "".join(sentence_chunk)
        # 在句号后和大写字母前添加空格，改善格式
        joined_sentence_chunk = re.sub(r'\.([A-Z])', r'. \1', joined_sentence_chunk)
        chunk_dict = {
            "page_number": item["page_number"],
            "sentence_chunk": joined_sentence_chunk,
            "chunk_char_count": len(joined_sentence_chunk),
            "chunk_word_count": len(joined_sentence_chunk.split(" ")),
            "chunk_token_count": len(joined_sentence_chunk) / 4
        }
        pages_and_chunks.append(chunk_dict)

# 查看块的数量
print(f"总块数: {len(pages_and_chunks)}")
print(random.sample(pages_and_chunks, k=1))
```

### 步骤6：过滤过短的块

一些块可能只包含标题或引用，信息量很少。我们可以过滤掉那些过短的块（例如，少于30个token）。

![](img/9bf8e9b233650e311443169d7109ebae_82.png)

```python
# 设置最小token长度
min_token_length = 30

![](img/9bf8e9b233650e311443169d7109ebae_84.png)

![](img/9bf8e9b233650e311443169d7109ebae_86.png)

![](img/9bf8e9b233650e311443169d7109ebae_88.png)

# 过滤掉过短的块
pages_and_chunks_over_min_token_len = [chunk for chunk in pages_and_chunks if chunk["chunk_token_count"] > min_token_length]

![](img/9bf8e9b233650e311443169d7109ebae_90.png)

![](img/9bf8e9b233650e311443169d7109ebae_91.png)

print(f"过滤后块数: {len(pages_and_chunks_over_min_token_len)}")
print(random.sample(pages_and_chunks_over_min_token_len, k=1))
```

### 步骤7：嵌入文本块

现在，我们将使用`sentence-transformers`库中的嵌入模型，将每个文本块转换为数值表示（嵌入向量）。嵌入是文本在高维空间中的“有用”的数值表示，相似的文本在嵌入空间中距离更近。

```python
from sentence_transformers import SentenceTransformer
import torch

# 选择嵌入模型（我们使用 all-MiniLM-L6-v2，它是一个质量与速度平衡的模型）
embedding_model = SentenceTransformer("all-mpnet-base-v2", device="cuda" if torch.cuda.is_available() else "cpu")

# 准备要嵌入的文本列表
text_chunks = [chunk["sentence_chunk"] for chunk in pages_and_chunks_over_min_token_len]

# 批量嵌入文本块（GPU加速）
text_chunks_embeddings = embedding_model.encode(text_chunks,
                                                 batch_size=32,
                                                 convert_to_tensor=True)

print(f"嵌入向量形状: {text_chunks_embeddings.shape}")  # 应为 (块数, 嵌入维度)
```

### 步骤8：保存嵌入向量以备后用

最后，我们将文本块及其对应的嵌入向量保存到文件中，以便在第二部分直接加载使用，无需重新计算。

```python
import pandas as pd

![](img/9bf8e9b233650e311443169d7109ebae_93.png)

![](img/9bf8e9b233650e311443169d7109ebae_95.png)

# 创建包含文本和嵌入向量的DataFrame
text_chunks_and_embeddings_df = pd.DataFrame(pages_and_chunks_over_min_token_len)
text_chunks_and_embeddings_df["embedding"] = text_chunks_embeddings.tolist()

# 保存到CSV文件
embeddings_save_path = "text_chunks_and_embeddings_df.csv"
text_chunks_and_embeddings_df.to_csv(embeddings_save_path, index=False)
print(f"嵌入向量已保存至: {embeddings_save_path}")
```

---

![](img/9bf8e9b233650e311443169d7109ebae_97.png)

![](img/9bf8e9b233650e311443169d7109ebae_99.png)

![](img/9bf8e9b233650e311443169d7109ebae_101.png)

## 第二部分：搜索与回答

上一节我们完成了文档的预处理和嵌入向量的创建，本节我们将利用这些嵌入向量，实现查询的语义搜索和答案生成。

![](img/9bf8e9b233650e311443169d7109ebae_103.png)

![](img/9bf8e9b233650e311443169d7109ebae_104.png)

### 步骤1：加载嵌入向量和模型

首先，我们加载之前保存的嵌入向量，并重新实例化嵌入模型（用于编码查询）。

```python
import torch
import pandas as pd
import numpy as np
from sentence_transformers import SentenceTransformer

device = "cuda" if torch.cuda.is_available() else "cpu"

# 加载保存的嵌入向量DataFrame
text_chunks_and_embeddings_df = pd.read_csv("text_chunks_and_embeddings_df.csv")

# 将嵌入向量列从字符串转换回numpy数组
text_chunks_and_embeddings_df["embedding"] = text_chunks_and_embeddings_df["embedding"].apply(lambda x: np.fromstring(x.strip("[]"), sep=" "))
embeddings = torch.tensor(np.stack(text_chunks_and_embeddings_df["embedding"].values), dtype=torch.float32).to(device)

![](img/9bf8e9b233650e311443169d7109ebae_106.png)

# 重新实例化嵌入模型（用于编码查询）
embedding_model = SentenceTransformer("all-mpnet-base-v2", device=device)

![](img/9bf8e9b233650e311443169d7109ebae_108.png)

# 将文本块列表转换为字典列表，便于索引
pages_and_chunks = text_chunks_and_embeddings_df.to_dict(orient="records")
```

### 步骤2：实现语义搜索（向量搜索）

![](img/9bf8e9b233650e311443169d7109ebae_110.png)

![](img/9bf8e9b233650e311443169d7109ebae_111.png)

语义搜索的核心是：将查询文本转换为嵌入向量，然后计算该查询向量与所有文档块嵌入向量之间的相似度，返回最相似的几个块。

我们将使用**点积**作为相似度度量，因为我们的嵌入模型输出已经是归一化的，此时点积等价于余弦相似度，但计算更快。

```python
import time
from torch import nn

![](img/9bf8e9b233650e311443169d7109ebae_113.png)

![](img/9bf8e9b233650e311443169d7109ebae_114.png)

def retrieve_relevant_resources(query: str,
                                embeddings: torch.Tensor,
                                model: SentenceTransformer,
                                n_resources: int = 5,
                                print_time: bool = True):
    """
    给定查询，从嵌入向量中检索最相关的资源。
    返回：分数和索引。
    """
    # 嵌入查询
    query_embedding = model.encode(query, convert_to_tensor=True)
    
    # 计算点积相似度
    start_time = time.time()
    dot_scores = nn.functional.cosine_similarity(query_embedding.unsqueeze(0), embeddings)  # 使用余弦相似度
    end_time = time.time()
    
    if print_time:
        print(f"在 {len(embeddings)} 个嵌入向量上计算分数耗时: {end_time - start_time:.5f} 秒")
    
    # 获取前n个最高分数和对应的索引
    scores, indices = torch.topk(dot_scores, k=n_resources)
    return scores, indices

# 测试语义搜索
query = "什么是宏量营养素？"
scores, indices = retrieve_relevant_resources(query, embeddings, embedding_model)
print(f"查询: {query}")
print(f"前5个相关块的索引: {indices}")
print(f"对应分数: {scores}")
```

### 步骤3：格式化检索结果

为了更清晰地查看检索结果，我们编写一个函数来打印分数最高的几个文本块及其元数据。

```python
from textwrap import fill

def print_top_results_and_scores(query: str,
                                 pages_and_chunks: list[dict],
                                 embeddings: torch.Tensor,
                                 model: SentenceTransformer,
                                 n_resources: int = 5):
    """打印查询的前n个相关结果及其分数。"""
    scores, indices = retrieve_relevant_resources(query, embeddings, model, n_resources, print_time=True)
    print(f"查询: {query}")
    for score, idx in zip(scores, indices):
        print(f"分数: {score:.4f}")
        print(f"文本: {fill(pages_and_chunks[idx]['sentence_chunk'], width=80)}")
        print(f"页码: {pages_and_chunks[idx]['page_number']}")
        print("-" * 50)

# 测试打印函数
print_top_results_and_scores("什么是宏量营养素？", pages_and_chunks, embeddings, embedding_model)
```

![](img/9bf8e9b233650e311443169d7109ebae_116.png)

![](img/9bf8e9b233650e311443169d7109ebae_117.png)

### 步骤4：加载本地LLM用于生成

现在，我们加载一个本地运行的大型语言模型来生成答案。我们将使用Google最近开源的`Gemma 7B`指令微调模型。请注意，运行此模型需要足够的GPU内存（约16GB VRAM用于FP16精度）。如果您的硬件资源有限，可以考虑使用更小的模型（如`Gemma 2B`）或量化版本。

```python
from transformers import AutoTokenizer, AutoModelForCausalLM, BitsAndBytesConfig
import torch

# 根据可用GPU内存选择模型和配置
gpu_memory_gb = torch.cuda.get_device_properties(0).total_memory / (1024**3)
print(f"可用GPU内存: {gpu_memory_gb:.2f} GB")

if gpu_memory_gb > 19:
    # 如果有足够内存，使用FP16精度加载7B模型
    use_quantization_config = False
    model_id = "google/gemma-7b-it"
else:
    # 否则，使用4位量化加载2B模型以节省内存
    use_quantization_config = True
    model_id = "google/gemma-2b-it"

![](img/9bf8e9b233650e311443169d7109ebae_119.png)

![](img/9bf8e9b233650e311443169d7109ebae_121.png)

# 配置量化（如果需要）
if use_quantization_config:
    quantization_config = BitsAndBytesConfig(load_in_4bit=True,
                                             bnb_4bit_compute_dtype=torch.float16)
else:
    quantization_config = None

# 加载分词器
tokenizer = AutoTokenizer.from_pretrained(model_id)

![](img/9bf8e9b233650e311443169d7109ebae_123.png)

![](img/9bf8e9b233650e311443169d7109ebae_124.png)

# 加载模型
llm_model = AutoModelForCausalLM.from_pretrained(model_id,
                                                 quantization_config=quantization_config,
                                                 torch_dtype=torch.float16,
                                                 low_cpu_mem_usage=False,
                                                 device_map