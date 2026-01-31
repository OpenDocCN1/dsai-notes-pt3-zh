# 强推！(2026最新版) 李宏毅最新课程：智能体AI【AI Agent】71集全！人工智能／机器学习／深度学习／大模型／LLM - P9：8-第五讲：利用多张GPU训练大型语言模型 - Ai人工智能工程师 - BV1QdzCB3Eu2

![](img/723e9c79ea07c23eb14c99280ea0a075_0.png)

好那我就开始了好，那我们呢就请这个王秀全助教来跟大家讲一下。

![](img/723e9c79ea07c23eb14c99280ea0a075_2.png)

怎么发挥GPU真正的能力，那你可能常常会听到有人说，今天要做一个语言模型，你要有一张好GPU，而且一张还不够，还要多张好的GPU，你也常常会听到有人说，哎呀这个模型塞不进GPU里面。

所以没办法训练这么大的模型，然后秀轩要来跟我们讲说怎么善用GPU的能力，尤其是多张GPU的能力好。

![](img/723e9c79ea07c23eb14c99280ea0a075_4.png)

那我们就给助教个热烈的掌声，谢谢。

![](img/723e9c79ea07c23eb14c99280ea0a075_6.png)

好诶大家好，那我是助教王秀轩，我今天要和大家讲的PY。

![](img/723e9c79ea07c23eb14c99280ea0a075_8.png)

就像老师刚刚提到的，就是如果说你今天要训练的是大语言模型的话，你会大概会需要哪一些硬体以及软体上的工具，这样子，那这个qr co呢是我的诶投影片，大家可以去扫一下。

因为我怕我刚看投影可能稍微有些不太清楚。

![](img/723e9c79ea07c23eb14c99280ea0a075_10.png)

所以呃如果呃大家需要看的更仔细的话。

![](img/723e9c79ea07c23eb14c99280ea0a075_12.png)

可以扫这个qr co，那我后面有放一些recommending的reading，大家有兴趣的话也可以参考一下，那第二个就是说呢。



![](img/723e9c79ea07c23eb14c99280ea0a075_14.png)

我有帮这场这个top开了一个slider。

![](img/723e9c79ea07c23eb14c99280ea0a075_16.png)

就是右下角的这个pin码，大家可以输入进去啊。

![](img/723e9c79ea07c23eb14c99280ea0a075_18.png)

就是你打这个slider，打com应该就可以找得到。

![](img/723e9c79ea07c23eb14c99280ea0a075_20.png)

然后这个slider这个平台呢，是可以让大家问问题的平台，那它也是匿名的。

![](img/723e9c79ea07c23eb14c99280ea0a075_22.png)

所以大家有问题的话，就可以上slider问一下诶。

![](img/723e9c79ea07c23eb14c99280ea0a075_24.png)

我把这个稍微再放大一点，我看大家扫的好像有点辛苦。

![](img/723e9c79ea07c23eb14c99280ea0a075_26.png)

那SLIDO这个平台呢，我课后的话也会把这些问题一一的回复。

![](img/723e9c79ea07c23eb14c99280ea0a075_28.png)

所以每一个问题我都会回，然后大家如果有问题的话。

![](img/723e9c79ea07c23eb14c99280ea0a075_30.png)

就可以hold在上面这样，然后这个slider的课的room应该是开一个礼拜。

![](img/723e9c79ea07c23eb14c99280ea0a075_32.png)

所以如果是在看录影的同学。

![](img/723e9c79ea07c23eb14c99280ea0a075_34.png)

一个礼拜之内应该也都可以来问问题，这样。

![](img/723e9c79ea07c23eb14c99280ea0a075_36.png)

好那哎我就开始今天的talk。

![](img/723e9c79ea07c23eb14c99280ea0a075_38.png)

那呃这个top的topic，就是要怎么样利用多张GPU训练大型语言模型，就我会从零开始介绍几个工具，Deep speed such，Attention，Lego kernel。



![](img/723e9c79ea07c23eb14c99280ea0a075_40.png)

还有quantization这四个工具，这样好。

![](img/723e9c79ea07c23eb14c99280ea0a075_42.png)

那呃这边是诶，我稍微再放大一些。

![](img/723e9c79ea07c23eb14c99280ea0a075_44.png)

这是overview，就是说我们要怎么样训练大语言模型呢。

![](img/723e9c79ea07c23eb14c99280ea0a075_46.png)

如果说用大家在机器学习的课学到的。

![](img/723e9c79ea07c23eb14c99280ea0a075_48.png)

训练neural network的方法，你用PYTORCH的扣写的话，大概会像是下面这个简单的样子。

![](img/723e9c79ea07c23eb14c99280ea0a075_50.png)

等于说你单纯只靠PYTORCH，其实就可以训练一个neural network这样。

![](img/723e9c79ea07c23eb14c99280ea0a075_52.png)

那但是呢呃在大圆模型的情况下，这样通常是没有办法跑了，因为大圆模型实在是太大了，那这么大的一个模型，它甚至有时候一张GPU都会塞不下，所以呢除了PYTORCH以外，你可能还会需要一些其他的工具。



![](img/723e9c79ea07c23eb14c99280ea0a075_54.png)

那下面这边就是我们今天会介绍的三个工具。

![](img/723e9c79ea07c23eb14c99280ea0a075_56.png)

那第一个叫做deep speed，那这个工具是由MICROSOFT开发的一套package，那它的用途就是说如果说你今天有多张的GPU，那你想要把你想要好好的利用多张GPU，达到平行运算的话。

那你可能会就会需要DSB，那第二个是如果说你今天的输入非常的长，像我们一般，如果你用的是recently的model，那它可能的context就会到32K或，甚至128K这么长的contact。

那在这个情况下，你可能就会需要like a kernel或是flash attention，这两个工具，那在最后一个就是如果说呃，像是大家在跑作业的时候，可能用COLAB上面的GPU，想要跑大圆模型。

这个时候就要用到QUALIZATION的技术，那今天这个talk呢，大概就是会从这三个面向去介绍说，如果你要训练大语言模型，或是你要influence大语言模型的话，你会需要哪些工具好。



![](img/723e9c79ea07c23eb14c99280ea0a075_58.png)

那在讲工具以前呢。

![](img/723e9c79ea07c23eb14c99280ea0a075_60.png)

先大概讲一下你在训练模型的时候呃。

![](img/723e9c79ea07c23eb14c99280ea0a075_62.png)

为什么会这么困难，那刚刚只是一个overview，现在要亲自带大家来算一下，说为什么呃大圆模型究竟多大，然后你的GPU到底多小才会放不进去。

这样那首先这个是一个很简单的forward跟background path，如果说你的大圆模型是中间这个白色的方格。



![](img/723e9c79ea07c23eb14c99280ea0a075_64.png)

那你的输入可能就会是一个token的sequence，譬如说the dog trace its，那带原模型的输出就会是一个token的distribution，在这边，那这个代理模型可能觉得。

后面大概率会接的spell，那也有可能是shadow ball之类的，然后在训练资料里面的label就会告诉他说，正确答案应该是tell，所以大圆模型应该要增加这个tale输出的几率。

所以我们就会用cross attention，哎不哎，cross entropy的loss去算出一个loss，那这个loss呢会再经由back propagation，从输出一路往前推到输入那边。

