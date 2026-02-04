# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P62：P62 StatsLearning Lect11d 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/e39f64b4bca740e48d78ea76d302e059_0.png)

Okay， so we've learn about support vector machines in the full generality。

 let's see how it works how they work on a simple example。

 which is the heart data where we've got a bunch of variables。

 not too many 10 or so variables and and。

![](img/e39f64b4bca740e48d78ea76d302e059_2.png)

![](img/e39f64b4bca740e48d78ea76d302e059_3.png)

There's two classes， heart disease or no heart disease。

 and we use to support vector machines to classify。



![](img/e39f64b4bca740e48d78ea76d302e059_5.png)

![](img/e39f64b4bca740e48d78ea76d302e059_6.png)

So in these two panels， we show the performance。

![](img/e39f64b4bca740e48d78ea76d302e059_8.png)

On the training data。And next slide we' show on the test data。



![](img/e39f64b4bca740e48d78ea76d302e059_10.png)

So what we are showing are ROC curves， so we've seen these before， but just to remind you。



![](img/e39f64b4bca740e48d78ea76d302e059_12.png)

![](img/e39f64b4bca740e48d78ea76d302e059_13.png)

Once we fit our function， which is initially going to be a linear function。



![](img/e39f64b4bca740e48d78ea76d302e059_15.png)

We threshold at zero and that's a decision boundary if the function is bigger than zero we'll classify to one class。

 otherwise less than zero to the other clause。

![](img/e39f64b4bca740e48d78ea76d302e059_17.png)

![](img/e39f64b4bca740e48d78ea76d302e059_18.png)

And you'll make a number of errors。 You'll make some false positives。And false negatives， yeah。

 we actually look at the false positives and the true positives。



![](img/e39f64b4bca740e48d78ea76d302e059_20.png)

![](img/e39f64b4bca740e48d78ea76d302e059_21.png)

Well， as you change the threshold， you're going to change the false positives and true positives。



![](img/e39f64b4bca740e48d78ea76d302e059_23.png)

And what the ROC curve does is trace out false the true positives versus the false positives as you change the threshold。

 and that gives you a curve。

![](img/e39f64b4bca740e48d78ea76d302e059_25.png)

![](img/e39f64b4bca740e48d78ea76d302e059_26.png)

And if you think about it， what you'd really like is a curve that really hugs this northwest current corner。

 this one seems to be doing pretty well。

![](img/e39f64b4bca740e48d78ea76d302e059_28.png)

![](img/e39f64b4bca740e48d78ea76d302e059_29.png)

Okay， and a way of comparing classifies is to see which one gets closer to the corner。



![](img/e39f64b4bca740e48d78ea76d302e059_31.png)

Okay。So that's called the ROC curve。 The name comes from an engineering term。

 but it's not really relevant in terms of how we use it today and remember the so called the AU。

 the area under the curve is the usual measure of how close the curve gets to the northwest corner good point Rob So AUC。



![](img/e39f64b4bca740e48d78ea76d302e059_33.png)

![](img/e39f64b4bca740e48d78ea76d302e059_34.png)

![](img/e39f64b4bca740e48d78ea76d302e059_35.png)

![](img/e39f64b4bca740e48d78ea76d302e059_36.png)

Area under。

![](img/e39f64b4bca740e48d78ea76d302e059_38.png)

Under the curve is a summary measure of how close you get to the corn here。

 if the area under the curve is one， notice this is a unit cube that means this curve exactly gets into the corner。



![](img/e39f64b4bca740e48d78ea76d302e059_40.png)

![](img/e39f64b4bca740e48d78ea76d302e059_41.png)

![](img/e39f64b4bca740e48d78ea76d302e059_42.png)

And there's a 45 degree line。You should always be above the 45 degree line， so A or be between 0。

5 and1。

![](img/e39f64b4bca740e48d78ea76d302e059_44.png)

So in this left panel， we've got this the linear support vector classifier， that's the red curve。



![](img/e39f64b4bca740e48d78ea76d302e059_46.png)

![](img/e39f64b4bca740e48d78ea76d302e059_47.png)

And we compare in it to linear disccrminants analysis here， which is the blue curve。

 and on the training data， they do pretty much the same。

 Maybe the support vectors got a slight edge in a few places。



![](img/e39f64b4bca740e48d78ea76d302e059_49.png)

