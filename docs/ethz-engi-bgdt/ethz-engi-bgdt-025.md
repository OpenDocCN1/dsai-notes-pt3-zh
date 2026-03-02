#  025：Spark (4/5) - 数据框架与Spark SQL 🚀

![](img/0523b274af023a6c51cb198c8d8dcf59_1.png)

在本节课中，我们将完成Spark章节的学习，并开始探讨数据框架（DataFrames）和Spark SQL。我们将了解为何需要这些概念，以及它们如何使大数据处理变得更高效、更易用。

---

## 课程互动与回顾

首先，我们通过一个互动问题来回顾之前的知识。在MapReduce和Spark中，我们讨论了任务（Task）与可用计算槽位（Slot）的数量关系。一个简单的方法是每个槽位分配一个任务。例如，有1000个槽位就调度1000个任务。但这种方法存在一个问题：由于不同任务完成时间不同，速度快的槽位在完成后会空闲，而整个作业需要等待最慢的任务完成。因此，我们通常希望任务数量多于槽位数量（例如，1000个槽位，5000个任务），这样能更好地平衡负载，提高整体效率。

---

![](img/0523b274af023a6c51cb198c8d8dcf59_3.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_5.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_7.png)

## Spark核心概念回顾

![](img/0523b274af023a6c51cb198c8d8dcf59_9.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_10.png)

上一节我们介绍了Spark的基本模型。现在我们来快速回顾一下。

与仅包含Map和Reduce两阶段的MapReduce不同，Spark更为通用。
1.  Spark可以处理任意类型的集合，而不仅仅是键值对。
2.  Spark的计算过程由一个**有向无环图（DAG）**表示，图中的每个节点称为一个**弹性分布式数据集（RDD）**，它是分布在集群中的不可变数据集合。

![](img/0523b274af023a6c51cb198c8d8dcf59_12.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_14.png)

Spark采用**惰性求值**。只有当需要某个RDD的结果（即触发一个**动作**，如保存或打印）时，才会计算整个依赖链。

![](img/0523b274af023a6c51cb198c8d8dcf59_16.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_17.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_19.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_21.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_23.png)

在物理执行层面，Spark会进行优化。当连续的**转换**操作（如`map`、`filter`）之间没有数据混洗（Shuffle）需求时（即**窄依赖**），它们会被合并到一个**阶段（Stage）**中。这样，数据可以在每个分区内被连续处理，中间结果无需物化，从而提升效率。

![](img/0523b274af023a6c51cb198c8d8dcf59_25.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_26.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_28.png)

相反，当操作需要数据混洗时（如`groupBy`、`sort`，即**宽依赖**），就会产生新的阶段。混洗开销很大，但有时可以避免，例如，如果输入数据已经按照后续操作所需的方式进行了预分区。

![](img/0523b274af023a6c51cb198c8d8dcf59_30.png)

---

## 性能优化：持久化RDD

![](img/0523b274af023a6c51cb198c8d8dcf59_32.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_34.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_35.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_36.png)

考虑以下场景：我们有一个复杂的RDD依赖图，需要从图中三个不同的RDD触发动作（例如，写入HDFS、打印到屏幕、计数）。如果每次动作都从头计算其所有上游依赖，效率会很低，因为许多中间计算是重复的。

这里的瓶颈在于，多个动作共享同一个上游RDD。解决方案是利用RDD的**弹性**特性：我们可以将关键的中间RDD**持久化**在内存或磁盘中。

![](img/0523b274af023a6c51cb198c8d8dcf59_38.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_40.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_41.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_43.png)

在代码中，你可以调用`persist()`或`cache()`方法来标记一个RDD，请求Spark保留其计算结果。这样，当后续动作需要该RDD时，Spark可以直接复用已存储的数据，而无需重新计算。即使内存不足，Spark也会优先处理，最坏情况也只是回退到重新计算，而不会导致作业失败。

![](img/0523b274af023a6c51cb198c8d8dcf59_45.png)

---

## 引入数据框架与Spark SQL

