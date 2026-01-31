# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P78：3-概述增強式學習 (Reinforcement Learning, RL) (三) - Actor-Critic - AI算法工程师Future - BV1ruqABeEFX

![](img/1da2592808784ec8e7b94bc3bc33f72c_0.png)

好那我们就开始上课吧，那等一下的规划是这样，我们先把RL呢讲到一个段落，然后再请助教公布作业好，那上一次啊IL的部分。



![](img/1da2592808784ec8e7b94bc3bc33f72c_2.png)

我们讲说我们要认一个actor好。

![](img/1da2592808784ec8e7b94bc3bc33f72c_4.png)

那这一次啊我们要认另外一个东西，这个东西呢叫做CRITI。

![](img/1da2592808784ec8e7b94bc3bc33f72c_6.png)

那我会先解释critics是什么，然后我们再来讲说这个CRITA。

![](img/1da2592808784ec8e7b94bc3bc33f72c_8.png)

对learn actor这个东西有什么样的帮助，好，我们先看critic是什么，critic是什么呢，critics是额，他要了拿他是他的工作，是要来评估一个actor的好坏哦。

就你现在已经有一个actor啊，它的参数呢叫sea，那CRIT的工作就是他要评估说，如果这个actor他看到某个样子的observation哦，看到某一个游戏画面，接下来他可能会得到多少的reward。

那CRITI有好多种不同的变形，有的CRITI是只看游戏画面来判断，有的critics是说采取某看到某一个游戏画面，接下来又发现actor采取某一个action，在这两者都具备的前提下。

那接下来会得到多少reward，那这样讲呢还是有点抽象，所以我们讲的更具体一点，我们直接介绍一个，我们等一下呢会真的被用上，你在作业里面真的派得上用场的。

这个critic叫做value function。

![](img/1da2592808784ec8e7b94bc3bc33f72c_10.png)

那这个value function呢，我们这边用大写的v of s来表示好，那它的输入是什么。

![](img/1da2592808784ec8e7b94bc3bc33f72c_12.png)

它的输入呢是S，也就是呃现在游戏的状况，比如说游戏的画面，那这边要特别注意一下V啊，它是有一个上标set a的，这个上标set a代表什么意思呢，代表这个V呢它观察的对象是sea这个actor哦。

他观察的这个actor呢，它的参数呢是sea好，那这个V呢v set大呢就是一个function哦，它的输入是S，那输出呢是一个SCALA哦，这边用v set大的S呢来表示这个SCALA啊。

那这个SCALER呢这个数值有什么样的含义呢，这个数值的含义是这一个actor set a，我放在上标的这个actor set a，它如果看到observation s，如果看到输入的这个S的游戏画面。

接下来他得到的discounted the cumulative reward，是多少，你还记得这个discounted accumulated reward。



![](img/1da2592808784ec8e7b94bc3bc33f72c_14.png)

是什么吗，记不记得，我们之前说在评估某一个action好坏的时候。

![](img/1da2592808784ec8e7b94bc3bc33f72c_16.png)

你不能单看那个action执行完的reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_18.png)

你要把那个action执行完的reward加上，接下来所有的reward，得到一个CUMULATED的reward，叫G，这样才能够评估在某一个state执行某一个action的呃，好坏的程度。

但是我们又说。

![](img/1da2592808784ec8e7b94bc3bc33f72c_20.png)

你把所有的R从执行某一个action开始到游戏结束，所有的R直接都加在一起，并不是一个好的想法，你应该乘上一个discounted factor，叫做伽马哦，就今天得到的reward。

如果离执行这个某一个action的时间越远的话，那那个reward就跟那个action越没有关系。

![](img/1da2592808784ec8e7b94bc3bc33f72c_22.png)

所以应该乘上一个discounted factor叫做伽马，那我们得到GP这个G派呢，就是这边所谓的discounted trumulated the reward啊。

那这个value function他的工作啊，就是要去估测说对某一个actor来说，如果现在他已经看到某一个游戏画面，那接下来会得到的discontact to ultrumulated reward。



![](img/1da2592808784ec8e7b94bc3bc33f72c_24.png)

应该是多少哦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_26.png)

当然discontaccumulated reward，你可以直接透过把游戏玩到底，就就就哎你看到某尼尔你已经有了actor set up。



![](img/1da2592808784ec8e7b94bc3bc33f72c_28.png)

那假设他看到这个stay s，那最后他到底会得到多少的这个GP呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_30.png)

你就把这个游戏玩完，你就知道了，但是这天这个value function他的能力就是他要未卜先知。

![](img/1da2592808784ec8e7b94bc3bc33f72c_32.png)

未看先猜，游戏还没有玩完，只光看到S就要预测这个actor。

![](img/1da2592808784ec8e7b94bc3bc33f72c_34.png)

他可以得到什么样的表现啊，那这个就是value function要做的事情。

![](img/1da2592808784ec8e7b94bc3bc33f72c_36.png)

举例来说呢，假设你给value function哎。

![](img/1da2592808784ec8e7b94bc3bc33f72c_38.png)

这个游戏画面，他就直接预测说看到这个游戏画面。

![](img/1da2592808784ec8e7b94bc3bc33f72c_40.png)

接下来应该会得到很高的CUMULATED的reward啊，为什么，因为游戏这个游戏画面里面还有很多的外星人。



