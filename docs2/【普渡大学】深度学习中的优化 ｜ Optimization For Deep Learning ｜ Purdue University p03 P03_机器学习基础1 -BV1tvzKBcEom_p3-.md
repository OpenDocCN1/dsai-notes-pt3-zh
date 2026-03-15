# 【普渡大学】深度学习中的优化 ｜ Optimization For Deep Learning ｜ Purdue University p03 P03_机器学习基础1 -BV1tvzKBcEom_p3-

🎼，🎼Yeah。Welcome back today we're going to talk a little bit about some basics of machine learning。

 the machine learning workflow， we're going to talk about some terminologies and we're going to see how optimization can be useful。

In。Performing machine learning。So let's first talk about machine learning。

 so machine learning means learning from data， okay， so we want to learn useful pattern from data。



![](img/170163ede9276479bd0f11e6a97adb06_1.png)

Forly， we assume that we have。

![](img/170163ede9276479bd0f11e6a97adb06_3.png)

A collection of data points。

![](img/170163ede9276479bd0f11e6a97adb06_5.png)

Training data points or samples， which I'm denoting them by Z1 through Z N now。



![](img/170163ede9276479bd0f11e6a97adb06_7.png)

It is instructive to think of these eyess as a collection of。

 let's say some features and their corresponding labels。 Okay。

 so a data point of this is specific structure。 For instance。

 X I can be taught as a vector with P features。 Okay， for instance， an image that has P pixelels。

 okay。

![](img/170163ede9276479bd0f11e6a97adb06_9.png)

And why we think of it as the label for the I sample。 Okay， for instance， if our sample is an image。

Y could be1 or0。To to note whether that image is an image of a car or not but this is just one example we did with data of different forms in practice for instance we can have collection of sentences and our labels could be whether the sentiment in that sentence is positive or negative right we can have collection of videos。

 we can have collection of nuotides， anything。

![](img/170163ede9276479bd0f11e6a97adb06_11.png)

![](img/170163ede9276479bd0f11e6a97adb06_12.png)

![](img/170163ede9276479bd0f11e6a97adb06_13.png)

But to keep things more abstract， we're going to denote data points with the ice。

 mostly in this course， right， but it is helpful to think of it as a collection of， again。

 features and their corresponding labels。Now this is our workflow， so we have the image。

 we feed it to some model。And that model is going to help us to determine whether determine some useful patterns that we can later on generalize to new data okay now typically ML problems can be of one of the followings so we have supervised learning problems where our data has the form that we have a collection of let's say features and labels。

 so we have labeled data in particular。

![](img/170163ede9276479bd0f11e6a97adb06_15.png)

![](img/170163ede9276479bd0f11e6a97adb06_16.png)

嗯。Also opposed learning。😊，Is a kind of function problem where our data is not necessarily labeled。

 Okay， so we will still want to learn some useful pattern from the data， but we don't know。

 for instance， whether that image is an image of a car or not or that image is an image of a cat or not。

 We don't have that information。 And finally， there are reinforcement learning problems。

 where the idea is to leverage data to to make decisions especially in uncertain environments。

 And this is a very advanced topic and requires its own advanced course as well。



![](img/170163ede9276479bd0f11e6a97adb06_18.png)

![](img/170163ede9276479bd0f11e6a97adb06_19.png)

![](img/170163ede9276479bd0f11e6a97adb06_20.png)

All right。But a。Let's see how we can do this a little bit more mathematically。

 So as we talk about in the previous the slide， we assume that we can learn this pattern。



![](img/170163ede9276479bd0f11e6a97adb06_22.png)

Using some model in particular using D models。 So let's see what we mean by that pattern。 Okay。

 so what we are assuming essentially is that there exists some true but unknown relationship between the features and labels。

 okay， in particular， you can imagine that this unknown model is as star Okay。

 so therefore you could think of learning as the problem of learning as star。



![](img/170163ede9276479bd0f11e6a97adb06_24.png)

![](img/170163ede9276479bd0f11e6a97adb06_25.png)

![](img/170163ede9276479bd0f11e6a97adb06_26.png)

From a collection of。

![](img/170163ede9276479bd0f11e6a97adb06_28.png)

Traing data points from a collection of features and labels。 Okay， now to do this。

 we're going to resort to a parametric model。 Okay， so a。

 which depends on some parameter W that we want to find by leveraging data。 Okay。

 so the hope is that。

![](img/170163ede9276479bd0f11e6a97adb06_30.png)

![](img/170163ede9276479bd0f11e6a97adb06_31.png)

![](img/170163ede9276479bd0f11e6a97adb06_32.png)

Did exist。A set of power with your WS star， the best model， if you will。

 such that my parametric model is going to be a really good appm of this true unknown relationship between the features and layers。

 Okay， Now， how are we going to find this W star， As I said， we're going to leverage data。



![](img/170163ede9276479bd0f11e6a97adb06_34.png)

