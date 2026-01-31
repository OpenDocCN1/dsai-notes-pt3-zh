# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P46：5-选修-GAN理论-1 - AI算法工程师Future - BV1ruqABeEFX

好好好，各位同学大家好，那我们就来上课吧，哦那上周我们讲了什么呢，上周我们讲了game的直观的想法，那今天呢我们要来讲game背后的理论，那我们今天要讲的呢是当初2014年。

dn good fellow在propose game的时候，他的想法诶，等下可以仔细听看看，听看看说跟我们上周讲的变得直观的想法，里面有没有矛盾的地方，其实是有一些地方还破矛盾的。

至今仍然没有好的solution，还有好的说法可以解决，哎你说可以开冷气吗，呃好啊，这样子开车吗，我来演啊，家在那什么问题要问吗，好如果大家没有什么问题要问的话呢。

那我们就来讲一下这个gain呢背后的理论。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_1.png)

当初yang fellow是怎么说的，好，那这个是我们上周说的，要大家在这个作业三支一一里面，要让gain做的事情，就让琪琪看了很多动画的图以后呢，产生呃自己产生二次元人物的头像，让我们知道说呃。

电他要做的事情，就是根据很多example去进行生成，那所谓生存这件事情，到底是一个什么样的问题呢，而假设我们今天要生成的东西是image，那我们用X呢来代表一张image。

那每一个image呢都是high dimensional，那假设你今天产生6464的image，它是64×64维空间中的一个点，那这边呢为了画图方便，我们假设每一个X就是二维空间中的一个点，好。

那我们现在要产生的东西，比如说我们要产生的image，它其实有一个固定的distribution，我们这边呢写成p data lof，而它有一个固定的distribution，什么意思呢。

在这整个image的space里面，其实只有非常少的部分，其实只有一小部分，它是它simple出来的image，看起来像是人脸，在多数的空间中，simple出来的image它都不像是人脸，举例来说。

在这个图上的例子里面，可能只有蓝色的这个区域，你去simple出X去simple个image，它看起来呢像是人脸啊。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_3.png)

举例来说，你在这个地方sample呢，你看起来的图片长得是这个样子，那你在其他地方，sample呢看起来的图片看起来就不像是人脸哦，所以假设我们今天要生成的X是人脸的话。

它有一个固定的distribution，这个distribution在蓝色的这个区域，它的几率是高的，在蓝色区域以外，它的几率是低的好，那我们今天要机器做的事情是什么呢。

我们要机器去找出这一个distribution，而这个distribution他到底长什么样子，我们实际上是不知道的，我们可以收集很多的image，知道说呃我们可以收集很多的X。

知道说X可能在某些地方分布比较高，但是要我们把他的式子找出来，我们是不知道要怎么做的，所以现在电做的是一个generation model。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_5.png)

做的事情就是要找出这个distribution，那在有get之前，我们怎么做GENERARRATIVE这件事呢，我们是用maximum likelihood estimation。

那其实maxwell likelihood estimation，我们在这个之前machine learning的时候有讲过了，这边呢只是一个很快的复习。

而我们现在有一个data的distribution啊，它是t data的F这个distribution实际上长什么样子，就是这个distribution它实际上它的formulation长什么样子。

我们是不知道的，我们可以从里面sample它，所以从这个distribution sample，它的意思就是，从你假设你做的是二次元人物的生成。

那也就是从你的database里面simple出image呃，这个就是从这个distribution里面sample1些贝塔出来，我们可以sample它，但是我们不知道它长什么样子好。

那接下来呢我们要自己去找一个distribution，这个distribution写成P下标GOA，那这个distribution呢是由一组参数SE达呢所操控的，而所谓由FA所操控的。

意思是说呢这个distribution举例来说，假设它是一个高选mixture的model，那这个set达呢，指的就是那个高选的mean跟variance，那我们要去调整这个高悬的命跟variant。

使得我们得到的这个distribution pg，跟真实的distribution p data塔越接近越好哦，所以虽然我们不知道p data塔长什么样子。

我们只能够从它从p data塔里面去sample，但是我们希望这个pg我们可以找一个这个sea，让pg跟p data a越接近越好好，那怎么做呢，假设你是用maximum likelihood的话。

怎么做呢，首先我们可以从p data里面sample些东西出来，sample x1 x2到XN好，可sample出一堆X出来好，接下来呢对每一个sample出来的X。

我们都可以计算它的LIKEYHOOD，所以可以计算他的LIKEYHOOD，意思是说假设给定一组参数，Theta，给定一组参数，Theta。

我们就知道pg这个pom ability and distribution长什么样子，知道这个popularity of distribution长什么样子，我们就可以计算。

从这个distribution里面sample出某一个xxi的几率，我们可以计算出这个like a ho，而接下来我们要做的事情就是，我们要找出一个sea，使得pg跟p data塔越接近越好越好。

这件事情的意思就是说呃，我们希望这些从BP data里面sample出来的example，如果是用pg这个distribution来产生的话，他的like混越大越好。

那每笔data它从pg里面产生出来的lily棍，我们都是可以算出来的，让我们把所有的几率乘起来，就得到一个偷偷的来赔AY混，那我们希望这个偷偷的来赔AY混，越大越好。

那怎么让total like liqu越大越好呢，你就是要去找一个sea star，找一组最佳的参数，它可以去maximize l这个值，这呃举例来说，在这个case里面呢。

假设你是一个高层vor model，就可能希望他的命呢落在这些地方哦，他的variance长这样啊，可能是高shvor model，它产生这些data的几率呢就是最大的好。

那这个是maxim like paper，我记得我们在machine类那堂课里面讲。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_7.png)

generating model的时候呢，就已经提过这些东西了，好那没什么，LIKEY混，其实如果你觉得他没有很直观的话，这边给你maxim lily co的另外一个解释。

就maxim lily co呢它等同于minimize k l的divergence，什么意思呢，我们说masm like，在MESMMELILLE里面，我们做的事情。

就是我们从P贝塔里面simple出M比贝塔，然后呢给我们一组参数，Theta，我们就可以计算每一个X被sample出来的几率，我们把这些几率全部乘起来，这个是我们要去maximize的对象。

那这个式子呢你可以稍微改变一下，你就呃在前面取一个log啊，取一个log不影响你找出来的呃，最好的sea好想这个大家都可以很快的知道啊，你可以把logo放进去啊，本来是很多项相乘。

取log等同于每一项取log以后相加，这个我相信对大家来说也没有问题，好接下来啊这件事情是什么意思呢，some mention over i等于一到n submention over，第一笔。

example到第N比，example这件事情其实就是在approximate，从p data这个distribution里面simple x出来哎。

从p data a这个distribution里面sample x出来，你就得到x1 x2到XN哦，所以今天这个式子他要maximize的对象，其实就是maximize呢。

log pg of x of maximize这一项的这个呃，expected的value，那你这个expected expectation的distribution呢，是你要sample的data好。

接下来呢我们可以把这个这一项啊，我们可以把这expectation这一项呢把它展开啊，它其实就是一个积分，好这个EXPLEXPECTATION，从X这个X呢是从BZ卡里面sample出来的。

从PA盘面sample出来的，意思就是说呢对X做积分，然后把它乘PA塔喽，FX然后乘上log呢，P区perfect好，接下来呢加一项看起来没有什么用的东西，我们在后面呢加这么一项，这一项是什么东西呢。

你看一下这一项哦，这一项里面它只有p data a，它跟pg是完全没有任何关系的哦，所以今天加这一项，根本不会影响你找出来的最大的F，那既然加这一项一点用都没有，为什么要加这一项呢。

加这一项目的是为了要告诉你说，Makes man likeihood，它就是kl divergence，因为加上这一项以后，你就可以把这个式子做一下整理，你看这边呢是对X做积分。

乘上p data塔和vex，再乘上log pg office，这边呢是减掉对X多积分，p data lovex乘上log p data a lovex哦，所以这边有积分p dal vs。

