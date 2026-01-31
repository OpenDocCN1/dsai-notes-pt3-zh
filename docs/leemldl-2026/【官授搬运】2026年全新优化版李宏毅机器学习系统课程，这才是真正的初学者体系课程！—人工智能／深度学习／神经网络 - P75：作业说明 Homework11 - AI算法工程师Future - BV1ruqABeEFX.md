# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P75：作业说明 Homework11 - AI算法工程师Future - BV1ruqABeEFX

大家好，我是追月11的助教陈坤，接下来由我来讲解第11次作业，首先我会先简单介绍此次作业的内容，使用到的资料集和上传到cargo时的CSV的格式，另外也会说明report的细节，整个作业的评分方式。

baseline和大家需要遵守的规则，右边附上的则是一些常用的连接，包含cargo的比赛连接code的城市码，还有呃home work，11的讨论区，那鼓励大家。

如果有任何问题都可以向cool来这个讨论区发问，或是帮忙回答，那这次作业的deadline，定在6月3号的午夜12点，那我们是不接受任何赐教。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_1.png)

那这次作业的主题内容呢是domain adaption，假设呢，我们今天想要进行一个跟3D相关的任务，那我们就要相对应的data set，但在刷收集data set的时候发现，如果我要拍很多的街景。

然后花很多的时间来进行呃，比如说SEMENTATION的label的话呢，就会需要花很多很多的时间，但是呢如今呢已经有非常多的游戏，可以做得很拟真，比如说gta five中也有街景的呃，拟真的画面。

那在这个画面中呢所出现的角色，比如说车子啊，路灯啊，或者是马路，都已经有自己在游戏城市内定义的label，那我们这样是不是就可以很轻松的获得大量，data set来进行training。

虽然呢跟原来的街景有一定的差异性，但是呢我们可以由GTF生成出一个比较庞大，而且接近真实街景的DATASET。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_3.png)

那假设呢我们今天真的拿gta five的data set，来做training的话呢，那我们的feature instructor假设叫做net u，我们的classify叫做net d的话。

而在一般的training过程，我们会将turning的图片先放到net u里面，拿到feature以后再送到classifier，拿到output logic，然后看是哪一个类别的最大值。

然后来比较答案，从呃从而获得loss，然后计算gradient，让我们的内work1步一步的计呃越来越好，但是呢当我们在做testing的时候，我们testing的是test在真实世界的街景。

那当我们把真实世界的街景放到training，在GTA5的这个模拟环境的街景时，就会发现我们没有办，其实没有办法确保说拿出来的feature会是好的，那当我没有办法确定拿出来feature是好的。

又更没有办法，更没有办法确保说，我们这个classifier能够看懂这个未知的feature，然后从而拿到一个好的output，因此呢对我们的net u来说，其实对我们的net u或者是net d来说。

呃，真实世界的街景，其实比较像是一个abnormal的data，就像我们前面座位有一个an呃annly detection一样，如如果我们今天的放进去呃，整个network的图片是在不同抖面上的时候。

会发现它在reconstruction的时候会比较差，当然就是因为拿出来的feature和decode，encoder和decoder都有受到抖面影响，那在这个情况下呢。

我们就要想办法来解决这个抖面上的差异，造成feature不一样，还有classify没有办法读懂的状况，因此呢我们想到一个最简单的解决方式，就是我们如果能够让在呃gta five。

也就是training，Data，training dman上面拿出来的feature，还有testing，也就是真实世界的呃，图片放进去以后，拿出来的feature如果都是很相近的话，那我们就期待。

如果他能够在training拿到一个很好的accuracy，那在testing的时候呢，也够也能够拿出一个好的feature p让classify认得，然后正确的预测出这张图片，到底是什么样的街景。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_5.png)

那在这次作业里面呢，就会希望大家可以使用，像刚刚讲到domain adaption的技巧，这样我们会给大家就是真实的图片，比如说这边就有牛，然后还有时钟，还有一些真实物品，然后还有label。

那就希望大家可以使用domain adaption的技巧，来预测说我们画画的图片，也就是相对应的种族，能不能不能够被分类出来。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_7.png)

