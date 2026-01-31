# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P84：3-DRL Lecture 2-  Proximal Policy Optimization (PPO) - AI算法工程师Future - BV1ruqABeEFX

好好好，各位同学大家好，那我们开始上课吧，好那呃，今天的规划是这样呃，嗯怎么建的好啊，今天的规划是这样，我们先讲呃PPO啊，这个是作业41用得到的东西，然后接下来讲呃q learning呃。

这个作业四之二用到的东西，然后最后助教会来讲一下作业42好，那上周我们做的事情是复习了一下policy，gradient好，那我们今天要讲的事情呢，是PARSEGRADIENT的一个变形，就是PPO。



![](img/db6658133db27bd03532a790377cbc37_1.png)

那上周已经讲过说PPO是现在这个呃，Open ai default，Reinforcement，learning algorithm好，那在讲PPPL之前呢。

我们要讲on policy和of policy。

![](img/db6658133db27bd03532a790377cbc37_3.png)

这两种training方法的区别好。

![](img/db6658133db27bd03532a790377cbc37_5.png)

那什么是on policy，什么是of policy呢，我们知道说在reinforcement learning里面，我们要认的就是一个agent。



![](img/db6658133db27bd03532a790377cbc37_7.png)

那如果我们今天拿去跟环境互动的那个agent，跟我们要LEAR的agent是同一个的话，这个叫做on policy，如果我们今天要LEAR的agent，跟看环境互动的agent不是同一个的话。

那这个叫做of policy，就如果比较拟人化一点，你的讲法的话，就是如果今天要学习的那个agent，他是一边跟环境互动，一边做学习，这个叫on policy，如果他是在旁边看别人玩。

透过看别人玩来学习的话，这个叫做of policy。

![](img/db6658133db27bd03532a790377cbc37_9.png)

而底下这个是麒麟王的比喻啊，就如果阿光在下棋的话，他自己下自己学。

![](img/db6658133db27bd03532a790377cbc37_11.png)

这个是on policy，如果他在旁边看左为下的话，这个是of policy好，那为什么我们会想要考虑of policy这样子的选项呢，让我们来想想看我们讲的这个part。



![](img/db6658133db27bd03532a790377cbc37_13.png)

我之前讲过的policy gradient，其实我们之前讲的policy gradi，它是on policy还是of policy的做法呢。



![](img/db6658133db27bd03532a790377cbc37_15.png)

它是on policy的做法，为什么我们之前讲说，在做这个做这个这个policy gradient的时候呢。



![](img/db6658133db27bd03532a790377cbc37_17.png)

我们会需要有一个agent，我们会需要有一个policy。

![](img/db6658133db27bd03532a790377cbc37_19.png)

我们会需要有一个actor，这个actor呢先去跟环境互动，去搜集资料，收集很多的涛，那根据他收集到的资料，会按照这个policy gradient，式子去update你的这个policy的参数。

这个就是我们之前讲过的policy gradient。

![](img/db6658133db27bd03532a790377cbc37_21.png)

所以它是一个on policy的ALISM，你拿去跟环境做互动的那个policy，跟你要认的那个policy是同一个。



![](img/db6658133db27bd03532a790377cbc37_23.png)

而那今天的问题是这个样子，我们之前有讲过说，因为在这个update的式子里面，其中有一项你的这个expectation啊。



![](img/db6658133db27bd03532a790377cbc37_25.png)

应该是对你现在的policy set up，so sample出来的trajectory操作expectation，所以当你今天update参数以后。

一旦你update参数从SETA变成set up pl，那这一个几率就不对了，你之前sample出来的data就变得不能用了。



![](img/db6658133db27bd03532a790377cbc37_27.png)

所以我们之前就有讲过说，pacy gradient是一个呃会花很多时间来sample data。

![](img/db6658133db27bd03532a790377cbc37_29.png)

air with的，你会发现大多数的时间都在sample sample data。

![](img/db6658133db27bd03532a790377cbc37_31.png)

跟你a app跟环境互动以后，接下来就要update参数，每次update完参数一次，你怎么跑一个呃，你整update参数一次，你只能做一次gradient descent，你整update参数一次。

接下来你就要重新再去collect data。

![](img/db6658133db27bd03532a790377cbc37_33.png)

然后才能再次update参数，这显然是非常花时间的。

![](img/db6658133db27bd03532a790377cbc37_35.png)

所以现在我们想要从on policy变成of policy的好处，就是我们希望说现在我们可以用另外一个policy。



![](img/db6658133db27bd03532a790377cbc37_37.png)

另外一个actor set来换去跟环境做互动，用theta快collect out的data去训练set a，假设我们可以用set up point collect到data去训练。



![](img/db6658133db27bd03532a790377cbc37_39.png)

Set a，意味着说我们可以把set up快collect到的data，用非常多次，你在做这个gradient descent的时候，其次规定ASSA，我要是optimize某个数值。



![](img/db6658133db27bd03532a790377cbc37_41.png)

所以是规定assent，在说规定ASSEND的时候，我们可以执行那个规定，assent好几次我们可以update参数好几次，都只要用同一笔data就好了。



![](img/db6658133db27bd03532a790377cbc37_43.png)

都知道用同一笔data就好了，因为假设现在SETA有能力从另外一个actor，Set up pl，他所sample算data来学习的话，那SA换就只要simple一次。



![](img/db6658133db27bd03532a790377cbc37_45.png)

也比simple多一点的data，让SA去update很多次，这样子就会比较有效率好。

![](img/db6658133db27bd03532a790377cbc37_47.png)

所以怎么做呢，这边就需要介绍一个叫做important sampling的概念，那这个important sampling on概念，不是只能用在IO上，它可以它是一个general的呃。

想法可以用在很多其他地方，我们先介绍这个general的想法好，那假设现在呢你有一个function f f f，那你要计算从P这个distribution sample x，再把X带到F里面得到FX。

