# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P4：3-PyTorch Tutorial-1 - AI算法工程师Future - BV1ruqABeEFX

![](img/c1be6461eafac84e9f3cb450f666a5f2_0.png)

好那各位同学大家好，我是曾源，今天要跟大家讲的是呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_2.png)

这个学期大家会大量使用的机器学习套件，Pytorch。

![](img/c1be6461eafac84e9f3cb450f666a5f2_4.png)

![](img/c1be6461eafac84e9f3cb450f666a5f2_5.png)

好啊。

![](img/c1be6461eafac84e9f3cb450f666a5f2_7.png)

今天要讲的东西，包括说PYTORCH到底是什么，然后如何用PYTORCH，去训练和测试我们的神经网络。



![](img/c1be6461eafac84e9f3cb450f666a5f2_9.png)

以及既然我们要训练和测试神经网络，要如何去把我们的资料给用PYTORCH给读进来。

![](img/c1be6461eafac84e9f3cb450f666a5f2_11.png)

那在PYTORCH里面，我们以后我们会用dr set跟data loader。

![](img/c1be6461eafac84e9f3cb450f666a5f2_13.png)

那PYTORCH的读进来的资料，会是什么样的形式呢。

![](img/c1be6461eafac84e9f3cb450f666a5f2_15.png)

在PYTORCH里面，我们将这些读进来的资料，我们称之叫cancer，那底下也会讲诶。

![](img/c1be6461eafac84e9f3cb450f666a5f2_17.png)

等下我会讲到说tensor里面的要怎么用，那到底是什么东西这样子，然后最后会讲到说要怎么用torch点N。



![](img/c1be6461eafac84e9f3cb450f666a5f2_19.png)

还有torch点option，这两个library来去定义你的神经网络。

![](img/c1be6461eafac84e9f3cb450f666a5f2_21.png)

来去选择你的loss function，并且去选择你的optimization的演算法。

![](img/c1be6461eafac84e9f3cb450f666a5f2_23.png)

去更改你的神经网络的参数，那最后会提到说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_25.png)

那你千千万股训练的模型，你要怎么样去存档跟读取。

![](img/c1be6461eafac84e9f3cb450f666a5f2_27.png)

呃首先就是我们会假设这边的同学都是修过额。

![](img/c1be6461eafac84e9f3cb450f666a5f2_29.png)

修过python3相关的课程的，所以我们不会再展示python3的基本语法，并且如果等下会讲到一些深度学习的概念。



![](img/c1be6461eafac84e9f3cb450f666a5f2_31.png)

那如果大家等一下听不清楚的话，没有关系。

![](img/c1be6461eafac84e9f3cb450f666a5f2_33.png)

等下晚上把投影片上传以后，我会把相关的链接都附在同一片的右下角，大家可以先去呃去复习啊。

![](img/c1be6461eafac84e9f3cb450f666a5f2_35.png)

去看一下弘毅老师的去年的上课影片。

![](img/c1be6461eafac84e9f3cb450f666a5f2_37.png)

去了解一下。

![](img/c1be6461eafac84e9f3cb450f666a5f2_39.png)

那这边也附上了老师去年的前两个影片的连接，最主要是这前两个影片。

![](img/c1be6461eafac84e9f3cb450f666a5f2_41.png)

当然如果这边有同学是学过线性代数的，有人使用过能拍的话，会发现说拍forge跟能拍有很大的相似之处。

![](img/c1be6461eafac84e9f3cb450f666a5f2_43.png)

那等下在听的时候可能会比较容易理解这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_45.png)

那首先PYTORCH是什么，那PYTORCH基本上就如我刚刚所说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_47.png)

它是一个在Python里面的机器学习的框架，它的好处是它把一些高维的矩阵运算呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_49.png)

这边的高维矩阵就是tor，是叫tensor。

![](img/c1be6461eafac84e9f3cb450f666a5f2_51.png)

是用GP可以用GPU去做加速运算的，除此之外。

![](img/c1be6461eafac84e9f3cb450f666a5f2_53.png)

因为我们在训练神经网络的时候，我们会去要去计算一些梯度的部分，那PYRS已经把这些梯度计算理论给打包的。



![](img/c1be6461eafac84e9f3cb450f666a5f2_55.png)

非常的漂亮漂亮，可以用很简单的的成几样程式吧。

![](img/c1be6461eafac84e9f3cb450f666a5f2_57.png)

就可以直接去计算并且训练我们的神经网络，这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_59.png)

OK那首先呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_61.png)

如果大家有看过弘毅老师，去年的第一个影片的话，会知道说我们要训练一个神经网络。

![](img/c1be6461eafac84e9f3cb450f666a5f2_63.png)

或有三个步骤，第一个步骤是先定义我们的神经网络，它里面有哪些层。

![](img/c1be6461eafac84e9f3cb450f666a5f2_65.png)

长得什么样，那当我们定义完神经网络以后，这样接下来就是要去选。

![](img/c1be6461eafac84e9f3cb450f666a5f2_67.png)

我们要去最小化的那个loss function，选完以后再去挑一个梯度下降的的最佳。

![](img/c1be6461eafac84e9f3cb450f666a5f2_69.png)

换一个算法来去优化我们的mono的参数。

![](img/c1be6461eafac84e9f3cb450f666a5f2_71.png)

当然额相关的影片我会在右下角，等晚上影片投影片上传的时候。

![](img/c1be6461eafac84e9f3cb450f666a5f2_73.png)

大家可以再回去看一下，那除此之外。

![](img/c1be6461eafac84e9f3cb450f666a5f2_75.png)

除了训练我们的神经网络以外，我们还要去做验证，Validation，还有测试testing。

![](img/c1be6461eafac84e9f3cb450f666a5f2_77.png)

那关于我们在训练跟测的验证的，这个要我们会通常会反复的去训练跟验证。

![](img/c1be6461eafac84e9f3cb450f666a5f2_79.png)

要去训练和验证，所以最后才会去做testing。

![](img/c1be6461eafac84e9f3cb450f666a5f2_81.png)

那这个步这个步骤呃，弘毅老师相关影片附在右下角，那这个步这些东西。

![](img/c1be6461eafac84e9f3cb450f666a5f2_83.png)

我们是怎么用PYORCH去做的呢，首先呃如刚刚所说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_85.png)

首先先从到底要怎么把资料读进，我们的促进我们的档案开始。

![](img/c1be6461eafac84e9f3cb450f666a5f2_87.png)

然后在PYTORCH里面有两个东西负责，一个是torch diaset跟torch点dai loader。



