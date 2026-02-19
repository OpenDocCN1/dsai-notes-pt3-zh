# 44：图数据库（2/3）📊

![](img/37e3a6fdcb39bc2d633e240d5faeec37_0.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_2.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_4.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_6.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_7.png)

在本节课中，我们将继续探索图数据库，特别是带标签的属性图模型。我们将学习其类型系统、查询语言Cypher的基本语法，以及如何将图模式与关系型数据库概念联系起来。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_9.png)

---

## 图模型与关系表的映射 🔗

上一节我们介绍了带标签的属性图的基本概念。本节中，我们来看看如何将关系型数据库的表结构映射到图模型上。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_11.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_13.png)

在带标签的属性图中，节点可以拥有标签（如“Person”）和属性（如“name: Albert”）。边（或称关系）也可以有类型（如“CHILD_OF”）和属性。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_15.png)

如果你想在图数据库之上实现关系表，本质上可以使用类似内存指针的链接，这类似于关系数据库中**外键**和**主键**之间的连接。这正是我们最初想通过使用内存指针来避免表连接的原因。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_17.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_18.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_19.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_21.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_23.png)

以下是一个映射示例：
*   一个标签为 `Person`、属性为 `name: Albert` 的节点。
*   另一个标签为 `Person`、属性为 `name: Hubert` 的节点。
*   一条从 Albert 指向 Hubert、类型为 `CHILD` 的关系边。

由此可见，关系表可以轻松地在带标签的属性图（或文档存储）之上实现。但这种映射不是双向的，因为无法轻松地将任何带标签的属性图转换为这样的关系表。

---

![](img/37e3a6fdcb39bc2d633e240d5faeec37_25.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_26.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_27.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_28.png)

## Cypher 类型系统 🧱

![](img/37e3a6fdcb39bc2d633e240d5faeec37_29.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_31.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_32.png)

现在，我们来探讨类型系统。这部分内容我们在几周前已经涉及过，目标是让你再次认识到它们本质上是相同的概念。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_34.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_35.png)

Cypher 是 Neo4j 图数据库的查询语言，用于操作带标签的属性图。其类型系统如下：

**核心原子类型**（用**黄色**标出）：
*   `INTEGER`
*   `FLOAT`
*   `STRING`
*   `BOOLEAN`
*   `DATE`
*   `TIME`
*   `DATETIME`
*   `DURATION`
*   `POINT` (用于地理信息系统 GIS)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_37.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_39.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_40.png)

`POINT` 类型是这里唯一相对较新的概念，用于处理空间位置信息（如地球坐标）。但许多现代系统（如 MongoDB）也支持类似功能。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_42.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_43.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_45.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_46.png)

**结构类型**（用**蓝色**标出）：
*   `LIST` - 对应 JSON 中的数组 (`array`) 或 Python 中的列表 (`list`)。
*   `MAP` - 对应 JSON 中的对象 (`object`) 或 Python 中的字典 (`dict`)。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_47.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_49.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_50.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_52.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_53.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_54.png)

**图特有的类型**：
*   `NODE` - 图中的节点。
*   `RELATIONSHIP` - 图中的边（关系）。
*   `PATH` - 由边连接的一系列节点，即图上的路径。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_56.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_57.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_58.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_60.png)

节点、关系和路径是图数据库中的一等公民，它们在 JSON 或 Python 中没有直接等价物。虽然理论上树是特殊的无环图，但在数据库的语境下，树形结构和图形结构的处理方式不同，因此不能简单等同。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_61.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_62.png)

---

## 节点与关系的属性限制 📝

![](img/37e3a6fdcb39bc2d633e240d5faeec37_64.png)

节点和关系都可以拥有属性。但属性值的存储有严格限制：属性必须是“平坦”的。

具体来说，属性中只能包含以下内容：
1.  **原子类型**的值（如整数、字符串、布尔值等）。
2.  **同质列表**（`LIST`），即所有元素类型必须相同的原子类型列表，例如：
    *   `[1, 2, 3, 4]` （整数列表）
    *   `["a", "b", "c"]` （字符串列表）
    *   `[true, false, true]` （布尔值列表）

![](img/37e3a6fdcb39bc2d633e240d5faeec37_66.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_67.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_68.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_69.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_70.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_71.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_72.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_73.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_74.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_75.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_76.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_77.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_79.png)

