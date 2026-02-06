# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P27：-027-Statistical Learning_ 4.7 Gaussian Discriminant Analysis (Many Variables).z - GPT中英字幕课程资源 - BV1u4421A7ZU

![](img/ccc7879f4532151d60bca34d7664ffcc_0.png)

Okay， so that was with a single variable。😊，And usually， when we do classification。

 we got more than one variable。

![](img/ccc7879f4532151d60bca34d7664ffcc_2.png)

So now we're going to go to multivariate Gausss。

![](img/ccc7879f4532151d60bca34d7664ffcc_4.png)

So here's a picture of a Gaussian density when you've got two variables。So it's one of these。

Fancy looking three dimensional plots。 It's beautiful， beautiful， isn't it。😊。

The heights colour coded。Could you make a plot like this one？I could try and you'd。Criticize。

You do criticize it。Actually。The， the beautiful thing is that R made this plot with very little work fromness。

So there's two variables， X1 and x2。 And you can see the Garussian density in in two dimensions looks like a bell function。

And this is left and case is the case when two variables are uncorrelated。

 So it's just really like a bell。And the right hand case is when there's correlation。

 So now it's like a stretched be。 You can see this's positive correlation between x 1 and x 2。

So those are pictures of the densities。 The formula for the density doesn't look nearly as pretty。

 And here it is over here。And it's somewhat complex， but you should go over this in great detail now。

 excruciating detail， please。I have a feeling that's a hint not to go into it in great detail。Anyway。

 this is just a generalization of the formula we had for a single variable。

 This is called a covariance matrix。And it's， if you。

 if you stay at this formula and you stay at the previous formula， you'll see that there。

 theres somewhat similarity， especially if you know a bit of vector algebra。嗯。

If you go through the simplifications， if you know your linear algebra。

 you can form the and do the cancellation similar to what we did before。

 you can form the discriminant function， which is given over year。And its looks complex。

 but important thing to note is that it's， again， linear in x。

 Yess x alone multiplied by a coefficient vector。And thisthe are or just constants。 So this， again。

 is a linear function。If the， if the maths beyond you don't let it bother you。

 This is a linear function， and we'll make that more clear a little bit later on as well that this is a linear function。

In fact， we make it clear right here。Its might look complex。

 but this can just be written in this form of view。Okay， it's a linear function。 So this C， K 0。

 So this is a function for class K， C， K 0。Is built up of all these pieces over year。

 And then each of the coefficients of x1， x2 up to X P come from this spot over year。Remember。

 x is a vector in this case。And so you can expand this expression and get this， this term of here。

And I I probably I I think I've forgot to mention it before。

 What the idea of the discriminant function is you compute one of these for each of the classes and then you classify it to the class for which it's largest。

You pick the discriminant function at largest。

![](img/ccc7879f4532151d60bca34d7664ffcc_6.png)

Well， we can draw other nice pictures for discriminant analysis。

 similar to the one dimension the one dimensional picture we do before。So here。

 we've got two variables and three classes。And。We can't instead of showing those density plots。

 what we do is show contours in this case， of the density。 So here's the blue class。 And we show a。

 the contour of a particular level of probability。Okay， for the blue class。

For the green class and for the orange class。Okay。And lo and behold。

 and the decision boundary is the dotted linear。And。It's really very pretty。 It， it shows you。

Where you classify to blue versus orange。And it's exactly where it cuts where the con。

 the line goes exactly through the points where the contours are cut。Both for the orange to blue。

 for the， the blue to green and for the green to， to orange。And you can see they all meet in the。

 in the middle over here。Right in the centre over here。And so if you knew the， the。

 the two densities。It would tell you exactly。 And， and in this case， like Gaussian。

 you get the exact decision boundaries。 Again， these are called the base decision boundaries。

 These are the true decision boundaries。Now， of course we don't。

But we go ahead and estimate the parameters for the Gaussians in each of the class。

 using formulas similar to what we had before， but appropriate for this multivariate case。

So in this case， we get to get the mean。For x 1 and x2， for the blue class。

It's about there for the green class with data points about there。 for the orange class， say there。

And then we plug them into the formula。 instead of getting the the dotted lines。

 we get the solid lines。 And in this case， it's remarkably close。Now。

 these data were actually generated from a Gaussian distribution。

 So it's not too surprising that we got close。 but with relatively few points。

 we get decision boundaries that look pretty close to the the real ones。



![](img/ccc7879f4532151d60bca34d7664ffcc_8.png)

You cannot learn about discriminant analysis without seeing Fser's iris data。

 It's maybe one of the most famous data sets around。It studies three species of， of iris。

