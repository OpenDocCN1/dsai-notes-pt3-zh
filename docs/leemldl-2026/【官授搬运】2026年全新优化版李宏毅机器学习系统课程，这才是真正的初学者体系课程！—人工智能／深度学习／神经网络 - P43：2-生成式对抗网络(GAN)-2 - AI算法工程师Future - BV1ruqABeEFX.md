# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P43：2-生成式对抗网络(GAN)-2 - AI算法工程师Future - BV1ruqABeEFX

好刚才啊就是用了一堆比喻，然后告诉你gain是怎么运作的，然后也实际上告诉你game的操作是怎么操作的，那接下来呢我们要讲一点理论的部分啊，讲一点农场我们不会讲到的部分。

告诉你说实际上为什么gain的这一番操作，为什么这个generator跟discriminator的互动，可以让啊，我们的generator产生像是真正的人脸的图片。

那这背后的互动在做的到底是什么样的事情啊，那我们先来弄清楚，我们今天的训练的目标到底是什么，你知道我们在训练network的时候，你就是要定一个loss function嘛。

定完以后用gradient design去调你的参数，去minimize那个loss function就结束了，那在这个generation的问题里面，到底我们要minimize的。

或者是我们要maximize的到底是什么样的东西呢，我们要把这件事弄清楚，才能够做接下来的事情好，那在generator里面，我们到底想要minimize或者是maximize，什么样的东西呢。

我们想要minimize的东西是这个样子的哦，我们有一个generator给他一大堆的factor，给他从normal distribution sample出来的东西，丢进这个generator以后。

会产生一个比较复杂的distribution，这个复杂distribution我们叫它pg，然后呢我们有一堆的data啊，这个是真正的data。

真正的data也形也形成了另外一个distribution叫做p data，我们期待pg跟p data越接近越好好，那如果你一下子没有办法想象，这个p g p data是怎么一回事的话。

那我们用一维的状况来跟大家说明，我们假设generator的input是一个一维的向量，觉得RATOR的output也是一维的向量，我们的真正的data也是一维的向量好。

那我们的normal with distribution就长这个样子，没有问题，那丢到generator以后，这边这每一个点呢，假设你输入五个点，那边这每一个点呢它的位置会改变。

那你就产生一个新的distribution，那可能本来大家都集中在中间，通过这个generator，通过一个network里面很复杂，不知道做了什么事情以后，这些点就分成两边。

所以你的distribution就变成这个样子，而PDA是指真正的资料的分布，真正资料分布可能长这个样子，它分两面的状况是更极端的啊。



![](img/561710c1d9812eec222b4092dfae0946_1.png)

左边的东西比较多，右边的东西比较少，那你期待左边这个分布，跟右边这个分布越接近越好，如果写成式子的话，你可以写成这个样子哦，你这边这个呃d i v of pg跟p data。

它指的意思就是pg跟p data，这两个distribution之间的diversion，那divergence这边指的是什么意思呢，divergence这边指的意思就是这两个呃。

你可以想成是这两个distribution之间的某种距离，如果这个divergence越大，就代表这两个distribution越不像，divergence越小。

就代表这两个distribution越相近啊，divergence就是衡量两个distribution相似度的一个major啊，然后呢我们现在的目标是要去找一个generator。

那所谓的找一个generator，实际上骨子里做的事情是，找一个generator里面的参数，找一组generator里面的参数，就generator也是一个network。

里面有一大堆的weight跟bias，找一组generator的参数，它可以让我们产生出来的，pg跟p data之间的divergence越小越好，我们要找的就是这样子的generator。

我们这边把它写作句子塔，所以我们这边要做的事情跟一般train network，其实非常的像，我们第一堂课就告诉你说，我们定义了loss function，找一组参数。

Minimize loss function，我们现在其实也定义了我们的loss function，在generation这个问题里面。

我们的loss function就是PG跟p data的divergence，就是他们两个之间的距离，他们两个越近，那就代表呃这个产生出来的pg跟p data越像。

所以pg跟p data我们希望他们越相像越好，所以我们希望pg跟p data的divergence越小越好，我们要做的事情就找一个G让divergence变得最小，但是我们这边遇到一个困难的问题。

怎么样困难的问题呢，这个呃loss啊，我们是可以算的，但是这个divergence要怎么样算呢，那你可能知道一些divergence的式子，比如说kl divergence。

比如说js divergence，这些divergence用在这种continuous distribution上面，你要做一个很复杂的，在实作上，你几乎你几乎不知道要怎么算的积分。

那我们根本就无法把这个diversion算出来。

![](img/561710c1d9812eec222b4092dfae0946_3.png)

我们算不出这个divergence，我们又要如何去找一个G去minimize这个divergence。



![](img/561710c1d9812eec222b4092dfae0946_5.png)

这个就是game所遇到的问题，这就是我们在train这一种啊，generator的时候会遇到的问题，again呢是一个很神奇的做法，它可以突破我们不知道怎么计算divergence的限制。



![](img/561710c1d9812eec222b4092dfae0946_7.png)

好像我们现在遇到的问题，就是不知道怎么计算divergence，而gain告诉我们，就是gain告诉我们的，就是只要你知道怎么从pg和p data这两个distribution，simple东西出来。

就有办法算diversion，你不需要知道pg跟pd它们实际上的formulation，长什么样子，你只要能够simple就能够算divergence，而P区跟p data是可以sample的吗。



![](img/561710c1d9812eec222b4092dfae0946_9.png)

是可以sample的，怎么从真正的data里面sample出东西来呢，那你就把你的图库拿出来，从图库里面随机产生随机呃，sample1些图片出来。



![](img/561710c1d9812eec222b4092dfae0946_11.png)

你就得到PDA了，好那怎么从generator里面产生一些东西出来呢。

![](img/561710c1d9812eec222b4092dfae0946_13.png)

哦那你就把你的generator输入这个啊啊normal的。

![](img/561710c1d9812eec222b4092dfae0946_15.png)

从normal distribution sample出来的vector丢到generator里面。

![](img/561710c1d9812eec222b4092dfae0946_17.png)

