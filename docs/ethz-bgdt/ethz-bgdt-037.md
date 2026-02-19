# 37：文档存储（3/4）📚

![](img/5e0c8fe096859d9d02c46c33ddb80b93_1.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_3.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_4.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_5.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_7.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_8.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_10.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_12.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_14.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_16.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_17.png)

在本节课中，我们将学习MongoDB文档存储的进阶知识，包括类型排序、模式验证、架构、索引原理及其在查询优化中的应用。

---

## 课程回顾与问题解答 🔍

![](img/5e0c8fe096859d9d02c46c33ddb80b93_19.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_20.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_21.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_22.png)

上一节我们介绍了MongoDB的基本操作和JSON模式。在课间休息时，我们研究了一些大家提出的问题。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_24.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_25.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_26.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_27.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_28.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_29.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_30.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_31.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_32.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_33.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_34.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_35.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_37.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_38.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_40.png)

以下是针对这些问题的解答：

![](img/5e0c8fe096859d9d02c46c33ddb80b93_42.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_43.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_44.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_45.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_47.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_48.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_49.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_51.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_53.png)

1.  **关于类型的排序顺序**：我们在MongoDB官方文档中找到了明确的排序规则。其顺序为：Null、数字、字符串、对象和数组、二进制数据、对象ID、布尔值、日期、时间戳、正则表达式，最后是`MinKey`和`MaxKey`这两个哨兵值。这意味着，在比较时，布尔值被认为大于任何数字。
2.  **MongoDB是否会追溯验证集合**：答案是否定的。模式验证是面向未来的，只应用于未来的插入或更新操作，不会对集合中已存在的文档进行回溯性扫描。
3.  **如何检查现有文档的有效性**：虽然模式验证不追溯，但你可以使用`find`命令配合`$jsonSchema`操作符来检查。例如，`db.collection.find({$jsonSchema: {...}})`会返回所有符合该模式的文档。使用`$not`操作符则可以找出所有无效的文档，然后你可以根据`_id`去修复它们。
4.  **有效数据是否会以更优格式存储**：根据我们的调查，MongoDB似乎始终使用BSON格式存储数据，即使数据符合模式定义。目前没有发现它会像数据框那样根据模式优化存储空间。这或许是一个未来的改进方向。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_55.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_56.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_57.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_58.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_59.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_60.png)

---

![](img/5e0c8fe096859d9d02c46c33ddb80b93_62.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_64.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_66.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_67.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_68.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_69.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_70.png)

## 更新粒度与API设计 🧩

![](img/5e0c8fe096859d9d02c46c33ddb80b93_72.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_73.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_74.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_75.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_76.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_77.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_79.png)

现在，让我们回到课程内容。文档存储的更新粒度与HBase类似，是以**文档**为单位的。这意味着同一文档无法被两个客户端同时更新，但可以同时更新同一集合中的不同文档。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_81.png)

我们之前注意到，MongoDB的API设计包含了许多特定选择，例如`$`关键字的使用、点号表示法、排序中`1`和`-1`的使用等。正因为底层API的这种特性，为了构建一个完整易用的产品，通常需要在之上提供一个更高级的**查询语言**。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_83.png)

许多文档存储系统都提供了这样的高级语言。例如，本课程将教授的**JSONiq**，还有**UnQL**、**GraphQL**等。目前，针对树状结构数据的查询语言尚未像SQL（针对表格）或某些图查询语言那样形成统一标准，市场上存在多种选择。我们将在后续课程中以JSONiq为例，深入探讨这种高级查询语言。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_85.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_87.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_89.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_90.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_91.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_92.png)

---

![](img/5e0c8fe096859d9d02c46c33ddb80b93_94.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_95.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_96.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_98.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_100.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_102.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_103.png)

## MongoDB的架构 🏗️

![](img/5e0c8fe096859d9d02c46c33ddb80b93_105.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_106.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_107.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_109.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_110.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_111.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_112.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_114.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_115.png)

为了处理海量数据，MongoDB采用了**分片**和**复制**的架构，这与HDFS的思想类似。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_117.png)

数据根据一个键（通常也是索引键）被分割成多个**分片**。每个分片又由一个**副本集**来管理。一个副本集包含多台机器，其中一台是**主节点**，负责处理读写请求；其他是**从节点**，存储相同的数据副本。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_119.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_121.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_122.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_123.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_124.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_126.png)

写入数据时，客户端连接到目标分片的主节点。主节点应用更新后，会将更改**同步**传播给一定数量的从节点（数量由用户配置）。一旦达到这个最小成功数，操作就被认为成功，并返回给客户端。剩余的复制操作会在后台**异步**完成。这种“同步到一定数量，然后异步完成全部”的模式，我们在GFS中也曾见过。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_128.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_129.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_130.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_131.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_133.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_135.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_136.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_138.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_140.png)

---

![](img/5e0c8fe096859d9d02c46c33ddb80b93_142.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_143.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_144.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_146.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_147.png)

## 索引：加速查询的魔法 ⚡

![](img/5e0c8fe096859d9d02c46c33ddb80b93_149.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_150.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_151.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_152.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_154.png)

