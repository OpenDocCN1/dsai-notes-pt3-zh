# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P110：作业说明 Homework15 - AI算法工程师Future - BV1ruqABeEFX

![](img/fbd9561f458f1a21f83ba8520b44bf05_0.png)

就是最后一个作业，好的好，那我就来讲一下作业时，那作业时我要做的是meal learning好。

![](img/fbd9561f458f1a21f83ba8520b44bf05_2.png)

那这边是这次作业简单的额外好，那这次呢我们是希望同学去做一个few，Shot classification，那使用的data set是欧米伽data赛，那这个对他赛呢就是有呃，看到这张图上面显示。

就是有很多不同的手写的数字，那就是这个情况就是很适合拿来做学校的classification，那我们呃就是怎么样塞到我们的这个problem呢，就是我们set到的problem是一个five four。

One shot cussification，那也就是说我们在每一个新的tag进来的时候，会有一个support set，一个query set，那support赛的话的话会有额五张不同的手写的数字。

像这边呃这五张，那query set，就是呃在一样是五张不同的手写数字，那我们要做的任务就是去看反说，例如说这一张手写应该是对应到这里面哪一张，那应该是这一章，那额对我们就要做这件事情。

那omega对他赛的赛道还有额分层式，就是原本的赛道是background，才是有30个alpha bets，然后里面会有不同的character。

那evaluation set是20个of a bts，但是这边呃，助教因为要呃让大家可以在靠我上面共同比赛，那所以我们这边与百六选赛，其实是有先帮大家申报，那这部分呃关于怎么sample。

就是我们的five four one shot的problem，等下会再仔细讲好，那这这次做的主要任务就是希望大家创一个呃，nemo on欧米噶的开ATION，那呃深深老师上课的投影片。

就是呃像这边有呃training set，是就是我们这边称为support set，能有这这么多张照片呃，手写数字的图片，那一个test set的进来的时候，我们希望变质说这张呃。

这张手写数字是对应到哪一章，那我们用的方式就是呃希望同学implement meal，这个metal learning algorithm，那它主要的概念就是呃会去希望找到呃。

最好的model的intralization point，就是每一次任务之前还会先呃sample support set，跟query赛，那会根据support下先走到一个set塔M的呃参数。

然后再根据query下去update，和我们initialization the point，那就是第一次update会走到现场呃，Five one，然后第二小队找到five two。

这样那根据额多次update时，希望找到一个好的insulation point，在开新赛的时候，我们根据我们呃，他现在的support image去update我们的模型之后。



![](img/fbd9561f458f1a21f83ba8520b44bf05_4.png)

得到最好的呃，few shot classification的结果好，那边这边仔细讲一下我们data format，那for training set跟validation赛。

因为呃就是我们不需要限制同学是怎么去simple的，然后simple的个数，那这边都是给完整的呃，30个阿尔法带跟，然后每个阿尔法BS里面有不呃，好几个不同的character。

那可以看到像右边那因为是background，下面有像这是第一个阿法代码，他的character01有额20张的不同的simple，那character02有也是一样，是20张。

那就是每次在做trap跟VIATION，那就会随机选呃五个不同的类别，然后当做五个不同的class，那会分别simple呃，一张support，下一张query里面去这样。

那对那这边是算是给大家原始的就是data structure。

![](img/fbd9561f458f1a21f83ba8520b44bf05_6.png)

但是data loader那些宗教都已经已经处理好，就是大家可以直接就是呃使用助教信号，data tao就是会从这不同的看呃，character去sample simple sequreset。

那至于他写下的部分，因为额如果我每次都让额分别sample的话，就是会额，就没有办法在coco上统一去比较大家的朋友，所以这边是助教们先帮大家申报好。

就是640比support跟CORREAPPEARS，然后每一个pair就是五个support image跟五个query image。



![](img/fbd9561f458f1a21f83ba8520b44bf05_8.png)

那folder structure就是像右边这样呃，在omica test folder下面有一个support folder，那有0000到额640比一的。

然后每每一个folder下面都有五张support，进去后，对应到的是query下面的000的五张，Querimage，那要做的事就是去辨，是说这五张image对应到呃。

