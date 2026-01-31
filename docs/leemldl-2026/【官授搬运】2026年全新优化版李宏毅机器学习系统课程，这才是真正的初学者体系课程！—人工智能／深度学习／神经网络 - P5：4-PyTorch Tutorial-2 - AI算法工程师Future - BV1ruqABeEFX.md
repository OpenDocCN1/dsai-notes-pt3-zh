# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P5：4-PyTorch Tutorial-2 - AI算法工程师Future - BV1ruqABeEFX

![](img/5b458ef48d4d386d8d41139b42da0d32_0.png)

那相信大家刚听完专员助教的对拍拓的介绍，对拍拓你都有一些基本的了解。

![](img/5b458ef48d4d386d8d41139b42da0d32_2.png)

那接下来我再举一个就是PYTORCH，实际上在应用的时候的例子。

![](img/5b458ef48d4d386d8d41139b42da0d32_4.png)

让大家知道就是可能在撰写PYTORCH的时候，那个流程单上会是什么样子好。

![](img/5b458ef48d4d386d8d41139b42da0d32_6.png)

那我们举这个例子就是homo one的题目，那我再简单的讲一下。

![](img/5b458ef48d4d386d8d41139b42da0d32_8.png)

就是他homo one做事情就是他给定5000呃。

![](img/5b458ef48d4d386d8d41139b42da0d32_10.png)

前5000的这个samarry song，然后要去预测第五天的new testing。

![](img/5b458ef48d4d386d8d41139b42da0d32_12.png)

Positicast，Percentage age，讲这一个regression的problem。

![](img/5b458ef48d4d386d8d41139b42da0d32_14.png)

那我等下下面投影片会出现的范例的cod，都是从homo one的code改写过来的。

![](img/5b458ef48d4d386d8d41139b42da0d32_16.png)

但是为了方便说明，所以会有一些简化，所以大家在做作业的时候。

![](img/5b458ef48d4d386d8d41139b42da0d32_18.png)

麻烦还是要以homo one的那个sample call为主，这样好。

![](img/5b458ef48d4d386d8d41139b42da0d32_20.png)

那我们在开始撰写那个machine learning的扣的时候。

![](img/5b458ef48d4d386d8d41139b42da0d32_22.png)

第一件还不错的，开始的事就是你可以先去检查。

![](img/5b458ef48d4d386d8d41139b42da0d32_24.png)

看看那个我们的data a是什么样子，那在从这个风work里面呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_26.png)

我们data a是储存在一个点csd file里面，那这个cs sp的每一个row呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_28.png)

它代表一笔的一台，那每个role总共有118个COLUMSP点。

![](img/5b458ef48d4d386d8d41139b42da0d32_30.png)

是就是在这笔data a118个features，那118feature的最后一个呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_32.png)

就是我们这里data a的label对。

![](img/5b458ef48d4d386d8d41139b42da0d32_34.png)

那知道这个data大致上会长什么样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_36.png)

之后，我们就开始可以开始想说要怎么把data a road进来。

![](img/5b458ef48d4d386d8d41139b42da0d32_38.png)

然后做一些简单的图processing这样子，那在这个case里面呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_40.png)

因为我们的贝塔是储存在一个点csd file里面的，所以这边就提供大家一个简单的方式。

![](img/5b458ef48d4d386d8d41139b42da0d32_42.png)

就用这个pandas点read csv就可以把它读进来，这样读进来会是一个浪拍的。

![](img/5b458ef48d4d386d8d41139b42da0d32_44.png)

而不然后接下来读下来之后，可能可以做一些简单的PREPROCESSING呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_46.png)

我这边就是卷一个最最最简单的例子，就是就是其实就是把它把读进来的东西。

![](img/5b458ef48d4d386d8d41139b42da0d32_48.png)

分成model input跟labels，把它分出来这样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_50.png)

那分开之后这个action就是我们models的input，YCHA就是我们的labels。

![](img/5b458ef48d4d386d8d41139b42da0d32_52.png)

这样，然后action它的shape是2699乘于一七。

![](img/5b458ef48d4d386d8d41139b42da0d32_54.png)

然后y chain我们的label，它的shift是2699，这代表就是我们总共有2699比chining data。



![](img/5b458ef48d4d386d8d41139b42da0d32_56.png)