你要计算这个FX的遗忘值，那怎么做呢，假设你今天没有办法对P这个distribution做积分的话。

![](img/db6658133db27bd03532a790377cbc37_49.png)

那你可以从P这个distribution去sample1些贝塔xi，那这一个期望值啊，这个f max的期望值啊，就等同于是你sample到的SI，把SI带到FMSI里面，把SI带到FX里面。

然后呢取它的平均值，就可以拿来近似这个期望值，假设你知道怎么从P这个distribution做sample的话，你要算这个期望值，你只需要从P这个distribution做sample就好。

但是我们现在有另外一个问题，那等一下我会更清楚，知道说为什么会有这样的问题，我们现在的问题是这样，我们没有办法从P这个distribution里面sample data。

那等下你可说哎怎么不能从DP这distribution sample data，等下会更清楚说为什么不能从P里面sample data，假设我们不能从p sample data哈。

我们只能从另外一个distribution q呢去sample data q，这个distribution可以是任何distribution，不管它是什么样的distribution，在多数情况下。

等一下讨论的东西都成立，我们不能够从P去sample data，但我们可以从Q呢去sample si，但我们从Q去sample si。



![](img/db6658133db27bd03532a790377cbc37_51.png)

我们不能够直接套这个式子，因为这边是假设说你的SI都是从p sample出来的，你才够套这个式子，从q cl出来的xi套这个式子，你也不会等于左边这一项期望值。



![](img/db6658133db27bd03532a790377cbc37_53.png)

所以怎么办，作为一个修正，这个修正是这样子的，遗忘值这一项啊，其实就是积分FX乘上POFX1X。

![](img/db6658133db27bd03532a790377cbc37_55.png)

然后呢我们现在呢上下都同乘Q的FX，上下同乘QFX不会改变任何事，但是呢我们可以把这个式子写成。

![](img/db6658133db27bd03532a790377cbc37_57.png)

对Q里面所sample出来的X取期望值。

![](img/db6658133db27bd03532a790377cbc37_59.png)

我们从Q里面sample x，然后再去计算FX乘上POFX除以Q和FX。

![](img/db6658133db27bd03532a790377cbc37_61.png)

再去起期望值，然后左边这一项会等于右边这一项，要算左边这一项。

![](img/db6658133db27bd03532a790377cbc37_63.png)

你要从P这个distribution sample x，但是要算右边这一项，你不是从P这个distribution去sample x，你是从Q的distribution去sample。

你从Q这个distribution是sample sample出来以后，再代入FVX乘上PLVXQ的FX，接下来你就可以计算左边这项，你想要算的期望值。

所以就算是我们不能够从P里面sample data。

![](img/db6658133db27bd03532a790377cbc37_65.png)

你想要计算这一项的期望值也是没有问题的，你只要能够从Q里面去sample data，可以带这个式子，你就一样可以计算从P这个distribution，sample x代入F以后所算出来的期望值。

那这两个式子唯一不同的地方是说，这边是从X做sample，这边是从Q做sample，因为它是从Q里面做sample，所以sample出来的每一笔data你需要乘上一个weight，乘上一个weight。

修正这两个distribution之间的差异。

![](img/db6658133db27bd03532a790377cbc37_67.png)

而这个weight就是p of FX的值，除以q of FX的值好，所以QFS其实它是任何distribution都可以。



![](img/db6658133db27bd03532a790377cbc37_69.png)

这边唯一的限制就是你不能够说呃，P的几Q的几率是零的时候。

![](img/db6658133db27bd03532a790377cbc37_71.png)

P的几率不为零，不然这样会没有定义，那假设P的Q的几率是零的时候。

![](img/db6658133db27bd03532a790377cbc37_73.png)

P的几率也都是零的话，那这样P除以Q4有定义的，所以这个时候你就可以apply important，SEMBLY这个技巧，所以你就可以从本来是从P做sample。



![](img/db6658133db27bd03532a790377cbc37_75.png)

换成从Q做sample好，那这个跟我们刚才讲的有什么关系呢，刚才讲的从on policy变成of policy有什么关系呢，而在继续讲之前呢。

我们来看一下important sampling的issue，在理论上你可以把一换成任何的Q，但是在实作上并没有那么容易，实作上P跟Q还是不能够差太多，如果差太多的话，会有一些问题，什么样的问题呢。

虽然我们知道说左边这个式子等于右边，这个式子对你不想想看，如果今天接左边这个是apple max，它的期望值distribution是P。

这边是apple FX乘以P除以Q这期望值它distribution是Q，我们现在如果不是算期望值，而是算variance的话，这两个variance你觉得他会一样吗，诶给你三秒钟的时间想一下。

好你觉得他会一样的同学运动一样，你觉得他不会一样的东西去，好多数同学都觉得他们不会一样，诶没错，他们确实是不一样的，两个random variable，他的命一样，并不代表它的variance一样。

对不对，所以今天你可以实际算一下，af vex这个random variable跟af bx除以P呃。



![](img/db6658133db27bd03532a790377cbc37_77.png)

乘以P除以Q这两个这个random variable，他们的这个这个这个variance是不是一样的。



![](img/db6658133db27bd03532a790377cbc37_79.png)

来计算一下，那我们知道variant of max，是就这个这是个这个公式啊，啊variance of FX是X平方。



![](img/db6658133db27bd03532a790377cbc37_81.png)

Expectation，减掉EOFX的平方好，那你就带一下这个式子，所以今天这一项的呃，various是这个样子啊。



![](img/db6658133db27bd03532a790377cbc37_83.png)

是这个样子，那这一项的variance呢就套一下这个公式，套一下这个公式写成这样，然后今天这一项啊，你其实是可以做一些整理的，这边有一个F平方，这边有一个P平方，这边有一个Q平方，这边又有一个Q好。

所以这边有一个这个额，这边有一个FX的平方，然后有一个p of x的平方，有一个Q到X的平方，那他前面呢是对Q呢取呃，expectation和Q的distribution是expectation，如果。

