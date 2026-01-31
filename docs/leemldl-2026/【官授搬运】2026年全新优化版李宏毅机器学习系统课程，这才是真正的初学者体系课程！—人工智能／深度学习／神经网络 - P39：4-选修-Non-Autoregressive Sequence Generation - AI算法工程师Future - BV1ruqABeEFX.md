# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P39：4-选修-Non-Autoregressive Sequence Generation - AI算法工程师Future - BV1ruqABeEFX

![](img/4d695e3e6dcbd714b509312b24df76f6_0.png)

好，那今天要讲的题目是关于NAOTO，aggressive的sequence。

![](img/4d695e3e6dcbd714b509312b24df76f6_2.png)

选择VIATION，好，那我们在作业一里面，大家都已经做过一个SECRETOSEON的语音辨识，那其实这种云变式的模型就是一个conditional的。



![](img/4d695e3e6dcbd714b509312b24df76f6_4.png)

Sequence generation。

![](img/4d695e3e6dcbd714b509312b24df76f6_6.png)

那你的condition就是input的语音讯号。

![](img/4d695e3e6dcbd714b509312b24df76f6_8.png)

然后你的output的句子就是你要generate的sequence。

![](img/4d695e3e6dcbd714b509312b24df76f6_10.png)

那它是对应到这段语音的文字。

![](img/4d695e3e6dcbd714b509312b24df76f6_12.png)

好那除了云变式之外呢，我们假如input是一张图片，然后output是对应那张图片的图说文字，那这个这个task也是conditional sequence generation。

那它叫做image caption generation。

![](img/4d695e3e6dcbd714b509312b24df76f6_14.png)

那如果你input是一段英文，output是对应那段英文的中文，那这个就是machine translation。



![](img/4d695e3e6dcbd714b509312b24df76f6_16.png)

那今天我们要探讨的这个now auto，regressive model的主题。

![](img/4d695e3e6dcbd714b509312b24df76f6_18.png)

通常都会用sequence generation，and通常都会用我们先translation来做他的task，所以等一下我们都是讨论翻译的这个任务。



![](img/4d695e3e6dcbd714b509312b24df76f6_20.png)

![](img/4d695e3e6dcbd714b509312b24df76f6_21.png)

好，那我们平常在做翻译的时候，都是用auto regressive的model，那假如你用的是R和N，那你会把input sequence丢进一个RN里面，然后引扣成向量，那再交给decoder。

decoder在每一个时间点都吐出一个字，那吐出来的这个字再拉到第二个位置，然后再吐吐出下一个字，那这个就是auto regressive的抵扣，所以你在抵扣每一个字的时候。

都会depend on你刚刚抵扣出来的字，那但是这样的方法有一点缺点，就是假如你要抵扣的句子很长，你需要花的时间，就跟你抵扣的句子的长度成正比，那现在我们有了transformer之后。

能不能对这件事情做改善呢，就有了选磁化之后，我们就不需要像RNN一样，在吃了前一个时间点的东西之后，才能吃下一个时间点的东西，所以他在银扣的速度是加快的。



![](img/4d695e3e6dcbd714b509312b24df76f6_23.png)

我们我们可以用平行的方法，把这个句子引扣起来。

![](img/4d695e3e6dcbd714b509312b24df76f6_25.png)

可是在抵扣的时候还是会遇到一样的问题。

![](img/4d695e3e6dcbd714b509312b24df76f6_27.png)

我们必须要等第一第一个位置的字吐完之后，再把它拉到第二个位置的input，然后吐出第二个字。

![](img/4d695e3e6dcbd714b509312b24df76f6_29.png)

所以说auto aggressive的model，在当decoder做使用的时候，还是会跟RNN一样，需要跟句子长度成正比的时间，才能把整句话抵扣出来。



![](img/4d695e3e6dcbd714b509312b24df76f6_31.png)

好，那所以说既然犬石墨脉都已经可以平行运算了。

![](img/4d695e3e6dcbd714b509312b24df76f6_33.png)

那我们就有一个想法是。

![](img/4d695e3e6dcbd714b509312b24df76f6_35.png)

能不能让选手们一口气把整句话吐出来，那这样的话时间就时间上就可以节省很多，那这个model你可能会有点纳闷。



![](img/4d695e3e6dcbd714b509312b24df76f6_37.png)

就是我们要怎么决定。

![](img/4d695e3e6dcbd714b509312b24df76f6_39.png)

到底要一口气吐出来的句子是要多长，那这边我们可以先让encoder随意取第一个长度。

![](img/4d695e3e6dcbd714b509312b24df76f6_41.png)

那decoder的output我就放position embedded，这个是最简单的想法，就是我们想要让decoder可以吐出一整个句子。



![](img/4d695e3e6dcbd714b509312b24df76f6_43.png)

在一个一个ties day的时间内。

![](img/4d695e3e6dcbd714b509312b24df76f6_45.png)

但是这个model如果照这样硬做的，硬做的话。

![](img/4d695e3e6dcbd714b509312b24df76f6_47.png)

其实会遇到一个很大的问题，那要讲这个问题之前，可以先看一下在影像上面的例子，那这个投影片是老师在NLDS这门课里面教。



![](img/4d695e3e6dcbd714b509312b24df76f6_49.png)

conditional game的投影片，那那个时候是在讲说，假如我们不要用gain的方法。

![](img/4d695e3e6dcbd714b509312b24df76f6_51.png)

我们用纯粹super摆子的方法，要训练一个text to image的model。

![](img/4d695e3e6dcbd714b509312b24df76f6_53.png)

那这个model呢会吃一个文字。

![](img/4d695e3e6dcbd714b509312b24df76f6_55.png)

假如这边是券，那这个券我们把它丢到model里面，model会要铺出一张图片，那因为我们是super白纸的方法。



![](img/4d695e3e6dcbd714b509312b24df76f6_57.png)

我们就直接把这个output的图片跟DIRC里面，火车的图片算l two distance，然后去minimize l two distance。



![](img/4d695e3e6dcbd714b509312b24df76f6_59.png)

那这个方法有什么缺陷呢，这个方法做出来的model。

![](img/4d695e3e6dcbd714b509312b24df76f6_61.png)

最后都会output一张比较模糊的图片，因为它会是每一张图片的平均。

![](img/4d695e3e6dcbd714b509312b24df76f6_63.png)

假如说你的data set里面有70帕是往左边的火车，有30帕是往右边的火车。

![](img/4d695e3e6dcbd714b509312b24df76f6_65.png)

那model为了要去mini买这两种火车的l two distance。

![](img/4d695e3e6dcbd714b509312b24df76f6_67.png)

最后他是会output出一张双头的火车。

![](img/4d695e3e6dcbd714b509312b24df76f6_69.png)

然后他是很模糊的，那这显然就不是我们要的结果。

![](img/4d695e3e6dcbd714b509312b24df76f6_71.png)

那为什么我们会遇到这个问题呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_73.png)

那第一个，因为这个models的output。

![](img/4d695e3e6dcbd714b509312b24df76f6_75.png)

是没有任何dependency关系的，也就是说这个model在output第二个位置的，此后他不知道第一个位置到底output了什么东西，所以他们没办法有dependence的关系。

那假如我没有auto与plc model当然就会避开这个问题，因为你在output第二个位置的时候，可以看到第一个位置的output。



![](img/4d695e3e6dcbd714b509312b24df76f6_77.png)

那另外还有一个方法是我用gain来解这个问题。

