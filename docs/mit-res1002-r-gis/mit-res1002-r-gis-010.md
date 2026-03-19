# 010：使用ggplot2绘制地图

![](img/94dfa678ac403e2040d11791a0d65164_0.png)

在本节课程中，我们将学习如何使用`ggplot2`包来绘制和美化地图。与R默认的绘图代码相比，`ggplot2`提供了更灵活、更易于调整的绘图方式，能够帮助我们创建出适合科学项目展示的图形。

## 准备数据

首先，我们需要准备要绘制的地图数据。这里我们使用一个温度地图作为示例。为了使R处理速度更快，我们将对地图数据进行聚合处理，将每5个像素合并为1个。这会使图像的分辨率降低，但能提高处理效率。

```r
# 聚合地图数据，因子为5
aggregated_map <- aggregate(original_map, fact=5)
```

接下来，我们需要将地图数据转换为数据框格式，这是使用`ggplot2`绘图的前提条件。默认的转换函数不会保留经纬度信息，因此我们需要特别指定。

```r
# 将地图转换为数据框，并保留经纬度作为变量
map_df <- as.data.frame(aggregated_map, xy=TRUE)
```

转换后，数据框包含三个变量：x（经度）、y（纬度）和温度值。为了便于后续操作，我们将温度值的列名重命名为更简洁的“temperature”。

```r
# 重命名温度列
colnames(map_df)[3] <- "temperature"
```

## 加载必要包

在开始绘图前，我们需要加载几个必要的R包。

```r
library(maptools)   # 用于处理地图数据
library(ggplot2)    # 核心绘图包
library(viridis)    # 提供美观的颜色调色板
```

此外，我们还需要加载一个表示陆地轮廓的地图数据，用于区分陆地和海洋。

```r
# 加载陆地轮廓地图
land_shape <- readShapeSpatial("path/to/land_shapefile.shp")
```

## 绘制基础地图

现在，我们可以开始使用`ggplot2`绘制基础地图。以下是创建最简单地图的代码。

```r
# 创建基础ggplot对象，指定数据源和美学映射
base_plot <- ggplot(data = map_df, aes(x = x, y = y))

# 添加栅格图层，用温度值填充颜色
base_plot <- base_plot + geom_raster(aes(fill = temperature))

# 显示图形
print(base_plot)
```

运行这段代码会生成一个基础的温度地图，但视觉效果可能不够理想。

## 美化地图

上一节我们绘制了基础地图，本节中我们将逐步添加元素来美化它。

首先，我们在温度图层上叠加陆地轮廓，以清晰地区分陆地和海洋。

```r
# 在基础地图上添加陆地轮廓线
base_plot <- base_plot + geom_polygon(data = land_shape, aes(group = group), fill = NA, color = "black")
print(base_plot)
```

接下来，我们进行一系列调整来改善地图外观：
1.  隐藏缺失值（NA）区域。
2.  反转颜色渐变的方向，使低温显示为浅色，高温显示为深色。
3.  更换颜色调色板。

```r
# 美化地图：处理NA值、反转色阶、更换调色板
base_plot <- base_plot +
  scale_fill_viridis(option = "C", direction = -1, na.value = NA)
print(base_plot)
```

然后，我们调整地图的主题样式，并限制Y轴的显示范围，以裁剪掉南纬60度以南的区域。

```r
# 应用简约主题并调整坐标轴范围
base_plot <- base_plot +
  theme_minimal() +
  coord_cartesian(ylim = c(-60, 90))
print(base_plot)
```

最后，我们为地图添加标题、修改图例位置，并为图例设置更清晰的标签。

```r
# 添加标题、调整图例、修改坐标轴标签
final_plot <- base_plot +
  labs(title = "Global Temperature Map",
       x = "Longitude",
       y = "Latitude",
       fill = "January Temperature (°C)") +
  theme(legend.position = "left")
print(final_plot)
```

## 导出地图

完成地图绘制后，我们可能需要将其保存为图像文件以便在报告或演示中使用。使用TIFF格式可以保存高质量的图像。

以下是保存地图的代码：

```r
# 将图形保存为TIFF文件
tiff(filename = "my_temperature_map.tif",
     width = 10, height = 6, units = "in", res = 200) # 设置图像尺寸和分辨率
print(final_plot) # 将图形写入文件
dev.off() # 关闭图形设备，完成保存
```

## 总结

![](img/94dfa678ac403e2040d11791a0d65164_2.png)

本节课中我们一起学习了如何使用`ggplot2`包绘制和美化地图。我们从准备和转换数据开始，逐步构建了一个基础地图，然后通过叠加轮廓、调整颜色、修改主题和添加标签等一系列步骤，最终创建了一幅清晰、美观且适合科学展示的温度地图。最后，我们还学习了如何将绘制好的地图导出为高质量的图像文件。`ggplot2`的强大功能使我们能够灵活控制图形的每一个细节。