所以如果你要算积分的话，你就会把这个Q呢把它存到前面去，算期望值，其实这样算的，然后再Q就可以消掉啊，这Q就可以Q就可以消掉了，然后你可以把这个P呢拆成两项，然后就会变成了是对P呢期望值就对。

变成是对P呢取期望值好，那这个是左边这一项，那额右边这一项呢，右边这一项呢，那右边这一项啊，这一项其实就就写在这边，所以这一项其实就是这一项。



![](img/db6658133db27bd03532a790377cbc37_85.png)

然后你把它平方就变成这样，就如果你比较这一项跟这一项的话。

![](img/db6658133db27bd03532a790377cbc37_87.png)

它们差别在哪里，它们差别在第一项是不同的，地下这边多层了，P除以Q这边没有乘P除以Q，这边多乘了P除以Q，所以如果P除以Q差距很大的话，这个时候这一项的various就会很大。

所以虽然理论上它的expectation一样，也就是说你只要对P这个distribution sample过多次，Q这个distribution sample够多次，你得到的结果会是一样的。

但是假设你sample的次数不够多，因为他们的variance是差距是很大的，所以你就有可能得到非常大的差别。



![](img/db6658133db27bd03532a790377cbc37_89.png)

如果这个地方你听的不是很懂的话，那没有关系，这边就是举一个具体的例子。

![](img/db6658133db27bd03532a790377cbc37_91.png)

告诉你说当P跟Q的差距很大的时候，会发生发生什么样的问题，假设这个是P的distribution，这个是Q的distribution，这个是FBAX，这是FBAX好。

那如果我们要计算呃f max的期望值啊。

![](img/db6658133db27bd03532a790377cbc37_93.png)

它的distribution呢是从P的distribution到sample，那显然这一项是负的，对不对，因为呃这个f max在这个区域，这个区域PLFS的几率很高啊。



![](img/db6658133db27bd03532a790377cbc37_95.png)

只要simple的话都会sample到这个地方，而MV在这个区域是负的，所以理论上这一项算出来会是负的好，接下来我们改成从Q这边做sample，那为Q呢在右边这边的几率比较高。

所以如果你simple点不够的话，那你可能都只sample到右侧，如果你都只sample到右侧的话，你会发现说哎如果只针如果只sample到右侧的话，算起来右边这一项搞不好，还应该是正的，对不对。

因为你这边sample到这些点，然后你去计算他们的f vs p除以Q都是正的啊，所以你sample这些点他们都是正的，所以你取期望值以后呢也都是正的，但为什么会这样，那是因为你sample的次数不够多。

因为假设你simple次数很少，有人能simple到右边这边，但左边这边几率虽然很低，但也不是没有可能被simple到。



![](img/db6658133db27bd03532a790377cbc37_97.png)

就假设你今天好不容易终于sample到左边的点，因为左边的点呢P跟Q是差很多的，P跟Q差很多，但是Q很小，P很大，所以今天呢f max好不容易sample到一个负的，这个负的就会被存一个非常巨大的胃。

就可以平衡到平衡掉刚才那边一直sample到呃，positive的value的情况，最后eventually你就可以算出说这个期望值，这这个这一项的期望值终究还是负的。



![](img/db6658133db27bd03532a790377cbc37_99.png)

但问题就是这个前提是你要sample够多次，这件事情才会发生，但有可能sample次数不够，那左四和右四就有可能有很大的差距。



![](img/db6658133db27bd03532a790377cbc37_101.png)

所以这是important sampling的问题，好，那现在要做的事情就是把intention这件事啊，用在of policy的case。

我要把on policy的training algorithm，改成of policy的training the alisthm。



![](img/db6658133db27bd03532a790377cbc37_103.png)

那怎么改呢，之前那我们是看这个呃，我们是拿sea这个policy去跟环境做互动，Sample to trajectory tower，然后呢计算这个中括号里面这一项，现在呢我们不根据sea。

我们不用sea去跟环境做互动，我们假设有另外一个policy，另外一个policy，它的参数是set up time，他就是另外一个actor，他的工作呢是他要去做demonstration。

他要去他要去示范给你看这个setup pl，他的工作是要去试示范给SA看，他去跟环境做互动，告诉SA说他跟环境做互动时会发生什么事，然后介词呢来训练theta。

我们要训练的是sea这个model sea派只是负责做demo的。

![](img/db6658133db27bd03532a790377cbc37_105.png)

负责跟环境做互动好，那我们现在，所以我们现在的call他是从set up time sample出来的，不是从sea sample出来。



![](img/db6658133db27bd03532a790377cbc37_107.png)

但我们本来要求的事实是这样，但是我们实际上做的时候是拿setup派。

![](img/db6658133db27bd03532a790377cbc37_109.png)

去跟环境做互动，所以sample出来掏是从SA派sample出来的，这两个distribution不一样，但没有关系，我们之前说过说，假设你本来是从P做sample，但你发现你不能够从P做sample。

就现在我们说我们不拿SA去跟环境做互动，所以不能做跟P做sample，你永远可以把P换成另外一个Q，然后呢在前在前面呢，在后面这边呢补上一个important the way，所以现在的状况就是一样。

把SA换成SA，换以后要再中括号里面补上一个important way，这important way就是某一个trajectory，T他用SA算出来的几率除以这个trajectory。

它用SA曼算出来的几率。

![](img/db6658133db27bd03532a790377cbc37_111.png)

那这一项是很重要的，因为呃今天你要认的actor。

![](img/db6658133db27bd03532a790377cbc37_113.png)

sea跟setup fine是不太一样的，所以SAF会遇到的状况，会见到的情形跟sea见到的情形不见得是一样的，所以中间呢要做一个修正的项，就像你在电影里面，你会看到说男女主角一遇到的时候。

他们可能就一见钟情，然热情在路上接吻，但是这个死臭生人在日常生活中是不能学的，你只能吃巴掌而已，所以并不是说的demonstration你都可以做到。

