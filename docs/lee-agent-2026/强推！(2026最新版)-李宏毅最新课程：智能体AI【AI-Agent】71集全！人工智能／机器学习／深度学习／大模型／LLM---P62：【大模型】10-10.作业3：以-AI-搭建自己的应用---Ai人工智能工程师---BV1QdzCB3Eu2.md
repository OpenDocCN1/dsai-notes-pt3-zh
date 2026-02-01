# 强推！(2026最新版) 李宏毅最新课程：智能体AI【AI Agent】71集全！人工智能／机器学习／深度学习／大模型／LLM - P62：【大模型】10-10.作业3：以 AI 搭建自己的应用 - Ai人工智能工程师 - BV1QdzCB3Eu2

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_0.png)

因为这次作业要涨超级无敌久，所以我们事不宜迟，马上开始吧，好那大家好，我是周越山的助教刘展宏，我们作业参赛题目是以AAPI，快速搭建自己的应用，那首先呢我们先来介绍一下什么是API。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_2.png)

那大家想必在作业二的时候，都有使用过网页版雀gt，那网页版雀，具体的话基本上就是你们把input写在这边，然后就送给雀GPT，然后就把response还给你，显示在网页上就这么简单，那假如说今天好了。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_4.png)

我们想要使用雀菊题来做个应用程式，那他感觉会怎样呢，举例来说，我们想要做一个EMOJA的app，它的功能就是我给他一段input，然后他丢给穴居说他就还给他嗯，加了一大堆emoji的版本。

OK那大家如果是用网页版的时候会怎么做呢，那可能就是这样子，我会写一段prop，他这个pump要跟他说，OK你要在这个文章里面加上一大堆的啊，有个emoji，OK好。

那下面就附上我们使用者想要给的那个文章，那OK那shift d就会把他的output还给你，然后就在这边看到也就很简单，但是呢我们今天想象一件事情哦，如果今天不止我要使用这个app，还有你的朋友啊。

还有你的同学，还有一大堆人都要使用这个app，那如果你还用网页版的话，会长怎样呢，那基本上就会变成说你必须要把他们的input，一个一个的复制到雀居的网页版里面。

然后拿到他output之后再还给你的朋友们，那这件事情会非常的麻烦，所以为了解决这件事情呢，我们可以使用这个东西叫做AAPI，那API全名是education program interface。

那基本上我会把它想象成就是，它是一个可以使用程式的方式来call che，具体的方法它的整个流程会长这样子，有没有看到这个地方装的，基本上就是我要拿来call chgt使用的程序。

那里面会装说我们要使用哪一个model，然后里面会装说我们有怎样的prop，然后里面会装说我们有怎样的文章在里面，然后这个东西送给CHHD之后，他会把response还给你。

那你就可以用城市的方式去拿到那个response，那这么做有个好处，就是假如说你这个app，有很多人都想要使用的时候，那你就可以叫他们自己把这个input，送进这个城市里面，然后城市丢给穴居的时候。

他就可以把这个城the response直接还给你的user，那在整能boss中，你就不需要做任何事情，它也可以顺利的运作，OK所以我们这次作业想要大家学到的事情，就是使用CHEGTAPI。

来build1些非常简单的应用程序，所以我们预期大家会学到两件事情，第一件事情是如何去抠雀具体API啊，再来一件事，该怎么去设计一个合理的prop，来让CHEGT有办法做到你想要做的事情，好那再来。

因为这一次作业会需要大家扣API，所以会需要写一点点城市，那么城市的平台会使用这个google colab，那另一个的话，因为我们希望我们的app会有一个可视化界面。

所以我们这次会使用一个套件叫做GRADIO，那这两个东西我们等下就会介绍给大家，大家不用紧张好，所以这个是今天我们会做的事，第一件事情是我们会用一个demo来跟大家介绍，COLAB跟radio。

那第二件事的话，我会跟大家说这次作业有哪些API可以使用，还有该怎么拿到那些API的API kiss，那大家可以想象API key它实际上就是那个model，它的一种password感觉。

那第三件事的话就是我会教大家怎么用call类，跟GRADIO来build一个简单的应用程序。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_6.png)

好，那大家可能想说，哇塞我这辈子就没写过城市会不会很恐怖啊，我会不会写啊，那基本上是不用担心的，因为我们基本上已经把所有的cod，全部都写好了，大家只需要做一点点事情就可以了。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_8.png)

好那这是今天的online，我们第一个会先介绍就是COLLA跟GRADIO，Tutorial，那第二个的话是介绍有哪些API，那第三件事就是这次作业有哪些app，是大家真的要做的。

OK第四个的话就是我们这次的作业批改一样，会跟作业二使用达芬奇平台，那我们也会跑一遍，这个流程，告诉大家要怎么使用，那剩下的就是要怎么扫描到NTL扩，还有daylight，还有一些我们的规则之类的。

好那这里装的是这些作业会使用的一些links，我们就放在这边，那我们首先开始讲call in跟GRADIO，Ok，那co类是什么呢，实际上co类它就是google做的一个，可以在网页上写程序的一个平台。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_10.png)

那它有几个好处，第一个就是就算你是个完全的城市新手。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_12.png)

