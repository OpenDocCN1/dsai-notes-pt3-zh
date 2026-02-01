# 强推！(2026最新版) 李宏毅最新课程：智能体AI【AI Agent】71集全！人工智能／机器学习／深度学习／大模型／LLM - P5：4-作业 Understanding transformers - Ai人工智能工程师 - BV1QdzCB3Eu2

好大家好，这次是machine learning，home work3的作业，Understanding transformers，那这次作业的DLINE，是4月4号的23：59分好。



![](img/118b53e1858e091eb8d7a8cfd19fad62_1.png)

那简单讲一下这次作业的test outline，这那我们会先分为呃test overview，然后stay out，然后讲一下问题，To duce，然后关于submission的规定以及你分评分的方式。

那所有相关的链接都在右手边，这样大家可以自行去做。

![](img/118b53e1858e091eb8d7a8cfd19fad62_3.png)

点击，那简单讲一下这次作业的overview，那这次作业主要focus在，我们去了解LM跟transformers的架构，那我们使用的model呢是去年6月底公布的。

game a two two bi it从google，然后同时我们呃有包含很多呃论文的阅读，需要大家去做理解，那与前两次作业比较不同的地方是，这次作业主要呃。

coding的部分是辅助大家做观念题的回答。

![](img/118b53e1858e091eb8d7a8cfd19fad62_5.png)

额那这次呢我们会分为两个比较大的部分，第一个的话会是coding以及要回答的问题，那这部分呢我们会再分成四个细项，那第一个呢会是关于chat template的比较，以及多轮对话。

那第二部分是关于TOGANIZATION，跟embedding的部分，那第三的话会是attention位的视觉化呃，第四部分的话呢则是SAA1的讲解，这那paper reading的部分。

我们有准备三篇论文给大家阅读，然后同学需要回根据这个问题回答八个呃，不同的问题，这样。

![](img/118b53e1858e091eb8d7a8cfd19fad62_7.png)

那cell的部分的话呢，我们会先介绍model download部分，那因为这部分需要请大家去创建一个，HuggingFace的账号，那如果同学已经有的话，就只需要登录就可以。

然后创建之后我们需要去创造一个RETOKEN，来去下载这个model。

![](img/118b53e1858e091eb8d7a8cfd19fad62_9.png)

那我们简单介绍一下如何去创建xx token，那首先的话邀请大家登录，或者是呃创建你们的哈电费账号。

![](img/118b53e1858e091eb8d7a8cfd19fad62_11.png)

然后进去之后点击左手边的settings部分，那这边的话去点击x tokens。

![](img/118b53e1858e091eb8d7a8cfd19fad62_13.png)

然后在右上角应该可以看到一个create new token。

![](img/118b53e1858e091eb8d7a8cfd19fad62_15.png)

然后点击一下，那这边他会请你选择token的type，这样那请同学就使用retype就可以了，因为我们是要下载model，那token name的话呢，大家就看大家想要填什么都可以。

那今天要注意的点是呃，在创建好token之后，他会请你先复制，那请同学先把那个token复制到你的记事本，或其他你记得起来的地方，因为当你关闭市场之后，他就没办法再重新复制。



![](img/118b53e1858e091eb8d7a8cfd19fad62_17.png)

好那我们得到这个ss token呢。

![](img/118b53e1858e091eb8d7a8cfd19fad62_19.png)

之后呢，我们需要去呃同意这个model的license，才可以使用这个model，这样那一样需要登录你的哈king face账号，那同时在呃model的页面，我们有把model的链接放在这边。

然后可以点击点击进去之后呢，它会有一个acknowledge license，然后我们需要点击它，然后填写一些个人资讯。



![](img/118b53e1858e091eb8d7a8cfd19fad62_21.png)

那就可以下载model这样，那这边的话因为他可能需要一段时间去呃，接收你的email，那你这部分的话，我们助教实际测可能呃不会很久，可能需要几小时，他就会回应你这样，但可能视情况而定，所以请。

所以建议同学可能啊提前几天就开始去申请。

![](img/118b53e1858e091eb8d7a8cfd19fad62_23.png)

这样，好那我们这边就开始讲解，第一个问题就是chat template的比较，那这个主要的大题呢，是要请大家观察有无chat template，对于model的回答造成的影响。

那这边有提供我们助教的prom，请同学依照我们的prom在sample code中进行呃，执行并回答问题，那我的问题呢会是请大家比较有没有，chat and play的coherence score。

