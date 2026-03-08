# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p154 P154_L18.6-PyTorch中生成人脸图像的DCGAN_--_代码示例 -BV16EC5BUEi7_p154-

All right， so the last topic in this already very long G lecture is on implementing a D C G for generating face images and Pytorch。

And just when I looked at the paper again， actually， I just noticed it's also so much that I hear。

 the author of the G tips and tricks that we discussed in the previous video。So。Essentially。

 the only thing that is different compared to our previous Mist G is that the dataset is， of course。

 different and that we are now using。

![](img/267b69d5601c7f8b5e5f6df929788cec_1.png)

A convolutionalgan， instead of fully connected layers。So let's go through this step by step。

 again our boiler platelate here。 can notice we have two learning rates like before。Now， we have。

Slip a data set。

![](img/267b69d5601c7f8b5e5f6df929788cec_3.png)

Instead of emnesst。And here's an example of some of the images， how they look like。



![](img/267b69d5601c7f8b5e5f6df929788cec_5.png)

So it's an image data set consisting of celebrities collected from Google， I think。

 from the Google image search。

![](img/267b69d5601c7f8b5e5f6df929788cec_7.png)

Yeah， so and this is our deep conutional G here。ItLos of layers for the generator。

 the con trans post layers because we go from laed dimension by default 100。

 100 dimension noise vector。We go up。Sample it up， so。That it has 64 times 64 dimensional。

 so I should mention I resized if I go back up again， I resized the images here。

 so I first cropped them and then I resized them to 64 times 64 It's easier to train again with small images of course there are GNs with bigger images and if you look there are multiple approaches to that some people train the again still on lower images and then use super resolution methods some others do that directly but yes you can see these have much higher quality it's just hard to do that and especially with regular agains so there are many advanced GNs which we can't all cover in this class but for regular conclusion again like this one。

 it's easier to work with smaller image sizes。 it also depends really on how large your data set how many images you have how diverse the images are in terms of colors and view angles and things like that。



![](img/267b69d5601c7f8b5e5f6df929788cec_9.png)

![](img/267b69d5601c7f8b5e5f6df929788cec_10.png)

Many， many factors to consider。

![](img/267b69d5601c7f8b5e5f6df929788cec_12.png)

So here I found 64 times 64 worked much better than 128 times 128， for example。



![](img/267b69d5601c7f8b5e5f6df929788cec_14.png)

Okay， so here's just a snapshot。

![](img/267b69d5601c7f8b5e5f6df929788cec_16.png)

Of some randomly sampled people。And then， here on on。Generator again。

 So here I'm alternating between transpose convolution。Or just transpose convolution。

 I don't use any pooling or something like that。 It's just or no upseling。

 is's just transpose a convolution for making it larger。Then batchome， likirelu transpose， batchome。

 liquirelu， same thing， same thing。 And then the last one with a 10 H function here。

So that we get-1 at1 pixel ranges。And the discriminator is a little bit and not that much simpler。

 but maybe it's a little bit too big。 It's also one aspect of the discriminator too good。

 and it's also then challenging for the generator， so。N could have been a bit too big。

 but it happened to work。 So here at this screenator has a convolution layer， leaky relo。

 convolution layer， batchome， leaky relo， and so forth。

 So I'm done sampling with the convolution here instead of using max pullinging。Yeah。And end。

 there's a flatten。To get from so we don't use any fully connected layer。

 So here this is similar to what we discussed in a convolutional lecture。

 When we said we can actually get rid of the last。嗯。Fully connected layer。 if we make the dimensions。

 So such here， if I have 64 times 64 inputs at this point， when you do the math。

 you will have four times 4 feature maps。 and then I'm applying a convolutional layer with kernel size 4。

 So from 4 to 4， it will go to 1 to 1。And then， I go from。8 channels to one channel。

 So the output will be a 1 by one by one tensor。 And then I'm flattening it into a single value。

 which is my。Probability that this is a real image。Because we are using binary cross entropy。

And this looks like before a little bit simpler now compared to our。

Mnes scan because I wrote all the training function such that it works with images。

 And then when I had my Mnes scan， I had to adjust a little bit to do the reshaping because a fully connected layer works but with back to us not with images right。

 So I had to just do this back and forth here to make it work with my training code。

 but you could also always write more elegant training code to have an if else statement whether it's a convolution layer or fully connected layer but I yet I didn't do that much。

Work because I felt like the code is already complicated enough。Hard to read already。Okay。

 so I'm using Adam again for both。 I tried using SGD for the the screen data。

 but it didn't work so well。Requires also more learning， great tuning。

 And already took me a long time to get this running well。So yes。

 my training function the same as before。 we can take a look at this again。 if you like。

 I there's nothing new so nothing has changed。But there was one thing I wanted to discuss briefly。

 So one thing I was wondering when I was going over the tips in the previous video that I was thinking of one additional tip that is。

Whether we should sample the noise separately for the discriminator and the generator。 So here。

I'm getting the generated fake images。 I was wondering， so here I'm using them again。

 so sorry here I'm using them for the the screenator and here。For the generator。

 I'm using them again。 So I was wondering。Instead of having the noise here。

Like for the screenator and the generator， we could maybe have。So it's pretty clear if I put it here。

 we could have it here。Fake images fall。The discreterier。

 but then use different ones for fooling the discreteer。

Find this is maybe also an interesting thing to try out。 Actually， I haven't tried this。

 I could run this and see if it performs better because。The rationale could be here。

 we are training the discriminator to recognize these images as fake。Here。

 and then we are training the generator。to basically fool the discer with these images。