你也可以直接上去，然后直接使用，不需要做任何设定，那在第二件事情的话，他会给大家一点点的免费GPU可以使用，那我们这次作业是不会使用到GPU的，但是在之后作业可能会需要，那那个时候就炮三用场。

然后第三件事就是他可以非常简单的把你的call，share给你的朋友们，那相信大家用过google slide或是google duck，可能就知道在右上角左右有一个共用的选项。

那google code也有一模一样的东西，你可以选择你的code是要仅供编辑啊，或是可以减试用什么之类的。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_14.png)

那一样可以炫给你的朋友好，那再来什么是GRADIO呢，GRADIO我们其实可以想象说，它其实就是把你的城市给可视化一个东西，你可以把你的城市给搭成一个这种，大家看得懂的样子，那大家看到这个例子。

他实际上就是一个缺霸，那我们可以把input写下这边，然后送给他，他就给你讲话，那我们接下来会跑一个COLLA，跟GRADIO的tutorial。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_16.png)

那我会用这个link来做好，那我们接下来是开始我们的tutorial的部分。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_18.png)

那首先我们点进来这里之后，会看到这样一个界面，那大家第一件要做的事情，是按这个复制到云端硬碟。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_20.png)

因为目前这个扣它本身是仅供检视，所以大家在上面做任何更改都不会被存下来。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_22.png)

所以必须要先存一份自己的copy，在自己的云端硬碟里面，它才会存下来好，那再来第二件事，就是大家可以看到这边有个名字，那大家可以把这个扣的名字改成y y u one，那我就随便改一下就OK好。

那再来的话，非常重要的一件事情是要记得按这个连线，按这个连线之后，他才有办法执行你的code，那我们等下跑一下，OK好连线完之后长这样子，大家确定它长这样子之后才可以开始写你的code。

然后我们接下来要介绍的是col类里面，最重要的一个单元叫做sell，那大家把滑鼠移过来之前之后，会看到这有个叫城市嘛啊。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_24.png)

另一个叫文字的东西，那我先示范一下什么是文字哦，我们点一下。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_26.png)

OK那我们来打个字，OK那大家看到诶这就多出一个城市，那没有文字，OK那大家可以理解说这个cell号的目的，事实上就是让你在里面打一些文字，那你可以打说呃这段call在做什么啊。

或是告诉别人说呃要怎么使用，接下来call类似这种东西，那我们再看程式码是做什么用的呢，哦我们点击OK。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_28.png)

那哦哦，那我们OK我们在里面打一个非常简单的城市，OK好我们打完程序之后，大家记得按这个键来执行，OK按了之后就ping出hello，OK所以它要分成两种sell，第一种就是让你打文字的文字sell。

那另一种的话就是让你打城市的城市cell，Ok，那我们接下来介绍一下，COLAB要怎么上传跟下载答案，那我们点左边这边有个答案的部分好。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_30.png)

点进来按这个这就是上传，那我们可以上传一个呃随便的东西。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_32.png)

我们就好，我们就粘这个test txt，那我们可以按这个点两下，可以看到里面装什么内容，OK装个test没问题，那我们接下来就是要怎么下载这东西呢，我们就按这个点，然后按下载。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_34.png)

Ok，那这样子就可以把东西。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_36.png)

存在你的自己的电脑里面了，OK那第一次使用co类，人可能会不小心做的事情是按到这个东西，按进去之后，它就会变成这个样子，那大家就会找不到自己原本的东西在哪，那这个时候我们只要按这个content。

我们就找到原本的档案在哪里了啊，所以大家如果不小心按到的话，就记得按content，然后就知道自己原本的东西在哪好，那还需要另外说明一件事情是，大家如果把call类放在你的网页上，一段时间没动。

它就会自动断开连线，那断开连线代表两件事情，第一件事情是你刚跑过的扣，需要全部跑重跑一遍，在第二件事情是，你在这里记录的答案会全部不见，所以如果这边放着非常重要的，一定要记录下来，答案要记得在消失以前。

把它存到自己的电脑里面，不然你就再也碰不到他了，OK那我们接下来讲GRADIO的部分，首先要做的第一件事情是按这个install package。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_38.png)

那他需要跑一段时间，那没有看到说他正在跑的时候，这个run button会变成这个旋转的样子，代表说他正在执行这个COBT，然后还没结束，然后等它结束之后。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_40.png)

它会变成这个OK绿色勾勾代表说这个执行成功，然后没有出错，那再来我们按这个import cup。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_42.png)

哦OK好，那再按这个long your call。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_44.png)

按这个之后，radio会在你的col类里面开一个这样子的界面。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_46.png)

我们等他一下好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_48.png)

那这个实际上就是一个，你可以跟他互动一个界面，那除此之外呢，你也可以点这个link。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_50.png)

点过来之后，它就变成一个嗯比较大的。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_52.png)

比较好互动的一个状态，那我们这里就测试一下，我们就打一个哦，可ASSEND，I don't know，OK随便，那总而言之，这个界面就是你可以把你input，用send的方式告诉GRADIO。

然后GRADIO就会还给你一个回话，那可以按这个receive把这东西清掉。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_54.png)

OK那大家记得结束之后要把这个按掉。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_56.png)

那我们等下会解释这个是什么意思好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_58.png)

那我们回到投影片，那基本上这几页是我刚才做的事情的图文版。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_60.png)

