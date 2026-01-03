# 4  The tidyverse

> 原文：[`rafalab.dfci.harvard.edu/dsbook-part-1/R/tidyverse.html`](https://rafalab.dfci.harvard.edu/dsbook-part-1/R/tidyverse.html)

1.  R

1.  4  The tidyverse

到目前为止，我们通过重新排序和通过索引进行子集化来操作向量。然而，一旦我们开始更高级的分析，数据存储的首选单位不是向量，而是数据框。在本章中，我们将学习如何直接与数据框一起工作，这极大地促进了信息的组织。我们将在这本书的大部分内容中使用数据框。我们将关注一种特定的数据格式，称为*tidy*，以及一组特别有助于处理*tidy*数据的包，称为*tidyverse*。

我们可以通过安装和加载**tidyverse**包一次性加载所有 tidyverse 包：

```r
library([tidyverse](https://tidyverse.tidyverse.org))
```

本书中我们将学习如何实现 tidyverse 方法，但在深入细节之前，在本章中我们介绍了一些最广泛使用的 tidyverse 功能，从用于操作数据框的**dplyr**包和用于处理函数的**purrr**包开始。请注意，tidyverse 还包括一个绘图包**ggplot2**，我们将在本书数据可视化部分的第八章中介绍，还有在第六章中讨论的**readr**包以及其他许多包。在本章中，我们首先介绍*tidy 数据*的概念，然后展示我们如何使用 tidyverse 以这种格式处理数据框。

## 4.1 整洁数据

我们说一个数据表处于*tidy*格式，如果每一行代表一个观察结果，而列代表每个这些观察结果可用的不同变量。`murders`数据集是一个整洁数据框的例子。

```r
#>        state abb region population total
#> 1    Alabama  AL  South    4779736   135
#> 2     Alaska  AK   West     710231    19
#> 3    Arizona  AZ   West    6392017   232
#> 4   Arkansas  AR  South    2915918    93
#> 5 California  CA   West   37253956  1257
#> 6   Colorado  CO   West    5029196    65
```

每一行代表一个州，五个列中的每一个提供与这些州相关的不同变量：名称、缩写、地区、人口和谋杀总数。

要了解相同的信息可以以不同的格式提供，请考虑以下示例：

```r
#>       country year fertility
#> 1     Germany 1960      2.41
#> 2 South Korea 1960      6.16
#> 3     Germany 1961      2.44
#> 4 South Korea 1961      5.99
#> 5     Germany 1962      2.47
#> 6 South Korea 1962      5.79
```

这个 tidy 数据集提供了两个国家在多年间的生育率。这是一个 tidy 数据集，因为每一行代表一个观察结果，有三个变量：国家、年份和生育率。然而，这个数据集最初以另一种格式提供，并为**dslabs**包进行了重塑。最初，数据是以以下格式提供的：

```r
#>       country 1960 1961 1962
#> 1     Germany 2.41 2.44 2.47
#> 2 South Korea 6.16 5.99 5.79
```

提供的信息相同，但在格式上有两个重要差异：1) 每一行包含多个观察结果，2) 其中一个变量，年份，存储在标题中。为了最优地使用 tidyverse 包，数据需要重新塑形为*tidy*格式，你将在本书的数据整理部分学习如何做到这一点。在此之前，我们将使用已经处于 tidy 格式的示例数据集。

虽然一开始可能不明显，但随着你阅读本书，你将开始欣赏在函数使用整洁格式进行输入和输出的框架中工作的优势。你会看到这如何使数据分析师能够专注于分析的重要方面，而不是数据的格式。

你准备好做练习 1-4 了。*

## *4.2 优化数据框*

来自**tidyverse**的**dplyr**包引入了执行数据框操作中最常见的一些函数，并使用相对容易记住的名称为这些函数命名。例如，要更改数据表并添加新列，我们使用`mutate`。要过滤数据表以仅显示行子集，我们使用`filter`。最后，要按选择特定列来子集数据，我们使用`select`。

### 4.2.1 添加列

我们希望分析所需的所有信息都包含在数据框中。第一个任务是向我们的谋杀数据框中添加谋杀率。函数`mutate`将数据框作为第一个参数，将变量名称和值作为第二个参数，使用约定`name = values`。因此，要添加谋杀率，我们使用：

```r
murders <- mutate(murders, rate = total/population*100000)
```

请注意，在这里我们在函数内部使用了`total`和`population`，这些对象在我们的工作空间中**没有**定义。但为什么我们没有得到错误？

这是**dplyr**的主要功能之一。此包中的函数，如`mutate`，知道在第一个参数提供的数据框中查找变量。在上面的`mutate`调用中，`total`将具有`murders$total`中的值。这种方法使代码更易于阅读。

我们可以看到新列已添加：

```r
head(murders)
#>        state abb region population total rate
#> 1    Alabama  AL  South    4779736   135 2.82
#> 2     Alaska  AK   West     710231    19 2.68
#> 3    Arizona  AZ   West    6392017   232 3.63
#> 4   Arkansas  AR  South    2915918    93 3.19
#> 5 California  CA   West   37253956  1257 3.37
#> 6   Colorado  CO   West    5029196    65 1.29
```*

