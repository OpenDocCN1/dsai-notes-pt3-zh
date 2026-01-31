# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P47：6-选修-GAN 理论-2 - AI算法工程师Future - BV1ruqABeEFX

D叫FKFK，呵呵好，我们要讲一个东西叫做FG，那这这一段是这个样子啊，这一段数学比较多，如果你听不懂的话，不用太在意就算了，因为这个东西有点用不上，这样为什么我们这边要讲的是什么。

我们这边讲的是说我们说我们定某种objective function，就是在量js diversion，那我们能不能够量其他的divergence呢。

f game就是告诉我们说怎么量其他的divergence，那我之所以会说这一招不太有用，关系原因就是呃用不同的divergence，就FK它可以让你的GA量不同的F改。

用不同的s divergence来量你的generated example，跟real example之间的距差距，但是用不同的f divergence的结果是差不多的。

所以这招好像没什么特别有用的地方，但是我们还是跟大家介绍一下啊，还因为这个呃在数学上他感觉非常的这样子，但但是在实作上好像没有什么特别的不同，好我们来讲一下FGFG是要想要告诉我们的。



![](img/bddadfa40708e93e33c7031e0592282d_1.png)

是说其实不只是用js diversion，任何f divergence你都可以放到game的架构里面去，那我们就先来介绍一下什么是f diversion。

f divergence是说我们现在假设有两个distribution p跟Q，我们两个distribution p跟Q，p of FX代表X从P这个distribution sample出来的几率。

QFX代表呃S呢从Q这个distribution sample出来的几率，那P跟Q这两个distribution的f divergence它长什么样子呢，他的长相就是我们可以把它写成，像这边这个式子。

PC的distribution，Q是一个distribution，然后你对X做积分，然后把q of FX乘上FPOFX除以Q导FX，那这个F这个方式呢，它是就是说。

假设这个东西要是一个f divergence的话呢，那F这个方程它必须是convex，这是第一个条件，第二个条件是FY必须要等于零，有这两个条件的话，这一个式子就是某一种f diversion。

这个F方不同的方式它就是不同的diversion，然后会看到说你F放某一个方向就是kl divergence。



![](img/bddadfa40708e93e33c7031e0592282d_3.png)

放另外一个方向就变成inverse的kl divergence好，那首先我们想要跟大家说明的事情是P跟Q2，就为什么这个式子，它可以看作是在衡量P跟Q的差异呢。

为什么这个式子可以看作是P跟Q的divergence呢，首先第一个我们要跟大家说明的是，如果P跟Q这两个distribution是一模一样的，那这个值会是零，因为这个东西，这个divergence。

等于是在衡量P跟Q两个distribution之间的距离，所以如果这样的distribution是一样的，它们的距离应该为零，所以我现在现在看看，假设P跟Q是一样的，它们距离是不是应该为零呢。

好假设P跟Q是一样的，会发生什么事呢，假设P跟Q是一样的，那这一项的值是一，那我们说f diversion是一个条件式，F这个式子带一要是零，所以这边就变成零，这边变成零意味着什么。

意味着这一整项都是零，所以当P和Q是一样的时候，他们距离呢会是零，接下来要跟大家说明的地方是，零呢是这一个式子可以达到的最小的距离。



![](img/bddadfa40708e93e33c7031e0592282d_5.png)

![](img/bddadfa40708e93e33c7031e0592282d_6.png)

也就是说如果P跟Q有些不同，它们不是完全一模一样，他们算出来的s sky version就会大于零啊。



![](img/bddadfa40708e93e33c7031e0592282d_8.png)

怎么说呢。

![](img/bddadfa40708e93e33c7031e0592282d_10.png)

因为F呢它是一个complex的function，这是它这是这个f diversion。

![](img/bddadfa40708e93e33c7031e0592282d_12.png)

第二条件也F必须要是一个CONVX的方选，如果是一个context的function，C的式子可以写成这样啊，这部跳的有点快，反正你自己回去check一下，反正就是这么回事就对了。

这个就这个因为F是COMBX的关系，所以这个式子会大于等于这个式子，就这个式子会是他的一个lower bb好，接下来呢你把Q消掉，然后积对PFS做积分。



