# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P87：作业说明 Homework13 - AI算法工程师Future - BV1ruqABeEFX

![](img/dd0b56d9e28b5fd7ca666457662e66b3_0.png)

好大家好，我是这次负责作业13的助教，那这次作业的主题是有关network compression，那等一下我会先简单介绍一下这次的任务，然后还有这次用到data aset，再简单介绍一下呃。

在这次作业neal compression会用到的一些技术，然后还有这个coco competition，他的regulations，然后还有一些评分标准，再告诉你们要怎么样去过各个base line。

然后还有介绍一下讲解一下report的questions，那右上角的话是呃cargo competition的连接，还有呃collab tutorial的连接。

那呃可以看到这边有这个report question3之一的，两个collab notebook的连接，那这两个notebook括号，它就是呃纯粹是for这个report3之一的。

所以呃可以可以到你要写这个题目的时候，再去看，他是有关network printing的东西，那其实这三个COLLAB的notebooks都有相对应的，那cargo的notebook的版本。

在cargo competition的扣的那个页面上面，可以找得到，所以大家如果习惯使用cargo的话，也不用担心，都可以在两个平台上面都找得到，这样，那呃这次作业deadline是6月17号的晚上呃。

11。59分，那cargo跟nt CORE，还有grace scope的deadline都是相同的，请大家务必要呃提早开始做，然后准时缴交，我们不接受任何指教，好那接下来简单介绍一下这次的任务。

那我们这次要做的就是network compression，那network compression，它最终极的目标就是希望呃训练出一个呃，很小呃小的模型，但同时又可以兼顾它的performance。

对，那所以在这次的作业，我们就希望你们可以去训练一个呃，非常小的模型，然后去完成homework3的这个image classification的任务额。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_2.png)

对那所以我们使用的DATASET就跟呃homework3很像，那主要的差别就是在于evaluation set上面。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_4.png)

我们有做了一些调整，所以这也导致你不能直接去呃下载使用呃，原原先homework3的呃，这个资料还是请你们去呃使用专门呃，专门我专门制造给这次作业出来的，这个-11的资料集。

这样然后你们也不能去尝试去寻找呃，这个testing set的任何original的呃labels，那也不可以使用任何额外的data set，就只能用-11的DATASET去做训练。

然记得要用homework13的这个版本，不然你在predict的时候可能会呃出重大的错误，对，那接下来就简单介绍一下有关network compression的，各个这个作业会用到技术。

那这部分的话我不会花太多时间琢磨，如果你觉得你对于这部分还没有很熟悉的话，呃可以可以去呃，去年2021年弘毅老师呃录好的那个YOUTUBE影片，去稍微复习一下这些这些大的概念，到底在讲什么东西。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_6.png)

这样那我这边的话只会简单带过好，那首先是knowledge distillation，那这部分的话，其实就是我们希望去从一个已经呃，训练的很好的teacher network去去呃学习一些他的知识。

那这个student network通常是比较小的一个network，然后我们希望透过一些teacher的output，或者说hidden layer的representation去呃。

提取一些学习一些有用的资讯，那最常见的话就是拿output的那个probability distribution，当做一个训练的目标，希望student net可以去呃。

predict to跟teacher net差不多的probability的distribution，对，那这部分的话，我们会需要你们去implement一个loss function。

是有关knowledge，knowledge distillation的LOFUNCTION，那等一下在sample code时候，我会再更详细的呃描述要做什么事情，然后这边我们会提供你们一个呃。

Well trained teacher network，去帮你们做knowledge distillation这件事情，那这个teacher network。

他在-11的testing set上面的accuracy，可以来到89。9帕，然后对是已经足够你去做这次作业的，那当然如果你想要用呃，你自己PRETRAIN的呃，teacher network也没关系。

那就是呃，但是你要记得去follow homework3的那些那些rules，就是你不能去使用额外资料，然后你的teacher network是呃render ininitialized的。

就是你不能去使用任何的ptrain weight，你只能自己train from scratch，用这个-11的training set去train from scratch，对。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_8.png)

那接下来就到那个architecture design部分，那这部分的话，我们希望你们可以去呃，把DEADWISE跟point wise convolution layer。

去运用在你们的student network上面，那之后会会给你会给你们介绍说，Strong baseline，可能就是需要去implement这部分，才有可能比较有机会过好。

