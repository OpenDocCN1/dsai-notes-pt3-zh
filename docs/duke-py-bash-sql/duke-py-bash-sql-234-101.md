#  101：Python中SQL查询回顾 🐍

在本节课中，我们将回顾如何在Python环境中执行SQL查询，并理解在数据库端与Python端进行数据处理的性能权衡。

![](img/f101378fe65a83fc796c19f70862bf6c_0.png)

## 概述

![](img/f101378fe65a83fc796c19f70862bf6c_1.png)

上一节我们介绍了如何连接SQLite数据库。本节中，我们将回顾执行基本SQL查询的方法，并讨论在SQL查询与Python代码中进行数据处理的效率差异。

## SQL查询执行

以下是使用Python的`sqlite3`模块执行SQL查询的基本步骤。

1.  首先，需要导入`sqlite3`模块并连接到数据库文件。
    ```python
    import sqlite3
    connection = sqlite3.connect('example.db')
    ```

2.  接着，创建一个游标对象，它是执行SQL命令的主要接口。
    ```python
    cursor = connection.cursor()
    ```

3.  然后，使用游标的`.execute()`方法运行SQL查询语句。
    ```python
    cursor.execute("SELECT * FROM users WHERE age > 20")
    ```

4.  最后，获取查询结果并关闭连接。
    ```python
    results = cursor.fetchall()
    connection.close()
    ```

## 性能考量：SQL vs. Python

我们了解到，虽然数据处理可以在Python端完成，但这会带来性能成本。

*   **高效方式**：尽可能使用SQL语句在数据库端完成筛选、聚合等操作。例如，使用`WHERE`子句过滤数据比将所有数据取到Python中再过滤要快得多。
    ```sql
    -- 在数据库端高效过滤
    SELECT name, salary FROM employees WHERE department = 'Sales' AND salary > 50000;
    ```
*   **Python处理**：对于复杂的、难以用单一SQL表达的逻辑，可以在获取数据后在Python中进行处理。但这通常意味着需要传输更多数据，可能影响性能。

## 知识的扩展与应用

尽管本节课使用的是嵌入式数据库SQLite，但所学的SQL查询概念可以无缝应用到其他数据库系统，如PostgreSQL和MySQL。关键在于构建高效的SQL查询，并明智地决定在何处进行数据处理。

## 总结

本节课中我们一起学习了在Python中执行SQL查询的流程，并重点探讨了数据处理策略。核心要点是：**优先利用SQL查询在数据库内部完成数据操作以获得最佳性能**，同时保留在Python端进行必要后处理的灵活性。现在，你可以基于这些SQL知识，开始更高效地处理数据了。