![](img/1da2592808784ec8e7b94bc3bc33f72c_42.png)

那假设你的这个actor他很厉害。

![](img/1da2592808784ec8e7b94bc3bc33f72c_44.png)

他是个好的actor，他是能杀得了外线的actor，那接下来他就会得到很多的reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_46.png)

那像这个画面，这已经是游戏的中盘游戏的残局。

![](img/1da2592808784ec8e7b94bc3bc33f72c_48.png)

游戏快结束了，剩下的外星人没几只了，那可以得到的reward就比较少。

![](img/1da2592808784ec8e7b94bc3bc33f72c_50.png)

那这些数值你把整场游戏玩完。

![](img/1da2592808784ec8e7b94bc3bc33f72c_52.png)

你也会知道，但是value function想要做的事情就是未卜先知，在游戏没玩完之前。

![](img/1da2592808784ec8e7b94bc3bc33f72c_54.png)

就先猜应该会得到多少的discounted，Accumulated reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_56.png)

那这边有一件要跟大家特别强调的事情，是这个value function是有一个上标set up的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_58.png)

这个value function跟我们观察的actor是有关系的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_60.png)

同样的observation，同样的游戏画面。

![](img/1da2592808784ec8e7b94bc3bc33f72c_62.png)

不同的actor他应该要得到不同的discounted。

![](img/1da2592808784ec8e7b94bc3bc33f72c_64.png)

Cumulated reward，我刚才在举例子的时候，我说假设我们有一个好的actor。

![](img/1da2592808784ec8e7b94bc3bc33f72c_66.png)

看到这个游戏画面会有高的value，看到这个游戏画面会有D的value。

![](img/1da2592808784ec8e7b94bc3bc33f72c_68.png)

但是假设你的actor其实很烂，它很容易被外星人杀死。

![](img/1da2592808784ec8e7b94bc3bc33f72c_70.png)

那也许看到这个画面，他的value也是低的，因为有一堆外星人，他随便动两下。

![](img/1da2592808784ec8e7b94bc3bc33f72c_72.png)

他就被杀死了，他根本得不到reward，这个land的actor，在这个画面他可能拿到的V也是D的哦。



![](img/1da2592808784ec8e7b94bc3bc33f72c_74.png)

所以value function的数值是跟观察的对象有关系的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_76.png)

好，这个是critic好。

![](img/1da2592808784ec8e7b94bc3bc33f72c_78.png)

那在讲CRITI要怎么被使用，在reinforcement learning之前呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_80.png)

我们来讲一下CRIT是怎么被训练出来的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_82.png)

那有两种常用的训练方法，第一种方法呢是monte carlo base的方法。

![](img/1da2592808784ec8e7b94bc3bc33f72c_84.png)

这边缩写成MC好。

![](img/1da2592808784ec8e7b94bc3bc33f72c_86.png)

那怎么训练出这一个value的呃function呢，这个value的creative reset大呢啊，你就如果是用MC的方法的话，非常直觉，你就这样做，你就把actor呢拿去跟环境互动互动很多轮。

那actor呢跟游戏跟环境互动以后呢，actor呢去玩这个游戏以后呢，你就会得到一些游戏的记录，你就会发现说假设actor看到SA。



![](img/1da2592808784ec8e7b94bc3bc33f72c_88.png)

那因为你已经把游戏玩完了嘛，你可能玩了很多场游戏，那你就知道说看到stay。

![](img/1da2592808784ec8e7b94bc3bc33f72c_90.png)

看到observation essay，接下来的cumulative reward会是g a plan。



![](img/1da2592808784ec8e7b94bc3bc33f72c_92.png)

我这边把DISCONTE省略掉了，反正你知道我的意思就好了好。

![](img/1da2592808784ec8e7b94bc3bc33f72c_94.png)

那这个时候呢你的value function就得到一笔训练资料。

![](img/1da2592808784ec8e7b94bc3bc33f72c_96.png)

这笔训练资料告诉他说，如果看到SA作为输入他的输出啊。

![](img/1da2592808784ec8e7b94bc3bc33f72c_98.png)

这个v set a到SA啊，应该要跟g a pl越接近越好好。

![](img/1da2592808784ec8e7b94bc3bc33f72c_100.png)

那假设你今天simple到另外一个observation。

![](img/1da2592808784ec8e7b94bc3bc33f72c_102.png)

看到另外一个游戏画面，把游戏玩完之后，发现得到的cumulated reward是GB pl。

![](img/1da2592808784ec8e7b94bc3bc33f72c_104.png)

那这个时候呢你的这个value function呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_106.png)

输入SA它就应该得到VC大do sb那这个v set。

![](img/1da2592808784ec8e7b94bc3bc33f72c_108.png)

然后等SB就应该跟GB pl越接近越好好，那这个非常直觉，你就去观察ex会得到的cumulated reward，那观察完你就有训练资料。



![](img/1da2592808784ec8e7b94bc3bc33f72c_110.png)

直接拿这些训练资料来训练value function。

![](img/1da2592808784ec8e7b94bc3bc33f72c_112.png)

好，这个MC呢是一个很直觉的做法，接下来我们来看另外一个。

![](img/1da2592808784ec8e7b94bc3bc33f72c_114.png)