**这是属性中唯一允许的嵌套形式**。除此之外，所有属性都必须是平坦的。这意味着你不能在属性中直接存储一个 `MAP`（对象）或一个包含多种类型元素的异构列表。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_80.png)

**重要区分**：在查询语言（Cypher）中，你可以操作和处理所有类型（包括嵌套的 `MAP` 和异构 `LIST`）。但在存储层面，节点和关系的属性必须遵守上述平坦化规则。

---

![](img/37e3a6fdcb39bc2d633e240d5faeec37_82.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_84.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_86.png)

## 跨模型的比较：类型排序与空值处理 🔄

![](img/37e3a6fdcb39bc2d633e240d5faeec37_87.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_88.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_89.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_90.png)

了解了一个系统的特性后，将其与其他系统对比有助于加深理解。这里有两个跨数据模型的对比点。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_92.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_93.png)

**1. 跨类型比较的顺序**
在 MongoDB 中，可以比较不同类型的值，系统内部有一个任意的类型排序规则。Neo4j 的 Cypher 语言也是如此，它也有自己的类型排序规则，并且能够进行跨类型比较。需要注意的是，Neo4j 的类型排序与 MongoDB 的**完全不同**，但这无关紧要，因为这只是一个实现细节。开发者只需知道“可以比较不同类型的值”即可。

**2. 空值（Null）的处理范式**
在不同系统中，对空值（Null）的处理主要有两种范式：
*   **视为特殊值**：例如 SQL 中的 `NULL`，它是一个可以属于任何类型的特殊标记值。
*   **视为值的缺失**：例如 JSONiq 中的空序列（empty sequence）。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_95.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_96.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_98.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_100.png)

在 Neo4j 中，`null` 的行为更接近 **SQL 的 `NULL`** 或 **JSONiq 的空序列**。你应该将其理解为“值的缺失”。任何数据类型都可以有一个 `null` 值，但这实际上意味着该值不存在。在类型系统中，这被称为类型是“可空的”（nullable）。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_102.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_103.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_104.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_105.png)

在 JSONiq 中，使用问号（`?`）表示可空类型，例如 `integer?` 表示“要么是一个整数，要么是空序列”。这与 Neo4j 中可空类型的概念是相通的。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_106.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_108.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_109.png)

---

![](img/37e3a6fdcb39bc2d633e240d5faeec37_111.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_113.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_115.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_116.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_117.png)

## 列表（LIST）与映射（MAP）详解 📚

理解了基本类型和限制后，我们进一步看看 `LIST` 和 `MAP` 的细节。

**列表（LIST）**
*   **异构列表**：在查询语言中，列表可以是异构的，例如 `[2, 3, true, "blah"]`。这在 JSONiq 和 MongoDB 中也很常见。
*   **同质列表**：在**属性存储**中，列表必须是同质的，例如 `[1, 2, 3, 4]`。
*   **索引访问**：在 Cypher 中，使用单方括号和从 `0` 开始的索引来访问列表元素，例如 `list[0]`。这与 JSONiq（从 `1` 开始）和 Python（从 `0` 开始）略有不同。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_119.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_121.png)

**映射（MAP）**
映射本质上就是 JSON 对象。
*   **语法差异**：在 Cypher 中，映射的键通常**不加引号**，例如 `{name: "Alice", age: 30}`。这与某些 JSON 解析库的宽松语法类似。
*   **嵌套性**：在通用查询语言中，映射可以任意嵌套，值可以是列表或其他映射。
*   **属性限制**：然而，当映射作为**节点的属性**存储时，它必须是平坦的，即其值只能是原子类型或同质原子类型列表。

**为什么查询语言支持更复杂的结构？**
既然属性存储限制严格，为什么查询语言还要支持嵌套映射和异构列表呢？这是为了提供最大的灵活性。例如，在查询时，你可能需要联合（union）来自不同节点、类型各异的属性值，或者需要在查询过程中构造复杂的数据结构进行中间计算。这种设计理念与 JSONiq 是一致的。

---

![](img/37e3a6fdcb39bc2d633e240d5faeec37_123.png)

## Cypher 查询语言入门：子句与导航 🧭