因为deadwise point as that deadwise跟point wise convolution，它就是一个比较呃节省parameter的一个一个network。

compression architecture design的一个做法，所以如果你们去实现了这个这个做法，你们就可以呃，用更少的parameters去达到，跟一般convolution类似的事情。

就是去提取额input each feature map的局部的资讯，还有input feature MAD，各个channel之间的资讯，对大家可以理解说就是deadvice convolution。

就是在提取呃各个input feature map局部的资讯，那他channel跟channel之间是还没有还没有咨询，会互相连通的。

那直到point wise这这个convolution的部分才去额提取，或者说额抽取出那个呃，各个channel之间才才会互相互相联通，去去做这个convolution，11的convolution。

这样可以这样子去理解，所以额只要呃就是通过一些简单的计算，你就可以，你就可以推导出下面这个这个parameter size，的这个比较，那可以看到，如果你是用standard的convolution。

就一般的convolution的话，你的model size就是那个conclusion layer的size的话，就是IOKKI的话就是input feature的channel size。

然后O的话就是output的channel size，那K的话就是那个filter的啊，JERNEL的size这样，那其实所以在可以看到在K比较大的时候，其实右边是非常。

右边这个implementation是非常非常有优势的，所以这也是为什么，我们会希望你们去把这个dead wise game and。

point wise convolution去实做在你们的student model上对，因为他他其实可以做到，类似于一般的conclusion的呃的这个事情。

但同时又又可以减少蛮多的parameter，好那接下来稍微讲一下，就是这次作业的一些regulation，那首先就是最基本就是你不不可以去share你的code。

还有你的prediction files，然后再来的话就是cargo的呃，每日submit的上限是五次，所以特别注意不要浪费你的submit的那个次数，然后再的话就是不能用额外资料，这点讲过很多次了。

请大家特别注意，那再的话就是不要找true label，testing set的true label这样，那接下来的话就是不要用pretrain model，也讲过很多次。

就是你一定要自己train from scratch，然后再来的话就是你违背了这些弱的话，你的总成绩就会被打九折，然后这些作业也会被以零分计算，对，那刚这边这边其实是呃最呃，各个职业都有了这个规范嘛。

那我们这个作业还有一些额外的规范去，第一个就是去限制你的student model的呃总参数量，那这边可以看到你的使用MOTO被限制在总参，总参数量被限制在100K这个数字上，也就是10万这个数字。

所以呃我们之后会教你们怎么去看这个，你们define好，student model的total parameters的数量，所以这点等下会讲解，但总之就是不能超过100K这个数字。

那样你散密到cargo的这些prediction file啊，他一定得是从student model呃，在不超过这个数字的server model influence，出来的结果才能丢到cargo上面。

对那呃之后我们也会，我们也会希望需要你们去cube and pace，里面的student model，还有呃torch，torch summary的一些结果，所以这点的话呃，请大家务必要遵守。

我们会去严格的查查这件事情，不不要去啊，乱撒密，你teacher network invalation的results，然后把那个leader board冲很高，那个是那个是没有用的，我们会去抓。

特别去严格的抓这一点，所以请不要呃乱撒密，你teacher network output的那个prediction file，你撒命的一定得是呃你的student network。

然后那个student network是不能超过10K哎，一一百K这个total parameters的这个数量的，那再来的话你的testing data只能用在influence上面，你不可以拿去呃。

比如说拿去给teacher network去呃，Predict shoole labels，然后再让student network去呃，Over feat，它这点是完全静止的，所以只要记得一件事情。

你的test data就是最后你拿呃influence呃，就是你student，你student network，Influence，在这些testing data上只能拿来做influencing。

不能来做其他任何事情，testing data部分对，那接下来就是呃，我们会教你们怎么用torch summary，这个cp package去计算。

或者是去测量这个额student network的总参数量，那再来的话就是ENSEMBLED的，如果你使用的ENSEMBLEDTECHNIX，在你的student model上。

就是你的那个prediction file的结果，是从多个student model的prediction ensembles出来的，那你要确保你的student model ma的总参数量加起来。

就全部加起来不能超过100K，好那接下来讲一下规定的部分，那其实跟之前的作业应该也差不多，所以report就四分，COSMISSION两分，剩下baseline，public private各0。5。

