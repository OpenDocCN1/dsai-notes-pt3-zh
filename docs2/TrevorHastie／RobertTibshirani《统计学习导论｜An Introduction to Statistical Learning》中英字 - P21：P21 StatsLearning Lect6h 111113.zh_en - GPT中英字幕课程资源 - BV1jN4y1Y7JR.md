# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P21：P21 StatsLearning Lect6h 111113.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

Okay， so that's discriminants analysis when we use Gaussian densities。

 but now the form that we wrote down is quite general and you can use other estimates of densities and plug them into this rule。



![](img/d194df07a854c29ad12dbefd4185dbe5_1.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_2.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_3.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_4.png)

And， and get classification rules。

![](img/d194df07a854c29ad12dbefd4185dbe5_6.png)

So up to now we've been using Gaussian densities with the same variance for the x's in each class。



![](img/d194df07a854c29ad12dbefd4185dbe5_8.png)

What if the， the variances are different in each class。Well。

 you can plug those forms in and then remember we had that magic cancellation because of the equal variances。

 Well， when the variances are different in each class。😊，There's no the quadratic terms don't cancel。

 And so now your discrimininate functions are going to be quadratic functions of X。



![](img/d194df07a854c29ad12dbefd4185dbe5_10.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_11.png)

Okay。So that's one form it's called quadratic discriminants analysis。



![](img/d194df07a854c29ad12dbefd4185dbe5_13.png)

Another thing you can do。

![](img/d194df07a854c29ad12dbefd4185dbe5_15.png)

Is you， and especially this is useful when you have a large number of features， like the 4000。



![](img/d194df07a854c29ad12dbefd4185dbe5_17.png)

Also that Rob mentioned when you really wouldn't want to estimate these large variance covariance matrices。



![](img/d194df07a854c29ad12dbefd4185dbe5_19.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_20.png)

You can assume that in each class， the density factors into a product of densities。



![](img/d194df07a854c29ad12dbefd4185dbe5_22.png)

That that's amounts to saying that the variables are conditionally independent in each of the classes。



![](img/d194df07a854c29ad12dbefd4185dbe5_24.png)

And if you do that and plug it into this formula here。



![](img/d194df07a854c29ad12dbefd4185dbe5_26.png)

You get something known as the Naive Bay Classifier。



![](img/d194df07a854c29ad12dbefd4185dbe5_28.png)

For linear discriminance analysis， this means that the covariances sigma sub K are diagonal。



![](img/d194df07a854c29ad12dbefd4185dbe5_30.png)

And。

![](img/d194df07a854c29ad12dbefd4185dbe5_32.png)

Instead of estimating the covariance matrix has got， if you got P variables。

 it's got P squared parameters。

![](img/d194df07a854c29ad12dbefd4185dbe5_34.png)

But if you assume this diagonal that that it's diagonal， and you need to estimate P parameters again。

 Now， a lot of assumption seems very crude。 I mean，''s assumption is wrong。

 Its naive based classifier is actually very useful in high dimensional problems。



![](img/d194df07a854c29ad12dbefd4185dbe5_36.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_37.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_38.png)

And it's one actually will we turn to later in different forms， right？



![](img/d194df07a854c29ad12dbefd4185dbe5_40.png)

So。In fact， we'd probably think it's always wrong， wouldn't we be wrong。



![](img/d194df07a854c29ad12dbefd4185dbe5_42.png)

And so what happens is， you know， we end up with quite。



![](img/d194df07a854c29ad12dbefd4185dbe5_44.png)

Flattened and maybe biased estimates for the probabilities。 But in terms of classification。

 you just need to know which probability is the largest to classify so you can tolerate quite a lot of bias and and still get good classification performance。



![](img/d194df07a854c29ad12dbefd4185dbe5_46.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_47.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_48.png)

And what you get in return is much reduced variance from having to estimate far fewer parameters。



![](img/d194df07a854c29ad12dbefd4185dbe5_50.png)

And then there's much more other general forms where we don't assume Gaussian at all。

 we we can estimate the densities using in our favorite density estimation technique and then go and plug them back into this formula。

 and that'll give you a classification rule。

![](img/d194df07a854c29ad12dbefd4185dbe5_52.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_53.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_54.png)

And it's a very general approach that can be used。 and in fact。

 many of the classifiers that we we know we can understand from this point of view。



