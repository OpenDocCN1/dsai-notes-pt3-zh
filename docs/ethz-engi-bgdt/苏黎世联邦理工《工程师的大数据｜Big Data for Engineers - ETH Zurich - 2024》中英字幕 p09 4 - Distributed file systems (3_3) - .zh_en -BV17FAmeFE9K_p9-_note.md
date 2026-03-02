# 工程师的大数据：4：分布式文件系统 (3/3) 🗂️

![](img/685fdc5d031e1ea068de43be27eed522_1.png)

![](img/685fdc5d031e1ea068de43be27eed522_2.png)

![](img/685fdc5d031e1ea068de43be27eed522_3.png)

![](img/685fdc5d031e1ea068de43be27eed522_5.png)

![](img/685fdc5d031e1ea068de43be27eed522_7.png)

![](img/685fdc5d031e1ea068de43be27eed522_8.png)

在本节课中，我们将完成对分布式文件系统（特别是HDFS）的探讨。我们将深入了解HDFS的写入协议、副本放置策略、NameNode的高可用性方案，以及如何使用HDFS的命令行工具。

## 回顾与提问

上一节我们介绍了HDFS的读取流程。本节中，我们来看看如何向HDFS写入文件。在开始之前，我们先回顾一个关键问题。

在HDFS中，客户端需要与哪些服务器通信？
*   创建目录时，需要与NameNode通信。
*   获取文件的数据块时，需要与DataNode通信。

因此，答案是：创建目录时与NameNode通信，获取数据块时与DataNode通信。客户端从NameNode获取的是标识数据块的ID，而实际的数据块内容则从DataNode获取。

## HDFS数据模型回顾

让我们快速回顾一下HDFS的数据模型。HDFS采用类似本地文件系统的层次化结构，包含目录和文件。文件内容被组织成固定大小的数据块（Block），默认大小为128MB（可配置）。除了最后一个块可能较小外，所有块大小相同，这样可以避免空间浪费。这些逻辑上的HDFS块在DataNode的本地文件系统中，就是一个个128MB大小的本地文件。

## 写入文件流程 ✍️

现在，我们来看看如何向HDFS写入或创建一个新文件。

![](img/685fdc5d031e1ea068de43be27eed522_10.png)

![](img/685fdc5d031e1ea068de43be27eed522_11.png)

![](img/685fdc5d031e1ea068de43be27eed522_12.png)

![](img/685fdc5d031e1ea068de43be27eed522_13.png)

![](img/685fdc5d031e1ea068de43be27eed522_15.png)

![](img/685fdc5d031e1ea068de43be27eed522_16.png)

**写入流程的核心步骤如下：**

![](img/685fdc5d031e1ea068de43be27eed522_18.png)

![](img/685fdc5d031e1ea068de43be27eed522_20.png)

![](img/685fdc5d031e1ea068de43be27eed522_22.png)

![](img/685fdc5d031e1ea068de43be27eed522_23.png)

1.  **客户端发起创建请求**：客户端首先连接到NameNode，告知其想要创建一个新文件。
2.  **NameNode响应**：NameNode检查文件路径是否合法且不存在，然后回复客户端“可以创建”，并返回第一个数据块的ID以及用于存储该块的三个DataNode的地址（例如IP地址）。这三个地址按与客户端的网络距离排序。
3.  **建立数据管道**：客户端并不直接连接所有三个DataNode，而是只连接距离最近（列表中的第一个）的DataNode。客户端会告知这个DataNode另外两个DataNode的地址，由这个DataNode负责建立到下一个DataNode的写入管道，依此类推，形成一个数据管道。
4.  **传输数据块**：客户端开始通过管道向第一个DataNode发送第一个数据块的数据。数据在网络上被分割成多个小数据包（例如64KB）进行传输。客户端持续发送数据包，并异步接收来自管道的确认信息。
5.  **写入后续块**：第一个块写入完成后，客户端会向NameNode请求下一个块的ID和存储位置，然后重复步骤3和4，建立新的管道并传输数据。
6.  **关闭文件与释放锁**：当所有数据块都发送完毕后，客户端会最后一次连接NameNode，告知文件写入完成，请求“关闭并释放锁”。在锁释放前，其他客户端无法写入该文件（读取可能被允许，但有风险）。锁释放后，其他客户端可以追加写入。
7.  **副本确认**：NameNode在收到关闭请求后，会等待来自DataNode的心跳信息，以确认每个数据块至少有一个副本已成功写入（这称为“最小副本数”，默认为1）。一旦满足条件，NameNode便向客户端确认写入成功。之后，NameNode会在后台异步地确保所有数据块都达到预设的副本数（例如3个）。

