# 008：读取JSON数据 📄

![](img/f72d296ea6a2374eddec379d04cb5c43_0.png)

在本节课中，我们将要学习如何读取和处理JSON格式的数据。JSON是一种在互联网上广泛使用的结构化数据格式，尤其在API接口中非常常见。我们将了解其基本结构，并学习如何在R语言中使用`jsonlite`包来读取和转换JSON数据。

![](img/f72d296ea6a2374eddec379d04cb5c43_2.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_3.png)

---

![](img/f72d296ea6a2374eddec379d04cb5c43_4.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_5.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_6.png)

## JSON简介

![](img/f72d296ea6a2374eddec379d04cb5c43_8.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_9.png)

上一节我们介绍了XML，本节中我们来看看另一种重要的数据格式——JSON。

![](img/f72d296ea6a2374eddec379d04cb5c43_11.png)

JSON是JavaScript对象表示法的缩写。它是一种轻量级的数据存储和交换格式。JSON在结构上与XML有相似之处，但语法和格式完全不同。

![](img/f72d296ea6a2374eddec379d04cb5c43_12.png)

JSON数据可以存储为以下几种类型：
*   **数字**
*   **字符串**
*   **布尔值**
*   **数组**
*   **对象**

如果你想了解更多关于JSON的信息，可以从维基百科的相关页面开始。

---

![](img/f72d296ea6a2374eddec379d04cb5c43_14.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_15.png)

## JSON结构示例

![](img/f72d296ea6a2374eddec379d04cb5c43_16.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_17.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_18.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_19.png)

以下是一个JSON文件的示例，它来自GitHub的API，展示了用户所贡献的代码仓库信息。

![](img/f72d296ea6a2374eddec379d04cb5c43_20.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_21.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_22.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_23.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_24.png)

整个JSON对象由一个最外层的大括号 `{}` 包裹。每个独立的代码仓库信息都位于其自身的大括号内。每个仓库都有一系列与之关联的变量。

JSON文件的基本结构是“键”后跟一个冒号，然后是“值”。例如：
```json
"id": 123456
```
你可以在结构中嵌套其他结构。例如，一个数组（用方括号 `[]` 表示）或另一个对象可以作为某个键的值。

![](img/f72d296ea6a2374eddec379d04cb5c43_26.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_27.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_28.png)

在示例中，`owner` 这个键的值就是一个包含多个信息的对象（由大括号 `{}` 包裹），里面有 `login`、`avatar_url` 等变量。

---

## 在R中读取JSON

在R语言中，有一个非常好用的包叫做 `jsonlite`，专门用于读取JSON数据。

读取JSON数据的基本方法是使用 `fromJSON()` 函数。你可以直接将JSON文件所在的URL传递给这个函数。

```r
library(jsonlite)
jsonData <- fromJSON("https://api.github.com/users/jtleek/repos")
```
执行上述代码后，`jsonData` 将变成一个结构化的数据框。数据框的列名对应JSON数据顶层的变量，例如 `id`、`name`、`full_name` 等。

![](img/f72d296ea6a2374eddec379d04cb5c43_30.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_31.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_32.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_33.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_34.png)

其中一个列是 `owner`。由于 `owner` 在原始JSON中本身是一个对象，因此在R的数据框中，`owner` 这一列实际上又包含了一个子数据框。我们可以像访问普通数据框列一样，进一步访问其内部信息。

例如，我们可以获取所有仓库的拥有者登录名：
```r
names(jsonData$owner)
jsonData$owner$login
```
因为本例中查询的是特定用户的仓库，所以所有 `login` 值都相同。

![](img/f72d296ea6a2374eddec379d04cb5c43_36.png)

---

![](img/f72d296ea6a2374eddec379d04cb5c43_37.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_38.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_39.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_40.png)

## 将数据框转换为JSON

除了读取，我们也可以将R中的数据框转换为JSON格式。这在需要向要求JSON格式的API导出数据时非常有用。

我们可以使用 `toJSON()` 函数进行转换。参数 `pretty=TRUE` 可以让输出的JSON字符串拥有良好的缩进，便于阅读。

![](img/f72d296ea6a2374eddec379d04cb5c43_42.png)

```r
data(iris)
irisJSON <- toJSON(iris, pretty=TRUE)
print(irisJSON)
```
此时，`irisJSON` 是一个文本变量，其内容就是Iris数据集的JSON格式表示。

![](img/f72d296ea6a2374eddec379d04cb5c43_43.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_44.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_45.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_46.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_47.png)

---

![](img/f72d296ea6a2374eddec379d04cb5c43_48.png)

## 从JSON文本转换回数据框

![](img/f72d296ea6a2374eddec379d04cb5c43_50.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_51.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_52.png)

我们可以将刚刚生成的JSON文本，再转换回R数据框。

```r
iris2 <- fromJSON(irisJSON)
head(iris2)
```
这里我们传递的不再是URL，而是一个包含JSON文本的变量名。`fromJSON()` 函数会将其解析并重建为数据框。使用 `head()` 命令查看，会发现 `iris2` 与原始的 `iris` 数据集完全一致。

---

![](img/f72d296ea6a2374eddec379d04cb5c43_54.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_55.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_56.png)

## 更多资源

![](img/f72d296ea6a2374eddec379d04cb5c43_57.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_58.png)

如果你想获得更多信息，可以访问 [JSON官网](http://www.json.org/) 了解JSON的通用知识。

关于 `jsonlite` 包，有一个非常棒的教程，也是本讲内容的重要基础，你可以在 [R-bloggers](http://www.r-bloggers.com/) 上找到。此外，`jsonlite` 包的官方文档也提供了详尽的信息，如果你需要处理更复杂的JSON结构，这些资源会很有帮助。

![](img/f72d296ea6a2374eddec379d04cb5c43_60.png)

---

![](img/f72d296ea6a2374eddec379d04cb5c43_61.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_62.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_63.png)

![](img/f72d296ea6a2374eddec379d04cb5c43_64.png)

本节课中我们一起学习了JSON数据格式的基础知识，掌握了在R中使用 `jsonlite` 包从URL或文本中读取JSON数据并转换为数据框的方法，同时也学会了如何将数据框导出为JSON格式。这些技能对于处理现代网络API和数据交换至关重要。