![](img/4d695e3e6dcbd714b509312b24df76f6_79.png)

我在训练这个model的时候，用gain的方法来做训练的话，model就可以学会output一个有structure的东西。



![](img/4d695e3e6dcbd714b509312b24df76f6_81.png)

为什么会这样呢，因为gain的训练方法是discriminator。

![](img/4d695e3e6dcbd714b509312b24df76f6_83.png)

给整张图打一个分数，然后把这个把这个分数debug给generator去做训练，所以说最后generator会学到的是，我要output一个完整的structure。

然后可以让discm net分不出来，哪一张图片是真的。

![](img/4d695e3e6dcbd714b509312b24df76f6_85.png)

那所以说gain是一个可以offer完整structure的呃。

![](img/4d695e3e6dcbd714b509312b24df76f6_87.png)

让让简net学会欧布完整刷TRI的方法。

![](img/4d695e3e6dcbd714b509312b24df76f6_89.png)

那除了这个问题之外，还有另外一个问题，是这个model的内部没有任何的随机的机制，他没有一个later variable，让这个model去决定说，他到底要output左边的火车还是右边的火车。

虽然说这个model在training的时候，他可能已经知道了，他已经知道有70趴都是左边的火车，有30趴都是右边的火车，但是这个model他在它内部没有任何随机的机制，所以即使你到了最后一个。

He doesn't say，他还是这两种火车的结合状态的叠加的状态，所以他最后还是只能要铺一张模糊的图片。



![](img/4d695e3e6dcbd714b509312b24df76f6_91.png)

那auto regressive model为什么没有这个问题呢，因为auto regressive model在每一个时间点的output，就会做一个sample的动作，他会挑一个可能几率比较大的。

然后把其他的可能性都排除掉，所以auto与base model就他的later variable，就是我在每一个time day sample的那个时候。



![](img/4d695e3e6dcbd714b509312b24df76f6_93.png)

那如果是game的话，大家大家应该假如大家有看过老师game的课程，应该都知道，不管是conditional game或是一般的game，你在input的时候都要input noise。

那这个noise其实就是让model，事先决定好生成的方向。

![](img/4d695e3e6dcbd714b509312b24df76f6_95.png)

所以所以这两个方法其实都会避开这两个问题，但是我们的now to与GRESSIVE的方法，就会遇到这两个问题。



![](img/4d695e3e6dcbd714b509312b24df76f6_97.png)

好那现在讲完图片的例子，我们回来看一下文字上上面的例子，那现在你有一你想要签一个挠头语base的model，那你有一句英文，那你想要翻成他的中文，可是中文有很多种不同的讲法，hello可以翻译成你好。

或者hello或者hi，那你假如说你的training set里面有50帕是hello，50帕是你好。



![](img/4d695e3e6dcbd714b509312b24df76f6_99.png)

那这个这个挠头里面写model，他最后就会学到说我在看到英文的hello的时候。

![](img/4d695e3e6dcbd714b509312b24df76f6_101.png)

我第一个字要output h或是米，然后这两个字的几率是差不多大，那第二个字呢要output low或是好，那这两个几率也是差不多大，那可是这样，最后的结果就是有一个错误的翻译叫做你有。

然后他的几率也是非常大，他非常有可能被sample出来。

![](img/4d695e3e6dcbd714b509312b24df76f6_103.png)

然后还有一个是哈哈也是一个错误的翻译，可是他也是可能被限播出的，那这个问题我们就叫做MARTIMODELITY。



![](img/4d695e3e6dcbd714b509312b24df76f6_105.png)

问题，就是说呃，因为同一个input，可能对应到很多不同模式的output，那假如我的decoder是not to aggressive。



![](img/4d695e3e6dcbd714b509312b24df76f6_107.png)

那他会把各种可能的模式叠加在一起。

![](img/4d695e3e6dcbd714b509312b24df76f6_109.png)

然后当成output。

![](img/4d695e3e6dcbd714b509312b24df76f6_111.png)

所以所以这个是我们在这一个这次的主题里面。

![](img/4d695e3e6dcbd714b509312b24df76f6_113.png)

主要要解决的问题，好那这边小小总结一下。

![](img/4d695e3e6dcbd714b509312b24df76f6_115.png)

假如你要用嗯。

![](img/4d695e3e6dcbd714b509312b24df76f6_117.png)

你要用model去生一张图片，然后用最简单的方法就是minimize l to lose，那你可能会生出很模糊的图片，它是每一张图片的平均，那对应到文字上的的状况。

就是你用脑auto aggressive的decoder，要要一次吐出整句话，那他吐出来的东西可能就是各种可能的。



![](img/4d695e3e6dcbd714b509312b24df76f6_119.png)

output的叠加的状态，那假如你用auto aggressive的方法在图片上。

![](img/4d695e3e6dcbd714b509312b24df76f6_121.png)

其实auto evasive方法就可以生出品质很好的图片，那对应到文字上，就是用一般的auto regres的decoder来生文字。



![](img/4d695e3e6dcbd714b509312b24df76f6_123.png)

那图片其实我们都知道game也可以生成，生出很高品质的图片，那我们在做game的时候，其实你model的架构可以用。



![](img/4d695e3e6dcbd714b509312b24df76f6_125.png)

一般第一个方法里面的model架构，我可以用简单的deconvolution layer来做。

![](img/4d695e3e6dcbd714b509312b24df76f6_127.png)

我不需要用auto与base model，但是他就是可以生出很好的图片。

![](img/4d695e3e6dcbd714b509312b24df76f6_129.png)

但是目前文字上是没有人这样做的，因为文字用game来做，我目前还没有非常成熟，因为文字是一个DISCREEN的东西，然后用电做训练的话，目前的研究都还没有得到很好的结果。



![](img/4d695e3e6dcbd714b509312b24df76f6_131.png)

所以目前game的研究都还是坐在auto，aggressive的model上面。

![](img/4d695e3e6dcbd714b509312b24df76f6_133.png)

好那所以说对文字来说，唯一能达成now auto regressive的model，就还是要回到第一个方法，那所以接下来的要介绍的东西，就是针对第一个model做改良。



![](img/4d695e3e6dcbd714b509312b24df76f6_135.png)

好那这个是第一篇作，然后TAGGRESSIVE翻译的paper，那嗯等一下都会把now to regressi全cation，简称叫AT。



![](img/4d695e3e6dcbd714b509312b24df76f6_137.png)

那这篇的概念还蛮简单的。

![](img/4d695e3e6dcbd714b509312b24df76f6_139.png)

他提出几个方法可以改良我们的，Not to regressive model，那第一个方法是我们在encoder的地方。



![](img/4d695e3e6dcbd714b509312b24df76f6_141.png)

每一个字去可以定一个数字，这个数字代表的意义是这一个input的字。

![](img/4d695e3e6dcbd714b509312b24df76f6_143.png)

对应到output的几个字。

![](img/4d695e3e6dcbd714b509312b24df76f6_145.png)

那像是这个字是很low，那它对应到output的名号，那所以说我们预测完这个数值之后，就把input copy两次，然后放到decoder的input，所以说他可以列出2121。



![](img/4d695e3e6dcbd714b509312b24df76f6_147.png)

那我就copy两次，一次两次一次这样子。

![](img/4d695e3e6dcbd714b509312b24df76f6_149.png)

所以最后他培育出来的这些数字的总和，就是决定了你的句子长度，那这个为什么我们要普及这个数值呢，其实它是代表了你的decoder。



