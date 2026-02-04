# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P26：P26 StatsLearning Lect7b 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/2017bd2dd44670bea96c352827ccd330_0.png)

Welcome back。In the last section， we talked about validation and we saw some drawbacks for that method。

 Now we're going to talk about K4 cross validation， which will solve some of these problems。

This is actually a very important technique that we're going to use throughout the course in various sections and also something that we use in our work all the time。



![](img/2017bd2dd44670bea96c352827ccd330_2.png)

So it's really important to understand capable flow cross validation， it's used for a lot of methods。

 it's extremely flexible and a powerful technique for estimating prediction error and to get an idea of model complexity。



![](img/2017bd2dd44670bea96c352827ccd330_4.png)

![](img/2017bd2dd44670bea96c352827ccd330_5.png)

![](img/2017bd2dd44670bea96c352827ccd330_6.png)

So what's the idea of create flow cross validation Well， it's really in the name。

 it's validation as we've seen， but done。

![](img/2017bd2dd44670bea96c352827ccd330_8.png)

Sort of like a K part play， it's done K times。

![](img/2017bd2dd44670bea96c352827ccd330_10.png)

With each part。Againing to play the role of the validation set and the other k minus1 parts。



![](img/2017bd2dd44670bea96c352827ccd330_12.png)

Playing the role of the training set。

![](img/2017bd2dd44670bea96c352827ccd330_14.png)

Should I say here， but let me go to the picture here。



![](img/2017bd2dd44670bea96c352827ccd330_16.png)

And I'll sort of point the picture as I say it， so here we're doing fivefold cross validation。



![](img/2017bd2dd44670bea96c352827ccd330_18.png)

As we'll talk about in a more detail， the best choices for K in number of folds is usually about five or 10。



![](img/2017bd2dd44670bea96c352827ccd330_20.png)

Okay so and I'll explain we'll talk about that in a few minutes about why those are good choices。

 but let's fix here k equals 5。

![](img/2017bd2dd44670bea96c352827ccd330_22.png)

So I've taken the data set， I've divided it at random the samples into five parts， again。

 of size about the same。

![](img/2017bd2dd44670bea96c352827ccd330_24.png)

![](img/2017bd2dd44670bea96c352827ccd330_25.png)

The grace box looks a bit bigger，Okay， so that's my lack of。



![](img/2017bd2dd44670bea96c352827ccd330_27.png)

Drawing ability， but anyway it's supposed to be the same that's trying try to squish the word validation in so the boxes is supposed to about the same size and observations。

 number of observations， but in this case the first parts through the validation set。

 the other four are the training parts。

![](img/2017bd2dd44670bea96c352827ccd330_29.png)

![](img/2017bd2dd44670bea96c352827ccd330_30.png)

![](img/2017bd2dd44670bea96c352827ccd330_31.png)

So what we're going to do， what Cross Foundation does。It forms these five parts。

 we're going to train the model on the four training parts put together as one big block。



![](img/2017bd2dd44670bea96c352827ccd330_33.png)

![](img/2017bd2dd44670bea96c352827ccd330_34.png)

Take the fitted model， and then。Predict on the validation part and record the error。

 and then that's phase one， phase two we' going to the validation set will be part two， this block。

 all the other four parts will be the training set。



![](img/2017bd2dd44670bea96c352827ccd330_36.png)

![](img/2017bd2dd44670bea96c352827ccd330_37.png)

![](img/2017bd2dd44670bea96c352827ccd330_38.png)

We fit the model to this rating set and then apply it to this validation part。



![](img/2017bd2dd44670bea96c352827ccd330_40.png)

And in the third stage， this is the validation piece， et cetera。

 so we have sort of we have five stages where each。



![](img/2017bd2dd44670bea96c352827ccd330_42.png)

And in each stage， one part gets to play the role of validation set。

 the other four parts of the training set。

![](img/2017bd2dd44670bea96c352827ccd330_44.png)

We take all the prediction errors from all five parts。

 we add them together and that gives us what's called the cross validation error。



![](img/2017bd2dd44670bea96c352827ccd330_46.png)

![](img/2017bd2dd44670bea96c352827ccd330_47.png)

So。Now in algebra， I'll basically give you the details of what I said in words。

 so we'll let the K parts。

![](img/2017bd2dd44670bea96c352827ccd330_49.png)

