# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P25：P25 StatsLearning Lect7a 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/c86edfc5418fe3d38620250de9e815d5_0.png)

Okay， we've learned about methods for regression and for classification and building predictors and for predicting making predictions from our data How do we test these out Well。

 ideally we'd like to get a new sample from the population and see how well our predictions do。😊。



![](img/c86edfc5418fe3d38620250de9e815d5_2.png)

![](img/c86edfc5418fe3d38620250de9e815d5_3.png)

![](img/c86edfc5418fe3d38620250de9e815d5_4.png)

Well， we don't always have new data， so what do we do and we can't use our training data just straight off because it's going to be a little bit optimistic。



![](img/c86edfc5418fe3d38620250de9e815d5_6.png)

![](img/c86edfc5418fe3d38620250de9e815d5_7.png)

So we're going to tell you about cross validation， Rob's going to tell you about cross validation。

 which is a very clever device for using the same training data to tell you how well your prediction method works。



![](img/c86edfc5418fe3d38620250de9e815d5_9.png)

![](img/c86edfc5418fe3d38620250de9e815d5_10.png)

The other thing going to give my entire lecture， I'll try not to Rob。

 just in case you miss out some of the salient points。



![](img/c86edfc5418fe3d38620250de9e815d5_12.png)

![](img/c86edfc5418fe3d38620250de9e815d5_13.png)

The other thing were going to look at is standard errors of estimators。

 sometimes our estimators are quite complex and we'd like to know the standard error which means what happens if we've got new samples from the population over and over again and we recomputed our estimate and the standard error is the standard deviation of those estimates under resampling。



![](img/c86edfc5418fe3d38620250de9e815d5_15.png)

![](img/c86edfc5418fe3d38620250de9e815d5_16.png)

![](img/c86edfc5418fe3d38620250de9e815d5_17.png)

![](img/c86edfc5418fe3d38620250de9e815d5_18.png)

Well， of course， we can't resample from the population， we only have one sample。Again。

 Rob's going to tell you about the bootstrapap， which is a very clever device for using the one single training sample you'll have to estimate things like standard deviations。

 Rob， okay， that thanks for that great introduction。 Good overview。

 So we're going to talk about cross validation and the bootsottrapap， as Treor mentioned， these are。

😊。

![](img/c86edfc5418fe3d38620250de9e815d5_20.png)

![](img/c86edfc5418fe3d38620250de9e815d5_21.png)

![](img/c86edfc5418fe3d38620250de9e815d5_22.png)

![](img/c86edfc5418fe3d38620250de9e815d5_23.png)

Resampling methods， so the word resampling original data is a sample， we're going to resample。

 use our we actually a sample from our data set in order to learn about the quantity of interest and the cross validation of the bootstrap are both ways of resampling from the data。



![](img/c86edfc5418fe3d38620250de9e815d5_25.png)

![](img/c86edfc5418fe3d38620250de9e815d5_26.png)

![](img/c86edfc5418fe3d38620250de9e815d5_27.png)

![](img/c86edfc5418fe3d38620250de9e815d5_28.png)

And the purpose of it is to get information about the additional information about the fitted model。

 for example， the main thing we use cross validation for is to get an idea of the。



![](img/c86edfc5418fe3d38620250de9e815d5_30.png)

![](img/c86edfc5418fe3d38620250de9e815d5_31.png)

The test set error of our model we're going to review that concept of training error and we'll see as we've talked about before the training error is too optimistic。

 the more we fit to the data the lower the training error but the test error can get higher if we overfit it often will so cross Foundation is a very important tool that we're going to talk about in this section and we'll use throughout the course to get a good idea of the test set error of our。



![](img/c86edfc5418fe3d38620250de9e815d5_33.png)

![](img/c86edfc5418fe3d38620250de9e815d5_34.png)

![](img/c86edfc5418fe3d38620250de9e815d5_35.png)

![](img/c86edfc5418fe3d38620250de9e815d5_36.png)

Of， of a model。

![](img/c86edfc5418fe3d38620250de9e815d5_38.png)

Bottstrrap， on the other hand， is most useful to get idea of the variability or standard deviation of an estimate and its bias。



![](img/c86edfc5418fe3d38620250de9e815d5_40.png)

So we'll talk about first cross validation and then Botrop。



![](img/c86edfc5418fe3d38620250de9e815d5_42.png)

