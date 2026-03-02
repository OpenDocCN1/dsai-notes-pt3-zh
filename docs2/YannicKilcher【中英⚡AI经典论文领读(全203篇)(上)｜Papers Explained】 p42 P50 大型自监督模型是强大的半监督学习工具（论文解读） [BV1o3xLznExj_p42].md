# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p42 P50 大型自监督模型是强大的半监督学习工具（论文解读） [BV1o3xLznExj_p42]

Hi there。 Today， we'll look at big selfsupervised models are strong semisupervised learners by Ting Cheen。

 Simon Cornlith， Kevin Swarski， Mohammamed Nuusi and Jeffrey Hinton of Google brainin。

 So this paper on a high level， It's also known as Scl V2 demonstrates that if you want to do semisupervised learning that youre very well served by starting out with selfsupervised learning and then doing fine tuning much like NLP models do。

 rather than the kind of semisupervised approach that image image tasks had so far。

 and they present this same clear V2， which is an improvement over the S clear approach to self-supervised pretraining。

 and they demonstrate it outperforms a lot of the baselines。 Allright。

 so if you like content like this， don't forget to share it out and leave a like and tell me what you think。



![](img/0e59df76c5a21fe4db98c8d06692f498_1.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_2.png)

In the comments。 So this paper。It sort of is kind of a club together thing of different of different things。

 So they present this new method like this Scle V2。

 which is a modification of Simcl and will go over that。

 but they also try to make like a and a scientific claim namely that the that somehow bigger models are better for this pathway of learning and will try to untangle all of these things。

 So first of all， we're in the semi supervised learning regime right here。

 semi supervised basically means that you have a data set。



![](img/0e59df76c5a21fe4db98c8d06692f498_4.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_5.png)

And。You only have labels for a part of that dataset。

 So this could be like here the bottom 10% or so because labels might be expensive to get And so you only have a few of them。

 but you have much more data that's unlabeled Now sometimes this problem is formulated as this here is your data And then this here is like a different data。

 but one that's close enough such that you can learn from it。

 And that's usually in NLP you'll have your data is like a sentiment classification task but you have all of Wikipedia that is not labeled。

 but it's just text so you can sort of pretrain on it。

 in this case will be in a situation where will artificially construct a small dataset。

 So this entire thing here is going to be the imagenet dataset and this right here is going to be our labelbeled portion like we have labels Now usually one has label。

For imagenet as well。 but we artificially restrict ourselves to simulate a situation where we have lots of data。

 and we only have a fixed budget。 So we can only because to obtain labels。

 oftentimes you have to ask humans to label images。

 And let's say we are a company and we've collected this big data。

 but we only have like maybe 500 bucks on Amazon mechanical Turk。

 and we only manage to get a very like1% of our data labeled。

 Now we're in the in the regime of semiupvised learning。

This is slightly different from what NLP does and as I said。

 in NLP usually assume you have different data sets， the large one being a different distribution。

 and in this semi supervised regime you often assume that it is actually the same data distribution。

 but you only have labels for some of them， but there should be a fair bit of overlap between the two things。



![](img/0e59df76c5a21fe4db98c8d06692f498_7.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_8.png)

So I've recently made a video about Open AI's image GPT that kind of goes into the same direction as this work right here that basically says pretrain on unlabeled data。

 like this whole data set without the labels。Can be a very good preconditioner for fine tuning later。

 And this paper says the same thing。 So basically。

![](img/0e59df76c5a21fe4db98c8d06692f498_10.png)

In， in the good old days， what you would do is you would devise a method that somehow takes。

 you know， takes in。

![](img/0e59df76c5a21fe4db98c8d06692f498_12.png)

devise a method that takes in a mini batch。 and in the mini batch， you'd have your data samples。

 And then some of them would be labeled right here， you'd have a why and here you'd have a why。

 But most of them would be not labeled And you'd have like some sort of loss function that would put special weight on the ones that are labeled or somehow handle these ones that are unlabeled in a way。

 you might be doing like some sort of a consistency loss。

 such that if they are very nearest near neighbors to these in the feature space。

 they should have similar labels or things like this。 So these semi supervised method。

 They basically try to solve the problem at once while taking data that is labeled and not labeled。

 This paper goes into a different direction。 This paper says first， we should。

 it's actually three stages right here。 And they have a diagram。 So I don't need to draw。



