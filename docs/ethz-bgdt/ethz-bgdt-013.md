# 13：分布式文件系统 (4/4) 📚

![](img/0c45e3714c00aeb6c77282fe9841df55_1.png)

在本节课中，我们将要学习HDFS（Hadoop分布式文件系统）如何解决单点故障问题，并了解其高可用性架构和联邦部署模式。我们还将学习如何使用HDFS的命令行工具。

---

![](img/0c45e3714c00aeb6c77282fe9841df55_3.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_5.png)

## 概述

![](img/0c45e3714c00aeb6c77282fe9841df55_7.png)

上一节我们介绍了HDFS的基本架构，并指出了NameNode作为单点故障的问题。本节中，我们来看看HDFS如何通过高可用性（HA）和联邦（Federation）等机制来解决这个问题，并学习如何与HDFS进行交互。

---

## 解决NameNode单点故障 🛡️

NameNode是HDFS的协调者，存储着所有文件的元数据。如果它崩溃，整个系统将无法访问。我们需要一种方法来恢复它。

### NameNode存储的关键信息

NameNode在内存中维护着三种关键信息：

1.  **文件命名空间**：整个目录和文件名的树状结构，包括访问控制等信息。
2.  **文件到块ID的映射**：记录每个文件由哪些数据块（Block ID）组成。
3.  **块位置映射**：记录每个数据块存储在哪些DataNode上。

为了在NameNode崩溃后能够恢复，我们需要持久化存储部分信息。

![](img/0c45e3714c00aeb6c77282fe9841df55_9.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_11.png)

以下是需要持久化的信息及其原因：

![](img/0c45e3714c00aeb6c77282fe9841df55_13.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_15.png)

*   **命名空间文件和块ID映射**：必须持久化。如果丢失，我们将不知道如何将分散的数据块重新组装成完整的文件。
*   **块位置映射**：无需持久化。因为当NameNode重启后，它可以主动向所有DataNode请求`块报告`来重新构建这份映射。

![](img/0c45e3714c00aeb6c77282fe9841df55_17.png)

### 恢复机制：命名空间镜像与编辑日志

![](img/0c45e3714c00aeb6c77282fe9841df55_19.png)

HDFS使用两种文件来持久化元数据：

1.  **FsImage（命名空间镜像文件）**：这是某一时刻完整的命名空间和文件到块ID映射的快照。
2.  **EditLog（编辑日志）**：这是一个只追加的日志，记录了自上一个FsImage创建以来所有对命名空间的更改操作（如创建文件、追加块等）。

恢复过程如下：
1.  NameNode重启后，首先将FsImage加载到内存中，还原到过去的某个状态。
2.  然后按顺序“回放”EditLog中的所有操作，将命名空间更新到最新状态。
3.  最后，等待DataNode发送块报告，重新构建块位置映射。

![](img/0c45e3714c00aeb6c77282fe9841df55_21.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_23.png)

这个过程可能需要**约半小时**，因为EditLog可能非常庞大，回放需要时间。

### 优化：定期创建检查点

![](img/0c45e3714c00aeb6c77282fe9841df55_25.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_26.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_27.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_28.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_29.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_30.png)

为了减少恢复时间，HDFS会定期执行**检查点**操作：
*   将当前的命名空间状态（内存中的信息）写入一个新的FsImage文件。
*   清空旧的EditLog，并开始一个新的EditLog。

![](img/0c45e3714c00aeb6c77282fe9841df55_32.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_33.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_34.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_35.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_37.png)

这样，重启时只需要加载最新的FsImage并回放较短的EditLog，从而加快恢复速度。

![](img/0c45e3714c00aeb6c77282fe9841df55_39.png)

---

![](img/0c45e3714c00aeb6c77282fe9841df55_41.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_42.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_44.png)

## 高可用性（HA）架构 🔄

为了彻底避免冗长的恢复时间，HDFS引入了高可用性架构，使用多个NameNode。

### NameNode的角色

在高可用性设置中，存在三种类型的NameNode进程：

1.  **Active NameNode**：处理所有客户端读写请求的活跃节点。
2.  **Standby NameNode**：备用节点。它同步Active NameNode的状态，但不处理任何请求。当Active节点故障时，它可以被快速提升为新的Active节点。
3.  **Observer NameNode**：观察者节点。它同步Active NameNode的状态，并且**可以处理客户端的读请求**，用于分担读负载。写请求仍然必须由Active NameNode处理。

### 状态同步：QJM（Quorum Journal Manager）

Standby和Observer节点如何与Active节点保持状态同步？它们通过一个名为 **QJM（法定人数日志管理器）** 的组件来同步EditLog。
*   QJM由一组（奇数个）**JournalNode**进程组成。
*   Active NameNode将EditLog条目发送给JournalNode集群。
*   只要大多数（法定人数）JournalNode确认写入，操作就被认为是持久的。
*   Standby/Observer NameNode从JournalNode集群读取EditLog并应用到自己的内存状态中，从而保持同步。

当Active NameNode故障时，Standby NameNode可以立即接管，因为它已经拥有了最新的命名空间状态和块映射信息。

![](img/0c45e3714c00aeb6c77282fe9841df55_46.png)

---

![](img/0c45e3714c00aeb6c77282fe9841df55_48.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_49.png)

## 联邦HDFS（Federation） 🌐

![](img/0c45e3714c00aeb6c77282fe9841df55_50.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_51.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_53.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_54.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_56.png)

