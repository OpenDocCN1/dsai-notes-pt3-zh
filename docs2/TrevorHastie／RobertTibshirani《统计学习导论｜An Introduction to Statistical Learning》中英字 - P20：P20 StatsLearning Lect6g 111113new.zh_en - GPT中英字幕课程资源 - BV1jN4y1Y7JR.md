# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P20：P20 StatsLearning Lect6g 111113new.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/31e65549044e1df68a31e3971b731997_0.png)

Okay， so that was with a single variable。And usually， when we do classification。

 we got more than one variable。

![](img/31e65549044e1df68a31e3971b731997_2.png)

So now we're going to go to multivariate Gausss。

![](img/31e65549044e1df68a31e3971b731997_4.png)

So here's a picture of a Gaussian density when we've got two variables。



![](img/31e65549044e1df68a31e3971b731997_6.png)

So it's one of these。

![](img/31e65549044e1df68a31e3971b731997_8.png)

Fancy looking three dimensional plants。 It's beautiful， beautiful， isn't it。😊。



![](img/31e65549044e1df68a31e3971b731997_10.png)

The heights colour coded。Could you make a plot like this one？



![](img/31e65549044e1df68a31e3971b731997_12.png)

I could try and then you'd criticize it。

![](img/31e65549044e1df68a31e3971b731997_14.png)

You do criticize it。Ex。The beautiful thing is that R made this plot with very little w fromness。



![](img/31e65549044e1df68a31e3971b731997_16.png)

So there's two variables， X1 and x2。 And you can see the Gaussian density in in two dimensions looks like a bell function。



![](img/31e65549044e1df68a31e3971b731997_18.png)

![](img/31e65549044e1df68a31e3971b731997_19.png)

And this is left and case is the case when the two variables are uncorrelated。

 so it's just really like a bell。

![](img/31e65549044e1df68a31e3971b731997_21.png)

![](img/31e65549044e1df68a31e3971b731997_22.png)

And the right hand case is when there's correlation。 So now it's like a stretched be。

 You can see thiss positive correlation between X 1 and X 2。



![](img/31e65549044e1df68a31e3971b731997_24.png)

So those are pictures of the densities。 The formula for the density doesn't look nearly as pretty。

 And here it is over here。

![](img/31e65549044e1df68a31e3971b731997_26.png)

![](img/31e65549044e1df68a31e3971b731997_27.png)

And it's somewhat complex。 But you should go over this in great detail now， excruciating detail。

 please。😊。

![](img/31e65549044e1df68a31e3971b731997_29.png)

![](img/31e65549044e1df68a31e3971b731997_30.png)

I have a feeling that's a hint not to go into it in great detail。😊，Anyway。

 this is just a generalization of the formula we had for a single variable。

 This is called a covariance matrix。

![](img/31e65549044e1df68a31e3971b731997_32.png)

![](img/31e65549044e1df68a31e3971b731997_33.png)

And it's， if you， if you stay at this formula and you stare at the previous formula。

 you'll see that there's， there's somewhat similarity。

 especially if you know a bit of vector algebra。

![](img/31e65549044e1df68a31e3971b731997_35.png)

![](img/31e65549044e1df68a31e3971b731997_36.png)

嗯。If you go through the simplifications， if you know your linear algebra。

 you can form and do the cancellation similar to what we did before。

 you can form the discriminant function which is given over year。



![](img/31e65549044e1df68a31e3971b731997_38.png)

![](img/31e65549044e1df68a31e3971b731997_39.png)

![](img/31e65549044e1df68a31e3971b731997_40.png)

And it looks complex， but important thing to note is that it's， again， linear in x。

 Yes x alone multiplied by a coefficient vector。

![](img/31e65549044e1df68a31e3971b731997_42.png)

![](img/31e65549044e1df68a31e3971b731997_43.png)

And this isthe are or just constants。 So this， again， is a linear function。



![](img/31e65549044e1df68a31e3971b731997_45.png)

If the， if the maths beyond you don't let it bother you。 This is a linear function。

 and well make that more clear a little bit later on as well that this is a linear function。



![](img/31e65549044e1df68a31e3971b731997_47.png)

![](img/31e65549044e1df68a31e3971b731997_48.png)

In fact， we make it clear right here。 It might look complex。

 but this can just be written in this form of view。



![](img/31e65549044e1df68a31e3971b731997_50.png)

![](img/31e65549044e1df68a31e3971b731997_51.png)

