# 024：自定义输出解析器 🛠️

在本节课中，我们将学习如何为LangChain创建自定义输出解析器。这使我们能够从大型语言模型通常产生的非结构化输出中，提取出我们真正需要的数据。

我们假设您使用OpenAI，并在此设置了环境变量。如果您使用Google Colab，它也会尝试从Colab可存储的密钥中获取。

---

![](img/d44e8adbfaf152964f41b7017956bdf9_1.png)

### 创建自定义输出解析器的两种方法

![](img/d44e8adbfaf152964f41b7017956bdf9_2.png)

自定义输出解析器主要有两种创建方式。

*   您可以在LangChain表达式语言中使用 `RunnableLambda`。
*   您也可以从输出解析器的基类进行继承。

换句话说，您既可以扩展基类，也可以使用Lambda。Lambda本质上是Python中一种可以传递的匿名函数。

---

![](img/d44e8adbfaf152964f41b7017956bdf9_4.png)

![](img/d44e8adbfaf152964f41b7017956bdf9_5.png)

### 方法一：使用RunnableLambda

以下代码创建了要使用的基础LLM。这里假设使用OpenAI，但您可以将其替换为任何您想要的大型语言模型，LangChain会处理其中的差异。

```python
# 示例：导入和初始化LLM
from langchain.llms import OpenAI
llm = OpenAI()
```

接下来，我创建一个输出解析器，其功能基本上是翻转文本的大小写。例如，“Hello World”会变成“hELLO wORLD”。

![](img/d44e8adbfaf152964f41b7017956bdf9_7.png)

![](img/d44e8adbfaf152964f41b7017956bdf9_8.png)

我只需为其创建解析函数，然后调用Python标准函数 `swapcase()`。您可以看到，我只需将我的输出传递给它。因为我本质上传递的是一个名为 `parse` 的Lambda函数体。然后，我们可以用“hello”来调用这个大语言模型。

它将处理的不是我输入的“hello”这个词，而是LLM对“hello”的响应，并翻转其大小写，正如您在那里所看到的。

```python
# 示例：使用Lambda创建简单的解析器
from langchain.schema.runnable import RunnableLambda

def swap_case(text: str) -> str:
    return text.swapcase()

# 将函数包装为RunnableLambda
case_swapper = RunnableLambda(swap_case)

![](img/d44e8adbfaf152964f41b7017956bdf9_10.png)

# 在链中使用
chain = llm | case_swapper
result = chain.invoke("hello")
```

这就是使用Lambda方法的方式。

---

### 方法二：继承基类

![](img/d44e8adbfaf152964f41b7017956bdf9_12.png)

![](img/d44e8adbfaf152964f41b7017956bdf9_13.png)

如果您想从基类继承，当然也可以这样做。

![](img/d44e8adbfaf152964f41b7017956bdf9_14.png)

这里我创建了一个名为 `BooleanOutputParser` 的解析器，它继承自LangChain内置的 `BaseOutputParser` 基类，并指定我们期望处理布尔值。

![](img/d44e8adbfaf152964f41b7017956bdf9_16.png)

这是一个用于解释“是/否”字符串与布尔值的自定义解析器。

![](img/d44e8adbfaf152964f41b7017956bdf9_18.png)

我们定义真值和假值。它通过去除空白字符来清理文本，然后确保值符合预期。

您可以看到它的灵活性：用“yes”调用，它会返回 `True`；用“okay”调用，它也会返回 `True`；用“no”调用，它会返回 `False`。

它非常适应，能够处理所有可能表示真或假的不同类型的值。

![](img/d44e8adbfaf152964f41b7017956bdf9_20.png)

```python
# 示例：通过继承基类创建自定义解析器
from langchain.schema import BaseOutputParser
from typing import Any

![](img/d44e8adbfaf152964f41b7017956bdf9_22.png)

class BooleanOutputParser(BaseOutputParser[bool]):
    """自定义解析器，将‘是/否’类字符串解析为布尔值。"""

    true_values = ["yes", "y", "okay", "ok", "true", "t", "1"]
    false_values = ["no", "n", "false", "f", "0"]

    def parse(self, text: str) -> bool:
        """解析输入文本为布尔值。"""
        cleaned_text = text.strip().lower()
        if cleaned_text in self.true_values:
            return True
        elif cleaned_text in self.false_values:
            return False
        else:
            raise ValueError(f"无法将‘{text}’解析为布尔值。")

![](img/d44e8adbfaf152964f41b7017956bdf9_24.png)

# 使用自定义解析器
parser = BooleanOutputParser()
print(parser.parse("yes"))  # 输出: True
print(parser.parse("NO"))   # 输出: False
```

![](img/d44e8adbfaf152964f41b7017956bdf9_26.png)

---

![](img/d44e8adbfaf152964f41b7017956bdf9_28.png)

### 应用：提取Python代码

接下来，我们将看一个剥离非Python文本的例子。这有时会很有用。

![](img/d44e8adbfaf152964f41b7017956bdf9_30.png)

例如，如果我要求它使用蒙特卡洛方法计算π的值，它通常会在代码前加上一大堆前言，然后才是Python代码。

![](img/d44e8adbfaf152964f41b7017956bdf9_31.png)

您可能希望有一种方法来剥离那段前言文本。

![](img/d44e8adbfaf152964f41b7017956bdf9_33.png)

这里，我们基本上会找到其中所有的Python代码块，并移除其他所有内容。

![](img/d44e8adbfaf152964f41b7017956bdf9_35.png)

然后您可以看到我们这里的示例：它只抓取嵌入的Python文本，并移除其他所有内容。

![](img/d44e8adbfaf152964f41b7017956bdf9_37.png)

接着，利用这个功能，我们可以创建代码输出解析器，它将使用我们刚刚构建的那个移除器。当我向它提出这类请求时，您将只得到纯代码文本作为返回。

```python
# 示例：创建提取Python代码的解析器
import re

![](img/d44e8adbfaf152964f41b7017956bdf9_39.png)

def extract_python_code(text: str) -> str:
    """从文本中提取Python代码块。"""
    # 匹配Markdown代码块或直接以`import`或`def`等开头的代码行
    pattern = r"```python\n(.*?)```|(?:^|\n)((?:import|def|class|from).*?)(?=\n\n|$)"
    matches = re.findall(pattern, text, re.DOTALL)
    # 合并所有匹配的代码部分
    code_blocks = [match[0] or match[1] for match in matches if any(match)]
    return "\n\n".join(code_blocks) if code_blocks else text

# 在链中使用
code_extractor = RunnableLambda(extract_python_code)
code_chain = llm | code_extractor
code_result = code_chain.invoke("Write a Python function to calculate factorial.")
```

![](img/d44e8adbfaf152964f41b7017956bdf9_41.png)

![](img/d44e8adbfaf152964f41b7017956bdf9_42.png)

---

### 总结

本节课中，我们一起学习了为LangChain创建自定义输出解析器的两种主要方法：使用 `RunnableLambda` 包装简单函数，以及通过继承 `BaseOutputParser` 基类来构建更结构化的解析器。我们还通过实例看到了如何利用解析器进行大小写转换、布尔值解析以及从混合文本中提取纯Python代码。掌握自定义输出解析器能帮助您更精准、更灵活地控制和处理LLM的输出，使其更好地集成到您的应用流程中。