所以我们这里就先跳过。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_62.png)

好，那这里的话我们跟大家稍微介绍一下，GRADI的原理到底是什么，那我们其实可以把GRADIO，想象成一个叠积木一样的东西，我们看到左边这里gradio tutorial，其实对应的就是右边这个界面的。

gradio tutorial的title，那这个缺霸界面呢，它对应的其实也是左边这个东西，所以我们其实就是在城市码的部分，像是叠积木一样把这个界面给叠起来，所以我们看到input对应这里input。

然后send有send reset reset，OK那我们他是怎么把这个东西送给城市嘛，然后再还给我们output呢，它实际上是这样子的感觉，首先呢我们按了send之后。

他会把这个东西丢到这段城市码里面，然后这个城市码的作用就是，它会决定说我们要还给怎样的output啊，等它决定好之后，他就把这个东西给丢给这个确爆，那我们就会看到OK他回了，You are right。

随便OK这样子的东西，那所以讲过这个时候大家其实可以想象说，GRADIO它的背后是靠着这个城市嘛来支撑着，所以当这个城市嘛结束的时候，这GRADIO界面也就没有办法再使用了。

好OK那code跟GRADIO部分我们到此为止。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_64.png)

我们接下来讲这支座有哪些可以使用的API。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_66.png)

那这次可以使用有两个，第一个叫做google Gemini的API，然后另一个则是CHAGPAPI，那大家只需要使用其中一种就好，那之所以会提供两种的最大原因，其实是google jami。

它的API是完全免费的，到目前为止，然后CHEGT的API他要钱，那大家可能想说，我们在网页版扣CHEGG的时候，不是完全不用钱吗，那这个其实是因为API，它的收费标准跟网页版那个是不一样的。

那API还要钱啊，但是确gt API它有可能是免费的。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_68.png)

那关于这一点，我们等下会说明好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_70.png)

那我们首先讲的是该怎么取得google Gemini API，那首先大家要做的事情是按进这个网页好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_72.png)

那我们示范一遍，没给大家看。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_74.png)

那大家进来之后会看到这样一个界面，那我们按这个gay GAM i API key。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_76.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_77.png)

好，那我们就把这些使用调整全部都勾一勾，1K continue好，那接下来要做的事情是按这个get API ke好。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_79.png)

那出来这个界面之后，按这个create a API ke好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_81.png)

我们按这个create API kein new project。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_83.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_84.png)

好久，OK好那跑出来这个就是你的API key，那大家记得把这个东西存到一个你可以信任，然后不会给别人看到的地方，那大家千万要记得是这些APIKE，你不可以share给除了你以外的任何人，知道，这个是。

因为这这个东西，它基本上就代表着你去使用那个模型的权限，而当你把这APIP给别人之后，别人也等于获得了他使用你的账号，去使用那个模型的权限，那最糟的情况下，就是别人拿你的APIP去乱搞一通。

然后让你账号出事，所以大家记得这东西不要泄给别人，OK那我们按了copy之后。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_86.png)

我们可以把它存到某个地方去，那当大家如果不小心没有存号。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_88.png)

像我刚才那样，我我没有存起来的话，那大家其实可以说按键来这里。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_90.png)

这回再出现一次，所以大家不用紧张，不用再新开一个，我们直接从这里再copy一次就好好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_92.png)

那这个是GEMINI的部分。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_94.png)

OK那我们就一样继续。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_96.png)

那值得注意的是，大家可能会遇到一个我们不知道原因的bug，就他跟你说，你没有那个permission去产生API，那如果遇到这个事情的话，我们就变成按这个create API。

Key in existing project。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_98.png)

然后按了之后它就会出现这样一个界面，我们就按这个第一个选项，Jnative language client，然后按之后一样按create new API t，这样就跟后面一样。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_100.png)

好那我们接下来讲的是该怎么拿到CHEGT的API。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_102.png)

和大家一样，点进这个open i打com。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_104.png)

好，那大家点进来之后，应该会看到这样子的一个界面，我们首先按login，Ok，那这里有两个，一个叫CHECH，一个叫API，那大家在做这个时候，应该都有点过左边这个选项。

那我们这次要点是右边这个API好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_106.png)

那因为我已经登录好了，那大家可能要登录一下，那我们首先要做的就是按这个左边这一栏的API。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_108.png)

keys好，那按进来之后，我们按这个create new secret key好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_110.png)

他要你打个名字，那我们就随便打一个，我们打一个，我就打个窝嘞，我们打个红work3好，然后就按。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_112.png)

虽然create，好那这个跑出来就是你的APIT，那跟刚才一样，不要把这东西献给除了你以外的任何人，不然你会出事。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_114.png)

OK好，那按copy之后，我们把它存在我们自己的档案里面，那我们等下会使用。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_116.png)

好OK那跟GEMINI不一样，是一旦你按了这个down。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_118.png)

OK你就再也没有办法看到这些API key完整的样子，所以大家在记得使用CHEGPAPI时候，要在第一次的时候就把copy存下来。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_120.png)

不然你就再也见不到他了，那当发生这种情况的时候，你就只能再新开一个。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_122.png)

OK那我们刚才有讲过CHEGDAPI要钱，但可能是免费的，这是为什么呢，我们点进左边这个usage这一栏。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_124.png)

