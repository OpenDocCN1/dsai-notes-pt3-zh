# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P28：P28 StatsLearning Lect7d 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/b1a362a6d5e4ebe9419968e56d590696_0.png)

Welcome back in the last section we talked about cross validation。

For the estimation of test error for supervised learning。



![](img/b1a362a6d5e4ebe9419968e56d590696_2.png)

Now we'll talk about a closer related idea called the Boottrapap。



![](img/b1a362a6d5e4ebe9419968e56d590696_4.png)

It's a powerful method for assessing uncertainty and estimates， in particular。

 for getting an idea of standard errors of an estimate and getting confidence limits。



![](img/b1a362a6d5e4ebe9419968e56d590696_6.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_7.png)

Wellow， it sounds like a powerful technique Rob。 Are there any good books on the topic。



![](img/b1a362a6d5e4ebe9419968e56d590696_9.png)

As a matter of fact， Rob has got a very famous book with Brad Eron on the bootstrap Oh I've got a actually of famous my supervisor was Brad Efron who's now our colleague and he's the adventure of the bootsottrap and there's a conversation with Brad in this course which he talks about the how he came to think of the bootsottrap the bootsottrap was something he thought of in 1979 and it's become one of the most important techniques and statistics in the last。



![](img/b1a362a6d5e4ebe9419968e56d590696_11.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_12.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_13.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_14.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_15.png)

30 years。

![](img/b1a362a6d5e4ebe9419968e56d590696_17.png)

So where does the name come from， well， it's the idea of pulling yourself up by your bootstraps。

 which is from a fabled by Rudolph Eric Rasppe， the Barren Fa。



![](img/b1a362a6d5e4ebe9419968e56d590696_19.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_20.png)

The ventures of。Baon Munhausen the baron had fallen into the bottom of a deep lake。



![](img/b1a362a6d5e4ebe9419968e56d590696_22.png)

And couldn't get out。 So he had an idea。 He thought hed pulled himself up by his bootstraps。

 his own bootstraps。 And in the f， he managed to pull himself out of the lake。



![](img/b1a362a6d5e4ebe9419968e56d590696_24.png)

And saves life。Thought where the term Boottrapap came from and that's the term we're using here。



![](img/b1a362a6d5e4ebe9419968e56d590696_26.png)

It's not the same as the term bootsottrap that one uses computer science to boot a computer。

 but it's the same idea you're trying to pull yourself up from what you've got。



![](img/b1a362a6d5e4ebe9419968e56d590696_28.png)

In this case， we'll see the bootstrap。I give a Wood is we're going to use the data itself to try to get more information about our estimator。



![](img/b1a362a6d5e4ebe9419968e56d590696_30.png)

So let's。

![](img/b1a362a6d5e4ebe9419968e56d590696_32.png)

Let's start with a simple example。Suppose we have。

![](img/b1a362a6d5e4ebe9419968e56d590696_34.png)

WeF sum of money， but we want to invest。In two assets， the yield returns x and Y。



![](img/b1a362a6d5e4ebe9419968e56d590696_36.png)

We X and y are random quantities， depending on how these assets do。

 and we want to invest a fraction alpha of our money in X in the remaining1 minus alpha in y。



![](img/b1a362a6d5e4ebe9419968e56d590696_38.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_39.png)

You want to choose the fraction alpha to minimize the total risk or the variance of our investment。



![](img/b1a362a6d5e4ebe9419968e56d590696_41.png)

So we have random variables x and y， we want to choose the alpha to minimize the variance of alpha x plus1 minus alpha times y。



![](img/b1a362a6d5e4ebe9419968e56d590696_43.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_44.png)

Now in this population model， you can show that the best。

The best fraction alpha is given by this formula。

![](img/b1a362a6d5e4ebe9419968e56d590696_46.png)

Sigma squared y， that's the variance of y， there's a variance of x。

 this is the covariant between x and y。

![](img/b1a362a6d5e4ebe9419968e56d590696_48.png)

And they're defined here， so in other words， if we know the variances of x。

 the variance of y and their covariance。