然后117。

![](img/5b458ef48d4d386d8d41139b42da0d32_58.png)

每一笔data总共有117个feature，这样然后这边还要再提醒大家。

![](img/5b458ef48d4d386d8d41139b42da0d32_60.png)

就是如果说我们作业里面没有提供，百lization set的话。

![](img/5b458ef48d4d386d8d41139b42da0d32_62.png)

其实大部分时候我们是要自己去把雷addation set，切出来，但我们这边一样是为了方便说明。

![](img/5b458ef48d4d386d8d41139b42da0d32_64.png)

所以就没有切realization set，但大家如果想要知道。

![](img/5b458ef48d4d386d8d41139b42da0d32_66.png)

本来就像这段实际上要怎么切的话，可以去参考homo one的sample code。

![](img/5b458ef48d4d386d8d41139b42da0d32_68.png)

这样子，OK那切完data之后，就像刚我们前面有讲到。

![](img/5b458ef48d4d386d8d41139b42da0d32_70.png)

接下来可以宣宣告一个就是data set这个东西一样。

![](img/5b458ef48d4d386d8d41139b42da0d32_72.png)

是要我们要写三个方式，Init get item，还有NINIT里面呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_74.png)

你可以去读你的data，或者是你也可以在里面做一些pre process。

![](img/5b458ef48d4d386d8d41139b42da0d32_76.png)

像前一页讲的那个PREPROCESS，其实你也可以在这个INIT这个方式里面去做。

![](img/5b458ef48d4d386d8d41139b42da0d32_78.png)

处理，也是没有问题的，那GAITOR呢就是也像前面讲。

![](img/5b458ef48d4d386d8d41139b42da0d32_80.png)

就是你给他一个index，然后get item这个方选，他要负责回传对应到这个index的内比贝塔。

![](img/5b458ef48d4d386d8d41139b42da0d32_82.png)

那在这个text里面呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_84.png)

我们要回传的东西，就是一个117维的feature。

![](img/5b458ef48d4d386d8d41139b42da0d32_86.png)

然后以及它对应的label，然后这个length呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_88.png)

它回传的是我们整个data a set的长度，那在这个TT里面呢，就像我们刚刚前面有print出来的这个。



![](img/5b458ef48d4d386d8d41139b42da0d32_90.png)

所以他回传的只会是就是2699这样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_92.png)

那宣告完这个贝塔set之后呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_94.png)

就可以宣告也是刚刚前面有讲过的贝塔loader。

![](img/5b458ef48d4d386d8d41139b42da0d32_96.png)

然后一样嗯，比较重要参数这个bech side，还有SHAO。

![](img/5b458ef48d4d386d8d41139b42da0d32_98.png)

那贝赛就是每个BAGE它里面有贝塔的数量，然后shuffle刚刚前面有大概讲过。

![](img/5b458ef48d4d386d8d41139b42da0d32_100.png)

我们在training的时候会通常会把它设成true，那样项链就是附了一个链接。

![](img/5b458ef48d4d386d8d41139b42da0d32_102.png)

如果大家有兴趣知道，为什么我们在全年的时候需要shuffle，这一趟的话。

![](img/5b458ef48d4d386d8d41139b42da0d32_104.png)

可以参考看看，或是也可以参考彭毅老师去年上课的影片。

![](img/5b458ef48d4d386d8d41139b42da0d32_106.png)

OK那处理完data ta的东西，就可以来看我们model会长什么样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_108.png)

那这里举个简单的例子，就是一个三层的linear的model。

![](img/5b458ef48d4d386d8d41139b42da0d32_110.png)

那因为在这个test里面，我们的每一个每一笔data，它的dimension是117。

![](img/5b458ef48d4d386d8d41139b42da0d32_112.png)

所以我们的这个linear model呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_114.png)

它的input，这个input dimension应该就会是117，然后最后的output呢就是一。

![](img/5b458ef48d4d386d8d41139b42da0d32_116.png)

因为我们是要去predict一个value这样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_118.png)

然后定义好我们的model之后。

![](img/5b458ef48d4d386d8d41139b42da0d32_120.png)

就可以开始挑选适合的criterion。

![](img/5b458ef48d4d386d8d41139b42da0d32_122.png)

