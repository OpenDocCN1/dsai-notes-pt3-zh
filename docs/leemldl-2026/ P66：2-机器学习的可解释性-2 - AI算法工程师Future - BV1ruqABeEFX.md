# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P66：2-机器学习的可解释性-2 - AI算法工程师Future - BV1ruqABeEFX

![](img/9c33c1c5ce19c5bb95301181f395d2c4_0.png)

好那我们来上课啦，那我们接下来呢要讲global的explanation。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_2.png)

那global的explanation是什么意思呢。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_4.png)

我们在前一堂课讲的是local的explanation，也就是给机器一张照片，那他告诉我们说，看到这张图片，他为什么觉得里面有一只猫，而global的explanation。

并不是针对特定某一张照片来进行分析，而是把我们训练好的那个模型拿出来，根据这个模型里面的参数去检查，说对这个network而言，到底一只猫长什么样子。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_6.png)

对于一个network而言，他心里想象的猫长什么样子好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_8.png)

举例来说，假设你今天train好一个convolutional neural network哦，train好在这边啊，那你知道在convolutional neural network里面呢。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_10.png)

就是有很多的filter啊，有很多的这个convolutional layer啊，convolutional layer里面呢有一堆的filter，那你把一张图片作为输入。

Convolutional layer，它的输出是什么呢，它的输出是一个feature map，那每一个filter都会给我们一个mattress，那今天呢假设我们有一张图片。

作为这个convolutional neural network的输入，而这张图片我们用一个大写的X来表示。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_12.png)

因为图片呢通常是一个呃矩阵，好，我们用大写的X呢来表示。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_14.png)

这个图片所构成的矩阵，而如果把这张图片丢进去，你发现某一个filter，比如说filter one，他在他的feature map里面呢。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_16.png)

很多位置都有比较大的值。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_18.png)

那意味着什么哦，那可能就是意味着说这个image x里面有很多。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_20.png)

filter one负责侦测的那些特征哦，这个image里面呢有很多的pattern，是filter one负责侦测的，那filter one看到这些pattern。

所以他在他的feature map上叫output，比较大的值好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_22.png)

但是现在我们要做的是global的explanation。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_24.png)

也就是我们还没有这张图片，image x我们没有针对任何一张特定的图片做分析。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_26.png)

但是我们现在想要知道说对filter one而言，他想要看的pattern到底长什么样子。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_28.png)

那怎么做呢，我们就去制造出一张图片，它不是我们的database里面任何一个特定的图片。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_30.png)

而是机器自己去找出来的。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_32.png)

自己创造出来的，我们要创造一张图片，这张图片它包含有filter one。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_34.png)

要detect的pattern，那借由看这张图片里面的内容。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_36.png)

我们就可以知道filter one，他负责detect什么样的东西好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_38.png)

那怎么找这张图片呢，我们假设filter one，它是这个filter one的这个feature map。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_40.png)

里面的每一个element叫做AIJ。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_42.png)

就是filter one的那个feature map是一个矩阵，那矩阵里面每一个element我们用AIJ来表示，那我们现在要做的事情是找一张图片X。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_44.png)

这张图片不是database里面的图片，而是我们把这个X呢当做一个unknown variable。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_46.png)

当做我们要训练的那个参数。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_48.png)

我们去找一张图片，这张图片丢到这个filter以后。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_50.png)

通过convolutional layer以后输出这个feature map以后。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_52.png)

filter one对应的feature map里面的值，也就是AIJ的值越大越好哦。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_54.png)

所以我们要找一个X好，让AIJ的总和也就是filter one的feature map的output。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_56.png)

它的值越大越好，那我们找出来的这个X啊。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_58.png)

我们就用x star来表示，它不是data base里面任何一张特定的图片。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_60.png)

我们是把X当做unknown的variable，当作要learn的参数去找出这个X大X大。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_62.png)

丢到这个呃已经劝好的network里面。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_64.png)

这个network convolutional layer，它输出的这些feature呃，它的值。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_66.png)

它输出的这个feature map里面的值会越大越好哦。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_68.png)

