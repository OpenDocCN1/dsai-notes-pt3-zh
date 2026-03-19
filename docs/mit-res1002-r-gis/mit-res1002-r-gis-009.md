# 009：利用空间数据点从地图中提取信息 🗺️📍

![](img/aab4c4e0d6458370ed34dea38b1c5250_0.png)

在本节课中，我们将学习如何利用地图数据来填补数据库中的缺失值。这是一个在研究中常用的过程，当我们面对包含空值（NA）的新数据库时，可以通过地理坐标从地图中提取信息来填补这些空白。虽然地图数据不如实地实验数据精确，但它是最大化利用现有数据、完善模型的有效方法。

我们将使用数据库中的经纬度坐标，将其转换为空间数据点，并用这些点从地图中提取信息（如温度、降水等）。接下来，让我们开始实际操作。

## 数据准备与加载

首先，我们需要加载一个包含缺失值的真实数据集。这里使用一个来自GitHub的、计算全球尺度氮吸收的数据库。该数据库的部分驱动因子（如温度、降水、土壤信息）存在数据缺失。

以下是加载数据并查看其结构的代码：

```r
# 加载数据
data <- read.csv("your_github_data_link.csv")

# 查看列名
names(data)

# 我们特别关注经纬度信息，它们通常是第三和第四列
# 确保经纬度列没有缺失值
data_clean <- data[!is.na(data$latitude) & !is.na(data$longitude), ]
```

## 创建空间数据点

将经纬度数据转换为空间数据点有两种主要方法：`SpatialPoints` 和 `SpatialPointsDataFrame`。两种方法都需要指定经纬度所在的列和所使用的坐标系。

以下是两种方法的示例代码：

```r
# 方法一：使用SpatialPoints
sp_points <- SpatialPoints(coords = data_clean[, c("longitude", "latitude")], proj4string = CRS("+proj=longlat +datum=WGS84"))

# 方法二：使用SpatialPointsDataFrame
sp_df <- SpatialPointsDataFrame(coords = data_clean[, c("longitude", "latitude")], data = data_clean, proj4string = CRS("+proj=longlat +datum=WGS84"))

# 绘制点以验证
plot(sp_points)
```

为了更直观地理解这些点的地理位置，我们可以将其叠加在世界地图上：

```r
# 加载世界地图
library(maps)
map("world", fill=TRUE, col="lightgray", bg="white")
points(data_clean$longitude, data_clean$latitude, col="red", pch=19, cex=0.5)
```

## 从地图中提取信息

上一节我们创建了空间点，本节我们将使用这些点从栅格地图中提取信息。我们将以一个全球温度栅格图为例。

首先，加载温度地图并使用 `extract` 函数提取数据：

```r
# 加载温度栅格图（假设已下载并保存为‘temperature.tif’）
library(raster)
temp_map <- raster("path/to/your/temperature_map.tif")

# 使用空间点提取温度值
extracted_values <- extract(temp_map, sp_points)

# 将提取的值添加到原始数据框中
data_clean$extracted_temp <- extracted_values
```

如果提取的是多个图层（例如多个月份的温度），`extract` 函数会返回一个多列的数据框。

## 综合练习：计算年均温并填补缺失值

现在，我们将通过一个综合练习来回顾本GIS课程中学到的所有函数和概念。这个练习将引导你完成从下载数据到填补缺失值的完整流程。

### 第一步：下载并计算全球年均温地图

请从WorldClim网站下载10米分辨率的月平均温度栅格数据。下载后，在R中加载所有月份的地图并计算它们的平均值，以得到年平均温度。

以下是实现代码：

```r
# 设置包含所有月份温度文件的文件夹路径
files <- list.files("path/to/temperature/files", pattern=".tif", full.names=TRUE)

# 将所有文件堆叠成一个RasterStack
temp_stack <- stack(files)

# 计算堆栈中所有图层的平均值（即年平均温度）
annual_temp <- calc(temp_stack, mean)

# 查看结果
annual_temp
plot(annual_temp)
```

### 第二步：加载数据并选择相关列

下载氮吸收数据（与之前使用的数据库相同）。创建一个新的数据框，仅包含纬度、经度和年均温（来自实地测量）这三列。注意，年均温列中存在一些缺失值（NA），这正是我们需要填补的。

```r
# 加载数据
n_data <- read.csv("path/to/nitrogen_uptake_data.csv")

# 选择第3、4、18列（假设分别是纬度、经度和年均温）
sub_data <- n_data[, c(3, 4, 18)]
names(sub_data) <- c("latitude", "longitude", "MAT_field") # MAT: Mean Annual Temperature
```

### 第三步：提取地图温度并合并数据

使用上一步创建的数据框中的经纬度创建空间点。然后，从第一步计算的年均温地图中提取温度值，并将提取出的值作为新列添加到数据框中。

```r
# 创建空间点
points_for_extraction <- SpatialPoints(coords = sub_data[, c("longitude", "latitude")], proj4string = CRS("+proj=longlat +datum=WGS84"))

# 从年均温地图中提取值
MAT_from_map <- extract(annual_temp, points_for_extraction)

# 将提取的值添加到数据框
sub_data$MAT_map <- MAT_from_map
```

现在，我们可以比较实地测量的年均温（`MAT_field`）和从地图提取的年均温（`MAT_map`）：

```r
# 绘制散点图比较
plot(sub_data$MAT_field, sub_data$MAT_map, xlab="Field MAT", ylab="Map MAT")
abline(0, 1, col="red") # 添加y=x的参考线

# 建立线性模型查看相关性
model <- lm(MAT_map ~ MAT_field, data=sub_data)
summary(model)
```

### 第四步：填补缺失值

最后，我们创建一个新的数据列，用地图提取的数据来填补实地测量数据中的缺失值。

以下是使用循环实现此逻辑的代码：

```r
# 创建一个新列，初始值与实地数据相同
sub_data$MAT_filled <- sub_data$MAT_field

# 使用for循环遍历每一行
for (i in 1:nrow(sub_data)) {
  if (is.na(sub_data$MAT_filled[i])) { # 如果实地数据是NA
    sub_data$MAT_filled[i] <- sub_data$MAT_map[i] # 则用地图数据填补
  }
  # 如果实地数据不是NA，则保持原样（这部分else逻辑可以省略）
}

# 检查新列是否还有NA
sum(is.na(sub_data$MAT_filled))
```

更简洁的写法是使用 `ifelse` 函数：

```r
sub_data$MAT_filled <- ifelse(is.na(sub_data$MAT_field), sub_data$MAT_map, sub_data$MAT_field)
```

这种方法高效地结合了实地数据的准确性和地图数据的覆盖性，从而获得一个更完整的数据集用于后续分析。

![](img/aab4c4e0d6458370ed34dea38b1c5250_2.png)

## 总结

![](img/aab4c4e0d6458370ed34dea38b1c5250_4.png)

本节课中，我们一起学习了利用空间数据点从地图中提取信息以填补数据缺失的完整流程。我们首先学习了如何将经纬度数据转换为空间点，然后使用 `extract` 函数从栅格地图中提取数值。通过一个综合练习，我们实践了下载气候数据、计算统计值、提取信息以及最终使用地图数据智能填补数据库空缺的整个分析链条。这是地理信息系统（GIS）与数据分析结合的一个强大应用，能够帮助我们在数据不完整的情况下仍能进行有效的建模和研究。