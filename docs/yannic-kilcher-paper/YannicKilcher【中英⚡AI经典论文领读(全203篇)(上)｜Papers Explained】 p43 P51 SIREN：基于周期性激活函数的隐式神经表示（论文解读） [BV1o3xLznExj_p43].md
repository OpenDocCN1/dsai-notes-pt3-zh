# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p43 P51 SIREN：基于周期性激活函数的隐式神经表示（论文解读） [BV1o3xLznExj_p43]

Hi there， Today we're looking at implicit neural representations with periodic activation functions by Vincent Sitzman。

 Julian NP P。 Martell， Alexander W。 Bergman， David Blanddell and Gordon Wettstein。

So this paper is a bit of a special paper。 If you're like me coming from like classic machine learning or deep learning。

 things like this， this paper requires you to think around your。



![](img/3ade99e91afc604146b08237908ca841_1.png)

Your notion of what it means to handle data and so on a bit and to think about data points and so on。

 essentially what they're doing is they are representing signals such as images or sound or generally waves or point clouds they're representing these signals as functions。

 mapping， for example， from their cord in it to their values。 and we'll see what that。



![](img/3ade99e91afc604146b08237908ca841_3.png)

Entails and they they're not the first ones to do do this。

 but they manage to do this very well using these new models called sirens。

 which are basically neural networks that so sirens spt like this。

 neural networks that have sine waves as their non nonlinearities instead of like res or hyperbolic tangents and so on。



![](img/3ade99e91afc604146b08237908ca841_5.png)

![](img/3ade99e91afc604146b08237908ca841_6.png)

So the it turns out that if you initialize these very carefully。

 those can be made to capture these signals very， very well。

 So that's the kind of high level overview and。

![](img/3ade99e91afc604146b08237908ca841_8.png)

Will go through the paper in a bit of a fashion of someone that is not in this particular literature。

 So this is not going to be like as in depth or technical as usually because I myself。



![](img/3ade99e91afc604146b08237908ca841_10.png)

I'm not super familiar with， with this kind of literature with the neural representations and so on。

 So if you go at this paper from a machine learning perspective， the first like you。

 you're going to be ultimately like super confused at the beginning。

 So I'm going to try to kind of clear up re retrace my steps of my confusion。 Okay。

 so I love that this paper starts out that we are interested in a class of functions Phi。

 that satisfy equations of the form。😊。

![](img/3ade99e91afc604146b08237908ca841_12.png)

This right here， like， aren't we all like。We are interested in a class of functions。Okay。I've never。

 you know， particularly had many dreams about functions like this。 But so how can you。

 how can you look at this。 So were， we're interested in the relation between inputs。And outputs。

 this here is the function。 as you can see， this maps input to output Okay and we're also interested in its derivatives。

 So here you go first， second， third derivative and so on。

 So this function right here is what we're going to call a neural representation or an implicit representation it's called a neural representation。

 I guess if it's a neural network that this function is so。



![](img/3ade99e91afc604146b08237908ca841_14.png)

![](img/3ade99e91afc604146b08237908ca841_15.png)

![](img/3ade99e91afc604146b08237908ca841_16.png)

So far， so good。 you've seen this， right， You've seen this could be a data point and then could map it to a label or something like this。

Since we're going to represent images， you already know maybe again a generative adversarial network where this here is the latent vector。

 And then you have a neural network mapping this latent vector to an image。

 right So this is going to produce an image。This here is quite similar， but not quite so in again。

 I guess this here would count as the the representation。

 the continuous representation of this picture。 however， in this case right here。

 the function itself is the representation。So in again， what we do， we learn this right here。

 this function p。 We learn this from data such that if I plug in one particular vector。

 I get one particular image。 And if I plug in another vector， I get another image。

 and the function always stays the same here， it's going to be one function per image。

 So each image the function is the image。 So how is a function and image， you can simply。

 if I have an image。

![](img/3ade99e91afc604146b08237908ca841_18.png)

![](img/3ade99e91afc604146b08237908ca841_19.png)

And it's made of pixels， right， So it's made of pixels。

Each pixel has an x and the y coordinate in it。 Okay， let's call that x1 and x2。

 the coordinate of that。And each pixel also has a color value， right， which is three dimensional。

 So each pixel has a three dimensional R G B color value。 So technically。

 an image is a function from coordinates to pixel values。 Okay， so if， if an。

 if this is my image is represented by a function， then if I input。



![](img/3ade99e91afc604146b08237908ca841_21.png)

![](img/3ade99e91afc604146b08237908ca841_22.png)