![](img/b1a362a6d5e4ebe9419968e56d590696_50.png)

Then this is the。The best amount proportion to put into x and the main goes into Y to minimize the total variance。



![](img/b1a362a6d5e4ebe9419968e56d590696_52.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_53.png)

Okay， so those are population quantities aren't there。 Those are population quantities so。

Since the population quantities， they're not known to us。



![](img/b1a362a6d5e4ebe9419968e56d590696_55.png)

In general。But if we， if we have a。A data set from the population that we're under study here。

 we can get an idea of these quantities， the variances and the covariances。



![](img/b1a362a6d5e4ebe9419968e56d590696_57.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_58.png)

From the sample values from from the data set and then plug them into the formula to get a。



![](img/b1a362a6d5e4ebe9419968e56d590696_60.png)

The alpha hat， which is the proportion that we should invest in X。



![](img/b1a362a6d5e4ebe9419968e56d590696_62.png)

Okay。So again， we if we have a sample of x and Y， we can。



![](img/b1a362a6d5e4ebe9419968e56d590696_64.png)

Get the empirical estimates of the variances the covariances， plug the moon and get a。



![](img/b1a362a6d5e4ebe9419968e56d590696_66.png)

An estimate of alpha。So in this next slide we see we've created a simulated population've simulated。



![](img/b1a362a6d5e4ebe9419968e56d590696_68.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_69.png)

Investments X and Y。There's four different simulations here。

 each one containing 100 pairs of X and Y。

![](img/b1a362a6d5e4ebe9419968e56d590696_71.png)

And for each one， we take that data， we compute the variances and covariances。

 and we plug it into the formula to get an estimate for alpha。



![](img/b1a362a6d5e4ebe9419968e56d590696_73.png)

And here we see the four estimates of alpha for the four panels。



![](img/b1a362a6d5e4ebe9419968e56d590696_75.png)

。576， et cetera to 0。651， so they're averaging around 0。6。



![](img/b1a362a6d5e4ebe9419968e56d590696_77.png)

Okay。

![](img/b1a362a6d5e4ebe9419968e56d590696_79.png)

So if we want to get an idea of the standard deviation of alpha hat。

 we can just repeat this process lots of times， let's say a thousand times。

 so we've got a thousand panels like this， each one gives us an alpha hat。



![](img/b1a362a6d5e4ebe9419968e56d590696_81.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_82.png)

From the format on the previous slide。

![](img/b1a362a6d5e4ebe9419968e56d590696_84.png)

And we do this a thousand times。We take the standard standard error of those well。

 actually we do a thousand times， we'll go to the。

![](img/b1a362a6d5e4ebe9419968e56d590696_86.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_87.png)

Look at the histogram in a couple of slides。This histogram on the left shows the 1，000 values over 1。

000 simulations from this experiment。

![](img/b1a362a6d5e4ebe9419968e56d590696_89.png)

Each one is a value of alpha hat。

![](img/b1a362a6d5e4ebe9419968e56d590696_91.png)

And the average around 0。6。It's called the sampling and distribution of that estimator。



![](img/b1a362a6d5e4ebe9419968e56d590696_93.png)

And the true value actually， since we know in this case we're playing God， right。

 we know the true variances and covariances， we know the true alpha and it's about 0。

6 I've indicated here are the purple line the 0。6。

![](img/b1a362a6d5e4ebe9419968e56d590696_95.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_96.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_97.png)

And the sampling distribution is averaging around 0。6 as we think it should。



![](img/b1a362a6d5e4ebe9419968e56d590696_99.png)

嗯。So。The mean over the 1，000 estimates。

![](img/b1a362a6d5e4ebe9419968e56d590696_101.png)

Okay， I should say， yeah I've said this already。

![](img/b1a362a6d5e4ebe9419968e56d590696_103.png)

HereThe histogram we've seen。For the simulations actually。

 these were the values of the parameters that we set。



![](img/b1a362a6d5e4ebe9419968e56d590696_105.png)

