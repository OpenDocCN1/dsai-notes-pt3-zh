# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P85：4-DRL Lecture 3- Q-learning (Basic Idea) - AI算法工程师Future - BV1ruqABeEFX

没有的话，我们就来讲一下q learning，好。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_1.png)

这个q learning是什么呢，我们等一下呢会简单的介绍一下q learning。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_3.png)

那其实在machine learning那门课里面，其实也简单的介绍过q learning了，那不过今天就算是在很快的复习一下，那接下来呢会讲一些q learning的TM，可是之前没有讲过的。

然后呢会讲说q learning呢，怎么样用在continuous的action上。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_5.png)

好，我们就先从q learning的简介开始说起，那我们说q learning这种方法，它是value base的方法，在value base的方法里面，我们认的并不是policy。

我们并不是直接认policy，我们直接我们要认的是一个CRITIQUIT，并不直接采取行为，他想要做的事情是评价现在的行为有多好，或者是多不好，只能说是pretty，并不直接采取行为。

他是说假设我们有已经有一个ACORP，那quit的工作就是来评价说这个app拍，他做的有多好或者是多不好，举例来说，有一种actor呢叫做state value的function。

这个state value function意思就是说假设现在的actor叫做拍，拿这个拍跟环境去做互动，拿拍跟环境去做互动的时候，现在假设拍这个艾特他看到了某一个stay s。

那如果在玩RITA游戏的话，stay s指的是某个画面，看到某一个画面，某一个cs的时候，接下来一直玩到游戏结束，累积的reward的期望值有多大。

late cumulated the reward expectation有多大哦，所以V拍啊，它是一个function，这个function呢它是吃一个肺当做input。

然后他会offer a scala，这个scale代表说现在拍这个actor，他看到cs的时候，接下来预期到游戏结束的时候。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_7.png)

他可以得到多大的value，我这边就举一个例子。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_9.png)

假设你是玩space invader的话，也许这个state这个S这个游戏画面，你的VPONS会很大，因为接下来还有很多的怪可以杀。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_11.png)

所以你会得到很大分数，一直到游戏结束的时候，你仍然有很多的分数可以吃。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_13.png)

那在这个case也许你得到的V拍就很小，因为一方面剩下的怪也不多了。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_15.png)

那再来就是现在因为那个防护罩，这个红色的东西，防护罩啊，那个防护罩已经消失了，所以可能很快就会死掉，所以接下来得到的预期的reward就不会太大。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_17.png)

那这边需要强调的一个点是说。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_19.png)

当你在讲这个quit的时候，你一定要注意quit都是绑一个actor的。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_21.png)

就CRITTY，他并没有办法凭空去evaluate个state的好坏，而是它是它所evaluate的东西，是在given某一个state的时候。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_23.png)

假设我接下来互动的actor是T。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_25.png)

那我会得到多少reward，因为就算是给同样的stay，你接下来的拍不一样。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_27.png)

你得到rework也是不一样的，比如说在这个case虽然假设是一个正常的拍，他可以杀很多怪，那假设他是一个很弱的拍，他就站在原地不动，然后马上就被射死了。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_29.png)

那你得到的V还是很小，所以今天这个拍有多大，这个这个V这个这个这个CRITIOUTPUT的值有多大，其实是取决于两件事，一个是stay。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_31.png)

另外一个其实是actor，所以今天你的credit其实都要绑一个actor，他是在衡量某一个actor好坏，而不是general的衡量一个state的好坏好。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_33.png)

这边要强调一下，你这个output，推荐output呢是跟actor呢是有关的。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_35.png)

好，那今天就是举一个例子啦，这个例子是呃阿光跟佐维的互动啊，就是这个这这件事发生在什么地时候呢，这件事发生在夏完弱狮之战的时候，我知大家知不知道这是什么，然后就是啊佐维跟阿光说，这个时候不要下小马不飞。

而是要下大马不飞，这边有个注释告诉你说小马不飞是什么，然后我们就不要管它好了。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_37.png)

阿光说他觉得呃为什么一定要下大马步，回笑下笑下小马步会不错，但是我说因为之前你没有很强，所以下小马不飞是对的，但是现在因为你变得比较强了，所以应该下大马不飞，才能够有比较好的发展啊。

所以今天呢假设左唯是一个critic的话，他的evaluation是比配上他的action，也就是阿光的能力，那如果是以前的阿光，因为他比较弱，所以像大马不亏，接下来可能会犯错。

所以是以前的阿光是actor，假设你的space是下大马不飞的话，你得到的value是小的，假设以假设现在evaluate actor其实是一个变强的，阿光的话，那下大马不飞反而是好的。

那这个例子想要强调的就是呃，你的state value其实是depend on，你的actor，当你的ACOR变的时候，你的state value function的output其实也是会跟着改变的好。

那再来的问题就是怎么衡量这一个state value的function呢，怎么衡量这个PPOFS呢，有两种不同的做法，那等一下会讲说像这种CRIT，它是怎么演变成可以真的拿来额采取action。

那这是等下要讲，我们现在先问的是怎么estimate这些quin好，那怎么STMAV拍的vs呢，有两个方向，一个是用这个monte carlo NC base的方法，如果是NC base的方法。

