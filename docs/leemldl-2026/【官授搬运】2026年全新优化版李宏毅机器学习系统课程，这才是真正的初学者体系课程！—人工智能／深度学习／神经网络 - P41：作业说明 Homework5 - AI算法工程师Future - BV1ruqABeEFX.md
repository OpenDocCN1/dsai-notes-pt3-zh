# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P41：作业说明 Homework5 - AI算法工程师Future - BV1ruqABeEFX

那OK我现在来开始进行哦，HOO5的讲解下，那首先是这是online，那一开始我就会先介绍这次要做的test，我们是要做呃translation，然后接下来是我们的work for就是流程。

然后要怎么去劝这个东西，那接下来就是呃我们的base line跟我们的report的问题，那后面会有，因为这是我们要使用judge boy，不是之前的cargo。

那会有josh boy的那个guide对。

![](img/1c0d9646a6905c392c97e5ecdae1f610_1.png)

然后后面就是一些呃课程规定对好。

![](img/1c0d9646a6905c392c97e5ecdae1f610_3.png)

那首先我先来介绍一下这次要做的test，哦我们这是要做translation，那我们就是要从英文翻到中文，那就是假设我们这边有一句就是呃，Thank you so much chris。

那我们会把它翻译成，非常谢谢佩斯对，那另外就是我们在不同语言里面，我们的句子可能会是不同的强度，那这时候就就可以用到我们的secreto secret framework，可以。

那我们这次data set呃，是我们有分配的data跟那个呃，这是这是一个只有中文的data，那pad data我们是从ted at2020里面抓下来，那就是我们会拿呃中文跟英文的data。

那后面我们会有一些是只有中文的data，那这个东西要怎么用，等下会再说对，好那我们的那个呃evaluation部分的话，我们这次是采用blue score这个这个机制，对，那我们这只呃。

其实我们只要知道就是说他他会去看你的output，跟你的target就是长得有多像，这大概就是这样子，好那这是哦我们的整个流程，一开始我们会先有usual data。

那我们会先去做PREPROCESSING，那会把它转成就是我们可以用全in data，那接下来我们去定义好，我们的model的那个架构以后，然后就把它丢进去train，那上完model以后。

我们就可以把我们test data放进去，那我们就可以得到我们的PREDATION，那也就可以得到我们的performance，对那PREFAST的部分的话。

就是我们会先download我们的呃raw data，那它里面就会是呃好几很多的中文句子，跟很多英文句子，那我们接下来就是会把一些太长的或太短的东，西的句子给先去掉。

那接下来就是呃再去做那个token anization，是，再来的话呃就是我们training的部分的话，就是去呃初始化我们的model，然后去确认我们的这些data。

那testing的部分就是会去生成我们的translation，出来的呃，taste data就就把我们test data放进去，然后做translation，然后去测试它的那个结构。

那以下是一些额就是要怎么去劝这个这个东西，那首先是呃这有大概有这个四点，那接下来会一个一个去说，那首先是token的的部分，那我会把这个data token呢成呃很多的Sol unit，那这样的好处。

就是说我们可以去减少我们的单子的量，就是假设我们可以用呃很多字，首，字根字尾之类这种概念去把我们字拆成很多呃，把我们字去用比较小的unit去表示，那也就可以减少我们很多的单词量，就是例如下面这个例子。

好接下来label smooth的部分就是在劝一个呃，像是classify的时候，我们可能会你的model就是output在一个labels，在一个index上面的话。

它就是1output出一个呃E这样子，那我们做label smooing的话，就是去把其他呃错误的呃，错误的部分的话也给他加一点可能性，那就是防止你的model会去呃OVERFITTING，对。

好那接下来是呃去做LINURASCHEDULE0部分，那我们会首先我会先去把我的name in rate从额，会先有一个WUPWWUP的步骤，那会先把它从D拉高，然后接下来到某个特定step以后。

再让我们的林瑞引入额，这样子递减下去，那接下来是额back translation部分，刚刚前面有提到，我们会有只有中文的data，那只有中文data要拿来干嘛呢，就是因为我们有para data嘛。

那我们可以先train一个从中文翻到，从中文翻到英文的model，那算完之后呢，我们再把我们的额单一只有中文的data，把它翻译成英文，那我们再放进去当做我们的data set。

