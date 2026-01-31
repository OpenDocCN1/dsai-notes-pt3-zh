# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P93：3-各種奇葩的元學習 (Meta Learning) 用法 - AI算法工程师Future - BV1ruqABeEFX

好那我们就开始来上课吧，好各位同学大家好，那今天呢想跟大家补充一些meta learning的知识。

![](img/444b4149d365af36fd28bce8c2cbe7b3_1.png)

那在开始这堂课之前呢，呃我先预设你已经有meta learning的基本概念。

![](img/444b4149d365af36fd28bce8c2cbe7b3_3.png)

那如果你还不知道什么是meta learning的话，那你可以看一下我们过去上课的这两段录音，看完这两段录音以后，再来进入今天的课程。



![](img/444b4149d365af36fd28bce8c2cbe7b3_5.png)

好这个今天呢会讲四件事情，那我会讲meta learning跟sales supervised learning的关系。

那讲meta learning怎么用在dman in generalization上面，那meta learning怎么用在knowledge destination上面。

还有meta learning怎么用在lifelong learning上面，那sale supervised learning，Dommain generalization。

Knowledge destination，还有lifelong learning，都是我们过去课堂上有讲过的技术，那我们来看看meta learning，跟这些技术有什么样的关联性好。



![](img/444b4149d365af36fd28bce8c2cbe7b3_7.png)

那我们先从meta learning和sale。

![](img/444b4149d365af36fd28bce8c2cbe7b3_9.png)

supervised learning之间的关联性说起，那对sale supervised learning呢想必大家一点都不陌生。

sale supervised learning最具有代表性的技术就是BT，跟他的好朋友们，那bird跟他的好朋友们，他们做的事情其实是找一个初始化的参数，其实是想要找一个比较好的参数的。

initialization的方式，那你从这个当讯的角度来看，sales supervised learning做的事情就是找初始化的参数，那我们在之前的课程中在介绍meta learning的时候。

也讲过，说在meta learning里面也有一系列的技术是在找参数的，Initialization，有一系列的技术，他做的事情就是learn to initialize。

他是想要用meta learning的方法来，自动学出合适的初始化参数，那其中最具有代表性的就是memo，那bird跟memo他们做的事情听起来目标是一样的，他们都是要找初始化的参数。

那bird跟memo它们之间有什么样的关系呢。

![](img/444b4149d365af36fd28bce8c2cbe7b3_11.png)

那根据近年的文献看来啊，虽然BERT跟memo他们有共同的目标，但是他们并不是互斥的，往往BT跟memo他们是可以互相相辅相成的，怎么说呢。

我们来看看BT这一种sales supervised learning的技术，怎么跟memo结合在一起好，那memo啊其实有一个很重大的弱点，就是memo是要learn初始化的参数。

memo是用什么方法论初始化的参数呢，memo是用gradient descent的方法，来learn初始化的参数，但你只要用到gradient descent，你就需要initialization。

所以有趣的地方是，虽然是在找这个initialize的参数，但是memo本身也需要initialization好。



![](img/444b4149d365af36fd28bce8c2cbe7b3_13.png)

这就好像是啊这个印度人的传说，说这个世界呢是站在一个呃，这个世界呢是在一个乌龟的背上，那有人就问说那乌龟又站在什么东西上面呢，哦乌龟站在更大的乌龟背上，更大的乌龟又站在更大更大的乌龟背上。

就好像memo它本身是要学initialize的参数，但是它本身也是要initialize的，怎么办呢，这个memo本身需要initialize，那memo的initialization可以来自哪里呢。

那近年在文献上看起来，往往memo的initialization，那假设你做的是NLP相关的任务，往往memo的initialization就是用bird好，用。

sell supervised learning学出来的参数，可以作为memo的初始化参数，再透过memo的技术再去找更好的初始化参数，那把memo跟bird结合起来有什么样的好处呢。



![](img/444b4149d365af36fd28bce8c2cbe7b3_15.png)

那BERT啊，虽然现在我们都知道，BERT呢在实务上这个结果非常好，但是BERT有一个重大的问题是，这些sell supervised learning的objective。

