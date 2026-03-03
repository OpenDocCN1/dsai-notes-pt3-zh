# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p25 P25 CornerNet：通过成对关键点实现目标检测（论文详解） [BV1o3xLznExj_p25]

Hello there。 Today we're looking at Cornet detecting objects as paired key points by Hai Law and Jia Ding。

So on a high level， this paper detects objects in images。

 let's say this is an image and here's a chair， you know you have your chair。

And the way you detect the chair for this paper is going to be you detect the bottom right and the top left corners of the bounding box of the image。

 so rather than detecting the middle and then specifying height and width like we saw in the Facebook D ETR paper you detect the two corners and this paper goes through what they have to do to get this to work。

 including a new pooling method called corner pooling。



![](img/2fd4697559b15204a71d887157a61401_1.png)

So that's the digitist of the paper as always if you like content like this。

 consider subscribing and sharing it out to other people that would be very helpful so a commenter actually recommended this paper to me after I made a video on Facebook's DETR object detection pipeline I said something like okay since that paper always would detect the middle of the object and the height and width。



![](img/2fd4697559b15204a71d887157a61401_3.png)

![](img/2fd4697559b15204a71d887157a61401_4.png)

Couldn't you make something that else that detects the corners here and the corner here。

 and then that would define a bounding box just as well。



![](img/2fd4697559b15204a71d887157a61401_6.png)

And in the comments， and thank you very much for that。 I someone made point me to this paper。

 It's a bit older as you can see， but it's， I still think it's， it's pretty cool。😊。



![](img/2fd4697559b15204a71d887157a61401_8.png)

![](img/2fd4697559b15204a71d887157a61401_9.png)

So。We've already seen the problem like the problem isn't hard and it's detecting bounding boxes and images and in these data set。

 the problems， the difficult parts are that you sometimes have multiple objects like here if two humans they can be overlapping that can be of different sizes that could be like a third human like small back here。

 there can be other objects you don't know how many there are and so on so is it is a fairly complicated problem but as I already said the way that corner net here does this is by predicting the locations of the top left and bottom right corner there defining a bounding box and it does this independently So there's one network basically。



![](img/2fd4697559b15204a71d887157a61401_11.png)

![](img/2fd4697559b15204a71d887157a61401_12.png)

![](img/2fd4697559b15204a71d887157a61401_13.png)

That does the top left and one that does the bottom right。 and they are then combined。

 And at the end， they're sort of refined， I think。

![](img/2fd4697559b15204a71d887157a61401_15.png)

So。The architecture is pretty simple。 First， you put the image through a convnet。

 which is like a feature extractor so。This is the basic part。

 It was even the basic part of Facebook's D ETR pipeline。 First， you have some sort of convnet。

 Now they in this case use in this hourglass architecture that they described down down。



![](img/2fd4697559b15204a71d887157a61401_17.png)

Here， somewhere。And。

![](img/2fd4697559b15204a71d887157a61401_19.png)

This basically compresses the image into a smaller resolution I would take that image and compress it down to very small resolution。

 but many， many channels， so it's sort of forced to learn a global semantic representation and then it ups samplesles the image again and downs samplesamples it again and it up samplesamples it again through So at each of these steps there are many convolutional layers right here。



![](img/2fd4697559b15204a71d887157a61401_21.png)

And because that would lose you too much space like local information。

 there are skip connections built in between pairs of layers where information can travel without computation。

 Basically， So this is this is fairly standard architecture right here。

 But then after this hourglass CNN。

![](img/2fd4697559b15204a71d887157a61401_23.png)

![](img/2fd4697559b15204a71d887157a61401_24.png)

![](img/2fd4697559b15204a71d887157a61401_25.png)

You get to these prediction modules now let me switch back to the top drawing。Ultimately。

 what you want as an output of these prediction modules is two things。 So first of all。

 you want these heat maps sorry and these heat maps will simply tell you where are the corners。



![](img/2fd4697559b15204a71d887157a61401_27.png)

Now， the heat maps， their dimensions are the height of the image。Sorry， the height here。H， come on。