![](img/4d695e3e6dcbd714b509312b24df76f6_151.png)

对这个output的规划和事前规划。

![](img/4d695e3e6dcbd714b509312b24df76f6_153.png)

也就是说，假如你的decoder他吃的input是2121，就是hello，复制两次逗点复制一次。

![](img/4d695e3e6dcbd714b509312b24df76f6_155.png)

word复制两次，惊叹号复制一次，那他就可能比例出这样的output。

![](img/4d695e3e6dcbd714b509312b24df76f6_157.png)

那如果他的hello是复制了一次，他可能就会发现我不能翻译成你好，因为你好有两字。

![](img/4d695e3e6dcbd714b509312b24df76f6_159.png)

那我就翻译成派世界，所以说这一个fertility就是有一个letter vable。

![](img/4d695e3e6dcbd714b509312b24df76f6_161.png)

![](img/4d695e3e6dcbd714b509312b24df76f6_162.png)

letter marable的功能，然后事先帮decoder决定好它要生成的方向。

![](img/4d695e3e6dcbd714b509312b24df76f6_164.png)

那我们要怎么训练这个fertility呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_166.png)

我们可以直接用一个外部的alignment的工具，然后去去对说一个input的这段话，它的每一个字会对应到output的几个字，所以这个其实是可以轻松的得到答案，那除此之外。

我们也可以直接劝一个secret secre的auto与ging model，然后直接去看他的天性位是怎么分布的，上次我们在作业一里面，就会看出哪一段语音讯号，会对应到output的哪一个字。

就是有一个对角线，那这里用的事情是一样的，只是他是坐在翻译上的，好那但是我们假如都是从外部得到答案，然后来劝这个fertility的prediction的话。

它跟最后model output1句不错的句子，是他的目标是不一致的，所以我们在model熟练之后会做一个翻跳的动作，就是用零封零封神learning的lose加在fertility上面。

然后去optimize fertility。

![](img/4d695e3e6dcbd714b509312b24df76f6_168.png)

好那刚刚讲FTI2题是第一招，那第二招是sence level的knowledge distillation。



![](img/4d695e3e6dcbd714b509312b24df76f6_170.png)

那knowledge distillation呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_172.png)

老师在NL，去年的NL这门课上面应该都有介绍过，就是假如你想要劝一个小model，然后你又希望这个小model的performance，可以跟大model一样好。

那你现在就把这个小model当成student。

![](img/4d695e3e6dcbd714b509312b24df76f6_174.png)

大model当成teacher，那小model在训练的时候。

![](img/4d695e3e6dcbd714b509312b24df76f6_176.png)

先把他的input丢给大model，让大model output出它本地的几率分布。

![](img/4d695e3e6dcbd714b509312b24df76f6_178.png)

那们让让小model直接去学这个培，提出来的几率分布，那这样小model就会学的比较好，那这个是nice distation在做的事情。



![](img/4d695e3e6dcbd714b509312b24df76f6_180.png)

那我们这边的case呢就是teacher model是auto regression model，那student model就是老头一类型model，但是后面的事情有一小点不一样。

我我没有要去学这一个集权model，吐出来的几率它一样是哎，我们是让这个teacher model，把COOPUS里面的每一句话用用他自己model pd出来，用规定抵扣的方式抵扣出来一个句子。

然后让student model把那一句抵扣出来的话，当成正确答案，然后做训练，所以就是跟一般的nice alasion有一小点不一样，那为什么我们可以解决哎。

为什么nice destation可以解决，我们想要解决的那个MARIMODELITY问题呢，那我们刚刚说MONTMODELITY问题。



![](img/4d695e3e6dcbd714b509312b24df76f6_182.png)

就是output之间没有dependency，所以错误的翻译的几率也会很大，那假如你的data set，有先给auto reversive的teacher model做抵扣的话呢。

因为他是auto与个性model，所以他在生出第二个字的时候，假如他已经看到第一个字是生命。

![](img/4d695e3e6dcbd714b509312b24df76f6_184.png)

那他就第二个字就会倾向生成好，他就不会把low生出来。

![](img/4d695e3e6dcbd714b509312b24df76f6_186.png)

所以说你要你假如让auto regressive model去抵扣，你的整个COPUS的话呢，你就会去掉某些可能你的翻译，你的正确答案里面就不会有hello。



![](img/4d695e3e6dcbd714b509312b24df76f6_188.png)

这个可能就只会留下你好，这个可能。

![](img/4d695e3e6dcbd714b509312b24df76f6_190.png)

所以这样做之后，你的DRC就变干净了，就是更容易让NAOTO与basive model去学习。

![](img/4d695e3e6dcbd714b509312b24df76f6_192.png)

因为就不会有多种的可能。

![](img/4d695e3e6dcbd714b509312b24df76f6_194.png)

好那这个这个是第二招，那第三招是叫做noisy paralo decoding。

![](img/4d695e3e6dcbd714b509312b24df76f6_196.png)

那他的概念就是我确认好我的not to reverse model，那我在抵扣的时候，其实是可以sample不同的fertility，所以sample出一个不同的fertility。

就会output出不同的句子，那我可以做很多事，然后output出一大堆的不同的句子。

![](img/4d695e3e6dcbd714b509312b24df76f6_198.png)

那这些句子再交给auto reversive model来打分数，然后选一个最好的句子翻成答案，那大家可能觉得有点奇怪，因为这样我我不就使用了auto与base model，这样不就变慢了吗。

那但是其实如果你要让auto reverse model去算一个。

![](img/4d695e3e6dcbd714b509312b24df76f6_200.png)

已经生出来的句子出现的几率，你是只需要一个step就可以完成，假如你用的是transformer的decoder，那你就用teacher force的方式，然后你会在这个decoder里面做mask。



![](img/4d695e3e6dcbd714b509312b24df76f6_202.png)

做mask就是让哎这个字不能attend到后面的字。

![](img/4d695e3e6dcbd714b509312b24df76f6_204.png)

所以说他就可以output出。

![](img/4d695e3e6dcbd714b509312b24df76f6_206.png)

看到begin of sentence，然后要删除你的几率，然后看到begin of sentence跟你要生出好的几率，所以这这整排几率就是存起来，就是这整句话被审核出来的记忆。

然后这样的过程是不需要auto与GRC的时间的。

![](img/4d695e3e6dcbd714b509312b24df76f6_208.png)

我只需要一个stay就可以算出这句话的几率。

![](img/4d695e3e6dcbd714b509312b24df76f6_210.png)

好所以啊，所以说我们就有三个方法可以加强这个model，那这里是实验的结果，那auto evacing model，那我们用in search size是一跟been search size是四来抵扣。

然后他的performance是这样，那他的时间我我假如说并设取size。

![](img/4d695e3e6dcbd714b509312b24df76f6_212.png)

设四的这个速度是一，那现在用挠头evasive model来做，发现它得加速到15。6倍，可是他的performance就差了很多，那我们现在加上fine to的机制，就是fertility。

劝完之后要做翻to的动作，那performance就会往上涨，那接下来再加上noz po decoding，然后普攻门子就会再进一步，可是进步的同时，你的速度也会变慢一点。



![](img/4d695e3e6dcbd714b509312b24df76f6_214.png)

那这边要来看说我做distillation跟做fertility，跟做fertility的fighting，这三件事情到底对model带来多大的帮助，那大家可以看到第一行。