support的是support下，下面拿五张页面是这样好，那这部分一样同学呃比较担心，就是他心下的data load也是助教有先处理好，就是额也不需要同学去改，不然如果不小心改到的话。

会造成额就是如果你动画顺序的话，在cargo上面会有额，就是很奇怪的结果，所以这部分是主要写好。

![](img/fbd9561f458f1a21f83ba8520b44bf05_10.png)

然后希望大家不要去动，这样好，那这边是一些杯赛的指引，那关于simple杯赛的部分是呃，在sample code部分是助教写好的。

那这边input本是一个简单的transfer learning的model，那他做的事就是在training的时候，他是去额，先首先会先选五个不同的class。

然后去做一般的classification，那呃在validation跟testing的时候，他是从嗯support image去做反球，也就是说他会呃在training的时候。

他其实没有额学不同text这件事情，他只是做一般的training，那在VIDATION我们需要他transfer到呃，就是布新的五章的support image。

那这个方法额就是会比呃meta learning还要差一些，那这就是当不是我们的悲伤，这样那这边部分是呃simple课一份吗，或是同学跑下去都可以。

那额直接上传的话应该是会过呃cargo的simple备上，那如果是关于media跟STR备赛的部分，就是呃助教在meta learning那边有挖了两个to do的blogs。

那哦这两个图标就可以对应到meal land的inner，loop跟alter loop，那么电beer的话只需要同学是去做到呃，First order memo。

那strong beer是会有input memo或ANEO，那关于额不同的metal line的方式的，inner loo跟alter loo要怎么去修改的话，可以对照下面这几个reference好。

那主要就是呃，我觉得同学如果觉得这边方法太多的话，可以主要是folk3MAO的部分就好，因为如果是只需input lemo话，就可以过SHO回程可以标呃，去管其他方法，就是如果有额需要一特曼。

其他方法可以在参考下面这几个链接，那关于boss bas赛的部分，那需要同学去做是a test of mentation，那额这边所有的task repetition，都是我们会有不同的test。

那你就可以想说有什么方法去argument，它就是原本这边左边是一个原本的test，可能是某一个手写数字，那用什么方法去argument之后，它可以变成呃另外一个task，然后跟原本的又不太一样。

但是它又可以被独立当成是新的一个task，新的一种手写的数字，那再加上这个方法，然后再加上前面的每条line就可以过boss bassi好，那这边是然后就看不下呃，不同的杯赛可以达到的。

大概的在考考上面的分数，那simple杯赛就是助教英特尔好，还在艾格斯可以在0。6左右，那MEDBA如果input正确，input first order level的话，可以带0。7，双倍扇的话。

在0。9，那boss被扇是就是呃memo加上test可选，可以到0。95好，那这边是额grading的一些额详细的分数，那就是一样是simple media strong。

跟boss那分成分成public和private各是占0。5分，那report部分是四分，那同学怎么分呢，额要记得找哦，那这report问题等下会再讲，那cos上面需要部分是同学要记得上传到呃。

nt l CORE上面，额那bonus的部分的话是，如果你的最后看过比赛结束之后，最后的REACKING在private leader wall上面，有前三的话，可以写一个呃简单的report。

那包含在下面几点，就是你的名称分id，然后你用什么方法reference，然后在200字以内，那这边期限的话是在呃就是cos上面选，跟呃开荒那些大战结束之后的一周，就是呃7月8号。

那是希望同时上传到NT5扩的discussion，那在通过15下面，那如果有上传的话，就是有符合这几个条件，就可以拿到额外的0。5分好，那这边讲一下呃，我们report希望呃同学回答的问题。

那这部分是讲交到呃grade scope上面，那part one的部分是希望同学去额分析一下，就是number of test，这边TT就只说我们可能有几种不同的手写数字。



![](img/fbd9561f458f1a21f83ba8520b44bf05_12.png)

那根据根据你最好的meta的resort，那你去画一个呃relation between death，Accurate and the number of tasks。

