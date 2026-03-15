# 【普渡大学】深度学习中的优化 ｜ Optimization For Deep Learning ｜ Purdue University p05 P05_机器学习基础3 -BV1tvzKBcEom_p5-

🎼，🎼Yeah。Welcome back。 So we were talking about the machine learning framework， right？

 So we talked about the training system。 We talked about how we assess the performance of the model we learn during the training on nuancecing data we talked about different sorts of errors right So representation error optimization error as well as the empirical approximation error。

 Now in this lecture。 I just want to talk about some basic examples in that we use to to basically solidify the machine learning framework okay。

So， and these are very basic examples， right？ and typically belong to the supervis learning category of machine learning。

 meaning that we have a collection of features and labels。 Again。

 those could be images and their labels。 and let's say we want to classify。 the images， right。

 So I have images of different digits，0 to 9。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_1.png)

And I want to learn a classifier that given a new image。

It can tell me whether that image is basically zero or is it1， is it 2， etc ce。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_3.png)

可。Alright， so the first set of problems or models， if you will， is binary classification。

 So it's a simple classification problem where you have only two classes， okay。都。

Imagine that I have a class of plus。ok。And of minuses。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_5.png)

Again， plus， you can think of it that。Images of a car and minus images that are not car。

Now the goal of the classification problem is to， as I said， learn a classifier in this case。

 a hyperplane。That can separate class plus from class minus， okay。

So what are the elements of this problem， We have our feature vector X， okay， again。

 could be the collection of pixels。We have our labels， plus1 and -1。

 So just two of them because they binary their classification problem。And we make an assumption that。

The data is linearly separable。 Again， there is a linear line。

 linear hyper planee that can separate the plus sign and minus sign。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_7.png)

Therefore， a natural class of models。Is basically models of the following form， right？

 So they look at basically the。The inner product between x and W。

 So W is basically the normal to the hyper plane。And if that inner product is positive， you say that。

 hey， this image belongs to the positive class。 and if that inner product is negative。

We say that that image belongs to the other side to negative class。 Okay。

 so we just look at the the sign of the inner product， right。So that's our our models。

 So it is essential to talk about loss functions when we want to perform training。So in this example。

 we typically deal with two loss functions。The first loss is 0，1 loss。Okay。

 so this essentially assigns a value of one。If the model is not able to fit the oil。嗯。Data。Okay。

In particular， if it miscalifies the I data。And otherwise， it assigns a value of 0。

 So if my model is able to classify the， let's say the I S image my train data correctly。

 there is no loss。If it classifies it incorrectly or youcur a loss of fun， okay。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_9.png)

Now， this is very intuitive。 And another reason that this is a useful loss is that when I talk about the average loss。

Or basically。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_11.png)

The loss of a sample。Z。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_13.png)

And by the way， this， this is basically the indicator function。 Okay， so it returns the value of one。

 If the argument is true。 Otherwise， it returns a value of 0。

 So it's not difficult to see that if I take the expected value of this quantity over the choice of Z。

 this is just going to be。The probability。De。I miscalify。D sample。

So the average loss in this case This is nothing but the probability of misclassification。All right。

Now， although this is very intuitive， one issue with that is that it's going to make the training difficult。

We talking about convicity。呃。And the fact that complex functions are nice and can be optimized。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_15.png)

Eff。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_17.png)

The issue with this zero loss is that it' going its not going to lead to a convex optimization problem。

Therefore。What we typically do is to replace this loss with the best。

Convet approximation that we can design。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_19.png)

And that approximation is called the hinge loss。Okay。

 so h loss is nothing but an approximation to the 01 loss， and it takes the following form。 Okay。

 so the max between 0 and 1 minus， the inner product between X X and W。Okay。As I mentioned。

 the nice thing about this is that the empirical riskization problem， basically the training problem。

Is going to become a convicts task。Meaning that we can efficiently solve it。给。

So the con of the learning intelligence depends on two key properties。

 The first one is the hinge loss。 the use of hinge loss that I mentioned。 And secondly。

 it depends on on， on basically this linear hyperplane。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_21.png)

