# 强推！(2026最新版) 李宏毅最新课程：智能体AI【AI Agent】71集全！人工智能／机器学习／深度学习／大模型／LLM - P41：40-10、LangChain进阶  基于LangChain的Claude-3 XML Agent - Ai人工智能工程师 - BV1QdzCB3Eu2

大家好，我是小木头，欢迎大家来到我的频道，今天我会介绍基于class three模型的excel agent。



![](img/eccecdbf3da5a6cd999968de627a3a6a_1.png)

在lantern极简入门课程的第八课，我介绍了代理，也就是agent，这是蓝拳支持的代理机制，有兴趣的同学可以点击视频上方的链接，回到当时的分享来了解lunch agent基本工作原理。

今天介绍的XML agent会在launch agent基础上，针对cloth three模型的特性来进行改进，让其最大化的发挥claw模型的优势。

我依然会用一份Python notebook来分享今天内容。

![](img/eccecdbf3da5a6cd999968de627a3a6a_3.png)

现在呢我们就来到今天分享的这份Python NO book，我会将分享中用到的文档和代码，链接呢都放在视频描述中，需要的同学呢就在描述中取用，首先我们来看看为什么要用agent，Agent。

这个概念的核心理念是，利用大圆模型来决定任务执行的顺序，或做决策该执行哪一个任务，首先我们来介绍一下什么是XML agent。



![](img/eccecdbf3da5a6cd999968de627a3a6a_5.png)

我们先回到ANTHROPIC所提供的开发者手册。

![](img/eccecdbf3da5a6cd999968de627a3a6a_7.png)

在这里呢有一个段落叫prompt engineering，这也就是提示词工程，其中有一个章节叫use XML text。



![](img/eccecdbf3da5a6cd999968de627a3a6a_9.png)

我们通过这部分内容来了解。

![](img/eccecdbf3da5a6cd999968de627a3a6a_11.png)

基于此就能知道为什么我们会有XML agent这个概念，大家应该对XML text也就是XML标签非常的熟悉，这是在cloud大模型的世界里面，来结构化提示词指导模型该如何响应，非常重要的一种手段。

一种非常强大的工具，在cloud大模型的世界里面，提示词中包含的XML标签有非常好的理解，cloud模型在训练的过程中，都是通过这种格式或者类型的提示词，来进行训练的，因此我们将一些关键的部分或信息呢。

通过XML标签来包裹，这样呢能够帮助cloud模型更好地理解上下文信息，并且生成更加准确的输出，当我们要处理复杂的提示词，或者在提示词中包含了变量输入时，这种技术变得特别的有用，我们接下来呢就会看看。

在提示词或在cloud模型的交互中如何使用XML text。

![](img/eccecdbf3da5a6cd999968de627a3a6a_13.png)

那为什么我们要用XML text，在文档中还有更加详细的介绍。

![](img/eccecdbf3da5a6cd999968de627a3a6a_15.png)

我们再次回到文档，这里，在下面这里有一段y use XML text，有几大理由支撑我们在与cloud模型交互时，尽量利用XML标签，第一个呢是更高的精确度，第二个呢是更加清晰的文字语言数据的结构。

最后呢是更加容易的后处理，Post processing，基于这几方面，那么我们也是在CD模型的agent实现中，推荐使用XMLTX。



![](img/eccecdbf3da5a6cd999968de627a3a6a_17.png)

也就是说我们推荐大家实现XML agent。

![](img/eccecdbf3da5a6cd999968de627a3a6a_19.png)

在今天的这个tutorial手册当中呢，会用到以下的这些工具或者组件，第一个是court模型，我们会用到class three，大家可以在opus或者sonnet之间做选择，他们各有所长。

一会呢我们也会再度的介绍，在agent构建呢用到了luncheon框架，另一方面我们会做向量数据存储，在这里用到了face，大家可以选择不同的向量存储解决方案，比如chrome a pine cone。

这些都可以，最后我们是用PDF文档做的演示，因此呢在这里也用到了PYPDF。

![](img/eccecdbf3da5a6cd999968de627a3a6a_21.png)

接下来我们看看代码部分究竟我们做了些什么，首先安装一系列的开发包，Luncheon，Luncheon，Hob，Luncheon，Anthropic，Launchopen ai pp i pdf。

简单介绍一下蓝拳相关的组件呢，大家都应该比较熟悉了，那LANCHANTHROPIC主要提供了ANTHROPIC，也就cloth three模型的集成接口。

