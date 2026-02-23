# 2025北京智源大会-特色活动：InnoVibe共创场 p06 SFT记忆，RL泛化：对基础模型后训练手段的对比研究-褚天哲 -BV1nNNJzJEx6_p6-

然后下一位是楚天哲，他要讲内容是SFTG，还有RLRL泛话，对吧？有请。呃，好，大家好，我是这个航空U的建哲。

然后我现在是一年级PHD今天我要讲的工作是这个SFT memorizes are generalizes。然后对在一开始呢我先给大家overview一下我们这个工作，就是我们team做的工作。

然后嗯有比较比较不错的collaborator。😊。

![](img/0a8ac11974f0a0a8bb446697d8524366_1.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_2.png)

对，就第一步我们先想一想这个为什么我要做这个呃，在在这个ge language model时代呢，大家大家在后训练中引用了非常多的这个比较f technique。然后可能从这个2018年开始。

现有这个supervis就已经在在一些比较 language model上面用上了。然后慢慢的大家用RHF来获得更加安全的这个model。然后接下来呢大家又又试着用来训一些agent。

最近呢这个自从opI开始，大家发现用vefiable可以训出来比较好的这个asoner。😊。

![](img/0a8ac11974f0a0a8bb446697d8524366_4.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_5.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_6.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_7.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_8.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_9.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_10.png)

对，就是大家发现GPT4的时候，大家已经意识到这个post training非常重要。

![](img/0a8ac11974f0a0a8bb446697d8524366_12.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_13.png)

就是在O one时代，大家发现在AIME上O one非常强。第二个呢就是嗯在现在这个LM时代，大家想做比较干净一点的比较这个能控制变量的非的缺少。

但是一个比较好的 example是朱泽源他在这 physicsM的工作里面提出了这个相当多的可以值得大家借鉴的一些这个做实验的对比实验的方法。

然后这里呢我可能是igh level里去in by his idea就是是否LM是真的学到了呃整个推理过程，还是说他只是学学出了这个 of mapping。😊。



![](img/0a8ac11974f0a0a8bb446697d8524366_15.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_16.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_17.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_18.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_19.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_20.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_21.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_22.png)

对，那进一步呢我们去去想，就是在mtimod的 reasoning task当中，呃，I和SFT分别都学到了什么样的东西。



![](img/0a8ac11974f0a0a8bb446697d8524366_24.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_25.png)

对，接下来我们可以先这个回顾一下呃R和FT两个的不同呃，在可能大家已经比较熟悉了。但我这里大概讲一下。

就是supervis的做法其实就是你输入了这然后把前面的ken求对ken做但是就不会去严格supervis每个kens而是他会给给这一个一条ject一或者是给一个step一个然后在在这个比较经典的比较在的这个出现之前呢。

大家可能是还是倾向于一ject有多每个一个一个自最后会用这个的去优化或者是加。😊。

![](img/0a8ac11974f0a0a8bb446697d8524366_27.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_28.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_29.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_30.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_31.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_32.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_33.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_34.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_35.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_36.png)

对，在我们的这个当中呢，我们其实就是呃用了最ive的类似，但是呃也是比较简单的这个 framework呃这frame呢其实就第一步是我们先从ment去ple一些问题。比如说这里的例子问题是一个324。

第二个是一个 task。然后采样了这些问题以后，他可以包含图片也可以不包含图片，我们把它未未进一个VRM然后希望他去回答一个问题。呃，回答完这个问题呢。

我们去人为的加上了一些simple verification。比如说他回答这个问题错了。然后ve告诉他你这个做错了，你再试一次就是在这个ification过过程中。

我们给他这respon同时还会给他一个比较简单的re。比如说回答对了，你就给他一个正，并且结束掉这个如果回答错误了，你就给他个 reward。😊。



![](img/0a8ac11974f0a0a8bb446697d8524366_38.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_39.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_40.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_41.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_42.png)

呃，这样的一个sial revision其实是inpired by呃2024年 Charlielie他的这个caling time compute的一个工作。

