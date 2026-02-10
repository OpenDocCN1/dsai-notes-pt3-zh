# 课程3-P10：从MySQL数据库读取数据 📊

![](img/a905c1dc4351e3f636e55858c3b5fdf9_0.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_2.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_3.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_4.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_5.png)

在本节课中，我们将学习如何使用R语言从MySQL数据库中读取数据。MySQL是一种广泛使用的开源关系型数据库，在互联网应用中非常普遍。作为数据科学家，从数据库中提取数据是一项核心技能。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_7.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_8.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_9.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_10.png)

## 概述：MySQL数据库结构

![](img/a905c1dc4351e3f636e55858c3b5fdf9_11.png)

上一节我们介绍了不同数据源的连接方式，本节中我们来看看如何与结构化的数据库进行交互。

MySQL数据库中的数据以层级结构组织。一个数据库服务器可以包含多个**数据库**。每个数据库内部包含一系列**表**，你可以将每个表理解为一个数据框。每个表则由多个**字段**（即列）组成，表中的每一行数据称为一条**记录**。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_13.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_14.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_15.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_16.png)

以下是一个员工数据库的示例结构，它展示了多个相互关联的表：

![](img/a905c1dc4351e3f636e55858c3b5fdf9_17.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_19.png)

```
数据库：员工
├── 表：部门 (departments)
├── 表：员工 (employees)
├── 表：薪资 (salaries)
├── 表：经理 (managers)
└── 表：职称 (titles)
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_21.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_22.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_23.png)

这些表通过共同的ID字段（如员工编号）相互关联，从而可以查询出某个员工所在的部门、薪资、职称以及其部门经理等信息。

## 第一步：安装与设置

在使用RMySQL包之前，需要完成一些安装和配置工作。这个过程会根据你的操作系统有所不同。

以下是安装步骤：

![](img/a905c1dc4351e3f636e55858c3b5fdf9_25.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_26.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_27.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_28.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_29.png)

1.  **安装MySQL数据库**：访问 [MySQL官方网站](https://dev.mysql.com/downloads/) 下载并安装适合你操作系统的MySQL版本。网站上提供了详细的安装指南。
2.  **安装RMySQL包**：在R中安装`RMySQL`包。
    *   在Mac系统上，可以直接使用 `install.packages("RMySQL")`。
    *   在Windows系统上，安装可能稍复杂，需要配置数据库驱动。你可以参考 [RMySQL官方说明](https://cran.r-project.org/web/packages/RMySQL/index.html) 或这份更直观的 [Windows安装指南](https://www.ahschulz.de/2013/07/23/installing-rmysql-under-windows/)。如果遇到问题，请在课程论坛提问。

为了便于教学演示，本节课我们将使用一个公开的、面向网络的MySQL服务器，即加州大学圣克鲁兹分校（UCSC）维护的基因组数据库。这样我们无需在本地安装MySQL即可体验连接过程。

**重要提示**：请勿所有人同时频繁访问该公共服务器，以免造成负载过大。最佳实践是在自己的系统上安装MySQL并进行练习。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_31.png)

## 连接数据库

![](img/a905c1dc4351e3f636e55858c3b5fdf9_33.png)

安装好RMySQL包后，第一步是建立与数据库的连接。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_35.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_36.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_37.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_38.png)

首先，加载RMySQL包，然后使用`dbConnect()`函数。你需要提供数据库类型、用户名、主机地址等信息。对于UCSC的基因组数据库，连接信息如下：

![](img/a905c1dc4351e3f636e55858c3b5fdf9_39.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_40.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_41.png)

```r
library(RMySQL)
# 建立连接
ucscDb <- dbConnect(MySQL(), user="genome", host="genome-mysql.cse.ucsc.edu")
# 为连接分配一个句柄（此处为ucscDb），便于后续操作
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_43.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_44.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_45.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_46.png)

这段代码会打开一个到指定MySQL服务器的连接，并将该连接对象赋值给变量`ucscDb`。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_48.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_49.png)

## 探索数据库与表

![](img/a905c1dc4351e3f636e55858c3b5fdf9_50.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_51.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_52.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_54.png)

成功连接后，我们可以开始探索服务器上有哪些可用的数据库。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_55.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_56.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_57.png)

使用`dbGetQuery()`函数向数据库发送SQL查询命令。下面的命令用于列出所有数据库：

![](img/a905c1dc4351e3f636e55858c3b5fdf9_59.png)

```r
# 执行SQL查询：显示所有数据库
result <- dbGetQuery(ucscDb, "show databases;")
# 断开连接
dbDisconnect(ucscDb)
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_60.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_61.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_62.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_63.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_64.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_65.png)

执行`dbDisconnect()`断开连接非常重要，它会释放服务器资源，并返回`TRUE`确认已断开。`result`变量中将保存所有数据库名称的列表。

我们将聚焦于其中一个名为`hg19`的数据库，它代表人类基因组的第19个版本。我们需要重新连接，并指定要使用的数据库：

![](img/a905c1dc4351e3f636e55858c3b5fdf9_67.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_68.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_69.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_70.png)

```r
# 连接到特定的数据库（hg19）
hg19 <- dbConnect(MySQL(), user="genome", host="genome-mysql.cse.ucsc.edu", db="hg19")
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_71.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_72.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_73.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_74.png)