而lunch OpenAI目的呢是使用OpenAI的embedding model，这里有许多选择，大家可以将open aembedding model，切换成其他大家想要使用的。

这里我们会下载一份PDF文件，这个文件呢来自ARCAVE上面的一一份paper。

![](img/eccecdbf3da5a6cd999968de627a3a6a_23.png)

我在这里也打开了，应该是叫esop agent这么一个agent的研究，paper来自于阿里巴巴集团的达摩学院。



![](img/eccecdbf3da5a6cd999968de627a3a6a_25.png)

这里面对这个agent有介绍他的方法论，他的实验以及结论，那我们正是以它来做的事例，为什么我用它呢，是因为在这篇文章的发布呢。



![](img/eccecdbf3da5a6cd999968de627a3a6a_27.png)

是在2024年，应该是非常新的。

![](img/eccecdbf3da5a6cd999968de627a3a6a_29.png)

绝大多数模型的训练呢，是没有包含这类数据的知识。

![](img/eccecdbf3da5a6cd999968de627a3a6a_31.png)

因此大概率通过直接与模型的问答训练，数据集中应该是无法给到我们答案的。

![](img/eccecdbf3da5a6cd999968de627a3a6a_33.png)

我们也可以确保这个问答只能由agent。

![](img/eccecdbf3da5a6cd999968de627a3a6a_35.png)

基于知识库来进行信息的检索。

![](img/eccecdbf3da5a6cd999968de627a3a6a_37.png)

那回到这里，我会将这个文件下载在本地，有这么一个文件。

![](img/eccecdbf3da5a6cd999968de627a3a6a_39.png)

ESOP或AESOOPA卷PDF，接下来准备两个环境变量，一个是OpenAI API key，一个呢是anthropic API key。



![](img/eccecdbf3da5a6cd999968de627a3a6a_41.png)

都是通过collab secrets这里加载，大家可以在这里安全的管理自己的密钥。

![](img/eccecdbf3da5a6cd999968de627a3a6a_43.png)

接下来呢加载一系列的组件，Pdf loader，Face，Open in a embedding，加载这个PDF文件加载并拆分，通过这个load and split将其一次性的完成操作。



![](img/eccecdbf3da5a6cd999968de627a3a6a_45.png)

有了拆分后的文档片段呢，就可以通过face来完成向量存储。

![](img/eccecdbf3da5a6cd999968de627a3a6a_47.png)

这样就得到了一个向量存储的变量，这个存储变量呢后面会被用来做检索用。

![](img/eccecdbf3da5a6cd999968de627a3a6a_49.png)

接下来利用了lunch的工具标记at t，这样呢就可以将一个函数封装成一个，launch的工具，这个就会被agent所用，非常简单的一个实现，他是做的issue agent search。

搜索的目的呢是通过一个提问，在向量存储中找到相关的文档，仅此而已，将搜索到文档的文本内容，通过双换行符串联起来，这就得到了一个长长的文本，这就是相关文档内容的信息，我们拿它来作为上下文信息。

在后续大漠线问答中使用，这就构建了一个esop agent search这么一个工具to。

![](img/eccecdbf3da5a6cd999968de627a3a6a_51.png)

目前我们示例中就这么一个唯一的工具，因此呢这个tools数组当中就这么一个工具。

![](img/eccecdbf3da5a6cd999968de627a3a6a_53.png)

接下来可以做一个测试，通过这个执行来测试一下，这个工具是否正常工作。

![](img/eccecdbf3da5a6cd999968de627a3a6a_55.png)

我们这里运行一下，可以看到这个文本就是工具的返回值。

![](img/eccecdbf3da5a6cd999968de627a3a6a_57.png)

它将搜索到的相关文档的内容串联了起来，那这就是我们的工具。

![](img/eccecdbf3da5a6cd999968de627a3a6a_59.png)

当有了工具就可以来构建agent，在构建agent之前呢。

![](img/eccecdbf3da5a6cd999968de627a3a6a_61.png)

会首先加载一个提示词模板，这个模板来自于luncheon hop，luncheon hop在哪里，现在分享一下。



![](img/eccecdbf3da5a6cd999968de627a3a6a_63.png)

在这里我已经打开了这个提示词的组件，叫XML agent convo conversation。

![](img/eccecdbf3da5a6cd999968de627a3a6a_65.png)

在这里可以看到他的细节详细内容。

![](img/eccecdbf3da5a6cd999968de627a3a6a_67.png)