![](img/c1be6461eafac84e9f3cb450f666a5f2_89.png)

首先pose点比赛所做的事情。

![](img/c1be6461eafac84e9f3cb450f666a5f2_91.png)

就是我们把我们一开始的原始资料，给一笔一笔的读进来。

![](img/c1be6461eafac84e9f3cb450f666a5f2_93.png)

并且我们用一个Python的class把它打包好，让我们去呼叫它，好呼叫。

![](img/c1be6461eafac84e9f3cb450f666a5f2_95.png)

这所以除了呃除了我们的原始资料以外，还要用原始资料输入模型以后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_97.png)

我们预期会得到的值这样子，譬如说用一举例，我们只是给你们很多很多的各式各样的资料。

![](img/c1be6461eafac84e9f3cb450f666a5f2_99.png)

譬如说他觉得有没有发烧症状，他觉得他自己有没有呃感冒症状。

![](img/c1be6461eafac84e9f3cb450f666a5f2_101.png)

或那我们要的预测结果，就是说，我们希望你可以判断说明天的确诊人数是多少。

![](img/c1be6461eafac84e9f3cb450f666a5f2_103.png)

相当那data holoader所做的事情，就是我们把DATASET的一笔一笔的资料。

![](img/c1be6461eafac84e9f3cb450f666a5f2_105.png)

我们把它给合并成一个呃，一个一个的batch。

![](img/c1be6461eafac84e9f3cb450f666a5f2_107.png)

一个一个的batch的的意思，就是里面会有可能会有几笔资料这样子，然后除了除此之外。

![](img/c1be6461eafac84e9f3cb450f666a5f2_109.png)

他data loader还背后有一些平行化处理的部分，让我们这些资料读取更快速呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_111.png)

至至于程式码要怎么写，首先我会先写一个写一个东西去去override。

![](img/c1be6461eafac84e9f3cb450f666a5f2_113.png)

原本PYTORCH被定义好的DARSON。

![](img/c1be6461eafac84e9f3cb450f666a5f2_115.png)

等一下下一页同学都会讲到，所以我们先有一个我们定义好的DIASET，My dad set。

![](img/c1be6461eafac84e9f3cb450f666a5f2_117.png)

然后去创造一个data set，结果object以后我们用一个DAYNLOADER把它给包起来。

![](img/c1be6461eafac84e9f3cb450f666a5f2_119.png)

然后去跟DIYLOAD定义说，我们需要用多大的backside，然后我们需不需要去收获我们的training data。



![](img/c1be6461eafac84e9f3cb450f666a5f2_121.png)

A或testing data，那通常我们training的时候会去会去SHO。

![](img/c1be6461eafac84e9f3cb450f666a5f2_123.png)

我们的data，而在是在测试的时候，我们就不会去去重新排列，那关于batch。

![](img/c1be6461eafac84e9f3cb450f666a5f2_125.png)

到底为什么要用一个，把一些资料给合并成一个一个batch，跟为什么要SHO。

![](img/c1be6461eafac84e9f3cb450f666a5f2_127.png)

或者为什么不SHO的话，可以参考弘毅老师这边的上课图片，这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_129.png)

OK那刚刚提到说要做，要我们要定义一个data set object之前。

![](img/c1be6461eafac84e9f3cb450f666a5f2_131.png)

我们要先先去写一个class，让去定义我们自己的data加set这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_133.png)

那你要自定义自己的data加set时候会有三个步骤，当然啊这些东西在作为一的城市里面。

![](img/c1be6461eafac84e9f3cb450f666a5f2_135.png)

我们会已经帮你写好，但是我们这边是做一个概概率的介绍。

![](img/c1be6461eafac84e9f3cb450f666a5f2_137.png)

这样子，那呃要定义自己的叠加赛有三个步骤，首先你要先override一个visualization的function。



![](img/c1be6461eafac84e9f3cb450f666a5f2_139.png)

他做的事情就是你在钢琴一行。

![](img/c1be6461eafac84e9f3cb450f666a5f2_141.png)

你去护照my dad set这个这个class，它你去产生一个object的时候，他会呼叫第一个INCIALIZATION的function。



![](img/c1be6461eafac84e9f3cb450f666a5f2_143.png)

所以你在那个方程做的事情，是要把资料给读进来，并且去对他做一些你想要做的前处理。

![](img/c1be6461eafac84e9f3cb450f666a5f2_145.png)

这样子，第二个function，是当你在去读取我们一笔一笔的资料时候。

![](img/c1be6461eafac84e9f3cb450f666a5f2_147.png)

他就会呼叫这个gai on这个方式他就是会去看。

![](img/c1be6461eafac84e9f3cb450f666a5f2_149.png)

说譬如说我的第I语资料它是什么东西，那你的这个方向你要写的就是。

![](img/c1be6461eafac84e9f3cb450f666a5f2_151.png)

你要如何把你的资料给回传出来，这样子，第三个第三个function要做的事情是。

![](img/c1be6461eafac84e9f3cb450f666a5f2_153.png)

你要去override这个late的function，来，让你的data loader知道说你的资料到底总共有多少。



![](img/c1be6461eafac84e9f3cb450f666a5f2_155.png)

这样他再去算你的bash的时候，才会知道总共有几个bash等等。

![](img/c1be6461eafac84e9f3cb450f666a5f2_157.png)

OK那刚刚讲的可能有点抽象屁。

![](img/c1be6461eafac84e9f3cb450f666a5f2_159.png)

所以这边画一个图来跟大家做说明，所以我们写好了一个their set class，我们data loader所做的事情。



![](img/c1be6461eafac84e9f3cb450f666a5f2_161.png)

是我们上面已经定义好的，Data loader，假设我们的best side是五的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_163.png)

然后我们不要去售后我们的资料，那我们会data lover会做的事情就是会去呼叫da set。

![](img/c1be6461eafac84e9f3cb450f666a5f2_165.png)

五四会呼叫刚刚GAIM的方程五四，然后得到五笔资料以后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_167.png)

我们去把它合并成一个batch，然后接下来拿这笔袋再去做后续的训练，这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_169.png)

OK那刚刚讲的是到底要怎么把资料读进来的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_171.png)

这个部分用一个比较概念化的形式说明，那到底PYTORCH读进来的东西。

![](img/c1be6461eafac84e9f3cb450f666a5f2_173.png)

我们要去怎么样去做数值呢，呃到它到底是什么，我们要怎么去做对他做处理呢。

![](img/c1be6461eafac84e9f3cb450f666a5f2_175.png)

在PYORCH里面，我们读进来的东西通常都是一些矩阵。