他非常的直觉，他是他怎么直觉呢，他就是说你就让actor去跟环境做互动，你要量actor好不好，你就让actor呢去跟环境互动给quitting看，然后接下来CRITTY就统计说。

这个item如果看到stay sa，他接下来accumulated reward会有多大。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_39.png)

如果他看到stay sb，他接下来accumulated the reward会有多大，但是因为实际上，你当然不可能把所有的state统统都扫过，不要忘了问你说完啊，TARA游戏的话。

你的state是image，你可能没有办法把所有的state统统扫过，所以实际上我们的这个v po vs它是一个network，它是一个network，对于一个network来说。

就算是input的st从来没有看过的，他也可以想办法估测一个value的值，那但是怎么训练这个network呢，因为我们现在已经知道说，如果在stay sa。

接下来的accumulated的reward就是GA，也就是说今天对这个value function来说，如果input stay sa，正确的output应该是GA。

如果input csb正确的output应该是value GB，所以在training的时候，其实它就是一个regression的problem，regression problem大家应该都知道吧。

这个这个胡乱抠一下，就有它是个regression的problem，你的network output就是一个value，你希望在input sa的时候，oper value跟GA越近越好。

input sb的时候，open value跟GB越近越好，接下把给我退下去就结束了。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_41.png)

这是第一个方法，这是mc base的方法，那还有第二个方法是temporal difference的方法，这个是t d base的方法，那ta base的方法是什么意思呢。

在刚才那个NC base的方法，每次我们都要算accumulated reward，也是从某一个CSA一直玩游戏，玩到游戏结束的时候，你会得到的所有reward的总和，我们这边我在前一个投影片里面。

把它写成GA或GB，所以今天你要apply mc base approach，你必须至少把这个游戏玩到结束，你才能够估测mc base approach，但是有些游戏非常的长。

你要玩到游戏结束才能够update work，你可能根本收集不到太多的资料，他花的时间太长了，所以怎么办，有另外一种TV base的方法，p p p base的方法，不需要把游戏玩到底。

只要在游戏的某一个情况，某一个stay s st的时候，采取action a t得到REWORRT，跳到stay s t加一就可以apply t d的方法，怎么派系列的方法呢，这边是基于以下这一个式子。

以下这个式子是说，我们知道说在stay s st采取某一个action，就就是说我们现在有某一个policy p，假设我们现在用的是某一个policy p，在state s st以后呢。

他会在CST它会采取HAT给我们reward RT，接下来进入CST加一，这就告诉我们说这个cs st加一的value跟state st的value，他们中间差了一下RT哦。

因为你把ST加一得到的value加上这边得到reward，RT就会等于ST得到的value，ST得到value就是RT的value加上ST加一的value。

ST的value就是RT加上ST加一的value，有了这个式子以后，你在training的时候，你要做的事情并不是真的直接去估测V，而是希望你得到的结果。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_43.png)

你得到的这个V呢可以满足这个式子，也就是说你training的时候啊，会是这样train的，你把s st丢到network里面，我看看我这边有没有好，我看看这边有没有写错嗯，没有写错好。

你把s st丢到network里面会得到VOST，你把ST加一丢到你的value network里面，会得到VOST加一，然后这个式子告诉我们，VLFST减VFST加一。

它应该值是RT vs T1减vs t加一，它得到的值应该是RT，然后按照这一样子的loss，希望他们两个相减跟RT越接近越好的loss，劝下去，那对V的参数你就可以把V这个方式认出来。

好诶讲到这边大家有没有什么问题要问的呢，问问的呢要认的啊，大家有什么问题要问的呢，行吗好。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_45.png)

那呃这边是比较一下MC跟TD之间的差别啊，那NC跟TD它们有什么样的差别呢，这个NC它最大的问题就是它的variance很大，因为今天我们在玩游戏的时候啊，它本身是有随机性的，所以GA本身你可以想成。

它其实是一个RANDO的variable，因为你每次同样走到SA的时候，最后你得到的GA其实是不一样的，对不对，你看到他们的stay sa，你最后玩到游戏结束的时候，因为游戏本身是有随机性的。

你怕了你的，那你的那个玩游戏的model本身搞不好也有随机性，所以你每次得到GA是不一样的，那每一次得到GA的差别其实会很大，为什么它会很大呢，因为GA其实是很多个不同的step的reward和。

假设你每个step都会得到一个reward，GA是从被SA开始一直玩到游戏结束，每一个time step的reward和那举例来说，我在右上角就列一个式子，是说哦。

假设本来只有X它的variance是vs，但是你把这个某一个variable乘上K倍的时候，它的VARI就会变成原来的K平方，所以现在这个GA的variance，相较于某一个state的reward。

它会是比较大的，GA的reward，而不是rewards说错GA的variance是比较大的，G的variance相较于某一个state，你会得到的得得得得这个reward。

variance它是比较大的好，那我们来看一下说如果用TD的话呢，用TD的话，你是要去minimize这样子的一个式子，在这中间会有随机性的是R，因为你在s st就算你采取同一个action。

你得到的reward也不见得是一样，所以R其实也是一个random variable，但这个random variable它的variance会比GA还要小，因为GA是很多R合起来。

这边只是某一个R而已，所以G的variance会比较大，R的variance会比较小，但是这边你会遇到的一个问题是，你这个VR不见得估得准，就假设你的这个V呢估的是不准的。

