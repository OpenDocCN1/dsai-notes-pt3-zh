# 36：文档存储（2/4）📄

在本节课中，我们将继续探索文档存储。上一节我们介绍了当数据是嵌套和/或异构时，传统关系型数据库和Spark SQL的局限性。本节中，我们来看看专门为处理此类数据形状而设计的系统——文档存储。


## 概述：什么是文档存储？


文档存储是一种数据库范式，专门用于存储和管理大量文档。这些文档通常是树形结构，例如JSON或XML格式。与关系型数据库的表格不同，文档存储直接处理嵌套和异构的数据，避免了“阻抗不匹配”问题。


## 文档存储的核心概念

文档存储的核心是**集合**，其中包含大量**文档**。一个文档就是一个树形结构的数据单元。




### 数据规模与格式



文档存储可以处理海量文档，从数百万到数万亿个。然而，单个文档的大小通常有限制，例如MongoDB限制在16MB左右。这符合大数据场景中“大量中小型文档”的特点。


如果数据是巨大的单个对象（例如千个GB级文件），则应使用对象存储（如S3），而非文档存储。

### 文档存储的类型

市场上有两种主要的文档存储：
*   **JSON文档存储**：例如 **MongoDB**。
*   **XML文档存储**：例如 eXist-db 或 MarkLogic。


它们的核心理念相同，只是处理的序列化格式不同。


### 与关系型数据库的对比




关系型数据库处理的是**扁平化、同构**的数据（表格），这只是文档存储所能处理数据的一个特例。文档存储天然支持**嵌套**和**异构**的数据。









以下是文档存储与关系型数据库的一些关键区别：

*   **操作支持**：文档存储支持投影、选择和聚合操作。但大多数系统**不原生支持连接（Join）操作**，因为连接操作成本高昂，可能影响性能。用户通常需要在应用层通过API自行实现连接逻辑。
*   **模式（Schema）**：关系型数据库必须有预定义的模式（`CREATE TABLE`）。文档存储中，模式是**可选的**。你可以：
    *   无需模式直接插入文档。
    *   在创建集合时定义模式，进行严格验证。
    *   先插入数据，后期再添加模式进行验证，并可以灵活处理验证失败的情况。







## MongoDB 简介 🍃


我们将以MongoDB为例进行讲解，它是目前最流行的JSON文档存储。理解MongoDB后，学习其他文档存储系统将非常容易。




需要明确的是，MongoDB是一个**在线事务处理（OLTP）数据库**，类似于PostgreSQL。你需要通过ETL过程将数据插入其中，而不是像在HDFS或S3这样的数据湖中直接存放文件。








### 存储格式：BSON


当文档插入MongoDB后，它并非以JSON文本形式存储，而是转换为一种称为**BSON**的优化二进制格式。BSON是Binary JSON的缩写，它在JSON模型基础上进行了二进制编码，体积更小，并且支持更多数据类型（如日期）。







对于用户而言，你通常只需要与JSON数据模型交互，BSON的细节由系统在后台处理。

### 基本操作：CRUD

与MongoDB交互的基础是CRUD操作（创建、读取、更新、删除），通过特定语言的API（如JavaScript、Python）实现。

核心的读取操作是 `find()` 函数。它返回一个**游标（Cursor）**，你可以迭代遍历结果。


以下是一些基本查询示例及其近似SQL对比：






**查询所有文档**
```javascript
db.scientists.find()
```
近似SQL：`SELECT * FROM scientists;`






**带条件的查询（选择）**
```javascript
db.scientists.find({ "theory": "relativity" })
```
近似SQL：`SELECT * FROM scientists WHERE theory = 'relativity';`





**投影（选择特定字段）**
```javascript
db.scientists.find({ "theory": "relativity" }).project({ "first": 1, "last": 1 })
```
使用 `1` 表示包含字段，`0` 表示排除字段。近似SQL：`SELECT first, last FROM scientists WHERE theory = 'relativity';`






**注意**：由于文档存储没有固定模式，`project({“field”: 0})` 这种“排除字段”的投影方式非常有用，而这在已知所有列的关系型数据库中不常见。

### 查询谓词与操作符

查询条件本身也是一个JSON对象，这使得它非常直观。








**AND 操作**
将多个条件放入同一个对象即表示AND关系。
```javascript
db.scientists.find({ "last": "Einstein", "theory": "relativity" })
```




