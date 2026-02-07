# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P34：-034-Statistical Learning_ 5.2 K-fold Cross Validation.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

Welcome back。In the last section， we talked about validation and we saw some drawbacks for that method。

 Now we're going to talk about K4 cross validation， which will solve some of these problems。

This is actually a very important technique that we're going to use throughout the course in various sections and also something that we use in our work all the time。

So it's really important to understand OK flow cross validation， it's used for a lot of methods。

 it's extremely flexible and a powerful technique for imating prediction error and to get an idea of model complexity。



![](img/462f920e799dbdba1b6a4261442b8746_1.png)

![](img/462f920e799dbdba1b6a4261442b8746_2.png)

So what's the idea of creating flow cross validation， well， it's really in the name。

 it's validation as we've seen， but done。Sort of like a K part play， it's done K times。

With each part。aing to play the role of the validation set and the other K minus1 parts。

Playing the role of the training set。

![](img/462f920e799dbdba1b6a4261442b8746_4.png)

Shouldha I say here， but let me go to the picture here。



![](img/462f920e799dbdba1b6a4261442b8746_6.png)

And I'll sort of point the picture as I say it， so here we're doing fivefold cross validation。

As we'll talk about in more detail， the best choices for K in the number of folds is usually about five or 10。

Okay so and I'll explain- we'll talk about that in a few minutes about why those are good choices。

 but let's fix here k equals 5。So I've taken the data set。

 I've divided it random the samples into five parts， again of size about the same。

And the grace box looks a bit bigger，Okay， so that's my my lack of。Drawing ability。

 but anyway it's supposed to be the same's to squish the word validation in。

 so the boxes is are supposed to about the same size and observations， number of observations。

 but in this case the first parts through the validation set， the other four are the training parts。

So what we're going to do， what Cross Foundation does。

It forms these five parts we're going to train the model on the four training parts put together as one big block。

Take the fitted model， and then。Predict on the validation part and record the error and then that's phase one。

 phase two， we're going to the validation set will be part two， this block。

 all the other four parts will be the training set。

We fit the model to this training set and then apply it to this validation part。

And in the third stage， this is the validation piece， et cetera。

 so we have sort of we have five stages where each。And in each stage。

 one part gets to play the role of validation set， the other four parts are the training set。

We take all the prediction errors from all five parts。

 we add them together and that gives us what's called the cross validation error。



![](img/462f920e799dbdba1b6a4261442b8746_8.png)

So。Now in algebra， I'll basically give you the details of what I said in words。

 so we'll let the K parts。B of the data B C1 through C。

So these are the observations that are in each of the five parts， remember K was five in our example。

And we'll try to make the number of observations about the same in every part。 Of course。

 if ends on a multiple of k of5， we can't do that exactly， but we'll do it approximately。

So we'll let end sub K be the number of observations in the case part。



![](img/462f920e799dbdba1b6a4261442b8746_10.png)

![](img/462f920e799dbdba1b6a4261442b8746_11.png)

So here's the cross validation error rate。Basically。



![](img/462f920e799dbdba1b6a4261442b8746_13.png)

This is the mean square area we get by applying。At the。



![](img/462f920e799dbdba1b6a4261442b8746_15.png)

，We fit to the。The K minus1 parts that don't evolve。Part number K that gives us our fit Y I hat。

For observation I，'s full fifth of the data in this case， right and then we add up the error。

 this is the mean square error that we obtain now on the validation part using that model。

So this is for the Ca part。And now we do this for all five parts in turn， the five acts of the play。

 and then we get the cross validation error rate。

![](img/462f920e799dbdba1b6a4261442b8746_17.png)

嗯。

![](img/462f920e799dbdba1b6a4261442b8746_19.png)

And a special case of this is leave 1 out cross validation where the number of folds is the same number of observations。



![](img/462f920e799dbdba1b6a4261442b8746_21.png)

![](img/462f920e799dbdba1b6a4261442b8746_22.png)

In this picture that actually would be。One box per observation， and in leave on out cross validation。

 each observation by itself gets to play the role of the validation set。

 the other n minus1 are the training set。

![](img/462f920e799dbdba1b6a4261442b8746_24.png)

![](img/462f920e799dbdba1b6a4261442b8746_25.png)

Me。Now， actually， leaving out cross validation there's a nice special case of that。

 it represents a nice special case in the sense that this cross validation can be done without actually having to refit the model at all。



![](img/462f920e799dbdba1b6a4261442b8746_27.png)