那这样子我们就有更多的资料可以拿来，劝我们的英文到中文的model，对，Ok，那这边有几点要注意的部分，就是额，首先是你的more lingu的data，就是应该要在一个相同的抖音上面，这是根对。

然后接下来是就是你的被过滤的model的呃，performance是很重要的，就是他如果他如果是一个呃上的不好的model的话，就是他他结果不好的话，那也会影响到你之后的data set。

然后就是你增加，因为你现在会增加你的那个后，后面会增加你data set的data量，那这时候就要去增加我们的model capacity，因为你的model那个你的data的量增加了。



![](img/1c0d9646a6905c392c97e5ecdae1f610_5.png)

对。

![](img/1c0d9646a6905c392c97e5ecdae1f610_7.png)

那接下来是baseline部分，那我们这边定个我们这边定的这些额，simple media strong跟boss，那我这边呃有给一些就是我预计的时间，那我们这次建议会在，希望大家可以在开口上面确认。

因为呃以simple bassline来说，KAO上面的P版GPU大概在一小时内可以劝完，但是如果使用免费版COLAB话，我自己试，大概要可可能要九个小时之类的，所以所以希望大家可以用卡go。

然后MILI话就是大概在多个额40分钟，然后算的话可能我预估大概在三个小时，那boss的话，因为你要先做，你要先劝一个反向的model，然后再劝回去，然后你劝回去以后，你的data量会变多。

那这边预估应该会大大于12小时，这是对会比较久一点，好那以下是就是呃要要怎么去过各个baseline，那首先是simple bassi部分额，就是基本上就是我们跑simple code。

然后我们就会跟我们simple base line，好那MEABASSEINE的部分，我们要加入额刚提到的那u schedule，然后还有我们把我们拉O线长一点。

那learn race schedule的部分，我有我有在扣呃，我有提供这个就是这个也可以选，那我们基本上只要把它input本出来以后就好了，对那装备赛的话就是去把我们的encoder。

decoder从RN变成transformer，那以及去调一些transformer的参数，那这边有一些建议的参数调整，然后其他就是如果想要再增进你的model的话，可能可以去参阅呃，这篇paper对。

好那boss背上一部分就是要去apply，额我们的back translation，那要去做BLACTIONTRATION的时候，有几个要注意的地方，就是首先你要先把。

因为model我们本来是定义从英文翻成中文，那我们现在要定义成从中文翻成英文，然后后面会有一些呃，看我们回去会有一些to do的部分，那基本上就是去照着呃，前面的步骤去把它做出来，对，那这边会有一些额。

这边是我们的KO声波code link。

![](img/1c0d9646a6905c392c97e5ecdae1f610_9.png)

然后collisible co跟转播的link，那接下来report部分，好那我接下来要讲report部分。



![](img/1c0d9646a6905c392c97e5ecdae1f610_11.png)

那这次report overview，大家可以就像屏幕上显示这样，那第一题呢在第一题里面呢，我会希望大家去visualize，每一个POSSESSIONALEBEATING之间的seniority。

然后MIRAS出来之后，我希望你们能够给出一个解释，这样子，那在第二题里面，我们需要你去你们去写作clip gradient noon，然后把gradient non在每个step的变化必须要出来。

然后圈出两个有发生grading expression的地方，那下面会有更详细的介绍嗯，那在例题里面嗯，假设你取出来的这个osational embedding的look up table。

是一个N乘D的matrix，那N就是代表作总共有N个口SHOMA0嘛，然后D就是这个cos勋OMB0它的代名权，那跟你你去计算两两就是两两之间的similarity。

之后你可以得到一个N乘N的similarity的matrix，那在这里面就是希望你们把这个N乘NUNDERING，meergy methods给VISUALI出来，然后简短的解释的结果大概会像一选出来。

大概之后会像右边这这张图这样子，那在这题里面，为了简化这个问题，我们就focus在decoder的processional and bing就好了啊，然后因为positional embedding。

它的用意就是要去encode positional的资讯，所以我们可以expect说就是position比较近的，position line也可以，他的SIMILITY会比较高的。

所以理论上我们visual，我们算出来这个similarity的matrix，他应该是在对角线附近的，security会比较强，这样做出来才是比较合理的结果，当额。

