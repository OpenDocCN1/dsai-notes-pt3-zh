# 强推！(2026最新版) 李宏毅最新课程：智能体AI【AI Agent】71集全！人工智能／机器学习／深度学习／大模型／LLM - P27：26-4、RAG共学二：RAG中如何进行查询转换？ - Ai人工智能工程师 - BV1QdzCB3Eu2

AI开发前途无限。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_1.png)

欢迎来到AI开发者的频道，今天呢我们来继续学习RAG的第二部分。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_3.png)

也就是查询转换这部分的内容啊。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_5.png)

看起来很多，但是呢理解起来其实非常的简单，查询转换的这个方法的原理呢。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_7.png)

就非常类似于咱们常说的三个臭皮匠，顶个诸葛亮。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_9.png)

下面我们就从这个角度啊，来看一下这个查询转换，首先我们来看看什么是查询转换。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_11.png)

查询转换呢它是为了更好地检索信息。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_13.png)

二对检索问题呢进行重写或修改的一系列方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_15.png)

简单直白的说就是将你问的问题啊换个说法，换个表达的方式来进行检索。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_17.png)

那为什么要换个说法，换个表达方式呢，这边呢是LANCHEN官方从技术角度的一个解释。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_19.png)

他这里介绍说呢。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_21.png)

RAG检索呢是将文本向量化之后。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_23.png)

那这种检索方式啊容易受到措辞表达的影响，从而难以捕捉到数据真实的语义，那这样的结果呢，就是RAG的所效果呢可能会不好。



![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_25.png)

也就是文档的召回率呢比较低，那么该如何解决呢。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_27.png)

那这一部分他提供的这些方法呢，就是使用了这个三个臭皮匠顶个诸葛亮的原理。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_29.png)

那一个臭皮匠呢肯定是比不过诸葛亮的那三个。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_31.png)

为什么就可以了呢，因为三个人嘛，每个人考虑问题的角度不一样。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_33.png)

那通过三个人的合作和相互补充呢，结果就是做到了比诸葛亮更厉害。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_35.png)

好的，那下面我们就来看看，这三个臭皮匠是怎么给整出来的。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_37.png)

这里啊他一共介绍了四种查询转换的方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_39.png)

我们先通过这张图呢，来看一下这几种方法的关系，中介呢是这个用户最初的查询描述。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_41.png)

横向呢表示的是与原问题相似的描述。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_43.png)

也就是这个MULTIQUERY的方法，这个方法呢它通过重写改写的方法呢。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_45.png)

生成多个相似的查询，那再往上面呢就是表示更加抽象的描述。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_47.png)

也就是这里的step back的方法，它是将查询问题进行总结概括。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_49.png)

通过更加概括的描述呢来进行文本的检索。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_51.png)

最下面呢表示更加具体细节的描述方式，也就是这里的day composition的问题分解方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_53.png)

它是将一个复杂的抽象问题分解为多个子问题。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_55.png)

除了上面的方法呢，最后还有一个基于假设解答的一个查询方式。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_57.png)

方法呢就是先使用大模型对问题呢进行解答。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_59.png)

然后根据这个解答呢来进行文本的检索，那上面呢就是四种制作臭皮匠的方法了，三个臭皮匠有了。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_61.png)

那么怎么将他们的想法进行合并呢，这就是啊这边提到的这个r a g fusion的方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_63.png)

这一部分呢就讲了这么多内容，看起来内容很多。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_65.png)

其实呢除了这个RAGFASION的方法，有些算法在里面之外啊，其他的四种方法呢都可以理解为啊，是提示词工程的方法，也就是呢通过使用一个大模型，以及不同的提示词，让大模型呢将用户输入的问题呢转化为另一种。



![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_67.png)

我们希望的描述，基于这种新的描述呢再进行检索。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_69.png)

最后呢生成最终的答案，好的，下面呢我们就来分别再看一下这四种方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_71.png)

首先呢是第一个，也就是这个multi query的方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_73.png)

通过这个图啊，我们可以看到，首先呢他将用户问题啊进行重写改写。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_75.png)

生成了多个问题，然后呢基于这个新的问题啊进行查询，最后呢将查询结果呢进行合并，最终呢生成答案。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_77.png)

那我们呀可以看一下它的提示词是怎么写的，这里呢我讲这个提示词啊翻译成了中文。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_79.png)

