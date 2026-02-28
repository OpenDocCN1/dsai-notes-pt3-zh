# 应用Python数据工程：3：Pytest大师班（可选） 🧪

![](img/b474a0e6453db60c238a6d55d6be3b12_0.png)

在本节课中，我们将从零开始，学习如何构建一个完整的Python项目测试环境。我们将涵盖从设置本地开发环境、使用持续集成服务器，到应用Pytest的高级功能，并最终构建一个包含库、命令行工具和Web服务的真实项目。

![](img/b474a0e6453db60c238a6d55d6be3b12_2.png)

## 概述：为什么需要测试？

测试是DevOps实践的核心组成部分。其核心概念是能够自动测试代码，形成一个反馈循环，即持续集成。持续集成的本质是能够快速获知代码是否正常工作。

![](img/b474a0e6453db60c238a6d55d6be3b12_4.png)

一旦你的代码在开发环境中正常工作，下一步就是将其复制到云端或生产环境。为此，你需要：
1.  **基础设施即代码**：能够定义与开发环境相似的云环境。
2.  **测试**：即持续集成组件。
3.  **部署**：将所有部分整合并部署到目标环境。

这就是持续交付。测试之所以重要，是因为它是持续交付的强制性组成部分。你肯定不希望将错误的代码部署到生产环境并导致服务中断。测试的本质是先在本地确保代码正常工作，然后将其可靠地复制到基于云的环境中。

## 第一部分：搭建本地开发环境

上一节我们介绍了测试的重要性，本节中我们来看看如何搭建一个高效的本地开发环境。

首先，我们从一个云基础的开发环境开始。目前，大多数开发者使用云基础开发环境会更好。我们将使用GitHub Codespaces，它类似于AWS Cloud9等其他环境。

### 创建并配置虚拟环境

![](img/b474a0e6453db60c238a6d55d6be3b12_6.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_7.png)

在任何Python项目中，第一步通常是创建一个Python虚拟环境。这可以确保项目依赖被隔离在一个目录中，提高可靠性。

以下是创建和激活虚拟环境的步骤：

```bash
# 创建虚拟环境，将其放在主目录的隐藏文件夹中，避免意外提交到Git仓库
virtualenv ~/.venv

# 激活虚拟环境
source ~/.venv/bin/activate

# 验证当前使用的Python解释器
which python
```

为了在每次打开新终端时自动激活虚拟环境，可以将其添加到 `~/.bashrc` 配置文件中：

```bash
# 编辑bashrc文件
vim ~/.bashrc

# 在文件末尾添加以下行
source ~/.venv/bin/activate
```

### 创建项目脚手架

接下来，我们为测试项目创建一个基础脚手架。一个最小化的项目结构通常包括以下文件：

```bash
# 使用touch命令创建空文件（幂等操作）
touch Makefile requirements.txt hello.py test_hello.py
```

以下是每个文件的作用：
*   **`Makefile`**：用于存放复杂的命令，方便重复调用。
*   **`requirements.txt`**：列出项目依赖的包。
*   **`hello.py`**：应用程序主文件。
*   **`test_hello.py`**：测试文件。

### 配置Makefile

Makefile可以极大地简化开发流程。以下是一个示例Makefile，包含了安装、测试、代码格式化和代码检查等常用任务：

```makefile
install:
    pip install --upgrade pip
    pip install -r requirements.txt

test:
    python -m pytest -vvs

![](img/b474a0e6453db60c238a6d55d6be3b12_9.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_11.png)

lint:
    pylint --disable=C0114,C0116 *.py

format:
    black *.py

all: install lint test format
```

![](img/b474a0e6453db60c238a6d55d6be3b12_13.png)

使用 `make` 命令可以查看所有可用的任务：

![](img/b474a0e6453db60c238a6d55d6be3b12_15.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_17.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_19.png)

```bash
make
```

### 管理项目依赖