**OR 操作**
需要使用以美元符号(`$`)开头的操作符。
```javascript
db.scientists.find({ $or: [ { "last": "Newton" }, { "last": "Einstein" } ] })
```

**比较操作**
同样使用`$`操作符。
```javascript
db.scientists.find({ "publications": { $gte: 100 } })
```
`$gte` 表示“大于等于”。





**处理嵌套字段**
使用点号(`.`)来导航嵌套结构。






```javascript
// 正确：查找 name 对象下 first 字段为 “Albert” 的文档
db.scientists.find({ "name.first": "Albert" })
// 错误：这要求整个 name 字段的值完全等于 {“first”: “Albert”} 这个对象
db.scientists.find({ "name": { "first": "Albert" } })
```








**处理数组**
如果字段的值是一个数组，查询该字段的特定值会检查该值是否存在于数组中。
```javascript
// 查找 university 字段包含 “ETHZ” 的文档（university 可以是字符串或数组）
db.scientists.find({ "university": "ETHZ" })
```



**其他操作符**
MongoDB提供了大量操作符，如 `$in`（在集合中）、`$nin`（不在集合中）、`$exists`（字段存在）等。



### 其他常用方法

你可以像Spark中一样链式调用方法。

**计数**
```javascript
db.scientists.find({ "theory": "relativity" }).count()
```

**排序**
```javascript
db.scientists.find().sort({ "founded": -1, “last”: 1 })
```
`1` 表示升序，`-1` 表示降序。**注意**：在排序条件对象中，键的顺序是有意义的，这违反了JSON对象键序无关的一般原则，是API设计的一个特点。

**分页**
```javascript
db.scientists.find().skip(30).limit(10)
```
相当于SQL的 `OFFSET 30 LIMIT 10`。




**去重**
```javascript
db.scientists.distinct(“last”)
```




### 聚合框架










MongoDB的 `aggregate()` 函数功能强大，它提供了一个**聚合管道**，概念上与Spark的转换操作序列非常相似。你可以定义一系列阶段（如 `$match` 过滤、`$group` 分组、`$sort` 排序等）来处理数据。
```javascript
db.scientists.aggregate([
  { $match: { “century”: “20th” } },
  { $group: { _id: “$university”, totalPubs: { $sum: “$publications” } } },
  { $sort: { totalPubs: -1 } }
])
```
如果你已经掌握了Spark，理解聚合管道会非常容易。





### 插入、更新与删除





**插入文档**
```javascript
db.scientists.insertOne({
  “first”: “Marie”,
  “last”: “Curie”,
  “theory”: “radioactivity”,
  “century”: “20th”,
  “publications”: 50
})
```
如果集合定义了模式，此时会进行验证。






**更新文档**






```javascript
// 更新多个文档
db.scientists.updateMany(
  { “century”: “20th” },
  { $inc: { “publications”: 20 } } // 将 publications 字段增加20
)
// 更新一个文档
db.scientists.updateOne({ “last”: “Curie” }, { $set: { “nobelPrizes”: 2 } })
```





**删除文档**


```javascript
// 删除多个文档
db.scientists.deleteMany({ “century”: “5th” })
// 删除一个文档
db.scientists.deleteOne({ “last”: “SomeName” })
```





## 总结





本节课我们一起深入学习了文档存储，特别是MongoDB。我们了解到：






1.  **文档存储**是为处理**嵌套**和**异构**的树形数据而设计的数据库范式。
2.  MongoDB作为典型的JSON文档存储，通过**集合**和**文档**来组织数据，使用**BSON**格式进行高效存储。
3.  与关系型数据库相比，文档存储具有**模式灵活**的特点，但通常**不原生支持连接操作**。
4.  我们学习了MongoDB的基本**CRUD操作**，包括使用 `find()` 进行复杂查询、利用 `$` 操作符构建谓词、以及链式调用 `sort()`, `limit()`, `count()` 等方法。
5.  MongoDB强大的**聚合框架**允许我们以管道方式处理数据，其概念与Spark类似。
6.  需要特别注意，MongoDB的交互方式是基于**API**而非声明式查询语言，因此语法上存在一些特殊约定（如键的顺序在某些情况下有意义）。





![](img/4c66387789767a8ec0c70211308ff733_218.png)

理解文档存储的核心思想及其适用场景，对于在大数据环境中选择合适的数据存储和处理工具至关重要。