![](img/3a5fc73f0faccf081f0c1b009a7858f6_22.png)

Model that I'm adopting as my classifier， okay。Now。

 this linear model is is is useful when the data is linearly separable。

 But if I give you an example where the data is not linearly separable。

 let's say I have one minus here。Something like this。

 where the positive class is surrounded by the negative。Negative care。

 This is not a linear superior model。So this is not a linear server problem。 Therefore。

 the linear hardware paper is not going to be a really good classifier for this case。So， what we。

Can do is to replace this simple linear relation。With something more complicated， for instance。

 we can replace it with a deep model。A highly known nonlinear model。Okay。

 that will typically increase the， again， the representation power of our model。

 But the cache is that is going to result in。No conves。Training test。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_24.png)

Okay， so that's one that's the first example。The second example is is called linear regression， okay。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_26.png)

So in particular， you can imagine that I have a bunch of data points。That头。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_28.png)

Very， very represented with the linear。Model， okay。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_30.png)

And my goal。Is to leverage these data points。To learn this linear。Reian relationship。Okay。

 so what are the elements of our problem。Again， we have our features。X is a collection of features。

 Okay， so in R D。The labels now could in general， be real valued。So， they're not necessary。

Plus 1 and minus-4。对。We also assume that， as I mentioned here。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_32.png)

The relationship between the features and labels is typically following a linear。

Model meaning that the label is just the inner product between X and some unknown parameter W that we hope to learn。

 We hope to find it by leveraging some， some data points。 Okay。

 sometimes we also include an noise term。 Okay， so basically the the then the labels that we see are noisy。

 Okay， so they don't always provide the the correct。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_34.png)

Labelbel， but the noise is small and manageable。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_36.png)

Such that if we label， if we leverage our our training data， we should be able to。

To learn this relationship， hopefully， very。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_38.png)

Is it the unefficient。Okay， so what's the other。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_40.png)

Element that is of essential to talk about。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_42.png)

That's nothing but the， but the loss function。 Okay。

 which losses are we going to use to fit our model to the train data。

 And typically in linear regression， we use their square loss。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_44.png)

对。So again， we we capture how well we can fit a specific sample。Xowe O。By looking at this squares。

Now， the nice thing about this problem is that again。

 if we use a linear model and if we use a square loss。

 the empiricalimization problem is going to become a conve convex task。

Which basically means that we should be able to solve it very， very efficiently。But again。

 one drawback here is that the relationship may not be as noise as linear as I'm。

 as I'm depicting here。 For instance， I could have。A highly nonlinear。Relationships， so obviously。

 my linear model is not gonna be。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_46.png)

A good fit。或者。No the your model。Such as this one。Is going to be able to fit the data much。

 much better。对요。And we can do this in practice。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_48.png)

By replacing this simple， linear relationship。With a much more complicated and and nonlinear model。

 for instance， using a deep learning architecture。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_50.png)

And the catch is that this is going to typically be an noncomx training task。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_52.png)

![](img/3a5fc73f0faccf081f0c1b009a7858f6_53.png)

Alright， the third example is also a classification example。 But for historical reason。

 it's called regression。Okay， but in fact， what we are doing。

 we are performing binary classification。 and that's the problem of logistic regression， okay。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_55.png)

![](img/3a5fc73f0faccf081f0c1b009a7858f6_56.png)

So in particular， what we are assuming is that they say we have some again。Positive class。反正。

A negative case here。Such that。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_58.png)

I can use like a S shape model， if you will。To classify them。 Okay， so。This side are all plus。

 and this side are all minuses。Okay， so therefore， the goal is to learn the specifics of this S shape model okay。

哦。Al， so what are the elements of the routeor Again， We have features。 Again。

 these could be collections of pixels of an image， okay。We have labels。 We can use plus 1 and -1。

 or we can use 01。 It doesn't really matter much。 So here I'm using 01 to denote the two different classes that I。

 I have in this， in this problem。And we are sort of assuming the following relationship between the features and labors。

 We are assuming that that could be represented by a sigmoid or logistic function。Or activation。

 So this S shaped model that I talked about is essentially capture with this relation。

 And this is called the soid function or logistic function， which is very， very important in。

 in machine learning and learning。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_60.png)

