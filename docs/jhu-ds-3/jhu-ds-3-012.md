# 012：从网络读取数据 🌐

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_0.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_2.png)

在本节课中，我们将要学习如何从网络上读取数据。网络数据来源广泛，本节课将主要聚焦于从网站中抓取数据，并简要介绍如何使用API以及进行身份验证。后续会有专门的课程深入讲解API部分。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_3.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_4.png)

## 什么是网络抓取？🕸️

上一节我们介绍了课程概述，本节中我们来看看网络抓取的具体定义。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_6.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_7.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_8.png)

网络抓取是指通过编程方式从网站的HTML代码或URL中提取数据。这是一种获取数据的有效方式。

例如，有人通过抓取Netflix为电影分配的所有类别数据，并进行了有趣的分析，这个故事因此广为传播。这展示了通过编程从网站提取数据可以收集到有价值的数据集。

## 网络抓取的注意事项 ⚠️

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_10.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_11.png)

了解了网络抓取的基本概念后，我们需要注意一些重要事项。

许多，甚至可以说几乎所有网站，都包含你可能希望通过编程方式读取的信息。然而，在某些情况下，这可能会违反网站的服务条款。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_13.png)

以下是需要注意的关键点：
*   一些网站明确声明不希望被爬取。如果你尝试抓取这些网站的数据，将自行承担风险。
*   如果你尝试过快地读取过多页面，一个非常常见的后果是你的IP地址可能会被封锁。
*   如果你从网站读取了大量专有信息，可能会遇到更大的麻烦。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_15.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_16.png)

因此，在决定从网站抓取数据时，需要谨慎。但总体而言，这仍然是一种快速收集大量数据的好方法。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_17.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_18.png)

## 示例：从Google Scholar抓取数据 📚

在了解了注意事项后，我们来看一个具体的例子：如何从我的Google Scholar页面编程提取数据。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_20.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_21.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_22.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_23.png)

这个页面展示了我发表的论文信息以及被引用次数，这是学术界关心的一类数据。

### 方法一：使用 `readLines` 和连接

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_25.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_26.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_27.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_28.png)

首先，我们将使用 `readLines` 命令从互联网获取数据。这是一种方法。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_29.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_30.png)

以下是操作步骤：
1.  使用 `url()` 函数打开到特定URL的连接。你需要传入你想建立连接的URL名称。
    ```r
    con <- url("http://scholar.google.com/citations?user=HI-I6C0AAAAJ&hl=en")
    ```
2.  使用 `readLines()` 函数从该连接中读取数据。
    ```r
    htmlCode <- readLines(con)
    ```
3.  就像操作数据库一样，使用完毕后务必关闭连接。
    ```r
    close(con)
    ```

查看我们从此收集的HTML代码，它会呈现为一个很长的大字符串。你可以指定 `readLines` 读取特定行数，但输出仍然会以这种未格式化的方式呈现，因此阅读起来有些困难。

### 方法二：使用 `XML` 包解析

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_32.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_33.png)

处理上述问题的一种方法是使用我们之前见过的 `XML` 包。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_34.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_35.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_36.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_37.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_38.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_39.png)

我们可以使用相同的URL，利用 `XML` 包并再次解析HTML，使用 `htmlTreeParse` 获取完整的结构。
```r
library(XML)
url <- "http://scholar.google.com/citations?user=HI-I6C0AAAAJ&hl=en"
html <- htmlTreeParse(url, useInternalNodes = TRUE)
```
然后，如果我想要获取页面标题，可以查找位于 `<title>` 标签内的节点来获取页面标题。或者，我可以通过查看该页面的特定表格元素来获取我的论文被引用的次数。
```r
# 获取标题
xpathSApply(html, "//title", xmlValue)
# 获取表格数据示例
xpathSApply(html, "//td[@id='col-citedby']", xmlValue)
```

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_40.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_41.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_42.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_44.png)

## 方法三：使用 `httr` 包进行GET请求 🔌

另一种获取数据的方法是使用 `GET` 命令，它位于 `httr` 包中。

对于像我们之前讨论的那样可以轻松访问的网站，使用连接可能是最简单的方式。但我们稍后会讨论为什么 `httr` 包在其他场景下非常有用。