那你apply这个式子认出来的结果，其实也会是不准，所以今天MC跟TD呢，他们是各有优劣，那等下其实会讲一个MC跟TD综合的版本，MC2方法其实是比较少用的好。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_47.png)

那这个图是想要讲一下这个TD呢跟MC的差异啊，这个图想要说的是什么呢，这个图想要说的是说，假设现在我们有某一个quick，他去观察某一个policy拍跟环境互动八个EXO的结，果然有一个actor拍呢。

他就跟环境互动了八次，得到了八次，玩游戏的结果是这个样子，接下来我们要这个quitting去估测state的value，那如果我们看SB这个state它的value是多少。

SB这个队在八场游戏里面都有经历过，然后在这八场游戏里面，其中有六场得到reward，一再有两场得到rewarding，所以如果你是要算期望值的话。

state sb就开到stay sb以后得到的reward，一直到游戏结束的时候，得到的accumulated reward，期望值是3/4，这个非常直觉，但是不直觉的地方是说。

SA的期望的reward到底应该是多少呢，这边其实有两个可能的答案，一个是零，一个是3/4，为什么有两个可能的答案呢，这取决于你用MC还是TD，你用NC跟用TD你算出来的结果是不一样的。

假如你用MC的话，你用MC的话，你会发现说这个SA就出现一次嘛，它就出现一次，看到SA这个state，接下来communulated reward是多少，就是零呢就是零呢。

所以今天SA他的expected reward就是零，但是如果你今天去看TD的话，如果你去看TD的话，他的这个这个呃pd在计算的时候啊，他是要update下面这个式子，然后update下面这个式子。

下面这个式子想要说的事情是呃，因为我们在stay sa得到reward r等于零以后，跳到stay sb，所以stay sb的reward会等于stay sb的reward。

加上在CSA他跳到CSB的时候可能得到的reward，而这个可能得到reward r呢，它的值是多少，它的值是零，而SP的expensive reward是多少呢，他的reward是34。

那SA呢它的reward应该是34，所以有趣的地方是用MC跟TD，你估出来的结果其实很有可能是不一样，就算今天你的quit observe到一样的training data。

他最后估出来的结果也不见得会是一样，那为什么会是这样呢，就是MC跟，那你可能接下来，那你可能问说呃哪一个比较对呢，其实就都对对不对，因为呃今天在SA这边，今天在第一个trajectory sa。

它得到reward0以后再跳到SB也得到与过零，这边有两个可能，一个可能是SA，它就是一个带赛的stay，所以只要有看到SA以后，SB就会拿不到礼物，有可能SA其实影响了SB。

如果是用MONTECARLO的的算法的话，他就会考虑这件事，那把SA影响SB这件事考虑这件考虑进去，所以看到SA以后，接下来SB就得不到rework，所以看到SA后期望的铝沃是零，但是今天看到SN以后。

SB的reward是零，这件事有可能只是一个巧合，这并不是SA所造成，并不是因为SA它是一个带赛的reward，而是因为说额SB有时候就是会得到rewording嘛，这只是单纯运气的问题。

其实平常SB他会得到reward，期望值是3/4，跟SA是完全没有关系的，所以SA假设呃之后会跳到SB那其实得到rework，按照TD来算，应该是3/4，所以不同的方法他有着他考虑了不同的假设。

最后你其实是会得到不同的运算的结果的哦。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_49.png)

那接下来呢我们要讲的是另外一种quit，这种CRITI呢叫做q function啊，它又叫做state action的value function，那我们刚才看到的那个stay function。

它的input就是一个state，它是根据state去计算出，看到这个state以后的CUMULATED，expected accumulated reward是多少。

那这个state action的value function呢，它input不是stay，它是一个stay跟action的pair，它的意思是说在某一个state采取某一个action。

接下来假设我们都使用actor拍得到的，accumulated的reward，他的期望值有多大，那在讲这个q function的时候，有一个会需要非常注意的问题是，今天这个actor拍啊。

在看到stay s的时候，他采取的action不一定是A，大家了解我的意思吗，two function的假设是说，假设在stay s强制采取action a，不管你现在考虑了这个actor拍。

它会不会采取action a，这个不重要，要在stay s强制采取action a，接下来都用actor拍继续玩下去，就只有在cs我们才强制一定要采取action a，接下来就进入自动模式。

让actor呢还能继续玩下去，得到了expected reward，才是KDLESA，那假设你让他看到这个stay的时候，他不见得要去采取A，我们只是强制手动让他一定要去采取action a好。

那q function有两种写法，一种写法是你input就是stay跟action，那output就是一个scanner。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_51.png)

就跟那个value function是一样，但还有另外一种写法，其实也许是比较常见的写法是这样，你input一个cs，接下来呢你会output好几个value，假设你的actor是discrete。

两对点，action比例会假设你的action是discrete，你action就走三个，可能往左往右或者是开火，那今天你的这个Q方向凹或者三个value，就分别代表。

假设A是向左的时候的q value，AS向右的时候q value，还有A是开火的时候的q value，那你要注意的事情是像这样子的function。

只有discreen actor才能够使action才能够使用，如果你action是无法穷举的，那你只能够用左边这个式子。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_53.png)