再进行一次模型权重的呃，造访之后呢，每一个每一个权重它都会得到一个gradient，那这个gradient再去经由optimizer，去更新NM的位置。

这样那这边其实只是把一般的neural network模型，换成large，那个是model a。

![](img/723e9c79ea07c23eb14c99280ea0a075_66.png)

没有没有任何的区别，这样那这样会有的问题。

![](img/723e9c79ea07c23eb14c99280ea0a075_68.png)

就是说，主要是因为这一格LM的位置实在是太大了。

![](img/723e9c79ea07c23eb14c99280ea0a075_70.png)

造成训练上的困难，那究竟有多大呢，可以大家可以看到下面这张图。

![](img/723e9c79ea07c23eb14c99280ea0a075_72.png)

那这张图我们假设的是，你今天要训练一个8B的模型，那8B的模型会需要多少资源呢，呃如果说因为我们知道LN的位置。



![](img/723e9c79ea07c23eb14c99280ea0a075_74.png)

是以浮点数储存的，那浮点数一个浮点数就是32个bit子。

![](img/723e9c79ea07c23eb14c99280ea0a075_76.png)

所以32再乘以8B就是810的九次方。

![](img/723e9c79ea07c23eb14c99280ea0a075_78.png)

大概就是32G这个大小。

![](img/723e9c79ea07c23eb14c99280ea0a075_80.png)

所以光是你要把模型全部都存到GPU里面，它就会占32G。

![](img/723e9c79ea07c23eb14c99280ea0a075_82.png)

那30G以外还会需要什么东西呢，我们这个可以请大家先看到这个绿色的箭头，这绿色的箭头指的是说这个LM的位置，在计算的时候，通常我们不会用32bits去计算，而是用16bits，那这有两个原因。

一个原因是说，16bits其实就是32bits的近似，所以他们算出来的结果不一定会差很多，至少在呃模型训练上来讲是可以接受的误差，所以基本上大家都会选择，把模型先转成FP16的格式。

那它的储存空间也会砍一半也比较好，就是会训练的比较快，那第二个原因就是说，因为像大部分的GPU，尤其是NVIDIA的GPU，其实对于FP16的这个格式，是有做特别的加速。

所以你算FP16会比散人还要快不少好，那这就是第二个component，所以其实在训练的时候，模型会有存，会储存两份LM的位置，一份是他最最原始精准呃，精确度最高的位置。

另外一个是专门在GPU上跑的时候。

![](img/723e9c79ea07c23eb14c99280ea0a075_84.png)

所训练的位置好，那现在讲完了这两个我们有LM的位置之后呢，就会有个input，那至于这个input的大小是多少，其实有时候你input有长有短，所以我们这边先等一下再讨论input的长度好。

那你有input之后呢，你会跑that propagation，that propagation会算出一个GRADI，那这个gradient，其实就是和LM的位置是一样大的，因为一个位置就会有一个呃。

它的gradient更新的方向，所以这gradient跟位置会是一样大的，那这个位置呃，这个gradient会被送到右上角的这个。



![](img/723e9c79ea07c23eb14c99280ea0a075_86.png)

ADAM的optimize去做运算，那这个optimize运算的时候呢，它其实大小是会是跟LM的位置是一样，因为ADAM这个optimized的精神，就是说我们希望每一个LM模型里面的权重。

都有一个他自己的learning rate，所以一个权重就会有一个FP32的momentum，还有一个P32的variance去模拟，一个就是呃指数decay的一个learning rate。

所以说可以看到这两格都是32GB的，原，是，因为每一个位置都会有一个momentum，跟variance去更新，所以这个item item optimizer的用途。

就是说呢它会把以gradient为输入，然后再加上它目前这个权重的momentum跟variance，去更新最原本32GB的这个LM的位置，这样好，那这边基本上就是扣除了input以外。

我们会需要的所有所有训练的时候会用到的，component好，那我这边简单的帮大家加了一下。

![](img/723e9c79ea07c23eb14c99280ea0a075_88.png)

全部加起来大概会是128GB，所以这个数字其实是超过了，现在几乎所有GPU的储存的大小，那也是为什么我前面在那个overview的时候讲说，如果你直接用PYTORCH跑是没办法训练。

也是因为这些component在一般的呃，内神经网络来说，可能都很小，只是你放到LM里面。

![](img/723e9c79ea07c23eb14c99280ea0a075_90.png)

它就会变得非常的大，这样子好。

![](img/723e9c79ea07c23eb14c99280ea0a075_92.png)

那其实讲了这些还没讲完，因为这个input其实在训练的时候呃，才是占最多的储存空间的部分。

![](img/723e9c79ea07c23eb14c99280ea0a075_94.png)

那所以第三个我们就来讲input。

![](img/723e9c79ea07c23eb14c99280ea0a075_96.png)

这边的input，我们讨论的是activation，那activation，其实在之前机器学习的课程的时候呢，它其实就是叫做呃每个一个模型，一个模型的某一层。

对于这个input所产生出来的反应就叫activation，所以呢每一层的output都会有一个ACTIVATIONS好，那这个ACTIVATIONS会为什么会有这个东西。

就是因为我们在做back propagation的时候，我们会用那个片尾分从后面一路上回前面，那这个时候就会需要每一个每一层的output，还有loss去得到它的gradient，这样。

那这边简单的举两个例子。

![](img/723e9c79ea07c23eb14c99280ea0a075_98.png)

就是说假设我们有一个8B的模型，那这个8B的模型呢它的输入可能有两种，第一种就是正常的输入很短，可能最多256个token，那如果大家问个简单的问题，比如说今天天气怎么样，加上season pro。

可能就只有256个token，就是输入短的时候，那输入长的时候呢，可能会到16K或甚至呃google的GEMINIK到200K，那就是它可能会有recently的data，或者是一些多模态的输入的时候。

它的输入就可能到很长很长，那这么长的输入会有什么问题呢，它的问题就是说，因为我们知道模型的每一层都会存ACTIVATIONS。



![](img/723e9c79ea07c23eb14c99280ea0a075_100.png)

所以右边这个方格表示的就是activation，所以可以看到8B的模型会有32层，那activation就是每一层都有一个，就会有32层好，那这个activation最占空间的其实是attention。

因为我们知道attention它是呃，两个sequence之间所算出来的一个方形的矩阵，所以它在空间复杂度上面，会从原本的ON变成N平方，那N就是你输入的sequence的长度。

所以以一个8B的模型来讲呃，每一层的ACTIVATIONS里面的attention就占了40G。

![](img/723e9c79ea07c23eb14c99280ea0a075_102.png)

那你简单的乘以32，其实就达到一个很不可思议大的一个大小。

![](img/723e9c79ea07c23eb14c99280ea0a075_104.png)

那这个大小呢，其实就是你在训练很长很长的输入的时候。

![](img/723e9c79ea07c23eb14c99280ea0a075_106.png)

会碰到的问题，就是这个activation实在是太大了，这样好，那其实嗯一个很直观的想法就是。

![](img/723e9c79ea07c23eb14c99280ea0a075_108.png)

其实你并不需要在训练的时候，把这些ACTIVATIONS都存下来。

![](img/723e9c79ea07c23eb14c99280ea0a075_110.png)

那下面就跟大家介绍一个名词，就是这个activation recomputation。

![](img/723e9c79ea07c23eb14c99280ea0a075_112.png)