These species are Siossa， versical and Virginiaica。And they colour coded in the scatter plot matrix。

 again， with three colours in this case。And there are four variables that are going to be used to try and automatically classify these。

 these three， to these three classes。Sple length。Sample width。Petal length and petal width。

So these are aspects of the， of the flower。And there's 50 samples in each class。Now。

 if you look at these scatter plots， you can see that there's some really good separation。

 For example， in this plot of petal length and petedal width。

 the blue class really stands out as being different from from the other two classes。



![](img/ccc7879f4532151d60bca34d7664ffcc_10.png)

They seem to be more confused in， in some of the plots。But in summary slightly more separation。

 But the idea here is to use all these variables together to come up with a discriminatory rule。And。

 and， and classify。And so this was a motivated example that that Fisher used in in his first description of linear discriminant analysis。

And， in fact， it's often known as Fisher's linear discriminant analysis。Importantly。

 what comes with discriminants analysis is a nice plot。Right， in this previous picture。



![](img/ccc7879f4532151d60bca34d7664ffcc_12.png)

There's four variables。 So we showed a scatterpl matrix of each variable against the wrist。



![](img/ccc7879f4532151d60bca34d7664ffcc_14.png)

But it turns out that there's a single plot that captures。

The classification information for all of these variables。And here it is。And。

I've got discriminant variable 1 and disccrminant variable 2 is the horizontal and vertical axes。

And it turns out these are linear combinations of the original variables。

but they spatial in new combinations。And when you plot the variables against these two。

 you see really good separation。And these arise from actually performing the linear discriminant analysis。

Because you've got three classes， what Fiser's linear discriminants analysis is really doing or Gaussian LDA is really doing。

Is it's measuring which centroid is the closest。But it's measuring in。

 in a distance that where it takes into account the covariance of， of the variables。

But ignoring the covariance for a moment。The distance， the three centroids。Actually， lying in。

 a plane， a subspace of the four dimensional space。And it's really distance。

 So if you have three points， they span a two dimensional subspace。

And that's essentially what we plot in is the two dimensional sub space。

 So seeing which class is closest。Really amounts to distance in that subspace。

And that leads to these nice， low dimensional plots。And so we have three classes here。

 We can make a two dimensional plot， and it captures exactly what's。

What's important in terms of the classification。And， and when we have more than three classes。

 we can find still find two dimensional plots。 But in that case。

 it doesn't capture all the information， the two dimensional plot。

 but we can find the best two dimensional plot for visualizing the discrimin rule。

And that's another important reason why linear discriminant analysis is very popular for multiclass classification。

 So keep in mind， this case， we had only four features，4 variables。

 right And Discri analysis was a very attractive method。 But imagine we had 4000 features。

 right then。In ingredient what we just did was the covariance matrix。

 we had to plug in an estimate of the covariance matrix。 Yes and if you had 4000 features。

 that covariance matrix would be of size 4000 by 4000。 Yes，' that's a great point Rob。

 And you know we just can't carry out discriminants analysis without other modifications if the number of variables are very large。

 and we're going to talk about some ways of doing that and later on in the class we'll talk about even more ways。



![](img/ccc7879f4532151d60bca34d7664ffcc_16.png)

嗯。What we， we've talked about discriminator functions， which is telling you how you classify。

 But it turns out that you can turn these into probabilities very easily。

And is it expression over yet。And so remember， we got the decays by doing a lot of simplification。

 Well， it turns out that those simplifications and cancellations hold exactly for computing the probabilities。

So in other words， those expressions we had earlier for。



![](img/ccc7879f4532151d60bca34d7664ffcc_18.png)

Computing the probabilities。It's go back to it。 for example， here's a expression。

 Yeah that's used in computing the probabilities。

![](img/ccc7879f4532151d60bca34d7664ffcc_20.png)

![](img/ccc7879f4532151d60bca34d7664ffcc_21.png)

Where is it。 This， This is the， the expression for the single variable case with all these constants in that that all the cancellation happens。

 and we get to。

![](img/ccc7879f4532151d60bca34d7664ffcc_23.png)

![](img/ccc7879f4532151d60bca34d7664ffcc_24.png)

This nice， simple expression of you， which just involves the discriminant functions， okay。So you see。

 you can see if you can actually show that as well。 It's not that hard to show。And so。

We can not only does discriminant analysis give us a classified also gives us the probabilities。嗯。

When case is 2， well classify to class 2， if these probabilities are bigger than 。5 else to class 1。

 just like in logistic regression。

![](img/ccc7879f4532151d60bca34d7664ffcc_26.png)