你要看一下说这个demonstration是不是你可以做的，然后做一下修正，这样子对。

![](img/db6658133db27bd03532a790377cbc37_115.png)

好所以我们做了一下修正，因为我们现在data不是从set up point sample出来的。

![](img/db6658133db27bd03532a790377cbc37_117.png)

是从sa sample出来的，好，那我们从SA换成SA派有什么好处呢，我们刚才就讲过说，因为现在跟环境互动的是sa fine，而不是SA，所以今天你sample出来的东西。



![](img/db6658133db27bd03532a790377cbc37_119.png)

跟sea本身是没有关系的，所以你就可以让SA快去跟环境做几次做互动。

![](img/db6658133db27bd03532a790377cbc37_121.png)

simple1大堆data以后，SETA可以update参数很多次。

![](img/db6658133db27bd03532a790377cbc37_123.png)

然后一直到赛达可能欠到一定的程度，他背很多次以后，SA不能再重新去做神通好，这就是on policy换成of policy的的这个妙用好，那我们其实上周有讲过说呢。

实际上我们在做这个policy gradient的时候，我们并不是给一整个trajectory套都一样的分数，而是每一个stay action的pa我们会分开来计算，所以我们上周其实都讲过说。

我们实际上update我们的gradient的时候，我们的式子是长这个样子的，而是长这个样子，我们用SETA去，我们用SETA这个actor呢去simple出ST跟AT。

sample出这个state跟action的pa，我们呢会计算这个state and action action的pair，它的advantage就它有多好，那我们像上周讲过。

说这一项呢就是那个accumulated的reward，减掉bias，那如果你忘记的话也没有关系，反正这一项就是估测出来的，他要估测的是现在在stay s t采取HAT，它是好的还是不好的好。

那接下来呢后面会乘上这个log p c r a t，基本ST也就是说如果这一项是正的，就要增加几率，这一项是负的。



![](img/db6658133db27bd03532a790377cbc37_125.png)

就要减少几率好，那我们现在就用了important samply的技术，把on policy变成of policy，那我就把on policy变成of policy，就从SA变成sa plan。

所以现在STAT它不是set up。

![](img/db6658133db27bd03532a790377cbc37_127.png)

跟环境互动以后所sample到的data，它是set a plan。

![](img/db6658133db27bd03532a790377cbc37_129.png)

另外一个actor跟环境互动以后所sample到的data，但是拿来训练我们要调整参数的mod。

![](img/db6658133db27bd03532a790377cbc37_131.png)

那个model是谁的，但是我们有说过说，因为SA派跟SA是不同的model，所以你要做一个修正的项，而这项修正项就是important sely的技术，把STAT用sa sample出来的几率除掉。

STAT用sa five sample出来的几率，那这边其实有一件事情，你们我们是需要稍微注意一下，这边A有一个上标set的代表，说这个是actor sea，跟环境互动的时候所计算出来的A，但是实际上。

当我们今天从SETA换到SETA派的时候。

![](img/db6658133db27bd03532a790377cbc37_133.png)

这一项啊其实你应该改成c a plan，而不是SA，为什么这个A这一项是怎么来的，这一项A这一项是想要估测说现在在某一个state，采取某一个action。

接下来会得到的accumulated reward呃，呃的值减掉baseline嘛，对不对，我们上周我讲过，你怎么估估这项advantage，你就看在这个sts st采取这个action a at。

接下来会得到的reward的总和再减掉贝sin，就是这一项嘛，对不对，这上周有讲过，而之前是sea在跟环境做互动。



![](img/db6658133db27bd03532a790377cbc37_135.png)

所以你观察到的是SA可以得到的滤波，但现在不是SA跟环境做互动。

![](img/db6658133db27bd03532a790377cbc37_137.png)

现在是setup plan在跟环境做互动，所以你得到的这个advantage，其实是根据setup plan所estimate出来的advantage。



![](img/db6658133db27bd03532a790377cbc37_139.png)

这样，但我们现在先不要管那么多，我们就假设这两项可能是差不多的，我们就假设他们是差不多的好，那接下来呢这个STAT呀，这一件事情你可以拆解成呃ST的几率，乘上ATTMST的几率。

然后接下来啊这边需要做一件事情，是我们假设这个当你的model是SA的时候，你看到s st的几率跟你的model是SA快的时候，你看到s st的几率是差不是差不多的啊。



![](img/db6658133db27bd03532a790377cbc37_141.png)

你把它删掉，因为它们是一样的，就可以把它删掉，为什么可以假设它是差不多的，当然你可以找一些理由举例来说，会看到什么stay啊，往往跟呃，你会采取什么样的action是没什么太大的关系的。

就是你比如说你玩不同的ATARI的游戏，那其实你看到的游戏画面都是差不多的，所以也许不同的sea对s st是没有什么影响的，但是有一个更直接的理由就是，这一项到时候真的要你算，你会算吗。

你不觉得这一项其实你不太能算吗，因为因为现在这这四项要怎么算，这项你还要说哦，我有一个参数sea，然后我拿SA去跟环境或说有互动。



![](img/db6658133db27bd03532a790377cbc37_143.png)

算ST出现的几率，这个这个你根本很难算，尤其是你如果input image的话。

![](img/db6658133db27bd03532a790377cbc37_145.png)

同样的s st根本就没有出现过，所以根本就不会出现过第二次啊，所以根本没办法服这一项，所以干脆就无视这个问题，对，然后在这demon s st接下来产生AT这个几率，你是会算的，对不对，这个很好算。

因为你有SA手套，SA这个参数他就是个network，你就把ST带进去，s st就是游戏画面，你把游戏画面带进去，他就会告诉你说某一个stat的几率是多少，对不对。

我们说我们其实有个policy的network，把s st带进去，他会告诉我们说每个AT的几率是多少。



![](img/db6658133db27bd03532a790377cbc37_147.png)