Okay， it's a linear function。 So the C， K 0。 So this is a function for class K， C， K 0。



![](img/31e65549044e1df68a31e3971b731997_53.png)

![](img/31e65549044e1df68a31e3971b731997_54.png)

Is built up of all these pieces over year。 And then each of the coefficients of x1。

 x 2 up to X P come from this spot over year。

![](img/31e65549044e1df68a31e3971b731997_56.png)

![](img/31e65549044e1df68a31e3971b731997_57.png)

Remember， x is a vector in this case？And so you can expand this expression and get this。

 this term of here。

![](img/31e65549044e1df68a31e3971b731997_59.png)

And I think I've forgot to mention it before， what the idea of the discriminant function is you compute one of these for each of the classes and then you classify it to the class for which it's largest。



![](img/31e65549044e1df68a31e3971b731997_61.png)

![](img/31e65549044e1df68a31e3971b731997_62.png)

You pick the discriminant function。 That's largest。



![](img/31e65549044e1df68a31e3971b731997_64.png)

Well， we can draw other nice pictures for discriminant analysis。

 similar to the one dimension the one dimensional picture we do before。



![](img/31e65549044e1df68a31e3971b731997_66.png)

![](img/31e65549044e1df68a31e3971b731997_67.png)

So yeah， we've got two variables and three classes。



![](img/31e65549044e1df68a31e3971b731997_69.png)

And。We can't instead of showing those density plots， what we do is show contours in this case。

 of the density。 So here's the blue class。 And we show the contour of a particular level of probability。



![](img/31e65549044e1df68a31e3971b731997_71.png)

![](img/31e65549044e1df68a31e3971b731997_72.png)

![](img/31e65549044e1df68a31e3971b731997_73.png)

Okay， for the blue class。For the green class and for the orange class。



![](img/31e65549044e1df68a31e3971b731997_75.png)

Okay。And lo and behold， and the decision boundary is the dotted linear。



![](img/31e65549044e1df68a31e3971b731997_77.png)

And。

![](img/31e65549044e1df68a31e3971b731997_79.png)

It's really very pretty。 It， it shows you。Where you classify to blue versus orange。



![](img/31e65549044e1df68a31e3971b731997_81.png)

And it's exactly where it cuts where the con， the line goes exactly through the points where the contours are cut。



![](img/31e65549044e1df68a31e3971b731997_83.png)

Both for the orange to blue， for the， the blue to green and for the green to， to orange。



![](img/31e65549044e1df68a31e3971b731997_85.png)

![](img/31e65549044e1df68a31e3971b731997_86.png)

And you can see they all meet in the， in the middle over here。Right in the centre over here。



![](img/31e65549044e1df68a31e3971b731997_88.png)

And so if you knew the， the， the two densities。It would tell you exactly。 And， and in this case。

 like Gaussian， youd get the the exact decision boundaries。 Again。

 these are called the base decision boundaries。 These are the true decision boundaries。



![](img/31e65549044e1df68a31e3971b731997_90.png)

![](img/31e65549044e1df68a31e3971b731997_91.png)

![](img/31e65549044e1df68a31e3971b731997_92.png)

Now， of course， we don't。But we go ahead and estimate the parameters for the Gaussians in each of the class。

 using formulas similar to what we had before， but appropriate for this multivari case。



![](img/31e65549044e1df68a31e3971b731997_94.png)

![](img/31e65549044e1df68a31e3971b731997_95.png)

So in this case， we get to get the mean。For x 1 and x 2， for the blue class。



![](img/31e65549044e1df68a31e3971b731997_97.png)

It's about there for the green class， with data points about there。 for the orange class， say there。



![](img/31e65549044e1df68a31e3971b731997_99.png)

And， then we plug them into the formula instead of getting the the the dotted lines。

 we get the solid lines。 And in this case， it's remarkably close。



![](img/31e65549044e1df68a31e3971b731997_101.png)

![](img/31e65549044e1df68a31e3971b731997_102.png)

Now， these data were actually generated from a gasline distribution。

 So it's not too surprising that we got close。 but with relatively few points。

 we get decision boundaries that look pretty close to the， the， the， the real ones。



![](img/31e65549044e1df68a31e3971b731997_104.png)

![](img/31e65549044e1df68a31e3971b731997_105.png)

![](img/31e65549044e1df68a31e3971b731997_106.png)

You cannot learn about discriminant analysis without seeing Fser's iris data。

 It's maybe one of the most famous data sets around。