接下来，查看`hg19`数据库中有哪些表。每个表对应一种特定类型的数据集。

```r
# 列出hg19数据库中的所有表
allTables <- dbListTables(hg19)
length(allTables) # 查看表的数量，可能超过10000个
allTables[1:5] # 查看前5个表的名称
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_76.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_77.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_78.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_79.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_80.png)

## 检查表结构与内容

假设我们对其中一个名为`affyU133Plus2`的表感兴趣。首先，我们可以查看这个表包含哪些字段（列）。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_82.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_83.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_84.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_85.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_86.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_87.png)

```r
# 列出指定表的所有字段（列名）
dbListFields(hg19, "affyU133Plus2")
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_88.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_90.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_91.png)

接着，我们可能想知道这个表有多少行数据。这可以通过发送一个SQL计数查询来实现：

```r
# 查询指定表的记录总数
dbGetQuery(hg19, "select count(*) from affyU133Plus2")
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_93.png)

`select count(*) from 表名` 是一个标准的SQL命令，用于计算表中的总行数。

## 提取数据

![](img/a905c1dc4351e3f636e55858c3b5fdf9_95.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_96.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_97.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_98.png)

要从数据库中获取整个表的数据到R中，可以使用`dbReadTable()`函数。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_99.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_100.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_101.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_102.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_103.png)

```r
# 读取整个表到R中，作为一个数据框
affyData <- dbReadTable(hg19, "affyU133Plus2")
head(affyData) # 查看数据框的前几行
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_105.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_106.png)

**注意**：数据库中的表可能非常庞大，直接读取整个表可能导致R内存不足。因此，更常见的做法是只提取所需的数据子集。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_108.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_109.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_110.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_111.png)

## 提取数据子集

![](img/a905c1dc4351e3f636e55858c3b5fdf9_113.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_114.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_115.png)

为了高效地提取部分数据，我们可以组合使用`dbSendQuery()`和`fetch()`函数。首先，发送一个带条件的SQL查询命令到数据库。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_116.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_117.png)

例如，我们只想提取`mismatches`字段值在1到3之间的所有记录：

![](img/a905c1dc4351e3f636e55858c3b5fdf9_119.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_120.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_121.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_122.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_123.png)

```r
# 发送查询命令到数据库，但不立即取回数据
query <- dbSendQuery(hg19, "select * from affyU133Plus2 where mismatches between 1 and 3")
# 从查询结果中取回数据到R
affyMis <- fetch(query)
# 检查取回数据的mismatches列分位数，确认筛选生效
quantile(affyMis$mismatches)
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_124.png)

如果想先预览少量数据，可以在`fetch()`中指定`n`参数来限制取回的行数。**完成后，务必用`dbClearResult()`清除服务器上的查询结果**。

```r
# 只取回前10行数据预览
affyMisSmall <- fetch(query, n=10)
dim(affyMisSmall) # 检查维度，应为10行
# 清除服务器上的查询结果
dbClearResult(query)
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_126.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_127.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_128.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_129.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_130.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_131.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_132.png)

你可以通过修改SQL查询语句（`select * from 表名 where 条件`）来灵活地选择任何行和列的组合。更多复杂的SQL语法可以参考MySQL官方文档。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_133.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_134.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_135.png)

## 重要注意事项与总结

![](img/a905c1dc4351e3f636e55858c3b5fdf9_137.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_138.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_139.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_140.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_141.png)

在结束操作时，有一个至关重要的步骤：**关闭数据库连接**。这是使用R操作数据库时最常见的疏忽之一。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_143.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_144.png)

```r
# 始终记得在完成数据提取后关闭连接
dbDisconnect(hg19)
```

![](img/a905c1dc4351e3f636e55858c3b5fdf9_145.png)

本节课中我们一起学习了从MySQL数据库读取数据的完整流程：

1.  **安装与准备**：安装MySQL和RMySQL包。
2.  **建立连接**：使用`dbConnect()`函数连接到数据库服务器或特定数据库。
3.  **探索数据**：使用`dbListTables()`、`dbListFields()`和`dbGetQuery()`了解数据库结构和内容。
4.  **提取数据**：使用`dbReadTable()`读取整表，或使用`dbSendQuery()`和`fetch()`组合提取特定子集。
5.  **清理工作**：使用`dbClearResult()`清除查询，并使用`dbDisconnect()`关闭连接。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_147.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_148.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_149.png)

**最后提醒**：
*   对于公共数据库服务器（如本节课示例），请仅使用`SELECT`查询读取数据，**不要**进行插入、删除或修改操作。
*   在实际工作中，应对自己的本地数据库进行练习，避免对生产环境或公共资源造成压力。
*   RMySQL包的帮助文档（vignette）和在线SQL教程是进一步学习的好资源。

![](img/a905c1dc4351e3f636e55858c3b5fdf9_150.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_151.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_152.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_153.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_154.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_155.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_156.png)

![](img/a905c1dc4351e3f636e55858c3b5fdf9_157.png)

通过掌握这些技能，你就能高效地从MySQL数据库中获取所需数据，为后续的数据清洗和分析工作奠定基础。