那关于coherence score的计算方式，我们在后续会做介绍，那这边有三个子问题，这样我们所有的问题跟选项都放在我们的grace sc，上面，也把同学加进去了，所以到时候呃，详细的问题跟选项。

可以参考GRASGO去做回答好，那第一个问题就是请大家呃去填写，说有无chat temper的coherence score分别是多少，是一个填充题，这样然后我们会有一个误差范围，只要在0。5，正-0。

5都会被接受，那第二个问题呢则是请大家去比较，哪一个score是比较高的，那第三个的话就是去解释这个实验，以及选出正确的答案。



![](img/118b53e1858e091eb8d7a8cfd19fad62_25.png)

然后这边会是一个多选题，那我们进一步介绍我们的coherence的model，这样我们主要是使用这个cross encoder，作为我们的呃open source的那个以平分的model。

那这个口这个model呢主要是去计算，就是呃model回应的这个coherent score，这样那我们使用的方法都放在simple code，大家可以去做参考。



![](img/118b53e1858e091eb8d7a8cfd19fad62_27.png)

那多人对话的部分呢，我们这边是主要是邀请大家，跟我们的模型去做呃，不止一轮，周瑜一轮的对话，这样，那我们conversation history也是提供给大家可以做参考，然后总共有三个run。

那每每输入一次之后呢，按enter模型就会回应你一个output，然后再你就可以再输入第二次，然后得到模型，第二个output，以此类推。

这样嗯那也请大家不要更改我们的conversation history，不然有可能会造成模型的输出，与我们预想的不同。



![](img/118b53e1858e091eb8d7a8cfd19fad62_29.png)

那我们这边的问题呢有分三个阶段，那第一个部分呢是要请大家提供，我们呃有chat template format过的prom，这样，那注意这边呃是在第三回合，而且它不是指模型的output。

而是指你输入之后，模型把你用chat template的形式包装起来的pro，那第二题的话呢呃要请大家回答，就是关于呃，第一个阶段的最高几率的token是什么，是这样，那这边呃刊物一下。

他这个是个填充题，那第三部分的话呢，这是一个呃关于观念的选择题，这样那请大家选出错误的叙述。

![](img/118b53e1858e091eb8d7a8cfd19fad62_31.png)

好那前面是前两个大题的，那我们进入第三个大题，就是关于organization的部分，那这边的话呢同样助教有提供一个呃，我们希望你TOGANIZATION的prompt，那也请大家不要做更改。

那呃这个部分呢会是一个填充体，然后会请大家实做，如何去把一个句子做token ize。

![](img/118b53e1858e091eb8d7a8cfd19fad62_33.png)

那实做完之后呢，应该会得到下面这个形式，那会请同学做这个填充题，关于我们挖空的1234个去做回答呃，分别是呃token index以及token的呃，就是token的那个词，这样子。

那分别占分也写在上面。

![](img/118b53e1858e091eb8d7a8cfd19fad62_35.png)

好，那我们进入第四个主题是auto regressive的generation，这那这边的主要的叙述的话呢，会是请大家日用auto regressive generation。

去生成20个sentence，这样子，那我们这边计算的评分标准是self blue score这样，那同样因为auto regressive generation，有两种不同的方式，一个是top k。

一个是top p，然后K跟P的值也可以做更改，会得到不同的呃，generated and sentence的多样性以及不同的叙述，这样所以就会请大家这边主要做的事呢。



![](img/118b53e1858e091eb8d7a8cfd19fad62_37.png)

就是让我们提供呃助教提供的sample prompt，然后去做auto regressive generation，那第一个问题会请大家先做对，self blue score做回答呃。

什么是self bluscore，然后你应该会看到，GRASCODE上面有相关的documentation，可以让大家做参考，那第二部分的话呢，邀请同学去了解top跟top k的差别是什么。

那也是一个多选题，这样那第三部分跟第四题的话呢，主要是邀请大家去调整K跟P的值，并且做啊，关于K等于一以及P等于零啊，所生成的句子分别是什么，那是一个填充题，那五跟六的话呢，会请大家调整K跟P的值。

并计算相对应的self blue score，然后做选择题的回答，看是K等于二跟K等于200，哪一个的soft blue score比较大，那一样，P等于0。6跟P等于零啊，P等于以0。

999哪一个self bluciscore比较大。

![](img/118b53e1858e091eb8d7a8cfd19fad62_39.png)

好那呃我们进到第五部分，第五部分的话呢，这边会是一个ts神一的作图，那呃同样我们把visualization的function都写在simple code，同学可以直接执行，并且观察图片并做回答。

