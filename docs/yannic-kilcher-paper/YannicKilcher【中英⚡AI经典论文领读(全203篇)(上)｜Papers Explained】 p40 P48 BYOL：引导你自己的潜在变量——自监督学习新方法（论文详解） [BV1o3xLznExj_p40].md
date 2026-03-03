# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p40 P48 BYOL：引导你自己的潜在变量——自监督学习新方法（论文详解） [BV1o3xLznExj_p40]

Hello there。 Today， we're looking at bootstrap your own latent。

 a new approach to selfsupvised learning by researchers of Deep mindd and imperial college。

 So not almost nowaday goes by where we don't hear some sort of new selfsupervised algorithm right here。

 this paper on a high level tries to get rid of the necessary negative samples when doing the contrastive loss for selfsupervised learning。

 and they basically combine momentum contrast and same clear and then remove the negative samples and that seems to work pretty well。

 even though it's magic。 So yeah， if you。

![](img/01db7e88dcf3c70446f310d1a5915756_1.png)

![](img/01db7e88dcf3c70446f310d1a5915756_2.png)

If you want to see how it's done， stick around， share the video out if you want other people to see how it's done and leave a comment。

 this one， I really don't get what's going on。

![](img/01db7e88dcf3c70446f310d1a5915756_4.png)

If you have ideas， put them there， I'll read them through， it'll be fun。Allright。

 so they say we introduce bootstrap your own latent or beol。

A new approach to self supervised image representation learning。Okay。

 so image representation learning is the simple task of taking an image。

And then feeding it through a function which is usually like a neural network。

 let's just say this is a neural network and in fact all of these。

 the community has sort of standardized this to be most of the time it's something like a ResNe 50 so what you want to do is you want to train a neural network like a Resnet 50 to give you a good representation of the image。

 so this would be like H and H is a vector。And H is a representation of this image。

 and the representation should be。Such that you can then take this representation and solve many tasks with it。

Which either can be like linear。 you can put a linear classifier on top of the H。

 or you can finet the entire architecture to solve some other task。

 The idea is if you have a large data set here you may use this dataset to train these good representations of these images and then you can transfer learn transfer this to a task where you might be not have as much data and because you don't have as much data。

 it's not enough to completely train an architecture like this but it is enough to take an architecture that's been trained with a large data and just adapt it to your small data and that usually it tends to work pretty well。

 This is called transfer learning This step here is called fine tuning sometimes and。

It's sort of the approach that comes from natural language processing from these big transformers like BerRT where you first train on a really big data set that might not be the data that you want in the end but it's really big so you can sort of learn a lot of things from that dataset and then the only thing left to do is to fine tunenet to basically adapted to the nuances of your dataset but it will have learned the most things already。

 and that's called representation learning so the goal is to learn a good representation。



![](img/01db7e88dcf3c70446f310d1a5915756_6.png)

Now， the self supervised here is also important because representation learning can be as easy as。



![](img/01db7e88dcf3c70446f310d1a5915756_8.png)

![](img/01db7e88dcf3c70446f310d1a5915756_9.png)

If this here is Inet， the Inet dataset set contains like a million images all with labels。

 you can simply train your Resnet 50 to predict the class。

 is the this is called supervised pretrain or supervised representation learning and that works pretty well。

 but you need a labeled data set in self supervised learning。 you do not need labels。

 What you do is you do self supervision and self supervision it has many there there are many ways to do self supervision。

 but what we'll see in this particular paper is。

![](img/01db7e88dcf3c70446f310d1a5915756_11.png)

![](img/01db7e88dcf3c70446f310d1a5915756_12.png)

![](img/01db7e88dcf3c70446f310d1a5915756_13.png)

That you will take an image and you'll make a different variant of that same image。

 So you'll take the image， and you'll make。Many， many variants of it。 Well let's just say two。



![](img/01db7e88dcf3c70446f310d1a5915756_15.png)

So you have some procedure to sort of change the picture a little bit。

 but it's essentially still the same and you do that through data augmentation。

 So this could be a random crop or you color jitter or you rotate it or something like this and then you exploit the fact that you know that these two things they should be still sort of the same image。

 So once you send them through through your encoder， the representations of the two images。

 they should be fairly close。

