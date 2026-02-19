# 40：查询树结构 (2/4) 🌳

在本节课中，我们将深入学习JSONiq语言的核心概念，特别是如何查询和处理树状结构数据。我们将从JSONiq的基本数据模型开始，逐步介绍导航、构造、过滤和聚合等操作。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_1.png)

---

### 概述：JSONiq的数据模型

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_3.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_5.png)

上一节我们介绍了大数据处理的基本框架。本节中，我们来看看JSONiq语言如何通过“序列”这一核心概念来处理数据。

JSONiq中最重要的概念是：**每一个表达式都接收一个序列（sequence）作为输入，并返回一个序列作为输出**。序列由零个或多个“项（item）”组成。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_7.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_8.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_10.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_11.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_12.png)

一个项可以是：
*   **原子值**：例如字符串、整数、布尔值。
*   **对象（Object）**：即JSON对象。
*   **数组（Array）**：即JSON数组。
*   **函数（Function）**：高阶函数（本课程不深入讨论）。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_14.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_16.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_17.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_19.png)

**关键点**：
*   包含单个项的序列（例如，`[“一个字符串”]`）与该单项本身（`“一个字符串”`）被视为等同。
*   序列总是扁平的，不会嵌套。例如，`[ [1, 2], [3, 4] ]` 会被自动扁平化为 `[1, 2, 3, 4]`。
*   空序列（`[]`）是有效的。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_21.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_22.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_23.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_25.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_27.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_28.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_29.png)

这种序列模型非常强大，因为它涵盖了从高度结构化到完全异构的各种数据形态：
*   一个由具有相同模式的对象组成的序列，等价于一个关系型数据库表。
*   一个由不同类型、不同结构项组成的序列，可以表示半结构化或非结构化数据。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_31.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_32.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_33.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_35.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_36.png)

---

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_38.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_40.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_42.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_43.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_45.png)

### 导航数据：点运算符和谓词

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_47.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_48.png)

理解了序列模型后，我们现在可以学习如何访问和查询数据。JSONiq的导航语法灵感来源于XPath和许多编程语言。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_50.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_51.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_52.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_53.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_54.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_55.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_56.png)

**读取JSON文件**：
使用 `json-doc` 函数读取标准的JSON文件（单个JSON值）。它返回一个包含单个项（该JSON值）的序列。
```jsoniq
json-doc(“file.json”)
```

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_58.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_60.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_62.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_63.png)

**点运算符导航**：
使用点（`.`）后接键名来访问对象内的值。
```jsoniq
json-doc(“file.json”).countries
```
这将导航到JSON对象中的 `countries` 键，返回其关联的值（可能是一个数组）。

**展开数组**：
使用方括号 `[]` 来“展开”一个数组，将其内容转换为序列中的多个项。
```jsoniq
json-doc(“file.json”).countries[]
```
现在，`countries` 数组中的每个对象都成为输出序列中的一个独立项。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_65.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_66.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_67.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_69.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_70.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_71.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_73.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_74.png)

**并行导航**：
即使序列中包含多个项，点运算符也能同时对每一项进行导航。
```jsoniq
json-doc(“file.json”).countries[].name
```
这会对序列中的每个国家对象执行 `.name` 操作，返回一个国家名字符串的序列。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_76.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_77.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_78.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_79.png)

---

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_81.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_82.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_83.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_84.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_86.png)

### 过滤数据：使用谓词

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_87.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_88.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_90.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_92.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_93.png)

我们经常需要根据条件筛选数据。在JSONiq中，这通过在方括号 `[]` 内放置一个布尔表达式（谓词）来实现。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_94.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_96.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_97.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_99.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_100.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_101.png)

**基本过滤**：
以下查询找出 `code` 等于 “CH” 的国家。
```jsoniq
json-doc(“file.json”).countries[][$$.code eq “CH”]
```
*   `$$` 是一个特殊变量，代表“上下文项”，即当前正在处理的序列中的项。在这个例子中，`$$` 会依次绑定到 `countries` 数组中的每一个国家对象。
*   `eq` 是JSONiq中的等于比较运算符。

**组合查询**：
你可以像搭积木一样组合这些操作。例如，先过滤，再导航：
```jsoniq
json-doc(“file.json”).countries[][$$.code eq “CH”].name
```
这将返回瑞士（Switzerland）的名字。

**关于方括号 `[]` 的说明**：
方括号内的表达式根据其计算结果类型有不同的行为：
*   **布尔值**：用作过滤谓词。保留使表达式为 `true` 的项。
*   **整数**：用作位置索引。返回序列中该位置的项（索引从1开始）。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_103.png)

---

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_105.png)

### 处理JSON Lines文件

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_107.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_108.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_109.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_111.png)

对于每行一个JSON值的文件（JSON Lines），使用 `json` 函数（注意不是 `json-doc`）。
```jsoniq
json(“file.jsonl”)
```
这将返回一个序列，其中每一行JSON都是一个独立的项。之后的所有导航和过滤操作与处理单个JSON文件时完全相同。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_113.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_114.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_115.png)

---

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_117.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_118.png)

### 探索与聚合函数