总共加起来十分，然后如果你是coco leader board上面的前三名的话，欢迎你写呃，你的做法让我们知道，那我们会帮你加一分，在你的这个这次作业上，所以你最多可以拿到11分，这样好。

那接下来是一些呃baseline的呃guide，那simple base line的话就很简单嘛，就是跑那个我们提供的simple code，然后submit就好了。

就应该可以过这个simple base e，那medium bassi的话，你就必须去试做刚刚提到的那个呃，专门给knowledge distillation的这个loss function。

然后去实做ko divergence的loss，然后在train的久一点就可以过medium baseline，那装备赛的话呢，你必须要去调整你的model的architecture。

用我们刚刚提到的这个deadwise and point，wise的convolutions去取代掉这个原本的CONUTION，然后让呃再这样取代掉之后。

你就可以去加深或加广你的model network，然后想办法去打造一个呃更好的架构，然后呃这部分的话，你可以去参考一些呃很有名的network，比如说mobile net，shuffle net这些。

那你也你也可以去用，就是任何你在homework3里面学到的data，augmentation的techniques，然后还有呃have a parameters。

你你就觉得home work3你做的不错，你可以直接把它移植过来，对teacher net上面也可以做一些呃，你觉得很很强的，data tail gentation这部分都是允许的。

那双倍赛的训练时间会来到8~12个小时，那这边给的所有训练时间，都是在cargo上面做过测试的，对那boss spine的话就是除了呃基本的knowledge，Distillation。

就是去学习最后一层output the probability distribution之外呢，我们还希望你们去试做一些更进阶的呃，knowledge distillation的做法。

比如说fit net是一个嗯，嗯蛮蛮蛮老蛮有名的一个做法，就是可以去从teacher model的hidden，layer的representation里面去做学习。

而不是只有学习最后面的那个呃output，再来的话就是像relational kd或DML这些，你们都可以自己去阅读原始的paper，然后去试着做做看，那再来的话就是你也可以让你的teacher。

或者是让我们给你的提那个teacher更再变得更强，那一样，记得一件事情，千万不要用额外data set，讲过很多遍了，就是希望大家不要不要额使用额额外点塔，这样。

好那接下来的话就稍微讲一下report question。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_10.png)

那我想嗯不然我们先跳到simple code上面去看好了。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_12.png)

然后我们之后再回来report question，这样该会额整体来讲会比较顺一点。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_14.png)

好，那大家可以看到，就是你们点那个caro competition的链接，应该就可以进到这边，那记得先先看过这边所有的rules。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_16.png)

然后去accept这个rules，然后接下来你就可以在code这边发现三个notebook。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_18.png)

那这个pruning tutorial跟network pruning example，都是for report question3之一的，所以这两个就比较呃，你们可以先先先不用碰。

可以留到比较之后再碰，主要是可以先打开这个notebook里面会有sample。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_20.png)

然后你可以去edit卡比，这样就跟homework3里面在使用这个cargo的呃，这个平台一样去呃看去下载这个homework13的data，其实就在这里，就是我你直接用cargo的话，其实很方便。

就可以看到所有的这些资料，然后包含我们提供给你的RESNET18teacher model，所以这边已经跟你说了，就是我们teacher model network的架构就是RESNET8的架构。

所以如果你要做更积极的，Not least detail distillation，可以去参考呃，the next8它它的模型架构，然后想办法去抽取一些资讯，这样那呃一样，我们这边就简单的概括一下呃。

额扣的部分，那因为时间关系，我就我就不做训练，然后我只提点一些，只讲解一些就是可能会比较有问题的部分，这样那首先因为torch summary这个package。

它没有预先装在那个cargo的image里面，所以呃你要先自己装起来，然后做一些package的import，然后这边CONFIG的话，你如果了解这个这些CONFIG是什么。

你都可以很free的去自由的做修改，这样好，那一样，这边我们就先跳过这里值设置random seed，然后还有create一个呃save pass。

然后这save pass就是到时候会放在这个save output，里面的这个save pass，这样那DATASET的话，这边就是让你去知道说，每个DATASET里面有多少资料。

那这边就是简单的一些资料的呃，呃trans image的transform，那这这部分的话就是testing的transform的话，你们应该是不太需要去做更改，那你们可以去做更改的。

应该是呃这部分training的transform的部分，那但是要记得就是我们提供的那个teacher network，他的input size是224，就是不是像你们home work三一样。