So weve went to cross validation。At least for a least squares model or a polynomial model。

 if the cross validation。Len Cross relation has the following form。

 so the why I had is now just to fit on the full data。HI is the。Dagonal of the hat matrix。

 So have a have a look in the book for details but the hat matrix is the。



![](img/462f920e799dbdba1b6a4261442b8746_29.png)

Projection matrix that projects Y onto the column space of x to give you the fit。

 This is something that can get computed easily when you fit your least squares model。 So yeah。

 we don't we haven't emphasized it。 but it's available。

 It's one of the things that's available when you fit your least squares model。

 So the overall point of this is that to do leave no cross validation for these particular models。

 You don't actually have to leave anything out。 You can do the fit on the overall data set and then extract the information you need to get the cross validation summer squares and it's interesting because the H tells you how much influence and observation has in its own fit。

 It's a number between0 and1。

![](img/462f920e799dbdba1b6a4261442b8746_31.png)

![](img/462f920e799dbdba1b6a4261442b8746_32.png)

![](img/462f920e799dbdba1b6a4261442b8746_33.png)

![](img/462f920e799dbdba1b6a4261442b8746_34.png)

And so if an observation is very influential in its own foot。

 you can see it punishes the residual because it divides by a number that's small and it inflates a residual。

 So it sort of does the right thing here。

![](img/462f920e799dbdba1b6a4261442b8746_36.png)

![](img/462f920e799dbdba1b6a4261442b8746_37.png)

Okay， so。A better， although leaving all cross validation does have this nice computational formula for most of the methods we talk about in this book and most statistical learning methods。

It's better to choose k to be5 or 10， rather than leave an all cross validation。And why is that？

One problem with leaving El Cross validation is that each of the training sets look very much like the other ones。

 right， they only differ by one observation。So when you take the average。

Cross Foundation is you take the average of errors。Over the n folds。

 and in leaving out cross validation， the end folds look very similar to each other because the training sets are almost the same。

 they're only different by one observation。So as a result。

 that average has a high variance because the ingredients are highly correlated。

So that's the main reason why。It's thought， and we also agree that a better choice for K and cross validation is five or 10。

On the other hand， the leave1 out cross validation is actually trying to estimate the error rate for the training sample of almost the same size as what you have。

So it's got low bias， but as Rob said high variance。

 so actually picking K is also a bias variance trade off for prediction area and as Rob said。

 K equals five or10 tend to be a good choice。So on the next slide。

 we've got a comparison of even out cross validation。And tenfold CV for the auto data。

 remember before we saw with twofold validation， what we started with。

Thisis validation into two parts， we got a lot of variability between the 10D。

When we change the sample the half sample that we took。

Now let's see what happens with leave it all cross validation， we get a curve that's。

Again got the minimum around the same place as we saw before。And then it's pretty flat after that。

10 full cross foundation now again， it's also showing the minimum around two。

 but it's there's not the what we're seeing here is the。T0fold cross validation as we take。

Different partitions into 10 parts of the data， and we see there's not much variability。

 they're pretty consistent。In contrast to the we divided into two parts。

 we got much more variability。

![](img/462f920e799dbdba1b6a4261442b8746_39.png)

And those get averaged as well， those curve in the right exactly Yeah， so they're averaged together。



![](img/462f920e799dbdba1b6a4261442b8746_41.png)

![](img/462f920e799dbdba1b6a4261442b8746_42.png)

Which we saw here， they're averaged together to give us the overall estimate of cross validation。



![](img/462f920e799dbdba1b6a4261442b8746_44.png)

Which the overall cross validation curve。We'll look very much like this with its minimum around。wo。



![](img/462f920e799dbdba1b6a4261442b8746_46.png)

Okay， this is。This is figure 5。6 from the textbook， and this is the simulated data example。

 which was figured from figure 2。9 of the book。Just recall that this is smoothing splies in three different situations。

In this case， the true curve， true air curve is the blue curve。And again。

 these three different functions that we're examining， this is mean square error for simulated data。

 a true error curve， how do we get that drug？Well simulated data。

 so we just so we can get we can get a very big test set exactly and estimate the area exactly Le all Cross Foundation is the。

The black broken line。And the orange curve is ten0fold cross validation。



![](img/462f920e799dbdba1b6a4261442b8746_48.png)

So we can see， what do we see， Well， here we see that。



![](img/462f920e799dbdba1b6a4261442b8746_50.png)

Test our curve is little higher than the。

![](img/462f920e799dbdba1b6a4261442b8746_52.png)

Tenfold and leave one out cross validation。The minimums。Fairly close。

 but the minimum of cross validation is around eight， whereas the true curve is minimize around six。