那我们问题的部分有分成三个字体，那第一个的话呢是关于T3TS1的观念题，然后是一个多选题，请选出正确的选项，那第二个部分的话呢，呃是要请大家根据这张图的呃观察去做回答，这样然后呃二三应该都是多选题。

要注意的是，二是选出正确的选项，然后三是选出不正确的选项。

![](img/118b53e1858e091eb8d7a8cfd19fad62_41.png)

好那呃pom six的部分的话是关于attention map，那嗯同学应该知道就是self attention的部分，就是算出一个sentence之间，token跟token相对应的关系。

这样那如果不清楚的话，可以参考老师的影片，在2021年机器学习的影片有，就有更详细的介绍。

![](img/118b53e1858e091eb8d7a8cfd19fad62_43.png)

那这个test呢主要就是请大家要去绘制，并且观察我们所画出来的attention map长什么样子，那我们有提供相对应的prop，以及你需要观察attention的layer以及head index。



![](img/118b53e1858e091eb8d7a8cfd19fad62_45.png)

那问题的部分的话呢就是邀请大家选出呃，关于attention map呃，正确的选项，这样子你应该可以透过呃，你执行出来生成的attention map去做回应，那一跟二主要的差别呢会是一是单选题。

二二是多选题，然后第三跟第四部分的话呢也是观念题。

![](img/118b53e1858e091eb8d7a8cfd19fad62_47.png)

那它是一个是非题，也是让他做回答，好那呃接下来介绍第七部分，第七部分还会针对SAE的部分去做探讨，这样那我们使用探讨模的方式呢是GAMUSGO这样，那关于game mosgo的网站。

以及它所细节化的呃平台，大家可以点击链接进行参考，那同样我们在sample code中也有写好，大家只需要去观察10004这个feature，代表的意义，以及它所生成的activation。

density是什么意思就可以了，那同一样是观念题，然后多选题。

![](img/118b53e1858e091eb8d7a8cfd19fad62_49.png)

那七十二七十三呢我们有准备两个不同的pro，然后分别是prom a，prom b大家可以做参考，这样那这边要比较的是两个prom，在在它的最大activation值上面，有什么不同的音呃，不同的值。

这样子就是哪一个会比较大，是PUA还是pub这样，那并且去解释说为什么碰杯或胖B，那the back nmaximize uh activation是比较大的，这样所以这边有两个小题，那这边有个小HT。

就是说大家可以根据activations distributions去做参考。

![](img/118b53e1858e091eb8d7a8cfd19fad62_51.png)

那74~76呢是关于呃同一个prompt，但是它是在固定layers，24底下呃，针对不同token的作图，那请大家去对于这个实验去做相对应的回答，那一样是一个选择题。



![](img/118b53e1858e091eb8d7a8cfd19fad62_53.png)

这样，那77~79比较不同的是呢，这边是针对呃同一个tokens，但是不同layers去作图这样，然后同样的我们准备一样的prompt，然后这边可以去调整token index并做回答。

那这边小hint就是说你可以去调整token index，然后呢去观察它是在比较浅层的layers，对于activation值会比较大或比较小，那在深层的话是比较大或比较小，大家可以根据作图去做回答。

然后二三题的话呢，也是针对这个实验的适配题对，然后是非就是会有true false，所以这件事写选择题这样。



![](img/118b53e1858e091eb8d7a8cfd19fad62_55.png)

那coding的部分的话，等下会做讲解，这样那我们也提供COLAB的链接，大家可以去呃去做reference好。



![](img/118b53e1858e091eb8d7a8cfd19fad62_57.png)

那进到part b的部分，就是我们有关于论文阅读的部分，那这边的话呢会总共有八个小题让大家回答，然后会请大家看看清楚这个三篇论文在讲什么。



![](img/118b53e1858e091eb8d7a8cfd19fad62_59.png)

这样，那因为我们这次的作业比较是偏观念题的回答，然后扣的部分就是也是请大家是需要实做，然后有些部分呢是根据你的实验去做回答的，所以呃我们还是需要去交交交交口，这样呃，那我们脚交扣的方式呢。

就是一样是学号底线红卫三，然后的压缩档，这样那里面就包含你的Python notebook，应该你只要是交一个可以执行的档，然后我们可以reproduce就可以了，这样。

那同样需要注意的就是在n to code上，那只我们只能接受你最后一次的缴交，然后如果你的code呃不合理，或者是呃我们可能没办法reproduce的话，会对你的分数做呃斟酌的呃。



