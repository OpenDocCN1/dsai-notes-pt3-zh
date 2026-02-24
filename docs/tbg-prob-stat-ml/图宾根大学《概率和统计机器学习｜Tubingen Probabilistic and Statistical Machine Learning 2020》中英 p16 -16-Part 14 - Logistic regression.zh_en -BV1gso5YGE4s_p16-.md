# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p16 -16-Part 14 - Logistic regression.zh_en -BV1gso5YGE4s_p16-

![](img/7a935592ef8ca19958a3e167444c8456_0.png)

The next classification algorithm that we want to look at is logistic regression。😊。



![](img/7a935592ef8ca19958a3e167444c8456_2.png)

And despite the fact that it is called regression， it is a classification algorithm。



![](img/7a935592ef8ca19958a3e167444c8456_4.png)

It is also one of the traditional classic algorithms， but as opposed to linear discriminant analysis。

 it's still used a lot also in practice， it's a very simple algorithm。

 but often it is quite effective。😊。

![](img/7a935592ef8ca19958a3e167444c8456_6.png)

![](img/7a935592ef8ca19958a3e167444c8456_7.png)

We start as follows。 So again， we want to solve a classification problem on RD。



![](img/7a935592ef8ca19958a3e167444c8456_9.png)

So we， our data list in R。

![](img/7a935592ef8ca19958a3e167444c8456_11.png)

Our output label is again plus or minus1 were in binary classification and because we want to have a linear model。

 we have again the same function space as before the space induced by all the hyperplanes on our original space。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_13.png)

![](img/7a935592ef8ca19958a3e167444c8456_14.png)

![](img/7a935592ef8ca19958a3e167444c8456_15.png)

What we want to do is empiricalgri risk minimization。



![](img/7a935592ef8ca19958a3e167444c8456_17.png)

And we have already seen that the square loss essentially corresponds to linear discriminant analysis。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_19.png)

![](img/7a935592ef8ca19958a3e167444c8456_20.png)

And now we want to use a different loss function named with the logistic loss function。



![](img/7a935592ef8ca19958a3e167444c8456_22.png)

The logistic loss function is defined as follows。The loss for input data x between the prediction f of x and the true label or the true class label when classification y。

Is defined as a log of1 plus e to the minus y times f of x。



![](img/7a935592ef8ca19958a3e167444c8456_24.png)

And if you plot that function。

![](img/7a935592ef8ca19958a3e167444c8456_26.png)

The plot looks as follows and here I have to explain what is really on the x axis of this plot because it's a bit confusing on the x axis of this plot we always plot the product y times f of x and if you think about it if you have a correct classification f of x so f of x is the function that you use to produce your suggested classification result and in the end we are going to look at the sine of this function if the function is positive we say it's class plus1 if the function is negative we say it's class minus-1。



![](img/7a935592ef8ca19958a3e167444c8456_28.png)

![](img/7a935592ef8ca19958a3e167444c8456_29.png)

![](img/7a935592ef8ca19958a3e167444c8456_30.png)

![](img/7a935592ef8ca19958a3e167444c8456_31.png)

![](img/7a935592ef8ca19958a3e167444c8456_32.png)

![](img/7a935592ef8ca19958a3e167444c8456_33.png)

![](img/7a935592ef8ca19958a3e167444c8456_34.png)

And if you now look at the product between y and f of x。

 it turns out that if this product is positive。

![](img/7a935592ef8ca19958a3e167444c8456_36.png)

Then our classification was correct because there are two cases if y is plus 1 f of x is plus is positive。

 then the product y times f of x is positive and also we have made a correct prediction。



![](img/7a935592ef8ca19958a3e167444c8456_38.png)

![](img/7a935592ef8ca19958a3e167444c8456_39.png)

![](img/7a935592ef8ca19958a3e167444c8456_40.png)

And the same if the true label is -1 and our function has a negative sign。

 then the product of y times f of x is again positive。 and again， we also made a correct prediction。



![](img/7a935592ef8ca19958a3e167444c8456_42.png)

The other cases， say y is -1 and our function has a positive value。

 then the product y times f of x is is a negative number。

 and this indicates that we made a wrong decision with our function F。



![](img/7a935592ef8ca19958a3e167444c8456_44.png)

And now we will see on the next slide maybe I go to the next slide to see it better there are many。

 many different loss functions in classification and here is a plot that shows many of them and we will see many of them during the course of this lecture what you have here on the x axis you have always so we plot as we had before the product of y times f of x。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_46.png)

![](img/7a935592ef8ca19958a3e167444c8456_47.png)

![](img/7a935592ef8ca19958a3e167444c8456_48.png)

0 is here。In this part， everything that is on the right hand side of0 are points where I made a correct decision。