![](img/bddadfa40708e93e33c7031e0592282d_14.png)

你就得到F1啊，然后会得到零，所以今天P跟Q他们如果一模一样的时候，你的f diversion算出来是零。



![](img/bddadfa40708e93e33c7031e0592282d_16.png)

如果P跟Q略有不同，他们一定会大于等于零。

![](img/bddadfa40708e93e33c7031e0592282d_18.png)

因为P跟Q是P，P跟Q的，P跟Q的值呢一定会大于等于零，所以P跟Q略有不同的时候，它们的值呢就会大于等于零。



![](img/bddadfa40708e93e33c7031e0592282d_20.png)

所以我们可以说这个式子，它可以拿来量P跟Q之间的差异好。

![](img/bddadfa40708e93e33c7031e0592282d_22.png)

那接下来呢我想告诉大家是说，假设你F带不同的式子，你就得到不同的diversion，举例来说，如果你的F是x log x，那带进去以后把这个F用x log x带进去以后。

你算出来就是ko diversion，如果你X是负log x，如果你把这个负log x带进去。

![](img/bddadfa40708e93e33c7031e0592282d_24.png)

你算出来的就是inverse reverse ko divergence。

![](img/bddadfa40708e93e33c7031e0592282d_26.png)

如果你现在FX在X减一平方，你算出来的就是KSQUARE的divergence，就这样还可以就带不同的东西。



![](img/bddadfa40708e93e33c7031e0592282d_28.png)

就得到各式各样的f divergence的的的major，就是了，好了，接下来要讲一个你可能没有听过的东西，叫做FICIAL的contract，这边要讲的意思是说呢。

这边要讲的东西是说每一个convex function的F啊，它都有另外一个contribute的方式叫做S8，就每一个F他都有一个对应的伙伴叫做S档，这个F跟F大它们之间的关系写成一个这样。

看起来很可怕的式子，这样看着就有点头痛，这样的等下就跟不上了，这样嘿嘿一看就觉得有点头痛，这样说这到底是什么东西，这东西是这个样子，这个东西是这个X这个这个呃我们有一个F。

那它的contrigate function叫做f star，这个f star它长的是这个样子，它是由f of x所导出来的，F大如果我们带T进去，要怎么算出它的值呢，你就穷举所有的T。

看哪一个T可以让XT减F和X的值最大，就是我们要的值啊，这样讲可能有点抽象，所以我们就实际上举个例子，X大的T换是多少，你就把T1带进去，然后求取各种不同X的值，看看哪一个X的值可以让T1最大。

举例来说，如果你X带x1，你得到s one T1减f s one，以S3x two，你得到x2，T1减f max two，以S3X以S3S3，你得到X31万减FX3，再看这些不同的X里面谁最大。

我发现哦x1最大，那我们得到的f star Lt one就是这个值，同理呢，假设你想要知道t two x大于t two的值是多少哦，那你就把不同的X呢，你就把t two先带进去。

然后把不同的X呢也带进去，你带XY进去得到这个值，等X2进去得到这个值，等S3进去得到这个值，看谁最大，看谁最大，最大值就是F大LT two，就这样子，好啊，所以如果你要今天要知道X大龙T长什么样子。

你都没点，从T0到T100和每一点都用这个方法去算，都用这个方法去算，你就可以把X大龙T1的把它描绘出来。



![](img/bddadfa40708e93e33c7031e0592282d_30.png)

但这样有点麻烦，所以另外一个方法是说，我们现在呀把XT减FX把它画出来，我们带不同的XY，但是把ST减到FFX画出来，假设X是x1的话，长这样，假设X是s two的话，长这样，就这个都是。

这都是一直线嘛，对不对，这个都是一直线，因为假设你的T是你唯一的变数，X是固定的，X减T减FXX是固定的，就要么是XY代码是XY它都是固定的，这个时候XT减FXX它都是直线，你带不同的S进去。

它就是不同的直线，但x1进去是这样。

![](img/bddadfa40708e93e33c7031e0592282d_32.png)