没有那么直觉的做法啊，这个做法呢叫做temperor difference approach。

![](img/1da2592808784ec8e7b94bc3bc33f72c_116.png)

缩写呢是TD那temporal difference approach，他希望做到的事情是不用玩完整场游戏。



![](img/1da2592808784ec8e7b94bc3bc33f72c_118.png)

才能得到训练value的资料，你只要在某一个observation s st的看到st的时候，你的actor执行的AT得到reward RT，然后接下来再看到ST加一这样的游戏画面。



![](img/1da2592808784ec8e7b94bc3bc33f72c_120.png)

光看到这样一笔资料就能够训练vs了哦，光看到这样子的资料，就可以拿来更新vs的参数了，那如果光看这样一笔资料就可以更新vs的参数，有什么样的好处呢，它的好处是你想在MC里面你要玩完整场游戏。

你才能得到一笔训练资料，但有的游戏其实很长啊，甚至有的游戏也许他根本就没有不不会结束，它永远他都他都一直继续下去，他永远都不会不会结束，那像这样子的游戏，你用NC就非常的不适合。

那这个时候你可能就希望采用TD的方法好。

![](img/1da2592808784ec8e7b94bc3bc33f72c_122.png)

那怎么只看到这样子的资料就拿来训练vs呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_124.png)

这边举一个例子好，我们先来看一下v of s t跟v of s t加一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_126.png)

它们之间的关系，那v of s st是什么。

![](img/1da2592808784ec8e7b94bc3bc33f72c_128.png)

我们说view of s st，就是看到s st之后的tumtumulated reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_130.png)

所以v of s t就是RT加上伽马RT加一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_132.png)

加上伽马平方RT加二，以此类推，然后v of s t加一就是RT加一加伽马RT加二。

![](img/1da2592808784ec8e7b94bc3bc33f72c_134.png)

以此类推，那你发现说这两个v v of s t，跟v of s t加一啊，它们之间是有关系的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_136.png)

什么样的关系呢，你可以把它写成这样一个式子。

![](img/1da2592808784ec8e7b94bc3bc33f72c_138.png)

把v of s t加一乘上伽马再加RT好吧。

![](img/1da2592808784ec8e7b94bc3bc33f72c_140.png)

v of s t加一每一项都乘伽马，再加上RT就会变成v of s t哦，所以v of s t跟v of s t加一，中间有这样子的关系。



![](img/1da2592808784ec8e7b94bc3bc33f72c_142.png)

我们现在呢有这样一笔资料以后，我们就可以拿来训练我们的value function。

![](img/1da2592808784ec8e7b94bc3bc33f72c_144.png)

希望value function呢可以满足。

![](img/1da2592808784ec8e7b94bc3bc33f72c_146.png)

这边我们所写的这个式子好，那怎么什么意思呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_148.png)

就是假设我们现在有这样一笔资料，我们就把s st带到value function里面。

![](img/1da2592808784ec8e7b94bc3bc33f72c_150.png)

得到VOST，我们要s st加一，带到value function里面得到v of s t加一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_152.png)

虽然我们不知道v of s t是多少，我们也不知道view of s t加一应该是多少，我们没有这两个东西的标准答案。



![](img/1da2592808784ec8e7b94bc3bc33f72c_154.png)

但我们知道它们相减应该是多少，根据上面这个式子，我们把v of s t加一乘上伽马，然后再去减v of s t哦。



![](img/1da2592808784ec8e7b94bc3bc33f72c_156.png)

把v of s t减掉伽马层，v of s t加一应该要跟RT越接近越好啊。

![](img/1da2592808784ec8e7b94bc3bc33f72c_158.png)

RT呢在这边我们是有收集到RT这笔资料的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_160.png)

我们要知道VOST跟这个v of s t加一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_162.png)

之间的关系，所以我们知道v of s T1减掉伽马乘上，v of s t加一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_164.png)

应该跟RT越接近越好，所以你就有了这样子训练资料，输入ST1，输入ST加一，他们都通过v set up，然后呢把它们相减，然后要跟RT越接近越好啊，这个就是TD的方法好。



![](img/1da2592808784ec8e7b94bc3bc33f72c_166.png)

那所以我们介绍了两个这个训练value function的方法啊。

![](img/1da2592808784ec8e7b94bc3bc33f72c_168.png)

介绍两个训练critic的方法，一个叫NC，一个叫pd，那这两个方法其实你拿来计算同样的呃，观察到的结果，同样的讯，同样的资料，同样的赛道，你用NC跟TD来观察。

你算出来的value function很有可能会是不一样的啊，那这边呢就举一个例子啊，这个例子是这样子的，我们观察某一个actor啊，这个VECTACTOR呢跟环境互动，玩了某一个游戏八次啊。

当然这边为了简化计算，我们假设这些游戏都非常简单，都一个回合就到两个回合就结束了哦，所以那个actor第一次玩游戏的时候呢，他先看到SA这个画面得到rewarding。

接下来看到SB这个画面得到rewarding，游戏结束，而接下来呢这个有连续六场游戏，都是看到SB这个画面得到reward1就结束了，最后一场游戏看到诶，SB这个画面得到rewarding就结束了。

那我们这边呢呃先无视actor呃，为了简化起见，无视actor，我们也假设呢伽马就等于一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_170.png)