And that implied a true value of alpha of 0。6， which was that middle value in the histogram。

 that's a true value of alpha。

![](img/b1a362a6d5e4ebe9419968e56d590696_107.png)

嗯。

![](img/b1a362a6d5e4ebe9419968e56d590696_109.png)

And now。We can also use this histogram to get to the standard deviation of the estimates just picking the standard deviation of those 1。

000 values of alpha hat。 and here we've done that。

![](img/b1a362a6d5e4ebe9419968e56d590696_111.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_112.png)

And that's 0。08 at 3。So the standard error of alpha hats roughly 。083。



![](img/b1a362a6d5e4ebe9419968e56d590696_114.png)

The standard error of an estimator is the standard deviation in that sampling distribution。

 So if you're able to recompute the estimator many， many times from new samples。

 the standard deviation is called the standard error so。



![](img/b1a362a6d5e4ebe9419968e56d590696_116.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_117.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_118.png)

If we repeat this experiment， we expect each time that the on average alpha hat will be about 0。6。



![](img/b1a362a6d5e4ebe9419968e56d590696_120.png)

And would vary by a standard deviation of 0。083， which we're seeing。



![](img/b1a362a6d5e4ebe9419968e56d590696_122.png)

In this histogram， right it's averaging about 0。08 and the standard deviationvi is's about 0。

08 of this histogram。

![](img/b1a362a6d5e4ebe9419968e56d590696_124.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_125.png)

O k。So that's all fine， except。We can't actually apply this with real data if we had a sample of investments。

 x and Y， we don't actually have the ability to sample from the population。

 we don't have the population， we have a single sample。So most of statistics。

 we don't have access to the population。All we have is a sample。If we had access to the population。

 we actually wouldn't need statistics at all for most of the part。

 we could learn all we wanted to know from the population。In the real world， we have data。

 we don't actually know the populations from which that data arose。

 we have an idea of what it looked might look like， but we can't generate more data。

So we can't actually。We can't produce the histogram on the left because we don't have the ability to generate more data。



![](img/b1a362a6d5e4ebe9419968e56d590696_127.png)

But the bootstrap is going to try， it's going to mimic this process by sampling not from the population。

 but from the data itself。So the data itself is going to act as the population。

So instead of obtaining independent data sets from the population， which we can't do。

Without access to the population。We're at to sample from the data itself with replacement。And'。

Remind you in a minute what that means。But。Basically。

 we a sample from the data set itself and then use those samples to get an idea of the variability in the same way that we use the samples from the population。

To produce this histogram。

![](img/b1a362a6d5e4ebe9419968e56d590696_129.png)

We're going to sample from the data。The data itself is the population。So。Here's an idea of this is。



![](img/b1a362a6d5e4ebe9419968e56d590696_131.png)

An illustration of bootstrap sampling， which is sampling with replacement。



![](img/b1a362a6d5e4ebe9419968e56d590696_133.png)

I've created a data here。Just with three observations just so we could draw it on a single slide。



![](img/b1a362a6d5e4ebe9419968e56d590696_135.png)

Here's our original data， here's the three observations。And now each of these is a bootstrap sample。

 bootstrapap sample is drawn。

![](img/b1a362a6d5e4ebe9419968e56d590696_137.png)

With replacement of the same the same size as the original data so the original data here iss about three observations so we're going to draw three observations with replacement。

 what does that mean， it means that the chance of each observation exampled is the same one third but it's done with replacement so imagine you put three balls into a bag。



![](img/b1a362a6d5e4ebe9419968e56d590696_139.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_140.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_141.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_142.png)

Say number one， two and three， we put a hand in the bag， we pull out one at random。

 maybe well get number one。

![](img/b1a362a6d5e4ebe9419968e56d590696_144.png)

That's our first observation， now to go to our second observation， we put the ball back in the bag。



![](img/b1a362a6d5e4ebe9419968e56d590696_146.png)

That's why it's called with replacement， and we sample again from all three balls。 So at every stage。



![](img/b1a362a6d5e4ebe9419968e56d590696_148.png)