这边有积分P等讨best，所以可以把它提出来，可以把它提出来哦，所以这一项跟这一项可以把它挤出来，然后这边就剩下rog pg减掉log p data塔，那大家一秒钟就可以反映说log p g减掉lop。

data a就是PG除以p data塔，总之这个式子啊他就是PDA跟pg的kl divergence，所以你找一个sea去maximize like he，Could。

等同于找一个C拉去minimize p data，跟pg的ko diversion，那如果你看到这边觉得数学式太多，你没有看懂的话呢，其实你只要知道一件事就好，所谓的maximum likeho。

就我们现在机器学习里面讲说呃，我们今天要找一个generator的model，去maximum likelihood，就maximum likelihood这件事情，其实就等同于minimize。

你的generative models的所定义的这个distribution，pg跟你现在的data p data塔之间的kl divergence好，那接下来我们会遇到的问题是。

假设我们的pg只是一个高选mixture model啊，那它显然有非常多的限制，我们希望pg是一个general的distribution，它可以不是高选，它可以是比高选更复杂的东西。

但是假设你今天把pg，换成一个比高选更复杂的东西，你会遇到什么问题呢，你会遇到问题就是你算不出你的likelihood，你算不出PGS基本SA这一项，而且假设今天PGX这个东西啊。

它是一个高选vor model，给你一个X，你可以计算它被sample出来的几率，但是如果它是一个很复杂的东西，他等一下我会讲说他可能是一个neural network。

那你就没有办法计算他的LIKELIHO好，所以所以怎么办呢，所以怎么办呢。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_9.png)

所以就有了一些新的想法，那其实亚马逊自动的产生成东西，比如说做image的generation从来都不是新的题目，你可能看说哦，最近用电呢做了很多image generation的task。

好像image generation是这几年才有的东西，其实不是image generation，这件事情呢在80年代就有人做过了，而那个时候的做法就是用高选mixture model啊。

就收集很多很多的image，那每个image其实就是高维中间一个data point，然后你就可以弄一个高深mixture model，去MAXIMI产生那些image likehood。

但是如果你看这个呃文献的话呢，你看这个古圣先贤留下来的东西，就会发现说过去做的，如果你用高深Mission model产生出来的image，非常非常的糊，非常非常的糊。

那这个可能原因是因为呃image啊，所以如果用高shamor model，它其实就不是一个manifold，就是你用高shamor model，你不管怎么调你的命跟variance。

他就不像是你的target distribution，所以你怎么做都是做不好哦，所以我们需要更generalize又更generalize的方式呢，来learn generation这件事情好。

那在这个game里面呢，在generative adversal network里面呢，我们的generator就是一个network，好我们来把它写作剧啊，等下我们就会告诉大家说一个network。

他怎么被看作是一个probability的distribution，好我们知道说我们选择RATOR就是一个network，那我们也都知道说network呢就是input一个东西。

然后呢output一个东西，举例来说呢，你input一个从某一个distribution sample出来的noise z啊，你input一个随机的vector z，然后呢他就会output一个X啊。

这个X呢，我们如果我们把这个generator，G看作是一个function的话，这个X呢就是g of z啊，这个X呢就是g of z啊，如果你今天是做image generation的话呢。

那你的X呢就是一个image好，然后我们说这个Z呢是从某一个prior distribution，比如说是从一个normal distribution里面sample出来的。

而今天每次sample出一个Z，你把它丢到这个generator里面，你就会得到一个X，你sample不同的Z，你得到的S呢就不一样，那今天这个Z呢是从一个高深distribution里面。

sample出来的，那你现在呢把这些从高深distribution里面sample出来的Z，通通通过G得到另外一大堆sample，把这些sample通通集合起来。

你得到的就会是另外一个distribution，那虽然input是一个normal distribution，是一个呃，是一个单纯的高效distribution，但是你通过这个generator以后。

因为这个generator是一个network，他可以把这个Z呢通过一个非常复杂的转换，把它变成X，所以你今天把通过这个generator产生出来的，S通通集合起来。

它可以是一个非常复杂的distribution哦，而这个distribution呢就是我们所谓的pg，那有人可能会问说，这个por distribution应该要设成什么样子呢。

好像文献上有人会用normal distribution，有人会用uniform distribution，大家可以在作业里面verify一下，说你觉得哪一种比较好，其实哪一种比较好，我其实也忘记了。

这样我觉得呢呃其实这边拍distribution用哪种distribution，也许影响并没有那么大，为什么呢，因为generator他是一个network，我们在一开学开学第一堂课就有讲过。

说一个hien there are的network，他就可以approximate任何function，那更何况是有多个hidden layer的network。

它可以approximate非常复杂的function，所以今天就算是你的input distribution，是一个非常简单的distribution，通过了这个part。

通过了这个network以后，他也可以把这个简单的distribution，凹成各式各样不同的形状，所以不用担心说啊，我这边如果是input a normal distribution。

会不会对output来说有很大的限制，其实不会，因为通过一个generator以后，你可以把一个单纯的normal distribution，凹成各式各样复杂的形状好，那我们接下来的目标是什么。

我们接下来的目标是，希望generator根据这个generator所定义出来的，这个distribution pg，它跟我们的目标跟我们的data的distribution，p data越接近越好好。

那如果要写一个optimization的formulation的话呢，这个formulation看起来是这个样子，就我们要找一个generator，我们要找一个generator区。

这个generator可以让它所定义出来的distribution pg，跟我们的data p data塔之间的某种divergence越小越好，举例来说。

如果是maximum likely who的话，它就是要minimize kl diversion，然后我们看到说其实在game里面，我们minimized的不是kl diversion。

而是其他的diversion，然后这边写一个DIV呢，就代表说反正他是某一种diversion，我们现在做的事情就是找一个generator。

这个generator定义出一个distribution pg，这个pg可以跟我们的p data a的divergence呢，越接近越好好，再来一个问题，就是怎么计算这个divergence呢。

假设你能够计算这个divergence，你要找一个机器minimize这个divergence，那不就只是gradient descent，用gradient descent就可以做了，对不对。

但是问题就是你要怎么计算出这个divergence呢，p data塔他的formulation我们是不知道的，他并不是什么高深distribution，它的formulation我们是不知道的。

pg他的formulations我们也是不知道的，假设pg跟p data他的formulation我们是知道的，我们其实带进那个divergence的formulation里面。

我们其实就可以算出他的diversion是多少了，那我们就用gradient descent去minimize他的divergence，但问题就是pg跟PC它它的formulation，我们是不知道的。

他formulation是不知道的，我们根本就不知道要怎么去计算它的divergence，所以根本就不知道要怎么找一个G去minimize，他的divergence，所以怎么办呢。

这个就是game呢神奇的地方好。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_11.png)

那在进入比较多的数学式之前呢，我们先很直观的来讲一下，说见到底是怎么做到minimize divergence，这件事情的好，那这边的前提是。

我们不知道pg跟p data的distribution长什么样子，但是我们可以从这两个distribution里面去simple data出来。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_13.png)

什么意思呢，什么叫做从p data去simple distribution出来呢，你就是把你的database拿出来，假设我们做二次元人物头像生成的话，就把你的database拿出来。

然后从里面sample很多image出来，这个就是从p data这个distribution里面做sample，怎么对pg做sample呢。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_15.png)

我们说这个pg啊，它是由你的generator所定义的，那我们在使用这个generator的时候，我们是从某一个party stribution里面去sample，一大堆的vector。

每一个vector就会产生一张image哦，所以所谓的从pg里面做sample，其实就是random sample，一个vector，把这个vector呢PO到选择REER面产生一张image。

这个就是从pg里面做sample，所以我们可以从p data里面做sample，我们也可以从pg里面做sample，我们现在的问题，接下来的问题就是我们可以从pg和PDA做sample。

根据这个sample，我们要怎么知道这两个distribution的divergence呢。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_17.png)

啊那更神奇的地方就是透过discriminator，我们可以来量这两个distribution间的divergence哦，就假设这个蓝色的星星是从p data里面，sample出来的东西。

红色的星星呢是从pg里面sample出来的东西，那根据这些data塔，我们去训练一个discriminator，那上周我们已经讲过说所谓训练的distant，Discriminator。

