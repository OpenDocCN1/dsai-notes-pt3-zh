# 强推！(2026最新版) 李宏毅最新课程：智能体AI【AI Agent】71集全！人工智能／机器学习／深度学习／大模型／LLM - P49：48-18、Nomic Embed  新手入门 - Open Source Long Context Embedding Model - Ai人工智能工程师 - BV1QdzCB3Eu2

大家好，我是小木头，欢迎大家再次来到我的视频频道，今天我为大家分享一款，最新发布的开源文本嵌入模型，No miembed，OpenAI的embedding model，一直领跑文本嵌入模型这个领域。

但是呢OpenAI的模型并不开源，训练数据集也无从审计，近期OpenAI发布了最新的嵌入模型，Text embedding，Three small，非常优秀，也更加的便宜。

那开源模型是否有能够匹敌甚至击败OpenAI的呢，今天NO mic发布了他们的文本嵌入模型，No make embed，终于在综合技术评分上有几百OpenAI的表现，更为重要的是。

这是一款完全开源的模型。

![](img/49cc53a301dafd39333ff04946782846_1.png)

现在我所分享的这一份NOMI博客呢，介绍了他们最新的文本嵌入模型，Nomain bed，在图表中对于目前不同的主流的文本嵌入模型，技术评分有做对比。

我们可以关注normal embed和OpenAI的嵌入模型，分别是embedding，three small或者embedding a的，可以看到norman embed在综合的测评或评分上呢。

都非常的优秀，因此这对于我们来讲是一个非常好的消息，我们可以开始尝试使用这些。

![](img/49cc53a301dafd39333ff04946782846_3.png)

开源的文本嵌入模型，那刚才我们介绍的它是开源的。

![](img/49cc53a301dafd39333ff04946782846_5.png)

那究竟是如何开源呢，在这里他们有非常详细介绍模型开源，甚至开源了训练数据，开源了代码训练代码，同时呢这个模型是可重现可审计的，这就确保了大家能够明明白白的使用它，我会将所有这些链接，包括博客文章链接。

今天所使用到的示例代码链接，都放到视频描述中，需要的同学呢就在描述中取用吧，接下来我们就简单的来了解一下normal embed，一些基本的技术参数。

并通过示例来分享如何基于norm API与luncheon。

![](img/49cc53a301dafd39333ff04946782846_7.png)

来实现一个RG应用，有兴趣的同学呢可以通过这篇博客文章，了解非常多，关于normal embed，这个文本嵌入模型的技术细节，要注意的是，这款模型具有8192的上下文环境，它在短上下文。

长上下文的任务执行上，都能够击败OpenAI的ADA以及taxi beding street small，这款最新的文本嵌入模型，No mi，同样也发布了模型的权重参数以及训练代码。

这对于技术人员了解他的更多细节非常有帮助，那如何使用norman embed，非常简单，NORMI发布了他们的API服务，这样呢我们就可以使用API key来调用API。

使用embedding model，目前提供了100万，也就是a million免费的token，这对于我们评估和测试embedding，API或模型的表现非常的有帮助，至少呢可以降低我们的成本。

长上下文，意味着意味着我们能够处理更大的文件，这对于我们在文件处理，在RG应用的构建上都非常的有好处。



![](img/49cc53a301dafd39333ff04946782846_9.png)

接下来呢我们通过noon API的后台，来了解如何创建API key，如何使用API，了解一些API的技术参数，最后呢来构建一个简单的RG应用，及omic embed文本嵌入模型。

以及OpenAI的GBT4大模型，来构建这么一个RG应用，现在呢我们就先来到这里。

![](img/49cc53a301dafd39333ff04946782846_11.png)

这个呢就是normal API的文档，我们来看看TEXEMBEDDING文本嵌入，目前这个模型的名称叫nomic embed text me one，这是最新的文本嵌入模型，有几大参数，我们来了解。

首先上下文环境8192，Dimension，786，这个呢大家要注意的，他这个dimension是786，我们如果使用的是老的open adder embedding model呢。

应该大家知道是1536。

![](img/49cc53a301dafd39333ff04946782846_13.png)

在这里呢他的dimension更更小，接下来呢我们可以简单的看一下，text embedding API的规范，使用方式和OpenAI的API几乎一样，只需要加API key。

以authorization头的形式传递就可以了，我们在这里呢并不直接调用API，luncheon也提供了norman embed，这个文本嵌入模型的集成，那我们呢使用luncheon框架。

来完成示例代码的ROG应用的构建。

![](img/49cc53a301dafd39333ff04946782846_15.png)

现在呢我们就来看看NAMICAI的API服务后台，大家访问alice dot，omic dot AI就可以来到这个后台完成注册登录，就进入跟我现在相似这个界面，我们可以暂时不去管DATASETS。