![](img/b474a0e6453db60c238a6d55d6be3b12_21.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_23.png)

在 `requirements.txt` 文件中，我们列出项目所需的包。对于测试项目，至少需要 `pytest`。此外，还可以添加其他有用的工具：

```txt
pytest
pytest-cov
pylint
black
ipython
```

使用 `make install` 命令安装所有依赖。确保代码可安装是持续集成的一个重要环节。

```bash
make install
```

![](img/b474a0e6453db60c238a6d55d6be3b12_25.png)

### 交互式调试与原型设计

![](img/b474a0e6453db60c238a6d55d6be3b12_27.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_29.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_31.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_33.png)

`iPython` 是一个强大的交互式Python shell，非常适合在编写正式测试前调试代码或进行原型设计。

![](img/b474a0e6453db60c238a6d55d6be3b12_35.png)

```python
# 在iPython中导入模块并测试功能
from hello import more_hello
assert "hi" == more_hello()
```

![](img/b474a0e6453db60c238a6d55d6be3b12_37.png)

### 编写第一个Pytest测试

Pytest使得编写测试变得非常简单。测试文件通常以 `test_` 开头，测试函数以 `test_` 开头。

在 `test_hello.py` 中：

![](img/b474a0e6453db60c238a6d55d6be3b12_39.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_40.png)

```python
from hello import more_hello

![](img/b474a0e6453db60c238a6d55d6be3b12_42.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_44.png)

def test_more_hello():
    assert "hi" == more_hello()
```

运行测试：

![](img/b474a0e6453db60c238a6d55d6be3b12_46.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_48.png)

```bash
# 使用Makefile中定义的test任务
make test
```

![](img/b474a0e6453db60c238a6d55d6be3b12_50.png)

如果测试失败，Pytest会提供清晰的错误报告，指出期望值和实际值。

![](img/b474a0e6453db60c238a6d55d6be3b12_52.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_54.png)

### 集成代码质量工具

除了测试，集成代码格式化和检查工具也是最佳实践。

*   **代码检查**：使用 `pylint` 或 `flake8` 检查代码风格和潜在错误。
*   **代码格式化**：使用 `black` 自动格式化代码，保持团队代码风格一致。

```bash
# 运行代码检查
make lint

![](img/b474a0e6453db60c238a6d55d6be3b12_56.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_58.png)

# 运行代码格式化
make format

# 运行所有任务：安装、检查、测试、格式化
make all
```

在提交代码前运行 `make all` 可以确保代码质量。

### 固定依赖版本

使用 `pip freeze` 可以生成当前环境中所有包的确切版本列表，将其写入 `requirements.txt` 可以确保环境的一致性。

```bash
pip freeze | grep -E "pytest|pytest-cov|pylint|black|ipython" > requirements.txt
```

## 第二部分：配置持续集成

上一节我们搭建了本地环境并编写了测试，本节中我们来看看如何配置持续集成系统，确保代码在任何地方都能正常工作。

![](img/b474a0e6453db60c238a6d55d6be3b12_60.png)

持续集成系统的核心是构建流水线，它作为代码质量的守门员，在代码合并或部署前自动运行测试。

![](img/b474a0e6453db60c238a6d55d6be3b12_62.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_63.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_64.png)

### 使用GitHub Actions

![](img/b474a0e6453db60c238a6d55d6be3b12_66.png)

GitHub Actions是一个与GitHub深度集成的CI/CD平台。我们可以在项目根目录创建 `.github/workflows/` 目录，并在其中添加YAML配置文件。

![](img/b474a0e6453db60c238a6d55d6be3b12_68.png)

以下是一个基础的GitHub Actions工作流配置示例，它在代码推送时触发，运行与本地相同的测试任务：

![](img/b474a0e6453db60c238a6d55d6be3b12_70.png)

