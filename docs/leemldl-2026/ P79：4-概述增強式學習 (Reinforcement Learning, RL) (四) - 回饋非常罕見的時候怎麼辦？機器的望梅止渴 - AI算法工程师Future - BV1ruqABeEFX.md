# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P79：4-概述增強式學習 (Reinforcement Learning, RL) (四) - 回饋非常罕見的時候怎麼辦？機器的望梅止渴 - AI算法工程师Future - BV1ruqABeEFX

好这个，接下来啊，想要跟大家分享的是一个叫做reward。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_1.png)

shaping的概念，什么是reward shaping呢，到目前为止，我们学到的东西是，我们把我们的actor拿去跟环境互动。



![](img/efa7d1c7ddcc63affe0cb1258c4fd167_3.png)

得到一堆reward，那把这些reward做某些的整理以后。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_5.png)

得到这边的分数A啊，有了这边的分数A你就可以去教你的actor，该做什么不做什么，但是在这个reinforcement learning里面，我们很怕遇到一种状况，是假设reward永远都是零的时候。

怎么办呢，假设多数的时候reward都是零，只有非常低的几率，你会得到一个巨大的reward的时候，那怎么办呢，假设reward几乎都是零，那意味着什么，意味着说你今天这个A不管怎么算。



![](img/efa7d1c7ddcc63affe0cb1258c4fd167_7.png)

都是都是零对，每一个action都是差不多的。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_9.png)

反正不管执行什么action，得到的reward都是零嘛，所以执行这个action，执行那个action根本没差，那如果不管执行什么action，reward几乎都是零的话。

那你根本没有办法去确认你的actor，那讲到这种sparse reward的问题，也许有人马上会想到的是诶，下围棋也许是一个sparse reward的问题，因为在下围棋的时候，你每落一子。

你并没有得到reward，你并没有得到positive或negative的reward，只有在整整场游戏结束，落完最后一子的时候，在中盘，在落完最后一局游戏结束的时候。

你赢了才会得到positive reward，你输了才会得到negative的reward，但是我觉得相较于其有一些其他任务，这个下围棋还算是比较有reward的，RL的问题，举例来说。

假设今天的问题是，你要教机器手臂去栓螺丝，而教机械手臂栓螺丝这个问题呀，你合理的reward的定义是，假设今天机械手臂成功把螺丝拴进去，他就得到positive reward，没有把螺丝钻进去。

reward就是零，但是你想想看，一开始你的机械手臂，它里面的act or的参数是随机的啊，所以他就在空中随便挥舞，怎么挥舞，reward都是零，不像是下围棋，你至少整场游戏玩完。

你还有正面的或负面的reward，而像机械手臂，你在你要叫机械手臂去栓螺丝，除非他正好且非常巧合的拿起一个螺丝，再把它拴进去，它得到正向的reward，不管他做什么事情都没差。

得到的reward通通都是零分好，那遇到这种状况的时候怎么办呢，遇到这种状况的时候，有一个解法，就是啊我们想办法去提供额外的reward，来引导我们的agent学习，也就是说在原来的reward。

也就是我们真正要agent去maximize的reward之外，我们在定义一些额外的reward，我们定义这些额外的reward，来帮助我们的agent学习学习。

那这种东西这种定额外的reward来帮助agent学习，这种事情呢，就叫做reward shaping，那你知道我们人呢其实也汉，很擅长做reward shaping呃，举例来说啊。

这我让我想到一个这个妙法莲华经中的故事啊，这个故事呢出自妙法莲华经中的化成御品啊，这个故事就是有一个领队，然后带一群人呢去呃找宝藏，然后宝藏呢在500由旬之外，那游巡是什么单位，我也忘了。

你就记你就当做很远就对了，就当五百五百万公里之外，然后呢这群人呢走到半路已经过了半途了，觉得很累，不想再往前走了，那大家就坐在地上哀嚎，不想再往前走了，那领队看他不想再往前走怎么办呢，他就跟大家说呃。

再往前10km呃，有一个五星级的饭店，大家就可以去休息了啊，大家就看到五星级的饭店就很高兴就去休息了，然后隔天早上饭店就不见了，而领队说那个饭店呢是我用法力变出来的，哎那领队有法力嗨。

但是法那饭饭店是领队用法力变出来的，然后为了鼓励大家在继续往前走，免得大家半途而废，哎这个妙法莲华经说这个故事是为了表示说啊，佛最后希望大家成就的是佛道啊，但佛道非常的长，所以中间呢设了小圣中圣。

大圣等不同的位阶来引导大家前进，那如果对应到比较生活化的例子，就是啊比如说现在叫你念博士啊，你可能觉得呃念你要博士毕业才能够夺博，拿到博士学位才能够得到reward，那你就会觉得哇这个路呢非常的长。

然后就不想要念博班了，但是如果告诉你说啊，你先休个课就可以得到reward，然后做一点专题，虽然可能也没有做出什么厉害的成果，但老师就会说你好棒啊，你也得到reward。

然后最后呃先发一个second tier的conference来得到reward，再发表top t top tier conference，再发再就得到reward，到最后你就可以博班毕业。