### **4.2.2 行子集**

*现在假设我们只想过滤数据框，只显示谋杀率低于 0.71 的条目。为此，我们使用`filter`函数，它将数据框作为第一个参数，然后是一个条件语句作为第二个参数。像`mutate`一样，我们可以在函数内部使用`murders`中的未引用变量名，并且它将知道我们指的是列而不是工作空间中的对象。

```r
filter(murders, rate <= 0.71)
#>           state abb        region population total  rate
#> 1        Hawaii  HI          West    1360301     7 0.515
#> 2          Iowa  IA North Central    3046355    21 0.689
#> 3 New Hampshire  NH     Northeast    1316470     5 0.380
#> 4  North Dakota  ND North Central     672591     4 0.595
#> 5       Vermont  VT     Northeast     625741     2 0.320
```**

### ***4.2.3 列子集***

**尽管我们的数据框只有六个列，但一些数据框包含数百列。如果我们只想查看其中的一些，我们可以使用**dplyr**的`select`函数。在下面的代码中，我们选择三个列，将其分配给一个新的对象，然后过滤这个新对象：

```r
new_dataframe <- select(murders, state, region, rate)
filter(new_dataframe, rate <= 0.71)
#>           state        region  rate
#> 1        Hawaii          West 0.515
#> 2          Iowa North Central 0.689
#> 3 New Hampshire     Northeast 0.380
#> 4  North Dakota North Central 0.595
#> 5       Vermont     Northeast 0.320
```

在`select`的调用中，第一个参数`murders`是一个对象，但`state`、`region`和`rate`是变量名。

*dplyr**提供了一系列辅助函数，用于根据内容选择列。例如，以下代码使用`where`函数仅保留数值列：

```r
new_dataframe <- select(murders, [where](https://tidyselect.r-lib.org/reference/where.html)(is.numeric))
names(new_dataframe)
#> [1] "population" "total"      "rate"
```

辅助函数`starts_with`、`ends_with`、`contains`、`matches`和`num_range`可以用来根据列名选择列。以下是一个示例，显示所有以`r`开头的行：

```r
new_dataframe <- select(murders, [starts_with](https://tidyselect.r-lib.org/reference/starts_with.html)("r"))
names(new_dataframe)
#> [1] "region" "rate"
```

辅助函数`everything`选择所有列。******

### ***4.2.4 变量转换***

**函数`mutate`也可以用于转换变量。例如，以下代码对人口变量进行了对数转换：

```r
mutate(murders, population = log10(population))
```

通常，我们需要将相同的转换应用于多个变量。函数`across`简化了这一操作。例如，如果我们想对人口总数和谋杀总数进行对数转换，我们可以使用：

```r
mutate(murders, across(c(population, total), log10))
```

当使用`across`时，辅助函数非常有用。例如，如果我们想将相同的转换应用于所有数值变量：

```r
mutate(murders, across([where](https://tidyselect.r-lib.org/reference/where.html)(is.numeric), log10))
```

或者所有字符变量：

```r
mutate(murders, across([where](https://tidyselect.r-lib.org/reference/where.html)(is.character), tolower))
```

*您现在可以开始练习 5-11 题了。*********

## *****4.3 管道*****

****在 R 中，我们可以通过使用所谓的*管道操作符* `%>%` 将一个函数的结果传递给另一个函数来执行一系列操作，例如`select`然后`filter`。自 R 版本 4.1.0 起，您也可以使用`|>`。以下包含了一些细节。

我们在第 4.2.3 节中编写了代码，以展示具有谋杀率低于 0.71 的州的三个变量（州、地区、比率）。为此，我们定义了中间对象`new_dataframe`。在**dplyr**中，我们可以编写看起来更像是我们想要执行的操作描述的代码，而不需要中间对象：

$$ \mbox{原始数据 } \rightarrow \mbox{ select } \rightarrow \mbox{ filter } $$

对于此类操作，我们可以使用管道`|>`。代码如下：

```r
murders |> select(state, region, rate) |> filter(rate <= 0.71)
#>           state        region  rate
#> 1        Hawaii          West 0.515
#> 2          Iowa North Central 0.689
#> 3 New Hampshire     Northeast 0.380
#> 4  North Dakota North Central 0.595
#> 5       Vermont     Northeast 0.320
```

此行代码等同于第 4.2.3 节中的两行代码。这里发生了什么？

通常，管道会将管道左侧的结果发送到管道右侧函数的第一个参数。这里有一个非常简单的例子：

```r
16 |> sqrt()
#> [1] 4
```

我们可以继续将值通过管道传递：

```r
16 |> sqrt() |> log2()
#> [1] 2
```

上述语句等同于`log2(sqrt(16))`。

记住，管道将值发送到第一个参数，因此我们可以定义其他参数，就像第一个参数已经定义一样：

```r
16 |> sqrt() |> log(base = 2)
#> [1] 2
```