![](img/118b53e1858e091eb8d7a8cfd19fad62_61.png)

打折这样好，那第二部分的话，我们gray scope的评分是暂时分这样，那我们grace code就是有包含所有的问题，以及选项在上面，然后大家可以登录进行呃回答这样，然后关于登录的部分的话呢。

假设你之前已经有申办，用学校的账号申办过great sco，你就可以直接登录，应该就可以看到有一个机器学习的呃，宏伟三的作业可以点击进去进行回答，那假设你之前没有办理过grace go的话呢。

应该是使用NTU库的账号就可以进行登录，这样然后也可以在登录之后呢去更改密码，那可是更改密码的话，他可能会寄送个一秒到你信箱，然后可能需要等一下下才可以看到，这样好。

那假设还有后续有登录GRASGO的问题的话，也可以在讨论区发问，或者是即兴跟我们说。

![](img/118b53e1858e091eb8d7a8cfd19fad62_63.png)

那介绍一下评分的部分，其实就是如上所示，我们评分都是以GRASGO为主，然后GRASGO又分为两个大题，一个是coding的问题，另外一个是我们论文阅读的问题。

这样那因为我们这次评分十分都是占GRASCODE，但是因为我们还是需要去reproduce他的code，所以会请大家还是需要上传你的code呃，在呃到NTU库上这样，那如果你没有上传的话呢。

就算你的归构是满分的话，我们可能还是没办法给你分数，那请大家要务必注意这一点，这样。

![](img/118b53e1858e091eb8d7a8cfd19fad62_65.png)

好那关于我们截止日期的话，嗯我们截止日期是呃，在nt l call或GRASCO上都是呃，四月十号的23。59分，这样。



![](img/118b53e1858e091eb8d7a8cfd19fad62_67.png)

然后我们这边有关于一些课程的规定，那请大家务必遵守，这样，那也应该跟红work one，红work two大同小异，大家可以做参考，就是你不能去呃作弊这样子，然后如果你有用其他的资源。

或是其他部分得到的选项，而不是你做实验得到的话，你要写在reference里面呃，就是可能你就是在code里面有标注这样子，那呃后来二三部分的话，就是呃不能把你的code分享给所有呃活着生物，这样。

然后另外就是你不能呃去，可能使用非我们扣的部分去生成一个答案，这样但是关于观念的问题的话，你当然是可以上网去搜寻，是没有问题，然后再来的话就是呃，如果你违反上述的规定的话，你可能在分数上会被打折嗯。

或然后加上这次功课可能没拿，没办法拿到分数这样，然后如果你违反规定太多次的话，我们助教会经过讨论之后，可能这可以给你F的分数这样，然后另外就是呃老师跟我们助教会保有说。



![](img/118b53e1858e091eb8d7a8cfd19fad62_69.png)

更改这些权利的规定，好如果你有任何问题的话，要怎么询问，就是我们有开一个红work3的讨论区，然后我们也建议你可以从上面去问大家问题，然后我们会优先回答讨论区上的问题对。

然后让大家让其他同学可以看到你的发问，也可能是别人的问题，这样那email的部分，假设你有个别问题的话，可以进行到我们助教的现象，那请大家记得我们的title要加上红work3啊，让我们助教方便辨识对。

然后tr worst的话呢，呃会是在礼拜五的课后哦，今天补充一下呃，刊物一下，就是还有课前这样子，然后课前的时间是呃是13。20到两点钟，这样对，然后课后的话是17。20到六点钟。



![](img/118b53e1858e091eb8d7a8cfd19fad62_71.png)

好那我今天简单介绍一下我们扣的部分。

![](img/118b53e1858e091eb8d7a8cfd19fad62_73.png)

好，那关于扣的部分的话呢，因为这次主要是辅助大家做，对观念题进行呃回答，所以我们需要大家实做的部分，没有像前两次那么多，那这次的话呢主要是一样，在我们拿到这个simple code。

第一件做的事情就是需要去创建一个副本，才可以去执行好。

![](img/118b53e1858e091eb8d7a8cfd19fad62_75.png)

所以要要大家记得一下，然后那接下来就是要检查一下有没有GPU。

![](img/118b53e1858e091eb8d7a8cfd19fad62_77.png)

然后我们需要install一个transformers的套件，那这个套件的话呢，因为我们呃会希望大家不要去更改，我们的版本资讯，因为虽然他现在可能有更新到4。474，4。48。0。

