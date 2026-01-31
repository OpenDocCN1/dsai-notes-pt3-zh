# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P35：作业说明 Homework4 - AI算法工程师Future - BV1ruqABeEFX

哦哦那我是负责对作业室的助教，那真正作业室的内容是要做secure的，可选好，那这是今天的outline，我会先讲一下这个task要做什么。

然后我们用的data asset和一些reprocess用的技巧，还有这四个模型跟架构，然后在这些face派跟首先report部分，然后跟一些开发一下子好，这次作为主题就是SATTENTION。

那就是它是以google提出的attention，使用流行这个数里面提到一个概念这样子，那这次作为目标是希望同学们去了解，就希望transformer，那关于transformer的影片的话。

右下角的链接是就是教授去年的那片，可以看一下这子好，那这次的任务是secreed application，那他经常就是input是一段的语音，那你的model要能够选定说这段语音是哪一个。

Speaker，这这样子算算是有分类的问题好。

![](img/33791df696a3000667834298814d2ed1_1.png)

那再来一次这次作业，我的data arset，那这次用的是一个叫做rust lab two的data Upset，它是一个在真实世界录音的一个data塔，set这样子。

那training data a的量大概是5万6000卢比，然后testing data a是from public produ个4000这样，然后总共会我们从里面选出了随机选610克。

来当做这次的用的data塔啊，原本等腰三角形可以放在右下角好。

![](img/33791df696a3000667834298814d2ed1_3.png)

那再次beta three processing的部分，那基本跟作业二是很类似的，只是少做了最后一步跟B习题，那作业是用VC1把，没有special green当成嗯那个叫什么MMCC对。

指的是用的是MC进步的，没有search pr这样子，那有兴趣了解的话，也可以看右下角。

![](img/33791df696a3000667834298814d2ed1_5.png)

这个也是宏毅教授的上课录音好，那再来一次data set载下来之后的for reman上怎样好，那目录底下会有这些东西啊，主要会有三个点JSON档，那第一个是关于meta data的资讯。

那meta data的资讯我等下之后会跟大家讲解一下啊，还有test testing data塔的资讯，跟matting点jason making点JASON。

就是因为呃我们speaker的id是用string，那就是要把它转成用数字来表示这样子，然后再就是呃每一笔语音那显示这个UTTR，然后又认真写点TT这样子的好。

那meta data uinjson点开来之后，主要会有两个东西，第一个是n max，那它是呃没有fresh grad的来源证，但亚洲这是作为话语可以用理它，那主要应该是speakers那个部分。

那他speakers下面就是会对呃，就是speaker下面每一笔都会是这个steep，就是这个steeper讲的语音这样子，然后下面还有个那它里面有两个东西，一个是feature path。

Feature type，就是那个被比邻的白名称，然后mail live就是这里有一个长度，那应该可以注意到说，这是像这里有两个比一比零，那一个是435，一个是长度是490，那价格比零长度不一样。

那长痛不友好，我们可能在训练方上面不方便。

![](img/33791df696a3000667834298814d2ed1_7.png)

所以为了解决这个问题的话，我们会用一个叫做DEFASTERMETATION的技巧，把就是每一笔笔的长度都弄到一样，那可以看这个例子是说就是现有量低于零，但它们的长度都不一样长，那我们可以这么做。

我就是把它切成很多个segment，然后选一一段连续的segment出来，然后做他的代表这个名额就是的确样子，像这个例子就是选两个连续的segment，嗯好那再来次就是作业的model的架构。



![](img/33791df696a3000667834298814d2ed1_9.png)

那基本上input就是一段语音，然后是处理好的，然后会丢到有点coder的东西里面，那encoder之后的事情就是把做一些特征抽取，抽出来，变成一些feature这样子，那因为feature的数量很多。

我们需要做一些DC模拟，这样后面处理会比较方便，所以我就把它丢到ply layer里面，然后跑出来就变成代表这个，代表city input的representation，这样子啊，把这东西抽出来之后。

我们再丢到一个01262里面做，就是production的动作，然后最后得到一个output，那output应该是代表没嗯，这里已经是那个speaker了嗯，几率分布这样子下载，那就应该是600。

就是我们现在总共621克下。

![](img/33791df696a3000667834298814d2ed1_11.png)

