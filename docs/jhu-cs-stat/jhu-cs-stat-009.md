#  009：R语言入门教程 🚀

![](img/78f3e52ceae981412ac062bfbfba280f_0.png)

在本节课中，我们将学习R语言的基础知识，包括变量赋值、基本运算、向量操作、数据表处理以及如何创建自定义函数。课程内容旨在帮助初学者快速上手R语言，并将其应用于计数和组合数学的计算中。

## RStudio环境介绍 📊

![](img/78f3e52ceae981412ac062bfbfba280f_2.png)

![](img/78f3e52ceae981412ac062bfbfba280f_3.png)

RStudio是R语言的集成开发环境，包含四个主要窗口。

![](img/78f3e52ceae981412ac062bfbfba280f_5.png)

![](img/78f3e52ceae981412ac062bfbfba280f_6.png)

*   左上角是脚本窗口，用于编写和加载R代码。我们首先加载了`stattools`包，这是进行统计和概率分析所需的基础包。
*   左下角是控制台窗口，可以直接输入命令并查看结果。
*   右上角是环境窗口，显示当前已定义的变量及其值。
*   右下角是多功能窗口，可以管理文件、查看图表、安装包和获取帮助。

## 变量赋值与基本运算 ➕

![](img/78f3e52ceae981412ac062bfbfba280f_8.png)

![](img/78f3e52ceae981412ac062bfbfba280f_10.png)

上一节我们熟悉了RStudio界面，本节中我们来看看如何创建变量并进行计算。

![](img/78f3e52ceae981412ac062bfbfba280f_12.png)

![](img/78f3e52ceae981412ac062bfbfba280f_13.png)

![](img/78f3e52ceae981412ac062bfbfba280f_15.png)

在R中，为变量赋值推荐使用箭头操作符 `<-`，而不是等号 `=`。这源于计算机科学中将值“指向”变量的传统。

![](img/78f3e52ceae981412ac062bfbfba280f_17.png)

```r
a <- 3
b <- 5
```

![](img/78f3e52ceae981412ac062bfbfba280f_19.png)

![](img/78f3e52ceae981412ac062bfbfba280f_21.png)

![](img/78f3e52ceae981412ac062bfbfba280f_23.png)

赋值后，输入变量名即可查看其值。

![](img/78f3e52ceae981412ac062bfbfba280f_25.png)

```r
a
# 输出: [1] 3
```

我们可以对变量进行各种基本数学运算。

![](img/78f3e52ceae981412ac062bfbfba280f_27.png)

![](img/78f3e52ceae981412ac062bfbfba280f_28.png)

```r
d <- a + b  # 加法
a - b       # 减法
a * b       # 乘法
a / b       # 除法
a ^ b       # 乘方
exp(a)      # 指数函数
log(a)      # 自然对数
log10(a)    # 以10为底的对数
```

![](img/78f3e52ceae981412ac062bfbfba280f_30.png)

## 工作目录与环境管理 📁

![](img/78f3e52ceae981412ac062bfbfba280f_32.png)

了解如何运算后，我们需要学习如何管理R的工作环境。工作目录是R读取和保存文件的默认位置。

以下是管理环境和目录的常用命令。

![](img/78f3e52ceae981412ac062bfbfba280f_34.png)

![](img/78f3e52ceae981412ac062bfbfba280f_35.png)

![](img/78f3e52ceae981412ac062bfbfba280f_36.png)

*   `getwd()`: 获取当前工作目录的路径。
*   `setwd(“path/to/directory”)`: 设置新的工作目录。
*   `ls()`: 列出当前环境中所有变量的名称。
*   `rm(list = ls())`: 清除当前工作环境中的所有变量。在切换不同项目或问题时，这是一个好习惯。

![](img/78f3e52ceae981412ac062bfbfba280f_38.png)

![](img/78f3e52ceae981412ac062bfbfba280f_40.png)

## 向量的创建与操作 🔢

![](img/78f3e52ceae981412ac062bfbfba280f_42.png)

![](img/78f3e52ceae981412ac062bfbfba280f_43.png)

R语言的核心数据结构之一是向量，它是一组有序的数字列表。`c()` 函数用于“连接”多个值以创建向量。

![](img/78f3e52ceae981412ac062bfbfba280f_45.png)

![](img/78f3e52ceae981412ac062bfbfba280f_46.png)

![](img/78f3e52ceae981412ac062bfbfba280f_48.png)

```r
x <- c(2, 5, 1, 3)
```