第一行是没有distillation，也没有没有fertility，也没有做翻译T，那这个时候model基本上是劝不起来的，他的blue score只有二。

and blue score就是我们在做翻译的时候，常常用的一个指标，然后他是越高越好，如果我们用了fertility的话，就会进步到18。8，但是如果我们fertility不要用pd的。

我们是直接看input和output对应的长度，然后直接只决定每一个字要copy几次，那这个叫uniform的copy，那如果是这样做的话，其实也有16。5。



![](img/4d695e3e6dcbd714b509312b24df76f6_216.png)

那现在把这一行加上distillation之后，就可以一口气进步到25。2。

![](img/4d695e3e6dcbd714b509312b24df76f6_218.png)

那如果再加上fertility的FIGHTUNE，又可以再进步到26点多好。

![](img/4d695e3e6dcbd714b509312b24df76f6_220.png)

那自从这一篇这篇。

![](img/4d695e3e6dcbd714b509312b24df76f6_222.png)

第一篇NOTABBEY的翻译出来之后，后面就冒出来一系列的不同的做法，就是在2018之后，到到现在，几乎每个月都有一个新，都有不止一个新的model出来，这样子，那第一个方法就是刚刚介绍的这个。

第一篇的nt model，那第二个出来的方法呢是iterative refinement，那iterative refinement的概念就是，如果我们想要让model1口气output。

整段话好像太勉强，那我们能不能让它output output，出一句话之后，把这句话拉到input，然后再抵扣一次，然后修正刚刚的错误，好那除了iterative refinement之外。

还有一个方法是insert base。

![](img/4d695e3e6dcbd714b509312b24df76f6_224.png)

那insertion base他也很像iterator refinal，只是他refinement的方式是透过插入的方法，就是有一句比较烂的句子，那我决定说，每两个字之间要不要插入一个新的字。

那为什为什么要这样做。

![](img/4d695e3e6dcbd714b509312b24df76f6_226.png)

因为原本的iterative refinement，它的句子长度是固定的，只是你在第一个times day抵扣出来的句子是多长，那我refine之后句子还是那么长，所以它的它的长度是不会改变的。



![](img/4d695e3e6dcbd714b509312b24df76f6_228.png)

但是如果用insert base，我们可以自由的让model决定句子的长度。

![](img/4d695e3e6dcbd714b509312b24df76f6_230.png)

然后我也我也可以同时音色，所以它的它也是有一定的品行化。

![](img/4d695e3e6dcbd714b509312b24df76f6_232.png)

但是这样还是会比较慢一点，假如最快最快，我想要生成一句话是ABCDEFG，那最快的方法就是我先生出最中间那个字，然后再伸出旁边这两个，SUBSEQUENCE的最中间那个字，然后最后再把剩下的字补完。

所以最快的话就是log n的时间，可以胜完这个句子，好所以insertion base的方法是比较偏向PARTI。



![](img/4d695e3e6dcbd714b509312b24df76f6_234.png)

理由to与格式就不是不是很纯正的挠头与归系，那有了insertion之后，我们又想到说，假如他映射了一个错字，他就不能再修改了，不像刚刚我们做iterative refinement的时候。

假如你有一个字是错的，可以拉回来再做一次修正，所以所以我们后来又有一个新的model，它是insertion加deletion，那dd dd就是去预测每一个字要不要被删掉。

所以假如他有一个错字是可以被model删掉。

![](img/4d695e3e6dcbd714b509312b24df76f6_236.png)

那最后最后就是大家在老师讲语音电视。

![](img/4d695e3e6dcbd714b509312b24df76f6_238.png)

这堂课里面有介绍的CP4，那其实CTC也是可以应用在文字上面，那等一下会介绍他要怎么应用。

![](img/4d695e3e6dcbd714b509312b24df76f6_240.png)

好，那这个就是第一篇做iterative refinement的NT的model。

![](img/4d695e3e6dcbd714b509312b24df76f6_242.png)

那它的方法，它的概念就是，当你你一个句子X你要翻译成Y之后，还可以做很多次的翻译，然后翻译成一个更好的Y，所以它的模型一开始也是一个encoder，然后去pd tt的长度。

然后就把input的句子做copy，做copy之后呢，抵扣出第一版的翻译，那其实这边做的事情，跟第一篇的NAT是差不多的事情，那只是后面又多加了第二个decoder。

这个decoder呢会把上一个时间的Y拉到input。

![](img/4d695e3e6dcbd714b509312b24df76f6_244.png)

然后做REFINAL，然后ref好几次这样子，那我要怎么训练这个decode2呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_246.png)

那其实我们除了可以直接拿Y里，然后放进来，然后让它跟正确答案算loss之外，我们也可以把正确答案加一些noise丢到input。



![](img/4d695e3e6dcbd714b509312b24df76f6_248.png)

然后让decoder去学DNOISE的过程。

![](img/4d695e3e6dcbd714b509312b24df76f6_250.png)

那加noise，我们可以直接把一个字重复两次啊，或是把字换成一个render的字，或是把两个字交换等等。



![](img/4d695e3e6dcbd714b509312b24df76f6_252.png)

那所以最后就会让model去学这两种不同的loss。

![](img/4d695e3e6dcbd714b509312b24df76f6_254.png)

要去minimize这些loss。

![](img/4d695e3e6dcbd714b509312b24df76f6_256.png)

那这个方法的performance其实也没有，也没有特别好。

![](img/4d695e3e6dcbd714b509312b24df76f6_258.png)

就是跟NATO与类型model的第一篇是差不多的。

![](img/4d695e3e6dcbd714b509312b24df76f6_260.png)

好像只有在这个data a set是有赢过他的。

![](img/4d695e3e6dcbd714b509312b24df76f6_262.png)

好那接下来这篇就比较强一点，他是在BT出来之后才做的，那它就是有用到BT的概念。

![](img/4d695e3e6dcbd714b509312b24df76f6_264.png)

那BT就是我们一句话把一些字换成max的token，那BT就会知道要在output，把那个被miss的调剂作为construction，那现在我们把这个BT加上一个encoder。



![](img/4d695e3e6dcbd714b509312b24df76f6_266.png)

然后把BT当decoder来用。

![](img/4d695e3e6dcbd714b509312b24df76f6_268.png)

所以他在做mask ln的时候。

![](img/4d695e3e6dcbd714b509312b24df76f6_270.png)

是可以看到对应的诶，就是翻译之前的句子，那假如我们这样训练好了一个这样的conditional的，nest的连续age model之后，我们要怎么使用它呢，那我们使用的时候。

我们会先让encoder去普定一个长度。

![](img/4d695e3e6dcbd714b509312b24df76f6_272.png)

然后pd出来是六，那我们就把max token复制六次。

![](img/4d695e3e6dcbd714b509312b24df76f6_274.png)

然后丢到我们的BT的里面，那FTER就会output出第一版的翻译，那这个翻译可能是比较烂的，因为他是只有一个stay就要熬不出来。



![](img/4d695e3e6dcbd714b509312b24df76f6_276.png)

那没关系，我们把这个比较烂的翻译拉到音谱，然后我们去看说哪一些字，在刚刚的generation里面几率是比较低的，我们把几率最低的N个字换成mask token，那换完之后呢。



![](img/4d695e3e6dcbd714b509312b24df76f6_278.png)

再让model重新output一次，被mask掉的字，那这样model的output就会比较好。

![](img/4d695e3e6dcbd714b509312b24df76f6_280.png)

