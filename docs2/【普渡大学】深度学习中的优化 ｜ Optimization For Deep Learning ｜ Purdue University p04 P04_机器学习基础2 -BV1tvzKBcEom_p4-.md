# 【普渡大学】深度学习中的优化 ｜ Optimization For Deep Learning ｜ Purdue University p04 P04_机器学习基础2 -BV1tvzKBcEom_p4-

🎼，🎼Yeah。Welcome back。 So last time we talked about the framework of machine learning。

 We talked about forming a training problem during which we aim to minimize the average loss over the training data。

 We also talked about population loss， right，Essential。

 the measure we use to assess whether the solution we learn。

During the training is gonna be performed well on newance in data。 Okay。

 and population loss was nothing but the loss over the entire。

 the average loss over the entire universe， okay。And we called basically the training problem as the empirical risk minimization problem。

 And the reason for that is that during the training。

 we basically form an empirical approximation of the population loss。

 Now we want to see how good is solving E RM。 Okay， essentially， how good is training， right。

 So how good is the model we learn during the training in terms of performing on on thin data。

 So how generalizable the patterns that we learn during the training are。



![](img/fc35729017339a318f3fd8eb38b3589f_1.png)

But one challenge is that the E RM problem itself cannot be solved exactly in many cases。

 And that's especially true when we talk about deeping models， optimizing deeping models。

So we're going to talk about some sorts of errors here。

That determine how good our learning is going to be， okay。So let's talk some notation。



![](img/fc35729017339a318f3fd8eb38b3589f_3.png)

Lets W hat be an approximate or suboptimal solution to the empirical risk minimization problem。

 So this is basically what you expect to learn when you optimize your deploy model。 Okay。

 so this is the base of the， the deploy model that you're gonna find。



![](img/fc35729017339a318f3fd8eb38b3589f_5.png)

After training is complete， okay。Now let W bar and W star。



![](img/fc35729017339a318f3fd8eb38b3589f_7.png)

Be the minimizers of the population loss， The average loss over the entire universe that obviously。

 we cannot have access to。And the empirical loss that we have access to， right。

 So this is the loss we form by looking at our training data。



![](img/fc35729017339a318f3fd8eb38b3589f_9.png)

No。What do we need in order to assess the learning is good。 Do we need to bond this quantity。



![](img/fc35729017339a318f3fd8eb38b3589f_11.png)

So， this is essentially。The the population loss of the model that we learn。So optimally。

 by solving the training problems optimally。 So that's basically F bar evaluated a W hat。Minus。

The performance of the model that we could have learned。



![](img/fc35729017339a318f3fd8eb38b3589f_13.png)

If we had access to the population loss。 So in some sense。

 you can imagine that this is best thing we could do， right。

 So if we had access to to the population loss that we obviously don't。 Okay。

 so this is like a learning gap that we want to， want to bond， okay。



![](img/fc35729017339a318f3fd8eb38b3589f_15.png)

No。In many cases。To bond and error them。So you can think of it as an error term or a quantity of interest。

 What we do are we add and subtract certain quantities， if you will。



![](img/fc35729017339a318f3fd8eb38b3589f_17.png)

呃 to。Relate this quantity of interest to some tangible concepts。 Okay， so in particular。

 to some error terms。That we have potentially a better understanding of。To do that here。

 So please bear with me。 We in particular， are going to add and subtract three terms。 Okay。

 so these terms are the performance of my suboptimal model on the empirical loss。



![](img/fc35729017339a318f3fd8eb38b3589f_19.png)

![](img/fc35729017339a318f3fd8eb38b3589f_20.png)

![](img/fc35729017339a318f3fd8eb38b3589f_21.png)

The performance of the models。呃。The optimizer of the empirical laws。And finally。

 the performance of the optimizer of the population loss on the on the empirical loss， okay。

But the merit of this story is that after you add and subtract these terms。

The estimation error that we aim to bond is going to be sort of upper bonded。背啊。Certain terms。对。都。

The first thing is this。So again， F F is our empirical loss。 So the first term is nothing but。

The essentially， how will we do。During an optimization process。

 So this is called the optimization error。

