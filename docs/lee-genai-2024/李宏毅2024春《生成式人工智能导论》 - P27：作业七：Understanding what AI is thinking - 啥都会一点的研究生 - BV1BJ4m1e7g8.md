# 李宏毅2024春《生成式人工智能导论》 - P27：作业七：Understanding what AI is thinking - 啥都会一点的研究生 - BV1BJ4m1e7g8

大家好，我是这次做一期的主角，接下来要讲解这一期让大家做什么事情。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_1.png)

只是今天online，我先简单介绍一下，为什么了解JAATI在想什么，这件事情是重要的，然后讲一下只作用到两个任务。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_3.png)

以及一些角教事宜，首先是为什么要了解卷ATI在想什么呢，就老师上课所讲的，当一个模型预测出正确的答案时候，不一定代表他是聪明的，他可能只是刚好歪打正着猜到了正确的答案，那除此之外，在一些高风险的产业。

像是医疗或是法律上面，我们可能会需要模型，不只是给出一个结果，还能够进一步的给出一些解释，来证它生成出来的结果，那根据模型给出来的这些解释，我还可以进一步的去让模型更加进步。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_5.png)

那什么是模型的解释呢，在一个传统的分类任务当中，我们的model会是一张图片，然后他还生成出的结果，那在这在这个例子当中，它会生成珠子，这张图片会是一只猫。

那model explanation就是进一步就是说，为什么模型会预测出这张图片会是一只猫呢，那下面的例子也是一样，确认gt不只是给出这个review positive，他也会进一步的给出说。

他预测这个reverse positive的理由是什么。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_7.png)

那这个就是model explanation。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_9.png)

那这次作业的第一个任务要带同学去了解，当我们的模型在生成出结果的时候，它的input token所占的重要性是多少，那我会使用一个叫feature，attribution的方法来做分析。

其中我们会带到两个经典的方法，分别是gradient base的方法以及attention的方法，那这部分会需要同学去呃，跑color上面的课，然后去完成CORE上面的一些问题。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_11.png)

那首先是gradient base的方法，当我们的input给出一个sentence，叫做the first president of america，Yes，我们的模型会给出一个output。

可能会是叫GEORGE，那我们想要了解，当这个模型再生成就这个字，它的input token所占的重要性多少的时候，我们就会在它生成出来的这个logic里面，去挑出GEORGE对应到的logic是谁。

那跳出这个log以后，我们就会变回去去计算，我们每一个input token所对应的重要性是多少。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_13.png)

那attention这个方法会是常见，在transformer base的模型上面，因为attention位所代表的意义，就是当我在生成output的时候。

我的input token所对应到的权重会是多少。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_15.png)

那在这次作业中，我们会用一个叫做INCEC的套件，来帮助我们做分析啊，INSIC套件它有资源非常多的feature，attribution的方法，那其中就包含ingredient和attention。

是我们这次作业会导。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_17.png)

啊inside这个套件非常简单，需要的东西只有三个，分别是我们想要使用的模型，以及我们想要的分析方法，还有我们的input是什么，然后根据这三个input，我们就会生成出一张sdc map。

然后这个sdc map就代表我生成出来的input，生出来的output，它对应到的input token的中心是多少。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_19.png)

那首先我们先坐在一个叫我们先会先坐在machine，translation text上面，那在mstation test上面，像这个例子当中。

我们的input the first president of america，Is a george washington，那它对应到这张CDCHMAP的左边。

那这个translation model它会把它翻译成中文，那中文对应到就会是，而output对应到就会是这个selency hemp的上半部，那这边的score代表是当我在生成出output的时候。

它的input token的重要信息多少，像是0。308这个数字，就是当我在生成美国这个字的时候。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_21.png)

AMERICA所占的重要性是多少，那我们还会住在sentence commission的任务上面，在sentence completion上面，他会把我前前缀的所有字都搭进去，我的input。

所以当我在生成first这个字的时候，the joy是我的input，当我在生成拍摄的这个字的时候，the first都会被当我队员去input。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_23.png)

所以当我生成到WASHINGTON这个字的时候，GEORGE会被我当成去应聘，所以即使我们刚开始的input，The first president of，America is。