意思就是给呃PDA的分数越大越好，给PG的分数呢越小越好，你去训练一个discriminator，这个训练的结果就会告诉我们，p data a跟pg他们之间的divergence呢有多大啊，有多大好。

那我们上周讲过说我们要训练个discriminator，我们是怎么训练个discriminator的呢，我们会写一个objective function。

我们会写一个objective function b1啊，那这个objective function它跟两项有关，一个是跟你的这个generator有关，一个是跟你的discriminator有关。

那我们在train这个discriminator的时候呢，我们会FX住generator好，所以G这一项呢是fix数的，我们只是去调这个discriminator参数。

想办法去maximize后面这一项好，那后面这一项是什么意思呢，后面这项意思是说，假设X是从p data里面sample出来的，那我们希望log d o FX越大越好。

也就我们希望discriminator的output，假设X呢是从p data塔里面sample出来的，我们就希望呢这个DIOFX越大越好，反之假设X呢是从genererator sample出来的。

那因为我们要maximize v这一项，所么叫maximize d项也要maximize第二项，而如果X是从P区里面sample出来的，那我们要maximize log1减D2FX。

maximize log log1减DOFX，就是maximize1减DOFX，也就是要minimize d o FX，所以X如果是从pg里面sample出来的，我们就希望它的值呢越小越好。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_19.png)

然后在训练的时候，我们就知道找一个D，它可以maximize的这个objective function，那其实如果你之前的这个呃machine learning有学通的话呢。

下面这个optimization的式子啊，跟train一个binary classify的式子，其实是完全一模一样的，就假设你今天要train一个logistic regression model。

logist regression model是一个binary的classify，然后呢你就把p data塔当做是class y，把pg当做是class to。

然后你train个logistic regression model，你会发现说你的objective function其实就是下面这个式子，其实就是下面这个式子哦。

所以今天这个discriminator在做的事情，跟一个binary classify在做的事情，其实是一模一样的，就假设蓝色的点是cs one，红色的点是class two。

Discriminator，就是一个binary的classify蹭下去，然后这个binary classify呢它是在minimize cross entropy。

我们之前讲过说binary classify小minimize cross entropy，要mini mize cos entrop，如果你minimize cross entropy的话呢，你就呃。

你其实就是在解这一个optimization的problem。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_21.png)

你其实就是在解这个optimization的problem好，那这片神奇的地方呢是，当我们解完这个optimization的problem的时候，你最后会得到一个loss，对不对。

你会得到一个最小的loss，或者是得到一个最大的objective的value，所以我们今天这边呢并不是minimize loss，而是maximize一个OBJECTIFUNCTION。

这个V呢是我们的objective value，我们要去调低呢，去maximize这个objective of value这个。

然后这边神奇的地方是这个maximize the objective value，就是你把这个D劝到最好就给了这些data，你把这次的D呢劝到最好，找出最大的D可以达到的objective value。

这个value其实会是跟js divergence，是有非常密切的关系，甚至你可以说他其实等下会有额更详细的证明，你可以说这个结果它其实就是cs divergence，也许你听了觉得很神奇。

但是我们可以给你一个非常非常直观的解释，你一秒钟就知道说，为什么这个东西，他应该跟某一个divergence是有关系的。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_23.png)

因为想想看，假设我们现在simple出来的data，它们靠的很近，有这个蓝色的这些星星跟红色的星星，如果把它们视成两个类别的话，它们靠的很近，对一个binary的classifier来说。

你还很难区别红色的星星跟蓝色的星星的不同，因为对一个binary classify，也就你的discriminator来说，它很难区别这两个类别的不同，所以你今天称下去，你的loss就没有办法压低。

对不对，就假设今天这两个class他们靠的很近，他们很难分辨很分别，在training data上的loss就会压不下去，或者反过来说你在training data上的loss压不下去。

就是我们刚才看到的那个objective的value，你没有办法把它拉的很高，你没有办法把刚才看到的这个V这一项，你没有办法找到那个D，它让V的值呢变得很大，这个时候意味着什么，这个时候意味着说。

今天这两堆data他们是非常接近的，他们的divergence是小的，所以如果今天对一个discriminator来说，很难分别这两种data之间的不同，它很难达到很大的appected value。

那意味着这两对data的divergence是小的，所以最后你可以达到最好的，objective value跟divergence是会有非常紧密的关系的哦，或者是说啊这个是一样的例子。

假设你的蓝色的星星跟红色的星星，它们距离很远。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_25.png)

他们有很大的divergence，那对discriminator来说，他就可以轻易的分辨这两堆data的不同，也就是说它可以轻易的让你的objective value。

也就这个V的这个value变得很大，那所以当V的value可以变得很大的时候，意味着你的这个两堆data，从p data里面generate出来的东西。

看成pg general generate出来的东西，他们的divergence是大的，所以discriminator就可以轻易分辨它的不同。

discriminator就可以轻易的maximize objected的value好，那在我们进入数学之前呢，有没有在这边先稍微停一下，看多同学有问题要问的呢，OK啦，好如果没有问题要问的话呢。

接下来就是实际上证明给你看，说为什么这个objected value跟divergence是有关系的。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_27.png)

再来就是一堆数学式，好这个数学式是这样，那个gifted的valuable我们就写在右上角啊，写在右上角，它长这个样子啊，它长这个样子好，那我们现在要做的事情是找一个D。

找一个discriminator d，它可以maximize这个式子，G是固定的啊，G是固定的，然后maximize这个式子和maximize这个式子好，怎么maximize这个式子呢，我们把它展开哦。

把本来expectation呢换成积分啊积分，所以这边是从X从P贝塔里面simple x出来，就变成对X做积分乘上P贝塔的贝好，乘上这个log第2face想load第2face。

而这边呢这边是对pg从p g sample x出来，就是对X做积分乘上PG乘上log1减DEOFX，我讲这个对大家来说应该都不成问题好，接下来呢就是这个整理一下，整理一下，因为这边都对X做积分。

对X做积分，所以你把放在基本里面，这一项跟放在基本面这一项加起来好，加起来好，接下来呢我们要想办法找一个D，它可以让这个式子呢越大越好，这边前提有一个假设是d of x，它可以是任何的function。

它可以是任何的function，但这件事在实做实质在实际上不见得是成立的，因为假设DIOFS是一个network的话，network除非他的neural无穷多，不然它其实也没有办法变成任何的方式。

就除非参数量，除非你的neural是无穷多的，不然你也没有办法变成任何的方式，但我们这边做一个非常强的假设是，假设DIOFS它可以是任意的方式，假设DOFX可以是任意的方式的话。

就是你input一个X它的值可以是任何的值，没有限制，你可以assign给DOFX任何的值，你可以EXCE给dio x1任何值，你可以EXCE给dio FX two任何的值。

这个时候假设你要maximize，这一项的话它实际上等同于什么呢，等同于说你知道这边对X做积分嘛，然后把这个中括号里面的式子带各个不同的X，再把它统统加起来嘛，对不对，这就是积分在做的事情。

那你要messing my这一项，然后DOFS又可以带任何的值，那意思就是说你可以把各个不同的X呢，通通都分开算，统统都分开算，所以今天你要找一个D呢去maximize这个式子。

那意思就是说你就把某一个X拿出来，某一个X拿出来，这边是P贝塔，我max low的第二个X加上pg log1减DOFX，你把某一个X拿出来，然后你要找一个D，它可以让这个式子呢越大越好。

那所有不同的S通通都分开来算，都分开来算，因为所有的X都是没有任何关系的，因为不管是哪一个S，你都可以assign给它一个不同的DIOBS，所以这个积分里面的每一项你都分开来算。

你都可以分开为他找一个最好的deal face，哎讲到这边大家有没有问题要问呢，有没有问题要问呢，好如果你可以，你可以接受这个想法的话，再来个问题就是怎么找一个D让这一项最大啊。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_29.png)

那这个数学其实是蛮简单的啊，这个数学其实蛮简单的，我们现在问题是找个B让这个式子最大，p data a是固定的，pg也是固定的，我们唯一要做的事情就是找一个d o max，找一个d o vex的值。