![](img/31e65549044e1df68a31e3971b731997_108.png)

![](img/31e65549044e1df68a31e3971b731997_109.png)

It studies three species of iris。

![](img/31e65549044e1df68a31e3971b731997_111.png)

These species are Cossa， Vererssic coloror and Virginiaica。

And they color coded in the scatter plot matrix。 again， with three colors in this case。



![](img/31e65549044e1df68a31e3971b731997_113.png)

![](img/31e65549044e1df68a31e3971b731997_114.png)

And there are four variables that are going to be used to try and automatically classify these。

 these three to these three classes。

![](img/31e65549044e1df68a31e3971b731997_116.png)

Sipple length。

![](img/31e65549044e1df68a31e3971b731997_118.png)

Sample width。Petal length and petal width。So these are aspects of the flower。



![](img/31e65549044e1df68a31e3971b731997_120.png)

And there's 50 samples in each class。

![](img/31e65549044e1df68a31e3971b731997_122.png)

Now， if you look at these scatter plots， you can see that there's some really good separation。

 for example， in this plot of petal length and petal width。

 the blue class really stands out as being different from from the other two classes。



![](img/31e65549044e1df68a31e3971b731997_124.png)

![](img/31e65549044e1df68a31e3971b731997_125.png)

They seem to be more confused in， in some of the plots。



![](img/31e65549044e1df68a31e3971b731997_127.png)

But and in summary， is slightly more separation。 But the idea here is to use all these variables together to come up with a discriminatory rule。



![](img/31e65549044e1df68a31e3971b731997_129.png)

![](img/31e65549044e1df68a31e3971b731997_130.png)

And， and， and classify。

![](img/31e65549044e1df68a31e3971b731997_132.png)

And so this was a motivated example that Fisher used in his first description of linear discriminant analysis。



![](img/31e65549044e1df68a31e3971b731997_134.png)

And， in fact。

![](img/31e65549044e1df68a31e3971b731997_136.png)

It's often known as Fisher's linear discriminant analysis。Importantly。

 what comes with discriminants analysis is a nice plot。



![](img/31e65549044e1df68a31e3971b731997_138.png)

Right， in this previous picture。

![](img/31e65549044e1df68a31e3971b731997_140.png)

There's four variables。 So we showed a scatterpl matrix of each variable against the wrist。



![](img/31e65549044e1df68a31e3971b731997_142.png)

But it turns out that there's a single plot that captures。



![](img/31e65549044e1df68a31e3971b731997_144.png)

The classification information for all of these variables。



![](img/31e65549044e1df68a31e3971b731997_146.png)

And here it is。And。I've got disccrminant variable 1 and disccrminant variable 2 is the horizontal and vertical axes。



![](img/31e65549044e1df68a31e3971b731997_148.png)

And it turns out these are linear combinations of the original variables。



![](img/31e65549044e1df68a31e3971b731997_150.png)

But they spatial in new combinations。

![](img/31e65549044e1df68a31e3971b731997_152.png)

And when you plot the variables against these two， you see really good separation。



![](img/31e65549044e1df68a31e3971b731997_154.png)

And these arise from actually performing the linear discriminant analysis。



![](img/31e65549044e1df68a31e3971b731997_156.png)

Because you've got three classes， what Fiser's linear discriminants analysis is really doing or Gaussian LDA is really doing。



![](img/31e65549044e1df68a31e3971b731997_158.png)

![](img/31e65549044e1df68a31e3971b731997_159.png)

Is it's measuring which centroid is the closest。

![](img/31e65549044e1df68a31e3971b731997_161.png)

But it's measuring in， in a distance that it takes into account the covariance of， of the variables。



![](img/31e65549044e1df68a31e3971b731997_163.png)

But ignoring the covariance for a moment。

![](img/31e65549044e1df68a31e3971b731997_165.png)

，The distance， the three centroids。

![](img/31e65549044e1df68a31e3971b731997_167.png)

Actually， lying in， a plane， a subspace of the four dimensional space。



![](img/31e65549044e1df68a31e3971b731997_169.png)

And it's really distance。 So if you have three points， they span a two dimensional subspace。



![](img/31e65549044e1df68a31e3971b731997_171.png)

And that's essentially what we plot in here is the two dimensional sub space。

 So seeing which class is closest。

![](img/31e65549044e1df68a31e3971b731997_173.png)

Really amounts to distance in that subspace。

![](img/31e65549044e1df68a31e3971b731997_175.png)