So in particular we're going to perform training， meaning that we're going to fit the model to the training data to find the best possible set of parameters WS star how do we do this。

 we're going to use optimization in particular we're going to design some loss functions which here on denoting by L。

 it depends on the parameter w。

![](img/170163ede9276479bd0f11e6a97adb06_36.png)

![](img/170163ede9276479bd0f11e6a97adb06_37.png)

And the oil here means that this is the loss of the model W fitting the I sample。

So we're going to leverage these loss functions， define optimization problems。

 and solve that optimization problem in order to perform the training a step up machine learning。

One example of the training loss is the simple quadratic loss function。



![](img/170163ede9276479bd0f11e6a97adb06_39.png)

Essentially， it captures using the quatic function how well our current solution W is able to fit the training data。

 If it's a really good fit， we expect this to be near0。 if it's a bad fit。

 this is going to be somewhat large。 So hopefully by performing training。

 we can ensure that the model is going to fit almost all of the training data well okay。



![](img/170163ede9276479bd0f11e6a97adb06_41.png)

![](img/170163ede9276479bd0f11e6a97adb06_42.png)

![](img/170163ede9276479bd0f11e6a97adb06_43.png)

So to ensure that we perform very well on all data points， collectively on all data points。

 what we're going to do， we're going to define this optimization problem。

 which focuses on minimizing。

![](img/170163ede9276479bd0f11e6a97adb06_45.png)

![](img/170163ede9276479bd0f11e6a97adb06_46.png)

The average loss over the training data。 Okay， so essentially。

 the most simple form of training is to， again。

![](img/170163ede9276479bd0f11e6a97adb06_48.png)

Design a loss function and minimize the average loss over the training data to ensure that on average you have a really good fit to the training data and once you do that。

 you'll find let's say a solution W star and that will give you a good approximation to this unknown true model that you don't know what you aim to find。



![](img/170163ede9276479bd0f11e6a97adb06_50.png)

Alright， so that's training。 And if it's done successfully。

 that means that we're going to fit the training data well。 Okay。

 but that's not the end of the story。 We also want to ensure that we're going to perform very well on on scene data。

 on new on scene data。Essential， we're going to make sure that the patterns that we learn。



![](img/170163ede9276479bd0f11e6a97adb06_52.png)

![](img/170163ede9276479bd0f11e6a97adb06_53.png)

![](img/170163ede9276479bd0f11e6a97adb06_54.png)

During the train step are generalizable to the data that we haven't seen。



![](img/170163ede9276479bd0f11e6a97adb06_56.png)

Okay。

![](img/170163ede9276479bd0f11e6a97adb06_58.png)

Now， this is step。

![](img/170163ede9276479bd0f11e6a97adb06_60.png)

Requires some assumption in order to assess whether the performance of the model that we learn by training。



![](img/170163ede9276479bd0f11e6a97adb06_62.png)

Is going to be good on an data，Essential， whether training is a good idea or not。



![](img/170163ede9276479bd0f11e6a97adb06_64.png)

One assumption is to assume that the new data that you're going to be tested on。



![](img/170163ede9276479bd0f11e6a97adb06_66.png)

And the training data belong to the same universe。

![](img/170163ede9276479bd0f11e6a97adb06_68.png)

And that's not a bad assumption， right， So if I want to test my model on some data。

 some new data and I have access to a data set right， let's say a set of images。

 those images better have some relation with the data that I'm going to be tested on right so if I'm performing training。

 let's say images of cast and dog。 and then I ask you and in a test I'm going give you let's say the images ofveales。

Obviously that's not going to perform well， so it is a reasonable assumption to assume training and test data or the new data if you will have some relation in particular。

 you can assume that they belong to the same universe okay。More mathematically， here is Ho。

How we show this。 So let Z be a new data。Then we say that Z comes from the same distribution that determines the training data。

 So in particular， Z comes from distribution P Z。And the training data D also comes from some distribution P subpsy。

And we call this data distribution。Now what's our measure of performance well for training our measure of performance was how well we are doing on an average over the training data here your measure of performance which is a national measure of performance is to check how well you are doing on average over the entire universe in particular this notation。

 the expectation over Z， you should think of it as again the average over the universe okay。



![](img/170163ede9276479bd0f11e6a97adb06_70.png)

![](img/170163ede9276479bd0f11e6a97adb06_71.png)

![](img/170163ede9276479bd0f11e6a97adb06_72.png)

![](img/170163ede9276479bd0f11e6a97adb06_73.png)

嗯。So not just the average over the training data， but average over every possible sample that I can be tested on。



![](img/170163ede9276479bd0f11e6a97adb06_75.png)

Okay。No。

![](img/170163ede9276479bd0f11e6a97adb06_77.png)

I'm going to denote this loss function with F bar。And this is in contrast to the last function that we use in training。

 which I denoteed by F。And it is important to know that F and F4 are not necessarily the same。



![](img/170163ede9276479bd0f11e6a97adb06_79.png)