我们会看到这边有写一个five dollar limit，它指的是你有个五美元的免费额度可以使用，这个实际上是因为当你新开一个open i的账号，他会给你一个五美元的limit。

让你去免费的体验它的API，但是这东西会过期，所以说如果大家的open i账号是在这次课堂以前，应该说这堂课以前就串好的话，那你有可能已经过期了，你就没有办法使用。

那如果你是在这堂课之后才创了这个账号的话，那你应该还会有这个免费的权限，那你就可以使用雀居API来免费的做这次作业好。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_126.png)

OK那我们就讲到这里为止。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_128.png)

那值得注意的是说，如果你是第一次点进这个API kiss的部分的话，应该会看到这个叫你认证你的电话号码部分，那你就照他指示一步步认证就好，OK那我们接下来要讲到这次作业，真正希望大家做的事情了，好。

那这是这次作业的work pro，首先呢我们要使用call类的方式去call API，来达成一些任务，那大家可以选择是要用雀居的API还是用GEMINI，那再来我们把任务达成之后。

我们会丢到达芬奇的平台去打分，就跟homo二一样，那我们之后再把打分出来的东西，丢到until库里面，撒密给我们这样子，那我们会等下会把整个流程全部demo过一遍。

那所以这次作业希望大家做的事情是使用call API，还有想一个合理的碰的方式去build的一个language model application，然后我们希望大家做test总共有三个。

第一个是SUIZATION占三分，第二则是role playing占三分，第三个是coser test占四分，那我们这次功课会使用底下这个link。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_130.png)

OK那我现在介绍一下第一个test summarization。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_132.png)

那什么筛选这东西，它实际上就是OK当你今天有一个很长的文章，你懒得自己看，你希望有人先帮你sunrise之后，你直接看他整理好的版本，这样就好，那我们需要他做的就是linkage model。

拿到一篇文章之后，他可以把它帮我们同整好，所以希望大家做的事情是想一个prompt，让language model有办法帮我们SUMMAR1篇文章。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_134.png)

那我先想象一下，如果我们使用网页版确gt的时候，他会怎么做这件事呢，OK我会先想一个prop，那这个pp就是非常article for me，OK没问题，那我们接下来就把article贴在下面。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_136.png)

然后这样子好了之后，我们按sin之后，shift gt就会把SUMMARIZATION结果放在这边好，那网页版雀gt跟API版雀gt有什么差别呢。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_138.png)

我们接下来看左边，这是网页版雀gt，然后右边就是我们要写在城市码里面的，API版的7GBT，大家也看到说他们其实还是一一对应的，这边这个PRT，其实就对应到右边这个这边的PRT。

然后左边article对应到其实就是右边这个article，那当他们把这两个组合起来之后，他就会丢到这个东西，那这块城市码呢，它其实就跟这个键是同样的功能，我们借由这个城市码的方式。

把我们的input丢给CHEGT，然后他再把response还给我们，就跟这个键做的事情是一模一样的。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_140.png)

所以说当他给嗯，结果还给我们之后，我们就看到说ok response，对应的其实就是这边的SUMMARIZATION。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_142.png)

OK好，那在我们要讲解说大家进到我们作业call类之后，会需要做的事情，首先大家第一件事要是要做，就是选一个自己要用的API，事实上我自己推荐，如果你有免费的额度的话，使用雀居API比较好。

那是因为GAMAPI它嗯比较慢，比较烂，所以嗯对，所以所以推荐大家使用雀居的API，然后我们接下来的demonstration，那接下来是在都会使用雀居gt API的版本好。

那大家第一件事是选定了我们要用CHEGTAPI，然后按这个键把unfold好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_144.png)

那再来就是我们要按这个install package。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_146.png)

然后这东西跑完之后，我们要把自己的确认，具体API给fill到这东西里面，那好了之后，我们再按run，好我们刚刚讲过，如果你一段时间没碰call类，它就会自动断开这件事情，那当你断开重新连回来之后。

要记得这两个bug都要重新跑一遍。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_148.png)

不然你之后的code就会出错，好，那再来就是等下大家会看到这里有个part one，SUMIZATION的地方，那我们这里有把怎么做事的教学写在这边啊，总之下面有个code。

这边有写fin your prompt，那这边就是要大家把PROMPP给写进去的地方，那假如说我们就这里写很简单的啊，Please somewhere is eq for me，我们就把它填进这个里面。

那填好之后，我们就按这个run button。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_150.png)

好那它跟程式码的对应关系是什么呢，实际上就是我们把pp写在这边之后，他就会丢给确GBT，那他就会知道说，OK我们现在的任务是要做summarization task。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_152.png)

好在第三步就是大家成执行这个程序码之后，会看到这样子的一个radio界面出来，那这里会有一个叫做article，那大家可以在里面填进任何你想要哈，sunrise的文章。

那我们这里就直接使用default来示范。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_154.png)

那一样是城市马里面有个article，这东西他会丢给雀gt，然后跟他讲说。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_156.png)

OK我们要同整的文章是这个，好那在第四步，大家会看到这里有个东西叫做temperature，那大家可能不知道什么是temperature，那实际上就是，它是一个可以拿来操控模型的参数。