其实跟当讯的任务并没有直接的关系，我们知道BERT做的就是填空题啊，虽然很神奇的是叫BERT做填空题以后，他在各式各样的NLP的任务上都可以发挥作用，但是实际上BERT在PRETRAIN的时候做的事情。

跟我们实际上要他最终解的任务，是有一段差距的，那这个差距有人叫做learning的gate，也就是我们教BT在PRETRAIN的时候做的事情，跟我们真正要他做的事情中间是有一段差距的。

而memo就没有这个问题，memo跟bird同样是找初始化的参数，但是BT找出来的初始化的参数，虽然在实物上很强，但他并没有特别保证，他一定在当讯的任务上会有好的表现，但是memo就不一样。

memo找出来的这个初始化参数啊，memo在找这个初始化参数的时候，它本来找初始化参数，目标，就是为了要在我们关心的这些任务上，得到好的表现，那如果你熟悉memo的话。

你会知道这系列meta learn的方法，都是要先收集一些训练的任务，那我们就是去找一组初始化的参数，在训练的任务上可以得到好的结果，他们有接近的分布的话，那我们可以想象说。

在训练的任务上可以有好的结果，初始化参数也可以被用在测试的任务上，所以如果我们比较memo跟bird，那memo是比较有保障的，memo在找这个初始化参数的时候，他的目标就是为了。

要在我们感兴趣的那些任务上得到好的结果，但是memo有一个劣势，就是如果你要使用memo这个技术，你需要准备训练的任务，那一方面memo本身的运算量非常的庞大，另外一方面要准备这些训练的任务。

也需要进行人工的标注，而这些训练的任务，里面的资料往往是需要标注的，而BT不一样，BT的训练本身可以用无所不在的，大量的未标注资料来完成，所以birth跟memo它们各有所长，各有缩短啊。

所以把它们结合在一起，可能会是一个不错的选择，好那在文献上啊，确实有非常多文章尝试把sale supervised，the model跟MAMO结合在一起，那这边就举两个例子。

一个例子呢是坐在test oriented的semantic parsing上，那如果你不知道这个是什么，没有关系，反正就是某一个NLP的任务啊，在这个纵轴呢的值越大越好，那横轴呢横轴是训练资料量。

越往右代表所用的训练资料越多，蓝色这一条线呢是BART的结果，BART是BT的一个变形啦，那如果你不知道BART是什么，没有关系，它就是一种BT的变形好，那but给我们的结果是蓝色的这一条线。

那你可以把BT再加reptile，reptile是一种memo的变形，你可以用but当做reptile，它的初始化参数再用reptile去呃，update but的参数得到更好的初始化参数。

那你得到的会是绿色的这一条线，那你发现说绿色这一条线，比蓝色这条线的结果更好，尤其是在训练资料特别少的时候，看起来把这个self supervised learning。

再加上meta learning，在训练资料特别少的时候。

![](img/444b4149d365af36fd28bce8c2cbe7b3_17.png)

它更具有优势好那这是另外一篇paper了，那这篇paper呢是做在一些natural language understanding的任务上，那这边paper同样也显示说，如果你用BT。

你得到的是蓝色的这一条线，纵轴是正确率，横轴是训练资料的量，那BT是蓝色这条线，如果把bird后面再加上reptile，你会得到橙色的这一条线，那一样，你会发现说在训练资料特别少的时候。

把self supervise model but t再加上meta learning的技术，reptile可以得到特别显著的进步。



![](img/444b4149d365af36fd28bce8c2cbe7b3_19.png)

好那像这样子的文章呢还有很多，那我最近写了一篇有关meta learning，用在指这个自然语言处理上面的overview paper，然后把链接放在这边好，那在这个paper里面呢有收集了呃。

近3年来呢，把memo或相关的技术，用在自然语言处理上的文章，然后我特别统计了在做memo的时候，他们都是怎么做initialization，那你会发现呢。

多数文章其实都是有用were embedding，或者是用bird或mtingle bird来做initialization，那真正完全train from scratch。

从随机的initialization来train memo的文章，其实是比较少的。

![](img/444b4149d365af36fd28bce8c2cbe7b3_21.png)

好，那接下来呢要跟大家分享的是，怎么把meta learning的概念用在knowledge destination上，好。