![](img/c1be6461eafac84e9f3cb450f666a5f2_177.png)

一些阵列，那我们在Python时里面称呼他为tensor，那tensor就是如刚刚所说的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_179.png)

它是一些高维度的阵列，你譬如说我们在假设，我们在对声音讯号去做一些处理的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_181.png)

它就是一些异维的阵列，如果是对黑白的灰线影像做处理的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_183.png)

它可能是一些二维阵列，如果是我们在初一彩色影像会有红绿蓝啊。

![](img/c1be6461eafac84e9f3cb450f666a5f2_185.png)

红蓝绿三个颜色，然后去就会是一个三维的探测。

![](img/c1be6461eafac84e9f3cb450f666a5f2_187.png)

这样子，如果你不知道你的读进来的资料。

![](img/c1be6461eafac84e9f3cb450f666a5f2_189.png)

到底大小是多大的话，你可以呼叫点，这个方式可以看到说你的你的资料。

![](img/c1be6461eafac84e9f3cb450f666a5f2_191.png)

它有总共有几个维度，然后它的每个维度的强度是多少。

![](img/c1be6461eafac84e9f3cb450f666a5f2_193.png)

譬如说以中间这个3×5的矩阵举例的话，你估照点SHA这个方式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_195.png)

就会看到说他的第零个维度的长度是三，第一个维度的长度。

![](img/c1be6461eafac84e9f3cb450f666a5f2_197.png)

这样子，那如果有使用过南派的同学，就会知道说呃，咱们这边PyTorch dimension跟npd access一样的东西。



![](img/c1be6461eafac84e9f3cb450f666a5f2_199.png)

之后再使用一些后续的方式的时候，是在这。

![](img/c1be6461eafac84e9f3cb450f666a5f2_201.png)

OK那所所以我们讲到说tensor是些高维阵列，那我们到底要怎么产生这些东西，如果同学有用过python3的话，或用文N派的话。



![](img/c1be6461eafac84e9f3cb450f666a5f2_203.png)

通常都是对于list或是number派ARRAP去做运算，那torch已经有写好方程式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_205.png)

你可以直接利用Python earth或是npon array，去直接把它转换成tens，或者是除此之外，有时候你想要去做一些数值运算，你想要一些全部都是零或全部都是一的东西。

那你也可以宣告说我是我是我啊，你可以指定一个大小。

![](img/c1be6461eafac84e9f3cb450f666a5f2_207.png)

譬如说我想要一个2×2的矩阵，那我就呼叫push点zeros。

![](img/c1be6461eafac84e9f3cb450f666a5f2_209.png)

然后你给他一个2×2的大小，它就会混出一个2×2的，全部都是零的矩阵，那也可以去宣告一个全都是一的矩阵，像底下这个样子。



![](img/c1be6461eafac84e9f3cb450f666a5f2_211.png)

那我们现在就是把我们的一些数值的的东西。

![](img/c1be6461eafac84e9f3cb450f666a5f2_213.png)

给读进来了，那我们可以对它做什么样的处理呢，其实torch已经帮我们，大部分的背后的东西都写好了。

![](img/c1be6461eafac84e9f3cb450f666a5f2_215.png)

你可以直接对它做加法，对做啊做啊，对它做减法可以去做一些。

![](img/c1be6461eafac84e9f3cb450f666a5f2_217.png)

要是要做一些比较复杂的数学运算，像是取对数的话，可以取power，你要对他负求和或是取平均。

![](img/c1be6461eafac84e9f3cb450f666a5f2_219.png)

都有一些对应的方程，那除此之外还有更多的方程。

![](img/c1be6461eafac84e9f3cb450f666a5f2_221.png)

那等下会稍微讲到一些，除了数值运算的部分以外。

![](img/c1be6461eafac84e9f3cb450f666a5f2_223.png)

如果说过线性代代数的同学就会知道说，有时候我们的矩阵应该去做一些呃，维度的互换的部分去。

![](img/c1be6461eafac84e9f3cb450f666a5f2_225.png)

那在快速里面它对应的方式就叫做transpose，譬如说我们有一个2×3的阵列。

![](img/c1be6461eafac84e9f3cb450f666a5f2_227.png)

我们想要把它的两个维度给互换，得到一个3×2的阵列，那只要去呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_229.png)

你只要去呼叫transpose01这个方式，他就去把它的定理的维度。

![](img/c1be6461eafac84e9f3cb450f666a5f2_231.png)

跟第一个维度去做互换，这样子，除此之外额有时候你会有一些高纬的阵列。

![](img/c1be6461eafac84e9f3cb450f666a5f2_233.png)

但它有个维度可能刚好只有程度是一，譬如说我右上角有个1×2乘三的的阵列。

![](img/c1be6461eafac84e9f3cb450f666a5f2_235.png)

那我要把它的那个维度给消除掉。

![](img/c1be6461eafac84e9f3cb450f666a5f2_237.png)

把它变成一个二维的，单纯的二维的2×3的矩阵的话，我就会呼叫这个点SZE这个方式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_239.png)

把他的那个维度给移除掉呃，除此之外，当然还有反过来操作。

![](img/c1be6461eafac84e9f3cb450f666a5f2_241.png)

就是如果你想要加一个维度的话，怎么加，那跟刚刚的做法差不多，我想要在我想要把2×3的矩阵变成二乘。

![](img/c1be6461eafac84e9f3cb450f666a5f2_243.png)

1×3的矩阵，我只要呼叫and squeeze。

![](img/c1be6461eafac84e9f3cb450f666a5f2_245.png)

他就会在第一个呃，第一个维度的地方增加一个长度，是一的单元选单。

![](img/c1be6461eafac84e9f3cb450f666a5f2_247.png)

呃最后最后的一个介绍的运算是。

![](img/c1be6461eafac84e9f3cb450f666a5f2_249.png)

假设我们有很多个矩阵。

![](img/c1be6461eafac84e9f3cb450f666a5f2_251.png)

我们是呃成多个tensor，我们想要把它去合并起来，合并成一个tensor，譬如说我们右上角有个2×1乘三的值。



![](img/c1be6461eafac84e9f3cb450f666a5f2_253.png)

矩阵额又是呃，Y是一个23乘三的tensor。

![](img/c1be6461eafac84e9f3cb450f666a5f2_255.png)

Z是一个22乘三的tensor，我们想要把它沿着它们的长度一样的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_257.png)

那个轴合并起来，得到一个26乘三的tensor，那我们呼叫语法就是torch点，看看cat name。



![](img/c1be6461eafac84e9f3cb450f666a5f2_259.png)