那这边number of才是同学要去呃，从co里面去限制说我们是呃，原本的test可能是有50个，那我们限制说，那如果现今天限制test只有20个或者十个，那就是因至少做三种不同的实验。

那去探索那这种情况下的def accuracy，跟number of task的关系，那画成一张呃折线图，然后这边这部分占了一分，那第二小题就是用呃简单的一句话去描述说，你从呃这张图观察到什么。

可能是呃def accur跟task个数的关系是什么，那怎么可能占一分，那第二部分的话是希望同学去呃探讨，Inner of their steps，那这边一样是根据你最好的那条人走。

那句话说呃你的death accurac跟in the object，Death at inference，然后这边重点是呃，是同学需要是希望同学去探讨在inference时候的呃。

Inner update that，而不是在training的时候，那training的时候，就是保持说你原本是你best meta的时候，是几个train step，就是维持几个。

那只是在呃在呃evaluation的时候去改变，说你在support side inner of the step的个数，那这边可能就是可以试说呃，可能update1步五步十步。

那一样是至少包含三个不同的experiment，然后再画成一张，然后画成一张折线图，额然后这部分也是占了一分，那第二部分就是以，同样是用一句简单的话去描述说，你从上面这张图中观察到什么。

就是def accuracy跟inner object step的关系是什么，好那呃这边是连接，就是有呃我们的sample code，还有cargo那report部分就是交在race scope上面讲。

就是前面提到的那几题要注意大额，我们的作业的，大概是七月一号的23。59分，那我们不接受指标，所以呃请大家额可以的话就尽早交交，然后bonus不玩，就是会比这个晚一个礼拜。

那submission到until co的format，这边是你要去把你的扣缴做缴掉时候，就是呃用student id底线通过实物去做角交，然后这部分额就是记得要去交交。

然后不要上传你的model或是data set好，那这边regular zation的部分，应该是跟额前面几期作业一样，就不仔细讲究，大家注意不要呃违反呃这这些规定好，那如果有任何问题的话，可以呃。

我建议是同学是在n two cor的呃，discussion board上面去讨论，或是呃记一秒钟的话，记得要用开头，要用中括号，通过15好。



![](img/fbd9561f458f1a21f83ba8520b44bf05_14.png)

那额最后部分就是呃大家应该有听过呃，讲过几次，就是大家如果还没有填这个后侧问卷的话，大希望大家去填一下，那这次PL扣可以扫一下，那呃不知道关于作业的部分有什么问题吗。



![](img/fbd9561f458f1a21f83ba8520b44bf05_16.png)

好那如果没有什么问题的话，快大家跟大家看一下我们这次的sample code。

![](img/fbd9561f458f1a21f83ba8520b44bf05_18.png)

那额sample code部分的话。

![](img/fbd9561f458f1a21f83ba8520b44bf05_20.png)

就是额前面答案应该不用太男性，就是额预先检查GPU。

![](img/fbd9561f458f1a21f83ba8520b44bf05_22.png)

还有download data下set的部分，那这边就是呃有时是不需要去动它的。

![](img/fbd9561f458f1a21f83ba8520b44bf05_24.png)

那这边是in a library。

![](img/fbd9561f458f1a21f83ba8520b44bf05_26.png)

Import importation，我去fix选择CY好，那这边主要额，跟前几期做的可能不太一样的部分，就是因为在intemea link的时候，我们在in the loop需要去呃。

就是不需要算到呃。

![](img/fbd9561f458f1a21f83ba8520b44bf05_28.png)

gradient在呃，就是呃我们要import的一个是functional forward这个东西，那就是只去forward这个方程。



![](img/fbd9561f458f1a21f83ba8520b44bf05_30.png)

但是不要去上他的GRA点，所以这部分的扣其实呃助教也是写好。

![](img/fbd9561f458f1a21f83ba8520b44bf05_32.png)

就是在我们的classify2里面有一个就是正常的，一般的forwards会像鬼一点的forward定在这里。



![](img/fbd9561f458f1a21f83ba8520b44bf05_34.png)

那如果是functional forward的话，也是要大写好。

![](img/fbd9561f458f1a21f83ba8520b44bf05_36.png)