B of the data be C1 through C。

![](img/2017bd2dd44670bea96c352827ccd330_51.png)

So these are the observations that are in each of the five parts， remember K was five in our example。



![](img/2017bd2dd44670bea96c352827ccd330_53.png)

And we'll try to make the number of observations about the same in every part。

 Of course if ends on a multiple of k of5， we can't do that exactly， but we'll do it approximately。



![](img/2017bd2dd44670bea96c352827ccd330_55.png)

So it'll let end sub KB the number of observations in the case part。



![](img/2017bd2dd44670bea96c352827ccd330_57.png)

So here's the cross validation error rate。Basically。



![](img/2017bd2dd44670bea96c352827ccd330_59.png)

This is the means square error we get by applying。At the。



![](img/2017bd2dd44670bea96c352827ccd330_61.png)

，We fit to the。The K minus one parts that don't evolve。



![](img/2017bd2dd44670bea96c352827ccd330_63.png)

Part number K that gives us our fit Y eye hat。For observation I， full fifth of the data in this case。

 right and then we add up the error， this is the mean square error that we obtain now on the validation part using that model。



![](img/2017bd2dd44670bea96c352827ccd330_65.png)

![](img/2017bd2dd44670bea96c352827ccd330_66.png)

So this is for the cave part。

![](img/2017bd2dd44670bea96c352827ccd330_68.png)

And now we do this for all five parts in turn， the five acts of the play。

 and then we get the cross validation error rate。

![](img/2017bd2dd44670bea96c352827ccd330_70.png)

嗯。

![](img/2017bd2dd44670bea96c352827ccd330_72.png)

And a special case of this is leave1 L cross validation where the number of folds is the same number of observations。



![](img/2017bd2dd44670bea96c352827ccd330_74.png)

![](img/2017bd2dd44670bea96c352827ccd330_75.png)

In this picture that actually would be。One box per observation。

 and in leave one out cross validation， each observation by itself gets to play the role of the validation set。

 the other n minus one are the training set。

![](img/2017bd2dd44670bea96c352827ccd330_77.png)

![](img/2017bd2dd44670bea96c352827ccd330_78.png)

![](img/2017bd2dd44670bea96c352827ccd330_79.png)

Li。Now， actually leaving out cross validation there's a nice special case of that。

 it represents a nice special case in the sense that this cross validation can be done without actually having to refit the model at all。



![](img/2017bd2dd44670bea96c352827ccd330_81.png)

![](img/2017bd2dd44670bea96c352827ccd330_82.png)

![](img/2017bd2dd44670bea96c352827ccd330_83.png)

So we went to cross validation。At least for a least squares model or a polynomial model。

 if the cross validation。

![](img/2017bd2dd44670bea96c352827ccd330_85.png)

![](img/2017bd2dd44670bea96c352827ccd330_86.png)

Lenal Cross F has the following form， so the why I had is now just to fit on the full data。



![](img/2017bd2dd44670bea96c352827ccd330_88.png)

HI is the。

![](img/2017bd2dd44670bea96c352827ccd330_90.png)

An。Diaagonal of the hat matrix。 So have a look in the book for details。 but the hat matrix is the。



![](img/2017bd2dd44670bea96c352827ccd330_92.png)

Projection matrix that projects Y onto the column space of x to give you the fit。

 This is something that can get computed easily when you fit your least squares model。

 So yeah we don't we haven't emphasized it， but it's available。

 It's one of the things that's available when you fit your least squares model。

 So the overall point of this is that to do Le O cross validation for these particular models。

 you don't actually have to leave anything out。 you can do the fit on the overall data set and then extract the information you need to get the cross validation summer squares and it's interesting because the H tells you how much influence and observation has in its own fit。

 It's a number between0 and1。

![](img/2017bd2dd44670bea96c352827ccd330_94.png)

![](img/2017bd2dd44670bea96c352827ccd330_95.png)

![](img/2017bd2dd44670bea96c352827ccd330_96.png)

![](img/2017bd2dd44670bea96c352827ccd330_97.png)

![](img/2017bd2dd44670bea96c352827ccd330_98.png)

![](img/2017bd2dd44670bea96c352827ccd330_99.png)

![](img/2017bd2dd44670bea96c352827ccd330_100.png)