所以这一项啊你只要知道SA参数，知道CA方向。

![](img/db6658133db27bd03532a790377cbc37_149.png)

这个就可以算，那这一项额不能其实不太好算，这就说服自己说这一项其实不太会有影响啊，我们只管前面这个部分就好了，好好。



![](img/db6658133db27bd03532a790377cbc37_151.png)

那，所以现在啊，我们得到了一个新的新的这个objective function，我们得到一个新的objective function。



![](img/db6658133db27bd03532a790377cbc37_153.png)

这一项是那个gradient啊，这一项是gradient，那其实我们可以把GRA从gradient呢。



![](img/db6658133db27bd03532a790377cbc37_155.png)

去反推原来的objective function，怎么从gradient去反推原来的objective function呢，呃这边有一个公式，你可以我们就背一下吧，FMX的GRADI等于FX乘上这个呃。

啊这个这个这个呃log f log f base乘上f base，这一项是这个样子的啦，前面哪有PC的，额不对，好然后下面呢有一个p set up派，然后这边呢有一个方选A。

然后那边呢有一个gradient的log p sa，这样好，然后呢我们看一下这边，那我们说这个FBS乘以gradient log af bs，这个FFX就是PC啦，就当做是apple max哦。



![](img/db6658133db27bd03532a790377cbc37_157.png)

这个是FX，这个是gradient log FX这两项合起来啊，这两项合起来啊，就可以变成gradient，apple就变成gradient t sea。



![](img/db6658133db27bd03532a790377cbc37_159.png)

这样子好，然后接下来呢我们要做的事情，就是这个是gradient的项目，我们要还原说原来没有取鬼点之前的样子，那是什么样子呢，其实就是把这个鬼点拿掉，所以就变成下面这个式子，就变成想就变成下面这个式子。

所以实际上当我们apply important sampling的时候，我们要去optimize的那一个objective function。



![](img/db6658133db27bd03532a790377cbc37_161.png)

长什么样子呢，我妈去optimize那个objective function就长这样。

![](img/db6658133db27bd03532a790377cbc37_163.png)

我们把它写作呃，j theta psa为什么要写这么麻烦。

![](img/db6658133db27bd03532a790377cbc37_165.png)

写JSA派发到theta呢，这个括号里面，SA代表是我们要去optimize那个参数。

![](img/db6658133db27bd03532a790377cbc37_167.png)

thea pr代表什么，set a pr是说我们拿set up pl去做demonstration。

![](img/db6658133db27bd03532a790377cbc37_169.png)

就现在在跟真正在跟环境互动的是set up pl，因set up是跟环境互动。

![](img/db6658133db27bd03532a790377cbc37_171.png)

是set up pl在跟环境互动，然后呢你用set up换去跟环境互动。

![](img/db6658133db27bd03532a790377cbc37_173.png)

sample出s SPA at以后，那你要去计算ST跟T的advantage。

![](img/db6658133db27bd03532a790377cbc37_175.png)

然后呢你再去把它乘上PC的ATDMST。

![](img/db6658133db27bd03532a790377cbc37_177.png)

再除掉p c lby a t given s t，那这两项都是好算的，这一项你是可以从data里面，你可以从这个sample的结果里面去估测出来的，所以这一整项你是可以算的。

那么实际上在update参数的时候，就是按照上面这个式子呢。

![](img/db6658133db27bd03532a790377cbc37_179.png)

update参数好，那所以我们现在做的事情就是，我们可以把on policy换成of policy。

![](img/db6658133db27bd03532a790377cbc37_181.png)

但是我们会遇到的问题是，我们在前面讲important sampling的时候。

![](img/db6658133db27bd03532a790377cbc37_183.png)

我们说important sampling有一个这个issue是什么呢，这个issue是其实你的PC啦跟PC的换不能差太多。



![](img/db6658133db27bd03532a790377cbc37_185.png)

差太多的话，你就important samply就结果就会不好啊。

![](img/db6658133db27bd03532a790377cbc37_187.png)

如果PC啦跟PC达不差太多的话，你真你的这这两个distribution差太多的话。

![](img/db6658133db27bd03532a790377cbc37_189.png)

important samping的结果就会不好，所以怎么避免它差太多呢。

![](img/db6658133db27bd03532a790377cbc37_191.png)

这个就是PPO在做的事情，这PPO虽然如果你看它原始的paper，或者你看TRPPO的前身，TRPO原始的paper的话，它里面写了很多的呃数学式，但他实际上做的事情是怎样呢。



![](img/db6658133db27bd03532a790377cbc37_193.png)

他实际上做的事情就是这样，他说我们原来在of policy的方法里面说。

![](img/db6658133db27bd03532a790377cbc37_195.png)

我们要optimize的是这个objective function，但是我们又说。

![](img/db6658133db27bd03532a790377cbc37_197.png)

因为这个objective function它牵涉到important samply，在说important sampling的时候。



![](img/db6658133db27bd03532a790377cbc37_199.png)

PC啦不能跟对打pl差太多，你做demonstration model跟那个真正的model不能够差太多，差太多的话，你pn center结果就会不好。



![](img/db6658133db27bd03532a790377cbc37_201.png)

所以我们在training的时候多加一个CTRL，这CTRL是什么，这个CTRL是SA跟si sa fine这两个model，他们output的action的kl divergence。



![](img/db6658133db27bd03532a790377cbc37_203.png)

就是简单来说这一项的意思。

![](img/db6658133db27bd03532a790377cbc37_205.png)

就是要衡量说SA跟SA派有多项，然后我们希望在training的过程中，我们认出来的theta跟theta pine越像越好，因为SETA如果跟sa fine不像的话，最后你做出来的结果就会不好哦。



![](img/db6658133db27bd03532a790377cbc37_207.png)

所以在PPO里面呢有两个式子，一方面就是optimize，你要得到的呃，你本来要optimize的东西。