让这个式子算起来最大，那两下为了计算方便，我们把PK还用AI表示d o max，用大D来表示pg，用小B来表示DMX，用大D来表示好，那所以整个式子呢写起来呢就是这个样子好。

怎么找一个D区maximize，这个式子呢，你可以额用你就算求一下他的GRA点啊，求一下他的呃微分，然后呢找先找出它的critical point，就找出微分是零的地方啊，找出微分是零的地方好。

那把这项做微分以后得到什么样的结果呢，a log d对D做微分等于A乘上E除以DVLOG，一减D对D做微分，你得到的结果是B乘上11减D好，再乘上一好，然后我们要找呢微分是零的地方啊。

找微分是零的地方好，那把式子整理一下，把这个一这一项拿到右边去啊，所以一就没有了哦，所以A乘以一除以D大，等于呢呃呃B乘以11减d star好，接下来呢要就要求一下这个d star是多少，要求一下说呃。

什么样的低，可以让这一可以让这个微分的值是零啊，什么样的D呢，它是critical的point好，那就整理一下，我这边都是很简单的数学，就整理一下，我这边是A乘以一减t star等于B乘以d st好。

把A呢乘进去，把A呢乘进去，得到A减A乘以d star，右边是B乘以d st好，整理一下，把有d star项呢挪到同一边去，所以变成A等于A加B乘上d star，而b star呢就等于A除以A加B。

所以我现在知道说，假设我们的d star，我们d star等于A除以A加B嘛，A就是正向啊，然后B呢就是这一项，A就是p data a b呢就是pg好。

那假设我们现在d start of x的值是PDA的vex，除以p data a max加PGOFX，它就可以让这一项的最低的微分为零，然后你可以轻易的检查说呃。

他现在呢它是一个呃local maxim，而不是local mini嘛，也不是say lopoint，可以轻易的检查说他是一个local的，它它其实是它，它不是它是一个maximum。

它不是一个minimum，也不是一个settle po哦，所以今天要怎么让这一项最大，你就把EOFX带这样的值，你就可以让这一项最大。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_31.png)

好所以接下来呢接下来要做的事情是什么呢。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_33.png)

接下来要做的事情，就是把这一项带到这个式子里面，把这一项带到这个式子里面，我们想知道说当我们找出一个最好的D，也就是d star的时候，我们的objective function的值到底长什么样子。

然后最后一展开以后，就会发现说这一项其实就是cs diversion，好，现在我们知道说呢d star呢，它的formulation就写成这个样子好，我们把d star呢带到这里面去，带到这里面去。

我们把这个dio max用PDA除以PDA，加pg呢来表示好，所以把它，然后是把这一项放进来，把这一项放进来啊，你得到结果呢就长这样好，就长这样就长这样好，那接下来呢哦这边有expectation啊。

by expectation展开哦，这边是对从对对这个p data a呢sample x啊，就对X做积分，这边是对pg sample s就对pg呢做积分啊，得到四值呢长这个样子好。

接下来呢为了要把它整理成，看起来像是js diversion，所以呢就做一些嗯看起来没有什么，好像什么事都没有做变换啊，就把这个呃分子跟分母呢都同除二啊，都同除二，分子分母呢都同除二，都同除二好。

那接下来呢你可以把1/2这一项啊，你可以把1/2这一项啊把它提出来好，把它提出来，你得到结果呢是两倍的log2分之一，那这个如果你没有跟上的话呢，不太重要，反正这边有1/2，你可以把它提出来。

变成两倍的log2分之一或等于-2log2好。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_35.png)

然后所以接下来呢我们就知道说今天，那假设我们已经有一个generator g，我们找到了最佳的discriminator d，我们找到最佳discriminator。

也就是dear dear的function会长这个样，当我们找到最佳的disc的时候，这个V这个objective function呢，他就写成这个看起来呢很复杂的样子啊，看起来很复杂的样子啊。

这个是两倍的log2加上对X做积分，然后呢PDA和vex乘上log p data，a max除上PDA跟pg的平均，还有第二项，我这个是额积分s pg乘上log pg，除掉pg和PDA的平均。

后面这一项是什么呢，后面这一项是这个p data跟12，PDA跟pg的平均的ko divergence，如果你不知道它是什么的话，没有关系，反正后面这两项合起来就叫做cs diversion。

或许你比较常听过kl diversion，或者是inverse ko diversion，不常听过js diversion，但是反正后面这个式子啊，他就是PDA跟pg的某一种divergence。

就如果今天PDA跟pg他们距离的越远，好这两项和呢这两项呢合起来就越大，反之呢它们合起来呢就越小啊，总之我们现在得到的结论就是，如果今天我们找到一个最佳的dist带进去以后，我们得到的这个value啊。

它是两倍的，log22倍的p gr和pg的cs diversion，所以我们现在知道说，假设我们另一个discriminator，我们写出了某一个objective function。

我们去maximize那个objective function以后，我们得到的结果，最后可以maximize那个objective function得到这，我们最后maximize的那个value。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_37.png)

其实就是PDA跟pg的js divergence哦。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_39.png)

所以假设呃这边的数学推导，你没有办法跟上的话呢，也没有关系，反正这边想要告诉你的事情，就是说当我们再圈一个discriminator的时候，我们想要做的事情是什么。

当我们在trader discriminator的时候，我们想做的事情就是去evaluate，p data跟pg这两个distribution，sample出来的data。

这两个distribution它们之间的这个js diversion，如果你今天定的这个object function，是跟前面的式子一样的话，你就是在量js divergence。

那你就可以量其他的各种不同的diversion哦。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_41.png)

那所以现在整个问题变成这个样子，我们本来呢是要找一个G，他去minimize pg跟p data的divergence。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_43.png)

我们说后面这个式子你没有办法算，但现在是可以算的，后面这个式子到底是什么呢，后面这个式子到底是什么呢，后面这个式子就是呃，我们今天呢写出一个objective function v of dg。

少一个B去maximize这个式子，它就是pg和p data塔之间的diversion，所以我们现在就可以把divergence这一项，用max对象呢把它替换掉，变成这个样子。

所以我们现在要找一个generator，他generate出来的东西跟你的data越接近越好，你实际上呢要解这样一个optimization的problem，你要解一个MINMAX的problem。

和这个optimization problem里面，它有一个minimum，他有一个maximum啊，看起来非常的复杂哦，你要这个非常的拗口，你要找一个generator。

他要去minimize这一个式子，在这个式子里面它有个discriminator，discriminator要去maximize这个式子哦，我知道说这个看起来非常的复杂，但是他实际上做的事情。

像是以下这个例子所讲的这样，假设世界上只有三个generator，就假设我们要选一个generator，去minimize这个objective function。

但是我们可以现在可以选择选择RATOR，总共只有三个，一个是GY，一个是G2，一个是G3，而假设我们选了g one这个卷的RATOR的话，那v of居腕低，他长这个样子。

就假设你的generator固定是g one，但是你的discriminator，它可以是不同的discriminator，我们假设discriminator呢，呃它可以用一个参数来操控。

所以这个横坐标在改变的时候，代表你选择了不同的discriminator，但实际上是更复杂的状况，实际上discriminator是一个neural network，它是由一个一组。

它是由数百万个参数所控制的，它应该是分布在一个高维空间里面，我这边为了简化问题，我们就说假设当横坐标变化的时候，代表你选择了不同的discriminator好。

代表你选择了不同的discriminator好，今天同样的假设你所以选择ATOR是G2，你把G2带进去，你选择不同的discriminator的时候，你就得到了不同的vo G2 d。

假如你选择rate是G3，你选择不同的discriminator的时候，你就得到不同的v of g3D好，那我们接下来的问题是，我们在给定一个generator的时候。

我们要找一个discriminator，它可以让b of gd最大，那假设我们现在固定我们的generator是g one，的时候，假设我们固定我们的假设。

我们固定我们的generator是g one的时候，那哪一个discriminator可以让VOGD最大呢，那个是落在这个这里的这个discriminator，可以让VOGYD最大。

