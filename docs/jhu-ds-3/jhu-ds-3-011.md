# 011：从HDF5文件读取数据 📂

![](img/e29bb9cccc66c4b6bb9ad745fe640974_1.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_3.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_4.png)

在本节课中，我们将学习如何从HDF5格式的文件中读取数据。HDF5是一种用于存储大型和结构化数据集的格式，广泛应用于科学计算和大数据领域。我们将了解其基本结构，并学习使用R语言中的`rhdf5`包来创建、写入和读取HDF5文件。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_6.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_7.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_9.png)

## 概述：什么是HDF5？ 🗂️

![](img/e29bb9cccc66c4b6bb9ad745fe640974_11.png)

HDF5用于存储大型数据集，也用于存储结构化数据集，它支持存储多种数据类型。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_12.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_13.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_14.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_15.png)

HDF代表**分层数据格式**。这是因为数据存储在**组**中，每个组包含零个或多个**数据集**及其**元数据**。

每个组都有一个组头，包含组名和该组对应的属性列表。它们还有一个组符号表，其中列出了组中的对象。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_17.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_18.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_19.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_20.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_21.png)

数据集则是多维元素数组及其元数据。它们可以有一个包含名称、数据类型、数据空间和存储布局的头部，以及一个数据数组，你可以将其视为HDF5元素的数据框架。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_23.png)

如果你想了解更多关于HDF5存储结构的信息，可以访问HDF5 Group的官方网站。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_25.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_26.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_27.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_28.png)

## 安装与加载rhdf5包 🔧

![](img/e29bb9cccc66c4b6bb9ad745fe640974_30.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_31.png)

`rhdf5`包需要通过Bioconductor安装。我们将通过以下URL来加载`biocLite`函数。首次使用`biocLite`安装包时，它还需要从Bioconductor安装`Biobase`包，因此可能需要一些时间。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_32.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_33.png)

安装完成后，我们可以像往常一样使用`library`命令加载该包。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_35.png)

```r
source("http://bioconductor.org/biocLite.R")
biocLite("rhdf5")
library(rhdf5)
```

![](img/e29bb9cccc66c4b6bb9ad745fe640974_36.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_37.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_38.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_39.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_40.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_41.png)

## 创建与操作HDF5文件 🛠️

![](img/e29bb9cccc66c4b6bb9ad745fe640974_43.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_44.png)

在本节中，我们将实际创建HDF5文件并与之交互。虽然你可以直接使用`rhdf5`包访问和提取HDF5数据集中的数据，但为了教学演示，我们将展示如何自己创建它们。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_45.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_46.png)

我们将使用`H5Fcreate`命令创建一个名为`example.h5`的HDF5文件。本课程内容与RHDF5教程非常相似，该教程链接在本幻灯片底部。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_48.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_49.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_50.png)

创建HDF5文件后，我们可以在文件中创建组。我们使用`H5Gcreate`命令。例如，我们可以在文件中创建组`foo`，另一个组`baa`，以及`foo`的一个子组`foobaa`。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_51.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_52.png)

然后，你可以使用`h5ls`命令查看我们创建的文件中的组和名称，这类似于`ls`命令，但只列出特定HDF5文件的组件。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_54.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_55.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_56.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_57.png)

## 向组中写入数据 ✍️

![](img/e29bb9cccc66c4b6bb9ad745fe640974_58.png)

接下来，我们可以向特定的组写入数据。例如，我们可以创建一个矩阵`A`，然后使用`h5write`命令将该矩阵写入一个特定的组。这里指定了我们要操作的文件以及文件内的组。

我们不仅可以写入矩阵，还可以写入多维数组。例如，这里有一个多维数组。我们还可以为其添加属性，例如，可以赋予它像“单位”这样的元数据。然后，我们再次使用`h5write`命令将这个数组写入一个特定的子组。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_60.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_61.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_62.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_63.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_64.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_65.png)

现在，如果我们列出文件中的内容，可以看到所有已创建的组，并且在那些组中，我们实际上有一些数据集。你可以看到`A`现在是一个HDF5数据集，由整数组成；下面还有另一个数据集`B`，由浮点数组成，并给出了这些可以是多维的数据集的维度。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_66.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_67.png)

## 直接写入与读取数据 📊

![](img/e29bb9cccc66c4b6bb9ad745fe640974_69.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_70.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_71.png)

我们也可以直接将数据写入顶级组。假设我们使用`data.frame`命令创建了一个数据框`df`。我们可以使用`h5write`命令将该数据框直接写入顶级组。我们不是传递它要发送到的组，而是直接传递变量名。然后，如果我们列出当前的情况，现在可以在顶级组（即根组）中看到`df`，它是一个数据集，并给出了数据的维度等信息。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_72.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_73.png)

然后，你可以使用`h5read`命令直接读取数据。你需要告诉它要查看哪个文件。例如，你可以告诉它读取一个非常具体的数据集，如`read foo/A`。你也可以通过指定路径来读取子数据集，或者通过仅指定数据集名称来读取顶级组中的数据集。

读取出来的数据就是你写入的数据。这就是当你有一个HDF5文件中的数据并想将其提取出来时的读取方式。

## 分块读取与写入的优势 ⚡

![](img/e29bb9cccc66c4b6bb9ad745fe640974_75.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_76.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_77.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_78.png)

HDF5文件格式的另一个优势是可以轻松地进行分块读取和写入。我们将再次使用`h5write`，写入我们文件中已有的数据`A`。我们将写入元素12、13和14，并可以指定将其写入该数据的特定部分。我们可以为其提供索引。这里的索引文件将为每个维度提供索引。对于第一个维度，我们将指定将这些值写入此数据集第一列的前三行。如果我们在此写入操作后读取数据，可以看到第一列的前三行正是我们写入的12、13和14。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_79.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_80.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_81.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_82.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_83.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_84.png)

你也可以使用类似的索引命令来仅读取数据的一个子组件。你可以传递一个索引，它是一个显示不同维度的列表。例如，如果你只想读取第一列的前三行，可以将相同的索引命令传递给`h5read`。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_85.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_86.png)

## 总结与进一步资源 📚

![](img/e29bb9cccc66c4b6bb9ad745fe640974_88.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_89.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_90.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_91.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_92.png)

本节课中，我们一起学习了HDF5文件格式的基础知识及其在R语言中的应用。我们了解了HDF5的分层结构，学习了如何安装和使用`rhdf5`包来创建HDF5文件、创建组、向组中写入数据集（包括矩阵、多维数组和数据框），以及如何从文件中读取特定数据或数据子集。我们还探讨了HDF5支持分块读写以优化磁盘I/O操作的特性。

需要记住的一点是，HDF5可用于优化R中磁盘的读取和写入。本课程引用的RHDF5教程提供了更多关于如何使用HDF5的信息。HDF5 Group网站也提供了大量关于使用HDF5的优秀资源。

![](img/e29bb9cccc66c4b6bb9ad745fe640974_94.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_95.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_96.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_97.png)

![](img/e29bb9cccc66c4b6bb9ad745fe640974_98.png)

通过掌握这些技能，你将能够有效地处理存储在HDF5格式中的大型科学数据集。