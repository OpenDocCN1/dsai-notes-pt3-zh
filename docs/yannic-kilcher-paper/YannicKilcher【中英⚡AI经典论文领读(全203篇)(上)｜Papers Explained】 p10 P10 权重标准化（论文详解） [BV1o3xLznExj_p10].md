# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p10 P10 权重标准化（论文详解） [BV1o3xLznExj_p10]

Hi there。 Today we're looking at weight standardization by Xi Wan Jo， Hu Wang， Shen Qi Liu， Weixhen。

 Alan Yu of John Hopkins University。So weight standardization is a normalization technique for training neural networks。

 and it goes basically in conjunction with another technique called group normalization。

 So if you haven't group。Normalization。Norm。That is ugly。

If you haven't seen my video on group normalization and don't know what it is。

 I suggest you go watch that first or read the group Nor paper or some blog post because weight standardization。

Is usually used together with group norm。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_1.png)

In order to work well， and that's what this paper also says。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_3.png)

Even though it's pretty much independent， but。Here you can see their main results。嗯。

So if they compare batch norm， group norm， and weight standardization used with group norm。

Then they can， as you can see here， they can outperform in the Inet top one accuracy。

 the other two models， and the important part here。

 as you can see is batch norm is trained with large batch sizes while group norm and group norm plus weight standardization or trained with one image per GPU。

 so they have a multi GPU setup， and this is just one image per GPU。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_5.png)

![](img/38dbe161acfb3f9454f4ff61a1b8588c_6.png)

And these results over here are on a mask R CNN。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_8.png)

Which I believe is a recurrent model， where。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_10.png)

The model is。Large， because the kind of。The model is large and therefore you can only have very small batches per worker。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_12.png)

And that means batch norm will work less。 Now， again。

 we've discussed why batch norm is not a good thing when you have to go to small batch sizes。

 because basically。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_14.png)

![](img/38dbe161acfb3f9454f4ff61a1b8588c_15.png)

![](img/38dbe161acfb3f9454f4ff61a1b8588c_16.png)

What people have discovered is that it is very beneficial in machine learning to normalize your data before working with it。

 What do we mean by it？ So if you have a bunch of data points right here。And let's say like this。

 it is， it is usually beneficial to first center the data。Like this。

 So basically calculate its mean and shift it。 And then to standardize the axiss。 So basically。

 divide it by the standard deviation in each direction and your data will look something like this of many classical methods that will improve the conditioning numbers。

Of the requirements to solve it and so on。 And even of deep learning methods。

 we just know that if you standardize your data like this， it works better。

 So people are basically have come up with these methods that。Where they say， well。

 if it helps for the data at the beginning of a neural network， then if after， if after a layer。

The data is kind of out of whack that can happen after a layer of neural network。

 we should maybe first before we send it to the next layer， do the same thing。 Center it again。

 and then send it through。 And if after the next layer， again， it's out of whack。

We should maybe center it and standardize it again before sending it through the next layer。

 So in each layer， you have these transformations that center and standardize the data。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_18.png)

And usually for the longest time， this was batch norm。

 batch normm does this across the mini batches of the data since you can't pass the entire data set。

 Now， group normm has come and replaced batch norm because in batch norm is very dependent on the batch size while group norm isn't。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_20.png)

![](img/38dbe161acfb3f9454f4ff61a1b8588c_21.png)

![](img/38dbe161acfb3f9454f4ff61a1b8588c_22.png)

Now the group norm paper has sort of made it clear that in like in competitive batch sizes in the large batch size regime。

 group norm is sorry batch norm is still the king。 batch norm still works better。

 It's only when you go to very small batch sizes that group norm takes over。

 and that's why you can see here。 So here， okay， it's a bit unfair because batch norm is trained with the larger batch size。

 but even if group norm were to be trained with the large batch size。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_24.png)

![](img/38dbe161acfb3f9454f4ff61a1b8588c_25.png)

It would still be in the same place because。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_27.png)

