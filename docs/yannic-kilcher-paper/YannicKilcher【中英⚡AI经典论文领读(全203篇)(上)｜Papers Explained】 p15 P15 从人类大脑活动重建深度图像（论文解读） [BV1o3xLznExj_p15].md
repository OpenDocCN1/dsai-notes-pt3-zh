# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p15 P15 从人类大脑活动重建深度图像（论文解读） [BV1o3xLznExj_p15]

Hi there。 Today we're looking at deep image reconstruction from human brain activity by Guwa Shen。

 Tomoyasu， Horiikawa， Kaimajima and Yukiyau。Comami doneni。



![](img/a962987a4a119c6b15df06abb938dc3a_1.png)

This is like reading thoughts。

![](img/a962987a4a119c6b15df06abb938dc3a_3.png)

So I was excited when I saw this paper， I saw this on Reddit and。



![](img/a962987a4a119c6b15df06abb938dc3a_5.png)

It is a bit older it is from the beginning of last year。

 so I'm sure there have been developments in this area。

 but basically what this paper does is it will have a human look at a picture as you can see。

 for example right up here it will measure the MRI activity then it will use a what they call a feature decoder in order to map that MRI activity to。



![](img/a962987a4a119c6b15df06abb938dc3a_7.png)

Features of a deep neural network。

![](img/a962987a4a119c6b15df06abb938dc3a_9.png)

And then they will reconstruct the image that is closest to those features in the neural network。



![](img/a962987a4a119c6b15df06abb938dc3a_11.png)

And by reconstruction， they get basically， they get out an image of what the human sees。

 So we're going to explore this pipeline right here。 but it's pretty cool。 And if it works， you know。

 it basically means that we can read someone's thoughts。



![](img/a962987a4a119c6b15df06abb938dc3a_13.png)

![](img/a962987a4a119c6b15df06abb938dc3a_14.png)

But of course theres going to be issues and problems so first of all， this is all visual。

 they measure the activity in the visual cortex right here。



![](img/a962987a4a119c6b15df06abb938dc3a_16.png)

![](img/a962987a4a119c6b15df06abb938dc3a_17.png)

So。

![](img/a962987a4a119c6b15df06abb938dc3a_19.png)

Let's。Break it down to the individual parts。

![](img/a962987a4a119c6b15df06abb938dc3a_21.png)

The individual parts here， they FMRI， that is a machine we cannot control right So you measure the FMRI activity。

 and that's basically measures which of these cells in your brain use oxygen。

It's it's functional FMRI。 It's not structural， so it measures which ones are active。

 and that's how you would see which parts of the brain brains are active。

 And I think the resolution on these things has gotten very。

 very good so you can make out very finegraed activation patterns in the neurons and they measure the visual cortex。

 which is the part responsible for basically visual stimuli over for seeing things。



![](img/a962987a4a119c6b15df06abb938dc3a_23.png)

![](img/a962987a4a119c6b15df06abb938dc3a_24.png)

Now they need this featured decoder， but because ultimately what they want to do is they want to have these features correspond to features in a neural network this DN here is like a VGG I think a VGG16 or a VGG19 it's called a VGG16 network this is a couple of years ago these architectures were very popular for imageNe and they're fairly basic so what that means it's not like a。



![](img/a962987a4a119c6b15df06abb938dc3a_26.png)

![](img/a962987a4a119c6b15df06abb938dc3a_27.png)

A super duper inception net where you have like layers within layers and so on。

 they're pretty straightforward convolutional neural networks with non nonlinearities and pooling here。

 you can see there is a bunch of layers。 Then there's pooling。 There is a bunch of layers。

 there's pooling and so on。So what you want to look at are these layers of the deep neural network。

 right， the individual layers。And you want to。

![](img/a962987a4a119c6b15df06abb938dc3a_29.png)

You want to basically put an image right here into the neural network and then observe its features in the neural network。

 and then you want to put the same image through the human and then you observe the MRI features。



![](img/a962987a4a119c6b15df06abb938dc3a_31.png)

![](img/a962987a4a119c6b15df06abb938dc3a_32.png)

And you know that this is the same image。 So you can basically learn a feature decoder。

 This is going to be another sort of machine learned， maybe a neural network。

 I haven't actually read this could be just like a linear regression or a neural network。

 just a regression from that maps the FMRI to the features。



![](img/a962987a4a119c6b15df06abb938dc3a_34.png)