也就是没有做discount好，那这个SB应该是多少呢，view of sb应该是多少呢，我们知道这个view of sb啊。



![](img/1da2592808784ec8e7b94bc3bc33f72c_172.png)

他的意思就是这个看到SB这一个这个画面。

![](img/1da2592808784ec8e7b94bc3bc33f72c_174.png)

你会得到的reward的期望值。

![](img/1da2592808784ec8e7b94bc3bc33f72c_176.png)

那SB这个画面呢我们在整，我们在这八次游戏中总共看到了八次。

![](img/1da2592808784ec8e7b94bc3bc33f72c_178.png)

每次游戏都有看到SB这个画面，看到SB这个画面之后会得到多少reward呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_180.png)

八次游戏里面哪有六次得到一分，两次得到零分，所以平均是3/4分没有问题，所以v of sb就是34，妥妥的，没有争议，那v of sa应该是多少呢，你觉得看到SA接下来应该要得到多少reward呢。

根据这八笔训练资料。

![](img/1da2592808784ec8e7b94bc3bc33f72c_182.png)

看到SA接下来应该得到多少reward呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_184.png)

好给大家十秒钟的时间，你把你的答案写在留言板上，你把你的答案打在留言区上，我们趁着这个机会来回答一下同学们的问题。



![](img/1da2592808784ec8e7b94bc3bc33f72c_186.png)

有吗哎，好如果大家有问题的话，你就可以打在聊天室里面，好接下来给大家一点时间想想看，你觉得v of sa，根据我们看到的这八笔训练资料，它应该是多少呢，把你的答案写在聊天室里面。

我看这个聊天室到底能不能用诶，可以，好我看到了好多答案，几乎所有人都说是零，哎好几乎所有人都是零。

![](img/1da2592808784ec8e7b94bc3bc33f72c_188.png)

有别的答案吗，好几乎没有其他答案，所有人都说是零，好多数同学都说是零，零是不是一个正确的答案呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_190.png)

零是不是一个正确的答案呢，他既对也不对。

![](img/1da2592808784ec8e7b94bc3bc33f72c_192.png)

其实还有另外一个可能的答案是3/4。

![](img/1da2592808784ec8e7b94bc3bc33f72c_194.png)

我看没有人写3/4啊，等一下来解释为什么有可能算出3/4等零。

![](img/1da2592808784ec8e7b94bc3bc33f72c_196.png)

也是一个合理的答案，为什么你会觉得应该是零呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_198.png)

零是用MONTECARLO的想法得到的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_200.png)

为什么是零，因为我们看到SA只有一次啊，看到SA以后会得到多少reward，这是零呐，看到SA以后哦，得到reward0，再看到SB得到reward还是零。

所以accumulated reward就是零。

![](img/1da2592808784ec8e7b94bc3bc33f72c_202.png)

所以如果从MONTECARLO的角度来看，我们看到SA接下来算出来的G应该是多少。

![](img/1da2592808784ec8e7b94bc3bc33f72c_204.png)

就是零呢，所以v of s a应该就是零，妥妥的，没问题，几乎所有同学都得到了正确答案，但如果你用TD，你算出来的可会是不一样的，结果怎么说呢，因为v of sa跟v of sb中间有这样子的一个关系。



![](img/1da2592808784ec8e7b94bc3bc33f72c_206.png)

这个v of s a啊应该要等于v of sb加上reward哦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_208.png)

就是你在看到SA之后得到reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_210.png)

接下来进入SB，那这个v of sa应该等于v of sb加上这个reward哦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_212.png)

这边notation没有用的呃。

![](img/1da2592808784ec8e7b94bc3bc33f72c_214.png)

非常好了，这个R哦指的是这边这一个R啊，这个这个R指的是这边这个R，所以按照这个想法，view of sb是多少34。



![](img/1da2592808784ec8e7b94bc3bc33f72c_216.png)

这个R是多少是零，但view of sa应该是34呐。

![](img/1da2592808784ec8e7b94bc3bc33f72c_218.png)

对不对，按照TD的想法，view of sa应该是34，你可能会问说，那到底MONTECARLO跟TD谁算出来是对的呢。



![](img/1da2592808784ec8e7b94bc3bc33f72c_220.png)

呃都可以说是对的，他们只是背后的假设是不同的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_222.png)

对MONTECARLO而言，他就是直接看我们观察到的资料，SA之后接SB得到的accumulated的reward就是零呢，所以v of sa当然是零，但对于TD而言，它背后的假设是这个呃。

呃SSAR跟SB啊是没有关系的，看到SA之后再看到SB并不会影响看到SB的reward，你现在看这八笔训练资料，给你一种错觉。



![](img/1da2592808784ec8e7b94bc3bc33f72c_224.png)

觉得说v of s s应该是零，那只是因为你sample到的资料太少了。

![](img/1da2592808784ec8e7b94bc3bc33f72c_226.png)

看到SB应该可以期望的reward是34，只是因为景这天正好运气不好，看完SA以后再看SB正好R是零，但是其实期望值应该3/4，你一直正好运气不好。



![](img/1da2592808784ec8e7b94bc3bc33f72c_228.png)

看到R40，你才会觉得SA是零，但是其SB看到SB以后。