至于是怎么去计算两个vector之间的SEVITY呢，我们是我们这边是推荐大家使用cos型RG，然后这个东西在PYT里面有increment，那如果你想要用其他方式去计算两个呃。

两个vector之间的distance或者security的话，你也可以对你也可以使用，又是说ukukradian distance，说不定有人想用，反正只要你算画出来的组织对角线附近比较强。

我就不会算你错，然后这边是一些tips，就是关于怎么把decoder的presional and adding拿出来，反正就用这行把它拿出来之后，然后印出来之后看一下他的shift。

像这边是1026×256，就是有1026个possessional and bd，然后每个是256。

![](img/1c0d9646a6905c392c97e5ecdae1f610_13.png)

等你选这，然后第二题是要去去实做create gradient long，那在在讲第二题之前，可能还是先跟大家简单介绍一下，什么是gradient expression。

因为老师在今年好像没有介绍这个部分，然后这张图其实是从下面这个paper来的，然后在这篇paper里面呢，作者就把RNN的error surface给visualize出来。

然后他发现了就是RN的error surface其实是非常崎岖的，就是在有些地方它的error的变化是很平坦的，那在有些地方它error变化是非常的陡峭的，对这张图的纵轴就是LR。

然后X轴跟Y轴就是分别是W这个参数，跟B这个参数对，所以说在一般的时候呢，你一般的时候，例如说在这个平坦的地方，你在这边做参数更新的时候，你可能会发现，你可能会觉得因为这些GRADI都很小。

所以你就设一个比较大的ring rate，那一旦一一旦这个模型更新的时候，一脚踩在这个比较陡峭的地方时候，这个gradient是非常大的，所以你比较大的learning tored。

乘上一个很大的gradient，你的模型参数就会一次更新很多很多，那这样会造成什么问题呢，这样子会造成你的train的会变得很不稳定，那这都是比较好的状况，更糟的状况是你模型一次更新太多。

然后就就NAN了，然后你整个城市就停下来对，所以这个现象就是green expression，那这张图是RNN的例子，但其实在很多sequence to sequence model里。

都会有类似的问题出现。

![](img/1c0d9646a6905c392c97e5ecdae1f610_15.png)

那要怎么解决呢，这个gradient expression的问题呢，其中一个常用的方法就是叫做creeping，Gradient noon，然后先来讲一下什么是gradient on啊。

其实gradient on这个东西非常简单，它就是把每一个参数的gradient先收集起来，变成一个vector，像这下面这段是X，就是这个收集起来的这个vector。

然后去对这个vector去计算PON，例如说CHUNKNOWN，就是那个那个element的平方和，然后开根号，这样子就是CHUNKNOWN，然后PON就是它的扩扩增的版本这样子。

然后对就简单来说就是去把每个GRA，每个gradient收集成一个vector，然后去计算这个vector的P弄，那这个就叫做gradient non。

然后我们creating gradient noon的步骤，就是嗯可以大致上写成这三步，第一步呢你就去set up一个maximum的note value，然后max n这样子。

然后你就把每个permit的gradient收集起来，变成一个vector之后，然后去计算这个vector的p NO，那这边就把它写成LN，那第三步就是会去检查说这个LN。

LNN有没有小于你设的这个max noon这个value，如果说它比这个max node小的话，你就不去做任何事情，那如果说它比这个max弄大的话。

那你就对每一个gradient去乘上一个skill vector，叫做呃，就是这个scale factor呢是max NO除以2ULNODE，那你乘完这一步呢，你就可以确保这个这个gradient嗯。

就是这个gradient的vector呢，它的它的gradient note会小于设置这个max note，呃做这件事情就可以确保不会发生green expression，这样的事情对。

然后在这题里面呢，我们希望你们把每一个step的radio non给visualize出来，会像类似像下面这张图，然后visual sone呢你就希望你们圈出两个地方。

发生green expression的地方，然后至于这个东西要怎么去influence，其实不会很难，因为PYTORCH里面就有套件给infer，然后我们code里面其实也已经写好了，那就是画荧光笔。

这一行是最重要的地方，就是这个clip great grandon，它回传过来的这个G这个值啊，就是每个step的radio note，那你们在确定的时候，就需要把这个这个值存起来。