Members usage。

![](img/49cc53a301dafd39333ff04946782846_17.png)

这些菜单，在API keys这里可以创建一个自己的API key，这也是我们在API调用中会用到的，这也是非常重要的，大家妥善保管，我们现在呢就会利用这个API key。

利用LUNCHE来构建一个RG应用。

![](img/49cc53a301dafd39333ff04946782846_19.png)

现在我所分享这份Python notebook，为我们演示如何利用LUNCHE来继承norman embed，这个文本嵌入模型，从而构建RG应用。



![](img/49cc53a301dafd39333ff04946782846_21.png)

在代码中用到的数据呢，是刚才我们所分享的这篇博客文章介绍，Norman in bed，当然了，这个文章长度和内容呢还不足以，耗尽8192这么长的一个上下文环境。



![](img/49cc53a301dafd39333ff04946782846_23.png)

所以代码呢仅做示例，有兴趣的同学呢可以寻找更庞大的文档，来充分的测试，评估长上下文的文本嵌入模型的表现，我们现在来看看这个代码，首先加载这个文档，然后呢做文档拆分，在拆分这里有两点要注意。

首先我们用到了tick token encoder的拆分器，那在这个拆分器中，chunk它的大小是基于TIKTOKEN，encoder编码后的token来计数，另一方面呢是chunk size。

我们设的比较大，7500，这也是得益于我们可以使用，长上下文的文本嵌入模型，也就是我们今天所使用的normal embed。



![](img/49cc53a301dafd39333ff04946782846_25.png)

在拆分以后。

![](img/49cc53a301dafd39333ff04946782846_27.png)

首先呢是做向量存储，构建检索器，再来构建一条lunch的链，基于检索器来得到相关文档，并结合提问。

![](img/49cc53a301dafd39333ff04946782846_29.png)

让大模型给到我们答案，在这里要注意我们需要设置几个环境变量，第一个呢是noma API key。

![](img/49cc53a301dafd39333ff04946782846_31.png)

这个环境变量会被后面normal embedding，这个类引用，我们将这个nomain API key。



![](img/49cc53a301dafd39333ff04946782846_33.png)

设置在COLLAB的个人的secret里面，这样呢就可以很方便的供我们在代码中使用。

![](img/49cc53a301dafd39333ff04946782846_35.png)

接下来就是构建一个向量存储，我们用到了chrome chroma中的embedding，使用的就是nomic embedding，要注意模型名，No make embed text v one。



![](img/49cc53a301dafd39333ff04946782846_37.png)

这是目前它所支持的唯一的一个模型名称，构建检索器。

![](img/49cc53a301dafd39333ff04946782846_39.png)

接下来呢就可以利用大模型来进行，RG应用的串联了，这就是一个LUNCHE的链，大模型呢会用到OpenAI API key。



![](img/49cc53a301dafd39333ff04946782846_41.png)

我们也从secrets当中获取链的创建，大家可以在这里关注一下模型，我们OpenAI的模型呢用的是GBT4，这样可以充分利用它的，长上下文的这么一个特性，所以我们在整个链的构建中。

既用到了长上下文的embedding model，也用到长上下文的聊天模型。

![](img/49cc53a301dafd39333ff04946782846_43.png)

也就是JPG4，现在呢我们就可以基于构建这条链来提问，比如norman embed是如何训练的。

![](img/49cc53a301dafd39333ff04946782846_45.png)

这个问题呢，其实在博客文章中有非常详细的介绍。

![](img/49cc53a301dafd39333ff04946782846_47.png)

介绍了如何的训练，那有兴趣的同学呢根据示例代码的执行，可以看看他的回答是否与博客中的介绍，技术细节相匹配，那这就是一个非常简单直白的RG应用及lunch，来集成了omic embed文本嵌入模型。

我们现在回到API文档。

![](img/49cc53a301dafd39333ff04946782846_49.png)

在这个文本嵌入模型的介绍中，大家需要注意的是，text length和dimension这两个指标，一个8192，一个786，特别是dimension，当我们使用像PYON这种云端的向量存储。

API服务的时候呢，会需要在创建索引的时候指定dimension，那我们需要去正确的设置它，这样呢才能够正确的使用这些云端的向量存储，服务好了，那有兴趣的同学呢可以赶紧来尝试一下。

看看究竟长上下文的这种开源的文本嵌入模型，在自己的AI应用中究竟能够发挥什么样的作用，是否在性能上和综合表现上能够做得更好呢，欢迎大家在评论区给我留言，那咱们就下期视频分享再见。



![](img/49cc53a301dafd39333ff04946782846_51.png)