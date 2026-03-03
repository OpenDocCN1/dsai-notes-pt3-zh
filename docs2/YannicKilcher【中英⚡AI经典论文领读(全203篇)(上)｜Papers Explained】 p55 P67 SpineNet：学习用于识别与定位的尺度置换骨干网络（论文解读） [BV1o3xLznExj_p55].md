# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p55 P67 SpineNet：学习用于识别与定位的尺度置换骨干网络（论文解读） [BV1o3xLznExj_p55]

Hi there， Today we'll look at Spynet learning scale permed backbone for recognition and localization by Xian Zdu et al of Google Research on a high level this paper proposes to take current recognition and localization networks which have a CNN backbone。

 usually something like a Resnet and switch up the order of the blocks in the Resnet and crossconnect them in a different way。

 such that they reach a higher accuracy with the new network that has the same amount of parameters or almost the same amount of parameters。

 they then further modify this network， such that it reaches that higher accuracy with less compute than the original network。

So if you w to know how it's done， you know， stick around。

 you can help me by sharing out this video if you liked it， if you didn't like it。

 leave a comment and tell me what you didn't like。 Otherwise I have no chance of improving。

 So that's the deal okay。

![](img/4417873120e7a7cc79467a91ca85b91c_1.png)

![](img/4417873120e7a7cc79467a91ca85b91c_2.png)

Cool， so the task here is recognition and localization， as you can see here。

 which basically means that you have an image and there's stuff on the image。

 Maybe there's a cat right here。 and maybe there is some kind of a house right here。And the task。

 these tasks come in various forms。 but some of the tasks are to say what's on the image。

 So in this case， cat。And house。And also， where is it now this could be a point。

 this could be a bounding box， or this could actually be a pixel segmentation。

 all of this sort of tasks exists in various forms。

What usually is done in these tasks is you want to go in some way through a neural network and the neural network will output the same image again or the same shape。

 So it will output a image that is of the same shape that if this is your input image。I'm gonna。

I'm just going to quickly redraw without the labels。If this is your input image。

 then the output image， let's say we're doing bounding boxes。

 The output would say something like here are bounding boxes。 and also the output would be。cat。

And house。So these are the two outputs that the neural network would generate。

 This is some sort of a convolutional neural network because they deal with images fairly well。Now。

 usually when we do image processing and we know this from， for example， image classification。

 So if we just have image classification just to classify here。

 if we just want the output's cat or house or even just one single thing， like an imagenet。

Our convolutional neural networks have a particular architecture。

 namely what we do as we have the first convolutional neural first layers will take the image。And。

Run these convolutional filters across them。Which gives you the same shape image back。

 But then with time， we scale it down。 We have a max pooling or a convolution with stride2。

 so that the image is only this big anymore。 And then we have a bunch of further layers and then we scale it down again and so on。

 Now， as we scale it down， the number of channels goes up。 Of course， at the beginning。

 you have three channels for the three colors。 But then after the first convolution。

 you might have whatever 32 channels right here。 This is no longer the original image。 This now is。

 of course， for each pixel， you have a stack of features。 right。

 You have a stack of features right here。 because。That's what your convolutional layer does。

 And then when you scale it down， you have even more feature maps。

 So we tend to scale down the resolution of our feature maps。

 but we tend to increase the number of feature maps right here。

 the reasoning behind this is if you look at these bounding boxes， they they don't really。

 so not enough， sorry， if you look at the labels right here。



![](img/4417873120e7a7cc79467a91ca85b91c_4.png)

![](img/4417873120e7a7cc79467a91ca85b91c_5.png)

![](img/4417873120e7a7cc79467a91ca85b91c_6.png)

The fact that there is a cat on the image shouldn't depend on the exact pixel location of the cat。

 right， So even if I scale this down a bit， I'll still recognize that there is a cat somewhere。

 It can still aggregate that information。 In fact， I could deal with a single， right。

 I could deal with scaling this down successively up to a single pixel。

 And that's ultimately what an image classifier does。

 You simply have a single vector at the end with the features in it。 And from that you classify。



![](img/4417873120e7a7cc79467a91ca85b91c_8.png)

So the reasoning is that as you go through the network， you pick up the low level features first。

 like here， you pick up the edges and the kind of low level shapes as you go higher through the network。

 your features become more abstract but less localized。

 which means that it's less important where they are。

 And that's why you look at this image through a coser and coarser segmentation and at the end。

 your segmentation might be something like this。

![](img/4417873120e7a7cc79467a91ca85b91c_10.png)

![](img/4417873120e7a7cc79467a91ca85b91c_11.png)

![](img/4417873120e7a7cc79467a91ca85b91c_12.png)