然后在train结束的时候把VISUALIS出来，这样子一定要在一定要记得存，要不然你就要重新训练对，然后visual之后visual出来之后呢。

就全组两个发生gradient expression的地方，如果没有发生，那就就不用全对好。

![](img/1c0d9646a6905c392c97e5ecdae1f610_17.png)

那上面是report的部分，接下来换judge board的juge board的一些概念。

![](img/1c0d9646a6905c392c97e5ecdae1f610_19.png)

Hello，大家好嗯。

![](img/1c0d9646a6905c392c97e5ecdae1f610_21.png)

这次的作业开始会用到judge for啊，这个跟大家之前用的开口不太一样，但我没有尽量让大家在使用上跟开口会差不多。



![](img/1c0d9646a6905c392c97e5ecdae1f610_23.png)

不过还是有因为不一样，所以有些地方要注意，那首先就是之前要请大家去填这个get a和COSPL，然后前几天就是之前助教里面有发一个reminder，那大家如果没钱的话，现在可以去填。

但是你这个作业可以扣一分，然后详细的扣分规定，你可以去给他一套设备里面的说明看，那大家要注意的是，如果你没有填这个的话，你可能你会发现，你可以登录我们的judge boy的网站，但是你没有办法上传。

所以你不管什么时候看，你会发现你的反面全扩大经用完了，所以大家记得之前的get up cosplay，才可以用我们的job board，那这个使用方式我有做成几页简单的投影片，来当做我们的一个流程图。

那其实大家先进到，我们现在在nq four上应该就可以看到，judge for homework five的连接，大大一进去的时候，可以先去找右上角这个loin的按钮，那我们这个登录的时候。

是要请大家用GITHUB账号去登录，然后这边登录的话呢，其实你不管有没有填名词备，你都可以登录，那你这边第一次登录的时候会请你授权，那这个授权其实没有干嘛，就是其实我也没有拿到什么权限。

那就是我要用这个，我要我要用，那我要让各位用这套账号登录的话，就一定要这个流程，大家可以不用太在意他会做什么，那你仔细去看，你会发现记录我也没有拿到什么权限，所以大家可以放心的授权。

那这边就是填你的账号密码，然后对他进去以后，他会问你要不要授权给我们这个process。

![](img/1c0d9646a6905c392c97e5ecdae1f610_25.png)

那你就完全授权到，那如果成功授权以后，你就可以顺利登录到我们的网页里面，那我们网页的左上角呢会有这个呃三条横杠，那这边就这这这就是有点像目录的概念，那点下去以后你会看到我们有四个四个RO美男。

home的话，其实就是我们呃home page，那没有什么有用的资讯，对就是对好，那比较重要的是你要上传扫描选时，你就点这个扫描，然后就嗯我们会有一个框框啊，你就写那个框框。

然后把你的submission上传到我们的家具board上面，那之后可以去一个boss上面看你的分数，那稍后呃助教应该也会示范，上传到judge boy以后的一些比较细节的操作。



![](img/1c0d9646a6905c392c97e5ecdae1f610_27.png)

那这边就不再赘述，OK那大家上传以后呢，我们这边一样跟cargo可以就跟cargo一样，可以让大家去选择你的submission，那大家最多可以选择两笔，怎么选，那这边有有一些东西要注意，第一个就是。

如果你没有选择任何submission一样的话，我们会跟开头一样，选择你的puppy score，最好的那一笔submission来计算你的diary sc啊，再来就是呃。

这个就是我们submission左边都会有个框框嘛，那你可能会发现deadline以后。

![](img/1c0d9646a6905c392c97e5ecdae1f610_29.png)

你还可以去勾那个框框，但是。

![](img/1c0d9646a6905c392c97e5ecdae1f610_31.png)

但是你勾了框框，你会发现你没有办法像在他以前一样，看到这个这个成成功选择了这个视窗，那其实就是因为我们后端的对API已经关掉了，所以你接完以后，你可以就你你可能可以很认真的去勾勒框框，但是完全没有用。

你重新整理以后，它就变回原来的样子，在这边就是怕大家之后会有疑问，先跟大家解释一下好。

![](img/1c0d9646a6905c392c97e5ecdae1f610_33.png)

那接下来是关于judge boy的一些规则，那这边大部分是比较general的rule，然也有一些是呃homwork five专有路，但是因为这边是第一个要把抓破了，所以我觉得时间不会特别兴奋。