😊，And everything that is on the left side is where I make a wrong decision。

And now I can try to plot a loss function and show how much do I punish a certain function if it makes a certain decision。

And this might depend on the function value f of x because y always has the absolute value 1。

 so it's plus 1 or minus1， so going to the right hand side of this plot means that f of x increases and going to the left hand means that also the absolute value to the negative side of f of x increases。



![](img/7a935592ef8ca19958a3e167444c8456_50.png)

![](img/7a935592ef8ca19958a3e167444c8456_51.png)

![](img/7a935592ef8ca19958a3e167444c8456_52.png)

![](img/7a935592ef8ca19958a3e167444c8456_53.png)

。And maybe lets look at the first loss function that is sort of the obvious one for classification。

 the 01 loss， it essentially says whenever I predict it correctly， this loss is 0。

 it is the black function here。😊。

![](img/7a935592ef8ca19958a3e167444c8456_55.png)

![](img/7a935592ef8ca19958a3e167444c8456_56.png)

![](img/7a935592ef8ca19958a3e167444c8456_57.png)

Whenever I predict wrongly the loss is1， no matter how I come to my prediction what is the function value f of x I don't care。

 I only look at the sign if the sign is correct， I don't incur a loss， if the sign is incorrect。

 I incur a loss of 1。

![](img/7a935592ef8ca19958a3e167444c8456_59.png)

![](img/7a935592ef8ca19958a3e167444c8456_60.png)

Well， this is sort of the one loss function that is from a theoretical point of view。

 the natural loss function for classification。 and we have also used it， for example。

 when we define a base classifier。😊。

![](img/7a935592ef8ca19958a3e167444c8456_62.png)

![](img/7a935592ef8ca19958a3e167444c8456_63.png)

![](img/7a935592ef8ca19958a3e167444c8456_64.png)

Now， in practice， this loss function is often very annoying because it's， as you can see already。

 it's again， a discrete loss function。 So it's typically not possible to optimize it。

 So we look for different loss functions。😊。

![](img/7a935592ef8ca19958a3e167444c8456_66.png)

![](img/7a935592ef8ca19958a3e167444c8456_67.png)

And we have seen here， do I have the squared loss。 I don't really have the squared loss here I。



![](img/7a935592ef8ca19958a3e167444c8456_69.png)

![](img/7a935592ef8ca19958a3e167444c8456_70.png)

The trunccade， it's squared loss。 Okay， let's look at the different loss functions。

 So what I'm interested in now is the logistic loss。



![](img/7a935592ef8ca19958a3e167444c8456_72.png)

And this is sort of the purple line here。 So it's this one。It's hard to distinguish reded purple。

 but this purple is here。 this line。 So it decreases like on this side of on the positive correctly classic classified examples。

 it's not a big difference， but for the negatively classified examples。

The wrongly classified example is the purple line essentially more or less increases in a linear fashion。

😊，And now the funny thing is if you look at this plot all these loss functions do not stop punishing if we are on the correct side of the hyperplane so all these points here are have been classified correctly but for example the purple line still attachedes some error to these points because this is the loss function it says and what is the loss I incur if I have a positive data point and say y times f of x is 1 I still incur a loss of about 0。

4 maybe。😊。

![](img/7a935592ef8ca19958a3e167444c8456_74.png)

![](img/7a935592ef8ca19958a3e167444c8456_75.png)

And the fact and this is the reason why we do that is because we want to drive essentially the classification the results far away from the hyperplane。

 so the larger f of x in absolute value if we're the correct side of the hyperplane the smaller the loss is at least for the logistic loss so in the end it vanishes but there's always a tiny bit of loss。

 but the further we away from a hyperplane， the more sure we are that we are really on this side of the hyperplane and not on the other side and then we incur a smaller loss。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_77.png)

![](img/7a935592ef8ca19958a3e167444c8456_78.png)

![](img/7a935592ef8ca19958a3e167444c8456_79.png)

![](img/7a935592ef8ca19958a3e167444c8456_80.png)

Whereas if we go to this site where we have wrongly classified a point。

 essentially we punish linear so if we go to the wrong side of a hyperplane we essentially punish by the amount by which we are on the wrong side in a linear fashion。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_82.png)

![](img/7a935592ef8ca19958a3e167444c8456_83.png)

![](img/7a935592ef8ca19958a3e167444c8456_84.png)

![](img/7a935592ef8ca19958a3e167444c8456_85.png)

。There are other loss functions that we are going to see。

 for example the hinge loss and that is the loss used by the support vector machine。

 it acts somewhat similarly to the logistic loss， at least for the examples that have been classified wrongly it also increases linearly。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_87.png)

![](img/7a935592ef8ca19958a3e167444c8456_88.png)