![](img/4417873120e7a7cc79467a91ca85b91c_13.png)

![](img/4417873120e7a7cc79467a91ca85b91c_14.png)

Okay， so we， we have had a lot of success building image classifiers with this reasoning。

 And this is sort of a human heuristic that just has worked well， right now。



![](img/4417873120e7a7cc79467a91ca85b91c_16.png)

![](img/4417873120e7a7cc79467a91ca85b91c_17.png)

When we do something like this bounding box classification or even per pixel classification。

 all of a sudden， it is very important where the things are， right。

 It is very important that it's this pixel and this pixel and this pixel and this pixel forming the bounding box。

 because the more accurate you are， the better your bounding box classifier。

 you still have this right here， this recognition， but the localization part。



![](img/4417873120e7a7cc79467a91ca85b91c_19.png)

![](img/4417873120e7a7cc79467a91ca85b91c_20.png)

We can't just scale down anymore because we need to output something that's of the same size。

 So what people have done。

![](img/4417873120e7a7cc79467a91ca85b91c_22.png)

![](img/4417873120e7a7cc79467a91ca85b91c_23.png)

I they've gone from this kind of from a architecture that scales down because we know that works well。

 we know the downscaling works well， so we take that and then we scale up again。

And there is some reasoning behind this， right， so that's what we can do。

Because we know this part works very well for extracting high level features that are not that localized。

 so our reasoning is going to be something like， okay。

 we'll force the network through this kind of bottleneck right here。

 it will force it to learn some high level features because otherwise you can just you know kind of remember the individual pixels and that won't work as well。

 we'll force it to remember the high level will' force it to remember what a cat is and then it will help in the pixel segmentation to know what a cat is。

This is very valid assumption， but it doesn't need to be the case。

 And so there is one additional thing that these networks usually do is that they have like some skip connections here from the layers that are of the same size to the layers that are of the same size right here to here in order to kind of recover these high level features because if you only look at an image through the lens of this right here。

 and you you have to segment the ear of the cat。 you know。

 you can only either color an entire pixel or not。 So you want to gain back some of that some of those high level features and that's what you do with skip connections。

 And that's why these networks usually look like this。



![](img/4417873120e7a7cc79467a91ca85b91c_25.png)

![](img/4417873120e7a7cc79467a91ca85b91c_26.png)

![](img/4417873120e7a7cc79467a91ca85b91c_27.png)

![](img/4417873120e7a7cc79467a91ca85b91c_28.png)

![](img/4417873120e7a7cc79467a91ca85b91c_29.png)

Now in this work， the authors sort of criticize this， they say why。

 why are we doing it like this isn't there a better way to do it。

 specifically we want to look at this part right here， which is called the backbone。

 So we assume that we have these output layers that give you at different scales。

 different features and what we have to do is we have to construct a backbone that somehow feeds features either you know through this direct way or through these connections right here and feeds features to this these ultimate classifiers so these classifiers will then be used to classify the bounding boxes and classify the output classes for recognition and localization。



![](img/4417873120e7a7cc79467a91ca85b91c_31.png)

![](img/4417873120e7a7cc79467a91ca85b91c_32.png)

This is an illustration of this on the left you see a typical backbone。



![](img/4417873120e7a7cc79467a91ca85b91c_34.png)

And they call this a scale decreased network， so an example of scale decreased network on the left versus a scale permuted network on the right。

The width of the block indicates feature resolution， and the height indicates feature dimension。

Dotted arrows represent connections from two blocks not ploted。 Okay， so on the left。

 you have the typical architecture you see。

![](img/4417873120e7a7cc79467a91ca85b91c_36.png)

That the the width。 So this is the resolution is very high。 And as you go through the layers。

 that resolution gets smaller and smaller and smaller。

 But the number of features indicated by the height gets higher and higher and higher as you go through。

 This is your typical architecture。 We are looking into。 let's say that this is not the only one。

 What we can do is we can build any sort of backbone。 And here， they restrict themselves。 they say。

 okay， in order to make it comparable in order to be， you know。

 scientifically a bit more rigorous than just building anything。

 what we restrict ourselves are simply permutations of this。

 So we only allow us to permute these things。 So all the you know this goes here and this goes here。

 as you see。

![](img/4417873120e7a7cc79467a91ca85b91c_38.png)

![](img/4417873120e7a7cc79467a91ca85b91c_39.png)

![](img/4417873120e7a7cc79467a91ca85b91c_40.png)

And that ensures that you still have roughly the same amount of parameters。 Now。

 there is sort of a parameter difference， because。These connections here。

 you need to up and down sample the images。 and sometimes that introduces parameters。 but in essence。

 you have the。

![](img/4417873120e7a7cc79467a91ca85b91c_42.png)