应该会是一个600维的factor好，那再也会讲一下，就是过各个ASY的方法，那很好，不用在意他声音好，就是那simple备赛就是你考森破课，如果就是主要带大家认识一下code的架构。

我待会讲解一下声波课，然后这方法我先大致介绍一下，等下会再细讲，然后medium bas赛，就是基本上都是去调动一些transformer的参数，然performer是编号，然后双杯赛的话。

我们会要求就是去contract和conformer，那什么是conformer，我等下会讲，然后最后是boss spline部分，为他同学只做两个东西，第一个是self attention ply。

第二个是avitive market soft max，那这两个等下你会讲好，simple备赛大概就是考生扣得过嘛，然后他发的一个分数大概是0。60多左右嗯，那确定的时间大概30到40分钟。

但扣个免费版放就跑出来对，所以他训练其实蛮快的好，那再来是media baseline的部分，那就是这个后跑完之后，你可能发现腿功能是不太好。

那可能是因为这个model有点open for armeatize，所以我们需要做一些把参数调动，比如说像它最后一层的fd layer，这边可能有点太复杂，我可能可以试试看。

就是比如说把这两个就是把一层其中一层一掉，看图功能时会变好，或者说就是transformer以后，对不对，它的header的数量设置不一定要这么多，你也可以调多看看拔变多或变少。

看performance变得怎么样啊，或者是这个d model，那d model是就是要先把你的input，因为我input经过一层叫做PRENET东西，那就是我们把input投影到。

投影成d model的这个维度，这样子对那d model也是一个可以调动的参数，那最后一个是下面这个被总结掉的，就是self有点encoder，那它基本上就是你可以把你上面这个encoder。

layer用n enttransformer holder包起来，那就是因为要把它们叠起来的概念，然后error就是你要叠几层，比如RERR这二就是叠两层这样子，这都是可以调动，单看参数好，那再次哦。

我忘记讲了，确定时间确定的时间大概是呃，我估是一到1。5个小时，然后也是在COLAB上面就可以跑得出来这样子，那他的花呗杯赛的分数是0。70375好，那再来是川face side的部分，那双黑赛的部分。

我们这边的要求是，希望同学们可以constrike conformer出来，那这边有个电子是原本paper连接，我等会大概讲一下它的架构好，那他就基本都是一种transformer变形。

就是把用像sample cos，用transforming coder当做我们的主要领code，那所以同学们可以试着把这个东西换成哦，收入换成confirm，然后看看沟通的怎么样好。

那这个训练时间应该会比较久一点，所以预计预计的全程餐大概是3~4个小时好，那public bas赛的分数是0。77750。



![](img/33791df696a3000667834298814d2ed1_13.png)

这样哦，那这个是conformer的架构图啊，基本上component主要的是这个部分卡通的BLOX，那它里面的东西其实跟transformer很类似。

只是它多了一层叫做contribution nor9的东西，那诶这这个会挡刀这样，然后把它按紧藏就好，按你藏好，OK那卡的路数的话，就里面有什么呢，里面基本上都是一些有些是用类的东西。

那他为什么要做这些事情，就要练三大FAQ啊，这也是report的东西，然后有一些point wise conution，或者是pair wise conution，那如果要知道这些是什么的话。

建议可以去看，也是教授去年上课的录音，有个叫做network conversion的主题，也有提到这些东西，这样子嗯，那最后是boss space line部分，好会希望同学们实做两个东西。

第一个是silver tension的ping啊，第二个是a this is marin soft max，然后去构成一个performance这样子，那我自己劝的话，是在开口上面劝。

然后劝大概两个小时多一点就可以跑出来，那他的分数大概是0。8600，那我先讲第一个silver entro处理，就是前面的马斗架构。



![](img/33791df696a3000667834298814d2ed1_15.png)

可以发个柏林北日吗，那这把就是因为飞车这么多吗，想八就everyday成一个可以代表input的feature，这样子对，所以我就会透过云端服务的方式。



![](img/33791df696a3000667834298814d2ed1_17.png)

那在这次的code里面，我们只用名谱里，就是直接去平子，就把你一开始扣的得到了2F，也取一个平均变成零，It is decoration tation，那你如果可以试着把这个方这个名名图里的雷。

也换成用self a tention的方式呃，呃普通型理论上来说变得更好啊，paper里就有放在这里，因为它的概念其实没有很复杂，所以就是大家有兴趣可以看一下好。