简称torch点can，然后我把它跟他说，我们是要沿着第一个维度去做合并。

![](img/c1be6461eafac84e9f3cb450f666a5f2_261.png)

然后最后就会得到一个26乘三的tensor，这样子，当然我这边是做一个很很概率的介绍。

![](img/c1be6461eafac84e9f3cb450f666a5f2_263.png)

所以除了这些分词以外，还有很多很多的操作，那如果同学们有想要做什么事情。

![](img/c1be6461eafac84e9f3cb450f666a5f2_265.png)

然后不想要自己思考很久，要怎么用加减乘除去多出来的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_267.png)

可以先去看PYTORCH的官方的说明文件，先去看有没有类似的操作。

![](img/c1be6461eafac84e9f3cb450f666a5f2_269.png)

![](img/c1be6461eafac84e9f3cb450f666a5f2_270.png)

那不OK讲完说tensor怎么用啊，那同学们对于tensor还不是很熟悉。

![](img/c1be6461eafac84e9f3cb450f666a5f2_272.png)

所以可能会遇到一些问题，所以先快速的提到一些，同学们之后可能会遇到的小问题。

![](img/c1be6461eafac84e9f3cb450f666a5f2_274.png)

譬如说呃PYTORCH它的里面的资料，它的tensor里面的资料形态有时候是浮点。

![](img/c1be6461eafac84e9f3cb450f666a5f2_276.png)

有时候是小数，有时候是整数，所以当你的模型或者你的跟你的data。

![](img/c1be6461eafac84e9f3cb450f666a5f2_278.png)

使用是不同的资料形态的时候，有时候会有些错误，这时候你就可以去参考一下呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_280.png)

官开放式官方文件去看书，是不是呃，如果你看到说是跟dn ta有关的错误的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_282.png)

就可以去参考一下官方文件，看出要怎么样去调整你的产生吗。

![](img/c1be6461eafac84e9f3cb450f666a5f2_284.png)

OK那刚刚有提到说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_286.png)

如果对南派很熟悉的同学的话，会发现说PTORCH呢他有很多类似的方式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_288.png)

所以如果呃在有使用过number派的同学，会发现说你在number派所使用过的方式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_290.png)

基本上都有对应的开拓形式，譬如说你要查看他的大小，查看他的资料形态。

![](img/c1be6461eafac84e9f3cb450f666a5f2_292.png)

或者说刚刚所提到的，你要调整一个矩阵的大小，你要移出一个维度。

![](img/c1be6461eafac84e9f3cb450f666a5f2_294.png)

你要增加一个维度，基本上都有对应的方式，这样子OK除了除此之外。

![](img/c1be6461eafac84e9f3cb450f666a5f2_296.png)

还有一个通常会遇到的问题，是说额会是你的tensor在哪边跑的一个问题呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_298.png)

应该说譬如说我刚刚一开始有提到说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_300.png)

PYTORCH的一个好处，就是在它可以它提供了一个方法，是我们可以把一些矩阵的运算。

![](img/c1be6461eafac84e9f3cb450f666a5f2_302.png)

让它在我们的GPU显示卡上面去跑，这样子跑的时候它的运算会变得更快。

![](img/c1be6461eafac84e9f3cb450f666a5f2_304.png)

但是不是每台电脑都会有显示卡。

![](img/c1be6461eafac84e9f3cb450f666a5f2_306.png)

所以我们要怎么样去特别跟POR说，我们想要在显示卡上面做运算呢。

![](img/c1be6461eafac84e9f3cb450f666a5f2_308.png)

首先呃如我刚刚所说，PYOR是会预设是你在CPU上面四时运算。

![](img/c1be6461eafac84e9f3cb450f666a5f2_310.png)

那我们就可以使用点to这个方式，去把我们的tensor给移动到它的对应的的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_312.png)

CPU或者GPU的位置，那所以如果你要把一个tensor移到CPU。

![](img/c1be6461eafac84e9f3cb450f666a5f2_314.png)

就是呼叫上面这行式子，如果你要把它移到GPU。

![](img/c1be6461eafac84e9f3cb450f666a5f2_316.png)

就是呼叫下面这行式子这样子，那同学们可能会想说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_318.png)

要怎么知道我的电脑是不是资源CPU的的运算呢，你就可以呼叫上面那个torch点code点available。



![](img/c1be6461eafac84e9f3cb450f666a5f2_320.png)

这个方式去看出你的电脑是不是有装好呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_322.png)

相关的套件，让你的让你的城市码可以用GPU去做加速，这样子呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_324.png)

这些部分在口袋上面，口袋上面已经有提供GPU碎纸之后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_326.png)

同学在撰写，在写作业的时候，也是可以用这个方程去检查。

![](img/c1be6461eafac84e9f3cb450f666a5f2_328.png)

说你现在到底是用CPU在跑还是用GPU在跑，如果而如果同学你们有自己的计算资源的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_330.png)

可能你有好几颗显示卡，那你这时候就必须要去选择说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_332.png)

你是要用哪一个显示卡去做用才这样子，OK那刚刚就有提到说GPU的优点。

![](img/c1be6461eafac84e9f3cb450f666a5f2_334.png)

就是它的它会跑的比较快，那为什么它会跑的比较快的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_336.png)

基本上概念上来讲就是GPU，它是很多科运算能力比较没有那么强。

![](img/c1be6461eafac84e9f3cb450f666a5f2_338.png)

但是很多科的核心在做运算，所以在做一些矩阵运算的时候。

![](img/c1be6461eafac84e9f3cb450f666a5f2_340.png)

他就可以同时处理很多的数值，那如果同学对这个有兴趣，可以参考底下这个链接。

![](img/c1be6461eafac84e9f3cb450f666a5f2_342.png)

分子，好那刚刚有一开始提到PYTORCH的两个好处。

![](img/c1be6461eafac84e9f3cb450f666a5f2_344.png)

第一个好处是它可以用GPU去做加速，第二个好处是它在去计算梯度的时候。

![](img/c1be6461eafac84e9f3cb450f666a5f2_346.png)

非常的方便，那到底有多方便呢，就展示给同学看。

![](img/c1be6461eafac84e9f3cb450f666a5f2_348.png)

那请同学们先看右下角这一块，假设我有一个2×2的矩阵。

![](img/c1be6461eafac84e9f3cb450f666a5f2_350.png)

我它是一零负一，我想要去对它计算某一个东西，然后假设我想要计算的东西是对它取平方和。

![](img/c1be6461eafac84e9f3cb450f666a5f2_352.png)

所以我计算Z也就是X里面的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_354.png)