因此，当使用管道与数据框和**dplyr**一起时，我们不再需要指定所需的第一参数，因为我们所描述的**dplyr**函数都接受数据作为第一个参数。在代码中，我们这样写：

```r
murders |> select(state, region, rate) |> filter(rate <= 0.71)
```

`murders`是`select`函数的第一个参数，而新的数据框（以前称为`new_dataframe`）是`filter`函数的第一个参数。

注意，管道操作符与那些第一个参数是输入数据的函数配合得很好。**tidyverse**包中的**dplyr**函数具有这种格式，并且可以很容易地与管道操作符一起使用。**********

## ****4.4 数据汇总****

***探索性数据分析的一个重要部分是总结数据。平均值和标准差是广泛使用的摘要统计的两个例子。通过首先将数据分成组，通常可以获取更有信息量的摘要。在本节中，我们介绍了两个新的**dplyr**动词，使这些计算更容易：`summarize`和`group_by`。我们学习使用`pull`函数访问结果值。

### 4.4.1 `summarize`函数

*dplyr**中的`summarize`函数提供了一种使用直观且易于阅读的代码来计算摘要统计的方法。我们从基于身高的简单示例开始。`heights`数据集包括课堂调查中报告的学生身高和性别。

```r
library([dplyr](https://dplyr.tidyverse.org))
library(dslabs)
```

以下代码计算了女性的平均值和标准差：

```r
s <- heights |> 
 filter(sex == "Female") |>
 summarize(average = mean(height), standard_deviation = sd(height))
s
#>   average standard_deviation
#> 1    64.9               3.76
```

这个函数以我们的原始数据框为输入，过滤它以仅保留女性，然后生成一个新的摘要表，其中只包含平均身高和标准差。我们可以选择结果表的列名。例如，上面我们决定使用`average`和`standard_deviation`，但我们可以使用其他名称。

因为存储在`s`中的结果表是一个数据框，我们可以使用访问器`$`来访问其组件：

```r
s$average
#> [1] 64.9
s$standard_deviation
#> [1] 3.76
```

与大多数其他**dplyr**函数一样，`summarize`了解变量名，我们可以直接使用它们。所以当我们在`summarize`函数的调用中写`mean(height)`时，函数正在访问名为“height”的列，然后计算结果数值向量的平均值。我们可以计算任何其他在向量上操作并返回单个值的摘要。

以下是我们如何使用`summarize`函数的另一个示例，让我们计算美国的平均谋杀率。记住，我们的数据表包括每个州的谋杀总数和人口规模，我们之前已经使用**dplyr**添加了一个谋杀率列：

```r
murders <- murders |> mutate(rate = total/population*100000)
```

记住，美国的谋杀率**不是**州谋杀率的平均值：

```r
murders |>
 summarize(rate = mean(rate))
#>   rate
#> 1 2.78
```

这是因为在上面的计算中，小州被赋予了与大州相同的权重。美国的谋杀率是美国谋杀总数除以美国总人口。因此，正确的计算方法是：

```r
us_murder_rate <- murders |>
 summarize(rate = sum(total)/sum(population)*100000)
us_murder_rate
#>   rate
#> 1 3.03
```

这种计算按比例计算较大州的规模，从而得到更大的值。******

### ***4.4.2 多个摘要***

**假设我们想要从同一个变量中获取三个摘要，例如中位数、最小值和最大值。我们可以这样使用`summarize`：

```r
heights |> summarize(median = median(height), min = min(height), max = max(height))
#>   median min  max
#> 1   68.5  50 82.7
```

但我们可以使用`quantile`函数仅用一行代码就获得这三个值：`quantile(x, c(0.5, 0, 1))`返回向量`x`的中位数（50th 百分位数）、最小值（0th 百分位数）和最大值（100th 百分位数）。在这里，我们不能使用`summarize`，因为它期望每行只有一个值。相反，我们必须使用`reframe`函数：

```r
heights |> reframe(quantiles = quantile(height, c(0.5, 0, 1)))
#>   quantiles
#> 1      68.5
#> 2      50.0
#> 3      82.7
```

然而，如果我们想为每个总结定义一个列，就像上面的 `summarize` 调用一样，我们必须定义一个返回类似这样的数据框的函数：

```r
median_min_max <- function(x){
 qs <- quantile(x, c(0.5, 0, 1))
 data.frame(median = qs[1], min = qs[2], max = qs[3])
}
```

然后我们可以像上面一样调用 `summarize`：

```r
heights |> summarize(median_min_max(height))
#>   median min  max
#> 1   68.5  50 82.7
```******

### ***4.4.3 使用 `group_by` 进行分组后总结***

**数据探索中一个常见的操作是首先将数据分成组，然后对每个组进行总结。例如，我们可能想分别计算男性和女性身高的平均值和标准差。`group_by` 函数帮助我们做到这一点。

如果我们输入这个：

```r
heights |> group_by(sex)
#> # A tibble: 1,050 × 2
#> # Groups:   sex [2]
#>   sex   height
#>   <fct>  <dbl>
#> 1 Male      75
#> 2 Male      70
#> 3 Male      68
#> 4 Male      74
#> 5 Male      61
#> # ℹ 1,045 more rows
```