SoBut before we get into those， let's review the idea of the concept of training error versus test error。



![](img/c86edfc5418fe3d38620250de9e815d5_44.png)

Remember， test error is the area that we incur on new data， so we fit our model to the training set。

 we take our model and then we apply it to new data that the model hasn't seen。



![](img/c86edfc5418fe3d38620250de9e815d5_46.png)

The test there is actually how well we'll do on future data the model hasn't seen。

Training error is much easier to compute。 We can do it in the same data set。 What is it。

 It's the error we get。Applying the model to the same data from which we trained right and as you can imagine。

 training areas is often quite。

![](img/c86edfc5418fe3d38620250de9e815d5_48.png)

![](img/c86edfc5418fe3d38620250de9e815d5_49.png)

It's lower than test error， the model has already seen the training set。

 so it's going to fit the training set。With lower error than it was going to occur in a test set。



![](img/c86edfc5418fe3d38620250de9e815d5_51.png)

And the more we overfit， the harder we fit the data， the lower the training error looks。

On the other hand， the test error can be quite a bit higher。

 so training error is not a good surrogate for test error。



![](img/c86edfc5418fe3d38620250de9e815d5_53.png)

And this picture is a good one to look at to summarize the concepts here。

 so what do we have here well first of all， along the horizontal axis is the model complexity low from low to high。

 for example in our。

![](img/c86edfc5418fe3d38620250de9e815d5_55.png)

![](img/c86edfc5418fe3d38620250de9e815d5_56.png)

A linear model， the model complexity is the number of features or the number of coefficients that we fit in the model。

 so low means a few number of features or coefficients or predictors， high means a large number。



![](img/c86edfc5418fe3d38620250de9e815d5_58.png)

![](img/c86edfc5418fe3d38620250de9e815d5_59.png)

![](img/c86edfc5418fe3d38620250de9e815d5_60.png)

think about fitting a polynomial with high and higher degree C model complexity increases with degree。

 so we move to the right we'd have a higher complexity， higher order of polynomial。

 The prediction errors is on a vertical axis， and we have two curves here。

 the training error in blue and the test error in red。



![](img/c86edfc5418fe3d38620250de9e815d5_62.png)

![](img/c86edfc5418fe3d38620250de9e815d5_63.png)

![](img/c86edfc5418fe3d38620250de9e815d5_64.png)

So what do we see， let's first look at the blue curve on the left。



![](img/c86edfc5418fe3d38620250de9e815d5_66.png)

The model complexity is low， for example， we're fitting a small number of parameters。

 maybe just a single constant。

![](img/c86edfc5418fe3d38620250de9e815d5_68.png)

The training error is high now as we increase the model complexity。

 we fit more and more features in the model or higher complexity or higher order polynomial。

 the training error goes down。

![](img/c86edfc5418fe3d38620250de9e815d5_70.png)

![](img/c86edfc5418fe3d38620250de9e815d5_71.png)

![](img/c86edfc5418fe3d38620250de9e815d5_72.png)

And actually this picture continues to go down a consistent length， in most cases， for most models。

 the more complex the model， the training error will go down。



![](img/c86edfc5418fe3d38620250de9e815d5_74.png)

![](img/c86edfc5418fe3d38620250de9e815d5_75.png)

As it does in this case。On the other hand， the test error is the red curve。

 it does not consistently go down。

![](img/c86edfc5418fe3d38620250de9e815d5_77.png)

Starts off high like the train here comes down for a while， but then it starts to come up again。

 Ha a minimum looks like around the middle here， but。



![](img/c86edfc5418fe3d38620250de9e815d5_79.png)

![](img/c86edfc5418fe3d38620250de9e815d5_80.png)

After this point。The more complex the model， the higher the tester。



![](img/c86edfc5418fe3d38620250de9e815d5_82.png)

What's happened there？Is an example of overfitting， right？



![](img/c86edfc5418fe3d38620250de9e815d5_84.png)

On the left we've added complexities some features that actually are important for predicting the response。

 so they reduce the test error， but at that point we seem to have fit all the important features and now we're putting in things which are just noise。



![](img/c86edfc5418fe3d38620250de9e815d5_86.png)

![](img/c86edfc5418fe3d38620250de9e815d5_87.png)

The training error goes down as it has to， but the test error is starting to go up。

 that's overfitting， right so we don't want to overfit because we'll increase the test error。