是128×128，它是224乘2242十，所以如果你们在调整这个，这个这边的参数的时候，记得如果如果你把这个参数调掉的话，就是你把它变成什么128或是256的话。

我们给你的这个teacher network，他可能没办法，就是呃如预期的，就是表现的像呃二四这个size一样这么好，对这点需要特别注意好，那这边的话其实跟homework3都蛮像的。

那这边额就是帮你们四则，就是帮你们实做出了这个dead wise point ones，合起来的这个convolution，那如果有兴趣的话，呃比较需要研究的可能是group这个东西。

那你们可以去参考一下PYTORCH它本身的呃，这个官网去了解group这个keyword，Argument，到底到底在这个convolution，2D里面扮演什么样的角色，然后在你们了解这个同时。

你们也会呃对这个group convolution呃有更进一步了解，这样那你会发现说deep wise conclusion。

其实就是一个呃specific type的group convolution，那这边也提供了各式各样的，你可能会呃想要拿来实践的architecture，design的一些呃，呃原始的paper这样好。

那接下来的话我们就来define我们的student network，那这边其实可以看到的是一个很简单的convolution，然后还有一些pulling layer组成的。

已经一个student net，那这边要记得请不要去跟动这个gas student model，你可以跟动的是gas student model里面的内容，你不能跟动这个这个韩式的名字。

或者说把它乱加argument，他就是一个呃我们可以去call的API，让我们可以去得到你的student name，你可以在这边额填写，或者是呃增加一些你想要的一些setting。

但是请不要动这个function的名字，还有他的argument，对所以可以看到这边我们会用同样的方式，就是跟自己同样的方式去去得到你的student model，所以这边不希望你去改这个函数的名。

称的用意是在这里，因为我们到时候有可能会去检查你们的呃，Sten net，然后也会去呃看你们的summary，就是这个summary，其实就是刚import torch summary。

所用那个套件得出来的结果，那他会去帮你做计算，说呃每一层的参数量啊，然后最重要的其实是这个total parameters，的这个数量在这边，那这个的话就是不能超过100K这个数字，所以要特别注意。

你可以design完之后呢，在run这个code blog去探索你的呃，student model的summary的total parameters呃，有没有超过厘米，如果超过厘米的话，你连试都不用试。

就是继续去修改你的student model，直到它就是不会超过100K，这个数字等于100K是OK的对，但是不要不要一一百，额不要超过100K这样好，那接下来的话呃。

就是在要来定义那个student model，那这边的话，RESNE8这个模型的架构对，然后把PRETRAIN设成false，然后再从刚刚这个input这边有一个checkpoint。

去load那个restless8的额，各个参数的weight在这边low load它的weight进来，然后这边有提到说嗯，如果你想要实做更积极拉拉力去DISTATION的话，你势必会去需要去看一下。

你使用的这个teacher network的呃原始码，所以这边就是放了RESNET它的原始码的链接，在这边，如果你们有兴趣的话，也可以去看一下，那呃值得注意的是。

这个teacher network其实是有额这么多的parameters，所以你跟呃，我们想要预计你们做出来的，这个这么小的model相比，你们其实会需要把这个T恤network压缩个有100倍。

压缩100倍小，如果你是用我提供的这个提前量过的话，所以其实还蛮惊人的一个数量，那你会发现哦，呃baseline，其实呃最后的boss space line跟teacher network。

其实只差了四五趴左右，所以其实我们花1%的这个parameter数量，就可以训练到呃，跟teacher man我只有四五帕差距的这个accuracy对，其实蛮惊人，那当然负-11。

这个大家set其实没有，因为它很大，所以也算是一个合理的结果，如果你的data压set再更大一点的话，可能就没办法呃，把student跟teacher的呃accuracy拉那么近，对。

那这边的话就是再简单勾述一下哪里，Age distillation，那这边最需要注意的是，你们有一个呃有关于knowledge distillation的last function，需要需要去十座。

那formula的话我打在这边对很很长一串，但其实没有很难，这个东西就是原本的cross entropy的loss，所以这个这个应该没什么问题，那最主要的话就是这个kl divergence的loss。

那kill divergence loss，它就是在呃呃因为我们要把teacher，teacher的LODGETS，或者说teacher output跟student output拉近嘛。

