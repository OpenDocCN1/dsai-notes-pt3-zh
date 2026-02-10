# 课程3-P7：读取XML文件 📄

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_0.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_2.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_3.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_4.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_5.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_6.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_8.png)

在本节课中，我们将要学习如何读取和处理XML文件。XML（可扩展标记语言）是一种常用于存储结构化数据的格式，在互联网应用，特别是网络数据抓取和API数据获取中非常普遍。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_10.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_11.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_12.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_13.png)

## XML简介

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_14.png)

上一节我们介绍了课程主题，本节中我们来看看XML的基本概念。XML文件由标记和内容两部分组成。标记是为文本提供结构的标签，而内容则是标签之间的实际文本。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_16.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_17.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_18.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_19.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_20.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_21.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_22.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_23.png)

以下是XML的三个核心组成部分：

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_25.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_26.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_27.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_28.png)

*   **标签**： 标签是应用于文本特定部分的标记，用于定义结构。标签分为开始标签和结束标签。
    *   **开始标签**： 格式为 `<标签名>`，例如 `<section>`。
    *   **结束标签**： 格式为 `</标签名>`，例如 `</section>`。
    *   **空标签**： 对于不需要包裹内容的标签（如换行），格式为 `<标签名/>`，例如 `<br/>`。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_30.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_31.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_32.png)

*   **元素**： 元素是标签的具体实例，包含开始标签、结束标签及其之间的内容。
    *   例如：`<greeting>Hello World</greeting>` 就是一个完整的元素。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_34.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_35.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_36.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_37.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_38.png)

*   **属性**： 属性是标签的附加信息，提供关于元素的更多细节。
    *   例如：`<img src="logo.jpg" alt="Instructor"/>` 中，`src` 和 `alt` 就是 `<img>` 标签的属性。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_40.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_41.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_42.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_43.png)

## XML文件示例

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_44.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_46.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_47.png)

理解了基本概念后，我们来看一个具体的XML文件例子。以下是一个早餐菜单的XML结构片段：

```xml
<breakfast_menu>
  <food>
    <name>Belgian Waffles</name>
    <price>$5.95</price>
  </food>
  <food>
    <name>Strawberry Pancakes</name>
    <price>$7.95</price>
  </food>
</breakfast_menu>
```

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_49.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_50.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_51.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_52.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_53.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_54.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_55.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_56.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_57.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_58.png)

在这个文件中，`<breakfast_menu>` 是根元素，它包含了多个 `<food>` 子元素。每个 `<food>` 元素内部又包含了 `<name>` 和 `<price>` 等子元素来存储具体信息。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_60.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_61.png)

## 在R中读取XML

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_62.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_63.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_64.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_65.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_67.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_68.png)

现在，我们来看看如何在R语言中读取并操作XML文件。这需要借助 `XML` 包。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_70.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_71.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_72.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_73.png)

首先，加载`XML`包并解析文件：
```r
library(XML)
fileUrl <- "http://www.example.com/menu.xml"
doc <- xmlTreeParse(fileUrl, useInternalNodes = TRUE)
```
`xmlTreeParse()` 函数将XML文档加载到内存中，并将其解析为一个可以在R中操作的结构化对象。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_74.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_75.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_77.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_78.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_79.png)

## 访问XML文档内容

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_81.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_82.png)

解析完成后，我们可以使用各种函数来访问文档的不同部分。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_84.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_85.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_86.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_87.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_88.png)

首先，获取根节点：
```r
rootNode <- xmlRoot(doc)
xmlName(rootNode)
```
`xmlRoot()` 获取整个文档的包装元素（根节点），`xmlName()` 则返回根节点的名称。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_89.png)

要查看根节点下直接包含哪些子元素，可以使用：
```r
names(rootNode)
```

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_91.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_92.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_93.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_94.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_95.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_96.png)

我们可以像访问列表一样，通过索引来访问特定元素：
```r
# 获取第一个<food>元素
rootNode[[1]]

# 获取第一个<food>元素下的第一个子元素（即<name>）
rootNode[[1]][[1]]
```

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_98.png)

## 使用XPath提取数据

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_99.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_100.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_101.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_102.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_104.png)

为了更灵活、更精确地提取数据，我们需要使用XPath语言。XPath是一种在XML文档中定位节点的语言。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_105.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_106.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_107.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_109.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_110.png)

以下是使用 `xpathSApply()` 函数提取特定数据的例子：

提取所有菜品的名称：
```r
xpathSApply(rootNode, "//name", xmlValue)
```
`//name` 这个XPath表达式会找到文档中所有名为 `name` 的节点，`xmlValue` 函数则提取这些节点的文本内容。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_112.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_113.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_114.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_115.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_116.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_117.png)

同样地，提取所有价格：
```r
xpathSApply(rootNode, "//price", xmlValue)
```

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_119.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_120.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_121.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_122.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_123.png)

## 实战：抓取网页数据

XML/HTML解析的一个常见应用是网络抓取。我们以从ESPN网站抓取巴尔的摩乌鸦队（一支美式橄榄球队）的比分信息为例。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_125.png)

首先，解析HTML网页：
```r
htmlUrl <- "http://espn.go.com/nfl/team/_/name/bal/baltimore-ravens"
htmlDoc <- htmlTreeParse(htmlUrl, useInternalNodes = TRUE)
```
注意，对于HTML文件，我们使用 `htmlTreeParse()` 函数进行解析。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_127.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_128.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_129.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_131.png)

然后，使用XPath提取特定元素。例如，提取所有class为”score”的列表项(`<li>`)的文本：
```r
scores <- xpathSApply(htmlDoc, "//li[@class='score']", xmlValue)
```
表达式 `//li[@class='score']` 的含义是：查找所有 `class` 属性等于 `score` 的 `<li>` 节点。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_133.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_134.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_135.png)

## 总结与资源

本节课中我们一起学习了XML的基础知识，包括其标签、元素和属性的结构。我们重点掌握了在R中使用`XML`包读取和解析XML/HTML文件的方法，并通过`xpathSApply()`函数结合XPath语言来精准提取所需数据。

*   **XML维基百科**： 提供关于XML的全面介绍。
*   **XML包简短教程**： 帮助快速上手R中的XML操作。
*   **XML包详细指南**： 提供深入和全面的使用说明。

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_137.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_138.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_139.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_140.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_141.png)

![](img/3fe7b8a3caf4b6ff905e73972007f5bd_142.png)

对于希望深入进行网络数据抓取或处理复杂XML数据的同学，进一步学习XPath语法和查阅上述资源将非常有帮助。