那它原则上是数字越大，你就可以让模型的output越有创造力，那数字越小，它你就可以让模型讲的话越严谨，OK那大家在作业的时候可以自己玩，看这个东西会让它的模型的output有什么不一样，那总而言之。

接下来大家按send，按send之后。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_158.png)

你就可以在GRADIO的界面里面，看到你的response，所以就看到说OK这就是啊确实做的SUPRIZATION，那如果你觉得说这个看起来还不赖。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_160.png)

蛮不错的，那你就按这个export键一样是在radio界面下面，按这export键之后，他就会把你的对话记录给save成一个档案，那值得注意的是，如果你的档案还没有先存在你的自己的电脑。

然后你又再按一次export键的话，你旧的档案就会被新的给覆盖掉。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_162.png)

那说档案产生是什么意思呢，实际上就是我们刚才讲的那个答案，这边会出现一个东西叫part万达JASON，那大家如果觉得这东西是自己要的话，为了避免它消失，请记得要卸载到自己的本地的电脑。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_164.png)

好那接下来下面还有个区块叫做check and bring your result，那这一块实际上是说，因为大家它存下来那个档案里面，你可能看不懂它里面到底存的什么东西，所以这块城市嘛。

目的是我们会把那个档案还原成一个，GRADIO的缺bug界面，所以大家可以看出这里面装的是不是真的。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_166.png)

我想要的东西，那除此以外呢，还有一个区块叫做copy part to your grading system，那这一块实际上就是你把东西丢到grading system，打分用的。

那我们这部分我们等下再一起讲好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_168.png)

那我们接下来来跑一下demo one的呃，test one的demo。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_170.png)

哦OK那一样先按这个复制到云端硬碟。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_172.png)

OK好那大家进来之后会看到这样子的样子，所以我们刚才决定要确局DAAPI同学把这里点开。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_174.png)

OK那第一件事要做的就是按连线，不好意思，我忘了，好那我们稍微等他一下，好啊，按这个install。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_176.png)

那在它install期间，我们现在把我们的API key给填进去，大家记得填进去的时候，这个引号不可以拿掉，那我们示范一遍给大家看。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_178.png)

那我们就是这东西，OK然后。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_180.png)

好填进这个地方好，那填进来之后，它会长这个样子，那我们等他一下，好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_182.png)

OK好，那等他跑完之后，大家会看到这个set chegt API successfully，代表说你这API key没有问题，接下来可以使用，那当你的API key有一些问题的时候。

它就会跳出这个呃SERPING3d run with you a API key，那如果是出现这个时候，大家记得照着实在的上面的步骤，再重新拿一次你的APIKE。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_184.png)

OK那会看到这东西叫做part one summarization。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_186.png)

那这边有讲实际上要怎么做这个task，那我们直接先下来，这里有个东西叫做PROMPFORSUMMARIZATION，那这里就是刚才我们说的。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_188.png)

要把你的pr填进去的地方，那我们这里就直接用一个很简单的用这个。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_190.png)

哦OK复制贴上，那OK贴上好之后，我们就按这个执行。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_192.png)

那执行之后呢，嗯造九等那一下咳，好那我们一样使用这个额外界面来做示范。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_194.png)

因为它比较大一点。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_196.png)

好那大家看到这就是我们预设的文章，那大家可以把它换掉，没关系，我们这就直接使用这个，那temperature的话，大家也可以去尝试不同的temperature，那总之我们这边直接按S好。

按了send之后。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_198.png)

我们就在这边缺乏这边看到CGT，他做出来什么还接选，那如果我们说看了这个角色，OK哈，我写的还不错的，随便好了，那我们就直接按这个export。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_200.png)

按了export之后，我们就会在左边这边的答案里面。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_202.png)

看到一个帕万达JSON这东西出来，OK那大家记得要离开这个pk之前要先把它停掉，不然你之后的东西就会被它卡住。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_204.png)

好那我们接下来讲第二个test要做什么好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_206.png)

This is test，基本上就是我们希望可以跟CHEGT，来玩一个角色扮演游戏，那所以就是我们需要跟大家跟确比例说，需要他扮演什么角色啊，例如需要扮演一个海盗，那他就会全身心投入那个角色。

然后跟你玩一个游戏，这样子，OK那我们现在大家做的事情是想一个PROMPP，可以让language model可以变成你想要他扮演那个角色，然后等他变成那个角色之后，我们需要你可以跟他互动两轮。

那实际上就是等他变成海盗之后，你就跟他玩一个角色扮演游戏。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_208.png)

然后这样子持续两轮，那我们等下会示范一下，那我们一样来看一下他如果在网页版雀gt的话，它会怎样运作呢，实际上就是我们先给他一个pump，那这pk可能就是加扮演一个海盗。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_210.png)

OK按你送书之后，他就跟你说，OK我现在已经是个好棒的海盗。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_212.png)

我没看好，那接下来就是我们要再跟大家讲，新的一句话的话，这边我们旧的打的东西就会变成他的history，所以确距离就是看着你的新的input跟你的history。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_214.png)

然后再给你一个新的output。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_216.png)

那在这件事情上，API那边是怎么实现的呢，首先我们先看到就跟刚才一样，input对应的是这边input，OK那会把东西送给这个function之后，那一样按send他就会送出给CHEGT。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_218.png)