![](img/db6658133db27bd03532a790377cbc37_209.png)

但是再加一个CTRL，这CTRL就是就好像那个REGZATIONTUR样。

![](img/db6658133db27bd03532a790377cbc37_211.png)

在我们在做我们训练的时候，不是有l one跟l two regalization吗，这一项也很像REGALIZATION这样。



![](img/db6658133db27bd03532a790377cbc37_213.png)

REGZATION做的事情，就是希望最后认出来的SA不要跟sea派太不一样。

![](img/db6658133db27bd03532a790377cbc37_215.png)

那PPU有一个前身叫做TRPO，而TRPO写的式子呢是这个样子的，这一项这一项跟呃前面这个这一项嘛是一样的。



![](img/db6658133db27bd03532a790377cbc37_217.png)

它唯一不一样的地方是说，这个control摆的位置不一样，这边是直接把那个control。

![](img/db6658133db27bd03532a790377cbc37_219.png)

放到你要optimize的那个式子里面，然后接下来你就可以用gradient。

![](img/db6658133db27bd03532a790377cbc37_221.png)

ascend的方法去maximize这个式子，但是如果是在TRPO的话。

![](img/db6658133db27bd03532a790377cbc37_223.png)

他是把kl divergence当做control，他希望set a跟SA换个ko divergence，小于一个DOTA，那你知道你在做那种optimization。

如果你用gradient descent base optimization的时候，有constrain是很难处理的，所以你会发现PPO上次助教有讲很多，相信大家应该都没有听懂，那个是很难处理的。



![](img/db6658133db27bd03532a790377cbc37_225.png)

因为就是因为他是他他他他是，他是把这个这这一个ko diversion content。

![](img/db6658133db27bd03532a790377cbc37_227.png)

当做一个额外的control，没有放object里面，所以它很难算。

![](img/db6658133db27bd03532a790377cbc37_229.png)

所以如果你不想要搬石头砸自己的脚的话，你就用PPO，不要用PRPO这样啊。

![](img/db6658133db27bd03532a790377cbc37_231.png)

看文献上的结果是，PPO跟TRPO可能performer差不多。

![](img/db6658133db27bd03532a790377cbc37_233.png)

但是PPO在实作上比TRPO容易得多好，那这边要注意一下，就是这边所谓的kl divergence到底指的是什么。



![](img/db6658133db27bd03532a790377cbc37_235.png)

这边我是直接把kl divergence当做一个function。

![](img/db6658133db27bd03532a790377cbc37_237.png)

它吃的input是sea跟sea p，但我的意思并不是说把SA当做一个distribution。

![](img/db6658133db27bd03532a790377cbc37_239.png)

把sea派当做一个distribution算这两个distribution之间的距离。

![](img/db6658133db27bd03532a790377cbc37_241.png)

我不是这个意思，今天这个所谓的set a跟sa point的距离，并不是参数上的距离，而是他们的behavior上的距离，我不知道大家可不可以了解这中间的差异，就是假设你现在呢有一个model。

还有个model哦，有一个ACOR，它是对的啊，你有一个mode，你有另外一个艾特，它是，所以它的参数是费两派，所谓的参数上的距离，就是啊你算这两个参数，这两组参数有多像。

他们两个都是memo里面的位置，跟白三个多像，可这不是我今天这边所讲的这个这个距离。

![](img/db6658133db27bd03532a790377cbc37_243.png)

我这边所讲的不是参数上的距离，我这边所讲的是他们的行为上的距离。

![](img/db6658133db27bd03532a790377cbc37_245.png)

就是你先带进去一个stay s，先带进去一个stay s，然后然后今天他不是为output一个distribution吗，他output the distribution，他会output一个。

还会对这个action的space好。

![](img/db6658133db27bd03532a790377cbc37_247.png)

注意个，假设你有三个action，三个可能H2布三个词。

![](img/db6658133db27bd03532a790377cbc37_249.png)

三个可能TION叫off put，三个，那我们今天所指持的distance。

![](img/db6658133db27bd03532a790377cbc37_251.png)

则是behavior distance，也就是说给同样的state的时候。

![](img/db6658133db27bd03532a790377cbc37_253.png)

他们output这个这个action，这个action之间的差距。

![](img/db6658133db27bd03532a790377cbc37_255.png)

那这里这两个action的distribution都，他们都是一个几率分布嘛，因为你这刀布通常都腰部，通常都那这是个几率分布，这是个几率分布。



![](img/db6658133db27bd03532a790377cbc37_257.png)

所以就可以计算这两个几率分布之间的，Kl diverge，but不同的state他们的output这两个distribution的hao divergence。



![](img/db6658133db27bd03532a790377cbc37_259.png)

平均起来才是我这边所指的，这两个actor间的KO带，我大家听不听得懂，我那个意思，加可可说唉，那怎么不直接算这个set a和set a派之间的距离，比如说甚至不用配合百分。



![](img/db6658133db27bd03532a790377cbc37_261.png)

就算有万分流TRNO，也许更能够也可以，也可以保证cw和cw快接近呢。

![](img/db6658133db27bd03532a790377cbc37_263.png)

在做reforce learning的时候，之所以我们考虑的不是额参数上的距离。

![](img/db6658133db27bd03532a790377cbc37_265.png)

而是action上的距离。

![](img/db6658133db27bd03532a790377cbc37_267.png)

是因为很有可能对actor来说，参数的变化跟action的变化，不是不一定是完全一致的。

![](img/db6658133db27bd03532a790377cbc37_269.png)

就有时候你参数小小变了一下，他可能output的那个行为就差很多。

![](img/db6658133db27bd03532a790377cbc37_271.png)

或是参数变了很多，但output的行为没什么差别，我真正在意的是这个actor他的行为上的差距，而不是他们参数上的差，所以这里要注意一下，在做PPO的时候。

所谓的ko divergence并不是参数的距离。

![](img/db6658133db27bd03532a790377cbc37_273.png)