我们来读一下，他这里说呢你是一个人工智能语言模型助手。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_81.png)

你的任务呢是生成五个不同版本的用户问题。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_83.png)

已从向量数据库中呢检索相关的文档。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_85.png)

通过从多个角度生成用户问题呢，你的目标啊是帮助用户克服基于距离。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_87.png)

相似搜索的一些限制，请提供这些替代问题。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_89.png)

并用换行符分割，在后面呢是给出了原始的问题。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_91.png)

通过这个提示词的写法，你可以看到他不仅啊告诉大语言模型啊。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_93.png)

他要做什么，还告诉了大语言模型是在什么场景下使用，以及啊是为了克服什么样的问题而来使用，大家在写提示词时呢，可以参考一下这种思路。



![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_95.png)

下面我们再来看一下这个decomposition的方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_97.png)

也就是将问题分解的一个方法，这边我们可以看到它也是先生成不同的问题。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_99.png)

然后进行文本检索，分别产生回答，最终答案产生的时候呢。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_101.png)

他这里呢提出了两种方法，一个是递归的回答方式。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_103.png)

另一个呢是独立回答，最后合并的方式，递归的方式呢是将前面回答的问题和答案呢。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_105.png)

作为下一个问题解答过程中的提示词的一部分。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_107.png)

来使用，独立回答的方式呢，是先将各个问题呢独立进行解答。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_109.png)

然后呢再将这所有解答的内容呢整合为提示词。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_111.png)

最后啊再用大语言模型做一次最终的解答，所以这个的主要工作呢它也是一个提示词工程。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_113.png)

这个提示词的写法呢教程中啊都有介绍。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_115.png)

这里我们就不做详细解释了，在下面呢是这个step back的方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_117.png)

也就是将问题进行抽象，通过抽象后的问题呢再进行文本的检索。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_119.png)

这里呢是因为啊对问题进行了抽象和概括。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_121.png)

所以在最终的答案生成时呢，会与原问题检索的结果一起来进行使用。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_123.png)

那具体的方法呢，可以看教程中的这一部分的代码。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_125.png)

最后呢就是这个HYDE这个方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_127.png)

也就是呢假设文档嵌入技术方法，这边呢我找到了一个与标准方法的对比图。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_129.png)

我们来看一下，左边呢是标准的RAG的检索过程。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_131.png)

右边呢是这个HYDE方法的检索过程，我们可以看到。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_133.png)

标准的方法呢，是直接基于问题来进行文本的检索。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_135.png)

最后呢返回检索的结果，但是这个HYD这个方法呢。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_137.png)

它是呢首先基于原问题产生一个回答，然后基于回答的文本呢进行检索。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_139.png)

好的以上呢就是这四种方法，最后呢我们再来看一下这个RAGFASION的部分。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_141.png)

虽然这个教程里啊，将fusion的方法呢放在前面介绍的，但是呢我觉得这个FASION的方法，它不仅可以用于这个MULTIQUERY的方法，也可以啊，对上面四种方法做检索结果的合并处理。

所以这里啊我把它放到最后啊。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_143.png)

来介绍这个教程当中啊，有两个结果合并处理的方法，第一种呢是这个方法，这个方法呢相对来说是比较简单粗暴的，但是呢直接将检索到的文本啊进行了去重，然后将所有的文本呢送给大圆模型。



![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_145.png)

进行最终的答案生成，最终能使用到多少里面的知识呢。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_147.png)

就完全依赖于大语言模型的能力了，第二种方法呢是这个r a g fusion的方法。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_149.png)

这个方法呢是根据一个文本啊，在各个子问题检索出来的文本当中。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_151.png)

排序的位置啊，来对这个文本啊进行重新打分的一个方式啊，对文本进行重新排序。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_153.png)

这样做的好处是呢越排在前面的文本呢，相关性啊应该是越大，尤其是啊你只希望选择有限个检索文本啊，来进行生成时，效果呢就会更好，以上呢就是这个教程啊，第二部分介绍的内容，教程中啊都有相关的代码。



![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_155.png)

大家可以执行一下这些代码测试一下，看看这些方法呢是否真的有效。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_157.png)

尤其是呢可以尝试一下这几种方法的组合。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_159.png)

看看呢是否可以获得更好的结果，好的，以上就是今天的分享。

![](img/c2d2ab00cccd5f7d4d1d0adaf4e055b7_161.png)

感谢您的收看。