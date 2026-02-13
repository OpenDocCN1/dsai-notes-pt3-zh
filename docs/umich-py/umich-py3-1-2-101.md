# 101：CSV文件读取 📖

![](img/579310cf91ae431b040bec9a6711156b_0.png)

![](img/579310cf91ae431b040bec9a6711156b_1.png)

在本节课中，我们将要学习如何读取和处理CSV（逗号分隔值）格式的文件。我们将了解CSV文件的基本结构，并学习使用Python的字符串分割方法来解析简单的CSV数据。

---

## 概述

CSV是一种常见的文件格式，用于存储表格数据。由于CSV本质上是一种特定格式的文本文件，我们可以像读取普通文本文件一样读取它。事实上，我们之前已经读取过CSV格式的文件（例如奥运会数据文件）。了解文件是CSV格式的优势在于，我们可以轻松地解析它，通过寻找逗号的位置将每一行分割成独立的组成部分。

## 读取与解析简单CSV文件

上一节我们介绍了CSV文件的基本概念。本节中我们来看看如何用代码读取并解析一个简单的CSV文件。

请看以下示例代码。第1至4行展示了文件的内容。第一行是表头，随后的每一行都包含由逗号分隔的个人姓名和其他值。

```python
# 示例：文件内容
# name,sex,age,country,sport,event,medal
# A Lemusia,M,23,China,Judo,NA
# B Johnson,M,28,USA,Swimming,Gold
```

以下是如何使用 `.split()` 方法处理这些内容。在第6行代码中，我们处理表头行。

```python
header_line = "name,sex,age,country,sport,event,medal"
# 首先，去掉行尾的换行符，然后在逗号处分割
fields = header_line.rstrip().split(',')
print(fields)  # 输出: ['name', 'sex', 'age', 'country', 'sport', 'event', 'medal']
```

`.split()` 方法将文本在指定字符（此处为逗号）处分割，并返回一个列表。对于表头行，我们得到了包含各个字段名的列表。

对于文件中的其他数据行，我们采用类似的方法。我们循环遍历所有行，对每一行在逗号处进行分割。

```python
data_line = "A Lemusia,M,23,China,Judo,NA"
values = data_line.split(',')
print(values)  # 输出: ['A Lemusia', 'M', '23', 'China', 'Judo', 'NA']
```

将一行（如 `A Lemusia,M,23,China,Judo,NA`）分割成列表后，我们就可以使用索引来访问特定值。例如，我们可以检查索引5（即第六个元素）的值是否为“NA”。

```python
if values[5] == 'NA':
    print("No medal won.")
else:
    print(f"Name: {values[0]}, Event: {values[4]}, Medal: {values[5]}")
```

这样，我们可以只打印出实际获得奖牌的运动员信息，跳过未获奖牌的行。在输出中，我们选择打印该行的三个元素：姓名（索引0）、项目（索引4）和奖牌（索引5）。

## 关键点：指定分割字符

必须注意，我们需要在逗号上进行分割。之前我们使用 `.split()` 命令时，往往不指定参数。当不指定参数时，它会在任何空白字符（空格、制表符、换行符）处进行分割。

如果对CSV行使用默认的 `.split()`：

```python
result = data_line.split()
print(result)  # 输出: ['A', 'Lemusia,M,23,China,Judo,NA']
```

我们得到的列表只有一个元素，即整个字符串。因为在整个字符串中没有空格，所以它没有被分割成多个部分。

`.split()` 方法会根据你指定的任何字符进行分割。对于CSV格式，我们需要指定逗号作为分割符，因为逗号分隔值格式规定，逗号是分隔不同值的符号。

## 处理更复杂的CSV格式

有时会遇到更高级的CSV格式，它虽然也用逗号分隔，但会用引号将每个值括起来。例如：

```
"name","sex","age","country","sport","event","medal"
"A Lemusia","M","23","China","Judo","NA",""
"B Johnson","M","28","USA","Swimming","100m Freestyle","Gold"
```

当某些值本身包含逗号时（例如“Speed Skating, 1500m”），这种格式就变得必要。如果像之前一样简单地按逗号分割，解析就会出错，因为我们无法区分逗号是值的一部分还是分隔符。

```python
complex_line = '"Speed Skating, 1500m","M","25","Netherlands"'
wrong_split = complex_line.split(',')
print(wrong_split)
# 错误输出: ['"Speed Skating', ' 1500m"', '"M"', '"25"', '"Netherlands"']
```

解析这种带引号的、更高级的逗号分隔值格式虽然仍有可能，但编程挑战更大。不建议自己尝试实现复杂的解析逻辑。

相反，当你遇到这种格式时，应该使用Python内置的 `csv` 模块来为你解析行。这个模块能正确处理带引号和嵌入逗号的字段。我们目前暂不学习这个模块。现阶段，为了理解底层原理，学习使用 `.split()` 方法解析简单的CSV是有益的。之后，你可以再学习使用 `csv` 模块处理更复杂的格式。

## 总结

本节课中我们一起学习了CSV文件的读取。
*   对于简单的CSV格式（使用逗号分隔且值周围没有引号），解析很容易。
*   你只需一次读取文件的一行，并使用指定逗号作为分隔符的 `.split()` 方法。
*   这为你提供了各个值的列表，或者表头行的各个字段名列表。
*   对于更复杂的、带引号的CSV格式，建议使用Python的 `csv` 模块进行解析。

我们下次再见。