那就先想想看，我这个text是在做一个regression的text。

![](img/5b458ef48d4d386d8d41139b42da0d32_124.png)

所以呢选择mispring error就是一个一个不错的选择。

![](img/5b458ef48d4d386d8d41139b42da0d32_126.png)

这样那如果同学们想要尝试不一样的，那个criterion的话。

![](img/5b458ef48d4d386d8d41139b42da0d32_128.png)

可以去参考touch点N那个document，里面有一些可以其他的选择，让大家去使用这样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_130.png)

然后一样宣告完criterion之后。

![](img/5b458ef48d4d386d8d41139b42da0d32_132.png)

就是OPTIMISER的部分，那这里前面刚刚有介绍过TIMESER的作用。

![](img/5b458ef48d4d386d8d41139b42da0d32_134.png)

这边就不再多赘述，那这边就简单举个例子。

![](img/5b458ef48d4d386d8d41139b42da0d32_136.png)

选用这个SGD来当做我们的optimizer。

![](img/5b458ef48d4d386d8d41139b42da0d32_138.png)

然后接下来前面前面这边结束之后呢，就可以进入。

![](img/5b458ef48d4d386d8d41139b42da0d32_140.png)

基本上就要进入我们的training的loop了，那最外面这个loop呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_142.png)

它就是指说我们的training的ea总共会有3000个。

![](img/5b458ef48d4d386d8d41139b42da0d32_144.png)

这样3000个只是一个举例，实际上可能会更多，有可能会更少。

![](img/5b458ef48d4d386d8d41139b42da0d32_146.png)

你可以继续设一个参数来做决定，然后接下来圈里面入口的东西。

![](img/5b458ef48d4d386d8d41139b42da0d32_148.png)

因为刚刚有说明过了，所以这边一样就是不不多介绍。

![](img/5b458ef48d4d386d8d41139b42da0d32_150.png)

这样简单来说，就是你可以先把input丢到model里面去。

![](img/5b458ef48d4d386d8d41139b42da0d32_152.png)

拿到我们的model prediction，然后呢用criterion呢去计算嗯。

![](img/5b458ef48d4d386d8d41139b42da0d32_154.png)

去计算我们的loss，然后再用lost点DETWORK去计算gradient。

![](img/5b458ef48d4d386d8d41139b42da0d32_156.png)

然后再用optimizer点step呢去更新模型的参数，然后最后记得每次更新完都要用optimizer。



![](img/5b458ef48d4d386d8d41139b42da0d32_158.png)

点real grade，把gradient重置到零。

![](img/5b458ef48d4d386d8d41139b42da0d32_160.png)

这样。

![](img/5b458ef48d4d386d8d41139b42da0d32_162.png)

好那上面就是我的PYTORCH的example。

![](img/5b458ef48d4d386d8d41139b42da0d32_164.png)

简单的说明，然后还有因为这点蛮重要。

![](img/5b458ef48d4d386d8d41139b42da0d32_166.png)

所以再说明一次，就是这个tutorial，他扣的是从homo one简单修改来的。

![](img/5b458ef48d4d386d8d41139b42da0d32_168.png)

所以大家如果要完要完成你phone one的话，记得还是一定要以homo one3头扣为主比较好。

![](img/5b458ef48d4d386d8d41139b42da0d32_170.png)

那大家有什么问题吗。

![](img/5b458ef48d4d386d8d41139b42da0d32_172.png)

OK好。

![](img/5b458ef48d4d386d8d41139b42da0d32_174.png)

大家有问题要问吗，有啊。

![](img/5b458ef48d4d386d8d41139b42da0d32_176.png)

好如果没有的话。

![](img/5b458ef48d4d386d8d41139b42da0d32_178.png)

下一个是你还要对对对好，在这里讲好好。

![](img/5b458ef48d4d386d8d41139b42da0d32_180.png)

那我接下来再说明一下，就是第三个部分是教大家怎么看document。

![](img/5b458ef48d4d386d8d41139b42da0d32_182.png)

拍照，Document viation，还有PYTORCH常见一些的error。

![](img/5b458ef48d4d386d8d41139b42da0d32_184.png)

那接下来这个tutorial，我们会之后晚上会附一个google colab的连接。