那再来第二个是a this is my rosoft max啊，哦就是呃一般分类的模型，比如用到SOPX的话，你model通常会有一个或decision founder里的东西。

它就是用来隔开两个class，比如cs在上面，然后在decision boundary下面就是class two这样子，但这种这种mode的问题就是说，如果你觉得testing的时候。

那个呃人们开始把东西全部调配到这里来，他就被换成pass to，这可能会有一些不够准确的问题，那就有人提出一种方法叫叫做gto modern so max，那他就是要求你原本的model。

在呃原本自由的design founder上面硬要加上，也就是加上一层MARIN，让你两个class可以分得更开来避免这个问题，那人手taper也住在这边，就大家进来看一下好啊。

再来是gradient的部分，那之最一开始就是已分类的CURACC这样子，那每个杯盖的public和private都是各得0。5分，然后交code的话就会有两分。



![](img/33791df696a3000667834298814d2ed1_19.png)

然后再report，所以report占了四分，这样子好，那你交上来的点CSD档的话，第一行就是第一个role，该就是ID，然后跟category，然后用逗号分开哦。

我知道这就是那接下来的是你每一笔REDITION，就是这一笔语音，然后跟它对应到的speaker id，这样子也是用逗号分开，它总共应该是拉前行，要么就总共拉线笔，这样子好。



![](img/33791df696a3000667834298814d2ed1_21.png)

那扣的就是扫描到NTU库上，然后格式就是你的学号10号十号当开头，然后底线作业时间SP这样子好，那再讲一下，首先report的两个问题，那第一个是就是请同学们简单的介绍一个。

transformer的变形，比如说component就是一个或者是其他的搭配，就是网络上搜寻看看，这样子他总共占两分啊，第六题就是刚刚提到的，是请同学们就简单的解释一下。

为什么加上convolutional layer，到transformer上面可以去，就是boss它的performance啊，那这题也是两分，那daylight的部分就是三个就cos Mission。

然后HAO跟你report都是三个礼拜，就是4月1号要交出来这样子，然后没有内少女神好，那这是写的link就是开口的领，然后simple co，然后跟就是用刚data就是data set得。

并跟原始data set就是刚讲的MARX来处的联系，那regulation的部分就是基本都是不要抄袭，然后也不要人工的去改那个proposition，然后也不要把你扣的或任何字。

就别说file分享给你的同学或者生物之类的，然后也不要公开账号去教你超过五次，然后也不能用turn model或者一些额外的data，那如果违反的话，就是女儿的成绩就乘确实成绩就乘0。9，这样子好。

那如果有问题的话，是可以到nt u cool讨论板上面提问，或者是email给就是助教形象，但建议用的就入库这样子，然后你email应该用作为空work for当做开头，但我们不会受理。

然后接R的时间是，英文的话是礼拜五晚上的十点到11点，然后中文的TL的时间是额，礼拜二的晚上八点到九点。



![](img/33791df696a3000667834298814d2ed1_23.png)

好啊，这次稍微提一下，就是我为什么cod上传到客户端之后，他素材看起怪怪的，就是它变两格，那基本就可以调整，所以如果你觉得两格太丑的话，你觉得上面的东西点开，然后点setting就可以把素材看一下价值。



![](img/33791df696a3000667834298814d2ed1_25.png)

这句话出，好准备要跑跑play是吧好诶，大家有问题要问吗，哎来这边的，字数我们没限定字数哎，但其实我们没要大家写太多，就是简单的介绍就好了，单笔录像这个诶，不然我我们要限定制数吗，没有啊。

我们就这样子就好了，哎没有要大家写很多，这样子啊就不限制数，就那是尽量简短说明。

![](img/33791df696a3000667834298814d2ed1_27.png)

那就开始啊，那就继续吧，好那接着就来看下神偷空嗯。

![](img/33791df696a3000667834298814d2ed1_29.png)

那就是后边四个好，那一开始就是download们的data set，那我们是不是把data set都放在GITHUB上面，所以就直接WEGA下来，然后cat起来之后解压缩，基本上data set就好了。

我要直接试着跑，没事我要试着跑嘛，还是就讲过去就跑不完吧。

![](img/33791df696a3000667834298814d2ed1_31.png)

对我就跑不完，那就算了，好那再来就是fix下REDC。

![](img/33791df696a3000667834298814d2ed1_33.png)

