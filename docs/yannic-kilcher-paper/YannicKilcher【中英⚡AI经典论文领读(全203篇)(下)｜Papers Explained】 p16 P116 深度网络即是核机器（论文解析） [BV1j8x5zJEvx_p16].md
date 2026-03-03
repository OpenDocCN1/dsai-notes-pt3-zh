# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p16 P116 深度网络即是核机器（论文解析） [BV1j8x5zJEvx_p16]

Hi there， Today we're looking at every model learned by gradient descent is approximately a kernel machine by Pedro Domingoz。

This paper on a high level establishes a theoretical connection between gradient descent learned models such as deep neural networks and kernel machines。

 as you might know them from topics such as support vector machines。The paper。

Interprets its own finding as meaning that deep neural networks essentially store their training data in their parameters as a superposition and when a new data point comes in。

What it does it is it sort of compares the data point to the stored training data and then decides with relation to that data what the output should be。

 which is， of course exactly what a kernel machine does。 So it is a theoretical paper and。

We're we're gonna go over it。 I'm not an entire expert on these things。

 but the main theorem is fairly easy to grasp， and the proof behind it is also fairly easy。

 So I thought it'd be a good paper to look over Further Pedro is coming to our machine learning street talk podcast in the future。

 and I wanted to get familiar with his work。 So， you know， if you like content like this， too。

 let me know let me know if you understood it or not or if I just made it worse yeah。



![](img/98a1aa7b28ac28a402c73ed50c96bf50_1.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_2.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_3.png)

Let's dive into the abstract。 The abstract is actually a pretty good summar of what the conclusions of the paper are。

It saysDe learning successes are often attributed to its ability to automatically discover new representations in the data。

 rather than relying on handcrafted features like other learning methods。

 and as you might know this is a success story of deep learning before deep learning。

 we had to do a lot of handcrafting of features where expert knowledge went into problems and then we would simply aggregate the handcrafted features with some sort of linear classifier or you know in some cases a kernel kernel classifier though the handcrafting of features would also go into kernel design。

Deep neural networks are different because we just feed in the training data as is。

 and the deep neural network will automatically discover the features that are important。

At least that's the prevailing notion of what's happening。 This paper challenges this view。

 They say we show， however， that deep networks learned by the standard gradient descent algorithm are in fact。

 mathematically approximately equivalent to kernel machines。

 a learning method that simply memorizes the data， and uses it directly for prediction via a similarity function。

 the kernel。

![](img/98a1aa7b28ac28a402c73ed50c96bf50_5.png)

So that's the main thesis of the paper。 They show that it is equivalent to a kernel machine。

 if you don't know anything about kernels， don't worry there is a good machine learning street talk episode with Alex Stanlock where I get to ask all the dumb questions about kernels so you don't have to ask them。

 So if you are interested in that check that out as well。

 That's on the machine learning street talk podcast。

 They say this greatly enhances the interpretability of deep network weights by elucidating that they are effectively a superposition of the training examples。

 so。

![](img/98a1aa7b28ac28a402c73ed50c96bf50_7.png)

Saying again that the deep neural networks they essentially store the training data in their weights and then use that to compare new data points too Now the conclusion of this paper is is is interesting。

 I don't fully agree like I don't agree with the framing here that it's sort of replacing this notion I think this gives rise to sort of a dual view of the problem。

 It is a way that you can also look at these deep neural networks。 I don't think it kind of。

Changes like it can both be true that they do discover good representations and also are a superposition of the training data。

 I think it's simply a different way of looking at the problem。 However， I， as I said。

 I'm not a super duper expert on this。

![](img/98a1aa7b28ac28a402c73ed50c96bf50_9.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_10.png)

And they allude to the fact here that this improved understanding should lead to better learning algorithms。

 and of course， even though this paper here has no impact for practitioners down the road。

 this could actually have some impact。

![](img/98a1aa7b28ac28a402c73ed50c96bf50_12.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_13.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_14.png)

So what is a kernel machine。 A kernel machine is this thing right here。 So in machine learning。

 we always wanna， we， we have some X。 and this is our input data， and we want to get some Y。 Now。

 for the purposes of this paper， think of Y being just a number。 So think of linear regression。 Okay。

 not linear， but just regression where y is a number。

 X is a data point and we want to function F that assigns each data point a。😊。



