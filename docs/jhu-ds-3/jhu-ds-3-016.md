# 016：汇总数据 📊

![](img/e4fe50d436b67513e91545ea2ad3cd5d_0.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_2.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_3.png)

在本节课中，我们将学习如何对加载到R中的数据进行检查和汇总。这是数据清洗的关键第一步，目的是在开始下游分析之前，识别数据中的异常值、缺失值或其他问题。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_4.png)

## 数据加载与初步查看

首先，我们需要将数据加载到R环境中。本节课我们将使用一个关于巴尔的摩市餐厅的数据集作为示例。该数据集可以从网络获取。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_6.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_7.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_8.png)

以下是加载数据的步骤：

![](img/e4fe50d436b67513e91545ea2ad3cd5d_9.png)

```r
# 创建数据目录（如果不存在）
if(!file.exists("./data")){dir.create("./data")}
# 数据文件的URL
fileUrl <- "https://data.baltimorecity.gov/api/views/k5ry-ef3g/rows.csv?accessType=DOWNLOAD"
# 下载文件
download.file(fileUrl, destfile = "./data/restaurants.csv", method = "curl")
# 读取CSV文件
restData <- read.csv("./data/restaurants.csv")
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_11.png)

数据加载后，我们需要查看其内容。直接输入数据框名称会显示全部数据，但如果数据量很大，显示会不清晰。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_12.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_13.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_14.png)

## 查看数据首尾

![](img/e4fe50d436b67513e91545ea2ad3cd5d_16.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_17.png)

为了有效查看数据，我们可以使用 `head()` 和 `tail()` 函数。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_18.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_19.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_20.png)

`head()` 函数用于查看数据框的前几行。默认显示前6行，但可以通过 `n` 参数指定行数。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_22.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_23.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_24.png)

```r
# 查看数据的前3行
head(restData, n=3)
```

`tail()` 函数则用于查看数据框的末尾几行，用法与 `head()` 类似。

```r
# 查看数据的后3行
tail(restData, n=3)
```

## 数据整体摘要

上一节我们学习了如何查看数据的首尾部分。本节中，我们来看看如何获取数据的整体统计摘要。

`summary()` 函数可以为数据框中的每个变量提供摘要信息。
*   对于文本型或因子型变量，它会显示每个类别的计数。
*   对于数值型变量，它会显示最小值、第一四分位数、中位数、均值、第三四分位数和最大值。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_26.png)

```r
# 获取数据集的统计摘要
summary(restData)
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_27.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_28.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_29.png)

运行 `summary()` 后，我们可能会立即发现一些有趣的信息，例如某个邮政编码被记录为负值，这显然是不合理的。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_31.png)

`str()` 函数可以提供关于数据框结构的更多信息，包括数据框的维度以及每一列的数据类型。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_32.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_33.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_34.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_35.png)

```r
# 查看数据框的结构
str(restData)
```

## 检查数值变量的分布

![](img/e4fe50d436b67513e91545ea2ad3cd5d_37.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_38.png)

了解数值变量的分布情况非常重要。`quantile()` 函数可以帮助我们做到这一点。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_40.png)

例如，我们可以查看“议会选区”这个变量的分位数。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_42.png)

```r
# 查看‘councilDistrict’变量的分位数
quantile(restData$councilDistrict)
```

我们还可以指定想要查看的具体分位点。

```r
# 查看特定分位点（如0%， 50%， 99%）
quantile(restData$councilDistrict, probs = c(0, 0.5, 0.99))
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_44.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_45.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_46.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_47.png)

## 创建频数表

![](img/e4fe50d436b67513e91545ea2ad3cd5d_48.png)

另一种查看数据的方式是为特定变量创建频数表。`table()` 函数可以实现这个功能。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_50.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_51.png)

以下是创建邮政编码频数表的示例：

![](img/e4fe50d436b67513e91545ea2ad3cd5d_52.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_53.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_54.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_55.png)

```r
# 创建邮政编码的频数表
table(restData$zipCode)
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_57.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_58.png)

默认情况下，`table()` 函数不会显示缺失值的数量。为了确保不遗漏缺失值，我们需要使用 `useNA = “ifany”` 参数。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_59.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_61.png)

```r
# 创建包含缺失值计数的频数表
table(restData$zipCode, useNA = "ifany")
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_62.png)

我们还可以创建二维交叉表，来观察两个定性变量之间的关系。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_64.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_65.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_66.png)

```r
# 创建议会选区和邮政编码的二维交叉表
table(restData$councilDistrict, restData$zipCode)
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_67.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_68.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_70.png)

## 检查缺失值

