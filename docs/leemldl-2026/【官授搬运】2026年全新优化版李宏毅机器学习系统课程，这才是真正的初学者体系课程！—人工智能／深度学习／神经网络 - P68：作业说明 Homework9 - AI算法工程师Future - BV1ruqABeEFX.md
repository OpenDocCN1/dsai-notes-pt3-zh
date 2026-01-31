# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P68：作业说明 Homework9 - AI算法工程师Future - BV1ruqABeEFX

诶好应该是可以的好。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_1.png)

那今天要讲的是homework9的部分。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_3.png)

那这次的主题会是explainable AI。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_5.png)

那这次作业的形式会跟以往都不太一样，就是这次会是全部都是选择题，然后也不会有leader board跟report。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_7.png)

所以希望大家可以好好把握住这次的作业。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_9.png)

那这次的作业总共会分成两个主题，第一个部分是CNN，就是homework3里面做过的部分，然后第二个主题就是bird。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_11.png)

那就是homework t7的部分，好那我们先讲就是第一个主题就是CNN。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_13.png)

那我们这边所使用的cn classify。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_15.png)

想做的事情就是去分类实物的照片，那其实这件事情也跟homemade3是一样的，那我们这次使用的模型就是基础的CNN模型，这样然后我们会提供TRA好的模型给各位使用。

那我们所使用的data set也跟HOMEX三一样，就是总共会有11种食物好。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_17.png)

那额在这个部分呢就是我们会提供collab code。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_19.png)

然后你们就可以去跑temple code，然后去完成这一总共是20题的选择题。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_21.png)

那在这个主题里面，总共会包含五种去解释这些模型，学到什么的的方法，那我们希望你们可以去了解这些方法，背后是怎么运作的，然后还要去实际跑跑看。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_23.png)

然后观察他们最后的结果。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_25.png)

那在这个主题当中，我们总共会观察十张图片，那也就是在PPT上面所列的这十张，那在跑扣的时候，跑扣的时候要千万要注意，就是你的所得到的十张图片。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_27.png)

就是PPT上面所show的这十张，不然会没有办法回答问题。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_29.png)

那另外还有一个要注意的是，在问题当中，这些这十张图片的标号是从零标到九，不是从一标到十。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_31.png)

所以在回答问题的时候，问题中可能会问你说，例如说呃图片四里面发生什么事情，那你就要知道图片是不是这张，而不是这张。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_33.png)

这样就是01234好，那我们同时也会鼓励你们去观察其他的图片。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_35.png)

来更了解这些方法好。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_37.png)

那我们一个一个来介绍，第一个方法是line，它是一个套件，只要你只要去pip install它就可以使用了。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_39.png)

那我们就会用里面的一些已经写好的function去执行。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_41.png)

那如果想要了解更多的话。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_43.png)

就可以看report，然后这边也附上了一篇介绍的文章。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_45.png)

那第二个方法是silency map，就是我们去针对这些input的图片，去计算他们的gradient，来观察说图片中有哪些部分，对于分辨这张图片是重要的，那同样我们这边也附上了一些介介绍的文章。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_47.png)

那第三种方法是smooth grade，那smooth grade就是利用加上noise的方式。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_49.png)

去让cnc map变得更robust，然后可以更能知道说哪些位置是重要的。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_51.png)

那这边也有附上他们的paper好。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_53.png)

第四种方法是filter visualization。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_55.png)

我们希望能够透过gradient，ascent mesa去了解说每一层layer，就是每一层的filter，实际上到底想要看到什么东西，那或者是这些图片在这些filter里面。

就是这些filter重视这些图片的哪一些位置，这样好。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_57.png)

那一样是附上了介绍的文章，那在最后一个就是integrated gradient。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_59.png)

这个这个题部分老师上课的影片应该也有提过。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_61.png)

就是呃，有时候你如果只是透过单一一张图片去观察。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_63.png)

它的gradient的话，其实可能并不会是你真正想要看到的东西。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_65.png)

所以它是会透过去，从baseline去产生出一系列的图片。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_67.png)

让这个GRAGRADIENT所产呃。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_69.png)

这个gradient可以是代表，更更能代表着这个classifiers所注重的位置，那同样也有附上他们paper的链接。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_71.png)

好这个就是第一个部分。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_73.png)

那第二部分是要针对BT去做解释。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_75.png)

那一样是我们这是在colab code里面，会提供所有你需要的simple code，然后呢总这边在这个部分总共会有十题选择题，然后总共会cover到三种方法，那我们也希望你可以去了解。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_77.png)