但对于WASHINGTON这个字来说，是后来生成出来的，GEORGE也会是他的前缀，所以他也会被当会，它也会被当成input丢进去，然后计算出一个对应的score是多少。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_25.png)

那这个可能是大家在作业中会看到的题目，那首先是我们会问说，当我们在生成WASHINGTON这个字的时候，那我们就需要同学对应到output washington z z z列，当时ZZ列。

那我们再会说呃，AMERICA对应的重要性是多少，所以我们就会收到，只有这个是0。18这个数字。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_27.png)

那这边先带同学看一下这次作业的sample code。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_29.png)

这一周的sample code很简单。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_31.png)

就只有两个block，三个block可以，那这个block就是做machine translation test，然后分分别会对应到呃，我们刚刚提到的gradient base的方法。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_33.png)

以及attention的方法，那同学就会得到这样的两张图。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_35.png)

分别是gradient的图以及attention的图。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_37.png)

那同学就会去根据这样的图去做，去过上面做回答。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_39.png)

那在sentence completion也是一样，我们会得到对应的图。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_41.png)

那同学一样，就是根据这两张图去做一些回答。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_43.png)

![](img/16afcde5e4ffa99caa0f1d11840c8fee_44.png)

好在第二个任务是LN的explanation。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_46.png)

LA有个特性是，它可以用我们人类就可以理解的natural language来表示，所以它相较于我们前面所计算出来的一些，importance score来说，它来得更直觉，现在这个例子当中去了。

g pd可以很直接跟我们讲说，它生成出这个review pad的理由是什么，然后他还说，因为fantastic跟terrific这两个字是positive的。

那像这样的natural language的方式，是非常容易让人们去理解的，所以我们就会想到说，那我们可不可以用LN的explanation，来帮助我们做模型，来来帮助我们判断模型的的解释。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_48.png)

哪只是作业任务，我会用两种方法来来做LN的explanation，第一个就是像刚上一个例子提到的，我们直接让模型去给出解释，那第二个是我们想要去模模拟，说我们在task问当中做的feature。

Precient method，去分析每个token的重要性，我们能不能同样用LN来做这件事情，那因为在这个任务当中，我们会需要比较好的model，所以一般的市面上open source model。

可没有办法做到这么好的事，所以我们会用到，我们会用ChatGPT来做，所以不需要用到COLLAB，那样同学会去扩上面回答对应到的题，对应到的问题。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_50.png)

那首先第一个是我们直接让模型去突出，它的解释是什么，所以我们就会给像这样的一个pro，然后很直接的就是除了叫他给出他的预测以外，我们会希望让模型去解释说，为什么你会预测出这样的答案。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_52.png)

那第二个例子是参考呃，最近的这篇论文，我们想要去模拟，看看能不能用LN来完成future tribution method，去对我们input token的importance做分析。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_54.png)

那一样我们就是会有对应到pro，那同学一样就是把这个pro贴到QG上面，然后去观察一下，看是不是能够做到同样的事情。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_56.png)

那这边就先示范一次给大家看。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_58.png)

那我们就直接像这样贴进来。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_60.png)

那模型可能就会去GBT，可能就会突出像这样的答案，像是呃它每个token都对应到一个score，以及最后它所分类出来是negative或是positive，那我们就是希望同学去分析一下。

他预测出来的答案是不是合理的，然后以及呃，因为true g b t会有一些随机性在，所以他不一定每次都可以生成出像这样的结果，所以如果它生成出来不是像这样的former的话。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_62.png)

同学们需要多试几次。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_64.png)

那再讲一下这次作业的角角示意，那这次作业的题目都会在扩上面，所以同学就是去cool换成quiz，然后要请同学注意，是我们只会看最后一次的submission，所以注意不要重复的角角。

那这次作业的deadline是一样，是在两周后的上课前一天的礼拜四，晚上11。59分，那再过两个礼拜以后，我们就会release他的。



![](img/16afcde5e4ffa99caa0f1d11840c8fee_66.png)

我们RESE分数，那我们一样鼓励同学在作业讨论区上做问问答，那我们也会优先回答呃，扩上面的题目，那如果有问题，如果有私下的问题的话，可以进行到这个信箱来，TL的话一样，就是上课结束后的04：30到5。

20，在上课地点好。

![](img/16afcde5e4ffa99caa0f1d11840c8fee_68.png)