![](img/444b4149d365af36fd28bce8c2cbe7b3_23.png)

那我们在讲模型的压缩的时候啊，我们在讲怎么把大的neural network缩小的时候，跟大家介绍过knowledge destination这个技术。

我们说knowledge destination这个技术，就是你先吹一个大的teacher model，接下来呢你把大的teacher model的输出，当做是小的student model的学习目标。

让小的student model的输出跟大的teacher model的输出，越接近越好，但是啊这个大的teacher model，它本身在训练的时候就是当做一般的呃。

假设我们现在做的是image classification的问题，那这个大的teacher model在训练的时候，就是当做一般的模型来解分类的问题，这个teacher啊他到底擅不擅长教学，我们不知道。

那甚至呢有文献指出。

![](img/444b4149d365af36fd28bce8c2cbe7b3_25.png)

这个在这个分类任务上做得特别好的teacher，它本身不见得是特别擅长教学的，举例来说，在这个table one里面有四个不同的模型，它们有不同的正确率好，那cp mix呢是正确率最高的模型。

但是如果拿student去跟这四个模型去学，你会发现呢，这个呃正确率最高的老师，教出来的不见得是最厉害的学生好，这个table two呢也这个呈现了很类似的结果啊。

这边有四个不同大小的Rest name好，那越大的RESNET好，它的正确率越高好，那现在呢用20层的RESNET，去跟这四个不同程度的老师学习，结果发现诶最烂的老师教出来的学生是最强的。

正确率最高的老师，教出来的学生反而是最弱的哦，所以老师本身的实力，并不一定能够反映在学生的成果上，这个我们的高等教育都假设最能做研究的人，就是最会教学的人啊，但往往也不见得是这样好。

那我们有没有办法让这个teacher network学习，怎么去teach呢，是有办法的，我们可以用meta learning的概念，我们可以引进meta learning的概念。

让这个teacher network学习，怎么去teach。

![](img/444b4149d365af36fd28bce8c2cbe7b3_27.png)

那怎么做呢，我们现在的这个teacher net，他的学习的目标不再是单纯的分类的正确率，我们的teacher net学习的目标是student跟teacher，学习以后的正确率好。

就假设你有一个teacher name给你一些训练资料好，你有个teacher net给你一些训练资料，你先做一下knowledge distillation，得到student net。

接下来你再拿另外一些资料来测试一下，student ne的好坏，得到student net在这个测试资料上的testing loss，那teacher net呢它会update它的参数。

它update的目标不是自己能够做得多好，他update的目标是student可以做的多好哦，所以这个teacher net，它不一定是一个正确率特别高的teacher net。

但是他是一个student，跟他做完knowledge distillation以后，结果会特别好的，teacher ne好，这边是简单跟大家讲一下啊。

怎么把meta learning的概念用在nose distillation上面，那如果你想要更知道更多的详情的话啊，可以阅读以下这两篇文章。

那有人可能会觉得说诶这个要update这个teacher net，最终目标是要让student的结果变好，这个会不会很难学，那其实这个teacher net update啊。

不一定要update1整个大模型的所有参数，举例来说，在有的文章里面，他只会去update，比如说teacher net的output temperature，我不知道大家还记不记得。

我们说在做knowledge deallesion的时候，有一个重要的事情是，你会把teacher的output加上temperature，如果忘了忘记的话，你再自己去复习那个啊过去的录影。

按这个temperature到底要加多大呢，过去只能啊当做一个呃hyper parameter，用人手来调啊，但是呢呃透过这种learn to teach的方法。

也许你可以用learn to teach的方法来learn，temperature应该有多大好，那这个是noise destination跟meta learning的结合。



![](img/444b4149d365af36fd28bce8c2cbe7b3_29.png)

接下来呢要跟大家分享meta learning跟domain adaptation的关系。

![](img/444b4149d365af36fd28bce8c2cbe7b3_31.png)

那我们课堂上在讲DMAILDETATION的时候，有给大家看过这个图，那最简单的是knowledge domain，我们有一些但是不多的label data。

那像这种case你要用meta learning来处理，完全是可以的，我们知道meta learning，他特别擅长的就是解few shot learning的题目。

