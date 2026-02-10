# 大数据课程 - 第18讲：宽列存储（2/4）📊

![](img/bcfe5ca478075bafb77e87320e5bb22e_0.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_2.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_3.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_5.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_6.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_8.png)

在本节课中，我们将要学习宽列存储（Wide Column Stores）的物理层实现，特别是HBase如何构建在HDFS之上，以及数据是如何被分区、存储和管理的。这是整个学期最复杂的部分，我们将逐步拆解，确保你能理解其核心机制。

![](img/bcfe5ca478075bafb77e87320e5bb22e_10.png)

---

![](img/bcfe5ca478075bafb77e87320e5bb22e_12.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_13.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_14.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_15.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_17.png)

## 概述

![](img/bcfe5ca478075bafb77e87320e5bb22e_18.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_19.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_20.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_22.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_24.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_25.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_26.png)

上一节我们介绍了宽列存储的逻辑模型，包括行键、列族和基本的查询操作。本节中，我们来看看其物理层的实现。我们将深入探讨HBase如何利用HDFS进行数据存储，理解“区域”（Region）和“存储”（Store）的概念，并解析数据在磁盘上的实际存储格式（HFile）。

![](img/bcfe5ca478075bafb77e87320e5bb22e_28.png)

---

![](img/bcfe5ca478075bafb77e87320e5bb22e_30.png)

## 物理层：数据分区与架构

![](img/bcfe5ca478075bafb77e87320e5bb22e_32.png)

在物理层面，首要任务是将数据分区，使其能够分布到集群的各个节点上。这与我们在HDFS中切割文件成块（Chunk）的思路一致。

![](img/bcfe5ca478075bafb77e87320e5bb22e_34.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_35.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_36.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_37.png)

最自然的分区方式是基于行（Row）或基于列（Column）。实际上，HBase同时采用了这两种方式。

### 水平分区：区域（Regions）

![](img/bcfe5ca478075bafb77e87320e5bb22e_39.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_40.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_41.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_42.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_43.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_44.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_45.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_46.png)

数据表在水平方向上被分割成多个**区域**。每个区域由一段连续的行键（Row Key）区间定义。
*   **区间表示**：通常表示为 `[起始行键, 结束行键)`，即起始键包含在内，结束键不包含在内。这种约定使得一个区域的结束键正好是下一个区域的起始键，形成无缝衔接。
*   **区域数量**：一个表可以拥有成千上万个区域。

### 垂直分区：列族（Column Families）

![](img/bcfe5ca478075bafb77e87320e5bb22e_48.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_50.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_51.png)

数据表在垂直方向上按**列族**进行分区。列族在创建表时定义，每个列族内的列可以动态添加。

![](img/bcfe5ca478075bafb77e87320e5bb22e_53.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_54.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_55.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_56.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_57.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_58.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_59.png)

### 存储单元：存储（Stores）

![](img/bcfe5ca478075bafb77e87320e5bb22e_60.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_62.png)

一个**区域**与一个**列族**的交集，被称为一个**存储**。你可以将其想象成一个三维数据立方体被同时进行了水平和垂直切割后得到的一个数据块。每个存储是数据管理和持久化的基本单元。

![](img/bcfe5ca478075bafb77e87320e5bb22e_64.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_66.png)

---

![](img/bcfe5ca478075bafb77e87320e5bb22e_68.png)

## HBase 系统架构

![](img/bcfe5ca478075bafb77e87320e5bb22e_70.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_72.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_73.png)

HBase的架构与HDFS类似，采用了主从（Master-Slave）模式。

![](img/bcfe5ca478075bafb77e87320e5bb22e_75.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_76.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_78.png)

### 核心进程

以下是HBase集群中的关键进程：

![](img/bcfe5ca478075bafb77e87320e5bb22e_80.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_82.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_83.png)

*   **HMaster**：运行在协调节点上，通常与HDFS的NameNode在同一台机器。它负责元数据操作（DDL），例如创建/删除表、管理列族等。它还会监控RegionServer的状态并在必要时进行区域重分配。
*   **RegionServer**：运行在数据节点上，与HDFS的DataNode进程在同一台机器。每个RegionServer负责管理分配给它的多个区域（Regions）。它处理客户端的读写请求，是实际进行数据操作的角色。
*   **备份HMaster**：为了防止单点故障，可以配置多个备份HMaster（最多9个），在主HMaster失效时接管工作。