But I'm wondering if it's just back and forth because we use the same batch。

 whether it might be better to use a fresh batch so。Instead of using the same one for both。

 having these two different ones might be another trick to try。

 I haven't tried this might be something else to consider。 Maybe doesn't make a difference。

 I don't know， okay。So， but except that the whole training function is still the same。

Going back to my coach。6 one。Training it。And see kind of stays okay。 So nothing。

 So the discgraator doesn't go to 0， which is bad。Or yeah。

0 loss for the disc means it's way too good。And。😔，Nothing unusual。 It's training for long time。

20 epochs。Sorry， one hour almost。 I mean， for the grand scheme of things for deep learning。

 it's actually pretty fast。 But if you try to code the lecture。So that I can talk about it。

 I was like。Yeah， a little bit on time constraints。

 I was happy that it finished so fast because I also had to try different hyperparmeters。 Yeah。

 so it's， it's a lot of work actually to do these codes。

 So I talk to some people during office hours and some students that it's kind of takes a long time to work on the project。

 But yeah， I can totally understand you because also for research or these even these simple class examples。

 It takes a long time。 It's just the nature of deep learning。😊，So yeah plotting things， I can see。

 it's interesting。 The generator goes up。 that is great S。Kind of low here， actually， to be honest。

 approaching 0。 But when I look at the results， they looked actually quite reasonable。



![](img/267b69d5601c7f8b5e5f6df929788cec_18.png)

So first epoch can see these don't really look like face images。 but as we go further， epoch 5。

 epoch 10， so。

![](img/267b69d5601c7f8b5e5f6df929788cec_20.png)

![](img/267b69d5601c7f8b5e5f6df929788cec_21.png)

Not all of them look realistic， but this person。

![](img/267b69d5601c7f8b5e5f6df929788cec_23.png)

Maybe this personnel， to some extent， start looking more realistic。 I mean， of course。

 you can see they are generated。 They are not that great， but they are also not terrible， right。



![](img/267b69d5601c7f8b5e5f6df929788cec_25.png)

![](img/267b69d5601c7f8b5e5f6df929788cec_26.png)

![](img/267b69d5601c7f8b5e5f6df929788cec_27.png)

So yeah， could be better。 The results could be better。 This person looks kind of realistic。 But yeah。

 given that this is very simple code， I only trained 20 epochs。 It doesn't look too terrible。

 in my opinion。 actually， just wanted to show you one that actually failed。



![](img/267b69d5601c7f8b5e5f6df929788cec_29.png)

![](img/267b69d5601c7f8b5e5f6df929788cec_30.png)

![](img/267b69d5601c7f8b5e5f6df929788cec_31.png)

So the difference between the 1 I just showed you and this one is only that here I initially had a regular relu。

And when I train it with a regular re。It was first going fine。 And then we had this huge spike here。

 and then suddenly。

![](img/267b69d5601c7f8b5e5f6df929788cec_33.png)

Things looked very different。 And now looking at the results first， it looks the same as before it。

 right。

![](img/267b69d5601c7f8b5e5f6df929788cec_35.png)

![](img/267b69d5601c7f8b5e5f6df929788cec_36.png)

Looks okayish。 But then suddenly there's some mod collapse and something like that。

 You can see they all look the same。 So it looks like mode collapse。



![](img/267b69d5601c7f8b5e5f6df929788cec_38.png)

Where。

![](img/267b69d5601c7f8b5e5f6df929788cec_40.png)

The screener can be easily probably fooled by the generator or something like that。



![](img/267b69d5601c7f8b5e5f6df929788cec_42.png)

generatorener is also very noisy。 It generates the same type of image。



![](img/267b69d5601c7f8b5e5f6df929788cec_44.png)

Kind of。 So yeah， that was also interesting。 Okay， so that is a deep convolution。 Again。

 it's overall， if you look at the code， it's a pretty complicated topic， right， we have a。



![](img/267b69d5601c7f8b5e5f6df929788cec_46.png)

A lot of training code。 But that's just yeah， the nature of deep learning。 To be honest。

 it also takes me time to write this， but。I remember when I was a student when this was all kind of new back then。

 I didn't learn this actually in class because yeah， I was finished with classes when Gs came out。

 but was reading the paper， looking at some early code examples。

 I think it was the yeah back in the day code was much harder to read compared to Pytor and it also took me a long time to kind of figure out how the code works。

Now it's， for me easier。 I can write these things myself。

 but it I would say it's still one of the more complicated。Models compared to， let's say， classifier。

 So if this looks all complicated to you， you just need to give it some time。

 You have to maybe implement it yourself or take some code， modify it a little bit。

 maybe apply some of the tricks。 So you could， for instance， apply the trick where。

You flip the labels for the discriminator or occasionally and just get a better of feeling for the code and where things are and。

Yeah then with some time you will also become pretty confident reading code。

 but yeah it really takes time so I can imagine just taking one class is not enough to really get confident doing this it takes probably years and what's very important is really working on the projects where you you just work by yourself I mean not totally by yourself you have your team you can ask me for feedback many students or several students an office hours where usually help with the coding parts of their errors but ultimately you need to spend time with the code there's no kind of textbook or anything like that that helps you really understanding everything it is really through interaction most of it and also doing some search on the internet and this is how everyone who's doing coding learns it's a process it takes practice。

Alright， so with that， let me then end this already long lecture on generative adsial networks。



![](img/267b69d5601c7f8b5e5f6df929788cec_48.png)