但是更希望大家还是使用4。47。0，因为呃对于之后model的下载跟执行上来讲。

![](img/118b53e1858e091eb8d7a8cfd19fad62_79.png)

会比较稳定的好，那to do第一个部分就是跟大家如果还记得的话，我们前面也请大家会去下载一个hiking face，x token嘛，所以会不希望大家把x token填在这个位置对。



![](img/118b53e1858e091eb8d7a8cfd19fad62_81.png)

那接下来的话就可以用ss token去下载model，那但是你的ss token是被认证过的话，应该可以成功的进行下载，那要注意的是，就是假设你想要个别回答单一问题，比如说我想要回答Q3那一样。

你需要先跑这个cell，就是先下载model才可以去跑。

![](img/118b53e1858e091eb8d7a8cfd19fad62_83.png)

才可以去执行的好，那我们听到question one的部分。

![](img/118b53e1858e091eb8d7a8cfd19fad62_85.png)

那同样我们有把eviation model的link放在这边，然后大家可以做对这个方选做参考，这样都帮大东方就是助教都已经写好的好。



![](img/118b53e1858e091eb8d7a8cfd19fad62_87.png)

那进入到to do1至1~1至四，那这边的话呢我们是需要去产生我们的output id，然后根据我们的呃token ize，token ized之后的imply t去产生OPERD。

这样那真要注意的地方呢是呃，我们的有个参数叫do sample，希望大家调成false，我们才可以得到固定的回答，也才可以保证就是答案跟我们所预期的，会没有太大的区别。

这样那关于如何呃产生我们的model response呢，我们这边有提供我们的呃，这个model的连接，那里面有很详细的叙述可以做参考。



![](img/118b53e1858e091eb8d7a8cfd19fad62_89.png)

应该就可以得到回应，这样那展产呢，假设大家已经知道如何产生额model的response。

![](img/118b53e1858e091eb8d7a8cfd19fad62_91.png)

之后呢，那就可以回答一次1~1次次的问题了。

![](img/118b53e1858e091eb8d7a8cfd19fad62_93.png)

那后续这两个bug主要在做的。

![](img/118b53e1858e091eb8d7a8cfd19fad62_95.png)

就是去计算coherent score，那同样假设前面执行了正确的话。

![](img/118b53e1858e091eb8d7a8cfd19fad62_97.png)

后面应该可以得到两个不同的可human score，然后大家可以做比较。

![](img/118b53e1858e091eb8d7a8cfd19fad62_99.png)

那第二部分的话呢是关于多轮对话的部分。

![](img/118b53e1858e091eb8d7a8cfd19fad62_101.png)

那这部分的话呢呃同学不需要做额写任何的扣，因为只需要去做观察，观察我们这个注解起来的部分就可以了。

![](img/118b53e1858e091eb8d7a8cfd19fad62_103.png)

那我们注解起来部分呢就是model在不同run里面呃，针对呃我们的使用输入的prompt，然后经包装成TRATTEMPT的format所对应的形式，这样那同学要回答的填充题。

也是根据这个cheat template former point去做回答，然后注意是回答run3的问题好。



![](img/118b53e1858e091eb8d7a8cfd19fad62_105.png)

所以同学可以根据这个口去做回答。

![](img/118b53e1858e091eb8d7a8cfd19fad62_107.png)

那进入到第三部分，第三部分我们会请同学去实做，关于如何去进行token ize的部分，那这部分的话呢一样呃，token id跟token如何获得呢，我们都有在这两个documentation。

大家可以去根据这两个documentation做参考，应该写的蛮详细的，那那同学要实做的就是，如何进行token d跟tokens这样。



![](img/118b53e1858e091eb8d7a8cfd19fad62_109.png)

那得到之后呢，我们就可以印出我们对应的形式，那你就可以看到我们在题目所述的那个挖空的，1234分别对应到什么值。



![](img/118b53e1858e091eb8d7a8cfd19fad62_111.png)

那第四个问题是auto regression的generation，这样那这边的话呢一样，我们大部分的sample code也帮同学写好，那主要是请大家做实验。

是需要去调整top k跟top p分别的值并做回答，这样那我们这里有一个预设值。

![](img/118b53e1858e091eb8d7a8cfd19fad62_113.png)

大家可以去调整。

![](img/118b53e1858e091eb8d7a8cfd19fad62_115.png)

另外呢就是因为我们有两种生成的方式，第一个是top k，第二个是top p，这样那top k的部分我们助教要帮大家写好，那请大家同学需要实做的是top的generated output，分别是什么。