落在这里的discriminator可以让LEOGQP最大，落在这里的discriminator，可以让VOG3D最大好，接下来我们要找一个G去minimize。

最大的那个discriminator可以找到的value，所以大家听得懂吗，这个点好，我们找一个居，它可以最小化最大的那个discriminator得到的value。

找一个G它可以minimize这个v of gd，用不同的最大的D可以达到的value，这个时候，假设我们的VOGD，长得就像是下面这个例子的话，那那这个问题的solution。

最好的车到底应该是哪一个呢，到底应该是哪一个呢，给你十秒钟的时间想一下，刚才按投影片的时候已经不小心按到了这样子，所以你才知道答案是什么，好十秒钟时间过了啊。

假设这是我们的optimization的problem，Deo gd，他就是长这个样子，我们现在要解这个optimization problem，哪一个G才是我们的solution呢。

哪一个G才是我们的solution呢，你觉得就假设G现在只有三个了，你只有三个选择，所以你随便猜，你也有这个1/3的正确率，你觉得g one是正确选择的同学举手一下。

你觉得g one他可以minimize上面这个四的同学，举手一下好，假设你觉得你觉得G2可以，minimize上面这个四的同学去搜一下，你觉得G3可以minimize上面这个四子的同学，举手一下。

好手放下好记好多数人都选择VG3啊，没错正确答案就是G3，所以如果你选择G3的话，代表说你了解这个前面加mean，后面又加max到底是什么样的意思好，那我们现在找出来的这个g star啊。

就是就是这个G3啊，就是这个G3好，那这边的每当我们给定一个g one的时候哦，当我们给定一个g one的时候，这边这个g one呃，d one大的这个高啊，其实就代表了g one的这个选择。

RATOR它所gg one的这个选择，RATOR它所generate出来的distribution跟pk塔之间的距离哦。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_45.png)

所以这个高就代表G2的这个generator，它所定义的distribution跟data间的距离飞的高，就代表G3的这个generator，它跟distribution所它之间的距离。

所以今天呢呃这个g one的这个generator，他的divergence，他跟那个data的divergence是这么大，G2它所定义的卷卷，它所定义的那个distribution。

跟贝塔之间的diversion是这么大，G3他所定下的distribution跟data a线diversion是这么干，那我们今天呢要minimize我们的diversion，所以你会选择G3呢。

当做是最好的结果。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_47.png)

好，那接下来呢，我们就是要想办法解这个min max的problem，那这个MMAX的problem怎么解呢，你记得我们在讲gain的时候，我们说gain是怎么做的。

pin是说我们有一个generator，有一个discriminator，然后我们在train的时候，我们是iterative的去理去train，选择RATOR和discriminator。

我们固定住选择RATOR去update discriminator，我们固定住discriminator，接下来去update generator，那如果以下等下要讲的东西，你听不太懂的话。

你就知道一件事情，左边的这个演算法就是在解这个min max的problem，在解这个MMAX的problem，或者解这个明max problem，解这个命max problem的目的。

就是要minimize，你的generator和你的data之间的js divergence，如果你V写成像之前后片放放的那个样子，就是js divergence，你可以写别的样子。

那你就是mini mize，其他的divergence好，那为什么下面这一个ALISM，是在解这一个optimization的problem呢，那以下企业投影片就是要解释说。

为什么这一个algorithm。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_49.png)

是在解这个optimization的problem，我们来看看，说假设你要解这个optimization problem的话，你要怎么做好。

那这个呃max d v of gd找一个D去maximize v of gd，这个式子看起来有点复杂，所以我们把它用lg呢来取代，因为它其实跟D是没有关系的，你是低配一个G，反正你就会找到一个最好的D。

让L和G的值呢越大越好哦，所以呃让这个VIVOGD的值呢越大越好，那我们假设这个最大的值呢，就是L就是l of f g可，那所以现在这整个问题就变成，你要找一个最好的generator g。

它可以minimize l of g，那这个问题任何人都会这样，他就是他就是一个，它就是跟train一般的network是一样的，就是用gradient design来解它。

而且你用gradient design来解它，很对LOG算偏微分啊，你要算这个gradient啊，你要找一个G去minimize l o g啊，你就把这个这个CAG呢。

算这个CAG呢对l of g的gradient，然后用gradient descent去update seta，居然你就可以minimize这一个式子，你就可以optimize这一个呃。

optimization的problem，找出你的g st好，但是现在有一个麻烦的地方，就是这个l of g啊，如果你把式子写出来的话，他长得是这个样子的，这个式子里面是有max的。

那有人就会问说哎这个式子里面有max，它可以微分吗，会不会嗯不不能够微分，因为你今天要算这个LFG的规点嘛，在LFG这四局面，如果max他会不会没有办法做微分，其实不会，因为你想想看。

我们之前之前在学的时候学到一个max out network，mix out network里面也有max的operation，但他显然是有办法用brain descent解的。

那到底实际上是怎么做的呢，我们现在假设有一个function apple fs，它里面是有max operation的，我们来看一下有max operation的这种方式，你有没有办。

你要怎么对它做微分，而现在有一个f max，它里面有max的operation，它是对F1F2和F3这三个方向里面呢，找一个最大的出来，它就是FBS好，那假设f one长这个样子。

f two呢长这个样子，F3呢长这个样子，那今天这个FF它是F1f two，F3里面取大的那个，那apple长什么样子呢，f max呢就是长这个样子，它就是取就如果F1比f two f3大的话呢。

就取F1哦，如果F2呢比F1F3都大的话呢，就取f two，如果F3是最大的话呢，就取F3，所以今天这个FX它长的会是这个样子，它长会这样，就我滑鼠现在移动的位置，它长的是这个样子啊。

它长的是这个样子好，那如果你现在呢要把这个apple max对X做微分的话，那其实这件事情等同于什么呢，这件事情等同于看看现在的X可以让哪一个function。

f y f two f3最大就拿最大的那个出来算微分，就是S对F的微分好像可能有点抽象，我们就举很具体的例子，现在呢假设这个呃，你要在这个地方对FX做微分，那算出来微分值多少呢。

你算出来的微分就等同于是在对f one做微分，但如果你在这个这个这个区域，你算出来的微分就等同于是在对F2做微分，如果你在这个区域，你算出来的微分就等同于是在对F3做微分。

所以今天假如你的这个方式里面呢，有一个max的operation，实际上你在算微分的时候，你只是看说现在在f one f two f3里面，哪一个人最大，你就把最大的那个人拿出来算微分。

你就可以用gradient descent去optimize，这样的式子，举例来说，假设你用gradient descent去optimize sm f vs，那实际上的做法就是说哦。

假设initialize的时候，在这个地方好算一下它的gradient哎，就向右移，而如果今天向右移的时候，你已经移到了另外一个region，本来是在这个region里面是f one最大。

但跑到这边以后呢，就变成f two最大，假设移到另外一个region，这个region是f two最大，这个时候你算出来的微分呢，就会变成是f two的微分。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_51.png)

以此类推，以此类推，总之就算是你的，总之我们刚才讲那么多，我只想告诉你说，就算是我们的objective function里面有max的operation，其实你也不需要害怕，你一样是可以对它做微分的。

你一样是可以对它做微分的好，那所以就回到了我们现在要解的这个，optimization的problem，那实际上你会怎么解它呢，我们刚才有讲说，如果一个optimization的problem里面。

你的loss function是有max的，那你要怎么解它呢，你会先看说现在你落在哪一个region里面，在算说现在在那个region里面，哪一个function是max。

对那个max的function做微分，对不对，就你现在在你现在出色的地方，在这个地方你就看说这个方程它是最大的，就对他做微分，现在你up备参数以后，你要重新检查一下你落在哪个region。

他就说你落在这个region，落在落在这个呃中间，这个f two这个方程是最大的vision，那你要对f two做微分这样好，所以今天呢把它套用到我们的这个。

要optimize的这个min max的problem里面，其实也是一样的呃，其实也是一样的，一开始我们有一个初始的居零，我们有一个初始的距离，然后接下来呢。