In particular， F。The loss function that we use in training is just an empirical color approximation of SBR。



![](img/170163ede9276479bd0f11e6a97adb06_81.png)

Alright， let's first see a simple example。To sort of see the connection between F and F bar。 Okay。

 and in this simple example， I'm going to assume that the distribution of data is discrete。And。

Essentially， I have a discrete for。嗯。Okay， so these are my data points， these are my images。

 if you will。Z1， z2， z3， etc ceter。 and I'm going to sample one of these。

 let's say with probability 1 over n。 So in particular this means that it is equally likely at test time it is equally likely that I sample one of these data points。



![](img/170163ede9276479bd0f11e6a97adb06_83.png)

![](img/170163ede9276479bd0f11e6a97adb06_84.png)

![](img/170163ede9276479bd0f11e6a97adb06_85.png)

And it tests you on that data point。 Okay， so it is equally likely to observe。

Each and every one of these。

![](img/170163ede9276479bd0f11e6a97adb06_87.png)

三东。

![](img/170163ede9276479bd0f11e6a97adb06_89.png)

In other words， the probability that I select sample ZI is nothing but one we're in。



![](img/170163ede9276479bd0f11e6a97adb06_91.png)

Now let's calculate the functions F and F4， in particular。

 the functions that we use during turning F and the function that we're going to be tested at F4。



![](img/170163ede9276479bd0f11e6a97adb06_93.png)

So。

![](img/170163ede9276479bd0f11e6a97adb06_95.png)

F was nothing。But the。The loss。Over the average loss over the training data。 Okay。

 so I assume that my training data is essentially the entire universe。



![](img/170163ede9276479bd0f11e6a97adb06_97.png)

![](img/170163ede9276479bd0f11e6a97adb06_98.png)

So， therefore。F。Is nothing but the average。Over the training data， okay。

I really loss over the same data。On the other hand4。Was the average over the entire。Unniverse。

 and this was essentially how we， you know， we know that done mathematically。



![](img/170163ede9276479bd0f11e6a97adb06_100.png)

![](img/170163ede9276479bd0f11e6a97adb06_101.png)

，Now given that our universe is discrete and it is equally lightly。😊。

That I observe each of these samples。 So in particular， it observing probability one over n。

 I can easily write down what this expected value is。 Okay， so the expected value is essentially。

So some over the entire universe， my universe is discrete and I have n elements。The probability。That。

Z is equal to Z O。And the loss of。Fitting the I sample。 Okay。

 and this probability is nothing but one over n。 That means that this is going to be one over n some over I from one to n。



![](img/170163ede9276479bd0f11e6a97adb06_103.png)

Of L WCI。

![](img/170163ede9276479bd0f11e6a97adb06_105.png)

And this is equal to， perhaps not surprisingly。

![](img/170163ede9276479bd0f11e6a97adb06_107.png)

F， the loss that we use in training。So this basically says that if your universe is discrete and you are able to observe every single one of those elements。

In your training data。You can perfectly learn。That universe。

 or we can perfectly learn patterns that are applicable to all elements in that universe by minimizing the training loss。

 Okay， but obviously， that's not the typically the case in practice。

 So even if I have access to billions of images that doesn't necessarily represent the entire universe of images。



![](img/170163ede9276479bd0f11e6a97adb06_109.png)

All right。

![](img/170163ede9276479bd0f11e6a97adb06_111.png)

No。There are some terminologies here， again distinguishing between what we can do in training and what we can。

 or we hope to do in general on nuancecing data that I'm going to briefly talk about。

 and that's basically the distinction between population and empirical loss okay。



![](img/170163ede9276479bd0f11e6a97adb06_113.png)

![](img/170163ede9276479bd0f11e6a97adb06_114.png)

![](img/170163ede9276479bd0f11e6a97adb06_115.png)

So。As we talked about。

![](img/170163ede9276479bd0f11e6a97adb06_117.png)

从。To ensure that the performance on all data points， all images， right。

 So whether I see them in my training data or not。

![](img/170163ede9276479bd0f11e6a97adb06_119.png)

Is good。 We aim to minimize what we call population loss or population risk。

 and that is essentially what we talked about before。

 minimizing the average over the entire universe。However。

 all we can do is practice to minimize the minimize the empirical loss， okay， and that's essentially。

The loss over the training data。 And the reason for that is that， first of all。

 we don't know the universe， right， or mathematically。

 we can say that we don't know this distribution is if we don't know the data distribution。



![](img/170163ede9276479bd0f11e6a97adb06_121.png)

This approach， where we。Minimize an empirical approximation of the population race is called empirical risk minimization or ERM。



![](img/170163ede9276479bd0f11e6a97adb06_123.png)

![](img/170163ede9276479bd0f11e6a97adb06_124.png)

So let me pause here and in the next lecture， we're going to talk about some sources of errors during the learning process that we need to understand and control。

Thank you。