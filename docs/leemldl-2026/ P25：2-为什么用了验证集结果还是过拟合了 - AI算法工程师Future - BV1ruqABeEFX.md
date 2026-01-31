# 【官授搬运】2026年全新优化版李宏毅机器学习系统课程，这才是真正的初学者体系课程！—人工智能／深度学习／神经网络 - P25：2-为什么用了验证集结果还是过拟合了 - AI算法工程师Future - BV1ruqABeEFX

![](img/0d89b39e33d6ae466561d22d234aa9c2_0.png)

好各位同学大家好啊，那今天这段影片呢是要来回答。

![](img/0d89b39e33d6ae466561d22d234aa9c2_2.png)

同学们常问的一个问题，就是为什么我用了validation set。

![](img/0d89b39e33d6ae466561d22d234aa9c2_4.png)

结果还是OVERFATED呢。

![](img/0d89b39e33d6ae466561d22d234aa9c2_6.png)

那如果你还不知道validation的概念是什么的话，那你先看右下角这支影片。

![](img/0d89b39e33d6ae466561d22d234aa9c2_8.png)

那很多同学呢有了validation的概念以后。

![](img/0d89b39e33d6ae466561d22d234aa9c2_10.png)

往往会觉得说我只要有用validation set，那就一定无往不利，那没想到说用了validation set以后，把结果传到LEADERBOARD上。

在testing set上却还是OVERFITTING了。

![](img/0d89b39e33d6ae466561d22d234aa9c2_12.png)

那这到底是怎么回事呢，好那我们先很快来复习一下validation，用validation set是怎么回事，好那现在呢假设你有三个模型，那我们分别用h one h two h3来表示这三个模型。

那我们要选择使用某一个模型，那怎么选呢，那我们先在training data上面，我们用d train代表training data，我们先用training data呢。

来找出这三个模型所表示的这个function的，candidate set里面最好的那个方式，那分别是h one star，h two star跟H3star。

那你不会直接用你的training data来决定h one star，HDUSTAR跟H3star哪一个比较好，你实际上做的事情是什么呢，你实际上做的事情是你会在一个validation set上。

那我们现在用DVAL呢，来代表这个validation set，那你会在这个validation set上来评估h one star，h two star h3star的好坏。

也就是呢你会计算h one star，在validation set上的loss，h two star在validation set上的loss，H3star在validation set上的loss。

那接下来看哪一个function，它的validation set，他在validation set上得到的loss最低。



![](img/0d89b39e33d6ae466561d22d234aa9c2_14.png)

你就会选择那一个function来用在testing set上好，那我们知道说呢，那其实testing set，代表了我们在之前课程里面讲过的DIO，就是所有可能的data。

那我们不可能真的收集到说可能data，所以我们用catching set来代表所有可能的data。

![](img/0d89b39e33d6ae466561d22d234aa9c2_16.png)

来近似所有可能的data，你仔细想想看哦。

![](img/0d89b39e33d6ae466561d22d234aa9c2_18.png)

这整个用validation set来挑model的过程，其实也可以想成是一种training，怎么说呢，我们来看一下这个validation这件事啊，那我们可以呃写成这个样子。

就是我们呢有一个由h one star，h two star h3star所组成的集合，我们把这个集合呢叫做大HVAL，那在做validation的时候呢，我们就是在大HVAL里面找到某一个H。

这个H可以让validation set上的loss最低，好我们找一个H它是在HVAL里面，它可以在validation set上loss最低，然后我们就拿这个在validation set上。



![](img/0d89b39e33d6ae466561d22d234aa9c2_20.png)

load最低的这个方式拿来用在testing set上。

![](img/0d89b39e33d6ae466561d22d234aa9c2_22.png)

那这整个过程呢你想想看，你会发现说它其实也可以被看作是一种training。

![](img/0d89b39e33d6ae466561d22d234aa9c2_24.png)

用validation set来选择model。

![](img/0d89b39e33d6ae466561d22d234aa9c2_26.png)

其实等同于是我们有一个这个model叫做HBL。

![](img/0d89b39e33d6ae466561d22d234aa9c2_28.png)

这个model里面只有三个可能的方选。

![](img/0d89b39e33d6ae466561d22d234aa9c2_30.png)

H one star，H two star，H 3star，那我知道一般的model假设你的model是一个deep的network，那可以选择的function当然是成千上万，是个天文数字。

