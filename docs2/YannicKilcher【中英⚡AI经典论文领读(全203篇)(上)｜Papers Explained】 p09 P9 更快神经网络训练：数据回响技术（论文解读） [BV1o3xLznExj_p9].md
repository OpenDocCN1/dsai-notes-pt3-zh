# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p09 P9 更快神经网络训练：数据回响技术（论文解读） [BV1o3xLznExj_p9]

Hi there。 Today we're looking at faster neural network training with data echoing by Dmmi Choi。

 Alexander Paso， Christopher J。 Shau and George E。 Doll So on a high level this paper basically says you should repeat data that's already in memory in order to speed up the entire process of neural network training and it also says that this can speed up your wall time without hurting your performance too much and I have mixed feelings about it。

 so let's jump in So they basically make a point of saying that machine learning doesn't happen in just one thing it's not like SK learned do fit anymore it is more of a pipeline So what do we mean by this if you have if you think of something like you want to train an imagenet model What you want to do is you have like your data somewhere and that could be。



![](img/2dc39765caa7640976d0961a70ff7d9b_1.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_2.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_3.png)

On in a database， it could be in the network somewhere。

 So if you have even something larger than Inet， you'll probably store it on a central server on an Amazon bucket somewhere。

 So this is in AWS。 And the first thing you actually need to do is you need to read that dataset。

 Now usually you're not gonna to have enough memory on a machine to just load in the entire data set into memory。

 So that means this process here is streaming。So this is continuously streaming data points。

 and once you have used the data points， you're going to throw it away because you need space for the next one right and so the streaming is done continuously。

 The next process is read and decode that means you have to you know read it from the network and actually bring it into a format where you can use it usually something like anump array or a tensorflow tensor。



![](img/2dc39765caa7640976d0961a70ff7d9b_5.png)

嗯。You need to apply some shuffling because usually the order。

 you can't really trust the order that it is stored in。

 Oftentimes there is like a bias in the ordering。 So you need some sort of a shuffle buffer here。

 Then often you wan to apply some data augmentation to it。 That means that you have one image。



![](img/2dc39765caa7640976d0961a70ff7d9b_7.png)

And we know for these models if this is your cat， we know for these models that what can help is to basically make many。

 many different images from one image。 So this could be by cropping part of it and saying， well。

 if it was a cat before the small upper right part here is still a cat。

 So this is one it's called data augmentation。 And you're gonna apply a whole bunch of these things。

 So you can crop。 you can rotate the image a bit。 It's still a cat right and you can also change its luminance and a bit of its colors。

 you can jit the colors。 you can horizontally flip it and it'll still be a cat。

 And that's basically how you make many data points from one data point。 And we know that helps。



![](img/2dc39765caa7640976d0961a70ff7d9b_9.png)

Then what you want to do is you want to batch this data so you want to put it into mini batches since you've shuffled here。

 that means when the next time the same data point comes along。

 it's going to be batched with a different with a different group of images and of course augmented differently with a different group of images and that basically means it's a different training batch for the model So this entire pipeline is basically away that we take data points that we have and we make a whole bunch of variations and various groupings and batchings of it and we know that helps enormously with the generalization capability of your final models and then here you do your apply your SGD update so that's usually where you forward propagate your data through your network which here is F。



![](img/2dc39765caa7640976d0961a70ff7d9b_11.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_12.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_13.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_14.png)

It'll get like some Y hat as an output， and then you have your labels that also come through the pipeline and you have some sort of loss function L。

That takes both as an input and gives you an output。 And then you do your back propagation。

 So the back propagation。Would go through your loss function through your network and update the network parameters。

Such that your network learns something， right？

![](img/2dc39765caa7640976d0961a70ff7d9b_16.png)

Now this step to the right here is usually what we focus on when we do deep learning。

The step on the right here。

![](img/2dc39765caa7640976d0961a70ff7d9b_18.png)

All of this。This can be done on a GPU or is usually done on something like a GPU or a TU。Right。



![](img/2dc39765caa7640976d0961a70ff7d9b_20.png)