我们刚才也说过，说你这边的这个distribution呢。

![](img/561710c1d9812eec222b4092dfae0946_19.png)

你拿来sample那个distribution要是简单的，要是你有办法simple的，所以我们选normal distribution是指我们是知道的。



![](img/561710c1d9812eec222b4092dfae0946_21.png)

是有办法sample的，我们从normal distribution里面sample1堆vector出来。



![](img/561710c1d9812eec222b4092dfae0946_23.png)

丢给generator，好让generator产生一堆图片出来。

![](img/561710c1d9812eec222b4092dfae0946_25.png)

那这些图片就是从pg sample出来的结果。

![](img/561710c1d9812eec222b4092dfae0946_27.png)

所以我们有办法从P区做sample，我们有办法从p data做sample。

![](img/561710c1d9812eec222b4092dfae0946_29.png)

接下来game这一整个系列的work，就是要告诉你说怎么在只有做sample的前提之下，我根本不知道pg跟p data。



![](img/561710c1d9812eec222b4092dfae0946_31.png)

实际上完整的formulation长什么样子，在只能做sample的前提之下。

![](img/561710c1d9812eec222b4092dfae0946_33.png)

居然就算出了，居然就估测出了divergence好，那这个就是要靠discriminator的力量，那我们刚才讲过说，discrimination是怎么训练出来的呢，我们有一大堆的real data。

这个real data就是从p data sample出来的结果，我们有一大堆generated data，generated data就可以看作是从pg sample出来的结果。

根据real的data跟generated data，我们会去训练一个discriminator，他的训练的目标啊，是看到real data就给他比较高的分数。

看到这个呃generated data就给他比较低的分数，我们刚才就说，discriminator训练的目标，就是要分辨好的图跟不好的图，分辨真的图跟深层的图。



![](img/561710c1d9812eec222b4092dfae0946_35.png)

所以看到真的图给他高分，看到深层的图给他低分，那实际上刚开始呢你也可以把它写成式子，把它当做是一个optimization的问题，这个optimization的问题是这样子的。

我们要训练一个discriminator，这个discriminator可以去maximize某一个function，我们这边叫做objective function，就是我们要maximize的东西。

我们会叫objective function或说minimize，我们就叫它loss function，我们现在要找一个第一，它可以maximize这个objective function。

这个objective function长什么样子呢，这个objective function长这个样子，我们有一堆Y它是从p data里面sample出来的，也就是他们是真正的image。

而我们把这个真正的image丢到D里面，得到一个分数再去lo，那另外一方面呢，我们有一个Y，它是从pg从卷的ERATOR所产生出来的，把这些图片也丢到discriminate里面，得到一个分数。

再取log1减这个UY，那我们希望这个object function b啊越大越好，我们希望V越大越好，意味着我们希望这边的DFY越大越好，我们希望Y如果是从p data sample出来的。

它就要越大越好，我们希望说如果Y是从这个pg sample出来的，它就要越小越好，那我们就去最大化V这个式子，我们去最大化找一个D可以啊，maximize这个object function。

我们其实就是呃呃让DOFY越大越好，让这边的d of fy，也就是机器generator生成的图片的值越小越好。



![](img/561710c1d9812eec222b4092dfae0946_37.png)

discriminator output的值越小越好，那这件事情呢其实又等同于你可能觉得没事。

![](img/561710c1d9812eec222b4092dfae0946_39.png)

突然写出这个式子有点奇怪。

![](img/561710c1d9812eec222b4092dfae0946_41.png)

但你不一定要把这个objective function写成这个样子，他完全可以有其他的写法，那最早年之所以写成这个样子，是有一个很明确的理由，有一个很明确的动机。

是为了要把discriminator跟binary的classification，跟分类跟二元的分类扯上关系，怎么说呢，事实上这一个object function它就是cross entropy。



![](img/561710c1d9812eec222b4092dfae0946_43.png)

乘一个负号。

![](img/561710c1d9812eec222b4092dfae0946_45.png)

我们知道我们在训练一个classify的时候，我们就是要minimize cross entropy。



![](img/561710c1d9812eec222b4092dfae0946_47.png)

所以当我们maximize这个objective function，maximize cos entropy乘一个负号的时候。



![](img/561710c1d9812eec222b4092dfae0946_49.png)

其实等同于minimize cross entrop。

![](img/561710c1d9812eec222b4092dfae0946_51.png)

也就等同于是在训练一个，也就是等同于是在训练一个classify，所以这个discriminator真正做的事情。

如果discriminator做的事情是去maximize self objective function，那这个discriminator其实可以当做是一个classify。



![](img/561710c1d9812eec222b4092dfae0946_53.png)

他做的事情就是把蓝色这些点，从p data sample出来的真实的image当做plus one。

![](img/561710c1d9812eec222b4092dfae0946_55.png)

把从pg sample出来的这些假的image当做class two。

![](img/561710c1d9812eec222b4092dfae0946_57.png)

有两个class的data训练。

![](img/561710c1d9812eec222b4092dfae0946_59.png)

一个binary的classify，训练完就等同于是解了这个optimization的问题。

![](img/561710c1d9812eec222b4092dfae0946_61.png)

那这边最神奇的地方是以下这句话。

![](img/561710c1d9812eec222b4092dfae0946_63.png)

这一个式子。

![](img/561710c1d9812eec222b4092dfae0946_65.png)

这个红框框里面的数值它跟js divergence有关。

![](img/561710c1d9812eec222b4092dfae0946_67.png)

那事实上有趣的事情是呃，我觉得最原始的game paper它的发想啊。

![](img/561710c1d9812eec222b4092dfae0946_69.png)

可能真的是从binary classify来的，一开始是把discriminator写成BBINARY的classify。



![](img/561710c1d9812eec222b4092dfae0946_71.png)

然后有了这样的objective function。

![](img/561710c1d9812eec222b4092dfae0946_73.png)

然后在经过一番推导以后，这个objective function它的maximum啊。

![](img/561710c1d9812eec222b4092dfae0946_75.png)