所以meta learning可以很自然地被用在有label data的domain，APTATION上面，但是这边呢我想要特别跟大家分享的，是一个比较tricky的东西。

怎么把meta learning用在dommen in generalization上面，那什么是dommain generalization，dommain generalization的意思。

就是说我们对target的抖man1无所知，我们在对target dman1无所知的情况下，我们想训练一个有比较好的generalize能力的模型，就算是未知的target dman。



![](img/444b4149d365af36fd28bce8c2cbe7b3_33.png)

他也可以有好的表现，好这边呢再稍微讲一下domain generalization的概念，那domain generalization想做到的事情，就是我们有一堆训练的抖man。



![](img/444b4149d365af36fd28bce8c2cbe7b3_35.png)

我们有一个learning alison，我们想用这一些来自不同抖man的资料，去训练一个模型，这个模型它很厉害，就算是在target dman上也有好的表现。

那当我们要把meta learning用在DOMMAGIZATION的时候，我们要做的事情就是learn这个learning algorithm，learn这个可以从不同DMAN里面学出一个模型。

这个模型可以被用在新的target dman上的，Learning algorithm，那至于实际上是要learn learning，algorithm里面的什么东西，那就看你自己。

比如说如果是memo那个系列的work，就是learn learning algism里面的initialization好，但是你仔细想一下，会发现说呃这个还不知真不知道该从何下手，为什么。

因为我们并没有target dman的data，如果我们有target domain data，你当然可以直接learn一个learning algorithm，然后你的目标是要去optimize。

在target dman上的performance，但是不要忘了，在dommen in generalization这样的任务里面，他给抖man的资料，我们在训练阶段是拿不到的。

那怎么把meta learning的概念用在domain generalization上呢。

![](img/444b4149d365af36fd28bce8c2cbe7b3_37.png)

这边就有个神奇的做法，既然target抖man的资料，我们实际上拿不到，那怎么办呢，我们就把training的这些抖man里面的其中一个，抖man in拿出来，让他来假扮target dman哦。

所以我们就把蓝色的这个dman in拿出来说，它是我们现在target dman，我们要在红色跟黄色的抖面上，训练出来一个模型，希望可以被用在蓝色的DMAN上哦。

所以我们就是有一个learning algorithm，他在红色跟黄色的DMAN上进行学习，学出一个模型，这个模型要被用在蓝色的DMAN上，这个蓝色的斗man这个资料我们是有的。

所以我们就可以说我们去learn，这个learning algorithm，比如说套用memo啊等等方法，套用memo learn这个呃initialize的参数啊，它最终的目标是要让啊。

让蓝色的这个抖面上的正确率呢越高越好，就找一个initialization的参数，用红色跟黄色斗man进行训练，但最终希望在蓝色斗面上的结果越高越好。



![](img/444b4149d365af36fd28bce8c2cbe7b3_39.png)

每一个这个training的DMAN呢，都可以各自来扮演这个target dman哦，所以你先拿红色的扮演target dman，那这个时候黄色跟蓝色就负责训练，这个黄色扮演target domman。

红色蓝色就负责训练，蓝色扮演target domin，黄色红色就负责训练，那这边每次不同的这个DMAN，来扮演target dman的时候，就是不同的training的任务好。

我们就在这些training的任务上。

![](img/444b4149d365af36fd28bce8c2cbe7b3_41.png)

learn一个learning the algorithm，然后呢期待把它用在testing的任务上，那testing的任务就是我们最终真正关心的问题。

把所有training domman里面的资料倒在一起，期待在我们从来没有看过的target dman上，在training的时候从来没有看过的target dman上。

在这个绿色的DMAN上也可以有好的表现好。

![](img/444b4149d365af36fd28bce8c2cbe7b3_43.png)

那在文献上呢也有人尝试过这种做法了，举例来说，你可以看看这边放的这个reference，那这个图呢是从reference里面截出来的啦，那你可以很明显的看到说他想要做的是这个呃。

text classification文件分类的任务，那他现在手上呢有英文的资料，有法文的资料，有德文的资料，但是他的target dman呢是日文的资料。

它所以它的这个training task里面呢，这个task one哦，就是train在英文法文上测试，在德文上，test to就是券在英文德文上测试，在发文上，task3就是券在法文德文上哦。