![](img/0e59df76c5a21fe4db98c8d06692f498_14.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_15.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_16.png)

They have a three stage approach， three stages。 The one on the left is unsupervised pre training。

 So they say let's forget about the labels right now。 even like your unlabeled data。

 So even the data where we have the labels， let's forget about the labels。

 and let's just do unsupervised pre training。

![](img/0e59df76c5a21fe4db98c8d06692f498_18.png)

Now， unsupervised pre training in this kind of setting is also known as selfsupvised pretrain and this first stage is done using a contrastive loss。

 and that's very similar to Simcl to this contrastive loss so what you'll do and they describe it very。

 very well here。

![](img/0e59df76c5a21fe4db98c8d06692f498_20.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_21.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_22.png)

So what you'll do is given a randomly sampled mini batch of images。

 each image is augmented twice using random crop color distortion and Gaussian blur。

 creating two views of the same example so you have an image in your mini batch each image you take and you make two versions of it and each version you crop real random crop somewhere so version 1 could be random cropped here。

 version2 could be random cropped here。And then you put some Gaussian blur on it and so on。

 So a little bit of， as you can see， random crop color distortion， Gaussian blur。

So what you'll want is two different versions of the same image。

 Each of these versions has been augmented in a different way， cropped in a different way。

 blurred in a different way。 such it's， it's two slightly different versions of the same image。

 And now you want to enforce。 you want to put this through。Your network。



![](img/0e59df76c5a21fe4db98c8d06692f498_24.png)

So ultimately， as you can see on the right side here， what you want to end up is a。A network。

 And then okay， we'll forget about this right now。What you want to train is this network right here。

 actually， including these projection layers。 We'll get to them later。

 This is the network that you want to train。 So you want to put， you take your unlabeled data。

 you take an image， youd make two versions of it。And you put those through the network， right。

 until the end right here。 So you'll get Z 1， Z2。 These are the。



![](img/0e59df76c5a21fe4db98c8d06692f498_26.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_27.png)

The output of the network for the two images。 And then what you want to do is you want to take another image that's not this image。



![](img/0e59df76c5a21fe4db98c8d06692f498_29.png)

And also put it through the network， maybe also augmented first。 and then you have Z3。

 So now you have the outputs of two things that are supposed to come from the same image and one thing that's supposed to come from a different image。

 And now your loss is simply going to be make those two things close together。



![](img/0e59df76c5a21fe4db98c8d06692f498_31.png)

And push those two things apart or those three， actually。



![](img/0e59df76c5a21fe4db98c8d06692f498_33.png)

So the loss and this is this is the contrastive loss of selfsupervised learning as you know you don't need any labels right here。

 you simply say the things that come from the same image should be close together and the things that come from different images should be far apart and this relies heavily on these data augmentations that you do right here。



![](img/0e59df76c5a21fe4db98c8d06692f498_35.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_36.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_37.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_38.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_39.png)

They also employ some other tricks like the momentum encoder from moco from momentum contrast and so on。

 but this is the main the main part。 So you can pull a lot of strings here to get like another percent of performance。

 but ultimately they won't see the similarity of。

![](img/0e59df76c5a21fe4db98c8d06692f498_41.png)

Z， I and Z， J， which are the outputs of the same image to be close together。 and then。This down here。

 they want to be far apart Z with ZK， where K is all the other images。



![](img/0e59df76c5a21fe4db98c8d06692f498_43.png)

Okay。You can do this in a mini batch fashion。 So this is self supervised learning。

 And the reason why you do this is you don't need labels and it tends， we know it tends to give very。

 very good representations。 So oh I'm past that。So what this network here will learn will be very good records for some reason。

 we still don't exactly know why combining augmentation with these self superupvised loss with contrastive loss。

 for example， gives such good performance， there have been papers recently that modify the loss and so on。

 but it's not super well understood it， but if you do it like this the network here will give you already very。



![](img/0e59df76c5a21fe4db98c8d06692f498_45.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_46.png)

![](img/0e59df76c5a21fe4db98c8d06692f498_47.png)