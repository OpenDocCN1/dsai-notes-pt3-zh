# 机器学习运维：从零构建Python函数 🚀

![](img/167ff403fde6068981e22130dcf39eab_0.png)

![](img/167ff403fde6068981e22130dcf39eab_2.png)

![](img/167ff403fde6068981e22130dcf39eab_4.png)

![](img/167ff403fde6068981e22130dcf39eab_6.png)

![](img/167ff403fde6068981e22130dcf39eab_7.png)

在本课程中，我们将学习如何从零开始构建一个Python函数，并将其逐步发展为一个完整的、可部署的微服务。我们将涵盖从基础语句、项目结构、命令行工具到容器化和云端部署的完整流程。

---

![](img/167ff403fde6068981e22130dcf39eab_9.png)

## 1：从零开始：Python基础语句与环境搭建 🏁

![](img/167ff403fde6068981e22130dcf39eab_11.png)

![](img/167ff403fde6068981e22130dcf39eab_13.png)

![](img/167ff403fde6068981e22130dcf39eab_15.png)

上一节我们介绍了课程目标，本节中我们来看看如何搭建开发环境并编写最基础的Python语句。

### 概述
我们将从最基础的“Hello World”开始，学习Python的核心语句、变量和数据结构，并搭建一个交互式的开发环境。

### 搭建开发环境
首先，创建一个GitHub仓库来管理我们的代码。推荐使用基于浏览器的开发环境，如Google Colab或GitHub Codespaces，它们提供了交互式学习和软件工程开发两种模式。

![](img/167ff403fde6068981e22130dcf39eab_17.png)

![](img/167ff403fde6068981e22130dcf39eab_18.png)

![](img/167ff403fde6068981e22130dcf39eab_20.png)

*   **Colab/Jupyter Notebook**：适合交互式学习和记笔记，像处理文档一样处理代码。
*   **GitHub Codespaces/VS Code**：适合构建结构化的软件工程项目。

### 编写基础语句
以下是Python中最核心的几个概念：

1.  **打印语句**：使用 `print()` 函数输出信息。
    ```python
    print("Hello World")
    ```

2.  **变量**：用于存储数据。
    ```python
    x = 1
    y = 2
    print(x + y)  # 输出：3
    ```

![](img/167ff403fde6068981e22130dcf39eab_22.png)

![](img/167ff403fde6068981e22130dcf39eab_24.png)

![](img/167ff403fde6068981e22130dcf39eab_26.png)

3.  **数据结构 - 列表**：用于存储一系列有序的元素。
    ```python
    my_list = [1, 2, 3]
    print(my_list[0])  # 输出：1 (索引从0开始)
    ```

![](img/167ff403fde6068981e22130dcf39eab_28.png)

4.  **数据结构 - 字典**：用于存储键值对，是Python中最灵活的数据结构之一。
    ```python
    my_dict = {1: "one", 2: "two"}
    print(my_dict.keys())   # 输出：dict_keys([1, 2])
    print(my_dict.values()) # 输出：dict_values(['one', 'two'])
    ```

5.  **循环控制**：用于遍历数据结构中的元素。
    ```python
    # 遍历字典
    for key, value in my_dict.items():
        print(f"This is my key: {key}")
        print(f"This is my value: {value}")

    # 遍历列表
    for item in my_list:
        print(f"This is the value in the list: {item}")
    ```

**总结**：掌握了打印、变量、列表、字典和循环，你就拥有了用Python进行基础编程和数据处理的能力。这是构建更复杂功能（如函数）的基石。

---

## 2：构建项目：从脚本到可测试的工程结构 🏗️

上一节我们学习了基础语句，本节中我们来看看如何将这些代码组织成一个结构化的、可测试的软件工程项目。

![](img/167ff403fde6068981e22130dcf39eab_30.png)

![](img/167ff403fde6068981e22130dcf39eab_31.png)

