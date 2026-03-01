# 004：使用R下载文件 📥

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_0.png)

在本节课中，我们将学习如何使用R编程语言从互联网下载文件。我们将了解为何在脚本中自动化下载过程比手动点击下载更具优势，并掌握相关的R函数和最佳实践。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_2.png)

---

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_3.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_4.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_5.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_6.png)

## 工作目录管理 🗂️

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_8.png)

在开始下载文件之前，我们需要明确当前的工作目录。工作目录是R读取和保存文件的默认位置。如果你学习过数据科学工具箱课程，应该对`cd`命令和目录操作有基本了解。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_9.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_10.png)

在R中，管理目录的两个主要命令是`getwd()`和`setwd()`。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_12.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_13.png)

*   `getwd()`：获取当前工作目录。它告诉你R当前在哪个文件夹中操作。
*   `setwd()`：设置新的工作目录。你可以用它切换到其他文件夹。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_14.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_15.png)

### 设置目录路径

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_17.png)

有两种方式可以指定`setwd()`的路径：相对路径和绝对路径。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_18.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_19.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_20.png)

以下是使用相对路径的例子。使用`..`可以向上移动一级目录。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_22.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_23.png)

```r
setwd("../")
```

以下是使用绝对路径的例子。这会直接将你切换到指定的完整路径。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_25.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_26.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_27.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_28.png)

```r
setwd("/Users/jtleek/data")
```

**注意**：在Windows系统中，路径需要使用反斜杠`\`，而不是在Mac或Linux中使用的正斜杠`/`。如果你需要更多关于路径的帮助，请回顾数据科学工具箱课程。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_30.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_31.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_32.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_33.png)

---

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_35.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_36.png)

## 创建数据目录 📁

在收集数据之前，我们通常希望创建一个专门的目录来存放数据。`file.exists()`函数可以帮助我们检查目录是否已存在。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_38.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_39.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_40.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_41.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_42.png)

`file.exists("directory_name")`会在当前目录下查找名为“directory_name”的子目录。如果目录存在，函数返回`TRUE`；如果不存在，则返回`FALSE`。

`dir.create()`函数用于创建目录。以下是一段常用代码，它检查“data”目录是否存在，如果不存在则创建它。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_44.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_45.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_46.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_47.png)

```r
if (!file.exists("data")) {
    dir.create("data")
}
```

这段代码的逻辑是：如果“data”目录不存在（`file.exists("data")`为`FALSE`），则`!`操作符将其变为`TRUE`，进而执行`dir.create("data")`来创建目录。

---

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_49.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_50.png)

## 使用`download.file`下载数据 🌐

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_51.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_52.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_53.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_54.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_55.png)

从互联网获取文件的主要方式是使用R的`download.file()`函数。虽然你可以手动访问网站并点击下载，但使用`download.file()`将下载过程整合到脚本中，能极大地提高分析的可复现性。这意味着你的整个数据处理流程，从获取数据开始，都被完整记录了下来。

`download.file()`函数有几个重要参数：
*   `url`：数据来源的网址。
*   `destfile`：文件下载后的保存路径和文件名。
*   `method`：下载方法，在处理某些协议（如HTTPS）时需要指定。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_57.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_58.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_59.png)

这个函数用途广泛，可以下载制表符分隔文件、CSV文件、Excel文件等多种类型的网络文件。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_61.png)

### 实践示例：下载巴尔的摩摄像头数据

我们将以巴尔的摩固定摄像头数据为例。这些是设置在巴尔的摩各处的测速摄像头数据。

1.  在数据网页上，找到“导出”按钮，选择CSV格式。
2.  右键点击CSV链接，选择“复制链接地址”。
3.  在R中，将这个链接地址保存到一个变量中。

```r
fileUrl <- "https://data.baltimorecity.gov/api/views/dz54-2aru/rows.csv?accessType=DOWNLOAD"
```

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_63.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_64.png)

4.  使用`download.file()`函数下载文件。我们指定将文件保存到“data”目录下，并命名为“cameras.csv”。由于这是一个HTTPS安全网站，在Mac系统上需要将`method`参数设置为`"curl"`。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_66.png)

```r
download.file(fileUrl, destfile = "./data/cameras.csv", method = "curl")
```

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_67.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_68.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_69.png)

5.  下载完成后，可以使用`list.files()`函数（类似于命令行中的`ls`命令）查看“data”目录下的文件，确认`cameras.csv`已存在。

```r
list.files("./data")
```

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_71.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_72.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_73.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_74.png)

### 记录下载日期 📅

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_76.png)

从网上下载的文件可能会更新。例如，摄像头数据可能会增加新的点位。因此，记录数据下载的日期非常重要，这有助于你在后续分析中追溯所使用的数据版本。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_77.png)

你可以使用`date()`函数来记录下载时间。

```r
dateDownloaded <- date()
```

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_79.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_80.png)

### 关于`method`参数的注意事项

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_81.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_82.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_83.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_84.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_85.png)

*   如果URL以`http://`开头，通常不需要特别设置`method`。
*   如果URL以`https://`开头：
    *   在Windows系统上，通常使用默认方法即可。
    *   在Mac系统上，需要将`method`参数设置为`"curl"`。

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_87.png)

### 性能与最佳实践

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_88.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_89.png)

`download.file()`会从互联网获取文件，下载时间取决于文件大小和你的网络连接速度。对于非常大的文件，你可能不希望每次运行脚本时都重新下载。一个常见的做法是将下载代码包含在脚本中，但在后续运行时，如果数据文件已存在且无需更新，可以注释掉下载部分。同时，务必记录下载日期以备查证。

---

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_91.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_92.png)

## 总结

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_93.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_94.png)

![](img/c4e14fee2b58ea66518883ae0dbc7bb7_95.png)

本节课我们一起学习了如何使用R从互联网下载文件。我们首先了解了如何通过`getwd()`和`setwd()`管理R的工作目录，然后学习了如何使用`file.exists()`和`dir.create()`创建用于存放数据的目录。核心内容是使用`download.file()`函数自动化下载过程，并通过一个巴尔的摩摄像头数据的实例进行了演练。我们还强调了记录下载日期的重要性，并讨论了在不同操作系统（特别是Mac）上下载HTTPS文件时设置`method = "curl"`的注意事项。掌握这些技能，能使你的数据分析流程更加完整和可复现。