![](img/5b458ef48d4d386d8d41139b42da0d32_186.png)

然后欢就很鼓励大家去自己执行，看看看看在什么情况下会喷这些error。

![](img/5b458ef48d4d386d8d41139b42da0d32_188.png)

然后有什么比较常见的解决方式。

![](img/5b458ef48d4d386d8d41139b42da0d32_190.png)

这样子好，那如果说大家就是大家如果对拍拖的方式。

![](img/5b458ef48d4d386d8d41139b42da0d32_192.png)

使用上有一些疑问的话，最简单最直接的方法就是去查这个PYTORCH。

![](img/5b458ef48d4d386d8d41139b42da0d32_194.png)

Document，那TCH连呢，它里面就是一些neural network架构相关的一些使用。

![](img/5b458ef48d4d386d8d41139b42da0d32_196.png)

说明那token人UPTIME就是optimization operism的。

![](img/5b458ef48d4d386d8d41139b42da0d32_198.png)

然后这个token点rooter sta就是有关data set。

![](img/5b458ef48d4d386d8d41139b42da0d32_200.png)

data loader的一些防选，这，那大家再看ptos document。

![](img/5b458ef48d4d386d8d41139b42da0d32_202.png)

对嗯的时候呢，它每个function基本上都会有这些要素。

![](img/5b458ef48d4d386d8d41139b42da0d32_204.png)

就是第一个就是他会告诉你说function的input，还有output会是什么这样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_206.png)

然后下面他会告诉你说每一个input的PARENTERS呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_208.png)

它的input的beta time，还有他会对这个每一个input。

![](img/5b458ef48d4d386d8d41139b42da0d32_210.png)

去做一些简单的说明，告诉你说这个东西它是用来做什么的。

![](img/5b458ef48d4d386d8d41139b42da0d32_212.png)

那下面会以torch点net的方式来做说明。

![](img/5b458ef48d4d386d8d41139b42da0d32_214.png)

那如果你把touch点max的document往下滑呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_216.png)

你会发现torch点max，它其实有很多个不一样的variant。

![](img/5b458ef48d4d386d8d41139b42da0d32_218.png)

对，就是在PYTORCH里面，有的时候你给方选不一样的input。

![](img/5b458ef48d4d386d8d41139b42da0d32_220.png)

这个方选呢它的behavior也会有些不一样，这样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_222.png)

那在这个在这个variant里面，有个比较特别的地方，就是它下面parament parameter的地方呢。



![](img/5b458ef48d4d386d8d41139b42da0d32_224.png)

它分成两种，一种就是原本我们刚看过的那个parameters。

![](img/5b458ef48d4d386d8d41139b42da0d32_226.png)

然后第二种就是这个keyword arguments，那这两个差别在哪里呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_228.png)

parameters你在传递给参数的时候，你不需要去specify它的它的parameter的名字。

![](img/5b458ef48d4d386d8d41139b42da0d32_230.png)

但是keyword argument在传递进去给参数的时候。

![](img/5b458ef48d4d386d8d41139b42da0d32_232.png)

你是一定要去specify它这个参数的名称。

![](img/5b458ef48d4d386d8d41139b42da0d32_234.png)

要不然会吞error，那在拍照里面好，在PYTORCH的DOCU里呢，这两种不同类型的参数，它会用这个红色框框框起来，这个星号可以做一个区隔。



![](img/5b458ef48d4d386d8d41139b42da0d32_236.png)

这样新号以前呢就是PARAME，新号以后呢就是keyword argument。

![](img/5b458ef48d4d386d8d41139b42da0d32_238.png)

然后有些参数呢它其实是会有DEFAB的value的。

![](img/5b458ef48d4d386d8d41139b42da0d32_240.png)

像是以这个例子来讲。

![](img/5b458ef48d4d386d8d41139b42da0d32_242.png)

就是像这个keep dimension等于false，它就是一个default value是false。



![](img/5b458ef48d4d386d8d41139b42da0d32_244.png)

像这种参数呢，我们就不一定要传递，我们传递一包留给他是ACTIONAL的。

![](img/5b458ef48d4d386d8d41139b42da0d32_246.png)

![](img/5b458ef48d4d386d8d41139b42da0d32_247.png)

好那就是以特点，那X为例，他总共有三种标准。