### 概述
我们将学习如何将零散的脚本转化为一个拥有标准目录结构、自动化测试和代码质量检查的专业项目。

### 创建Python脚本
首先，将代码写入 `.py` 文件，形成可执行的脚本。

*   **`hello.py`**：一个简单的Hello World脚本。
    ```python
    print("Hello World")
    ```
    运行方式：`python hello.py`

*   **`my_statements.py`**：一个更复杂的脚本，包含列表、字典和循环。
    ```python
    my_list = ["apple", "cherry", "lemon"]
    my_dict = {"drink": "coffee", "milk": "whole milk"}

    for item in my_list:
        print(f"My favorite thing to eat is {item}")

    for _, value in my_dict.items():
        print(f"My favorite thing to drink is {value}")
    ```

### 搭建项目脚手架
为了确保代码的可重复性和可维护性，需要为项目创建标准结构。以下是三个核心文件：

1.  **`Makefile`**：用于定义常用的自动化命令（如安装、测试、代码检查）。
    ```makefile
    install:
        pip install --upgrade pip
        pip install -r requirements.txt

    lint:
        pylint --disable=C0114,C0116 *.py

    test:
        python -m pytest -v

    all: install lint test
    ```
    *运行命令示例*：`make all` 会依次执行安装、代码检查和测试。

![](img/167ff403fde6068981e22130dcf39eab_33.png)

2.  **`requirements.txt`**：列出项目依赖的第三方库。
    ```
    pylint
    pytest
    black
    ```

![](img/167ff403fde6068981e22130dcf39eab_35.png)

![](img/167ff403fde6068981e22130dcf39eab_37.png)

![](img/167ff403fde6068981e22130dcf39eab_38.png)

3.  **测试文件**：用于编写单元测试，确保代码逻辑正确。
    *   **`test_hello.py`**：测试 `hello.py` 中的函数。
        ```python
        from hello import add

        def test_add():
            assert 2 == add(1, 1)
        ```

![](img/167ff403fde6068981e22130dcf39eab_40.png)

![](img/167ff403fde6068981e22130dcf39eab_42.png)

![](img/167ff403fde6068981e22130dcf39eab_44.png)

### 使用虚拟环境
为了避免不同项目间的依赖冲突，强烈建议使用Python虚拟环境。

![](img/167ff403fde6068981e22130dcf39eab_46.png)

```bash
# 创建虚拟环境
python3 -m venv .venv
# 激活虚拟环境 (Linux/Mac)
source .venv/bin/activate
# 激活后，安装的包将仅限于此项目
```

![](img/167ff403fde6068981e22130dcf39eab_48.png)

![](img/167ff403fde6068981e22130dcf39eab_50.png)

### 集成持续集成
使用GitHub Actions可以自动化运行测试和代码检查。每次代码推送后，GitHub会自动运行 `make all` 命令，并通过状态徽章直观展示项目健康度。

**总结**：通过创建 `Makefile`、`requirements.txt` 和测试文件，我们建立了一个专业的项目结构。这就像为代码建立了“退休账户”，现在的投入（编写测试和配置）将在未来长期受益，使协作、维护和部署变得异常轻松。

---

![](img/167ff403fde6068981e22130dcf39eab_52.png)

## 3：核心构建块：深入理解Python函数 ⚙️

![](img/167ff403fde6068981e22130dcf39eab_54.png)

![](img/167ff403fde6068981e22130dcf39eab_56.png)

![](img/167ff403fde6068981e22130dcf39eab_58.png)

上一节我们建立了项目结构，本节中我们来看看Python编程的核心——函数。

### 概述
函数是Python中最重要的构建块。理解函数是将代码逻辑模块化、实现代码复用和构建复杂应用（如命令行工具、Web服务）的关键。

### 函数的多种形式
函数可以有多种形式，从简单到复杂：

1.  **最简单的函数**：什么都不做。
    ```python
    def simple():
        pass
    ```

