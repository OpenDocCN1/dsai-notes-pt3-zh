# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P64：作业说明 Homework8 - AI算法工程师Future - BV1ruqABeEFX

![](img/9403bbde9ce8e895b3dec0135918d9e9_0.png)

嗯嗨大家好，我是这次负责作业吧的助教，那我们这次作业要做的是annamely detection。

![](img/9403bbde9ce8e895b3dec0135918d9e9_2.png)

这边是online呃，一开始我会讲一下这个task要做什么，然后接下来讲一下我们用的data，那接下来就是呃方法部分，也就是auto encoder，然后呃讲完方法之后。

那我们就要呃讲一下我们要怎么evaluate，这个我们圈出来的model，然后最后是呃baseline的部分，还有两个report questions好。



![](img/9403bbde9ce8e895b3dec0135918d9e9_4.png)

那就是我们这次要做的是unsupervised的，Anamma detection，也就是说呃我们给给你们的资料，都只会有正常的资料，所以也没有level，那我们的目的是想要劝出一个model呃。

使得说在inference的时候，就just testing的时候可以判断出呃，呃这些未进来的资料是正常的，或者是呃不正常的，然后这边举个例子哦，呃假如说我们在圈内的时候。

喂大堆正常的猫的图片给model看，那我们model就或许可以呃去看出呃training data的distribution，那在testing的时候呢，如果我们为正常的猫给model看。

那他可能就会告诉我们哦，哦这张图片是正常的，那如果我们把有戴口罩的猫的图片喂给model看，那model就应该要告诉我们说，呃这张图片是有一些异常的情况的，因为我们在training的时候。

都没有看过有戴口罩的猫。

![](img/9403bbde9ce8e895b3dec0135918d9e9_6.png)

好那这边是我们用的data额，我们这次用的training data会有10万张的人脸，那testing data ta有大概总共2万张的人脸。

那1万张是跟training data a一样的distribution，那我们这边level成零，那另外1万张是从另外一个distribution抽出来的图片，那我们这回label成一。

也就是呃异常的资料哦，那下面是呃data的部分，data format的部分，那我们这次会会给一个呃data，然后底下会有training set点NPY，还有testing set点NPY。

那这两个档案里面分别呃放一个N派array，那ship大概是下面这样子。

![](img/9403bbde9ce8e895b3dec0135918d9e9_8.png)

那接下来是方法的部分，而如同老师上课所讲，呃，anama detection或呃可是可以用呃，auto encoder来做的，也就是说我们在training的时候。

为一大堆training data给这个auto encoder，然后想办法让auto encoder去呃，重建未进来的这些data。



![](img/9403bbde9ce8e895b3dec0135918d9e9_10.png)

也就是这些图片，那在testing的时候，如果有异常的图片。

![](img/9403bbde9ce8e895b3dec0135918d9e9_12.png)

也就是跟training data呃不像的图片，未进去这个auto encoder，那这个auto encoder就很有可能没有办法去重建呃，这个位进来的图片。

那这时候也会有呃大的reconstruction loss，那利用这个呃reconstruction loss，我们可以判断说一张图片是不是ANNY好。



![](img/9403bbde9ce8e895b3dec0135918d9e9_14.png)

那这是大概的流程呃，第一步就是我们要change一个auto encoder，然后让这个auto encoder的reconstruction error是小的。

那在inference是inference的时候呢，我们可以用这个reconstruction error，当做我们的ne score，那这边annamely score就可以呃。

看成一张图片异常的程度好，所以说一张图片呃，如果从额，如果你没有看过这张图片的话，那很有可能你丢到这个你圈出来的auto encoder，那这个reconstruction error就会是很高的。

那同时呢，这个enemy score，也会是我们最后要缴交到cargo上面的呃。

![](img/9403bbde9ce8e895b3dec0135918d9e9_16.png)

prediction file好，那我们来讲一下evaluation的部分，那我们这次要的要用的metric是ROCLU，C score，那在那为什么我们不用accuracy score呢。

是因为说呃我们的model的output output会是ANNAMISCORE，然后如果我们想要判断，说一张图片是正常或是异常的，那我们还需要一个threshold去呃切。

说高于这个threshold会是ANEMELY，然后低于这个threshold会是呃正常的图片，那这样很麻烦一件事，就是你有2万张图片，那你会有很多种service hole可以去切。

所以说这不是我们主要目的，我们只想只是想要呃圈出来的model，告诉我们一张图片异常的情况有多大就好了，好，那下面是roc curve的一些想更详细的介绍。