那我们的data set呢一共有十个class，那会从零标号到9号，那就位可以像现在下面这个图上看到的有马啊，床啊，还有时钟等等等，那training的图片呢总共有5000张RGB的图片。

那都是32×32，然后有附带label的，那testing的话呢一样会是这十种class，但是呢会是黑白的图片，而且是28×28的画画图片。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_9.png)

那总共会有10万张，那在大家解压缩完real drain点zip以后呢，应该就会看到training data，里面有0号到9号这个资料，这十个资料夹那里面呢就各会有500张的图片。

那testing data里面呢就只会有一个0号的的资料夹，因为它没有任何的label，那全部呢总共会有10万张的图片，那额在城市马中，在COLAB的翻译程式码已经帮大家呃解压缩。

然后在城市码也会先定义好data set，直接用image for the这个函式帮大家的定义好data set，还有data loader，在城市码中就可以直接使用。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_11.png)

在假交的时候呢，角角CSB应该会有两个栏位，第一个栏位呢是图片的id，第二个栏位呢是你预测出来的label，那总共会有10万个需要预测，需要提供的预测结果。

因为我们总共就是有10万张的testing data，那我们衡量的标准就是使用accuracy，来当做衡量的基准。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_13.png)

好那评分方式的话跟前几次作业一样，总共会有四个best night，每个baseline会有public跟private各0。5分，所以呢四个baseline总共会有四分。

那report的话呢是交到GRASSCOPE上，那会有两题，一题两分，再加上城市马的角，交两分的话，总共就是十分，那simple baseline的话呢，PC0。5分，private0。5分。

那在public的accuracy呢，希望大超过0。44288，那在圈里的时候，基本上应该小一个小时就可以结束，那只要跑呃范例程式码，然后角交CSB应该就可以轻松的通过simple baseline。

那medium bas赛呢一样有分public跟private各0。5分，AQS1的话，就是要超过0。64996，那大概需要花两到四小时来做全练，那如果想要过media备赛呢，需要调整一下正确的浪。

就是DNN里面会有一个浪打值需要大家调整，那在范例程式码中原本是设浪打值为零，那如果想要过MEDI电背出来的话，就是要直接自己去自己去implement，就是浪打得随时间的变化这样子。

那当然呢也是需要一些运气，然后要train更多的AIRPODS才能拿到比较好的结果，那如果想要过strong bassline的话呢，则是需要超过0。75684，那可能需要圈大概5~6个小时。

才能得到双非赛的结果，那在刚刚介绍data set的时候，其实有说到我们的testing data呢是label balance，也就是说每一个呃每一个class总共有10万张。

那每个class应该会有额1万张的图片，那在预测出来的时候呢，应该就可以知道说最后全部预测出来的结果，里面每一个class都要有十十万个预测结果，那看大家可不可以利用这个额外的资讯呢。

来达到双倍line，希望大家可以多做尝试，那波space line呢则是需要大的accuracy，超过0。80464，那因为我们这次呢进行的作业，其实也是算是classioccasion task。

在逐月三的时候，大家应该用过非常多的CNN的技巧，比如说改编optimizer呃，改变learning rate，还有改变，还有一个增加一个learning reschedule。

或是呢把model或者output ensemble，都是大家可以多做尝试的方法，或者是呢可以使用更进阶的ADDIVERSIAL，training的一些network来可以参考，看看以下三个连接。

或者是呢大家有没有想过，其实这次的作业呢跟作业三有一点点相像，就是他有一些不知道label的图片，但是呢其实是相同的class的，虽然说抖面不一样，所以大家有没有想过。

可能SAMISUPERVICE也可以帮助呢，或者是呢可以尝试，完全昂，就是完全没有任何监督师的unsupervised learning。

比如说universal domain adaption来做一些clustering的方法，来增加最后training的accuracy，那在greeting的部分呢，我们还有一个bonus。

如果你在cargo上的private submission是前三名的话，你可以缴交一份报告，然后简单讲下你如何实作，然后你使用的一些参考的GITHUB或者是论文，那在做完这份report以后呢。

