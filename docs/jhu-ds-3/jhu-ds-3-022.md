# 022：编辑文本变量 📝

在本节课中，我们将学习如何通过编程方式操作数据集中的文本变量。这是一个非常常见的数据清理步骤，用于处理格式混乱、包含多余空格、句点或下划线的文本，以便获得整洁的变量名和数据集内容。

![](img/a5ca6491b12470ff23d861e542e7b24f_1.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_2.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_3.png)

## 概述与数据准备

我们将使用两个示例数据集来演示文本编辑技巧：巴尔的摩固定摄像头数据和同行评审实验数据。

首先，我们需要下载并加载巴尔的摩摄像头数据。

```r
# 检查并创建数据目录
if (!file.exists("data")) {
    dir.create("data")
}
# 下载数据
fileUrl <- "https://data.baltimorecity.gov/api/views/dz54-2aru/rows.csv?accessType=DOWNLOAD"
download.file(fileUrl, destfile = "./data/cameras.csv", method = "curl")
# 读取数据
cameraData <- read.csv("./data/cameras.csv")
```

加载数据后，我们可以查看其列名。

```r
names(cameraData)
```

![](img/a5ca6491b12470ff23d861e542e7b24f_5.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_6.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_8.png)

## 转换字母大小写

查看列名时，你可能会发现不一致的大小写，例如变量 `crossStreet` 中有一个大写字母“S”。虽然看似小事，但在输入时容易因大小写错误导致R报错。一个解决方案是将所有字母转换为小写。

![](img/a5ca6491b12470ff23d861e542e7b24f_10.png)

R中的 `tolower()` 函数可以实现这一功能。

```r
tolower(names(cameraData))
```

同样，如果需要将所有字母转换为大写，可以使用 `toupper()` 函数。

上一节我们介绍了如何统一字母大小写，本节中我们来看看如何处理变量名中的分隔符。

![](img/a5ca6491b12470ff23d861e542e7b24f_12.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_13.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_14.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_15.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_16.png)

## 分割文本变量

![](img/a5ca6491b12470ff23d861e542e7b24f_17.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_18.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_19.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_20.png)

另一个常见情况是变量名中包含句点等分隔符。例如，数据中的 `location.1` 变量。这通常发生在从文件加载数据时。

![](img/a5ca6491b12470ff23d861e542e7b24f_21.png)

我们可以使用 `strsplit()` 函数来分割这些文本。

![](img/a5ca6491b12470ff23d861e542e7b24f_23.png)

```r
splitNames <- strsplit(names(cameraData), "\\.")
```

这里需要使用转义字符 `\\`，因为句点在正则表达式中是保留字符。`strsplit()` 函数返回一个列表。

![](img/a5ca6491b12470ff23d861e542e7b24f_25.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_26.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_27.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_28.png)

查看列表的第六个元素，可以看到 `location.1` 被分割成了“location”和“1”两部分，句点已被移除。

![](img/a5ca6491b12470ff23d861e542e7b24f_29.png)

为了深入理解后续操作，我们需要简要回顾一下R中列表的索引方式。

![](img/a5ca6491b12470ff23d861e542e7b24f_31.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_32.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_33.png)

## 列表索引快速回顾

以下是如何创建和操作列表的示例。

```r
myList <- list(letters = c("A", "b", "c"), numbers = 1:3, matrix(1:25, ncol=5))
```

我们可以通过多种方式访问列表元素。

```r
# 访问第一个元素
myList[1]
# 通过名称访问
myList$letters
# 访问第一个元素的实际内容（向量）
myList[[1]]
```

![](img/a5ca6491b12470ff23d861e542e7b24f_35.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_36.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_37.png)

理解了列表索引后，我们可以回到分割变量名的问题上。

![](img/a5ca6491b12470ff23d861e542e7b24f_38.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_39.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_40.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_41.png)

## 提取分割后的部分

![](img/a5ca6491b12470ff23d861e542e7b24f_42.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_43.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_44.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_45.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_46.png)

