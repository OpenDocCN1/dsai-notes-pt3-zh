# 强推！(2026最新版) 李宏毅最新课程：智能体AI【AI Agent】71集全！人工智能／机器学习／深度学习／大模型／LLM - P18：17-作业HW7 - RLHF - Ai人工智能工程师 - BV1QdzCB3Eu2

各位同学大家好啊，我是作业期的助教，那我们就来看一下这次的作业吧，好，那今天OLAY大概卫视我会先讲一下这个test overview，然后会需要你们做些什么。

然后最后是讲submission ingredient的部分，那第三页的话我有提供一些连接，那就是这是说各位同学可能会用到的部分。



![](img/fcd5a1e4bceb5baed30332b9358a103c_1.png)

这样。

![](img/fcd5a1e4bceb5baed30332b9358a103c_3.png)

好那在讲我们test之前，我们现在讲一下，就是跟之前作业五就是做supervise funity这件事情，跟我们现在要做的就是用IO去align model，这件事有什么不一样。

那在supervise fine tuning里面呢，我们会需要给他就是准备好的标准答案，去让就是模型记忆这些答案下来，但是呢在真实情况底下，我们会有很多就是开放性的问题。

那可能就会没有一个标准答案让模型去回答，这样子，那我们就会需要一个preference space approach，那就像是就是这个这这这次作业的标题，就是IOHF这样。

那就可以看到像上面sf t的范例会写，说就是哎三原色是什么，那他就会回答你说哦是红红蓝黄这样，但如果你是问例如说什么道德性的问题啊，那可能这个模型它就会有很多不一样的回答啦。

有时候会跟你说哎我觉得我觉得他很棒啊，我觉得他不好啊，或者是就是跟你说哎我不知道，我只是说嗯就是他很值得讨论这样，那我们这次的目标就是要让同学学到，就是怎么去online glm到一个就是特定的价值观。

这样，那就是用我们有限的运算资源去做好这件事，然后就是让同学有有感有感的去，就是感受到这个部分，那最原始的做法就是IOHF诶，IOHF嘛，那IOCHP的话它也有它的一些就是嗯一些缺点。

那会在我们paper reading的时候也会讨论到这些部分，那我们这次的话是用DPO来做我们这个task，然后你会看到就是就是我们会让同学去观察，说就是在alignment之后。

model是怎么去behave的，然后也会让同学去认识一些。

![](img/fcd5a1e4bceb5baed30332b9358a103c_5.png)

就是常用的alignment methods，那我们这次test的话是要呃line l ym，同意或者是不同意，就是之前很火红的，就是吉普力生成图像这件事情，那上面可以看到就是老师的官方网页上。

有一个就是他自己的照片，然后我要请check GB把它生成就是吉普力画这样子。

![](img/fcd5a1e4bceb5baed30332b9358a103c_7.png)

对那我们就会变成说就是在align之前呢，我们会问说哎这件事情是道不道德的，那他就会说哦，可能就会说哎这是一个很有趣的问题，那可能需要讨论，那我们这次想要做到的事情，就是他会直接跟你说哦。

我同意这件事情，或者是不同意这件事情，那这DPO的话呢，它会它是会直接提供，就是一个ASCHOSEN，或者你说accepted response，然后另外一个是reject response。

那他是直接的去从这两个response去学习，那就会在chosen的response呢，就是它的几率会上升，然后在rejected response，它的几率会下降，好那就像刚才讲的，就是我们要做到。

这就是同不同意吉普力动画这件事情，哎，就是吉普利图像生成这件事情，那我们这次用的model是拉玛三八比，那原本的response会比较tricky一点，就是有时候会跟你说好啊，我觉得这个这个提议不错。

有时候会跟你说哦，我觉得这样子不行，然后就是有时候会跟你说哦，这是个很值得讨论的部分，这样子那更新的妈的话，可能他的嗯它的response就会更更不一样，那如果有空的话，同学也可以自己去尝试啊。

但是在这原则上，我们是希望大家用拉玛三，然后data set的话是用靠3。7首NE，去生成的一个preference data。



![](img/fcd5a1e4bceb5baed30332b9358a103c_9.png)

这样子，那就会像上面看到就是training set，就是会有一个prom，然后一个support的这个这个response，然后一个opposed response，那这里有50比data这样。



![](img/fcd5a1e4bceb5baed30332b9358a103c_11.png)

然后testing set的话，我们是给十比data去，就是去生成结果。