![](img/e39f64b4bca740e48d78ea76d302e059_50.png)

In the left panel， the right，s in the right panel。

![](img/e39f64b4bca740e48d78ea76d302e059_52.png)

We compare the linear support vector classify， which is the rate curve to the SVM using a radial kernel with different values of gamma。



![](img/e39f64b4bca740e48d78ea76d302e059_54.png)

![](img/e39f64b4bca740e48d78ea76d302e059_55.png)

And you'll notice that。

![](img/e39f64b4bca740e48d78ea76d302e059_57.png)

It's not monotone。So when gamma is 10 to the minus1， we seem to do really well。



![](img/e39f64b4bca740e48d78ea76d302e059_59.png)

嗯。

![](img/e39f64b4bca740e48d78ea76d302e059_61.png)

When gammas 10 to the -2。That's the green curve。

![](img/e39f64b4bca740e48d78ea76d302e059_63.png)

We do。 we do worse than the red curve。And 10 to the -3， even worse again。

So remember the larger gamma。The more restrictive。 sorry， the more wggly。

 the decision boundary and so。

![](img/e39f64b4bca740e48d78ea76d302e059_65.png)

![](img/e39f64b4bca740e48d78ea76d302e059_66.png)

This is ordered in complexity， so when gamma is large，10 to the -1。

 we're doing the best and then as we decrease gamma。

 we start doing worse and worse and the linear classifier sort of comes in between in the middle of that regime。



![](img/e39f64b4bca740e48d78ea76d302e059_68.png)

![](img/e39f64b4bca740e48d78ea76d302e059_69.png)

![](img/e39f64b4bca740e48d78ea76d302e059_70.png)

Which means gamma is another tuning parameter for the support vector class。

 And just keep in mind what they're telling us， it's not really a fair comparison in the right panel。

 right， because the。

![](img/e39f64b4bca740e48d78ea76d302e059_72.png)

![](img/e39f64b4bca740e48d78ea76d302e059_73.png)

The gamma smaller has more complexity so it's going to fit more and this is a bigger yeah。

 so a training year comparison isn't a fair comparison。



![](img/e39f64b4bca740e48d78ea76d302e059_75.png)

![](img/e39f64b4bca740e48d78ea76d302e059_76.png)

Right， so we didn't do it yet， but if we made gamma even much bigger。

 we'd probably get an area under the curve of one。

![](img/e39f64b4bca740e48d78ea76d302e059_78.png)

![](img/e39f64b4bca740e48d78ea76d302e059_79.png)

So of course， we know we should look at test data and so yeah。

 we put aside 80 observations as test observations and fit the classifierifies on the training data and now compared to the now we look at ROC curves on the test data。



![](img/e39f64b4bca740e48d78ea76d302e059_81.png)

![](img/e39f64b4bca740e48d78ea76d302e059_82.png)

![](img/e39f64b4bca740e48d78ea76d302e059_83.png)

And again， linear versus LD， it looks like the S support vector classifiedify does a little bit better just by a small amount。

 but notice that this ROC curve is not as good as the previous one on the training data。

 Of course that was。

![](img/e39f64b4bca740e48d78ea76d302e059_85.png)

![](img/e39f64b4bca740e48d78ea76d302e059_86.png)

![](img/e39f64b4bca740e48d78ea76d302e059_87.png)

![](img/e39f64b4bca740e48d78ea76d302e059_88.png)

Overfitting a bit。And。

![](img/e39f64b4bca740e48d78ea76d302e059_90.png)

In the right hand panel， we look at the different support vector machines again。

 and now the one with the biggest value of gamma actually does the worst。



![](img/e39f64b4bca740e48d78ea76d302e059_92.png)

![](img/e39f64b4bca740e48d78ea76d302e059_93.png)

So， while it was。Doing the best on the training data that actually does the worst on the test data。



![](img/e39f64b4bca740e48d78ea76d302e059_95.png)

And yeah， the linear support vector machine does pretty much the best。



![](img/e39f64b4bca740e48d78ea76d302e059_97.png)

And the most regularized SVM is with gamut 10 to the minus。You can't see that number。

 but three is doing about the same。

![](img/e39f64b4bca740e48d78ea76d302e059_99.png)

Okay， so these are tuning parameters and we'd have to use all our usual tools for deciding。



![](img/e39f64b4bca740e48d78ea76d302e059_101.png)