尽管RDD API功能强大，但在处理结构化或半结构化数据（如JSON）时，编写复杂的转换函数（尤其是涉及Lambda表达式和嵌套数据操作）会变得非常繁琐且难以阅读和维护。

这引出了**数据框架（DataFrame）**的概念。DataFrame是一种以**行**为单位的分布式数据集合，但每一行都具有相同的**模式（Schema）**。这本质上就是一个带有列名和类型的表。

使用DataFrame带来两大优势：
1.  **存储高效**：数据以列式格式（如Parquet）存储。同列数据具有相同类型，可以紧密排列，无需重复存储字段名，相比存储一堆JSON对象节省大量内存。
2.  **编程高效**：我们可以使用熟悉的**SQL**语言或**DataFrame API**来操作数据，这比编写复杂的RDD转换函数直观得多。

Spark可以自动从多种数据源（如CSV、JSON Lines）推断模式并创建DataFrame。对于Parquet或关系数据库（通过JDBC）等本身包含模式的数据源，读取速度更快。

---

![](img/0523b274af023a6c51cb198c8d8dcf59_47.png)

## Spark SQL 与执行优化

![](img/0523b274af023a6c51cb198c8d8dcf59_49.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_51.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_53.png)

使用Spark SQL时，你只需编写标准的SQL语句（`SELECT ... FROM ... WHERE ... GROUP BY ... ORDER BY ...`）。Spark会在底层自动将其转换为优化的RDD操作执行计划。

例如，考虑以下查询：
```sql
SELECT country, COUNT(*) as cnt
FROM people
WHERE age > 18
GROUP BY country
HAVING cnt > 100
ORDER BY country
```
在这个查询中：
*   `WHERE`子句是窄转换，不会引起混洗。
*   `GROUP BY`和`ORDER BY`都可能引起混洗。但是，由于它们都是按`country`字段操作，Spark可以优化：在执行`GROUP BY`将相同国家的数据聚集到一起后，数据实际上已经按照`country`分区和排序了。因此，后续的`ORDER BY country`可能完全不需要额外的混洗操作。这是利用预分区避免不必要混洗的典型例子。

---

![](img/0523b274af023a6c51cb198c8d8dcf59_55.png)

## 数据类型与局限

![](img/0523b274af023a6c51cb198c8d8dcf59_57.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_59.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_61.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_62.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_63.png)

DataFrame支持丰富的数据类型，包括基本类型（整型、字符串、布尔型等）和复杂类型（数组、结构体）。这些类型与其他系统（如Python、Java、JSON Schema）中的类型有直接的对应关系，学习起来并不陌生。

![](img/0523b274af023a6c51cb198c8d8dcf59_65.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_66.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_67.png)

尽管DataFrame和Spark SQL非常强大，但它们并非万能。它们主要针对结构化或半结构化数据的批处理查询进行了优化。对于某些复杂的、非结构化的数据处理逻辑，或者需要更细粒度控制的场景，可能仍需回归到RDD API。

---

## 总结

![](img/0523b274af023a6c51cb198c8d8dcf59_69.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_71.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_73.png)

本节课中我们一起学习了：
1.  **任务调度优化**：通过设置多于槽位数量的任务来平衡负载。
2.  **Spark执行模型回顾**：包括RDD、DAG、惰性求值、阶段划分以及窄依赖与宽依赖。
3.  **RDD持久化**：如何通过缓存中间结果来避免重复计算，提升多作业性能。
4.  **数据框架（DataFrame）的引入**：将其视为有模式的分布式表格，带来了存储和编程效率的双重提升。
5.  **Spark SQL**：使用声明式的SQL语言进行数据查询，Spark会自动进行优化（如利用预分区减少混洗）。
6.  **数据类型**：了解了DataFrame支持的类型系统及其与其他编程语言的对应关系。

![](img/0523b274af023a6c51cb198c8d8dcf59_75.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_76.png)

![](img/0523b274af023a6c51cb198c8d8dcf59_78.png)

通过引入DataFrame和SQL接口，Spark使得大规模结构化数据处理变得更加高效和易于上手，同时其底层依然基于灵活且强大的RDD模型。