你们就可以直接上传到home work11的讨论版，让大家看一下，那如果确认你是前三名，而且你要缴交这份报告的话呢，就可以拿到额外的0。5分，城市马的角胶一样是在NTUPO上面。

那截止日期是在6月3号的零呃半午夜12点，角角的格式是要请大家把呃PY档，或者是IPYNB档压缩到资料夹里面，然后将zip档取名为你的学号底线，homework11点zip。

那我们只能看到你最后一次的submission，那请也不要将任何的呃model啊，或者是资料集放到里面，不然会太大，那如果你的城市码呢有点奇怪。

没有办法符合你角角的submission的accuracy，那我们有可能会将你的血总成绩呢乘上0。9，接下来要跟大家讲解的是report部分，首先在第一题中呢。

要请大家视觉化不同class之间feature的分布，那微信大家使用的是TSN1，这个非线性降维工具呢，来将高维度的feature分别视觉化到二维的作图，那一共呢要做三张图。

分别是训练的前期中期还有晚期，那在做完这三张图以后呢，希望大家可以简单的说明，并分析图片中feature分布，那提示就是说呢按照这样子的分布，那可以看得出来。

这个feature extrator到底对我们的分类问题，是一个好的feature extrator，还是一个不好的feature extractor，那如果想要知道跟T2S1，更多相关的内容的话呢。

可以看一下附上的T2SN1课程链接，这边提供的是一张范例作图，这张作图里面呢可以发现总共会有十种颜色，那上面的标示的数字呢应该也有19，因为我们今天是对不同的class之间去做。

那我们的data tc中有十种class，自然作图中也会有十种class，那可以看到说在final stage的时候呢，每一个class的分布其实都是一坨一坨一坨一坨的，那大家可以想一下。

这样子呢对classify或者说对整个classification text来说，这是不是一个好的feature，附上的链接是sk learn所提供的，TSNE这个function。

使用的一些细节参数的使用方式，那大家把feature做完呃，非线性降为替身一以后呢，也记得要将这些资料点map到零跟一之间，那如果呢想要跟这张图一样有不同的颜色。

可以参考map plot提供的c map，那c map就会有自动将index对应到颜色的功能，这样这样你做图起来呢就更方便，问题二呢一样是希望大家可以去做视觉化，但这次视觉化对象呢是在不同的抖边之间。

那我们会希望你你们可以将model，也就是你们的feature extractor evaluate，在source data set跟target data asset上收集好他们的feature。

还有分别的domain labels，以后呢一样做三张电神仪的plot，那一样会希望大家做完图以后可以简单的分析，还有解释一下这个分布，对于呃domain adaption这样的text来说。

到底是不是一个好的feature extrator。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_15.png)

附上的图片呢是助教实际去做以后，实际去做图以后呢得出来的图片，那这张图片呢是坐在final stage时，feature的分布，那可以看到在图片中呢，只有蓝色跟红色这两种label。

那数字上的话则是看到零跟一，也就是一代表source，零代表target，那由于我们的testing，由于我们的testing的DATASET就是target data set，其实非常的大。

所以呢我们可以随机的挑取5000张图片，来做evaluate，那5000张的来源呢，就是跟source的data set是一样的大小，这样子呢我们作图出来也比较，不会有unbalance的情况。

就可以看得出来蓝色跟红色的重叠状况，是不是蓝色是否有跟红色重叠，来借此判断说这是不是好的domain adaption的结果。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_17.png)

当然呢也不能将你的城市码或者是呃，预测出来的答案跟任何人分享，那也不能使用任何的方法来，一天脚就要超过五次的结果，也不能找任何的额外资料，或者是pretrain model来使用。

那如果上述的任何规则被违反的话呢，那这次的分数也会被被视为零分，那如果大家有任何问题呢，可以上NTU库来NT库的home work，11讨论区来问问题，或者是呢寄信到MLTA202spring。

这个GMAIL的网址来记，那大家在即兴的时候呢，记得如果是跟这位11相关的话，请在开头打上就是轰work11这个主机，那附上的呢是在training的时候呢，可能会有点learning curve。