And that leads to these nice， low dimensional plots。



![](img/31e65549044e1df68a31e3971b731997_177.png)

And so we have three classes here。 We can make a two dimensional plot。

 and it captures exactly what's。

![](img/31e65549044e1df68a31e3971b731997_179.png)

What's important in terms of the classification。

![](img/31e65549044e1df68a31e3971b731997_181.png)

And， and when we have more than three classes， we can find still find two dimensional plots。

 But in that case， it doesn't capture all the information， the two dimensional plot。

 but we can find the best two dimensional plot for visualizing the discriminant rule。



![](img/31e65549044e1df68a31e3971b731997_183.png)

![](img/31e65549044e1df68a31e3971b731997_184.png)

And that's another important reason why linear discriminant analysis is very popular for multiclass classification。

 So keep in mind， this case， we had only four features，4 variables， right。

 And Discri analysis was a very attractive method。 But imagine we had 4000 features。 right then。



![](img/31e65549044e1df68a31e3971b731997_186.png)

![](img/31e65549044e1df68a31e3971b731997_187.png)

![](img/31e65549044e1df68a31e3971b731997_188.png)

![](img/31e65549044e1df68a31e3971b731997_189.png)

An ingredient what we just did was the covariance matrix。

 we had to plug in an estimate of the covariance matrix and if we had 4000 features。

 that covariance matrix would be of size 4000 by 4000。 Yes， that's that's a great point Rob。

 And you know we just can't carry out discriminants analysis without other modifications if the number of variables are very large and we're going to talk about some ways of doing that And later on in the class。

 we'll talk about even more ways。

![](img/31e65549044e1df68a31e3971b731997_191.png)

![](img/31e65549044e1df68a31e3971b731997_192.png)

![](img/31e65549044e1df68a31e3971b731997_193.png)

![](img/31e65549044e1df68a31e3971b731997_194.png)

![](img/31e65549044e1df68a31e3971b731997_195.png)

嗯。What we， we've talked about discriminator functions， which is telling you how you classify。

 But it turns out that you can turn these into probabilities very easily。



![](img/31e65549044e1df68a31e3971b731997_197.png)

![](img/31e65549044e1df68a31e3971b731997_198.png)

And is the expression over yet。

![](img/31e65549044e1df68a31e3971b731997_200.png)

And so remember， we got the decays by doing a lot of simplification。 Well。

 it turns out that those simplifications and cancellations hold exactly for computing the probabilities。



![](img/31e65549044e1df68a31e3971b731997_202.png)

![](img/31e65549044e1df68a31e3971b731997_203.png)

So in other words， those expressions we had earlier for。



![](img/31e65549044e1df68a31e3971b731997_205.png)

Computing the probabilities。It's go back to it。 for example， yes's a expression。

 Yeah that's used in computing the probabilities。

![](img/31e65549044e1df68a31e3971b731997_207.png)

![](img/31e65549044e1df68a31e3971b731997_208.png)

Where is it。 This， This is the， the expression for the single variable case with all these constants in that。

 that all the cancellation happens， and we get to。

![](img/31e65549044e1df68a31e3971b731997_210.png)

![](img/31e65549044e1df68a31e3971b731997_211.png)

This nice， simple expression of you， which just involves the discriminant functions， okay。



![](img/31e65549044e1df68a31e3971b731997_213.png)

So you see， you can see if you can actually show that as well。 It's not that hard to show。



![](img/31e65549044e1df68a31e3971b731997_215.png)

And so。We can not only does discriminant analysis give us a classified also gives us the probabilities。



![](img/31e65549044e1df68a31e3971b731997_217.png)

![](img/31e65549044e1df68a31e3971b731997_218.png)

嗯。When case 2， well classify to class 2， if these probabilities are bigger than 。5 else to class 1。

 just like in logistic regression。

![](img/31e65549044e1df68a31e3971b731997_220.png)

![](img/31e65549044e1df68a31e3971b731997_221.png)

Here's the credit data。嗯。

![](img/31e65549044e1df68a31e3971b731997_223.png)

And we produce， in this case， misclassification table。



![](img/31e65549044e1df68a31e3971b731997_225.png)

Okay。So this table is， is got。

![](img/31e65549044e1df68a31e3971b731997_227.png)

Along the horizontal， it's got the， the two status， so。It's a true default status， which is no。

 or yes。

![](img/31e65549044e1df68a31e3971b731997_229.png)