![](img/fcd5a1e4bceb5baed30332b9358a103c_13.png)

然后会请各位观察，这样好。

![](img/fcd5a1e4bceb5baed30332b9358a103c_15.png)

那再来讲to do的部分，那to do的话会想要先请同学跑COLAB上的sample code，那我们会请同学就是去调整这些training的，Hahyper parameters。

然后再去看他们对于这个这十笔testing set，结果会是怎么样，然后再去回答，就是我们在上面有提供的问题这样，然后也有一些就是比较开放式的指引，那也是请同学去回答这些问题，这样那这些问题的话。

会希望同学就是把他们缴交到grace scope，然后最后要请各位注意的，就是我们也会在sample code里面会生成，就是指定的追送党，那邀请各位依照格式把他们就是压缩成zip档。

然后上传到NQU库，那就是这些格式在后面的简报，还有就是NTU库上也都有解释说哎，就是你的架构应该要长怎样怎样，对，那就像刚才讲的，就是要做到上面所述的这三件事情。



![](img/fcd5a1e4bceb5baed30332b9358a103c_17.png)

然后我们这次会调整的HYPERPARAMETERS，就是这三项，一个是support ratio，然后data size跟number of apex这样。



![](img/fcd5a1e4bceb5baed30332b9358a103c_19.png)

那我们会需要观察susport ratio，基本上就是0~1了，那他就是在说哎，依旧是完全同意，就是用AI生成吉普力图像的这件事情，那零就是完全不同意这样，然后da size的话。

就是你会送进去一个APOC的，就是资料的笔数，然后number of firefox这个概念应该前面的作业也都有，就是看过就是例如说你number feepox设成三。



![](img/fcd5a1e4bceb5baed30332b9358a103c_21.png)

他就会看这整这整个东西三次，这样好，那再来看一下code啊，下。

![](img/fcd5a1e4bceb5baed30332b9358a103c_23.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_24.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_25.png)

好那就是最前面的话就是先安装B2package嘛。

![](img/fcd5a1e4bceb5baed30332b9358a103c_27.png)

然后我们这一次跟应该是作业五也是一样，就是会用到on slows这个能够加速的库，然后会在这边，就是就是要放大吗。



![](img/fcd5a1e4bceb5baed30332b9358a103c_29.png)

要放大，好好。

![](img/fcd5a1e4bceb5baed30332b9358a103c_31.png)

这表好，那就是会去载入这个lama38B的model，那这颗是我用的是on source的一个copy，那它跟原始的meta lama是完全一模一样的。



![](img/fcd5a1e4bceb5baed30332b9358a103c_33.png)

然后会去就是从GLAB去DECLONE下来。

![](img/fcd5a1e4bceb5baed30332b9358a103c_35.png)

这个DATASET的部分，然后会就是载入之后。

![](img/fcd5a1e4bceb5baed30332b9358a103c_37.png)

我们会定义这个嗯。

![](img/fcd5a1e4bceb5baed30332b9358a103c_39.png)

data formula跟就是extract responses的function的部分。

![](img/fcd5a1e4bceb5baed30332b9358a103c_41.png)

然后会让各位先去看，就是原始的model他会怎么样去behave，就是就是就是对这些这些嗯。

![](img/fcd5a1e4bceb5baed30332b9358a103c_43.png)

嗯testing set的问题去回答这样。

![](img/fcd5a1e4bceb5baed30332b9358a103c_45.png)

然后就是邀请各位去调整这三个hyper parameters。

![](img/fcd5a1e4bceb5baed30332b9358a103c_47.png)

然后去就是观察，后面就是在tn tn完之后会生成出的结果。

![](img/fcd5a1e4bceb5baed30332b9358a103c_49.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_50.png)

然后对，然后这边的话基本上就是我们都已经调整好。

![](img/fcd5a1e4bceb5baed30332b9358a103c_52.png)

就是6LAURA这些部分文都已经就是设定好了。

![](img/fcd5a1e4bceb5baed30332b9358a103c_54.png)

那这些都是不用动的对，然后就是在跑完train之后。

![](img/fcd5a1e4bceb5baed30332b9358a103c_56.png)

会在这边就是再跑一次。

![](img/fcd5a1e4bceb5baed30332b9358a103c_58.png)

刚才一模一样的influence，然后生存就是你可以去观察说诶，这些嗯就是生出来的东西有什么不一样的地方。



![](img/fcd5a1e4bceb5baed30332b9358a103c_60.png)