![](img/98a1aa7b28ac28a402c73ed50c96bf50_16.png)

Number， and then that number is going into a loss function。

 So there is going to be a loss function that compares that number2。

The number that we have in the training data set our true label Y star。 Okay。

 so we have training data X I。 this gives so the neural network gives an output Y。

 we compare that to the true label in the loss function。



![](img/98a1aa7b28ac28a402c73ed50c96bf50_18.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_19.png)

Now， a kernel machine。

![](img/98a1aa7b28ac28a402c73ed50c96bf50_21.png)

Is a particular way of how this F here is built。And usually。

 if you think of this as a neural network， you simply say， oh， X goes into layer， layer， layer。

 layer。 And at the end， you get Y， okay， A kernel machine is different。

 A kernel machine actually builds a a database of all the training examples。

 So what it would do is it takes your training data set。



![](img/98a1aa7b28ac28a402c73ed50c96bf50_23.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_24.png)

And it will sort of build a list of all the training data points in here。 I'm duper。

 super oversimplifying this， but it will build a list of all the training data right here。

 And now when you want to know about a new data point。 say you want to classify this X right here。

 What it will do is it will go to its database and it will compare X to each of those training data points to each。

 And from each of those training data points， you get a response of how similar is X to that training data point。

 So for for the first training data point。

![](img/98a1aa7b28ac28a402c73ed50c96bf50_26.png)

You would get a score of how similar the is， and that score is computed by this kernel function。

 so x1。And kernel of x with x 2。 You get kernel of x with x 3。 So for each data point。

 you want to know how similar is the data point that you wonder about to the data points that you've already seen。

 If we look at this in kind of achematic。 So let's say this is our data space。

 and you have kind of a data point here and one here and one here and one here in the training data set And。



![](img/98a1aa7b28ac28a402c73ed50c96bf50_28.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_29.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_30.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_31.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_32.png)

You want to know， how should I classify this red data point right here？Your kernel will tell you。

 and it looks easy if it's on the plane， but it's not easy at all in high dimensions with complicated data like images or structured data。

 it's not as easy as simply taking the distance， though here it is。

 So here a good kernel function would simply be the Euclidean distance to these data points。

 And this says something like the kernel function would tell you that these two data points right here are very similar to the data points we care about。

 Well these two data points right here are not that similar so。



![](img/98a1aa7b28ac28a402c73ed50c96bf50_34.png)

When you classify the data point， you consider all the data in your training data set。

 at least in the ground case。 So here is your training data set。

And your kernel will tell you how similar each one is， okay， that's the kernel。



![](img/98a1aa7b28ac28a402c73ed50c96bf50_36.png)

And then。You take that similarity and you aggregate the labels of the training data points since you know and the labels they are in here。

 So why star it says AI here。

![](img/98a1aa7b28ac28a402c73ed50c96bf50_38.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_39.png)

But why I star。 So the true label is usually what gives rise to this。 A。

 It doesn't need to be the true label， but in the simplest case。

 you will simply aggregate the labels of these data points in， in proportion to how close they are。

 It's， it's a bit of a nearest neighbor classifier， okay。



![](img/98a1aa7b28ac28a402c73ed50c96bf50_41.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_42.png)

So that's a kernel machine。 The important thing is that there is this kernel。

 This is a function that tells you how close any two data points are。

 and there is this sum right here， So that means that the your prediction y is going to be can be a nonlinear function of the sum。

 but it's going to contain a sum over the training data。Okay。

 and each training data point is measured in its similarity through the kernel function。

 and then the labels of the training data points are aggregated。 That's a kernel machine。



![](img/98a1aa7b28ac28a402c73ed50c96bf50_44.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_45.png)

So you don't， you don't need， you know， any model for this， right？

 The learned parameters here are often the the A's and the the B right here， the offset。 However。

 the kernel can also be learned， but very often the kernel is also fixed。

 And you can see immediately that choosing the kernel is the name of the game in kernel on machines。

 And before deep learning。

![](img/98a1aa7b28ac28a402c73ed50c96bf50_47.png)

![](img/98a1aa7b28ac28a402c73ed50c96bf50_48.png)