And so if an observation is very influential in its own foot。

 you can see it punishes the residual because it divides by a number that's small and it inflates a residual。

 So it sort of does the right thing yeah。

![](img/2017bd2dd44670bea96c352827ccd330_102.png)

![](img/2017bd2dd44670bea96c352827ccd330_103.png)

![](img/2017bd2dd44670bea96c352827ccd330_104.png)

Okay， so。

![](img/2017bd2dd44670bea96c352827ccd330_106.png)

A better， although leaving all cross validation does have this nice computational formula for most of the methods we talk about in this book and most statistical learning methods。



![](img/2017bd2dd44670bea96c352827ccd330_108.png)

It's better to choose K to be 5 or 10， rather than leave an all cross Foundation。



![](img/2017bd2dd44670bea96c352827ccd330_110.png)

And why is that？

![](img/2017bd2dd44670bea96c352827ccd330_112.png)

One problem with Le one El Cross validation is that each of the training sets look very much like the other ones。

 right， they only differ by one observation。

![](img/2017bd2dd44670bea96c352827ccd330_114.png)

So when you take the average。

![](img/2017bd2dd44670bea96c352827ccd330_116.png)

Cross Foundation is you take the average of errors。



![](img/2017bd2dd44670bea96c352827ccd330_118.png)

Over the end folds， and in leave and out cross validation。

 the end folds look very similar to each other because the training sets are almost the same。

 they're only different by one observation。

![](img/2017bd2dd44670bea96c352827ccd330_120.png)

![](img/2017bd2dd44670bea96c352827ccd330_121.png)

So as a result， that average has a high variance because the ingredients are highly correlated。

So that's the main reason why。

![](img/2017bd2dd44670bea96c352827ccd330_123.png)

ItIt's thought， and we also agree that a better choice for K and cross validation is5 or 1。



![](img/2017bd2dd44670bea96c352827ccd330_125.png)

On the other hand， the leave one out cross validation is actually trying to estimate the error rate for the training sample of almost the same size as what you have。



![](img/2017bd2dd44670bea96c352827ccd330_127.png)

![](img/2017bd2dd44670bea96c352827ccd330_128.png)

So it's got low bias， but as Rob said high variance。

 so actually picking K is also a bias variance trade off for prediction area and as Rob said。

 K equals 5 or10 tend to be a good choice。

![](img/2017bd2dd44670bea96c352827ccd330_130.png)

![](img/2017bd2dd44670bea96c352827ccd330_131.png)

![](img/2017bd2dd44670bea96c352827ccd330_132.png)

So on the next slide， we've got a comparison of even out cross validation。



![](img/2017bd2dd44670bea96c352827ccd330_134.png)

And tenfold CV for the auto data， remember before we saw with twofold validation， what was our with？



![](img/2017bd2dd44670bea96c352827ccd330_136.png)

This validation into two parts， we've got a lot of variability between the 10 the。



![](img/2017bd2dd44670bea96c352827ccd330_138.png)

When we change the sample the half sample that we took。



![](img/2017bd2dd44670bea96c352827ccd330_140.png)

Now let's see what happens with leave it all cross validation， we get a curve that's。



![](img/2017bd2dd44670bea96c352827ccd330_142.png)

Again got the minimum around the same place as we saw before。



![](img/2017bd2dd44670bea96c352827ccd330_144.png)

And it's pretty flat after that。10 full cross foundation。 Now， again。

 it's it's also showing the minimum around two， but it's there's not the what we're seeing here is the。



![](img/2017bd2dd44670bea96c352827ccd330_146.png)

T0fold cross validation as we take。

![](img/2017bd2dd44670bea96c352827ccd330_148.png)

Different partitions into 10 parts of the data， and we see there's not much variability。

 they're pretty consistent。

![](img/2017bd2dd44670bea96c352827ccd330_150.png)

In contrast to the we divided into two parts， we got much more variability。



![](img/2017bd2dd44670bea96c352827ccd330_152.png)

And those get averaged as well， those curves in the right exactly yeah so they're averaged together。



![](img/2017bd2dd44670bea96c352827ccd330_154.png)

![](img/2017bd2dd44670bea96c352827ccd330_155.png)

Which we saw here， they're averaged together to give us the overall estimate of cross validation。



![](img/2017bd2dd44670bea96c352827ccd330_157.png)