就是如果呃就是在写to do的时候，记得有这个functional forward可以去用。

![](img/fbd9561f458f1a21f83ba8520b44bf05_38.png)

那这边create label，就是呃，根据你的N位跟K下个数去产生你的label。

![](img/fbd9561f458f1a21f83ba8520b44bf05_40.png)

然后算accuracy。

![](img/fbd9561f458f1a21f83ba8520b44bf05_42.png)

那主要同学需要注意的部分就是呃，首先这个base server就是投影片里面提到的，transfer learning的agent，那呃为了consistency，所以呃这边的input。

format都跟neal line的server是一模一样的。

![](img/fbd9561f458f1a21f83ba8520b44bf05_44.png)

那大家可以去参考一下这个呃，transfer learning的做法。

![](img/fbd9561f458f1a21f83ba8520b44bf05_46.png)

那大家主要去做的部分就是有两部分是METALLISA。

![](img/fbd9561f458f1a21f83ba8520b44bf05_48.png)

下面这边in the loop，有一个呃这边的to do然就是你要去啊，没额看根据你是input的什么样的meta类方法，如果是meal的话，你可能就要这边呃。

把它填上inner lumemo的update wor，然后把额记得就是填完之后把这个呃，not implement to error comment掉。



![](img/fbd9561f458f1a21f83ba8520b44bf05_50.png)

然后才会正常的跑好，然后第二部分就是在outer loop的update。

![](img/fbd9561f458f1a21f83ba8520b44bf05_52.png)

就是在这个地方去finish它out呃，就是根据你的METALLIORG去去填上他的outlook的update。



![](img/fbd9561f458f1a21f83ba8520b44bf05_54.png)

will那一样就填完之后记得把呃这行command掉。

![](img/fbd9561f458f1a21f83ba8520b44bf05_56.png)

那呃做完这几件事之后再呃好。

![](img/fbd9561f458f1a21f83ba8520b44bf05_58.png)

这边的话是同学们去设定的呃，Have a parameters，不过这边呃大家应该不用太担心去调这个部分。



![](img/fbd9561f458f1a21f83ba8520b44bf05_60.png)

就是如果呃你的呃，METALLINN的algorithm是正确的。

![](img/fbd9561f458f1a21f83ba8520b44bf05_62.png)

input的话，就是理论上不需要调节的参数就可以过。

![](img/fbd9561f458f1a21f83ba8520b44bf05_64.png)

我们呃刚刚提到的那几个背算好，那还有一点要注意的是，在train的这个block，我们一开始的solver是指是用base as soover。



![](img/fbd9561f458f1a21f83ba8520b44bf05_66.png)

那这部分就会去跑transfer learn the agent，那如果大家把to do f填完之后，记得去把这个server改成呃meta。



![](img/fbd9561f458f1a21f83ba8520b44bf05_68.png)

那他就会去让说你额，根据你IMPLEMONMETALLI的方法去让你的METALLINOGM哦。

![](img/fbd9561f458f1a21f83ba8520b44bf05_70.png)

那跑出来的结果大家会像呃下面就是有呃。

![](img/fbd9561f458f1a21f83ba8520b44bf05_72.png)

CHING的XX跟VIATIONACCUR好。

![](img/fbd9561f458f1a21f83ba8520b44bf05_74.png)

那最后这部分的话就是不需额同学去动的，因为呃如果动的话。

![](img/fbd9561f458f1a21f83ba8520b44bf05_76.png)

可能改到顺序就上传卡狗的话，结果就很奇怪，那同学可以去改的话，就是这一个变数，就是你可以去改，说你在test点的时候。



![](img/fbd9561f458f1a21f83ba8520b44bf05_78.png)

你的inner ching step到底是多少，那其他部分应该都不需要去动，那最后的话会额有一个传承，一个奥put点CH，那就把这个奥put点CP上传到卡狗。



![](img/fbd9561f458f1a21f83ba8520b44bf05_80.png)

那扣部分应该就这样，那大家对CP的部分有什么疑问的吗，嗯好，那如果大家没有什么问题的话。

![](img/fbd9561f458f1a21f83ba8520b44bf05_82.png)