![](img/78f3e52ceae981412ac062bfbfba280f_49.png)

![](img/78f3e52ceae981412ac062bfbfba280f_51.png)

除了手动输入，R提供了多种快速创建序列向量的方法。

![](img/78f3e52ceae981412ac062bfbfba280f_53.png)

![](img/78f3e52ceae981412ac062bfbfba280f_55.png)

![](img/78f3e52ceae981412ac062bfbfba280f_57.png)

*   `y <- 1:4`: 创建从1到4的整数序列。
*   `length(x)`: 获取向量`x`的长度（元素个数）。
*   `z <- rep(2, times=10)`: 将数字2重复10次。
*   `seq(1, 10, by=2)`: 创建从1到10，步长为2的序列。
*   `seq(1, 10, length.out=20)`: 创建在1到10范围内均匀分布的20个数字序列。

![](img/78f3e52ceae981412ac062bfbfba280f_59.png)

## 使用数据表与描述性统计 📈

![](img/78f3e52ceae981412ac062bfbfba280f_61.png)

对于结构化数据，`data.table`是一种高效且易于操作的数据结构。首先需要加载`data.table`包。

![](img/78f3e52ceae981412ac062bfbfba280f_63.png)

```r
library(data.table)
```

![](img/78f3e52ceae981412ac062bfbfba280f_65.png)

然后可以创建数据表，并为各列命名。

![](img/78f3e52ceae981412ac062bfbfba280f_67.png)

![](img/78f3e52ceae981412ac062bfbfba280f_69.png)

```r
d <- data.table(
  Tall = c(2, 1, 3, 5),
  Grande = c(2, 1, 3, 5),
  Venti = c(2, 1, 3, 5)
)
```

![](img/78f3e52ceae981412ac062bfbfba280f_71.png)

![](img/78f3e52ceae981412ac062bfbfba280f_72.png)

创建数据表后，我们可以方便地计算各列的描述性统计量。使用`$`符号可以访问数据表中的特定列。

![](img/78f3e52ceae981412ac062bfbfba280f_74.png)

```r
mean(d$Tall)      # 平均值
median(d$Grande)  # 中位数
sd(d$Venti)       # 标准差
min(d$Tall)       # 最小值
max(d$Grande)     # 最大值
sum(d$Venti)      # 求和
```

## 创建自定义函数：排列与组合 ⚙️

![](img/78f3e52ceae981412ac062bfbfba280f_76.png)

![](img/78f3e52ceae981412ac062bfbfba280f_78.png)

最后，我们将学习如何创建自定义函数来解决排列组合问题。在R中，使用`function`关键字定义函数。

排列数公式为：**P(n, x) = n! / (n-x)!**

```r
perm <- function(n, x) {
  factorial(n) / factorial(n - x)
}
```

![](img/78f3e52ceae981412ac062bfbfba280f_80.png)

![](img/78f3e52ceae981412ac062bfbfba280f_82.png)

组合数公式为：**C(n, x) = n! / (x! * (n-x)!)**

```r
comb <- function(n, x) {
  factorial(n) / (factorial(x) * factorial(n - x))
}
```

定义函数后，即可调用它们进行计算。

![](img/78f3e52ceae981412ac062bfbfba280f_84.png)

![](img/78f3e52ceae981412ac062bfbfba280f_85.png)

```r
factorial(10)        # 计算10的阶乘
perm(10, 10)         # 10个元素的全排列数
perm(10, 5)          # 从10个元素中选取5个进行排列
comb(10, 10)         # 从10个元素中选取10个的组合数（仅1种）
comb(10, 3)          # 从10个元素中选取3个的组合数
```

## 总结 ✨

![](img/78f3e52ceae981412ac062bfbfba280f_87.png)

![](img/78f3e52ceae981412ac062bfbfba280f_88.png)

![](img/78f3e52ceae981412ac062bfbfba280f_89.png)

![](img/78f3e52ceae981412ac062bfbfba280f_90.png)

![](img/78f3e52ceae981412ac062bfbfba280f_91.png)

![](img/78f3e52ceae981412ac062bfbfba280f_92.png)

本节课中我们一起学习了R语言的基础操作。我们掌握了如何为变量赋值、进行基本数学运算、管理工作目录、创建和操作向量、使用`data.table`处理数据并计算描述性统计量，最后还学习了如何创建自定义函数来计算排列数和组合数。建议你在练习中使用本课介绍的R脚本，并根据需要修改它以完成作业。