因为它它可以看到旁边已经生出来的字。

![](img/4d695e3e6dcbd714b509312b24df76f6_282.png)

长什么样子，那我要怎么决定每次要mask掉几个字呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_284.png)

那他是用一个linually decay的strategy，也就是说最开始要mask多一点字，那假如你抵扣抵扣十次，那到到第九次的时候，就不要mask太多字，他是用这样的strategy去做mask。



![](img/4d695e3e6dcbd714b509312b24df76f6_286.png)

那这边可以看一个example。

![](img/4d695e3e6dcbd714b509312b24df76f6_288.png)

假如它的input是这句话，那他output的第一个step。

![](img/4d695e3e6dcbd714b509312b24df76f6_290.png)

他一口气就吐出了这段文字，但是因为他是一口气吐出来的，所以没有很好像这里有两个重复的字，但是没关系，我们就把这些几率比较低的黄色的字，把它miss起来，然后再让model吐出来一次。

那这个时候就会做一些求职，那我们再把几率低的字再没死掉，然后再退一次，然后这句话的品质就会更好一点。

![](img/4d695e3e6dcbd714b509312b24df76f6_292.png)

好那mask vd的这个方法其实还蛮厉害的，其实它跟前面两个方法比起来，performance进步非常多。



![](img/4d695e3e6dcbd714b509312b24df76f6_294.png)

那甚至这个大的model，他的performance是快要接近auto regressive的。

![](img/4d695e3e6dcbd714b509312b24df76f6_296.png)

Transformer，接下来介绍完练手培第就要讲insertion的方法。

![](img/4d695e3e6dcbd714b509312b24df76f6_298.png)

那第一篇就是这个insertion transformer，那银色先遣former的概念，就是你有一句残缺的句子，那这是你生成到一半的句子，那你其实可地说，每两个字之间要不要插入一个字。

然后他要插入什么样的字，那我们要怎么做这件事情呢，因为你的decoder，假如input有六个字，那output就会有六个vector。



![](img/4d695e3e6dcbd714b509312b24df76f6_300.png)

那我们先把相邻的两个vector都接起来，做contact name，那这样就会得到每两个字，中间就会有一个representation，那我们把每两个字中间的REGRETATION拿来predict。



![](img/4d695e3e6dcbd714b509312b24df76f6_302.png)

他要插入的字，那假如那一个地方已经没有要插入一个字，Model j f d end of slot，代表说那一个slot是不需要插入字的。



![](img/4d695e3e6dcbd714b509312b24df76f6_304.png)

那假如他是有比例出资格，我们就把它插回去，原本的句子。

![](img/4d695e3e6dcbd714b509312b24df76f6_306.png)

那可是这个model我要怎么训练它呢，那这边我们讲一下我们要怎么制造一个sample，让model去学，那你在DARC里面可能会有一段话，然后他是十个字的，我们就先把这四个字做下，否，然后让他打乱顺序。

然后我们从0~10之间，uniform随便挑一个数字，那假如我挑五，那我就只取前五个字，后五个字就是被我撞掉的字，那我们先把这个句子还原回来，那刚刚被召回掉的字就会形成一个slut。



![](img/4d695e3e6dcbd714b509312b24df76f6_308.png)

等一下就是要插入字的位置。

![](img/4d695e3e6dcbd714b509312b24df76f6_310.png)

好所以说我们现在得到一个chining example，那我们只留下我们呃刚刚挑的那五个字，那在每一格每两个字的中间的这个slot，我们会去pd说，那个slot原本要原本被召回掉的是什么字。

但假如刚刚召回掉连续两次。

![](img/4d695e3e6dcbd714b509312b24df76f6_312.png)

那要怎么办呢，那其实我们就是两个的loss都要算。

![](img/4d695e3e6dcbd714b509312b24df76f6_314.png)

那假如这两个字中间本来就没有字的话，只是个地。

![](img/4d695e3e6dcbd714b509312b24df76f6_316.png)

End of slot，好那刚刚说假如有一个smart是很多个字的话，我们就直接把全部的loss都要计算，那这边其实还有一个策略，就是哦，原本我们可能就是把这些loss都平均，有平均起来。

但是有一个更好的策略是，我们让model倾向伸出这个slut，靠中间的值，为什么要这样做呢，那大家可以想象，假如你要伸出一句话，然后你希望伸出来的step越短越好。

那我们会希望它是用binary ary tree的方法做抵扣，那假如你每次都是抵扣最中间的那一个字，那这样子的话，你抵扣的那棵树就会越接近一颗balance的白那里去。

那所以说我们也可以让这一堆slut里面的。

![](img/4d695e3e6dcbd714b509312b24df76f6_318.png)

自己的loss，在加的时候，把中靠中间的字做一个比较大的微体，然后靠旁边的字做一个比较小的微体。

![](img/4d695e3e6dcbd714b509312b24df76f6_320.png)

那这样model就会学到说我在映射的时候，要优先映射靠中间的字。

![](img/4d695e3e6dcbd714b509312b24df76f6_322.png)

那这边可以看一个sample，就是model在学过binary tree的loss之后呢，他在抵扣这句话的时候，就先抵扣了最中间的那个字，那第二步的时候，他又去抵扣这两个四大最中间的那一个字。

所以每一个time step其实都是比例靠中间的字，那最后他五个step就可以比例出很长的一个句子。

![](img/4d695e3e6dcbd714b509312b24df76f6_324.png)

好那如果你是用uniform的lose去做训练的话，其实第一个test类它也是土地总监，但是后面的次序就比较乱一点，model就没有照着摆能力去的方法去做抵扣。

好那这个models除了可以paro decode之外，其实我们也可以每次选一个几率最大的，直接做抵扣，但是这样花的时间就跟auto与gration model会是一样的。



![](img/4d695e3e6dcbd714b509312b24df76f6_326.png)

那我们就可以比较一下。

![](img/4d695e3e6dcbd714b509312b24df76f6_328.png)

说到底每次抵扣一个字还是perl decode，哪一个比较好，其实他们的performance没有差非常多，但是他们的performance其实都赢过原本的挠头子。



![](img/4d695e3e6dcbd714b509312b24df76f6_330.png)

跟随的方法，甚至跟auto与GRESSIVE的方法是差不多的。

![](img/4d695e3e6dcbd714b509312b24df76f6_332.png)

这边是27。4，然后这边是27。3，所以这篇其实已经算是小小赢过的auto1辈子model。

![](img/4d695e3e6dcbd714b509312b24df76f6_334.png)

好那哎，insertion transformer出来之后。

![](img/4d695e3e6dcbd714b509312b24df76f6_336.png)

又出来一篇叫做kit特。

![](img/4d695e3e6dcbd714b509312b24df76f6_338.png)

这个科米特其实又是芝麻街里面的人物吧，那他为了凑梗，他为了凑如克敏这个字，他把第一个CONTEXTR原本是英文是C开头，它把它换成德文的CONTEXTRO，所以开头就是K，然后就可以凑出克命哦。



![](img/4d695e3e6dcbd714b509312b24df76f6_340.png)

那这个commit it的概念，其实跟颜色选transformer是一模一样的，那唯一的不同就是insertion，显示former有encoder加decoder。

那他把encoder der跟decoder合在同一个model里面，就是就像BT一样，那假如我要中泛音，我就把中文跟英文接在一起，然后插入英文的这半边就好了，那为什么需要这样做呢。