保证你可以reproduce一个结果，这样子。

![](img/33791df696a3000667834298814d2ed1_35.png)

那DATASET里面的form me刚刚也提到了吗，那这边就是data set里面的东西啊。

![](img/33791df696a3000667834298814d2ed1_37.png)

基本上是不用动的，因为就是多方写好对。

![](img/33791df696a3000667834298814d2ed1_39.png)

所以其实可以不用动它，然后再是data loader会用到的一些防选项。

![](img/33791df696a3000667834298814d2ed1_41.png)

colab batch这些东西，那基本上也是不太需要去动它好。

![](img/33791df696a3000667834298814d2ed1_43.png)

主要要动的地方应该是model的架构，这边。

![](img/33791df696a3000667834298814d2ed1_45.png)

![](img/33791df696a3000667834298814d2ed1_46.png)

好那就是我们model架构，就像刚刚讲的，就是先把input input进来的引导，应该说已经处理好了，那个mail special green投影到DEMODEL这个维度。

然后再就是会有encoder，encoder做的事情，就是在把做一些特征抽取这样子，然后再还会过一层predict layer，就是它是linear layer组成。

然后就是把你encoder output。

![](img/33791df696a3000667834298814d2ed1_48.png)

这投影到正确的维度上，这样子对，所以就是。

![](img/33791df696a3000667834298814d2ed1_50.png)

大致上是这样，然后。

![](img/33791df696a3000667834298814d2ed1_52.png)

然后刚提到的ping的东西是在这里，就是他会把output做一个命的动作，这是这叫名普领，就是，直接把全部的encoder output作为直接取命，当做是这笔include recipation。

那同学们就是self attension处理。

![](img/33791df696a3000667834298814d2ed1_54.png)

就是把这个换成用self attention的方式做好好。

![](img/33791df696a3000667834298814d2ed1_56.png)

再就是learning reschedule，就是这样就是会有warn up的阶段。

![](img/33791df696a3000667834298814d2ed1_58.png)

然后跟training session，那这边同学们有兴趣的话。

![](img/33791df696a3000667834298814d2ed1_60.png)

可以试试看，不同的就是learning reschedule的schedule的方式，这样子好啊。

![](img/33791df696a3000667834298814d2ed1_62.png)

model function基本就是把你的发一个batch，就是喂给model，然后产出对应output，讲lost跟EQUACY这些好。



![](img/33791df696a3000667834298814d2ed1_64.png)

那再来是BDATION的部分。

![](img/33791df696a3000667834298814d2ed1_66.png)

就是这周考of validation code。

![](img/33791df696a3000667834298814d2ed1_68.png)

这样子他这边应该也是不太需要改动它好，那再就是主要的就是training function会用到参数。



![](img/33791df696a3000667834298814d2ed1_70.png)

大概就在这里叫batch size或者是NEWORKER，那这是给data hellogo用的，然后一些vitation step，这就是你每多少个step要跑一次validation。

他这边是预测是2000，然后went up state就是learning reschedule，它word aris的st的数量预设是1000，然后每1万个step我们会存一次model。

就是最好的model这样子，然后预设总共是跑7万个step，那想法更多就改成别人就好了。

![](img/33791df696a3000667834298814d2ed1_72.png)

对，那。

![](img/33791df696a3000667834298814d2ed1_74.png)

那再来是influence部分，就是inference DC在这边，然后其实这些东西基本上都开，需要动它，就是它是套inference用的，然后如果你呃，你要漏着别的。

应该说你要落的checkpoint就是写在这边，然后output file path就写在这边这个CONFIG这边，这样子主要应该就这样嗯。



![](img/33791df696a3000667834298814d2ed1_76.png)

![](img/33791df696a3000667834298814d2ed1_77.png)

好，哎那我这样好。

![](img/33791df696a3000667834298814d2ed1_79.png)

有同学有问conformer需要自己实做吗，还是可以使用套件，可以使用套件，但你也可以自己试做，就是你都可以很freeze，对我记得是不是有个套件有bug啊，记不记得bug吗。

我记得有个套件是去年很常用这卡，这个跑起来，然后但是他跑的时候那个memory会用开会用很多，这样哦对记不记得详细，然后大家就抱歉，这次还是可以跑的，我试过就是应该是没有这个问题。



![](img/33791df696a3000667834298814d2ed1_81.png)