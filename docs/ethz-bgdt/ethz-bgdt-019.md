# 19：宽列存储 (3/4) 📚

![](img/b0c31719dab12e29fce05a2b7945d86e_1.png)

在本节课中，我们将深入学习HBase的物理存储模型，特别是其核心的Key-Value结构、读写流程以及用于实现高吞吐量的LSM树（Log-Structured Merge Tree）架构。我们将从HBase的物理存储单元开始，逐步深入到其内部的数据组织、写入、读取和合并机制。

---

## 概述：HBase的物理存储单元

上一节我们介绍了HBase的逻辑视图，本节中我们来看看其物理存储的核心单元——Key-Value（KV）。

在HBase中，用户看到的是表和行，但物理上存储的是称为Key-Value（KV）的单元。一个KV是存储的最小物理单元。它的键（Key）是一个多维结构，包含了以下信息：
*   **行ID (Row ID)**
*   **列族 (Column Family)**
*   **列限定符 (Column Qualifier)**
*   **版本 (Version)**

这不同于简单的键值存储，后者的键通常是单一维度的。HBase的键是二维的（行和列），并且具有版本控制，这些版本是**全序的**（通过锁机制保证），而不是像最终一致性系统中的向量时钟那样形成有向无环图（DAG）。

KV在物理上被组织在称为“存储（Store）”的单元中，一个Store是特定区域（Region，行的区间）和特定列族的交集。这些KV最终被持久化到HDFS上的HFile中。

---

![](img/b0c31719dab12e29fce05a2b7945d86e_3.png)

## 架构与协调：ZooKeeper的作用

![](img/b0c31719dab12e29fce05a2b7945d86e_5.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_7.png)

HBase的架构与HDFS类似，采用主从（Master-Worker）模式。HMaster是协调者，Region Server是工作节点。

一个关键问题是节点间的协调与心跳检测。早期版本的HBase使用自定义的心跳机制，但这容易引入竞态条件等问题。为了解决这个在分布式系统中反复出现的协调问题，HBase（以及Hadoop生态中的其他系统）采用了**ZooKeeper**。

![](img/b0c31719dab12e29fce05a2b7945d86e_9.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_11.png)

ZooKeeper是一个专为分布式系统提供协调服务（如命名、配置管理、同步）的独立系统。Region Server不再直接向HMaster发送心跳，而是向ZooKeeper注册自己。HMaster通过查询ZooKeeper来获知哪些Region Server是存活的。这种方式更加健壮和通用。

![](img/b0c31719dab12e29fce05a2b7945d86e_13.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_15.png)

---

![](img/b0c31719dab12e29fce05a2b7945d86e_17.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_18.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_19.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_20.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_21.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_22.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_23.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_24.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_25.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_27.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_28.png)

## HFile的内部结构：块与索引

![](img/b0c31719dab12e29fce05a2b7945d86e_30.png)

现在，让我们深入一个Store在HDFS上的持久化文件——HFile。

HFile内部存储了一系列按Key排序的KV。为了提高读取效率，这些KV并非逐个读取，而是被组织成更大的块，称为**HBase块（HBlock）**，默认大小为64KB。

以下是HFile的内部结构：

![](img/b0c31719dab12e29fce05a2b7945d86e_13.png)

*   **数据部分**：由多个HBlock组成，每个HBlock包含一组完整的、有序的KV。
*   **索引部分**：一个内存友好的索引，记录了每个HBlock的键范围（例如，从Key11到Key17）。当需要查找某个键时，首先在内存中加载索引，快速定位到目标键所在的HBlock，然后只需读取那个特定的HBlock，而不是整个HFile。

需要注意的是，HFile作为文件存储在HDFS上，因此它本身又会被分割成多个HDFS块（默认128MB）。一个HDFS块内可能包含许多HBase块。Region Server会尽量通过“短路读取”直接从本地磁盘读取数据，从而绕过HDFS的某些开销，实现高效访问。

![](img/b0c31719dab12e29fce05a2b7945d86e_32.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_34.png)

---

## 写入流程：内存、预写日志与刷新

![](img/b0c31719dab12e29fce05a2b7945d86e_36.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_37.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_39.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_40.png)

HFile是只追加且内部有序的，这引出了一个核心问题：如何实现随机写入和更新？

![](img/b0c31719dab12e29fce05a2b7945d86e_42.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_44.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_45.png)

答案是：**不直接修改HFile**。HBase的写入流程是一个多级缓存和合并的过程。

![](img/b0c31719dab12e29fce05a2b7945d86e_46.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_47.png)

以下是写入数据时涉及的组件：

![](img/b0c31719dab12e29fce05a2b7945d86e_49.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_36.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_51.png)