No， it wouldn't， it would not， sorry。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_29.png)

That is， that is not the case because the batches still influence the gradient stochasticity and so on。

 But still batch norm is better than group norm， as you can see here。 But here over here。

 where you kind of have to go to the small batch sizes。 Then batch norm is all of a sudden。

 worse than group norm。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_31.png)

![](img/38dbe161acfb3f9454f4ff61a1b8588c_32.png)

And the weight standardization。Is a technique to actually make group norm better than batch norm in any of these。

 so even in these in the large batch regime。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_34.png)

Okay， so we'll now explore weight standardization。So in the group norm paper。

 we've looked at the diagram on the left。 so basically in batch norm。

 here is the number of data points。 This is your batch。

This is the channels of the batch of the individual images， channels。

 And this is the height and width of the image。 So this is the image itself， a single channel。

 So a single channel in the image would be a column in this thing right here。

Patchorm normalizes across the data points in a single channel。Layer norm。

 which is a precursor to group norm， normalizes only in a single data point instance。

 but across all of the channels， as you can see here。

 Now that frees its dependence on the batch size。 Each data point is treated individually。

 but of course， it it sort of convolves all the channels with each other。

 It doesn't distinguish them。Instance norm tries to fix this instance norm down here。

Tries to fix this by saying it was a good idea to normalize each feature individually and takes it to the extreme basically normalizes。

A single image for by each of these single features。

But that loses too much information group normorm comes along and says maybe some of the features naturally depend on each other。

 naturally exhibit the same responses。Therefore， we should normalize them in groups so we take still a single image。

 but we take groups， in this case， groups of three channels together and normalize across that。Now。

 this。Here is all in data space。 This all normalizes the data。

 like we said up here when we drew this， this is all normalizing the data before passing it through the next layer。

 Now， what actually happens in these layer。 So what happens here。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_36.png)

![](img/38dbe161acfb3f9454f4ff61a1b8588c_37.png)

What happens here in a convolutional neural network is that the images get convolved with kernels。

 that's how that's what a neural network layer is。 So if you have an image right here。

Of our trusty cat， I've drawn whiskers in a while。 That nose is very high。 The eyes must be， like。

 up here。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_39.png)

Sorry， Kas。 And the layer inherently has these things called kernels。 Now。

 I'm just gonna draw one of these kernels right here。 It's a 3 by three kernel。

 And what you'll do is you'll slide the kernel across this， right， across like this。

 you'll slide it across， across， across， across。 And for each point， you convolve the kernels。

 So you convol the values here with the pixels here。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_41.png)

And sum them up。 And that for each position in the image means that。

You'll basically get a new value at each point， and that will be your next layer data point。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_43.png)

Now， in。These normalization techniques， we usually normalize the data points。

 So here we have multiple channels， maybe a red， a green and a blue and so on。

 And in the intermediate layers you have even more。And but you also have multiple kernels。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_45.png)

You can see here。You have multiple of these kernels which will then result in multiple output channels。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_47.png)

The old normalization methods， batch norm， layer norm， group norm。They all work in。

They all work in this or in this space， in the space of data。

 whereas weight standardization works on the kernel space。

 so weight standardization means you want to normalize the weights of the neural network。

 not the data。

![](img/38dbe161acfb3f9454f4ff61a1b8588c_49.png)

![](img/38dbe161acfb3f9454f4ff61a1b8588c_50.png)

And that's why it can be used in conjunction with something like group norm。

 or actually batch norm or layer norm could be used with any of these。

 But these authors use it in conjunction with group norm。

 So what does it do if you have these kernels， the kernels are。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_52.png)

Of are characterized， actually， a kernel is characterized by four numbers。 So first of all。

 it's the height and width of the kernel， which in our case was 3 by3。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_54.png)

It is characterized by two more numbers， which is the C in the in channels and the out channels。

So the in channels is the number of channels that come into the layer and the out channels are。



![](img/38dbe161acfb3f9454f4ff61a1b8588c_56.png)