那第一个第一个规定呢，就是我们会有每天会有五次的上传的过来，然后我们在午夜的时候会重置，那这边要注意的是，有时候你隔天刚打开的时候，你会发现它的扩展还没有重置，让大家不要担心，就是重新整理几次。

然后就会重置了，然后这边有个要注意的，就是如果你没有去填，你给他考试备，或是你才刚填，你还没有等到我们下次更新why list，你就去上传的话，那你会发现你一直都是没有过来的，然后第二点呢。

我们对上传的档案的副档名以及size，都有一些要求啊，避免大家传一些奇怪的答案上来对，所以大家选择档案的时候，如果你不是一个EST档，或者是你的档案太大，你会发现你没办法按下那个和上面的按钮啊。

再来就是呃我们的homepage其实会有一个倒数的对，会有一个倒数的界面，不过这个界面是写在前端，所以我们舍会很大控制，那以后去赶你电脑的时间，你可能可以让他就是还剩非常多时间，但是这一点用都没有。

所以不要做这种无聊的事情，但只是让大家大概看一下，你还剩多少时间而已好，然后因为我们这个server它不是一个非常呃production server，所以我们要限制一些呃连线的数量。

还要你呃一段时间内可以连线数，就是避免有人可能一秒内，就是只送了1000个零件，然后我们是不就坏掉，这样啊，如果你发现你突然啊没办法连线的话，那可能是你，你某一段时间内送出了太多连线的请求。

那你就稍等一下，应该就可以正常连线，那你如果从事了几次以后，发现这个混联，让你在就是到我们N优酷的讨论区留言，描述你的状况就可以，但是大部分时候应该是，只要等一下就可以正常连线，OK那下一点呢。

就是因为我们这个server毕竟是自己维护的，然后他也没有任何的网络skill的机制，我们就是只有一台机器那边，所以在接近DI的时候，可能会有一代人都要疯狂上传，那这个时候如果而你刚好就比较催。

那个就是比人家慢一点点，然后导致你没办法在实践前正常上传的话，那我们不会提供额外的上传机会，所以请大家不要就是冒险在最后5分钟，10分钟才就是想要上传你的嗓音选项，好。

最重要的一点就是请大家不要攻击我们的john boy，你是他对我，我觉得他可能蛮脆弱的，所以大家如果觉得他有哪哪里有一些漏洞的话，就直接跟我讲就好，然后就不用自己去尝试一下，哈哈哈嗯就是对好谢谢大家。

然后我们每周有三个小时的维护时间，就是每个礼拜五早上的六点到九点，那基本上这个时间，我们社会有可能会就是一直重启，那重启的时候就有可能，你在这时候如果去上传的话，可能就不太会word。

所以希望大家尽量避免在这个习惯去使用，我们judge for，那理论上，我们这个时间也会去更新我们的Y历史，所以你如果在这个时间前去填我们的呃，Github coster v。

那你在我们这个维护时间之后，应该就会在我们的WILIST里面，然后最后一点呢，就是大家如果有任何josh boy有问题，希望大家直接到我们NT酷的讨论区去留言，呃，虽然我们前前前面的作业。

还有后续的作业都可以让大家记起，但我觉得josh boy会遇到问题的性质呃，应该比较跟作业不太一样，就是可能使用上一些细节我没有讲清楚，那这些东西大家如果在讨论区留言的话。

很多人看到可能就知道自己的问题要怎么解决，所以我相信JOJO有问题，应该比较适合在一个公开讨论区里面去做讨论，所以希望大家跟josh boy相关的问题，就不要用即兴的，就直接到我们的这个NT酷的讨论区。



![](img/1c0d9646a6905c392c97e5ecdae1f610_35.png)

留言就可以了，然后我现在有开一个josh boy的讨论区，大家在我们的首页呢，这边应该就会看到一个job for issues，然后这边要写一些general rules。

还有这个一些可能有用的link，第一个link是我们的设备，然后第二个就是我们的WIDIS。

![](img/1c0d9646a6905c392c97e5ecdae1f610_37.png)

那这个yd其实你就可以先去检查，说你目前到底有没有在我们的这个白名单里面，那如果没有的话，就代表你不能用对，所以就对。