每一项的平方的相加，那我得到一个值以后，我想要去去计算它的梯度的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_356.png)

我在我我只是去对每一项去算片尾分，然后得到二啊。

![](img/c1be6461eafac84e9f3cb450f666a5f2_358.png)

每它的因为是我们是取平方的，所以对每一项片尾分就是它的两倍。

![](img/c1be6461eafac84e9f3cb450f666a5f2_360.png)

这样子，那我们把它的每一项的平方呢再化成一个矩阵，就是我所谓的梯度的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_362.png)

就会得到一个二零负220矩阵这样子，那在porch里面怎么做呢，基本上如左上角所示。

![](img/c1be6461eafac84e9f3cb450f666a5f2_364.png)

你只要先定义好你的tensor，也就是你的矩阵，然后特别强调说你现在我想要计算我的梯度。

![](img/c1be6461eafac84e9f3cb450f666a5f2_366.png)

所以把require gradient给打开，然后去计算我们想要算的东西。

![](img/c1be6461eafac84e9f3cb450f666a5f2_368.png)

我这边是用平方的举例，所以就取平方的求和。

![](img/c1be6461eafac84e9f3cb450f666a5f2_370.png)

那第三部分你想要算它的片尾分，就是他的梯度的每一项的时候就呼叫点backward。

![](img/c1be6461eafac84e9f3cb450f666a5f2_372.png)

它就会自动计算出每呃Z之后的东西的梯度。

![](img/c1be6461eafac84e9f3cb450f666a5f2_374.png)

那再去检查说原本的矩阵的梯度的话，就会得到这个二零负二二的矩阵这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_376.png)

那同学们如果还没有看过弘毅老师。

![](img/c1be6461eafac84e9f3cb450f666a5f2_378.png)

上课影片的话，可能不是很确定说为什么要去计算梯度这样子，那底下附上弘毅老师呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_380.png)

去年的第二个上课可有解，也解释说，我们到底是如何用梯度的计算来去优化。

![](img/c1be6461eafac84e9f3cb450f666a5f2_382.png)

我们的神经网络，这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_384.png)

OK那底上底上是大概前半部分就是在讲。

![](img/c1be6461eafac84e9f3cb450f666a5f2_386.png)

说到底资料如何处理，然后如何读，把资料给读进来，然后让开拓视做使用，接下来就是讲到是真的在做training的时候。



![](img/c1be6461eafac84e9f3cb450f666a5f2_388.png)

要怎么用hyper去做这样子，首先那我们要怎么用PYTORCH去啊。

![](img/c1be6461eafac84e9f3cb450f666a5f2_390.png)

接下来该说接下来我讲的是第二个部分。

![](img/c1be6461eafac84e9f3cb450f666a5f2_392.png)

要怎么用PYTORCH去定义神经网络呢，这边如果也是用弘毅老师去年的影片。

![](img/c1be6461eafac84e9f3cb450f666a5f2_394.png)

来做一个简单的举例。

![](img/c1be6461eafac84e9f3cb450f666a5f2_396.png)

譬如说我先用啊，应该说我先用PYTORCH，是最简单的一个一个linear layer来举例。

![](img/c1be6461eafac84e9f3cb450f666a5f2_398.png)

同学们可能会一，可能我比较熟悉的名字是fully connected there。

![](img/c1be6461eafac84e9f3cb450f666a5f2_400.png)

那如果不知道没关系，等下会再解释展示他的时，他能在程序上，他基本上就是你只要跟他说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_402.png)

他的输入程度是多少，它的输出程度是多少，然后你给他输入一个最后一个维度的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_404.png)

长度是32的tensor，它经过这个layer的layer以后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_406.png)

他算出来就会是一个最后的维度是六四的弹子，那它只是变成输入天子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_408.png)

它的它它是几个维度，并不限制，你只要它的最后一个维度乘以32。

![](img/c1be6461eafac84e9f3cb450f666a5f2_410.png)

他就可以去做运算，那这边的linear layer到底是什么呢，如果有看过弘毅老师的影片的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_412.png)

就会老师呃可能就有印象说，弘毅老师去年有提到。

![](img/c1be6461eafac84e9f3cb450f666a5f2_414.png)

是说我们再去对建立神经网络的时候，会去对它呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_416.png)

会去右脸，像左边这个样子，会去每每一项去做它的线性组合，然后去再加上一个值。

![](img/c1be6461eafac84e9f3cb450f666a5f2_418.png)

得到一个新的新的一排的值，那就相当于是对于我们的输入的向量。

![](img/c1be6461eafac84e9f3cb450f666a5f2_420.png)

去做一个矩阵乘法，再加上一个向量，那底下柱上对应的连接。

![](img/c1be6461eafac84e9f3cb450f666a5f2_422.png)

那用刚刚的30 264来举例的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_424.png)

我们所做的事情基本上就是向量额，这就是矩阵的乘法。

![](img/c1be6461eafac84e9f3cb450f666a5f2_426.png)

还有向量的加法这样子，所以我们刚刚的layer layer，其实所对应到的事情。

![](img/c1be6461eafac84e9f3cb450f666a5f2_428.png)

就是一个32×64的矩呃，64×32的矩阵乘上我们的输入的向量。

![](img/c1be6461eafac84e9f3cb450f666a5f2_430.png)

因为我们强调说，我们的输入向量的有一个维度一定是三。

![](img/c1be6461eafac84e9f3cb450f666a5f2_432.png)

长度是32，所以我们乘完以后，会得到一个长度是六四的向量。

![](img/c1be6461eafac84e9f3cb450f666a5f2_434.png)

再加上一个另一个长度是64的向量，以后便会得到Y这个向量。

![](img/c1be6461eafac84e9f3cb450f666a5f2_436.png)

那我们的LINUVUE所指的就是蓝色这两块，然后我们的输入就是X输出就是Y这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_438.png)

![](img/c1be6461eafac84e9f3cb450f666a5f2_439.png)

那如果呃在Python是怎么撰写这样子的城市码话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_441.png)

就是直接呼叫说我现在要定义一个linear，然后输入是在这输出是64的的linear layer。

![](img/c1be6461eafac84e9f3cb450f666a5f2_443.png)

这然后如果同学们觉得这样子，可能看不出它到底背后是什么东西。

![](img/c1be6461eafac84e9f3cb450f666a5f2_445.png)

你可以去看一下嗯，譬如说以linear layer举例的话，你可以去看书。

![](img/c1be6461eafac84e9f3cb450f666a5f2_447.png)

他的weight就是W这块，你可以发现说它的确是一个64×32的，一个一个tensor。