And the width of the image。this here would be the number of classes C okay so you have one channel for each of the classes that you predict and the heat map will basically be very high at the location and channel where there is a corner of that So you see have one heat map for the top left corners and one heat map for the bottom right corners and then also what you want to predict are these embeddings now simply because you have you know I said there can be multiple instances of the same class in in the same image so now you have in this case。

 particular case you are going even if you predict absolutely correctly you predict two top left corners and two bottom right corners Now this isn't particularly hard because there is only one configuration that can possibly be。

 but there could be situations where there are multiple and。



![](img/2fd4697559b15204a71d887157a61401_29.png)

![](img/2fd4697559b15204a71d887157a61401_30.png)

![](img/2fd4697559b15204a71d887157a61401_31.png)

AndThat's why you need to somehow match these corners。 You have to match。

 You have to know which ones of those are the same objects。

 And they do this by a second output in their heads called this embeddings。 Now these embeddings。



![](img/2fd4697559b15204a71d887157a61401_33.png)

They're simply vectors。 and the only thing that they're asked to do is they're asked to have a large inner product whenever they belong to the same object and they are asked to have a small inner product。

 sorry when when they're， when they belong to the different。To different。Objects。

 so this orange thing here would have a large inner product with this green bottom right corner embedding。

 so you train these embeddings。 they don't need to mean anything。

 You simply train them to predict the same thing for the same objects and different things for different objects。

So after that， when you match the corners， you can simply go over， you can say， a this。

 which one of these two right here has the larger inner product or you can do like some Hungarian matching and maximize the total inner product or something like this。

This was quite surprising to me that it works， but it's based on a line of research that is already has already established that this can work because。



![](img/2fd4697559b15204a71d887157a61401_35.png)

Ultimately， these things， these two pipelines do not really communicate。

 right So I'm going to guess what they learn is sort of a a sort of a descriptor of of the actual object that's there because if both describe the object that that's there with their embeddings。

 their embeddings are going have a large inner product。 And if they describe different objects。

 then their embeddings are not gonna match， right So even though you train this objective。

 I still think that these embeddings would pick up something about the object。

 something about the visual characteristics of the objects。

 will be very interesting to see whether someone could actually parse out what they what they do because。



![](img/2fd4697559b15204a71d887157a61401_37.png)

![](img/2fd4697559b15204a71d887157a61401_38.png)

![](img/2fd4697559b15204a71d887157a61401_39.png)

![](img/2fd4697559b15204a71d887157a61401_40.png)

It's almost impossible otherwise， for these things to be learnable。



![](img/2fd4697559b15204a71d887157a61401_42.png)

Alright， so that's that's the goal right here。 we want to get these heat maps in these embeddings and the way you do it is fairly easy architecturally。

 you have these two prediction modules， one for top left and one for bottom right and each of them have three outputs。

 the heat maps， the embeddings and here the offsets are simply a way for you to deal with the fact that you downs and by down sampling you have to round certain pixels to certain locations and then the offsets they compensate for this。

 but I don't want to focus on these right now。

![](img/2fd4697559b15204a71d887157a61401_44.png)

![](img/2fd4697559b15204a71d887157a61401_45.png)

So you simply have these two outputs right here。Now we'll look at corner pooling in a second。



![](img/2fd4697559b15204a71d887157a61401_47.png)

How do you train this， So you can now say， okay， if I have a picture like this， there。

 there is exactly two locations in the class human where the。The top left corner is correct。

 And that's right here。 And that's right here。 Okay， so two locations。 So I fill， I make my matrix。

 my target matrix with a one here and the one here and 0s everywhere else。 All right，0，0，0，0，0，0，0，0。

 And I train my network to give me this particular thing as an output for these heat for this heat map in the channel。

 human。This this might work， but it is more profitable， let's say if you allow for some slack。

 so what they say is， you know， since if if I'm anywhere within this orange circle right here with my prediction my resulting bounding box is still going to overlap fairly well with the ground truth。

 bounding box and the the accuracy measures for these things I think are based on how much you overlap with the ground truth bounding boxes so。

What they do， basically， is they。They give， they put a one in the spot。

