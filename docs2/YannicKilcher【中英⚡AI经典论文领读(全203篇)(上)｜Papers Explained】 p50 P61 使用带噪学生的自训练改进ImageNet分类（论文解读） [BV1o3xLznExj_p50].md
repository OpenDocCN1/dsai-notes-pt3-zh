# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p50 P61 使用带噪学生的自训练改进ImageNet分类（论文解读） [BV1o3xLznExj_p50]

Hi there。 Today we'll look at self training with Noisy student Is Inet classification by Chi Z Siia。

 Min Tan Longong， Edward Hovey and Kk V Li。So this paper takes an Inet classifier that's been trained on the Inet dataset set and uses that classifier as a teacher model to label a whole bunch of unlabeled images and then it trains a student model that is larger than the original teacher model on those teacher labelbeled images and that turns out to improve the classification on the Inet validation set now that there is a couple of things that make this all work。

And today， we're going to explore how this paper does it and what they say is important。



![](img/174fe2ec0e22df6931d8853c6997e99e_1.png)

If you enjoy content like this as always， don't hesitate to share it out or tell your friends about it and if you're not subscribed yet then do so I would appreciate that and you'll get more content so win win。

So this， this paper is about semi supervised learning in。In effect， so it's at the intersection。

 actually， of semi supervised learning， knowledge， distillation and transfer learning。

 So what do we mean by semi semi supervised learning， Usually in supervised learning。

 you'll have some sort of data set。 and the dataset set will contain。 let's say it's an image net。

 It's image dataset set。 So the dataset set will contain images。

 This is an image with like some sort of cat on it。 And。It will contain the labels according to that。

 so cat。Now， in semiupvised learning， you， you assume that so this is supervised learning In semisvised learning。

 you assume that only part of your dataset has the labels。

 So like only this part down here has the labels and the upper part does not have the labels。

 So that's semi supervised learning。 it's often the case when it's very expensive to get labels。

 so you can only get labels for a couple of images in your dataset。

 but very often in semiservised learning， you still assume it's the same dataset set。

 There is a slightly different set up here， that's called transfer learning。



![](img/174fe2ec0e22df6931d8853c6997e99e_3.png)

So in transfer learning， what you'll have is you'll have your dataset set that has the labels。

 but it's very small。 So you'll notice I've drawn it smaller。 That means you have very little。

 That is also the case when it's very expensive to get labels。

 but also it's expensive to get the data itself。 This is often the case。

 like say in medical data where not only is it expensive to get labels for like a C T scan。

 It's actually expensive to get the C T scan。

![](img/174fe2ec0e22df6931d8853c6997e99e_5.png)

So what the goal in transfer learning is is to say， well， I do I do have only this small dataset set。

 but I do have this giant other data set over here。

 Now can't I it's not the same Its maybe they're not C these are C scans。

 Maybe these are xrays right they're fairly similar similar technology if you slice the CT It'll give you sort of an xray。

 can't I you know train my model pretrain my model on xray data and then fine tune it on the CT data。



![](img/174fe2ec0e22df6931d8853c6997e99e_7.png)

So that's called transfer learning。 usually。 Now， this can be done with or without labels。

 So it can be that for the X ray data set， you do have the labels or you don't have the labels。

 There are techniques for all of those now。

![](img/174fe2ec0e22df6931d8853c6997e99e_9.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_10.png)

What we're going to look at today is kind of this situation right here。

 It's the transfer learning situation where you do not have the labels for。



![](img/174fe2ec0e22df6931d8853c6997e99e_12.png)

This X ray dataset set。 But other than in this X ray example。

 what we're going to look at is the small data set is going to be our imagenet database。

 So our original。

![](img/174fe2ec0e22df6931d8853c6997e99e_14.png)

Picture with label database。 So you'll see immediately the difference here is that in the transfer learning setting。

 we usually assume that the data set we want a train on is fairly small here， you know。

 imagenet is already sable。

![](img/174fe2ec0e22df6931d8853c6997e99e_16.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_17.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_18.png)

But what we have is we have a much larger database of unlabeled images that we can just get from the internet so we can scrape the internet for any kind of pictures。

 and that will be our unlabeled dataset and what we'll try to do is somehow incorporate this unlabeled dataset here into the training process to get better on the Inet dataset。



![](img/174fe2ec0e22df6931d8853c6997e99e_20.png)