![](img/9403bbde9ce8e895b3dec0135918d9e9_18.png)

可以去WIKIPEDIA上面看，那接下来讲一下这个roc i u c score。

![](img/9403bbde9ce8e895b3dec0135918d9e9_20.png)

是怎么算出来的，好，那嗯，这个roc a v c score可以想象成在不同three so的，然后我们去看一下他们的force，发positive rate，还有true positive rate。

分别是多少，然后画出来的一个curve好，那呃注意一下，就是我们随手是从由大往小位移这样子，那假如说在这点他的false false positive sample，就呃呃先说一下呃。

绿色的这个distribution会是呃normal data的anemely score，呃，也就是偏小的对，然后这红色的这个distribution会是呃anami data的呃。

Anammi score，所以看起来是偏大的，没有错好，那横轴就是ENEMISC了，对，那我们这时候先把third so定在0。5，那我们可以看到说a false positive rate呃。

false past tvt就是呃整个绿色这个面积底下，这个大于这个street Sol，而且是normal data的是呃数量有多少，那这就是false positive rate。

那true positive rate也是类似的。

![](img/9403bbde9ce8e895b3dec0135918d9e9_22.png)

呃概念好，那我们可以看到，假如说这点好了嗯。

![](img/9403bbde9ce8e895b3dec0135918d9e9_24.png)

呃用这个threshold的那force past twork，可能会在这边就是很就是会很小，然后true positive rate占了很几乎几乎所有的data了。

对然后然后最后画出来的curve就是会长这样子，因为呃起点是零零，然后终点是一一，也如同刚刚所说的，THRESOL是从大往小位移，那我们可能一开始THRESOL可以切在这边。

那这时候false positive rate就会是零嘛，因为它没有任何高于呃three SSO的资料，那到最后就随手一直位移到这边的时候，呃，他的false positive rate。

还有true positive rate都是一嘛，因为全部的资料都高于64RECO，那好，那这边也有另外一张图片，可以去比较一下这两个的好坏。



![](img/9403bbde9ce8e895b3dec0135918d9e9_26.png)

那我们这边就用实际的例子来算一下，Roc a u c score，那我们这边举五笔的资料，然后这边是model output出来的NAMISCORE，然后这边是我们的ground truth。

就是呃你们不会拿到的，然后这是你们要output出来的东西，对，那我们先嗯对score来salt就会变，会变右边这样子好。



![](img/9403bbde9ce8e895b3dec0135918d9e9_28.png)

那我们可以去计算说呃在每个不同的ths hold，然后他的false positive sample，还有true positive，true positive sample有多少，那一开始呃。

我们可以切在86万和84万中间。

![](img/9403bbde9ce8e895b3dec0135918d9e9_30.png)

可能切个85万，当service凑，那这样子。

![](img/9403bbde9ce8e895b3dec0135918d9e9_32.png)

那这样子false passer ti呃的sample会是零嘛，因为这呃大于这个threshold的资料只有一笔，而且它的level是一，所以它的true positive sample数量是一。

然后接下来我们可以在呃，84万跟25万中间切一个threshold，那额这边的false positive就会增，就会增加一，因为你的label是零，但是高于这个水草。

所以你把他判断成他是ANEMELY，然后以此类推推，那最后呃就可以用出这十个值，就是false positive assample，还有true positive sample数量，那做完这件事之后。



![](img/9403bbde9ce8e895b3dec0135918d9e9_34.png)

我们要把它转换成rate嘛，就是除以它总共的额，就假如说false positive，是除以它总共的normal的data数量，那true positive要除以它总共的NI的data数量。

所以说呃fourth parity也要除以三，now true passity也要除以二，然后出来的值就是长这样子，然后直接画在额，直接画成roc curve，就用成右边的这个情况，那我们可以看到00。

5是对应到这个点，然后接下来是0。30。5，0。5，那会对应到这个点，然后0。30。33331，然后然后0。666667，然后一然后最后是一一这样子，那我们就可以去计算它的这个面积，会是0。833。

就会是我们的呃，最后的roc a u c school好，那我们来讲一下baseline的部分嗯。

![](img/9403bbde9ce8e895b3dec0135918d9e9_36.png)

simple baseline就是嗯我在sample for code有三种auto encoder，那三种auto encoder跑了都可以过simple base line好。

然后接下来是media basin，就是可能要请你们去调一下model架构，可能调浅或是调深，然后LETTERREPRESENTATION可以调多一点。

胆mansion或是少一点DMANSION都可以试试看，那strong的话，我这边是有呃，strong和boss的话不一定要用我的方法的，就是我的方法是可以过strong和boss，但就只是参考用。