![](img/685fdc5d031e1ea068de43be27eed522_25.png)

![](img/685fdc5d031e1ea068de43be27eed522_27.png)

## 副本放置策略 🧱

![](img/685fdc5d031e1ea068de43be27eed522_29.png)

![](img/685fdc5d031e1ea068de43be27eed522_31.png)

![](img/685fdc5d031e1ea068de43be27eed522_33.png)

HDFS通过存储多个数据块副本（Replica）来保证可靠性。默认副本数为3。这些副本是对称的，没有主从之分。

![](img/685fdc5d031e1ea068de43be27eed522_35.png)

![](img/685fdc5d031e1ea068de43be27eed522_37.png)

NameNode负责决定每个数据块的副本放置在哪些DataNode上。其策略旨在平衡可靠性、写入带宽和读取性能。

![](img/685fdc5d031e1ea068de43be27eed522_39.png)

![](img/685fdc5d031e1ea068de43be27eed522_40.png)

![](img/685fdc5d031e1ea068de43be27eed522_42.png)

![](img/685fdc5d031e1ea068de43be27eed522_43.png)

**以下是默认的副本放置策略：**

![](img/685fdc5d031e1ea068de43be27eed522_45.png)

1.  **第一个副本**：放置在运行客户端的同一个节点上（如果该节点也是DataNode）。如果客户端不在集群内，则随机选择一个DataNode。
2.  **第二个副本**：放置在与第一个副本**不同机架**（Rack）的某个DataNode上。
3.  **第三个副本**：放置在与第二个副本**相同机架**的另一个DataNode上。
4.  **更多副本**：如果副本数大于3，则随机放置在集群的其余节点上，但会尽量保证每个节点最多一个副本，每个机架不超过两个副本。

![](img/685fdc5d031e1ea068de43be27eed522_47.png)

![](img/685fdc5d031e1ea068de43be27eed522_49.png)

![](img/685fdc5d031e1ea068de43be27eed522_51.png)

![](img/685fdc5d031e1ea068de43be27eed522_52.png)

![](img/685fdc5d031e1ea068de43be27eed522_53.png)

**策略的直观解释：**
*   将第一个副本放在客户端本地，实现了最高效的写入。
*   将另外两个副本放在另一个机架，而非客户端所在机架，是为了防止整个机架故障导致多个副本同时丢失。这比将两个副本都放在客户端本地机架更安全。
*   这种策略将数据块分散在集群中，有利于负载均衡。

![](img/685fdc5d031e1ea068de43be27eed522_54.png)

![](img/685fdc5d031e1ea068de43be27eed522_56.png)

![](img/685fdc5d031e1ea068de43be27eed522_58.png)

![](img/685fdc5d031e1ea068de43be27eed522_60.png)

## NameNode高可用性 🛡️

![](img/685fdc5d031e1ea068de43be27eed522_62.png)

![](img/685fdc5d031e1ea068de43be27eed522_63.png)

![](img/685fdc5d031e1ea068de43be27eed522_65.png)

![](img/685fdc5d031e1ea068de43be27eed522_66.png)

HDFS的架构存在一个单点故障风险：NameNode。如果唯一的NameNode发生故障，虽然DataNode上的数据块仍然存在，但失去了将数据块重新组装成文件的“地图”（即命名空间和块映射关系），数据将无法访问。

![](img/685fdc5d031e1ea068de43be27eed522_68.png)

**解决方案的演进：**

![](img/685fdc5d031e1ea068de43be27eed522_70.png)

1.  **备份与日志（基础方案）**：
    *   **命名空间镜像**：定期将NameNode内存中的元数据（文件系统命名空间和文件到块ID的映射）保存为一个快照文件，存储到可靠的远程存储（如网络附加存储）。
    *   **编辑日志**：在两次快照之间，将所有对元数据的修改操作顺序记录到编辑日志中。
    *   **恢复过程**：NameNode故障重启后，先加载旧的命名空间镜像，然后按顺序“重放”编辑日志中的所有操作，以恢复最新的元数据状态。最后，通过接收DataNode的心跳来重建块位置映射。这个过程可能耗时较长（例如30分钟）。

![](img/685fdc5d031e1ea068de43be27eed522_72.png)

![](img/685fdc5d031e1ea068de43be27eed522_74.png)