![](img/5b458ef48d4d386d8d41139b42da0d32_249.png)

那下面会很很简单的演示一下，这可能这三个是在做什么，这样那第一种VR呢它的input是一个tensor。



![](img/5b458ef48d4d386d8d41139b42da0d32_251.png)

那它的output呢就是这个tensor。

![](img/5b458ef48d4d386d8d41139b42da0d32_253.png)

里面最大的那个value，像嗯以这个为例的话。

![](img/5b458ef48d4d386d8d41139b42da0d32_255.png)

他的他的他的输出就会是六这样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_257.png)

然后第二个VR呢就是它会有两个最主要的input。

![](img/5b458ef48d4d386d8d41139b42da0d32_259.png)

一个是就是一个tensor。

![](img/5b458ef48d4d386d8d41139b42da0d32_261.png)

然后第二个呢，就是你必须给定给他一个指定的DMANSION。

![](img/5b458ef48d4d386d8d41139b42da0d32_263.png)

那这防犬在做的事情呢，他就是会沿着你给他的胆mansion。

![](img/5b458ef48d4d386d8d41139b42da0d32_265.png)

然后去找到对应的input，但他会去找到你给它tensor里面。

![](img/5b458ef48d4d386d8d41139b42da0d32_267.png)

然后沿着那个版面前去找到max man的发力。

![](img/5b458ef48d4d386d8d41139b42da0d32_269.png)

那这样说可能会有机会抽象，所以还是鼓励大家去实际去google colab上面。

![](img/5b458ef48d4d386d8d41139b42da0d32_271.png)

执行看看，或者是你可以自己开一个简单的FIL。

![](img/5b458ef48d4d386d8d41139b42da0d32_273.png)

去测试看看，这样子，那第三个标准就是给他两个两个tensor。

![](img/5b458ef48d4d386d8d41139b42da0d32_275.png)

两个size相同的tensor，然后他会去对这两个size相同的tensor。

![](img/5b458ef48d4d386d8d41139b42da0d32_277.png)

做element wise的比较，然后取两个里面比较大的那个。

![](img/5b458ef48d4d386d8d41139b42da0d32_279.png)

然后构建成一个新的天子。

![](img/5b458ef48d4d386d8d41139b42da0d32_281.png)

那前面这三种VON在google工类的都有例子。

![](img/5b458ef48d4d386d8d41139b42da0d32_283.png)

大家可以去试试看，那其中的第二个第二个variant呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_285.png)

它大部分的例子都是正确的，不会喷L，最后两个例子是我们故意设计会分析LL。

![](img/5b458ef48d4d386d8d41139b42da0d32_287.png)

让大家知道什么样的状况下会看LL。

![](img/5b458ef48d4d386d8d41139b42da0d32_289.png)

那第一个例子它错的地方在于P这个参数，它是他是这个out的这个呃这个t o argument。

![](img/5b458ef48d4d386d8d41139b42da0d32_291.png)

所以说呢你在传递out这个q argument的时候呢。

![](img/5b458ef48d4d386d8d41139b42da0d32_293.png)

你必须要指定它的current的名字。

![](img/5b458ef48d4d386d8d41139b42da0d32_295.png)

像这里就是没有指定，所以会会PROTE，那最后一个地方。

![](img/5b458ef48d4d386d8d41139b42da0d32_297.png)

他错的地方在于他没有specify dimension，这个parameters。

![](img/5b458ef48d4d386d8d41139b42da0d32_299.png)

![](img/5b458ef48d4d386d8d41139b42da0d32_300.png)

好那接下来跟大家讲一下，就是拍照的一些常见的以及它的解决方法一样。

![](img/5b458ef48d4d386d8d41139b42da0d32_302.png)

在google play上面会有实际的例子，大家可以去咨询看看。

![](img/5b458ef48d4d386d8d41139b42da0d32_304.png)

那第一种就是嗯，你的model跟你的tensor是在不一样的debug上面。

![](img/5b458ef48d4d386d8d41139b42da0d32_306.png)

这是还蛮蛮蛮常遇到的问题，就是现在这个model它是在库达。

![](img/5b458ef48d4d386d8d41139b42da0d32_308.png)

就是显卡上面，那这个tensor呢它是在CPU上面，那如果你想要把这个tensor丢进去。