![](img/1c0d9646a6905c392c97e5ecdae1f610_39.png)

就是大家可以先用这个做初步的检查，这样子呃，然后大家问问题的时候，就是麻烦大家告诉我你的student id，还有你的giub com id，不然就是因为垃圾留言以后只能显示名称。

然那我我就还要用大名称去搜寻你的student id，还有你的介绍的高id，那可能就直接会变成这样麻烦，所以请大家问问题的时候，就记得留下你的学号。



![](img/1c0d9646a6905c392c97e5ecdae1f610_41.png)

还有点机号，Account id。

![](img/1c0d9646a6905c392c97e5ecdae1f610_43.png)

对看我们刚刚点的走进。

![](img/1c0d9646a6905c392c97e5ecdae1f610_45.png)

好那我关于josh boy的讲解到这里，大家有什么问题吗，啊没有的话就，好然后接下来应该是一些呃对规定。



![](img/1c0d9646a6905c392c97e5ecdae1f610_47.png)

然后还有平衡方式。

![](img/1c0d9646a6905c392c97e5ecdae1f610_49.png)

那这次的呃平分方式应该也跟之前是一样的，就是那个贝斯拉0。5分，然后report4分扣上面剩两分，然后这边是呃课堂里选择格式，那report部分就是请大家直接交到GRASCODE上面。

那我们的DI设在额4月8号一半，然后就是每个每个DI都是在这一天好，然后这边是呃就是一些呃基本基本规定，那相信大家都蛮清楚的，好，那有问题的话就可以到问题four或是呃寂静，或是铁奥对。



![](img/1c0d9646a6905c392c97e5ecdae1f610_51.png)

可以来询问，那接下来我要讲解这次的呃城市网部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_53.png)

![](img/1c0d9646a6905c392c97e5ecdae1f610_54.png)

好然后，OK这是城市网部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_56.png)

我们把它分成几个部分，那首先是而download对他say。

![](img/1c0d9646a6905c392c97e5ecdae1f610_58.png)

然后就是得先去呃装一些呃必要的package。

![](img/1c0d9646a6905c392c97e5ecdae1f610_60.png)

然后这边也是剧中我们的package。

![](img/1c0d9646a6905c392c97e5ecdae1f610_62.png)

然后这边是去import他们对，这应该都是基本的东西，然后这边是fix ren set，那哦这边是当O我们在到这个部分，然后如果这个我觉得这个link应该不会烂掉，如如果烂掉的话。



![](img/1c0d9646a6905c392c97e5ecdae1f610_64.png)

就是也可以就是赶快跟我们反映。

![](img/1c0d9646a6905c392c97e5ecdae1f610_66.png)

OK就是然后这边的部分的话就是刚刚有讲到，如果你要做PATIATION的话，就是要请你把它改，把他给交换对，那现在是呃，ASSOURCE是英文，然后PARIS是中文。



![](img/1c0d9646a6905c392c97e5ecdae1f610_68.png)

那我们可以看到我们的raw data的话就会长成，就是我的英文部分大概就会是这样一句一句的，然后中文会是一句一句的对，那他们应该是会去对应有对应上的。



![](img/1c0d9646a6905c392c97e5ecdae1f610_70.png)

那接下来是PREPROCESS的部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_72.png)

那proposal部分的话就是像我刚刚讲的一样，就是呃把一些太长的或太短的东西给去掉。

![](img/1c0d9646a6905c392c97e5ecdae1f610_74.png)

然后把额把它变成。

![](img/1c0d9646a6905c392c97e5ecdae1f610_76.png)

就是比较好去偷看的德性。

![](img/1c0d9646a6905c392c97e5ecdae1f610_78.png)

我这边是早就分train in vue，那额以下部分的话。

![](img/1c0d9646a6905c392c97e5ecdae1f610_80.png)

就会直接去把它转成少数UNUNIT。

![](img/1c0d9646a6905c392c97e5ecdae1f610_82.png)

那这边这边基本上都是呃我们我们写好的东西，就是不太需要去动，除了到最后去做啊。

![](img/1c0d9646a6905c392c97e5ecdae1f610_84.png)

你要去做BTRATION的时候，可能会需要用到这边去参考这边的code对。

![](img/1c0d9646a6905c392c97e5ecdae1f610_86.png)