然后呃同时我们这个工作是在long COT出现之前的工作，并且我们只采用了最简单的没有COT的这个framework。对，接下来呢我们在想呃，一个用什么样的tsask可以用来给我们做这个对比实验。

来区分R跟SD的区别。

![](img/0a8ac11974f0a0a8bb446697d8524366_44.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_45.png)

那呃task selection最重要的其实就是能让一部分model能解决。但是比如说通过training之后，他能解决大部分的问题。但是在没有training之前，他可能做的比较烂。

那我们这里采用的这个第一个任务就是24点呃，即使现在 model非常强，他们算24点其实还是会会fa的，尤其是这些比较sll model或者是没有在 data上特意训练过的mod。

这里呢我们希望造的造的这个情况，就是既能有一个 rule又有一个 rule我们怎么设计呢？就是对于算24点来说，你有两种interpre。第一个是你把JQK当做1来看。

然后第二种inpre你是把JQK当做11是23。然后这样就可以很自然的说我们训练一个然后t看看他有没有学真的学到说24点这个运算规则是怎么样，还是说只是记住了这个 data里的样子是怎样的。😊。



![](img/0a8ac11974f0a0a8bb446697d8524366_47.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_48.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_49.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_50.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_51.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_52.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_53.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_54.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_55.png)

呃，在有vision的情况下呢，我们就是instead of直接把呃这个卡牌的数数字告诉他，我们会给他输入一张图片。然后图片里面有4张复克牌。然后相同的。

我们还设计了一个vision上的呃 out of distributionion scenario。就是说呃如果说训练的时候，我们只只给他看过这些黑色的卡牌，然后呃evaluate的时候。

我们去evalu点红色的卡牌。这样子的话，他在vision上也会有也会经历到一个这个ditriion shift。😊。



![](img/0a8ac11974f0a0a8bb446697d8524366_57.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_58.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_59.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_60.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_61.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_62.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_63.png)

嗯，第二个任务呢就是我们希望能做一个更加re world一点的。比如说呃在刚才的那个呃数学里面，我们可能没有没有让这个model真的去呃用vision去感知周围的环境。那。如何用这个re word来呢？

我们就采用了赛林之前的一比较vi的工作。它是。这个工作是这样的，就是。嗯，go是给这个model一个一句话的instruction，希望他从A navigate到B。然后在navig的过程中。

你还会告诉他呃，你会在途中遇到怎样的怎样的landmark。你在遇到landmark需要执行左转右转或者是向前的操作。呃，在这个t当中。

我们也同样设计了这个indiout of distribution呃，在纯 language情况下呢，它的indi就是采用绝对坐标系的转弯。

比如说向东向西转在呃out of distribution就是相对坐标系，比如说向左向右转呃，在vis上面呢就是indi是呃这个在一个城市，比如说在纽约训练。

然后out of distribution就在全世界的其他不同城市去。😊。

![](img/0a8ac11974f0a0a8bb446697d8524366_65.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_66.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_67.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_68.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_69.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_70.png)

第下就是我们的 resultsult，我们 results一句话就可以概括，那就是SF generalizemor generalize呃。

其实就是说R可以在不同的OOD的情况下都能让perform有一些提高，但是supervis它就是会严重的 over即使它in distribution上涨的很快。

但是 distribution会有一个比较明显的下降。呃，这里我们test是呃这个只改变规则。😊。

![](img/0a8ac11974f0a0a8bb446697d8524366_72.png)

可以看到在我们的两个task，并且是带vis或者是不带vis的情况下，呃，reinforment learning都可以提高下面的这个呃out of distribution的 performance。

呃，接下来我们又试了一下，改变那个visual domain all of distribution。我们依然发现呃reinfor learning会有一个generalization的现象。



![](img/0a8ac11974f0a0a8bb446697d8524366_74.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_75.png)

这样你可能会在这个图里发现一个比较有意思现象，就是我们的SFT并没有把把这个呃d的这个情况，即是in我们也没有给他调work。这是为什么呢？

我我可能觉得呃大家在做的也也有可能之前有一些工作也表明呃supervis并不完全能让一个你认为能work的东西work。比如说呃你给他为很多训练训练 data，他依然不会work。😊。