然后moto motile encoder，auto encoder就是如右边这张图所示呃，呃一开始一张image v进去，可以位置会给很多个encoder。

然后这个encoder呃丢出来的representation，然后再丢到这个底decoder去，呃最后再抵扣出来一个reconstruction，Reconstructed image。

那这么做有可能好，是因为呃假如说你这三个OPENCODE，你这三个encoder呃的架构如果非常不一样，那你是不是就很有可能你这个image可以嗯，萃取出很不一样的资讯。

那可以让这个decoder更方便的去RECONSTRUT，出来这个image对。

![](img/9403bbde9ce8e895b3dec0135918d9e9_38.png)

然后接下来是boss的，是space line的部分，我们在train完AUTOENCODER之后，可以再多乘一个haer classifier来分辨说呃。

decoder出来的reconstructed images，是real的还是fake的，那就如这整个架构所示，呃real的话可能呃real的话会对应到真正的image。

就是image会过encoder，然后再过decoder，然后就变成real的reconstructed image，那如果是fake的情况，就是呃我们我们会在latent space里面去呃。

Simple random noise，然后丢到decoder之后就会变成fake的呃，呃reconstructed image，那我们想要训练一个classifier嗯。

去分辨说哪些是real的image，哪些是fake的image，那这么做目的就可以呃，这么做的效果就可以在呃testing的时候去呃，分辨说哪些是normal，哪些是呃anomaly。

就是对应到real，还有fake的情况，那classified的output呃，应该会是一个probability，就是说这张图片是fake的几率有多大。

那我们或许就可以用这个probability来去呃，当做我们的anne score，也就是说在应用在testing的情况下，就会是呃你一张图片越异常。

那他的classify output的那个fake的probability，就会越来越高，好那这是boss space sign的部分。



![](img/9403bbde9ce8e895b3dec0135918d9e9_40.png)

pro部分，那第一个问题是要求你们去介绍一个auto encoder，的变形呃，这边列的是VARIATIONALAUTOENCODER，那呃。

然后还要去列出一个variational auto encoder的优点，然后还有variational auto encoder呃的问题，也就是缺点，那原始的paper附在这边。

然后后面两个连接是教授过去的录影，那第二个快呃，第二个问题是呃，我要你们先去劝一个fully connected的auto encoder，然后去调整它latter representation的呃。

某两维就是一次调一维就好，呃可以怎么调呢，就是可以可能乘以2×3之类的，都可以试试看，就是这边是看你怎么调都可以这样，然后最后最后要你们附在report里面的会是model架构，然后以及呃你调整的方法。

那我这边有要求至少两个嘛，所以说还要你们附上呃一张原版的图片，然后至少两张的额，调整之后的reconsulting image，呃最后是呃去叙述一下嗯。

这些reconsulting image有什么不一样的地方，那如果你们调了没有的话，也没有关系，就是尽量去调调，看看呃怎样的调整会有不一样的变化好。



![](img/9403bbde9ce8e895b3dec0135918d9e9_42.png)

那接下来是grading的部分，那grading就跟之前的作业几乎都一样，就是simple bass line过了就加一分，然后median base line过了再加一分。

strong和boss都再加一分，然后有交扣的就两分，然后report去grascode grade scope上面交。



![](img/9403bbde9ce8e895b3dec0135918d9e9_44.png)

那这边就是呃prediction file的形式，额可以看到说就是image id跟ANAMASC，就是如同下下面所示。



![](img/9403bbde9ce8e895b3dec0135918d9e9_46.png)

然后coder要找到n to co，嗯注意一下那个嗯你要党名要用成以下的形式。

![](img/9403bbde9ce8e895b3dec0135918d9e9_48.png)

呃DAIRLINE会是定在5月13号的晚上，11。59分，那三个DAYLINE都是一样的啊。

![](img/9403bbde9ce8e895b3dec0135918d9e9_50.png)

这边是cargo，还有collab link，接下来是regulation的部分，那就是一样，你不能作弊，然后如果你用了任何其他的资源，你要去specify它。

那你也不能手动的去调整你的prediction file，那你也不能去分享code或是prediction file，去给任何活着的生物，那嗯你不能用其他方法去让你可以交，一天超过五次。

就是不能创账号之类等等的，那你也不能用额外的data，然后或是其他的pretrain models，那如果你第一次违反的话，你的最后成绩会乘以0。9，而且这次的作业算零分。



![](img/9403bbde9ce8e895b3dec0135918d9e9_52.png)