![](img/167ff403fde6068981e22130dcf39eab_60.png)

![](img/167ff403fde6068981e22130dcf39eab_62.png)

![](img/167ff403fde6068981e22130dcf39eab_64.png)

![](img/167ff403fde6068981e22130dcf39eab_65.png)

2.  **无参数函数**：执行一些操作，但不返回数据。
    ```python
    def simple2():
        print("simple")
    simple2()  # 调用函数
    ```

3.  **最实用的函数模式**：接收输入，进行处理，并返回输出。这是构建更高级应用的基础模式。
    ```python
    def worker(fruit):
        statement = f"My favorite meal is chicken and {fruit}"
        meals = {"dinner": statement}
        return meals

    def human(food):
        consume = food["dinner"]
        return consume

    # 使用函数
    meal = worker("apple")
    print(f"I want my meal, it will be {human(meal)}")
    ```
    **模式解析**：
    *   `worker` 函数接收参数，处理业务逻辑，将结果放入数据结构（字典）并返回。
    *   `human` 函数接收 `worker` 的返回结果，进行进一步处理。
    *   这种“输入-处理-输出”并传递给下一个函数的模式，在构建命令行工具、Web API和数据处理流水线时极为常见。

![](img/167ff403fde6068981e22130dcf39eab_67.png)

### 构建一个实际函数：维基百科摘要抓取器
让我们构建一个更有用的函数，它调用维基百科API获取页面摘要。

![](img/167ff403fde6068981e22130dcf39eab_69.png)

1.  **添加依赖**：在 `requirements.txt` 中加入 `wikipedia` 库并安装 (`make install`)。
2.  **探索API**：使用 `ipython` 交互环境快速了解库的用法。
    ```python
    import wikipedia
    print(wikipedia.summary("Microsoft", sentences=1))
    ```
3.  **编写函数**：创建 `wikibot.py`，将逻辑封装成函数。
    ```python
    import wikipedia

    def scrape(name="Microsoft", length=1):
        """从维基百科抓取摘要"""
        result = wikipedia.summary(name, sentences=length)
        return result

    if __name__ == "__main__":
        # 当直接运行脚本时执行
        print(scrape("Facebook"))
    ```
4.  **为函数编写测试**：创建 `test_wikibot.py` 确保函数逻辑正确。
    ```python
    from wikibot import scrape

    def test_scrape():
        result = scrape("Microsoft")
        assert "Microsoft" in result
    ```

**总结**：函数是封装逻辑、实现代码复用的单元。掌握“接收参数-处理-返回结果”这一核心模式，是构建命令行工具、Web服务乃至机器学习流水线的第一步。我们已将维基百科抓取逻辑成功封装为一个可测试的函数。

---

## 4：功能扩展：将函数转化为命令行工具 🛠️

![](img/167ff403fde6068981e22130dcf39eab_71.png)

![](img/167ff403fde6068981e22130dcf39eab_73.png)

![](img/167ff403fde6068981e22130dcf39eab_75.png)

上一节我们创建了可复用的函数，本节中我们来看看如何为其添加命令行界面，使其成为易用的工具。

![](img/167ff403fde6068981e22130dcf39eab_77.png)

![](img/167ff403fde6068981e22130dcf39eab_78.png)

![](img/167ff403fde6068981e22130dcf39eab_80.png)

![](img/167ff403fde6068981e22130dcf39eab_82.png)

### 概述
我们将使用两个流行的库——`Click` 和 `Fire`，为我们的函数快速创建功能强大且用户友好的命令行界面。

![](img/167ff403fde6068981e22130dcf39eab_84.png)

![](img/167ff403fde6068981e22130dcf39eab_85.png)

### 使用 Click 创建命令行工具
`Click` 库通过装饰器让定义命令行参数变得非常简单。

![](img/167ff403fde6068981e22130dcf39eab_87.png)