大家也并不一定必须使用篮球hop，大家也可以自己手动来编写这个提示词，也可以参考这个模板，在这个模板当中呢有几个细节点。



![](img/eccecdbf3da5a6cd999968de627a3a6a_69.png)

大家可以注意，首先变量这是依然存在的tools，这里呢就嵌入目前agent支持的tools，这个在后面参数会传递，另外一个呢就是chat history。



![](img/eccecdbf3da5a6cd999968de627a3a6a_71.png)

剩下部分input就是用户的提问，Agent scratch path，这里呢包含了在后续agent执行过程中，中间步骤的信息，最后我们要注意的是，在这个提示词当中呢多了一些XML标签。

可以看到在这里给到的示例工具，也就函数调用的一些信息呢，是通过XML标签来标记的，大家应该有印象，在过去分享中，当我们需要给到一些事例的时候呢，通常用的是JASON的数据格式。

那在这里呢都用到了XML标签，包括回答该怎么回答，也是通过XML标签来定义的，在这里当模型完成工作以后要回答的时候，最终的回答呢应该通过final answer这个标签包裹。

这就是我们在提示词当中该如何使用XML标签，这就是我们所谓的XML agent。

![](img/eccecdbf3da5a6cd999968de627a3a6a_73.png)

好了，现在可以回到Python notebook这里。

![](img/eccecdbf3da5a6cd999968de627a3a6a_75.png)

当我们拉取了这个组件，那其实也就是拉取到了一个提示词。

![](img/eccecdbf3da5a6cd999968de627a3a6a_77.png)

就可以开始agent构建，我们用的是ANTHROPIC模型，在模型的支持上呢，现在有三个变体，一个呢是opus，一个是sonnet，还有high ko，大家可以根据自己的需求来选择。

如果想选择快一些的模型呢，可以使用sonnet，如果想选用更功能强大一些的呢，选择opus。

![](img/eccecdbf3da5a6cd999968de627a3a6a_79.png)

在这里我们用了sonnet，当构建好这个模型，我们可以尝试问who developed esop agent，大概率呢他是不能够正确的回答出这个问题的。



![](img/eccecdbf3da5a6cd999968de627a3a6a_81.png)

或者说得不到我们想要的这个答案。

![](img/eccecdbf3da5a6cd999968de627a3a6a_83.png)

阿里巴巴集团的达摩学院，我这里呢就不执行这个问题了。

![](img/eccecdbf3da5a6cd999968de627a3a6a_85.png)

有兴趣的同学可以去测试一下，下面有两个辅助函数，它帮助我们将中间步骤转换成XML标签，标记的内容，中间步骤呢是代理在执行过程中，根据基于上下文信息有大模型来决策的，下一步该做什么。

我们后面也会看到这些中间步骤的信息。

![](img/eccecdbf3da5a6cd999968de627a3a6a_87.png)

究竟是什么样的，接下来就可以来定义一个agent，这个agent会接受一系列参数，包括了输入信息，也就是用户提问，聊天历史记录以及中间步骤，中间步骤呢就会被填写到agent scratch pad。



![](img/eccecdbf3da5a6cd999968de627a3a6a_89.png)

这个标签定义的地方，或者这个变量定义的地方，我们回到这个提示词模板。

![](img/eccecdbf3da5a6cd999968de627a3a6a_91.png)

可以看到它就在这里，agents scratch版，它也就追加在了提示词。

![](img/eccecdbf3da5a6cd999968de627a3a6a_93.png)

最后我们现在有了agent，就可以来构建一个记忆组件，在这里呢使用的是conversation buffer。



![](img/eccecdbf3da5a6cd999968de627a3a6a_95.png)

Window memory，我们只会让他记忆最近的五条记录，我们如何将这个聊天历史嵌入到提示词中呢，我们再次回到提示词模板，这里可以看到他有一个chat history，那我们就需要代码。

将这些聊天历史记录或者是记忆转换成字符串，这样呢才能够嵌入到提示词中，因此就有了这个memory to string这个函数，它将这个消息数组转换成一条长长的字符串。



![](img/eccecdbf3da5a6cd999968de627a3a6a_97.png)

会根据是人类human的消息还是AI的响应，来将其转换转换格式分别是human冒号或AI冒号，这样就有了聊天历史。



![](img/eccecdbf3da5a6cd999968de627a3a6a_99.png)

它也会被嵌入到提示词中，最后呢就定义一个代理的执行器agent execute。

![](img/eccecdbf3da5a6cd999968de627a3a6a_101.png)