Okay so this is the problem statement is you have the Inet dataset and you have a second much larger dataset set of unlabeled images and you somehow want to make use of them。

 so I hope you see how this is sort of connected to the others it's essentially sort of a transfer semiupvised learning setting but with the exception that usually in transfer learning you assume that the labeled dataset is like super small which is not the case here and that's going to result in us being able to apply a different technique so this different technique is called the noisy student。



![](img/174fe2ec0e22df6931d8853c6997e99e_22.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_23.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_24.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_25.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_26.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_27.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_28.png)

Now usually what you might do in a transfer learning setting is you might want to start with that big data set。

 right because that's the data that's sable enough to allow you to train a really big model on it and then you fine tune and you sort of hope that the information transfer is over。



![](img/174fe2ec0e22df6931d8853c6997e99e_30.png)

Here， on the other hand， what we want to do is we start with the Inet dataset set。

 So first we train this in a supervised learning fashion into our model。

 Now this model is going to be called the teacher model。



![](img/174fe2ec0e22df6931d8853c6997e99e_32.png)

We know how to do this。 We know how to train imagenet models， right。

 so we can train this into a teacher model that has a reasonable accuracy on the Inet dataset。

 Step two， we're going to take that big data over here and use the teacher model to label the unlabeled images。



![](img/174fe2ec0e22df6931d8853c6997e99e_34.png)

So for each image。

![](img/174fe2ec0e22df6931d8853c6997e99e_36.png)

For each image coming in here， the teacher。So maybe this is， again， another cat。

 The teacher will say， that's a cat。

![](img/174fe2ec0e22df6931d8853c6997e99e_38.png)

Okay， so that gives you the big data set。Where now you have images along with labels。

 just the labels aren't true labels they're generated by the teacher。



![](img/174fe2ec0e22df6931d8853c6997e99e_40.png)

And then in the third step。

![](img/174fe2ec0e22df6931d8853c6997e99e_42.png)

You train this big data set。

![](img/174fe2ec0e22df6931d8853c6997e99e_44.png)

You train on this big data set and that's what you call your student model。

 And then the student model in this paper will see how can we make it such that the student is then better at the original image at task than the teacher ever was which seems counterintuitive at first because all of the information that the student is trained from is basically what the teacher already knows right all the labels here come from the teacher。

 Therefore， the student shouldn't be able to outperform the teacher but in this case。

 the student will be able to outperform the teacher and their argument here is that this is mainly due to the fact that you use noise in this training procedure。

 So when。

![](img/174fe2ec0e22df6931d8853c6997e99e_46.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_47.png)

You train the student What you'll do is you'll use noise and one of the types of noise is that you severely augment this data right here in order to train the student now we've known for a long time that data augmentation for example。

 in the frameworks of self-supvised learning and so on can have a very large benefit to training and here the fact that we incorporate this extra data and we use noise and augmentations on it is going to result in a student that can sort of learn more about the data than then the teacher did know。



![](img/174fe2ec0e22df6931d8853c6997e99e_49.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_50.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_51.png)

Okay， this this is basically it。 and as you can see。

 this is kind of their main final results where they say on imagenet。

 our top one accuracy sort of increases right here and even on these kind of subsets of imagenet or these are sort of corrupted sets of imagenet。

 they make even more substantial improvements as you can see here now we'll go into what these corrupted subsets are。

 but you know just。

![](img/174fe2ec0e22df6931d8853c6997e99e_53.png)

For now， these here are very difficult variants of ImageNe。

 they can be severely corrupted or distorted and so on。

And you can see that the model improves severely over the previous state of the art。

 which basically means that this model is more robust， and that's a direct consequence of the noise。

 Now， one last thing I should say is that the student here is also larger than the teacher。

 So that's also one thing that makes the student better。

 So what you will make is the student model is larger than the teacher model as a model as the architecture。

 So in combination with the noise right here。

![](img/174fe2ec0e22df6931d8853c6997e99e_55.png)

![](img/174fe2ec0e22df6931d8853c6997e99e_56.png)

With the noise。In combination， that means the student model is probably able to capture more of the variance of the data。

 It's larger。 it has more parameters。 It can learn more about the data together with the noise。



![](img/174fe2ec0e22df6931d8853c6997e99e_58.png)

It can probably be more robust and that's what makes it generalized better。

 and we'll also see as we see here， it's more robust to these transformations and it's also going to be more robust to adversarial perturbations。



![](img/174fe2ec0e22df6931d8853c6997e99e_60.png)

So the technique。