这样然后我们会在这边就是生成追踪，那要请各位就是帮我就是改这个学号的部分。

![](img/fcd5a1e4bceb5baed30332b9358a103c_62.png)

然后就是生成出来的追踪党应该要有四个，然后就是在请各位把他们打包到zip档。

![](img/fcd5a1e4bceb5baed30332b9358a103c_64.png)

然后交上去，对那后面有一些开放式问题，就可以从这边去调整，就是可以改私生point跟就是user的input。



![](img/fcd5a1e4bceb5baed30332b9358a103c_66.png)

这样，然后就是去观察他们有什么样不一样的地方。

![](img/fcd5a1e4bceb5baed30332b9358a103c_68.png)

对然后哦对，然后刚才就是追送党的话。

![](img/fcd5a1e4bceb5baed30332b9358a103c_70.png)

会希望同学就是在这边就是files的部分，它会它会列出来，然后就是把他们直接六右键下载，这样然后对我就随便找一个档案，然后先示范一次，这样对就是会有一个会有个download。



![](img/fcd5a1e4bceb5baed30332b9358a103c_72.png)

然后再把它download下来就好了，然后另外一件要请大家注意的。

![](img/fcd5a1e4bceb5baed30332b9358a103c_74.png)

就是在你每次调整完HYPERPARAMETER，需要记得去上面把那个原始的model再搂进来一次。

![](img/fcd5a1e4bceb5baed30332b9358a103c_76.png)

不然你很有可能会就是用你听完的model，然后再去用不同的hyperparameter study train一次，那这样出来的结果会相当的奇怪。



![](img/fcd5a1e4bceb5baed30332b9358a103c_78.png)

对。

![](img/fcd5a1e4bceb5baed30332b9358a103c_80.png)

好了，以上就是扣的部分诶，哦对。

![](img/fcd5a1e4bceb5baed30332b9358a103c_82.png)

![](img/fcd5a1e4bceb5baed30332b9358a103c_83.png)

好算了，我就这样，好那就是这次主要会调HYPERPARAMETERS，是有三个问题，那就是分别把就是separation从就是零跟一的差别，然后把number of fairpox1跟三的差别。

还有data set10跟50的差别，那这六个就是hyper programal set，里面有就是蓝色框框的，都就是他们的设定是一样的，所以这这三个蓝色框框，其实你基本上做一次就好。

所以才会说刚才四个追送，就是刚才只会有四个追踪，这样对，那就是一样，就是要注意把la model就是重新漏进来一次，那最快速的方式就是额上面有一个restart，And run out。

这样子就再跑一次就好，因为它嗯安装的时间不会太久，那第四题的话就会分别是四个啊，四个邀请各位观察，我问你哎，Sorry，这四个四个分别邀请大家观察问题，那第一个话是就是我们原本的SYSTESYSTEM。

From me，是说哎你只能在就是100个character里面回答，那如果我们调整这个system prom到更长的时候，他的model会怎么样去比黑，那就是可以观察一下它的输出。

那第二个的话是我们会想要去请同学问说诶，就是例如说不同的动画或者是不同的啊，or work会他会怎么样去比配，例如说如果我们今天生成的是海贼王类的，就是图片或者是迪士尼的图片。

那model会怎么去回应这样，那第三个的话是不同的，就是our work的style，诶，应该说种类就是说像是巴赫的音乐啊，或者是或者是什么什么模仿大师画作之类的，那就是要请同学去升这个prom。

然后回答，那最后一个话是会想要请同学用中文，去问这个model，那就是例如说con pron说哎请使用中文回答，然后就说诶就是生成吉普力风格的艺术作品，是不是就是道德的。

那如果不就是不太会用中文生的同学，可以直接用上面的prom去回答就好了，好然后再来的话是paper reading的部分，那我们这次提供的是三篇paper，那第一篇的话是extract gbt。

也就是cheat gbt的前身的这篇paper，那就是想要请同学去了解一下，当初他们RHF的部分，然后第二篇paper的话就是DPO的原paper，那当然啦就是DPO有很多不同的variance。

跟后来出现的一些衍生方法，但我们还是就是选了它最原始的paper，还有他们的方法这样子，那对于就是这些颜色方法，这些KTU啊，这些同学在了解之后可以再继续看这样子，那最后一个是depsg max。

还有deep segone的部分，那主要就是要看GRPO这个方法啊，因为GRPO他算是就是少数有公开完整，recently的这个recipe的方法之一，那就是想要请同学多去了解这样。