![](img/c86edfc5418fe3d38620250de9e815d5_89.png)

![](img/c86edfc5418fe3d38620250de9e815d5_90.png)

The training error has not told us anything about wefitting because it's using the same data to。



![](img/c86edfc5418fe3d38620250de9e815d5_92.png)

To measure error， the more parameters， the better it looks。

 so it does not give us a good idea of the test error。

 the test error curve on the other hand is minimized around this level at this mal complexity and beyond that is overfitting。



![](img/c86edfc5418fe3d38620250de9e815d5_94.png)

![](img/c86edfc5418fe3d38620250de9e815d5_95.png)

![](img/c86edfc5418fe3d38620250de9e815d5_96.png)

The ingredients for diary actually are biasing variants。



![](img/c86edfc5418fe3d38620250de9e815d5_98.png)

So the bias is how far off on the average the model is from the truth。



![](img/c86edfc5418fe3d38620250de9e815d5_100.png)

The variance is how much that the estimate varies around its average。



![](img/c86edfc5418fe3d38620250de9e815d5_102.png)

When we don't fit very hard， the bias is high。

![](img/c86edfc5418fe3d38620250de9e815d5_104.png)

The variance is low because there's a few parameters being fit as we increase the model complexity moving to the right。



![](img/c86edfc5418fe3d38620250de9e815d5_106.png)

The bias goes down because the model can adapt to more and more。



![](img/c86edfc5418fe3d38620250de9e815d5_108.png)

Sttleties in the data， but the variance goes up because we have more and more parameters to estimate from the same amount of data。



![](img/c86edfc5418fe3d38620250de9e815d5_110.png)

So bias andvaris together give us prediction error， and there's a trade off。

 They sum together to give prediction error and the trade off。



![](img/c86edfc5418fe3d38620250de9e815d5_112.png)

![](img/c86edfc5418fe3d38620250de9e815d5_113.png)

Is minimized in this case around a model complex near the middle here。



![](img/c86edfc5418fe3d38620250de9e815d5_115.png)

So bias andvaris together give us test error。We want to find that the model complexity giving the smallest test error and training error does not give us a good idea of that of test error。

 and they refer to it as the bias variance trade off。



![](img/c86edfc5418fe3d38620250de9e815d5_117.png)

![](img/c86edfc5418fe3d38620250de9e815d5_118.png)

Okay， so。We can't use training error to estimate test error as the previous picture shows us so what do we do well the best solution if we have a large test set we can use that。

 we simply take our model that we've applied the fit on the training set， apply it to the test set。



![](img/c86edfc5418fe3d38620250de9e815d5_120.png)

![](img/c86edfc5418fe3d38620250de9e815d5_121.png)

![](img/c86edfc5418fe3d38620250de9e815d5_122.png)

But。

![](img/c86edfc5418fe3d38620250de9e815d5_124.png)

Very often we don't have a large test yet。 So if we can't do that， what do we do， Well。

 there there are some ways to。

![](img/c86edfc5418fe3d38620250de9e815d5_126.png)

Get an idea of test error using an adjustment to training error。

 basically training error can be too small as we've seen in the previous picture。

 so these methods adjust a training error。

![](img/c86edfc5418fe3d38620250de9e815d5_128.png)

![](img/c86edfc5418fe3d38620250de9e815d5_129.png)

By increasing it。

![](img/c86edfc5418fe3d38620250de9e815d5_131.png)

By a factor that involves the amount of fitting that we've done to the data and the variance。



![](img/c86edfc5418fe3d38620250de9e815d5_133.png)

And these methods include this the CP statistic， the EIC and the BIC。



![](img/c86edfc5418fe3d38620250de9e815d5_135.png)

We'll talk about these later on in the course， not in this section。

 here instead we're going to talk about cross validation or validation or cross validation。

 and these involve removing part of the data， holding it out。



![](img/c86edfc5418fe3d38620250de9e815d5_137.png)

![](img/c86edfc5418fe3d38620250de9e815d5_138.png)

Ftting the model to the remaining part， and then applying that the fitted model to the data that we've held out。

 and this is called validation or cross validation， as we'll see。



![](img/c86edfc5418fe3d38620250de9e815d5_140.png)

![](img/c86edfc5418fe3d38620250de9e815d5_141.png)

![](img/c86edfc5418fe3d38620250de9e815d5_142.png)