我们要算居零对l of g的gradient，但是在算G0对l of g的规点之前，因为l dog里面有max，所以我们不知道l dog长什么样子，所以我们要把max的D找出来。

所以假设说现在在基本基本驱离的前提之下，哪一个低可以让LG最最大呢，它是低龄star哦，D0star呢可以让VOG0D最大也就可以，也就是说这个呃VOG0，就如果我们今天这个D啊带D0star的话。

我们就可以得到呢这个l dog啊，你这件事情你可以用gradient asset，就可以找出这个D它可以maximize这个objective function。

而找到低配maximize objective objective function以后之后之后，这个东西就是l of g了啊，这个东西就是l of g了，接下来呢你就可以把C大G对这一项算归点。

那就可以它对比的参数，你就得到新的generator g one和你update g的参数，你就得到新的generator g one，而接下来呢接下来呢你有新的generator g one，以后哦。

你有了新的g one，你就要重新找一下最好的D，因为你可能已经本来你的region在这边最好的，最好的D呢是这个，但是你现在呢移动你的GY以后，你可能已经进入下一个region。

所以你要重新找一个最好的D哦，所以现在我们把这个选择REER从G0呢啊，背到g one啊，背到g one，那可以让这个v f g one d最大的那个D呢，假设是d one大好了。

接下来呢你就有一个新的capt function，它是v o g T1 star，那再把它呢对准的ROR呢，算这个gradient来加a FA连选择RR好，你就得到G2好。

所以这整个operation就是呃你有一个GG0，找一个可以让VOG0D最大的D0star，那就得到了你的V的方式，然后让他对G做微分，然后再重新去找一个新的D。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_53.png)

再重新对你的objective function做微分，所以发现说这整个process啊其实跟gain是一模一样。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_55.png)

其实跟game是一模一样的，那你可以把它想成说呢，现在在找这个低龄star去maximize这个objective function的process。

其实就是在量披萨跟PG0的cs diversion哦，当我们今天找到一个g one，我们去找到一个d one star，它可以让这个objective function10分MAIMIZE。

其实我们就是在计算呢，p data a跟pg跟pg one的cs diversion，而下面这个式子呢，下面这个式子我们是要我们说这一项啊，它就是你的js diversion。

那你要update你的generator去minimize你的js diversion，这个时候你其实就是在减少你的js diversion，就是在呃达成你的目标。

就是要去minimize你的jay diversion好。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_57.png)

但是这边呢我们打了一个问号，这边为什么打一个问号呢，因为这件事情未必等同于真的，在minimize dadiversion，为什么这么说，因为我们有说过说，假设给你一个generator。

假设你的generator就是居里好，那你的v of g0D，假设它长这个样子，你找到一个低龄start，这个低龄star的值啊，就是G0跟你的data塔之间的cs diversion。

但是但是当你今天阿佩你的居民的时候，当你先update你的居零变成g one的时候，这个时候呢这个vf g one d，它的function呢可能就会变了，本来VFG0D是这个样子。

V of g0 d 0star，就是G0跟你的data的j is diversion，但是今天你update你的居零变成GY，这个时候你的整个function就变了。

这个时候因为你的G0star仍然是固定的，但是因为你的G0star仍然是固定的，所以你的vlog one d listar，它就不是在evaluate this divergence。

我们说evaluate js divergence的第第一呢，是今天这个v of gd的这个值里面呢，最大的那一个哦，最大的那一个，所以今天当你的车变了，你的这个方程就变了，当你的方权变的时候。

同样的D就不是在evaluate你的js divergence，如果在这个例子里面，js divergence会变成是这个值，而不是这个值，而不是这个值，那但是为什么我们又说。

这一项可以看作是在减少cs divergence的这边，做了一个前提的假设，就是哦这两个式子可能是非常的像的，就假设你只update一点点的居，从距离变到g one g的参数只动了一点点。

那这两个方式他们的长相呢可能是比较像的哦，所以因为他们的长相人是比较像的，所以一样用低龄star，一样用低龄star，你仍然是在量cs divergence这样的情形，就这边本来值很小。

突然变很高的情形可能是不会发生的，因为G0跟g one是很像的，所以这两个方选应该是比较接近，所以你可以指同样用固定的T0st，就可以evaluate gi跟g one的js divergence。

所以今天在train这个game的时候，他的tick就是呃，因为你有这个假设，就是G0跟g one应该是比较像的，所以今天在劝你的generator的时候，你就不能够一次update太多。

但是你在劝你的discriminator的时候，理论上你应该把它称到底，应该把它up配多次一点，因为今天在量你的discriminator的时候，你必须要找到maximize，maximum的值。

你才是在量js diversion，所以在train discriminator的时候，你其实会需要比较多的iteration，把它TRA到底，但是generator的话。

你应该只要跑比较少的iteration，免得今天你现在在这个投影片上讲的假设呢，是不成立的好。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_59.png)

那接下来我们来讲一下，实际上你在做bin的时候，你其实是怎么做的，我们说我们的objective function里面要对x transportation，要对x transportation。

但是在实际上你没有办法真的算expectation，所以我们都是用sample来代替expectation，所以本来是对p data simple x取它的expectation。

但实际上你在做的时候呢，就是从p data这个distribution里面sample n比data，把这N比data的d o fans统统算出来，然后再把它统统平均起来。

就当做是expectation一样，本来你要从pg里面sample x1跟X出来，算它expedition，但在实作上你没有办法这么做，所以实作上你做的行为是从pg里面simple出N比data。

那再把这M比data和去计算它的log1减d of x pa，然后把它全部平均起来，你就得到呃，你就得到正向的APPROIMATION，所以实际上我们在做的时候，我们就是在maximize这个式子。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_61.png)

而不是真的去maximize他的expectation，而这个式子啊如果你回去检查看看的话，我们刚才也讲过这件事情，就等同于是在劝一个binary的classifier，所以今天在实做GG的时候。

它并不是一个呃，就你完全不需要用什么，你原来不知道的东西，你在TRADISCRIMINATOR的时候，你就是在train一个binary的classify，所以实际上在做的时候怎样。

你的discriminator是一个binary classify，这个binary classify呢，它是一个这个logistic的regression，就是它的output呢。

有一它的output呢有接一个SIGMMODE，所以它output的值是介于0~1之间的，然后从p data里面你sample n比data出来。

这NM比data就当做是party sample或是class one example，然后呢你从pg里面再sample，另外M比data出来，这N比data就当做是nected sample。

就当做是press to sample，接下来就劝你的final classify，你TRA你的CRERI，你会minimize postentropy。

诶发现说如果你在minimize cos entropy，你把你的式子写出来。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_63.png)

它会等同于上面maximize这个objective function。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_65.png)

Minimize cos entropy，等同于maximize上面这个objective function好，那最后我们就再重新复习一次game的ALPISM，整个game的ALISM是这样子。

我们有一个sea b，我们有一个CDG哦，这个是你initialized parameter，在每一个iteration里面，你做的事情是什么，你从p data a这个distribution里面。

simple m比example，你从你的某一个priate distribution，它可以是高层distribution，可以是normal distribution，其实没有那么重要。

你就固定住某一个PRISTRIBUTION，从这个PDISTRIBUTION里面去sample出N个vector，这些vector呢用Z来表示，根据这些vector z，你把它丢到选择RATOR里面。

它们会产生一堆image，也就是x ta好，所以你产生一堆x ta，你这边有一堆real的image，你这堆有一堆generated的image，接下来你要train你的discriminator。

这个discriminator在training的时候，他就是maximize下面这个objective function，但我们刚才有讲过。

说maximize下面这个objective function，其实就等同于直接吹一个finally的classify，把这边的S当做是一类，把这边的XTA当做是另外一类。

直接吹一个binary classify，你BIOCLASSIFY是minimum cost entropy，就是在maximize下面这个式子哦，就是在maximize下面这个式子好。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_67.png)

那你劝了一个discriminator出来，那我们之前有讲过，说我们trap discriminator的目的是什么，是为了要evaluate jase divergence。