那怎么解决这个问题呢，呃你会用类似gradient descent的方法啊，只是因为我们现在是要去maximize某一个东西。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_70.png)

所以它不是gradient descent，它是gradient sent。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_72.png)

不过它的原理跟gradient descent是一模一样的。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_74.png)

好，那我找出这个X大以后，我们就可以去观察这个X大，那看看X大有什么样的特征。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_76.png)

我们就可以知道说呃，X大它可以maximize这个filter map，map的value，也就这个filter one，他在detect什么样的pattern好，那这边是一个实际操作的结果了。

我们就用这个ANNEST，ANNEST也是一个手写数字辨识的COPUS，用enlist圈出一个classify，这classify给上一张一张图片，他判断出这张图片里面是1~9的哪一个数字。

训练好这个呃这个数字的classifier以后呢，我们就把它的第二层的convolutional layer。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_78.png)

里面的filter拿出来。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_80.png)

然后找出每一个filter对应的X大哦。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_82.png)

所以下面这边每一张图片就是一个X大，然后每一张图片都对应到一个filter。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_84.png)

那所以你可以想象说，这个第一张图片就是filter one。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_86.png)

他想要detect the pattern，第二张图片就是filter to。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_88.png)

想要detect the pattern，以此类推，那这边是画了12个filter出来好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_90.png)

那从这些pattern里面我们可以发现什么呢。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_92.png)

我们可以发现说这个第二层的convolution啊，他想要做的事情。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_94.png)

确实是去侦测一些基本的pattern，比如说类似笔画的东西哦。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_96.png)

你可以看出这个filter他想侦测什么pattern。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_98.png)

他想侦测横线，这个filter他想侦测什么pattern。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_100.png)

他想侦测斜直线等等哦，这个pattern这个filter他想要侦测什么pattern。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_102.png)

他想要侦测直线啊，每一个filter都有他想要侦测的pattern。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_104.png)

那因为我们现在是在做手写的数字辨识。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_106.png)

那你知道数字就是由一堆笔画所构成的。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_108.png)

所以convolution layer里面的每一个filter，他的工作就是去侦测某一个笔画。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_110.png)

这件事情是非常合理的好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_112.png)

那接下来啊你可能就会去想说，那假设我们不是看某一个filter，而是去看最终这个image classifier的output，那可不可以呢，那我们会观察到什么样的现象呢。

而如果我们今天呐是去看这个image classify，这个dj classify的output，我们想办法去找一张图片X，这个X可以让某一个类别的分数越高越好，因为我们现在做的是这个数字变式哦。

所以这个Y呢总共就会有十个值哦，分别对应到0~9好，那我们就选某一个数字出来，比如说你选数字一出来，然后你希望呢找一张图片，这张图片丢到这个classify以后呃，数字一的分数越高越好。

那如果你用这个方法，你可以看到什么样的东西呢，你可以看到数字0~9吗。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_114.png)

你实际上做一下以后发现没有办法，你看到的结果大概就像是这个样子哦。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_116.png)

就这一张X这张图片，它可以让这个image classify，觉得看到数字零的分数最高，这张图片可以让你的这个classify觉得，看到一的分数最高，二的分数最高，三的分数最高，以此类推。

你会发现说你观察到的其实就是一堆杂讯，你根本没有办法看到数字，那这个结果啊，假设我们还没有教adversarial attack，你可能会觉得嗯好神奇，怎么会这个样子，机器看到一堆是杂讯的东西。

他以为他看到数字吗，怎么会这么愚蠢，但是因为我们已经教过adversal attack，所以想必你其实不会太震惊，因为我们在做adversal attack的时候，我们就已经告诉你说。

在image上面加上一些人眼根本看不到的，奇奇怪怪的杂剧，就可以让机器看到各式各样的物件，那所以这边也是一样的道理，对机器来说，它不需要看到真的很像零那个数字的图片，他才说他看到数字零。

