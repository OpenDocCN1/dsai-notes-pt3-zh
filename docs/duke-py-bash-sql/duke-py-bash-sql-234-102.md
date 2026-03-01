#  102：使用Python进行网络爬虫入门 🕸️

在本节课中，我们将学习如何从互联网上高效地提取数据。你将了解如何使用爬虫库从网站读取数据，并从中识别和提取特定的信息。接着，我们将学习从HTML中定位和分离关键数据的技术。最后，我们会将解析后的数据使用SQL持久化存储到数据库中。

## 网络爬虫概述

网络爬虫是一种自动从万维网上收集信息的程序。它模拟人类浏览网页的行为，但以更快的速度和更大的规模进行。对于数据工程而言，爬虫是获取外部数据源的重要工具。

## 核心工具与库

要进行网络爬虫，我们需要借助一些Python库。以下是主要的工具：

*   **Requests库**：用于向网站发送HTTP请求并获取网页的HTML内容。其基本用法是 `requests.get(‘url’)`。
*   **Beautiful Soup库**：用于解析HTML和XML文档，并从中提取数据。它能将复杂的HTML文档转换成一个树形结构，便于我们导航和搜索。

![](img/b13544181383a1515ddc8def9caf7afc_0.png)

上一节我们介绍了爬虫的基本概念，本节中我们来看看如何实际获取网页内容。

## 获取网页内容

使用Requests库可以轻松地获取网页的原始数据。以下是基本步骤：

![](img/b13544181383a1515ddc8def9caf7afc_1.png)

1.  导入`requests`库。
2.  使用`get`方法向目标URL发送请求。
3.  检查响应状态码（如200表示成功）。
4.  通过`response.text`属性获取网页的HTML内容。

```python
import requests

url = ‘https://example.com‘
response = requests.get(url)

if response.status_code == 200:
    html_content = response.text
    print(html_content[:500]) # 打印前500个字符
else:
    print(‘Failed to retrieve the webpage‘)
```

成功获取HTML内容后，下一步就是从这些结构化文本中提取我们需要的信息。

## 解析与提取数据

Beautiful Soup库是解析HTML和提取数据的利器。它提供了简单的方法来搜索文档树。以下是使用Beautiful Soup的基本流程：

1.  使用Beautiful Soup解析获取到的HTML内容。
2.  利用其查找方法（如`find`, `find_all`）或CSS选择器（`select`）定位特定元素。
3.  从元素中获取文本、属性等信息。

```python
from bs4 import BeautifulSoup

# 假设html_content是上一步获取的HTML字符串
soup = BeautifulSoup(html_content, ‘html.parser‘)

# 查找所有的段落标签
all_paragraphs = soup.find_all(‘p‘)
for p in all_paragraphs:
    print(p.get_text())

# 使用CSS选择器查找特定class的元素
specific_elements = soup.select(‘.article-title‘)
for elem in specific_elements:
    print(elem.text)
```

我们已经学会了如何定位和提取数据，接下来需要将这些零散的数据点系统地保存起来。

## 数据持久化

将爬取的数据保存下来至关重要，通常我们会选择存入数据库以便后续分析。SQLite是一个轻量级的数据库，非常适合初学者和快速原型开发。以下是基本步骤：

1.  连接到SQLite数据库（或创建一个新库）。
2.  创建一个表来定义数据存储的结构。
3.  将解析后的数据插入到表中。
4.  提交更改并关闭连接。

```python
import sqlite3

# 连接到数据库（如果不存在则创建）
conn = sqlite3.connect(‘scraped_data.db‘)
cursor = conn.cursor()

# 创建表
cursor.execute(‘‘‘
CREATE TABLE IF NOT EXISTS articles (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    content TEXT
)
‘‘‘)

# 假设我们有一个提取好的数据列表 data_to_save
data_to_save = [(‘标题1‘, ‘内容1‘), (‘标题2‘, ‘内容2‘)]

# 插入数据
cursor.executemany(‘INSERT INTO articles (title, content) VALUES (?, ?)‘, data_to_save)

![](img/b13544181383a1515ddc8def9caf7afc_3.png)

# 提交并关闭
conn.commit()
conn.close()
```

## 总结

本节课中我们一起学习了网络爬虫的完整流程。我们从使用Requests库获取网页原始HTML开始，然后利用Beautiful Soup库解析文档并提取出有价值的结构化数据，最后通过sqlite3库将这些数据持久化存储到SQLite数据库中。掌握这些技能，你就能自动化地从互联网上收集所需的数据，为数据工程项目提供丰富的外部数据源。