而是action的距离，那假设这个你没有听得很懂的话。

![](img/db6658133db27bd03532a790377cbc37_275.png)

我们等一下还有一个p p o two，我们这个是ppp p p o one，它还是略微复杂的，我们来看一下这个p p o one的这个algorithm，他就是这样。



![](img/db6658133db27bd03532a790377cbc37_277.png)

他说呃initial一个policy的参数啊，在哪里，然后在每个iteration里面呢，你要用参数CAKCAK怎么来的，那SAK就是你在前一个training的iteration。

得到的actor的参数，你用SARK呢去跟环境做互动，sample到一大堆的state action appear，然后根据set up开互动的结果，你也要估测一下ST跟AT这个state。



![](img/db6658133db27bd03532a790377cbc37_279.png)

跟h pair它的advantage，然后接下来呢，你就apply p p o的这个optimization of function。



![](img/db6658133db27bd03532a790377cbc37_281.png)

但是跟up after optimization的formulation。

![](img/db6658133db27bd03532a790377cbc37_283.png)

但是跟原来的PARAGGRADIENT不一样，原来PARAGGRADIENT你整update参数update完以后。



![](img/db6658133db27bd03532a790377cbc37_285.png)

你就要重新sample data，但现在不用你拿set up k去跟环境做互动。

![](img/db6658133db27bd03532a790377cbc37_287.png)

sample到这组data以后，你就你就力，你就努力去劝赛达，你可以让sa update很多次，想办法去maximize你的objective function，你让塞达呢update很多次。

那这边set update很多次没有关系，因为我们已经有做important sembly。

![](img/db6658133db27bd03532a790377cbc37_289.png)

所以这个X这些这些experience，这些state action的pair是从C打k sample出来的。



![](img/db6658133db27bd03532a790377cbc37_291.png)

没有关系，SDK update很多次，它跟SAK变得不太一样，也没有关系，你还是可以照样训练SA。

![](img/db6658133db27bd03532a790377cbc37_293.png)

那其实其实就说完了哎其实就说完了，那在呃PPO的paper里面呢，这边还有一个adaptive的ko divergence，因为这边会遇到一个问题，就是这个贝塔呢要设多少。

他就跟那个REGRIZATION一样。

![](img/db6658133db27bd03532a790377cbc37_295.png)

是一个是一个high realization，它前面也要乘一个weight嘛，所以这个hero diversion前面也要成一个weight贝。



![](img/db6658133db27bd03532a790377cbc37_297.png)

但贝塔要设多少呢，呃所以有个动态调整贝塔的方法，那这个调整的方法其实也是蛮直观的啊，在这个直观的方法里面呢，你先设一个kl divergence，你可以接受的最大值，然后假设你发现说你找到你。

optimize完这个式子以后，kl divergence的项太大，那就代表说后面这个PANALYZE，the turn没有发挥作用，那就把beta调大。

那结果那另外你定一个ko divergence的最小值，哎发现说论文OPTIMI完上面这个式子，OK你得到ko diversions比最小值还要小，那代表说后面这一项它的效果太强了。

那你怕他都只弄后面这一项，那SA跟SA可以说一样，这不是你要的，所以你这个时候你就要减少贝塔啊。

![](img/db6658133db27bd03532a790377cbc37_299.png)

所以这个贝塔呢是可以动态调整的，那这个叫做addictive的kl penalty，诶，你解说，啊哦对对，把这个问题问的很好，刚才没有讲的不够清楚，所以实际上你在算这个kl的时候，也是有点麻烦的。

怎么有点麻烦呢，因为这个KL啊，理论上你应该simple1大堆不同的费，然后每个F都丢进去，然后等到然后再算不同的类下，有点偏，再把它举起来嘛，对不对好，那这个不同类那不可能穷举所有不同的类。

这simple是在哪里来的，从你的sample data来，就这样，从你的sample data来，因为在这边会用SA可以去做sample啊，所以他也sample了很多不同的S。

那就把这些不同的S通通带进去，这个ko diversion的式子去算他的不同的，每output的action之间还有爱，那这是你实际上的做法，好啊，讲真大，有问题要问吗。



![](img/db6658133db27bd03532a790377cbc37_301.png)

好如果你觉得这个很复杂，因为什么还要算ko diversion很复杂。

![](img/db6658133db27bd03532a790377cbc37_303.png)

有一个p p o two，p p o two呢，这个它的式子我们就写在这边，他要去maximize的这个object function呢写成这样，它的式子看它里面就没有什么kl了啊，没有kl好。

这个式子看起来有点复杂，但是我们这实际INTEMENT黑啊，这很简单很简单，我们来实际看一下，说这个式子到底是什么意思，这个事很复杂哦。

这边是summation over stay action的pair，那没有问题。

![](img/db6658133db27bd03532a790377cbc37_305.png)

这个是minimize，要就是说这个这边有个大括号，这边有大括号，看到这边有个括号，这边有个括号，而这个括号里面有两项，这是第一项。



![](img/db6658133db27bd03532a790377cbc37_307.png)

这个是第二项，然后NIN这个这个operator，他要做的事情是，第一项和第二项里面选那个比较小的那个，OK好，然后呢第一项比较单纯，第二项比较复杂，第二项前面有一个clip。

这个方选pick这个方程是什么意思呢，pick方程，这个方程的意思是说在括号里面有三项，如果第一项既大于第二项的话，呃对吧，第一项小于第二项的话，那就output1减X咯，D项如果大于第二。



![](img/db6658133db27bd03532a790377cbc37_309.png)

第三项的话，就output1加X了，那X系统是一个hyper parade。

![](img/db6658133db27bd03532a790377cbc37_311.png)

然后two的，比如你就设0。1啊，设0。2啊，也就是说这个指甲这边设0。2的话。

![](img/db6658133db27bd03532a790377cbc37_313.png)

就是说这个值如果算出来小于0。8，那就当做0。8，这个值如果算出来大于1。2，那就当做是1。2好，那这个式子到底是什么意思呢。