那对大大概就是这样子好，那如果你还有其他的问题，你可以去呃nt CORE上面问，或是email给我们，然后title要呃，开头要是homework8，好那接下来是讲解code部分。



![](img/9403bbde9ce8e895b3dec0135918d9e9_54.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_55.png)

好嗯。

![](img/9403bbde9ce8e895b3dec0135918d9e9_57.png)

这就是COLAB的code，那我们一开始会先装一些package。

![](img/9403bbde9ce8e895b3dec0135918d9e9_59.png)

等他装一下。

![](img/9403bbde9ce8e895b3dec0135918d9e9_61.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_62.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_63.png)

然后接下来就把data set下载下来。

![](img/9403bbde9ce8e895b3dec0135918d9e9_65.png)

那如果是在cargo上面做的话，可以直接呃用上传在上面的data。

![](img/9403bbde9ce8e895b3dec0135918d9e9_67.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_68.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_69.png)

然后就import1些package，先import1些package在这边。

![](img/9403bbde9ce8e895b3dec0135918d9e9_71.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_72.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_73.png)

然后接下来就把training data，还有testing ta去漏漏进来。

![](img/9403bbde9ce8e895b3dec0135918d9e9_75.png)

然后这边是呃FIXC的部分。

![](img/9403bbde9ce8e895b3dec0135918d9e9_77.png)

那这边有三种吗，三种auto encoder，第一个就是复利connected的auto encoder，那架构就是只有linear，这样子，可以可以可以看到说嗯它的维度是下降的。

然后encoder的维度是一直下降的，然后decoder是上升的。

![](img/9403bbde9ce8e895b3dec0135918d9e9_79.png)

直到说他把那个图片重建这样子，那还有CNN的auto encoder。

![](img/9403bbde9ce8e895b3dec0135918d9e9_81.png)

就是如同下面这样，然后第三个是VA1。

![](img/9403bbde9ce8e895b3dec0135918d9e9_83.png)

就是刚刚有稍微提到过的，好跑一线好。

![](img/9403bbde9ce8e895b3dec0135918d9e9_85.png)

接下来是呃呃data的处理。

![](img/9403bbde9ce8e895b3dec0135918d9e9_87.png)

就是在在这块。

![](img/9403bbde9ce8e895b3dec0135918d9e9_89.png)

然后这边就是一些嗯一些参数的设定，然后就是你的AIRPO卡，然后batch size，然后learning rate。



![](img/9403bbde9ce8e895b3dec0135918d9e9_91.png)

然后等等等等等，然后这边有三种model给你选嘛，那你就可以直接在这边去做操作，那你想要换成fully connect，你就打FCN好，那这边的criterion就是用MACDLOS。

也就是我们reconstruction error的呃。

![](img/9403bbde9ce8e895b3dec0135918d9e9_93.png)

lows就是Mac lows。

![](img/9403bbde9ce8e895b3dec0135918d9e9_95.png)

啊接下来就是training的部分。

![](img/9403bbde9ce8e895b3dec0135918d9e9_97.png)

嗯可以看到说嗯我们这边有存了两种model。

![](img/9403bbde9ce8e895b3dec0135918d9e9_99.png)

一个是呃Mac loss。

![](img/9403bbde9ce8e895b3dec0135918d9e9_101.png)

最小的，还有最后一个这样子，那我们先圈个几个EPOC。

![](img/9403bbde9ce8e895b3dec0135918d9e9_103.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_104.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_105.png)

好那这边先卡掉圈。

![](img/9403bbde9ce8e895b3dec0135918d9e9_107.png)

两个EPOC做好好。

![](img/9403bbde9ce8e895b3dec0135918d9e9_109.png)

那这边就是influence的部分呃，这边是把test data漏进来，然后model的trip point也漏进来，然后这是设定我们最后的prediction file的位置。



![](img/9403bbde9ce8e895b3dec0135918d9e9_111.png)

好执行一下啊。

![](img/9403bbde9ce8e895b3dec0135918d9e9_113.png)

这边就是去算我们的anema school，然后最后再把output到那个prediction file。



![](img/9403bbde9ce8e895b3dec0135918d9e9_115.png)

好那我们看一下这个prediction f，就是如同我们刚刚讲的呃，投影片讲的呃，这边会是ANNAMISCORE，就是data形式会长这样，然后就可以直接交到卡口上了。



![](img/9403bbde9ce8e895b3dec0135918d9e9_117.png)

![](img/9403bbde9ce8e895b3dec0135918d9e9_118.png)