But then it keeps on decreasing linearly until were a bit away from from the hyperplane。

 this is going to be called a margin。 So as long as we are still close to the hyperplane。

 we still incur a certain loss， but once were beyond this particular point。

 we don't incur loss any at all。

![](img/7a935592ef8ca19958a3e167444c8456_90.png)

![](img/7a935592ef8ca19958a3e167444c8456_91.png)

But this is what we' are going to look at in future。 For now， we want to look at the logistic loss。😊。



![](img/7a935592ef8ca19958a3e167444c8456_93.png)

![](img/7a935592ef8ca19958a3e167444c8456_94.png)

And now we want to consider the empirical risk minimization framework。

So we want to find the best linear function under the logistic loss。

The first observation is that there is no closed form solution for this problem。

 So what you can do is you can plug it into your optimization solver and the nice thing about the logistic loss is that it leads to a convex optimization problem。

 So this is easy to solve。😊，And if you want to prove why this is convex。

 you can look at the Hassian matrix and prove that the Hassian matrix is positive definite。

You might want to look into a textbook if you really want to do that。

So you can use your favorite convex however。And so， of course。

 people have tried to figure out what are the best solves that you can use in this case。

 And the Newton refsson algorithm is one that works particularly well in this case。

 But as I said before， we are not going to discuss the optimization algorithms in detail here。

So this is all about logistic regression， but now why in the first place would someone come up with a logistic loss function。

 it sounds like a completely arbitrary choice， why would you define a loss function in such a way。😊。

And here's， again， a connection to the patient kind of approach。In this approach。

 we do not make a full model of the joint probability distribution or the class conditional distributions between x and Y。



![](img/7a935592ef8ca19958a3e167444c8456_96.png)

![](img/7a935592ef8ca19958a3e167444c8456_97.png)

We only， so this is what would happen in the generative approach。

 We are in a discriminative approach where we are only interested in the probability of observing a certain output label Y。



![](img/7a935592ef8ca19958a3e167444c8456_99.png)

![](img/7a935592ef8ca19958a3e167444c8456_100.png)

Given the input X。

![](img/7a935592ef8ca19958a3e167444c8456_102.png)

And now here's a particular model that people can choose。

 so that the model is 1 over1 plus e to the minus y f of x。



![](img/7a935592ef8ca19958a3e167444c8456_104.png)

And again， F has the same form as before and this function， this is called the logistic function。

 and it is used in many， many different contexts， and it looks like this。



![](img/7a935592ef8ca19958a3e167444c8456_106.png)

![](img/7a935592ef8ca19958a3e167444c8456_107.png)

So it is close to 0 here。 It is close to one here。 And then there's a smooth transition that brings it from 0 to 1。



![](img/7a935592ef8ca19958a3e167444c8456_109.png)

Now， why， again， would use want to use this logistic function here as sort of maybe a more intuitive。



![](img/7a935592ef8ca19958a3e167444c8456_111.png)

![](img/7a935592ef8ca19958a3e167444c8456_112.png)

A kindin of plot。 So here consider we are in a two dimensional case。 What you see on this slide here。

 we have the data points of one class， and here we have the data points of one other class。

And now consider a projection scenario。 So were a linear classification。 So as we said before。

 this is equivalent to saying we project on one particular vector。

 the normal vector of our hyperplane。 and then we try to put the threshold be such that the hyperplane cuts in the middle of these two classes。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_114.png)

So we consider the projection， this is what I've plotted here。

And now this probabilistic model essentially says there is a certain likelihood of belonging to one and the other class and this likelihood on this side it is very so this is maybe the likelihood of class plus one sos on this side of the threshold here it's very unlikely that you belong to class plus one but the likelihood increases and here it's very likely that you belong to class plus one。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_116.png)

![](img/7a935592ef8ca19958a3e167444c8456_117.png)

And as intuition， this is maybe as in this height example for male and female people。

 like there's the two classes， male and female people。 and in the middle between these two classes。

 there's a certain transition。 So if you're in the middle between the classes。

 it's not really clear whether you're male or female， if you just look at the weight。😊。



![](img/7a935592ef8ca19958a3e167444c8456_119.png)

![](img/7a935592ef8ca19958a3e167444c8456_120.png)

![](img/7a935592ef8ca19958a3e167444c8456_121.png)

Or the height of a person And but the further you go to the extreme case。

 is the more clear you are that you really belong to this particular class。

 but you still cannot be 1 hundred0% sure in sort of the intuition between the or behind this logistic model is you never can be 1 hundred0% sure there's always a tiny probability that you're wrong。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_123.png)

![](img/7a935592ef8ca19958a3e167444c8456_124.png)

But and this probability increases towards the middle between the two classes and then you and then on the other side。

 the further you go outside， again， you're more sure to be on the other side on the on on this other。

 to belong to this other class。