不能够用右边这个式子啊，这个是呃那个呃这个是文献上的结果啦，但是在作业41里面了，呃其实Q作业四之二不是要玩这个作业，四之二是玩打砖块啊，但如果是呃作业四之一的这个碰的这个游戏，你apply这个呃。

你去estimate q function的话，那你看到结果呢可能会像是这个样子哦，这个样子这是什么意思呢，他说假设现在在这个state上面，这个画面就是stay在这个st，那我们有三个action嘛。

我们三个action，三个action都是原地不动，向上还有向下，那假设是在这个st，不管是采取这个action，这个action还是这个action。

最后到游戏结束的时候得到的expected reward，其实都差不了多少，因为今天就算是因为球在这个地方，就算你是你向下，接下来你其实应该还来得及救，所以今天不管是采取哪一个action都差不了太多。

但假设现在这个球啊，这个乒乓球它已经反弹到很接近额边缘的地方，这个时候呢你采取向上，你就才能够得到positive reward，才接得到球，如果你站在原地不动或向下的话，接下来都会miss掉这个球。

你得到的reward就会是负的啊，这个K也是一样，球很近的，所以一定要向上，那接下来呢球被反弹回去，这时候采取哪一个action呢，就都没有差了，这个是spaction value的一个例子。

是在文件上截下来的，是那个大家都应该知道说deep reinforcement learning，最早的受到大家重视注意的一篇paper，就是这个deep m啊，发表在neural上的那个paper。

就是用DQN可以做啊，玩阿塔瑞游戏可以痛电人类的。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_55.png)

那个是那篇配合上的一个图，就是我那今天要讲的是说，虽然表面上我们任意一个q function，它只能够拿来评估某一个X拍的好坏，但是实际上只要有了这个q function。

我们就可以做reforcement learning，其实有这个Q方式，我们就可以决定要采取哪一个action，它的大原则是这样，它大原则是这样，假设你有一个初始的actor，也许一开始很烂。

所以积累也没有关系，初始的actor叫做排，那这个拍呢跟环境互动会collect data，接下来呢你任意一个拍这个actor的q value，用拍这个呃，你去衡量一下，拍这个actor。

他在某一个state强制采取某一个action，接下来用猜这个policy会得到的expected the reward，那可以用TD，也可以用NC都是可以的，你认出一个Q方式以后。

等下我接下来会细讲的一个神奇的地方，就是只要认得出某一个policy plot to function，就保证你可以找到一个新的policy，这个policy叫做hip这个py Python。

他一定会比原来的PAIPR好，那等一下会定义说什么叫做好，所以这边神奇的地方是，假设你只要有一个q function，你有某一个policy p，你根据那个policy拍认出那policy派和Q方选。

接下来保证你可以找到一个新的policy叫做pine，他一定会比嗨还要好，哎你今天找到一个新的拍拍，他一定会比拍还要好，以后你把原来的拍用拍派取代掉，再去找他的Q，然后再去呃呃这得到新的Q以后。

再去找个更好的policy，然后一这个循环一直下去，你的policy就会越来越好。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_57.png)

好那今天这边呢哦我们讲完这一页，我们就下课，这一要讲的是什么呢，这一页就是要讲说我们刚才讲的到底是什么，首先第一个要定义的是什么叫做比较好，我们说拍出来一定会比拍还要好，什么叫做好的。

这边所谓的好的意思是说，对所有可能的state s而言，拍的对同的cs而言，拍的value function一定会小于pine的value function，也就是说我们走到同一个cs的时候。

如果拿拍继续跟环境互动下去，我们得到的reward一定会小于用拍快，跟环境互动下去得到rework，所以今天不管在哪一个state，你用拍point去做interaction。

你得到的expected reward一定会比较大，所以拍point是比拍还要好的一个呃，呃pacy好，那有了这个Q以后，怎么找这个派派呢，那这边的机构这边的构想非常简单，事实上这个派派是什么。

这个派派就是，如果你根据以下的这个式子去决定你的action，把根据以下式子去决定的，action的这个步骤叫做拍拍的话，那这个拍拍一定会比拍还要好，而在下一页会有证明好，那这个是什么意思呢。

这个意思是说，假设你已经认出拍的Q方式，你已经认出拍的Q方式，接在某一个state s，你把所有可能的action a都一一带入这个q function。

看看说哪一个A可以让q function的value最大，那这一个action就是拍快会采取的action，那这边要注意一下，今天在given这个cs，我们刚才有讲过Q方向的定义，given这个cs。

你的PARTICIP并不一定会采取action a，它不一定会采取action a，今天是given某个STS强制采取ha，用pg去互动下去得到的expected reward，才是这个Q方向的定义。

所以在state s里面不一定会采取action a，我们强调了在cs里面不一定会采取action a哦，所以今天呢今天假设我们用这个pipeline，它采stay s采取action a跟拍。

所谓采取action是不一定会一样的，然后派派所采取action会让他得到比较大的，比如好，所以实际上啊根本就没有一个所谓的policy，叫做pipeline，Fil pipeline。

其实就是用q function推出来的，所以并没有另外一个network决定派派怎么interaction，我们只要Q就好，有Q就可以找出拍派，那这边有另外一个问题是我们等一下会解决的。

就是在这边要解一个arg max版本，所以A如果是continuous就会有问题，如果是DISCREENA走三个选项，一个一个带进去，看谁的Q最大没有问题，但如果是continue。

