#  028：Pandas与替代方案介绍 🐼📊

![](img/d04c56ad8c8a86dda216ae033a060fbf_0.png)

在本节课中，我们将学习功能强大且流行的Pandas库。我们将了解如何创建Pandas的DataFrame，编写语句从DataFrame中选择列和行，应用比较和布尔运算符作为筛选数据的方法，以及何时使用Pandas DataFrame的替代方案。

让我们开始吧。



![](img/d04c56ad8c8a86dda216ae033a060fbf_2.png)

## 创建Pandas DataFrame 🏗️

上一节我们概述了本节课的内容，本节中我们来看看如何创建Pandas的核心数据结构——DataFrame。

DataFrame是一个二维的、大小可变的、具有潜在异构列的表格型数据结构。你可以把它想象成一个Excel表格或SQL表。

以下是创建DataFrame的几种常见方法：

![](img/d04c56ad8c8a86dda216ae033a060fbf_0.png)

*   **从字典创建**：字典的键将成为列名，值将成为列数据。
    ```python
    import pandas as pd
    data = {'Name': ['Alice', 'Bob', 'Charlie'],
            'Age': [25, 30, 35],
            'City': ['New York', 'London', 'Tokyo']}
    df = pd.DataFrame(data)
    ```
*   **从列表的列表创建**：需要单独指定列名。
    ```python
    data = [['Alice', 25, 'New York'],
            ['Bob', 30, 'London'],
            ['Charlie', 35, 'Tokyo']]
    df = pd.DataFrame(data, columns=['Name', 'Age', 'City'])
    ```
*   **从文件读取**：Pandas可以轻松读取CSV、Excel等格式文件。
    ```python
    df = pd.read_csv('data.csv')
    ```

## 选择列和行 🔍

现在我们已经有了一个DataFrame，接下来学习如何从中提取特定的数据部分，即选择列和行。

选择数据是数据分析中最常见的操作之一。

### 选择列

选择单列会返回一个Series（可以看作一维数组），选择多列则返回一个新的DataFrame。

以下是选择列的方法：

*   **使用方括号 `[]` 选择单列**：`df[‘column_name’]`
*   **使用方括号 `[]` 选择多列**：`df[[‘col1’， ‘col2’]]`
*   **使用点号 `.` 访问属性（仅限列名是有效的Python标识符时）**：`df.column_name`

### 选择行

选择行通常基于索引位置或条件筛选。

以下是选择行的方法：

*   **使用 `.iloc[]` 按整数位置选择**：`df.iloc[0]` 选择第一行。
*   **使用 `.loc[]` 按索引标签选择**：如果索引是自定义标签，使用此方法。
*   **使用切片选择多行**：`df[0:2]` 选择前两行。

## 应用比较与布尔运算符筛选 🎯

上一节我们介绍了如何通过位置选择行，但更强大的方式是通过条件进行筛选。本节中我们来看看如何应用比较和布尔运算符来精确选择数据。

你可以通过将比较操作（如 `>`， `==`， `!=`）应用于列，生成一个布尔值（True/False）序列（称为布尔掩码），然后用这个掩码来筛选DataFrame。

以下是使用布尔运算符筛选的步骤：

1.  **创建条件**：例如，`df[‘Age’] > 30` 会生成一个布尔Series。
2.  **应用条件**：将布尔Series放入方括号中对DataFrame进行筛选。`df[df[‘Age’] > 30]`
3.  **组合多个条件**：使用 `&` (与)、`|` (或)、`~` (非) 运算符，每个条件需用括号括起来。例如，`df[(df[‘Age’] > 25) & (df[‘City’] == ‘London’)]`

## Pandas的替代方案 ⚖️

虽然Pandas是Python数据分析的事实标准，但在某些场景下，其他工具可能更合适。本节中我们来看看何时应考虑使用Pandas DataFrame的替代方案。

了解替代方案有助于你为特定任务选择最佳工具。

以下是需要考虑替代方案的几种情况及其对应工具：

*   **处理超大规模数据集（超出内存容量）**：可以考虑 **Dask** 或 **Vaex**。它们提供了类似Pandas的API，但能进行并行计算或惰性计算，处理比内存大的数据。
*   **需要极高的单机性能**：可以考虑 **Polars**。这是一个用Rust编写的新库，其查询引擎经过高度优化，速度通常远超Pandas。
*   **与大数据生态系统集成（如Spark）**：**PySpark** 的DataFrame是分布式计算环境下的标准选择。
*   **进行交互式数据分析与可视化**：**Pandas** 本身很强大，但结合 **Jupyter Notebook** 和可视化库（如Matplotlib， Seaborn）是常见工作流。对于更丰富的交互式可视化，可以考虑 **Plotly** 或 **Tableau** 等专业工具。

## 总结 📝

![](img/d04c56ad8c8a86dda216ae033a060fbf_2.png)

本节课中我们一起学习了Python数据处理的核心库Pandas。

我们首先介绍了如何创建DataFrame。接着，我们学习了从DataFrame中选择特定列和行的多种方法。然后，我们探讨了如何使用比较和布尔运算符进行条件筛选，这是数据清洗和分析中的关键技能。最后，我们讨论了Pandas的适用场景及其主要替代方案，例如在处理海量数据、追求极致性能或需要分布式计算时，可以考虑Dask、Polars或PySpark等工具。

掌握这些基础将为你后续进行更复杂的数据工程和数据分析任务打下坚实的基础。