![](img/7a935592ef8ca19958a3e167444c8456_126.png)

![](img/7a935592ef8ca19958a3e167444c8456_127.png)

Yeah。And sort of the value of this P of y given Y X is X tells us how far we are from this decision surface。

 This is what I've just been explaining。

![](img/7a935592ef8ca19958a3e167444c8456_129.png)

Now， we want to maximize the probability for a certain class。

 given the input value under this particular model。



![](img/7a935592ef8ca19958a3e167444c8456_131.png)

![](img/7a935592ef8ca19958a3e167444c8456_132.png)

And you can now see by deing the formulas that this corresponds to minimizing a certain loss function。

😊，Namely， it is the logistic loss function。

![](img/7a935592ef8ca19958a3e167444c8456_134.png)

So， so again， we have this kind of coincide or not coincidence， but this translation。

 we start with a model based approach right down in this case， only the。



![](img/7a935592ef8ca19958a3e167444c8456_136.png)

Yeah， let's go back， sorry。

![](img/7a935592ef8ca19958a3e167444c8456_138.png)

Here， we just write down。And the conditional posterior distribution given of the label。

 given the input。

![](img/7a935592ef8ca19958a3e167444c8456_140.png)

And。

![](img/7a935592ef8ca19958a3e167444c8456_142.png)

Maximizing this probability。It's the same as minimizing。A loss function。 And in this case。

 it's a luisticos。And this is where it comes from， where where the logistic loss function comes from。



![](img/7a935592ef8ca19958a3e167444c8456_144.png)

。This is more or less the same plot as we have before so here we have our data set this is the decision function here we decide for class minus-1 here we decide for class plus 1 and this is what the loss would be that you would have depending on what you predict for these particular points。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_146.png)

Now， this is essentially logistic regression。

![](img/7a935592ef8ca19958a3e167444c8456_148.png)

As in regular as in or in in linear regression， you can now also add some kind of regularization if you like to so you could use again。

 the two norm of omega as in rich regression to punish to sort of regularize your problem to get maybe solutions that are not as as variant have not as such a high variance as before。

 you could use the one norm as in NAso。 and in the end。

 then you simply solve the standard regularized risk minimization problem， minimize your loss。



![](img/7a935592ef8ca19958a3e167444c8456_150.png)

![](img/7a935592ef8ca19958a3e167444c8456_151.png)

![](img/7a935592ef8ca19958a3e167444c8456_152.png)

On the training data plus your regularization， and you need to fix this regularization trade of constant Lada typically by cross validation。



![](img/7a935592ef8ca19958a3e167444c8456_154.png)

![](img/7a935592ef8ca19958a3e167444c8456_155.png)

The reason why one often choose this L1 or L 2 penalization is at least these are convex functions。

 And we know that the logistic losses convex。So if you have look。



![](img/7a935592ef8ca19958a3e167444c8456_157.png)

A convex regularized as well。 Then the whole problem is still convex， and we can solve it。



![](img/7a935592ef8ca19958a3e167444c8456_159.png)

This is all I want to say about logistic regression and there's lots of stuff in textbooks。

 if you like， and I think for applying this algorithm for now it's sort of enough maybe a bit to the history of this algorithm。

😊。

![](img/7a935592ef8ca19958a3e167444c8456_161.png)

![](img/7a935592ef8ca19958a3e167444c8456_162.png)

There's a very nice and historic account， account of this whole algorithm。

 the origins of logistic regression。😊。

![](img/7a935592ef8ca19958a3e167444c8456_164.png)

And this has been written in 2002。Apparently this is what I've I've read in this paper I didn't know it before。

 it dates back to the 19th century of a person called Perre Hoonsishut。

 well I don't know this sounds like a but it's your name maybe I have no clue。

 it well I don't speculate on the nationality of this person I don't know it。😊，嗯。

And this has been published sort of around the 1850s， then it has been rediscovered in 1920。

And then there are millions of variations of this kind of algorithm。And in fact。

 something that I also want to point out in 1973， there is this economist Daniel McFin。

 who draw connections between logistic regression and。Economic decision theory。

And then this is a person who has been， who has earned the Nobel Pri for economy for economy in the year 2000。

And essentially he has been working on models for analyzing discrete choices and logistic regression is just one aspect of little piece in this whole picture that he has been drawing。

 but this is quite interesting so even logistic regression is an old algorithm there are still things to say about this algorithm so much to say that you can win a Nobel prize by saying all these things。

😊，Okay， this is all I wanted to say about logistic regression。 Thank you。



![](img/7a935592ef8ca19958a3e167444c8456_166.png)

![](img/7a935592ef8ca19958a3e167444c8456_167.png)

And so it's almost done right。