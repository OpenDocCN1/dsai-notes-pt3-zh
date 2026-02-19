# 28：MapReduce (3/3) 🧩

在本节课中，我们将继续并完成关于 MapReduce 的讨论，然后转向 Spark。我们将学习如何将不同类型的数据转换为键值对，探索更多 MapReduce 的应用实例，并深入理解其内部机制，如组合器函数和任务调度。

---

![](img/ca8291cba9ab650efd47a56c5ffb34f9_1.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_3.png)

## 数据输入格式与键值对转换

![](img/ca8291cba9ab650efd47a56c5ffb34f9_5.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_6.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_7.png)

上一节我们介绍了 MapReduce 的基本模型。本节中我们来看看如何将现实世界的数据适配到这个模型中。

MapReduce 的输入、中间结果和输出都是**键值对**的集合。然而，现实中的数据并不总是这种格式，因此我们需要将其转换为键值对。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_9.png)

以下是几种常见的转换方式：

![](img/ca8291cba9ab650efd47a56c5ffb34f9_11.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_12.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_14.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_16.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_17.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_19.png)

*   **文本文件**：可以将文本的每一行作为一个键值对。通常，键是**行偏移量**（即该行之前的所有字符数），值是整行文本内容。
*   **分隔符文件**：可以使用特定分隔符（如逗号、制表符）来分隔每一行。分隔符左侧的部分作为键（字符串），右侧部分作为值。

## MapReduce 应用实例

![](img/ca8291cba9ab650efd47a56c5ffb34f9_21.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_23.png)

现在，我们通过几个具体例子来看看如何使用 MapReduce 执行常见操作。

### 单词计数 📊

![](img/ca8291cba9ab650efd47a56c5ffb34f9_25.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_27.png)

目标：统计文档中每个单词的出现次数。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_29.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_30.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_31.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_32.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_33.png)

*   **Map 函数**：将每一行文本分割成单词（分词）。对于每个单词，输出一个中间键值对，其中**键是单词**，**值是 1**。
    *   代码示例（伪代码）：`map(line) -> for each word in line: emit(word, 1)`
*   **Reduce 函数**：接收同一个单词对应的所有值（即一堆 1），将它们**求和**。
    *   代码示例（伪代码）：`reduce(word, list_of_ones) -> emit(word, sum(list_of_ones))`

![](img/ca8291cba9ab650efd47a56c5ffb34f9_35.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_36.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_38.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_39.png)

这样，最终输出就是每个单词及其总出现次数。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_41.png)

### 数据筛选（选择） 🔍

![](img/ca8291cba9ab650efd47a56c5ffb34f9_43.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_44.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_45.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_46.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_47.png)

目标：根据给定的条件（谓词）过滤数据行。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_49.png)

*   **Map 函数**：对每一行应用谓词判断。如果条件为真，则原样输出该键值对；如果为假，则不输出。
*   **Reduce 函数**：使用**恒等函数**，即直接输出接收到的键值对，不做任何改变。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_51.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_52.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_53.png)

这实质上实现了关系代数中的**选择**操作（类似于 SQL 中的 `WHERE` 子句）。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_55.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_57.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_59.png)

### 数据投影 📏

![](img/ca8291cba9ab650efd47a56c5ffb34f9_61.png)

目标：从结构化的数据行（例如 JSON 对象）中选取特定的字段。

*   **Map 函数**：
    1.  将输入的字符串（如 JSON 行）**解析**为程序可操作的对象。
    2.  从对象中**选取**所需的字段。
    3.  将结果**序列化**回字符串并输出。
*   **Reduce 函数**：同样使用**恒等函数**。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_63.png)

这实现了关系代数中的**投影**操作（类似于 SQL 中的 `SELECT` 特定列）。选择和投影操作在 MapReduce 中成本较低，因为它们通常不需要 Shuffle 阶段。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_65.png)

## 组合器函数：优化网络传输 🚀

