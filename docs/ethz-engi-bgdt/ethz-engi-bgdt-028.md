#  028：文档存储 (2/3) 📄

![](img/a294a0699ef942f9a2fa51cadc28dd1f_1.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_2.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_3.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_5.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_6.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_7.png)

在本节课中，我们将学习文档存储的核心概念，特别是以 MongoDB 为例，了解其数据模型、查询方式、系统架构以及索引机制。我们将看到文档存储如何通过嵌套结构和异构性来扩展传统表格模型的能力。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_8.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_10.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_12.png)

## 数据模型回顾

![](img/a294a0699ef942f9a2fa51cadc28dd1f_13.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_14.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_15.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_16.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_17.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_18.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_20.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_21.png)

上一节我们介绍了数据的不同形态，从表格到数据框。本节中我们来看看文档存储所处理的数据模型——树形结构。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_23.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_25.png)

文档存储的核心是处理**树形结构**的集合。与关系型数据库的表格相比，树形结构有两个关键特征：

![](img/a294a0699ef942f9a2fa51cadc28dd1f_27.png)

1.  **嵌套性**：数据可以有多层嵌套，类似于“表格中的表格”，但实际上是“对象数组中的对象数组”。如果一个对象数组中的所有对象都符合相同的模式且是扁平的，那么它本质上就是一个表格。
    *   公式表示：`Array[Object]`，其中 `Object` 可以是另一个 `Array[Object]`。
2.  **异构性**：如果放弃模式约束，集合中的对象可以拥有完全不同的结构。

正是这两个特性构成了 NoSQL（不仅仅是 SQL）的广阔世界。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_29.png)

## 文档存储：MongoDB 的逻辑视角

现在，我们需要一个类似于 PostgreSQL 但用于处理树形数据的系统，这就是文档存储。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_31.png)

在文档存储（如 MongoDB）中，我们拥有**树的集合**，就像 PostgreSQL 中拥有表格一样。这些集合可以包含数百万甚至数十亿棵树，但每棵树的尺寸有限（例如 MongoDB 限制为 16MB）。因此，我们处理的是海量的中型对象集合。

### 与表格和数据框的关系

理解嵌套性和异构性后，我们可以发现：
*   **表格是树集合的一个特例**：当树是扁平的（所有值都是原子值）且同构的（所有记录拥有完全相同的键和类型）时，我们就得到了一个关系型表格。
    *   核心概念：`Table = Homogeneous Collection of Flat Trees`
*   **数据框处于中间地带**：数据框允许嵌套性，但要求同构性（即拥有模式）。
    *   核心概念：`DataFrame = Homogeneous Collection of Possibly Nested Trees`

### 基本操作与查询

在文档存储中，我们同样可以实现关系代数中的基本操作：投影、选择、聚合、排序。然而，**连接**操作不那么常用，因为树形数据通常是反规范化的。嵌套的对象数组本身就相当于预计算好的连接结果。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_33.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_34.png)

关于模式，MongoDB 提供了灵活性：
*   可以无模式运行，直接存入异构的树。
*   也可以定义模式，在存入时或之后进行数据验证和清理。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_36.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_37.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_38.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_40.png)

### MongoDB 生态系统

![](img/a294a0699ef942f9a2fa51cadc28dd1f_42.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_43.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_44.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_45.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_46.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_48.png)

文档存储领域有许多产品，如 MongoDB、CouchDB（基于 JSON）、Elasticsearch（基于 JSON，主要用于搜索）、BaseX（基于 XML）等。它们的原理相似。本课程将重点介绍最流行的 MongoDB。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_50.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_51.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_52.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_53.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_54.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_56.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_57.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_58.png)

## 物理存储与查询 API

我们之前学习的数据湖（如 S3、HDFS）允许直接查看文件。而像 MongoDB 这样的系统需要先导入数据，其物理存储布局对用户是隐藏的。MongoDB 使用 **BSON** 格式在磁盘上存储数据，它是一种二进制的、更紧凑的 JSON 表示。

### 低级 CRUD API

![](img/a294a0699ef942f9a2fa51cadc28dd1f_60.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_62.png)

MongoDB 提供了一个低级的、基于语言的 API（如 JavaScript 或 Python）来进行操作，遵循 **CRUD**（创建、读取、更新、删除）范式。这与拥有独立查询语言（如 SQL）的体验不同。

以下是使用 JavaScript API 进行查询的一些示例，并与 SQL 进行对比：

**查询所有文档（相当于 `SELECT *`）**
```javascript
db.scientists.find({})
```
此命令返回 `scientists` 集合中的所有文档。