So let's first of all talk about the validation approach。

 so here we're going to the simple idea is basically we're going to divide the data into two parts at random。



![](img/c86edfc5418fe3d38620250de9e815d5_144.png)

Approximately of equal size。

![](img/c86edfc5418fe3d38620250de9e815d5_146.png)

Well call the first part of ring set and the second part the validation or holdout set。

the idea is simple， we take the model， we fit it out on the training half。



![](img/c86edfc5418fe3d38620250de9e815d5_148.png)

And then we apply the fitted model to the other half， the validation or holdout set。



![](img/c86edfc5418fe3d38620250de9e815d5_150.png)

And we record the error that we get on the holdout set。



![](img/c86edfc5418fe3d38620250de9e815d5_152.png)

And that error， the validation set error， provides us a good idea of the test error。

 well at least some idea of the test error。

![](img/c86edfc5418fe3d38620250de9e815d5_154.png)

![](img/c86edfc5418fe3d38620250de9e815d5_155.png)

And the error will measure by mean square error in the case of quantitative response。Or。



![](img/c86edfc5418fe3d38620250de9e815d5_157.png)

This classification error or a rate in the case of a qualitative or discrete response。

 classification。

![](img/c86edfc5418fe3d38620250de9e815d5_159.png)

Okay so just to make that clear， and let's look at the next slide， we have our data set here。

 I've divided in two at random。

![](img/c86edfc5418fe3d38620250de9e815d5_161.png)

The blue part on the left is the training set in。

![](img/c86edfc5418fe3d38620250de9e815d5_163.png)

Orange part or pink part on the right is the validation or holdout set these observations。

 for example， 722 and 13 and more of them are part at random chosen to be in the training set。



![](img/c86edfc5418fe3d38620250de9e815d5_165.png)

![](img/c86edfc5418fe3d38620250de9e815d5_166.png)

Obs 91 was at random chosen to be in the holdout set。



![](img/c86edfc5418fe3d38620250de9e815d5_168.png)

We fit the model to the blue part， and then we apply it and predict the observations in the pink part。



![](img/c86edfc5418fe3d38620250de9e815d5_170.png)

And that's validation， or we might call that twofold validation。



![](img/c86edfc5418fe3d38620250de9e815d5_172.png)

Well， as may I shouldn't call it twofold because as we'll see we don't cross over。

 this is simply a one stage process we divide it in half。



![](img/c86edfc5418fe3d38620250de9e815d5_174.png)

Train on one half and predict on the other half。

![](img/c86edfc5418fe3d38620250de9e815d5_176.png)

It seems a little wasteful if you got a very small data ce yeah that is wasteful and as we'll see its cross foundation will remove that waste and be more efficient。

 but let's first of all see how this works。

![](img/c86edfc5418fe3d38620250de9e815d5_178.png)

![](img/c86edfc5418fe3d38620250de9e815d5_179.png)

![](img/c86edfc5418fe3d38620250de9e815d5_180.png)

。In the auto data， we're trying to recall we're comparing the linear model to high orbital polynomials in regression。



![](img/c86edfc5418fe3d38620250de9e815d5_182.png)

And we had 392 observations divided into so we divide up into two parts at random。



![](img/c86edfc5418fe3d38620250de9e815d5_184.png)

196 in one part and 196 in the other part。First part being the training set and the other part being the validation set。



![](img/c86edfc5418fe3d38620250de9e815d5_186.png)

Am。

![](img/c86edfc5418fe3d38620250de9e815d5_188.png)

Here's if we do this once。It was a single split and we record the mean square error。



![](img/c86edfc5418fe3d38620250de9e815d5_190.png)

We get this red curve as a function of the degree of the polynomial。

 so a linear fits on the left and quadratic is here， etc ce as we increase the polynomial order。



![](img/c86edfc5418fe3d38620250de9e815d5_192.png)

![](img/c86edfc5418fe3d38620250de9e815d5_193.png)

And we see the minimum seems to occur maybe around two。



![](img/c86edfc5418fe3d38620250de9e815d5_195.png)

Well， it's rising a bit and coming down a bit after that， it's pretty flat after vote two。



![](img/c86edfc5418fe3d38620250de9e815d5_197.png)

So it looks like a linear model， actually a quadriotic model， excuse me is probably the best。

 and then after that we're not getting much gain if any at all。



![](img/c86edfc5418fe3d38620250de9e815d5_199.png)