![](img/c1be6461eafac84e9f3cb450f666a5f2_449.png)

并且你去看他的BIOS，你会发现说他是一个长度是六四向量这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_451.png)

所以你就可以确认出，你LINULA就的确是先去做一个矩阵乘法，再去做一个向量的加法得到输出。

![](img/c1be6461eafac84e9f3cb450f666a5f2_453.png)

这样子，除了除了VENULAYER以外。

![](img/c1be6461eafac84e9f3cb450f666a5f2_455.png)

可能啊在做神经网络的训练的时候。

![](img/c1be6461eafac84e9f3cb450f666a5f2_457.png)

还会使用到很多非线性的函数，譬如说老师去年上课里面有提过的SIGMOY。

![](img/c1be6461eafac84e9f3cb450f666a5f2_459.png)

有提过的个例，那这些在PYTORCH里面都已经帮你写好了，只要直接使用就可以。

![](img/c1be6461eafac84e9f3cb450f666a5f2_461.png)

然后至于为什么要使用非线性函数的话，可以参考弘毅老师去年的上课影片。

![](img/c1be6461eafac84e9f3cb450f666a5f2_463.png)

那OK那讲到要到底要怎么样。

![](img/c1be6461eafac84e9f3cb450f666a5f2_465.png)

用我们刚刚所提到的layer，还有非线性函数来组成你的神经网络。

![](img/c1be6461eafac84e9f3cb450f666a5f2_467.png)

类似于刚刚的data set，我们要先首先我们要先去four arride。

![](img/c1be6461eafac84e9f3cb450f666a5f2_469.png)

原本torch点刚才写好的点model这个class，然后我们要去定义我们自己的模型。

![](img/c1be6461eafac84e9f3cb450f666a5f2_471.png)

那我们一样要去override，我们的initialization的function，然后去写说我们的模型是由哪哪几层所组成。



![](img/c1be6461eafac84e9f3cb450f666a5f2_473.png)

譬如说我们这边我这边定义一个很简单的模型，它的第一层是一个linear layer。

![](img/c1be6461eafac84e9f3cb450f666a5f2_475.png)

第二层是一个SIGMIN，一个非线性函数，第三层又是一个32~1的linear layer这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_477.png)

所以我的模型所做的事情是，假设我的输入向量输入的tensor。

![](img/c1be6461eafac84e9f3cb450f666a5f2_479.png)

它的最后一维的长度是十，它最后它经过我的运算以后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_481.png)

就会得到一个最后一位的重物是一的向量，这样子，OK那刚刚所说的是定义呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_483.png)

定义我的自己的模型的ANCIALIZATION的方式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_485.png)

那我定义完我的模型有哪些层以后，我要去计算我的模型。

![](img/c1be6461eafac84e9f3cb450f666a5f2_487.png)

要啊我要去跟我要去定义是我的模型。

![](img/c1be6461eafac84e9f3cb450f666a5f2_489.png)

它到底要怎么样去做运算，所以我必须要去overrun一个点forward呃，一个forward的方式去说。



![](img/c1be6461eafac84e9f3cb450f666a5f2_491.png)

我的模型到底得到一个输入资料以后，要去怎么样去做运算。

![](img/c1be6461eafac84e9f3cb450f666a5f2_493.png)

所以啊我上面这边我的做法是，我先用一个NN点CCONTRO的东西，把这三层给包起来。

![](img/c1be6461eafac84e9f3cb450f666a5f2_495.png)

变成一个东西，然后说，那我把这三层给套用在我们的输出输入X上面。

![](img/c1be6461eafac84e9f3cb450f666a5f2_497.png)

然后就会得到我们的输出这样子，所以要定义一个自己的模型。

![](img/c1be6461eafac84e9f3cb450f666a5f2_499.png)

大约是这样子的步骤，最后额刚刚有提到。

![](img/c1be6461eafac84e9f3cb450f666a5f2_501.png)

说我们这边是用N点SEQUENTI，把那三层给包成同一个东西，然后再直接坐在输入输入的tensor上面。



![](img/c1be6461eafac84e9f3cb450f666a5f2_503.png)

当然也不一定要这样子做，你也可以定义说我的第一层就是一个linear。

![](img/c1be6461eafac84e9f3cb450f666a5f2_505.png)

第二层就是一个SIGMOID，第三层又是一个linear，然后要去把这三层给逐步的对应。

![](img/c1be6461eafac84e9f3cb450f666a5f2_507.png)

在我们的输入的tensor上面，这样的做法跟左边是完全等价的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_509.png)

这，所以如果之后同学们在看助教的范例程式的话，不用不用担心说左边有随及宽手。

![](img/c1be6461eafac84e9f3cb450f666a5f2_511.png)

跟右边有什么差别，这两个做法是等价。

![](img/c1be6461eafac84e9f3cb450f666a5f2_513.png)

OK第三个部分呃快要讲完了。

![](img/c1be6461eafac84e9f3cb450f666a5f2_515.png)

那第三个部分是我们的loss function，要怎么样去定义呢。

![](img/c1be6461eafac84e9f3cb450f666a5f2_517.png)

如果MOSMOTION在这边的事情，就是我们的神经网络想要去最小化的一个东西。

![](img/c1be6461eafac84e9f3cb450f666a5f2_519.png)

那可能是呃可能是方均根误差。

![](img/c1be6461eafac84e9f3cb450f666a5f2_521.png)

可能是各式各样的误差，在PYTORCH里面已经touch点L已经帮你定义好。

![](img/c1be6461eafac84e9f3cb450f666a5f2_523.png)

除掉常用的the lost f式，所以譬如说我们作业一，我们使用的是misquare error。

![](img/c1be6461eafac84e9f3cb450f666a5f2_525.png)

就是跟正确答案的的差的距离这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_527.png)

然后如果做一份之后会做一些分类的任务，可能使用的是一个不同的loss通式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_529.png)

这样子，那在hyper里面，你只要先定义好你想要用什么方式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_531.png)

并且把它套用在模型的输出，还有预期的结果上面，就会得到一个loss，这样那时候我们想要做的事情。

![](img/c1be6461eafac84e9f3cb450f666a5f2_533.png)

就是要把袜子给越小越好，这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_535.png)

OK那讲完讲完读资料。

![](img/c1be6461eafac84e9f3cb450f666a5f2_537.png)

讲完定义神经网络，讲完我们定义loss function，最后要讲呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_539.png)

最后在training的part里面，要讲的就是选择你的optimization的演算法。

![](img/c1be6461eafac84e9f3cb450f666a5f2_541.png)

这样子，那同样如同last function，PYTORCH已经帮我们定义好一些常见的优化啊。