我们可能只想保留被句点分割后的第一部分变量名。例如，对于 `location.1`，我们只想要“location”。

我们可以编写一个函数来提取列表每个元素的第一个部分，然后使用 `sapply()` 函数将其应用到整个列表上。

```r
# 定义一个提取第一个元素的函数
firstElement <- function(x){x[1]}
# 应用函数
sapply(splitNames, firstElement)
```

这样，所有变量名中的句点及后续部分都被移除了。

接下来，我们将使用另一个数据集来展示更多的文本操作技巧。

## 替换特定字符

![](img/a5ca6491b12470ff23d861e542e7b24f_48.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_49.png)

现在，我们加载同行评审实验数据。

![](img/a5ca6491b12470ff23d861e542e7b24f_50.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_51.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_52.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_53.png)

```r
# 下载数据
fileUrl1 <- "https://dl.dropboxusercontent.com/u/7710864/data/reviews-apr29.csv"
fileUrl2 <- "https://dl.dropboxusercontent.com/u/7710864/data/solutions-apr29.csv"
download.file(fileUrl1, destfile = "./data/reviews.csv", method = "curl")
download.file(fileUrl2, destfile = "./data/solutions.csv", method = "curl")
# 读取数据
reviews <- read.csv("./data/reviews.csv")
solutions <- read.csv("./data/solutions.csv")
```

![](img/a5ca6491b12470ff23d861e542e7b24f_54.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_55.png)

查看数据，我们发现一些变量名包含下划线，如 `solution_id`、`reviewer_id`。我们可能希望移除这些下划线。

可以使用 `sub()` 函数进行替换。

```r
# 将第一个下划线替换为空（即删除）
sub("_", "", names(reviews))
```

`sub()` 函数只替换第一个匹配项。如果要替换所有匹配项，需要使用 `gsub()` 函数。

以下是两者的区别示例。

![](img/a5ca6491b12470ff23d861e542e7b24f_57.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_58.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_59.png)

```r
testName <- "this_is_a_test"
# 只替换第一个下划线
sub("_", "", testName)
# 输出: "thisis_a_test"

![](img/a5ca6491b12470ff23d861e542e7b24f_60.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_61.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_62.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_63.png)

# 替换所有下划线
gsub("_", "", testName)
# 输出: "thisisatest"
```

![](img/a5ca6491b12470ff23d861e542e7b24f_64.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_65.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_66.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_67.png)

这些函数不仅可以用于变量名，也可以用于数据集中的实际文本值。

学会了替换字符，我们接下来学习如何在文本中搜索特定值。

![](img/a5ca6491b12470ff23d861e542e7b24f_69.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_70.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_71.png)

## 搜索特定值

![](img/a5ca6491b12470ff23d861e542e7b24f_72.png)

我们回到巴尔的摩摄像头数据，查看 `intersection` 变量。假设我们想找出所有包含“Alameda”的道路交叉口。

可以使用 `grep()` 函数进行搜索。

![](img/a5ca6491b12470ff23d861e542e7b24f_74.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_75.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_76.png)

```r
# 查找包含“Alameda”的条目索引
grep("Alameda", cameraData$intersection)
```

![](img/a5ca6491b12470ff23d861e542e7b24f_77.png)

函数返回了 `intersection` 向量中“Alameda”出现的位置（第4、5、36个元素）。

另一个有用的函数是 `grepl()`，它返回一个逻辑向量（TRUE/FALSE），指示搜索词是否出现在每个元素中。

![](img/a5ca6491b12470ff23d861e542e7b24f_79.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_80.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_81.png)

```r
# 返回逻辑向量
grepl("Alameda", cameraData$intersection)
# 统计出现次数
table(grepl("Alameda", cameraData$intersection))
```

![](img/a5ca6491b12470ff23d861e542e7b24f_82.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_83.png)

我们可以利用这个逻辑向量来对数据进行子集筛选。

```r
# 筛选出包含“Alameda”的数据
cameraData2 <- cameraData[!grepl("Alameda", cameraData$intersection), ]
```