就是你找到一个D，可以让这个objective function它的值最大的时候。

![](img/561710c1d9812eec222b4092dfae0946_77.png)

这个最大的值跟js divergence是有关的。

![](img/561710c1d9812eec222b4092dfae0946_79.png)

他们没有完全一模一样，所以显然一开始并不是针对jazz，diversion设计的。

![](img/561710c1d9812eec222b4092dfae0946_81.png)

而是经过一番推导以后，发现它们是非常有关联的，那至于实际上的推导过程。

![](img/561710c1d9812eec222b4092dfae0946_83.png)

你可以参见原始yang fellow写的文章，那其实里面的推导过程。

![](img/561710c1d9812eec222b4092dfae0946_85.png)

我觉得写的算是蛮清楚的好。

![](img/561710c1d9812eec222b4092dfae0946_87.png)

所以真正神奇的地方，就是这一个objective function的最大值，它跟divergence是有关的。



![](img/561710c1d9812eec222b4092dfae0946_89.png)

所以我们刚才说我们呃不知道怎么算divergence。

![](img/561710c1d9812eec222b4092dfae0946_91.png)

没关系，train你的discriminator train完以后。

![](img/561710c1d9812eec222b4092dfae0946_93.png)

看看他的object function可以到多大，那个值就跟divergence有关。

![](img/561710c1d9812eec222b4092dfae0946_95.png)

好那额，这边我们并没有把证明拿出来跟大家讲了，但是我们还是可以从直观上来理解一下，为什么这个objective function的值会跟divergence有关呢，那这个直观的理解并没有很困难。

因为你可以想想看，假设pg跟p data，他的divergence很小，也就pg跟p data很像，他们差距没有很大，它们很像pg跟p data sample出来的，蓝色的星星跟红色的星星。

它们是混在一起的，这个时候对discriminator来说，discriminator就是在train一个binary的classifier嘛，对discriminator来说。

既然这两堆资料是混在一起的，那就很难分开，这个问题很难，所以既然这个问题很难，你在解这个optimization的problem的时候，你就没有办法让这个objective的值非常的大。

所以这个object这个V的maximum的值就比较小哦，所以小的divergence对应到小的这个objective，function的maximum的值哦。

所以不是object function的值本身哦，是objective function在穷举所discriminator以后。



![](img/561710c1d9812eec222b4092dfae0946_97.png)

可以得到的最大的值，而如果今天呢你的两组data。

![](img/561710c1d9812eec222b4092dfae0946_99.png)

很不像他们的divergence很大，那对discriminator而言就可以轻易的把它分开，当discriminator可以轻易把它分开的时候，这个objective function就可以冲的很大。

那所以当你有大的divergence的时候。

![](img/561710c1d9812eec222b4092dfae0946_101.png)

这个object function的maxim的值就可以很大，按这边是用直观的方法来跟你讲的。

![](img/561710c1d9812eec222b4092dfae0946_103.png)

那详细的证明请参见game原始的paper里面，在做了一些假设，比如说discriminator的capacity是无穷大啊，等等的假设以后可以做出啊。

这个maximum的值跟js divergence值是相关的。

![](img/561710c1d9812eec222b4092dfae0946_105.png)

这个推导好，所以啊，我们说我们本来的目标是要找一个generator，去minimize pg跟p data的divergence设置。



![](img/561710c1d9812eec222b4092dfae0946_107.png)

让我们卡在不知道怎么计算divergence，那我们现在要知道，我们只要训练一个discriminator，训练完以后，这个object function的最大值就是这个divergence。

就跟这个divergence有关，那我们何不就一把红框框里面这一项，跟divergence做替换呢，我们何不就把divergence替换成红框框里面，这一项呢。

所以我们就有了这样一个objective function，这样jt function乍看之下有点复杂，还有一个minimum，又有一个maximum，所以你一不小心就会脑筋转不过来。

我们是要minim，我们是要找一个generator去minimize，红色框框里面这件事，但是红框框里面这件事，又是另外一个optimization problem。

他是在给定generator的情况下，去找一个discriminator，这个discriminator可以让V这个objective function越大越好，然后我们要找一个G。

让红框框里面的值最小。

![](img/561710c1d9812eec222b4092dfae0946_109.png)

这个G就是与我们要的generator，而刚才我们讲的这个generator。

![](img/561710c1d9812eec222b4092dfae0946_111.png)

跟discriminator互动啊，互相欺骗啊，这个过程其实就是想解这一个有minimize。

![](img/561710c1d9812eec222b4092dfae0946_113.png)

又有maximize，这个min max和MINMAX的问题，就是透过下面这一个啊，我们刚才讲的game的algorithm来解。



![](img/561710c1d9812eec222b4092dfae0946_115.png)

那至于实际上为什么下面这个ALGM可以解，这个问题，你也可以参见原始的电的paper。

![](img/561710c1d9812eec222b4092dfae0946_117.png)

那讲到这边，也许你就会问说为什么是jazz diversion。

![](img/561710c1d9812eec222b4092dfae0946_119.png)

而且还不是真的js diversion，是跟js divergence相关而已。

![](img/561710c1d9812eec222b4092dfae0946_121.png)

怎么不用真正的js divergence或不用别的，比如说kl divergence，你完全可以这么做，你只要改了那个object function，你就可以量各式各样的divergence。

而至于怎么样设计object function，得到不同的divergence，那有一篇叫做f game的paper里面有非常详细的证明，它有很多的table。

告诉你说不同的divergence要怎么设计它的object function，你设计什么样的object function去找他的maximum value，就会变成什么样的divergence啊。

在这篇文章里面都有详细的记载，所以一开始有人会觉得说啊，game之所以没有很好trap，也许是因为J呃，呃就是我们没有在真的这个minimize zis，Divergent。

但是有了这个FK这边paper以后，他就告诉你说，我们有办法minimize this is divergence，但就算你真的可以minimize this divergence，结果也还是没有很好。



![](img/561710c1d9812eec222b4092dfae0946_123.png)

GA还是没有很好权好，所以gain呢是以不好train而闻名的，所以你知道俗话就说啊。

