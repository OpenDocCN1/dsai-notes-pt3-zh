# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p74 P95 Axial-DeepLab：基于纯轴向注意力机制的全景分割（论文解读） [BV1o3xLznExj_p74]

Transformers are quickly coming for your favorite models。 Yesterday， they replaced LSTMs in NLP。

 They used to be good at NLP。 but v we now have transformers。 Think again。 today。

 we're going to see that maybe in the near future， Transformers will replace convolutions in image processing。

 So this paper is a step in towards this direction。 You just wonder， what is it going to be tomorrow。

 Maybe linear regression is going to be replaced just by giant transformers trained on 5000 Tpus。

 Who knows， well see。😊，In any case， we're looking at Axial DeepLb standalone axial attention for Pan optic segmentation by Hoiyuwang。

 Yukon chu， Bradley Green， Hartwickig Adam， Alan Yu and Liang Chiie Chen of John Hopkins University and Google research so this paper combines a bunch of techniques that have been introduced recently to deal with attention in problems where you would traditionally use a convolution。

So in this particular case， they deal with this problem of pan optic segmentation。

 which basically you'll see you'll get an image and there's a bunch of stuff on the image like a cat here。

And。A house right here。 And you're supposed to color the pixels of the same object， the same。

 So you you busy all these pixels here are house。 and then all these pixels。

 these pixels right here are cat and so on。 And then there's also the background。

 So all these pixels right here。 I know， beautiful， beautiful， beautiful， our background。

 So for this problem。

![](img/8b0cd6b92286db6a789361ff3f6e71cb_1.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_2.png)

It's kind of important that there you you， you are very precise， first of all。 So you can look at。

 you know， pixels or clusters of pixels and also that you take long range dependencies into account because if you。

 for example， recognize that this is a house and you recognize that here's a wall right here。

 you might be able to much better classify what is wall over here and what isn't。 Okay。

 so the kind of long range dependencies play a role in these problems across images and。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_4.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_5.png)

Usually attention mechanisms are pretty good for these long range dependencies。

 but they're also expensive and that's what this paper deals with。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_7.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_8.png)

They use this axial attention that has been introduced for exactly resolving this problem in types of data like images or higher order tensors and they also combine this together with learned positional encodings。

 which we've also seen time and time again throughout the kind of transformer and attention literature So the combination of axial attention。

 these learned positional embeddings allows them to replace the resnet backbone that usually is found in panoptic segmentation models with with a standalone attention。

 So they build models that are partial replace the convolutions with attention modules or replace them entirely。

 So the entire model is going to be just and attention models。 So no more convolutions in it。

 and they perform pretty well in classic tasks like they they test on imagenet Class。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_10.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_11.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_12.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_13.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_14.png)

They performed pretty well and they achieve state of the art on some of these segmentation tasks so we'll go through the model right here。

 this is a very very extensive paper in terms of experimental evaluation what I want to get into is mainly how the method works and show you what their model looks like so we'll go through it and as always let me know what you think in the comments and tell me if you like it or not share it out if you did。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_16.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_17.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_18.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_19.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_20.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_21.png)

Alright， so they go over a very long list of prior work， which is， you know， pretty， pretty cool。

 And here they say their contributions。 So their contributions are fourfold。😊。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_23.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_24.png)

First of all。The proposed method is the first attempt to build standalone attention models with larger。

 large or a global receptive field。 And we'll see what that means。

 We propose position sensitive attention layer that makes better use of positional information without adding much computational cost。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_26.png)

We show that axial attention works well not only as a standalone model on image classification。

 but also as a backbone on pan optic segmentation， instant segmentation and semantic segmentation。

Maybe what I did before described before was instance or semantic segmentation and not panoptic segmentation excuse me if that's the case。

 As you can see it can be used for various image tasks。Lastly。

 our Axial deep lab improved significantly over bottom up state of the art on Coco。

 achieving comparable performance of two stage methods。

 we also surpassed previous state of the art methods on mepiy vistas and cityscapes。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_28.png)

So these are various tasks， as I said and also what they don't mention here is that they perform fairly well on INe。

 in fact， in the abstract， they formulate this as。

![](img/8b0cd6b92286db6a789361ff3f6e71cb_30.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_31.png)

In particular our model outperforms all existing standalone self attention models on imagenet like that's you know that's a way to phrase it。

 you just exclude all of the other models until you're the best outperforms all existing standalone self attention models on imagenet yeah I mean。

😊，That's good。

![](img/8b0cd6b92286db6a789361ff3f6e71cb_33.png)

I mean there's something to be said of comparing apples to apples。

 but you can also you can also go overboard if you want to make your work look as good as possible。

 of course you know everyone everyone does that and there's no particular shame in it。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_35.png)

Okay， so。If we we're going to build up our model right here。

 and the basic element of this model is going to be this self attention mechanism。 Now， very quickly。

 because I know you all know what it is， but very quickly。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_37.png)

![](img/8b0cd6b92286db6a789361ff3f6e71cb_38.png)

You want to perform this action right here。Over a region right here。 So there is always a query。

And now the subscripts here are going to be important in this paper。 Okay。

 so the query is at a given position， position O。 And you can see that's the O right here。

 That's the， I'm going to call it the output。 I guess that's what they said as well。

 So the output position。

![](img/8b0cd6b92286db6a789361ff3f6e71cb_40.png)

You want to go over all of the input positions， and you want to aggregate。

Data from all of the input positions。 So that's right here。

 And how do you aggregate data by this softmax operator right here。

 And you can see the key also has a P right here。 and the softmax is over the axis of P。

 So in particular case of the image， what does that mean if you have an image。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_42.png)

Right here， it's made into pixels。 Okay， so you have pixels。 now， a transformer or， in generally。

 these attention models， What you can imagine is they always transform。

A data point into a data point of the same dimensions。 Now， this doesn't have to be。 actually。

 And I think one of the developments that is going to come in coming years or months or weeks。

 Maybe someone's already doing it is， in fact， to play more with this， with this。

Arbitrary constraint that we're imposing on ourselves。

 because it's not really clear that this is the best thing。 But for now。

 a attention layer is always transforming。A data point here。

 a 4 by4 image into a data point of the same size。 also a 4 by four image right here。Now this is。

 as I said， this is quite simplified， but it is true in NLP where we always transform our whatever 512 sequence toeken sequence into a 512 toeken sequence and it is true here。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_44.png)

Now， the output is going to be here on the right and。The question always is， okay。

 so I'll go over these these pixels right here。 and for every pixel， let's say for this pixel。

 I'm going to ask what data goes there， What's the output of the layer at that particular pixel。

And the output of the layer is going to be somehow dependent on， on the input right here。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_46.png)

Now， if you know classic convolutional models， what the classic convolutional model says。

 the output of this is going to be。Depenent on this region right here。

 if it's like a three by three filter。 Okay， so you have this convolutional filter。

 and that means that blue dot on the right is going to pay attention to you know。

 its own location in the input plus everything around it。 Okay。

 and then every single data point here is going to do that。 So， for example。

 this screen data point is going to pay attention to this region right here。 Now。

 there' is a border so there's maybe some padding， but。The question is always。

 where does the information come from and how is it aggregated， Okay， in a convolution layer。

 what happens in a convolution layer， in a convolution layer， you simply have your filter， right。



![](img/8b0cd6b92286db6a789361ff3f6e71cb_48.png)