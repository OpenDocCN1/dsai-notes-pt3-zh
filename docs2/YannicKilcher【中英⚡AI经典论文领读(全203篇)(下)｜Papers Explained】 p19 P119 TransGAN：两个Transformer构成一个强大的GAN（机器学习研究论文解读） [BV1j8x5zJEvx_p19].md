# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p19 P119 TransGAN：两个Transformer构成一个强大的GAN（机器学习研究论文解读） [BV1j8x5zJEvx_p19]

Hi there。 Today， we'll look at transgan。 Two transformers can make one stronggan by Y Fan Qang。

 Xuqang and Changyang Wang。 So in this paper， the authors attempt to make a generative adversarial network a G out of only transformers。

 So far， attention or transformer like things have been used in Gs。

 but they've always had some component of convolutions in there。

 This paper attempts to do generator and discriminator just using transformers。

 They discuss what is needed to do that。 how they built the architecture and there are a couple of training tricks that make this work and actually make this competitive to current state of the art architectures。

 So the biggest data set they tackle is setup a， which is 64 by 64 pixels。



![](img/319e251b3df63126658a89ca72911788_1.png)

But， you know， due to their numbers suggest you can scale this much larger。

 The model is called transgan。 I I don't know if this is a bit of an unfortunate naming。

 I guess the question is， which bathroom do the transcan go to。



![](img/319e251b3df63126658a89ca72911788_3.png)

![](img/319e251b3df63126658a89ca72911788_4.png)

I don't know in any case。

![](img/319e251b3df63126658a89ca72911788_6.png)

Let's dive into the paper， let's check it out if you like content like this， share it out。

 leave a like， and tell me what you think in the comments。



![](img/319e251b3df63126658a89ca72911788_8.png)

So the paper is fairly straightforward， actually。There is code available。

 so definitely check that out I'll link that of course， in the description。

 the paper is fairly straightforward and answers one question。

 Can we build a strong ga completely free of convolutions。



![](img/319e251b3df63126658a89ca72911788_10.png)

So usually in Gs， you have convolutions both in the generator and the discriminator。

 and their goal is to just replace that using transformers， as we say， their contributions。

 there are three， the model architecture。

![](img/319e251b3df63126658a89ca72911788_12.png)

So the discriminator， as we're going to see， is a vision transformer， like we saw before。

 the generator is also a transformer that is interlaed with up sampling。



![](img/319e251b3df63126658a89ca72911788_14.png)

Then training technique， they do discuss that you do need。Three things specifically。

 so you do need data augmentation， you need multitask code training for the generator and you need a localized initialization for the self attention in order to make this work。



![](img/319e251b3df63126658a89ca72911788_16.png)

And then they reach a G， so their model， their biggest model transgan XL。

 reaches very competitive FID scores and also very competitive inception scores。Wait， this is F here。

 Here is the inception score。 The I S score is a bit of a misnome or 2。 I mean。

 the S is already score， but。

![](img/319e251b3df63126658a89ca72911788_18.png)

You know who it's okay。

![](img/319e251b3df63126658a89ca72911788_20.png)

Yeah。So first architecture， the architecture is fairly straightforward， so for again。

 you need a discriminator and a generator。Now the discriminator， as I already said here。

 that is the exact model from VIT and I've done video about it。

 the paper is calledA picture is worth 16 by 16 pixels or something like this。



![](img/319e251b3df63126658a89ca72911788_22.png)

Well I don't exactly remember， but you can you can check you can definitely find that it is a transformer based image classifier so what you do with an image so here you see an example image this image of the dog what you would see if you were to feed this into the discriminator。

 of course the discriminator gets the output from the generator， but also the real data you would。



![](img/319e251b3df63126658a89ca72911788_24.png)

![](img/319e251b3df63126658a89ca72911788_25.png)

![](img/319e251b3df63126658a89ca72911788_26.png)

![](img/319e251b3df63126658a89ca72911788_27.png)

You would unroll that picture into these kind of sub pixels， as you can see right here。



![](img/319e251b3df63126658a89ca72911788_29.png)

But not into full pixels but into kind of these super pixels。

 so every one of those super pixels will then be unrolled。

 this is this flattening operation right here into a single vector and that then is like a word in a sentence okay so this picture here just becomes a series of vectors。



![](img/319e251b3df63126658a89ca72911788_31.png)

And then you can simply apply your regular transformer or architecture。

 So every patch becomes a vector， like a word embedding。

 And then you just go ahead and you put a transformer encoder。 So this is very much like Bt。

 for example。

![](img/319e251b3df63126658a89ca72911788_33.png)

![](img/319e251b3df63126658a89ca72911788_34.png)

![](img/319e251b3df63126658a89ca72911788_35.png)

It is a similar architecture， as you say you can go look at this paper。

 and at the end you simply classify whether it's real or fake。



![](img/319e251b3df63126658a89ca72911788_37.png)

You do have to add position encodings because you lacking the convolutions。

 the transformer has no idea where in the picture a given given thing appears because it is not a sequential architecture it's actually a set transformation architecture。



![](img/319e251b3df63126658a89ca72911788_39.png)

So you do need to add positional encodings， but in general。

 this has been shown to work quite well in things like INe classification。



![](img/319e251b3df63126658a89ca72911788_41.png)

