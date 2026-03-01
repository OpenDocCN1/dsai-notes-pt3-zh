# 机器学习运维：P52：通过Streamlit集成OpenAI技术 🚀

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_0.png)

在本节课中，我们将学习如何将OpenAI的API功能集成到一个Web应用中。我们将使用Streamlit框架快速构建一个交互式界面，并重构代码以创建可复用的库。整个过程将涵盖环境设置、代码重构、测试编写以及Web应用开发。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_2.png)

---

## 概述

我们将从一个现有的命令行工具开始，将其核心逻辑提取到一个独立的库中。然后，我们将利用这个库，构建一个能够根据自然语言描述生成代码的Streamlit Web应用。课程将展示如何设置开发环境、确保代码质量，并快速迭代开发。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_4.png)

---

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_6.png)

## 环境设置与代码重构

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_8.png)

上一节我们运行了一个基于OpenAI的问答命令行工具。本节中，我们来看看如何优化项目结构，为后续开发打下基础。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_10.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_12.png)

首先，我们需要确保开发环境配置正确，包括设置GitHub Actions工作流和开发容器。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_14.png)

以下是设置持续集成工作流的步骤：
1.  进入项目的“Actions”标签页。
2.  选择“Set up a workflow yourself”。
3.  粘贴预先准备好的工作流配置代码，用于代码格式化和测试。

同时，我们通过命令 `Shift + Command + P` 并选择“Add Development Container Configuration Files”来配置开发容器，确保环境一致性。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_16.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_18.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_20.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_22.png)

接下来，我们重构项目，将核心功能移入库中以提高代码复用性。

我们创建一个库文件 `oa_lib/solutions.py`，并将命令行工具中的 `submit_question` 函数逻辑移动至此。

```python
# oa_lib/solutions.py
import openai
import os

def submit_question(question: str) -> str:
    """向OpenAI API提交问题并返回答案。"""
    openai.api_key = os.getenv("OPENAI_API_KEY")
    response = openai.Completion.create(
        engine="text-davinci-003",
        prompt=question,
        max_tokens=150
    )
    return response.choices[0].text.strip()
```

原命令行工具则简化为导入并使用库函数。

```python
# question_answer_cli.py
import click
from oa_lib import solutions

@click.command()
@click.argument('question')
def main(question):
    """一个简单的问答CLI工具。"""
    answer = solutions.submit_question(question)
    click.echo(f"答案: {answer}")

if __name__ == '__main__':
    main()
```

运行 `make lint` 和 `make test` 来确保代码质量，解决所有格式和逻辑错误。

---

## 扩展库功能：代码生成

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_24.png)

现在我们已经有了一个基础的库，本节中我们来看看如何为其添加新的功能，例如将自然语言描述转换为代码。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_26.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_28.png)

我们参考OpenAI的文档，使用 `code-davinci-002` 模型来实现代码生成功能。在 `oa_lib/solutions.py` 中添加一个新函数。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_30.png)

```python
# oa_lib/solutions.py
def create_code(text: str, language: str) -> str:
    """根据文本描述和指定语言生成代码。"""
    openai.api_key = os.getenv("OPENAI_API_KEY")
    prompt = f"# 语言: {language}\n# 描述: {text}\n# 代码:\n"
    response = openai.Completion.create(
        engine="code-davinci-002",
        prompt=prompt,
        max_tokens=256
    )
    return response.choices[0].text.strip()
```

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_32.png)

为了快速测试这个新功能，我们创建一个命令行工具 `mk_code.py`。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_34.png)

```python
# mk_code.py
import click
from oa_lib import solutions

@click.command()
@click.option('--language', '-l', default='Python', help='目标编程语言，例如 Python, JavaScript')
@click.argument('text')
def main(text, language):
    """根据描述生成代码示例。"""
    code = solutions.create_code(text, language)
    click.echo(f"生成的 {language} 代码：\n{code}")

if __name__ == '__main__':
    main()
```

运行工具进行测试：
```bash
./mk_code.py -l Python “计算两个数字的和”
```

---

## 构建Streamlit Web应用

有了功能完善的库之后，本节我们将利用它快速构建一个交互式的Web应用。

我们创建一个新的Streamlit应用文件 `code_gen_web_app.py`。其核心是提供一个文本输入框供用户描述需求，并选择一个目标语言，然后调用我们的库来生成并显示代码。

```python
# code_gen_web_app.py
import streamlit as st
from oa_lib import solutions

st.title('OpenAI 代码生成器 🧑‍💻')
st.write('输入您的需求，选择语言，即可自动生成代码。')

# 用户输入
user_input = st.text_area("描述您想要的功能：", "例如：创建一个函数，计算列表的平均值")
language = st.selectbox("选择编程语言：", ["Python", "JavaScript", "SQL", "Java"])

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_36.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_37.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_39.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_41.png)

if st.button('生成代码'):
    with st.spinner('正在生成代码，请稍候...'):
        try:
            generated_code = solutions.create_code(user_input, language)
            st.code(generated_code, language=language.lower())
        except Exception as e:
            st.error(f"生成代码时出错: {e}")
```

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_43.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_45.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_47.png)

运行Streamlit应用：
```bash
streamlit run code_gen_web_app.py --server.enableCORS false
```
请注意，`--server.enableCORS false` 参数可能在某些开发环境下需要，以解决应用加载问题。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_49.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_51.png)

应用启动后，在浏览器中打开提供的本地地址，即可使用代码生成器。

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_53.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_55.png)

---

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_57.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_59.png)

## 总结

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_61.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_63.png)

![](img/4453d35498bdfd5cfb13d03c5fdc52e2_65.png)

本节课中我们一起学习了如何将OpenAI API集成到实际项目中。我们从重构代码、创建可复用库开始，然后扩展了代码生成功能，并最终使用Streamlit框架构建了一个直观的Web应用程序。这个过程展示了如何系统化地开发AI应用，并强调了代码质量、环境配置和快速原型开发的重要性。