![](img/e39f64b4bca740e48d78ea76d302e059_102.png)

If we had to pick a value for gamma， we may use cross validation or validation data set to pick it。



![](img/e39f64b4bca740e48d78ea76d302e059_104.png)

As well as the the cost parameter to see。

![](img/e39f64b4bca740e48d78ea76d302e059_106.png)

So。With a kernel， we've got two tuning parameters with a linear support vector classifier。

 we've just got one， which is C。

![](img/e39f64b4bca740e48d78ea76d302e059_108.png)

![](img/e39f64b4bca740e48d78ea76d302e059_109.png)

Okay， so everything we've talked about so far is for two classes separating Hyplan two classes。

 so what do we do if we have more than two classes？



![](img/e39f64b4bca740e48d78ea76d302e059_111.png)

![](img/e39f64b4bca740e48d78ea76d302e059_112.png)

Well， unfortunately things get a little bit ad hoc here， and so there's two general approaches。😊。



![](img/e39f64b4bca740e48d78ea76d302e059_114.png)

And the one's called OVA。

![](img/e39f64b4bca740e48d78ea76d302e059_116.png)

One versus all。It's an acronym。And so the idea is you fit K different support two class support vector machine classifiers。

Each class versus the rest， so you just relabel all the other classes as a mega minus1 class and say the target class as class plus one。



![](img/e39f64b4bca740e48d78ea76d302e059_118.png)

You fit a support vector classifier and you do that with each of the classes as being the plus one and all the others being the minus one。

 so that means you'll fit K different classifiers。

![](img/e39f64b4bca740e48d78ea76d302e059_120.png)

![](img/e39f64b4bca740e48d78ea76d302e059_121.png)

Which means you'll have K different functions。AndNow when you come to classify a new point。

 you evaluate those K different functions and you'll classify to the class， which is the largest。



![](img/e39f64b4bca740e48d78ea76d302e059_123.png)

![](img/e39f64b4bca740e48d78ea76d302e059_124.png)

So that's the one approach。And the other approach is OVO。



![](img/e39f64b4bca740e48d78ea76d302e059_126.png)

Which is one versus1， which means you do all K choose2 pairwise classifiers。



![](img/e39f64b4bca740e48d78ea76d302e059_128.png)

So。

![](img/e39f64b4bca740e48d78ea76d302e059_130.png)

if k is， for example， 10， that means you have to fit k choose2， which is4545。

 45 classifiers and so obviously that gets big as the number of classes gets big。



![](img/e39f64b4bca740e48d78ea76d302e059_132.png)

And so now you've got all these paywise classifiers and to classify a new point。

 what you do is you evaluate every single one of these classifiers。



![](img/e39f64b4bca740e48d78ea76d302e059_134.png)

![](img/e39f64b4bca740e48d78ea76d302e059_135.png)

And you see which class wins the most pairwise competitions。



![](img/e39f64b4bca740e48d78ea76d302e059_137.png)

And that's the cost to which you classify。So these see ad hoc。



![](img/e39f64b4bca740e48d78ea76d302e059_139.png)

The actual mechanisms aren't quite as ad hoc as they sound。

 and so you can explain this from a somewhat theoretical point of view。

 but that's what gets done in practice one of these two The number of classes is too large。

 usually OVA otherwise OVO tends to get favored。

![](img/e39f64b4bca740e48d78ea76d302e059_141.png)

![](img/e39f64b4bca740e48d78ea76d302e059_142.png)

![](img/e39f64b4bca740e48d78ea76d302e059_143.png)

Okay， near the end of this section， we will end up by comparing support vector machines to logistic regression So remember logistic regression。



![](img/e39f64b4bca740e48d78ea76d302e059_145.png)

![](img/e39f64b4bca740e48d78ea76d302e059_146.png)

What did solve classification problems by modeling the probabilities of the classes？



![](img/e39f64b4bca740e48d78ea76d302e059_148.png)

![](img/e39f64b4bca740e48d78ea76d302e059_149.png)

We support vector machines were optimizing。Going directly for the decision boundary。

 They seem very different。 Well it turns out they're not as different as one might think。



![](img/e39f64b4bca740e48d78ea76d302e059_151.png)

![](img/e39f64b4bca740e48d78ea76d302e059_152.png)

So if we write the linear function in this form， as we've done before。It turns out we can。



![](img/e39f64b4bca740e48d78ea76d302e059_154.png)