2.  **检查点**：为了控制编辑日志的大小，从而缩短恢复时间，可以定期将编辑日志合并到命名空间镜像中，生成新的、更最新的镜像文件，然后清空或截断编辑日志。

![](img/685fdc5d031e1ea068de43be27eed522_76.png)

3.  **备用NameNode**：这是一个更先进的方案。备用NameNode像“副总统”一样，实时同步主NameNode的所有元数据变更。当主NameNode故障时，备用NameNode可以立即接管工作，实现几乎无中断的故障转移。

4.  **观察者NameNode**：这是最新的演进。观察者NameNode除了具备备用NameNode的故障转移能力外，还可以分担主NameNode的**读请求**负载。客户端可以向观察者NameNode查询元数据，但写操作仍需由主NameNode处理。

5.  **联邦HDFS**：类似于Linux文件系统的分区挂载，可以将HDFS的命名空间划分为多个部分，每个部分由一个独立的NameNode负责。这允许集群水平扩展，以支持更大的文件系统。

## 使用HDFS 🖥️

在实践中，使用HDFS与使用本地文件系统非常相似，主要通过命令行工具。

**基本命令格式为：**
```bash
hadoop fs -<command> [arguments]
```
常用的命令与Linux命令类似：

![](img/685fdc5d031e1ea068de43be27eed522_78.png)

![](img/685fdc5d031e1ea068de43be27eed522_79.png)

![](img/685fdc5d031e1ea068de43be27eed522_80.png)

![](img/685fdc5d031e1ea068de43be27eed522_81.png)

![](img/685fdc5d031e1ea068de43be27eed522_82.png)

![](img/685fdc5d031e1ea068de43be27eed522_83.png)

![](img/685fdc5d031e1ea068de43be27eed522_84.png)

![](img/685fdc5d031e1ea068de43be27eed522_86.png)

以下是常用命令示例：
*   `hadoop fs -ls <path>`：列出目录内容。
*   `hadoop fs -cat <file>`：显示文件内容。
*   `hadoop fs -mkdir <path>`：创建目录。
*   `hadoop fs -rm <path>`：删除文件/目录。
*   `hadoop fs -put <local_src> <hdfs_dst>`：从本地文件系统上传文件到HDFS。
*   `hadoop fs -get <hdfs_src> <local_dst>`：从HDFS下载文件到本地。

![](img/685fdc5d031e1ea068de43be27eed522_88.png)

需要注意的是，由于涉及网络通信，HDFS命令的延迟会比本地命令高，通常会有1-2秒的等待时间。

## 相关工具与术语对照 🔧

还有一些工具常与HDFS配合使用：
*   **Apache Flume**：用于高效地收集、聚合和移动大量日志数据到HDFS。
*   **Apache Sqoop**：用于在HDFS和关系型数据库之间高效地传输批量数据。

![](img/685fdc5d031e1ea068de43be27eed522_90.png)

![](img/685fdc5d031e1ea068de43be27eed522_91.png)

![](img/685fdc5d031e1ea068de43be27eed522_92.png)

![](img/685fdc5d031e1ea068de43be27eed522_93.png)

最后，了解不同系统间的术语对照有助于阅读相关文献：
*   HDFS中的 **Block** 在GFS中称为 **Chunk**。
*   HDFS中的 **NameNode** 在GFS中称为 **Master**。
*   HDFS中的 **DataNode** 在GFS中称为 **Chunk Server**。
*   HDFS中的 **命名空间镜像** 在GFS中称为 **检查点镜像**。
*   HDFS中的 **编辑日志** 在GFS中称为 **操作日志**。

![](img/685fdc5d031e1ea068de43be27eed522_95.png)

## 总结

![](img/685fdc5d031e1ea068de43be27eed522_97.png)

本节课中，我们一起深入学习了HDFS的核心机制。我们掌握了HDFS写入文件的完整流程，理解了其通过数据管道高效传输数据的原理。我们探讨了副本放置策略如何权衡性能与可靠性。针对NameNode的单点故障问题，我们回顾了从备份恢复、检查点到备用NameNode和观察者NameNode的演进解决方案。最后，我们学习了如何使用熟悉的命令行工具与HDFS进行交互，并了解了一些相关的生态工具。

![](img/685fdc5d031e1ea068de43be27eed522_99.png)

至此，我们对分布式文件系统HDFS的讨论就告一段落了。接下来，我们将开始学习如何存储和表示数据。