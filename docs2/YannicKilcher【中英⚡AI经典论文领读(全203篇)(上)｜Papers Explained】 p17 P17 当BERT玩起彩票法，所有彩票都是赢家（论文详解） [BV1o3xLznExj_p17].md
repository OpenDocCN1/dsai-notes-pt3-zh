# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p17 P17 当BERT玩起彩票法，所有彩票都是赢家（论文详解） [BV1o3xLznExj_p17]

Hi there。 Today we're looking at when Bert plays the lottery， all tickets are winning by Sai Prasana。

 Anna Rogers and Anna Russki。So a high levelve overview of this paper is the following。

 the paper basically looks at BerRT in terms of the lottery ticket hypothesis and it says that if you fine tuned Bert on different downstream tasks。

 then the lottery ticket winners you're going to find are different between the task。

 and also the claim all tickets are winning refers to the fact that if you remove the winning tickets。

 then you can still train the rest to relatively good performance。

 therefore all tickets are winning not just the subnetwork。

So that was the high level overview for those if you who just want to be interested if you want to continue watching this video。

 if you do like videos like this， consider sharing， liking， subscribing， telling your mother， father。

 brother。

![](img/2c05689fee2344289f55e83775951a45_1.png)

![](img/2c05689fee2344289f55e83775951a45_2.png)

And friends about it。Alright， let's dive in。 So Bert。

 it is a language model basically if you don't know what bird is， I've done a video on Bt。

 but really quickly what you can do with Bert is you can take a sentence， something like hello there。

😊。

![](img/2c05689fee2344289f55e83775951a45_4.png)

![](img/2c05689fee2344289f55e83775951a45_5.png)

And you can put it through this multi layer neural network and what you'll get out is basically an embedding of that。



![](img/2c05689fee2344289f55e83775951a45_7.png)

Sentence， so a vector embedding of it will make it really easy。



![](img/2c05689fee2344289f55e83775951a45_9.png)

And what is usually done is this is pretrained on a task called masked language modeling。

 this is unsupervised training， and then you take this embedding and do fine tune basically you put on a classifier head。

Baically say， let's take sentiment classification， so you have two output classes and you want to say。

 is this sentence I put in positive or negative sentiment？



![](img/2c05689fee2344289f55e83775951a45_11.png)

So you would train this classifier by basically taking this part from the pretrained masked language modeling and then training the part here that does the sentiment classification。

 you would sort of add that on top and then fine tune the entire network。



![](img/2c05689fee2344289f55e83775951a45_13.png)

![](img/2c05689fee2344289f55e83775951a45_14.png)

![](img/2c05689fee2344289f55e83775951a45_15.png)

To solve this task。Right， so that that is basically birdt fine tuning on different tasks。

 And there is this benchmark called glue， where it has a number of tasks。 in this case。

 I think they look at9 tasks of glue。 It has nine of these tasks。 want to see。



![](img/2c05689fee2344289f55e83775951a45_17.png)

![](img/2c05689fee2344289f55e83775951a45_18.png)

![](img/2c05689fee2344289f55e83775951a45_19.png)

An example is the sentiment classification and it basically gets a score for each one and thereby you can sort of estimate how good your language model is by how well it is performing on each of those individual tasks。



![](img/2c05689fee2344289f55e83775951a45_21.png)

But the notable difference here too， let's say a computer which like an imagenet classifier is the fact that first it is pretrained。

 this part here is pretrained on a large corpus and second there are different downstream tasks that you fine tune on。

So。

![](img/2c05689fee2344289f55e83775951a45_23.png)

The second part that is important is the lottery ticket hypothesis。

 so I've also done a video on the lottery ticket hypothesis and。



![](img/2c05689fee2344289f55e83775951a45_25.png)

If you very quickly what the lottery ticket hypothesis is the following。

 so let's say you have an image classifier and I have a bunch of layers in my neural network andm going to draw them like this。

And at the end， right， I can classify it into like 10 different or a thousand different classes。

 whatever。And the input here is an image。So my neural network is going to have weights so every one of these neurons is connected to each other now this can be a convolutional network or a MLP。

 so all is connected to all and as well here right everything' is connected to pretty much everything。

So we know， first of all， we know that we can train these big networks。诶。To relatively good accuracy。

And then second of all， so first we can train them。Second， we know we can prune them after training。

What pruning means is the fact that after I have trained such a thing。

 I can then go and I can figure out which one， which of these connections that I have learned are the important ones。

 And maybe I'll say， these， these here， actually these， these five。 I don't need more than those。

 let's actually connect them to the end。These seven or so I don't need all of the other ones。

 I just need those and I can pretty much get the same accuracy as the full network。

