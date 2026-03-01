# 数据工程基础：2-4：Python脚本与SQL入门 🐍💾

在本节课中，我们将学习如何结合使用Python脚本技术与SQL。具体内容包括：创建一个数据库、存储数据，以及从Python中执行SQL来查询这些数据。我们将使用小巧但功能强大的SQLite数据库，并通过Python与其建立连接。最后，我们将介绍一些关键的SQL语句和命令，以便高效地从数据库中筛选和提取数据。

---

## 使用Python连接SQLite数据库

上一节我们概述了课程目标，本节中我们来看看如何从Python连接到SQLite数据库。SQLite是一个轻量级的数据库引擎，非常适合学习和原型开发。Python标准库中的 `sqlite3` 模块提供了与SQLite数据库交互的接口。

以下是建立数据库连接并创建一个游标对象的基本步骤：

```python
import sqlite3

![](img/e99b3406bea788e8c878c2decb8fb789_0.png)

# 连接到数据库（如果不存在则会自动创建）
connection = sqlite3.connect('my_database.db')

# 创建一个游标对象，用于执行SQL语句
cursor = connection.cursor()
```

---

![](img/e99b3406bea788e8c878c2decb8fb789_1.png)

## 创建表与插入数据

成功连接数据库后，下一步是创建表结构并向其中插入数据。表是数据库中存储数据的基本单元，类似于Excel中的一个工作表。

以下是创建表和插入数据的示例：

```python
# 创建一个名为‘users’的表
create_table_sql = """
CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    age INTEGER
);
"""
cursor.execute(create_table_sql)

# 向‘users’表中插入一行数据
insert_sql = "INSERT INTO users (name, age) VALUES (?, ?)"
cursor.execute(insert_sql, ('Alice', 30))

# 提交更改，使插入操作生效
connection.commit()
```

---

## 使用SQL查询数据

表中有数据后，我们就可以使用SQL查询语句来检索信息。SQL的 `SELECT` 语句是用于从数据库获取数据的主要工具。

以下是一些基本的查询示例：

```python
# 查询‘users’表中的所有数据
cursor.execute("SELECT * FROM users")
all_users = cursor.fetchall()
print(all_users)

# 查询特定条件的数据，例如年龄大于25的用户
cursor.execute("SELECT * FROM users WHERE age > ?", (25,))
users_over_25 = cursor.fetchall()
print(users_over_25)
```

---

## 核心SQL语句与命令

为了更高效地操作数据库，我们需要掌握几个核心的SQL命令。这些命令构成了与数据库交互的基础。

以下是几个必备的SQL语句：

1.  **`CREATE TABLE`**：用于创建新表。
    ```sql
    CREATE TABLE table_name (column1 datatype, column2 datatype, ...);
    ```

2.  **`INSERT INTO`**：用于向表中插入新行。
    ```sql
    INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);
    ```

3.  **`SELECT`**：用于从表中查询数据。
    ```sql
    SELECT column1, column2 FROM table_name WHERE condition;
    ```

4.  **`UPDATE`**：用于修改表中现有的记录。
    ```sql
    UPDATE table_name SET column1 = value1 WHERE condition;
    ```

5.  **`DELETE`**：用于从表中删除记录。
    ```sql
    DELETE FROM table_name WHERE condition;
    ```

---

## 关闭数据库连接

完成所有数据库操作后，务必正确关闭连接。这是一个重要的好习惯，可以确保所有数据被正确保存并释放资源。

关闭连接的代码如下：

![](img/e99b3406bea788e8c878c2decb8fb789_3.png)

```python
# 关闭游标和数据库连接
cursor.close()
connection.close()
```

---

本节课中我们一起学习了如何使用Python脚本操作SQLite数据库。我们从建立连接开始，逐步完成了创建表、插入数据、执行查询等核心操作，并介绍了关键的SQL语句。最后，我们强调了在操作完成后关闭连接的重要性。掌握这些基础技能，是迈向更复杂数据工程任务的重要一步。