当拿到一个新数据集时，我们通常需要先探索其结构和内容。JSONiq提供了一系列函数用于此目的。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_120.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_122.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_123.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_124.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_126.png)

以下是用于数据探索的关键函数：

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_128.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_129.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_131.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_132.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_133.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_134.png)

*   **`keys`**：返回对象中所有键（属性名）的序列（去重后）。用于发现数据结构。
    ```jsoniq
    keys(json(“large-dataset.jsonl”))
    ```
*   **`distinct-values`**：返回序列中所有不重复值的序列。用于了解某个字段有哪些可能的值。
    ```jsoniq
    distinct-values(json(“large-dataset.jsonl”).type)
    ```
*   **`count`**：返回输入序列中项的总数。
    ```jsoniq
    count(json(“large-dataset.jsonl”))
    ```

**性能提示**：
*   在JSON Lines文件上运行 `keys()` 或 `count()` 可能需要扫描整个文件。
*   如果数据存储在Parquet等列式格式中，相同的查询可能会快得多，因为系统可以直接从文件元数据（如模式）中获取信息，而无需扫描所有数据。**查询语法保持不变**，体现了数据独立性。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_136.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_137.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_138.png)

---

### 构造数据：字面量与序列

除了查询，我们经常需要创建新的数据。JSONiq的一个设计目标是成为JSON的超集。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_140.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_141.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_142.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_143.png)

**构造基本JSON值**：
任何有效的JSON字面量（字符串、数字、布尔值、对象、数组）本身就是一个有效的JSONiq查询，它会返回自身。
```jsoniq
“Hello”
42
{ “name”: “Alice”, “age”: 30 }
[1, 2, 3]
```

**构造其他数据类型**：
对于JSON不原生支持的类型（如日期、时间、二进制数据），可以使用类型构造函数。
```jsoniq
date(“2023-11-26”)
base64Binary(“SGVsbG8=”)
```

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_145.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_146.png)

**构造序列**：
使用逗号 `,` 将多个表达式连接起来，可以创建序列。
```jsoniq
“apple”, true, 42, { “id”: 1 }
```
这会返回一个包含4个异构项的序列。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_148.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_149.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_150.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_151.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_152.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_154.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_155.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_156.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_157.png)

**生成整数范围序列**：
使用 `to` 操作符可以快速生成一个连续的整数序列。
```jsoniq
1 to 100
```
这会生成一个包含1到100的整数序列。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_159.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_160.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_162.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_163.png)

---

### 算术与字符串操作

JSONiq支持标准的算术和字符串操作，但需要特别注意其对序列的处理逻辑。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_165.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_167.png)

**算术运算**：
支持 `+`, `-`, `*`, `div` (除法), `idiv` (整数除法), `mod` (取模)等。
```jsoniq
5 + 3
10 idiv 3 // 结果为 3
```

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_169.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_171.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_173.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_175.png)

**序列处理规则（算术运算）**：
*   如果运算符任意一侧的表达式结果为空序列，则整个运算结果为空序列。
*   如果任意一侧的表达式结果包含**多于一个**项，则会发生错误。
*   运算要求类型匹配（例如，不能将字符串与数字相加）。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_177.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_178.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_180.png)

**字符串连接**：
使用双竖线 `||` 进行字符串连接（类似于SQL）。
```jsoniq
“Hello” || “ “ || “World”
```
此外，还有丰富的字符串函数库，如 `concat`, `substring`, `string-join` 等。
```jsoniq
string-join((“a”, “b”, “c”), “-”) // 结果为 “a-b-c”
```

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_182.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_184.png)

**比较运算**：
支持 `eq`, `ne`, `lt`, `le`, `gt`, `ge` 等比较运算符。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_186.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_187.png)

**序列处理规则（比较运算）**：
与算术运算不同，当比较运算符的一侧或两侧为多项目序列时，采用**存在量化**逻辑：
*   表达式 `(1, 2, 3) eq 2` 返回 `true`，因为序列中存在等于2的项。
*   表达式 `(1, 2) lt (3, 4)` 也返回 `true`，因为存在左边的项（1）小于右边的项（3）。
这种逻辑为检查序列中是否包含某个值提供了便捷的语法。

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_189.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_190.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_191.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_192.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_194.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_195.png)

---

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_197.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_198.png)

### 总结

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_199.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_200.png)

![](img/f491a7ebfa6f4edbc0f11554d63dd4b4_202.png)

本节课中我们一起学习了JSONiq查询语言的核心部分。我们首先建立了**序列（sequence of items）** 这一核心数据模型，它是所有JSONiq表达式操作的基础。接着，我们学习了如何通过**点运算符（`.`）** 和**方括号（`[]`）** 来导航和过滤JSON树结构数据。然后，我们了解了如何通过直接书写JSON字面量或使用构造函数来**创建新的数据**。最后，我们探讨了**算术运算**、**字符串操作**和**比较运算**，并特别强调了这些操作在处理**序列**时的特殊规则（如空序列、单值序列和多值序列）。掌握这些基础，是使用JSONiq有效处理各种结构化与半结构化数据的关键。