![](img/319e251b3df63126658a89ca72911788_42.png)

On the generator side， it is very similar， but a little bit different。



![](img/319e251b3df63126658a89ca72911788_44.png)

Here， what you need to achieve are of course。

![](img/319e251b3df63126658a89ca72911788_46.png)

而。These 32 by 32 by 3 pixel image， right， That's at the end。 You need to achieve that。 Now。

 you can't just go the reverse from over here and somehow try to predict these patches because that。

 I guess that is just to。

![](img/319e251b3df63126658a89ca72911788_48.png)

![](img/319e251b3df63126658a89ca72911788_49.png)

![](img/319e251b3df63126658a89ca72911788_50.png)

You know， if if you predict these patches as such like independent patches from each other。

 the borders would never match up in a discriminator。

 this is not does not matter because you don't need to construct the image simply need to classify it。

 but if you need to generate images it you know it doesn't look good if you have these borders here where things don't match up。

 so you will actually need to produce an image that is in the size that you require。 So in this case。

 yeah， 32 by 32 and of course， three color channels。



![](img/319e251b3df63126658a89ca72911788_52.png)

![](img/319e251b3df63126658a89ca72911788_53.png)

![](img/319e251b3df63126658a89ca72911788_54.png)

![](img/319e251b3df63126658a89ca72911788_55.png)

![](img/319e251b3df63126658a89ca72911788_56.png)

![](img/319e251b3df63126658a89ca72911788_57.png)

So the way they achieve it is by this upsembling architecture。 The problem with transformers。

 of course， is they do require quite a bit of memory and also compute because the attention mechanism basically connects every single token with every single other token in each transformation。

 In this case， they connect every pixel to every other pixel。 Now if you were to do this for many。

 many layers that is going to be you know 32 squared in this case memory requirements pretty quickly you will run into problems。

 So what they do is they have。

![](img/319e251b3df63126658a89ca72911788_59.png)

![](img/319e251b3df63126658a89ca72911788_60.png)

![](img/319e251b3df63126658a89ca72911788_61.png)

![](img/319e251b3df63126658a89ca72911788_62.png)

![](img/319e251b3df63126658a89ca72911788_63.png)

![](img/319e251b3df63126658a89ca72911788_64.png)

![](img/319e251b3df63126658a89ca72911788_65.png)

Intrinsic upscaling of their dimensions。

![](img/319e251b3df63126658a89ca72911788_67.png)

What does that mean， So at the beginning， you have like some。

 some noise input and you have a little MP generating the initial sequence。 Now。

 the initial sequence is going to be 8 by 8 by number of channels。

 You can see there are also position encodings right here。

 So your noise generator essentially creates an 8 by 8 grid。 Okay。



![](img/319e251b3df63126658a89ca72911788_69.png)

Let's say for the sake of argument， we create a 2 by2 grade instead of an8 by8 with a number of channels。

 so here is the number of channels to the back。

![](img/319e251b3df63126658a89ca72911788_71.png)

You want to unroll those into four vectors of these channels。One，2，3，4。

 you get the idea and then that you feed into the transformer so now you have four tokens or here 64 tokens in that case。

 but in our case four tokens that you feed to the transformer so right now at this stage this is like a sentence with four different words so you run that through M layers of the transformer。



![](img/319e251b3df63126658a89ca72911788_73.png)

![](img/319e251b3df63126658a89ca72911788_74.png)

![](img/319e251b3df63126658a89ca72911788_75.png)

![](img/319e251b3df63126658a89ca72911788_76.png)

And then at some point you decide， okay， now it's time to do upscaling。



![](img/319e251b3df63126658a89ca72911788_78.png)

And the upcal in the upscal， you take that those four words。

 So you take that two by two image that you have right here with the C channels and you generate somehow from it。

 And we're going to look at， I'm going to draw this over here。 So you generate somehow。



![](img/319e251b3df63126658a89ca72911788_80.png)

![](img/319e251b3df63126658a89ca72911788_81.png)

![](img/319e251b3df63126658a89ca72911788_82.png)

An image that is double。The density in pixels。So this is now a four by four image。

But it has less channels。 So the way they save memory is that they start out with many channels。

 but very very coarse resolution。 and progressively as they go up the layers。

 they ups sampleample so that they have more resolution， but less channels， okay。



![](img/319e251b3df63126658a89ca72911788_84.png)

![](img/319e251b3df63126658a89ca72911788_85.png)

![](img/319e251b3df63126658a89ca72911788_86.png)

![](img/319e251b3df63126658a89ca72911788_87.png)

And the exact。 so this is， this is very much like like the convolutionalgans do。 So like they。

 they would start out with a very coarse image grid， and then they do some kind of up samplingling。

 some kind of strided pooling and so on in order to reach higher。



![](img/319e251b3df63126658a89ca72911788_89.png)

![](img/319e251b3df63126658a89ca72911788_90.png)

Higher pixel densities and with the higher pixel densities they often decrease the number of channels。

 so you get a trade off between the density and the kind of depth of information at the end they end up with their target resolution and a number of channels and then they feed that through a small they feed each individually through a small。



![](img/319e251b3df63126658a89ca72911788_92.png)

![](img/319e251b3df63126658a89ca72911788_93.png)