![](img/d194df07a854c29ad12dbefd4185dbe5_56.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_57.png)

So yeah， we have it。 Quadratic discriminant analysis uses a different covarience matrix for each class。

 And so there's no cancellation of the sigma。 So the discriminant functions now have。



![](img/d194df07a854c29ad12dbefd4185dbe5_59.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_60.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_61.png)

This distance term that involves sigma sub K， which is for the K class。



![](img/d194df07a854c29ad12dbefd4185dbe5_63.png)

There's a term to do with the the prior probability。

 and there's a determined term that comes from the the covariance matrix。



![](img/d194df07a854c29ad12dbefd4185dbe5_65.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_66.png)

And you can see it gives you a curved discriminant boundary。

 and the quadratic terms matter here because they're different。



![](img/d194df07a854c29ad12dbefd4185dbe5_68.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_69.png)

Okay。And so in the left plot here。

![](img/d194df07a854c29ad12dbefd4185dbe5_71.png)

We see a case when the true boundary really should be linear。

 that's the dotted curve and in this case， of course linear discriminant analysis does a good job。

 quadratic discriminant analysis curve somewhat and gives a slightly bent boundary but it won't really affect misclassification performance much in the righthand plot and now this other hand。



![](img/d194df07a854c29ad12dbefd4185dbe5_73.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_74.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_75.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_76.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_77.png)

The， true data came from a situation where the covari answerss were different。



![](img/d194df07a854c29ad12dbefd4185dbe5_79.png)

The， the base decision boundary is。Curved and the quadratic disccrminment analysis pretty much got it。

 whereas linear disccrminants analysis gives you quite a different boundary in that case。



![](img/d194df07a854c29ad12dbefd4185dbe5_81.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_82.png)

Quratic discriminant analysis is attractive if the number of variables is small。

 when the features the number of variables or features is large。

 you've got to estimate these big covariance matrices and things can break down and even for LDA can break down years where naive Bay becomes attractive。



![](img/d194df07a854c29ad12dbefd4185dbe5_84.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_85.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_86.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_87.png)

It makes a much stronger assumption， it assumes that the covariances in each of the classes。

 although different are diagonal。😊。

![](img/d194df07a854c29ad12dbefd4185dbe5_89.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_90.png)

And so that's much fewer parameters and now when you look at the discriminant functions。

 because diagonal and Gaussian means that the densities are independent and so we have this product here when we take logs。

 we get a relatively simple expression。

![](img/d194df07a854c29ad12dbefd4185dbe5_92.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_93.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_94.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_95.png)

Which is in each class， there's a contribution of the feature from the mean for the class scaled by the variance。

 there's the determinant term and there's the prior term。



![](img/d194df07a854c29ad12dbefd4185dbe5_97.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_98.png)

And so this is a。This is the discrimininate function for the Caith class for naive Bay。

 and you compute one of these for each of the classes。 then you classify。



![](img/d194df07a854c29ad12dbefd4185dbe5_100.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_101.png)

You can use mixed features for naive bay and in that case。

If if what we mean by that is some qualitative and some quantitative features and so for the quantitative ones。

 we'd use the Gaussian and for the qualitative ones， we'd replace the densities。

 the Gaussian densities by just histograms or probability mass functions in this case over the discrete categories。



![](img/d194df07a854c29ad12dbefd4185dbe5_103.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_104.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_105.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_106.png)

So naive Bayes is very handy from this point of view， and even though it has strong assumptions。

 it often produces good classification results because often once again in classification。

 we're mainly concerned about which class has the highest probability and not whether we got the probabilities exactly right。



![](img/d194df07a854c29ad12dbefd4185dbe5_108.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_109.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_110.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_111.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_112.png)

Okay， so。We've seen two forms of， of classification。

 logistic regression and linear discriminants analysis。 And we saw its generalizations。



![](img/d194df07a854c29ad12dbefd4185dbe5_114.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_115.png)

嗯。Now， it turns out， are they， How do they differ。it seems they may be similar similarities between the two。



![](img/d194df07a854c29ad12dbefd4185dbe5_117.png)

Now， it turns out you can show for linear discriminant analysis。😮。



![](img/d194df07a854c29ad12dbefd4185dbe5_119.png)