关于 `grep()` 函数，还有更多用法。通过设置参数 `value=TRUE`，可以直接返回匹配的文本值，而不是索引。

```r
# 返回匹配的文本值
grep("Alameda", cameraData$intersection, value=TRUE)
```

![](img/a5ca6491b12470ff23d861e542e7b24f_85.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_86.png)

此外，还可以用它来检查某个值是否出现。如果 `grep()` 返回的向量长度为0，则表示未找到。

![](img/a5ca6491b12470ff23d861e542e7b24f_87.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_88.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_89.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_90.png)

```r
# 检查“JeffStreet”是否出现
grep("JeffStreet", cameraData$intersection)
length(grep("JeffStreet", cameraData$intersection))
```

![](img/a5ca6491b12470ff23d861e542e7b24f_91.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_92.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_93.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_94.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_95.png)

掌握了搜索功能后，我们最后来看一些其他有用的字符串函数。

## 其他有用的字符串函数

`nchar()` 函数可以计算字符串中的字符数。

![](img/a5ca6491b12470ff23d861e542e7b24f_97.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_98.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_99.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_100.png)

```r
nchar("Jeffrey Leek")
# 输出: 12
```

![](img/a5ca6491b12470ff23d861e542e7b24f_101.png)

`substr()` 函数可以提取字符串的子串。

![](img/a5ca6491b12470ff23d861e542e7b24f_103.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_104.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_105.png)

```r
# 提取第1到第7个字符
substr("Jeffrey Leek", 1, 7)
# 输出: "Jeffrey"
```

`paste()` 函数可以将多个字符串连接在一起。

![](img/a5ca6491b12470ff23d861e542e7b24f_107.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_108.png)

```r
paste("Jeffrey", "Leek")
# 输出: "Jeffrey Leek"
```

![](img/a5ca6491b12470ff23d861e542e7b24f_109.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_110.png)

可以通过 `sep` 参数设置分隔符。如果希望直接拼接而无空格，可以使用专门的 `paste0()` 函数。

![](img/a5ca6491b12470ff23d861e542e7b24f_112.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_113.png)

```r
paste0("Jeffrey", "Leek")
# 输出: "JeffreyLeek"
```

![](img/a5ca6491b12470ff23d861e542e7b24f_114.png)

最后，`stringr` 包中的 `str_trim()` 函数可以非常方便地去除字符串首尾的空格。

![](img/a5ca6491b12470ff23d861e542e7b24f_116.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_117.png)

```r
# 假设已安装并加载stringr包
library(stringr)
str_trim("Jeff      ")
# 输出: "Jeff"
```

![](img/a5ca6491b12470ff23d861e542e7b24f_118.png)

## 总结与最佳实践

![](img/a5ca6491b12470ff23d861e542e7b24f_120.png)

本节课中，我们一起学习了在R中编辑和清理文本变量的多种方法。

以下是关于数据集中文本处理的一些重要原则：

![](img/a5ca6491b12470ff23d861e542e7b24f_122.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_123.png)

*   **统一小写**：尽可能使用全小写字母，因为遗漏的大小写可能导致难以发现的错误。
*   **具有描述性**：变量名应具有描述性（例如用 `diagnosis` 而非 `dx`）。
*   **保持简洁**：变量名不应重复，并应避免使用下划线、句点或空格。我们已经学习了如何移除它们。
*   **合理处理因子**：具有字符值的变量通常应转换为因子变量，但这取决于具体应用。
*   **使用明确标签**：变量值应使用描述性标签。例如，用“TRUE”/“FALSE”而非“1”/“0”；用“male”/“female”而非“M”/“F”。这使数据更易于理解。

![](img/a5ca6491b12470ff23d861e542e7b24f_124.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_125.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_126.png)

![](img/a5ca6491b12470ff23d861e542e7b24f_127.png)

遵循这些原则，可以使你的数据集更整洁、更易于分析，并减少后续工作中的错误。