为什么不能乖乖用encoder加encoder呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_342.png)

那他这样做是有一个好处的，我们在做英翻中的话，就把英文跟中文接起来，然后在中文这边做音色的动作。

![](img/4d695e3e6dcbd714b509312b24df76f6_344.png)

那这个model同一个model其实也可以训练中翻译，我们就把后面的中文放完整的中文，然后英文的部分做插入，那这样他就可以同时训练中翻译的任务。



![](img/4d695e3e6dcbd714b509312b24df76f6_346.png)

那我们还可以训练中文英文的作文成power比二题。

![](img/4d695e3e6dcbd714b509312b24df76f6_348.png)

那什么意思呢，就是我们把中文跟英文接在一起，那中文有DP掉一些字，英文也有DP掉一些字，那英文要pd的时候，他要pd word这个字的时候，他就会去看一下中文那边有什么字，那你要回记中文的时候一样。

他要输出好这个字的时候，他可能是看到hello，所以他才输出好，所以这样的训练会让他去optimize英文，中文的joint power。



![](img/4d695e3e6dcbd714b509312b24df76f6_350.png)

第二题，那同时我们也可以只放中文。

![](img/4d695e3e6dcbd714b509312b24df76f6_352.png)

然后做以色选择train，或是只放英文做影射选择train，所以这个model是同时可以学五件事情的。



![](img/4d695e3e6dcbd714b509312b24df76f6_354.png)

那可是为什么我们要同时学五件事情，这样真的有好处吗，那我们可以看他实验结果，第一个他是做单项的翻译，那他是做英文，翻德文或是德文翻译英文，那如果我们只有券单项的翻译是27。8。

那如果同时劝英文翻德文跟德文翻英文，两个方向。

![](img/4d695e3e6dcbd714b509312b24df76f6_356.png)

我嵌在同一个model里面，其实performance是往下掉，因为model要学的事情变多了，反而它普通粉丝是往下掉的，那如果我在学就往头跑的第二题，普通感是又往下掉了。

那这个时候再去学纯英文或是纯德文的marginal，那这个时候performance也没有起来很多，但是他在学完这一系列这五个test之后，最后再做一个ft翻译to，原本你要做英文翻译德文的task。

然后performance就突然暴冲了一波，所以说他同时劝55个task是有道理的，那最后你再做一下FTING。



![](img/4d695e3e6dcbd714b509312b24df76f6_358.png)

就可以超过原本只欠一个task的performance。

![](img/4d695e3e6dcbd714b509312b24df76f6_360.png)

那这个科米这个mode，他之所以用芝麻街的人物来命名，其实他因为他可以跟BERT扮演同样的角色，就他也可以像bot一样当成pretrain model，然后我我用来抽feature。

或是用来翻译ting，然后直接做到stream task，那GU，就是我们常常拿来让BERT跑的一个BENCHMAR，那我们发现拿科米来跑glue这个benchmark。

得到的performance竟然跟BT是不相上下的，那dot本身不能做简选，但我们的科米又同时可以做整ration，又可以做glue这个benchmark。



![](img/4d695e3e6dcbd714b509312b24df76f6_362.png)

那commit it还有一个神奇的功用。

![](img/4d695e3e6dcbd714b509312b24df76f6_364.png)

就是它可以解鸡窝下的刻漏字QA。

![](img/4d695e3e6dcbd714b509312b24df76f6_366.png)

那这个课后制QA的意思，就是我有一个QA的段落，然后中间有个空格，这个空格我们要普及它的正确答案是什么，那假如你用g p t two。



![](img/4d695e3e6dcbd714b509312b24df76f6_368.png)

也就是从左边到右边的那种language model来做pd的话呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_370.png)

你就会有一个问题，你你没办法看到空格右边的东西，那如果你用BT的话呢，虽然它可以看到左边跟右边的东西。



![](img/4d695e3e6dcbd714b509312b24df76f6_372.png)

可是这个空格到底要填入几个mask token。

![](img/4d695e3e6dcbd714b509312b24df76f6_374.png)

你是不知道的，所以bot会有一点小问题，但是commit it，它可以非常自然的在这一个空格的地方，插入新的字，所以最后在这个sample里面。



![](img/4d695e3e6dcbd714b509312b24df76f6_376.png)

它的output的结果是最接近正确答案。

![](img/4d695e3e6dcbd714b509312b24df76f6_378.png)

那他测了整个squad zo夏克制德task，那发现说科明的performance，是赢过g p t two跟vert，那但是这个是zero shot的city，就是这些model都没有在。

都没有在签名的时候，看过任何克制的QA的题目。

![](img/4d695e3e6dcbd714b509312b24df76f6_380.png)

嗯好，那后面科米又有一个新版本，这个新版本叫做MARI林国科米，他就是把各种pair的翻译的data，全部券在同一只科目上面，那大家有兴趣的话可以去看一下这个配合。



![](img/4d695e3e6dcbd714b509312b24df76f6_382.png)

好，那我们这边就是现在要把insertion加上比例，选的操作，那这篇叫做lance sttransform，那要怎么加上delete deletion的操作呢，我们一样有一句中文，我们要把它翻成英文。

那encoder encode完句子之后，decoder会分成三个部分。

![](img/4d695e3e6dcbd714b509312b24df76f6_384.png)

那首先你会有一句是嗯，翻到一半的句子，它还不是很完整，那我们把它丢进decoder，然后再decoder出来之后，再过一个deletion的classifier，然后去预测说这一个字要不要被删掉。

那像在这个例子里面，这个字就被删掉了。

![](img/4d695e3e6dcbd714b509312b24df76f6_386.png)

所以句子就变成这样，那在第二步的时候，我们再把这个句子丢到decoder里面，最后过一个insertion的classify，那他就会去比例说，每两个字之间到底要插入多少个字，那像这里要插入一个字。

它就放一个place holder。

![](img/4d695e3e6dcbd714b509312b24df76f6_388.png)

这里要插入三个字，它就放三个place holder，那最后一步，我们再把这个已经插入placeholder的句子，丢到decoder里面，再过一个token的classifier。

那去预测说每一个place holder到底要翻译成诶，到底要replace成什么样的字，那最后我们就会得到一个完整的句子。



![](img/4d695e3e6dcbd714b509312b24df76f6_390.png)

那这就是investment，transformer在做influence的时候的步骤。

![](img/4d695e3e6dcbd714b509312b24df76f6_392.png)

但是我们要怎么去劝这个model呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_394.png)

那他是用invitation learning的方法好，那要做invitation learning的话，你需要有一个模仿的对象，就是有一个expert，那这个expert呢就跟他的名字有关。

就是levant disc的算法，那这个这个演唱法大家在做A1，在玩开口的时候应该都有用过，就是他会算两个两个sequence之间的编辑距离，像这两个sequence之间的编辑距离是三。

那我们也可以让机器直接帮我们删除，我们要怎么把第一个sequence，编辑成第二个sequence，像这里是我们要在第三个地方映射，在第七个地方比例，然后在第八个地方做replacement。

不过在这篇paper里面，他把replacement这个动作，又把它拆解成先比例再银色。

![](img/4d695e3e6dcbd714b509312b24df76f6_396.png)

这样才比较好处理，好那接下来要怎么训练呢，呃首先我们会在data set里面，制造一些需要被比例制的句子，上次我们只要有一个完整的句子，我们就映射一些错的字进去，那它就需要被比例。