只要解arc max power你就会有问题，但这个是呃之后才会解决的好，那我们就在这边呢休息10分钟。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_59.png)

好那接下来啊，下一页投影片想要跟大家讲的是说。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_61.png)

为什么用这个q set up这个Q方式所决定出来的，pipeline一定会比拍还要好，所以下一页是要证这件事，但下一页的证明，假设你觉得你没有办法follow的话，其实就算了。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_63.png)

这样你就只要记得这个结果就可以了，好下一个投影面是要证的，就是这样啊，假设现在呢我们有个pass叫拍拍，它是由Q拍决定的，我们要正说对所有的cs而言，V拍pine一定会比V拍还要大，这件事怎么证呢。

这边式子是这样，我们先把B拍写出来，先把D拍写出来，那D拍这个式子啊会等于q plos pdle base哦，假设你在state s这个地方，你发了拍这个actor，他会采取的action。

也就是pdle base，那你算出来的Q拍会等于V拍，之所以Q拍不记之前以general而言，Q拍不见得等于V拍，是因为这一个action不见得是拍龙，那这个action如果是拍到vs的话。

Q拍是等于一拍的好，然后呢，今天呢q po s po max一定会小于等于q pile of s，AA取最大的那一个，对不对，因为这边是某一个action。

这边是所有action里面可以让Q最大的那一个action，所以今天这一项一定会比它大，那我们知道说这一项是什么，这一项就是这个Q拍of sa，然后A是什么，A就是开派的，因为今天派派OSS。

它欧布的A就是可以让Q派LOS最大的那一个，所以今天这个式子可以写成Q派，等S还拍了好，那这边我们就知道说VPOBS，他一定小于等于q po s hipine office。

也就是说你在某一个state，如果你按照policy拍一直做下去，你得到的reward一定会小于等于你在现在这个cs，你故意不按照拍所给你指示的方向，你故意按照拍派的方向走一步。

但只有在只有第一步是按照派派的方向走，只有在stay s这个地方，你才按照开派的方向走，开派的指示走，但接下来就按照拍的指示走，虽然只一步之差，但是我们可以按照上面这个式子资料说。

这个时候你得到reward只有一步之差，你得到的reward一定会比完全发了，拍得到的reward还要大，那接下来eventually，你想要证的东西就是这个Q派of s派派。

LOFX会小于等于V派派的分，也就是说只有一步之差，你会得到比较大的reward，那假设每步都是不一样的，每步通通是follow拍拍，而不是拍的话，那你得到的reward一定会更大，就这样。

那直觉上想起来是这样子的，但如果你要用数学数学式把它写出来的话，略显麻烦，但是也呃也没有很难，这只是比较呃繁琐而已，怎么写呢，你可以这样写，我们现在呢在这个Q拍这个式子怎么写啊，Q拍这个式子。

它的意思就是说我们在state s t我们会采取action at，接下来会得到reward RT加一，然后跳到嗯sin s t加一，这边有一个地方啊，我觉得我写的不太好，我觉得这边应该写成RG。

跟我之前的那个notation感觉不太一致啊，但这边写成了RT加一好，因为我们这个其实都是可以在文献上，有时候有人会说在CST的筛选，action a t得到reward叫RT加，有人会写成RT。

但T4其实都是一样的啊，其实都是一样的好，这cs采取按照开派采取某一个HAT得到reward，RT加一，然后接下来看到state s t加一，然后我们这边呢是state s t加一。

根据拍这个actor所估出来的value，上面这个式子等于下面这个式子，这边要取一个期望值，因为在同样stay采取他的action里得到的reward，还有会跳到stay，不见得是一样的。

所以这边需要取一个期望值，这一项啊会小于等于下面这个式子，为什么这一项就等于小于等于下面这个式子呢，因为我们上面已经讲过说V拍了呗，一定小于等于q po s pt，也就这边VPOST加一。

一定会小于等于QPOST加一，TPOST加一，也就是也就是说现在你一直follow拍，跟某一步发low拍，拍接下来的发low拍比起来某一步发low拍拍得到，如果是比较大好，那这一个式子啊就可以写成下面。

就可以写成下面这个式子，因为Q拍这个东西可以写成RT加二，加上ST加二的value，然后接下来呢你再把这个式子，再你再把B拍小于等于Q拍S派派，LOVEX这件事情再带进去。

然后一直算算算算到底算到EPISOO结束，那你就知道说VPOFX会小于等于B拍拍off啊，这反正呃这边假设你没有办法follow的话，总之想要告诉你的事情是说。

你可以estimate某一个policy的bq function，接下来就一定可以找得到另外一个policy叫做拍拍，它一定比原来的policy还要更好。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_65.png)

好那我们讲一下那个呃target呢，我们讲一下，接下来呢在q learning里面，typical你一定会用到的tip，还有几个tip，第一个是你会用一个东西叫做target network。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_67.png)

什么意思呢，我们在认Q方程的时候，你也会用到TD的概念，那怎么用TD的概念呢，就是说你现在收集到的data是说在cs st，你采取HMAT以后，你跳到你得到reward RT。

然后跳到stay s t加一，然后呢今天根据这个q function，你会知道说QPLESTAT跟QPLEST加一，TOFST加一，他们中间差了一下，就是RT哦，所以你在learn的时候，你会说啊。