那其实它也叫做gradient checkpointing，他的意思就是说你在forward pass的时候，你不要把所有的activation都存下来，你只存一些重要的就好。

那你在by word需要用到的时候，再重新算一次就可以了，所以其实有用到这个技巧的话呢，呃这个package应该说呃这个十重的演算法，就是它会只存必要的东西，因为你by word是从后面往前算。

那你可以在需要的时候，再一层一层的去算出它的activation就好。

![](img/723e9c79ea07c23eb14c99280ea0a075_114.png)

这样你就不需要存到这个1。35TV，这个这么夸张的数值。

![](img/723e9c79ea07c23eb14c99280ea0a075_116.png)

那当然这个RECOMRECOMPUTE的过程也会增加一些，Computation overhead，所以你在训练的时候会稍微慢个一点点，这样所以如果大家在训练。

比如说呃transformer的training的ARGUARGUMENT，里面可能会看到一个叫做gradient checkpointing。



![](img/723e9c79ea07c23eb14c99280ea0a075_118.png)

它其实就是在节省ACTIVATIONS的计算训练的时候。

![](img/723e9c79ea07c23eb14c99280ea0a075_120.png)

所需要的储存空间好，那还有最后一个小细节是batch size的部分。

![](img/723e9c79ea07c23eb14c99280ea0a075_122.png)

那我们都知道呃，大语言模型或甚至是一般的neural network，它所依靠的就是你的输入，会用会算出一个gradient，那用这个gradient来更新你的呃神经网络。

那这个gradient呢它不能是随便的gradient，它必须要是呃非常稳定的告诉模型说，它的权重应该往哪边降低，所以如果这个batch size不够大的话。

会造成说它的gradient会非常的bias，所以基本上在训练的时候呃，通常一个batch的大小都要有4~60个million，这么多个token，那举例来说，像deep sick的V3。

就是他在训练的时候的某一个阶段，他在训练32K的context的时候，他的batch size是1920，那等于说他输入了1920个32K的context，之后才会做一次呃，optimizer的更新。

那192032K，大概就是61M的token这样，所以还有一个challenge是说你会需要这个by size，会需要很大很大才能够符合你这个呃，才能对你的训练有帮助。



![](img/723e9c79ea07c23eb14c99280ea0a075_124.png)

所以我们不可能再一次的训练，就把1920个32K的context都丢进去。

![](img/723e9c79ea07c23eb14c99280ea0a075_126.png)

所以这边有另外一个名词，叫做gradient accumulation。

![](img/723e9c79ea07c23eb14c99280ea0a075_128.png)

那这个gradient accumulation，就是说我们把原本的global size，就是上面这个1920给切成若干个mini batch，那这个mean batch就是可以。

GPU可以装得下一次forward background的数字，等于说如果说这个mini bad size是16的话，那我们一次forward就是把16个输入给丢进去，算出一个gradient。

那这gradient我们先不拿去更新模型的参数，而是先保留，那保留多久呢，保留120个forward by word之后，再一起拿去更新最后的global的模型。



![](img/723e9c79ea07c23eb14c99280ea0a075_130.png)

那这就是gradient accumulation，它可以让你在你没有办BATCHESS开那么大的时候。



![](img/723e9c79ea07c23eb14c99280ea0a075_132.png)

那这是一个小细节。

![](img/723e9c79ea07c23eb14c99280ea0a075_134.png)

好讲到这边，其实大圆模型训练的时候会遇到的困难。

![](img/723e9c79ea07c23eb14c99280ea0a075_136.png)

都讲完了，所以大家可以看一下这个图表。

![](img/723e9c79ea07c23eb14c99280ea0a075_138.png)

那这个图表就是他讲的是，你训练的时候会需要多少memory，那这三张图呢分别是8B70B，405B的模型好，那下面横轴指的是你输入的长度，那纵轴就是你所需要的GPU的memory。

那大家可以看到说底下的这个诶紫色。

![](img/723e9c79ea07c23eb14c99280ea0a075_140.png)

红色绿色。

![](img/723e9c79ea07c23eb14c99280ea0a075_142.png)

这部分在所有context长度来说都是一样的。

![](img/723e9c79ea07c23eb14c99280ea0a075_144.png)

因为它就是你的parameter的大小，然后你的gradient的大小，你的optimize的大小，这样然后会随着嗯你的context变长，而指数增长的呢就是ACTIVATIONS。

可以看到它基本上就是指数型的成长，所以当你要训练8B的模型的时候，你需要克服的就是你需要的memory这么多，那究竟你要怎么样用呃，那么小的一个GPU去训练呢，这就是啊我们今天要讲的问题。



![](img/723e9c79ea07c23eb14c99280ea0a075_146.png)

这样，那这个talk我总共会分成三个阶段。

![](img/723e9c79ea07c23eb14c99280ea0a075_148.png)

第一个阶段我会先讲呃，就是这个橘色的activation以外的部分，要怎么样优化，所以part one讲的是你要怎么优化parameter gradient，还有optimizer的states。

这是part one，part two要讲的就是橘色的这个ACTIVATIONS好，然后party才会讲QUALIZATION，这样那QUALIZATION基本上只是for inference。

所以training的部分会需要用到的package，会在part one和part two的时候就讲完。



![](img/723e9c79ea07c23eb14c99280ea0a075_150.png)

哦那我们就先来讲第一个就是我们究竟要呃。

![](img/723e9c79ea07c23eb14c99280ea0a075_152.png)

我们有这么多的parameter gradient。

![](img/723e9c79ea07c23eb14c99280ea0a075_154.png)

还有optimizer要怎么样装到GPU里面呢。

![](img/723e9c79ea07c23eb14c99280ea0a075_156.png)

那这边讲的component就是前面这边诶，前面这边讲了。

![](img/723e9c79ea07c23eb14c99280ea0a075_158.png)

这是12345这五个component，因为input是算是activation要处理的，就我们part万千不考虑，那这五个component加起来的这个128GB的话。



![](img/723e9c79ea07c23eb14c99280ea0a075_160.png)

一个GPU基本上是绝对装不下的，那既然一个GPU装不下，我们其实就可以用多个GPU来凑。

![](img/723e9c79ea07c23eb14c99280ea0a075_162.png)

所以意思就是说呢，如果说我们今天有四个GPU，那刚刚所提到的这个东西，其实你就可以把它做，把它切成小片小片的装到GPU里面就可以了，就是说如果说你一个GPU只有呃三十三十二G。



![](img/723e9c79ea07c23eb14c99280ea0a075_164.png)

那你其实可以把这个128G切成四份，就装得下了。

![](img/723e9c79ea07c23eb14c99280ea0a075_166.png)

这样那这边的component就会对应到，刚刚左边part one的图里面的component，这样好，那究竟怎么样切才会是一个好的切法，因为其实嗯他这个还会有很多个需要考量的。



![](img/723e9c79ea07c23eb14c99280ea0a075_168.png)

譬如说你的GPU是GPU有几张，那你的模型训练的过程，所以呃你在训练的时候，这些东西其实是需要仔细考虑，那MICROSOFT就帮大家写好了一个package。



![](img/723e9c79ea07c23eb14c99280ea0a075_170.png)

叫做deep speed，那这个deep spin呢它主要就是zero的这个演算法，那zero是zero redundancy optimizer的意思。



![](img/723e9c79ea07c23eb14c99280ea0a075_172.png)