那同时我们也会制造一些需要被音设置的句子，上次有一句完整的句子，我们把一些字drop掉，那它就会变成一句需要被音设置的句子，那有了这两种sample之后呢，我们就让嗯首先先让这个需要背比例子的句子。

这里举一个例子叫说是this is is a pen，那它的意思重复的，所以它需要被举例子，那我们把这句话跟原本的正确答案。



![](img/4d695e3e6dcbd714b509312b24df76f6_398.png)

丢到留言写算法里面。

![](img/4d695e3e6dcbd714b509312b24df76f6_400.png)

那他就会output出哪一个字需要被比例，像这里他会output出第三个字，需要给比例，所以你现在就得到一个training sample。

这training sample就是看到this is is a pen，这句话我要output出00100000，那这个sample就交给deletion的classify去学。



![](img/4d695e3e6dcbd714b509312b24df76f6_402.png)

那再来你筛选的状况也是一样。

![](img/4d695e3e6dcbd714b509312b24df76f6_404.png)

我会有一句需要被音设置的句子，那假如是this pen。

![](img/4d695e3e6dcbd714b509312b24df76f6_406.png)

那INVINCIDENT的算法在看了正确答案之后，就会告诉你说这边要插入两个字，所以你现在又得到一个sample。



![](img/4d695e3e6dcbd714b509312b24df76f6_408.png)

那这个sample我们再交给insertion的classify去学，那最后呢我们把原本这句话插入place holder之后，去看一下原本这些place holder是对应到什么样的字。

那这件事情就交给我们的token classify去学好。

![](img/4d695e3e6dcbd714b509312b24df76f6_410.png)

所以这样就可以训练出我们的BENANCE。

![](img/4d695e3e6dcbd714b509312b24df76f6_412.png)

全是我们那DINSTANT填充满，在抵扣的时候到底是什么样的情况呢，假如我们有一句英文要翻译成日文，那他在第一个时间点，他句子是空的，一开始是空的，所以没有东西要比例，那在第一个时间点。

他一口气就映射了这么多个字，但是因为这些字是一口气生出来的，所以有一些错误，他把这两个字重复了，那在第二步的时候，他就把其中一个字删掉，然后银色的时候又加了新的字。

所以他短短的三部里面就抵扣出一句完整的话。

![](img/4d695e3e6dcbd714b509312b24df76f6_414.png)

好那这是他的结果，这个如果你用auto regressive的transformer的话。

![](img/4d695e3e6dcbd714b509312b24df76f6_416.png)

表现是这样，那如果你用advancement transformer。

![](img/4d695e3e6dcbd714b509312b24df76f6_418.png)

其实它performance并没有差非常多，那如果你是用雷ension disc哎，雷ENSON选择后门加上knowledge distillation。

那就发现他performance是可以超过前车门。

![](img/4d695e3e6dcbd714b509312b24df76f6_420.png)

那如果是看抵扣的速度，我们一般的auto reversion model，要300ms才可以抵扣出句子，但LEVENSON遣充门就只需要100ms。



![](img/4d695e3e6dcbd714b509312b24df76f6_422.png)

附近就可以抵扣出句子，那他所需要花的抵扣的step。

![](img/4d695e3e6dcbd714b509312b24df76f6_424.png)

大概只要二点多个step就可以抵扣出整句话，所以其实还蛮有效率。

![](img/4d695e3e6dcbd714b509312b24df76f6_426.png)

呃那以上就是有INSER弦跟INTRL加比例的方法。

![](img/4d695e3e6dcbd714b509312b24df76f6_428.png)

那最后讲一下c t c base的方法。

![](img/4d695e3e6dcbd714b509312b24df76f6_430.png)

那CTC大家在老师之前。

![](img/4d695e3e6dcbd714b509312b24df76f6_432.png)

语音电试的课都有学过了，就是你的encoder可以直接output出一个VERSECRE。

![](img/4d695e3e6dcbd714b509312b24df76f6_434.png)

那对每一个frame就要布置一个token。

![](img/4d695e3e6dcbd714b509312b24df76f6_436.png)

那这个token是可以包含blank token的，所以最后model复出这句话之后呢，你就把blank token拿掉，然后把重复的字也缩成一个字，最后就会生出你好棒这个句子。

那CTC通常我们是用在语音电子上面比较多，那其实语音电视我们平常比较少，看到有人在讨论，然后托与base的model。



![](img/4d695e3e6dcbd714b509312b24df76f6_438.png)

因为CTC本身就已经是个不错的noto revy model。

![](img/4d695e3e6dcbd714b509312b24df76f6_440.png)

那而且就是对语音电视来说，其实我们在做now to与base的语音辨识的时候，不会遇到很严重的MARIMODELITY问题，因为同一段语音所对应的output的文字，都是有一个正确答案的。

他不会有各种可能的说法，通常一段语音就是搭配一种可能的说法，所以他比较不会遇到martial dd的问题，CTC嗯有有几个小缺点，第一个就是虽然他performance其实还不错，但是还是会输给基坑。

吐西肯德laas model，那第二个是CCTC，虽然是一个NAOTO与类型model，可是他没办法做REFINAL的动作，就是说我因为input是语音，output是文字，那文字不能再拿来input。

然后当成下一个时间点的input，然后做refine不行。

![](img/4d695e3e6dcbd714b509312b24df76f6_442.png)

没有这种用法，它就只能抵扣一次，那所以说嗯假如说我output出一个错字。

![](img/4d695e3e6dcbd714b509312b24df76f6_444.png)

那这这个错字是没有机会被修正，他他不能说，因为他看到旁边已经伸出棒了，然后他才发现啊，这个字生错了。

![](img/4d695e3e6dcbd714b509312b24df76f6_446.png)

然后他把这个字删掉是没有这种机制，所以说为了改良这些哎，这这些问题就有一个新的model叫INPUTER，那它它的概念就是CTC加mask p d，那这个是非常新的paper。

那它的model呢跟CTC很像。

![](img/4d695e3e6dcbd714b509312b24df76f6_448.png)

可是我在input的地方，同时把token sequence也加进来，那在时间为零的时候，我们的token sequence就是全部都是mask token。



![](img/4d695e3e6dcbd714b509312b24df76f6_450.png)

就跟我们在做MASAPD的时候，一开始都放max token是一样的道理。

![](img/4d695e3e6dcbd714b509312b24df76f6_452.png)

第一个test day。

![](img/4d695e3e6dcbd714b509312b24df76f6_454.png)

它就会把一些字换成真的字，那也可以直接要put一个blank token，link token跟mess的token是不一样，MESTER的token是最后都会被换掉。

可是rank token是CTC用的，那个之后要被reduction掉的东西。

![](img/4d695e3e6dcbd714b509312b24df76f6_456.png)

那在时间为一的时候，他就把刚刚output出来的那那句话，在跟云讯号同时丢进encoder里面，那这时候又会把一些max的token换掉。



![](img/4d695e3e6dcbd714b509312b24df76f6_458.png)

所以最后就会得到一句更好的translation。

![](img/4d695e3e6dcbd714b509312b24df76f6_460.png)

也不是TRANSACATION，是speech的，肯定选。

![](img/4d695e3e6dcbd714b509312b24df76f6_462.png)

哦那这边还有一个技巧，就是呃我让与input feature有一个block，就是像这里我讲上block size是三，所以我把input feature每三个分成一块。

那在每一个时间点我都限制model。

![](img/4d695e3e6dcbd714b509312b24df76f6_464.png)