You can see we have 10，000 samples in the credit data。



![](img/31e65549044e1df68a31e3971b731997_231.png)

And in the vertical we've got the predicted status， no or yes。



![](img/31e65549044e1df68a31e3971b731997_233.png)

So， of course， we'd like everything to rely on the diagonal。



![](img/31e65549044e1df68a31e3971b731997_235.png)

It turns out we got a lot of the nose right， and， and。



![](img/31e65549044e1df68a31e3971b731997_237.png)

Not that many of the， the yes is， right。So on the diagonal is what you got correct。

 and the off diagonals is what you got incorrect。

![](img/31e65549044e1df68a31e3971b731997_239.png)

Nevertheless， overall， we make 2。75% misclassification errors here。



![](img/31e65549044e1df68a31e3971b731997_241.png)

Okay， so。This is called a confusion matrix that tells how well you did。



![](img/31e65549044e1df68a31e3971b731997_243.png)

Now， there's some caveats。 This is training error。

![](img/31e65549044e1df68a31e3971b731997_245.png)

Right， we， we fit the rule to these data。 And now we see how well it performs on these data。

 So we may be overfitting。

![](img/31e65549044e1df68a31e3971b731997_247.png)

Well， we've got 10000 training samples here， and we've only fit a handful of parameters。

 So it's very unlikely in this case that were overfitting for small training sets。

 that would be an issue。 and you need to have a separate test set。



![](img/31e65549044e1df68a31e3971b731997_249.png)

![](img/31e65549044e1df68a31e3971b731997_250.png)

![](img/31e65549044e1df68a31e3971b731997_251.png)

嗯。

![](img/31e65549044e1df68a31e3971b731997_253.png)

Another， another thing to note is that although 2。75% seems really good misclassification rate。



![](img/31e65549044e1df68a31e3971b731997_255.png)

![](img/31e65549044e1df68a31e3971b731997_256.png)

If we just use a very naive classification rule and said， I mean order always classify to the。

 the largest class。 In other words， classify according to the prior。



![](img/31e65549044e1df68a31e3971b731997_258.png)

![](img/31e65549044e1df68a31e3971b731997_259.png)

We'd only make 3。333% errors， right， because there's a predominance of， of no in this。

 in this data set， right。

![](img/31e65549044e1df68a31e3971b731997_261.png)

![](img/31e65549044e1df68a31e3971b731997_262.png)

The， the total number of nos is 333 out of out of 10000。



![](img/31e65549044e1df68a31e3971b731997_264.png)

Right， so this we call the null rate。 And so you always， you always use a bear in mind the。

 the null rate when， in getting excited about a misclassification error rate。



![](img/31e65549044e1df68a31e3971b731997_266.png)

![](img/31e65549044e1df68a31e3971b731997_267.png)

![](img/31e65549044e1df68a31e3971b731997_268.png)

The other thing to look at， though， is you can break the errors into different kinds。

 So of the true nose。

![](img/31e65549044e1df68a31e3971b731997_270.png)

We make。

![](img/31e65549044e1df68a31e3971b731997_272.png)

Po2% errors。 So we hardly ever misclassify a no。But of the yeses， we make a whopp in 75。7% errors。

 right， So the errors are very lopsided in this case。



![](img/31e65549044e1df68a31e3971b731997_274.png)

![](img/31e65549044e1df68a31e3971b731997_275.png)

And that's maybe not such a good idea。

![](img/31e65549044e1df68a31e3971b731997_277.png)

So。We。

![](img/31e65549044e1df68a31e3971b731997_279.png)

Break down these errors into， into finer categories。 So we call the false positive rate。



![](img/31e65549044e1df68a31e3971b731997_281.png)

The fraction of， of negative examples that are classified as positive， right。

 So they false positives。 In that case， that was the 2。2% in this case。



![](img/31e65549044e1df68a31e3971b731997_283.png)

![](img/31e65549044e1df68a31e3971b731997_284.png)

And the false negative rate， that's the fraction of positive examples that are classified as negative。



![](img/31e65549044e1df68a31e3971b731997_286.png)

The 75。7% in this case。

![](img/31e65549044e1df68a31e3971b731997_288.png)

Now， we produced the classification table by。Intuitively correct。 Classifying default is yes。



![](img/31e65549044e1df68a31e3971b731997_290.png)

嗯。If the probability of default was bigger than 05。



![](img/31e65549044e1df68a31e3971b731997_292.png)