这样一步一步往前走，最终你就可以达成最终的目标，这样这种地方也要夜配念博班，我实在是有点受不了了，不过没关系。



![](img/efa7d1c7ddcc63affe0cb1258c4fd167_11.png)

反正这门课快结束了，要在叶配也没几次了，好那这个呢就是reward shaping的概念好，那我们接下来呢就举一个reward shaping，真正实际使用在RL里面的例子给大家参考。

那这边举的例子呢是用WISDO来跟大家举例。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_13.png)

那因为怕大家不知道威斯顿是什么，所以这边呢还是放一个影片给大家看一下。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_15.png)

这个vista呢是一个第一人称的射击游戏，那蛮常有人用IL来玩VISTON的。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_17.png)

那以下呢是一个WINSTON，用RL来玩vista，用机器来玩VISTON这个游戏的的这个啊，比赛的录影。



![](img/efa7d1c7ddcc63affe0cb1258c4fd167_19.png)

我们来看一下这个比赛录影，长起来像这个样子，这边的每一个选手啊都不是人哦，每一个选手通通都是机器。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_21.png)

所以你仔细看一下会发现说啊。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_23.png)

有些人的行为很奇怪，比如说右上右上角这个人他还蛮容易卡墙的。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_25.png)

呃右上角这个人还蛮容易卡墙的，他在他在撞墙壁，为什么，因为他不是个人，他是一个机器好，这个是让你知道一下，bison大概是什么样的游戏啊，那这个影片非常长啊，它是一个长达两小时的史诗级的战斗。

你有兴趣再慢慢把它看完。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_27.png)

而在当年那个bison的比赛里面呐，第一名的队伍就有用到了reward shaping的概念，那在VISTON这个游戏里面，你被敌人杀掉，你就扣分，你杀了敌人就加分。

但如果你光凭着这个游戏里面真正的reward，来训练agent，你是很难把它训练起来的哦，所以呢在这篇文章里面就使用了一些reward，shaping的概念。

那我们就来看一下他是怎么定这些reward啊，举例来说，这个第一点呢我们等一下再看，我们先看第二点，第二点他说如果今天有扣写，那你就得到负的reward，那其实在游戏里面扩写并没有死。

惩罚扣血并不会扣分，你要死掉才扣分，但是如果机器要到死掉才知道呃，他得到负的reward，那可能他可能要很花很久的时间才能学到，扣血跟死掉之间的关联性，所以这边直接告诉机器不可以扣血，扣血是坏的事情好。

然后这边是如果呃损失弹药就扣一点分数，然后减到这个医药包就加分，捡到弹药的补给包就加分，那这些事情在游戏里面是不会影响分数的，但是我们人我们developer另外强加给机器，来引导机器学习好。

接下来就是一些比较有趣的reward了，举例来说，他说呢如果你的agent总是呆在原地，那就要扣分哦，为什么需要这样的reward呢，因为如果你没有这样的reward，对agent来说，一开始他非常弱。

他出去时候能随便走两步就被敌人杀死了，所以对他来说，对一开始很弱的agent来说，可以得到比较高，reward的做法，也许就是呆在原地，待在原地，至少reward室里呢，那出去碰到敌人哦，还要被扣血。

那多划不来啊，所以为了避免machines最后什么都没有学到，就只会待在原地，所以强制告诉他说你只要待在原地就直接扣分，然后还告诉他说，如果你动诶，就给你一个很小的分数啊，这边你只要每动一下。

就给你9×10的五次方，一个非常小的，但是是positive的reward好，但是光是要求机器动是不够的，所以这边就多加了一个非常有趣的reward，这个reward是每次如果A证活着。

A证每活着他就要被扣分，你感觉很奇怪，活着不是一件好事吗，为什么活着反而应该要被扣分呢，那是因为假设现在活着没有扣分，或者是甚至是一件正面的事情，对AJ来说，他会学到的可能就是边缘ob啊。

诶你虽然有要求它动，那你要求它动没有关系啊，他就在边缘一直呃自转就好，他在边缘一直转圈圈就好，然后看到敌人就躲开，就不要不要正跟敌人做任何的正面交锋，那对你的A卷来说，也许这是一个最安全的做法。

但是为了强迫ASI学习去杀敌人，所以反而告诉他说，你只要活着就是扣分，你要想办法呃，呃不可以活太久，你要想办法去跟别人交手哦，所以这是一个非常有趣的reward shaping的方式。

那看到这些reward shaping，你就会发现说reward shaping这一件事情呢，其实是需要花domman in knowledge的，它其实是需要凭借着人类对你现在环境的理解，来强加上去。

那今天再举另外一个reward shaping的例子啊，假设你今天要训练一个机器手臂，那这个机器手臂的工作呢，就是把这个蓝色的板子插到这个棍子上好，那像这样子的任务，你要凭着RL的方法让机器凭空学会。



![](img/efa7d1c7ddcc63affe0cb1258c4fd167_29.png)