![](img/01db7e88dcf3c70446f310d1a5915756_17.png)

![](img/01db7e88dcf3c70446f310d1a5915756_18.png)

Now let's actually read on right here。U。Bole relies on two neural networks referred to as online and target networks that interact and learn from each other from an augmented view of an image。

 we train the online network to predict the target representation of the same image under a different augmented view。

Okay， that's sort of what we saw， so have we have the same image under a different augmented view。



![](img/01db7e88dcf3c70446f310d1a5915756_20.png)

So what does it mean， what， what I just said you make two versions of the same image。

 one that are slightly different， and then their representation should be close。 Now。

 until this point， we have always thought that this would degenerate because。

What if you think of this neural network that does this encoding to the hidden space。

 thissnet 50 right here。

![](img/01db7e88dcf3c70446f310d1a5915756_22.png)

If it wants to， if you simply want to make the two representations close。

 what's the best thing it can do， it can simply map all map the hidden。

 It can simply have the constant function H equals 0 or something like this just a constant function because then this loss here is always going to be0 like perfect okay so no matter what image comes in if you always map it to the same thing you you will always be close in representation space and therefore you always win that doesn't learn a really good representation right So what people have done is they have included socalled negative samples。



![](img/01db7e88dcf3c70446f310d1a5915756_24.png)

![](img/01db7e88dcf3c70446f310d1a5915756_25.png)

Where you'll say。I'll take a different image from， you know from this data set。

 but it's a different image than this image and I also do some maybe some data augmentation with that image。

 and then I send this through the same encoder to also give me an H so this is the H what's call that H original this is H plus because it's the same image but slightly differently augmented and this is H minus which is a different image。



![](img/01db7e88dcf3c70446f310d1a5915756_27.png)

And now the task is， let's make those two very similar to each other。

 but let's distance them from this other one。 So we want， we want this to be as far away as possible。

 And these two to be close to each other。

![](img/01db7e88dcf3c70446f310d1a5915756_29.png)

Now the network can't simply map everything to a constant function anymore， right。

 it needs to actually do something to make these be close together and this be far apart。



![](img/01db7e88dcf3c70446f310d1a5915756_31.png)

![](img/01db7e88dcf3c70446f310d1a5915756_32.png)

And the combination of this， together with the augmentation procedure that goes into augmenting the images has been sort of a good combo to learn good representations and a lot of papers have alluded to the fact that this is so the negative samples are to to not have these degeneracy so to not have the simple solutions。

 but the fact that the representation then is actually good like is good for image image tasks down the line。

 probably comes from the fact of these augments right here and there's a lot of evidence from the fact that depending on which augmentations we choose these representations are going to be better or worse。

 for example， random cropping of an image， so the random sub like taking a random crop from the image。

Tends to be very， very。Beneefficial， because so here， this is the same image twice， right。

 Let's say we take a random crop here and one up here。

 It's sort of maybe there's an overlap here in the middle， right。



![](img/01db7e88dcf3c70446f310d1a5915756_34.png)

So it sort of needs to understand that these random crops sort of needs to communicate。

Between these two places in these random groups， so the representation has to somehow。

Make sure that the object that is overlapping here is somehow represented。

 but it can't represent it just as a pixel value because it doesn't know where the crops come from。

 so there's a lot of evidence that these representations are the thing that's responsible for making the representation so good。



![](img/01db7e88dcf3c70446f310d1a5915756_36.png)

![](img/01db7e88dcf3c70446f310d1a5915756_37.png)

![](img/01db7e88dcf3c70446f310d1a5915756_38.png)

Okay， now this paper。

![](img/01db7e88dcf3c70446f310d1a5915756_40.png)

Simply says do we really need these negative samples right here， Let's just get rid of them。

 And with a couple of tricks， this seems to work。 And this is。

 this is what seems like magic to me because。

![](img/01db7e88dcf3c70446f310d1a5915756_42.png)

![](img/01db7e88dcf3c70446f310d1a5915756_43.png)

![](img/01db7e88dcf3c70446f310d1a5915756_44.png)

As we go forward， think of it， nothing。Nothing keeps this model right here from doing the degenerate solution H equals constant。



![](img/01db7e88dcf3c70446f310d1a5915756_46.png)