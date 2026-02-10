# 约翰霍普金斯大学数据科学课程4：《探索性数据分析》｜P11：基础绘图系统（第一部分）📊

![](img/589c4daf77d4fcd7157c03f7725bd5b1_0.png)

在本节课中，我们将要学习R语言中的基础绘图系统。这是R语言中最常用、最核心的绘图系统，我们将了解其基本工作原理、关键函数以及如何创建和定制简单的图形。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_2.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_3.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_4.png)

## 概述：R的绘图系统

R语言拥有三个主要的绘图系统：基础绘图系统、Lattice系统和ggplot2系统。本课程将专注于**基础绘图系统**。基础绘图系统的核心功能封装在`graphics`和`grDevices`这两个包中。`grDevices`包包含了所有图形设备的代码，包括屏幕设备（如X11、Windows）和文件设备（如PDF、PostScript）。`graphics`包则包含了实际的绘图函数，如`plot()`、`hist()`和`boxplot()`等。

Lattice系统封装在`lattice`包中，它基于另一个底层图形系统`grid`。我们通常不直接调用`grid`包，而是通过`lattice`或`ggplot2`间接使用。ggplot2系统则融合了基础绘图和Lattice系统的概念。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_6.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_7.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_8.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_9.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_10.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_11.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_12.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_13.png)

## 绘图前的考量

![](img/589c4daf77d4fcd7157c03f7725bd5b1_14.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_15.png)

在开始绘图前，需要考虑几个关键问题：
*   图形将在何处显示？是屏幕上还是输出到文件？
*   图形的用途是什么？是临时在屏幕上查看、用于网页、论文发表还是幻灯片演示？
*   图形中会包含大量数据还是少量数据？是图像还是线条图？
*   是否需要能够动态调整图形大小？这决定了应选择矢量格式还是位图格式。

此外，还需要决定使用哪个绘图系统，因为这三个系统不能混合使用。基础绘图系统采用**分步构建**的方式，通过一系列函数调用来组合图形。Lattice系统则通过**单次函数调用**创建完整图形。本节课我们只关注基础绘图系统，并且仅讨论在屏幕设备上创建图形。

## 基础绘图系统的工作原理

![](img/589c4daf77d4fcd7157c03f7725bd5b1_17.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_18.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_19.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_20.png)

基础绘图系统用于创建二维图形，其过程分为两个阶段：
1.  **初始化新图形**：启动一个图形设备并绘制基础图形框架。
2.  **注释或添加内容**：在已存在的图形上添加额外的元素，如点、线、文本或图例。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_21.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_22.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_24.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_25.png)

以下是用于初始化图形的一些关键函数示例。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_27.png)

### 初始化图形的函数

![](img/589c4daf77d4fcd7157c03f7725bd5b1_28.png)

`plot()`函数和`hist()`函数是初始化图形的典型例子。如果当前没有打开的图形设备，这些函数会启动一个新的图形设备（通常是一个弹出的窗口），并在其上绘制图形。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_30.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_31.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_32.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_33.png)

`plot()`函数是R中的一个**泛型函数**，其行为会根据传入的数据类型而变化。如果传入的是普通向量数据（例如x和y向量），则会使用其**默认方法**。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_35.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_36.png)

`plot()`函数的默认方法包含许多参数，可用于设置标题、坐标轴标签等细节。基础绘图系统拥有大量可调整的参数，允许用户高度自定义图形外观。这些参数大多记录在`par()`函数的帮助页面中。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_37.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_38.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_39.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_40.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_41.png)

### 基础图形示例

![](img/589c4daf77d4fcd7157c03f7725bd5b1_43.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_44.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_46.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_47.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_48.png)

以下是一些使用基础绘图系统创建基本图形的例子。

**1. 直方图**
使用`hist()`函数可以创建一维数据的直方图。以下代码加载`datasets`包中的`airquality`数据集，并绘制臭氧（Ozone）浓度的直方图。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_50.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_51.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_52.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_53.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_54.png)

```r
library(datasets)
hist(airquality$Ozone)
```

![](img/589c4daf77d4fcd7157c03f7725bd5b1_55.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_56.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_57.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_58.png)

这段代码使用了`hist()`函数的默认参数。如果图形设备未打开，R会自动打开一个窗口并显示直方图。

