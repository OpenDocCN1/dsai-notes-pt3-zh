# 【NPTEL】计算机视觉的深度学习 p43 P43_超越解释CNN -BV1vNWkzpEua_p43-

![](img/f5629ab6a820bf5d08ca784e7605b693_0.png)

For the last lecture of this week。We are going to try to go beyond explaining CNs and look at a couple of interesting applications of using the concepts that we saw so far。

 gradients and various other artifacts for explaining CNNs， but use them in interesting ways。

Before we go there， let's review one of the homeworks that we left behind last lecture。

Which was for you to read axioms of attribution。Hope you had a chance to go through that work。

So here are a few of the axioms that have been claimed in the paper which all attribution methods or saency methods or visual explanation methods。

 they are all the same in this particular context， attribution methods generally refer to methods that broadly cover entire machine learning maybe even beyond vision。

 but in the context of computer vision， attribution methods， saency map， visual explanations。

 they are all broadly synonymous， but wed like these attribution methods to satisfy a few of these axioms。

The completeness axiom says that for any input X。The sum of the feature attributions。Equals f of x。

Which means if you had， say10 different attributes or 10 different attributes in your input。

The sum of their attributions should be the actual output that you get of the neural network。

 the some of the attributions with respect to your neural network should be the actual output。

 This is a bit similar to what you see in deeplift where we said that the contributions must add up to deelta t which was the difference of the output。

With respect to the reference output， so the completeness property is something that deeplift satisfies another axiom sensitivity states if x has only one non0ro feature and f of x the output of the neural network is not 0。

Then the attribution to that feature should be non zero。

And you'd actually find that gradient based methods do not satisfy this sensitivity axiom。

Think about it and try to answer why you can also read this paper for the answer。

When I say integrated gradient actually satisfies vanilla gradient based methods do not satisfy the sensitivity same。

😊，Another axiom is implementation invari。When you have two neural networks that compute the same mathematical function。

 f of x。Regardless of how differently they are implemented the attributions to all features should always be identical so let's assume that you had two neural networks。

13 layer and one2 layer but it happens at the end that they exactly give the same output for every input that you can give by some means they have learned the same function maybe use re in one3 layer network and use a sigmoid in another two layer network but let's assume they learned exactly the same function。

If that happens， the attributions to all features that you get in both of these networks should be the same。

And you will actually see that deeplift violates implementation in variance once again。

 the reason please look at this paper at the bottom。

Another axiom states about the symmetry preservation of the attribution method。

Which states that for any input x where the two values of2 symmetric features are the same。

Their attributions should be identical as well。By symmetric features。

 we mean features that can be swabbed and the neural network output will still remain the same。

So this could be in an input， this could be an intermediate layer general eyme is a broader concept。

 but we are saying now that if two inputs could have been replaced and the output still stays the same。

In that scenario， both those features should have the same attribution。

Please do read this work below for more details about the vaccines。With that。

 lets go on to these interesting applications that go beyond explanations but use the concepts that we discussed over the course of this week。

The first one is a work known as Deep Dream which was developed in 2015。

 which uses the ideas that we talked about in the earlier lectures of the week but in a different and interesting way。

😊，It modifies a given image in a way in we that boosts all activations at any layer creating a feedback loop。

And which means if you have a dog。A feature or a kernel that detects a dog's face in a particular layer。

 you back propagate that onto this given sky image and keep adding the dogs face to this cloud image and you will end up getting a pretty interesting artistic image。

To to end at the end of this process。Let's study this method in more detail。

 So you have an input image。Let us choose a particular layer and a particular filter in that layer。

 lets say that this is that layer and there is a filter in that particular layer。

Now you input the image through the CNN and you forward propagate until that particular layer in the neural network。

Once you do that。You back propagate the activations of that filter back to the input image。So。

 you do a back to image very similar to what we did in one of the earlier lectures but this time the input is not a black image or a gray image this time the input is just any other image that you want to juxtapose or overlay that input onto so you take the an image of the sky。

Take a face of the dog or any other filter and keep adding to this image the gradient that you get from the face of the dog。

 you try to see what in the input image would have resulted in that filter being fired which would be given by the gradient of that filter with respect to the input remember we talked about if you wanted to maximize a filter's activation you set the gradient of only those filters to one everything else to0 and backpro to image and update the image using gradient as。

You do the same thing here。And now you multiply those gradients with your learning rate and add them to the input image that' is the gradient accent that we talked about。

What happens？You now see that you will get an image such as this in this case it is not a dog。

 it looks like a bunch of buildings that you add to the original image and then you go back to two again。

 you input this image into the neural network again maybe you want to use the same filter maybe you want to use a different filter and you can keep playing with this to create different kinds of images you can now take。