结果看起来与 `heights` 并没有太大区别，除了打印对象时我们会看到 `Groups: sex [2]`。尽管从外观上并不立即明显，这现在是一个特殊的数据框，称为 *分组数据框*，并且 **dplyr** 函数，特别是 `summarize`，在作用于这个对象时会表现出不同的行为。从概念上讲，你可以将这个表格视为许多表格，它们具有相同的列，但行数不一定相同，堆叠在一个对象中。当我们对分组后的数据进行总结时，就会发生这种情况：

```r
heights |> 
 group_by(sex) |>
 summarize(average = mean(height), standard_deviation = sd(height))
#> # A tibble: 2 × 3
#>   sex    average standard_deviation
#>   <fct>    <dbl>              <dbl>
#> 1 Female    64.9               3.76
#> 2 Male      69.3               3.61
```

`summarize` 函数会对每个分组单独应用总结。

作为另一个例子，让我们使用上面定义的 `median_min_max` 计算国家四个地区的谋杀率的中间值、最小值和最大值：

```r
murders |> 
 group_by(region) |>
 summarize(median_min_max(rate))
#> # A tibble: 4 × 4
#>   region        median   min   max
#>   <fct>          <dbl> <dbl> <dbl>
#> 1 Northeast       1.80 0.320  3.60
#> 2 South           3.40 1.46  16.5 
#> 3 North Central   1.97 0.595  5.36
#> 4 West            1.29 0.515  3.63
```*****

### ***4.4.4 使用 `pull` 提取变量***

**在 4.4.1 节 中定义的 `us_murder_rate` 对象只代表一个数字。然而，我们将其存储在一个数据框中：

```r
class(us_murder_rate)
#> [1] "data.frame"
```

因为，像大多数 **dplyr** 函数一样，`summarize` 总是返回一个数据框。

如果我们想使用需要数值型值的函数，这个结果可能会出现问题。这里我们展示了一个在通过管道使用数据时访问存储的值的实用技巧：当一个数据对象通过管道传递时，可以使用 `pull` 函数访问该对象及其列。要从原始数据表中获取一个数字，我们只需多写一行代码，可以输入：

```r
us_murder_rate <- murders |> 
 summarize(rate = sum(total)/sum(population)*100000) |>
 pull(rate)
 us_murder_rate
#> [1] 3.03
```

现在是一个数值型：

```r
class(us_murder_rate)
#> [1] "numeric"
```*********

## ****4.5 排序****

***在检查数据集时，按不同的列对数据框进行排序通常很方便。我们了解 `order` 和 `sort` 函数，但为了对整个数据框进行排序，**dplyr** 函数 `arrange` 非常有用。例如，这里我们按人口规模对州进行排序：

```r
murders |> arrange(population) |> head()
#>                  state abb        region population total   rate
#> 1              Wyoming  WY          West     563626     5  0.887
#> 2 District of Columbia  DC         South     601723    99 16.453
#> 3              Vermont  VT     Northeast     625741     2  0.320
#> 4         North Dakota  ND North Central     672591     4  0.595
#> 5               Alaska  AK          West     710231    19  2.675
#> 6         South Dakota  SD North Central     814180     8  0.983
```

使用 `arrange`，我们可以决定按哪个列进行排序。例如，要按谋杀率对州进行排序，我们会使用 `arrange(rate)`。

注意默认行为是按升序排序。在 **dplyr** 中，函数 `desc` 将向量转换成降序。要按谋杀率降序排序数据框，我们可以输入：

```r
murders |> arrange(desc(rate)) 
```

### 4.5.1 嵌套排序

如果我们按有并列的列进行排序，我们可以使用第二个列来打破并列。同样，第三个列可以用来打破第一和第二之间的并列，依此类推。这里我们按 `region` 排序，然后在区域内按谋杀率排序：

```r
murders |> 
 arrange(region, rate) |> 
 head()
#>           state abb    region population total  rate
#> 1       Vermont  VT Northeast     625741     2 0.320
#> 2 New Hampshire  NH Northeast    1316470     5 0.380
#> 3         Maine  ME Northeast    1328361    11 0.828
#> 4  Rhode Island  RI Northeast    1052567    16 1.520
#> 5 Massachusetts  MA Northeast    6547629   118 1.802
#> 6      New York  NY Northeast   19378102   517 2.668
```

### *4.5.2 顶部 $n$ 个*

在上面的代码中，我们使用了`head`函数来避免整个数据集填充整个页面。例如，使用`arrange(desc(rate))`然后使用`head`将按顺序显示谋杀率最高的 6 个州。相反，要查看具有最高谋杀率的具体数量的观测值，我们可以使用`slice_max`函数。这个函数将其第一个参数作为数据框，第二个参数是要显示的行数，第三个参数是要过滤的变量。以下是一个查看前 5 行示例：