而什么时候discriminator可以evaluate js diversion，当它可以让你的V的值最大的时候。

那个discriminator才是在invaluable jazz divergence，你要让第一个词被maximize，他才是在evaluate face divergence。

那为了要让这个V的值最大，你一定要劝很多次，劝到收敛为止，他才能够让V的值最大，对不对，但在实作上，你没有办法真的吹很多次，吹到收敛为止，但是你会说哦，我今天劝这个D的时候，我要反复K次。

我这个参数呢要UPBEK字，而不是像投影片上面只写up背一次，而你可能会up背，比如说三次或五次才停止，好那这个步骤呢是在解这个问题，找一个第一他可以maximize v of gd。

但是其实你没有办法真的找到一个最好的DH，Maximize vo gd，你真正找你能够找的其实只是一个呃，lower down而已，因为这边你通常是在实做的时候，你没有办法真的劝到收敛。

你没有办法真的劝一直劝低，劝到说你可以让VFGD真的变得最大，那就是劝几步好，然后呢就停下来，那就算我们退1万步说，你这边你可以一直劝劝劝劝到收敛。

你其实也未必真的能够maximize这个objective function，对不对，因为你在train的时候，你的低的capacity并不是无穷大的，你会蹭蹭蹭。

你那就卡在一个local minima，然后就结束了，对不对，所以你并不真的可以maximize这个式子，然后再退1万步说，假设你没有local mamaxim，没有你没有那个什么local密码。

local maximum的问题，你可以直接解这个问题，你的D呢他的capacity也是有限的，你记得我们有说过说，如果你要量cs divergence，我们一个假设是你的D可以是任何方向。

但事实上你的D是一个network，所以它也不可以，它其实也不是任何方式，所以你没有办法真的maximize这一项，你能够找到的只是一个lower范围。

但我们就假设你其实可以maximize这一项就是了，好那接下来呢要劝generator，然trap generator，那我们说trap discriminator的时候。

是为了量cs divergence，trap generator的时候是为了要minimize cs divergence，为了要减少cs divergence。

就前面这个步骤是在量出j diversion，接下来下一个步骤呢是在减少j diversion，怎么做呢，怎么做呢，你就从你的嗯，你就先一样呢，simple and vector出来。

从你的price stribution面sample and vector出来。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_69.png)

然后接下来呢你就要解下面这个式子一样一样，就我们说本来这个discriminator上，minimize这个式子嘛，那选择ROR呢要minimize一个一模一样的式子。

但是下面这个式子里面你会发现说第一项，第一项呢跟generator呢是没有关系的，因为第一项只跟discriminator有关，它跟generator没有关系，所以你要劝你的generator。

去minimize这个式子的时候，第一项呢你是可以不用考虑它的，所以你把第一项拿掉，只去minimize第二项的式子好，这个第二个步骤呢就是在劝你的generator。

那我们刚才有讲过说generator你不能够train太多，因为一旦你train太多的话，你的discriminator就没有办法evaluate js divergence。

所以你的generator没有不能确认太多，你只能够少量的update它的参数而已，所以通常你的generator这边update一次就好，所以你可以update discriminator很多次。

但是generator你update一次就好，所以你用discriminator算出js divergence以后，你只用generator少少的update一次，让你的js diversion变小。

但你不能走太多，你要背太多，你量出来js diversion不对了，你就不是在量js divergence，所以这边呢你就不能够update update太多，好，那我们刚才我们到目前为止。

我们讲说今天在TRAGENERATOR的时候，你要去minimize的式子，长这个样子，他在yn good fellow原始paper里面，他从开篇从一从有GA以来，从开天辟地以来，他就不适用，它。

就不是在mini maze这个式子，因为他在paper里面加了一小段，他说这个式子啊log1减d of FX，它长的是这个样子，而我们一开始在做training的时候，你的DX的值通常是很小的。

因为你的discriminator会知道说，你的generator产生出来的image，它是fake的，所以他会给他很小的值，所以一开始你的d ox的值呢会落在这个地方，那它的微分是很小的。

所以在training的时候，会造成你在training的一些问题，所以他说呢我们把它改成这个样子没有，为什么我们把它改成这个样子，本来是log1减DOFX，把它换成负的log d o FX。

那负的log d2FS，它长的是这个样子，那这两个式子的趋势是一样的，在这边最大的东西在这边还是最大，在这边最小的东西在这边才是最小，他们的趋势是一样的，但是他们在同一个位置的斜率呢，就变得是不一样。

在一开始dio method值还很小的时候，你算出来的微分会比较大啊，所以yle flow觉得说，这样子training是比较容易的，那你再从另外，其实你再从另外一个词作的角度来看。

如果你是要maximize这个式子，你会发现说你需要改code有点麻烦，如果你再仔细想想，你今天如果是要mix呃，minimize这个式子说错了，如果你要minimize这个式子，其实你要改扣的。

如果你是minimize这个式子，你可以不用改扣的，你直接把你刚才我们刚才不是说return，discriminator的时候，你就是TRA了一个binary的classifier吗。

他就分辨两个不同的类别对吗，今天如果你是用下面这个式子来嗯，要mini版下面这个式子的时候，你其实只是把那个binary classify的label换过来，就本来是说呃sample的data。

从data里面sample出来的是class one，从非从generator sample出来的是class two，可以把它level换过来。

把generator sembles出来的改标成label one，然后用同样的code去跑下去就可以了，我认为YN哥哥他其实只是懒得改扣的而已，所以就胡乱编一个理由，说应该要用下面这个式子。

但实际上后来有人试了比较这两种不同的方法，发现都是可以称得起来，performance其实也是差不多的，不知道为什么严格beer1开始就选择这个，我觉得只是因为他input们下去才发现。

说嗯弄错了这样子，然后又缠着开扣了，所以他就用这个东西继续做下去，像11天对啊，那算这些东西是有名字的啦，因为呃就大家都不这些，这因为这些方法就是嗯有人就会说哦，这个叫做什么original game。

这个叫modify game，然后都搞不清楚什么是什么，所以后来英girl还写了另外一篇文章，他说我们应该把这些game证明啊，上面这个叫做mini max game，就是nn game啊。

下面这个叫做nsituation ration game。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_71.png)

就是n s game，好那在下课之前呢，我们在讲一些刚才讲了很多的数学，现在我们讲一些比较直观的东西，所以按照yang fellow的想法，今天这个generator和discriminator。

他们之间的关系是什么样子呢，假设这个是你的这个data的distribution，这个是你的generator的所产生出来的data distribution好。

那你现在要认一个discriminator，discriminator要给绿色的点比较高的分数，给蓝色的点比较低的分数，这个discriminator的objective，The value。

就是这两堆data a的C的cs diversion，或某种其他的divergence好，那你现在有了这个discriminator以后，有了这个discriminator以后。

这些generated的点，因为在train的时候呢，这个general你会generator会希望呢他产生出来的东西，通过discriminator以后得到的分数越大越好，所以这些点呢就会往右移动。

这些点呢就会往右移动，但它可能会一下子跑太多，就跑到蓝色的点的右边去，但没有关系，接下来呢你会再劝一次你的discriminator，但因为现在蓝色点和绿色点比较近。

所以这个discriminator呢它的loss就比较大，它的loss比较大，代表说这两种点的j divergence呢是比较小的好，那接下来呢这些蓝色的点呢。

会顺着这个discriminator的给的，这个gradient的方向呢往左移啊，往左移好，最后呢蓝色distribution跟绿色distribution就会越来越近。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_73.png)

当这两种distribution完全一模一样的时候哦，完全一模一样的时候，你缺一个discrimination，这个discrimination会完全没有办法分别这两种data。

因为对这个discriminator来说，这两种data是一模一样的，不管他怎么努力，都没有办法分别这两种data，所以最后discriminator会坏掉，会坏掉，对他来说每一个地方都是一样的。

每一个地方，这个P贝塔跟pg出现几率都是一样的，所以呢discriminator呢就会变成一条水平的线，它没有办法再做任何事情。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_75.png)