Now the important part here is that you can only do pruning after you've trained a network if you try to prune at the beginning。

 it doesn't work so what the lottery ticket hypothesis says is basically so how does training work first you have your parameters let's tell them as a list so each of these weights is an entry in the list here。



![](img/2c05689fee2344289f55e83775951a45_27.png)

First， you initialize。These randomly， then through training。Training， you get to your train state。

 right， You get each of the ones into your。 These are now trained。And in the train state。

 you can select the ones you think are important。The lottery ticket hypothesis says。

 if I take those that are important and basically go back to the beginning。

Like here here and here and I basically rolled them back to that state that they were in when they were initialized。

 so I put the same random number there that I got at initialization I can then。



![](img/2c05689fee2344289f55e83775951a45_29.png)

![](img/2c05689fee2344289f55e83775951a45_30.png)

Make a network where I only have those。I can train that network。

And I can get a good accuracy so this basically wasn't possible in the pruning framework because we said we can't prune。

 we can only prune after training because only then do we know which ones are the important ones in fact the lottery ticket hypothesis or the paper shows that you can train the smaller neural network from the beginning。

 but the catch of course is you have to know which ones those are and you have to know what value to set them on at the beginning and you only know that after you've trained the full network but still it kind of gives the。



![](img/2c05689fee2344289f55e83775951a45_32.png)

![](img/2c05689fee2344289f55e83775951a45_33.png)

![](img/2c05689fee2344289f55e83775951a45_34.png)

![](img/2c05689fee2344289f55e83775951a45_35.png)

It tells you that you don't need all these connections for training。

 you basically only need so many connections such that somewhere in there there's going to be the good ones right and if you knew the good ones from the beginning。

 you could just train those and then only train the smaller subnet。



![](img/2c05689fee2344289f55e83775951a45_37.png)

![](img/2c05689fee2344289f55e83775951a45_38.png)

![](img/2c05689fee2344289f55e83775951a45_39.png)

So that's the lottery ticket hypothesis Natural these connections here。

 this small network is called the winning a winning ticket because if you knew what it was。

 you could basically train a much smaller network and reach the same accuracy So this paper looks at Bt in terms of this lottery ticket hypothesis now it's a bit more complicated than just in these feet forward networks because Bt is not a feet forward network Bt is a transformer so what does that mean。



![](img/2c05689fee2344289f55e83775951a45_41.png)

![](img/2c05689fee2344289f55e83775951a45_42.png)

![](img/2c05689fee2344289f55e83775951a45_43.png)

![](img/2c05689fee2344289f55e83775951a45_44.png)

![](img/2c05689fee2344289f55e83775951a45_45.png)

![](img/2c05689fee2344289f55e83775951a45_46.png)

A transformer consists of many layers and each layer， let's expand the layer here。

 so each layer consists of。

![](img/2c05689fee2344289f55e83775951a45_48.png)

Let's go over there， need some space。

![](img/2c05689fee2344289f55e83775951a45_50.png)

So again， we have our layers of B。And it goes the signal goes like this so each layer consists of two things first of all of many attention heads that's called and I'm going to draw these as blocks right here so for let's call them four attention heads individual attention heads are all parameterized by individual matrices and then on top of that there is an MLP so this is the multilayer per separate this is one basically a feet forward layer residual actually。

And so there is a skip connection right here， and these are the attention heads。Okay。



![](img/2c05689fee2344289f55e83775951a45_52.png)

And then the next layer would again have the same structure for of these and then one of these and so on with the skip connection。



![](img/2c05689fee2344289f55e83775951a45_54.png)

![](img/2c05689fee2344289f55e83775951a45_55.png)

So the pruning in Bt is different than pruning in the feed forwarder convolutionary at which that we looked at pruning in B to what this paper looks at is pruning either an entire attention head like this。



![](img/2c05689fee2344289f55e83775951a45_57.png)

So it's kind of leaving out in the entire head away， which is this is an entire matrix。

 this is not a single weight， right this is many， many weights or even more drastically leaving away an entire MLP and basically only relying on the skip connection。

All right， so this。You have these two things you can do。

 you can leave away heads or you can leave away entire MLPs or you can combine these things in some way。



![](img/2c05689fee2344289f55e83775951a45_59.png)

![](img/2c05689fee2344289f55e83775951a45_60.png)

Right so the notable difference here to the lottery ticket hypothesis pruning is the fact that here over up here。

 what we prune are connections so prune。

![](img/2c05689fee2344289f55e83775951a45_62.png)

Connections， individual connections。Individual connections。And here we prune entire modules。

Now this is a， in my opinion， this is a qualitative difference， a very large quality。



![](img/2c05689fee2344289f55e83775951a45_64.png)