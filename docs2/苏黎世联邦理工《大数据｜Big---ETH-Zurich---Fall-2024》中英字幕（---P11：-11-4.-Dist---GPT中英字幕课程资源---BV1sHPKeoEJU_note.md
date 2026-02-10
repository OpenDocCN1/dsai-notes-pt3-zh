# 课程 11-4：分布式文件系统 (2/4) 📂

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_0.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_2.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_3.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_4.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_5.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_6.png)

在本节课中，我们将继续学习 Hadoop 分布式文件系统。我们将深入探讨 HDFS 的设计逻辑、核心概念以及其物理实现，特别是文件如何被分割成块（blocks）以及这些块如何分布在集群中。

---

## 逻辑模型：文件与块

上一节我们介绍了 Hadoop 是 Google 文件系统的开源实现。本节中，我们来看看 HDFS 的逻辑模型。

HDFS 的逻辑模型与传统的文件系统类似，它包含目录和文件的层次结构。然而，与对象存储（如 S3）将整个对象作为一个大块存储不同，HDFS 采用**块存储**。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_8.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_10.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_12.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_13.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_15.png)

在 HDFS 中，文件被分割成固定大小的**块（blocks）**。这是为了支持远超单机容量的超大文件（例如 PB 级别），并为后续的并行计算（如 MapReduce 和 Spark）提供更简单的数据抽象层。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_17.png)

核心概念可以表示为：
```
文件 -> 块序列
```
每个文件本质上是一个有序的块序列。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_19.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_21.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_23.png)

---

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_24.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_25.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_26.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_28.png)

## 块大小的设计考量

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_30.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_31.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_32.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_33.png)

那么，HDFS 的块应该是多大呢？这与**吞吐量（throughput）**和**延迟（latency）**的权衡有关。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_35.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_37.png)

想象一下复制大量小文件与复制单个大文件的区别。复制大文件时，数据流是连续的，我们主要受**吞吐量**限制。而复制大量小文件时，需要在每个文件间频繁寻址，大部分时间花在了**等待（延迟）**上，实际传输数据的时间很短。

HDFS 的设计目标是最大化吞吐量，最小化延迟的影响。因此，它的块尺寸远大于本地文件系统（如 4KB）。HDFS 的默认块大小是 **128 MB**。

选择这个大小的原因如下：
1.  **足够大**：使得通过网络传输数据时，大部分时间花在数据传输上，而不是建立连接和寻址上，从而**避免被延迟限制**。
2.  **足够小**：可以均匀地分布在集群的许多机器上，实现良好的负载均衡和并行性。如果块太大（如 5TB），每个机器上的块数会很少，不利于并行处理。

---

## 物理架构：主从模式

理解了逻辑模型后，我们来看看 HDFS 的物理实现。HDFS 采用**集中式架构**，这与 Dynamo 的对等网络不同。

以下是该架构中的核心组件：
*   **NameNode（名称节点）**：作为集群的“大脑”或协调者。它管理文件系统的**命名空间**（目录和文件结构）以及文件到数据块的映射关系。**它本身不存储文件数据**。
*   **DataNode（数据节点）**：作为工作节点。它们负责在本地磁盘上实际存储**数据块**。
*   **客户端（Client）**：用户或应用程序通过与 NameNode 交互来执行文件操作（如创建、读取），然后直接与相应的 DataNode 进行数据传输。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_39.png)

---

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_41.png)

## NameNode 的职责

NameNode 作为中央协调者，主要维护以下元数据：
1.  **文件系统命名空间**：整个目录和文件的树状结构。
2.  **文件到块的映射**：记录每个文件由哪些块（通过块ID标识）按顺序组成。
3.  **块的位置信息**：跟踪每个数据块副本存储在哪些 DataNode 上。默认情况下，每个块会有**三个副本**存储在不同的机器上，以实现容错。

如果某个块的副本数量因机器故障而低于设定值（如从3个变为2个），NameNode 会发起复制指令，在另一台机器上创建新的副本。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_43.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_45.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_47.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_49.png)

---

## DataNode 的职责

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_51.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_52.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_53.png)

DataNode 的职责相对简单：
*   在本地文件系统上存储和检索数据块。
*   定期向 NameNode 发送心跳信号，报告其状态和存储的块列表。
*   执行来自 NameNode 的指令，如块的创建、删除和复制。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_55.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_57.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_58.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_60.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_62.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_64.png)

需要理解的是，在 DataNode 的本地视角，每个 HDFS 块就是一个普通的文件。例如，一个 72MB 的块在本地磁盘上就是一个 72MB 的文件，不会浪费 128MB 的完整块空间。这体现了**数据独立性**——逻辑上的“块”在物理层就是本地文件。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_66.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_67.png)

---

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_69.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_71.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_72.png)

## 问答与深入探讨

在讲解过程中，同学们提出了一些关键问题，帮助我们更深入地理解 HDFS：

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_74.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_75.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_76.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_78.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_80.png)

**关于单点故障**：NameNode 是单点故障吗？是的，这是一个关键问题。如果 NameNode 宕机，整个文件系统将无法访问，因为元数据丢失了。HDFS 通过**Secondary NameNode** 和 **High Availability** 机制来解决这个问题，这将在后续课程中详细讨论。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_82.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_83.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_85.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_87.png)

**HDFS 与 S3 的对比**：为什么有了 S3 还需要 HDFS？两者都是优秀的存储层，但各有侧重。S3 是云服务，易于使用且可扩展。HDFS 通常部署在自有或租用的集群上，其最大优势在于**数据本地性**——计算任务（如 MapReduce）可以直接在存储数据的同一台机器上运行，避免了网络传输开销，从而速度更快。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_89.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_91.png)

**块在本地磁盘的存储**：HDFS 块是如何存储在 DataNode 本地磁盘的？DataNode 机器上的磁盘通常使用 ext4 或 XFS 等标准文件系统格式化。HDFS 块作为普通文件写入这些磁盘。因此，从操作系统层面看，一个 128MB 的 HDFS 块在磁盘上可能由许多个 4KB 的物理磁盘块组成，但这对于 HDFS 用户来说是透明的。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_93.png)

---

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_95.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_97.png)

## 总结

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_99.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_101.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_102.png)

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_104.png)

本节课中我们一起学习了 HDFS 的核心架构。我们了解到：
1.  HDFS 采用**块存储**模型，将大文件分割成固定大小（默认为 128MB）的块，以支持超大文件和并行计算。
2.  其设计通过增大块尺寸来优化**吞吐量**，减少**延迟**的影响。
3.  物理上采用**主从（Master-Slave）架构**，由 NameNode 管理元数据，DataNode 存储实际数据块，并通过多副本（默认3份）机制实现容错。
4.  我们探讨了 HDFS 与 S3 的差异，并指出了 NameNode 单点故障等挑战，为后续课程埋下伏笔。

![](img/b14fe5f2e33f9bbdbb3239aa8689e88f_106.png)

理解 HDFS 的这种以吞吐量为导向、数据分块、集中式元数据管理的设计思想，是掌握整个 Hadoop 生态及其并行计算框架的基础。