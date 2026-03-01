# 013：从API读取数据 📡

![](img/a4f5f031e4badf9f97c4faca6a32e08a_0.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_2.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_3.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_4.png)

在本节课中，我们将学习如何从网络应用程序编程接口获取数据。API是许多互联网公司提供数据访问的标准化方式。我们将以Twitter API为例，演示使用R语言的`httr`包进行身份验证、发送请求和处理返回的JSON数据。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_5.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_6.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_8.png)

## 什么是API？

![](img/a4f5f031e4badf9f97c4faca6a32e08a_10.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_11.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_12.png)

API是应用程序编程接口。大多数互联网公司，如Twitter或Facebook，都提供API，允许开发者下载数据。例如，你可以获取哪些用户在发推文、推文内容或人们在Facebook上发布的信息。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_13.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_15.png)

通常，你可以通过向特定URL发送GET请求来获取这些数据，URL中可能包含参数。

我们将能够使用`httr`包从这些网站获取数据。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_17.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_18.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_19.png)

## 创建API应用程序账户

![](img/a4f5f031e4badf9f97c4faca6a32e08a_20.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_21.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_22.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_23.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_24.png)

通常，你需要做的第一件事是创建一个账户。这里不是指普通的用户账户，而是需要与特定组织的API或开发团队创建一个应用程序账户。

例如，我们将访问 `dev.twitter.com/app`。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_26.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_27.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_28.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_29.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_30.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_31.png)

我们将创建一个应用程序。在这个例子中，我们将使用我博客的Twitter账号“simplystats”来创建一个应用程序。

现在，我们已经使用Twitter详细信息登录。你可以看到我以“simply statistics”登录。我可以点击按钮创建一个新应用程序。这将为我提供一些数字，稍后我将用这些数字在R中进行身份验证以访问数据。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_33.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_34.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_35.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_36.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_37.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_38.png)

这里我已经创建了一个名为“Simplyimp Sta blog”的应用程序。点击该应用程序，会进入一个类似这样的页面。这是应用程序，上面是应用程序的URL。还有一些关于我的组织和组织网站的信息我没有填写。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_40.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_41.png)

在下面的OAuth设置中，我可以看到我对API拥有读写权限。然后有一串数字，我在这里将它们涂黑了，因为这些数字对于你创建的应用程序是私密的。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_43.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_44.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_45.png)

你将拥有一个消费者密钥、一个消费者密钥、一个请求令牌URL和一个授权URL的数字。创建应用程序后，你需要记下所有这些数字，因为我们稍后将在R代码中使用它们来访问API。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_47.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_48.png)

## 在R中进行身份验证和获取数据

我们将使用`httr`包。加载该包后，我们将使用`oauth_app`命令。这将启动应用程序的授权过程。你需要为应用程序命名，这实际上不会发送到API，只是为了方便。我在这里将其命名为“Twitter”，因为它将是Twitter应用程序。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_50.png)

然后，我将在这里输入我从应用程序网站获得的消费者密钥和消费者密钥。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_51.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_52.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_53.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_54.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_55.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_56.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_57.png)

接下来，我将使用从网站收集的令牌和令牌密钥来登录。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_58.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_59.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_60.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_61.png)

完成这些后，我就创建了允许我访问Twitter私有数据的凭证，这些数据仅对拥有应用程序的人可用。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_63.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_64.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_65.png)

现在，我使用`GET`命令。这与我从互联网读取数据时所做的非常相似。我将使用一个非常特定的URL，这是对应于Twitter API的URL。URL的这一部分是API的版本1.1，这是Twitter API的当前版本。然后我传递更多组件，这些组件对应于我想要获取的数据。在这个例子中，我想获取我的主页时间线上的状态，并将其作为JSON文件获取，这是Twitter目前唯一支持的数据类型。然后，我将传递使用OAuth登录的身份验证，而不是使用用户名或密码进行身份验证。我将返回的是对应于这个URL的页面，实际上只是一些JSON数据。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_67.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_68.png)

## 处理JSON数据

![](img/a4f5f031e4badf9f97c4faca6a32e08a_69.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_70.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_71.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_72.png)

我可以使用`content`函数来提取JSON数据。`content`函数会识别出这是JSON数据，并使用`RJSONIO`包中的`fromJSON`函数。

这将返回一个结构化的R对象，但有点难以阅读。因此，我将使用`jsonlite`包将其重新格式化为数据框。我将从原始命令`content`中获取的JSON结构，将这个结构化的R对象转换回JSON，然后使用`jsonlite`版本的`fromJSON`参数来创建数据框。

现在，这个数据框的每一行都对应于我主页时间线上的一条推文。在这里，你可以看到我将查看这个数据框的第一行，这是我提取数据时主页时间线上最新的推文。我将查看前四列：推文创建的时间、推文的ID号、ID字符串，以及推文的文本。这就是我收集数据时最新的推文。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_74.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_75.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_76.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_77.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_78.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_79.png)

你可以这样做来从Twitter提取信息。这实际上只是如何收集关于我的主页时间线信息的请求。但你可以做很多其他请求，可以通过Twitter访问许多不同的数据。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_80.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_81.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_82.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_83.png)

## 如何查找API文档和参数

![](img/a4f5f031e4badf9f97c4faca6a32e08a_85.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_86.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_87.png)

那么，我是如何知道使用哪个URL的呢？你需要查看Twitter API的文档。这是之前的同一个网站。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_89.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_90.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_91.png)

我将查看Twitter文档，我会看到资源URL，这就是我将传递给`GET`命令的URL。

它下面还有很多参数。如果你查找如何格式化发送给API的参数，你实际上可以发送许多不同的参数。例如，你可以告诉它收集多少条推文，从什么时间开始收集等等，这取决于你访问的URL。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_93.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_94.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_95.png)

如果你想获取其他信息，不仅仅是关于主页时间线的信息，你可以访问主要的Twitter文档。这是API最新版本1.1的文档，它会提供获取多种不同信息的方法。你可以获取关于提及的所有信息，可以获取用户时间线信息，可以获取主页时间线信息，可以获取转发信息，可以下载所有这些信息。你还可以搜索Twitter feed，获取你感兴趣的特定标签或你可能想关注的话题标签。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_96.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_97.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_98.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_99.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_100.png)

## 总结与扩展

![](img/a4f5f031e4badf9f97c4faca6a32e08a_102.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_103.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_104.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_105.png)

总的来说，你必须查看文档。如果你被授权，`httr`允许GET、POST、PUT、DELETE请求。正如你所见，我被授权对“simply stats”的时间线进行读写，因为我是通过它创建应用程序的。

在某些情况下，你也可以使用用户名和密码进行身份验证。不过，大多数现代API使用类似OAuth的东西，就像我们在Twitter上看到的那样。`httr`与Facebook、Google、Twitter、GitHub等配合良好。如果你访问GitHub上的`httr`演示组件，你实际上可以看到许多如何访问不同网站API的示例。本讲座实际上就是以Twitter API的演示为蓝本的。

![](img/a4f5f031e4badf9f97c4faca6a32e08a_107.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_108.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_109.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_110.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_111.png)

![](img/a4f5f031e4badf9f97c4faca6a32e08a_112.png)

本节课中，我们一起学习了从API读取数据的基本流程：创建应用程序、获取密钥、在R中使用`httr`包进行OAuth身份验证、发送GET请求获取JSON数据，并使用`jsonlite`包将数据转换为易于分析的R数据框。掌握这些步骤，你就能从许多提供API的网站获取丰富的数据。