文档存储与数据湖的一个关键区别在于，它可以构建**索引**来极大加速查询。试想，在存有数十亿文档的数据湖中，使用Spark通过`filter`查找一个特定文档（点查询），需要扫描全部数据，即使并行处理也效率不高。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_156.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_157.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_158.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_159.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_161.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_162.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_163.png)

索引的原理类似于书籍末尾的索引。它建立一个额外的、高效的数据结构，让你能快速定位目标，而无需遍历所有数据。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_165.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_166.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_167.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_168.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_169.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_171.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_172.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_173.png)

### 哈希索引

![](img/5e0c8fe096859d9d02c46c33ddb80b93_175.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_176.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_177.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_178.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_180.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_182.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_184.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_186.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_188.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_189.png)

哈希索引使用一个**哈希函数** `H`，它能将任何输入值快速、确定性地映射到一个整数（数组位置）。MongoDB创建哈希索引的命令如下：
```javascript
db.collection.createIndex({ field: "hashed" })
```
构建索引需要时间扫描集合。查询时，对查询值计算哈希`H(value)`，直接定位到数组位置，然后通过指针找到文档，时间复杂度接近 **O(1)**。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_191.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_192.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_193.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_194.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_195.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_196.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_198.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_200.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_202.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_204.png)

**哈希索引的局限性**：
*   不支持范围查询（如 `field > 100`）。
*   可能存在哈希冲突。
*   需要较多内存空间来减少冲突。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_206.png)

### B+树索引

![](img/5e0c8fe096859d9d02c46c33ddb80b93_208.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_209.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_211.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_212.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_213.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_214.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_216.png)

B+树索引将数据以排序的方式组织在树结构中。每个节点有多个键和子节点指针，数据值只存储在叶子节点。MongoDB创建升序B+树索引的命令如下：
```javascript
db.collection.createIndex({ field: 1 }) // 1 表示升序，-1 表示降序
```
在B+树中查找，时间复杂度为 **O(log n)**。它的巨大优势是**高效支持范围查询**。查找一个范围时，可以从起始点开始，顺序遍历叶子节点即可。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_217.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_218.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_220.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_222.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_224.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_226.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_227.png)

**B+树的特点**：
*   所有叶子节点在同一深度。
*   除根节点外，每个节点的子节点数量在一定范围内（如d+1 到 2d+1），以匹配磁盘块大小，优化I/O。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_229.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_230.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_231.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_232.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_233.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_234.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_236.png)

### 索引在MongoDB中的应用

![](img/5e0c8fe096859d9d02c46c33ddb80b93_237.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_238.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_240.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_242.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_244.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_246.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_248.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_249.png)

MongoDB默认为 `_id` 字段创建一个B+树索引，称为**主索引**。用户在其他字段上创建的索引称为**二级索引**。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_251.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_253.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_254.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_256.png)

索引的核心好处是：**减少磁盘读取**。查询时，优化器会分析查询条件，选择使用一个或多个索引来快速定位候选文档，然后再在内存中进行必要的额外过滤，而不是读取全部数据。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_257.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_258.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_260.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_262.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_263.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_264.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_266.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_268.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_269.png)

**查询示例**：
1.  **完全匹配**：如果查询条件恰好是索引字段的等值匹配，索引能直接返回结果，速度最快。
2.  **复合条件**：如果查询是多个条件的“与”关系，且其中一个条件有索引，MongoDB会先用索引筛选出满足该条件的文档，再在内存中检查其他条件。
3.  **范围查询**：B+树索引可以高效处理范围查询，直接定位到范围内的起始点。
4.  **复合索引查询**：在`(birth, death)`的复合索引上，查询仅包含第一个字段`birth`的范围是高效的。但仅查询第二个字段`death`则无法有效利用该索引。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_271.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_273.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_275.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_277.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_278.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_280.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_282.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_284.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_285.png)

MongoDB的查询优化器会评估各种可能的执行计划（包括使用不同索引的组合），并选择它认为成本最低的计划。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_287.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_288.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_290.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_292.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_294.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_295.png)

---

![](img/5e0c8fe096859d9d02c46c33ddb80b93_297.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_298.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_299.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_300.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_302.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_303.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_305.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_306.png)

## 总结 📝

![](img/5e0c8fe096859d9d02c46c33ddb80b93_308.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_309.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_311.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_313.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_315.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_316.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_317.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_319.png)

本节课我们一起深入探讨了MongoDB文档存储的多个核心方面。我们首先解答了关于类型排序和模式验证的疑问。接着，我们了解了其基于分片和副本集的分布式架构，以及写入数据的同步/异步复制过程。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_321.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_323.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_324.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_325.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_327.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_329.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_331.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_333.png)

课程的重点是**索引**。我们学习了哈希索引（O(1)查找，仅支持等值查询）和B+树索引（O(log n)查找，支持范围查询）的工作原理及其优缺点。最后，我们通过实例看到了索引如何在实际查询中发挥作用，显著提升性能，以及MongoDB查询优化器如何选择最佳执行计划。

![](img/5e0c8fe096859d9d02c46c33ddb80b93_335.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_336.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_338.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_340.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_341.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_343.png)

![](img/5e0c8fe096859d9d02c46c33ddb80b93_345.png)

理解索引是高效使用任何数据库系统的关键。在下一讲中，我们将完成文档存储部分的剩余内容。