![](img/1da2592808784ec8e7b94bc3bc33f72c_230.png)

得到的期望reward应该是34呢，所以看到SA以后。

![](img/1da2592808784ec8e7b94bc3bc33f72c_232.png)

你会看到SB，那你得到的这个期望的reward也应该是34。

![](img/1da2592808784ec8e7b94bc3bc33f72c_234.png)

那所以从TD的角度来看。

![](img/1da2592808784ec8e7b94bc3bc33f72c_236.png)

SB会得到多少reward，跟SA是没有关系的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_238.png)

所以你应该，所以SA的这个cumulated reward应该是34。

![](img/1da2592808784ec8e7b94bc3bc33f72c_240.png)

但对于monty color而言，他并不觉得SA跟SB是没有关系的，也许SA就是一个带赛的observation，看到SA以后，你就影响了SB会得到的reward，也许看到SA以后。

SB就是会得到reward等于零，就他们之间互相有影响的，看到SA以后，SB就会等于零，那v of sa应该等于零哦，所以总之用MC来计算，用TD来计算会有微妙的差异，好我来看看有没有同学有问题。

好目前没有啊，助教我统计一下，说哦只有一个同学回答一，其他都是零好，那这个是NC跟TD啊。

![](img/1da2592808784ec8e7b94bc3bc33f72c_242.png)

这个是MC跟TD好，那接下来我们就是要看说哎。

![](img/1da2592808784ec8e7b94bc3bc33f72c_244.png)

这个呃critic怎么被用在训练actor上面。

![](img/1da2592808784ec8e7b94bc3bc33f72c_246.png)

那还记不记得我们上一次啊，最后我们讲到这个actor的方法的时候，我们说啊怎么训练一个actor，你就先把actor跟环境互动，得到一些reward。

然后你得到一堆这个observation跟这个action的pair，然后你要说诶，这个在s one执行a one的时候多好呢，得到一个分数a one。

那我们说这个a one呢它是TRIULATED的reward，那上周又有同学问到说，难道CUMULATED的reward不需要做normalization吗，需要做normalization。



![](img/1da2592808784ec8e7b94bc3bc33f72c_248.png)

所以我们说这个减掉一个B当做normalization。

![](img/1da2592808784ec8e7b94bc3bc33f72c_250.png)

但这个B的值应该设多少呢，九不好说。

![](img/1da2592808784ec8e7b94bc3bc33f72c_252.png)

那我这边呢告诉大家说，一个V合理的设法是把它设成v of s。

![](img/1da2592808784ec8e7b94bc3bc33f72c_254.png)

假设你现在认出了一个quit。

![](img/1da2592808784ec8e7b94bc3bc33f72c_256.png)

就根据这些训练资料，其实你也可以去认一个critic嘛。

![](img/1da2592808784ec8e7b94bc3bc33f72c_258.png)

等下认出这个critic以后，这个critic给他一个state，它就会产生一个分数。

![](img/1da2592808784ec8e7b94bc3bc33f72c_260.png)

那你把这个分数啊当做B啊。

![](img/1da2592808784ec8e7b94bc3bc33f72c_262.png)

你把这个分数当做B，所以g one pine就是要减掉v o c a one。

![](img/1da2592808784ec8e7b94bc3bc33f72c_264.png)

G2 point就是减掉v o c a two，以此类推好。

![](img/1da2592808784ec8e7b94bc3bc33f72c_266.png)

那再来的问题就是，为什么减掉V是一个合理的选择。

![](img/1da2592808784ec8e7b94bc3bc33f72c_268.png)

那我们在下一页投影片来跟大家解释一下好，那现在呢我们已经知道说这个呃SA这个pair，它有多好呢，这个AT代表它有多好呢，我们是用g pan减掉VFST来定义这个A好。

那我们先来看一下这个view of s st，到底代表什么意思，v of s t代表什么意思呢，v of s t是看到某一个画面s st以后，接下来会得到的reward，那它其实是一个期望值。

因为假设你今天看到同一个画面，接下来再继续玩游戏，游戏有随机性，你每次得到的reward都不太一样的话，那view f s st呢其实是一个期望值好，那在这个时候啊，在看到s st的时候啊。

你的actor不一定会执行AT这一个action。

![](img/1da2592808784ec8e7b94bc3bc33f72c_270.png)

A说为什么呢，为什么它不一定执行AT这个action呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_272.png)

不要忘了actor本身是有随机性的，在训练的过程中，我们甚至鼓励actor是有随机性的，所以同样的S你的actor呢，它会输出的这个action不一定是一样的。

我们说actor的输出其实是一个probability distribution。

![](img/1da2592808784ec8e7b94bc3bc33f72c_274.png)

是一个在这个action的space上面的probability distribution，它会给每一个action一个分数，你按照这个分数去做sample，有些action被sample到的几率高。

有些action被sample到的几率低。

![](img/1da2592808784ec8e7b94bc3bc33f72c_276.png)

但每一次sample出来的action，并不保证一定要是一样的哦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_278.png)

所以看到ST之后，接下来有很多的可能。

![](img/1da2592808784ec8e7b94bc3bc33f72c_280.png)

很多的可能，所以你会算出不同的呃，TRIUMULATED的reward好，那当然如果你有discount的话，就是discounted tuulated reward。