那我们现在有一个很特别的model。

![](img/0d89b39e33d6ae466561d22d234aa9c2_32.png)

它叫HBL这个HBAL里面只有三个可能的选择。

![](img/0d89b39e33d6ae466561d22d234aa9c2_34.png)

H one star，H two star，H 3star，接下来呢我们在DVAL上面做training。



![](img/0d89b39e33d6ae466561d22d234aa9c2_36.png)

但这个training不是一般的training啊。

![](img/0d89b39e33d6ae466561d22d234aa9c2_38.png)

不是用gradient descent train network那种training，所以我们这边呢加一个双引号。



![](img/0d89b39e33d6ae466561d22d234aa9c2_40.png)

但是这边我们一样是要找一个function。

![](img/0d89b39e33d6ae466561d22d234aa9c2_42.png)

他在全在data上面的，在这个validation set上的这个loss是最低的，我们知道我们一般在做training的时候，你就是要找一个function。



![](img/0d89b39e33d6ae466561d22d234aa9c2_44.png)

在某一组data上，它的loss最低。

![](img/0d89b39e33d6ae466561d22d234aa9c2_46.png)

这就是你的training嘛，那现在我们已经找，我们现在这个做validation的过程。

![](img/0d89b39e33d6ae466561d22d234aa9c2_48.png)

其实就是在validation set上。

![](img/0d89b39e33d6ae466561d22d234aa9c2_50.png)

从我们定好的model h v l，VHVAL里面找一个H。

![](img/0d89b39e33d6ae466561d22d234aa9c2_52.png)

它可以让loss最低，所以其实validation这件事情。

![](img/0d89b39e33d6ae466561d22d234aa9c2_54.png)

也可以看作是在validation set上做训练，只是我们现在的模型可以选择的方向非常的少。

![](img/0d89b39e33d6ae466561d22d234aa9c2_56.png)

在这个例子里面只有三个。

![](img/0d89b39e33d6ae466561d22d234aa9c2_58.png)

好，那我们再回头来看看这件事情跟会不会OVERFIT。

![](img/0d89b39e33d6ae466561d22d234aa9c2_60.png)

有什么关系呢，那你记不记得我们说什么时候，你的理想跟现实会有很大的差距，我们说如果你抽到一个不好的training data的时候，你的理想跟现实会有你没办法接受的差距，那抽到不好的data。

抽到不好的training data取决于哪些因素呢，一个取决于你的训练资料，你那另外一个问题是你的model的complexity有多大，你的模型有多复杂。

你的模型里面可以选择的function的candidate有多少，那如果你可以选择的function的candidate越多，你的模型越复杂，那抽到不好的training set。

会让你的这个呃现实跟理想的距离差距太大，的training set，你知道这种training set的几率呢就很大，好那同样的道理呀。

我们如果把validation set就想成是training set，什么时候你在validation set上看到的现实，会跟你的理想差距很大呢。

当你拿到的validation set是不好的DATASET的时候，那什么时候validation set不好呢，这取决于两个因素，第一个因素是validation set大小。

那第二个因素是validation set带对应的这个模型，HVAL啊，这个HVAL的复杂的程度，那这个HVAL啊通常不会太大，像我们刚才举的例子里面，HVAL只有三个选择。

相较于deep network，你的可能选择的function可以说是无穷无尽，HBAL只有三个function，当然HBL它总是很小吗，它会不会很小呢，那就取决于你怎么设计你的实验了。



![](img/0d89b39e33d6ae466561d22d234aa9c2_62.png)

如果你今天呐HVAL太大，你想你想要决定你的hyper parameter，比如说network架构的时候，你做的太猛，你说哎这个我的network架构呢要从一层到十层，那每一层要多少个neural呢。

我想是1~1000啊，那种十层的，那那有十层的network啊，那每一层呢有1~1000个选择，我决定跑这个1000个十次方，1000的十次方的模型，这样validation set来选你的模型。

那这个时候你的HVAL就有1000的十次方，那么大了，那你的HVAL很大，那你也很有可能会OVERFIT，你在validation set上看到的结果，也可能跟真正的data差距非常的大哦。

所以今天如果你用validation set，在决定你的模型的时候，你待选择的模型太多了，你仍然有可能会OVERFIT好，那这边呢就是想跟大家解释，为什么有了validation set以后。



![](img/0d89b39e33d6ae466561d22d234aa9c2_64.png)