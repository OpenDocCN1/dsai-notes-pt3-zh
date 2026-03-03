# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p06 P6 大型迁移模型（BiT）：通用视觉表征学习（论文详解） [BV1o3xLznExj_p6]

Hi there。 Today we're talking about big transfer， general visual representation learning by Alexander Klesnikov。

 Lukas Bayer， Jawa Chai and others of Google Bra。

![](img/6542aa70625ecea811eb2d48337fa310_1.png)

So this paper is basically an application slash engineering paper for the community。

 and it is about the task of transfer learning for visual tasks。

 So what does that mean in a visual task， the meaning is basically that the input is an image。

 So it could be a classifier where you have an image and you have to say that this is a cat。

 or it could be， let's say， a。

![](img/6542aa70625ecea811eb2d48337fa310_3.png)

Medical image of a lung。And you have to point out where the defect in the lung is or or if there is a defect in the lung or something like this。

 As we all know， this field is pretty much dominated by CNNNs。

 by convolutional neural networks that take in these images through many layers of convolution。

 especially residual networks are doing particularly well on these tasks。 The problem， of course。

 is that in in in some tasks。You have lots of data。

 And that's fine because C N Ns need lots of data to train。 But in some tasks。

 especially these medical tasks， you only have like very small database。 Look at the small database。

 only very few labeled samples where the model could learn from。

 And that just is is not enough to learn these big models that would perform well。

 So you will have to settle for a less performing model。 Now。

 the solution or one of the solutions is transfer learning in transfer learning。

 What you do is you take。A large data set， for example。The imagenet dataset set。

 you have this big data set right here， and you train your CNN on that。

And then you take that CNN and you do what's called a fine tuning step on this small dataset set。

 you take the CNN that you gained from the large dataset set as a starting point。

 And then you just train for a few steps， You just kind of adapt it to this final dataset set that you actually want to train it on。

 And that usually helps。 And why does that help Because。

You sort of hope that the the large dataset set and the small dataset set are at least somewhat overlapping in in there。

 So the the images in the large dataset set are somewhat similar to the images in the small dataset set。

 It doesn't need to be super similar， but just somewhat。

 and you hope that the features that the CNN learns from the large dataset set are useful in the small dataset set。

Because then if that is the case， when you fine tune on the small data set。

 that's this step down here。 that's called fine tuning。 When you fine tune。

 you can pretty much reuse those features。 you only have to adjust them a little bit and you just have to learn how to map the features to the output which now is。

 of course different than in the original task， but you won't have to rediscover the features。

So that's why transfer learning can help。 So the first phase is called pre training。



![](img/6542aa70625ecea811eb2d48337fa310_5.png)

![](img/6542aa70625ecea811eb2d48337fa310_6.png)

The second phase is called fine tuning。 Now， the ultimate goal in this is the following。

 Imagine you have like a giant database of data。Right， this is giant。

 Look at the size comparison to the others。And so you have this big。

 big database of images and you train a CNN on that big database of labeled images。Now。

 what you're hoping is that you can do this once。 and then this one CNN trained on this giant dataset will become starting point for all kinds of small tasks now。

 So basically you can post this on a repository online。

 and everyone that has a visual task will not train from scratch but they will basically take the this one CNN as a starting point。

 is is very similar to what people are doing right now with Bt or generally these transformer language models。

 You never want to train them from scratch。 You always want to train from a pretrained state that someone else has done because usually the big work is now shifted to the pretraining So the goal is to find this one universal starting point for visual learning。



![](img/6542aa70625ecea811eb2d48337fa310_8.png)

![](img/6542aa70625ecea811eb2d48337fa310_9.png)

![](img/6542aa70625ecea811eb2d48337fa310_10.png)

![](img/6542aa70625ecea811eb2d48337fa310_11.png)

And of course， no better place to do this than Google。

 they certainly do have a giant databases of images。 They certainly have lots of computation。

 which we're going to see is very necessary for something like this。



![](img/6542aa70625ecea811eb2d48337fa310_13.png)

![](img/6542aa70625ecea811eb2d48337fa310_14.png)

![](img/6542aa70625ecea811eb2d48337fa310_15.png)

Now， they do train three different models。 Their model is called B I T。

 and they train three different variants。 B I T， small， medium and large。 So the L model。