![](img/1c0d9646a6905c392c97e5ecdae1f610_87.png)

那我们去呃把它转换成小无语。

![](img/1c0d9646a6905c392c97e5ecdae1f610_89.png)

你的话的时候，就会把本来的句子变成像这样子的形式。

![](img/1c0d9646a6905c392c97e5ecdae1f610_91.png)

嗯那这部分的话就是呃，这部分的话就是去做ABARRISE，那final rise，那就是对，就是把它变成可以喂进去model里面的的形式好。



![](img/1c0d9646a6905c392c97e5ecdae1f610_93.png)

接下来是比较重要的部分，就是呃我们的CONFIG部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_95.png)

那额首先就是说像我们MEI背上的话。

![](img/1c0d9646a6905c392c97e5ecdae1f610_97.png)

我们可能就说我们要劝强一点。

![](img/1c0d9646a6905c392c97e5ecdae1f610_99.png)

那这边可以去调整我们的呃A法数，然后。

![](img/1c0d9646a6905c392c97e5ecdae1f610_101.png)

OK然后呃刚刚有提到，就是我们report第二题的话是要去做呃，green explosion的部分，那我们那时候说，我们要把我们的呃那个next值设在一，那这就是去设那个值。



![](img/1c0d9646a6905c392c97e5ecdae1f610_103.png)

![](img/1c0d9646a6905c392c97e5ecdae1f610_104.png)

那log部分后退的这些都没什么，然后我们这次使用额。

![](img/1c0d9646a6905c392c97e5ecdae1f610_106.png)

就是直接来来自我们套件的translation test。

![](img/1c0d9646a6905c392c97e5ecdae1f610_108.png)

那就大概就是这样子去做INTRALIZE。

![](img/1c0d9646a6905c392c97e5ecdae1f610_110.png)

还想吃一些就是去漏data ta的部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_112.png)

![](img/1c0d9646a6905c392c97e5ecdae1f610_113.png)

好那我们这边encoder部分的话，我们额提供final code是用rn encoder。

![](img/1c0d9646a6905c392c97e5ecdae1f610_115.png)

那我们这边额定义大概就像里面罩子。

![](img/1c0d9646a6905c392c97e5ecdae1f610_117.png)

它的价格都在涨价。

![](img/1c0d9646a6905c392c97e5ecdae1f610_119.png)

然后接下来是呃attention部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_121.png)

然后再来是decoder部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_123.png)

那所以我们这次整个mod大概就会是说呃。

![](img/1c0d9646a6905c392c97e5ecdae1f610_125.png)

我们先去过0coder，然后再把问到我们的decoder去。

![](img/1c0d9646a6905c392c97e5ecdae1f610_127.png)

OK那接下来是呃就呃in your invisualize model的部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_129.png)

那本来的encoder和decoder是i encoder和decoder，那我们要把它换成transformer的话，我们大概就是把这两行被注解掉了。



![](img/1c0d9646a6905c392c97e5ecdae1f610_131.png)

把它换注解就好了，对。

![](img/1c0d9646a6905c392c97e5ecdae1f610_133.png)

![](img/1c0d9646a6905c392c97e5ecdae1f610_134.png)

额以下部分的话会是，哦我们的一些CONFIG部分，那上面的部分的话是。

![](img/1c0d9646a6905c392c97e5ecdae1f610_136.png)

如果你用rn in poder ninport的话，会用到的，那下面的话会是呃。

![](img/1c0d9646a6905c392c97e5ecdae1f610_138.png)

如果你是使用，如果你要使用transformer的话，你会你会必须要去靠这个方选，那去加一些呃。

![](img/1c0d9646a6905c392c97e5ecdae1f610_140.png)

设定对。

![](img/1c0d9646a6905c392c97e5ecdae1f610_142.png)

OK那下面的话就是一些哦哦买ZATION部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_144.png)

那首先是LALSMOVING。

![](img/1c0d9646a6905c392c97e5ecdae1f610_146.png)

然后接下来是呃NUSCHEDULE的部分，那我们这次会请大家在明天base line，就是请大家实做这个东西，那我会就是请大家去把这个方选给填好，那就照上面这个这个呃一个选区刻就好了。

那我觉得参数应该算是传都有传到蛮清楚的对。