测试在英文上啊，这些是他的训练的任务，那实际上他用的是一个叫NGL的方法啊，那详情我们这边就不讲，总之就是找一个learning algorithm，然后在测试的时候呢，我们测试的任务是要劝在英文。

法文，德文上，然后呢用在日文上哦，所以这是训练的任务，这是测试的任务，用这些训练的任务，learn一个learning的ALISON，期待这个learning algison在测试的任务。

看到这些data的时候，认出来的model可以generalize到没有看过的data，可以generalize到日文上面。



![](img/444b4149d365af36fd28bce8c2cbe7b3_45.png)

好那我们已经知道说呢，meta learning可以拿来帮助这个domain aptation或domain generalization，但是meta learning本身也有可能会遇到。

需要做DOMMEDITATION或domain generalization的状况，什么意思呢，为什么我们需要做DM的TATION，那是因为我们的训练资料跟测试资料。



![](img/444b4149d365af36fd28bce8c2cbe7b3_47.png)

有可能有很不一样的分布，而在meta learning上有另外一个层次的分布差异的问题，在meta learning上，它们分布是不像的状况，这个时候你需要另外一个层级的呃。

domain adaptation哦，所以meta learning可以拿来帮助，machine learning里面的动漫的domain adaptation，但是另外一方面。

mata learning本身可能也会自己也会需要domain adaptation，但这是另外一个level的DOMINDICTATION，训练出一个learning algorithm。

可以apply在不太一样的测试任务上面，这是一个尚待研究的问题，然后在下面呢放了一篇相关的论文给大家参考。



![](img/444b4149d365af36fd28bce8c2cbe7b3_49.png)

好，那最后一个想跟大家分享的主题呀，是meta learning，怎么用在lifelong learning上。



![](img/444b4149d365af36fd28bce8c2cbe7b3_51.png)

啊啊那这边很快的帮大家复习一下live phone learning啊，一般人呢对AI的想象是这个样子的，我们先给我们的模型资料集一，那模型呢就学会任务一，再给他资料集。



![](img/444b4149d365af36fd28bce8c2cbe7b3_53.png)

二模型就学会任务1+2，你不断教他，不断教他，几千年后。

![](img/444b4149d365af36fd28bce8c2cbe7b3_55.png)

它就会变成天网，但是我们知道说，实际上今天的machine learning的训练过程并不是这样的。

![](img/444b4149d365af36fd28bce8c2cbe7b3_57.png)

如果你今天让你的model先看过data1，再看过data2。

![](img/444b4149d365af36fd28bce8c2cbe7b3_59.png)

他很有可能会只记得在data2上学过的东西，但是不记得在data set一上面学过的东西，那这种状况叫做CATROPHIC的forget it。



![](img/444b4149d365af36fd28bce8c2cbe7b3_61.png)

那在过去的课程中，我们已经讲过了一系列可以处理CATROPHY。

![](img/444b4149d365af36fd28bce8c2cbe7b3_63.png)

forgetting的方法，那meta learning有没有可能强化这些方法呢。

![](img/444b4149d365af36fd28bce8c2cbe7b3_65.png)

是有可能的，我今天这边举个例子说明meta learning怎么用，在selective synaptic plasticity上，那这类的方法呢又叫做regalization base的方法好。



![](img/444b4149d365af36fd28bce8c2cbe7b3_67.png)

那现在假设我们有一个data set one，然后我们用data set one呢训练一个模型，这个模型呢叫做SA啊。



![](img/444b4149d365af36fd28bce8c2cbe7b3_69.png)

接下来呢在这个lifelong learning的scenario里面，我们会有data set to，那data set to呢会拿来呢再调整set达参数。



![](img/444b4149d365af36fd28bce8c2cbe7b3_71.png)

得到set a plan，那我们这边期待可以做到的事情是set a派，不只要能够处理data set to的data，它也仍然要可以记得过去学过的东西。

他也要可以处理data set one里面的data，那怎么办呢，在之前课堂上，我们已经提过了一系列REGZATION的方法，比如说EWCSINAS等等，但是这些方法他们是人所设计的人。