```r
murders |> slice_max(rate, n = 5)
#>                  state abb        region population total  rate
#> 1 District of Columbia  DC         South     601723    99 16.45
#> 2            Louisiana  LA         South    4533372   351  7.74
#> 3             Missouri  MO North Central    5988927   321  5.36
#> 4             Maryland  MD         South    5773552   293  5.07
#> 5       South Carolina  SC         South    4625364   207  4.48
```

`slice_min`函数做的是同样的事情，但是针对最小值。

你准备好做 12-19 题练习了。*********

## *****4.6 Tibbles*****

****要使用 tidyverse，数据必须存储在数据框中。我们在第 2.3.1 节中介绍了数据框，并在整本书中使用了`murders`数据框。在第 4.4.3 节中，我们介绍了`group_by`函数，它允许在计算汇总统计之前对数据进行分层。但是，数据框中存储了分组信息在哪里？

```r
murders |> group_by(region)
#> # A tibble: 51 × 6
#> # Groups:   region [4]
#>   state      abb   region population total  rate
#>   <chr>      <chr> <fct>       <dbl> <dbl> <dbl>
#> 1 Alabama    AL    South     4779736   135  2.82
#> 2 Alaska     AK    West       710231    19  2.68
#> 3 Arizona    AZ    West      6392017   232  3.63
#> 4 Arkansas   AR    South     2915918    93  3.19
#> 5 California CA    West     37253956  1257  3.37
#> # ℹ 46 more rows
```

注意，没有包含此信息的列。但是，如果你仔细查看上面的输出，你会看到`A tibble`后面跟着维度。我们可以使用以下方法了解返回对象的类别：

```r
murders |> group_by(region) |> class()
#> [1] "grouped_df" "tbl_df"     "tbl"        "data.frame"
```

`tbl`，发音为“tibble”，是一种特殊的数据框。`group_by`和`summarize`函数总是返回这种类型的数据框。`group_by`函数返回一种特殊的`tbl`，即`grouped_df`。我们将在稍后详细介绍这些。为了保持一致性，**dplyr**操作符（`select`、`filter`、`mutate`和`arrange`）保留输入的类别：如果它们接收一个常规数据框，则返回一个常规数据框；如果它们接收一个 tibble，则返回一个 tibble。但是，tibbles 是 tidyverse 中首选的格式，因此 tidyverse 函数从头开始生成数据框时返回一个 tibble。例如，在第六章中，我们将看到 tidyverse 函数用于导入数据时创建 tibbles。

## *****4.7 Tibbles 与数据框*****

****Tibbles 与数据框非常相似。实际上，你可以把它们看作是数据框的现代版本。尽管如此，它们之间还有一些重要的区别，我们将在下面描述。

*(1) Tibbles 显示得更好**

Tibbles 的打印方法比数据框的可读性更好。为了看到这一点，比较一下输入`murders`和将`murders`转换为 tibble 后的输出。我们可以使用`as_tibble(murders)`来完成这个操作。如果在 RStudio 中使用，tibble 的输出会根据你的窗口大小进行调整。为了看到这一点，改变你的 R 控制台宽度，注意显示的列数是更多还是更少。

如果你从数据框中提取列，你可能会得到一个不是数据框的对象，例如向量或标量。例如：

```r
class(murders[,4])
#> [1] "numeric"
```

不是一个数据框。使用 tibbles 就不会发生这种情况：

```r
class(as_tibble(murders)[,4])
#> [1] "tbl_df"     "tbl"        "data.frame"
```

这在 tidyverse 中很有用，因为函数需要数据框作为输入。

使用 tibbles，如果你想访问定义列的向量，而不是得到一个数据框，你需要使用访问器 `$`：

```r
class(as_tibble(murders)$population)
#> [1] "numeric"
```

一个相关特性是，如果你尝试访问一个不存在的列，tibbles 会给出警告。如果我们不小心将 `Population` 写成 `population` 而不是这样：

```r
murders$Population
#> NULL
```

返回一个没有警告的 `NULL`，这可能会使调试变得更困难。相比之下，如果我们尝试使用 tibble，我们会得到一个有用的警告：

```r
as_tibble(murders)$Population
#> Warning: Unknown or uninitialised column: `Population`.
#> NULL
```

**(2) Tibbles 可以有复杂条目**

虽然数据框的列需要是数字、字符串或逻辑值的向量，但 tibbles 可以有更复杂的对象，例如列表或函数。此外，我们还可以使用函数创建 tibbles：

```r
tibble](https://tibble.tidyverse.org/reference/tibble.html)(id = [c(1, 2, 3), func = c(mean, median, sd))
#> # A tibble: 3 × 2
#>      id func 
#>   <dbl> <list>
#> 1     1 <fn> 
#> 2     2 <fn> 
#> 3     3 <fn>
```

**(3) Tibbles 可以分组**

函数 `group_by` 返回一种特殊的 tibble：分组 tibble。这个类存储了信息，让你知道哪些行属于哪个组。tidyverse 函数，特别是 `summarize` 函数，都了解分组信息。

### 4.7.1 创建 tibbles