随着集群规模增长，单个NameNode的内存可能成为瓶颈。联邦HDFS允许水平扩展命名空间。

### 联邦的核心思想

![](img/0c45e3714c00aeb6c77282fe9841df55_58.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_59.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_60.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_61.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_62.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_63.png)

在联邦架构中，可以有**多个独立的NameNode**，每个NameNode管理文件系统命名空间的一部分（例如，不同的目录子树）。
*   **命名空间卷**：每个NameNode负责的命名空间部分。
*   **共享的DataNode池**：所有DataNode向所有NameNode注册，并存储来自不同命名空间卷的数据块。块存储是共享的。

![](img/0c45e3714c00aeb6c77282fe9841df55_65.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_66.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_68.png)

例如：
*   NameNode-1 管理 `/user` 和 `/data` 目录下的所有文件。
*   NameNode-2 管理 `/project` 目录下的所有文件。
*   所有DataNode同时为这两个NameNode存储数据块。

![](img/0c45e3714c00aeb6c77282fe9841df55_69.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_70.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_71.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_72.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_73.png)

### 联邦与高可用性的结合

![](img/0c45e3714c00aeb6c77282fe9841df55_75.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_76.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_77.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_78.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_79.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_81.png)

可以同时使用联邦和高可用性。即，每个命名空间卷（如负责`/user`的NameNode逻辑组）自身都可以配置为一套Active-Standby-Observer的高可用集群。

---

![](img/0c45e3714c00aeb6c77282fe9841df55_83.png)

## 与HDFS交互：命令行工具 💻

用户可以通过与本地文件系统类似的命令来操作HDFS。

### Hadoop FS Shell

![](img/0c45e3714c00aeb6c77282fe9841df55_85.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_86.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_88.png)

Hadoop提供了一个通用的文件系统Shell命令 `hadoop fs`，它支持多种后端存储。

以下是常用命令示例：

```
# 列出HDFS根目录下的文件 (默认连接到配置的HDFS)
hadoop fs -ls /

![](img/0c45e3714c00aeb6c77282fe9841df55_90.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_91.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_92.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_93.png)

# 在HDFS上创建一个新目录
hadoop fs -mkdir /user/bigdata

![](img/0c45e3714c00aeb6c77282fe9841df55_95.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_96.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_97.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_99.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_101.png)

# 从本地文件系统复制文件到HDFS
hadoop fs -copyFromLocal localfile.txt /user/bigdata/

![](img/0c45e3714c00aeb6c77282fe9841df55_103.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_105.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_106.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_108.png)

# 从HDFS复制文件到本地文件系统
hadoop fs -copyToLocal /user/bigdata/hdfsfile.txt ./

![](img/0c45e3714c00aeb6c77282fe9841df55_110.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_111.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_112.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_113.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_114.png)

# 查看HDFS上的文件内容
hadoop fs -cat /user/bigdata/hdfsfile.txt

![](img/0c45e3714c00aeb6c77282fe9841df55_115.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_116.png)

# 删除HDFS上的文件或目录
hadoop fs -rm -r /user/bigdata/olddir
```

![](img/0c45e3714c00aeb6c77282fe9841df55_118.png)

### 关键特性

*   **统一接口**：`hadoop fs` 命令通过URL scheme（如 `hdfs://`, `file://`, `s3a://`）自动适配不同的文件系统（HDFS、本地FS、Amazon S3等）。
*   **配置默认值**：通常通过配置文件设置默认的文件系统（如 `fs.defaultFS`），这样在命令中就可以直接使用 `/path` 而不需要写完整的 `hdfs://namenode:port/path`。
*   **延迟感知**：由于涉及网络通信，这些命令的响应速度会比操作本地磁盘慢一些。

---

![](img/0c45e3714c00aeb6c77282fe9841df55_120.png)

## 术语差异与演进说明 📝

![](img/0c45e3714c00aeb6c77282fe9841df55_122.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_123.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_124.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_126.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_127.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_128.png)

需要注意的是，不同的分布式文件系统或HDFS的不同版本/发行版中，术语可能有所不同：
*   **GFS (Google File System)** 中使用 **Chunk**（块）、**Chunk Server**（数据节点）、**Master**（名称节点）。
*   **HDFS** 中使用 **Block**（块）、**DataNode**（数据节点）、**NameNode**（名称节点）。
*   块大小的默认值也在演进（如早期64MB，后来128MB，某些云版本可能更大）。

![](img/0c45e3714c00aeb6c77282fe9841df55_130.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_131.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_132.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_133.png)

核心概念是相通的，但具体实现和参数会随着硬件和需求的发展而变化。

![](img/0c45e3714c00aeb6c77282fe9841df55_135.png)

---

## 总结

![](img/0c45e3714c00aeb6c77282fe9841df55_137.png)

![](img/0c45e3714c00aeb6c77282fe9841df55_139.png)

本节课中我们一起学习了HDFS如何解决其架构中的关键单点故障问题。我们探讨了通过**FsImage和EditLog进行恢复**的机制，并介绍了更先进的**高可用性（HA）架构**，该架构利用Active、Standby和Observer NameNode以及QJM来实现快速故障转移。此外，我们还了解了**联邦HDFS**如何通过多个NameNode水平扩展命名空间。最后，我们学习了使用 `hadoop fs` 命令行工具与HDFS及其他兼容的文件系统进行交互的基本方法。理解这些机制对于设计和运维可靠的大数据存储系统至关重要。