那这张图片呢仅供大家参考一下，在不同iteration底下的loss会是长什么样子，那这个浪打值呢则是在过密电费赛呢，需要去做调整的，那大家也可以参考一下。

这个iteration和long a值之间的关系，那大家在training的时候，因为这次的作业其实没有办法去做validation，accuracy去做参考。

所以呢可能会不太知道到底要圈多少个a pop，才会是足够的，那这边助教提供了一张照片，可以看得出来说全景到2000个APPODS之后呢，其实testing的accuracy都还是在上升的。

那当然大家没有办法拿到testing的across，因为大家没有正确答案，不过可以知道，如果training越久，那texting的accuracy自然也会跟着上升。

不会是一直在做OVERFITTING。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_19.png)

在继续讲解COLLAB前呢，会先跟大家简单的介绍一下，这次范例程式码中使用到的network DNN，那这里我们介绍的是最基最基础的DNN，那DN的全名呢是domain of a cereal。

Training of endance，当我们在一般在进行training的时候呢，如果训练的资料集是两个不同的，不同分布的资料集的话呢，通常会造成CON在training的时候暴走，那就像图中所示的。

如果ADATASET是属于正常的全体data set，但是BDATASET呢是是属于正常电压，C也就是像是真实或者是画画中的图片，那我们拿到的输出就有可能会是up noa的输出。

那当我们拿到of NOVA的feature的时候呢，当然整个圈里呢就会坏掉，那会让整个让会让CNN没有办法正常输出呃，data set b中的答案的原因是，因为呢我们没有对他在B中的label。

可以让整个模型去学习，说D24B应该要有怎么样的分布。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_21.png)

所以为了因应这样的状况呢，DNN就将CNN预先拆成两个部分，也就是feature shor跟label predictor这两个部分，那CNN在吃入DATASETA跟DCB以后呢。

就就会希望呢能够将输出的feature的distribution是相近的，那如果这两个输出的feature的distribution distribution很相近。

那我们的label predictor，当然就也可以正常的去预测出额，预测出呃，输入的data是什么样的图片或是什么样的种类。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_23.png)

那要努力的让逼得呃feature接近A，努力的让A的feature接近B，所以我们就引进了类似gain discriminator的功能，那get discriminator呢就是用来分辨说哎。

我今天放进来的图片到底是从data aza来的，还是从data set b来的，那如果我们的discriminator分得出来，说是ADRC还是BDRC的话。

代表说呢我们的feature attractor还要进行调整，才能让我们的discriminator，没有办法分辨出是A还是B的，来自A的还是来自B的图片，那当我们在training的最后的时候呢。

我们应该就会希望说我们的discriminator，完全没有办法分辨出来，我们的feature，EXTRATOR给出来的feature到底是来自A的图片，还是B的图片。

那当我们输出的而当我们输出的feature呢，不管是来自A还是来自DRSB呃，feature都能非常接近的时候呢。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_25.png)

经过我们的label predictor的output呢，就也会是非常好的。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_27.png)

![](img/3fd7874917b47ffed2b00ebd4aa9830a_28.png)

那接下来呢就来介绍一下COLLAB中范例。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_30.png)

城市马的实作方式，那可以看到，在上面呢我们要先提供一些简单的review。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_32.png)

来说明一下这次作业的呃。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_34.png)

十座的domain adaption，是属于呃transport learning中的哪一种。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_36.png)

还有为什么我们要去进行DOMELECTION，那如果大家有空的话。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_38.png)

务必呢仔细看一下，因为呢里面的叙述其实跟report也是有些相关的，像图中的呃，像图中的这个作图，其实应该就是类似T2S1的作图。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_40.png)

可以看得出来呢，由于我们的feature distribution相差的蛮大的，也就是蓝色跟红色完全不重叠，所以对classify来说。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_42.png)

我们只能分配好source，也就是PVE的地方蓝色的点，那蓝色点就是一群一群一群一群的。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_44.png)

也就是说呢它可能是不同的类别，那我们classify呢就可以很好的去辨别出来。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_46.png)

他是它究竟是哪个类别，但是红色的。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_48.png)