![](img/c1be6461eafac84e9f3cb450f666a5f2_543.png)

优化模型的演算法，那嗯同学们可能如果不是还很了解说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_545.png)

为什么不需要不同的验算法的话，可以参考老师去年的上课影片。

![](img/c1be6461eafac84e9f3cb450f666a5f2_547.png)

那这边的演算法指的东，指的意思是如何用不同的梯度。

![](img/c1be6461eafac84e9f3cb450f666a5f2_549.png)

基于梯度下降的演算法去计算呃，去调整你的模型的参数怎样。

![](img/c1be6461eafac84e9f3cb450f666a5f2_551.png)

那么请参考老师去年的上课影片，譬如说假设我要做最基本的梯度下降的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_553.png)

我只要去呼叫SD呃，SGD这个方式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_555.png)

并且给它我们的模型的参数，定义一个学习的速度。

![](img/c1be6461eafac84e9f3cb450f666a5f2_557.png)

然后给他一些这个演算法可能需要的其他数字，那这样子就是我们的的演算法。

![](img/c1be6461eafac84e9f3cb450f666a5f2_559.png)

这样子，那我们定义好这个演算法以后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_561.png)

我们在实际训练的时候会有三个步骤，第一个步骤是要把我们的演算法。

![](img/c1be6461eafac84e9f3cb450f666a5f2_563.png)

前一个步骤可能所计算的梯度给归零，第二个步骤是我们要去呼叫点backward。

![](img/c1be6461eafac84e9f3cb450f666a5f2_565.png)

如同我刚刚所说，我们要去把我们算出来的结果，回推去算每一层的梯度。

![](img/c1be6461eafac84e9f3cb450f666a5f2_567.png)

第三个步骤是我们要把演算法去往区，我们要呼叫点step。

![](img/c1be6461eafac84e9f3cb450f666a5f2_569.png)

把演算法去往，根据自己上一个步骤所算出来的梯度，去调整我们模型的参数。

![](img/c1be6461eafac84e9f3cb450f666a5f2_571.png)

这样子，然后如果呃除同学们之后在写作业，可能会想说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_573.png)

有没有除了SED以外，其他的颜色的的optimization也算法。

![](img/c1be6461eafac84e9f3cb450f666a5f2_575.png)

那可以看PYORCH的官方文件，附在这边。

![](img/c1be6461eafac84e9f3cb450f666a5f2_577.png)

OK最后一个part，我们如何把刚刚讲过的全部的东西给加起来。

![](img/c1be6461eafac84e9f3cb450f666a5f2_579.png)

把资料给读进来了，神经网络也定义好了，lost function也要最小化的东西也知道要。

![](img/c1be6461eafac84e9f3cb450f666a5f2_581.png)

然后如何要去调整我们模型和参数的算法。

![](img/c1be6461eafac84e9f3cb450f666a5f2_583.png)

我们也学好了，又是怎么样去做训练，怎么样去做validation，怎么样去做测试呢，那整个步骤做起来的会是像这个样子。



![](img/c1be6461eafac84e9f3cb450f666a5f2_585.png)

首先如把刚要该定义的东西都定义好。

![](img/c1be6461eafac84e9f3cb450f666a5f2_587.png)

我们先做好我们的DANCON，把DANCON用一个dn word包起来。

![](img/c1be6461eafac84e9f3cb450f666a5f2_589.png)

然后去定义好我们的模型，把它移动到CPU或者GPU，看你用哪一个。

![](img/c1be6461eafac84e9f3cb450f666a5f2_591.png)

然后定义好我们的loss function，定义好我们的演算法，然后就可以准备开始读训练。

![](img/c1be6461eafac84e9f3cb450f666a5f2_593.png)

首先训练的步骤是说，我们第一个回旋是说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_595.png)

我们要把整个资料集给跑过几次，那跑知道定义完第一回旋以后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_597.png)

我们里面要做的事情，首先是我们要先要把模型给调到训练模式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_599.png)

为什么要调到训练模式，等下最后会再做说明，然后接下来就是把data logo里面的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_601.png)

每个batch的资料去去做处理，那这边X是说我们的预期呃。

![](img/c1be6461eafac84e9f3cb450f666a5f2_603.png)

模型的输入，然后Y是说我们输入模型以后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_605.png)

预期会得到的结果，这样子，OK那如同刚刚在optimization演算法所说的所说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_607.png)

我们在一开始要先把我们的演算法的上一个。

![](img/c1be6461eafac84e9f3cb450f666a5f2_609.png)

上一个迭代可算过的梯度给归零，然后要把我们的资料给移动到我们的正确的的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_611.png)

CPU或者GPU上面，第三个步骤。

![](img/c1be6461eafac84e9f3cb450f666a5f2_613.png)

把我们的输入资料给放到模型里面，得到我们的模型产生的结果，得到模型产生的结果以后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_615.png)

跟真正呃跟预期的结果去算我们的loss。

![](img/c1be6461eafac84e9f3cb450f666a5f2_617.png)

然后得到loss以后会去算它的梯度，回去算梯度完以后，用我们的optimization的一个算法。

![](img/c1be6461eafac84e9f3cb450f666a5f2_619.png)

去去调整我们的模型的参数，并且把这整个流程给反复的做。

![](img/c1be6461eafac84e9f3cb450f666a5f2_621.png)

直到跑过整个整个资料集，跑过一跑。

![](img/c1be6461eafac84e9f3cb450f666a5f2_623.png)

跑过我们定义的次数，这样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_625.png)

那训练的部分是这样子，那测试的部分跟训练的部分很像，唯一的差额，唯二的差别就是说，我们必须要先把模型调到测试模式，然后要在计算我们的模型的结果。



![](img/c1be6461eafac84e9f3cb450f666a5f2_627.png)

跟计算loss的时候，要把要特别跟T跟PYTORCH讲说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_629.png)

我们要把梯度的计算给关掉，除此之外过程是差不多的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_631.png)

我们把资料给移动到对应的东西呃，对应的CPU或者GPU上面把。

![](img/c1be6461eafac84e9f3cb450f666a5f2_633.png)

然后去计算模型的数，得到一个X的失误以后会得到的预期结果。

![](img/c1be6461eafac84e9f3cb450f666a5f2_635.png)

然后去计算loss，然后去去得去算一下我们的模型。

![](img/c1be6461eafac84e9f3cb450f666a5f2_637.png)

目前算出来的的the sloth平均起来大概是多少。

![](img/c1be6461eafac84e9f3cb450f666a5f2_639.png)