The way to make sense of this is to think of。This quantity， one over one plus exponential。

As the probabilityty。That the label of x is1。So this quantity。

 which incidentally is always between 0 and 1。I's gonna say the probability that X the level of x is equal to one or not。

 So if this is very， very large， then it means that it is， it is very likely。

That X belongs to the class of ones。 For instance， X is very lucky that X is a car。

 the the image of a car。On the other hand， if this quantity is very low near 0。

 that means that it is unlikely for x to be an image of a car。 So therefore。

 it belongs to the other class。Now， a natural loss function to optimize here。

Its called the binary cross entropy loss， okay。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_62.png)

This， in some， captures the difference difference between two distributions， if you will， Okay。

 and this is something that we're going to talk about it a little bit more when we talk about classification again。

 but in the context ofing deeping models。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_64.png)

![](img/3a5fc73f0faccf081f0c1b009a7858f6_65.png)

But in some again， So the way to think of this is that that this is a notion that captures the distance between。

呃 to。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_67.png)

Distributions。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_69.png)

In particular， if I leverage this during my training process。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_71.png)

This is gonna be this is going to learn a model that can very well fit the。

 the training data that I have， meaningan that ideally， if the training is done successfully。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_73.png)

![](img/3a5fc73f0faccf081f0c1b009a7858f6_74.png)

This is going to return a value which is very， very close to1 or even v。

For all the examples that I have in the training data that belong to the first class。

 and it's going to return a value which is0 or very。

 very close to0 for all the examples that I have in my training data that belong to the order class。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_76.png)

Okay， now。Again， like the other two examples we talked about。嗯。

This is going to lead to a convex optimization problem。

 So our training problem is going to be become a convex problem and could be solved very。

 very efficiently as long as we again use this a specific way to represent the relationship between the features and labels。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_78.png)

![](img/3a5fc73f0faccf081f0c1b009a7858f6_79.png)

And as long as we are leveraging the binary carcenttropy loss。Like the previous examples。In practice。

 this is not gonna be powerful in many cases。In representing again。

 the relationship between the features and labels。 So what we tend to do is that we replace this linear relationship。

With something more complex and nonlinear， such as a deep learning model。

 And that would result in a non convex training task。Now， one question here that we may ask is that。

 okay， these examples are simple， So we may not be able to leverage them in in in， in， in practice。

 right， So then why are we talking about them。And the reason for that is that this gives us the way to talk about the。

 the process of deploy models in particular。You can think of differing as finding a much。

 much better representation of the original。Training data， in particular。

 I have the original features。 Let's call it X。Maybe if I just look at X， I'm not gonna be able to。

 again， crack the the the learning task。But if I have a very powerful dip model。

 what I can do is that I can feed this image， let's say， into a dip model。 And instead。

 I can find a much， much better representation。Of。Of， of the input image， I can extract very。

 very useful features from that image， such that。If I feed this to one of these examples we talk about。

 let's say linear。Rereion。Logistic regression。Which depends on again。

 whether you are talking about a regressionreation problem or a classification problem。

After finding this useful。Features extracting these useful features from the data。

 thanks to leveraging a deploy model。You should be able to perform very well。So， therefore。

Despite the simplicity of these， these models， there are still lots of useful concepts that will be leveraging When we talk about learning problems in the context of differing。

 notably， the， the loss function that we introduce here。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_81.png)

![](img/3a5fc73f0faccf081f0c1b009a7858f6_82.png)

![](img/3a5fc73f0faccf081f0c1b009a7858f6_83.png)

These relations that we talked about here， such as the the sigmma functions。

 Sigma activations are something that we're going to build upon。



![](img/3a5fc73f0faccf081f0c1b009a7858f6_85.png)

When we， as we are progressing in this course。

![](img/3a5fc73f0faccf081f0c1b009a7858f6_87.png)

So that's basically the end of our lecture on the basics of machine learning procedure。

In the next lecture， we're going to start talking about some of our training algorithms。 notably。

 we're going to talk a bit about the gradient descent algorithm。What's see you next time。