有时我们创建自己的数据框是有用的。要在 tibble 格式下创建数据框，你可以通过使用 `tibble` 函数来实现。

```r
grades <- tibble](https://tibble.tidyverse.org/reference/tibble.html)(names = [c("John", "Juan", "Jean", "Yao"), 
 exam_1 = c(95, 80, 90, 85), 
 exam_2 = c(90, 85, 85, 90))
```

请注意，基础 R（未加载任何包）有一个 `data.frame` 函数，可以用来创建常规数据框而不是 tibble。

```r
grades <- data.frame(names = c("John", "Juan", "Jean", "Yao"), 
 exam_1 = c(95, 80, 90, 85), 
 exam_2 = c(90, 85, 85, 90))
```

要将常规数据框转换为 tibble，你可以使用 `as_tibble` 函数。

```r
as_tibble](https://tibble.tidyverse.org/reference/as_tibble.html)(grades) |> [class()
#> [1] "tbl_df"     "tbl"        "data.frame"
```*************

## ****4.8 占位符****

***使用管道 `|>` 的一大优点是我们不需要在操作数据框时不断为新对象命名。管道左侧的对象用作管道右侧函数的第一个参数。但如果我们想将其作为非第一个参数传递给右侧函数怎么办？答案是占位符运算符 `_`（对于 `%>%` 管道，占位符是 `.`）。下面是一个简单示例，它将 `base` 参数传递给 `log` 函数。以下三个是等价的：

```r
log(8, base = 2)
2 |> log(8, base = _)
2 %>%](https://magrittr.tidyverse.org/reference/pipe.html) [log(8, base = .)
```****

## ****4.9 **purrr** 包****

***在 第 3.5 节 我们学习了 `sapply` 函数，它允许我们将相同的函数应用于向量的每个元素。我们构建了一个函数，并使用 `sapply` 来计算 `n` 的前 `n` 个整数的和，如下所示：

```r
compute_s_n <- function(n) {
 sum(1:n)
}
n <- 1:25
s_n <- sapply(n, compute_s_n)
```

这种类型的操作，将相同的函数或过程应用于对象中的元素，在数据分析中相当常见。`purrr`包包括类似于`sapply`但与其他 tidyverse 函数更好地交互的函数。主要优势是我们可以更好地控制函数的输出类型。相比之下，`sapply`可以返回几种不同的对象类型；例如，我们可能期望一行代码的结果是数值，但在某些情况下`sapply`可能会将我们的结果转换为字符。`purrr`函数永远不会这样做：它们将返回指定类型的对象，或者在不可能的情况下返回错误。*

我们将要学习的第一个`purrr`函数是`map`，它的工作方式与`sapply`非常相似，但始终，没有例外，返回一个列表：

```r
library([purrr](https://purrr.tidyverse.org/))
s_n <- map(n, compute_s_n)
class(s_n)
#> [1] "list"
```

如果我们想要一个数值向量，我们可以使用`map_dbl`，它总是返回一个数值向量。*

```r
s_n <- map_dbl(n, compute_s_n)
class(s_n)
#> [1] "numeric"
```

这会产生与上面显示的`sapply`调用相同的结果。*

一个特别有用的`purrr`函数，用于与其他 tidyverse 交互，是`map_df`，它总是返回一个 tibble 数据框。然而，被调用的函数需要返回一个带有名称的向量或列表。因此，以下代码会导致`Argument 1 must have names`错误：

```r
s_n <- map_df(n, compute_s_n)
```

函数需要返回一个数据框才能使这起作用：*

```r
compute_s_n <- function(n) {
 tibble](https://tibble.tidyverse.org/reference/tibble.html)(sum = [sum(1:n))
}
s_n <- map_df(n, compute_s_n)
```