**带条件的查询（相当于 `WHERE`）**
```javascript
db.scientists.find({“theory”: “relativity”})
```
此命令查找 `theory` 字段等于 “relativity” 的文档。

**投影（选择特定字段）**
```javascript
db.scientists.find({}, {“first”: 1, “last”: 1})
```
此命令仅返回 `first` 和 `last` 字段。使用 `0` 则表示排除该字段。

**组合条件（AND）**
```javascript
db.scientists.find({“last”: “Einstein”, “century”: 20})
```
此命令查找同时满足两个条件的文档。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_64.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_66.png)

**或条件（OR）**
```javascript
db.scientists.find({$or: [{“last”: “Newton”}, {“last”: “Einstein”}]})
```
使用 `$or` 操作符表示或条件。

**比较操作符**
```javascript
db.scientists.find({“publications”: {$gte: 200}})
```
使用如 `$gte`（大于等于）、`$lte`（小于等于）等操作符进行比较查询。

**处理嵌套字段**
```javascript
db.scientists.find({“name.first”: “Albert”})
```
使用点号 `.` 来访问嵌套字段。注意，`{“name”: {“first”: “Albert”}}` 是要求精确匹配整个 `name` 对象。

**其他操作**
*   `count()`: 计数。
*   `sort({“field”: 1})`: 排序（1升序，-1降序）。
*   `skip(30).limit(10)`: 分页。
*   `distinct(“last”)`: 去重。
*   `aggregate([...])`: 聚合管道，功能强大，类似于一系列的数据转换操作，概念上类似 Spark 的转换。

**插入、更新、删除**
*   `insertOne({...})` / `insertMany([...])`
*   `updateMany({...}, {$set: {...}})`
*   `deleteMany({...})`

![](img/a294a0699ef942f9a2fa51cadc28dd1f_68.png)

需要注意的是，MongoDB 将 `null` 值和字段缺失视为相同。此外，每个文档都有一个自动添加的唯一 `_id` 字段。

这种 API 方式在简单查询时直观，但对于复杂查询，其语法会变得繁琐且需要记忆大量特定操作符（以 `$` 开头）。这体现了低级 API 与高级声明式查询语言的区别。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_70.png)

## 系统架构：复制与分片

![](img/a294a0699ef942f9a2fa51cadc28dd1f_72.png)

与之前的分布式系统（如 HDFS）类似，MongoDB 也采用**复制**和**分片**来保证可靠性与扩展性。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_74.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_76.png)

*   **复制**：创建数据的多个副本，防止数据丢失。副本组成了**副本集**。
*   **分片**：将数据集合水平分割成多个部分（称为**分片**），分布到不同机器上，实现并行处理。

MongoDB 的架构特点是：每个分片本身又是一个副本集。每个副本集内部有一个主节点和多个从节点。写入数据时，可以配置需要等待多少个节点确认后才向客户端返回成功，从而实现可调的持久性保证。

## 索引机制

![](img/a294a0699ef942f9a2fa51cadc28dd1f_78.png)

索引是物理层面的优化技术，用于加速查询，其原理类似于书籍末尾的索引。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_80.png)

在 MongoDB 中，可以对文档的字段创建索引。例如，在 `century` 字段上创建索引：
```javascript
db.scientists.createIndex({“century”: 1}) // 1 表示升序索引
```

索引创建后，系统会维护一个排序的键值列表（如所有 `century` 值）以及指向对应文档的指针。当执行基于该字段的查询（特别是点查询 `field = value` 或范围查询 `field > value`）时，数据库可以直接在索引中快速定位，而无需扫描整个集合，从而极大提升查询速度。

![](img/a294a0699ef942f9a2fa51cadc28dd1f_82.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_83.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_85.png)

## 总结

![](img/a294a0699ef942f9a2fa51cadc28dd1f_87.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_88.png)

![](img/a294a0699ef942f9a2fa51cadc28dd1f_90.png)

本节课中我们一起学习了文档存储的核心内容。我们首先回顾了文档存储的树形数据模型及其嵌套性、异构性特点，并理解了它与表格和数据框的关系。接着，我们深入探讨了 MongoDB 的低级 CRUD API，通过大量示例了解了如何进行查询、投影、筛选等操作，同时也认识到这种 API 方式的复杂性。然后，我们考察了 MongoDB 的分布式架构，包括其通过副本集实现高可用、通过分片实现水平扩展的机制。最后，我们介绍了索引的基本原理及其对查询性能的巨大提升作用。文档存储为处理灵活、半结构化的数据提供了强大的工具，是现代大数据生态系统中的重要组成部分。