But look what happens when we repeat this process with more and more splits at random into two parts。

 we had a lot of variability the minimums does tend to occur around two。



![](img/c86edfc5418fe3d38620250de9e815d5_201.png)

![](img/c86edfc5418fe3d38620250de9e815d5_202.png)

Generally， but look at the air， it's severing from about 16 up to 24 depending on the split。



![](img/c86edfc5418fe3d38620250de9e815d5_204.png)

So this is。This is a consequence， partly the fact that we divided the data up into two parts。



![](img/c86edfc5418fe3d38620250de9e815d5_206.png)

When you divide data in two， you get a lot of variability depending on the split。

 the training set for example， is half as big as it was originally。



![](img/c86edfc5418fe3d38620250de9e815d5_208.png)

![](img/c86edfc5418fe3d38620250de9e815d5_209.png)

So it's interesting， Rob， that even though you get that variability。

 it seems to often have this pattern where the shape of the curves are much the same， but the height。

 the level hops around。

![](img/c86edfc5418fe3d38620250de9e815d5_211.png)

![](img/c86edfc5418fe3d38620250de9e815d5_212.png)

So that's a good point and it actually reminds me to say there's two things we want to use validation for or cross validation。

 both to pick the best size of the model in this case， the degree of polynomial。

 and also to give us an idea of how good the error is to give an idea of the actual test error at the end of the。



![](img/c86edfc5418fe3d38620250de9e815d5_214.png)

![](img/c86edfc5418fe3d38620250de9e815d5_215.png)

![](img/c86edfc5418fe3d38620250de9e815d5_216.png)

Of the fitting process。

![](img/c86edfc5418fe3d38620250de9e815d5_218.png)

Twofold， this。Breaking up into two parts is successful at the first thing， as Trevor has mentioned。

 the minimums are around two pretty consistently。

![](img/c86edfc5418fe3d38620250de9e815d5_220.png)

![](img/c86edfc5418fe3d38620250de9e815d5_221.png)

So that seems to be okay， but the actual level of the curve is varying a lot。

 so it wouldn't be so good at telling us an idea of the error because we get a very wide range here。



![](img/c86edfc5418fe3d38620250de9e815d5_223.png)

In here。

![](img/c86edfc5418fe3d38620250de9e815d5_225.png)

So。So I've said a little bit of the first point already that。



![](img/c86edfc5418fe3d38620250de9e815d5_227.png)

Its this method is highly variable because we're splitting into two parts and there's lots of ways to split data into two parts and because we're splitting in two。

 we're losing a lot of the。

![](img/c86edfc5418fe3d38620250de9e815d5_229.png)

The power and the training set were throwing away half the data each time in training。



![](img/c86edfc5418fe3d38620250de9e815d5_231.png)

嗯。

![](img/c86edfc5418fe3d38620250de9e815d5_233.png)

And。Another consequence of that is that you remember one of our original questions was， well。



![](img/c86edfc5418fe3d38620250de9e815d5_235.png)

What's the best size model to pick， second of all， how well does that model do in terms of test error？



![](img/c86edfc5418fe3d38620250de9e815d5_237.png)

Our training sets here are half as big as our original training set。

 I if to go back to this previous slide， right we've split the date in half。

 we actually want the test error for a training set of size n。

 we're getting an idea of test error for a training set of size n over two。



![](img/c86edfc5418fe3d38620250de9e815d5_239.png)

![](img/c86edfc5418fe3d38620250de9e815d5_240.png)

![](img/c86edfc5418fe3d38620250de9e815d5_241.png)

And that's likely to be quite a bit higher than。

![](img/c86edfc5418fe3d38620250de9e815d5_243.png)

你。The error4。A training set of size n。

![](img/c86edfc5418fe3d38620250de9e815d5_245.png)

Why wrong， why。That was my question。

![](img/c86edfc5418fe3d38620250de9e815d5_247.png)

Well， that's because in general， the more data one has the lower the error if I offer you your choice of would you' rather have 100 observations or 200 observations。

 you'd generally like 200 observations to train on because the more data the more information you have and in general the lower your error is so if your training sets is only half as big as your original training set。

As it is in this situation， the error that it yields is probably going to be higher than the actual error you want to get。

So as we can see， there's some drawbacks of validation。In the next section。

 we'll talk about cross validation， which will help to remove some of these drawbacks。