Which the overall cross validation curve。Well look very much like this with its minimum around。



![](img/2017bd2dd44670bea96c352827ccd330_159.png)

就。

![](img/2017bd2dd44670bea96c352827ccd330_161.png)

Okay， this is。

![](img/2017bd2dd44670bea96c352827ccd330_163.png)

This is figure 5。6 from the textbook， and this is the simulated data example。

 which was figured from figure 2。9 of the book。

![](img/2017bd2dd44670bea96c352827ccd330_165.png)

Just recall that this is smoothing splines in three different situations。



![](img/2017bd2dd44670bea96c352827ccd330_167.png)

In this case， the true curve， true air curve is the blue curve。



![](img/2017bd2dd44670bea96c352827ccd330_169.png)

And again， these three different functions that we're examining。

 this is mean square error for simulated data， a true error curve， how do we get that drug？



![](img/2017bd2dd44670bea96c352827ccd330_171.png)

![](img/2017bd2dd44670bea96c352827ccd330_172.png)

Well it simulated data。 so we just so we can get we can get a very big test set exactly and estimate the error exactly Le all cross Foundation is the。



![](img/2017bd2dd44670bea96c352827ccd330_174.png)

![](img/2017bd2dd44670bea96c352827ccd330_175.png)

The black broken line。And the orange curve is ten0fold cross validation。



![](img/2017bd2dd44670bea96c352827ccd330_177.png)

So we can see what do we see， Well， here we see that。



![](img/2017bd2dd44670bea96c352827ccd330_179.png)

Test our curve is little higher than the。

![](img/2017bd2dd44670bea96c352827ccd330_181.png)

Tenfold and leave one out cross validation。The minimums。Fairly close。

 but the minimum of cross validation is around eight。

 whereas the true curve is minimize it around six。

![](img/2017bd2dd44670bea96c352827ccd330_183.png)

![](img/2017bd2dd44670bea96c352827ccd330_184.png)

In this case， the two cross validation athletes are doing a better job of approximating the test error curve and have the minimum- well。

 the minimums， again， the fairly close， not exactly on the mark， black curve minimize around six。



![](img/2017bd2dd44670bea96c352827ccd330_186.png)

![](img/2017bd2dd44670bea96c352827ccd330_187.png)

![](img/2017bd2dd44670bea96c352827ccd330_188.png)

And the true air curve is minimized around。That'sMaybe three。

 although those Eric curve are fairly flat， so there's obviously a high variance in where the minimum should be。



![](img/2017bd2dd44670bea96c352827ccd330_190.png)

![](img/2017bd2dd44670bea96c352827ccd330_191.png)

Right， and that doesns really matter。That's right， it's not going to matter much if you choose a model with flexibility two or maybe even 10 here because the error is pretty flat in that region。



![](img/2017bd2dd44670bea96c352827ccd330_193.png)

![](img/2017bd2dd44670bea96c352827ccd330_194.png)

And then the third example， the two cross validation curves do quite a good job of approximating the test error curve。



![](img/2017bd2dd44670bea96c352827ccd330_196.png)

And the minimum is around 10 in each case。

![](img/2017bd2dd44670bea96c352827ccd330_198.png)

Okay。

![](img/2017bd2dd44670bea96c352827ccd330_200.png)

So actually， I said this already， but I'll say it again that one issue with cross validation is that since the training set is not as big as the original training set。



![](img/2017bd2dd44670bea96c352827ccd330_202.png)

![](img/2017bd2dd44670bea96c352827ccd330_203.png)

The essence of predictionary will be。We'll be biased up a little bit because we have less data we're working with。



![](img/2017bd2dd44670bea96c352827ccd330_205.png)

And。And I also said and I'll say again that leave one on cross validation。



![](img/2017bd2dd44670bea96c352827ccd330_207.png)

Has smaller bias in this sense because the training set is almost the same size as the original set。

 but the other hand it's got a higher variance because the training sets that it's using are almost the same as the original set。

 the only different by one observation。

![](img/2017bd2dd44670bea96c352827ccd330_209.png)

![](img/2017bd2dd44670bea96c352827ccd330_210.png)

![](img/2017bd2dd44670bea96c352827ccd330_211.png)

So a K equals five or ten fold is a good compromise for this biopherence trade off。



