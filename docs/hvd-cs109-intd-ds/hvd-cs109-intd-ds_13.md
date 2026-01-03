# 第六章 data.table

> 原文：[`rafalab.dfci.harvard.edu/dsbook/data.html`](https://rafalab.dfci.harvard.edu/dsbook/data.html)

在这本书中，我们使用 tidyverse 包来展示，因为初学者发现代码易于阅读，这使我们能够专注于数据分析与统计概念。然而，在 R 中处理和分析数据还有其他方法，它们更快，更擅长处理大型对象。例如，**data.table**包是最受欢迎的之一，因此我们在本章中提供了一个非常快速的介绍。对于那些想要了解更多的人来说，有几个在线资源，包括这个介绍¹⁵。

## 6.1 操作数据表

`data.table`是一个独立的包，需要安装。一旦安装，我们然后需要加载它：

```r
library(data.table)
```

我们将提供示例代码，展示**data.table**对第四章中展示的**dplyr**的`mutate`、`filter`、`select`、`group_by`和`summarize`方法的处理。与该章节一样，我们将使用`murders`数据集：

使用**data.table**的第一步是将数据框转换为`data.table`对象，使用`setDT`函数：

```r
murders <-setDT(murders)
```

没有这个初始步骤，下面展示的大多数方法将不会工作。

### 6.1.1 选择

使用**data.table**进行选择的方式与子集矩阵类似。当使用**dplyr**时，我们这样写：

```r
select(murders, state, region)
```

在**data.table**中，我们使用与矩阵中使用的类似记法：

```r
murders[, c("state", "region")] |> head()
#>         state region
#> 1:    Alabama  South
#> 2:     Alaska   West
#> 3:    Arizona   West
#> 4:   Arkansas  South
#> 5: California   West
#> 6:   Colorado   West
```

我们还可以使用`.()` **data.table**记法来提醒 R，括号内的变量是列名，而不是 R 环境中的对象。因此，上述内容也可以这样写：

```r
murders[, .(state, region)] |> head()
#>         state region
#> 1:    Alabama  South
#> 2:     Alaska   West
#> 3:    Arizona   West
#> 4:   Arkansas  South
#> 5: California   West
#> 6:   Colorado   West
```

### 6.1.2 添加列或更改列

我们通过这个例子学习了如何使用**dplyr**的`mutate`函数：

```r
murders <- mutate(murders, rate = total / population * 100000)
```

**data.table**采用一种避免新赋值（通过引用更新）的方法。这有助于处理占用你电脑大部分内存的大型数据集。**data.table** :=`函数使我们能够这样做：

```r
murders[, rate := total / population * 100000]
```

这向表中添加了一个新的列，`rate`。注意，与**dplyr**一样，我们使用了`total`和`population`而没有引号。

我们可以看到新列已被添加：

```r
head(murders)
#>         state abb region population total rate
#> 1:    Alabama  AL  South    4779736   135 2.82
#> 2:     Alaska  AK   West     710231    19 2.68
#> 3:    Arizona  AZ   West    6392017   232 3.63
#> 4:   Arkansas  AR  South    2915918    93 3.19
#> 5: California  CA   West   37253956  1257 3.37
#> 6:   Colorado  CO   West    5029196    65 1.29
```

要定义新的多个列，我们可以使用带有多个参数的`:=`函数：

```r
murders[, ":="(rate = total / population * 100000, rank = rank(population))]
```

### 6.1.3 技术细节：引用与复制

**data.table**包旨在避免浪费内存。因此，如果你复制了一个表，如下所示：

```r
x <- data.table(a = 1)
y <- x
```

`y`实际上引用了`x`，它不是一个新对象：它只是`x`的另一个名称。直到你更改`y`，不会创建新对象。然而，`:=`函数通过引用进行更改，所以如果你更改`x`，不会创建新对象，`y`继续只是`x`的另一个名称：

```r
x[,a := 2]
y
#>    a
#> 1: 2
```

你也可以这样更改`x`：

```r
y[,a := 1]
x
#>    a
#> 1: 1
```

为了避免这种情况，你可以使用`copy`函数，该函数强制创建一个实际的副本：

```r
x <- data.table(a = 1)
y <- copy(x)
x[,a := 2]
y
#>    a
#> 1: 1
```

### 6.1.4 子集

使用**dplyr**，我们这样过滤：

```r
filter(murders, rate <= 0.7)
```

使用 **data.table**，我们再次使用与子集矩阵类似的方法，但 **data.table** 知道 `rate` 指的是列名，而不是 R 环境中的对象：

```r
murders[rate <= 0.7]
#>            state abb        region population total  rate rank
#> 1:        Hawaii  HI          West    1360301     7 0.515   12
#> 2:          Iowa  IA North Central    3046355    21 0.689   22
#> 3: New Hampshire  NH     Northeast    1316470     5 0.380   10
#> 4:  North Dakota  ND North Central     672591     4 0.595    4
#> 5:       Vermont  VT     Northeast     625741     2 0.320    3
```

注意，我们可以将筛选和选择合并为一个简洁的命令。以下是那些比率低于 0.7 的州的名字和比率。

```r
murders[rate <= 0.7, .(state, rate)]
#>            state  rate
#> 1:        Hawaii 0.515
#> 2:          Iowa 0.689
#> 3: New Hampshire 0.380
#> 4:  North Dakota 0.595
#> 5:       Vermont 0.320
```

与 **dplyr** 方法比较：

```r
murders |> filter(rate <= 0.7) |> select(state, rate)
```

## 6.2 练习

1. 加载 **data.table** 包和谋杀数据集，并将其转换为 `data.table` 对象：

```r
library(data.table)
library(dslabs)
data(murders)
murders <- setDT(murders)
```

记住，你可以这样添加列：

```r
murders[, population_in_millions := population / 10⁶]
```

添加一个名为 `rate` 的谋杀率列，其每 10 万人的谋杀率如上面的示例代码所示。

2. 添加一个包含排名的列 `rank`，从最高到最低的谋杀率。

3. 如果我们只想显示州和人口规模，我们可以使用：

```r
murders[, .(state, population)] 
```

在 `murders` 中显示州名和缩写。

4. 你可以这样显示纽约的行：

```r
murders[state == "New York"]
```

你可以使用其他逻辑向量进行筛选。

显示谋杀率最高的前 5 个州。在我们添加谋杀率和排名后，不要更改谋杀数据集，只显示结果。记住，你可以根据 `rank` 列进行筛选。

5. 我们可以使用 `!=` 运算符来删除行。例如，要删除佛罗里达州，我们会这样做：

```r
no_florida <- murders[state != "Florida"]
```

创建一个新的数据框 `no_south`，移除南部地区的州。这个类别中有多少个州？你可以使用 `nrow` 函数来做这件事。

6. 我们还可以使用 `%in%` 进行筛选。因此，你可以这样查看纽约和德克萨斯州的数据：

```r
murders[state %in% c("New York", "Texas")]
```

创建一个新的数据框 `murders_nw`，只包含东北部和西部的州。这个类别中有多少个州？

7. 假设你想要住在东北部或西部 **并且** 谋杀率要低于 1。我们想查看满足这些条件的州的数据。注意，你可以使用逻辑运算符与 `filter` 一起使用。这里有一个例子，我们筛选出东北地区的中小州。

```r
murders[population < 5000000 & region == "Northeast"]
```

确保谋杀数据集已经定义了 `rate` 和 `rank`，并且仍然包含所有州。创建一个名为 `my_states` 的表格，其中包含满足以下两个条件的行：它们位于东北部或西部，谋杀率低于 1。只显示州名、率和排名。

## 6.3 汇总数据

作为例子，我们将使用 `heights` 数据集：

```r
library(dplyr)
library(dslabs)
data(heights)
heights <- setDT(heights)
```

在 **data.table** 中，我们可以在 `.()` 内部调用函数，并且它们将应用于行。所以相当于：

```r
s <- heights |> 
 summarize(average = mean(height), standard_deviation = sd(height))
```

在 **dplyr** 中如下所示：

```r
s <- heights[, .(average = mean(height), standard_deviation = sd(height))]
```

注意，这允许一种紧凑的子集和汇总方式。而不是：

```r
s <- heights |> 
 filter(sex == "Female") |>
 summarize(average = mean(height), standard_deviation = sd(height))
```

我们可以写成：

```r
s <- heights[sex == "Female", .(average = mean(height), standard_deviation = sd(height))]
```

### 6.3.1 多个汇总

在第四章，我们定义了函数：

```r
median_min_max <- function(x){
 qs <- quantile(x, c(0.5, 0, 1))
 data.frame(median = qs[1], minimum = qs[2], maximum = qs[3])
}
```

与 **dplyr** 类似，我们可以在 `.()` 内部调用此函数以获得三个数字摘要：

```r
heights[, .(median_min_max(height))]
#>    median minimum maximum
#> 1:   68.5      50    82.7
```

### 6.3.2 分组后汇总

**data.table** 中的 `group_by` 后跟 `summarize` 与 **dplyr** 中的单行执行相同。我们只需将 `by` 参数添加到根据分类变量的值拆分数据：

```r
heights[, .(average = mean(height), standard_deviation = sd(height)), by = sex]
#>       sex average standard_deviation
#> 1:   Male    69.3               3.61
#> 2: Female    64.9               3.76
```

## 6.4 排序数据框

我们可以使用与过滤相同的方法来排序行。以下是按谋杀率排序的状态：

```r
murders[order(population)] |> head()
#>                   state abb        region population total   rate rank
#> 1:              Wyoming  WY          West     563626     5  0.887    1
#> 2: District of Columbia  DC         South     601723    99 16.453    2
#> 3:              Vermont  VT     Northeast     625741     2  0.320    3
#> 4:         North Dakota  ND North Central     672591     4  0.595    4
#> 5:               Alaska  AK          West     710231    19  2.675    5
#> 6:         South Dakota  SD North Central     814180     8  0.983    6
```

N 要按降序排序表格，我们可以按`population`的负值排序或使用`decreasing`参数：

```r
murders[order(population, decreasing = TRUE)] 
```

### 6.4.1 嵌套排序

同样，我们可以通过包含多个变量来执行嵌套排序

```r
murders[order(region, rate)] 
```

``

## 6.5 练习

对于这些练习，我们将使用**NHANES**数据。

```r
library(NHANES)
data(NHANES)
```

1. 我们将提供一些关于血压的基本事实。首先，让我们选择一个组来设定标准。我们将使用 20 至 29 岁的女性。`AgeDecade`是一个具有这些年龄的类别变量。注意，类别编码为“20-29”，前面有一个空格！使用**data.table**包计算存储在`BPSysAve`变量中的平均收缩压和标准差。将其保存到名为`ref`的变量中。

2. 报告同一组的最大和最小值。

3. 计算女性的平均和标准差，但针对每个年龄组分别计算，而不是像问题 1 中那样选择一个十年为一个组。注意，年龄组由`AgeDecade`定义。

4. 为男性重复练习 3。

5. 对于 40-49 岁的男性，比较在`Race1`变量中报告的种族间的收缩压。将结果表按最低到最高的平均收缩压排序。

* * *

1.  [`cran.r-project.org/web/packages/data.table/vignettes/datatable-intro.html`](https://cran.r-project.org/web/packages/data.table/vignettes/datatable-intro.html)↩︎