![](img/462f920e799dbdba1b6a4261442b8746_54.png)

In this case， the two cross validation athletes are doing a better job of approximating the test error curve and have the minimum。

 well， the minimums， again， there fairly close， not exactly on the mark。

 black curves minimize around six。

![](img/462f920e799dbdba1b6a4261442b8746_56.png)

And the true air curve is minimized around。maybe three， although those Ericers are fairly flat。

 so there's obviously a high variance in where the minimum should be。Right。

 and that doesn't really matter。You know， that's right。

 it's not going to matter much if you choose a model with flexibility two or maybe even 10 here because the air is pretty flat in that region。



![](img/462f920e799dbdba1b6a4261442b8746_58.png)

And then the third example， the two cross validation curves do quite a good job of approximating the test error curve。



![](img/462f920e799dbdba1b6a4261442b8746_60.png)

And the minimum is around 10 in each case。

![](img/462f920e799dbdba1b6a4261442b8746_62.png)

Okay。So actually， I said this already， but I'll say it again that one issue with cross validation is that since the training set is not as big as the original training set。

The essence of predictionary will be。We'll be biased up a little bit because we have less data we're working with。



![](img/462f920e799dbdba1b6a4261442b8746_64.png)

嗯m。And I also said and I'll say again that leave one our cross validation。



![](img/462f920e799dbdba1b6a4261442b8746_66.png)

Has smaller bias in this sense， because the training set is almost the same size as the original set。

 but the other hand it's got a higher variance because the training sets that it's using are almost the same as the original set。

 the only different by one observation。

![](img/462f920e799dbdba1b6a4261442b8746_68.png)

So a cake was five or ten fold is a good compromise for this bio experience trade off。



![](img/462f920e799dbdba1b6a4261442b8746_70.png)

Okay， so we talked about cross validation for a quantitative response and we use mean square error for classification problems。

 it is exactly the same， the only thing it changes is a measure of error。

 of course you no longer use square error， but a misclassification error。

 otherwise cross validationation process is exactly the same。



![](img/462f920e799dbdba1b6a4261442b8746_72.png)

![](img/462f920e799dbdba1b6a4261442b8746_73.png)

![](img/462f920e799dbdba1b6a4261442b8746_74.png)

Do I have the it up into K parts？We train on k minus1 parts。

We record the error on the case part and we add things up together to get the overall cross validation error。

 It looks like a weighted average genetic foam in。There's N K over N Well do you want to explain that because each of the folds might not be exactly the same size so we actually compute a weight which is proportioned to this which is the relative size of the fold and then use the weighted average and if we are lucky that the k divides the n divides by k exactly then that weight' will just be1 one over K。

One other thing to add， is that since this cross validation error just an average。



![](img/462f920e799dbdba1b6a4261442b8746_76.png)

![](img/462f920e799dbdba1b6a4261442b8746_77.png)

The standard error of that average also gives us a standard error of the cross validation estimate。

 So we take the error rates from each of the folds。 Their average is the cross validation error rate。

Their standard error is the standard deviation of the cross validation estimate。

 so here's the formula for that so this is a useful quantity and when we draw CV curves we should always put a standard error band around the curve at get of the variability so in these previous pictures we should have had a standard error band around the curves to give us an idea of how variable they are。



![](img/462f920e799dbdba1b6a4261442b8746_79.png)

![](img/462f920e799dbdba1b6a4261442b8746_80.png)

I say here it's useful of， but not quite valid。Why is that？Dr。 Hastty。Well， I wonder why。Well。

 the thing is we compute in the standard errors if these were independent observations。

 but they're not strictly independent Arab subK overlaps with error sub J because they share some training samples。

So there's some correlation between them， but we use this anyway using it's actually quite a good estimate and people have shown this mathematically。



![](img/462f920e799dbdba1b6a4261442b8746_82.png)

Again， the important point being that is that the cross validation separates the training part of the data from the validation part。



![](img/462f920e799dbdba1b6a4261442b8746_84.png)

When we talk about the bootsottrap method in the next part of this section。

 we'll see that that's not the case and that's going to cause a problem。

 so cross validation explicitly separates the training set from the validation set in order to get a good idea of test error。



![](img/462f920e799dbdba1b6a4261442b8746_86.png)

Okay， so this again， want I want to reemphasize that cross validation is a very important technique to understand。



![](img/462f920e799dbdba1b6a4261442b8746_88.png)

Both for quantitative response and cross validation and classification。



![](img/462f920e799dbdba1b6a4261442b8746_90.png)