你给他一些乱七八糟的杂讯，他也说看到数字零，而且他的信心分数是非常高的，那所以其实如果你用这个方法，想用这种呃，找一个图片，让image的输出某一个对应到某一个类别的输出，越大越好。

这种方法你想要用这个方法来看到，看到这个呃，呃机器心里想象的某一个object长什么样子，其实不一定有那么容易，那像今天这个例子，今天这个手写数字辨识的例子，你单纯只是找说我要找一张image。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_118.png)

让某对应到某一个数字的信心，分数越高越好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_120.png)

你单纯只做这件事情，你找到的只会是一堆杂讯，怎么办呢。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_122.png)

假设我们希望我们今天看到的是比较像，是人想象的数字。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_124.png)

应该要怎么办呢，你在解这个optimization的问题的时候。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_126.png)

你要加上更多的限制，举例来说，我们先对这个数字已经有一些想象，我们已经知道数字可能是长什么样子。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_128.png)

我们可以把我们要的这个限制，加到这个optimization的过程里面。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_130.png)

举例来说，我们现在不是要找一个X让YI的分数最大。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_132.png)

而是要找一个X，同时让YI还有r of x的分数都越大越好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_134.png)

那这个r of x是什么意思呢。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_136.png)

这个r of x啊，是要拿来衡量说这个X有多么像是一个数字。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_138.png)

举例来说。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_140.png)

今天数字就是由笔画所构成的哦，所以一个数字它在整张图片里面。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_142.png)

它有颜色的地方其实也没那么多哦，整一个图片很大嘛，按那个笔画就是几画而已嘛。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_144.png)

所以在整张图片里面有颜色的地方没有那么多，所以我们可以把这件事情当做一个限制。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_146.png)

硬是塞到我们找X的这个过程中。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_148.png)

硬是塞到我们找X的这个最佳化。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_150.png)

optimization的过程中，那期望，借此我们找出来的X就会比较像是数字好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_152.png)

那如果加上一些额外的限制以后，举例来说，我们希望这个白色的点呢越少越好哦，在这个这个CTRL呢，它的意思就是希望这个白色的点越少越好好，那假设我们加三个限制，希望白色的点越少越好的话哦。

那我们看到的结果会是这个样子，但看起来还是不太像数字啦，不过你仔细观察白色的点的话，还真有那么一点样子，比如说这个啊有点像是六啊，这个有点像是吧好，那如果你要真的得到非常像是数字的东西。

或者是假设你想要像那个文献上啊，你知道文件上有很多人都会说啊，他用某种这个global explanation的方法，然后呢去反推一个image classify，他心中的某种动物长什么样啊。

比如说你看下面这篇文献，他告诉你说他有一个image classifier，还有我们刚才提到的方法，它可以反推说哦，这个image classify里面，心中的这个丹顶鹤长什么样子。

或他心中的这个甲虫长什么样子，来看这些图片，诶这个真的都还蛮像丹顶鹤的，你完全可以看到说诶这个有一只鸟，诶这个丹顶鹤，然后他有一只脚插在水里面，那这些图片真的都可以看到甲虫在图片里面。

但是你要得到这样子的图片呢，其实没有你想象的那么容易，你如果仔细去看这个文献的话，你就会发现说嗯要得到这些图片，你必须要下非常多的CTRL，你要根据你对影像的了解的一个object。

长什么样子的了解下非常多的限制，再加上一大堆的hyper parameter tuning，你知道我们解optimization的problems的时候，你也是需要这个调hyper parameter。

比如说learning rate之类的好，所以下一堆CTRL调一堆参数哦，你才可以得出这样的结果哦，所以这样的结果并不是，随随便便就可以轻易的做出来的。

好像刚才讲的那种global explanation的方法，如果你真的想要看到非常清晰的图片的话哦，现在有一个招数是使用generator。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_154.png)

你就训练一个image的generator，你有一堆训练资料哦，有一堆image来拿这个一堆image呢。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_156.png)

来训练一个image的generator，比如说你可以用game啊，可以用VAE啊，等等给我们教过了。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_158.png)