![](img/6542aa70625ecea811eb2d48337fa310_17.png)

Is trained on 300 million images。The medium model is trained on 14 million images。 so this is the。

 I think it's called J ofT data set。 this here is called the imagenet 21 k dataset set。

 which looks pretty funky it has like objects in front of weird backgrounds and stuff like that。

 and the small is simply trained on the 1。3 million imagenet dataset set。 So I mean。

 just look at this we're in a situation now where the small model is train is pretrained on imagenet just。



![](img/6542aa70625ecea811eb2d48337fa310_19.png)

![](img/6542aa70625ecea811eb2d48337fa310_20.png)

For reference， if you had imagined this five years ago this， you would not have。

 maybe you would have guessed it， but it's still impressive。



![](img/6542aa70625ecea811eb2d48337fa310_22.png)

![](img/6542aa70625ecea811eb2d48337fa310_23.png)

So they do release these two models here， the medium and the small one， pretrained。

 I believe they don't release the large one， which maybe that's the price we have to pay for getting the medium and the small one。

 the fact that now Google can use this in their products。

 because they have probably spent the considerable amount of money in doing this。

 I'm not sure this is a philosophical discussion whether in the interest of science。

 they should release all because they do give the the sort of exact training protocol。

 You just need the money basically。

![](img/6542aa70625ecea811eb2d48337fa310_25.png)

![](img/6542aa70625ecea811eb2d48337fa310_26.png)

![](img/6542aa70625ecea811eb2d48337fa310_27.png)

![](img/6542aa70625ecea811eb2d48337fa310_28.png)

![](img/6542aa70625ecea811eb2d48337fa310_29.png)

Allright， but that's not topic of this video。So the models here are all pretty much just residual networks。

 there are all these resnet 152， I think X4， which means that basically scale the width of each layer by a number of four from the original resonnet architecture and that's pretty much it they just this is the architecture there's nothing really new in this paper。

 It's the paper just details what exactly you have to do which things exactly matter when you pretrain these things and which ones don't and therefore I believe it is it is a pretty good paper and I think that these models here。

 the M and S models and maybe someone else trains an L model and releases it will sort of become the standard like we have in B now。

 So whenever you have a visual task。 you're just gonna start from those。



![](img/6542aa70625ecea811eb2d48337fa310_31.png)

![](img/6542aa70625ecea811eb2d48337fa310_32.png)

![](img/6542aa70625ecea811eb2d48337fa310_33.png)

![](img/6542aa70625ecea811eb2d48337fa310_34.png)

In practice。 So this， I think， is mainly relevant for people in practice。All right。

Here you can see the。These models。First of all， excellent， excellent， not labeling of your X axis。

 Absutely beautiful。 The X axis， I believe， is the number of samples per data class。

 So now they take their preted model， this bit L， and they fine tune it on these data sets。

 So Inet is one of the tasks they find tune on or C for 10， C for 100 and so on。😊。



![](img/6542aa70625ecea811eb2d48337fa310_36.png)

And。First of all， look on the right side， this full thing。

 This is when you take the entire dataset set。 So often they outperform。

 they get state of the art on the full dataset sets。 Now。

 they do compare against what they call generalist models。

 So generalist models are ones that have this particular training protocol where they train on one big giant database and then fine tune to all the other tasks。

 They do not achieve state of the art on all data sets in what they call specialist models。

 The specialist models would be such models that。

![](img/6542aa70625ecea811eb2d48337fa310_38.png)

![](img/6542aa70625ecea811eb2d48337fa310_39.png)

Have this exact task in mind。 And therefore， they don't care about other tasks。

 They outperform some of these specialist models， but not all of them， so。



![](img/6542aa70625ecea811eb2d48337fa310_41.png)

This is not a， this is not the new state of the art in everything。

 but it is in this transfer learning regime。And I think even more important， if you see on the left。

 this is in the small label regime。 So here you have something like 100 or 25 or 10 or even five labels per class。

 And if you take five labels per class for C for 10， this model。

 so of course you have to pretrain it first on the big dataset set。



![](img/6542aa70625ecea811eb2d48337fa310_43.png)

But just taking five labels per class， you still get like 94% accuracy on C410。

 and that's pretty good。

![](img/6542aa70625ecea811eb2d48337fa310_45.png)