![](img/561710c1d9812eec222b4092dfae0946_125.png)

No pain，No game，这样子，嘿我们就要讲一些game训练的小技巧，game有什么样训练的小技巧呢，那其中的最其他game训练的小技巧非常非常多，那我想了很久以后，我们只挑一个最知名的来讲。

这个最知名的就是很多人都听过诶，是不是没电了，哈喽哈喽好，换一个麦克风，哈喽哈喽好好，这个最知名的啊，就是很多人都听过的RUN，那这个w game是什么呢，在讲w game之前。

我们先讲js divergence有什么样的问题，在最早的GG说我们要minimize的是js divergence，那选择js diversion的时候会有什么问题呢。

好在讲js diversion的问题之前呢，我们先看一下pg跟p data有什么样的特性，那pg跟p data有一个非常关键的特性，是pg跟p data他们重叠的部分往往非常少，怎么说呢。



![](img/561710c1d9812eec222b4092dfae0946_127.png)

这边有两个理由，第一个理由是来自于data本身的特性，因为你想pg跟p data他们都是要产生图片，那图片其实是高维空间里面的一个低维的，Maniph，因为你想想看。

你在高维空间里面随便sample一个点，它通常都没有办法构成一个二次元人物的头像，所以二次元人物的头像它的分布啊，在高维的空间中其实是非常狭窄的哦，所以二次元头像的分布。

这个图片的分布其实是高维空间中的低维的，Maniphor，或者是如果是以二维空间来想的话，那图片的分布可能就是二维空间的一条线，二维空间中多数的点都不是图片。

就高维空间中随便sample一个点都不是图片，只有非常小的范围，只有非常小的范围，simple出来它会是图片，所以从这个角度来看，从资料本身的特性来看。

pg跟p data他们都是low dimensional的manifold，用二维空间来讲，pg跟p data都是二维空间中的两条直线，而二维空间中的两条直线，除非它刚好重合。

不然它们相交的范围几乎是可以忽略的，这是第一个理由，那也许有人说啊，这个也许图片根本就不是什么，low dimension of the metaphor啊，那会不会第一个理由就不成立了呢。



![](img/561710c1d9812eec222b4092dfae0946_129.png)

那我给你第二个理由，第二个理由是，我们是从来都不知道pg跟p data塔长什么样子，我们对pg跟p data，它的呃分布的理解其实来自于simple，所以也许pg跟p data。

他们是有非常大的overlap的范围，但是我们实际上在了解这个pg跟p data，在计算他们的divergence的时候，我们是从p data里面sample1些点出来。

从pg里面sample1些点出来，如果你sample的点不够多，你sample的点不够密，那就算是这两个divergence，实际上这两个distribution实际上有重叠。



![](img/561710c1d9812eec222b4092dfae0946_131.png)

但是假设你sample的点不够多，对discriminator来说。

![](img/561710c1d9812eec222b4092dfae0946_133.png)

它也是没有重叠的，就就是这个蓝色的分布跟红色的分布。

![](img/561710c1d9812eec222b4092dfae0946_135.png)

明明是有重叠的，但如果你从蓝色分布simple1些点，红色分布simple1些点，这些点你要simple的不够多，你根本就可以画一条楚河汉界，把红色的点跟蓝色的点完全的分开来，然后说红色的点。

它的分布就是在这个楚河汉界的右边，蓝色点就在左边，它们完全是没有任何重叠的，所以以上给你两个理由，试图说服你，说pg跟p data这两个分布，它们重叠的范围是非常小的。



![](img/561710c1d9812eec222b4092dfae0946_137.png)

而几乎没有重叠，这件事情对于js divergence会造成什么问题呢，this is divergence有个特性是两个没有重叠的分布，js divergence算出来就永远都是log2。

不管这两个分布长什么样子，所以两个分布只要没有重叠，算出来就一定是log2，不管他们长什么样子，算出来都是log2，所以举例来说，假设这是你的PDA，这是你的pg，他们距它们都假设他们都是一条直线。

然后中间呢有很长的距离。

![](img/561710c1d9812eec222b4092dfae0946_139.png)

你算他们的js divergence是log2，假设你的pg跟p data其实蛮接近的，那中间的间隔其实是比较小的。



![](img/561710c1d9812eec222b4092dfae0946_141.png)

算出来结果还是log2，除非你的pg跟p data有重合，不然这个pg跟p data，只要它们是两条直线，它们这两条直线没有相交，那算出来就是log2，算出来这样的case算出来是log2。

这个case算出来也是log2。

![](img/561710c1d9812eec222b4092dfae0946_143.png)

那但是明明这个case就比这个case好啊，中间这个case，中间这个generator明明就比左边这个generator好啊，但是你不知道，明明蓝色的线就跟红色的线比较近呐。

但是从js diversion上面看不出这样子的现象，那既然从js divergence上看不出这样子的现象，你在training的时候，你根本就没有办法把这样子的generator update。

参数变成这样子的generator，因为对你的loss来说，对你的目标来说，这两个generator是一样好或者是一样糟的，那以上是从比较理论的方向来说明。



![](img/561710c1d9812eec222b4092dfae0946_145.png)

如果我们从更直观的实际操作的角度来说明。

![](img/561710c1d9812eec222b4092dfae0946_147.png)

你会发现当你是用js divergence的时候，你就假设你今天在TRA一个binary的classify，去分辨real的image跟generated image，你会发现实际上你通常劝完以后。

正确率几乎都是百分之百，为什么，因为你sample的图片根本就没几张啊，对你的discriminator来说，你sample256张real的图片，256张fake的图片，他是直接用硬背的。

都可以把这两组图片分开。

![](img/561710c1d9812eec222b4092dfae0946_149.png)

知道说谁是real的，谁是fake的，所以实际上如果你有自己劝过gain的话。

![](img/561710c1d9812eec222b4092dfae0946_151.png)

你会发现如果你用binary的classify train下去，你会发现你几乎每次劝完你的classifier以后。



![](img/561710c1d9812eec222b4092dfae0946_153.png)