via1我没有教过，反正就是你可以有想办法呢，训练出一个image generator，image generator输入是一个low dimensional的vector。

是一个从高ction distribution里面sample出来的，低维度的向量叫做Z丢到这个image rator以后呢，它输出就是一张图片X，那这个image generator我们用大G来表示。

那输出的图片X啊，我们就可以写成X等于大g of z好，那怎么拿这个emission rator来帮助我们，反推一个image classify里面他所想象的某一种类别，比如说某一只猫。

它心里所想象的猫这个类别，或狗这个类别长什么样子呢。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_160.png)

那你就把这个image classify呃，image generator跟这个image classify接在一起哦。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_162.png)

这个image generator输入是一个Z输出是一张图片。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_164.png)

然后这个image classify把这个图片呢当做输入。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_166.png)

然后输出分类的结果，那在刚才前几页投影片里面呢。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_168.png)

我们都是说我们要找一个X，让Y里面的某一个dimension。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_170.png)

让某一个类别它的信心分数越高越好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_172.png)

那我们说这个X叫做X2，那么刚才看到说光这么做，你往往做不出什么特别厉害的结果。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_174.png)

现在有了image generator以后，方法就不一样了。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_176.png)

我们现在不是去找X，而是去找一个Z。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_178.png)

我们要找一个Z，这个Z通过image的rate产生X，再把这个X丢到image classify去。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_180.png)

产生Y以后，希望Y里面对应的某一个类别，它的分数越大越好哦，我们找一个ZZ产生xx在产生Y以后。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_182.png)

希望YI越大越好，那这个可以让YI越大越好的Z啊。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_184.png)

我们就叫它z star，找出这个z star以后。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_186.png)

我们再把这个Z大丢到G里面，丢到卷的RATOR里面，看看它产生出来的image x大长什么样子来好。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_188.png)

![](img/9c33c1c5ce19c5bb95301181f395d2c4_189.png)

那找出来的x star长什么样子呢。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_191.png)

假设你今天想要产生，比如说比比如说这个让蚂蚁分数，让蚂蚁的信心分数最高的image，那产生出来的蚂蚁的照片哦，这个很厉害，这个长得是这个样子，都看得出这个就是蚂蚁哦，或者是要让机器产生火山的照片。

产生一堆照片，丢到classifier以后，火山的信心分数特别高的，那确实可以找出一堆image，这些image1看就知道像是火山一样好，但讲到这边，你可能会觉得嗯，呃这整个想法听起来有点强调啊。

这样就是呃今天呢你你找出来的图片，如果跟你想象的东西不一样啊，今天找出来的蚂蚁火山跟你想象的不一样啊，你就说这个explanation的方法不好，然后你硬是要弄一些方法去找出来。

那个图片跟人想象的是一样的啊，你才会说这个explanation的方法是好的，那也许今天对机器来说，它看到的图片就是像是些杂讯一样啊，也许他心里想象的某一个数字，就是像是那些杂讯一样啊。

那那我们却不愿意认同这个事实，而是硬要想一些方法，让机器产生出看起来比较像样的图片，那今天explainable AI的技术往往就是有这个特性，我们其实没有那么在乎机器真正想的是什么。

其实我们也不知道机器真正想的是什么，我们是希望有些方法解读出来的东西，是人看起来觉得很开心的，然后你就说嗯，机器想的应该就是这个样子，然后你的老板啊，你的客户啊听了就会觉得很开心。

那今天explainable AI往往会呃有这样的倾向好，那我们今天呢就是跟大家介绍了。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_193.png)

explainable AI的两个呃主流的技术，一个是local的explanation，一个是global的explanation。

那其实EXPLAABLE的machine learning还有很多的技术。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_195.png)

这边再举一个例子，举例来说啊，你可以用一个比较简单的模型，想办法去模仿复杂的模型的行为，如果简单的模型可以模仿复杂模型的行为，你再去分析那个简单的模型，也许我们就可以知道那个复杂的模型在做什么。

举例来说，你有一个neural network，你它是一个黑盒子，你丢一堆X进去，比如说丢一堆图片进去，它会给我们分类的结果，但我们搞不清楚他决策的过程。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_197.png)