把蓝色的板子插到这个棍子上，没有那么容易是，但是你可能会想到一个很直觉的reward，shaping的方法是，假设今天这个蓝色的板子离这个棍子越近，那我们得到的reward就越大，但是如果你仔细想想。

会发现说，单纯让蓝色的板子离这个棍子越近是不够的，为什么让蓝色的板子离棍子近是不够的呢，你可以看看这个诶，呃像右边这右边这两个case，机械手臂也是想把蓝色的板子挪进棍子。

但他做的事情呢其实就是去打那个棍子，然后从侧面接近，从侧面接近是没有用的，把蓝色的板子从侧面接近，棍子并不能够达到你最终的目标啊，所以如果我们单纯只是说啊，现在你的蓝色的板子离这个棍子越近。

它的reward就越大，你用reward shaping的方法，把蓝色的板子跟棍子之间的距离，当做一个新的reward，但可能对你最终想要解决问题，本身是不一定有帮助的。

所以reward shaping这个东西，你在用的时候必须要小心，它需要你对这个问题本身有足够的理解，你才有办法使用reward shaping这样的招数，好我们看一下有没有同学有问问题的。

好毛目前没有同学问问题。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_31.png)

那我们就继续啦，好，那reward shing里面呢。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_33.png)

有一个特别有趣而知名的做法，叫做to riosity base的reward shaping。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_35.png)

也就是呢给机器加上好奇心啊。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_37.png)

给机器加上好奇心，什么叫做给机器加上好奇心呢。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_39.png)

所谓好奇心的意思就是要去探索新的事物。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_41.png)

所以在原来的reward之外，我们加上一个reward。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_43.png)

这个reward是，如果机器它在活动的过程中看到新的东西。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_45.png)

它就被加分，但这边呢又有一点要强调的是，新的东西必须是有意义的心，不是无谓的心。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_47.png)

什么叫做有意义的心，不是无谓的心呢，那这个我们等一下再解释好。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_49.png)

那这个curiosity base的呃，这个reinforcement learning呢。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_51.png)

呃它来自于ICNL2017的这篇文章，那这篇文章里面有一个额非常惊人的demo。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_53.png)

那我们来播一下这个demo。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_55.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_56.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_57.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_58.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_59.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_60.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_61.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_62.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_63.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_64.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_65.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_66.png)

Du da da ba du du du du du du du du du du。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_68.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_69.png)

哎我想稍微解释一下刚才那个影片的意思啊。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_71.png)

刚才那个影片的意思是说啊，哎我把它停下来，等我一下哦，就是他让机器玩马力欧，那他甚至在马力欧这个游戏里面，没有任何的reward，他甚至没有告诉机器说，破关就可以得到positive的reward。

那其实你告诉机器破关可以到positive reward，也没用啦，这个容reward太SPSS了，大概很难拿来训练的agent，他只告诉机器说你要不断地看到新东西，那光是这一件事情。

就可以让机器学会破马力欧的其中一些关卡，那当然这样子的方法，也许对马力欧而言是最合适的，你知道马力欧是横向卷轴游戏吗，那你要破关就是要不断的往右走嘛，那机器它要看到新的东西，就不断的需要往右走嘛。

所以机器会呃，光借由curiosity这件事，就可以学到破解马力欧的一些关卡，不过他有尝试说训练在前面几关。



![](img/efa7d1c7ddcc63affe0cb1258c4fd167_73.png)

然后然后直接测。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_75.png)

直接把AG卷放在那个呃地下迷宫地下的关卡，然后就发现说做不起来。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_77.png)

在地下关卡还是要微调一些network，才微调一下network才做的起来好。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_79.png)

那这个影片还有后半段了，我们。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_81.png)

诶我们直接从某个地方开始看好了。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_83.png)

哦他接下来是他。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_85.png)

直接下来是直接拿叫机器去玩那个威斯顿啊，直接到机器去玩威斯顿。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_87.png)

我们来放一下威斯顿的部分好了。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_89.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_90.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_91.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_92.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_93.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_94.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_95.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_96.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_97.png)

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_98.png)

好那最后那一个背景有一堆杂讯。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_100.png)

有点像是那个电视机坏掉那种杂讯的那个画面，你可能有点不知道这他这个影片想要表达什么，但那个部分就是我想要，我刚才在最前面讲到的有意义的心这件事情诶。



![](img/efa7d1c7ddcc63affe0cb1258c4fd167_102.png)

等我一下哦，好有意有意义的心。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_104.png)

这件事情就是，假设我们要求agent要一直看到新的东西。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_106.png)

那如果你的经画面背景有一个杂讯。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_108.png)

那杂讯会不断的变化，所以对agent来说。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_110.png)

杂讯是新的东西，也许他就不会学到去探索新的环境了。

![](img/efa7d1c7ddcc63affe0cb1258c4fd167_112.png)

反正光站在那边看杂讯就够了，他会觉得他不断的看到新的东西，所以其实在curiosity base的这个IO里面呢，也有想办法克服这种没意义的心，这种看到杂讯的问题，至于实际上怎么做。



![](img/efa7d1c7ddcc63affe0cb1258c4fd167_114.png)