![](img/e4fe50d436b67513e91545ea2ad3cd5d_71.png)

数据清洗中一个关键步骤是检查缺失值。`is.na()` 函数是完成此任务的核心工具。

`is.na()` 函数会返回一个逻辑向量（TRUE/FALSE），指示每个值是否为缺失值（NA）。我们可以对其结果求和来计算缺失值的数量。

```r
# 检查‘councilDistrict’变量中缺失值的数量
sum(is.na(restData$councilDistrict))
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_73.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_74.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_75.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_76.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_77.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_78.png)

此外，`any()` 和 `all()` 函数也很有用。
*   `any()` 检查向量中是否存在至少一个TRUE值。
*   `all()` 检查向量中是否所有值都为TRUE。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_79.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_80.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_81.png)

```r
# 检查‘councilDistrict’变量中是否存在任何缺失值
any(is.na(restData$councilDistrict))
# 检查所有邮政编码是否都大于0
all(restData$zipCode > 0)
```

我们可以将 `is.na()` 与 `colSums()` 结合，快速检查整个数据框中各列的缺失情况。

```r
# 检查数据框每一列的缺失值数量
colSums(is.na(restData))
# 确认所有列的缺失值数量都为0
all(colSums(is.na(restData))==0)
```

## 数据子集与匹配

![](img/e4fe50d436b67513e91545ea2ad3cd5d_83.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_84.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_85.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_86.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_87.png)

有时我们需要根据特定条件筛选数据。`%in%` 运算符在这方面非常高效。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_88.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_89.png)

例如，我们想找出邮政编码为“21212”或“21213”的所有餐厅。

```r
# 创建一个逻辑向量，标识邮政编码是否为21212或21213
zip_match <- restData$zipCode %in% c("21212", "21213")
# 使用该逻辑向量对数据框进行子集筛选
restData[zip_match, ]
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_91.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_92.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_93.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_94.png)

## 创建交叉表与扁平化表

![](img/e4fe50d436b67513e91545ea2ad3cd5d_95.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_96.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_98.png)

对于包含多个分类变量的数据集，交叉表（Cross Tabulation）是分析变量间关系的强大工具。`xtabs()` 函数用于创建交叉表。

我们以R内置的“UCBAdmissions”数据集为例，这是一个关于伯克利分校录取情况的经典数据集。

```r
# 加载数据并创建交叉表，按性别和录取状态分解频数
data("UCBAdmissions")
DF <- as.data.frame(UCBAdmissions)
xtabs(Freq ~ Gender + Admit, data = DF)
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_100.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_101.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_102.png)

当涉及两个以上变量时，交叉表的输出可能很长且难以阅读。这时可以使用 `ftable()` 函数将其扁平化，以更紧凑的格式呈现。

![](img/e4fe50d436b67513e91545ea2ad3cd5d_103.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_104.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_105.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_106.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_107.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_108.png)

```r
# 使用‘warpbreaks’数据集创建多变量交叉表并扁平化
data("warpbreaks")
warpbreaks$replicate <- rep(1:9, len=54)
xt <- xtabs(breaks ~., data=warpbreaks) # 按所有其他变量分解
ftable(xt) # 扁平化表格
```

## 检查对象大小

![](img/e4fe50d436b67513e91545ea2ad3cd5d_110.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_111.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_112.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_113.png)

最后，在处理大型数据集时，了解数据在内存中占用的空间很有用。`object.size()` 函数可以查看对象的大小，`print()` 函数可以指定显示单位。

```r
# 创建一个示例数据并检查其大小
fake_data <- rnorm(1000000)
object_size <- object.size(fake_data)
print(object_size, units="MB") # 以MB为单位打印大小
```

![](img/e4fe50d436b67513e91545ea2ad3cd5d_115.png)

## 总结

![](img/e4fe50d436b67513e91545ea2ad3cd5d_116.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_117.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_118.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_119.png)

![](img/e4fe50d436b67513e91545ea2ad3cd5d_120.png)

本节课中，我们一起学习了在R中汇总和初步探索数据的一系列核心技能。我们掌握了如何查看数据的首尾 (`head`, `tail`)、获取整体摘要 (`summary`, `str`)、检查分布 (`quantile`)、创建频数表和交叉表 (`table`, `xtabs`, `ftable`)、识别缺失值 (`is.na`, `any`, `all`, `colSums`)、根据条件筛选数据子集 (`%in%`)，以及检查数据对象的大小 (`object.size`)。这些是数据清洗过程中至关重要的第一步，能帮助我们快速理解数据质量，为后续的分析和清理工作奠定坚实基础。