`purrr`包提供了更多这里没有涵盖的功能。有关更多详细信息，您可以查阅[这个在线资源](https://jennybc.github.io/purrr-tutorial/)¹。*********

## ****4.10 Tidyverse 条件语句****

***典型数据分析通常涉及一个或多个条件操作。在第 3.1 节中，我们描述了`ifelse`函数，我们将在本书中广泛使用它。在本节中，我们介绍了两个`dplyr`函数，它们提供了执行条件操作的功能。**

### 4.10.1 `case_when`

`case_when`函数对于向量化条件语句很有用。它与`ifelse`类似，但可以输出任意数量的值，而不仅仅是`TRUE`或`FALSE`。以下是一个将数字分为负数、正数和 0 的示例：

```r
x <- c(-2, -1, 0, 1, 2)
case_when(x < 0 ~ "Negative", 
 x > 0 ~ "Positive", 
 TRUE  ~ "Zero")
#> [1] "Negative" "Negative" "Zero"     "Positive" "Positive"
```

这个函数的常见用途是根据现有变量定义分类变量。例如，假设我们想要比较四个州组（*新英格兰*，*西海岸*，*南部*和*其他*）的谋杀率。对于每个州，我们需要询问它是否在新英格兰，如果不是，我们询问它是否在西海岸，如果不是，我们询问它是否在南部，如果不是，我们将其归为*其他*。以下是使用`case_when`来完成此操作的示例：*

```r
murders |> 
 mutate(group = case_when(
 abb %in% c("ME", "NH", "VT", "MA", "RI", "CT") ~ "New England",
 abb %in% c("WA", "OR", "CA") ~ "West Coast",
 region == "South" ~ "South",
 TRUE ~ "Other")) |>
 group_by(group) |>
 summarize(rate = sum(total)/sum(population)*10⁵) 
#> # A tibble: 4 × 2
#>   group        rate
#>   <chr>       <dbl>
#> 1 New England  1.72
#> 2 Other        2.71
#> 3 South        3.63
#> 4 West Coast   2.90
```*

### **4.10.2 `between`**

*数据分析中的一个常见操作是确定一个值是否在区间内。我们可以使用条件语句来检查这一点。例如，为了检查向量`x`的元素是否在`a`和`b`之间，我们可以输入**

```r
x >= a & x <= b
```

然而，这可能会变得繁琐，尤其是在 tidyverse 方法中。`between`函数执行相同的操作。

```r
between(x, a, b)
```*******

## ****4.11 练习****

***1. 检查内置数据集`co2`。以下哪项是正确的：

1.  `co2`是整洁数据：每行有一个年份。

1.  `co2`不是整洁数据：我们需要至少有一个字符向量列。

1.  `co2`不是整洁数据：它是一个矩阵而不是数据框。

1.  `co2`不是整洁数据：为了变得整洁，我们需要将其整理成三列（年份、月份和值），然后每个 co2 观测值将有一行。

2. 检查内置数据集`ChickWeight`。以下哪项是正确的：

1.  `ChickWeight`不是整洁数据：每只鸡有多于一行。

1.  `ChickWeight`是整洁数据：每个观测值（一个重量）由一行表示。这个测量的鸡是其中一个变量。

1.  `ChickWeight`不是整洁数据：我们缺少年份列。

1.  `ChickWeight`是整洁数据：它存储在数据框中。

3. 检查内置数据集`BOD`。以下哪项是正确的：

1.  `BOD`不是整洁数据：它只有六行。

1.  `BOD`不是整洁数据：第一列只是一个索引。

1.  `BOD`是整洁数据：每行是一个观测值，包含两个值（时间和需求）

1.  `BOD`是整洁数据：所有小型数据集按定义都是整洁的。

4. 以下哪个内置数据集是整洁的（您可以选择多个）：

1.  `BJsales`

1.  `EuStockMarkets`

1.  `DNase`

1.  `Formaldehyde`

1.  `Orange`

1.  `UCBAdmissions`

5. 加载**dplyr**包和谋杀数据集。

```r
library([dplyr](https://dplyr.tidyverse.org))
library(dslabs)
```

您可以使用**dplyr**函数`mutate`添加列。此函数了解列名，在函数内部您可以不使用引号调用它们：

```r
murders <- mutate(murders, population_in_millions = population/10⁶)
```

我们可以写`population`而不是`murders$population`。`mutate`函数知道我们在从`murders`中获取列。

使用`mutate`函数添加一个名为`rate`的谋杀率列，其值如上例代码所示，每 10 万人谋杀率。确保您像示例代码中那样重新定义`murders`（`murders <- [your code]`），这样我们就可以继续使用这个变量。

6. 如果`rank(x)`给出`x`从低到高的排名，则`rank(-x)`给出从高到低的排名。使用`mutate`函数添加一个包含谋杀率从高到低排名的`rank`列。确保您重新定义`murders`，这样我们就可以继续使用这个变量。

7. 使用**dplyr**，我们可以用`select`来只显示某些列。例如，使用以下代码我们只会显示州和人口规模：

```r
select(murders, state, population)
```

使用`select`来显示`murders`中的州名和缩写。不要重新定义`murders`，只需显示结果。

8. **dplyr**函数`filter`用于选择数据框中特定的行以保留。与用于列的`select`不同，`filter`用于行。例如，您可以像这样显示仅纽约的行：

```r
filter(murders, state == "New York")
```

您可以使用其他逻辑向量来过滤行。

使用 `filter` 显示谋杀率最高的前 5 个州。从现在开始，不要更改 `murders` 数据集，只需显示结果。记住，你可以根据 `rank` 列进行筛选。

9. 我们可以使用 `!=` 操作符来删除行。例如，要删除佛罗里达州，我们会这样做：

```r
no_florida <- filter(murders, state != "Florida")
```

创建一个新的数据框 `no_south`，删除南部地区的州。这个类别中有多少个州？你可以使用 `nrow` 函数来做这件事。

10. 我们还可以使用 `%in%` 与 **dplyr** 进行筛选。因此，你可以这样查看纽约和德克萨斯州的数据：

```r
filter(murders, state %in% c("New York", "Texas"))
```

创建一个新的数据框 `murders_nw`，只包含东北部和西部的州。这个类别中有多少个州？

11. 假设你想要住在东北部或西部 **并且** 谋杀率要低于 1。我们想要查看满足这些条件的州的数据。注意，你可以在 `filter` 中使用逻辑运算符如 `&`。以下是一个示例，其中我们筛选出仅包含东北部小州的例子。

```r
filter(murders, population < 5000000 & region == "Northeast")
```

确保 `murders` 已经使用 `rate` 和 `rank` 定义，并且仍然包含所有州。创建一个名为 `my_states` 的表格，其中包含满足以下两个条件的行：它位于东北部或西部，谋杀率低于 1。使用 `select` 仅显示州名、率和排名。

12. 管道 `|>` 可以用来按顺序执行操作，而无需定义中间对象。首先，重新定义 `murders` 以包括率和排名。

```r
murders <- mutate(murders, rate =  total/population*100000, 
 rank = rank(-rate))
```

在上一题的解决方案中，我们做了以下操作：

```r
my_states <- filter(murders, region %in% c("Northeast", "West") & 
 rate < 1)
 select(my_states, state, rate, rank)
```

管道 `|>` 允许我们按顺序执行操作，而无需定义中间变量 `my_states`。因此，我们可以在同一行中突变和选择，如下所示：

```r
mutate(murders, rate =  total/population*100000, 
 rank = rank(-rate)) |>
 select(state, rate, rank)
```

注意，`select` 的第一个参数不再是数据框。第一个参数被认为是 `|>` 之前执行的操作的结果。

重复上一个练习，但现在不是创建一个新的对象，而是显示结果，并且只包括州、率和排名列。使用管道 `|>` 在一行内完成此操作。

```r
my_states <- murders |>
 mutate SOMETHING |> 
 filter SOMETHING |> 
 select SOMETHING
```

13. 对于第 13-19 题的练习，我们将使用美国国家健康统计中心（NCHS）收集的调查数据。自 1960 年代以来，该中心进行了一系列健康和营养调查。从 1999 年开始，每年大约有 5,000 名各年龄段的个人接受采访，并完成调查的健康检查部分。部分数据通过 **NHANES** 包提供。一旦安装了 **NHANES** 包，你可以这样加载数据：

```r
library(NHANES)
```

**NHANES** 数据有许多缺失值。在 R 中，如果输入向量的任何条目是 `NA`，则 `mean` 和 `sd` 函数将返回 `NA`。以下是一个示例：

```r
library(dslabs)
mean(na_example)
#> [1] NA
sd(na_example)
#> [1] NA
```

要忽略 `NA`，我们可以使用 `na.rm` 参数：

```r
mean(na_example, na.rm = TRUE)
#> [1] 2.3
sd(na_example, na.rm = TRUE)
#> [1] 1.22
```

现在让我们探索 **NHANES** 数据。

我们将提供一些关于血压的基本事实。首先，让我们选择一个组来设定标准。我们将使用 20 至 29 岁的女性。`AgeDecade` 是一个具有这些年龄的类别变量。请注意，类别编码为 `" 20-29"`，前面有一个空格！`BPSysAve` 变量中保存的收缩压的平均值和标准差是多少？将其保存到名为 `ref` 的变量中。

提示：使用 `filter` 和 `summarize`，在计算平均值和标准差时使用 `na.rm = TRUE` 参数。您还可以使用 `filter` 过滤 NA 值。

14. 使用管道操作符，将平均值赋给名为 `ref_avg` 的数值变量。提示：使用前一个练习中的代码，然后使用 `pull`。

15. 现在报告同一组的最大值和最小值。

16. 计算女性的平均值和标准差，但分别按年龄组计算，而不是像练习 13 中那样选择一个十年。注意，年龄组由 `AgeDecade` 定义。提示：与其按年龄和性别过滤，不如按 `Gender` 过滤，然后使用 `group_by`。

17. 对男性重复练习 16。

19. 对于 40-49 岁的男性，比较 `Race1` 变量中报告的种族间的收缩压，并按平均收缩压从低到高排序结果表。

19. 加载 `murders` 数据集。以下哪个说法是正确的？

1.  `murders` 是整洁格式，存储在 tibble 中。

1.  `murders` 是整洁格式，存储在数据框中。

1.  `murders` 不是整洁格式，存储在 tibble 中。

1.  `murders` 不是整洁格式，存储在数据框中。

20. 使用 `as_tibble` 将 `murders` 数据表转换为 tibble 并将其保存在名为 `murders_tibble` 的对象中。

21. 使用 `group_by` 函数将 `murders` 转换为按地区分组的 tibble。

22. 编写与以下代码等价的 tidyverse 代码：

```r
exp(mean(log(murders$population)))
```

* 使用管道操作符，确保每个函数调用不带参数。使用点操作符访问人口。提示：代码应从 `murders |>` 开始。

23. 使用 `map_df` 创建一个包含三个列名为 `n`、`s_n` 和 `s_n_2` 的数据框。第一列应包含从 1 到 100 的数字。第二列和第三列应分别包含从 1 到 $n$ 的数字之和，其中 $n$ 是行号。*******************

* * *

***1.  [`jennybc.github.io/purrr-tutorial/`](https://jennybc.github.io/purrr-tutorial/)↩︎*****