我们在这里除了指定agent，告诉他用哪个代理执行工具集tools，还将这return intermediate steps设为了true，这样呢我们可以在后面的agent执行的结果中。

看到究竟中间步骤有哪些，也就是intermediate depth。

![](img/eccecdbf3da5a6cd999968de627a3a6a_103.png)

我们将verb设为true。

![](img/eccecdbf3da5a6cd999968de627a3a6a_105.png)

这样呢大家可以看到究竟做了什么，最后定义了一个chat函数，这个函数呢是完成聊天，接收一个字符串作为输入，这个参数呢就是用户的提问，这样呢来完成代理执行，输入两个参数，第一个呢是用户的提问。

第二个呢是聊天历史，我们会将这个记忆组件作为参数，通过memory to string函数将其转换成长长字符串，嵌入到提示词中，当我们完成一次问答，会在聊天的记忆组件当中添加两条信息。

第一条呢是用户的输入信息，第二条呢是AI的响应，AI响应呢是在这个agent executor，invoke函数的返回值中，output字段就是AI的回答，这样呢就完成了xm agent的构建。



![](img/eccecdbf3da5a6cd999968de627a3a6a_107.png)

现在呢我们就可以基于这个agent来提问，我将这个问题略作修改，我来提问谁开发的ESOAGENT，这个呢一定是应该是从知识库中检索而来，现在执行一下这部分代码。



![](img/eccecdbf3da5a6cd999968de627a3a6a_109.png)

来看看它的执行结果，可以看到这里用到的工具。

![](img/eccecdbf3da5a6cd999968de627a3a6a_111.png)

Esop agent search，这也是刚才我们定义的工具，输入这些信息呢都是通过XXL标签来标记的。



![](img/eccecdbf3da5a6cd999968de627a3a6a_113.png)

![](img/eccecdbf3da5a6cd999968de627a3a6a_114.png)

详细的调试和执行信息呢都是来自于，刚才我们将verse设为了true。

![](img/eccecdbf3da5a6cd999968de627a3a6a_116.png)

在这里来看看结果。

![](img/eccecdbf3da5a6cd999968de627a3a6a_118.png)

结果应该就是通过final answer这个标签标记的，我们来看看他的回答，有几点关键信息，第一呢是由达摩学院，也就阿里巴巴集团的达摩学院的研究员提议的。

这是一个story to video production system。

![](img/eccecdbf3da5a6cd999968de627a3a6a_120.png)

剩余信息呢我们就暂时忽略了。

![](img/eccecdbf3da5a6cd999968de627a3a6a_122.png)

有兴趣的同学，大家可以进一步的比对一下，包括研究员的名字有哪些，在这里，最后来看看中间步骤，也就是intermediate steps。



![](img/eccecdbf3da5a6cd999968de627a3a6a_124.png)

看看他究竟做了哪些中间步骤的操作，在这里呢就是这个工具的使用，its of agent search输入信息是who developed is of agent，那后面呢就是其他一系列信息了。

有兴趣的同学呢也可以来调试一下，这就是咱们今天这个xm agent的示例。

![](img/eccecdbf3da5a6cd999968de627a3a6a_126.png)

最后呢我们回到ANTHROPIC用户手册，这里，刚才我们介绍了使用XMTX，这也是推荐的在cloth street模型应用中，用来标记或结构化提示词的一种方式，但是呢它也不是唯一支持的数据的格式。



![](img/eccecdbf3da5a6cd999968de627a3a6a_128.png)

在后续这里有control upper format，这里也介绍，cloth street目前能够支持其他的数据格式，它有JASONXML，Html markdown，Csv。



![](img/eccecdbf3da5a6cd999968de627a3a6a_130.png)

甚至一些自定义的格式，在底下呢，这里就可以看到一个非常简单的JSON，数据格式的例子，用户提问是期望能够用JASON格式来得到数据，cloud也能很好的给到我们一个结果。

因此大家也可以在自己的应用场景中，进行一些测试和评估，看看究竟XML text，是否能够在一些特定应用场景中，表现的比JASON更好，那这呢那这就是今天我们分享的主要内容。

介绍了什么是xxl agent，如何实现它，那究竟哪种格式最能够符合自己的应用场景，哪种格式究竟在close three模型的应用中表现最好，那也请大家在测试后，欢迎在评论区给我们反馈。

那今天视频分享就到这里，也感谢大家观看，大家记得继续关注我们频道哦，那咱们就下次视频分享再见。

![](img/eccecdbf3da5a6cd999968de627a3a6a_132.png)