那ko divergence就是提供一个可以让他们建立起呃，可以去major他们之间的distance的一个一个function，那透过去等一下跑到哪里好，跑到刚刚原石里面去了，透过去呃。

minimize这个这个loss就可以去minimize teacher，lodges跟seven larges之间的距离，这样那这边也有till divergence lost的example。

那这个非常的呃，可能会对你们有非常大的帮助，所以建议是你如果不懂，你就直接看这个这个sample，然后直接把它太空进来，再加上cross entropy，再加上一些参数的设定。

阿尔法跟T都是呃模型的参数而已，而不是就是那个hyper parameter而已，所以呃就是把它加进来而已，所以应该不会太难，那如果你想要知道说呃，original的这个呃观念或者概念是什么的话。

就是kl divergence lost这个概念是什么的话，你可以去参考这篇原始的paper，它里面有稍微提到一下，就是T这个T这个have a parameter，是拿来做什么用的，好，那这边的话。

其实就是根据你刚刚前面的那个CONFIG，去选择loss function，那预设的话我们是使用cross entropy，所以在simple baseline里面并没有去使用到。

knowledge distillation的技巧，那就是纯粹根据train set的呃，true label去做训练，这样去做cross entropy的loss，然后去做训练，然后如果你要使用呃。

那就是knowledge distillation的话，你必须要把CONFIG里面的这个呃直接拉回去，看好，你直接把这个地方改成KD。

就stands for knowledge distillation，那你这边这个衣服就会选择到这个，你刚刚前面implement的这个bass function对，所以这是一个呃小细节。

请大家特别注意，那你当然也可以去实做你自己的custom的呃，一些advanced的knowledge，distillation的last function，那就是呃随便你要怎么定义。

这样如果你想要过boss的话，就可以自己去定义自己的呃last function好，那剩下的话其实都跟呃homework3，这训练过程其实跟homework3都差不多，那比较需要注意的是。

如果你要过medium的话，你这边teacher model，就是我后面会有这个大写的medium basline，你要把它注解掉，就是把这个呃注解掉，先这样。

然后就是因为那密电BAS赛会需要去distill，knowledge嘛，所以就需要teacher model，然me simple basin的话就不需要，所以medium baseline。

你只要把这个有medium baseline给他注解起来，我这边直接注解好了，注解该注解的地方，注解掉刚才注解掉的地方，然后这里这里有MEDI电备赛嘛，就把注解掉。

然后last function因为你的那个argument变了，所以要使用这个medium杯赛，这个loss loss function的argument，所以这边一样。

那后面的话REDATION这边也一样，我就不不不多做讲解了，这边有medium visi都把它改掉，然后是function也给他摆改掉，对那接下来的话就是influence，那influence的话。

他其实就是拿你刚刚训练完这个这个training的，这个student best的checkpoint，然后把它重新load进来之后去做predict，然后再把submission点CSV。

save到你的这个safe path里面，save pass是最早前面定义的，可以回去稍微看一下，对那这次是整个呃simple code的architecture，对好那，现在我们就来稍微看一下那个呃。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_22.png)

Grace scope，The report question，那其实我们这边蛮长一大串，但其实前半部分都是在copy and paste，所以第一题第一呃，1~1的话。

就是你要把你的整个student net去copy and paste下来，然后包含这个function对。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_24.png)

所以就是可以看到就是你要把哦，sorry这个，这个诶在后面。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_26.png)

这个整个block这个整个blog去给他CIN配置下来，然后这边就不做了，反正你们就知道是这个这个整个blog就好。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_28.png)

那第二部分的话就是你们需要把你们跑出来的，这个student network，跑出来的这个touch summary的结果也copy，and paste到这里面，那这部分的话应该也是蛮直接的。

那呃这个loss function的话也是一样。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_30.png)

Copy and paste，你的额，你自己试做出来的这个loss function，整个给他cup and paste。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_32.png)

我们会去一个你的实做的结果，这样，那接下来的话就是一些这个选择题，就是请你去稍微去不管是读论文也好，或者是上网查资料也好，去了解一下T这个GRAMETER是干嘛的，那其实老师的呃之前的影片也有稍微提到。

所以可以去找答案，这样那接下来的话就来到刚刚讲的，有给呃COLLAB两个notebook sample的呃，部分就是有有关network pruning的部分，那其实呃你们就根据这边描述的嘛。