**2. 散点图**
使用`plot()`函数可以创建散点图。以下代码使用相同的数据集，绘制风速（Wind）与臭氧浓度的散点图。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_60.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_61.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_62.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_63.png)

```r
with(airquality, plot(Wind, Ozone))
```

![](img/589c4daf77d4fcd7157c03f7725bd5b1_64.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_65.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_66.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_67.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_68.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_69.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_70.png)

这里同样使用了所有默认参数。默认的绘图符号是一个空心圆。

**3. 箱线图**
`boxplot()`函数用于初始化箱线图。以下代码按月份（Month）绘制臭氧浓度的分布箱线图。

```r
boxplot(Ozone ~ Month, airquality, xlab = "Month", ylab = "Ozone (ppb)")
```

![](img/589c4daf77d4fcd7157c03f7725bd5b1_72.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_73.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_74.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_75.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_76.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_77.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_78.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_79.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_80.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_81.png)

`boxplot()`函数使用了**公式表示法**：波浪号（`~`）左侧`Ozone`指定了y轴变量，右侧`Month`指定了用于分组的x轴变量。参数`xlab`和`ylab`分别用于设置坐标轴标签。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_82.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_84.png)

## 关键基础图形参数

![](img/589c4daf77d4fcd7157c03f7725bd5b1_86.png)

有几个基础图形参数非常常用，值得重点记忆。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_87.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_88.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_89.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_90.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_91.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_92.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_93.png)

以下是这些核心参数及其作用：
*   **`pch`**：绘图符号。可以是数字（对应内置符号表）或单个字符（如“A”）。默认值为1（空心圆）。
*   **`lty`**：线条类型。用于指定是实线、虚线还是点线等。
*   **`lwd`**：线条宽度。数值越大，线越粗。常用于根据展示场景（如演讲或出版物）调整图形。
*   **`col`**：绘图颜色。可以使用颜色编号、颜色名称字符串或十六进制代码指定。`colors()`函数可以列出所有可用的颜色名称。
*   **`xlab`**：x轴标签。
*   **`ylab`**：y轴标签。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_95.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_96.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_97.png)

### 全局图形参数

![](img/589c4daf77d4fcd7157c03f7725bd5b1_99.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_100.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_101.png)

`par()`函数用于设置**全局图形参数**，这些设置将影响之后创建的所有图形。虽然大部分参数可以在单个绘图函数调用中被覆盖，但有些参数（如边距、多图布局）只能通过`par()`函数设置。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_102.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_103.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_104.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_105.png)

以下是一些有用的全局参数：
*   **`las`**：坐标轴标签的方向（如水平或垂直）。
*   **`bg`**：图形的背景颜色。
*   **`mar`**：图形边距大小。包含四个数值，分别代表**下、左、上、右**四个边的边距（以文本行高度为单位）。例如，`c(5.1, 4.1, 4.1, 2.1)`。
*   **`oma`**：外边界大小。在组合多图时有用。
*   **`mfrow`** / **`mfcol`**：多图布局。用于控制在一个设备窗口中按行或按列排列多个图形，例如`mfrow = c(2, 2)`会创建一个2行2列的图形矩阵。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_107.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_108.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_109.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_110.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_112.png)

可以通过调用`par()`函数并传入参数名来查看其默认值。

```r
par("lty") # 查看默认线条类型
par("col") # 查看默认颜色
par("pch") # 查看默认绘图符号
par("bg")  # 查看默认背景（通常为透明）
par("mar") # 查看默认边距
par("mfrow") # 查看默认多图布局（通常为c(1,1)，即单图）
```

![](img/589c4daf77d4fcd7157c03f7725bd5b1_114.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_115.png)

## 总结

![](img/589c4daf77d4fcd7157c03f7725bd5b1_116.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_117.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_118.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_119.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_120.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_121.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_122.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_123.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_124.png)

本节课我们一起学习了R语言基础绘图系统的核心概念。我们了解到基础绘图系统分两步工作：先初始化图形，再添加注释。我们介绍了`plot()`、`hist()`和`boxplot()`等初始化函数，并学习了如何通过`pch`、`col`、`lwd`等关键参数定制图形外观。最后，我们探讨了如何使用`par()`函数设置影响所有图形的全局参数，如边距和多图布局。掌握这些基础知识是使用R进行有效数据可视化的第一步。