我们有这个q function，input s t a t得到的value跟input s t加一拍，ST加一得到的value，中间我们希望它插了一个RT，这跟刚才讲的TT的概念是一样。

但是实际上在论的时候，你会发现说这样in general而言，这样的一个方式并不好论，为什么，因为假设你说这是一个regression的problem，这是你network的output。

这是你的target，你会发现你的target是会动的，但是你但是你要implement这样的training，其实也没有问题，对不对，就是呃你在做back propagation的时候。

这个model它的参数会被update，这个model参数会被update，然后同同个model，所以呃你会把两个update的结果加在一起，它们是同一个model，所以两个update结果会加在一起。

但是实际上在做的时候，你的圈里会变得不太稳定，因为假设你把这个当做你的model output，这个当做target的话，也会变成说你要去fit的target，它是一直在变的。

那这种一直在变target的，这这这这种TRA力其实是不太好称，所以实际上怎么做呢，实际上你会把其中一个Q，通常是你就选择下面这个Q把它固定住，也就是在training的时候。

你并不update这个Q的参数，你只update左边这个Q的参数，而右边这个Q的参数它会被固定住，那我们叫它target network，他负责产生target，所以叫做target network。

因为target network是固定的，所以你现在得到的target也就是RT，加上QPOST加一，POST加一的值也会是固定的好，那我们只调左边这个network的参数。

那假设因为target network是固定的，我们只条左边network参数，它就变成是一个regression的版本，我们希望我们的model output，它的值跟你的目标越接近越好。

因为minimize他的means，quare error和minimize他们的l two的distance，那这个东西就是regression，然后在实作上呢，你会把这个q update好几次以后。

再去把这个target network用update过的Q去把它替换掉，在train的时候先他逮他好几次，然后再把它替换掉，但他们两个不要一起动，他们两个一起动的话，你的结果会很容易坏掉。

这样大家呃听得懂我的意思吗，这个地方大家有问题要问的吗，哎你说你说会记住那个哦，对所以所以今天转一开始这两个network是一样的嘛，对不对，一开始，然后接下来在train的时候，你会把它fix住。

然后你只调你只调这个，你在做gradient descend的时候，只调左边这个network参数，那可能update，比如说100次以后，才把这一个参数复制到右边去，把它盖过去，那把它盖过去以后。

你这个target的value就变了，就好像说你今天本来在做个regression的problem，来劝劝劝，把这个regression problem的loss压下去以后。

接下来你把这边的参数把它copy过去以后，你的差距就会就变掉了，你output tb就变掉，那接下来你就要重新再TRA样子好，这样大家有问题吗，一起坐一起，哎他其实不会变成零，为什么呢。

因为首先呢呃他们的input是不一样，同样的function，那这边input是ST跟T，这边input是ST加一跟呃，在ST加一会采取的action po s t加一，因为input不一样。

所以它欧姆的值是会不一样，所以光这一项跟这一项的值就会不一样，然后今天再加上RT，所以它们的值就会更不一样，但是你希望说你会把这两项的值，把它把它拉近样子，要把他拉进好，这样大家还有问题要问吗。

好了大家OK的话，这个是第一个你会用到的tip啦。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_69.png)

好第二又会用到的tip呢是exploration，我们刚才讲说当我们使用q function的时候，我们的policy是怎样，我们policy完全depend on那个q function。

他说given某一个state，你就穷举所有的A看哪个A可以让q value最大，它就是以采取的policy，他就是采取的action，那其实这个跟PARAGGRADIENT不一样。

在做policy gradient的时候，我们的output其实是stochastic的，对不对，我们output action的distribution。

根据这个action的distribution去做sample，所以在py gradient里面，你每次采取action是不一样的，是有水平性，那像这种Q方式，如果你才学action总是固定的。

会有什么问题呢，你会遇到的问题就是，这不是一个好的收集data的方式，为什么这不是一个好的收集data的方式呢，因为假设我们今天真的要播某一个哎，我这边应该要就说某一个state可以采取action。

A one a two a3，我这边应该写a one a two a3，但我忘了加了，我忘了加了好，今天你要估测在某一个state采取某一个action，会得到的q value。

你一定要在那一个state采取过那一个action，你才估得出他的value，对不对，如果你没有在那个stay采取过那个action，你其实估不出那个value的呃。

呃一当然如果是用deep的network，就你的Q方向其实是一个network的话，这种情形可能会比较没有那么严重，但是in general而言，假设你Q方向是一个table，没有看过的。

Stay action pair，他就是估不出值来，但they work也会有一样的问题，就是只是没有那么严重，但也会有一样的问题，所以今天假设你在某一个state action。

a one a two a3都没有采取过，那你估出来的s a one s a two，SA3的q value可能就都是一样的，就都是一个初始值，比如说零。

但是今天假设你在STX里simple过某一个action a two了，那simple到某一个action a two，它得到的值是positive reward。

那现在Q到sa two就会比其他的action都要好，那我们说今天在采取action的时候，就看出谁的tube value最大就采取谁，所以之后你永远都只会sample到a two。

其他的action就再也不会被做了，所以今天就会有问题，就像说你进去一个餐厅吃饭，人家餐厅都有个菜单，那些你都很难选，你选到某一个，你今天点了某一个东西以后，接下来你可能就不会先下次再去吃的时候。