也就你串完你的discriminator以后，正确率都是100percent。

![](img/561710c1d9812eec222b4092dfae0946_155.png)

我们本来会期待说，这个discriminator的loss也许代表了某些事情。

![](img/561710c1d9812eec222b4092dfae0946_157.png)

这个binary classify loss也许代表某些事情，这个loss越来越大，代表问题越来越难，代表我们的generated的data和real的data越来越接近。



![](img/561710c1d9812eec222b4092dfae0946_159.png)

但实际上你在实际操作的时候。

![](img/561710c1d9812eec222b4092dfae0946_161.png)

你根本观察不到这个现象，这个binary classify训练完的loss，根本没有什么意义，因为它总是可以让它的正确率变到100percent，两组image都是sample出来的。



![](img/561710c1d9812eec222b4092dfae0946_163.png)

它硬背都可以得到100percent的正确率，你根本就没有办法看出你的generator。

![](img/561710c1d9812eec222b4092dfae0946_165.png)

有没有越来越好哦，所以过去啊。

![](img/561710c1d9812eec222b4092dfae0946_167.png)

尤其是在还没有w game这样的技术，在我们还用binary classifier当做discriminator的时候。



![](img/561710c1d9812eec222b4092dfae0946_169.png)

哇，train game真的就很像巫术黑魔法。

![](img/561710c1d9812eec222b4092dfae0946_171.png)

你根本就不知道你train的时候有没有越来越好，所以怎么办呢，那时候的做法就是你每次update几次generator以后。



![](img/561710c1d9812eec222b4092dfae0946_173.png)

你就要把你的图片print出来看，然后你就要一边那个吃饭，一边看那个图片生成的结果，然后跑一跑就发现哇坏掉了，然后卡掉重做这样子啊，所以以前你根本就没有。



![](img/561710c1d9812eec222b4092dfae0946_175.png)

不像我们在train一般的network的时候，你有个loss function，然后那个loss呢随着训练的过程啊。



![](img/561710c1d9812eec222b4092dfae0946_177.png)

我会慢慢慢慢变小，那你就会看说哎loss慢慢变小。

![](img/561710c1d9812eec222b4092dfae0946_179.png)

就放心，知道说你的network有在train，但会不会OVERFITTING是另外一件事，至少他在training data上有越来越好。



![](img/561710c1d9812eec222b4092dfae0946_181.png)

但是对game而言，本来我们期待classify的loss可以提供一些资讯。

![](img/561710c1d9812eec222b4092dfae0946_183.png)

但是当你的classify是一个简单一般的binary。

![](img/561710c1d9812eec222b4092dfae0946_185.png)

classify的时候，他训练的结果你就没有任何资讯，你每次训练出来正确率都是100percent。

![](img/561710c1d9812eec222b4092dfae0946_187.png)

你根本不知道你的generator有没有越来越好，变成你只能够用人眼看，用人眼守在电脑前面看，发现结果不好卡掉，重新用一组hyper parami，重新调一下network架构重做好。

所以过去呢训练game是有点辛苦的。

![](img/561710c1d9812eec222b4092dfae0946_189.png)

然后了，那既然是js divergence的问题，于是有人就想说，那会不会换一个衡量两个distribution的啊。



![](img/561710c1d9812eec222b4092dfae0946_191.png)

呃相似程度的方式，换一种divergence就可以解决这个问题了呢。

![](img/561710c1d9812eec222b4092dfae0946_193.png)

于是就有了这个VESS，使用使用vesa state distance的想法。

![](img/561710c1d9812eec222b4092dfae0946_195.png)

好，那faceant distance啊，这边有一个冷，这边有一个冷知识啦啊就是这个W啊，其实呃这边是念VER不是念不是不是发W的音，不是念WASSUSTAIN，而是念vs stin好。

那这个best sustadistance是怎么计算的呢，best sustadistance想法是这个样子，假设你有两个distribution啊，一个distribution我们叫它P啊。

另外一个distribution我们叫它q resistant distance，它计算的方法啊，就是想象你在开一台推土机。



![](img/561710c1d9812eec222b4092dfae0946_197.png)

推土界英文呢叫做earth mover啊。

![](img/561710c1d9812eec222b4092dfae0946_199.png)

想象你在开一台推土机，那你把P呢想成是一堆土，把Q呢想成是你要把土堆放的目的地，那这个推土机把P这边的土挪到，Q所移动的平均距离就是resistant distance。



![](img/561710c1d9812eec222b4092dfae0946_201.png)

在这个例子里面，我们假设P呢都集中在这个点，Q都集中在这个点，对推土机而言，假设他要把P这边的土挪到Q这边，那他要平均走的距离就是一哦，所以在这个例子里面，假设P集中在一个点，Q集中在一个点。

这两个点之间的距离是D的话，那P跟Q的best than distance就是D，那因为在讲这个vs ant distance的时候啊。



![](img/561710c1d9812eec222b4092dfae0946_203.png)

你要想象有一个earth mover，有一个推土机在推土，所以其实very suant distance，又叫earth mover distance啊，那但是呢如果是更复杂的distribution。



![](img/561710c1d9812eec222b4092dfae0946_205.png)

你要算better than distance就有点困难了，怎么说呢，假设这是你的皮，假设这是你的Q，假设你开了个推土机，想要把P呢把它重新塑造一下形状，让P的形状跟Q比较接近一点，那有什么样的做法呢。

你会发现说你可能的moving plan，就是你把Q呢把P呢重新塑造成Q的，方法有无穷多种，你可以说我把这边的土搬到这里来，我把这边的土搬到这里来，把P呢变成Q。



![](img/561710c1d9812eec222b4092dfae0946_207.png)

但你也可以舍近求远，说我把这里的土搬到这里来，把这里的土搬到这里来，舍近求远一样，还是可以把P变成Q，所以当我们考虑比较复杂的distribution的时候，把Q把P变成Q的方法。

是有非常非常多不同的方法，你有各式各样不同的moving plan，用不同的moving plan，你算出来的距离，你推土机平均走的距离就不一样啊，在左边这个例子里面，推土机平均走的距离比较小。