![](img/db6658133db27bd03532a790377cbc37_315.png)

我们先来解析一下，我们来看一下这个后第二项这个就好，我们先来看第二项，这个算出来到底是什么样的东西。

![](img/db6658133db27bd03532a790377cbc37_317.png)

第二项这一项算出来的意思是这个样子，假设这个横轴啊是PC啦，除以PC拉K好，横轴是第一项PC啦，除以PC大K纵轴啊，是这个pick这个方式它实际上的输出，那我们刚才讲过说。

如果PCA除以PCAK大于一加XL，那输出就是一加X喽，如果小于一减X总输出就是一减X哦，如果介于一加X中一减X总之间，就是输入等于输出，所以PCA除以PCAK，跟K方程的输出的关系是这样的一个关系啊。

是这样的关系好，那接下来呢我们就加入前面这一项，来看看前面这一项到底在做什么。

![](img/db6658133db27bd03532a790377cbc37_319.png)

而前面这一项呢其实就是绿色的这一条线。

![](img/db6658133db27bd03532a790377cbc37_321.png)

对不对，前面这样就是绿色这一条线PC啦，所以PC拉K就是绿色的这一条线。

![](img/db6658133db27bd03532a790377cbc37_323.png)

但是这两项里面的第一项和第二项，也就是绿色的线跟蓝色的线中间，我们要取一个最小的，我们要取一个最小。

![](img/db6658133db27bd03532a790377cbc37_325.png)

假设今天前面乘上的这个turn a，它是大于零的话，取最小的结果就是红色的这一条线，我就是红色的这一条线。



![](img/db6658133db27bd03532a790377cbc37_327.png)

反之如果A小于零的话，那取红色取最小的以后就得到红色的这一条线。

![](img/db6658133db27bd03532a790377cbc37_329.png)

那这个结果其实非常的直观。

![](img/db6658133db27bd03532a790377cbc37_331.png)

其实非常的直观，所以这个这个事实上看起来有点复杂。

![](img/db6658133db27bd03532a790377cbc37_333.png)

但是improvement起来是蛮简单的，然后呃直想法也非常的直观。

![](img/db6658133db27bd03532a790377cbc37_335.png)

因为今天这个式子想要做的事情，就是希望PC的跟PC的K。

![](img/db6658133db27bd03532a790377cbc37_337.png)

也就你拿来做demonstration的那个model，对，实际上论的model。

![](img/db6658133db27bd03532a790377cbc37_339.png)

最后在optimize以后不要差距太大，那这个式子是怎么让他做到不要差距太大的呢，你要怎么让它做到不要差距太大了呢，再再复复习下，这横轴的意思，就是PC达除以PC达K。

这横轴是PC大除以PC大K如果今天A大于零，也就是某一个state跟action的pair是好的。

![](img/db6658133db27bd03532a790377cbc37_341.png)

那我们想要做的事情，当然是希望增加这一个state跟action pair的几率。

![](img/db6658133db27bd03532a790377cbc37_343.png)

也就是说我们想要让PC大越大越好，但是我们觉得PCA越大越好，没有问题，但是它不可它跟这个SAK的比值，不可以超过一加XC龙，如果超过一加XC龙的话，就没有benefit，就是我们要我们这是红色的线。

是我们的objective function，我们希望我们的objective越大越好，当PC达比PC达K的比值。



![](img/db6658133db27bd03532a790377cbc37_345.png)

我们希望PCR越大越好，但是PCR比PCA可比直。

![](img/db6658133db27bd03532a790377cbc37_347.png)

只要大过一加XL就没有benefit了，所以今天在train的时候，PSA只会被劝到比PCAK它们相除大，1+19，它就会停止，那假设今天不幸的是，PCA比PCAK还要小，PCA比CCAK还要小。

因为我们的目标是要让PCA越大越好。

![](img/db6658133db27bd03532a790377cbc37_349.png)

因为假设这个advantage是正的，我们当然希望PCA越大越好，假设这个action是好的。

![](img/db6658133db27bd03532a790377cbc37_351.png)

但希望这个action被采取的几率越大越好，所以假设是PSA还比PCAK小，那就尽量把它挪大，但只要大到一加X用就好，那负的时候也是一样。



![](img/db6658133db27bd03532a790377cbc37_353.png)

如果今天某一个staction paper是不好的，我们当然希望PC啦把它减小。

![](img/db6658133db27bd03532a790377cbc37_355.png)

假设现在PCA比PCAK还要大，那你就赶快把血量压小。

![](img/db6658133db27bd03532a790377cbc37_357.png)

压小压小，那压到什么样就停止呢，压到PC啦，所以PCRK是一减X形容的时候就停了，就算了就算了，就不要再压的更小。



![](img/db6658133db27bd03532a790377cbc37_359.png)

那这样的好处就是你不会让PC啦，跟PCRK差距太大。

![](img/db6658133db27bd03532a790377cbc37_361.png)

那要import ment，这个东西，其实对你来说可能不是一个太困难的事情，好在最后这些投影片呢只是想要秀一下，在文献上PPO跟其他方法的比较，那今天这边有秀的，有这个呃ACEQUIT的方法。

这边有a to c，a to c加trust region，他们都是actiquit base的方法，EXEQUIT我们之后会讲到，然后呃还有这边有个PPO，PPO是紫色的线的方法。

然后还有TRPOPPPO就是紫色的线，PPO就是紫色的线。

![](img/db6658133db27bd03532a790377cbc37_363.png)

那你会发现说在多数的task里面，这样，每张图就是某一个某一个这个IO的任务啊。

![](img/db6658133db27bd03532a790377cbc37_365.png)

还发现说在多数的case里面，TPO的都是额不错的。

![](img/db6658133db27bd03532a790377cbc37_367.png)

不是最好的，就是第二好的。

![](img/db6658133db27bd03532a790377cbc37_369.png)