![](img/fc35729017339a318f3fd8eb38b3589f_23.png)

Okay， because this just says that how well your suboptimal solution W hat is compared to the optimal solution WS star。

Okay。The second term。If you look at it for the fixed solution W had。

 it is comparing the empirical loss and the population loss。



![](img/fc35729017339a318f3fd8eb38b3589f_25.png)

Therefore， this is called the empirical approximation。There。Epriiccro estimation error。

 because this essentially says that。

![](img/fc35729017339a318f3fd8eb38b3589f_27.png)

How well your training data， your empirical training data can represent the entire universe for all models W。



![](img/fc35729017339a318f3fd8eb38b3589f_29.png)

Similarly， the third term。Is also。Related to empirical approximation error。Because again。

 I'm comparing the empirical loss F。

![](img/fc35729017339a318f3fd8eb38b3589f_31.png)

And the population was F bar。 But instead of evaluating their difference that W hat。

 I'm evaluating that on some other model， W star。 Okay， so if I had。



![](img/fc35729017339a318f3fd8eb38b3589f_33.png)

If if I knew that the empirical approximation error responded for all W。I could be able。

To bond both termme 2 and the 3。Okay。Alright， so term1， basically the optimization or error。

 term 2 and term 3 are related to the empirical approximation error。

And let's talk about the third term。 the last term。 Okay。

 so here I have if the population loss evaluated at W star minus sorry。

 the empirical loss evaluated at W star minus the empirical loss evaluated。



![](img/fc35729017339a318f3fd8eb38b3589f_35.png)

At W bar， okay。

![](img/fc35729017339a318f3fd8eb38b3589f_37.png)

So what let's recall what are W star and W bar。 Okay， so W star is nothing but the minimizer of F。

And W bar。

![](img/fc35729017339a318f3fd8eb38b3589f_39.png)

Is the minimizer of F plus。 now here， I'm evaluating them on F。So。

Because W star is the minimizer of F。 It must be that the value of F at W store is less than all other ws。

In particular。This is less than。The loss。Of W bar。Therefore， this last term。Is non positive。Okay， so。

Sometimes it's useful to get rid of non non positiveitive terms， non positive error terms。

 And this is an example of a case that I'm， I'm dropping this term。 So in particular。

 you can safely remove this term， right。Okay。So therefore， what's the outcome of this analysis。

 This analysis says that the estimation error， which is essentially our way of characterizing how good the model that we learn。

If we so optimally solve the。

![](img/fc35729017339a318f3fd8eb38b3589f_41.png)

，The training problem。Is going to be bonded by basically， two terms。

The first term is optimization error。 How well you can。Solve the empirical re music problem。

 How well you can perform the training step。And。Emirical approximation error。

 How well your training data can represent the entire universe。



![](img/fc35729017339a318f3fd8eb38b3589f_43.png)

Okay。Now， these two error attemptss can be controlled by better training algorithms and also having access to better or larger data sets。

 Okay， so in particular， it is。

![](img/fc35729017339a318f3fd8eb38b3589f_45.png)

It is intuitive。To see that if I have better algorithms that can solve the training problem faster and sooner。

呃。And potentially find higher quality solutions。 I can reduce the opt optimization error。

 And similarly， if I have training algorithms， right。

 that can leverage the data better or if I have access to more data points。

 I should be able to get a better approximation empirical approximation to the population loss。



![](img/fc35729017339a318f3fd8eb38b3589f_47.png)

![](img/fc35729017339a318f3fd8eb38b3589f_48.png)

So therefore， I should be able to control the as step。



![](img/fc35729017339a318f3fd8eb38b3589f_50.png)

Alright， so we talked about basically the estimation error。

 We talked about the optimization error and also the empirical approximation error。However。

 all of this is dependent upon which parametric model we are using。

To learn the relationship between the， the features and labels。



![](img/fc35729017339a318f3fd8eb38b3589f_52.png)

In particular， if the models that we we are leveraging。



![](img/fc35729017339a318f3fd8eb38b3589f_54.png)