然后先去看这个这个ptorch network prt的tutorial。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_34.png)

应该是这个这个tutorial。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_36.png)

然后去go through，他会有一步一步教你说呃，这个torch n n就这个prune的这个package。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_38.png)

还要怎么怎么利用。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_40.png)

你怎么利用它来它来做这个ever printing。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_42.png)

对那额接下来的话你就是要实做呃，pruning就是prove你的那个teacher network，那你也可以听prom我们provide的teacher model，所以这边就呃。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_44.png)

为了怕你们就是大家实做的方式不一样，我们提供了一个呃简单的sample code。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_46.png)

在这里面你就可以看到，就是假设我们ratio设0。2的话，我们要怎么去prom我们的model，这个model是在前面define，那当然这边要是可以，要是你的teacher network。

就是你要去想办法去呃load你的teacher network，或者说去load我们提供的teacher network对，那当然如果你不喜欢COLAB。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_48.png)

你也可以用这个这边的cargo的code，那这边要漏了，teacher model就很好漏的嘛，就是直接直接跟homework呃。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_50.png)

直接跟这个sample code一样，去load这个teacher的checkpoint对。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_52.png)

所以这部分的话你只需要嗯，因为这边我我只pron了0。2这个ratio，那你还需要做的事情就是呃去调整这个ratio，然后去去把这个model呃，evaluate在呃。

我们提供给你的复习的validation set上面的。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_54.png)

所以可以看到这边的accuracy，其实是a uvalidation set上面的accuracy model，Accuracy，然后这边是printing的ratio，所以可以看到呃。

我们提供了这个提取难度，大概在0。40。5，这边就会有一个大幅度的衰减，这样那你们需要闪避的就是这这张图，这张图对，那请不要试图去后置掉这个这个浮水印啊，因为因为你后置掉这浮水印的时间。

说不定你都可以直接拿来做完这张这张图的，就是没有很难这样，那我们也呃鼓励你去prune，就是做同样的这个图，在你的student network上，然后去观察说哦。

到底student network prune多少，它就会开始下跌，那teacher name pin多少，它就开始下跌，这样去比较说teacher和student，PN出来的结果的差异。

然后最后是一个选择题，就是根据这个这个package出来的。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_56.png)

这个pruning的方法，你根据这个tutorial，你去你去观察说哦。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_58.png)

到到底他怎么实做这个never promi。

![](img/dd0b56d9e28b5fd7ca666457662e66b3_60.png)

那这个实作方式到底能不能够真的去呃，reduce model的inference time呢，那这边有两个选项，就是选一个你觉得对的，那如果你真的不确定的话呢，你可以去测量influence的时间。

就是你可以去PRIN一个呃，print98掉，然后跟一个完全没有print的去测量它们，influence的时间，看他们到底差了多少，这样然后这边就是记得要select upload你的图片，这样的好。

那以上的部分大概是这样，那最后的话讲一下code，submission有一个特别需要注意的东西，就是我们这次除了code之外，我们还希望你们还需要你们去SUBMI呃。

你们student best的checkpoint，那这个东西的话，它其实就是跟你在下载submission一样，就是你发现你的上你的submission呃，冲的很高。

你就可以同时也顺便把这个student best s的，c k p t check checkpoint也下载下来，那这个东西它其实不会很大，大概四五百KB而已，所以不用担心，就是呃下载速度很慢。

或者是呃下载这个档案很大或者怎么样，因为他参数量很少，所以他这个checkpoint其实非常小，甚至有可能比你的扣子还要小，所以大家不用太担心呃，呃答案大小的问题，他应该是个蛮小的东西。

那report的话一样就是SUBMI到gray scope嘛，那这部分应该没什么问题，那嗯如果你有任何问题的话，欢迎在homework13的讨论区里面发问，然后也可以额再寄信给我们发问也都可以好。

那以上就是这次作业的内容好，那最后再麻烦大家帮我填一下这个后测问卷，就是machine learning这堂课的一个后测问卷，那这部分的话大家不用太担心，它，是它是。

它是不会完全不会影响到你的学习分数的，所以请大家一定要记得填这个东西，然后就是去扫个qr code，或者直接点这个链接都可以，好感谢大家，以上是这次作业讲解内容。



![](img/dd0b56d9e28b5fd7ca666457662e66b3_62.png)