![](img/118b53e1858e091eb8d7a8cfd19fad62_117.png)

这样子，那同样我们有可以参考的documentation，大家可以点击进去进行参考，如果不太清楚的话。



![](img/118b53e1858e091eb8d7a8cfd19fad62_119.png)

好另外的话呢，因为我们有top k跟top p生成20次的结果，我们会把那些值的平均去做self blue的运算，这样那stublue score，会分别得到关于top k跟TOPT的呃值的结果。

大家可以根据这些去回答问题。

![](img/118b53e1858e091eb8d7a8cfd19fad62_121.png)

那第五部分关于TS音的部分的话呢。

![](img/118b53e1858e091eb8d7a8cfd19fad62_123.png)

我们这里有准备呃，注要在投影片以及在great go grasgo上面所呃。

![](img/118b53e1858e091eb8d7a8cfd19fad62_125.png)

所需要的sentence。

![](img/118b53e1858e091eb8d7a8cfd19fad62_127.png)

然后一样这部分是不需要去改扣的，应该同样执行观察结果就可以回答我们的题目。

![](img/118b53e1858e091eb8d7a8cfd19fad62_129.png)

好那进入到attention位的部分。

![](img/118b53e1858e091eb8d7a8cfd19fad62_131.png)

attention位的部分呢，这边请大家需要实做的部分，就是我们因为我们的model，一个output的形式已经写好了，这样子，然后可以注意的是，我们output attention是true。

也就是说我们可以从output中提取出attention的值，这那要要怎么提取呢，就是邀请同学去做实做，那实作部分呢一样有可以参考的大UMENTICATION，应该有蛮详细的，output的架构。

大家可以从output中提取出LOGIES，也可以从output中提取出attention scores这样子，所以大家可以呃通过这边去做回应。



![](img/118b53e1858e091eb8d7a8cfd19fad62_133.png)

那实做完之后呢，大家应该可以成功的看到呃，attention waste的视觉化的图，那并且对问题做回答。



![](img/118b53e1858e091eb8d7a8cfd19fad62_135.png)

那第七部分是S1的部分，那需要注意的是，在执行第七部分，不管是哪个小题的话，大家记得去批评inststore SAE length这个套件，这样然后呃就是要请大家注意一下。



![](img/118b53e1858e091eb8d7a8cfd19fad62_137.png)

嗯好，另外的话就是呃去下载这个game mascope的部分。

![](img/118b53e1858e091eb8d7a8cfd19fad62_139.png)

才可以进行回答，那下载完之后呢，我们这边有一个视觉化的function，大家可以根据这个去看到一个网页的平台，这样那这边我们有提供好features index，也是大家需要观察的。

features10004这样，那根据这个视觉化的平台，大家应该可以在执行这个code之后，就可以看出feature10004代表的意义是什么，然后进而回答question。



![](img/118b53e1858e091eb8d7a8cfd19fad62_141.png)

其之一，那七十二七十三呢是观察最大的maximum，MAXIMUS呃，activation值，这样，那同样是我们有帮大家写好一个function。



![](img/118b53e1858e091eb8d7a8cfd19fad62_143.png)

那因为我们需要比较两个pp，所以pn may跟PB1写在这边，那大家只要执行call话就可以看出呃，pom a跟pom b分别最大的activation值是多少。



![](img/118b53e1858e091eb8d7a8cfd19fad62_145.png)

并回答问题好，74~76呢。

![](img/118b53e1858e091eb8d7a8cfd19fad62_147.png)

这部分是观察呃activation的distribution，那74~76是固定layer，去观察不同token s的分布，所以这边是我们有固定好layer4，那也是问题。

只需要观察24layer就可以了，这样然后你还会看到一个activation的分布，那可以根据那个图去回答问题。



![](img/118b53e1858e091eb8d7a8cfd19fad62_149.png)

那77~79呢会是一样。

![](img/118b53e1858e091eb8d7a8cfd19fad62_151.png)

是针对呃activation分布，但是是针对固定的token index，然后观察不同layer的呃activation值的影响，那同样这边的话可以请大家去调整token index。



![](img/118b53e1858e091eb8d7a8cfd19fad62_153.png)

进而回答问题，好那这次主要是我们全额整个扣的呃，解释这样子，那如果还有其他个别的问题的话呢，欢迎在讨论区询问，也可以去即兴询问我们这样子好点。



![](img/118b53e1858e091eb8d7a8cfd19fad62_155.png)