因为neural network本身非常的复杂好，那我们能不能拿一个比较简单的模型出来，比较能够分析的模型出来，拿一个INTERPRETABLE的模型出来，比如说一个linear model，然后呢。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_199.png)

我们训练这个linear的model去模仿neural network的行为，neural network输入x1到X大N，他就输出y one到Y大N。

那我们要求这个linear model输入x1到X大N，也要输出跟对bug这个黑盒子一模一样的输出，y one到Y大N，我们要求这个linear的model去模仿黑盒子的行为。

那如果linear的model可以成功模仿黑盒子的行为，我们再去分析linear model做的事情，因为linear的model比较容易分析，分析完以后，也许我们就可以知道这个黑盒子在做的事情。

而当然这边你可能会有非常非常多的问题，举例来说呃，一个linear的model，有办法去模仿一个黑盒子的行为吗，我们开学第一堂课就说过，说有很多的问题是neural network才做得到。

而linear的model是做不到的，所以今天黑盒子可以做到的事情，linear的model不一定能做到啊。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_201.png)

没错，在这系这一系列的work里面呢，有一个特别知名的叫做local interpretable model。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_203.png)

agnostic explanation啊。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_205.png)

它的缩写呢是L那像这种方法，他也没有说，他要用linear model去模仿黑盒子全部的行为，还有特别开宗明义。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_207.png)

在名字里面就告诉你说他是local interpret able，也就是它只让linear model去模仿这个黑盒子。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_209.png)

在一小个区域内的行为。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_211.png)

因为linear model能力有限，他不可能模仿整个neural network的行为。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_213.png)

但也许让他模仿一小个区域的行为，那我们就解读那一小个区域里面发生的事情，那这个是一个非常经典的方法。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_215.png)

叫做line，如果你想要知道lb是什么的话，你可以看以下的录影。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_217.png)

那今天呢我们就不再细讲，那在作业里面我们也有有关line的作业。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_219.png)

那这个部分就是留给大家自己去阅读文献。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_221.png)

自己去感受这个line呢是在做什么好，那这个部分呢就是有关explainable machine learning的简介，那我们来看一下线上有没有同学有问问题的好，哇哎我是可以那个看到大家的问题的，诶。

等一下哦。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_223.png)

好有同学问说，如果在classify上面多加一个都不是的选项，并把这个选项的可能性最小化，会不会好一点，呃我试着来解读你的问题哦，你的问题是说我们刚才劝了一个image的classify。

比如DIJ的classify，那如果我们在这个classify上多加一个选项，这个选项是我们输入的东西，它不是任何的呃，不是任何的digit，那我们今天得到的结果会不会好一点呃，我没有做过类似的实验。

在实作上啊，如果我们今天是拿ENNEST的话，可能会有点小问题，因为ENNEST里面并没有任何图片，不是数字，我们所有的图片都是数字，那但另外一方面，假设我们说啊，我们今天真的收集的。

只收集到一些不是数字的图片，然后多加一个类别，说有些东西就叫做它不是数字，然后我们要求说今天输入一张图片，同时要让classify觉得他像是数字，同时又要他觉得说不是数字的。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_225.png)

那个类别的的的几率越小越好，到底会发生什么事情呢，我其实没有试过。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_227.png)

所以我一下子没有非常好的答案，不过依照今天这个呃这个呃，diversal attack这么容易成功的状况，我认为还是非常有可能可以找到一张image，看起来不像是数字，但是network觉得它是数字。

同时它不是数字的几率又非常的小，但是我没有试过这个，如果你有兴趣的话，其实也可以自己试试看，看看结果会怎么样，好好好。



![](img/9c33c1c5ce19c5bb95301181f395d2c4_229.png)

这样子，不知道大家有没有问题，我知道直播其实没有非常的及时啊，所以我跟大家其实应该是有几分钟的。

![](img/9c33c1c5ce19c5bb95301181f395d2c4_231.png)

几分钟的delay啊。