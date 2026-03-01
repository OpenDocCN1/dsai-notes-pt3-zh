# Python、Bash和SQL数据工程基础：2-4：Python中使用SQL查询入门 🐍

在本节课中，我们将学习如何在Python中执行基本的SQL查询。我们将从连接到数据库开始，然后学习如何运行查询、提取数据，并在Python端处理这些数据。课程还将探讨何时使用SQL语句更高效，以及何时在Python中进行处理更具可读性和可维护性。最后，我们会介绍SQL中的通配符搜索，以便根据已知的数据属性来提取匹配的信息。

![](img/c1aaab14698f492200215f18400c9a6f_0.png)

## 连接到数据库与执行查询

![](img/c1aaab14698f492200215f18400c9a6f_1.png)

上一节我们介绍了数据库连接的基础。本节中，我们来看看如何执行基本的SQL查询并提取数据。

连接到数据库后，你可以执行查询来提取所需的数据。以下是一个基本步骤示例：

```python
import sqlite3

# 连接到数据库（示例中使用SQLite）
connection = sqlite3.connect('example.db')
cursor = connection.cursor()

# 执行一个简单的SELECT查询
cursor.execute("SELECT * FROM users")
results = cursor.fetchall()

for row in results:
    print(row)

# 关闭连接
cursor.close()
connection.close()
```

## SQL查询与Python处理的权衡

有时查询会变得非常复杂。你需要学习在何时以及如何使用SQL或Python处理数据。

这主要归结为效率与可维护性之间的权衡。使用**SQL语句**通常效率更高，但代码的可读性和可维护性可能会稍差。其效率优势可以用一个简单的公式来理解：**数据库处理量 ≈ 数据量 × 查询复杂度**。在数据库服务器上执行复杂过滤和聚合，通常比将大量数据拉取到Python中处理要快得多。

另一方面，在**Python中进行处理**可能速度较慢，但后续的维护和过滤操作会容易得多。例如，如果你需要对结果进行复杂的、动态的逻辑判断，Python可能更灵活。

## 使用SQL通配符进行搜索

最后，我们将了解如何执行搜索，以及SQL中可用的通配符，以便提取与我们已知数据属性相匹配的数据。

SQL提供了`LIKE`操作符和通配符（如`%`和`_`）来进行模式匹配。以下是通配符的用法：

- `%`：匹配任意数量的字符（包括零个字符）。
- `_`：匹配单个字符。

以下是一个使用通配符进行搜索的示例：

```python
# 假设我们要查找名字以'J'开头的所有用户
cursor.execute("SELECT * FROM users WHERE name LIKE 'J%'")
j_names = cursor.fetchall()

# 查找名字第二个字母是'o'的所有用户
cursor.execute("SELECT * FROM users WHERE name LIKE '_o%'")
second_o_names = cursor.fetchall()
```

本节课中我们一起学习了在Python中执行SQL查询的基础。我们掌握了连接数据库、执行查询以及提取结果的方法。我们探讨了在复杂数据处理场景下，选择使用高效SQL语句与选择可维护性更强的Python代码之间的权衡。最后，我们介绍了如何使用SQL通配符进行灵活的数据搜索。理解这些核心概念，将帮助你在数据工程项目中更有效地操作数据库。