在x2不进去是这样，但X3进去是这样，在带不同的直进去呢，它就是不同的直线，而接下来我们要找最大的那一个，给定一个T我们要找最大的那一个，那最大的那个是什么呢。



![](img/bddadfa40708e93e33c7031e0592282d_34.png)

假设给定T1最大的那个就是呃在这个地方。

![](img/bddadfa40708e93e33c7031e0592282d_36.png)

假设给定t two最大那个就是在这个地方，所以今天你要把f style t画出来。

![](img/bddadfa40708e93e33c7031e0592282d_38.png)

就是把所有不同XY所造成的直线统统画出来。

![](img/bddadfa40708e93e33c7031e0592282d_40.png)

通通画出来，通通画出来，然后再取他们的阿法B，再把他们的阿根棒找出来。

![](img/bddadfa40708e93e33c7031e0592282d_42.png)

这个就是X大的T就X大的T好。

![](img/bddadfa40708e93e33c7031e0592282d_44.png)

所以今天你会发现说X大等题，他一定是context。

![](img/bddadfa40708e93e33c7031e0592282d_46.png)

所以今天如果你画很多条直线，画很多条直线，随便乱画，随便乱画。

![](img/bddadfa40708e93e33c7031e0592282d_48.png)

不管你怎么随便画，最后你只要找的是他的阿布B，你得到的方程都会是combs。

![](img/bddadfa40708e93e33c7031e0592282d_50.png)

所以今天f method是COMBX，F大于T其实也一定是COMBX的。

![](img/bddadfa40708e93e33c7031e0592282d_52.png)

好在这边是想要举一个例子跟大家说明一下，我们刚才讲的是什么，假设FX是x log x啊，FX是x log x，今天如果我们X带0。1，我们会得到这样一条直线X大一，我们会得到这样一条直线S带十。

我们会得到这样一条直线，把这些直线的up棒通通串起来，我们会得到一个看像看起来像是这样子的直线，差不多，是不是直线看起来像这样的一个曲线，那就X2带不同的值，你从呃00。1带进去得到一条线，0。

1001带进去也是一条线，0。1002带进去，一条线通通带进去，得到无穷无尽的线，把这些所有的线的up棒通找出来。



![](img/bddadfa40708e93e33c7031e0592282d_54.png)

就是红色这一条线，那你会发现过这条红色的线，那它看起来像是exponential，没错这一条红色的线它是EXPANALT减一，所以FFX它的CONJUG就是exponential t，减一啊。

他叫exponential t减一嘶好，那这边呢是举一个很直观的例子啊。

![](img/bddadfa40708e93e33c7031e0592282d_56.png)

然后下一页是一个proof，我们也许就可以把它跳过去，反正你就怒算一波以后，会发现说确实这个X大呃，假设FX是X减log x怒刷一波以后，就知道他是EXTRANALT减一样。

他contract是EXTRANALT减一嘶好。

![](img/bddadfa40708e93e33c7031e0592282d_58.png)

那讲这么多好像都跟game没半毛钱的关系。

![](img/bddadfa40708e93e33c7031e0592282d_60.png)

到底为什么要讲这些呢，接下来我们就要进入跟game有关的内容了。

![](img/bddadfa40708e93e33c7031e0592282d_62.png)

我们就跟记录跟game有关的内容了，好我们刚才知道说apple max有一个conjugate，就是F大的T，其实F大头T它本身的contract也就是FX。

所以FX和F大的T他们其实是互为contract，所以F大于T跟F和实验的关系，可以写成这样的式子好，所以接下来呢假设你有个convex function叫做FFX。

你就可以把这个combt function，FFX换成右边这样的式子，换成右边这样式诶，我就想说哎，这不是把本来简单的问题变得更复杂了吗，到底在搞什么这样子，人家告诉你说这件事情跟骗是有关系的。

神庙的地方就是这件事情跟骗是有关系的，好，所以假设我们有一个f divergence的function，f divergence的function，你是对X做积分，QX乘上FP除以Q。