那这个zero呢它有它的演算法。

![](img/723e9c79ea07c23eb14c99280ea0a075_174.png)

一共有三个level，level越高，省下来的记忆体就越多。

![](img/723e9c79ea07c23eb14c99280ea0a075_176.png)

那zero one指的是说我们上面看到的这个图。

![](img/723e9c79ea07c23eb14c99280ea0a075_178.png)

这个GPU里面它占最多空间的，其实是这个optimizer，所以第一个就先找他开刀，你就把它你有几个GPU，你就把它切成几片。



![](img/723e9c79ea07c23eb14c99280ea0a075_180.png)

所以可以看到蓝色这一部分，我们把一个optimizer切成四片，那一个GPU里面装一点，所以这样就有的GPU就会装得下，这样子好，那等于说啊，你的GPU，等于说你可能会需要用到第一个optimizer。

的时候呢，呃你就把他的资料传到第二个，第三个第四个GPU去，这样其实就是在GPU上面的意思。

![](img/723e9c79ea07c23eb14c99280ea0a075_182.png)

只是它可以看到，大家可以看到的话，就是这边多了一个蓝色的箭头，那这个箭头指的就是，你把一旦把东西给切小了之后呢，它就会多出一些transfer的overhead。



![](img/723e9c79ea07c23eb14c99280ea0a075_184.png)

不过大家也不用太担心这个transfer的OVERLA，呃的overhead在GPU跟GPU之间是非常快的。



![](img/723e9c79ea07c23eb14c99280ea0a075_186.png)

这样好，那zero two的话也其实也很好理解，就是你最大块的切完了，就是找第二大块的去切，那第二大的是什么呢，就是gradient跟LM的位置，就是绿色的这个部分。



![](img/723e9c79ea07c23eb14c99280ea0a075_188.png)

你也把它切小了，那可以看到一个QQ里面要装的东西，就基本上少了很多很多，那你就更有可能把它全部都塞到一个，小的GPU里面，那也可以看到说这个箭头从呃蓝色变橘色，代表说它需要的传输的东西又更多了。

因为有些东西你GPU one在算的时候，他在GPU4里面，你就要把它传输过来。

![](img/723e9c79ea07c23eb14c99280ea0a075_190.png)

你才能计算这样，所以会多一些传输的overhead。

![](img/723e9c79ea07c23eb14c99280ea0a075_192.png)

然后zero3就是全开的状态，如果你把zero这个演算法每一个level都开了的话。

![](img/723e9c79ea07c23eb14c99280ea0a075_194.png)

他就是把最后一个LM的位置也切开，那基本上这个就是你，它你可你把LM的training可以切到最小，大概就是zero3这个状态好，那刚刚有提到这个transfer的部分，在GPU跟GPU之间是非常快的。



![](img/723e9c79ea07c23eb14c99280ea0a075_196.png)

究竟有多快呢，呃他是如果说你用的是NVIDIA的GPU。

![](img/723e9c79ea07c23eb14c99280ea0a075_198.png)

他用的是一个nv link的技术，那他基本上每秒可以传900GB。

![](img/723e9c79ea07c23eb14c99280ea0a075_200.png)

这个速度是非常快的，这样然后不只是单纯的快。

![](img/723e9c79ea07c23eb14c99280ea0a075_202.png)

在deep speed这个package里面，MICROSOFT他们也有针对传输这件这个东西，做一些schedule，所以基本上他会尽量呃能先传好就先传好，不会delay到training这样好。



![](img/723e9c79ea07c23eb14c99280ea0a075_204.png)

那其实嗯。

![](img/723e9c79ea07c23eb14c99280ea0a075_206.png)

你这样子把LM训练的时候需要用到的memory都切。

![](img/723e9c79ea07c23eb14c99280ea0a075_208.png)

一切之后，大家现在可以看下面这个图表来看，说究竟我们节省了多少空间。

![](img/723e9c79ea07c23eb14c99280ea0a075_210.png)

那上面这个这个图呢一样是一个8B的模型，那他这边DP等于八，指的是说他一共有八张卡，那就其实就是上面的图，只是每一个component把它切成四片，改成切成八片这样子，那最左边这个是切之前。

如果你没有开zero的话，它其实这个红色的虚线是80GB，那他这边假设的是，如果你有一个呃H100，那它是80GB的话，你8B的模型就训练不了，但如果你开了zero one的话。



![](img/723e9c79ea07c23eb14c99280ea0a075_212.png)

可以看到就是橘色的部分没有变，但是紫色啊，红色绿色这边呃，呃应该说红色跟绿色是没有变的，因为zero one只有切optimizer，所以是紫色的部分变成1/8，然后如果你连GRA点都切的话。

就是这个红色再变1/8，这样所以就是八分之一八分之一，最后你可以知道说呃，80GB的H100里面，其实可以训练到16K长度的8B的模型。



![](img/723e9c79ea07c23eb14c99280ea0a075_214.png)

这样如果你用的是zero3，这个也算法的话好那刚刚有提到说。

![](img/723e9c79ea07c23eb14c99280ea0a075_216.png)

因为你把模型切成小片，所以他要用到的这个东西，有可能在那个当下并不在这个GPU里面，所以它会有一些transfer的overhead。



![](img/723e9c79ea07c23eb14c99280ea0a075_218.png)

那这个overhead的速度呢，基本上嗯它会跟很多东西有关系。

![](img/723e9c79ea07c23eb14c99280ea0a075_220.png)

譬如说如呃你的GPU跟GPU之间间隔的bandwidth，或是你的model size，或是一些硬体的设计有关，但基本上不会到很夸张的慢，就说不会慢到十倍或以上。



![](img/723e9c79ea07c23eb14c99280ea0a075_222.png)

这样他就是一个大家都可以接受的，一个train的速度，而且基本上你有用的zero这个演算法的话呢。

![](img/723e9c79ea07c23eb14c99280ea0a075_224.png)

它就是让你从不能训练便可以训练，所以大家基本上都是会用zero这个方法去训练的，这样好。

![](img/723e9c79ea07c23eb14c99280ea0a075_226.png)

那讲完了，讲到目前，我们其实介绍了DEPC的一个部分。

![](img/723e9c79ea07c23eb14c99280ea0a075_228.png)

就是zero的这个演算法。

![](img/723e9c79ea07c23eb14c99280ea0a075_230.png)

那还有一个就是如果说嗯，你连这样子切都还装不下的话。

![](img/723e9c79ea07c23eb14c99280ea0a075_232.png)

就你的GPU真的很小颗的情况下，其实你还可以用一个东西叫做CPU的ram来凑，那大家可以看到说这个图，其实CPU的ram相较于现在GPU的ram，都是大概是十倍大的这个量级。

所以说如果你今天GPU真的很小颗，或是说你真的想要训练很大的模型，你还是可以把它一部分的呃，训练要用到的component搬到CPU去存着。



![](img/723e9c79ea07c23eb14c99280ea0a075_234.png)

要用的时候再拿出来好。

![](img/723e9c79ea07c23eb14c99280ea0a075_236.png)

那所以说刚刚看到的这个图啊，它DEPC提供了两种方法。

![](img/723e9c79ea07c23eb14c99280ea0a075_238.png)

一种叫做optimizer的OFFLO，那简单来说就是把跟optimizer有关的东西，搬到CPU上面，所以留在GPU上面就只有large linux model的权重而已。

