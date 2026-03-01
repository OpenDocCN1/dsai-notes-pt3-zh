# 数据工程基础：2-4：SQLite与Python回顾 🗂️

在本节课中，我们将回顾如何使用Python与SQLite数据库进行交互。我们将学习连接数据库、执行查询以及管理数据的基本操作。

![](img/d219e8ada351ee84cc25b855d16a52aa_0.png)

---

![](img/d219e8ada351ee84cc25b855d16a52aa_1.png)

上一节我们介绍了SQLite的基本概念，本节中我们来看看如何在实际的Python代码中运用这些知识。

SQLite是一个轻量级的嵌入式数据库，它不需要独立的服务器进程。这意味着你可以将整个数据库存储在一个单一的文件中。使用Python的`sqlite3`库，操作这些数据库变得非常简单直接。

我非常喜欢这种方式。它是我开始学习数据库、深入理解数据库的起点，因为我当时已经熟悉了Python。学习如何连接到一个新数据库、提取数据、添加更多数据并执行查询，让我在处理数据时成为了一个更出色的程序员。

SQLite是一个优秀的数据库，非常稳定且应用广泛。它几乎可以在任何地方轻松使用。如果某个系统没有预装SQLite，通常也能找到相应的软件包或安装程序。

现在，你已经准备好使用一个真正的数据库来更多地实践SQL和数据操作了。请注意，说它是“嵌入式”数据库并不意味着它不是“真正的”数据库。它是一个完全合规的数据库，你可以对其运行标准的SQL查询，它的行为与其他任何真正的数据库一样。

---

以下是使用Python操作SQLite的核心步骤：

1.  **导入库**：首先需要导入Python内置的`sqlite3`模块。
    ```python
    import sqlite3
    ```

2.  **连接数据库**：使用`connect()`函数连接到一个数据库文件。如果文件不存在，它会被自动创建。
    ```python
    conn = sqlite3.connect('example.db')
    ```

3.  **创建游标**：游标对象用于执行SQL语句并获取结果。
    ```python
    cursor = conn.cursor()
    ```

4.  **执行SQL命令**：使用游标的`execute()`方法运行SQL语句，例如创建表或插入数据。
    ```python
    cursor.execute('''CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, name TEXT)''')
    ```

5.  **提交更改**：对于修改数据库的操作（如INSERT, UPDATE, DELETE），需要调用连接对象的`commit()`方法来保存更改。
    ```python
    conn.commit()
    ```

6.  **查询数据**：使用`execute()`执行SELECT语句，然后通过`fetchall()`、`fetchone()`等方法获取结果。
    ```python
    cursor.execute("SELECT * FROM users")
    rows = cursor.fetchall()
    for row in rows:
        print(row)
    ```

7.  **关闭连接**：完成所有操作后，记得关闭数据库连接。
    ```python
    conn.close()
    ```

---

本节课中我们一起学习了如何利用Python的`sqlite3`库与SQLite数据库进行交互。我们回顾了从连接数据库、执行SQL命令到查询和提交数据的完整流程。SQLite作为一个强大而简单的工具，是初学者理解和实践数据库操作的绝佳起点。