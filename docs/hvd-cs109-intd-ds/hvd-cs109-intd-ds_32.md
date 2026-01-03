# 第二十一章 重塑数据

> 原文：[`rafalab.dfci.harvard.edu/dsbook/reshaping-data.html`](https://rafalab.dfci.harvard.edu/dsbook/reshaping-data.html)

正如我们在书中所见，拥有*整洁*格式的数据是 tidyverse 流畅运行的关键。在数据分析过程的第一步，即导入数据之后，一个常见的下一步是将数据重塑成便于后续分析的形式。**tidyr**包包含几个对整理数据有用的函数。

我们将使用第 4.1 节中描述的生育宽格式数据集作为本节的示例。

```r
library(tidyverse) 
library(dslabs)
path <- system.file("extdata", package="dslabs")
filename <- file.path(path, "fertility-two-countries-example.csv")
wide_data <- read_csv(filename)
```

## 21.1 `pivot_longer`

**tidyr**包中最常用的函数之一是`pivot_longer`，它用于将宽数据转换为整洁数据。

与大多数 tidyverse 函数一样，`pivot_longer`函数的第一个参数是要转换的数据框。我们希望重塑`wide_data`数据集，使得每一行代表一个生育观察值，这意味着我们需要三个列来存储年份、国家和观察值。在其当前形式中，不同年份的数据分布在不同的列中，年份值存储在列名中。通过`names_to`和`values_to`参数，我们将告诉`pivot_longer`我们想要分配给包含当前列名和观察值的列的列名。默认名称是`name`和`value`，这些通常是可用的选择。在这种情况下，这两个参数的更好选择可能是`year`和`fertility`。请注意，数据文件中任何地方都没有告诉我们这是生育数据。相反，我们是从文件名中解读出来的。通过`cols`参数，我们指定的第二个参数是包含观察值的列；这些是将会被旋转的列。默认情况下是旋转所有列，所以大多数情况下，我们必须指定这些列。在我们的例子中，我们想要`1960`、`1961`直到`2015`这些列。

旋转生育数据的代码因此看起来是这样的：

```r
new_tidy_data <- pivot_longer(wide_data, `1960`:`2015`, names_to = "year", values_to = "fertility")
```

我们也可以使用管道操作符像这样：

```r
new_tidy_data <- wide_data |> 
 pivot_longer(`1960`:`2015`, names_to = "year", values_to = "fertility")
```

我们可以看到，数据已经被转换为整洁格式，列有`year`和`fertility`：

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

由于我们有两个国家，并且这个列没有被旋转，所以每个年份都会产生两行。以更快捷的方式编写此代码是指定哪些列**不**包含在旋转中，而不是所有将被旋转的列：

```r
new_tidy_data <- wide_data |>
 pivot_longer(-country, names_to = "year", values_to = "fertility")
```

`new_tidy_data`对象看起来就像我们这样定义的原始`tidy_data`。

```r
data("gapminder")
tidy_data <- gapminder |> 
 filter(country %in% c("South Korea", "Germany") & !is.na(fertility)) |>
 select(country, year, fertility)
```

只有一个细微的差别。你能找到吗？看看年份列的数据类型：

```r
class(tidy_data$year)
#> [1] "integer"
class(new_tidy_data$year)
#> [1] "character"
```

`pivot_longer`函数假设列名是字符。因此，在我们准备好绘制图表之前，我们需要进行一些额外的处理。我们需要将年份列转换为数字：

```r
new_tidy_data <- wide_data |>
 pivot_longer(-country, names_to = "year", values_to = "fertility") |>
 mutate(year = as.integer(year))
```

注意，我们也可以使用`mutate`和`as.numeric`。

现在数据已经整理好了，我们可以使用这个相对简单的 ggplot 代码：

```r
new_tidy_data |> ggplot(aes(year, fertility, color = country)) + 
 geom_point()
```

## 21.2 `pivot_wider`

正如我们将在后面的示例中看到的那样，有时为了数据整理的目的，将整洁数据转换为宽数据是有用的。我们通常将其用作整理数据的一个中间步骤。`pivot_wider`函数基本上是`pivot_longer`的逆函数。第一个参数是数据，但由于我们正在使用管道，所以我们没有显示它。`names_from`参数告诉`pivot_wider`哪个变量将被用作列名。`values_from`参数指定了用于填充单元格的变量。

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

## 21.3 `分离`

与通常所需相比，上述数据整理很简单。在我们的示例电子表格文件中，我们包括了一个稍微复杂一点的说明。它包含两个变量：预期寿命和生育率。然而，它的存储方式并不整洁，正如我们将解释的那样，也不是最优的。

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

首先，请注意数据是宽格式。其次，请注意这个表格包括两个变量的值，即生育率和预期寿命，列名编码了哪一列代表哪个变量。在列名中编码信息是不推荐的，但不幸的是，这相当常见。我们将运用我们的整理技能来提取这些信息，并以整洁的方式存储。

我们可以使用`pivot_longer`函数开始数据整理，但我们应该不再使用`year`作为新列的列名，因为它还包含变量类型。我们暂时将其称为`name`，这是默认值：

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

结果并不完全是我们所说的整洁，因为每个观测值与两行相关联，而不是一行。我们希望将两个变量的值，即生育率和预期寿命，放在两个单独的列中。实现这一目标的第一大挑战是将`name`列分离成年份和变量类型。请注意，这个列中的条目使用下划线`_`将年份和变量名分开：

```r
dat$name[1:5]
#> [1] "1960_fertility"       "1960_life_expectancy" "1961_fertility" 
#> [4] "1961_life_expectancy" "1962_fertility"
```

在列名中编码多个变量是一个如此常见的问题，以至于`readr`包包含一个函数来将这些列分离成两个或更多。除了数据之外，`separate`函数还接受三个参数：要分离的列名、用于新列的名称以及分隔变量的字符。因此，第一次尝试如下：

```r
dat |> separate(name, c("year", "name"), "_")
```

由于`_`是`separate`默认的假设分隔符，我们不需要在代码中包含它：

```r
dat |> separate(name, c("year", "name"))
#> Warning: Expected 2 pieces. Additional pieces
#> discarded in 112 rows [2, 4, 6, 8, 10,
#> 12, 14, 16, 18, 20, 22, 24, 26, 28, 30,
#> 32, 34, 36, 38, 40, ...].
#> # A tibble: 224 × 4
#>   country year  name      value
#>   <chr>   <chr> <chr>     <dbl>
#> 1 Germany 1960  fertility  2.41
#> 2 Germany 1960  life      69.3 
#> 3 Germany 1961  fertility  2.44
#> 4 Germany 1961  life      69.8 
#> 5 Germany 1962  fertility  2.47
#> # ℹ 219 more rows
```

函数确实分离了值，但我们遇到了一个新的问题。我们收到警告`在 112 个位置值过多:`并且`life_expectancy`变量被截断为`life`。这是因为下划线`_`被用来分隔`life`和`expectancy`，而不仅仅是年份和变量名！我们可以添加第三个列来捕捉这一点，并让`separate`函数知道当没有第三个值时，应该用缺失值`NA`填充哪个列。在这里，我们告诉它填充右侧的列：

```r
var_names <- c("year", "first_variable_name", "second_variable_name")
dat |> separate(name, var_names, fill = "right")
#> # A tibble: 224 × 5
#>   country year  first_variable_name second_variable_name value
#>   <chr>   <chr> <chr>               <chr>                <dbl>
#> 1 Germany 1960  fertility           <NA>                  2.41
#> 2 Germany 1960  life                expectancy           69.3 
#> 3 Germany 1961  fertility           <NA>                  2.44
#> 4 Germany 1961  life                expectancy           69.8 
#> 5 Germany 1962  fertility           <NA>                  2.47
#> # ℹ 219 more rows
```

然而，如果我们阅读`separate`的帮助文件，我们会发现更好的方法是在存在额外分离时合并最后两个变量：

```r
dat |> separate(name, c("year", "name"), extra = "merge")
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

这实现了我们想要的分离。然而，我们还没有完成。我们需要为每个变量创建一个列。正如我们所学的，`pivot_wider`函数可以做到这一点：

```r
dat |> 
 separate(name, c("year", "name"), extra = "merge") |>
 pivot_wider()
#> # A tibble: 112 × 4
#>   country year  fertility life_expectancy
#>   <chr>   <chr>     <dbl>           <dbl>
#> 1 Germany 1960       2.41            69.3
#> 2 Germany 1961       2.44            69.8
#> 3 Germany 1962       2.47            70.0
#> 4 Germany 1963       2.49            70.1
#> 5 Germany 1964       2.49            70.7
#> # ℹ 107 more rows
```

数据现在以整洁格式存在，每行一个观察值，包含三个变量：年份、生育率和预期寿命。

## 21.4 `unite`

有时做`separate`的逆操作很有用，即将两列合并为一列。为了演示如何使用`unite`，我们展示了以下代码，尽管这不是最佳方法，但它可以作为示例。假设我们不知道`extra`，并使用此命令进行分离：

```r
var_names <- c("year", "first_variable_name", "second_variable_name")
dat |> 
 separate(name, var_names, fill = "right")
#> # A tibble: 224 × 5
#>   country year  first_variable_name second_variable_name value
#>   <chr>   <chr> <chr>               <chr>                <dbl>
#> 1 Germany 1960  fertility           <NA>                  2.41
#> 2 Germany 1960  life                expectancy           69.3 
#> 3 Germany 1961  fertility           <NA>                  2.44
#> 4 Germany 1961  life                expectancy           69.8 
#> 5 Germany 1962  fertility           <NA>                  2.47
#> # ℹ 219 more rows
```

我们可以通过合并第二列和第三列，然后旋转列并将`fertility_NA`重命名为`fertility`来实现相同的结果：

```r
dat |> 
 separate(name, var_names, fill = "right") |>
 unite(name, first_variable_name, second_variable_name) |>
 pivot_wider() |>
 rename(fertility = fertility_NA)
#> # A tibble: 112 × 4
#>   country year  fertility life_expectancy
#>   <chr>   <chr>     <dbl>           <dbl>
#> 1 Germany 1960       2.41            69.3
#> 2 Germany 1961       2.44            69.8
#> 3 Germany 1962       2.47            70.0
#> 4 Germany 1963       2.49            70.1
#> 5 Germany 1964       2.49            70.7
#> # ℹ 107 more rows
```

## 21.5 练习

1. 运行以下命令以定义`co2_wide`对象：

```r
co2_wide <- data.frame(matrix(co2, ncol = 12, byrow = TRUE)) |> 
 setNames(1:12) |>
 mutate(year = as.character(1959:1997))
```

使用`pivot_longer`函数将此整理成整洁的数据集。将包含二氧化碳测量值的列命名为`co2`，将月份列命名为`month`。将结果对象命名为`co2_tidy`。

2. 使用以下代码绘制二氧化碳与月份的关系图，每年使用不同的曲线：

```r
co2_tidy |> ggplot(aes(month, co2, color = year)) + geom_line()
```

如果预期的图形没有生成，可能是因为`co2_tidy$month`不是数值型：

```r
class(co2_tidy$month)
```

重新编写你的代码以确保月份列是数值型的。然后绘制图形。

3. 我们从这个图中能学到什么？

1.  二氧化碳测量值从 1959 年到 1997 年单调递增。

1.  二氧化碳测量值在夏季较高，并且从 1959 年到 1997 年，年平均值有所增加。

1.  二氧化碳测量值看起来是恒定的，随机变异性解释了差异。

1.  二氧化碳测量值没有季节性趋势。

4. 现在加载`admissions`数据集，该数据集包含六个专业的男女录取信息，并仅保留录取百分比列：

```r
load(admissions)
dat <- admissions |> select(-applicants)
```

如果我们将观察视为一个专业，并且认为每个观察都有两个变量（男性录取百分比和女性录取百分比），那么这就不整洁。使用`pivot_wider`函数将其整理成整洁的形状：每个专业一行。

5. 现在我们将尝试一个更高级的整理挑战。我们想要整理录取数据，以便对于每个专业，我们有 4 个观察值：`admitted_men`、`admitted_women`、`applicants_men`和`applicants_women`。我们在这里执行的*技巧*实际上相当常见：首先使用`pivot_longer`生成一个中间数据框，然后使用`pivot_wider`获得我们想要的整洁数据。我们将逐步进行，并在接下来的两个练习中这样做。

使用`pivot_longer`函数创建一个包含观察类型`admitted`或`applicants`的列的`tmp`数据框。将新列命名为`name`和`value`。

6. 现在你有一个名为 `tmp` 的对象，包含列 `major`、`gender`、`name` 和 `value`。注意，如果你将 `name` 和 `gender` 结合起来，我们就能得到我们想要的列名：`admitted_men`、`admitted_women`、`applicants_men` 和 `applicants_women`。使用 `unite` 函数创建一个名为 `column_name` 的新列。

7. 现在用 `pivot_wider` 函数生成每个专业有四个变量的整洁数据。

8. 现在用管道符写一行代码，将 `admissions` 转换为上一练习中产生的表格。