那再来的话是当我们有一个history的存在的时候，它实际上我们必须要手动的把那个history记录下来，就像这里这里user讲的这段话，那对应就是这边这个user讲这个，那确具体讲这段话。

对应就是这边这个assistant讲的，所以就是这个user的角色代表说是你讲的话，那assistant讲的这个角色就是确居对他讲的话。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_220.png)

那一样，我们新的input就会丢到这个input这边来，然后丢给这个function，然后拿到新的output，那因为我们刚才说当你使用API的时候，你必须要自己去记录你的history。

所以实际上这东西对应的只是新的output，那整个history对应的是这一块东西，所以这一块里面包含的是你全部的dialog，就跟这边这个是一样的好。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_222.png)

那大家要做的事情，就是在这个filin your character里面，放入你想要扮演角色，那这个PROFRAP里面放入你想要它。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_224.png)

你想要怎么碰它，让它变成那个角色，OK那我们先来示范一下。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_226.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_227.png)

我不是吗，好，那OK那首先我们把滑鼠滑到这个part two。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_229.png)

roll play的部分，那我们就看到这里的filin your cat and filin your prom，那我们这里就呃让他扮演一个海盗好，Ok，好那point的部分我们就用。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_231.png)

这个。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_233.png)

好都填好之后，我们就按执行。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_235.png)

好久好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_237.png)

OK好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_239.png)

那我们一样用这个link。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_241.png)

好进来之后我们看到这样一个界面，那我们看到说哦这边写的parry代表说，OK那现在秀吉去扮演是一个这个海盗角色，那我可以跟他互动一下，那好我来看看说什么了，我随便打哪个。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_243.png)

Hello，那我按SOK。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_245.png)

他就会回你一些话，那那时我们再随便打一下。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_247.png)

Ok，好那这样子就OK了。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_249.png)

那所以就是你在它变成海盗之后，你就跟他讲一句hello。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_251.png)

然后讲一句，OK那基本上这样就算是互动两轮，就是没有问题，那如果你觉得说这东西已经很满意的话。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_253.png)

你就按这个export。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_255.png)

那按了export之后，他一样会在这边出现一个part two打JSON的答案。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_257.png)

那我们一样把这个关掉好，OK那接下来我们讲的是text three cosmic task。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_259.png)

那TAE这句话，基本上就是我们希望大家自己想一个，想要确认一下做的事情，那基本上什么都可以，那你也可以说叫他帮忙解一些简单的数学问题，或者说帮他嗯，我每说一个词，他就要想一个这个词的反义词之类的。

然后随便都可以，那所以大家第一个要做的就是想一个prompt，来让确实有办法达成你要他做的事情，那为了我们批改也方便，基本就不要输入，会让雀居讲出太长的字的task，虽然我不知道怎么做到这件事。

但总还是别这么做，那再来第二件事就是enter那个test input，那这里举例的话就是我们需要它输入啊，输出这个词的反义词，那我们打个big，它就回个small，OK那大家想要做单轮或是多轮都可以。

但是为了我们批改方便。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_261.png)

请不要超过三轮，OK那我们一样来想想看，在网页版确局我会怎么做，OK那这个就是prop。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_263.png)

那这里的话就是我们的input，那按send之后。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_265.png)

它就还给我们这样子的感觉，那对应到API的话就一样，这个prompt对应到这边这个prop，那这个input的话会对应到这里，那我们一样按send的方式把它送出给CHEGT，就跟刚才是一模一样的。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_267.png)

OK那大家要做的事情是，首先feeling a text，这边要讲的是你希望模型他做什么事情，那封印的PRT，这边要做的就是你实际上要怎么pump，确gt的的转化。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_269.png)

把写在这边，那我们这里一样demo一下。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_271.png)

OK那好我们把滑鼠滑下来。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_273.png)

滑到这个customer test部分，然后到这里会看到这个fill in a test，And fill in a prompt，那我们这里就叫他做一个，非常非常非常非常非常非常简单的task。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_275.png)

叫做reff after me。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_277.png)

好啊。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_279.png)

好那还有一样是prop，那这个prop叫做，Please repeat the fine wi say。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_281.png)

OK都填好之后，按这个执行的button。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_283.png)

好按了之后们一样等他一下，总觉得特别久好OK那按这个键。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_285.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_286.png)

好那这边就会跟你讲说好，现在他能做的事情是repeat after me，那我们就来打一些字。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_288.png)

我们就像我们打一个large好了，我拿个large。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_290.png)

按send，他就回应个large，那我们打一串乱码啊。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_292.png)

这回给你一模一样乱码，那好强啊。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_294.png)

OK那我们觉得这东西看起来不错，我们框也写的不错，表现很好，那我们就按这个export。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_296.png)

那export之后一样会在这边出现一个passer JSON，Ok。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_298.png)

再的话就是这样，我们刚才已经把我们该做的事情都做好了。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_300.png)

那我们现在可以把我们API key给删掉，那我们来示范一下要怎么删API keys，首先呢在我们刚才看到API kiss那边，选项这边会有一排这个乐色桶，这个键按这个之后。

你就可以把你的API key给删掉，那你什么时候需要做这件事情，最大的原因就是你怀疑你的API keys，不知道，因为不明原因泄露给别人了，但一旦发生这种事情，就建议大家赶快把它删掉。