但是红色的feature人就没有办法被分类出来。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_50.png)

那我们在进行domain adversarial training的时候，也就是我们这次使用的DNN。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_52.png)

在城市码最开始呢，我们会先下载这次其要使用的data set，那我是直接从GITHUB的release上下载下来，那如果第一个下载link没有办法使用的话，可以用下面这两个呃。

mirror的data set link来下载看看。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_54.png)

那下载好以后呢，它应该会自动把它解压缩。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_56.png)

![](img/3fd7874917b47ffed2b00ebd4aa9830a_57.png)

那这次的DRC其实应该不大。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_59.png)

不过有蛮多张图片，所以可能解压缩的时候要等一下子。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_61.png)

![](img/3fd7874917b47ffed2b00ebd4aa9830a_62.png)

![](img/3fd7874917b47ffed2b00ebd4aa9830a_63.png)

那在解压缩移完以后呢，我们可以先简单的先看一下这次的DLC图片。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_65.png)

究竟有哪些类别，还有它对应的图片。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_67.png)

把他秀出来，看一下究竟是不是正确的，那可以看到说呢总共会有十个类别，分别有马啊。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_69.png)

床啊，然后时钟苹果等等等，那我们的target的data set呢。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_71.png)

也就是test data一样是有十个类别，那这边就没有按照顺序了，那总共有画画的图片，有苹果蓝马时钟等等等等等。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_73.png)

![](img/3fd7874917b47ffed2b00ebd4aa9830a_74.png)

那由于呢我们今天的可以看到。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_76.png)

我们的画画的图片跟我们真实的物体的图片。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_78.png)

其实长相差异非常非常大，所以呢假设呢我们可以让我们的真实图片，越接近我们的长相，越接近我们呃。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_80.png)

target也就是我们的画画图片的DMAN的话呢，或许就可以让我们的training the accuracy。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_82.png)

变得更好，所以呢我们就会希望可以对这些真实的图片。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_84.png)

进行一些呃，computer vision就是电脑视觉的影像处理，让它越接近这个抖面。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_86.png)

越接这个target抖面越好。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_88.png)

所以呢我们就会将图片先进行灰接。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_90.png)

然后再使用KENNY这个呃h detection的。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_92.png)

h detection的CV的function来将图片变成边缘化。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_94.png)

也就是比较像是画画的样子。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_96.png)

那在我们挑好。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_98.png)

也就是我们进行完PREPROCESS以后呢，我们就希望对整个data set去做process。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_100.png)

那在这边进行的时候呢，我们是用CV的呃。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_102.png)

CV的操作来进行，但是在training的时候呢，我们应该就会直接使用呃。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_104.png)

呃PyTorch torch vision提供的一些transform，那我会直接把它compose成一整组的transform。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_106.png)

那我们会有source跟target这两个transform。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_108.png)

因为我们的source才需要进行KY进行灰阶化。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_110.png)

还有kenny detection这个环节，那我们的呃我们的target delset本来就是画画的图片。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_112.png)

所以讲的就会是很接近呃黑白的这张画画图片。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_114.png)

那这在定义好source data set，target data set以后呢，我们就source data loader，target data loader跟test data loader。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_116.png)

![](img/3fd7874917b47ffed2b00ebd4aa9830a_117.png)

那这边呢我们就定义好我们的model，那model就像刚刚讲解DNN的时候一样。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_119.png)

分成三个部件，第一个呢是feature extractor，feature restrator呢是由一连串的CNN来构成，那大家如果在如果如果想要调整的话，也可以直接来这个定义的地方直接做调整。

那fefeature extractor以外，我们还有label predictor，也就是分类，将取出来的feature进行分类所需要的label predictor，还有当做呃。

还有类似game里面呢用来分类domain的domain classifier，那domain classify用意呢就是希望来强迫我们的feature。

EXTRATOR的取出来的feature能够越接近越好，那以上呢就是三个，我们这是呃，我们这是DNA里面架构会用到的三个大的八九。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_121.png)

![](img/3fd7874917b47ffed2b00ebd4aa9830a_122.png)

我们这边呢会先将三个module呢。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_124.png)

