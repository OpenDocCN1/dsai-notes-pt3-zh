# 5  data.table

> 原文：[`rafalab.dfci.harvard.edu/dsbook-part-1/R/data-table.html`](https://rafalab.dfci.harvard.edu/dsbook-part-1/R/data-table.html)

1.  R

1.  5  data.table

在这本书中，我们使用 tidyverse 包，主要是因为它们提供了对初学者有益的易读性。这种易读性使我们能够强调数据分析与统计概念。然而，虽然 tidyverse 对初学者友好，但 R 中还有其他更高效的方法，可以更有效地处理更大的数据集。其中一个这样的包是 **data.table**，它在 R 社区中得到了广泛的应用。我们将在本章简要介绍 **data.table**。对于那些想要深入了解的人，有大量的在线资源，包括提到的介绍¹。

## 5.1 精炼数据表

`data.table` 是一个独立的包，需要安装。一旦安装，我们就需要加载它以及我们将使用的其他包：

```r
library(dplyr
library(dslabs)
library(data.table)
```

我们将提供示例代码，展示 **data.table** 对应于 第四章 中展示的 **dplyr** 的 `mutate`、`filter`、`select`、`group_by` 和 `summarize` 的方法。就像那章一样，我们将使用 `murders` 数据集：

使用 **data.table** 的第一步是将数据框转换为 `data.table` 对象，使用 `as.data.table` 函数：

```r
murders_dt <- as.data.table(murders)
```

如果没有这个初始步骤，下面展示的大多数方法将无法工作。

### 5.1.1 列子集

使用 **data.table** 进行选择的方式与子集矩阵类似。当使用 **dplyr** 时，我们写

```r
select(murders, state, region)
```

在 **data.table** 中我们使用

```r
murders_dt, [c("state", "region")] 
```

我们还可以使用 `.()` **data.table** 语法来提醒 R，括号内的变量是列名，而不是 R 环境中的对象。所以上面的代码也可以写成这样：

```r
murders_dt[, .(state, region)] 
```**

### ***5.1.2 添加或转换变量***

**我们通过这个例子学习了如何使用 **dplyr** 的 `mutate` 函数：

```r
murders <- mutate(murders, rate = total / population * 100000)
```

**data.table** 使用一种避免新赋值（通过引用更新）的方法。这可以帮助处理占用你电脑大部分内存的大数据集。**data.table** 的 `:=` 函数允许我们这样做：

```r
murders_dt[, rate := total / population * 100000]
```

这向表中添加了一个新的列，`rate`。注意，就像在 **dplyr** 中一样，我们使用了 `total` 和 `population` 而没有引号。

要定义新的多个列，我们可以使用带有多个参数的 `:=` 函数：

```r
murders_dt, ":="(rate = total / population * 100000, rank = [rank(population))]
```*****

### ***5.1.3 引用与复制***

****data.table** 包旨在避免浪费内存。所以如果你复制了一个表格，就像这样：

```r
x <- data.table(a = 1)
y <- x
```

`y` 实际上是在引用 `x`，它不是一个新对象：`y` 只是 `x` 的另一个名称。除非你改变 `y`，否则不会创建新对象。然而，`:=` 函数通过引用来改变，所以如果你改变 `x`，不会创建新对象，`y` 仍然只是 `x` 的另一个名称：

```r
x[, a := 2]
y
#>        a
#>    <num>
#> 1:     2
```

你还可以这样改变 `x`：

```r
y[, a := 1]
x
#>        a
#>    <num>
#> 1:     1
```

为了避免这种情况，你可以使用 `copy` 函数，该函数强制创建实际的副本：

```r
x <- data.table(a = 1)
y <- copy(x)
x[, a := 2]
y
#>        a
#>    <num>
#> 1:     1
```

请注意，函数 `as.data.table` 会创建正在转换的数据框的副本。然而，如果处理大型数据框，使用 `setDT` 避免这一点是有帮助的：

```r
x <- data.frame(a = 1)
setDT(x)
```

请注意，因为没有创建副本，以下代码不会创建新对象：

```r
x <- data.frame(a = 1)
y <- setDT(x)
```

对象 `x` 和 `y` 引用了相同的数据表：

```r
x[, a := 2]
y
#>        a
#>    <num>
#> 1:     2
```*********

### ***5.1.4 行级子集***

**使用 **dplyr**，我们这样过滤：

```r
filter(murders, rate <= 0.7)
```

使用 **data.table**，我们再次使用类似于子集矩阵的方法，但与 **dplyr** 一样，**data.table** 知道 `rate` 指的是列名，而不是 R 环境中的对象：

```r
murders_dt[rate <= 0.7]
```

注意，我们可以将过滤和选择合并为一个简洁的命令。以下是那些速率低于 0.7 的状态名称和速率。

```r
murders_dt[rate <= 0.7, .(state, rate)]
#>            state  rate
#>           <char> <num>
#> 1:        Hawaii 0.515
#> 2:          Iowa 0.689
#> 3: New Hampshire 0.380
#> 4:  North Dakota 0.595
#> 5:       Vermont 0.320
```

这比 **dplyr** 方法更紧凑：

```r
murders |> filter(rate <= 0.7) |> select(state, rate)
```

*您已准备好做练习 1-7。**********

## ****5.2 总结数据****

***作为一个例子，我们将使用 `heights` 数据集：

```r
heights_dt <- as.data.table(heights)
```

在 **data.table** 中，我们可以在 `.()` 内调用函数，它们将应用于列。因此，相当于：

```r
s <- heights |> summarize(avg = mean(height), sd = sd(height))
```

在 **dplyr** 中是以下内容在 **data.table** 中：

```r
s <- heights_dt, .(avg = [mean(height), sd = sd(height))]
```

请注意，这允许一种紧凑的子集和汇总方式。而不是：

```r
s <- heights |> 
 filter(sex == "Female") |>
 summarize(avg = mean(height), sd = sd(height))
```

我们可以写成：

```r
s <- heights_dtsex == "Female", .(avg = [mean(height), sd = sd(height))]
```

### 5.2.1 多个总结

在 第四章 中，我们定义了以下函数，以允许在 **dplyr** 中进行多列摘要：

```r
median_min_max <- function(x){
 qs <- quantile(x, c(0.5, 0, 1))
 data.frame(median = qs[1], minimum = qs[2], maximum = qs[3])
}
```

在 **data.table** 中，我们通过 `.()` 调用函数来获取三个数字摘要：

```r
heights_dt[, .(median_min_max(height))]
```*

### **5.2.2 分组后总结**

*在 **dplyr** 中的 `group_by` 后跟 `summarize` 在 **data.table** 中一行完成。我们只需添加 `by` 参数，根据分类变量的值将数据拆分为组：

```r
heights_dt, .(avg = [mean(height), sd = sd(height)), by = sex]
#>       sex   avg    sd
#>    <fctr> <num> <num>
#> 1:   Male  69.3  3.61
#> 2: Female  64.9  3.76
```***********

## ****5.3 排序****

***我们可以使用与过滤相同的方法对行进行排序。以下是按谋杀率排序的州：

```r
murders_dt[order(population)]
```

要按降序对表进行排序，我们可以按 `population` 的负值排序或使用 `decreasing` 参数：

```r
murders_dt[order(population, decreasing = TRUE)] 
```

同样，我们可以通过包含多个变量来进行嵌套排序：

```r
murders_dt[order(region, rate)] 
```

*您已准备好做练习 8-12。**********

## *****5.4 练习*****

****1. 加载 **data.table** 包和 `murders` 数据集，并将其转换为 `data.table` 对象：

```r
library(data.table)
library(dslabs)
murders_dt <- as.data.table(murders)
```

记住，您可以这样添加列：

```r
murders_dt[, population_in_millions := population / 10⁶]
```

添加一个名为 `rate` 的 `murders` 列，其每 10 万人谋杀率为上例代码所示。

2. 添加一个包含排名的列 `rank`，从最高到最低谋杀率排序。

3. 如果我们只想显示状态和种群大小，我们可以使用：

```r
murders_dt[, .(state, population)] 
```

显示 `murders` 中的州名称和缩写。

4. 您可以这样显示纽约行：

```r
murders_dt[state == "New York"]
```

您可以使用其他逻辑向量来过滤行。

显示谋杀率最高的前 5 个州的名称。从现在开始，不要更改 `murders` 数据集，只需显示结果。请记住，您可以根据 `rank` 列进行过滤。

5. 我们可以使用 `!=` 运算符删除行。例如，要删除佛罗里达，我们会这样做：

```r
no_florida <- murders_dt[state != "Florida"]
```

创建一个新的数据框`no_south`，移除南部地区的州。这个类别中有多少个州？你可以使用`nrow`函数来完成这个操作。

6. 我们也可以使用`%in%`进行过滤。因此，你可以如下查看纽约和德克萨斯州的数据：

```r
murders_dtstate [%in% c("New York", "Texas")]
```

创建一个新的数据框`murders_nw`，只包含东北部和西部的州。这个类别中有多少个州？

7. 假设你想要住在东北部或西部**并且**谋杀率要低于 1。我们想要查看满足这些选项的州的资料。注意，你可以使用逻辑运算符与`filter`一起使用。以下是一个示例，其中我们过滤以仅保留东北地区的较小州。

```r
murders_dt[population < 5000000 & region == "Northeast"]
```

确保`murders`已经被定义为带有`rate`和`rank`，并且仍然包含所有州。创建一个名为`my_states`的表格，包含满足以下两个条件的行的州：它们位于东北部或西部，谋杀率低于 1。只显示州名、率和排名。

对于第 8-12 题，我们将使用**NHANES**数据。

```r
library(NHANES)
```

8. 我们将提供一些关于血压的基本事实。首先，让我们选择一个组来设定标准。我们将使用 20 至 29 岁的女性。`AgeDecade`是一个具有这些年龄的类别变量。请注意，类别编码为`" 20-29"`，前面有一个空格！使用**data.table**包计算存储在`BPSysAve`变量中的收缩压的平均值和标准差。将其保存到名为`ref`的变量中。

9. 报告同一组的最大和最小值。

10. 计算女性的平均值和标准差，但对于每个年龄组分别计算，而不是像第 8 题那样选择一个十年为一个组。注意，年龄组由`AgeDecade`定义。请注意，类别编码为`" 20-29"`，前面有一个空格！使用**data.table**包计算存储在`BPSysAve`变量中的收缩压的平均值和标准差。将其保存到名为`ref`的变量中。

11. 为男性重复第 10 题的练习。

12. 对于 40-49 岁的男性，比较在`Race1`变量中报告的种族间收缩压。将结果表按最低到最高的平均收缩压排序。*************

* * *

***1.  [`cran.r-project.org/web/packages/data.table/vignettes/datatable-intro.html`](https://cran.r-project.org/web/packages/data.table/vignettes/datatable-intro.html)↩︎****