1.  **安装依赖**：将 `click` 加入 `requirements.txt` 并安装。
2.  **改造 `wikibot.py`**：添加Click命令行接口。
    ```python
    import click
    import wikipedia

    def scrape(name, length):
        result = wikipedia.summary(name, sentences=length)
        return result

    @click.command()
    @click.option("--name", prompt="Wikipedia page to scrape", help="The web page we want to scrape.")
    @click.option("--length", default=1, help="Length of the output from Wikipedia.")
    def cli(name, length):
        """一个简单的维基百科摘要抓取工具"""
        result = scrape(name, length)
        click.echo(click.style(result, fg="green"))  # 用绿色输出结果

    if __name__ == "__main__":
        cli()
    ```
3.  **使用工具**：
    ```bash
    # 查看帮助
    python wikibot.py --help
    # 运行工具
    python wikibot.py --name Microsoft --length 2
    ```

![](img/167ff403fde6068981e22130dcf39eab_89.png)

![](img/167ff403fde6068981e22130dcf39eab_91.png)

![](img/167ff403fde6068981e22130dcf39eab_93.png)

### 使用 Fire 自动生成命令行工具
`Fire` 库是Google开发的，可以自动将任何Python对象（函数、类等）转化为CLI，几乎无需额外代码。

1.  **安装依赖**：将 `fire` 加入 `requirements.txt`。
2.  **创建 `fire_cli.py`**：
    ```python
    import fire
    from my_lib.bot import scrape  # 从我们的库中导入函数

    if __name__ == "__main__":
        fire.Fire(scrape)  # 关键的一行：让Fire接管scrape函数
    ```
3.  **使用工具**：
    ```bash
    # 自动生成帮助信息
    python fire_cli.py --help
    # 运行工具
    python fire_cli.py --name Microsoft --length 1
    ```
    `Fire` 会自动解析 `scrape` 函数的参数 (`name`, `length`) 并将其转化为命令行选项。

### 为命令行工具添加测试
使用 `click.testing` 可以为Click应用编写自动化测试。

![](img/167ff403fde6068981e22130dcf39eab_95.png)

![](img/167ff403fde6068981e22130dcf39eab_97.png)

```python
from click.testing import CliRunner
from wikibot import cli

def test_cli():
    runner = CliRunner()
    result = runner.invoke(cli, ["--name", "Microsoft"])
    assert result.exit_code == 0
    assert "Microsoft" in result.output
```

**总结**：通过 `Click` 和 `Fire`，我们可以轻松地将一个纯Python函数转化为功能完整的命令行工具。`Click` 提供了更多自定义和控制选项，而 `Fire` 则以极简的代码实现了自动化CLI生成。这极大地提升了函数的可用性和可交互性。

---

![](img/167ff403fde6068981e22130dcf39eab_99.png)

![](img/167ff403fde6068981e22130dcf39eab_101.png)

![](img/167ff403fde6068981e22130dcf39eab_103.png)

## 5：服务化：将函数部署为Web微服务 🌐

![](img/167ff403fde6068981e22130dcf39eab_105.png)

上一节我们创建了命令行工具，本节中我们来看看如何将同样的函数逻辑包装成一个可通过HTTP访问的Web API。

![](img/167ff403fde6068981e22130dcf39eab_107.png)

![](img/167ff403fde6068981e22130dcf39eab_109.png)

![](img/167ff403fde6068981e22130dcf39eab_111.png)

### 概述
我们将使用 `FastAPI` 框架快速构建一个RESTful API，它能够提供与命令行工具相同的功能，并通过Swagger UI自动生成交互式文档。

![](img/167ff403fde6068981e22130dcf39eab_112.png)

![](img/167ff403fde6068981e22130dcf39eab_114.png)