在右边这个例子里面，因为舍近求远，推土机平均走的距离比较大，那难道这个B跟Q他们之间的vs stdistance，会根据你的不同的方法不同的，这个推土机行进的方法就算出不同的值吗。



![](img/561710c1d9812eec222b4092dfae0946_209.png)

为了让vesl stin distance只有一个值。

![](img/561710c1d9812eec222b4092dfae0946_211.png)

所以这边VESSSTIN的定义是穷举所有的movie plan，然后看哪一个推土的方法，哪一个moving的moving的计划。



![](img/561710c1d9812eec222b4092dfae0946_213.png)

哪一个推土的计划可以让平均的距离最小。

![](img/561710c1d9812eec222b4092dfae0946_215.png)

那个最小的值才是vs stdistance哦，所以会穷举所有把P变成Q的方法。

![](img/561710c1d9812eec222b4092dfae0946_217.png)

然后看哪一个推图的平均距离最短，那选最短的那个距离当做是resident distance，所以其实要计算vs stdistance是挺麻烦的。



![](img/561710c1d9812eec222b4092dfae0946_219.png)

你会发现说光我只是要计算一个distance，我居然还要解一个optimization的问题。

![](img/561710c1d9812eec222b4092dfae0946_221.png)

解说这个optimization的问题，才能算vs ant distance好。

![](img/561710c1d9812eec222b4092dfae0946_223.png)

那我们先不讲怎么计算vs stdistance这件事，我们先来讲，假设我们能够计算faster than distance的话，它可以带给我们什么样的好处呢，那假设pg跟p data它们的距离是D0。

那在这个例子里面，veal stin distant算出来就是D0，在这个例子里面，pg跟p data它们之间的距离是d one，那vs state算出来的距离就是d one，那假设d one比较小。

低龄比较大，那算VESASTIN的时候，这个case的VESASTIN就比较小，这个case的VESASTIN就比较大。



![](img/561710c1d9812eec222b4092dfae0946_225.png)

所以我们就可以知道说由左向右的时候，vs stan是越来越小的，所以如果你观察vs stands的vs stance的话，会知道说从左到右我们的generator越来越进步。

但是如果你观察discriminator，你会发现你观察不到任何东西，对discriminator而言，这边每一个case算出来的js divergence都是一样的，都是一样好或一样差。

但是如果换成vs stdistance。

![](img/561710c1d9812eec222b4092dfae0946_227.png)

由左向右的时候，我们会知道说我们的discriminator，做我们的generator做的越来越好，所以我们换一个计算divergence的方式。

我们就可以解决this divergence有可能带来的问题。

![](img/561710c1d9812eec222b4092dfae0946_229.png)

这让我想到什么呢，这又让我想到一个演化的例子哦。

![](img/561710c1d9812eec222b4092dfae0946_231.png)

就是眼睛的生成好，右边呢这个是人类的眼睛啊，人类的眼睛是非常的复杂的，那有一些生物它有非常原始的眼睛，比如说有一些细胞具备有感光的能力啊，这可以看作是最原始的眼睛，但是这些最原始的眼睛。

怎么变成最复杂的眼睛呢，这对人类来说其实觉得非常难想象，这个这么简单，只是一些感光的细胞在皮肤上经过呃突变，产生一些感光细胞，听起来像是合理的，但是天泽突变，怎么可能产生这么复杂的呃器官呢。

怎么产生眼睛这么精巧的器官呢，那如果你直接觉得说从这个地方就可以，一步跳到这个地方，那根本不可能发生，但是中间其实是有很多连续的步骤哦。



![](img/561710c1d9812eec222b4092dfae0946_233.png)

从感光细胞到眼睛，中间其实是有连续的步骤的，举例来说，感光的细胞可能会呃，出现在一个比较凹陷的地方哦，皮肤凹陷下去，这样感光细胞呢就可以接受，来自不同方向的光源，然后后来觉得说呢干脆把凹陷的地方盖起来。



![](img/561710c1d9812eec222b4092dfae0946_235.png)

后来觉得盖起来的地方里面呢可以放一些啊，一体，然后最后呢就变成了人的眼睛，而从这边跳到这边，这一步非常大，但是这边每一小步，都可以让一个生命存活的几率变大，都可以让生命繁衍下去的几率变高。

既然这边每一个步骤都可以让生命繁衍几率，繁衍的几率变高，那生命就可以从左边一直演化到右边，最终产生复杂的器官，而我觉得对于当你使用WGA，当你使用这个vs stdistance。

来衡量你的divergence的时候，其实就制造了类似的效果，本来pg10跟PDA非常的遥远，你要他一步从这里跑到这里。



![](img/561710c1d9812eec222b4092dfae0946_237.png)

一步从这里跑到这里，让这个PG0跟PDA直接ALI在一起，是不可能的，可能非常的困，非常的困难，对js divergence而言。



![](img/561710c1d9812eec222b4092dfae0946_239.png)

他需要做到直接从这一步跳到这一步，他的js divergence the loft才会有差异。

![](img/561710c1d9812eec222b4092dfae0946_241.png)

但是对w distance而言，你只要每次有稍微把pg往p data挪近一点，w distance就会有变化，w distance有变化。

你才有办法劝你的generator去minimize w distance哦，所以这就是为什么当我们从js divergence，换成best sistant distance的时候，可以带来的好处。

好，那W跟实际上就是用用，你当你用vs stdistance来取代js divergence的时候，这个game呢就叫做w game了，那接下来你会遇到的问题就是，vs stdistance要怎么算呢。

p data跟pg它的VESSSTDISTANCE要怎么计算呢，vs stdistance是一个非常复杂的东西，我光要算个vs stin distance，还要截一个optimization的问题。

实际上要怎么计算呢，好那这边呢就不讲过程，直接告诉你结果，解下面这一个optimization的problem，解出来以后，你得到的值就是VESASTDISTANCE。