![](img/bcfe5ca478075bafb77e87320e5bb22e_84.png)

### 数据分布与区域分配

![](img/bcfe5ca478075bafb77e87320e5bb22e_86.png)

HMaster负责将表的各个区域分配给集群中的RegionServer。一个RegionServer通常被分配多个区域（实践中可达上千个）。

![](img/bcfe5ca478075bafb77e87320e5bb22e_88.png)

*   **动态分裂**：当一个区域因数据不断写入而变得过大时，负责它的RegionServer会将其分裂成两个新的区域。最初，这两个新区域仍由同一个RegionServer管理。
*   **负载均衡**：HMaster会监控集群负载，并可能将某些区域从一个RegionServer重新分配到另一个，以实现负载均衡。

![](img/bcfe5ca478075bafb77e87320e5bb22e_90.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_92.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_94.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_96.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_97.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_98.png)

**关键点**：区域被“分配”给RegionServer，这是一种管理职责，而**非**数据存储位置。数据实际存储在底层的HDFS中。

---

## 数据存储：HBase 与 HDFS 的协作

理解HBase和HDFS的分层关系至关重要。

### 分层模型

![](img/bcfe5ca478075bafb77e87320e5bb22e_100.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_102.png)

*   **逻辑层**：HBase，提供宽列数据模型和API。
*   **物理层**：HDFS，提供分布式文件存储。
*   **关系**：HBase使用HDFS作为其所有数据的存储介质。每个RegionServer同时也是一个HDFS客户端，会向HDFS读写数据。

![](img/bcfe5ca478075bafb77e87320e5bb22e_104.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_105.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_107.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_109.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_111.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_112.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_113.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_115.png)

### 数据位置与职责转移

![](img/bcfe5ca478075bafb77e87320e5bb22e_117.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_119.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_120.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_121.png)

*   **数据存储**：所有表数据最终以文件（HFile）形式存储在HDFS上，并由HDFS管理其副本（通常为3份）。
*   **职责与数据分离**：当将一个区域的管理职责从一个RegionServer转移到另一个时，**底层HDFS上的数据文件不会移动**。新的RegionServer可以直接通过HDFS访问这些文件。这使职责转移变得非常轻量和快速。
*   **数据本地性**：如果一个RegionServer长期管理某个区域，它写入的HDFS数据块的第一副本通常会落在本地机器（DataNode）上，从而获得最佳读取性能。当区域被重新分配后，新的RegionServer最初可能需要通过网络读取数据，但随着它开始写入新数据，数据本地性会逐渐恢复。

![](img/bcfe5ca478075bafb77e87320e5bb22e_123.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_125.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_127.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_128.png)

**为什么区域不需要多副本？** 因为数据冗余已由HDFS在块级别通过多副本机制保证。RegionServer故障时，只需将其负责的区域重新分配即可，数据不会丢失。

![](img/bcfe5ca478075bafb77e87320e5bb22e_130.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_131.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_132.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_134.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_135.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_137.png)

---

![](img/bcfe5ca478075bafb77e87320e5bb22e_138.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_139.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_141.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_143.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_145.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_147.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_148.png)

## 数据文件格式：HFile

![](img/bcfe5ca478075bafb77e87320e5bb22e_149.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_151.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_153.png)

每个“存储”（Store）的数据在HDFS上体现为一个或多个**HFile**。HFile是存储键值对（Key-Value）序列的二进制文件。

### 从逻辑表到HFile

![](img/bcfe5ca478075bafb77e87320e5bb22e_155.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_157.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_158.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_159.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_160.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_161.png)

逻辑视图中的每个单元格（Cell，由行键、列族、列限定符和时间戳唯一标识）在HFile中对应一个**键值对**。
*   **键（Key）**：单元格的坐标，即 `行键 + 列族 + 列限定符 + 时间戳 + 键类型`。
*   **值（Value）**：单元格的实际内容。

![](img/bcfe5ca478075bafb77e87320e5bb22e_163.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_164.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_166.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_167.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_168.png)