![](img/2017bd2dd44670bea96c352827ccd330_213.png)

Okay， so we talked about cross validation for a quantitative response and we use mean square error for classification problems that it is exactly the same。

 the only thing it changes is a measure of error， of course you no longer use square error。

 but a misclassification error， otherwise cross validation process is exactly the same。



![](img/2017bd2dd44670bea96c352827ccd330_215.png)

![](img/2017bd2dd44670bea96c352827ccd330_216.png)

![](img/2017bd2dd44670bea96c352827ccd330_217.png)

![](img/2017bd2dd44670bea96c352827ccd330_218.png)

Do I the up into K parts？We train on k minus1 parts。



![](img/2017bd2dd44670bea96c352827ccd330_220.png)

We record the error on the case part and we add things up together to get the overall cross validation error。

 It looks like a weighted average genetic that foam in a room。



![](img/2017bd2dd44670bea96c352827ccd330_222.png)

There's N K over n Well do you want to explain that because each of the folds might not be exactly the same size so we actually compute weight which is proportion to this which is the relative size of the fold and then use the weighted average and if we are lucky that the k divides the n divides by K exactly then that weight will just be1 one over K？



![](img/2017bd2dd44670bea96c352827ccd330_224.png)

![](img/2017bd2dd44670bea96c352827ccd330_225.png)

![](img/2017bd2dd44670bea96c352827ccd330_226.png)

![](img/2017bd2dd44670bea96c352827ccd330_227.png)

![](img/2017bd2dd44670bea96c352827ccd330_228.png)

One other thing to add which is that since this cross validation error just an average。

 the standard error of that average also gives us a standard error of the cross validation estimate。

 so we take the error rates from each of the folds， their average is the cross validation error rate。



![](img/2017bd2dd44670bea96c352827ccd330_230.png)

![](img/2017bd2dd44670bea96c352827ccd330_231.png)

![](img/2017bd2dd44670bea96c352827ccd330_232.png)

![](img/2017bd2dd44670bea96c352827ccd330_233.png)

Their standard error is the standard deviation of the cross validation estimate。

 so here's the formula for that， so this is a useful quantity and when we draw CV curves we should always put a standard error band around the curve at of the variability so in these previous pictures we should have had a standard error band around the curves to give us an idea of how variable they are。



![](img/2017bd2dd44670bea96c352827ccd330_235.png)

![](img/2017bd2dd44670bea96c352827ccd330_236.png)

![](img/2017bd2dd44670bea96c352827ccd330_237.png)

![](img/2017bd2dd44670bea96c352827ccd330_238.png)

I say here it' useful but not quite valid。

![](img/2017bd2dd44670bea96c352827ccd330_240.png)

Why is that？Dr。 Hastty。

![](img/2017bd2dd44670bea96c352827ccd330_242.png)

Well， I wonder why， well the thing is we compute in the standard errors if these were independent observations。

 but they're not strictly independent Arab subK overlaps with error sub J because they share some training samples。



![](img/2017bd2dd44670bea96c352827ccd330_244.png)

![](img/2017bd2dd44670bea96c352827ccd330_245.png)

![](img/2017bd2dd44670bea96c352827ccd330_246.png)

So there's some correlation between them， but we use this anyway。

 we use it it's actually quite a good estimate， and people have shown this mathematically。



![](img/2017bd2dd44670bea96c352827ccd330_248.png)

![](img/2017bd2dd44670bea96c352827ccd330_249.png)

Again， the important point being that is that the cross validation separates the training part of the data from the validation part。



![](img/2017bd2dd44670bea96c352827ccd330_251.png)

When we talk about the bootsottrap method in the next part of this section。

 we'll see that that's not the case and that's going to cause a problem。

 so cross validation explicitly separates the training set from the validation set in order to get a good idea of test error。



![](img/2017bd2dd44670bea96c352827ccd330_253.png)

![](img/2017bd2dd44670bea96c352827ccd330_254.png)

![](img/2017bd2dd44670bea96c352827ccd330_255.png)

Okay， so。This again， just want want to reemphasize that cross validation is a very important technique to understand both for quantitative response and cross validation and classification。



![](img/2017bd2dd44670bea96c352827ccd330_257.png)

![](img/2017bd2dd44670bea96c352827ccd330_258.png)