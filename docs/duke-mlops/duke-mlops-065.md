# 65：课程回顾-处理数据框 📊

在本节课中，我们将回顾使用Pandas数据框进行数据处理的核心操作。我们将学习如何创建新列、筛选行、进行文本操作与替换，并最终将处理结果可视化。这些技能是进行更高级数据分析的坚实基础。

---

上一节我们介绍了数据框的基本概念，本节中我们来看看一些更具体的操作。

![](img/ec1b3dfb40fba289fd79b323c90844fb_1.png)

## 创建新列

在数据分析中，经常需要基于现有数据计算并生成新的数据列。这可以通过直接赋值给一个新列名来实现。

以下是创建新列的常用方法：

*   **直接赋值**：`df['new_column'] = df['existing_column'] * 2`
*   **使用`apply`函数**：`df['new_column'] = df['existing_column'].apply(lambda x: x**2)`
*   **使用向量化操作**：`df['new_column'] = df['col1'] + df['col2']`

## 提取与筛选行

从数据框中提取特定行是数据清洗和探索性分析的关键步骤。我们可以根据条件来筛选出需要的数据子集。

以下是提取行的主要方式：

*   **布尔索引**：`df[df['column'] > 50]`
*   **使用`loc`和`iloc`**：`df.loc[df['column'] == 'value']` 或 `df.iloc[0:5]`
*   **多重条件筛选**：`df[(df['col1'] > 10) & (df['col2'] == 'A')]`

## 文本操作与替换

处理文本数据时，Pandas提供了强大的字符串方法来执行清洗和转换。这些操作通常作用于`Series`对象的`str`属性上。

以下是常见的文本操作：

*   **字符串方法**：`df['text_column'].str.lower()`， `df['text_column'].str.contains('pattern')`
*   **替换文本**：`df['column'].replace('old_value', 'new_value', inplace=True)`
*   **分割字符串**：`df['column'].str.split(' ', expand=True)`

## 数据可视化

将数据处理结果可视化，能帮助我们更直观地理解数据模式和洞察。Pandas集成了Matplotlib，可以方便地绘制基本图表。

以下是简单的可视化示例：

*   **绘制折线图**：`df['column'].plot()`
*   **绘制柱状图**：`df['column'].value_counts().plot(kind='bar')`
*   **绘制直方图**：`df['numeric_column'].plot(kind='hist', bins=30)`

![](img/ec1b3dfb40fba289fd79b323c90844fb_3.png)

---

本节课中我们一起学习了Pandas数据框的几个核心操作：创建新列、筛选行、进行文本处理与替换，以及基础的数据可视化。这些技能构成了数据处理工作流的重要部分，为你后续进行更复杂的机器学习数据准备打下了坚实的基础。