![](img/1da2592808784ec8e7b94bc3bc33f72c_282.png)

那我们这边呢是把discount这件事情，暂时省略掉。

![](img/1da2592808784ec8e7b94bc3bc33f72c_284.png)

嗯好反正大家知道我的意思，我这边没有教，我这边没有加play啦，不过大家知道没有加上标pl，不过大家知道我的意思就好好，那把这些可能的结果平均起来就是v of s t。

这是v of s t这一项的含义好，那GTP这一项的含义是什么呢，gt play这一项的含义是在s st这个位置。



![](img/1da2592808784ec8e7b94bc3bc33f72c_286.png)

在s st这个画面下执行a at以后，接下来会得到的cumulated reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_288.png)

就你执行at以后，接下来呢再一路玩下去，你会得到一个结果，得到一个reward，就是gt pl，那如果今天AT大于零是什么意思，如果AT大于零，代表说gt plan大于VWFST，这个时候代表说呢。



![](img/1da2592808784ec8e7b94bc3bc33f72c_290.png)

这个action是比我们random sample到的action还要好的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_292.png)

在这边得到gt play的时候，我们确定是执行了AT。

![](img/1da2592808784ec8e7b94bc3bc33f72c_294.png)

那在ST在算这个v of s t的时候，我们不确定我们会执行哪一个action哦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_296.png)

所以我们执行action at的时候，得到的reward大于随便执行一个action得到的reward哦。



![](img/1da2592808784ec8e7b94bc3bc33f72c_298.png)

![](img/1da2592808784ec8e7b94bc3bc33f72c_299.png)

所以当AT大于零的时候，代表说AT大于随便执行的一个action，那这个时候这个action at它就是好的，所以我们给它一个大于零的a at，反之，如果a at小于零，什么意思，AT小于零。

代表说这个平均的reward，大过执行AT得到的reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_301.png)

你随机采取的action，按照某一个distribution sample出来的action。

![](img/1da2592808784ec8e7b94bc3bc33f72c_303.png)

得到的这个trumulated reward的期望值，大过采取at这个action所得到的reward。



![](img/1da2592808784ec8e7b94bc3bc33f72c_305.png)

那这个时候a at就是坏的。

![](img/1da2592808784ec8e7b94bc3bc33f72c_307.png)

所以要给他负的大AT，所以这样就非常的直觉，为什么我们应该把gt pline减掉VOFST。

![](img/1da2592808784ec8e7b94bc3bc33f72c_309.png)

但讲到这边，你有没有觉得有一些地方有点违和呢，什么地方有点违和呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_311.png)

嘶这个GP它是一个sample的结果。

![](img/1da2592808784ec8e7b94bc3bc33f72c_313.png)

他是执行at以后一直玩玩玩，玩到游戏结束某一个sample出来的结果，而view of s st是很多条路径，很多个可能性平均以后的结果，我们把一个sample去减掉平均，这样会准吗。



![](img/1da2592808784ec8e7b94bc3bc33f72c_315.png)

也许这个sample特别好或特别坏呀，我们为什么不是拿平均去减掉平均呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_317.png)

所以我们这门课要讲的最后一个版本。

![](img/1da2592808784ec8e7b94bc3bc33f72c_319.png)

就是拿平均去减掉平均，也就是说我们执行完a at以后得到reward RT。

![](img/1da2592808784ec8e7b94bc3bc33f72c_321.png)

然后跑到下一个画面ST加一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_323.png)

把这个s st加一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_325.png)

接下来一直玩下去，有很多不同的可能，每个可能通通会得到一个reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_327.png)

把这些reward平均起来，把这些accumulated的reward平均起来是多少呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_329.png)

其实就是v of s t加一，本来你会需要玩很多场游戏，才能够得到这个平均值，但没关系，假设你训练出一个好的quit。



![](img/1da2592808784ec8e7b94bc3bc33f72c_331.png)

那你直接带v of s t加一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_333.png)

那你就得到是你直接得到，你直接带v of s t加一，你就知道说在ST加一这个画面下。

![](img/1da2592808784ec8e7b94bc3bc33f72c_335.png)

接下来会得到的trumulative reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_337.png)

的期望值应该多少好，接下来呢你再加上RT啊，接下来再加上RT代表说在ST这个位置，采取AT跳到ST加一以后。



![](img/1da2592808784ec8e7b94bc3bc33f72c_339.png)

会得到的reward的期望值，因为我们知道说在ST这边采取AT。

![](img/1da2592808784ec8e7b94bc3bc33f72c_341.png)

会得到reward RT再跳到ST加一，然后ST加一会得到期望值，期望的reward是view of s t加一，所以我们这边呢再给它加上RT。



![](img/1da2592808784ec8e7b94bc3bc33f72c_343.png)

代表说在ST这边执行AT以后，会得到的reward的期望值。

![](img/1da2592808784ec8e7b94bc3bc33f72c_345.png)

接下来再把这两个东西相减哦，再把RT v of s t加一减掉v of s t。

![](img/1da2592808784ec8e7b94bc3bc33f72c_347.png)

也就我们把GP换成RT加v of s t加一。

![](img/1da2592808784ec8e7b94bc3bc33f72c_349.png)

再减掉v of s t，我们就知道说呃采取AT这个reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_351.png)