Here's the credit data。嗯。And we produce， in this case， misclassification table。Okay。So this table is。

 is got。Along the horizontal， it's got the， the two status， so。It's a true default status。

 which is no， or yes。You can see we had 10000 samples in the， in the credit data。And in the vertical。

 we've got the predicted status。 No or yes。So of course， we'd like everything to lie on the diagonal。

It turns out we got a lot of the nose right， and， and。Not that many of the， the yes is， right。

So on the diagonal is what you got correct。 on the off diagonals is what you got incorrect。

Nevertheless， overall， we make 2。75% misclass errors here。Okay， so。

This is called a confusion matrix It tells how well you did。Now， there's some caveats。

 This is training error。Right， weve， we fit the rule to these data。

 And now we see how well it performs on these data。 So we may be overfiing。Well。

 we've got 10000 training samples here， and we've only fit a handful of parameters。

 So it's very unlikely in this case that were overfitting for small training sets。

 that would be an issue。 and you need to have a separate test set。



![](img/ccc7879f4532151d60bca34d7664ffcc_28.png)

嗯。Another， another thing to note is that although 2。75% seems really good misclassification rate。

If we just use a very naive classification rule and said， I mean order always classify to the。

 the largest class。 In other words， classify according to the prior。We'd only make 3。333% errors。

 right， because there's a predominance of， of no in this， in the dataset set， right。The。

 the total number of nos is 333 out of out of 10000。Right， so this we call the null rate。

 And so you always， you always use a bear in mind the， the null rate when。

 in getting excited about a misclassification error rate。The other thing to look at， though， is。

You can break the errors into different kinds。 So of the true nose。We make 02 per cent errors。

 so we hardly ever misclassify a no。But of the yeses， we make a whopp in 75。7% errors， right。

 So the errors are very lopsided in this case。And that's maybe not such a good idea。



![](img/ccc7879f4532151d60bca34d7664ffcc_30.png)

So。We。Break down these errors into， into finer categories。 So we call the false positive rate。

The fraction of， of negative examples that are classified as positive， right。

 So they false positives。 In that case， that was the 2 per。2% in this case。

And the false negative rate， that's the fraction of positive examples that are classified as negative。

The 75。7% in this case。Now， we produced the classification table by。Intuitively correct。

 Classifying default is yes。嗯。If the probability of default was bigger than 0。5。Okay。

But it gave us this very lopsided， false， positive and false negative rate。In some cases。

 especially for these kinds of screening examples。

![](img/ccc7879f4532151d60bca34d7664ffcc_32.png)

You may want to change the。The false， positive and false negative rates and skew them to one side or the other。

 And you can do this by changing this threshold。 instead of classifying， in this case， to default。

 if it's bigger than 0。5， you can change a threshold and maybe make the threshold in this case smaller so that you can catch more of the。

 the high risk cases for default。Okay。And so here， we've done it as， as a function of the threshold。

 And we've just looked at negative thresholds， a decreasing thresholds。Okay， and so in this plot。

 we've got in black， the overall error rate。In， in。In orange， we've got the false positive rate。

 And in blue， we've got the false negative rate。And so as we decrease the threshold。

The false positive rate increases because now we're gonna classify more and more negatives as positive。

But it increases very slowly。 You'll see for a long region long part of。

 of the threshold going down the decrease in threshold， the， the false negative。

 false positive rate doesn't increase very fast。Of course。

 the false negative rate increases as we do that。And so even at point1。Right。The false。

 the false positive rate hasn't increased a huge amount。

 and the false negative hasn't increased a huge amount， but we've changed the balance of。

 of classification。

![](img/ccc7879f4532151d60bca34d7664ffcc_34.png)

And so you can change the threshold。Well， you can capture that change in threshold in what's known as an R O C curve。

So what this shows is。The two error rates， in this case， false positive rate and true positive rate。

嗯。As we change the threshold， okay and。We'd like。 We'd like both。

We'd like the false positive rate to be low and the true positive rate to be high。

And so this R O C curve traces out as we change the threshold。And。

The 45 degree line is the kind of no information line。 And what you'd like is， you'd like。

This curve to be right up as far as possible into the top left hand corner。

So if you had a true positive rate of， of one and a false positive rate of of 0。

You flip the coin you be on the straight line， you'd be on the straight line。Okay。And。

 and so this is a single curve that sort of captures the。

 the behavior of the classification rule for all possible thresholds。 And you can， and。

 and you can compare different classifiers by comparing the R O C curves。Okay。

And to summarize it even more， we sometimes use the area under the curve or AU。

Which captures the extent to which you up in the， in the northwest corner， Then higher A U C is good。



![](img/ccc7879f4532151d60bca34d7664ffcc_36.png)

![](img/ccc7879f4532151d60bca34d7664ffcc_37.png)

Okay。