![](img/37e3a6fdcb39bc2d633e240d5faeec37_125.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_126.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_127.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_128.png)

前面我们讨论了数据模型和类型系统。现在，我们开始接触 Cypher 查询语言本身，首先是基本的子句和导航操作。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_130.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_132.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_133.png)

**基本导航**
导航数据的语法与 JSONiq 非常相似：
*   **点号（.）访问属性**：`node.name` 类似于 JSONiq 中的对象查找。
*   **方括号（[]）访问列表元素**：`list[0]`。Cypher 没有 JSONiq 中用于区分序列和数组的双重方括号概念，因为它的列表不会像 JSONiq 序列那样巨大。

**核心子句**
Cypher 的查询由一系列子句构成，其设计思想非常接近现代查询语言（如 JSONiq、Google SQL Pipe Syntax），允许子句以灵活的顺序组合（只要以 `RETURN` 结束）。数据以**绑定元组流**的形式在子句间传递。
*   `RETURN`：用于输出结果，相当于 SQL 的 `SELECT` 或 JSONiq 的 `return`。
*   `WITH`：用于将中间结果绑定到变量，并传递到下一个子句。它类似于 JSONiq 的 `let` 子句，但有一个关键区别：每个新的 `WITH` 子句只会保留其显式指定的变量，之前绑定的其他变量会被丢弃。如果需要保留，必须在新的 `WITH` 中重新列出。
*   `UNWIND`：用于将列表“展开”为多行记录，相当于 JSONiq 的 `for` 子句。例如，`UNWIND [1, 2, 3] AS num` 会生成三行数据，每行的 `num` 变量分别绑定为 1, 2, 3。
*   `WHERE`：用于过滤，和 SQL 的 `WHERE` 类似，但可以出现在查询的多个位置，与其他子句灵活交织。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_135.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_136.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_138.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_140.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_141.png)

这种基于子句和绑定流的范式，使得 Cypher 在表达复杂的数据转换和流水线处理时，比传统的 SQL 更加灵活和强大。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_143.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_144.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_145.png)

---

![](img/37e3a6fdcb39bc2d633e240d5faeec37_146.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_147.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_148.png)

## 图模式匹配：Cypher 的核心 🎯

![](img/37e3a6fdcb39bc2d633e240d5faeec37_150.png)

现在，我们进入 Cypher 最核心、最强大的部分：**图模式匹配**。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_151.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_153.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_155.png)

你的数据库就是一个图。图查询的本质是识别图中的特定模式，然后从这些模式中提取数据。Cypher 使用一种直观的 **ASCII 艺术** 风格语法来描述这些模式。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_157.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_158.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_160.png)

**基本模式匹配**
假设我们想在一个图中找到如下模式：三个节点，其中第一个节点通过类型为 `A` 的关系连接到第二个节点，第二个节点通过类型为 `B` 的关系连接到第三个节点。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_161.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_163.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_165.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_167.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_168.png)

在 Cypher 中，你可以这样写：
```cypher
(alpha)-[:A]->(beta)-[:B]->(gamma)
```
*   `(alpha)`, `(beta)`, `(gamma)` 是为节点分配的变量名。
*   `[:A]` 和 `[:B]` 指定了关系的类型。冒号（`:`）后面是类型标签。
*   箭头（`->`）指明了关系的方向。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_170.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_172.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_173.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_174.png)

执行这个 `MATCH` 子句时，数据库会在图中查找所有符合该模式的子图。每找到一次，就将匹配的节点绑定到变量 `alpha`, `beta`, `gamma` 上，生成一条记录。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_176.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_177.png)

**增加过滤条件**
你可以在模式内部或使用 `WHERE` 子句来增加过滤条件：
1.  **过滤节点标签**：`(beta:Yellow)` 要求节点 `beta` 必须有标签 `Yellow`。
2.  **过滤节点属性**：`(alpha {name: "Einstein"})` 要求节点 `alpha` 的 `name` 属性等于 “Einstein”。
3.  **两者结合**：`(alpha:Blue {name: "ETH"})` 要求节点同时满足标签和属性条件。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_179.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_181.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_182.png)