三个network都先放到coda里面，然后定义好我们这次的呃loss function，也就是使用cross entropy loss。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_126.png)

那由于抖面呢只有2class，所以我们就用binary class，Un loss。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_128.png)

我们三个network的权利。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_130.png)

所以呢总共会有三个optimize，那如果大家呢想要更换这个ADAM的ARTIMIZE。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_132.png)

换成别的也可以做尝试。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_134.png)

那最后呢就到了我们的重头戏。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_136.png)

也就是我们的training的loop会怎么进行。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_138.png)

那在这边呢我们是直接用一个for回圈呢，来进行圈里。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_140.png)

那在每个圈里里面呢，我们都会我们会先将domain classification的loss设为零。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_142.png)

然后feature shatter。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_144.png)

还有label predict loss设为零，那在training的时候呢，我们会一次将source data跟target data load里面的资料，一次先取出来一个batch。

那都放到GUA以后呢。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_146.png)

我会将source data跟target data相接在一起，变成一个大的mix data，那这个miss data呢一样要有对应的dman in label，也就是说呢。

我们的source data的对应到的label应该要是1target data，对应到label要是零，所以呢domain label呢就会是由一个先，全部是零的矩阵。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_148.png)

那前半段呢由于是SODATA主要设成一。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_150.png)

那把MISSTA放到feature instructor以后呢，取出来的就会是全部的feature，那再把这个feature呢放到domain classify以后呢。

我们就可以让domain classify来预测，说到底哪些哪些资料呢是source source data，哪些资料呢是target data。

那再来跟我们刚刚的domain label来计算loss。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_152.png)

那把loss相加完以后呢。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_154.png)

就可以计算BWORK，然后来更新我们的参数。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_156.png)

那step two的话呢就是要劝我们的feature iterator，还有label classify，因此呢我们的我们在TRALABEL，predictor跟PEACHATTRATOR的时候呢。

我们只能拿前半段，也就是有label的部分，Southea，那将它放进去class label attraction以后呢。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_158.png)

就是拿到class logi，那这些class logic呢就可以拿来去算，我们的cross entroo，我们就可以来算cross entropy lost，然后我们还要再扣掉呢。

Binary cross entroplost，那这时候呢就会有一个浪打的参数，可以去做调整，那这浪打参数呢就可以让你调整，说在training我们的呃。

feature extractor跟label classify的时候呢，我们的权重要是多少，那我们的domain logic呢。

则会是将feature放到domain发射法以后的domin logic。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_160.png)

那在计算完这个loss以后呢，我们就一样是对使用OPTIMIZZE来更新参数。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_162.png)

那在做完一次更新后呢。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_164.png)

记得要将所有的瑞典都清空以后，然后来计算accuracy。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_166.png)

所以呢我们的return值就会有training的domain loss，Training the feature，Feature is shot again，Classified loss。

还有整个training the accuracy，那在training的结束呢，我们就会去储存feature strator model的checkpoint。

还有ulabel predictor的checkpoint。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_168.png)

![](img/3fd7874917b47ffed2b00ebd4aa9830a_169.png)

那在influence时候呢，将label is那level predictor跟feature shor，都设成evaluation mode，然后将所有的test data的放进去。



![](img/3fd7874917b47ffed2b00ebd4aa9830a_171.png)

然后看看预测出来的结果是什么。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_173.png)

然后使用pandas，将所有预测出来的结果直接写入成一个CSV。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_175.png)

那接下来呢会是visualization的部分。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_177.png)

也就是我们在jaja grace scope report，会需要需要使用到的一些套件。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_179.png)

那在这边呢有提供了三个步骤，和一些可能会用到function的的import。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_181.png)

那大家只要跟着上面的步骤去进行，然后分别作图出来三个stage。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_183.png)

也就是early middle跟final stage的图以后呢。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_185.png)

就可以找交report。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_187.png)

错，那如果有任何的问题呢，可以寄信到我的信箱。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_189.png)

或是寄信到呃MLTA的信箱，或者是呢也可以提问到呃。

![](img/3fd7874917b47ffed2b00ebd4aa9830a_191.png)