那像是前几天刚刚出的five four的recently plus，也是用了这个方法，他们只是调整一些嗯，reward model的设定，这样子对，那题目的话大部分就是在问。

就是有哪一些不对跟不对的地方，那这些都是paper里面有直接提到的对，那比较需要注意的是，像是这个是它里面有提到的一个real model loss function。

那这个的话就是想要请同学用给定的这些数字，去计算它一次comparison的部分，那这个部分的话主要就是会就是他的call loss function，就是会在这个负的，在logo后面这一串的部分。



![](img/fcd5a1e4bceb5baed30332b9358a103c_85.png)

那那个sigma是SIGMIN，这样，然后这一题的话是问，就是因为他们在charge v1推出之后，有再一次的ICO有给talk，就是说哎就是他有一些OVEROPTIMIZATION的部分。

那老师在我记得是72022年的机器学习，有讲到就是这个部分啊，就是哦对了哦对了哦，ICLR2022了，然后老师在2024年的生成式人工智慧导论，有讲到这件事情，那就是请同学可能去参考一下这部影片。



![](img/fcd5a1e4bceb5baed30332b9358a103c_87.png)

这样，那再来DPO的部分的话，也是问一些，就是就是有给一些叙述，然后就是讲对和错的地方，那这边的话应该没有太有疑问的地方。



![](img/fcd5a1e4bceb5baed30332b9358a103c_89.png)

对，那再来的话是GRPO，GRPO的话就是就是第一题跟第二题都是问，PPPO跟gr po1些方法啦，还有一些叙述上的对跟错的部分，那PPPO这个也是可以去看老师的影片。

那我们也有附在grace scope里面这样子。

![](img/fcd5a1e4bceb5baed30332b9358a103c_91.png)

对那就像刚才讲到第二题，就是看他的数学跟method有什么，就是就是叙述上有什么对跟错的地方。

![](img/fcd5a1e4bceb5baed30332b9358a103c_93.png)

对。

![](img/fcd5a1e4bceb5baed30332b9358a103c_95.png)

好那在submission ingredient的部分，就是像刚才讲到的，就是要把额舒适，就是要求要写就是写观察，然后写的部分就是加到GRASSCOPE上，那刚才那些选择题也跟简答题。

也都是在greek scope上这样子，那剩下的话就是要在NTU扩上缴交这个zip档，然后就是要包含这四个档案，这样那student id的话要麻烦各位，就是帮我注意要小写了对。

就是跟前面几次作业的要求都是一样的，那后面这些格式就是HW7什么AIRPOK啊，然后ratio这些都是就是COLLAB，扣里面已经生好了，这样那也是请同学不要去改动到，就是追送党里面的内容。

不然有可能会影响到你的分数，好那就是grace scope，刚刚TU扩的部分的话，就是刚才都已经上线了，我们是设定四点就上线，那死线的话是五月23号23。59分，那我们是不接受任何补交以及补救的。

那再请同学注意一下，好那我们一些规则的话，就是大概都是跟前几次一样，就是我们当然是不接受任何的抄袭的，然后我们要就是把追追送党交对，然后把你的答案交对，但然后这次需要更就是提醒各位同学。

是就是昨天大助教有发一篇公告，就是在讲抄袭，还有一些相关的就是qualification跟一些rules这样子，那就是我们想要请同学，就是保护好你自己的答案，不要让任任何人看到，就任就算是什么。

你问ChatGPT的内容，你也不要去分享给人家这样，那这就是超与被遭同罪了，那这件事情呢我们会从作业六开始实施，那就是请各位同学再注意，然后就是你如果第一次犯了，这就是这些规则的话，你的作业会是零分。

然后最终的等级等就是成绩会乘以0。9，那如果你是你不是初犯了，你已经犯第二次以上的话，那就是直接当掉，那如果有任何疑问的话，我们是建议各位先到NTU扩上的，做一期讨论区去，就是讨论。

那可能其他有需要的同学会先看到你这个讨论，那他们就不用再费力气去问我们了，那如果有一些比较私密的问题的话，就是请同学再寄到，就是我们的主要信箱，然后就是在title要有HW7的部分。

那TL5的话是下午一点，下午01：20到02：10分在隔壁的113，然后5。20到六点在这间教室好，那以上就是这次作业的内容。



![](img/fcd5a1e4bceb5baed30332b9358a103c_97.png)