### 构建FastAPI应用
1.  **安装依赖**：将 `fastapi`, `uvicorn`, `pydantic` 加入 `requirements.txt` 并安装。
2.  **创建主应用文件 `main.py`**：
    ```python
    from fastapi import FastAPI
    from pydantic import BaseModel
    from my_lib.bot import scrape  # 导入我们自己的函数

    # 定义请求体的数据模型
    class Wiki(BaseModel):
        name: str

    # 创建FastAPI实例
    app = FastAPI()

    # 定义一个根路径端点，用于健康检查
    @app.get("/")
    def read_root():
        return {"Hello": "Functions"}

    # 定义核心的API端点
    @app.post("/wiki/")
    def scrape_story(wiki: Wiki):
        """接收一个包含页面名称的JSON，返回维基百科摘要"""
        result = scrape(wiki.name)
        payload = {"wiki_page": wiki.name, "scraped_result": result}
        return payload
    ```
3.  **运行服务**：
    ```bash
    uvicorn main:app --reload --host 0.0.0.0 --port 8080
    ```
    *   `main:app`：指定应用对象。
    *   `--reload`：开发模式，代码修改后自动重启。
    *   `--host 0.0.0.0`：允许外部访问。
    *   `--port 8080`：指定服务端口。

![](img/167ff403fde6068981e22130dcf39eab_116.png)

![](img/167ff403fde6068981e22130dcf39eab_118.png)

![](img/167ff403fde6068981e22130dcf39eab_120.png)

### 测试API
启动服务后，打开浏览器访问：
*   `http://localhost:8080/`：返回 `{"Hello": "Functions"}`。
*   `http://localhost:8080/docs`：自动生成的Swagger交互式文档。你可以在这里直接测试 `/wiki/` 端点，无需编写任何客户端代码。

### 使用cURL测试API
也可以通过命令行工具如 `cURL` 进行测试：
```bash
curl -X POST "http://localhost:8080/wiki/" \
     -H "Content-Type: application/json" \
     -d '{"name":"Microsoft"}'
```

**总结**：使用 `FastAPI`，我们只需极少的代码就将一个本地函数变成了一个可通过网络调用的Web服务。自动生成的API文档极大地简化了前后端协作。现在，我们的函数逻辑可以通过命令行和HTTP两种方式被调用，适用性大大增强。

---

![](img/167ff403fde6068981e22130dcf39eab_122.png)

## 6：容器化与部署：迈向生产环境 🐳

![](img/167ff403fde6068981e22130dcf39eab_124.png)

![](img/167ff403fde6068981e22130dcf39eab_126.png)

![](img/167ff403fde6068981e22130dcf39eab_128.png)

![](img/167ff403fde6068981e22130dcf39eab_130.png)

![](img/167ff403fde6068981e22130dcf39eab_132.png)

上一节我们创建了Web服务，本节中我们来看看如何将其打包成容器，并部署到云平台，实现持续交付。

![](img/167ff403fde6068981e22130dcf39eab_134.png)

![](img/167ff403fde6068981e22130dcf39eab_135.png)

![](img/167ff403fde6068981e22130dcf39eab_137.png)

![](img/167ff403fde6068981e22130dcf39eab_139.png)

![](img/167ff403fde6068981e22130dcf39eab_141.png)

![](img/167ff403fde6068981e22130dcf39eab_143.png)

### 概述
容器化将应用及其所有依赖打包成一个标准单元，确保环境一致性。我们将使用Docker构建镜像，并部署到AWS的托管服务上。

### 使用Docker容器化应用
1.  **创建 `Dockerfile`**：
    ```dockerfile
    # 使用轻量级的Python镜像
    FROM python:3.9-slim
    # 设置工作目录
    WORKDIR /app
    # 复制依赖文件并安装
    COPY requirements.txt .
    RUN pip install --no-cache-dir -r requirements.txt
    # 复制应用代码和自定义库
    COPY main.py .
    COPY my_lib ./my_lib
    # 声明容器运行时暴露的端口
    EXPOSE 8080
    # 启动命令
    CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8080"]
    ```
