# IBM 生成式人工智能工程 Flask 笔记：1：Flask 基础入门

在本节课中，我们将要学习 Flask 框架的基础知识，包括其核心概念、基本结构以及如何运行一个最简单的 Web 应用。

Flask 是一个使用 Python 编写的轻量级 Web 应用框架。它被称为“微框架”，因为它核心简单，但可以通过扩展增加功能。Flask 基于 Werkzeug WSGI 工具包和 Jinja2 模板引擎。

## 核心概念与安装

上一节我们介绍了 Flask 的基本定义，本节中我们来看看如何开始使用它。

首先，你需要安装 Flask。可以通过 Python 的包管理工具 pip 来完成安装。

```bash
pip install Flask
```

安装完成后，你可以通过导入 `Flask` 类来开始构建应用。一个 Flask 应用的核心是创建 `Flask` 类的一个实例。

```python
from flask import Flask
app = Flask(__name__)
```

这里的 `__name__` 是一个 Python 特殊变量，它表示当前模块的名称。Flask 使用它来确定应用的根路径。

## 定义路由与视图函数

在 Flask 中，客户端（例如浏览器）发送的请求需要被映射到特定的 Python 函数来处理，这个映射过程通过**路由**来实现。

路由使用 `@app.route()` 装饰器来定义。装饰器下方的函数被称为**视图函数**，它负责处理请求并返回响应。

以下是一个定义路由的示例：

```python
@app.route('/')
def home():
    return 'Hello, World!'
```

这段代码意味着，当用户访问网站的根路径（`/`）时，Flask 将调用 `home()` 函数，并将该函数返回的字符串 `'Hello, World!'` 发送给用户的浏览器。

## 运行 Flask 应用

定义了路由之后，我们需要让应用运行起来。Flask 内置了一个用于开发的服务器。

在脚本末尾添加以下代码即可运行应用：

```python
if __name__ == '__main__':
    app.run(debug=True)
```

`app.run(debug=True)` 启动了开发服务器。设置 `debug=True` 可以在代码修改后自动重启服务器，并在出错时提供调试信息。

将以上所有代码整合，一个完整的、最简单的 Flask 应用如下所示：

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(debug=True)
```

将代码保存为 `app.py`，然后在终端执行 `python app.py`。打开浏览器访问 `http://127.0.0.1:5000/`，你将看到 “Hello, World!” 的页面。

## 总结

本节课中我们一起学习了 Flask 框架的入门知识。我们了解了 Flask 是一个轻量级的 Web 框架，学会了如何安装 Flask，并掌握了创建 Flask 应用实例、使用 `@app.route()` 装饰器定义路由和视图函数，以及运行开发服务器的基本步骤。这是构建所有 Flask Web 应用的起点。