就是p data跟pg的vs stdistance，那这边我发现我犯了一个小小的错误，是什么样小小的错误呢，就是这边的X大可能都把它改成Y，会跟前面的投影片比较，是啊好。

所以这边的X在前面的投影片里面其实都是Y，他们指的都是一张图片，而不是他们指的都是network的输出，而不是network的输入，好那这个式子里面有什么样的东西呢，我们就观察一下这个式子。

这个式子里面有说X如果是从p data来的，那我们要计算它的d of FX的期望值，X如果是从pg来的，我们计算它的DOFX的期望值，但是前面乘上一个负号。

所以如果你要maximize这个objective function，你会达成什么样的效果，你会达成，如果X是从p data saml出来的。

DOFX就discriminator的output要越大越好，如果X是从pg从generator sample出来的，那d of FX也就discriminator的output，应该要越小越好。

但是这边呢还有另外一个限制，它不是光叫你把这里括号大，括号里面的值变大就好，还有一个限制是D不能够是一个随便的function，一必须要是一个one dience的function。

可能会问说one dience是什么东西呢，如果你不知道是什么的话，也没有关系，我们这边你就想成第一，必须要是一个足够平滑的function好，它不可以是变动很剧烈的function。

它必须要是一个足够平滑的function，那为什么足够平滑这件事情是非常重要的呢，我们可以从直观来理解它，好假设这个是真正的资料的分布，这是generated的资料的分布，如果我们没有这个限制。

只看大括号里面的值的话，大括号里面的目标是要这些真正的值，它的DOFX越大越好，那要让generated的值，它的DOFX越小越好，如果你没有做任何限制，只单纯要这边的值越大越好，这边的值越小越好。

在蓝色的点跟呃绿色的点也就是真正的image，跟generated的image没有任何重叠的情况下，你的discriminator会做什么。



![](img/561710c1d9812eec222b4092dfae0946_243.png)

他会给real的image无限大的正值，给呃generated the image无限大的负值，所以你这个training根本就没有办法收敛，而且你会发现说只要这两堆data没有重叠。

你算出来的值都是无限大，你算出来的这个maximum值都是无限大，这显然不是我们要的，这不就跟js divergence的问题一模一样吗，所以这边你需要加上这个限制，其实你要加上这个限制以后。

你这个MESSAM的值才会是veal state distance。

![](img/561710c1d9812eec222b4092dfae0946_245.png)

你才是做w game好，那为什么加上这个限制，就可以解决刚才的问题呢，因为这个限制啊是要求discriminator不可以太啊，变化剧烈，它必须要够平滑，那今天如果你要求你的discriminator。

够平滑的时候，假设real data跟generated的data他们距离比较近，那你就没有办法让real的data值非常大，然后generated的值非常小，因为如果你让real的值非常大。

卷的rate值非常小，它们中间的差距很大，那这一个discriminator变化就很剧烈嘛，它就不平滑了，它就不是one disc了，那为了要是one this is，这边的值没办法很大。

这边的值没办法很小，如果real跟genererrated the data差距离很远。

![](img/561710c1d9812eec222b4092dfae0946_247.png)

那它们的值就可以差很多，你这边算出来的值就会比较大，你的best accent distance就比较大。



![](img/561710c1d9812eec222b4092dfae0946_249.png)

如果real跟generating很近，就算他们没有重合，因为有了这个限制，有了这一个呃，写在max下面的one dance function的限制。

因为有one this is function的限制，所以real data的值跟generated，data值就没有办法差很多，你算出来的vs and distance就会比较小。



![](img/561710c1d9812eec222b4092dfae0946_251.png)

那接下来的问题就是怎么做到这个限制呢，怎么确保discriminator，一定符合one distance function的限制呢，最早刚提出w game的时候，其实没有什么好想法。

只知道写出了这个式子，那要怎么真的解这个式子呢，嗯有点困难，所以最早的一篇w get的paper，最早使用vs stin的那一篇paper，他说了，他做了一个呃比较rough，比较粗糙的处理的方法。

他是说啊我就train个network，那train network的时候呢，如果我training的那个参数啊，呃我就要求它BD在C跟负C之间。

如果超过C就gradient design update以后，超过C就设为C，gradient descent update后小于负C就直接设为负C，那其实这个方法并不一定真的能够。

让discriminator变成one this is function，但你可以想象说，这个方法也许真的可以，让我们的discriminator比较平滑。

但他并没有真的去解这个optimization department，他并没有真的让discriminator和这个限制，所以接下来就有其他的想法啦，有一个想法叫做gradient的penalty。

gradient penalty呢是出自improve w game这篇paper。

![](img/561710c1d9812eec222b4092dfae0946_253.png)

那improve w跟Zen paper是说啊。

![](img/561710c1d9812eec222b4092dfae0946_255.png)

假设这个是你的real data的分布，这个是你的这个啊，呃fake data的分布，那我在real data这边取一个sample，fake data这边取一个sample。



![](img/561710c1d9812eec222b4092dfae0946_257.png)

两点连线，中间再取一个sample，我要求这个点它的gradient要接近一。

![](img/561710c1d9812eec222b4092dfae0946_259.png)

那你可能觉得说这个不知道，在不知道在说些什么，这样这件事情的关系，跟这个限制的关系到底是什么呢，那就详见prove w w game的paper。



![](img/561710c1d9812eec222b4092dfae0946_261.png)

那其实我觉得你现在也不一定要真的非常较真。

![](img/561710c1d9812eec222b4092dfae0946_263.png)

说这件事情，gradient penalty跟这个限制之间的关系，因为其实有更多其他的方法，真的可以去解这个问题，那其实后来improve w get之后。

还有什么improve对improve w game，真的我这边paper啊，他就是把这个限制再稍微改一改，有另外一篇paper就叫improve the improve w game。



![](img/561710c1d9812eec222b4092dfae0946_265.png)

那今天其实你有一个方法真的把第一限制。

![](img/561710c1d9812eec222b4092dfae0946_267.png)

让它是one lest function，这个叫做spectral normalization。

![](img/561710c1d9812eec222b4092dfae0946_269.png)

那我就把他论文放在这边给大家参考。

