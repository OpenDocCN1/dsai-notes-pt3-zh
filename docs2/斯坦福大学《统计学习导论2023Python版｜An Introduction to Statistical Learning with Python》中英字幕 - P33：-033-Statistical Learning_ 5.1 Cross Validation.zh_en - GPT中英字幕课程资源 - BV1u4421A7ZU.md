# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P33：-033-Statistical Learning_ 5.1 Cross Validation.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_0.png)

Okay， we've learned about methods for regression and for classification and building predictors and for predicting making predictions from our data how do we test these out Well ideally we'd like to get a new sample from the population and see how well our predictions do。

😊。

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_2.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_3.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_4.png)

Well， we don't always have new data。 So what do we do。

 and we can't use our training data just straight off because it's going to be a little bit optimistic。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_6.png)

So we're going to tell you about cross validation， Rob is going to tell you about cross validation。

 which is a very clever device for using the same training data to tell you how well your prediction method works。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_8.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_9.png)

The other thing going to give my entire lecture， and I'll try not to， Rob。

 just in case you miss out some of the salient points。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_11.png)

The other thing we're going to look at is standard errors of estimators。

 sometimes our estimators are quite complex and we'd like to know the standard error which means what happens if we've got new samples from the population over and over again and we recomputed our estimate and the standard error is the standard deviation of those estimates under resampling。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_13.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_14.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_15.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_16.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_17.png)

Well， of course， we can't resample from the population。 We only have one sample。Again。

 Rob's going to tell you about the bootstrap， which is a very clever device for using the one single training sample you'll have to estimate things like standard deviations。

 Rob， Okay， well for that， thanks for that great introduction。 Good overview。

 So we're going talk about cross validation in the bootsottap， as Trbo mentioned， these are。😊。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_19.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_20.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_21.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_22.png)

Resampling methods， so the word resampling our original data is a sample， we're going to resample。

 use our we're actually a sample from our data set in order to learn about the quantity of interest and the cross validation。

 the bootstrap are both ways of resampling from the data。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_24.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_25.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_26.png)

And the purpose of it is to get information about the additional information about the fitted model。

 for example， the main thing we use cross validation for is to get an idea of the。

The test set error of our model we're going to review that concept of training error and we'll see as we've talked about before。

 the training error is too optimistic the more we fit to the data， the lower the training error。

 but the test error can get higher if we overfit it often will so cross foundation is a very important tool that we're going to talk about in this section and we'll use throughout the course to get a good idea of the test set error of a model。

Bottttrarap， on the other hand， is most useful to get idea of the variability or standard deviation of an estimate and its bias。

So we'll talk about first cross validation and then bootsstrrop。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_28.png)

SoBut before we get into those， let's review the idea of the concept of training error versus test error。

Remember， test error is the area that we incur on new data， so we fit our model to a training set。

 we take our model and then we apply it to new data that the model hasn't seen。

The test there is actually how well we'll do on future data the model hasn't seen。

Training error is much easier to compute。 We can do it in the same data set。 What is it。

 It's the error we get。Applying the model to the same data from which we trained right and as you can imagine。

 training areas is often quite。It's lower than test error。

 the model has already seen the training set， so it's going to fit the training set。

With lower error than it was going to occur on a test set。And the more we overfit。

 the harder we fit the data， the lower the training error looks。On the other hand。

 the test error can be quite a bit higher， so training error is not a good surrogate for test error。

And this picture is a good one to look at to summarize the concepts here， so what do we have here。

 well first of all， along the horizontal axis is the model complexity low from low to high。

 for example in our，A linear model， the model complexity is the number of features or the number of coefficients that we fit in the model。

 so low means a few number of features or coefficients or predictors， high means a large number。

think about fitting a polynomial with high and higher degree C model complexity increases with degree。

 so we move to the right， we'd have a higher complexity， higher order of polynomial。

 The prediction errors on a vertical axis， and we have two curves here， the training error in blue。

 and the test error in red。So what do we see， let's first look at the blue curve on the left the model complexity is low。

 for example we're fitting a small number of parameters， maybe just a single constant。

The training error is high now as we increase the model complexity。

 we fit more and more features in the model or higher complexity or higher order polynomial。

 the training error goes down。And actually， this picture continues to go down a consistent way。

 and in most cases， for most models， the more complex the model， the training error will go down。

As it does in this case。On the other hand， the test error is the red curve。

 it does not consistently go down。Starts off high like the training air comes down for a while。

 but then it starts to come up again。 Has a minimum looks like around the middle here， but。

After this point。The more complex the model， the higher the tester。What's happened there？

Is an example of overfitting， right？On the left， we've added complexities some features that actually are important for predicting the response。

 so they reduce the test there， but at that point we seem to have fit all the important features and now we're putting in things which are just noise。

The training error goes down as it has to， but the test error is starting to go up。

 that's overfitting， right so we don't want to overfit because we'll increase the test error。

The training error is not told us anything about overfitting because it's using the same data to。

To measure error， the more parameters， the better it looks， so it's not a good。

Does not give us a good idea of the test error， the test error curve， on the other hand。

 is minimized around this level at this model complexity and beyond that is overfitting。

The ingredients for there actually are bias invaris。

So the bias is how far off on the average the model is from the truth。

The variance is how much that the estimate varies around its average。When we don't fit very hard。

 the bias is high。The variance is low because there's few parameters being fit as we increase the model complexity moving to the right。

The bias goes down because the model can adapt to more and more。sttleties in the data。

 but the variance goes up because have we have more and more parameters to estimate from the same amount of data。

 so bias andvaris together give us prediction error and there's a trade off they sum together to give prediction error and the trade off。