But in。These things are getting faster and faster。 The point the paper makes is that the TUus and GPUus of the world are getting faster。

 but this entire other thing right here， this is basically CPU land。 Now。

 I know there is some data augmentation now happening on the GPU and so on。 but in in essence。

 you can think of a pipeline where the thing to the left is happening on CPU and the thing to the right is happening on TU and even even worse。

 let's say the speed is continuously。

![](img/2dc39765caa7640976d0961a70ff7d9b_22.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_23.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_24.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_25.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_26.png)

Is continuously increasing。 So in your pipeline， the kind of speed would be。

So here is the network reading。And here over here is the GPU SGD step。And this is speed。



![](img/2dc39765caa7640976d0961a70ff7d9b_28.png)

Basically， the further to the right in your pipeline you go， faster the faster your hardware gets。

 and that means that。

![](img/2dc39765caa7640976d0961a70ff7d9b_30.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_31.png)

If， if this since this is a continuous pipeline， right。

 that basically means that if I input something here。It goes through the pipeline。

 And even if this is all running in parallel at this thing over here is going to idle。This。

 since this is the fastest part of the pipeline， it is going to just idle a lot。



![](img/2dc39765caa7640976d0961a70ff7d9b_33.png)

Right because because it can only consume things as fast as this thing can produce Now if you if you have some sort of a multi GPU machine and just train imagenet like you just around the code。

 usually your this is not the bottleneck， usually your GPUs here are at 100% capacity so this paper is not for you but if you are let's say a big company have this network storage。

 have a big data set have very expensive data augmentation this happens for example this can happen in NLP and so on。



![](img/2dc39765caa7640976d0961a70ff7d9b_35.png)

This can be quite your situation where the earlier in the pipeline， the slower it is。



![](img/2dc39765caa7640976d0961a70ff7d9b_37.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_38.png)

And don't you just love these graphics， so。Here's， here's time。And apparently。

 it goes in both directions。 And so does it go like this， I。

 I think what they mean is just time goes in this direction， and you're here and。Your're upstream。

So your upstream is your network， this is your network reading or your pre processing。

 and the downstream this is the GPU。So as you are pre processing things， you， you。And this should be。

 this should be different。It should me， okay。To correct this right here， this is idle。

And this is running。So as your upstream processes images right at the beginning， your GPU is idle。

 but then as soon as it ships off the first batch of images。

 your GPU can run now now it's running while you're doing that， your upstream。

 your network is still reading new images preprocessing them and so on。

 but it cannot is too slow to insert a batch at the time that the GPU is done the time the GPU is done。

 it's still processing this batch so the GPU is idle。Until here。

 where it finally manages to process that batch and then the GPU is running again。

 I think that would have been a much better graphic， but， you know。



![](img/2dc39765caa7640976d0961a70ff7d9b_40.png)

So their goal basically is。

![](img/2dc39765caa7640976d0961a70ff7d9b_42.png)

That what you'll have。Is right here， for example， after the batch。

 What you'll do is you scrap this connection。You take this and you put it into a smaller buffer。

And the buffer here is a repeat buffer。 So what it does is it simply will repeat。

The whatever you have in the buffer until something new comes in， right， so new data point comes in。

 you just output that data point again， again， again， again。The for the GPU。

 it's gonna feel like these are all new batches and they continuously come in。

 but it's always the same until the next data point comes in and then you output that one again and again and again and again。

 Now the the actual factor here， you can， of course。

 tune by hand or you can just say repeat until something else comes in。



![](img/2dc39765caa7640976d0961a70ff7d9b_44.png)

In this paper， they have an explicit factor where they say we repeat each data point four times or three times or so on。

 So this is data echoing。 You basically echo the data point multiple times。



![](img/2dc39765caa7640976d0961a70ff7d9b_46.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_47.png)

![](img/2dc39765caa7640976d0961a70ff7d9b_48.png)

And。This can be done in various places， so they experiment with echoing in any of these places right here。

 So they they experiment with it right here after reading and decoding after shuffling。



![](img/2dc39765caa7640976d0961a70ff7d9b_50.png)

No， I think。Always before a shuffle。