# 029：注释进阶（第二部分）

在本节课中，我们将学习如何在散点图中添加文本注释，并解决标签重叠的问题。我们还将介绍如何使用`ggrepel`包优化文本显示，以及如何利用`annotate`函数添加自定义形状和标签来突出显示特定数据点。

---

## 绘制带文本注释的散点图

上一节我们介绍了基础注释方法，本节中我们来看看如何在散点图中为数据点添加文本标签。

我们将继续使用国会立法效能数据集。该数据集及代码手册已附在本视频相关材料中。

假设我们想绘制政治意识形态与国会成员通过法案数量之间的关系。数据中的`DW Nom1`变量衡量从自由到保守的意识形态，`all_pass`变量可衡量国会成员在众院通过的法案数量。为简化处理，我们使用`filter`命令将数据限定在第115届国会。

```r
# 基础绘图代码框架
ggplot(data = filtered_data, aes(x = DW_Nom1, y = all_pass, label = Thomas_name)) +
  geom_point() +
  geom_text()
```

此处，我们没有在`geom_text`函数的美学映射中设置标签，而是在初始`ggplot`函数中设置了`label = Thomas_name`。`Thomas_name`是包含每位国会成员姓名的列。请记住，此映射会传递到图形命令串的后续函数中。

运行上述代码后，你会发现存在一个严重问题：文本标签大量重叠，导致图表难以阅读。

---

## 解决标签重叠问题

由于数据点过多，为每个成员绘制文本并不现实。以下是解决此问题的步骤：

观察图表，y轴值大于8的数据点相对较少，我们可以选择仅标注这些点。这可以通过为`geom_text`函数提供新的数据参数来实现，该参数筛选出`all_pass`值大于8的观察值。

```r
# 仅标注高绩效成员
ggplot(data = filtered_data, aes(x = DW_Nom1, y = all_pass, label = Thomas_name)) +
  geom_point() +
  geom_text(data = filter(filtered_data, all_pass > 8))
```

此代码中，美学映射仍来自原始的`ggplot`命令，但`geom_text`使用的数据已不同。这种方法允许我们在函数中灵活切换不同的映射和数据，在制作复杂图表时非常有用。

运行后，图表将只显示y轴值较高的点的文本标签，从而缓解了重叠问题。

---

## 使用ggrepel优化文本标注

尽管我们已筛选数据，但某些标签可能仍存在轻微重叠。为此，我们可以使用`ggrepel`库中的`geom_text_repel`函数替代基础的`geom_text`。

`ggrepel`并非`tidyverse`的一部分，而是开源生态中另一个开发者创建的包，它能与`ggplot2`良好协作，是数据可视化的有力补充。

请先安装并加载`ggrepel`库：

```r
install.packages("ggrepel")
library(ggrepel)
```

然后修改我们的绘图代码：

```r
# 使用ggrepel避免标签重叠
ggplot(data = filtered_data, aes(x = DW_Nom1, y = all_pass, label = Thomas_name)) +
  geom_point() +
  geom_text_repel(data = filter(filtered_data, all_pass > 8))
```

`geom_text_repel`会自动应用间距算法，将文本标签彼此推开，使其更易读。这为读者提供了一种便捷的方式来理解数据点标签。

---

## 使用annotate函数添加自定义注释

假设我们希望特别关注代表John Katco（他在y轴上位置很高），并希望通过绘制一个框来突出显示他是该届国会中的高绩效成员。

我们可以使用`annotate`命令直接在`ggplot`图形中绘制高亮框或其他形状。

以下是添加红色透明高亮框和说明文本的代码：

```r
ggplot(data = filtered_data, aes(x = DW_Nom1, y = all_pass, label = Thomas_name)) +
  geom_point() +
  geom_text_repel(data = filter(filtered_data, all_pass > 8)) +
  annotate("rect",
           xmin = x_coord_min, xmax = x_coord_max,
           ymin = y_coord_min, ymax = y_coord_max,
           alpha = 0.2, color = "red") +
  annotate("text",
           x = text_x_coord, y = text_y_coord,
           label = "Most Passed Bills")
```

代码说明：
*   `annotate("rect", ...)`：绘制一个矩形。你需要根据数据坐标定义`xmin`、`xmax`、`ymin`、`ymax`。
*   `alpha = 0.2`：设置透明度。
*   `color = "red"`：设置边框颜色。
*   第二个`annotate("text", ...)`：在指定坐标添加文本标签。

这些命令直接将图形元素添加到绘图中。通过仔细调整参数，你可以实现对可视化内容的精细控制。

---

## 总结

本节课中我们一起学习了：
1.  在散点图中添加文本注释的基本方法。
2.  通过筛选数据子集解决标签重叠问题。
3.  利用`ggrepel`包的`geom_text_repel`函数自动优化标签布局。
4.  使用`annotate`函数添加自定义形状（如高亮框）和文本来突出显示关键数据点。

通过一些预先思考和参数调整，你可以运用这些技术使数据可视化更加丰富和具有表现力。