首先加载 `httr` 包，然后使用相同的URL，通过 `GET()` 函数获取该URL。
```r
library(httr)
html2 <- GET(url)
```
现在需要做的是从该HTML页面中提取内容。我通过 `content()` 函数来实现，并指定以文本形式提取内容，即一个大文本字符串。
```r
content2 <- content(html2, as = "text")
```
然后，我可以使用 `htmlParse` 命令来解析该文本并获取解析后的HTML。
```r
parsedHtml <- htmlParse(content2, asText = TRUE)
```
这个 `parsedHtml` 看起来会和我直接用 `XML` 包提取的数据完全一样。然后我可以使用 `xpathSApply` 来提取标题，就像我之前做的那样。
```r
xpathSApply(parsedHtml, "//title", xmlValue)
```

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_46.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_47.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_48.png)

## 处理需要身份验证的网站 🔑

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_49.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_50.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_51.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_52.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_53.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_54.png)

以上就是使用 `GET` 进行与 `XML` 包类似操作的方法。在某些情况下，你可能需要处理更复杂的事情。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_55.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_56.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_57.png)

如果你用浏览器导航到这个网页，会发现它需要输入用户名和密码。如果我仅尝试使用 `httr` 包中的 `GET` 命令获取该页面，会得到一个状态码为401的响应，这是因为我没有通过身份验证，无法登录。

使用 `httr` 包，你实际上可以为网站进行身份验证。你可以通过分配给一个“句柄”来实现。我们去获取那个网站，再次传入URL，但这次我们使用 `authenticate()` 命令，并给它用户名和密码。在这个例子中，这只是一个测试网站，所以用户名是“user”，密码是“password”。你可以测试类似的情况，看看是否能获得访问权限。
```r
# 这是一个需要认证的示例URL
pg2 <- GET("http://httpbin.org/basic-auth/user/passwd",
           authenticate("user", "passwd"))
```
现在，响应状态码是200，这意味着我们实际上能够访问该文件，并且已经通过身份验证。现在我们可以查看 `pg2` 的名称，它提供了所有不同的组件，包括我们为此文件获取的cookie、用于访问它的句柄等等。然后，在通过R登录后，我们可以使用 `content()` 函数从该网站提取内容。
```r
names(pg2)
content(pg2)
```

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_59.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_60.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_61.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_62.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_63.png)

## 使用句柄保持认证状态 💾

确保使用句柄，因为如果你使用句柄，你可以在多次访问网站时保存身份验证状态。

如果你将Google设置为一个句柄（代表特定网站），那么你可以告诉 `GET()` 去获取那个句柄，并可以指定获取特定路径，或者发送不同的路径。例如，如果你对这个句柄认证一次，那么cookie将保留在该句柄中，你将保持已认证状态，无需在每次访问该网站时反复进行身份验证。
```r
# 创建并认证一个句柄
google <- handle("http://google.com")
pg3 <- GET(handle = google, path = "/")
pg4 <- GET(handle = google, path = "search")
```

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_65.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_66.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_67.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_68.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_69.png)

## 总结与进一步学习资源 📖

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_70.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_71.png)

本节课中我们一起学习了从网络读取数据的几种核心方法。

R-bloggers网站有很多关于如何从网络抓取数据的好例子。如果你去R-bloggers上搜索“web scraping”，你将能够找到所有这些教程。`httr` 包的帮助文件也包含许多有用的示例，主要是玩具示例。如果你将这些与R-bloggers上更实用的例子结合起来，可以学到很多东西。此外，请关注后续关于API的课程，以了解如何以编程方式与网站的API进行交互。

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_73.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_74.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_75.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_76.png)

![](img/638f563f38e8b3eb4d0f7c21d2a22ad8_77.png)

**核心要点总结：**
*   **网络抓取**是从网站HTML中提取数据的过程。
*   可以使用基础R的 `readLines()`、`XML` 包或 `httr` 包来获取和解析网页数据。
*   访问需要认证的网站时，可以使用 `httr::authenticate()` 或通过句柄管理会话。
*   进行网络抓取时，务必尊重网站的 `robots.txt` 和服务条款，避免过快请求导致IP被封。