![](img/0a8ac11974f0a0a8bb446697d8524366_77.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_78.png)

对，然后我们就试图exore why呃，我们发现的原因其实是这样的，就是在supervis的过程中，它可能会有一个local的 overfitting。

比如说它它会overfit到那个算 equation的那个地方。但是在recogni那个部分的token它就没有去fit到。因此呢它的这个recogni的 performance会变低。

即使是在indo的情况下，它的识别卡牌的准确度也会非常的低。😊。

![](img/0a8ac11974f0a0a8bb446697d8524366_80.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_81.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_82.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_83.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_84.png)

这样子就会导致他后面的推理也不可能做对。😊，我们同时还ab了很多不同的这个learning rate，也发现了呃在即使换各各种各样参数，他也依然调不work。呃。

第二个情况下是呃第二个这个比较有意思的现象是呃，我们发现即使换了一些更加dverse的supervise training data呃，它的这个 overfi的现象会有一些降降，但依然是会出现的。



![](img/0a8ac11974f0a0a8bb446697d8524366_86.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_87.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_88.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_89.png)

对。第三个有意思的现象是，我们发现对于比较弱的模型，我们如果不让他提前具有instruct following能力。比如说提前让他呃用SFT warm up一下，他依然会work。比如说他会直接。



![](img/0a8ac11974f0a0a8bb446697d8524366_91.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_92.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_93.png)

0这种要比较低的performance。对，最后我们还研究了一下这个test time scaling对 generalralization的影响。我们发现就是呃verification的越多。

比如说test time scaling它它能够试错的机会越多，它的 generalralization也会越好。它其实是会更加ampplify，或者说让这个现象更加的明显。😊。



![](img/0a8ac11974f0a0a8bb446697d8524366_95.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_96.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_97.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_98.png)

对，我们当然有一些 limitation，比如说我们没有没有摸任何的 theoryory，然后我们也没有去rese on cross task general。

但是这些在后续的一些大家的research，比如说我们抛砖引玉了。后面我观察到很多工作也有研究这个现象，并且发现R尔还是很不错的。



![](img/0a8ac11974f0a0a8bb446697d8524366_100.png)

![](img/0a8ac11974f0a0a8bb446697d8524366_101.png)

OK感感谢感谢感谢。呃，这个因为我们现在还有点时间，所以这个而且刚才讲这个题目比较有趣，所以我希望大家能多提两个问题。😊。



![](img/0a8ac11974f0a0a8bb446697d8524366_103.png)

有现在有问题没有的话，我有一个问题。对，因为我觉得就是说这个推理能力ra它是一个能力，对吧？但是SFT呢或者RL是方法。对对，能力跟方法是不一样。比如说我们教小孩游泳，可以把它扔到河里，他自己会有了。

或者他不会有淹这两种不同的结果，对吧？相当于是我们给他更多探索的空间，但是有可能失败，但是我们会奖励他成功的SFT呢就是我们教的时候取决于这个老师怎么样。对。

所以有的时候我们是是有没有可能就是我们做的SFT不够好。因为我不觉得大部分的这个比如说人类的知识也好，技能实际上已经探索出来了。但是有可能SFT的训练不够高级。对对对，我觉得您说这个非常非常有道理。

就是在最近的一些se当中，大家发现如果我们用一个更加好的老师，比如说接用来教教这个模型，后用他的out来这样他也会有非常强的这个至少是能让他的这ken。😊，很长，然后解决一些呃比较复杂问题。

也有相应的泛化性。对，所以我觉得就是更高级的方法，有可能是用这个Htrain更好的ST可以用一种高阶的形式来做训练。为空间太，所以导致计算效的的那我们这个工作当我们就取用最简单的这个这个模式。

所以我们的非常简单。但是可能在工业界大家实际上会用的时候，可能已经加了这加了这个加上甚至人为的去 out一些不好的这样子的话你可以尽可能的把这个super data去做的非常完善而非然后这样子的话其实是对于你后续的训练会常非常强的这个加速的作用是会让更加那个主觉得刚才这个已经到训练目前最核心的一些问题。

😊。