那这个F是一个COMBX的方式，对不对，怎么说，Convex function，Apple vex，都可以换成右边这个看起来比较复杂的样子，所以我们就把它换掉就好，把简单问题弄得更复杂。



![](img/bddadfa40708e93e33c7031e0592282d_64.png)

把它换掉，所以本来X是P除以Q，X这边是P除以Q是P除以Q，所以让P除以Q带进去，P是Q带进去，就得到这样子的一个式子，所以把FP除以Q就变成了P除以Q乘上T，再减掉f star of t。

f star of t是F的Ctrl gate，然后呢再对所有的HT取一个max，你就得到这一个值，要得到这个值好。



![](img/bddadfa40708e93e33c7031e0592282d_66.png)

接下来呢我要告诉你说，我们现在任一个D它其实就是discriminator。

![](img/bddadfa40708e93e33c7031e0592282d_68.png)

他这个D这个function呢，它就是input s，它output一个SCALA，它output的这个scale，就是这边这个T就是这边这个T，所以我们把这个T用d of x取代表。

就我们希望说我们可以认出一个方式，这个方式不我们不要解这个max problem，我们不要写这个max problem，本来应该是说哦给你P给你PFS给你QFS，给你X大长什么样子。

求你做个P看哪一个T可以让这个值最大，那这个就是你在小括号里面的值，就在小括号，小括号里面的值，也希望大家听得懂，这样子好，那接下来我们要找一个discriminator。

这个discriminator帮我们解这个max的problem，这discriminate怎么帮我们解max的problem呢，呃他就是input一个X，他会告诉我们说哦，你现在input这个X以后。

到底哪一个T可以让这个值最大，它是一个这个这个D就他就是要做这件事好，但是因为假设D的capacity是有限的，那你今天把这个T呢换成DIO倍，你先把这个T换成第二类。

这一项就会变成是f divergence的一个lower BF。

![](img/bddadfa40708e93e33c7031e0592282d_70.png)

![](img/bddadfa40708e93e33c7031e0592282d_71.png)

f divergence的一个lower b。

![](img/bddadfa40708e93e33c7031e0592282d_73.png)

好然后接下来呢你再把它展开，你再把它展开，这边Q呢可以删掉，所以变成POFX乘上POFX减掉呢，Q在X乘上X大的F大的DOX。



![](img/bddadfa40708e93e33c7031e0592282d_75.png)

那就把这个式子呢列X上来，因为我现在说我们要找一个D它，因为如果你随便找一个D，他一定是它，它会它会比这个f diversion的值还要小，如果你找一个最好的低，他预测出来的T呢是最准的。

你就可以去逼近f diversion，所以我们找一个T他可以maximize后面这一项，他就可以去逼近f diversion，所以f diversion的这个式子会等于找一个D。

它可以maximize后面这一项，后面这一项是什么呢，后面这项是对所有的X多积分，Q跟X乘上Q5X减掉，对所有的X多积分，Q和X乘上F大龙DOFS好。



![](img/bddadfa40708e93e33c7031e0592282d_77.png)

接下来呢我要跟你说他跟GA式有什么关系，这个式子我们可以写成是对POS，就是一个几率嘛，POS是一个几率，对POS做积分乘上p max就等于是用P这个distribution，最近又开始取期望值。

这边呢是用F大于DOMMX这个值，然后用用用这个这个Q这个distribution，对F大于DMX取期望值好，接下来呢接下来呢这边我们只是换了一下名字，我们把P改成PDA，我们把Q改成pg。

所以今天PDA跟pg之间的f divergence，就可以写成后面这个式子，你的f divergence是什么，就会影响到这个s star，你放的是什么。

OK所以今天假如你的F5f divergence是ko divergence，那你就看ko divergence f star是什么，KODIVERGF是x log x。

他的f star4is financial7-1，所以这个f star就带SANALT减一，就这样子哎就这样哎，你看这个式子跟电看起来的式子，怎么看起来这么像呢，怎么看起来这么像呢，所以想想看。

我们今天在劝一个generator的时候，我们要做的事情就是去minimize某一个divergence，某一个f diversion，Ko diversion，Sadiversions。

reverse ko divergence等等。