2.  **构建Docker镜像**：
    ```bash
    docker build -t wiki-service .
    ```
3.  **本地运行容器**：
    ```bash
    docker run -p 8080:8080 wiki-service
    ```
    访问 `http://localhost:8080/docs` 确认服务在容器内运行正常。

### 推送到容器仓库
为了在云上部署，需要将镜像推送到一个容器仓库（如AWS ECR）。

1.  在AWS ECR控制台创建一个新的仓库（例如 `wiki-repo`）。
2.  按照ECR提供的指引，在本地终端执行登录、打标签和推送命令：
    ```bash
    # 1. 登录到ECR
    aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <account-id>.dkr.ecr.<region>.amazonaws.com
    # 2. 为本地镜像打上ECR仓库的标签
    docker tag wiki-service:latest <account-id>.dkr.ecr.<region>.amazonaws.com/wiki-repo:latest
    # 3. 推送镜像到ECR
    docker push <account-id>.dkr.ecr.<region>.amazonaws.com/wiki-repo:latest
    ```

### 部署到AWS App Runner
AWS App Runner是一项完全托管的服务，可以自动从容器仓库部署Web服务。

![](img/167ff403fde6068981e22130dcf39eab_145.png)

![](img/167ff403fde6068981e22130dcf39eab_147.png)

![](img/167ff403fde6068981e22130dcf39eab_149.png)

1.  在App Runner控制台点击“创建服务”。
2.  选择“容器仓库”，并浏览选择我们刚刚推送的 `wiki-repo` 镜像。
3.  配置服务名称（如 `function-as-a-service`），其他设置可保持默认。
4.  点击“创建并部署”。App Runner会自动完成以下步骤：
    *   从ECR拉取镜像。
    *   配置网络和负载均衡。
    *   运行健康检查。
    *   提供一个可访问的HTTPS端点。

部署完成后，App Runner会提供一个URL（如 `https://xxx.us-east-1.awsapprunner.com`）。访问此URL的 `/docs` 路径，即可使用运行在AWS云上的微服务。更重要的是，App Runner设置了自动部署流水线，以后每次向ECR推送新的镜像标签，服务都会自动更新。

**总结**：通过Docker容器化和AWS App Runner，我们实现了从代码到生产部署的自动化流水线。这个过程展示了现代软件交付的核心：**一次构建，随处运行**。我们从一个简单的Python函数开始，最终获得了一个高可用、可自动扩展、持续交付的云原生微服务。

---

## 课程总结 🎉

在本课程中，我们一起完成了一次完整的Python函数演进之旅：

1.  **奠基**：从“Hello World”和基础数据结构开始，掌握了Python的核心语法。
2.  **工程化**：建立了标准的项目结构，引入了代码检查、格式化、单元测试和持续集成，使项目变得专业且可靠。
3.  **抽象核心**：深入理解了函数作为代码构建块的重要性，并封装了可重用的业务逻辑。
4.  **多样化接口**：为同一个函数逻辑添加了命令行界面（使用Click和Fire），大大提升了工具的易用性。
5.  **服务化**：使用FastAPI将函数快速转变为拥有自动文档的Web API，使其可通过网络调用。
6.  **产品化**：通过Docker容器化应用，并利用AWS ECR和App Runner将其部署到云端，实现了完整的持续交付流水线。

![](img/167ff403fde6068981e22130dcf39eab_151.png)

![](img/167ff403fde6068981e22130dcf39eab_153.png)

![](img/167ff403fde6068981e22130dcf39eab_154.png)

这条学习路径的核心思想是：**从简单开始，迭代演进**。你不需要一开始就设计一个庞大的系统。从一个能工作的简单函数出发，逐步添加项目结构、测试、不同的接口和部署策略，最终就能构建出健壮、可维护的生产级应用。希望本教程为你提供了从“写代码”到“交付产品”的清晰路线图。