```yaml
name: Python application test with Github Actions

![](img/b474a0e6453db60c238a6d55d6be3b12_72.png)

on: [push]

![](img/b474a0e6453db60c238a6d55d6be3b12_74.png)

jobs:
  build:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        python-version: ["3.7", "3.8", "3.9"]

    steps:
    - uses: actions/checkout@v2
    - name: Set up Python ${{ matrix.python-version }}
      uses: actions/setup-python@v2
      with:
        python-version: ${{ matrix.python-version }}
    - name: Install dependencies
      run: make install
    - name: Lint with pylint
      run: make lint
    - name: Test with pytest
      run: make test
    - name: Format code with black
      run: make format
```

这个配置的关键点包括：
*   **矩阵测试**：可以同时测试多个Python版本，确保代码兼容性。
*   **复用Makefile**：CI流水线中的步骤直接调用本地定义的 `make` 命令，保持了配置的一致性。

![](img/b474a0e6453db60c238a6d55d6be3b12_76.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_78.png)

### 添加测试覆盖率报告

![](img/b474a0e6453db60c238a6d55d6be3b12_80.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_82.png)

使用 `pytest-cov` 可以生成测试覆盖率报告。在 `Makefile` 的 `test` 任务中添加覆盖率参数：

![](img/b474a0e6453db60c238a6d55d6be3b12_84.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_85.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_87.png)

```makefile
test:
    python -m pytest -vvs --cov=hello --cov=greeting --cov-report=term-missing
```

![](img/b474a0e6453db60c238a6d55d6be3b12_89.png)

### 获取状态徽章

![](img/b474a0e6453db60c238a6d55d6be3b12_91.png)

GitHub Actions可以为项目生成状态徽章，显示构建状态。将其添加到 `README.md` 文件中，可以直观展示项目的健康度。

### 在其他云环境中验证

![](img/b474a0e6453db60c238a6d55d6be3b12_93.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_95.png)

持续集成的目标是确保代码在任何新环境中都能轻松运行。我们可以在AWS CloudShell或Cloud9等云环境中快速验证。

![](img/b474a0e6453db60c238a6d55d6be3b12_97.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_99.png)

```bash
# 克隆代码仓库
git clone <repository-url>
cd <project-directory>

![](img/b474a0e6453db60c238a6d55d6be3b12_101.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_103.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_105.png)

# 运行完整测试流程
make all
```

![](img/b474a0e6453db60c238a6d55d6be3b12_107.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_109.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_111.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_113.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_115.png)

如果一切配置正确，新环境的搭建和测试验证将变得非常简单，这对于团队新成员快速上手至关重要。

![](img/b474a0e6453db60c238a6d55d6be3b12_117.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_119.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_121.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_123.png)

### 使用AWS CodeBuild

![](img/b474a0e6453db60c238a6d55d6be3b12_125.png)

如果你的公司使用AWS，AWS CodeBuild是一个与AWS服务深度集成的替代CI/CD方案。配置逻辑与GitHub Actions类似。

在项目根目录创建 `buildspec.yml` 文件：

![](img/b474a0e6453db60c238a6d55d6be3b12_127.png)

```yaml
version: 0.2

![](img/b474a0e6453db60c238a6d55d6be3b12_129.png)

phases:
  install:
    commands:
      - make install
  build:
    commands:
      - make lint
      - make test
      - make format
```

![](img/b474a0e6453db60c238a6d55d6be3b12_131.png)

在AWS CodeBuild控制台创建构建项目，并链接到GitHub仓库。CodeBuild的优势在于可以轻松集成S3、EFS等其他AWS服务。

![](img/b474a0e6453db60c238a6d55d6be3b12_133.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_135.png)

## 第三部分：Pytest高级功能与真实项目测试

![](img/b474a0e6453db60c238a6d55d6be3b12_137.png)

上一节我们配置了CI/CD流水线，本节中我们将深入Pytest的高级功能，并测试一个更真实的项目，该项目包含库、Web服务和命令行工具。

### 测试Jupyter Notebook