Have a very high capacity。 They're very powerful。They should be able to represent very complex relationships between features and labels。

 Okay， so we should expect better learning performance on the other Hanform model is， is very simple。

 It's not powerful。 It may not be able to learn。

![](img/fc35729017339a318f3fd8eb38b3589f_56.png)

![](img/fc35729017339a318f3fd8eb38b3589f_57.png)

The complicated relationship between the features and labels。



![](img/fc35729017339a318f3fd8eb38b3589f_59.png)

Despite having access to very advanced training algorithms。

 despite having access to a large amount of data， high quality data。 Okay。

 so this is another source of error。 therefore for representation error， okay。

 so let's again recall our notation， W bar was the minimizer of the population loss。 the loss。

 the average loss over the entire universe。And what we assume is that there exists this unknown relationships。

 A star between their features and labels， okay。As I mentioned， if our model is not powerful enough。

 even by minimizing the population loss， even if I had access to the entire universe。

 we may not be able to fully learn the relationship between the features and labels。Mathematically。

 that means that a star。And our parametric model， when using W bar are not necessarily the same。

 Okay， that depends on how powerful our para models are。 Okay。

 and this leads to the representation error。 that we define by the difference between F bar at W bar and let's say some quantity that I denoted by F opt。



![](img/fc35729017339a318f3fd8eb38b3589f_61.png)

![](img/fc35729017339a318f3fd8eb38b3589f_62.png)

![](img/fc35729017339a318f3fd8eb38b3589f_63.png)

An effort， you can think of it as the loss if we knew the through relation。And many times。

 we can assume that if bar is is 0 or approximately 0， okay。都。Basically。

 this discussion can be demonstrated by the following figure。 So let's assume that this is some A SR。

 the true relationship between the features and labels that I want to learn， okay， now。



![](img/fc35729017339a318f3fd8eb38b3589f_65.png)

This is the entire class of functions， A W。That time leveraging during the training process。No。

This distance is nothing but the representation error。Okay。In this case。

 my model is not powerful enough。Therefore， regardless of what how well I do during the training。

 regardless of。How much data points you have access to。

I may not be I'm not gonna be able to reduce this error。 Okay， because my， the。

 the family of the apartmenting model that I'm leveraging does not include a S star at all。 Okay。

 on the other hand。

![](img/fc35729017339a318f3fd8eb38b3589f_67.png)

![](img/fc35729017339a318f3fd8eb38b3589f_68.png)

If I had access to the say another class of functions， this denoted by A Tilla。

This is now a much more powerful class。So it does include aR in it。 Therefore。

 I'm not going have any representation error here in this example。

 And if I have access to better training algorithms。

 if I have access to an adequate number of data points， I should be able to perform very well。



![](img/fc35729017339a318f3fd8eb38b3589f_70.png)

![](img/fc35729017339a318f3fd8eb38b3589f_71.png)

![](img/fc35729017339a318f3fd8eb38b3589f_72.png)

So the learning is gonna be very， very successful。

![](img/fc35729017339a318f3fd8eb38b3589f_74.png)

Rightright。Now， this representation error can can be controlled。

 So we've had this observation in practice。 and we also have some theoretical understanding of that that as our deep learning models become deeper。

And Voer。They tend to become more powerful。So that means that the representation is is gonna go go down。

Alright， so in summary， there are three important source of error。During the learning process。

 So the total learning error， if you will， is basically the sum of the representation error。

 how powerful our models are or deeping models are in terms of capturing the relationships or arbitrary relationships。

 if you will。Optimization or training error。How good our algorithms are in terms of minimizing the empirical loss。

 And finally， empirical approximation error， okay。嗯。



![](img/fc35729017339a318f3fd8eb38b3589f_76.png)

Basically， how good our data is in terms of representing the universe of all。データボイス。

And these are sorts of errors， as I mentioned， that hopefully we can control by designing more powerful。

 more advanced models， by designing more advanced training algorithms。嗯。



![](img/fc35729017339a318f3fd8eb38b3589f_78.png)

That can leverage the data better。

![](img/fc35729017339a318f3fd8eb38b3589f_80.png)

So in the next lecture， we're going to talk about a few simple examples of machine learning problems to solidify these concepts。

Thank you。