![](img/bddadfa40708e93e33c7031e0592282d_79.png)

而这个divergence我们就可以把它写成这个式子，随着你要用什么divergence，你这X大就换不同的式子，你就是在量不同的divergence。



![](img/bddadfa40708e93e33c7031e0592282d_81.png)

而这个东西就是我们说在train again的时候，你要用discriminator去maximize，你的generator，要去minimize object function，Vo gd。

所以view gd的定义不同，你就是在量不同的divergence，你设某种样子，他就是在量cs diversion，你设另外一种样子，就是在量kl diversion啊。



![](img/bddadfa40708e93e33c7031e0592282d_83.png)

这边这个页头这个都是从paper上面组，他就告诉你说各种不同的divergence的a campty function，都帮你列好了啦，就选一个你自己喜欢的讲啊，这个是total marion。

这是k l reverse，KLPETERSON呃，呃JEFFREYJS，然后其实get那个不算是JS，他跟ZS有一点点不一样，他市值也列在这边啊，到然后到。



![](img/bddadfa40708e93e33c7031e0592282d_85.png)

所以所以说你可以去optimize各种不同的，你喜欢的diversion好，那还可以optimize不同的divergence，到底有什么厉害的地方呢，它厉害的地方是，也许这一招可以解决一个。

长期以来困扰着大家的问题，是当你劝game的时候，你会遇到一个现象，叫做MOCH，选more class的意思是说你的real data的distribution是比较大的。

但是你generate出来的example，他的distribution非常的小，举例来说，你在自己在做这个二次元人物生成的时候，如果你update information太多。



![](img/bddadfa40708e93e33c7031e0592282d_87.png)

你得到的结果可能会是这个样，你会发现某一张特定的人脸，它就开始蔓延了，他就开始蔓延，变得到处都是这样，所以他这些人脸其实是略有不同的，这个是比较偏黄，这个是比较偏红，但是他们都是看起来就像是同一张人脸。

也就是说你今天产生出来的distribution，它会越来越小，越来越它会越来越小，而而最呃最后会发现说，同一张人脸不断的反复的出现，那这个case叫做more plex。

那有另外一个case比more class稍微轻微一点，叫做more dropping，意思是说你的distribution其实有很多个mod，就假设你的real distribution是两群。

但是你的generator只会产生同一群而已，它没有办法产生两群不同的data。

![](img/bddadfa40708e93e33c7031e0592282d_89.png)

举例来说，你可能缺一个人脸的产生的系统，你会发现说呢。

![](img/bddadfa40708e93e33c7031e0592282d_91.png)

它产生出来的人脸长得是这个样子，你仔细一看，觉得嗯看起来都还可以。

![](img/bddadfa40708e93e33c7031e0592282d_93.png)

也许没有什么太大的问题，但你发现你在update一次参数以后。

![](img/bddadfa40708e93e33c7031e0592282d_95.png)

再在update次generator参数以后，产生出来的image变成这样，所以发现说其实刚才在前面产生的image，它只产生他没有产生黄皮肤的人，他只产生比较皮肤色比较偏白的人，他没产生黄皮肤的人。

但是你今阿贝一次诶，他就变成产生黄皮肤的人，就没产生白皮肤的人，在他背一次，他就变成产生黑皮肤的人，而且他每次都只能够产生某一种肤色的人，这样子就感觉好像是不太OK的，好那为什么会发生这种现象呢。

一个远古的猜测是，也许是因为我们divergence选的不好啊。

![](img/bddadfa40708e93e33c7031e0592282d_97.png)

选的不好，如果今天你的data的distribution是蓝色这样子的分布。

![](img/bddadfa40708e93e33c7031e0592282d_99.png)

![](img/bddadfa40708e93e33c7031e0592282d_100.png)

你的generator distribution它只能够有一个mixture，它是绿色的虚线的分布。

![](img/bddadfa40708e93e33c7031e0592282d_102.png)

如果你选不同的divergence，他们就会你最后optimize的结果，你最后选出来可以minimize，divergence的那个generator distribution，你会发现就是不一样。