你就会再点一样东西，只点了某个东西，比如说椒麻鸡，你觉得还可以，接下来你每次去就都会点椒麻鸡，就再也不会点别的东西了，但你就不知道说别的东西，是不是会比椒麻鸡还要好吃，就是了，诶这个是一样的问题。

但如果你今天没有好的SPRATION的话，你在training的时候，你就会遇到这种问题，举例来说，举一个实际的例子，假设你今天是用那个呃to learning来玩，比如说sliver I/O。

我在玩C和IO的时候，你会个蛇，然后它在环境里面就走来走去，然后就吃到呃猩猩，他就加分好了，今天假设这个游戏一开始他采取往上走，然后就吃到那个星星，他就得到分数，他就知道说嗯往上走是positive。

接下来他就再也不会采取往上走以外action了，所以接下来就会变成每次游戏一开始，他就往上冲，然后就死掉，再也做不了别的事这样，所以所以今天呃，所以今天要需要有exploration的机制。

需要让machine知道说，虽然a two，这是根据之前sample的结果，好像是不错，但你至少偶尔也试一下a one跟A3，搞不好，他们更好，也说不定，那有两个方法解决这个问题，一个是X中归零。

X中归零，意思是说我们有一减X9的几率，通用X9就设一个很小的值啊，所以一减X总可能是得90percent，也就90percent的几率，完全按照Q方程来决定action，但是你有十和三的几率。

你是随机的，但通常在石座上，ACCO嘛会随着时间递减，也就是在最开始的时候，因为还不知道哪个action是比较好的，所以你会花比较大的力气在做expo，那接下来随着training的次数越来越多。

已经比较确定说哪一个Q是比较好的，你就会减少你的formation，要把X用的值变小，主要根据Q方向来决定，你的action比较少做render啊，这是eston grading。

那还有另外一个方法叫postman exploration，这个方法就比较像是那个PAYGRADIENT，在PARSEGRADIENT里面。

我们说network output是一个根据probability的，二，根据H3，action play上面的一个probability distribution。

再根据probability distribution去做sample，那其实你也会可以根据q value去定一个probability distribution。

你可以说假设某一个action他的q value越大，代表它越好，那我们采取这个action的几率就越高，但是某一个action它的q value小，也不代表我们不能够try try，看说它呃好不好用。

那我们所以有时候我们也要踹出，看那些q value比较好的action，那怎么做呢，因为q value它是有正有负的，所以你要把它弄成一个几率，你可能就先取exponential。

然后再做normalize，然后把呃呃Q到msn is for nature，在做normalize以后的这个几率啊，就当做是你在决定action的时候，sample的几率。

这样你这样距也可以达到formation来请坐，哦Q1开始吗，就是其实在实作上啊，你那个Q是个开货，所以你有点难知道，说哎哎今天在一开始做network的output，A到底会长什么样。

但是你其实可以猜测说，假设你开始没有任何的training data卡，你的参数是随机的，那given以某一个stay s，你的不同的A的output的值可能就是差不多的。

所以一开始Q我们SA应该是会倾向于是uniform，比如在一开始的时候，你这个possibility没有算出来，他可能是比较uniform的，哦你是说他实际上的值算哦，不会不会。

就是假设你今天你的值通通，比如说通通都是一啊，你的值通通都是二，你的值通通都是100套，这个式子以后算出来的结果会是一样的，对不对，好诶这样子大家还有什么问题要问呢。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_71.png)

好没有的话，我们就呃请我们就继续，那还有第三个你会用的tip啊，这个tip叫做replay buffer，这replay buffer的意思是说，现在我们会有某一个policy拍去跟环境做互动。

然后他会去收集data，我们会把所有的data呢放到一个buffer里面啊，那buffer里面就排了很多data，那你buffer你看会设比如说5万，然后里面可以存5万笔资料，每笔资料是什么。

每笔资料就是记得说啊，我们之前在某一个sps st采取某一个action at，接下来我们得到了reward RT，然后接下来跳到state s t加一，就每笔资料就是这样好。

那你用排序跟环境互动很多次，把所有收集到的资料，通通都放到这个replay buffer里面，我都放到replay buffer理念哦，那这边要注意的事情是呃，这个replay buffer啊。

它里面的experience可能是来自于不同的沙拉，就是你每次你拿拍去跟环境互动的时候，你可能只互动1万次，然后接下来就更新你的拍了，但是你的这个呃buffer里面你可以放5万笔资料。

所以那5万笔资料他们可能是来自于不同的policy，那这个buffer只有在他装满的时候，才会把旧的资料丢掉，所以这个buffer里面它其实装了很多不同的policy。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_73.png)

所计算出来的所不同的policy的experience，好，那呃接下来啊你有了这个buffer以后，你做的事情你是怎么劝这个Q的吗，构的呢，你是怎么估这个Q的function的呢，你的做法是这样。

你会iteratively trans，这q function在每个iteration里面，你从这个buffer里面随机挑一个batch出来，就就跟一般的network training一样。

你从那个training data set里面去挑个batch出来啊，就simple个batch出来，里面有100experience，再根据这把experience去update q方式。

就跟我们刚才讲的那个td learning啊，要要有一个target name was我是一样的啊，你去simple1堆batch，simple一个batch的data sample。