设计了一些CTRL，让setup update变成set a pl的时候，不要忘记过去学到的东西，那除了用人来设计REGALIZATION以外，有没有可能透过meta learning的力量。

来找一个比较好的learning algorithm，这个比较好的learning algorithm，它是可以避免catrophic forgetting的呢。



![](img/444b4149d365af36fd28bce8c2cbe7b3_73.png)

是有可能的哦，我们有可能用meta learning的方法来认一个learning，Algorithm，那这个learning algorithm的目标。

不是单纯要让testing set上的正确率变高，我们之前一般在讲meta learning的时候，我们要learn的learning algorithm。

我们LEAR这个learning algorithm，人的目标都是往往都是期待说啊，找到一个learning的algorithm，它可以在testing data上有比较低的loss。

或者是比较高的正确率，但这边我们要处理的是catrophic forgetting的问题，所以你可以改一下meta learning的目标。

你可以说我们要learn一个learning algorithm，这个learning algorithm，他的目标呢是要避免catrophic forget it。

也就是说我们要找一个learning algorithm，这个learning algorithm，把set up update变成set up play以后，不止可以学会新的东西，也不忘记旧的东西。

那有可能用meta learning的方法找到这样子的learning algm吗，是有可能的，以下我列了两篇文章给大家参考。



![](img/444b4149d365af36fd28bce8c2cbe7b3_75.png)

好那就像刚才我们讲DMAIL的TATION的时候，我们说meta learning可以帮助DOMINDICTATION，但是meta learning本身可能也需要domain the patient。

那在lifelong learning其实也是一样的状况。

![](img/444b4149d365af36fd28bce8c2cbe7b3_77.png)

我们说meta learning可以帮助我们认出一个learning，Algorithm，这个learning algorithm，比较有机会可以避免catrophy forget。



![](img/444b4149d365af36fd28bce8c2cbe7b3_79.png)

但是meta learning本身也有可能会遇到CATROPHIC，forgetting的状况，假设你信，建在你在训练这个learning algorithm的时候。

你有一系列的training task，你先用第一组training task，来找一个learning algorithm，接下来再拿第二组的learning the task。

来找learning algorithm，接下来再拿第三组的training the task，来找learning algorithm。

但你仍然有可能遇到cattrophy forgetting的问题，你仍然有可能看完这一组训练的任务以后，找出来的learning alism，他只在黄色的这组任务上面，黄色的这个distribute。

黄色的这组任务上面可以发挥作用，可能就没有办法解了，那你仍然有可能会遇到meta learning本身，仍然有可能会遇到catrophy for getting的问题。

所以meta learning可以避免catrophic forgetting，但meta learning本身也有可能遇到CATROPHIC，forgetting的问题，那怎么解，以下再列出两篇文章。

那这边我们就不细讲。

![](img/444b4149d365af36fd28bce8c2cbe7b3_81.png)

我再列出两篇文章给大家参考，今天就是很简短跟大家介绍meta learning，还有以前呢我们所讲过的种种技术，Self supervised learning。

Domain generalization，Noise desolation，还有lifelong learning之间的晚期好。



![](img/444b4149d365af36fd28bce8c2cbe7b3_83.png)

那呃如果你想学更多跟meta learning有关的事情，尤其是meta learning怎么被用在自然语言处理上的话，那欢迎参考我最近写的一篇overview paper。



![](img/444b4149d365af36fd28bce8c2cbe7b3_85.png)

那我把链接放在这里好，那我讲一件跟课程无关的事情，那其实我现在仍在美东参加frederick genetic，Memorial summer workshop，那我会带领一个团队。

跟很多厉害的学者一起研究，怎么把sales supervised learning的技术用在语音上好，那如果你有兴趣想知道我们打算做什么的话，可以线上听一下6月27号的opening。

那我的演讲的时间是在台湾时间的晚上，11。10分。

![](img/444b4149d365af36fd28bce8c2cbe7b3_87.png)

最后呢我要感谢台智云提供给我们运算资源，让我们可以在workshop的期间做更多的尝试，跑更大的模型好，所以感谢台智云，那今天课呢就上到这边，谢谢大家。



![](img/444b4149d365af36fd28bce8c2cbe7b3_89.png)