这样子，那为什么要做evaluation跟torch grade这两部分。

![](img/c1be6461eafac84e9f3cb450f666a5f2_641.png)

等一下会再做解释，那测试那实际在做测试的时候。

![](img/c1be6461eafac84e9f3cb450f666a5f2_643.png)

我们也是跟刚刚所做的事情差不多。

![](img/c1be6461eafac84e9f3cb450f666a5f2_645.png)

但我们在做测试的时候，我们不知道我们模型得到这个输入资料，它到底它预期的输出会是什么样子。

![](img/c1be6461eafac84e9f3cb450f666a5f2_647.png)

那所以我们的testing dataset，它里面就只有X这个资料。

![](img/c1be6461eafac84e9f3cb450f666a5f2_649.png)

我们得到X这个资料以后，我们去特特别把梯度的计算给关掉以后。

![](img/c1be6461eafac84e9f3cb450f666a5f2_651.png)

去计算模型，得到X这个输入以后会得到输出，并且我们把所有的的输出给去去统计下来。

![](img/c1be6461eafac84e9f3cb450f666a5f2_653.png)

然后再去看要写稿的答案，或者做什么做处理。

![](img/c1be6461eafac84e9f3cb450f666a5f2_655.png)

这样子，OK那刚刚说到为什么要去做model的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_657.png)

去年的测试模式的调整，还有说为什么要把梯度关掉，首先就是虽然目前还没有交到。

![](img/c1be6461eafac84e9f3cb450f666a5f2_659.png)

但是之后有些模型的层数像是drop up。

![](img/c1be6461eafac84e9f3cb450f666a5f2_661.png)

像是bash bonalization，他们的他们在训练跟测试的时候，他们所做的事情是不一样的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_663.png)

因此我们要特别去强调说，我们现在做训练还是做测试。

![](img/c1be6461eafac84e9f3cb450f666a5f2_665.png)

第二个部分是，为什么我们要在去做validation跟testing的时候。

![](img/c1be6461eafac84e9f3cb450f666a5f2_667.png)

把梯度的计算给关掉，首先最大的好处就是当我们在做测试的时候，我们其实是梯度是拿来调整我们的模型的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_669.png)

但是我们在做测试的时候，我们不需要做这件事情，所以你把屁股计算关掉。

![](img/c1be6461eafac84e9f3cb450f666a5f2_671.png)

它会跑的比较快一点点，第二个部分是也是第二个部分是我们计算梯度。

![](img/c1be6461eafac84e9f3cb450f666a5f2_673.png)

它很有可能就会被拿去优化我们的演算法。

![](img/c1be6461eafac84e9f3cb450f666a5f2_675.png)

如果你程序写的不好的话，你可能就会不小心拿我们的测试资料来去，训练的模型。

![](img/c1be6461eafac84e9f3cb450f666a5f2_677.png)

那这时候把梯度的基层给关掉，可以确可以确保说。

![](img/c1be6461eafac84e9f3cb450f666a5f2_679.png)

一定不会有拿你的FADDITION的资料或者test资料，来修正模型参数的可能性好了。

![](img/c1be6461eafac84e9f3cb450f666a5f2_681.png)

![](img/c1be6461eafac84e9f3cb450f666a5f2_682.png)

那刚刚上面那几页是如何用PYTORCH去做训练，去做validation去做测试。

![](img/c1be6461eafac84e9f3cb450f666a5f2_684.png)

那你好不容易你去把你的模型给训练好了，你要把它存起来的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_686.png)

就是呼叫TCHZ这个模型啊，这个function，然后去把模型给存起来。

![](img/c1be6461eafac84e9f3cb450f666a5f2_688.png)

然后要把你存好的模型读起读回来拿来用，那就是呼叫点漏的这个方式。

![](img/c1be6461eafac84e9f3cb450f666a5f2_690.png)

那这些这这存档跟读档部分，我们助教都已经在城市马里面帮你们写好了。

![](img/c1be6461eafac84e9f3cb450f666a5f2_692.png)

所以到时候看看我们的城市马，就大概知道怎么做。

![](img/c1be6461eafac84e9f3cb450f666a5f2_694.png)

OK那以上就以上就是PYTORCH的说明，那PYTORCH现在就是一个深入学习的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_696.png)

目前最热门的套件，它现在被拿来做语音的处理。

![](img/c1be6461eafac84e9f3cb450f666a5f2_698.png)

他现在被拿来，他现在被拿来在各式各样的领域上面，做机器学习的运算。

![](img/c1be6461eafac84e9f3cb450f666a5f2_700.png)

譬如说语音处理，譬如说自然语言处理，譬如说电脑视觉的部分。

![](img/c1be6461eafac84e9f3cb450f666a5f2_702.png)

都有用PYTORCH去做一些运算这样子，而如果同学们对于机器学习有兴趣的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_704.png)

呃，对于机器学习的研究，或是机器学习的应用有兴趣的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_706.png)

现在很多在GITHUB上面的repository，他们都是使用PYTORCH来去做编写的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_708.png)

譬如说很有呃，很有名的自然语言处理的BT模型的，GPT模型的一个the repository叫hiking face。



![](img/c1be6461eafac84e9f3cb450f666a5f2_710.png)

还有用PYTORCH去做撰写，譬如说FACEBOOK他去做一些。

![](img/c1be6461eafac84e9f3cb450f666a5f2_712.png)

他有个很有名的repository叫PERCY等等等等。

![](img/c1be6461eafac84e9f3cb450f666a5f2_714.png)

而除此之外，在大部分学界的，目前的的论文都是用PYORCH去作撰写的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_716.png)

所以同学们在这堂课的学习，Pytorch，如果对机器学习有兴趣的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_718.png)

以后非常的有用，这样子，OK那这个今天的tutorial大概就到这边了。

![](img/c1be6461eafac84e9f3cb450f666a5f2_720.png)

那我参考了很多，一部分是从去年的tutorial来的。

![](img/c1be6461eafac84e9f3cb450f666a5f2_722.png)

如果觉得有哪些地方不是很清楚的话，如果除了参考我的讲解。

![](img/c1be6461eafac84e9f3cb450f666a5f2_724.png)

也可以参考去年的讲解，而如果觉得听完还是没有理解的话。

![](img/c1be6461eafac84e9f3cb450f666a5f2_726.png)

最有用的资源就是PYTORCH，自己给出的官方文件可以去阅读，并且得到答案。

![](img/c1be6461eafac84e9f3cb450f666a5f2_728.png)

这样子，OK那我今天大概讲到这边。

![](img/c1be6461eafac84e9f3cb450f666a5f2_730.png)