Is minimized in this case around a model complex near the middle here。

So bias andvaris together give us test error。We want to find that the model complexity giving the smallest test error and training error does not give us a good idea that of test error。

 and they refer to it as the bias variant trade off。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_30.png)

Okay， so。We can't use training error to estimate test error as the previous picture shows us so what do we do well the best solution if we have a large test set we can use that。

 we simply take our model that we've applied fit on the training set， apply it to the test set。But。

Very often we don't have a large test yet。 So if we can' do that， what do we do， Well。

 there there are some ways to。Get an idea of test error using an adjustment to training error。

 basically training error can be too small as we've seen in the previous picture。

 so these methods adjust the training error。By increasing it。

By a factor that involves the amount of fitting that we've done to the data and the variance。

And these methods include this the CP statistic， the EIC and the BIC。

We'll talk about these later on in the course， not in this section。

 here instead we're going to talk about cross validation or validation cross validation。

 and these involve removing part of the data， holding it out。Ftting the model to the remaining part。

 and then applying that fitted model to the data that we've held out。

 and this is called validation or cross validation， as we'll see。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_32.png)

So let's first of all， talk about the validation approach。 So here we're going to。

The simple idea is basically we're going to divide the data into two parts at random。

Approximately of equal size。We will call the first part of training set and the second part the validation or hold out set。

So the idea is simple， we take the model， we fit it out on the training half。

And then we apply the fitted model to the other half the validation or holdout set。

And we record the error that we get on the holdout set。And that error， the validation set error。

 provides us a good idea of the test error， well at least some idea of the test error。

And the error will measure by mean square error in the case of quantitative response。Or。

This classification error or rate in the case of a qualitative or discrete response， classification。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_34.png)

Okay， so just to make that clear， and let's look at the next slide， we have our data set here。

 I've divided it in two at random。The blue part on the left is the training set and the。

Orange part or pink part on the right is the validation or holdout set。 These observations。

 for example， 7，22 and 13 and more of them are part at random chosen to be in the training set。

Oosation 91 was at random chosen to be in the holdout set。We fit the model to the blue part。

 and then we apply it and predict the observations in the pink part。And that's validation。

 or we might call that twofold validation。Well， I maybe I shouldn't call it twofold because as we'll see we don't cross over。

 this is simply a one stage process we divide it in half。

Train on one half and predict on the other half。It seems a little wasteful if you got a very small data syndrome。

 yeah， that is wasteful and as we'll see its cross foundation will remove that waste and be more efficient。

 but let's first of all see how this works。

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_36.png)

。In the auto data， we we're trying to recall we're comparing the linear model to high order polynomials in regression。

And we had 392 observations divided into so we divided up into two parts at random。

196 in one part and 196 in the other part。First part being the training set and the other part being the validation set。

A。Here's if we do this once。It was a single split， and we record the mean square error。

We get this red curve as a function of the degree of the polynomial。

 so a linear fits on the left and quadratic is here， etc ce， as we increase the polynomial order。

And we see the minimum seems to occur maybe around two。Well。

 it's rising a bit and coming down a bit after that， it's pretty flat after vote two。

So it looks like a linear model， actually a quadriotic model， excuse me is probably the best。

 and after that we're not giving much gain if any at all。

But look what happens when we repeat this process with more and more splits at random into two parts。

 we had a lot of variability。The minimums does tend to occur around two。Generally。

 but look at the error， it's severing from about 16 up to 24 depending on the split。So， this is。

This is a consequence， part of the fact that we divided the data up into two parts and when you divide data in two。

 you get a lot of variability depending on the split， the training set， for example。

 is half as big as it was originally。So it's interesting， Rob。

 that even though you get that variability， it seems to often have this pattern where the shape of the curves are much the same。

 but the height， the level hops around。So that's a good point and it actually reminds me to say there's two things we want to use validation for or cross validation。

 both to pick the best size of the model in this case。

 a degree of polynomial and also to give us an idea of how good the error is to give an idea of the actual test error at the end of the。

Of the fitting process。Twofold this。Breaking up into two parts is successful at the first thing。

 as Trevor has mentioned， the minimums are around two pretty consistently。So that seems to be okay。

 but the actual level of the curve is varying a lot。

 so it wouldn't be so good at telling us an idea of the error because we get a very wide range here。

In here。

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_38.png)

So。So I've said a little bit of the first point already that。

Its this method is highly variable because we're splitting into two parts and there's lots of ways to split data into two parts and because we're splitting in two we're losing a lot of the。

The power and the training set were throwing away half the data each time in training。嗯。And。

Another consequence of that is that you remember one of our original questions was， well。

What's the best size model to pick， second of all， how well does that model do in terms of test error？

Our training sets here are half as big as our original training set and if we go back to this previous slide。

 we've split the data in half， we actually want the test error for a training set of size n。

 we're getting an idea of test error for a training set of size n over two。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_40.png)

![](img/59e4b76bd6d8a7df4dcd466c2ed52360_41.png)

And that's likely to be quite a bit higher than。The error for。A train set of size n。Why wrong， why？

That was my question。Well， that's because in general。

 the more data one has the lower the error if I offer you a choice of would you' rather have 100 observations or 200 observations。

 you're generally like 200 observations to train on because the more data。

 the more information you have and in general the lower your error is so if your training sets is only half as big as your original training set。

As it is in this situation， the error that it yields is probably going to be higher than the actual error you want to get。



![](img/59e4b76bd6d8a7df4dcd466c2ed52360_43.png)

So as we can see there's some drawbacks of validation in the next section we'll talk about cross validation which will help to remove some of these drawbacks。

