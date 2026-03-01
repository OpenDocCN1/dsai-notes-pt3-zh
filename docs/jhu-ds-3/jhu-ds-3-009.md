# 009：数据表（data.table）软件包 📊

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_1.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_2.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_3.png)

在本节课中，我们将要学习R语言中的`data.table`软件包。这是一个常用于数据分析的工具，它提供了比标准数据框（data.frame）更快、更高效内存使用的版本。我们将从基本概念开始，逐步学习其创建、操作和高级功能。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_5.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_6.png)

## 概述 📋

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_8.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_9.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_10.png)

`data.table`继承自数据框，因此所有接受数据框的函数通常也能在`data.table`上工作。它使用C语言编写，在数据子集化、分组变量和更新变量方面比标准数据框快得多，内存效率也更高。然而，使用它需要学习一些新的语法。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_12.png)

---

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_14.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_15.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_16.png)

## 创建与查看数据表

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_18.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_19.png)

上一节我们介绍了`data.table`的基本概念，本节中我们来看看如何创建和查看数据表。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_20.png)

加载`data.table`包后，我们可以像创建数据框一样创建数据表。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_22.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_23.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_24.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_25.png)

```r
library(data.table)
DF = data.frame(x=rnorm(9), y=rep(c("a", "b", "c"), each=3), z=rnorm(9))
DT = data.table(x=rnorm(9), y=rep(c("a", "b", "c"), each=3), z=rnorm(9))
```

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_27.png)

查看数据表的前几行，其外观与数据框相似。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_29.png)

我们可以使用`tables()`命令查看内存中所有数据表的信息。这个命令会列出数据表的名称、行数、占用内存大小（MB）、列数以及是否设置了键（key）。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_30.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_31.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_32.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_33.png)

```r
tables()
```

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_35.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_36.png)

---

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_37.png)

## 数据子集化

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_39.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_40.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_41.png)

上一节我们学习了如何创建数据表，本节中我们来看看如何对行和列进行子集化。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_42.png)

对行进行子集化的方式与数据框类似，使用方括号中逗号前的第一个位置。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_44.png)

```r
DT[2, ] # 选择第二行
DT[DT$y=="a", ] # 选择y列等于"a"的行
```

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_45.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_46.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_47.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_48.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_49.png)

当只使用一个索引进行子集化时，`data.table`默认是对行进行操作。

```r
DT[c(2,3)] # 选择第二和第三行
```

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_51.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_52.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_53.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_54.png)

然而，对列进行子集化的方式与数据框不同。`data.table`使用**表达式**来以各种方式汇总数据，而不是简单的列索引。表达式是包含在花括号`{}`内的一组语句。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_56.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_57.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_58.png)

---

## 使用表达式汇总数据

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_60.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_61.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_62.png)

上一节我们看到了列子集化的不同，本节中我们将深入理解如何使用表达式进行数据操作和汇总。

在方括号的第二个参数位置，我们可以传递一个要执行的函数列表，这些函数将应用于以列名命名的变量。注意，我们不需要使用引号。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_64.png)

```r
DT[, list(mean(x), sum(z))] # 计算x的均值和z的总和
DT[, table(y)] # 对y列生成频数表
```

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_65.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_66.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_67.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_68.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_69.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_70.png)

以下是使用表达式进行多步操作的示例：

```r
DT[, {tmp <- (x+z); log2(tmp+5)}]
```
这个表达式首先计算临时变量`tmp = x + z`，然后计算`log2(tmp+5)`并返回结果。

---

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_72.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_73.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_74.png)

## 添加与修改列

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_75.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_76.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_77.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_78.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_79.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_80.png)

`data.table`可以非常快速且高效地添加新列。使用`:=`运算符可以直接在原有数据表上添加列，而无需创建整个数据集的副本，这对于处理大数据集非常有利。

```r
DT[, w:=z^2] # 添加新列w，其值为z的平方
```