他哦不是不是reward a t不是reward还是action。

![](img/1da2592808784ec8e7b94bc3bc33f72c_353.png)

采取AT这个action接下来得到的期望。

![](img/1da2592808784ec8e7b94bc3bc33f72c_355.png)

reward减掉，不采取AT，而是随便sample一个action，根据某个distribution sample。



![](img/1da2592808784ec8e7b94bc3bc33f72c_357.png)

一个action会得到的reward，两者的期望值差距有多大。

![](img/1da2592808784ec8e7b94bc3bc33f72c_359.png)

那如果RT加v of s t比较大，就代表AT比较好。

![](img/1da2592808784ec8e7b94bc3bc33f72c_361.png)

它比随便sample reward好，RT加v of s t小于v of s t，就代表AT它是lower than average。

它比从一个distribution sample到的action还要差。

![](img/1da2592808784ec8e7b94bc3bc33f72c_363.png)

所以呃，今天呢这个就是大名鼎鼎的一个常用的方法。

![](img/1da2592808784ec8e7b94bc3bc33f72c_365.png)

叫做advantage的ACTIQUITY。

![](img/1da2592808784ec8e7b94bc3bc33f72c_367.png)

好在advantage的ACTIQUITY里面，你是怎么定义AT的呢，你就是RT加VFST减掉呃，呃RT加v of s t。



![](img/1da2592808784ec8e7b94bc3bc33f72c_369.png)

加一减掉v of FST就是我们的AT了。

![](img/1da2592808784ec8e7b94bc3bc33f72c_371.png)

好那这边呢有一个训练ACCRITIC的小技巧啦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_373.png)

那你在作业里面也不妨使用这个技巧，这个技巧是什么呢，actor是一个network critic，也是一个network actor，这个network是一个游戏画面，当做输入。



![](img/1da2592808784ec8e7b94bc3bc33f72c_375.png)

它的输出是每一个action的分数，quit是一个游戏画面。

![](img/1da2592808784ec8e7b94bc3bc33f72c_377.png)

当做输入，输出是一个数值，代表接下来会得到的accumulated的reward。

![](img/1da2592808784ec8e7b94bc3bc33f72c_379.png)

这边有两个network，它们的输入是一样的东西，所以这两个network，他们应该有部分的参数可以共用吧。



![](img/1da2592808784ec8e7b94bc3bc33f72c_381.png)

尤其假设你的输入又是一个非常复杂的东西，比如说游戏画面的时候，前面几层应该都需要是CNN吧。

![](img/1da2592808784ec8e7b94bc3bc33f72c_383.png)

要了解这个游戏画面需要用的CNN，也许是差不多的吧。

![](img/1da2592808784ec8e7b94bc3bc33f72c_385.png)

所以actor跟critic，他们可以共用前面几个layer哦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_387.png)

所以你今天在实做的时候，往往呢，你会把你的ACTIQUITY设计成这个样子哦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_389.png)

ACTIQUITY呢他们有共用多大部分的network。

![](img/1da2592808784ec8e7b94bc3bc33f72c_391.png)

然后只是最后呢呃输出不同的action就是actor。

![](img/1da2592808784ec8e7b94bc3bc33f72c_393.png)

输出一个SCALA就是critic啊，那这是一个训练act critic的小技巧。

![](img/1da2592808784ec8e7b94bc3bc33f72c_395.png)

好那额其实今天讲的并不是reinforcement learning的全部。

![](img/1da2592808784ec8e7b94bc3bc33f72c_397.png)

那其实re在reinforcement learning里面。

![](img/1da2592808784ec8e7b94bc3bc33f72c_399.png)

还有一个系列的做法，是直接采取critic，也就是直接用CRITI就可以决定要用什么样的action，那其中最知名的就是deep q network d q n。



![](img/1da2592808784ec8e7b94bc3bc33f72c_401.png)

那不过呢这边我们就不细讲DQN了。

![](img/1da2592808784ec8e7b94bc3bc33f72c_403.png)

如果你真的想知道DQN的话，可以参考过去上课的录影，那DQN哇有非常非常多的变形，这边呢就是找一个非常有一篇非常知名的paper。



![](img/1da2592808784ec8e7b94bc3bc33f72c_405.png)

叫做rainbow哦，里面呢就是试着去尝试了各种DQN的变形。

![](img/1da2592808784ec8e7b94bc3bc33f72c_407.png)

试了七种，然后再把这七种变形集合起来。

![](img/1da2592808784ec8e7b94bc3bc33f72c_409.png)

又有七种变形集合起来，所以他说它是一个彩虹哦，所以它把它的方法叫做rainbow。

![](img/1da2592808784ec8e7b94bc3bc33f72c_411.png)

那我也把这个paper留在这边给你参考。

![](img/1da2592808784ec8e7b94bc3bc33f72c_413.png)

那如果你想知道rainbow里面的每一个小技巧，是怎么做的话，你就参见上课录影，过去的课程，有把rainbow里面的每一个小技巧都讲过一遍好。



![](img/1da2592808784ec8e7b94bc3bc33f72c_415.png)

那讲到这边呢，正好告一个段落，我们现在看看有没有同学有问题。

![](img/1da2592808784ec8e7b94bc3bc33f72c_417.png)