1.  **写入内存（MemStore）**：当用户执行`Put`操作插入或更新一个KV时，该KV首先被写入Region Server内存中的一个有序数据结构（如跳表或B树），称为**MemStore**。这保证了极低的写入延迟。
2.  **预写日志（Write-Ahead Log, WAL）**：为了保证持久性，在KV被写入MemStore**之前**，它会被先追加写入一个称为**HLog**（或WAL）的文件。HLog按到达顺序记录所有操作。这样，即使服务器崩溃，MemStore中的数据丢失，也能通过重放HLog来恢复。
3.  **刷新到磁盘（Flush）**：当MemStore的大小达到阈值时，其内容会被**刷新（Flush）** 到HDFS，生成一个新的、有序的HFile。由于MemStore中的数据已经有序，刷新过程是**线性时间复杂度O(n)** 的，非常高效。刷新后，MemStore被清空，对应的HLog段可以被安全删除。

![](img/b0c31719dab12e29fce05a2b7945d86e_53.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_54.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_56.png)

---

![](img/b0c31719dab12e29fce05a2b7945d86e_58.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_60.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_61.png)

## 读取流程：合并视图

读取数据时，系统需要提供一个统一的、包含最新数据的数据视图。

![](img/b0c31719dab12e29fce05a2b7945d86e_63.png)

![](img/b0c31719dab12e29f8ce05a2b7945d86e_82.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_65.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_66.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_68.png)

当用户请求读取某个键时，Region Server需要：
*   检查当前的**MemStore**。
*   检查磁盘上该Store对应的所有**HFile**（可能有很多个）。

![](img/b0c31719dab12e29fce05a2b7945d86e_70.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_72.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_74.png)

系统会扫描所有这些位置，收集所有版本的KV，然后根据时间戳返回最新的版本。如果HFile很多，读取性能会下降。

![](img/b0c31719dab12e29fce05a2b7945d86e_76.png)

---

![](img/b0c31719dab12e29fce05a2b7945d86e_78.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_80.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_82.png)

## 文件合并：Compaction与LSM树

![](img/b0c31719dab12e29fce05a2b7945d86e_84.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_85.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_87.png)

为了解决HFile数量膨胀导致的读放大问题，HBase引入了**压缩（Compaction）** 操作。

![](img/b0c31719dab12e29fce05a2b7945d86e_89.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_90.png)

压缩会将多个较小的HFile合并成一个更大的、有序的HFile，并在此过程中清理已删除或过期的数据（旧版本）。合并多个已排序文件的算法也是**线性时间复杂度O(n)** 的（归并排序）。

![](img/b0c31719dab12e29fce05a2b7945d86e_92.png)

这种将数据先写入内存，再顺序刷新到磁盘，并分层合并的存储结构，被称为**日志结构合并树（Log-Structured Merge-Tree, LSM-Tree）**。

以下是LSM-Tree的工作模式，类似于游戏“2048”：

![](img/b0c31719dab12e29fce05a2b7945d86e_94.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_96.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_98.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_100.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_102.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_104.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_94.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_105.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_107.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_108.png)

*   **第0层（L0）**：**MemStore**，活跃的内存缓冲区。
*   **第1层（L1）**：从MemStore刷新产生的**小HFile**。
*   **更高层（L2, L3...）**：由下层文件合并产生的**更大、更老的HFile**。

当某一层积累了一定数量（例如，达到阈值T）的文件时，这些文件会被合并到下一层的一个更大文件中。数据随着时间推移，从上层“沉降”到下层，文件也越来越大。这种结构特别适合**写吞吐量高、读延迟要求相对宽松**的场景（与B+树适用于低延迟读的场景形成对比）。

![](img/b0c31719dab12e29fce05a2b7945d86e_110.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_111.png)

更新和删除在LSM-Tree中也被视为特殊的写入：更新是插入一个带新版本号的新KV；删除是插入一个标记删除的“墓碑（Tombstone）”记录。这些无效数据会在后续的压缩过程中被物理清除。

![](img/b0c31719dab12e29fce05a2b7945d86e_112.png)

---

![](img/b0c31719dab12e29fce05a2b7945d86e_114.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_116.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_118.png)

## 总结

![](img/b0c31719dab12e29fce05a2b7945d86e_120.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_122.png)

本节课中我们一起学习了HBase物理存储的核心机制：

![](img/b0c31719dab12e29fce05a2b7945d86e_124.png)

1.  **物理模型**：数据以多维Key-Value为单元存储，通过Region和Column Family进行分区。
2.  **协调机制**：使用ZooKeeper进行可靠的节点协调，取代了直接的心跳。
3.  **存储格式**：HFile内部由数据块（HBlock）和索引组成，以实现高效的点查。
4.  **写入路径**：写入先到WAL保证持久性，再到MemStore保证速度，最后批量刷新到HFile保证有序性。
5.  **读取路径**：读取需要合并MemStore和多个HFile的视图，返回最新数据。
6.  **合并优化**：通过Compaction合并小文件，控制文件数量，优化读取性能。
7.  **核心架构**：上述流程共同构成了LSM-Tree，这是一种为高吞吐量写入而设计的经典存储结构。

![](img/b0c31719dab12e29fce05a2b7945d86e_126.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_128.png)

![](img/b0c31719dab12e29fce05a2b7945d86e_130.png)

理解这些底层原理，有助于我们更好地设计HBase表结构、配置参数以及诊断性能问题。