# 31：Spark (3/4) 🚀


在本节课中，我们将继续学习Spark，深入探讨其核心执行模型，特别是RDD的依赖关系、阶段划分以及性能优化技巧。随后，我们将介绍Spark中更高级的数据抽象——DataFrame，并了解其如何通过结构化数据带来性能提升和更便捷的查询方式。






## 窄依赖与阶段执行


上一节我们介绍了RDD和转换操作。本节中我们来看看转换操作之间的依赖关系如何影响Spark的执行。







窄依赖转换是指输出中的每个数据项仅依赖于输入中的一个数据项。例如 `map` 和 `filter` 操作。





```
// 窄依赖转换示例
val rdd2 = rdd1.map(x => x * 2) // 每个输出只依赖一个输入
val rdd3 = rdd2.filter(x => x > 10) // 每个输出只依赖一个输入
```








由于是窄依赖，多个转换可以被组合并在一个阶段内并行执行。Spark的Executor（对应YARN容器）包含多个任务槽（对应虚拟核心），任务会被动态分配给空闲的槽执行。




## 宽依赖与Shuffle






并非所有转换都是窄依赖。许多转换操作，如 `groupBy`、`join`、`sort` 等，会产生宽依赖，其执行过程像“意大利面条”一样交织。





当遇到宽依赖时，Spark需要进行**Shuffle**操作。因为数据需要根据键重新分布到不同的节点上进行计算。


Shuffle会创建新的**阶段**。一个Spark作业的逻辑执行计划（DAG）会被划分为多个阶段，阶段边界就是Shuffle发生的地方。与MapReduce只有一个Shuffle不同，Spark作业可以包含多个Shuffle阶段，这使得Spark比MapReduce更通用。


以下是Spark作业执行的图形化表示：



*   **阶段**：由一组具有窄依赖关系的转换操作组成，可以并行执行。
*   **Shuffle**：阶段之间的数据重分布过程。
*   **任务**：一个阶段被分割到集群不同节点上执行的工作单元。



Spark调度器负责协调所有阶段的执行。整个集群先并行执行第一个阶段的所有任务，然后进行Shuffle，接着再并行执行下一个阶段，依此类推。

对于需要多个输入的转换（如 `join`），可能涉及多个上游阶段，每个上游阶段输出都需要经过Shuffle，然后才能进行计算。

## 核心概念关系梳理

理解Spark中的逻辑概念和物理概念之间的关系很重要。





*   **逻辑层面（用户可见）**：用户编写**转换**操作，并触发一个**作业**的执行。
*   **物理层面（集群执行）**：Spark将转换操作按依赖关系分组为**阶段**，每个阶段被拆分为多个**任务**在集群上执行。

**转换**和**阶段**没有直接的一对一关系。一个阶段可能包含多个窄依赖转换。一个作业则是由一系列阶段组成的有向无环图。

## 性能优化技巧

理解执行模型有助于我们优化Spark应用性能。

### 缓存（Caching）




观察以下执行计划，三个动作（Action）有共同的计算路径。





如果内存充足，Spark会自动将中间结果（如RDD4）**缓存**在内存中，供后续动作复用，避免重复计算。如果内存不足，缓存可能会被溢出到磁盘，甚至被清除，导致需要重新计算。








作为高级用户，你可以通过**固定（Pinning）** RDD来显式控制缓存。你可以指定缓存级别（如仅内存、内存和磁盘），给予其更高的缓存优先级，确保其不被轻易移除。这也体现了RDD“弹性”的含义：即使数据丢失，也能根据血统图重新计算。





### 减少Shuffle





Shuffle是昂贵的操作，应尽量减少。






有时，数据本身已经以有利于后续操作的方式分布。例如：
*   如果数据已经按照你想要的键排序，那么 `sortByKey` 操作可能不需要Shuffle。
*   如果数据已经按照 `groupBy` 的键进行了分区，且每个组都完整地位于某个分区内，那么 `groupBy` 也可以避免Shuffle。








你可以通过两种方式利用这一点：
1.  **显式预分区**：使用 `partitionBy` 等方法预先对RDD进行分区。
2.  **隐式优化**：Spark有时足够智能。例如，先进行 `groupByKey`，紧接着对同一个键进行 `sortByKey`，Spark可能只会执行一次Shuffle。




对于 `join` 操作，如果一侧的数据已经按照连接键分区好了，那么这一侧就无需Shuffle。