A different filter in a different layer and now you could add that and you now end up getting a different kind of a construction of the image。

So you would see that higher layers produce more complex features while lower ones enhance the edges and the textures you can even see that example in these two images here。

 this was the top red one was created from a slightly earlier layer and this yellow one here was constructed by the yellow bordered one here was constructed by a slightly later layer。

A few more examples of deep dream so given an image of an horizon you can actually convert it to one of a tar you can actually see that this is the same image taken but you keep on juxtapoing a tower filter on it and you end up getting a construction such as this。

Another example is of going from trees to keep adding buildings to it and you come up with a nice pagoda lake structure。

On the same scene。And here is a photo of leaves and you keep adding the gradients of bird and insect filters and you get an interestingest variant of an image starting with the original leaf image。

More examples。And now lets see the other application， other similar interesting application。

 which is known as neural style or neural style transfer as it is popularly known。

The idea here is given an image。And given a particular style， let's say a modern art style。

You want to know how do I get this image in this style for example。

 can I take my photograph and make it look like Van Goh had painted it？

How would I get that style into my photo that is what we want to study here one is you could simply overlay take one of Van Goh's paintings。

 overlay that on top of an image that I have。But unfortunately。

 this really doesn't give good results。😊，Another option is to ask a human to do it for us but that is not what we want to go for so the third option what we are going to look for is what is known as neural style transfer which was also a method that was proposed in 2015 and let us see how this works。

So， once again you have a trained alnet model remember in the scope of this entire week we already have a pretrained model。

 we are not training the model in any way we are only working with a trained model in different ways。

So you provide the input image that you want to your network and you extract the activations at different layers for the given input image。

Then you also extract what are known as style targets。

 so you give the style image to the same neural network so the style image could be a painting by Picasso or Wgo or something like that。

 you give that as input to the same neural network。

But this time you don't get the activations of this input at different layers。 Instead。

 you get what are known as gram matrices of。Connet activations of all layers What does that mean So if you take a particular layer here。

 remember this is composed of a set of feature maps。

 so you have a volume of different set of feature maps。Now。

 each feature map could be say 20 cross 20 dimensions as an example， now what we do here。

Is to linearize or raize this entire feature map into a 400 dimensional vector。

And now you take the covariance of this 400 dimensional vector with the another channel or another feature map in that volume and you would now get one such value of the covariance of one channel with the next channel。

Similarly， you compute the covariance of every channel with every other channel and you would get a gram matrix of convenet activations of all layers。

Why is this a style target？There's no clear answer。But。One could surmise that。 This is because。

The relationships between the filters give us an idea of what style is being understood by the neural network that is the broad idea here。

So， what do we do with the style target？Once you obtain these gram matrix of con activations from the style image。

Now you take a new you again take a network， a train model。

 and now you give a blank input as an image。And。To this image， you backrup the image again。

But you try to ensure that the activations that you get at any layer of this model is close to the activations that you get for this image on the same model in a different context。

And the gram matrix of activations that you get here resemble the gram matrix of activations that you get for the style volume。

So remember， this is the content part of it。And this is the style part of it。See you now。

Back prop to image。For a gray image and another of these Alexnet models or any CNN model。

 you would do a backrup image， remember that piece said was ag max of I。

We try to maximize the score of I with respect to particular neuron。

 but this time we are going to try to minimize。The distance between the activations that we get for this input here and the activations that we get for this dog image on this network。

Similarly minimize the distance between the gram matrix of the covariances between activations here and the gram matrix of the covariance between the activations in this style when you forward propagate the style image。

When you combine these two you end up getting an image which takes the style from the style image and the content from the input image and thats the output that you get while you started with a simple gray image。

Here are some examples of various neural styles so you can see here is the input image and here is the style and you get a pretty interesting output that resembles the style so here is Steve Jobs picture and you have a style and you see the picture changes similarly you see several other examples which are fairly good in terms of what they achieve。

More examples here if you would like to take a look where the content and style is varied and you have an entire grid of several examples of taking a content and trying different styles on them。

So if you'd like to understand this more， there are a couple of interesting links here。

which give you an intuitive understanding of neural style transfer both are on the towards data science links。

 and there is also a nice understanding of deep dream on hacker known with the code provided。

And an interesting exercise for you is going to be to watch this fun video of YouTube on doing deep dream on videos。

 the example that we talked about in this lecture was about doing deep dream on a given input image。

What if you do deep dream on videos？Thats what this fun video on YouTube does。

 Please take a look at it more importantly try to figure out how it was done。

That's the exercise for you this week。

![](img/f5629ab6a820bf5d08ca784e7605b693_2.png)