![](img/1da2592808784ec8e7b94bc3bc33f72c_418.png)

好那个呃，我来回答一下同学们的问题。

![](img/1da2592808784ec8e7b94bc3bc33f72c_420.png)

这样怎么办，这是一个很好的问题。

![](img/1da2592808784ec8e7b94bc3bc33f72c_422.png)

SA后面不一定接SB，那这个问题在刚才我们看到的那个例子里面，就没有办法处理，因为在刚才那个我们看到那个只有八个episode，的例子里面，SA后面就只会接SB。



![](img/1da2592808784ec8e7b94bc3bc33f72c_424.png)

所以我们观察没有观察到其他的可能性。

![](img/1da2592808784ec8e7b94bc3bc33f72c_426.png)

所以没办法处理这个问题，所以这就告诉我们说啊，在做reinforcement learning的时候。



![](img/1da2592808784ec8e7b94bc3bc33f72c_428.png)

simple这件事情是非常重要的，你reinforcement learning最后认的好不好。

![](img/1da2592808784ec8e7b94bc3bc33f72c_430.png)

跟你在simple的时候simple的好不好关系非常大哦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_432.png)

所以这个哈，reinforcement learning是一个非常吃人品的方法了。

![](img/1da2592808784ec8e7b94bc3bc33f72c_434.png)

所以在作业里面你可以这个体验一下，就你sample到的结果，对你最后training的结果有非常大的影响啊。



![](img/1da2592808784ec8e7b94bc3bc33f72c_436.png)

然后下一个问题，所以每一个V都需要对应到顾定的环境。

![](img/1da2592808784ec8e7b94bc3bc33f72c_438.png)

![](img/1da2592808784ec8e7b94bc3bc33f72c_439.png)

发生顺序吗。

![](img/1da2592808784ec8e7b94bc3bc33f72c_441.png)

哎我先说一下那个王大华同学其实是助教啦，那这不是他的本名啦，那是但但这个王大华同学是助教还是助教。

![](img/1da2592808784ec8e7b94bc3bc33f72c_443.png)

然后。

![](img/1da2592808784ec8e7b94bc3bc33f72c_445.png)

诶我看一下哦。

![](img/1da2592808784ec8e7b94bc3bc33f72c_447.png)

所以V每一个V都需对应到固定的环境。

![](img/1da2592808784ec8e7b94bc3bc33f72c_449.png)

发生顺序吗，我没有很确定你的问题。

![](img/1da2592808784ec8e7b94bc3bc33f72c_451.png)

但是我试着回答一下，就是呃每一个V它不会固定。

![](img/1da2592808784ec8e7b94bc3bc33f72c_453.png)

它不会对应到固定的环境发生顺序，也就是V啊，如果你的游戏有随机性的话，那V其实是代表了一个期望值，他想要算的就是给某一个observation。



![](img/1da2592808784ec8e7b94bc3bc33f72c_455.png)

看到某一个游游戏画面以后，接下来你会得到的communulative reward平均值。

![](img/1da2592808784ec8e7b94bc3bc33f72c_457.png)

他的期望值就如果你的游戏有随机性的话，V代表的是期望值，你看到某个游戏画面以后，接下来会发生什么事情，不见得是一样的，但把所有的可能性都平均起来，取他的期望值。



![](img/1da2592808784ec8e7b94bc3bc33f72c_459.png)

这个就是V所代表的意思。

![](img/1da2592808784ec8e7b94bc3bc33f72c_461.png)

后面出现的S应该是不固定的，这样怎么带公式。

![](img/1da2592808784ec8e7b94bc3bc33f72c_463.png)

好那个我想我刚才应该算是有回答到的，后面出现的，看到某一个这个observation后面出现后，后面出现的observation确实是不固定的。



![](img/1da2592808784ec8e7b94bc3bc33f72c_465.png)

那如果有些状况，某些observation你没观察到的话，哇，那你真的就没办法训练。

![](img/1da2592808784ec8e7b94bc3bc33f72c_467.png)

哦V当一，然后有同学问说，就是拿V当一般人的实力超过他就是猛，没超过就是烂吗，对就是这样哎V就是平均的实力超过V就是好。



![](img/1da2592808784ec8e7b94bc3bc33f72c_469.png)

哎，想请问这个distribution要从哪里知道呢。

![](img/1da2592808784ec8e7b94bc3bc33f72c_471.png)

我知我我想你这个distribution问的是那个actor的distribution了，对不对，我们说distribution action的distribution呃。

action是从某一个distribution sample出来的，而那个distribution是谁呢，那个distribution是这样，就是你的actor不是像是一个classifier吗。



![](img/1da2592808784ec8e7b94bc3bc33f72c_473.png)

你的actor像是一个classifier。

![](img/1da2592808784ec8e7b94bc3bc33f72c_475.png)

然后你把S丢进去，每一个state，而不是每个state，每一个action都会有一个分数。

![](img/1da2592808784ec8e7b94bc3bc33f72c_477.png)

得把这个分数呢通过soft max就做一个normalize，它就变得像几率一样。

![](img/1da2592808784ec8e7b94bc3bc33f72c_479.png)

然后按照那个几率去做sample，那这个就是actor从个distribution sample出来的。



![](img/1da2592808784ec8e7b94bc3bc33f72c_481.png)