剩下的所有东西都放在CPU上面，要用到的时候再来搬。

![](img/723e9c79ea07c23eb14c99280ea0a075_240.png)

那第二个就是你甚至可以连optimizer都放上去，那基本上你的GPU就可以很小很小，只要你CPU的ram够大的话呢。



![](img/723e9c79ea07c23eb14c99280ea0a075_242.png)

你就可以呃训练这个模型，但这个offload方法有一个缺点。

![](img/723e9c79ea07c23eb14c99280ea0a075_244.png)

所以导致它其实不太好用的，原因是因为GPU跟CPU之间的传输速度是很慢的，就比刚刚的900GB per second还要再慢一个量级，所以你的训练会变得非常非常的慢。



![](img/723e9c79ea07c23eb14c99280ea0a075_246.png)

那究竟有多慢呢，我这边有稍微跑了一个小实验。

![](img/723e9c79ea07c23eb14c99280ea0a075_248.png)

那这个实验就是呃如果大家在实验室啊，或是一些课可能会用到国网中心的资源，那国网中心上面呃的主要的CPU呃，主要的GPU是D100，那最近有H100可以使用，但大部分之前做实验都还是做在V100上面。

所以如果大家有用过网中心的资源的话，可以参考这上面的数字好。

![](img/723e9c79ea07c23eb14c99280ea0a075_250.png)

那呃详细的script我放在这个rapport里面。

![](img/723e9c79ea07c23eb14c99280ea0a075_252.png)

所以大家如果想要自己试试看reproduce的话，可以参考这个，那呃首先我做了两组实验。

![](img/723e9c79ea07c23eb14c99280ea0a075_254.png)

一组是有offload，就是刚刚说的会搬到CPU的rain上面，会跑的很慢的，那一组第二个是没有offload，那有of flow的话呢，就是四张GPU的情况下，就四张V100，那V100一张是32G。

所以四张加起来其实就是128G，刚刚算的那个呃8B的模型，其实是刚好勉强可以装得下的量的那一种好，那不过要注意的是，我这边其实input开的很小啊，就是bad size91。

然后呃长度最多只有512这样，那这边这个表格呢是deep speed，它有提供的一个工具，就是如果你今天有一个环境，然后你有一个模型想要训练，它，可以帮你算出你需要多少memory。

那有of flow的话，可以看到我这边offload就只有optimizer，等于说我把optimizer给放到CPU上面。



![](img/723e9c79ea07c23eb14c99280ea0a075_256.png)

就是上面的这个第一个case，我把模型的parameter留在上面，然后其他的optimizer有关的东西放去CPU。



![](img/723e9c79ea07c23eb14c99280ea0a075_258.png)

那这样的话你的per GPU要的memory，其实只有5。7GB，然后但是你的CPU要够大，等于说你一个CPU里面要有179GB，这样好，这是他预估的数字，所以跟实际的数字其实是会差非常多的。

那我实际上测出来呢，它一个GPU大概会占15GB的记忆体，然后一个step大概会跑74秒，那74秒这个数字其实是很夸张的慢，因为这个batch这个诶输入是很短的。

不过它一个一个forward background，还有update，就要跑74秒，那这个意思就是说因为你把东西搬到CPU上面，然后国网中心它的硬体其实比较针对GPU做加速。

它的GPU跟CPU之间传输是比较慢一点，所以才会是74秒这个速度。

![](img/723e9c79ea07c23eb14c99280ea0a075_260.png)

那这个速度基本上呃就是train的很夸张的慢，这样那同样的东西同样的扣。

![](img/723e9c79ea07c23eb14c99280ea0a075_262.png)

如果我有八张GPU的话，故事就会不太一样，就是他per GPU只要18。7G就装得下，所以32G的V100其实是装得下的，你就不用用到任何offload技巧，它跑起来就会顺很多。

那它一个step就会变7。3秒，这样，那它的VR虽然说他预估的是18。7，但实际上用到的还会考量一些，比如说PYTORCH，它自己会有一些呃，它需要保留的一些记忆体，以及你输入的长度也会有影响。

所以最后他是在24~32之间跑，它会有点上上下下，上上下下的话，就是因为我这边是有开zero的，所以它传来传去的时候，有些有时候GPU会某一张会记忆体会比较多，但总之它不会OOM，然后就是训练的时候。



![](img/723e9c79ea07c23eb14c99280ea0a075_264.png)

会比上面这个setting还要快十倍这样，所以这边有大概有两个小结论给大家。

![](img/723e9c79ea07c23eb14c99280ea0a075_266.png)

第一个小结论就是说，如果你想要训练的模型是8B的模型，你其实是可以fully fune。

![](img/723e9c79ea07c23eb14c99280ea0a075_268.png)

它的在国网中心上面，用八张V100是可以做到的，那速度大概是7。3秒这一个level，那第二个小结论就是能不要用of flow。



![](img/723e9c79ea07c23eb14c99280ea0a075_270.png)

就不要用of flow，因为它真的很慢，那为什么他们会开发这个东西，纯粹就是他们那个时候想做一个很无聊的实验，就是要怎么样用呃，16张V100去训练175B的模型，这样，所以他们为了做这个东西。

才开发of flow这个东西，但实际上在做实验的时候是不好用的。

![](img/723e9c79ea07c23eb14c99280ea0a075_272.png)

这样好。

![](img/723e9c79ea07c23eb14c99280ea0a075_274.png)

那这个就是part one，part one的部分，帮大家做个总结，就是呃part one我们介绍的是deep speed。



![](img/723e9c79ea07c23eb14c99280ea0a075_276.png)

那diss speed这个东西对于这一张图来说。

![](img/723e9c79ea07c23eb14c99280ea0a075_278.png)

它改进的是橘色以外的地方，让它可以压到一张GPU状态下的程度。

![](img/723e9c79ea07c23eb14c99280ea0a075_280.png)

这个是deep speed做的事情，那刚刚所展示的case其实是呃8B的模型。

![](img/723e9c79ea07c23eb14c99280ea0a075_282.png)

所以对于大公司来讲，他们有的可能不是八张卡，是80张卡，那他们就可以训练十倍大的模型。

![](img/723e9c79ea07c23eb14c99280ea0a075_284.png)

只是把模型切成80份，这样子其实是可以装的下来。

![](img/723e9c79ea07c23eb14c99280ea0a075_286.png)

好那part two要介绍的是ACTIVATIONS。

![](img/723e9c79ea07c23eb14c99280ea0a075_288.png)

那我们可以知道这个这个地方要解决的问题，是说，因为attention这个考呃，这个算法它会需要的记忆体空间是N平方，那这实际上是一个非常呃非常大的一个数字，尤其是在你的输入很长的时候。

所以part two要介绍的就是要怎么样解决。

![](img/723e9c79ea07c23eb14c99280ea0a075_290.png)

activation的问题，好那在介绍以前呢。

![](img/723e9c79ea07c23eb14c99280ea0a075_292.png)

我们先讲一下这个问题的话会怎么解决，因为我们想要改善的是attention这个operation，计算的效率，那attention这个东西会在GPU上面跑。

所以这个问题解决方法就是我们重写attention时，做的co让它跑快一点，那要怎么样重写呢，呃这边先跟大家介绍kernel这个概念，kernel其实就是跑在GPU上面的function的意思。