这些方法是怎么做的，跟去观察结果好，那第一个方法呢就是attention的visualization。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_79.png)

我们希望你们可以去透过这个网站嗯，COLLAB上面也会提供这个网站连接，但是如果要使用的话，直接去点这个网站，这个网站连接就好了，应该会稍微方便一点，那我们这个网站呢可以去呃输入一个句子。

然后去观察在BT里面，这在每一层attention它们之间的关系是什么，那呃同时我们也会这边有提供，就是这个网站跟这个网站会连到同一个地方，所以如果就这个网站有点问题的话，也可以点到这个网站。

那这边提供的是这个提供这个网站的paper，然后这个YOUTUBE影片则是就是介绍，如何使用这个网站，那在问题中所需要的所有方法，就是只要去点这个网站就可以知道怎么使用了。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_81.png)

那第二个部分是embedding visualization，那这个部分呢我们有使用，就是已经串好了birth，然后find two下1question，Ansering，Question。

answering上上面，然后呢去针对question选呢，answer还有context去把它喂ing bird，产生一些这些embedding之后，看它们之间的关系，那透过这几张图呢去观察。

说我们的bird在各个层面，可能各个层数可能会在做些什么事情。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_83.png)

然后就可以去回答问题好，那最后一个部分呢，就则是额去透过uclidean distance跟cos similarity，去观察不同句子的同一个字，像这边就是也是上课影片会提到的，就是苹果。

苹果总共会分成呃品吃的苹果或是品牌的苹果，那去观察说在不同的菌子里面的，这些同样是苹果，它们之间的embedding的关系是什么，那这个部分呢。

我们会希望你们是实做出euclidean distance，跟cosine similarity的算法，那只要只要做好，就是只要写好，那个我们都在上面留一个位置给大家，所以不用去动到任何其他地方。

就是避免我们的扣子会跑不起来。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_85.png)

好那我们最后来总结一下，就是总共会有30题选择题，那要注意的事情是在这些选择题中，有些是单选题，有些是多选题，所以就是呃上面会写出它是单选或多选，但是在多选部分的话。

你们就要回答出所有正确答案才可能会有分数，这样那呃CNN的部分是20题，然后一题是0。3分，然后BERT是十题，一题是0。4分，所以加起来就是总共是十分，所以就不需要有任何额外的。

就是交扣的或是交report或是leader board都不需要这样。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_87.png)

那还有一个要注意的事情。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_89.png)

就是所有的问题都放在grace DOS grace goe上面，所以就是呃大家直接去GRASCOOPE上面的网站，看到，就会看到就是homework9的题目们，那呃虽然说就是这次的作业。

不太需要去tr手模型或者突破什么baseline，但是你把那个collab code上面的sample code全部跑完，它其实还是需要时间的，所以请不要在就是deadline的前一刻。

才开始去猜这些选择题，这样那我们这次也不会接受任何的持交，那我们并在grace score上面，我们并没有去限制你们的答题的次数，或者是你们答题所需要的时间，那在grab soul上面会记录。

你们最后最后一次的submission，当成是算就是算分数的依据好，那额就是在GRASCOE上面，就是好像只要不要设定他的那个回答时间的话，你就必须要自己去试，就是当你有跟回答问题。

或是更改你的答案的时候，你就必须要去另外额外去点那个save answer，他才会真的储存到变更，所以就是在作答的时候要小心一点对，然后我们死线之后才会公布成绩，那死线的时间就是三个礼拜后。

也就是5月20号的半夜好。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_91.png)

那这边提供的就是我们COLAB，上面会有所有的sample code，然后这个就是question所在的地方，就是grace scope的网站，那呃在这在这边再强调一下，就是除非说除非那个问题有希望。

你可以去跟动那个code，不然就是所有扣理论上都已经可以跑起来，你只要按照那个顺序一个一个慢慢跑下来。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_93.png)

他理论上应该是可以跑好的，就不要乱动它。

![](img/c840d1dce9861f720017e3ecd1b3fd5d_95.png)

那如果有任何问题的话，就可以去那个nt CORE上面已经开好讨论区了，可以在那边发问，或者是来记助教信箱，那ta hour的话就是跟以前一样，但是因为我们现现在线上关系，所以多了一个。

就是星期五的下午四点半到5。20分，那那些这些的连接，都会在就是TL2之前再公布，这样好，那基本上就是这样子的好，大家有什么问题吗，诶大家有问题吗。



![](img/c840d1dce9861f720017e3ecd1b3fd5d_97.png)