That if you take its， we had expression for the probabilities for each of the classes。

 So if you have two class， we can show that if you take the log odds。

 just like we did in logistic regression。

![](img/d194df07a854c29ad12dbefd4185dbe5_121.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_122.png)

Right， which is the log of the probability for class 1 versus the probability for class 2。



![](img/d194df07a854c29ad12dbefd4185dbe5_124.png)

It's a linear function of x。

![](img/d194df07a854c29ad12dbefd4185dbe5_126.png)

For two classes。So it's got exactly the same form as logistic regression。



![](img/d194df07a854c29ad12dbefd4185dbe5_128.png)

So they both give you linear logistic models。

![](img/d194df07a854c29ad12dbefd4185dbe5_130.png)

So the difference is in how the parameters are estimated。



![](img/d194df07a854c29ad12dbefd4185dbe5_132.png)

Logistic regression uses the conditional likelihood based on probability of Y given x。

 Remember it was using the probabilities of a1 or a0。



![](img/d194df07a854c29ad12dbefd4185dbe5_134.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_135.png)

嗯。Given X in each of the classes。

![](img/d194df07a854c29ad12dbefd4185dbe5_137.png)

And in machine learning， this is known as discriminative learning。



![](img/d194df07a854c29ad12dbefd4185dbe5_139.png)

Using the conditional distribution of Y given X， discriminant analysis。



![](img/d194df07a854c29ad12dbefd4185dbe5_141.png)

Turns out it's estimating these parameters。

![](img/d194df07a854c29ad12dbefd4185dbe5_143.png)

Over， using the full likelihood。Because it's using the， the， the distribution of x is and Y。



![](img/d194df07a854c29ad12dbefd4185dbe5_145.png)

Whereas logistic regression was only using the distribution of Ys。



![](img/d194df07a854c29ad12dbefd4185dbe5_147.png)

And in that case， it's known as generative learning。



![](img/d194df07a854c29ad12dbefd4185dbe5_149.png)

Remember， we model the， the， the， the means and variances of x in each of the classes。

 and we model the， the prior probabilities。 So that can be seen as modeling the joint distribution of x and Y。



![](img/d194df07a854c29ad12dbefd4185dbe5_151.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_152.png)

So that's one way of seeing what's different between the two。



![](img/d194df07a854c29ad12dbefd4185dbe5_154.png)

But despite these differences in practice， the results are often very similar。



![](img/d194df07a854c29ad12dbefd4185dbe5_156.png)

And you can use one method with the other， and you're going get very similar results。



![](img/d194df07a854c29ad12dbefd4185dbe5_158.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_159.png)

As a footnote， logistic regression can also fit quadratic boundaries。



![](img/d194df07a854c29ad12dbefd4185dbe5_161.png)

We use quadratic discriminants analysis to get quadratic boundaries。



![](img/d194df07a854c29ad12dbefd4185dbe5_163.png)

But we can fit quadratic boundaries by explicitly， including quadratic terms in the model。



![](img/d194df07a854c29ad12dbefd4185dbe5_165.png)

Just like we did in linear regression， in logistic regression。

 we can put in X squares and X I times X Js and， and terms like that。

 and just explicitly get a quadratic boundary。

![](img/d194df07a854c29ad12dbefd4185dbe5_167.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_168.png)

Okay， so。That's the end of this section。 That's an introduction to classification using these two very popular methods。

 And later on in the class， you're going to see that we're going to come back to some of these methods and look at more general versions of them and and build richer classification rules。

 And importantly， we'll discuss another very popular method called the support vector machine。

 which is another approach to classification。 And by way of coming attractions。

 the next section is going to be on cross foundation and bootstap。



![](img/d194df07a854c29ad12dbefd4185dbe5_170.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_171.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_172.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_173.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_174.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_175.png)

And in that section， we will get to meet Brad Efferron， who's our colleague。



![](img/d194df07a854c29ad12dbefd4185dbe5_177.png)

And also， it was my PhD supervisor many years ago， and it was the person who had invented the bootstrap。

 So he'll tell us a bit about。

![](img/d194df07a854c29ad12dbefd4185dbe5_179.png)

![](img/d194df07a854c29ad12dbefd4185dbe5_180.png)

The bootsstrrap and how he came about to how he proposed it in his 1980 paper， fantastic。



![](img/d194df07a854c29ad12dbefd4185dbe5_182.png)