# 14  区域设置

> 原文：[`rafalab.dfci.harvard.edu/dsbook-part-1/wrangling/locales.html`](https://rafalab.dfci.harvard.edu/dsbook-part-1/wrangling/locales.html)

1.  数据处理

1.  14  区域设置

计算机设置根据语言和位置而变化，对此可能性的不了解可能会使某些数据处理挑战难以克服。

区域设置的目的在于将可能影响以下方面的常见设置组合在一起：*

1.  月份和日期名称，对于解释日期是必要的。

1.  标准日期格式，对于解释日期也是必要的。

1.  默认时区，对于解释日期时间至关重要。

1.  字符编码，对于读取非 ASCII 字符至关重要。

1.  小数点和数字分组符号，对于解释数值非常重要。

在 R 中，*区域设置*指的是一组设置，这些设置决定了系统如何根据文化惯例行事。这些设置影响数据的格式化和展示方式，包括日期格式、货币符号、小数分隔符和其他相关方面。

R 中的区域设置影响多个领域，包括字符向量的排序方式，以及日期、数字和货币格式。此外，错误、警告和其他消息可能会根据区域设置翻译成除英语以外的语言。

## 14.1 R 中的区域设置

要访问 R 中的当前区域设置，您可以使用 `Sys.getlocale()` 函数：

```r
Sys.getlocale()
#> [1] "en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8"
```

要设置特定的区域设置，请使用 `Sys.setlocale()` 函数。例如，要将区域设置为美国英语：*

```r
Sys.setlocale("LC_ALL", "en_US.UTF-8")
#> [1] "en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8"
```

用于设置区域设置的精确字符串（如“en_US.UTF-8”）可能取决于您的操作系统及其配置。

上面的代码中使用的 `LC_ALL` 指的是所有区域设置类别。R，像许多系统一样，将区域设置分解为类别，每个类别负责以下列出的不同方面。

+   `LC_COLLATE`: 用于字符串排序

+   `LC_TIME`: 日期和时间格式化

+   `LC_MONETARY`: 货币格式化。

+   `LC_MESSAGES`: 系统消息翻译。

+   `LC_NUMERIC`: 数字格式化。

如果您不想通过 `LC_ALL` 改变所有内容，您可以单独为每个类别设置区域设置。

我们已经展示了控制区域设置的工具。这些设置很重要，因为它们会影响您数据的外观和行为。然而，并非所有计算机都提供这些设置；它们的可用性取决于您拥有的计算机类型及其配置。

改变这些设置，尤其是 `LC_NUMERIC`，当您在 R 中处理数字时可能会导致意外问题。例如，如果您习惯于使用点作为小数点，但您的区域设置使用逗号，这种差异在导入数据时可能会引起问题。

重要的一点是要记住，这些区域设置只持续一个 R 会话。如果你在操作时更改它们，当你关闭 R 并再次打开时，它们将恢复到默认设置。***

## ***14.2 `locale` 函数***

**`readr` 包包含一个 `locale()` 函数，可以在 R 中使用它来学习或更改当前的区域设置：

```r
library(readr
locale()
#> <locale>
#> Numbers:  123,456.78
#> Formats:  %AD / %AT
#> Timezone: UTC
#> Encoding: UTF-8
#> <date_names>
#> Days:   Sunday (Sun), Monday (Mon), Tuesday (Tue), Wednesday (Wed),
#>         Thursday (Thu), Friday (Fri), Saturday (Sat)
#> Months: January (Jan), February (Feb), March (Mar), April (Apr), May
#>         (May), June (Jun), July (Jul), August (Aug), September
#>         (Sep), October (Oct), November (Nov), December (Dec)
#> AM/PM:  AM/PM
```

您可以通过输入以下内容来查看系统上可用的所有区域设置：

```r
system("locale -a")
```

这里是你将日期区域设置改为西班牙语时得到的结果：

```r
locale(date_names = "es")
#> <locale>
#> Numbers:  123,456.78
#> Formats:  %AD / %AT
#> Timezone: UTC
#> Encoding: UTF-8
#> <date_names>
#> Days:   domingo (dom.), lunes (lun.), martes (mar.), miércoles (mié.),
#>         jueves (jue.), viernes (vie.), sábado (sáb.)
#> Months: enero (ene.), febrero (feb.), marzo (mar.), abril (abr.), mayo
#>         (may.), junio (jun.), julio (jul.), agosto (ago.),
#>         septiembre (sept.), octubre (oct.), noviembre (nov.),
#>         diciembre (dic.)
#> AM/PM:  a. m./p. m.
```*****

## ****14.3 示例：处理西班牙语数据集****

***在 第 6.3.2 节 中，我们提到读取文件：

```r
fn <- file.path(system.file("extdata", package = "dslabs"), "calificaciones.csv")
```

具有与默认的 UTF-8 编码不同的编码。我们使用了 `guess_encoding` 来确定正确的编码：

```r
guess_encoding(fn)$encoding[1]
#> [1] "ISO-8859-1"
```

并使用 `locale` 函数来更改这一点，并读取此编码：

```r
dat <- read_csv(fn, locale = locale(encoding = "ISO-8859-1"))
```

此文件提供了七个学生的家庭作业分数。列代表学生姓名、他们的出生日期、提交作业的时间以及他们获得的分数。您可以使用 `read_lines` 查看整个文件：

```r
read_lines(fn, locale = locale(encoding = "ISO-8859-1"))
#> [1] "\"nombre\",\"f.n.\",\"estampa\",\"puntuación\"" 
#> [2] "\"Beyoncé\",\"04 de septiembre de 1981\",2023-09-22 02:11:02,\"87,5\""
#> [3] "\"Blümchen\",\"20 de abril de 1980\",2023-09-22 03:23:05,\"99,0\"" 
#> [4] "\"João\",\"10 de junio de 1931\",2023-09-21 22:43:28,\"98,9\"" 
#> [5] "\"López\",\"24 de julio de 1969\",2023-09-22 01:06:59,\"88,7\"" 
#> [6] "\"Ñengo\",\"15 de diciembre de 1981\",2023-09-21 23:35:37,\"93,1\"" 
#> [7] "\"Plácido\",\"24 de enero de 1941\",2023-09-21 23:17:21,\"88,7\"" 
#> [8] "\"Thalía\",\"26 de agosto de 1971\",2023-09-21 23:08:02,\"83,0\""
```

作为一个说明性的例子，我们将编写代码来计算学生的年龄并检查他们是否在 2023 年 9 月 21 日午夜之前提交了作业：

我们可以用正确的编码读取文件，如下所示：

```r
dat <- read_csv(fn, locale = locale(encoding = "ISO-8859-1"))
```

然而，请注意，最后一列，本应包含 0 到 100 之间的考试分数，显示的数字大于 800：

```r
dat$puntuación
#> [1] 875 990 989 887 931 887 830
```

这是因为文件中的分数使用的是欧洲的十进制点，这会混淆 `read_csv`。

为了解决这个问题，我们也可以将编码更改为使用欧洲十进制，这可以修复问题：

```r
dat <- read_csv(fn, locale = locale(decimal_mark = ",",
 encoding = "ISO-8859-1"))
dat$puntuación
#> [1] 87.5 99.0 98.9 88.7 93.1 88.7 83.0
```

现在，为了计算学生年龄，让我们尝试将提交时间更改为日期格式：

```r
library(lubridate
#> 
#> Attaching package: 'lubridate'
#> The following objects are masked from 'package:base':
#> 
#>     date, intersect, setdiff, union
dmy(dat$f.n.)
#> Warning: All formats failed to parse. No formats found.
#> [1] NA NA NA NA NA NA NA
```

没有任何内容被正确转换。这是因为日期是西班牙语。我们可以将区域设置更改为使用西班牙语作为日期的语言：

```r
parse_date(dat$f.n., format = "%d de %B de %Y", locale = locale(date_names = "es"))
#> [1] "1981-09-04" "1980-04-20" "1931-06-10" "1969-07-24" "1981-12-15"
#> [6] "1941-01-24" "1971-08-26"
```

我们也可以使用正确的区域设置重新读取文件：

```r
dat <- read_csv(fn, locale = locale(date_names = "es",
 date_format = "%d de %B de %Y",
 decimal_mark = ",",
 encoding = "ISO-8859-1"))
```

计算学生的年龄现在变得简单：

```r
time_length](https://lubridate.tidyverse.org/reference/time_length.html)(today() - dat$f.n., unit = "years") |> [floor()
#> [1] 44 45 94 56 43 84 54
```

最后，让我们检查哪些学生在 9 月 22 日的截止日期之后提交了他们的作业：

```r
dat$estampa >= make_date(2023, 9, 22)
#> [1]  TRUE  TRUE FALSE  TRUE FALSE FALSE FALSE
```

我们看到有两个学生迟交了。然而，由于时间，我们必须特别小心，因为一些函数默认使用 UTC 时区：

```r
tz(dat$estampa)
#> [1] "UTC"
```

如果我们将其更改为东部标准时间（EST），我们看到没有人迟交：

```r
with_tz(dat$estampa, tz =  "EST") >= make_date(2023, 9, 22)
#> [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE
```*****************

## ****14.4 练习****

***1\. 加载 **lubridate** 包并将区域设置为此练习的法国。

2\. 创建一个包含以下数字的数值向量：12345.67, 9876.54, 3456.78, 和 5432.10。

3\. 使用 `format()` 函数将数值向量格式化为货币，显示以欧元表示的值。确保根据法国区域设置正确表示小数点。打印格式化的货币值。

4. 创建一个包含三个日期的日期向量：1789 年 7 月 14 日、1803 年 1 月 1 日和 1962 年 7 月 5 日。使用 `format()` 函数将日期向量格式化为“dd 月 yyyy”格式，其中“月”应使用法语显示。确保月份名称根据法语地区正确翻译。打印格式化后的日期值。

5. 将地区重置为默认设置（例如，“C”或“en_US.UTF-8”），以恢复标准格式。

6. 对数值向量重复步骤 2-4，对日期向量重复步骤 5-7，以观察标准格式。****