把箭头叫出来啊，这个箭头叫出来啊。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_77.png)

这个demo是这个样子的，绿色的点是你的P贝塔。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_79.png)

蓝色点是你的pg哦，所以绿色点是你的目标，蓝色点是JERRATOR产生出来的东西。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_81.png)

背景这个颜色啊是discriminator的值。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_83.png)

对不对，discriminator会塞给每一个X，就是背上每一个X1个值。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_85.png)

所以这个背景的这个颜色是DISCRIMINOR的值，而这个demo看起来是这个样子。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_87.png)

你就会发现说呢这个discriminator呢，就把你的pg产生出来的蓝色的点呢赶来赶去。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_89.png)

赶来赶去，直到最后呢，蓝色的点跟绿色的点重合在一起的时候。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_91.png)

那对你的discriminator来说。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_93.png)

它就会坏掉，因为他完全没有办法分辨，pg跟p data塔之间的差别啊。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_95.png)

这好再播一次吗，他长得这样子对，就这样子。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_97.png)

首先对好，然后最后呢你的那个discriminator呢就会坏掉它。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_99.png)

因为它完全没有办法分辨，generator和discriminator之间的差别。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_101.png)

它就会坏掉，诶想到这边大家有没有问题要问的呢。

![](img/f7a31ddb6db81c87f5b86cc36d385be0_103.png)

诶请说请问下那两个S的数量已经都要讲了，我是奥赛克斯用，一般在做的时候，你知道我们今天在trainer teify的时候，我们其实会害怕take a imbalance的问题，那今天在这个task里面。

data是我们自己sample出来的，所以为了我们不会给故意给自己制造data，imbalance的问题，所以你的两种test你会把你会sample一样的数目，就是说假设你从generator面。

generate256比data，那你今天从你的sample的data base里面，你也会sample256笔data，好诶，讲到这里，大家还有问题要问的吗。



![](img/f7a31ddb6db81c87f5b86cc36d385be0_105.png)

好如果你没有问题要问的话，其实我有一个问题要问，这样子，我问题是这个样子的，呃，你不觉得今天讲的跟上周讲的是有点矛盾的吗，如果按照yana fellow的讲法。

上面这个图是yana fellow paper上的图啦，他说最后discriminator圈圈圈圈，到后来它就会烂掉，变成一个水平线。

像我们上周说discriminator其实就是evaluation的function，也就是说discriminator的值代表，他想要评断说这一个啊，object这个generate出来的东西。

它到底是好还是不好，如果今天你的discriminator是一条水平线，它就不是一个evaluation的function啦，对他来说，所有的东西都是一样好或者是一样坏的啊，这个是伊恩格菲尔画的图啊。

右上角这个啊是那个young的co画的图，你看young的康，他在画那个图的时候，这个他也是在讲gin啦，他也在讲game啊，然后他画的这个他画的这个图，就是那个discriminator的图。

然后这个绿色的点呢，这个绿色的点就是real data分布，你发现他在画的时候，在他的想象里面，最后discriminator并没有死掉，并没有烂掉，变成一个水平线，而是说有贝塔分布的地方。

它会得到比较小的值，而没有贝塔分布的地方，它会得到比较大的值，而他跟我上课讲的是相反，我上课讲说我data分布的地方值比较大，没有data a分布的地方应该值比较小，他这讲的是正好相反。

但是意思完全是一样，就DA分布的地方值是比较小，其他地方值是比较大，跟英格菲尔话讲的是有一些矛盾的样子好，而这个就是神奇的地方，就是因为这个都是上代发展中的理论，所以有很多的问题是未知的。

也许下个学许明年我们再开同样的课的时候，我又会有不一样完全不一样的想法，说不定就好像以前我们在train keep learning的时候。

我们都要用restrictive postmemachine过去，我们都相信说没有restricted，BOSMEMACHINE是劝不起劝不起来的对，所以呃呃像我们之前第一次开LDS的时候。

其实就会花两周讲restricted bostm machine，那今天如果再讲respect postmemach，我相信你就生气了，觉得在拖台前这样子，因为根本就用不上，因为根本就用不上这个技术。

所以这个变化是非常快的，也许我们明年再来讲同样的东西的时候，就会有截然不同的讲法，也说不定，那今天如果你问我说到底是哪一种的话，就假设你硬要我给你一个答案，告诉你说到底应该是伊恩戈菲尔的讲的比较对。

还是ya特讲的比较对，那我的感觉是，首先你可以从实验上来看看，如果你真的劝完你的get，然后你去evaluate一下你的discriminator，他的感觉好像是介于这两个case中间。

所以他绝对不是烂掉，但它绝对不是变成一个完全烂掉的，discriminator啊，这你你你你自己是回去自己做做，看你几时劝出这样子的结果，居然是这种简单的例子，你也劝不出这个结果的，真的哎。

所以就算是就算是这个一维的例行，都做不出这个结果，所以不太像是DQFO讲的这样，但是你的discriminator也不完全反映了data的distribution，这感觉是介于这两个case之间好。

那这些观点到底对我们了解更有什么帮助呢，也许again的ALISON就是一样，那个演算法就是那个样子，就是tra generator train，Discriminator。

Terrative train，也许他的这个呃呃，algorithm是不会随着你的观点不同，但是这个观这是但是你用不同的观点来看待GA，你其实在设计你的ALGISM的时候，中间会有些微妙差别。

也许这些微妙差别，导致最后圈年的结果会是很不一样的，但其实我觉得也许ja queen的这个讲法，反而是就是说我上周讲的discriminator，是在evaluate一个object的，好还是不好。

它是在反映了data ta的distribution这件事也许更接近现实，为什么我会这么说呢，首先你在文献上看到很多人会做什么事情，他会把discriminator当做一个classifier来用。

所以你先劝好一个game，然后你把那个discriminator拿来做其他的事情，假设今天discriminator其实劝到最后，跟像按照英格fl猜想会烂掉的话。

那你拿它来当做PRETRAINING根本就没有意义啊，但很多人会拿它来当做PRETRAINING，也显示它是有用的，所以所以他不太可能是真的劝到后来就坏掉了，然后这是第一个evidence。

另外一个eminence，只是说你想想看你今天在train骗的时候，你并不是每一次都重新劝你的discriminator，对不对，我们并不是呃每次都重劝discriminator。

而是会拿前一个iteration的discriminator，当做下一个iteration的initialize的参数，如果你今天你的discriminator。

是想要衡量两个beta distribution的divergence的话，你其实没有必要把前一个iteration的东西拿来用，因为现在你的generator已经变啦。

你保留前一个iteration的东西有什么意义呢，所以这样子感觉是还感觉好像是不太，感觉是不太合理的，诶，也有人可能会说，因为今天的generator他update参数，他update的量是比较小的。

所以也许把前一个TC得到generator，当做下一个time stimmitialization，可以加快generator训练，可以加快discriminator训练的速度，也说不定。

那这个理由感觉也是感觉也是成立的，不过在文献上我们会看到说有人在劝game的时候，他有一招是他每次劝的时候，他不止拿现在的generator去sample data。

他也会拿过去的generator也sample data，然后把这些各个不同的generator，sample data通通集合起来，再去train discriminator。

可以得到的performance会是比较好，那如果今天discriminator是在evaluate，你现在的generator跟你的data distribution的差异的话。

好像做这件事情也没有太大的意义，就你拿过去的general，因为现在量现在generator跟你贝塔之间的差异，你拿过去的generator产生出来的东西有什么用呢，没有什么用啊，为什么要这么做。

但是在实作上，你发现拿过去的generator所产生出来的东西，再去训练discriminator，是可以得到比较好的成果的，所以这样看起来也许这是另外一个support支持说呃。

也许DISCRIMINI做做的事情并不见得是在evaluate，两个distribution之间的divergence，不过烟至少烟跟fellow1开始是这么说的，所以我们也把J呢最开始的理论告诉大家。

这样子好，那呃我们就在这边啊，现在这边呢先休息10分钟，然后等一下呢，下一堂课要讲到40分到50分之间。