因此，一个HFile本质上是一个按行键排序的键值对序列。

![](img/bcfe5ca478075bafb77e87320e5bb22e_170.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_171.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_173.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_175.png)

### 版本控制与行锁

![](img/bcfe5ca478075bafb77e87320e5bb22e_177.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_179.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_181.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_182.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_184.png)

*   **版本控制**：HFile不仅存储单元格的最新值，还会保留一定数量的历史版本（类似于Git），通过时间戳区分。
*   **行级锁**：HBase通过行级锁保证对同一行的修改是串行化的。这确保了同一行数据版本更新的**全序性**，避免了Dynamo风格的数据版本冲突。

![](img/bcfe5ca478075bafb77e87320e5bb22e_185.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_186.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_188.png)

### HFile 内部结构详解

![](img/bcfe5ca478075bafb77e87320e5bb22e_189.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_190.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_191.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_192.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_194.png)

为了在二进制流中明确每个部分的边界，HFile使用了长度前缀的编码方式。

![](img/bcfe5ca478075bafb77e87320e5bb22e_196.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_197.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_198.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_199.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_200.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_201.png)

#### 键值对（KeyValue）结构

![](img/bcfe5ca478075bafb77e87320e5bb22e_203.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_204.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_206.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_208.png)

每个KeyValue由以下部分组成，按顺序存储：
1.  **键长度（Key Length）**：固定长度（如32位），表示后续“键”部分的字节数。
2.  **值长度（Value Length）**：固定长度（如32位），表示后续“值”部分的字节数。
3.  **键（Key）**：可变长度，具体结构见下文。
4.  **值（Value）**：可变长度，即单元格数据。

![](img/bcfe5ca478075bafb77e87320e5bb22e_210.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_211.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_212.png)

通过先读取两个固定长度的字段，解析器就能知道需要读取多少字节来获取完整的键和值。

#### 键（Key）的内部结构

![](img/bcfe5ca478075bafb77e87320e5bb22e_214.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_216.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_218.png)

键本身也是一个可变长结构，包含：
1.  **行键长度（Row Length）**：固定长度，表示行键的字节数。
2.  **行键（Row Key）**：可变长度。
3.  **列族长度（Column Family Length）**：固定长度，表示列族的字节数。
4.  **列族（Column Family）**：可变长度。
5.  **列限定符（Column Qualifier）**：可变长度。其长度可通过 `键长度 - (行键长度+列族长度+时间戳长度+键类型长度)` 计算得出，因此无需单独存储长度。
6.  **时间戳（Timestamp）**：固定长度（如64位）。
7.  **键类型（Key Type）**：固定长度，用于标识此键值对是插入、删除等操作。

![](img/bcfe5ca478075bafb77e87320e5bb22e_220.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_221.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_222.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_224.png)

**设计启示**：行键和列名的长度应尽可能短，因为它们会作为键的一部分被重复存储无数次，影响存储效率。

![](img/bcfe5ca478075bafb77e87320e5bb22e_226.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_227.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_228.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_230.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_232.png)

---

![](img/bcfe5ca478075bafb77e87320e5bb22e_234.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_236.png)

## 总结

![](img/bcfe5ca478075bafb77e87320e5bb22e_238.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_240.png)

![](img/bcfe5ca478075bafb77e87320e5bb22e_242.png)

本节课我们一起深入学习了宽列存储系统HBase的物理层架构：
1.  我们理解了数据通过**区域**和**列族**进行水平与垂直分区，形成基本管理单元——**存储**。
2.  我们剖析了HBase的**主从架构**，包括HMaster和RegionServer的角色。
3.  我们明确了HBase与HDFS的**分层关系**：HBase是逻辑层，使用HDFS作为物理存储层；数据管理职责与物理存储位置分离。
4.  我们详细解析了数据在磁盘上的存储格式**HFile**，了解了其键值对结构、版本控制机制以及内部二进制编码方式。

![](img/bcfe5ca478075bafb77e87320e5bb22e_244.png)

这部分内容是理解分布式宽列存储如何实现高效、可靠数据管理的核心。下节课我们将继续探讨数据写入、读取和压缩合并等过程。