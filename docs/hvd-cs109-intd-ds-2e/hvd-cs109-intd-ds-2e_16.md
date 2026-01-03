# 11  重塑数据

> 原文：[`rafalab.dfci.harvard.edu/dsbook-part-1/wrangling/reshaping-data.html`](https://rafalab.dfci.harvard.edu/dsbook-part-1/wrangling/reshaping-data.html)

1.  数据处理

1.  11  重塑数据

正如我们在书中所见，数据以*整洁*格式存在是 tidyverse 流畅运行的关键。在数据分析过程的第一步，即导入数据之后，一个常见的下一步是将数据重塑成便于后续分析的形式。**tidyr**包是**tidyverse**的一部分，它包含了一些对整理数据有用的函数。

在本节中，我们将使用第 4.1 节中描述的生育宽格式数据集作为示例。

```r
library(tidyverse 
library(dslabs)
path <- system.file("extdata", package = "dslabs")
filename <- file.path(path, "fertility-two-countries-example.csv")
wide_data <- read_csv(filename)
```

## 11.1 `pivot_longer`

在**tidyr**包中最常用的函数之一是`pivot_longer`，它可以将宽数据转换为整洁数据。

与大多数 tidyverse 函数一样，`pivot_longer`函数的第一个参数是要转换的数据框。在这里，我们想要重塑`wide_data`数据集，使得每一行代表一个生育观察值，这意味着我们需要三个列来存储年份、国家和观察值。在其当前形式中，不同年份的数据位于不同的列中，年份值存储在列名中。通过`names_to`和`values_to`参数，我们将告诉`pivot_longer`我们想要分配给包含当前列名和观察值的列的列名。默认名称是`name`和`value`，这些通常是可用的选择。在这种情况下，这两个参数的更好选择可能是`year`和`fertility`。请注意，数据文件中没有任何地方告诉我们这是生育数据。相反，我们是从文件名中解读出来的。通过`cols`参数，第二个参数，我们指定包含观察值的列；这些是将会被旋转的列。默认情况下是旋转所有列，所以大多数情况下我们必须指定这些列。在我们的例子中，我们想要`1960`、`1961`直到`2015`的列。

因此，旋转生育数据的代码如下：

```r
new_tidy_data <- wide_data |>
 pivot_longer(`1960`:`2015`, names_to = "year", values_to = "fertility")
```

我们可以看到数据已经被转换为整洁格式，列有`year`和`fertility`

```r
head(new_tidy_data)
#> # A tibble: 6 × 3
#>   country year  fertility
#>   <chr>   <chr>     <dbl>
#> 1 Germany 1960       2.41
#> 2 Germany 1961       2.44
#> 3 Germany 1962       2.47
#> 4 Germany 1963       2.49
#> 5 Germany 1964       2.49
#> # ℹ 1 more row
```

并且由于我们有两个国家，并且这一列没有被旋转，所以每年产生了两行。有一种更快的方式来编写这段代码，即指定哪些列**不会**包含在旋转中，而不是所有将要旋转的列：

```r
new_tidy_data <- wide_data |>
 pivot_longer(-country, names_to = "year", values_to = "fertility")
```

`new_tidy_data`对象看起来与这样定义的原始`tidy_data`相同

```r
tidy_data <- gapminder |> 
 filter(country %in% c("South Korea", "Germany") & !is.na(fertility)) |>
 select(country, year, fertility)
```

只有一个细微的差别。你能发现吗？看看年份列的数据类型。`pivot_longer`函数假设列名是字符。因此，在我们准备好绘图之前，我们需要进行一些额外的处理。我们需要将年份列转换为数字：

```r
new_tidy_data <- wide_data |>
 pivot_longer(-country, names_to = "year", values_to = "fertility") |>
 mutate(year = as.integer(year))
```

现在数据已经整洁，我们可以使用以下相对简单的 ggplot 代码：

```r
new_tidy_data |> 
 ggplot(aes(year, fertility, color = country)) + 
 geom_point()
```

## 11.2 `pivot_wider`

正如我们将在后面的示例中看到的那样，有时为了数据整理的目的，将整洁数据转换为宽数据是有用的。我们经常将此用作整理数据的一个中间步骤。`pivot_wider`函数基本上是`pivot_longer`的逆函数。第一个参数是数据，但由于我们正在使用管道，所以我们没有显示它。`names_from`参数告诉`pivot_wider`哪个变量将被用作列名。`values_from`参数指定哪个变量用于填充单元格。

```r
new_wide_data <- new_tidy_data |> 
 pivot_wider(names_from = year, values_from = fertility)
select(new_wide_data, country, `1960`:`1967`)
#> # A tibble: 2 × 9
#>   country     `1960` `1961` `1962` `1963` `1964` `1965` `1966` `1967`
#>   <chr>        <dbl>  <dbl>  <dbl>  <dbl>  <dbl>  <dbl>  <dbl>  <dbl>
#> 1 Germany       2.41   2.44   2.47   2.49   2.49   2.48   2.44   2.37
#> 2 South Korea   6.16   5.99   5.79   5.57   5.36   5.16   4.99   4.85
```

与`pivot_wider`类似，`names_from`和`values_from`默认为`name`和`value`。

## 11.3 分离变量

与通常所需的数据整理相比，上述数据整理很简单。在我们的示例电子表格文件中，我们包括了一个稍微复杂一些的示例。它包含两个变量：预期寿命和生育率。然而，它的存储方式并不整洁，而且，正如我们将解释的，也不是最优的。

```r
path <- system.file("extdata", package = "dslabs")
 filename <- "life-expectancy-and-fertility-two-countries-example.csv"
filename <-  file.path(path, filename)
 raw_dat <- read_csv(filename)
select(raw_dat, 1:5)
#> # A tibble: 2 × 5
#>   country     `1960_fertility` `1960_life_expectancy` `1961_fertility`
#>   <chr>                  <dbl>                  <dbl>            <dbl>
#> 1 Germany                 2.41                   69.3             2.44
#> 2 South Korea             6.16                   53.0             5.99
#> # ℹ 1 more variable: `1961_life_expectancy` <dbl>
```

首先，请注意数据是宽格式。其次，请注意这个表格包含了两个变量的值，生育率和预期寿命，列名编码了哪一列代表哪个变量。在列名中编码信息是不推荐的，但不幸的是，这相当常见。我们将运用我们的整理技巧来提取这些信息，并以整洁的方式存储。

我们可以使用`pivot_longer`函数开始数据整理，但不再使用`year`作为新列的列名，因为它还包含变量类型。我们暂时将其称为`name`：

```r
dat <- raw_dat |> pivot_longer(-country)
head(dat)
#> # A tibble: 6 × 3
#>   country name                 value
#>   <chr>   <chr>                <dbl>
#> 1 Germany 1960_fertility        2.41
#> 2 Germany 1960_life_expectancy 69.3 
#> 3 Germany 1961_fertility        2.44
#> 4 Germany 1961_life_expectancy 69.8 
#> 5 Germany 1962_fertility        2.47
#> # ℹ 1 more row
```

结果是并不完全符合我们所说的整洁，因为每个观测值都关联着两行，而不是一行。我们希望将两个变量，生育率和预期寿命的值，分别放在两个单独的列中。实现这一目标的首要挑战是将`name`列分割成年份和变量类型。请注意，这个列中的条目使用下划线将年份和变量名称分开：

```r
dat$name[1:5]
#> [1] "1960_fertility"       "1960_life_expectancy" "1961_fertility" 
#> [4] "1961_life_expectancy" "1962_fertility"
```

在列名中编码多个变量是一个如此常见的问题，以至于**tidyr**包包括将列分割成两个或更多列的函数。`separate_wider_delim`函数接受三个参数：要分割的列的名称、用于新列的名称以及分隔变量的字符。因此，将变量名称从年份中分离出来的第一次尝试可能是：

```r
dat |> separate_wider_delim(name, delim = "_", 
 names = c("year", "name"))
```

然而，这一行代码将产生错误。这是因为预期寿命的名称由三个由下划线分隔的字符串组成，而生育率的名称有两个。这是一个常见问题，因此`separate_wider_delim`函数有`too_few`和`too_many`参数来处理这些情况。我们在帮助文件中看到，选项`too_many = merge`*将合并任何额外的部分*。以下一行代码就是我们所需要的：

```r
dat |> separate_wider_delim(name, delim = "_", 
 names = c("year", "name"), 
 too_many = "merge")
#> # A tibble: 224 × 4
#>   country year  name            value
#>   <chr>   <chr> <chr>           <dbl>
#> 1 Germany 1960  fertility        2.41
#> 2 Germany 1960  life_expectancy 69.3 
#> 3 Germany 1961  fertility        2.44
#> 4 Germany 1961  life_expectancy 69.8 
#> 5 Germany 1962  fertility        2.47
#> # ℹ 219 more rows
```

但我们还没有完成。我们需要为每个变量创建一个列，并将 `year` 转换为数字。正如我们所学的，`pivot_wider` 函数可以做到这一点：

```r
dat <- dat |> 
 separate_wider_delim(name, delim = "_", 
 names = c("year", "name"), 
 too_many = "merge") |>
 pivot_wider() |>
 mutate(year = as.integer(year))
 dat
#> # A tibble: 112 × 4
#>   country  year fertility life_expectancy
#>   <chr>   <int>     <dbl>           <dbl>
#> 1 Germany  1960      2.41            69.3
#> 2 Germany  1961      2.44            69.8
#> 3 Germany  1962      2.47            70.0
#> 4 Germany  1963      2.49            70.1
#> 5 Germany  1964      2.49            70.7
#> # ℹ 107 more rows
```

数据现在以整洁格式存在，每行有一个观测值，包含三个变量：年份、生育率和预期寿命。

三个相关函数是 `separate_wider_position`、`separate_wider_regex` 和 `unite`。`separate_wider_position` 使用宽度而不是分隔符。`separate_wider_regex`，在第 16.4.13 节中描述，提供了更多控制我们如何分隔以及保留什么的选项。`unite` 函数可以看作是 `separate` 函数的逆操作：它将两列合并为一列。

## 11.4 使用 data.table 重新塑形

一般来说，你可以使用 **tidyverse** 做的所有事情都可以使用 **data.table** 和 base R 做到，尽管可能更难阅读，但它通常更灵活、更快、更高效。在这里，我们展示了如何使用 **data.table** 方法进行 `pivot_longer`、`pivot_wider` 和 `separate`。我们将使用之前使用的这个例子来说明：

```r
path <- system.file("extdata", package = "dslabs")
filename <- file.path(path, "fertility-two-countries-example.csv")
```

### 11.4.1 `pivot_longer` 是 `melt`

如果在 **tidyverse** 中编写

```r
wide_data <- read_csv(filename)
new_tidy_data <- wide_data |>
 pivot_longer(-1, names_to = "year", values_to = "fertility")
```

在 **data.table** 中，我们使用 `melt` 函数。

```r
library(data.table)
dt_wide_data <- fread(filename) 
dt_new_tidy_data  <- melt(dt_wide_data, 
 measure.vars = 2:ncol(dt_wide_data), 
 variable.name = "year", 
 value.name = "fertility")
```

### 11.4.2 `pivot_wider` 是 `dcast`

如果在 **tidyverse** 中编写

```r
new_wide_data <- new_tidy_data |> 
 pivot_wider(names_from = year, values_from = fertility)
```

在 **data.table** 中，我们使用 `dcast` 函数。

```r
dt_new_wide_data <- dcast(dt_new_tidy_data, formula = ... ~ year,
 value.var = "fertility")
```

### 11.4.3 分离变量

我们现在用之前使用的例子来说明：

```r
path <- system.file("extdata", package = "dslabs")
filename <- "life-expectancy-and-fertility-two-countries-example.csv"
filename <-  file.path(path, filename)
```

在 **tidyverse** 中，我们使用

```r
raw_dat <- read_csv(filename)
dat <- raw_dat |> pivot_longer(-country) |>
 separate_wider_delim](https://tidyr.tidyverse.org/reference/separate_wider_delim.html)(name, delim = "_", names = [c("year", "name"), 
 too_many = "merge") |>
 pivot_wider() |>
 mutate(year = as.integer(year))
```

在 **data.table** 中，我们可以使用 `tstrsplit` 函数：

```r
dt_raw_dat <- fread(filename)
dat_long <- melt(dt_raw_dat, 
 measure.vars = which(names(dt_raw_dat) != "country"), 
 variable.name = "name", value.name = "value")
dat_long, [c("year", "name", "name2") := 
 tstrsplit(name, "_", fixed = TRUE, type.convert = TRUE)]
dat_long[is.na(name2), name2 := ""]
dat_long, name := [paste(name, name2, sep = "_")][, name2 := NULL]
dat_wide <- dcast(dat_long, country + year ~ name, value.var = "value")
```

## 11.5 `janitor` 包

`janitor` 包包括一些常见的数据整理步骤的函数。这些步骤通常是重复且耗时的。关键特性包括检查和清理列名、删除空或重复行以及转换数据类型的函数。它还提供了轻松生成频率表和执行交叉表的特性。该包旨在与 **tidyverse** 无缝工作。在这里，我们展示了四个示例。

电子表格通常使用与编程不兼容的名称。最常见的问题是带有空格的列名。`clean_names()` 函数试图解决这个问题和其他常见问题。默认情况下，它强制变量名变为小写，并使用下划线代替空格。在这个例子中，我们更改了上一节中创建的 `dat` 对象的变量名，然后演示了这个函数的工作方式：

```r
library(janitor)
names(dat) <- c("Country", "Year", "Fertility",  "Life Expectancy")
clean_names](https://sfirke.github.io/janitor/reference/clean_names.html)(dat) |> [names()
#> [1] "country"         "year"            "fertility" 
#> [4] "life_expectancy"
```

另一个非常常见的挑战现实是，数字矩阵保存在电子表格中，并包含一个包含行名的字符列。为了解决这个问题，我们必须删除第一列，但只有在将它们分配为我们将在将数据框转换为矩阵后用作 rownames 的向量之后才能这样做。`column_to_rows`函数为我们执行这些操作，我们只需要指定包含 rownames 的列：

```r
data.frame(ids = letters[1:3], x = 1:3, y = 4:6) |> 
 column_to_rownames("ids") |>
 as.matrix() 
#>   x y
#> a 1 4
#> b 2 5
#> c 3 6
```

另一个常见的挑战是电子表格将列名作为第一行。为了快速解决这个问题，我们可以使用`row_to_names`：

```r
x <- read.csv(file.path(path, "murders.csv"), header = FALSE) |> 
 row_to_names(1)
names(x)
#> [1] "state"      "abb"        "region"     "population" "total"
```

我们的最后一个例子与查找重复项有关。在创建电子表格时，行重复是一个非常常见的错误。`get_dups`函数可以找到并报告重复记录。默认情况下，它考虑所有变量，但你也可以指定使用哪些变量。

```r
x <- bind_rows(x, x[1,])
get_dupes(x)
#> No variable names specified - using all columns.
#>     state abb region population total dupe_count
#> 1 Alabama  AL  South    4779736   135          2
#> 2 Alabama  AL  South    4779736   135          2
```

## 11.6 练习

1. 运行以下命令以定义`co2_wide`对象：

```r
co2_wide <- data.frame(matrix(co2, ncol = 12, byrow = TRUE)) |> 
 setNames(1:12) |>
 mutate(year = as.character(1959:1997))
```

使用`pivot_longer`函数将此整理成整洁数据集。将包含二氧化碳测量的列命名为`co2`，将月份列命名为`month`。将结果对象命名为`co2_tidy`。

2. 使用以下代码绘制二氧化碳与月份的关系图，每年使用不同的曲线：

```r
co2_tidy |> ggplot(aes(month, co2, color = year)) + geom_line()
```

如果预期的图表没有生成，可能是因为`co2_tidy$month`不是数字：

```r
class(co2_tidy$month)
```

重写你的代码以确保月份列是数字的。然后绘制图表。

3. 我们从这个图表中学到了什么？

1.  二氧化碳的测量值从 1959 年到 1997 年单调递增。

1.  二氧化碳的测量值在夏季较高，并且从 1959 年到 1997 年的年平均值有所增加。

1.  二氧化碳的测量值看起来是恒定的，随机变异性解释了差异。

1.  二氧化碳的测量值没有季节性趋势。

4. 现在加载`admissions`数据集，该数据集包含六个专业中男性和女性的录取信息，并仅保留录取百分比列：

```r
load(admissions)
dat <- admissions |> select(-applicants)
```

如果我们把一个观测值看作是一个专业，并且每个观测值有两个变量（男性录取百分比和女性录取百分比），那么这就不整洁。使用`pivot_wider`函数整理成整洁形状：每个专业一行。

5. 现在我们将尝试一个更高级的数据整理挑战。我们想要整理录取数据，以便对于每个专业，我们都有 4 个观测值：`admitted_men`、`admitted_women`、`applicants_men`和`applicants_women`。我们在这里执行的*技巧*实际上相当常见：首先使用`pivot_longer`生成一个中间数据框，然后使用`pivot_wider`获取我们想要的整洁数据。我们将逐步进行，并在接下来的两个练习中也是如此。

使用`pivot_longer`函数创建一个包含观测类型列（`admitted`或`applicants`）的`tmp`数据框。将新列命名为`name`和`value`。

6. 现在你有一个名为 `tmp` 的对象，包含 `major`、`gender`、`name` 和 `value` 列。注意，如果你将 `name` 和 `gender` 结合起来，我们就能得到我们想要的列名：`admitted_men`、`admitted_women`、`applicants_men` 和 `applicants_women`。使用 `unite` 函数创建一个名为 `column_name` 的新列。

7. 现在用 `pivot_wider` 函数生成每个专业有四个变量的整洁数据。

8. 现在用管道符写一行代码，将 `admissions` 转换为上一练习中产生的表格。
