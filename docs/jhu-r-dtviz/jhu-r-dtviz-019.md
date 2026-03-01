# 019：开始使用ggplot（第2部分）📊

在本节课中，我们将继续学习如何使用ggplot2创建散点图，并逐步添加图形元素，如颜色、标签和分面，以增强图表的可读性和表现力。

---

## 从基础散点图开始

上一节我们介绍了如何创建一个空白的ggplot图形框架。本节中，我们来看看如何向散点图中添加数据点。

以下是创建基础散点图的步骤：

1.  使用`geom_point()`函数添加点。
2.  通过加号`+`将`geom_point()`连接到初始的`ggplot()`命令上。

```r
ggplot(data = congress_data, aes(x = seniority, y = bills_passed)) +
  geom_point()
```

运行上述代码后，我们生成了一个散点图。图中的每个点代表第115届国会的一名议员，其X轴位置由资历（seniority）决定，Y轴位置由通过的法案数量（bills_passed）决定。

---

## 处理数据点重叠问题

当前图表存在一个问题，即过度绘制（overplotting）。当多名议员拥有完全相同的资历和法案通过数量时，他们的数据点会完全重叠在一起。

为了解决这个问题，我们可以使用`geom_jitter()`函数替代`geom_point()`。该函数会在数据点的X和Y值上添加少量随机噪声，使它们稍微分开，从而更清晰地展示数据分布。

```r
ggplot(data = congress_data, aes(x = seniority, y = bills_passed)) +
  geom_jitter()
```

在数据可视化中，此类技巧有助于读者解读数据，但需谨慎使用，确保不会扭曲或误导数据的真实情况。

---

## 添加标题和轴标签

基础散点图生成后，我们可以立即通过添加`labs()`函数来改善图表的外观，例如添加标题和修改轴标签。

以下是添加标签的步骤：

1.  使用`labs()`函数。
2.  在函数内指定`title`、`x`和`y`参数。

```r
ggplot(data = congress_data, aes(x = seniority, y = bills_passed)) +
  geom_jitter() +
  labs(title = "国会资历与法案通过数量",
       x = "议员资历（年）",
       y = "通过的法案数量")
```

现在，图表具备了基本元素，但我们还可以做得更多。

---

## 按政党为数据点上色

为了更深入地分析，我们可以利用颜色来区分国会中的两个主要政党：民主党和共和党。

首先，我们需要在数据整理步骤中确保包含政党信息（例如`party`列）。然后，在`ggplot()`的`aes()`映射中，将`color`参数设置为政党变量。

```r
ggplot(data = congress_data, aes(x = seniority, y = bills_passed, color = party)) +
  geom_jitter() +
  labs(title = "国会资历与法案通过数量（按政党）",
       x = "议员资历（年）",
       y = "通过的法案数量")
```

运行后，图表会根据政党自动分配颜色。但默认颜色可能不是我们想要的。

---

## 手动控制颜色

在美国政治语境中，蓝色通常代表民主党，红色代表共和党。我们可以使用`scale_color_manual()`函数手动指定这些颜色。

以下是手动设置颜色的步骤：

1.  添加`scale_color_manual()`函数。
2.  在`values`参数中按顺序指定颜色。

```r
ggplot(data = congress_data, aes(x = seniority, y = bills_passed, color = party)) +
  geom_jitter() +
  labs(title = "国会资历与法案通过数量（按政党）",
       x = "议员资历（年）",
       y = "通过的法案数量") +
  scale_color_manual(values = c("blue", "red"))
```

现在，图表使用了更符合惯例的政党颜色。

---

## 创建分面图

有时，我们可能希望将民主党和共和党的数据分别绘制在两个独立的子图中进行比较。这可以通过“分面”（faceting）功能实现。

我们使用`facet_wrap()`函数来创建分面图。在函数中，使用波浪号`~`后接用于分割数据的变量（此处为`party`）。

```r
ggplot(data = congress_data, aes(x = seniority, y = bills_passed, color = party)) +
  geom_jitter() +
  labs(title = "国会资历与法案通过数量",
       x = "议员资历（年）",
       y = "通过的法案数量") +
  scale_color_manual(values = c("blue", "red")) +
  facet_wrap(~party)
```

运行代码后，我们得到了两个并排的散点图，分别展示两个政党的数据。

---

## 总结

本节课中，我们一起学习了如何使用ggplot2构建一个完整的散点图。我们从准备数据开始，然后系统地、一步一步地添加了图形标记（`geom_jitter`）、标签（`labs`）、颜色映射（`aes(color)`）、手动颜色设置（`scale_color_manual`）以及分面（`facet_wrap`）。

这个构建图形的过程展示了ggplot2的基本逻辑：**所有图形都遵循相同的基本流程**。无论你是制作散点图、折线图、条形图，还是更复杂的图形（如地图），方法都是相通的。这为你未来的探索和实践打下了良好的基础。

在接下来的视频中，我将使用完全相同的方法论，演示如何创建更多经典类型的可视化图表。