所以呃如果你要写一个可以跑在GPU上面的function，你可能会有一些选择，第一个是PYTORCH，Pytorch，它其实就可以把tensor或是一些常用的operation，放到QQ上面跑。

是可以比CPU跑还要快很多的，那第二个呢就是我先介绍一下，这这边的这个排序，就是上面的指的是high level的language，它比较方便，但它跑的就相对没有那么快。

而且呃它没有办法让你很精细的可以控制配置，你的记忆体以及一些数算的呃。

![](img/723e9c79ea07c23eb14c99280ea0a075_294.png)

算数的顺序，那越往下是越low level的language，它跑起来会比较快，但然后它也可以让你控制所有呃，所有运算过程中的detail，但它相对来讲它的learning curve就比较难一点。



![](img/723e9c79ea07c23eb14c99280ea0a075_296.png)

所以好，那讲回来这边的第二个torch compile，它是PYTORCH的一个function的decorator，那这个decorator就是它你把它加在你的。

譬如说加载模型的forward的function上面，那它就可以帮你，因为像是compile整个PYTORCH它计算的graph，这个graph因为你的function是确定的。

所以它会针对这个graph去做一些memory的呃，调度跟PREFETCH之类的，会让你的扣跑的快很多，那基本上这是一个无痛，就可以让你的扣跑的更快的方法，那再下来这个叫做TRITTON。

TRITTON是OpenAI他们开发的一个呃，在Python里面写的。

![](img/723e9c79ea07c23eb14c99280ea0a075_298.png)

你让你用Python可以写kernel function的一个界面。

![](img/723e9c79ea07c23eb14c99280ea0a075_300.png)

那它基本上就比PYTORCH还要灵活很多，那再来最下面最后一个是KDA，KDA就是NVIDIA他们开发的诶，C或C加加的套件，这样那基本上最low label的GPU的计算。



![](img/723e9c79ea07c23eb14c99280ea0a075_302.png)

那这边就是四种常用的，如果说你想要写kernel function，你可以用这边的这四种。

![](img/723e9c79ea07c23eb14c99280ea0a075_304.png)

可以考虑用这边的这四种语言。

![](img/723e9c79ea07c23eb14c99280ea0a075_306.png)

然后，讲完了kernel是什么东西之后，我们就可以在kernel function这个东西上面去实作。



![](img/723e9c79ea07c23eb14c99280ea0a075_308.png)

更快的kernel function，来让attention的这个呃运算算的更快。

![](img/723e9c79ea07c23eb14c99280ea0a075_310.png)

所以第一个就是flash attention，这个或许大家都有听过flash attention这个东西。



![](img/723e9c79ea07c23eb14c99280ea0a075_312.png)

那他实际上要做到的就是，他要加速attention的计算，让它不仅可以算得更快，还用更少的记忆体，不过当然呃要做到这件事情，当然不是没有成本，他的成本就是它有些东西会放到CPU的ram上面。

所以它是透过把大部分的东西放在CPU上面，要用的时候再把它fetch到GPU上面去算，才能让他劝的更快，又用的更少的memory好。



![](img/723e9c79ea07c23eb14c99280ea0a075_314.png)

那我会分两步来介绍slash attention，一个是它究竟为什么可以劝的更快，第二个是它为什么可以用比较少的记忆体，那第一个speed的话。



![](img/723e9c79ea07c23eb14c99280ea0a075_316.png)

在速度上面的部分，大家可以看到左边的这个图，这个图的来源就是attention is all you need这篇paper，那他讲的是scale到product attention这个运算。

那这个运算的输入呢，就是在下面这边的QKV的呃矩阵，然后输出就是一个attention的矩阵。

![](img/723e9c79ea07c23eb14c99280ea0a075_318.png)

这样可以看到说这个attention的运算啊，它会有矩阵乘法skill，然后soft max，然后再一次矩阵乘法，这样四五个复杂的呃function，所以flash attention这边做的事情。

就是呢他重新拾做一个kernel function，这个kernel function就叫做flash attention，那大家可以这样子理解。

那这个kernel function呢它的输入就是GOKV，输出就是attention，它把这四五个东西全部压成一个东西。



![](img/723e9c79ea07c23eb14c99280ea0a075_320.png)

那就可以让他算的比较快，因为他在这个方kernel方程里面做了很多的优化。

![](img/723e9c79ea07c23eb14c99280ea0a075_322.png)

这样子那记忆体的话。

![](img/723e9c79ea07c23eb14c99280ea0a075_324.png)

相比原本拿if的呃attention而言，它其实也可以降到接近线性的机体的空间好。

![](img/723e9c79ea07c23eb14c99280ea0a075_326.png)

![](img/723e9c79ea07c23eb14c99280ea0a075_327.png)

那这边再介绍一个小的名词，就是fuse kernel，那这个fth kernel，这张图的来源其实就是flash attention，他们的GITHUB，那这个的意思就是说。



![](img/723e9c79ea07c23eb14c99280ea0a075_329.png)

当你把这五个function全部压成一个function的时候，它实际上执行时间可以快很多。

![](img/723e9c79ea07c23eb14c99280ea0a075_331.png)

那这个图还有一个小的啊，inside就是其实我们可以想象说，attention算来就是矩阵的乘法，所以理论上矩阵乘法应该要花最多的时间，不过实际上因为矩阵乘法多数的GPU都有做加速。

所以实际上它不会真的算那么久，在attention里面算比较久的，居然是抓爆soft max boss mask之类的运算。



![](img/723e9c79ea07c23eb14c99280ea0a075_333.png)

所以fresh attention就是做了一个新的kernel，那来去做算这个attention。

![](img/723e9c79ea07c23eb14c99280ea0a075_335.png)

这样的事情就可以让它速度快很多。

![](img/723e9c79ea07c23eb14c99280ea0a075_337.png)

那第二个部分就是memory，那memory，其实这张图要表示的就是刚刚跟大家有提到的，把大部分的东西放在CPU这样的技巧，所以白色底的指的是呃在存在CPU上面，那黄色底的是放在GPU上面。

所以基本上Q，然后这个QKV还有A这些矩阵呢，在你的contact到非常长的时候，它会占很多的记忆体，所以筛选腾讯用的技巧，就是它在你要运算的时候，再把它搬到GPU上面去算就可以了。



![](img/723e9c79ea07c23eb14c99280ea0a075_339.png)

那这个图表示的就是这个意思而已。

![](img/723e9c79ea07c23eb14c99280ea0a075_341.png)

好那讲完了原理可以看一下它究竟有多快。

![](img/723e9c79ea07c23eb14c99280ea0a075_343.png)

那在performance上面，这个是跑在H100上面的实验，那嗯这是横轴呢，指的是你输入有多长，然后纵轴指的是你跑的多快，所以越越高就是越快的意思。



![](img/723e9c79ea07c23eb14c99280ea0a075_345.png)

那可以看到蓝色的这个standard attention，它会碰到的问题就是第一个他算的很慢，然后第二个就是他在16K或以上的时候，就会甚至H100的都会记忆体都会不够这样。

所以如果你用了TRITTON去实做的attention的话，它会快很多，只是这是绿色的这个部分，然后CUDNN就是KDA10做的，kernel的话是红色的这个。

那如果你用的是flash attention的二或三，就他们有很多版本，他们一直在呃更新，现在最新的应该是fresh attention呃，三这样，那三的话呢它就可以在额不仅是context。