**关于Shuffle的数据传输**：并非所有宽依赖都需要将所有数据发送到所有节点。例如 `groupBy`，数据只需根据键的哈希值发送到对应的目标节点，传输量是线性的。但像 `distinct` 或 `intersect` 这类操作，可能需要更全局的信息。



## 引入DataFrame

Spark早期只有RDD API，后来因性能等原因引入了DataFrame。






DataFrame的核心思想是针对**结构化数据**进行优化。当数据是同构的（遵循相同的模式）时，可以将其从RDD of Objects（如Python字典）转换为更高效的**DataFrame（即RDD of Rows）**。



### 为何DataFrame更高效？




1.  **列式存储**：数据在内存和磁盘（如Parquet格式）上按列组织。这带来了巨大优势：
    *   **谓词下推**：如果查询不需要某些列，可以直接跳过读取，减少I/O。
    *   **压缩高效**：同列数据类型一致，便于压缩。
2.  **空间节省**：相比存储完整的JSON字符串或Python对象，DataFrame的二进制格式占用内存更少，能容纳更多数据，计算更快。









### 使用DataFrame


创建DataFrame非常方便，Spark可以原生读取JSON、CSV等格式，并**推断（infer）** 模式。当然，如果你已知模式，显式提供会避免扫描开销，效率更高。




```python
# 读取JSON文件为DataFrame
df = spark.read.json("path/to/file.json")
```


有了DataFrame，你可以选择两种查询方式：
1.  **Spark SQL**：使用熟悉的SQL语法。
    ```python
    df.createOrReplaceTempView("people")
    results = spark.sql("SELECT name, age FROM people WHERE age > 20")
    ```
2.  **DataFrame API**：提供一套类似Pandas的链式转换API，适合喜欢编程式操作的用户。
    ```python
    results = df.select("name", "age").filter(df.age > 20)
    ```





DataFrame的类型系统与其他大数据系统（如Avro、Parquet）类似，包含基本类型（整型、布尔型、字符串等）和复杂类型（`struct` 对应JSON对象，`array` 对应数组）。`Map` 类型允许键不是字符串，这是对JSON的扩展。






### DataFrame的执行





DataFrame在物理上仍然由RDD支持。当你编写SQL或DataFrame API代码时，Spark会经过一个复杂的优化器（Catalyst），生成最优的RDD执行计划。这实现了**数据独立性**，用户无需关心底层如何实现。






## Spark SQL 详解





Spark SQL语法是标准SQL的超集，包括 `SELECT`, `FROM`, `WHERE`, `GROUP BY`, `HAVING`, `ORDER BY`, `LIMIT`, `OFFSET` 等。






我们可以将其映射回RDD操作以理解执行：
*   `SELECT`（投影）、`WHERE`（过滤）是窄依赖转换。
*   `GROUP BY`、`ORDER BY`（除非键相同）通常需要Shuffle。
*   `LIMIT` 和 `OFFSET` 在分布式环境下实现起来比较复杂，可能涉及为数据添加索引（如 `zipWithIndex` 转换）再进行过滤。


### 处理嵌套数据





标准SQL是为扁平表设计的，而DataFrame支持嵌套结构（对象、数组）。Spark SQL提供了扩展来处理它们：
*   **点号（.）访问**：使用 `column.nestedField` 访问对象内的字段。
*   **EXPLODE函数**：将数组列“炸开”，为数组中的每个元素生成一行，并复制其他列的值。这实现了非第一范式到第一范式的转换。
*   **LATERAL VIEW**：更强大的展开方式，允许在 `FROM` 子句中展开多个数组列，类似于进行自连接，可以处理多级嵌套。







## 总结



本节课我们一起深入学习了Spark的核心执行机制和高级数据抽象。







我们首先回顾了RDD的窄依赖和宽依赖，理解了Spark如何通过划分**阶段**和进行**Shuffle**来执行作业。我们探讨了**缓存**和**减少Shuffle**等性能优化技巧。


随后，我们引入了**DataFrame**，认识到它对结构化数据的列式存储和高效压缩带来的性能优势。我们学习了如何使用Spark SQL和DataFrame API进行查询，并了解了其类型系统。最后，我们探讨了Spark SQL如何扩展以处理嵌套数据结构。






![](img/2cddd2779ce203202a37adedfb3ca6a8_238.png)

这些知识将帮助你编写出更高效、更优雅的Spark应用程序。