![](img/1c0d9646a6905c392c97e5ecdae1f610_148.png)

![](img/1c0d9646a6905c392c97e5ecdae1f610_149.png)

那这边会是去额V9，还是我的整个整个schedule。

![](img/1c0d9646a6905c392c97e5ecdae1f610_151.png)

那再来是training。

![](img/1c0d9646a6905c392c97e5ecdae1f610_153.png)

training的部分，那这边可以看一下好，那这边就是要大家去记起来的这个呃GREN，那就是大家我是建议把可能存在一个list之类的，然后到最后再拔一次。



![](img/1c0d9646a6905c392c97e5ecdae1f610_155.png)

全部画出来。

![](img/1c0d9646a6905c392c97e5ecdae1f610_157.png)

好接下来是UFDATION跟influence部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_159.png)

我觉得应该也就是大家都可以不用去动它们。

![](img/1c0d9646a6905c392c97e5ecdae1f610_161.png)

然后面方程的话就是呃。

![](img/1c0d9646a6905c392c97e5ecdae1f610_163.png)

呃去劝你指定的A85，然后就到我们最后呃还要去扫描选部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_165.png)

那扫描选部分话。

![](img/1c0d9646a6905c392c97e5ecdae1f610_167.png)

我们可以我们会先去跑这个呃average age point是吧，会去把你的呃平均把你过去五个。

![](img/1c0d9646a6905c392c97e5ecdae1f610_169.png)

最后一个平均起来对，那这样的话可能会得到比较好的结果。

![](img/1c0d9646a6905c392c97e5ecdae1f610_171.png)

![](img/1c0d9646a6905c392c97e5ecdae1f610_172.png)

那接下来就是呃generous position的部分。

![](img/1c0d9646a6905c392c97e5ecdae1f610_174.png)

那我们其实只要做抠这个防水的话，我们应该就会先出一个普选点TST。

![](img/1c0d9646a6905c392c97e5ecdae1f610_176.png)

那后面是SPECTION，所以选的部分，哦被选择被选择选的话，就是他的步骤大概是这样。

![](img/1c0d9646a6905c392c97e5ecdae1f610_178.png)

就是我们先去DOBLE他的data set，那再用我们刚我们如果是圈一个呃，从中文到英文的model话，那我们再去用刚刚那个model呃。



![](img/1c0d9646a6905c392c97e5ecdae1f610_180.png)

在把这些资料给处理过以后，然后就去把它翻成呃英文，把从中文翻成英文对，然后再去把它加到我们的data set里面，对。



![](img/1c0d9646a6905c392c97e5ecdae1f610_182.png)

那基本上就是参考前面呃，preposal proposals的code就差不多了。

![](img/1c0d9646a6905c392c97e5ecdae1f610_184.png)

![](img/1c0d9646a6905c392c97e5ecdae1f610_185.png)

好那接下来我可能要示范一下脚胶的部分，那因为可能要劝一个人话，可能要一点时间，所以我这边直接抱回一个生蚝的QD呃，给拿来当素，拿来当做示范哦。



![](img/1c0d9646a6905c392c97e5ecdae1f610_187.png)

那我们先打开我们的呃。

![](img/1c0d9646a6905c392c97e5ecdae1f610_189.png)

Josh boy，那这边我经已经登录好了，我们可以看到先看到live four，这边的话应该会有一些，所以我们可以看到嗯各有place line，然后现在每个人的分数比较。



![](img/1c0d9646a6905c392c97e5ecdae1f610_191.png)

那点这边闪密的话。

![](img/1c0d9646a6905c392c97e5ecdae1f610_193.png)

那我们就直接把我们的忘记上哦。

![](img/1c0d9646a6905c392c97e5ecdae1f610_195.png)

不行好不好。

![](img/1c0d9646a6905c392c97e5ecdae1f610_197.png)

![](img/1c0d9646a6905c392c97e5ecdae1f610_198.png)

OK那我们就去选画我们的PREDATION，然后把它交出去，好然后我们就可以看到我们的分数哦，现在应该是对下面这个好，然后要去选的话，大概就是对这样把它卷起来，那重新整理，我应该对还是有。

那我这边额专座尾部分，还有应该就差不多这样子。

![](img/1c0d9646a6905c392c97e5ecdae1f610_200.png)