Each ball has the same probability being sampled and can be sampled more than once at each from stage one to N。

 So here， for example。

![](img/b1a362a6d5e4ebe9419968e56d590696_150.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_151.png)

We've got observations three twice， and observation one once， Ob two didn't get sampled at all。



![](img/b1a362a6d5e4ebe9419968e56d590696_153.png)

In this second bootsstrrap sample， and we're drawing three samples from these three observations。

 we happen to get two， three， and one， so each observation actually occurred once。



![](img/b1a362a6d5e4ebe9419968e56d590696_155.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_156.png)

This next sample， we got observation two twice， and then observation one。



![](img/b1a362a6d5e4ebe9419968e56d590696_158.png)

So。Just to summarize， we sampled the same number of observations as at our original sample with replacement。

 meaning each observation can appear more than once or maybe not at all。

 depending on what happens as we draw the samples。

![](img/b1a362a6d5e4ebe9419968e56d590696_160.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_161.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_162.png)

So these are called Botrap samples。Bootriap data sets。



![](img/b1a362a6d5e4ebe9419968e56d590696_164.png)

And then。To each bootsrap data， we apply the estimator in this case are the alpha。

 this is the proportion of。

![](img/b1a362a6d5e4ebe9419968e56d590696_166.png)

Investment X。

![](img/b1a362a6d5e4ebe9419968e56d590696_168.png)

We compute it from this sample， just as we computed it from the original sample。

And we use the standard deviation of these numbers to give us an idea of the standard error。

 the standard deviation of alpha hat。

![](img/b1a362a6d5e4ebe9419968e56d590696_170.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_171.png)

So having drawn 1000 bootstrap samples and got our 1 thousand0 estimates of alpha hat。

 we can draw the histogram as we did before， let's go back to this slide。 So now back on slide 29。



![](img/b1a362a6d5e4ebe9419968e56d590696_173.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_174.png)

The member on the right， excuse me， on the left is the histogram when we sample from the population。



![](img/b1a362a6d5e4ebe9419968e56d590696_176.png)

The histogram alpha had values。

![](img/b1a362a6d5e4ebe9419968e56d590696_178.png)

We can't sample from the population because we don't have the population。

 so we did bootstrap sampling， we get the histogram in the middle of the blue histogram。



![](img/b1a362a6d5e4ebe9419968e56d590696_180.png)

And looks very much like the one on the left。It's averaging around 。

6 and its variability is about the same as。

![](img/b1a362a6d5e4ebe9419968e56d590696_182.png)

We got some from the population。

![](img/b1a362a6d5e4ebe9419968e56d590696_184.png)

As a matter of fact， well， so over here we've got the。



![](img/b1a362a6d5e4ebe9419968e56d590696_186.png)

Box plots of the alpha hat values。

![](img/b1a362a6d5e4ebe9419968e56d590696_188.png)

A。The true ones the sample from the population and the bootstrap ones。

 and they're looking pretty similar。

![](img/b1a362a6d5e4ebe9419968e56d590696_190.png)

You're averaging around 0。6 although the bootstrap is a little lower。



![](img/b1a362a6d5e4ebe9419968e56d590696_192.png)

In this case。In general， this gives you a pretty good idea of what we would get if we could sample from the population in the standard error estimate。



![](img/b1a362a6d5e4ebe9419968e56d590696_194.png)

Let's see that we have that in the next。

![](img/b1a362a6d5e4ebe9419968e56d590696_196.png)

Back here。Yeah， the standard error。Estimate is 0。087。



![](img/b1a362a6d5e4ebe9419968e56d590696_198.png)

Whi is similar， we got 0。083 before when we used to sample from the population。

 so the bootstrap has used the data itself as the population and got us a good estimate of the standard error。

 very similar to the one we get if we could sample from the population。



![](img/b1a362a6d5e4ebe9419968e56d590696_200.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_201.png)

![](img/b1a362a6d5e4ebe9419968e56d590696_202.png)

So we've seen some examples of a bootstrap in simple problems in the next section we'll talk about the method of more generality。