至少要把其中一个token换成真的字，所以所以这样做之后呢，这个model在三步之内一定可以抵扣完整个句子，第一次抵扣一个字，第二次抵扣另一个，第三次就可以全部抵扣完。



![](img/4d695e3e6dcbd714b509312b24df76f6_466.png)

好那这里可以看一个example，他的block size是八，所以它每一格里面就有八个feature，那这些feature原本对应的token都是max和token，都是master和token。

那它在第一个stay就会挑一个字换成真的token，换成真的token，那每一个stay都会调一个字换成token，然后也可以换成blank token，那最后第八个std的时候。

就所有字都已经变成真的token。

![](img/4d695e3e6dcbd714b509312b24df76f6_468.png)

就没有mask token，那他的结果还还算不错。

![](img/4d695e3e6dcbd714b509312b24df76f6_470.png)

就是前面这些是auto与basic的SECRENEWSECRE。

![](img/4d695e3e6dcbd714b509312b24df76f6_472.png)

那7KTOC可能在这叠加set上面的，我也我瑞其实可以压到非常低。

![](img/4d695e3e6dcbd714b509312b24df76f6_474.png)

那如果你用CDC的话，没办法压到那么低嗯，那但是用了computer之后是可以赢过CDC的。

![](img/4d695e3e6dcbd714b509312b24df76f6_476.png)

那这个CCTC或是INPUTER，有没有办法用在文字的生成上面呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_478.png)

那其其实有两篇paper都在做这件事情。

![](img/4d695e3e6dcbd714b509312b24df76f6_480.png)

那我们想要做一个翻译的task，就跟刚刚讨论的test是一样的，就是可能是中文翻译成英文。

![](img/4d695e3e6dcbd714b509312b24df76f6_482.png)

那我们直接让input的句子经过encoder之后。

![](img/4d695e3e6dcbd714b509312b24df76f6_484.png)

做一个up sampling的动作，就是把每一个feature分裂成多个feature，那这样你的句子就变长了，然后变得有点像语音讯号的感觉，那我们再对这个变长的secrets去确认CDC。

那这样就可以用CDC来做翻译，然后是纯文字的。

![](img/4d695e3e6dcbd714b509312b24df76f6_486.png)

那INPUTER也是一样，computer原本左边这里是要放语音讯号进去的，但是我们现在要放成source sentence的up simply，那后面的事情都是跟原本一样。



![](img/4d695e3e6dcbd714b509312b24df76f6_488.png)

那这个方法拿来做成文字的翻译效果好不好呢。

![](img/4d695e3e6dcbd714b509312b24df76f6_490.png)

我我们可以看到，他跟其他所有只要ETIES类，抵扣除句子的方法做比较，那我用CTC来做，我用CTC来做翻译的话，performance可以赢过之前所有的model。



![](img/4d695e3e6dcbd714b509312b24df76f6_492.png)

那IMPPUTER又可以再更好一点。

![](img/4d695e3e6dcbd714b509312b24df76f6_494.png)

那再来我们跟其他的auto aggressive model做比较，或是not auto aggressive model，可是需要iterative refine的model。



![](img/4d695e3e6dcbd714b509312b24df76f6_496.png)

那就发现我们的computer，在抵抵扣的iteration多一点的时候，已经可以赢过auto与base model。



![](img/4d695e3e6dcbd714b509312b24df76f6_498.png)

然后赢过之前所有的银蛇选哪。

![](img/4d695e3e6dcbd714b509312b24df76f6_500.png)

或是refm base的model，所以这个这个方法其实还蛮强的，然后概念也蛮简单的。

![](img/4d695e3e6dcbd714b509312b24df76f6_502.png)

好那最最后再提一个东西，就是knowledge distillation。

![](img/4d695e3e6dcbd714b509312b24df76f6_504.png)

呃，到底为什么有用，这样子就是一天满星的paper，那他做了一个实验，就是我让一个data set同时具有英文翻译，德文，英文翻西班牙文，英文翻法文，这三种翻译全部混混合在同一个data set里面。



![](img/4d695e3e6dcbd714b509312b24df76f6_506.png)

然后让我们的翻译的model，也许那如果说你的翻译的model是auto reverse的话，model其实也分不清到底每次要吐出德文。



![](img/4d695e3e6dcbd714b509312b24df76f6_508.png)

还是吐出西班牙文还是吐出法文，可是他每次讲的是，只要一吐出德文，他的整个句子里面所有的字都会是德文的词汇，这里的每一个点就是他凹凸出来的一句话，然后他的那句话里面的，西班牙文跟德文跟法文所占的比例。

所以我们可以发现，要么那句话整句话都是德文，要么整句话都是西班牙文，要么整句话都是法文，就不会出现，不太会出现同一句话有三种不同的文字的状况，但是如果我们用NAT的model去学硬学这个DATASET。

就发现说他常常会output出同一句话，里面有德文，也有西班牙文，也有法文，所以这个就是我们刚刚讲MARIMODELITY的问题，那现在只是他把MODELITY这件事情，用不同语言来做呈现。

然后更好的更容易去做分析，那假如说我们把data set里面原本是一句英文，会对应到德文，西班牙文法文，那我们把这三个翻译随便DP掉，其中两个，那这个mar提莫在提的问题就会减轻一些。

可是我们发现更有效的是。

![](img/4d695e3e6dcbd714b509312b24df76f6_510.png)

我们直接让n a t model去学auto evasive model的output。

![](img/4d695e3e6dcbd714b509312b24df76f6_512.png)

就是做distillation，那这个状况可以减轻的更多，所以说啊nice distation的效果。



![](img/4d695e3e6dcbd714b509312b24df76f6_514.png)

就是在这个实验里面有一个很好的呈现，那后面还有做一个分析，就是说我在不同的T恤model的size之下，像这个是大model的teacher，Teacher model，这是装的，这是小的，这是很小的。

那让这个我的老auto与编写model去学不同的，提前model的output，那不管你跟哪一个T恤学，都会赢过，不做distillation，就是用real data去确认的结果。

但是对这一篇这个是嗯最开始那篇NAT，那他是跟小model学的效果是最好的，那可是如果是iterative refinement，是跟做model学的比较好。

那如果是max pd是跟大model学比较好，那LEVENSONCHROMAN也是跟大model学会比较好，那所以说每个model都有适合他的器，确model的Tenacity的大小，那又可以发现说。

其实levant reformer，已经跟他的其他model特工也是都差不多了，好那这边其实就讲完了，后面就是一些reference，就是其实里面这三篇paper。

就包括第一篇MAT跟dnsation former，跟最后那一篇分析都是以FACEBOOKAIRESEAR取的。



![](img/4d695e3e6dcbd714b509312b24df76f6_516.png)

这个人做的，那今天讲的有CHROMAN，然后and then insertion trroman，Commit inputer。



![](img/4d695e3e6dcbd714b509312b24df76f6_518.png)

都是这个人做的，这个人其实是那个eason attends fail的第一作者。

![](img/4d695e3e6dcbd714b509312b24df76f6_520.png)

他同同时又最近又在做这个挠to与vs的东西。

![](img/4d695e3e6dcbd714b509312b24df76f6_522.png)

好，这最后是剩下的四篇的reference好。

![](img/4d695e3e6dcbd714b509312b24df76f6_524.png)

其实就讲完了。

![](img/4d695e3e6dcbd714b509312b24df76f6_526.png)