We can rephrase。The optimization problem for the support vector classifier in the following form。



![](img/e39f64b4bca740e48d78ea76d302e059_156.png)

Now， this is somewhat technical， but there's a lost function。



![](img/e39f64b4bca740e48d78ea76d302e059_158.png)

Between y and F of x。

![](img/e39f64b4bca740e48d78ea76d302e059_160.png)

Summed over the observations。 So this is。Similar to， but not the same as a log like it。

 And there's a penalty on the coefficients。 lookss like it's a quadratic penalty like a rich penalty here。

 and there's a tu in parameter lambda。

![](img/e39f64b4bca740e48d78ea76d302e059_162.png)

![](img/e39f64b4bca740e48d78ea76d302e059_163.png)

Now this loss function is a somewhat strange beast that's known as the hinge loss。

 and maybe it's better just to show you a picture。

![](img/e39f64b4bca740e48d78ea76d302e059_165.png)

So its primary argument is y times F of x。 Remember， this is what we call now the margin。

 This is the quantity we'd like to be positive。

![](img/e39f64b4bca740e48d78ea76d302e059_167.png)

![](img/e39f64b4bca740e48d78ea76d302e059_168.png)

And。The bigger it is， the further a point is away from its margin。



![](img/e39f64b4bca740e48d78ea76d302e059_170.png)

Okay。So。This is the loss that we assign to that quantity。



![](img/e39f64b4bca740e48d78ea76d302e059_172.png)

In this formulation， if it's bigger than one， we sign 0 loss。 So that's 0 over year。

 But if it's less than one， and particularly if it goes negative， it means。



![](img/e39f64b4bca740e48d78ea76d302e059_174.png)

![](img/e39f64b4bca740e48d78ea76d302e059_175.png)

In all these regimes， we were on the wrong side of our margin。



![](img/e39f64b4bca740e48d78ea76d302e059_177.png)

We pay an increase in linear loss。So that's called the hingelo and if you optimize this problem。

 this criterion with respect to the betas。

![](img/e39f64b4bca740e48d78ea76d302e059_179.png)

![](img/e39f64b4bca740e48d78ea76d302e059_180.png)

The solution is equivalent to the sports vector machine。 Oh， that's not obvious， right。

 It' it's pretty hard。

![](img/e39f64b4bca740e48d78ea76d302e059_182.png)

The derivation is not so easy。 really， Ru， you can't see just from looking。 No， it's very hard。 Well。

 it's not very hard， but it's quite hard to map this to the other one， but。



![](img/e39f64b4bca740e48d78ea76d302e059_184.png)

![](img/e39f64b4bca740e48d78ea76d302e059_185.png)

What's more important， and it's not necessarily that this is the way one does it。

 it's just illustrative， because it allows us to compare to logistic regression。



![](img/e39f64b4bca740e48d78ea76d302e059_187.png)

![](img/e39f64b4bca740e48d78ea76d302e059_188.png)

Because with logistic regression， we also fit in a linear function。 So the function looks the same。



![](img/e39f64b4bca740e48d78ea76d302e059_190.png)

Remember there， the linear function was the lo of the probability of class 1 versus class -1 in this case。



![](img/e39f64b4bca740e48d78ea76d302e059_192.png)

So and for logistic regression， we had a log likelihood plus we could have a log likelihood plus a rich penalty。

And the log likelihood is given by this green curve over here。



![](img/e39f64b4bca740e48d78ea76d302e059_194.png)

And you'll notice it looks very similar。

![](img/e39f64b4bca740e48d78ea76d302e059_196.png)

In this formulation， it tapers off to be horizontal over year。



![](img/e39f64b4bca740e48d78ea76d302e059_198.png)

It asympts to be linear over year。 but instead of having a sharp corner over here。

 it has a gentler corner。

![](img/e39f64b4bca740e48d78ea76d302e059_200.png)

Which means you can also think of logistic regression as having a kind of soft margin。



![](img/e39f64b4bca740e48d78ea76d302e059_202.png)

And and that it focuses more and points close to the margin and points further away。



![](img/e39f64b4bca740e48d78ea76d302e059_204.png)

So there's a lot of similarity between logistic regression and support vector machines。



![](img/e39f64b4bca740e48d78ea76d302e059_206.png)