但是，需要注意赋值时的引用行为。如果直接将一个数据表赋值给另一个变量，修改原表也会影响新变量，因为它们指向同一内存地址。要创建真正的副本，需要使用`copy()`函数。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_82.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_83.png)

```r
DT2 <- DT # DT2是DT的引用，而非副本
DT[, y:=2] # 修改DT也会影响DT2
DT3 <- copy(DT) # DT3是DT的一个独立副本
```

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_84.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_85.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_86.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_87.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_88.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_89.png)

---

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_90.png)

## 分组操作

我们可以轻松地执行分组汇总操作。例如，首先创建一个二元变量A，然后按A分组计算另一个表达式的均值。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_92.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_93.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_94.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_95.png)

```r
DT[, a:=x>0] # 创建逻辑列a，指示x是否大于0
DT[, mean(x+w), by=a] # 按a分组计算x+w的均值
```
这会在所有`a`为TRUE的行中填入`x+w`在`a=TRUE`组内的均值，在`a`为FALSE的行中填入`a=FALSE`组内的均值。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_96.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_97.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_99.png)

`data.table`提供了一些特殊变量来加速操作。例如，`.N`是一个整数，包含每个分组出现的次数。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_101.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_103.png)

```r
# 假设DT_large是一个包含大量“a“，”b“，”c“的数据表
DT_large[, .N, by=x] # 快速统计每个x值的出现次数
```
这比使用`table(DT_large$x)`等等效操作要快得多。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_104.png)

---

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_106.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_107.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_108.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_109.png)

## 键与快速合并

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_110.png)

`data.table`的一个独特功能是**键**。设置键可以极大地提高数据表的子集化和排序速度，并促进数据表之间的合并。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_112.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_113.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_114.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_115.png)

首先，创建一个数据表并设置键。

```r
DT1 <- data.table(x=rep(c("a", "b", "c"), each=100), y=rnorm(300))
setkey(DT1, x) # 将x列设置为键
```

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_117.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_118.png)

设置键后，可以快速基于键值进行子集化。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_119.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_120.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_121.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_122.png)

```r
DT1["a"] # 快速提取所有x为"a"的行
```

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_124.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_125.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_126.png)

键还可以用于加速数据表的合并（连接）。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_128.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_129.png)

```r
DT2 <- data.table(x=c("a", "b"), z=c(TRUE, FALSE))
setkey(DT2, x)
merge(DT1, DT2) # 基于键x快速合并DT1和DT2
```

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_131.png)

---

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_133.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_134.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_135.png)

## 快速读取数据

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_136.png)

使用`data.table`的`fread()`函数从磁盘读取文件通常比基础的`read.table()`或`read.csv()`快得多，尤其对于大型文件。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_138.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_139.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_140.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_141.png)

```r
# 创建一个大型临时文件并写入数据
DF <- data.frame(x=rnorm(1e6), y=rnorm(1e6))
file <- tempfile()
write.table(DF, file=file, row.names=FALSE, col.names=TRUE, sep="\t", quote=FALSE)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_143.png)

# 使用fread快速读取
system.time(DT <- fread(file))
```
`fread`的读取速度通常显著快于`read.table`。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_144.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_145.png)

---

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_147.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_148.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_149.png)

## 总结与资源

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_150.png)

本节课中我们一起学习了`data.table`软件包的核心功能。

总结来说，`data.table`在速度和内存效率上通常优于数据框，但它需要学习一些新语法，并且在复制数据时需要稍加注意。

该软件包正在快速发展，其开发版本包含了类似`reshape2`包中`melt`和`dcast`功能的实现。更多最新发展和与数据框的详细对比，可以参考以下资源：
*   开发版本与更新：[http://r-datatable.com](http://r-datatable.com)
*   与数据框的详细对比：[https://github.com/Rdatatable/data.table/wiki/...](https://github.com/Rdatatable/data.table/wiki/...) （此处应为原视频中显示的完整URL）

> 本讲稿很大程度上基于Raphael Gottardo和Kevin Uthe放置在GitHub上的优秀笔记。