反正这个东西只要重创一个就好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_302.png)

那GEMINI的部分的话一样是在刚才get API key的部分，这会有个垃圾桶的选项，那一样，就是大家觉得这个key不在安全的时候，就记得把它给删了。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_304.png)

OK那再来的话是你在执行COLLAB的时候。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_306.png)

可能会遇到一些问题，那这些东西基本上是你可能没有啊，照着顺序执行啊，或者是你APIT有些问题，那我们就把这段留在这边。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_308.png)

大家有需要的话再来看，那我们这边先跳过。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_310.png)

好那比较值得注意的是，这边来他会因为不明原因挡掉一些prop，那像是这一句，Tell me how to stay healthy，那这句话他就非常容易触发这个bug，那解决这个问题的办法。

我们目前为止就只能改你的pump，也没有其他办法了，基本上这是我这应该是GEMINIAPI那边的问题。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_312.png)

好，那我们再示范一下。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_314.png)

我们该怎么在达芬奇平台上面改我们的功课，好，那我们这次的model使用的是GB t four，那assistant的名字叫做ji home worship assistant。

然后它里面会装着三个prompt，第一个是来做SUMMARIZATION的，这个是role play，这个是customer task，那你要把你在co类上的RESOCOPY，到达芬奇平台里面。

那我们等下示范一下该怎么做这个copy的步骤好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_316.png)

那我们就现在直接来看一下。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_318.png)

那咱们进平台长这样，大家应该使用过了，我们就直接进去，那大家要做的第一件事是按这个cheat。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_320.png)

然后按assistant，然后在里面找到我们home work3的批改助教，叫做jai home work3的SEON，然后大家点进来之后要按这个install，那我已经install好。

我们就不按再一次了。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_322.png)

好那再来就是我们按这个就按home work是有season，按之后它就会出现这三个surprization grader，rope grader跟customer test grader。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_324.png)

我们现在这个summarization grader，它就会出现两个空格让你填，一个是article，另一个是扫描ZATION，那我们要怎么获得这个东西呢。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_326.png)

就是我们回到刚才城市这里，那我们回到刚才part one summarization的部分。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_328.png)

OK我回到这里之后，我们往下拉。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_330.png)

看到这里有一个chicken pryour result，那我们先确定说，OK左边的答案栏里面有这个part万达JON了。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_332.png)

那我们再按执行。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_334.png)

好执行之后呢，他就会跑出一个跟刚才一样的GRADIO界面。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_336.png)

那你就可以趁这个机会看一下你刚才的结果，有没有顺利的被存下来，这个是不是你想要的那个答案，然后再就是把这个article给复制到批改系统里面，哦sorry我不小心看错了。

OK那实际上这个copy part to grading system，那这边会有一个复制的选项，我完全就按这个复制，然后我们就跑到这边来，然后按贴上。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_338.png)

然后这边下面会有一个SUIZATION这个选项，然后要按复制，OK那我们就一样贴上，那我们就按SAM，那就跟你说刚才那个东西几分，然后两分，OK代表说可能你的pump还不够强，你可能要再想一下。

要怎么让他的pp变更强，那满分是三分，OK那因为他是GB t four，所以他会需要跑一段时间，那我们可以小等它一下。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_340.png)

我嘞落落的奶奶，OK好他跑完了，那我们接下来看是啊，row pay规则的部分。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_342.png)

那么按这个还出现弱跟dialogue，那要做的事情一样。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_344.png)

我们先进到这个part two role play的部分。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_346.png)

然后按这个chicken print resolve部分，然后按执行。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_348.png)

好那这边呢大家唠。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_350.png)

基本上就是我们刚刚跟他互动出来的那个结果，那我们要往下拉。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_352.png)

拉到这个kobe party grading system，那我就把这个东西复制，然后到这里贴上。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_354.png)

那我们把这个大家让复制。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_356.png)

然后到这里贴上，OK然后按SAM，然后跟你说哦，两分，Ok，那看来是因为我刚才非常的敷衍，那个呃那个啊那个船长，OK那所以他只给我两分，那大家在实做的时候，就可以稍微认真的跟他对话一下。

搞不好就可以拿到三分了。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_358.png)

这样子好，那我们接下来看的是customer test的部分。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_360.png)

那我一样点，这里它就会出现这个DISCTION跟dialog，那我们要做的事情一样。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_362.png)

我们把这个停掉之后，来到pass的呃。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_364.png)

check and pryour result部分好，那我们就按执行。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_366.png)

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_367.png)

OK它就会出现这样子的GRADIO界面，那的确是我刚才那个没错。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_369.png)

那我们就把这个东西复制到那边，哦养杂了养父制。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_371.png)

好按SAM他给几分呢，啊三分啊没满分，那可能是test本身太简单了，那总而言之，这样子就可以拿到你的批改的结果，然后哦我们等他跑一下哦，我们等他跑的时候，我们注意一下左下角的东西。

我100percent，那大家可能已经知道，在作业二时候也有一样东西，那我的额度跟你们不太一样，那我们等下会介绍一下，改制作业的话，一天可以撒币几次，那再来，就是我们要把这东西给存到自己的电脑里面。

