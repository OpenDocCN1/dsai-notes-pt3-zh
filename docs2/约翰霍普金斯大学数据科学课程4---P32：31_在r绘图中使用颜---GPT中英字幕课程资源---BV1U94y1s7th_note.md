# 约翰霍普金斯大学数据科学课程4：《探索性数据分析》｜P32：在R绘图中使用颜色（第二部分）🎨

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_0.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_2.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_3.png)

在本节课中，我们将要学习R语言`grDevices`包中两个用于创建和操作颜色的核心函数：`colorRamp`和`colorRampPalette`。我们将通过简单的比喻和代码示例，理解它们如何基于给定的颜色调色板生成平滑过渡的中间色。

## 概述：颜色混合的原理

上一节我们介绍了R中颜色的基本表示方法。本节中我们来看看如何通过混合基础颜色来创建新的颜色。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_5.png)

你可以将这个过程想象成画家在调色板上混合颜料。画家在调色板上有几块特定的颜色（例如红色和蓝色），然后用画笔将它们混合，创造出介于两者之间的新颜色。`colorRamp`和`colorRampPalette`函数正是基于这个原理：它们接收一组构成调色板的颜色，并通过数值计算在这些颜色之间进行插值，生成混合后的新颜色。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_6.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_7.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_8.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_9.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_10.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_11.png)

## 核心函数介绍

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_12.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_13.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_14.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_15.png)

以下是本节课将要详细讲解的两个核心函数。

### 1. `colorRamp` 函数

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_17.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_18.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_19.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_20.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_21.png)

`colorRamp`函数接收一个颜色调色板，并返回一个新的函数。这个返回的函数接受一个介于0和1之间的数值作为参数，返回一个代表该位置颜色的RGB值矩阵。

一个类似的现有函数是`gray`，它在黑色和白色之间进行插值，生成各种灰色调。`colorRamp`是其泛化版本，因为它可以接受调色板中的任意一组颜色，并返回一个函数，该函数根据0到1之间的数值在调色板的极端颜色之间进行插值。

**代码示例：**
```r
# 创建一个由红色和蓝色组成的调色板
pal <- colorRamp(c("red", "blue"))
```

### 2. `colorRampPalette` 函数

`colorRampPalette`函数与`colorRamp`非常相似。它也接收一个颜色调色板，并返回另一个函数。但返回的函数接受一个整数参数，并返回一个插值了该调色板的颜色向量。

这与`heat.colors`或`topo.colors`等函数类似。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_23.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_24.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_25.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_26.png)

**代码示例：**
```r
# 创建一个由红色和黄色组成的调色板
pal2 <- colorRampPalette(c("red", "yellow"))
```

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_27.png)

## 函数使用详解

### `colorRamp` 函数工作流程

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_29.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_30.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_31.png)

让我们通过一个快速示例来理解`colorRamp`。这里我们创建一个由红色和蓝色两种颜色组成的调色板。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_32.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_33.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_34.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_35.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_36.png)

**代码示例：**
```r
# 创建调色板函数
pal <- colorRamp(c("red", "blue"))
```

现在，`pal`是一个函数，可以接受0到1之间的数字。当我们调用`pal(0)`时，会返回一个1行3列的矩阵。这三列分别代表红、绿、蓝（RGB）的值，每个值的范围是0到255（共256个可能值）。

*   `pal(0)`返回的是红色，因为它是我们指定调色板的一个端点。矩阵显示红色值为255（最大），绿色和蓝色值均为0。
*   `pal(1)`返回的是蓝色，即调色板的另一个端点。矩阵显示红色和绿色值为0，蓝色值为255。
*   `pal(0.5)`返回一个介于红色和蓝色中间的颜色。矩阵显示红色和蓝色值均为127.5，绿色值为0。这个颜色是半红半蓝的混合色。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_38.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_39.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_40.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_41.png)

注意，在这些调用中都没有绿色，因为在红色和蓝色之间插值时，不会经过绿色。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_42.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_43.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_44.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_45.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_46.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_47.png)

如果我们给`pal`一个从0到1的序列，它会返回一系列从红色渐变到蓝色的颜色。

**代码示例：**
```r
# 生成10个从红到蓝的渐变颜色
seq_colors <- pal(seq(0, 1, len=10))
print(seq_colors)
```
输出矩阵的顶部从纯红色（255, 0, 0）开始，随着序列推进，红色值逐渐减少，蓝色值逐渐增加，到底部时变为纯蓝色（0, 0, 255）。这些就是在红色和蓝色之间插值得到的各种颜色。

### `colorRampPalette` 函数工作流程

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_49.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_50.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_51.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_52.png)

`colorRampPalette`函数返回的函数类型略有不同。这里我们传递一个由红色和黄色组成的调色板。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_53.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_54.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_55.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_56.png)

**代码示例：**
```r
# 创建调色板函数
pal2 <- colorRampPalette(c("red", "yellow"))
```

现在，`pal2`接受整数参数，而不是0到1之间的数字。假设我们给它参数2。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_58.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_59.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_60.png)

**代码示例：**
```r
colors_2 <- pal2(2)
print(colors_2)
```
`pal2(2)`将返回两个插值了调色板的颜色。由于调色板本身只有两种颜色，当只请求2个颜色时，它就直接返回调色板上的两个颜色：第一个是红色，第二个是黄色。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_61.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_62.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_63.png)

这里的格式略有不同：它返回一个字符向量，其中的红、绿、蓝值用十六进制表示。每个字符串以`#`开头，后面有6位十六进制数字：前两位代表红色，中间两位代表绿色，后两位代表蓝色。

*   第一个字符串`#FF0000`：`FF`（红色最大值），`00`（绿色），`00`（蓝色），代表红色。
*   第二个字符串`#FFFF00`：`FF`（红色最大值），`FF`（绿色最大值），`00`（蓝色），代表黄色（红色和绿色混合得到黄色）。

当我们调用`pal2(10)`时，第一个元素是红色（`#FF0000`），最后一个元素是黄色（`#FFFF00`），中间的元素则是插值产生的颜色。你可以看到十六进制表示的颜色从红色逐渐向黄色变化，过程中没有蓝色，因为在红色和黄色之间插值不会遇到蓝色。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_65.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_66.png)

## 其他有用函数：`colors`

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_67.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_68.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_69.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_70.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_71.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_72.png)

另一个可能感兴趣的函数是`colors`。不带参数执行它，会返回一个字符向量，包含所有可以在绘图函数中使用的颜色名称。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_73.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_74.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_75.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_76.png)

这些颜色可以通过名称直接引用，而无需像我们后面会讲到的那样引用它们的红绿蓝值。

**代码示例：**
```r
# 查看所有可用颜色名称
all_colors <- colors()
head(all_colors) # 查看前几个
```

## 总结

本节课中我们一起学习了R语言中用于颜色插值的两个强大工具。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_78.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_79.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_80.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_81.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_82.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_83.png)

*   **`colorRamp`函数**：接收颜色调色板，返回一个函数。该函数接受0到1之间的数值，返回对应的RGB矩阵，用于在连续数值和颜色之间建立映射。
*   **`colorRampPalette`函数**：同样接收颜色调色板，但返回的函数接受一个整数，并返回一个包含指定数量渐变颜色的字符向量（十六进制格式），非常适合需要离散颜色序列的场景。

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_84.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_85.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_86.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_87.png)

![](img/7f0d0d6aa1b9e14a1fc2e7db7d17dbc7_88.png)

通过理解这两个函数，你可以超越预定义的颜色集，灵活地创建出符合你数据特性和可视化需求的定制化颜色渐变。