**更复杂的模式**
Cypher 可以表达非常复杂的模式：
*   **变长路径**：`(alpha)-[:A*1..4]->(beta)` 查找从 `alpha` 到 `beta`、通过类型为 `A` 的关系、路径长度在 1 到 4 之间的所有路径。这类似于正则表达式，在 SQL 中实现此类查询会非常复杂。
*   **环状路径**：`(alpha)-[:A]->(beta)-[:B]->(gamma)-[:C]->(alpha)` 查找一个回到起点的三角形环。
*   **无方向边**：如果你不指定箭头方向，模式将匹配任意方向的关系。

**`MATCH` 子句的使用**
图模式需要放在 `MATCH` 子句中使用。`MATCH` 子句会生成变量绑定，然后可以与其他子句（如 `WITH`, `WHERE`, `RETURN`）组合，形成完整的查询。例如：
```cypher
MATCH (alpha)-[:A]->(beta)-[:B]->(gamma)
WHERE alpha.name = "Einstein"
RETURN gamma
```
这个查询会找到所有符合模式的子图，然后过滤出其中 `alpha` 节点名为 “Einstein” 的记录，最后返回对应的 `gamma` 节点。

---

![](img/37e3a6fdcb39bc2d633e240d5faeec37_184.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_186.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_188.png)

## 数据更新与其他操作 ⚙️

![](img/37e3a6fdcb39bc2d633e240d5faeec37_190.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_191.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_192.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_193.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_194.png)

与 SQL、MongoDB 和 JSONiq 一样，Cypher 也支持数据更新操作。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_196.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_197.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_199.png)

**创建数据**
使用 `CREATE` 子句可以创建新的节点、关系和属性。它是声明式的：你描述你想要的数据状态，数据库会使其成为现实。
```cypher
CREATE (e:Person {name: "Einstein", first: "Albert"}),
       (u:University {name: "ETH Zurich"}),
       (e)-[:VISITED]->(u)
```

![](img/37e3a6fdcb39bc2d633e240d5faeec37_201.png)

**合并数据**
`MERGE` 子句类似于 `CREATE`，但具有“存在即忽略，不存在则创建”的语义。它确保图中的某个模式存在，如果模式中的节点或关系已存在，则不会重复创建。`MERGE` 同样会绑定变量供后续子句使用。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_203.png)

**其他子句**
Cypher 还包含许多其他实用子句，例如：
*   `DELETE`：删除节点或关系。
*   `SET`：更新属性。
*   `LIMIT` / `SKIP`：限制返回结果的数量和偏移。
*   `ORDER BY`：排序。
*   `UNION`：合并结果集。

这些子句都可以与前面介绍的子句自由组合，为你提供强大的数据操作能力。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_205.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_207.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_208.png)

---

![](img/37e3a6fdcb39bc2d633e240d5faeec37_210.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_211.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_213.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_215.png)

## 总结 🎓

![](img/37e3a6fdcb39bc2d633e240d5faeec37_217.png)

![](img/37e3a6fdcb39bc2d633e240d5faeec37_218.png)

本节课我们一起深入学习了图数据库的核心——带标签的属性图模型及其查询语言 Cypher。

我们首先了解了如何将关系表映射到图结构，并认识到这种映射的单向性。接着，我们系统学习了 Cypher 的类型系统，明确了节点和关系在属性存储上的限制（平坦化、同质列表）。通过对比 Neo4j 与 MongoDB 在类型比较和空值处理上的异同，我们加深了对不同系统设计理念的理解。

![](img/37e3a6fdcb39bc2d633e240d5faeec37_220.png)

然后，我们详细探讨了 Cypher 查询语言。从基本的子句（`RETURN`, `WITH`, `UNWIND`, `WHERE`）和灵活的绑定流模型入手，我们看到了它与 JSONiq 等现代查询语言的相似性。最后，我们聚焦于 Cypher 最强大的功能：**使用 ASCII 艺术风格的语法进行图模式匹配**。我们学习了如何描述基本模式、增加过滤条件、表达复杂路径（如变长路径、环），并将 `MATCH` 子句与其他子句结合以构建完整查询。此外，我们也简要介绍了数据的创建（`CREATE`）、合并（`MERGE`）等更新操作。

掌握 Cypher 的关键在于理解其**基于模式匹配**和**声明式子句流水线**的核心思想。这使你能够直观而高效地查询和操作复杂的关联数据。