那我们就按这个呃，大会看到说。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_373.png)

这个是刚才那个SURIZATION的的评分的部分，我们就把这个按这个export键，那我们就可以在这边存，那大家党名帮我改成说这个你的学号，呃学号，然后加上，呃part one。

如果part one的话，就是part填part one，那part two就part two，OK然后这样子，然后再home work3。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_375.png)

然后按存档，OK那大家要撒密去n t code，要记得是要撒密，从达芬奇平台export这个JSON党，而不是刚才在这里出现的这三个part one，Part two，part three打JSON。

大家要千万记得不要上传错了。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_377.png)

OK那这部分到此为止，那这边的话就是我刚才做的解说，所以我们就先跳过。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_379.png)

好那大家要注意的是，因为三个test它用的是pd的长度不一样，所以它搭一天能更改次数也不太一样，那散RIZATION话，那ROPAY是十次左右，cos买只是15次左右，那大家记得这个意思指的是说。

如果你一天连续上传了五次扫描ZATION的话，你的额度就会被用完，那你上传14ROPAY的话，额度就被用完，所以他这里是or你就只能选个这个十次，然后用完的话就用完，你就等等隔天。

那当然这个东西是一个粗略的，估计，不一定说真的会这样子，那实际上他收你多少钱，还是取决于你的input和output的长度，那你可以靠着左下角这边去，确定你还剩下多少额度。

OK那再就是一个比较重要的事情，是请大家不要讲出，不要填入一些呃具有冒犯性或者会伤害人，或者有一些风险的pp，这是因为现在不管是雀gt还是GEMINI，就是google，他们都超级无敌。

怕他们的模型讲出一些会让他们被告的话，所以基本上就是只要它检测到你的prompt，有一点点的风险，它就把它挡掉，所以大家记得当一个超级级老好人，就讲一些老生常谈的好话，这样就可以了，防止他把你挡掉。

OK那这边的话是给旁听生用的，那我们会因为旁听生没有办SS，到我们的达芬奇平台，所以我们把我们批改作业用的prop写在这边，那大家只要点进去里面，然后把里面东西换掉。

然后再配上GB t four就可以用了，虽然gt four要钱啊，然后具体的用法就是里面会有这个双引号，包子的参数，大家把这个双引号，这整个东西换成里面对应的参数，这样就可以正常的批改。

那这个是房听声材料使用。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_381.png)

那有修这堂课的同学是不需要管这1part的好。

![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_383.png)

那在我们讲submission的部分，大家记得要交的JSON档，是你从达芬奇平台export那些，而不是在code里面出来，那些大家记得绝对不要搞错，然后export出来之后。

把它们改名叫做你的student id，然后part one哄我去打JSON，然后student id帮写小写，好那这也是几个注意事项，第一个就是不要把code交上来，因为我们不会看。

然后再就是大家记得在达芬奇平台里面出现，在output之后，要看里面有没有这东西，grade冒号three point或two point之类的，那我们是靠着这个东西，这这东西去判断你拿几分。

所以要记得确定一下里面有这个东西出现，那NTU库的话，你可以想撒咩几次就撒咩几次，来改，OK那我们这些作业不不允许持交，那如果你没有上传到正确的JSON档，或甚至你上传了其他总副档名档案。

像是TXT或者是一张图片之类的，那你还会拿零分，那就跟我反复强调一样，只能上传你从达芬奇平台export出来的JSON党，不要上传其他东西，那不要去更改你JS档里面的内容，因为我们有后台可以看。

那我们抓到的话算是作弊，OK那这次作业会在两周后，deadline就是3月21号的晚上，那成绩公布的话是在两周，而4月4号晚上之前公布成绩，那接下来是一些规定的部分，那当然抄袭是不被允许的。

那还有就是不要把你的prompt或是你的information的result，就你的JSON file给别人看，然后不要把你不是从达芬奇平台拿到的JSON file，上传到nt cor。

然后也不要尝试手动去更改你的里面的JSON范，那这些东西我们是抓得到的，所以大家不要做这件事情，那第一次违反以上规定的话，就是这次作业零分，那第二次违反以上规定的话，就是直接学成GF。

好那如果你有任何问题的话，请大家优先到我们n t call home work序的作业讨论区，那如果你真有一些比较隐私的问题的话，再寄信到这个NTUJAI2024的这个地方。

那因为这一次作业开始要写扣了，所以想必大家可能会在扣上遇到一些问题，那如果是要问城市出错的问题的话，请将城市出错的讯息连同它在哪里发生的，一起贴给我们，我们是要判断你出了什么问题。

OK那因为这是说要写扣，所以我们加开一个TAR2，在下周的01：30到2。20，我们一样会出现在这边，好那这一次周月三就到此为止，谢谢大家，那哎教问题吗，好看有没有头，这种问题要马上现在问一下的来啊。

这边来，我下次多一个，包括这个差嗯，我觉得这个差别的感，应该是感觉上只有奶差一点，但实际上会不会真的差很多呃，我觉得是还好，就是感觉伤害比较差，比较弱一点而已，那真正比较差应该是在罗配的部分rape。



![](img/a1bb5ffd6ec5b5cac29de2de3f3ddc32_385.png)

你们需要好好的创个JINA，他才不会吐出一下。