很长的时候可以顺利的计算，它也可以比，甚至比你用KDA去实做哪一个attention。

![](img/723e9c79ea07c23eb14c99280ea0a075_347.png)

还要再快一点，这样好，那以上就是part two有关flash attention的介绍。

![](img/723e9c79ea07c23eb14c99280ea0a075_349.png)

好那fresh attention这个东西其实大家可以知道就好。

![](img/723e9c79ea07c23eb14c99280ea0a075_351.png)

因为现在呃有名的一些package，像是transformer之类的，他基本上原生都会支持flash attention。



![](img/723e9c79ea07c23eb14c99280ea0a075_353.png)

所以大家就知道说这个东西，如果他跟你说你没有安装的话。

![](img/723e9c79ea07c23eb14c99280ea0a075_355.png)

你就要去安装一下，因为会差很多，这样子好。

![](img/723e9c79ea07c23eb14c99280ea0a075_357.png)

那再来part two要讲就是like a kernel，那从这个名字大家可以看到说，它其实也是一种kernel，那kernel就是跑在GPU上面的function。

那所以lego kernel这个东西，就是它写了很多个kernel。

![](img/723e9c79ea07c23eb14c99280ea0a075_359.png)

那这个kernel他要做的事情，就是说呢他把呃LM在进行运算的时候，很常会用到一些function给包成一个fuse的kernel，所以呃然后他是用TRITTON去实做的。

等于说你把你的PYTORCH的code的，某些部分给抽掉，换成TRITTON的kernel的话，它就可以让你的LM算的更快以外。



![](img/723e9c79ea07c23eb14c99280ea0a075_361.png)

也可以用更少的MEMOR，那也值得一提的是。

![](img/723e9c79ea07c23eb14c99280ea0a075_363.png)

这个套件其实是一个台湾人写的，这样就是大家如果有听过他的演讲，就知道说他是在美国的linking工作，只是他某一个open source project，就说他想要做这个东西。

然后来做出来之后就受大家的喜欢，这样那我觉得最神奇的一个地方就是。

![](img/723e9c79ea07c23eb14c99280ea0a075_365.png)

它用法非常的简单，它用法就只是你更改你载入LM的方法，其实就可以了，那上面这个是大家通常用transformer的时候，会用这个auto model for cos ln的方法去载入你的模型。



![](img/723e9c79ea07c23eb14c99280ea0a075_367.png)

那如果你要用的是liger kernel的话，你就把这个东西换成auto lia kernel，for cos l m就可以了，那它基本上资源的模型还算蛮多的，就是开源的，基本上他都已经帮你。

把TRITTON的code给插入到PYTORCH里面，所以你就直接这样low的话。

![](img/723e9c79ea07c23eb14c99280ea0a075_369.png)

它就可以帮你把很多个运算都加速。

![](img/723e9c79ea07c23eb14c99280ea0a075_371.png)

他的performance的话，大家可以参考这张图，那这也是他们GITHUB截下来的，就是不管是速度啊，记忆体都可以用的比较少，怪还跑比较快，然后你也可以训练你之前所训练不了的。

比较长的context的模型。

![](img/723e9c79ea07c23eb14c99280ea0a075_373.png)

这样好，那以上其实就是part two的介绍。

![](img/723e9c79ea07c23eb14c99280ea0a075_375.png)

所以总结来说，如果说你今天碰到的问题是，你想要训练很长的context，譬如说你想要训练的是reasoning的模型，那或者是呃，你想要训练的是以影片的token当做输入的话。



![](img/723e9c79ea07c23eb14c99280ea0a075_377.png)

你可能就会碰到呃，呃activation占太多记忆体的问题，那解决这个问题呢。

![](img/723e9c79ea07c23eb14c99280ea0a075_379.png)

通常就是透过改写kernel去做到，然后常见的package一个是leg kernel。

![](img/723e9c79ea07c23eb14c99280ea0a075_381.png)

一个是flash attention，这样好。

![](img/723e9c79ea07c23eb14c99280ea0a075_383.png)

那讲到目前为止呢，power跟part two都讲完了。

![](img/723e9c79ea07c23eb14c99280ea0a075_385.png)

那可以知道说这一张图里面所有的元件。

![](img/723e9c79ea07c23eb14c99280ea0a075_387.png)

我们都有相对应的package可以去加速，所以下面诶下面这张图。

![](img/723e9c79ea07c23eb14c99280ea0a075_389.png)

基本上每一个东西我们都可以尽量把它往下压，就往下压，让它可以想办法塞到我们的GPU里面。

![](img/723e9c79ea07c23eb14c99280ea0a075_391.png)

所以虽然说LM他训练会需要很多的GPU的memory。

![](img/723e9c79ea07c23eb14c99280ea0a075_393.png)

不过也是有方法可以让它呃塞进去，并且做训练的。

![](img/723e9c79ea07c23eb14c99280ea0a075_395.png)

那这些工具也都是开源的，所以基本上大家用起来应该是都会非常的方便。

![](img/723e9c79ea07c23eb14c99280ea0a075_397.png)

这样好，那最后啊我还想花点时间。

![](img/723e9c79ea07c23eb14c99280ea0a075_399.png)

讲的是QUALIZATION这个东西，那刚刚的诶。

![](img/723e9c79ea07c23eb14c99280ea0a075_401.png)

刚刚的图里面有提到说，有些东西的浮点数是用32bit去存的。

![](img/723e9c79ea07c23eb14c99280ea0a075_403.png)

然后有些东西是用16倍去存的，所以实际上我们也可以不要用三二，也不要用16，甚至用更低一点的呃精度去存。



![](img/723e9c79ea07c23eb14c99280ea0a075_405.png)

那QUALIZATION这个东西，它其实做的就是一个lossy compression。

![](img/723e9c79ea07c23eb14c99280ea0a075_407.png)

也就是说这个蓝色的呃tensor，你可以把它压缩之后还原，它可能会变一个，它原本稍微不太一样，但还是很近似的一个tension，透过类似这样的技术，就可以让呃LM在底下的这个就是它储存。

大部分都可以用中间这根比较短的，压缩过后的天色去进行储存，需要计算的时候再把它还原回来就可以了。

![](img/723e9c79ea07c23eb14c99280ea0a075_409.png)

那它会有一个叫做QUALIZATION的演算法，那基本上呃会有很多种不一样的演算法，会让你可以把32bit的东西压成8bit，4bit或甚至有的可以近似到一倍这么小，那常见的演算法我把它列在这边。



![](img/723e9c79ea07c23eb14c99280ea0a075_411.png)

但实际上真的是五花八门，很多种演算法都可以做到QUALIZATION，还有DQUALIZATION。

![](img/723e9c79ea07c23eb14c99280ea0a075_413.png)

所以我就大概放了一些，那中间这个最大的就是大家在做诶，轰二一的COLLAB的时候，就是其实就是就是用gg ml family这一个呃。



![](img/723e9c79ea07c23eb14c99280ea0a075_415.png)

演算法的quantization的模型，所以大家用到的其实是这颗模型。

![](img/723e9c79ea07c23eb14c99280ea0a075_417.png)

就是METARA38B，这是default一个模型，那这个模型是什么意思呢，大家可以看这两个数字，就是一个是8B，假如说它是呃拉马38B，那Q8指的是说他把里面的每一个tensor。