![](img/5b458ef48d4d386d8d41139b42da0d32_310.png)

model做运算的话，他就会喷你个error，告诉你说你有些东西在不同的迪拜是商用。

![](img/5b458ef48d4d386d8d41139b42da0d32_312.png)

那解决方法其实很简单。

![](img/5b458ef48d4d386d8d41139b42da0d32_314.png)

就是你以这个例子来讲话，就是把X这个tensor，然后去投射到PUA这个这个b box上面就可以了。

![](img/5b458ef48d4d386d8d41139b42da0d32_316.png)

![](img/5b458ef48d4d386d8d41139b42da0d32_317.png)

那第二种常见的hero就是你的你的tensor呢，它的百年选是mismatch的。

![](img/5b458ef48d4d386d8d41139b42da0d32_319.png)

举例来说，举一个最简单的例子，就是像这X这个tensor。

![](img/5b458ef48d4d386d8d41139b42da0d32_321.png)

它的size是45，那Y这个TENSAN他size是54，那如果想把它加起来的话。

![](img/5b458ef48d4d386d8d41139b42da0d32_323.png)

它就会跟一个L告诉你说你的size是你的size。

![](img/5b458ef48d4d386d8d41139b42da0d32_325.png)

是mismatch的这样子，那这边呢就推荐大家用上一个tutor。

![](img/5b458ef48d4d386d8d41139b42da0d32_327.png)

在上上个tutorial，我教过了transport space啊，space这三个函式呢去改变你的tensor的形状。



![](img/5b458ef48d4d386d8d41139b42da0d32_329.png)

把它改变到正确的形状。

![](img/5b458ef48d4d386d8d41139b42da0d32_331.png)

那第三种常见还有是库大号NAVI，那它在什么时候会发生呢，就是你显卡的机体爆掉的时候，那这种时候解决一个常见的解决方法，就是你去减少你的bad stars，像这边S开512可能就有点太大了。

所以把batch size减少。

![](img/5b458ef48d4d386d8d41139b42da0d32_333.png)

然后减少到适合的大小就没有问题。

![](img/5b458ef48d4d386d8d41139b42da0d32_335.png)

但是这是一个比较难应付的解决方法，但不鼓励不鼓励大家这样做。

![](img/5b458ef48d4d386d8d41139b42da0d32_337.png)

就是你你或许可以考虑把这个贝塔EJY过去，其实就是跟beset意思一样的意思。

![](img/5b458ef48d4d386d8d41139b42da0d32_339.png)

不过还是鼓励大家用刚刚我讲到data load去调整。

![](img/5b458ef48d4d386d8d41139b42da0d32_341.png)

best side会比较好。

![](img/5b458ef48d4d386d8d41139b42da0d32_343.png)

那最后一个error就是mismatch的tensor time。

![](img/5b458ef48d4d386d8d41139b42da0d32_345.png)

因为在PYTORCH里面其实不同的不同的资料。

![](img/5b458ef48d4d386d8d41139b42da0d32_347.png)

它储存的type是可以是不一样的，那举例来说。

![](img/5b458ef48d4d386d8d41139b42da0d32_349.png)

你今天如果在做一个classification的text的时候，你会可能会用到一个criterion。



![](img/5b458ef48d4d386d8d41139b42da0d32_351.png)

叫做cross entropy loss，那这个cross entropilots呢，它第二个parameters是嗯是label。



![](img/5b458ef48d4d386d8d41139b42da0d32_353.png)

那他会要求说这个label的tensor的type是long。

![](img/5b458ef48d4d386d8d41139b42da0d32_355.png)

所以如果说你没有把它变成long long type的话。

![](img/5b458ef48d4d386d8d41139b42da0d32_357.png)

它就会put l，我告诉你说你的tensor type错误，这样那解决方法也很简单。

![](img/5b458ef48d4d386d8d41139b42da0d32_359.png)

就是你把它点弄这样子，把它用到。

![](img/5b458ef48d4d386d8d41139b42da0d32_361.png)

把它改变成动态的就没有问题，好。

![](img/5b458ef48d4d386d8d41139b42da0d32_363.png)

那介绍大致这样子。

![](img/5b458ef48d4d386d8d41139b42da0d32_365.png)