Okay。But it gave us this very lopsided， false， positive and false negative rate。



![](img/31e65549044e1df68a31e3971b731997_294.png)

In some cases， especially for these kinds of screening examples。



![](img/31e65549044e1df68a31e3971b731997_296.png)

You， you may want to change the。

![](img/31e65549044e1df68a31e3971b731997_298.png)

The false positive and false negative rates and skew them to one side over the other。

 And you can do this by changing this threshold。 instead of classifying， in this case， to default。

 if it's bigger than 0。5， you can change a threshold and maybe make the threshold in this case smaller so that you can catch more of the。

 the high risk cases for default。

![](img/31e65549044e1df68a31e3971b731997_300.png)

![](img/31e65549044e1df68a31e3971b731997_301.png)

![](img/31e65549044e1df68a31e3971b731997_302.png)

![](img/31e65549044e1df68a31e3971b731997_303.png)

![](img/31e65549044e1df68a31e3971b731997_304.png)

Okay。And so here， we've done it as， as a function of the threshold。

 And we've just looked at negative thresholds， a decreasing thresholds。



![](img/31e65549044e1df68a31e3971b731997_306.png)

Okay， and so in this plot， we've got in black， the overall error rate。In， in。



![](img/31e65549044e1df68a31e3971b731997_308.png)

In orange， we've got the false positive rate。 And in blue， we've got the false negative rate。



![](img/31e65549044e1df68a31e3971b731997_310.png)

And so as we decrease the threshold。The false positive rate increases because now we're going to classify more and more negatives as positive。



![](img/31e65549044e1df68a31e3971b731997_312.png)

![](img/31e65549044e1df68a31e3971b731997_313.png)

But it increases very slowly。 You'll see for a long region long part of， of the threshold going down。

 the decrease in threshold， the， the false negative， false positive rate doesn't increase very fast。



![](img/31e65549044e1df68a31e3971b731997_315.png)

![](img/31e65549044e1df68a31e3971b731997_316.png)

Of course， the false negative rate increases as we do that。



![](img/31e65549044e1df68a31e3971b731997_318.png)

And so even at point1。Right。

![](img/31e65549044e1df68a31e3971b731997_320.png)

The false， the false positive rate hasn't increased a huge amount。

 and the false negative hasn't increased a huge amount， but we've changed the balance of。

 of classification。

![](img/31e65549044e1df68a31e3971b731997_322.png)

![](img/31e65549044e1df68a31e3971b731997_323.png)

And so you can change the threshold。Well， you can capture that change in threshold in what's known as an R O C curve。



![](img/31e65549044e1df68a31e3971b731997_325.png)

So what this shows is。The two error rates， in this case， false positive rate and true positive rate。

嗯。As we change the threshold， okay， and。

![](img/31e65549044e1df68a31e3971b731997_327.png)

We'd like， we'd like both。We'd like the false positive rate to be low and the true positive rate to be high。



![](img/31e65549044e1df68a31e3971b731997_329.png)

And so this R O C curve traces out as we change the threshold。



![](img/31e65549044e1df68a31e3971b731997_331.png)

And。The 45 degree line is the kind of no information line。

 And what you'd like is you'd like this curve to be right up as far as possible into the top left hand corner。



![](img/31e65549044e1df68a31e3971b731997_333.png)

![](img/31e65549044e1df68a31e3971b731997_334.png)

![](img/31e65549044e1df68a31e3971b731997_335.png)

So if you had a true positive rate of， of one and a false positive rate of of 0。



![](img/31e65549044e1df68a31e3971b731997_337.png)

You flip the coin you'd be on the straight line。 you'd be on the straight line。



![](img/31e65549044e1df68a31e3971b731997_339.png)

Okay。And， and so this is a single curve that sort of captures the。

 the behaviour of the classification rule for all possible thresholds。 And you can， and。

 and you can compare different classifierifies by comparing the R O C curves。



![](img/31e65549044e1df68a31e3971b731997_341.png)

![](img/31e65549044e1df68a31e3971b731997_342.png)

![](img/31e65549044e1df68a31e3971b731997_343.png)

Okay。And to summarize it even more， we sometimes use the area under the curve or A U。



![](img/31e65549044e1df68a31e3971b731997_345.png)

Which captures the extent to which you up in the， in the northwest corner and higher A U C is good。



![](img/31e65549044e1df68a31e3971b731997_347.png)

![](img/31e65549044e1df68a31e3971b731997_348.png)

Okay。