![](img/3ade99e91afc604146b08237908ca841_23.png)

![](img/3ade99e91afc604146b08237908ca841_24.png)

Any coordinates like 3，4， that function should return。 What are the RGB values at that。

 Maybe it's like 0。5，0。7 and 0。1。 Those are the RGB values at that。 Okay。

 so now the goal is to have this right here。

![](img/3ade99e91afc604146b08237908ca841_26.png)

Be a neural network where I have like a multilay perceptron。 And they。

 I think they always use like a five layer MlP。 So really simple neural networks。

 And you simply input。 So here you have two input neurons where this here goes。

 So one gets the 31 gets the4。 Then this travels through the network。 And at the end。

 the network should output 3 output nodes。 and this should be like the 05。7。1。Okay。Now。Again。

This network here。Is they now train this network to map input to output。 Okay。

 to map coordinates two values。 And this， of course， it it is one particular image。

 So you're gonna have one neural network per image Now you might reasonably ask why。

 why do we do it like this， right？ Why don't we just save the image as the pixel values。

 Why do we need like a function mapping the coordinates to the pixels。



![](img/3ade99e91afc604146b08237908ca841_28.png)

![](img/3ade99e91afc604146b08237908ca841_29.png)

And that's a valid question， I guess。 And the image is just one example of this。

 but one advantage that you immediately get is that now you have a continuous representation。

 So now you can not not only do you know because if you store an image like this。

You only know its value at each of the pixel locations。 However， if you store an image like this。

 you know its value at any continuous in betweent location， right， So you can ask the network。

 what's the pixelel value at 3。2 and 4。1 right it will give you an answer。

 And if the network is trained Well， it will give you sort of an answer that makes sense that is what's the exact color at this subpixel location right here。



![](img/3ade99e91afc604146b08237908ca841_31.png)

![](img/3ade99e91afc604146b08237908ca841_32.png)

Now。

![](img/3ade99e91afc604146b08237908ca841_34.png)

So far， so good， right， so。Essentially， this boils down to not really a machine learning problem in the classic sense。

 but an optimization problem， because all you have to do is you have to make the neural network match all input to all output。

 There' is not really a training and a test set right here。

 namely your data set is going to be all the pixels in the image。

 So each pixel in the image is going to be one data point because it's one so each pixel is X。

 Y2 R GB and the way they train these networks now at the examples of pixels。

 the way they train it they simply。

![](img/3ade99e91afc604146b08237908ca841_36.png)

![](img/3ade99e91afc604146b08237908ca841_37.png)

![](img/3ade99e91afc604146b08237908ca841_38.png)

![](img/3ade99e91afc604146b08237908ca841_39.png)

Sample a mini batch of pixels like this one， this one， this one， this one， this one。

They use that mini batch to train the network to do one step。To train the network。

 And then they sample another mini batch chance on， you might sample the same pixels multiple times。

 But ultimately， what you want is sort of a continuous representation of the image that there。

 this is not a new idea。 And this has been around。 and they cite a lot of literature where this has been around before。

 so。

![](img/3ade99e91afc604146b08237908ca841_41.png)

![](img/3ade99e91afc604146b08237908ca841_42.png)

![](img/3ade99e91afc604146b08237908ca841_43.png)

![](img/3ade99e91afc604146b08237908ca841_44.png)

What their new thing is is that they say these other representations。

 so if you use a neural network in a classic sense like this and you do your training with the mini batches like this。



![](img/3ade99e91afc604146b08237908ca841_46.png)

![](img/3ade99e91afc604146b08237908ca841_47.png)

What you'll end up with is a bad image。 So if you then if you then simply go right once you've trained the network。

 you can take it， take your network and you can simply output each pixel location， so you say okay。



![](img/3ade99e91afc604146b08237908ca841_49.png)

![](img/3ade99e91afc604146b08237908ca841_50.png)

Now I'm going to reproduce this image using my network because if it's trained， well。

 it it certainly give me back the positions at the pixels。 right， So you ask it， what's 0，0。

 What's 0，1， What's 0，2， What's 0 at 0，3。 And you can fill in the picture。

 And that usually gives you very bad outcomes。 or so they claim。 I mean。

 I haven't checked it particularly。 but you can see right here。 This is the ground truth。



![](img/3ade99e91afc604146b08237908ca841_52.png)

![](img/3ade99e91afc604146b08237908ca841_53.png)

And the here you have a network that is parameterized with relu functions。

 like with relu non nonlinearities。 And as you can see。

 the Relu network misses a lot of the sort of higher deficit。