So this is what you have to learn。 Basically， they took a bunch of humans。

 stuck them in an MRII machine， right， got out their， their FMRI data for the same image。

 So for a given image X， they got the human FMRI data。And they got the VGG。Vjihiji。

They got the features。When they put the X， the image through the neural network。

 and now they learn a function that minimizes the error， so there is an error。



![](img/a962987a4a119c6b15df06abb938dc3a_36.png)

![](img/a962987a4a119c6b15df06abb938dc3a_37.png)

So basically they run this on a test set of images。

 and then you end up with a function that can basically map FMRI features。

 to neural network features。

![](img/a962987a4a119c6b15df06abb938dc3a_39.png)

Now the second step now you you can you can give the human， let's say this works。

 you can give the human an arbitrary image and the human will basically。



![](img/a962987a4a119c6b15df06abb938dc3a_41.png)

Interpret it through its visual cortex， you measure the activity in the visual cortex。

 and then you can predict。The neural network features if that image were given to the neural neural network。

Okay， but now you don't give the image to the neural network instead of what you do。

 you do something like deep dream does。That means you start from a noisy image at the beginning and you try to find the image。

 so you start from this noisy image right here。And through iterative gradient descent。

 you refine this image， and that's this arrow right here。

You' try to find the image that as closely as possible in the internal representation matches the features that you predict from the FMRI signal。

Because these are the features that the neural network should see right if your feature decoder is good。

 these are the features that the neural network should output for that image。

 so you're basically trying to find this image right here。

 but you're not looking at it you only look at the features that should be in the neural network。

So after a bunch of steps of refining that image， you hope you basically end up with an image that corresponds to these features and then you。

You you can look at it and it usually looks something like this。

 we're used to these kind of things from neural networks。

 and if I invite you to look at something like the open AI Atlas。

 if you want to understand how this is done， but basically we can get the image that most faithfully corresponds to these features。



![](img/a962987a4a119c6b15df06abb938dc3a_43.png)

![](img/a962987a4a119c6b15df06abb938dc3a_44.png)

![](img/a962987a4a119c6b15df06abb938dc3a_45.png)

Now， this doesn't always work super well because there are actually since the neural network is sort of a dimension reduction technique。

 there are many images that correspond to the same features and they often end up like really weird。

 So what they do is they have this deep gene network as a prior。

 Basically this is the generator from agan from a generative adversarial network。

 So this network right here。

![](img/a962987a4a119c6b15df06abb938dc3a_47.png)

Is really good at just producing naturally looking images。



![](img/a962987a4a119c6b15df06abb938dc3a_49.png)

And。Now， because we have that， our task is not going to be to start from this image right here。

 our task will be to do the exact same thing， but with the input to the deep generator network。

 So basically what we're trying to do is we're trying to find the input vector to the deep generator network。



![](img/a962987a4a119c6b15df06abb938dc3a_51.png)

Such that these features right here correspond to the features that we predict from the FMRI activity。

And because the deep generator network is trained to produce natural looking images。

 this will always give us sort of a natural looking image， no matter what our input vector is。

 So thereby we basically constrain the optimization procedure to only output natural looking images。

 So let's see how well this works。So these are the reconstructions。I have to say their training set。

 their training and testing set。 So up here， this procedure where we learned right here。

 this would be done on a training set of images and then they expose the humans to testing set of images so this reconstruction right here would happen on images that the feature decoder wasn't trained on but the humans are looking at it so the humans would be looking at the picture here on the left and then this would be to the right you'll see as more and more iterations of this process of reconstructionconing happens。

 The image gets basically clearer and clearer。

![](img/a962987a4a119c6b15df06abb938dc3a_53.png)

![](img/a962987a4a119c6b15df06abb938dc3a_54.png)

![](img/a962987a4a119c6b15df06abb938dc3a_55.png)

And you can see on the right， you get pretty good looking images for the ones on the left。Now。

These researchers， they tend to。They tout this success， like to say， oh， look， look at this。 But。

 you know。Honestly。Like this。Is a leopard。This is a。



![](img/a962987a4a119c6b15df06abb938dc3a_57.png)

Dog sheep。This。Is an owl。This is a dog。 So， so you know， this is a fish。And this is a like a shell。

 like a a muscle。 So I'm。And you can go through these， and basically。You know， this is a sled。

And then this is a truck。嗯。So they， they， they go basically and they say， wow。

 the accuracy is really good。 so they do。

![](img/a962987a4a119c6b15df06abb938dc3a_59.png)