![](img/b474a0e6453db60c238a6d55d6be3b12_139.png)

数据科学和工程团队经常使用Jupyter Notebook。可以使用 `nbval` 工具来测试Notebook。

![](img/b474a0e6453db60c238a6d55d6be3b12_141.png)

首先，将Notebook保存到GitHub仓库。然后安装 `nbval` 并添加到 `requirements.txt`。

```bash
pip install nbval
```

在 `Makefile` 中添加测试Notebook的任务：

![](img/b474a0e6453db60c238a6d55d6be3b12_143.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_145.png)

```makefile
test-notebook:
    python -m pytest --nbval notebook.ipynb
```

`nbval` 会执行Notebook中的所有单元格，并像普通Pytest测试一样进行断言验证。

![](img/b474a0e6453db60c238a6d55d6be3b12_147.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_149.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_151.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_153.png)

### 使用PDB进行调试

![](img/b474a0e6453db60c238a6d55d6be3b12_155.png)

PDB是Python的内置调试器。可以在代码中插入断点进行交互式调试。

![](img/b474a0e6453db60c238a6d55d6be3b12_157.png)

在代码中添加以下行来启动PDB：

```python
import pdb; pdb.set_trace()
```

当代码执行到这一行时，会进入PDB调试会话。你也可以在运行Pytest时使用 `--pdb` 标志，在测试失败时自动进入PDB：

```bash
python -m pytest --pdb
```

![](img/b474a0e6453db60c238a6d55d6be3b12_159.png)

为了方便，可以在 `Makefile` 中创建一个调试任务：

![](img/b474a0e6453db60c238a6d55d6be3b12_161.png)

```makefile
debug:
    python -m pytest -vvs --pdb
```

![](img/b474a0e6453db60c238a6d55d6be3b12_163.png)

### 测试选择与过滤

![](img/b474a0e6453db60c238a6d55d6be3b12_165.png)

在大型项目中，可能只需要运行特定的测试。Pytest提供了多种方式来选择要运行的测试。

*   **运行单个测试模块**：`pytest test_hello.py`
*   **运行单个测试函数**：`pytest test_hello.py::test_more_hello`
*   **运行某个目录下的所有测试**：`pytest tests/`

![](img/b474a0e6453db60c238a6d55d6be3b12_167.png)

在 `Makefile` 中可以为常用场景创建快捷命令。

![](img/b474a0e6453db60c238a6d55d6be3b12_169.png)

### 使用Fixture

Fixture是Pytest的一个强大功能，用于提供测试所需的固定环境或数据。它可以实现测试的setup和teardown逻辑。

以下是一个Fixture示例，它为一个简单的“姓名”函数提供测试数据：

```python
import pytest

@pytest.fixture
def name_bob():
    return "Bob"

@pytest.fixture
def name_sally():
    return "Sally"

![](img/b474a0e6453db60c238a6d55d6be3b12_171.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_173.png)

def test_my_name_bob(name_bob):
    from greeting import my_name
    assert f"My name is {name_bob}" == my_name(name_bob)

def test_my_name_sally(name_sally):
    from greeting import my_name
    assert f"My name is {name_sally}" == my_name(name_sally)
```

![](img/b474a0e6453db60c238a6d55d6be3b12_175.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_177.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_179.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_181.png)

Fixture使测试代码更清晰、更易于维护，并且可以复用。

![](img/b474a0e6453db60c238a6d55d6be3b12_183.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_185.png)

### 测试Flask Web应用

对于Web服务，我们可以使用Pytest来测试Flask应用。关键是为测试创建一个Flask应用实例和测试客户端。

首先，创建一个简单的Flask应用 `web.py`：