假设你现在去minimize kl divergence，你用maximum likeable的方法去mass minimuhao divergence。

那你的generator最后认为最make最好的那个distribution，长得是这个样子。

![](img/bddadfa40708e93e33c7031e0592282d_104.png)

长得是这个样子，诶发现说假设你的generreal distribution长的是这个样子。

![](img/bddadfa40708e93e33c7031e0592282d_106.png)

你从它里面去simple data，你simple在mor maker之间结果反而会是差的。

![](img/bddadfa40708e93e33c7031e0592282d_108.png)

所以这可以解释为什么过去没有pin的时候，我们是在minimize pale diversion，我们在max mum likelihood，我们产生的图片会那么模糊。

也许就是因为我们产生distribution是这个样子的，我们在sample的时候，其实并不是真的在data它tensity很高的地方sample。

而是为sample在data density很高很低的地方，所以这些这个地方就对应到模糊的图片，那有人就说如果你觉得是kl divergence所造成的，那如果你换别的divergence。

比如说你换这个inverse ko diversions。

![](img/bddadfa40708e93e33c7031e0592282d_110.png)

那你就会发现说呢对generator来说。

![](img/bddadfa40708e93e33c7031e0592282d_112.png)

最好的distribution是完全跟某个mod1模一样，就就因为如果你看这个reverse ko divergence的事，你就会发现说对他来说，如果它产生出来的贝塔是原来的distribution。

蓝色DISTR就没有涵盖它，penalty比较大，所以如果你今天选择的是reverse panel diversion，那你的那个generator，他就会选择集中在某一个more就好。

而不是分散在不同的mo，而我们传统的gain的那个JADIVERGENCE，它比较接近reverse hell divergence，这也许解释了为什么你劝一下gain的时候，你会产生出来。

你会有那个more class或者是more dropping的情形。

![](img/bddadfa40708e93e33c7031e0592282d_114.png)

因为对你的选择RATOR来说，产生这种more克莱斯for more jin的情形，其实反而是比较optimal的，所以今天f diversion f gang的厉害的地方就是。

如果你觉得是js diversion的问题，那现在你可以换了，你可以换ko diversion，但结果就是换不同的divergence，more dropping的case状况还是一样。

所以看起来不是more，more dropping或者是more progress的问题，并不完全是选择不同的divergence所造成的。



![](img/bddadfa40708e93e33c7031e0592282d_116.png)

好好那你赶快问说，那我要怎么解决MOCHLESS的问题呢，你在做作业的时候，你很有可能会遇到more plex的问题，我们不是要求大家要产生25张图吗，你的generator可能会产生出来的图。

统统都是一样的，但这样就会被扣分了，那怎么避免这个情形呢，这边有一个呃，其实做得好的同学都会这么做的，就是做UNSABLE，什么意思呢，今天让你产生25张图片。



![](img/bddadfa40708e93e33c7031e0592282d_118.png)

你就train25个generator，然后你的选择每一个generator也许他都more class，也许你的generator one只会产生这样的图卷。



![](img/bddadfa40708e93e33c7031e0592282d_120.png)

reor two只会产生这样的图，但没有关系，你有25个generator，所以实际上是要在run你的code的时候。



![](img/bddadfa40708e93e33c7031e0592282d_122.png)

其实是跑了25个generator，每个generator会产生一张image。

![](img/bddadfa40708e93e33c7031e0592282d_124.png)

但是但是对使用者来说，那些你这是使用者，并不知道你有很多个generator，那所以你产生出来的结果看起来就会diverse，这是一个我觉得最有效，可以避免more collapse的问题，这样啊。

只是这一个月要一个月，不会啊，你就圈25个generator，假设一个圈三小时，也是几天就圈完了，对不对，嘿嘿嘿嘿嘿，哎妈好。



![](img/bddadfa40708e93e33c7031e0592282d_126.png)

其实今天要讲的呢大概就是这个样子。

![](img/bddadfa40708e93e33c7031e0592282d_128.png)

![](img/bddadfa40708e93e33c7031e0592282d_129.png)

![](img/bddadfa40708e93e33c7031e0592282d_130.png)