And。And if you want to learn more about that， you may want to look at our book elements of statistical learning where we go into this in a little bit more detail。

 It's one thing to add the fact that the hinge loss has that corner is what gives it the support vector property right is the alpha thatter some which is zero。

 whereas the smooth loss doesn't have that property。

 You don't get support points Good point job and you may get points whose sort of weight gets close to zero。

 but not exactly zero。

![](img/e39f64b4bca740e48d78ea76d302e059_208.png)

![](img/e39f64b4bca740e48d78ea76d302e059_209.png)

![](img/e39f64b4bca740e48d78ea76d302e059_210.png)

![](img/e39f64b4bca740e48d78ea76d302e059_211.png)

![](img/e39f64b4bca740e48d78ea76d302e059_212.png)

![](img/e39f64b4bca740e48d78ea76d302e059_213.png)

Okay， so which do you use， Support Victor machine or logistic regression。



![](img/e39f64b4bca740e48d78ea76d302e059_215.png)

Will just sum up yeah。 so if the classes are nearly separable。

 the support vector machine tends to do better than logistic regression and so does linear discriminants analysis Lo regression actually breaks down if the classes are exactly separable。



![](img/e39f64b4bca740e48d78ea76d302e059_217.png)

![](img/e39f64b4bca740e48d78ea76d302e059_218.png)

![](img/e39f64b4bca740e48d78ea76d302e059_219.png)

In that case， you'd have to use some kind of regularization with logistic regression。



![](img/e39f64b4bca740e48d78ea76d302e059_221.png)

But support， that's a regime where support vector machines do well。



![](img/e39f64b4bca740e48d78ea76d302e059_223.png)

When the classes aren't separable where there somewhat， there's quite a bit of overlap。



![](img/e39f64b4bca740e48d78ea76d302e059_225.png)

Logistic regression， perhaps with a rich penalty or with a less so penalty。



![](img/e39f64b4bca740e48d78ea76d302e059_227.png)

Tends to do better。And and it's more useful。 they similar。 The results will be similar。

 but it's more useful because it's actually estimating probabilities for you。



![](img/e39f64b4bca740e48d78ea76d302e059_229.png)

![](img/e39f64b4bca740e48d78ea76d302e059_230.png)

For nonlinear boundaries， you can use kernel support vector machines and they popular。

 you can use the same kernels with logistic regression and LDA as well。

 but the computations tend to be more expensive， and so in those scenario support vector machines tend to be used。



![](img/e39f64b4bca740e48d78ea76d302e059_232.png)

![](img/e39f64b4bca740e48d78ea76d302e059_233.png)

![](img/e39f64b4bca740e48d78ea76d302e059_234.png)

So here we are at the end of the session。 Rob， do you have anything to add Well I was going to add about you know there's sort of a no- freeee lunch principle with support vector machines we saw a way with kernels to finesse to get a solution essentially in high dimensions for free。

 but one price you pay is you don't get a feature selection you get for the laso for L1 penalties right where we explicitly put a penalty on the features and as a result a lot of the features are set to zero with support vector machines。

 one disadvantages it uses all the features and it doesn't easily select which features are important。

 So for high dimensional problems that can be a drawback not so much for the classification performance but the interpretation of the solution。



![](img/e39f64b4bca740e48d78ea76d302e059_236.png)

![](img/e39f64b4bca740e48d78ea76d302e059_237.png)

![](img/e39f64b4bca740e48d78ea76d302e059_238.png)

And the other point that Trevor mentioned about probability， that's a really important point。

 like if you're working on a cancer diagnosis problem。

 very often you don't just want to classify but you want to know the probabilities of the estimated class probabilities。



![](img/e39f64b4bca740e48d78ea76d302e059_240.png)

![](img/e39f64b4bca740e48d78ea76d302e059_241.png)

![](img/e39f64b4bca740e48d78ea76d302e059_242.png)

Because if something's got a probability being cancer of 0。51 as opposed to 0。99。

 the classification is the same， but the implications in the actual situation are very different。

 so class probabilities are very important and support vector machines don't provide an easy way of getting those。



![](img/e39f64b4bca740e48d78ea76d302e059_244.png)

The community and support vector machines have tried to address these problems with sort of post post our ad hoc kind of add on something called recursor feature elimination。

 and also they have ways of actually getting probabilities by fitting logistic regressions after fitting support vector machines。

 but we can do that directly with。For example， Le Su regularized logistic regression。