```python
from flask import Flask, jsonify
from mylib.m_change import change

![](img/b474a0e6453db60c238a6d55d6be3b12_187.png)

app = Flask(__name__)

![](img/b474a0e6453db60c238a6d55d6be3b12_189.png)

@app.route('/')
def index():
    return jsonify({"hello": "Bob"})

@app.route('/change/<dollars>/<cents>')
def get_change(dollars, cents):
    amount = float(f"{dollars}.{cents}")
    return jsonify(change(amount))

if __name__ == "__main__":
    app.run(debug=True, port=8080)
```

![](img/b474a0e6453db60c238a6d55d6be3b12_191.png)

然后，创建对应的测试文件 `test_web.py`，使用Fixture来设置应用和客户端：

![](img/b474a0e6453db60c238a6d55d6be3b12_193.png)

```python
import pytest
import json
from web import app as flask_app

@pytest.fixture
def app():
    yield flask_app

@pytest.fixture
def client(app):
    return app.test_client()

def test_index(client):
    result = client.get('/')
    assert result.status_code == 200
    expected = {"hello": "Bob"}
    assert expected == json.loads(result.get_data(as_text=True))

def test_change(client):
    result = client.get('/change/1/34')
    assert result.status_code == 200
    # 根据change函数的实际返回值进行断言
    # 例如：assert 5 in json.loads(result.get_data(as_text=True)).values()
```

### 测试Click命令行工具

对于命令行工具，我们可以使用Click自带的测试工具 `CliRunner`。

![](img/b474a0e6453db60c238a6d55d6be3b12_195.png)

首先，创建一个命令行工具 `cli.py`：

![](img/b474a0e6453db60c238a6d55d6be3b12_197.png)

```python
#!/usr/bin/env python
import click
from mylib.m_change import change

![](img/b474a0e6453db60c238a6d55d6be3b12_199.png)

@click.command()
@click.option('--amount', prompt='Amount', help='Amount for change calculation.')
def make_change(amount):
    """Gives correct change in coins."""
    result = change(float(amount))
    click.echo(click.style(f"Change for ${amount}:", fg='red'))
    for coin, number in result.items():
        click.echo(click.style(f"{number} {coin}", fg='green'))

![](img/b474a0e6453db60c238a6d55d6be3b12_201.png)

if __name__ == '__main__':
    make_change()
```

![](img/b474a0e6453db60c238a6d55d6be3b12_203.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_205.png)

然后，创建测试文件 `test_cli.py`：

```python
import pytest
from click.testing import CliRunner
from cli import make_change

@pytest.fixture
def runner():
    return CliRunner()

def test_cli_help(runner):
    result = runner.invoke(make_change, ['--help'])
    assert result.exit_code == 0
    assert "Usage" in result.output

def test_cli_change(runner):
    result = runner.invoke(make_change, ['--amount', '1.34'])
    assert result.exit_code == 0
    # 断言输出中包含预期的内容，例如硬币数量
    assert "5" in result.output  # 示例断言
```

### 重构与代码组织

随着项目增长，良好的代码组织至关重要。将通用逻辑提取到独立的库中（例如 `mylib/`），然后在Web服务和命令行工具中复用，可以使代码更清晰、更易于测试。

## 总结

![](img/b474a0e6453db60c238a6d55d6be3b12_207.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_209.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_211.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_213.png)

![](img/b474a0e6453db60c238a6d55d6be3b12_215.png)

在本节课中，我们一起学习了如何从零开始构建一个具备完整测试能力的Python项目。我们从搭建本地开发环境开始，使用了云开发平台和虚拟环境。然后，我们配置了持续集成系统，包括GitHub Actions和AWS CodeBuild，实现了自动化测试和矩阵测试。接着，我们深入探索了Pytest的高级功能，如Fixture、调试和测试选择。最后，我们将所学应用于一个真实的项目，成功测试了Python库、Flask Web应用和Click命令行工具，并建立了完整的CI/CD流水线。

![](img/b474a0e6453db60c238a6d55d6be3b12_217.png)

通过掌握这些技能，你可以在新的工作环境中快速搭建起高效、可靠的开发和部署流程，确保代码质量并加速团队协作。