一堆experience，然后再去UPDATA的平方，我这边其实有一个东西你可以稍微想一下，你会发现说实际上当我们这么做的时候，它变成了一个of policy的做法，对不对。

因为现在本来我们的Q是要观察拍摄的action，他的value，但实际上存在你的replay buffer里面的这些experience，不是通通来自于拍，对不对。

有一些是过去的其他的拍所遗留下来的experience，因为你不会拿某一个拍，就把整个buffer装满，然后拿去圈q function。

这个拍子是simple1些data data塞到那个buffer里面去，然后接下来就让Q去train，所以Q在sample的时候，它会sample到过去的一些资料，但是这么做到底有什么好处呢。

这么做有两个好处，第一个好处是，其实在做reinforcement learning的时候，往往最花时间的step是在是跟环境做互动，你就劝劝劝network反而是比较快的，因为GPU圈其实很快。

真正花时间往往是在跟环境做互动，先用replay buffer，你可以减少跟环境做互动的次数，因为今天你在做training的时候，你的experience不需要统统来自于某一个policy。

一些过去的policy，他所得到的experience可以放在buffer里面被使用，很多次，被反复的在利用，这样让你的这个sample到experience的利用，是比较EFFICI。

那还有另外一个理由是，你记不记得我们说在train network的时候，其实我们希望一个batch里面的data越diverse越好，如果你的batch里面的data通通都是同样性质的。

你劝下去其实是容易坏掉的，对不对，不知道大家有没有这样的经验，如果batch里面都是一样的，Data，确实说performance是会比较差的，我们希望batch里面的data越窄，verse越好。

但如果你今天你的这个buffer里面的那些experience，它通通来自于不同的policy的话，那你得到的结果，你sample到的一个batch里面的data，会是比较diverse的。

但是接下来你会问的一个问题是，我们明明是要观察拍的value哇，我们要量的明明是拍的value，瓦里面混杂了一些不是拍的experience，到底有没有关系，有没有关系，但一个很简单的解释是说啊。

也许这些不同的拍也没差那么多了，所以也没有关系，但是你仔细想一想，这一件事情其实是没有关系的，这并不是因为过去的拍跟现在的拍很像，虽然过去的拍没有很像，其实也是没有关系的。

就这个点这个就留给大家回去想一下，说为什么会这个样子，今天主要的原因是，因为我们并不是去simple一个trajectory，我们只sample了一笔experience。

所以跟我们是不是of policy这件事是没有关系的，就算是of policy，就算是这些experience不是来自于拍，我们其实还是可以拿这些experience来估测。

QPOBA这件事有点难解释啊，不过你就记得说呃。

![](img/bfffb4cd647ef3cf4d38c9da7911d03a_75.png)

replay buffer这招其实是在理论上也是没有问题的，好那这个就是typical的，一般的正常的q learning的演算法，好，这个演算法是这样。

我们说我们需要一个target network嘛，所以一开始你initialize的时候，你需要两个network，一个是Q，一个是QH，那其实QA就等于Q了。

一开始这个target network和你target的q network，跟原来q network是一样好了，在每一个ACISSO就你拿你的那个agent，拿你的这个ACER呢去跟环境做互动。

那每一次在每一次互动的过程中，你都会得到一个state s t，一个游戏的画面，那你会采取某一个action n a t，那怎么知道参与哪个action at呢，你就根据你现在的Q方程。

但是要记得你要有exploration机制，比如说你用forcement exploration，或abs on creted的exploration，有一点exploration机制好。

那接下来你得到reward RT，然后跳到stay s t加一，那现在可能到一笔data，这笔data是STATRTST加一，你把这笔data就塞到你的buffer里面去，那如果buffer满的话。

你就把一些旧的资料再把它丢掉好，那接下来呢你就从你的buffer里面呢去sample data，那你sample到的是SIAIRISI加一，这笔data跟你刚放进去的不见得是同一笔，懂吗。

你你你你另外你把这笔data a塞到buffer里面，再到buffer里面去抽DA，抽出来并不是同一笔，你只可能抽到一个旧的也是有可能的，那在这边另外要注意的事情，就是我这边notation不太好写啊。

其实你sample sample出来不是一笔data，sample出来的是一个batch的贝塔，sample一个batch出来sample100experience出来好。

你sample这100experience之后，接下来你要做的事情就是计算你的tin，根据你sample出来的data呢，假设你sample出这么一笔data，根据这笔data去算你的MARIN。

你的target是什么呢，target要记得要用target network，也就是q head来算，我们用q head来代表target network好，那ti是多少呢。

TARIN就是RI加上q had si加1AA是什么A，就是看说现在哪一个A，可以让这个q head的值最大，你就选那一个A，因为我们在这边呢在stay a si加一会采取的action a。

其实就是那个可以让呃呃，two value的值最大的哪一个A这样子好好，那接下来呢我们要update那个呃Q的值，那它就把它当成个regression problem，希望Q到我们SIIAI。

跟你的target呢越接近越好好，然后今天假设这个update已经update了呃，某一个数末次，比如说C次，有的就设一个100，C等于100，那你就把q head设成Q，然后就就这样。



![](img/bfffb4cd647ef3cf4d38c9da7911d03a_77.png)