![](img/561710c1d9812eec222b4092dfae0946_271.png)

那如果你要train真的非常好的game，你可能会需要用到spectrum的normalization。



![](img/561710c1d9812eec222b4092dfae0946_273.png)

讲到这边告正好告一个段落，那呃我看也快6。20了。

![](img/561710c1d9812eec222b4092dfae0946_275.png)

我们就停在这边好了好，我们就看看大家有没有问题要问。

![](img/561710c1d9812eec222b4092dfae0946_277.png)

那如果你没有问题的话，你就可以先离开了，好那你请说。

![](img/561710c1d9812eec222b4092dfae0946_279.png)

![](img/561710c1d9812eec222b4092dfae0946_280.png)

就是每一次确实把这一次的丢进去，还是要把这只跟之前又只丢这只会不会有，就是只是简单一点再点。

![](img/561710c1d9812eec222b4092dfae0946_282.png)

那你把以前更烂一些，就比反而反而他得到的分数较高。

![](img/561710c1d9812eec222b4092dfae0946_284.png)

好呃，我们先我们从实作跟理论两个方向来考虑好，如果今天我们看的是理论的话，理论是要量卷的，现在的generator的open跟啊真正data之间的距离，所以你不需要去管之前的东西，你只要你对。

你只要看现在的generator的output就好了，这个是理论上的做法，但是实作上你确实可以把过去的资料也加进来，那过去的资料加进来，好处可能是哎。

我现在觉得RATOR只宣只generate1部分的资料啊。

![](img/561710c1d9812eec222b4092dfae0946_286.png)

那过去的资料比较多，都是ENGGENERATE在那里了啊，那我把过去的资料再加上来。

![](img/561710c1d9812eec222b4092dfae0946_288.png)

我资料比较多，也许我训练出来的结果会比较robust，就把过去的资料加进来。

![](img/561710c1d9812eec222b4092dfae0946_290.png)

这样子的想法是真的有人会做的，这是一个呃train game的替补。

![](img/561710c1d9812eec222b4092dfae0946_292.png)

而且其实这边你也还没有发现一个问题，就是呃我们今天呐，因为我们说我们确认那个discriminator，maximum的值就代表了我们的divergence嘛，那呃其实照理说。

我们每次discriminator应该都是从TRA的，对不对，我们每次就是重新去重新initialize，一个discriminator重新去训练，但是在实作上没有任何人是这么做的。

因为实际上我们在update discriminator的时候，我们并没有办法真的跑很多，Iteration。



![](img/561710c1d9812eec222b4092dfae0946_294.png)

本来理论上应该是跑跑跑，跑到discriminator真的收敛为止，但实际上没有人要这么做。

![](img/561710c1d9812eec222b4092dfae0946_296.png)

因为你每次如果discriminator都要跑跑到首领上，update是generator太太花时间了。



![](img/561710c1d9812eec222b4092dfae0946_298.png)

没有人这么做，所以真正所以变成实际上的做法，都是discriminate update。

![](img/561710c1d9812eec222b4092dfae0946_300.png)

几次就要轮到generator update，所以discriminator其实update的次数是非常的少的，我们并没有办法真的去maximize那一个objective function。

所以变成说我们discriminator都不是从头train的，它的参数都是从前一个iteration继承过来的，它都是从前一个iteration再重新称起，对这就是有很多理论跟实作上有歧义的地方。

这样回答到你的问题吗，好就大家有，大家有事就可以先走啊啊如果有问题的话，就欢迎你留下来问好诶，你还有没有问题想问呢。



![](img/561710c1d9812eec222b4092dfae0946_302.png)

哎大家有问题要问吗，哎哎你说。

![](img/561710c1d9812eec222b4092dfae0946_304.png)

所以说在刚才那个。

![](img/561710c1d9812eec222b4092dfae0946_306.png)

好你们先想一下，我刚刚还忘了复数，亲，那个刚才那个同学问那同学，问题，是说我我们在训练那个discriminator的时候呃，能不能够用之前generator sample出来的资料，好没关系。

你慢慢来诶，大家有事就可以先离开，没有关系。

![](img/561710c1d9812eec222b4092dfae0946_308.png)

![](img/561710c1d9812eec222b4092dfae0946_309.png)

嘿嘿啊，你请说话。

![](img/561710c1d9812eec222b4092dfae0946_311.png)

实际上在这就该理论讲的那一块，我们要找到一个是校考的哪个卷子诶。

![](img/561710c1d9812eec222b4092dfae0946_313.png)

找找到一个比哎我们要做的是divergence的function。

![](img/561710c1d9812eec222b4092dfae0946_315.png)

其实是已经定好了，就比如说js divergence或W或者w distance，那个是我们事先定好，我们training的目标是在这个固定好的divergence的，对，就是这样，可刚才有人说。

因为这个奶油其实比较难的，或者是你真的对外都比较难的。

![](img/561710c1d9812eec222b4092dfae0946_317.png)

如果说可以积攒了，那我们就直接用传统方法，让他这个真的出来都越来越近。

![](img/561710c1d9812eec222b4092dfae0946_319.png)

但就是今天要给的，这是因为我没法计算，这个等于是要找到一个镜子。

![](img/561710c1d9812eec222b4092dfae0946_321.png)

这个这个载人的镜，一个可以计算的镜头，就是这样，就是这样，所以说所以说刚才讲那个这样子那个again，那你上面讲的那个，咱们这中学是我们要去学的东西，还是说他是我们的，就是我们要算的那个百REGI。

你是说我们刚才在讲w game的时候，我猜你就是指这一页投影片这个东西是什么。

![](img/561710c1d9812eec222b4092dfae0946_323.png)

对不对，这个东西解完，就这个maximum的值就是vessels and distance。

![](img/561710c1d9812eec222b4092dfae0946_325.png)

最多这个东西动的是D对对。

![](img/561710c1d9812eec222b4092dfae0946_327.png)

就是你把D劝完，然后这边会得到一个value吗。

![](img/561710c1d9812eec222b4092dfae0946_329.png)