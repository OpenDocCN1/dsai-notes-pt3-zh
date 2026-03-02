# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p60 P74 梯度起源网络（论文讲解与实时编程） [BV1o3xLznExj_p60]

Hi there Today we'll look at gradient origin networks by Sam Boon Taylor and Chris G。

 Wilcox of Durham University。 so on a high level this paper trains implicit representation networks。

 but not on single data points but on entire data set。

 it does so by using a latent encoding of each data point。

 and it doesn't obtain that encoding through an explicit enr。

 but by simply looking at the gradient of the latent variable when initialized at the origin。

So it's a bit of a weird formulation。 and I've seen this paper uploadvoed on Reddit and the top comments would would always say like。

 I don't really get it， I don't really get it。And I thought， you know， maybe I'm completely wrong。

 but I can just give my opinion kind of what's going on in this paper。 Now， also。

 most people on Reddit or a lot did say， I don't really get it。 but here is what I think is going on。

 And then listing something。 And that's theres where I， I stopped reading。

 So as to not be kind of as to form my own opinion。 I like to kind of understand papers by myself。

 So again， maybe I'm completely wrong。 But here is my opinion。



![](img/9a716e99b8ffbdca405713998d2a6237_1.png)

![](img/9a716e99b8ffbdca405713998d2a6237_2.png)

If you like opinions， hit the like button and subscribe if you aren't yet。 and yeah。

 share this video out， maybe that that helps someone else understand。

 So this paper is a very short paper。 It is four pages。



![](img/9a716e99b8ffbdca405713998d2a6237_4.png)

![](img/9a716e99b8ffbdca405713998d2a6237_5.png)

And it's a dense paper it definitely can warrant it definitely can warrant making a longer paper out of it。

 though that being said it's on archive paper for now。

 so you know there's nothing wrong with archiving kind of unfinished work。

 but we'll just going look at it and try to understand it okay so the abstract says this paper proposes a new type of implicit generative model that is able to quickly learn a latent representation without an explicit encoder。



![](img/9a716e99b8ffbdca405713998d2a6237_7.png)

![](img/9a716e99b8ffbdca405713998d2a6237_8.png)

![](img/9a716e99b8ffbdca405713998d2a6237_9.png)

![](img/9a716e99b8ffbdca405713998d2a6237_10.png)

![](img/9a716e99b8ffbdca405713998d2a6237_11.png)

![](img/9a716e99b8ffbdca405713998d2a6237_12.png)

So。For that， you need to know what an implicit generative model is。

 and I've covered one type of implicit generative model。

 specifically the type that theyre using here， what they're called siren。



![](img/9a716e99b8ffbdca405713998d2a6237_14.png)

So sirens are implicit representation networks， and I've made a video about sirens so if you don't know what that is。

 go look it up but very quickly。

![](img/9a716e99b8ffbdca405713998d2a6237_16.png)

![](img/9a716e99b8ffbdca405713998d2a6237_17.png)

A siren will is a neural network to represent a single data point。

 So each data point in a data is represented by its own neural network。 And the neural network。

 So this might be a bit foreign to you， but usually you have some kind of image right。

 and it's simply represented as an， as an array of RGB coordinates， right its。

 it's simply an array of this says like 10。5 and so on。 So all the pixels are in this array。

 This is the explicit representation of that data point。 now。



![](img/9a716e99b8ffbdca405713998d2a6237_19.png)

This here is a long list and it has some regularities to it so that's why you can also think of an implicit representation of the data point。

 the implicit representation works as follows you imagine again your image your image is made up of pixels and these pixels are on x and y coordinates so this pixel right here would be00 this pixel right here would be01 and so on a siren is or generally an implicit representation network is a network that takes in any x and y coordinate as the input so the input itself is the numerical x and y coordinate of that picture and it passes it through a neural network and out comes the RGB value。



![](img/9a716e99b8ffbdca405713998d2a6237_21.png)

![](img/9a716e99b8ffbdca405713998d2a6237_22.png)

Okay and so an entire picture is represented by this neural network。

 The neural network maps each coordinate to its RGB value and here you can see that these a single picture can become an entire data set for this neural network in fact it has to because for a different picture of course。

 there is a different mapping from x and y coordinates to RGB coordinates。

 but this allows you to do multiple things。 So first of all。

 this neural network can be smaller than the explicit representation。 Second of all。

 you can capture some regularity in the data specifically sirens have sine waves as non nonlinearities in the neural network here。

 which is also a bit special but lends itself very well to capture natural signals because natural signals are often you know repeated at different scales and derivatives of themselves and so on so。



![](img/9a716e99b8ffbdca405713998d2a6237_24.png)