在单词计数的例子中，Map 阶段会为每个单词生成大量 `(word, 1)` 的中间结果，导致 Shuffle 阶段网络传输量巨大。为了优化，我们可以使用**组合器函数**。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_67.png)

*   **作用**：在 Map 阶段本地提前聚合中间结果，减少需要通过网络传输的数据量。
*   **原理**：组合器在 Map 任务输出到磁盘前或内存刷新时被调用，它将多个具有相同键的中间值合并为更少的键值对。
*   **关键要求**：为了不改变最终结果，组合器函数必须是**可交换的**和**可结合的**。常见的满足条件的操作包括求和、求最大值、最小值等。
*   **使用方式**：通常，如果 Reduce 函数使用的聚合操作（如加法 `+`）满足交换律和结合律，那么可以直接将 Reduce 函数作为组合器使用。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_69.png)

这种“尽早计算以减少数据量”的思想，在数据库系统中称为**下推优化**。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_71.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_73.png)

## MapReduce API 与实现细节 ⚙️

![](img/ca8291cba9ab650efd47a56c5ffb34f9_75.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_77.png)

MapReduce 原生使用 Java 实现，但也支持通过标准输入/输出流使用其他语言（如 Python）。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_79.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_81.png)

以下是核心组件的 Java 接口概念：

![](img/ca8291cba9ab650efd47a56c5ffb34f9_83.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_84.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_86.png)

*   **Map 函数**：接收一个输入键值对，可以输出零个、一个或多个中间键值对。
*   **Reduce 函数**：接收一个键和该键对应的所有值的列表，可以输出零个、一个或多个最终键值对。
*   **作业配置**：用户需要指定 Map 类、Reduce 类、输入路径、输出路径等。若要使用组合器，则额外设置 Combiner 类。

需要避免使用“Mapper”、“Reducer”这类模糊术语，而应使用更精确的概念：

*   **Map 函数 / Reduce 函数 / Combiner 函数**：指代具体的数学或编程函数。
*   **Map 任务 / Reduce 任务**：指顺序执行 Map/Reduce 函数处理一批数据的工作单元。
*   **Map 槽位 / Reduce 槽位**：指集群中用于执行任务的 CPU（虚拟）核心。一个槽位依次顺序执行分配给它的多个任务。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_88.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_89.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_91.png)

任务由集群动态调度给空闲的槽位执行，以此实现并行。通常，Map 任务数量远多于 Map 槽位数，以实现负载均衡。对于 Reduce 任务，常见的经验配置是每个 Reduce 槽位对应 0.95 或 1.75 个任务，以优化集群利用率。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_93.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_95.png)

## 一个棘手的问题：Split 与 HDFS Block 的错位 🔧

![](img/ca8291cba9ab650efd47a56c5ffb34f9_97.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_98.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_99.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_100.png)

MapReduce 的输入被划分为 **Split**，而 HDFS 中的数据存储在 **Block** 中。两者定义不同：

![](img/ca8291cba9ab650efd47a56c5ffb34f9_102.png)

*   **HDFS Block**：是固定大小的数据块（如 128MB），切割点不考虑数据内容。
*   **Split**：是逻辑上的记录集合，包含完整的键值对。

![](img/ca8291cba9ab650efd47a56c5ffb34f9_104.png)

![](img/ca8291cba9ab650efd47a56c5ffb34f9_106.png)

因此，一个 Split 中的最后一个（或第一个）记录可能会跨越两个 HDFS Block。这意味着，处理某个 Split 的 Map 任务在读取完本地 Block 后，可能还需要从另一个节点（远程或本地）读取下一个 Block 的开头部分，以获取完整的记录。这是 MapReduce 框架在实现时需要处理的一个工程挑战。

---

![](img/ca8291cba9ab650efd47a56c5ffb34f9_108.png)

本节课中我们一起学习了如何将数据适配到 MapReduce 模型，实现了计数、筛选和投影操作，认识了用于优化传输的组合器函数，并剖析了 MapReduce 的 API 设计、任务调度原理以及底层数据划分的细节。这些知识为我们理解大规模分布式数据处理奠定了基础。