![](img/723e9c79ea07c23eb14c99280ea0a075_419.png)

都压到八个bit里面去储存。

![](img/723e9c79ea07c23eb14c99280ea0a075_421.png)

那这样的话，其实模型整个载到记忆体面的时候就会很呃，它的空间就会比较小，那如果是八个币的话，你一个一个位词用的是八个bit h存，总共其实就只需要8G的记忆体，就可以载入一个8B的模型。

那所以COLAB上面的GPU免费的话是t four，t four就是15GB。

![](img/723e9c79ea07c23eb14c99280ea0a075_423.png)

就是呃很可以装得下，这样那你就还有7G左右的空间去存。

![](img/723e9c79ea07c23eb14c99280ea0a075_425.png)

你呃要用的输入。

![](img/723e9c79ea07c23eb14c99280ea0a075_427.png)

这样好，那最后做个总结，就是今天这个talk呢，主要就是告诉大家说有哪些实用的package，可以去解决，训练大语言模型的时候可能会碰到一些问题，那同时如果说你今天有大于一张的GPU，可以使用的话。

你要怎么最大化的利用好这么多的GPU。

![](img/723e9c79ea07c23eb14c99280ea0a075_429.png)

那最后还有一些recommend，就是推荐的reading的话，主要是这两个，我可以大概介绍一下，上面这个呢是哈根face他们写的一个非常详细的，有关于你要怎么样好好的用GPU cluster。



![](img/723e9c79ea07c23eb14c99280ea0a075_431.png)

去计算的呃，一个网站，然后这个网页呢非常的长，他他写的推荐的reading时间是两到三天，所以大家可以呵呵对，所以大家可以去看一下，然后如果你用手机看的话，可能就是它会载很久，你可能用电脑看对。

然后下面这个就是其实这算是一个坑啦，就是我在做呃DSB的实验的时候，他官方的文档我觉得很难看懂，因为他官方有一个它自己的API，我觉得很难用，所以如果大家想要用deep seed呃。

deep speed跑东西的话，比较推荐，就是你直接用transformer的trainer去载，然后你就看这个链接里面，它会告诉你怎么样把deep speed打开。

那实际上你要做的就是写一个JSON档就可以了，就你就可以把D4speed的功能全部都打开，这样子对好，那我大概就讲到这边对，谢谢大家，谢谢，好诶，那大家有问题想问的吗。



![](img/723e9c79ea07c23eb14c99280ea0a075_433.png)

我不知道怎么会在这里留言，我看一下啊，有啊有人留言吗，诶好那我就回答一下这个问题，好哦这个问题我觉得诶为什么会那么慢，是因为他们储存的GPU的时候，他们储存的可能是用高效的ram寄存的。

那CPU的话它的ram的label就会呃比较低一些，那等于说CPU它原生用的rain，是希望rain可以越大越好，那比较大的rain相对来讲，它的overhead就是传输的速度会比较慢。

那GPU的rain比较小，但是它传输速度还有呃，存取的速度会比较快，它基本上是一个跟你的ram的大小去做一个呃，就是你可能会需要TRADEOFF的一个原因，所以基本上是跟它硬体的设计有关啦。

这可能是硬体要解决的问题，让他可以在需要的时候再去拿，这样子对，希望有回答到你的问题，好诶大家还有问题要问的吗，好如果你们要打字的话，你可以直接举手画圈，对，来这边呃，就据我所知。

土耳其有一个DISTR，呃训练对应该跟刚刚介绍完什么好。

![](img/723e9c79ea07c23eb14c99280ea0a075_435.png)

呃，我刚刚介绍多个GPU的话，应该是part two的部分。

![](img/723e9c79ea07c23eb14c99280ea0a075_437.png)

那诶part one的部分，part one讲的是呃DSB这个套件，所以刚刚刚刚同学你讲的那个应该是额不冲突，就是它是两个可以一起用的东西，刚的那个torch的distribution。

这个东西用的是说呃，你今天他把同一份扣放到四个GPU上面，所以四个GPU上面都是跑一样的东西，只是资料不一样，这是一种平行化的方法，然后diss speed这边做的事情是它不止跑一样的co。

他还把一个模型切成四份，所以它多处理的是你模型在计算的时候，它会需要呃从别的GPU那边拿一些参数过来算，所以DSP处理的是多个GPU之间，你在切模型的时候需要考虑的问题。

但是torch的distribution，他做的事情是把一份co放到多个GPU上面，跑一模一样的东西，所以实际上你在跑deep speed的script的时候，你下的指令其实不是Python。

然后train点P，而是torch distribution，然后train点拍让它可以，因为torch distribution就是处理GPU之间的通讯，然后d speed只是额外处理切模型的部分。

所以它其实是两个嗯，可以一起搭在一起使用的东西，对这样有回答到你的问题吗，那我可以理解为就是distributed，相较之下比较不会出比较极品，对他处理的就只是GPU之间的呃通讯而已。

就是你资料要怎么样传过去，然后什么时候要传回来这样，所以说distribute其实还有个细节，就是distributed这个东西，它会有一个呃算算是master的node。

那这个method node就是负责把所有呃，GPU所计算的gradient全部整合在一起，更新模型，那个东西叫做呃MASTERNODE，所以呃具体来说就是他在管理method node。

还有worker node之类之间的存的呃，资料传输，这样子对对对，好诶，大家有问题要问吗，好诶如如果没有的话，其实大家也可以call在slide，然后我之后会一一回复，之后呢。

就可能放在NPU库一个大家会看得到的地方，这样好，那我们如果哎我其实想问帮大家问一个问题，那个那个d speed它有三个版本嘛，对不对，他一开始选择的是峰哥optimizer。

所以我觉得他这些选择应该你们cover一下，他这些选择the choice，因为他应该是先选择说如果分割optimizer，我需要的传输是最少的，然后接下来的分割需要的传输是越来越多了。

你可以cover一下哦。

![](img/723e9c79ea07c23eb14c99280ea0a075_439.png)

诶为什么会这样说，那好就是嗯他zero zero one。

![](img/723e9c79ea07c23eb14c99280ea0a075_441.png)

其实他他选择分割optimizer的原因是。

![](img/723e9c79ea07c23eb14c99280ea0a075_443.png)

因为大家可以看到左边的这个图。

![](img/723e9c79ea07c23eb14c99280ea0a075_445.png)

那左边的这个图呢，我中间这边其实用蓝色的线切开，它上面是32bit，然后下面是16bit，所以实际上32bit的东西不仅比较大，他用到的时间也比较少，像是这个ADAM的optimizer。

它会用到的时候，其实是你要更新一个global step的时候才会用到呃，ADAM的optimization，所以上面这三个东西其实呃是比较少用到的，那他们就选择说这三个东西先优先放在CPU上面。

那剩下的东西还是放在GPU上面，那基本上就是有这么样个分割，去让他们有一个initial的想法，说可以第一个选择先放optimizer，然后速度也不会降的那么夸张，对好大家还有问题想问吗。



![](img/723e9c79ea07c23eb14c99280ea0a075_447.png)

好没有的话，我们就再次谢谢助教，谢谢讲的很清楚，太棒了，大家，好谢谢好，那我们还是休息5分钟，然后让助教换个场，等下讲作业。



![](img/723e9c79ea07c23eb14c99280ea0a075_449.png)