I've covered this all in my video and also this allows you to have a continuous representation rather than a discrete representation like here you just have each pixel Now you have a continuous representation Allright。

 so these are implicit representation models or implicit generative models or these neural networks right here that map from coordinates to two colors Now what's the problem with this is as we said。

 you need one neural network per data point。

![](img/9a716e99b8ffbdca405713998d2a6237_26.png)

![](img/9a716e99b8ffbdca405713998d2a6237_27.png)

![](img/9a716e99b8ffbdca405713998d2a6237_28.png)

![](img/9a716e99b8ffbdca405713998d2a6237_29.png)

Now the idea that these people here go with is that can't we do kind of the same thing。

 but except we have one neural network per data point。

 we want to have the same neural network for the entire data set。

 so again they want to have a neural network that somehow outputs RGB coordinates。



![](img/9a716e99b8ffbdca405713998d2a6237_31.png)

But now it's not for a single image now we have a data set okay and the data set has many images like this is image I。

 this is image J， this is image K。 So what we could do is we could simply tell the neural network the x and Y coordinate that we where we would like the RGB values to know。



![](img/9a716e99b8ffbdca405713998d2a6237_33.png)

![](img/9a716e99b8ffbdca405713998d2a6237_34.png)

And we could also tell it which image it is， right？Or I or J。



![](img/9a716e99b8ffbdca405713998d2a6237_36.png)

And。This will give us a neural network right here that can represent the entire dataset set because it always can see。

 a， I want of image J， I want these in these X Y coordinate， it doesn't help you very much though。

 because it still has to learn for each image individually， how to encode it， how to produce it。



![](img/9a716e99b8ffbdca405713998d2a6237_38.png)

What's much more interesting is if you kind of mix this with the kind of old style。

 the kind of old style generative models， so in old style generative models， let's consider。

 for example， an auto encoder so in an auto encoder what you would do is you would take your image and you would put it through an encoder。



![](img/9a716e99b8ffbdca405713998d2a6237_40.png)

![](img/9a716e99b8ffbdca405713998d2a6237_41.png)

And this encoder will give you a latent variable zm。

 and then you would put it through a decoder again。And that would give you an image。

So your generative model now is this part right here。

 And this Z variable is your latent encoding of this data point。 Now。

 if you train these models correctly be this a， be this a an auto encoder or a variational auto enr or the green part can actually just be agan。

 right， if you train this correctly， then this Z right here will be sort of a。

 a latent encoding of the。

![](img/9a716e99b8ffbdca405713998d2a6237_43.png)

What the what of the information in the image itself Okay， and that can generalize。

 So now I can input a picture that the model has never seen during training。

 and the encoder will map it to a latent representation that sort of makes sense that is able to reconstruct。



![](img/9a716e99b8ffbdca405713998d2a6237_45.png)

The image that I've put in。Okay， so。TheYour hope with this latent representation is is that there is some kind of data manifold somewhere in hidden in the in the entire space of parameters。

 and as long as you're on that data manifold， you will produce a sensible data point and this is kind of a continuous and so on。

 so even though you've only seen a few during training， if you have a new one during testing。

 then you can。

![](img/9a716e99b8ffbdca405713998d2a6237_47.png)

![](img/9a716e99b8ffbdca405713998d2a6237_48.png)

![](img/9a716e99b8ffbdca405713998d2a6237_49.png)

Sort of it will be mapped to a correct place on the data manifold and it will produce a data point again。



![](img/9a716e99b8ffbdca405713998d2a6237_51.png)

And you've seen this right， you've seen these interpolations in GNs where you can interpolate in latent space and and so on。

 The problem here is that you know in so in GNs we sample these things right here。



![](img/9a716e99b8ffbdca405713998d2a6237_53.png)

![](img/9a716e99b8ffbdca405713998d2a6237_54.png)

So that's a different story。 but in VEs， we need this encoder or in autoenrs。

 We need this encoder to obtain a latent representation for a given data point in GNs。

 there is no way if we have an image， there is no way to obtain the corresponding Z variable。

 if we don't have an encoder and that's the the problem we're tackling right here。

 So here what we want to do is we want to give the x and Y。

 and we want to give the Z we say we have some way of obtaining a latent representation of one of the image right here And from that we want to generate the RGB variables。

 Now the question is。

![](img/9a716e99b8ffbdca405713998d2a6237_56.png)

![](img/9a716e99b8ffbdca405713998d2a6237_57.png)

![](img/9a716e99b8ffbdca405713998d2a6237_58.png)

Think of again， the question is， how do we obtain the Z variable without having access to the encoder？



![](img/9a716e99b8ffbdca405713998d2a6237_60.png)

And that's the problem of this paper， and this paper proposes a solution。

So they say this is achieved。