# IBM数据工程专业证书 课程11：《使用Spark和Hadoop进行大数据介绍》｜P9：Hadoop简介 🐘

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_0.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_1.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_3.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_5.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_7.png)

在本节课中，我们将要学习Hadoop的基本概念。我们将了解Hadoop是什么，它诞生的背景，以及它如何成为处理海量数据的解决方案。同时，我们也会探讨Hadoop的核心组件及其面临的一些挑战。

## 什么是Hadoop？ 🤔

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_9.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_10.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_11.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_12.png)

Hadoop是一个用于处理海量数据集的开源框架。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_14.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_15.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_17.png)

想象这样一个场景：你拥有1GB的数据需要处理，这些数据可能是客户销售记录或调查问卷的回复。数据存储在你台式机或笔记本电脑的关系型数据库中。这些设备处理这个数据集没有问题，你可以轻松地查询数据。

你的公司业务发展迅速，数据量增长到了10GB，然后是100GB。你获得了一个大客户，例如一家拥有多个数据库的零售商。或者你是一名矿山经理，新的管理决策要求你开始处理来自设备（如前端装载机、挖掘机和运输卡车）的数据。你还有关于环境、土壤、天气、安全以及岩石样本的数据。又或者，你的公司是一家快递服务商，你在整个车队上安装了传感器。你的客户、司机和他们的车辆都开始收集你需要处理的数据。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_19.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_20.png)

当你的数据从1TB增长到10TB，再到100TB时，你很快又接近了本地计算机的处理极限。你可能还需要处理来自Facebook、Twitter、传感器等来源的非结构化数据。公司的高级领导团队希望从关系型数据和非结构化数据中获取洞察，以便做出明智的决策，并且他们希望尽快获得这些信息。你如何完成这个任务？Hadoop可能就是答案。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_21.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_22.png)

## Hadoop的定义与核心思想 💡

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_24.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_25.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_26.png)

在了解Hadoop如何解决问题之前，我们先来理解Hadoop是什么。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_27.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_28.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_29.png)

Hadoop是一套开源程序和规程，可以作为大数据操作的框架。它用于在相互连接的分布式文件系统中处理海量数据。它允许在集群上运行应用程序。**集群**是同时协同工作以执行任务的计算机集合。

需要指出的是，Hadoop不是一个数据库，而是一个可以并行或并发处理进程和作业的生态系统。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_31.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_32.png)

Hadoop经过优化，可以处理海量数据，这些数据可以是结构化的表格数据、非结构化数据（如图像和视频），或者是半结构化数据，并且它使用相对廉价的计算机来实现。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_34.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_35.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_36.png)

## Hadoop的历史背景 📜

在20世纪90年代，进入新千年之际，网络显著增长到数百万个页面和不同结构的数据。需要自动化来帮助同时处理数据结构差异和网络搜索。

1999年，Apache软件基金会作为非营利组织成立。2002年，Doug Cutting和Mike Cafarella创建了Nutch搜索引擎。Nutch的创建基于这样一个理念：它能够同时在不同计算机上处理多个任务，并以分布式方式存储和处理数据，从而更快地返回最相关的搜索结果。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_38.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_39.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_40.png)

2006年，Cutting带着Nutch项目加入了雅虎，该项目被分为网络爬虫和分布式处理两部分。分布式处理部分被称为Hadoop。2008年，雅虎将Hadoop贡献给了Apache软件基金会。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_41.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_42.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_43.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_44.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_45.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_46.png)

## Hadoop的核心组件 ⚙️

如今，数据量已达到PB和EB级别，“大数据”一词被用来解释数据的复杂性。Hadoop拥有用于存储和处理数据的独立组件。术语“Hadoop”通常既指Hadoop的核心组件，也指其相关项目的生态系统。

Hadoop的核心组件包括：

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_48.png)

以下是Hadoop的核心组件列表：

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_49.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_50.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_51.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_52.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_53.png)

*   **Hadoop Common**：Apache Hadoop框架的重要组成部分，指的是支持其他Hadoop模块的通用工具和库的集合。
*   **Hadoop分布式文件系统**：存储组件，简称**HDFS**。它处理在商用硬件上运行的大型数据集。**商用硬件**是低规格、低等级的硬件。单个Hadoop集群可以扩展到数百甚至数千个节点。
*   **MapReduce**：Hadoop的处理单元，是Hadoop框架的重要核心组件。MapReduce通过将大量数据分割成较小的单元并同时处理它们来处理数据。有一段时间，MapReduce是访问存储在HDFS中数据的唯一方式。现在还有其他系统，如Hive和Pig。
*   **YARN**：全称是“Yet Another Resource Negotiator”。YARN是一个非常重要的组件，因为它为Hadoop准备RAM和CPU，以运行存储在HDFS中的批处理、流处理、交互式处理和图形处理数据。

## Hadoop的挑战与不足 ⚠️

开发人员无法忽视Hadoop的缺点。Hadoop包含许多较小的组件，尽管乍一看很高效，但Hadoop在某些简单任务上失败了。

以下是Hadoop不擅长的场景列表：

*   **不擅长处理事务**：由于其缺乏随机访问能力。
*   **不擅长无法并行化的工作或数据内部存在依赖关系时**：当记录1必须在记录2之前处理时，就会产生依赖关系。
*   **不擅长低延迟数据访问**：低延迟允许输入被处理和相应输出之间只有人类无法察觉的微小延迟，从而提供实时特性。这对于利用交易、在线游戏和IP语音等服务的互联网连接尤其重要。
*   **不擅长处理大量小文件**：尽管有相关工作在进行，例如IBM的自适应MapReduce。
*   **不擅长数据量小但计算密集型的场景**。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_55.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_56.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_57.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_58.png)

为了应对Hadoop的不足，在Hadoop之上构建了像Hive这样的新工具。Hive提供了类似SQL的查询，并为用户提供了强大的统计函数。Pig因其多查询方法而流行，该方法减少了数据被扫描的次数。

## 总结 📝

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_60.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_61.png)

本节课中，我们一起学习了Hadoop。我们了解到Hadoop是一个用于处理大数据的开源框架。Hadoop的核心组件是HDFS、MapReduce、YARN和Hadoop Common。同时，我们也认识到Hadoop存在一些缺点，这些缺点在某些场景下可能超过其带来的好处。理解这些核心概念和局限性，是有效利用Hadoop生态系统进行大数据处理的基础。