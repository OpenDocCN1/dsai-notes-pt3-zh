# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P8：P8 StatsLearning Lect5a 112113.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/f941382afc7835985d9470bfd706ad0d_0.png)

Hello everyone。We're going to continue now our discussion of supervised learning。



![](img/f941382afc7835985d9470bfd706ad0d_2.png)

Linear regression is the topic。 And actually， as we'll see， it's a very simple method。

 but that's not a bad thing。 Simple is actually good。

 It's as we'll see it it's very useful and also the concepts that we learn in linear regression are useful for the a lot of the different topics in the course。

 So this is chapterpt 3 of our book。

![](img/f941382afc7835985d9470bfd706ad0d_4.png)

![](img/f941382afc7835985d9470bfd706ad0d_5.png)

![](img/f941382afc7835985d9470bfd706ad0d_6.png)

Let's look at the first slide。

![](img/f941382afc7835985d9470bfd706ad0d_8.png)

As we say， linear regression is a simple approach to supervised learning that assumes the dependence of the outcome Y on the predictors x1 through xB is linear。



![](img/f941382afc7835985d9470bfd706ad0d_10.png)

Now， let's look at that assumption。 So in this little cartoon example。

 the true regression function is red。

![](img/f941382afc7835985d9470bfd706ad0d_12.png)

![](img/f941382afc7835985d9470bfd706ad0d_13.png)

And it's not linear， but it's pretty close to linear and the approximation in blue there。

 the blue line is it looks like a pretty good approximation。

 especially if the noise around the true red curve。

 as we'll see is substantial that the regression curve in blue can be quite a good approximation。



![](img/f941382afc7835985d9470bfd706ad0d_15.png)

![](img/f941382afc7835985d9470bfd706ad0d_16.png)

![](img/f941382afc7835985d9470bfd706ad0d_17.png)

So。

![](img/f941382afc7835985d9470bfd706ad0d_19.png)

Although this model is very simple， I think there's been sort of a。

A tendency of people to think simple is bad。 We want to use things that are complicated and fancy and impressive。

 Well， actually I want to say the opposite simple is actually very good。

 and this model being very simple。 it actually works extremely well in lot of situations。



![](img/f941382afc7835985d9470bfd706ad0d_21.png)

![](img/f941382afc7835985d9470bfd706ad0d_22.png)

![](img/f941382afc7835985d9470bfd706ad0d_23.png)

And in addition， the concepts we learn in regression are important for a lot of the other supervised learning techniques in the course。

 so this it's important to start slowly to learn the concepts of this simple method。

 both for the method itself and for the future methods in the course。



![](img/f941382afc7835985d9470bfd706ad0d_25.png)

![](img/f941382afc7835985d9470bfd706ad0d_26.png)

![](img/f941382afc7835985d9470bfd706ad0d_27.png)

So what is？

![](img/f941382afc7835985d9470bfd706ad0d_29.png)

The regression model。 Well， before I define the model， let's actually look at the advertising data。

 which we。

![](img/f941382afc7835985d9470bfd706ad0d_31.png)

I'll go on the next slide this data is。

![](img/f941382afc7835985d9470bfd706ad0d_33.png)

His looks at sales as a function of three kinds of advertising。



![](img/f941382afc7835985d9470bfd706ad0d_35.png)

TV， radio and newspaper。And here I've got scatter plots of of the sales versus each of the three predictors individually。

 And you can see the approximations。

![](img/f941382afc7835985d9470bfd706ad0d_37.png)

![](img/f941382afc7835985d9470bfd706ad0d_38.png)

By the regression line are pretty good， looks like for the most part。

 the are reasonable approximations on the left side， maybe for low TV advertising。

 the sales are actually lower than expected。

![](img/f941382afc7835985d9470bfd706ad0d_40.png)

![](img/f941382afc7835985d9470bfd706ad0d_41.png)

![](img/f941382afc7835985d9470bfd706ad0d_42.png)

Which we can see here。Right。

![](img/f941382afc7835985d9470bfd706ad0d_44.png)

But for the most part， the linear approximation is reasonable， partly because again。

 the amount of noise around the curve around the line is quite large。



![](img/f941382afc7835985d9470bfd706ad0d_46.png)

So even if the actual regression function was not linear。

 we wouldn't be able to see it from this data。 So this example of how it's。



![](img/f941382afc7835985d9470bfd706ad0d_48.png)

![](img/f941382afc7835985d9470bfd706ad0d_49.png)

This crude approximation， which is potentially quite useful。

So what are the questions when we might ask this kind of data and you might ask the regression model to help us to answer。

 well one question is is there a relationship between the budget of advertising and sales。

 that's sort of the overall global question is do these predictors have anything to say about the outcome。



![](img/f941382afc7835985d9470bfd706ad0d_51.png)

![](img/f941382afc7835985d9470bfd706ad0d_52.png)

![](img/f941382afc7835985d9470bfd706ad0d_53.png)

![](img/f941382afc7835985d9470bfd706ad0d_54.png)

Furthermore， how strong is that relationship， The relationship might be there。

 but might be so weak as not to be useful。

![](img/f941382afc7835985d9470bfd706ad0d_56.png)

Now， assuming there is a relationship， which media contribute to the sales？



![](img/f941382afc7835985d9470bfd706ad0d_58.png)

Is it TV？Radio or newspaper， or maybe all of them。

![](img/f941382afc7835985d9470bfd706ad0d_60.png)

If we want to use this model to predict， how well can we predict future sales？



![](img/f941382afc7835985d9470bfd706ad0d_62.png)

Is the relationship linear， And we just discussed that already。 If it's not linear。

 maybe if we use a nonlinear model， we'll be able to make better predictions。

 Is there synergy among the advertise media， in other words。



![](img/f941382afc7835985d9470bfd706ad0d_64.png)

![](img/f941382afc7835985d9470bfd706ad0d_65.png)

![](img/f941382afc7835985d9470bfd706ad0d_66.png)

Do they media work on their own in a certain way or do they work in combination and we'll talk about ways of looking at synergy later in this section。



![](img/f941382afc7835985d9470bfd706ad0d_68.png)

Okay， well， what is linear regression， Well let's start with the simplest case we have a simple model with just a single predicty。



![](img/f941382afc7835985d9470bfd706ad0d_70.png)

![](img/f941382afc7835985d9470bfd706ad0d_71.png)

And this is the model here， it says that the outcome is just a linear function of the single predictor x with noise with errors。

 that have the epsilon， so this just is just the equation of a line where we've added some noise at the end to allow the points to deviate from the line。



![](img/f941382afc7835985d9470bfd706ad0d_73.png)

![](img/f941382afc7835985d9470bfd706ad0d_74.png)

![](img/f941382afc7835985d9470bfd706ad0d_75.png)

The parameters， the constants beta 0 and beta 1 are called parameters or coefficients。

 they're unknown。

![](img/f941382afc7835985d9470bfd706ad0d_77.png)

![](img/f941382afc7835985d9470bfd706ad0d_78.png)

And we're going to find the best values to make the line fit as well as possible。

 So you see a law of terminology。 those parameters are called the intercept and slope， respectively。



![](img/f941382afc7835985d9470bfd706ad0d_80.png)

![](img/f941382afc7835985d9470bfd706ad0d_81.png)

Because they're this interceptent slope of the line。 And again。

 we're going to find the best fitting values。

![](img/f941382afc7835985d9470bfd706ad0d_83.png)

![](img/f941382afc7835985d9470bfd706ad0d_84.png)

To find the line that best fits the data。Now， and we'll talk about that on the next actually the next slide。

 But suppose we have for the moment some good values for the slope and intercept。



![](img/f941382afc7835985d9470bfd706ad0d_86.png)

![](img/f941382afc7835985d9470bfd706ad0d_87.png)

Then we can predict the future values simply by。

![](img/f941382afc7835985d9470bfd706ad0d_89.png)

Plugging them into the equation So if we have we have a value of x we want for which you want to predict。

 the x might be， for example， the amount of the advertising budget for TV。



![](img/f941382afc7835985d9470bfd706ad0d_91.png)

![](img/f941382afc7835985d9470bfd706ad0d_92.png)

And we have our。Our coefficients that we've estimated。

 We simply plugged them into the equation and our prediction for for future sales at that value of x is given by this equation。



![](img/f941382afc7835985d9470bfd706ad0d_94.png)

![](img/f941382afc7835985d9470bfd706ad0d_95.png)

And you'll see throughout the course， as in standard as statistics， we put a hat。

 this little symbol over top of a。

![](img/f941382afc7835985d9470bfd706ad0d_97.png)

A parameter to indicate。

![](img/f941382afc7835985d9470bfd706ad0d_99.png)

The estimated value， which we've estimated from data。 Okay。

 so that's looks sort of funny but that's become a standard。



![](img/f941382afc7835985d9470bfd706ad0d_101.png)

It'Con。

![](img/f941382afc7835985d9470bfd706ad0d_103.png)

So how do we find the best values of the parameters？Well， let's suppose that we have our。



![](img/f941382afc7835985d9470bfd706ad0d_105.png)

The prediction for a given value of the parameters at each each value in the data set。



![](img/f941382afc7835985d9470bfd706ad0d_107.png)

Then the residual， what's called the residual， is the。



![](img/f941382afc7835985d9470bfd706ad0d_109.png)

Discrpancy between the actual outcome and the predicted outcome。



![](img/f941382afc7835985d9470bfd706ad0d_111.png)

So we define the。The residual sum squares as a total square discrepancy。



![](img/f941382afc7835985d9470bfd706ad0d_113.png)

Between。The actual outcome in the fit。

![](img/f941382afc7835985d9470bfd706ad0d_115.png)

Or equivalent， if we write that out in detail， it looks like this， right， is， this is the error。

 the residual for the first observation， square， second， et cea。



![](img/f941382afc7835985d9470bfd706ad0d_117.png)

So it makes sense to say。

![](img/f941382afc7835985d9470bfd706ad0d_119.png)

Well， I want to choose the values of these parameters。

 the intercept and slope to make that as small as possible。

 Now words I want the line to fit the points as closely as possible。



![](img/f941382afc7835985d9470bfd706ad0d_121.png)

![](img/f941382afc7835985d9470bfd706ad0d_122.png)

See， this next slide， I'll come back to the equation in the previous slide。

 but this next slide shows it in pictures。

![](img/f941382afc7835985d9470bfd706ad0d_124.png)

So here are the points。Each of these residuals is health is the， is the。



![](img/f941382afc7835985d9470bfd706ad0d_126.png)

The distance of each point from the line， and I square up these。



![](img/f941382afc7835985d9470bfd706ad0d_128.png)

Distances， I don't care if I'm below or above。 I'm not going to give any preference。

 but I want the total square distance of all points to the line to be as small as possible。



![](img/f941382afc7835985d9470bfd706ad0d_130.png)

![](img/f941382afc7835985d9470bfd706ad0d_131.png)

Because I want the line to be as close as possible to the points。

This is called the least squares line。

![](img/f941382afc7835985d9470bfd706ad0d_133.png)

It's a unique line that fits the best in this sense。And equations。



![](img/f941382afc7835985d9470bfd706ad0d_135.png)

For the slope interceptor given here， here's a slope。



![](img/f941382afc7835985d9470bfd706ad0d_137.png)

And the intercept。 So just basically a formula involving the observations。For the slope intercept。



![](img/f941382afc7835985d9470bfd706ad0d_139.png)

And these give a called the least squares estimates。These are the ones that minimize the sum squares。



![](img/f941382afc7835985d9470bfd706ad0d_141.png)

![](img/f941382afc7835985d9470bfd706ad0d_142.png)

Okay， so and of course the computer program like R or pretty much any other statistical program will compute that for you。



![](img/f941382afc7835985d9470bfd706ad0d_144.png)

You don't need to do it by hand。

![](img/f941382afc7835985d9470bfd706ad0d_146.png)

So okay， so we have our data for a single predictor， we've obtained the least squares estimates。

 well we want to know one question we want to know is how precise are those estimates？



![](img/f941382afc7835985d9470bfd706ad0d_148.png)

![](img/f941382afc7835985d9470bfd706ad0d_149.png)

In particular we want to know what we want to know， for example， is a slope zero。

 if the slope is zero， that means there's no relationship between y and x。



![](img/f941382afc7835985d9470bfd706ad0d_151.png)

Suppose we obtained a slope of 0。5。 is that bigger than0 or not？



![](img/f941382afc7835985d9470bfd706ad0d_153.png)

Well， we need a measure of of precision。 How close is that actually to 0。

 We're nots maybe maybe if we got a new data set from the same population。



![](img/f941382afc7835985d9470bfd706ad0d_155.png)

![](img/f941382afc7835985d9470bfd706ad0d_156.png)

We get a slope of minus 0。1， then the 0。5 is not as impressive as it sounds。



![](img/f941382afc7835985d9470bfd706ad0d_158.png)

So we need what's called a standard error for the slope。



![](img/f941382afc7835985d9470bfd706ad0d_160.png)

And intercept。 Well， here are the formants for the standard errors of the slope and intercept。



![](img/f941382afc7835985d9470bfd706ad0d_162.png)

Here's the one we really care about， this is the square standard error of the slope。

It's sigma squared。 where sigma squared is the noise， the the variance of the of the of the。



![](img/f941382afc7835985d9470bfd706ad0d_164.png)

Of the errors around the。The line， and this is interesting。

 it says this is the spread of the x's around their mean。



![](img/f941382afc7835985d9470bfd706ad0d_166.png)

![](img/f941382afc7835985d9470bfd706ad0d_167.png)

This actually makes sense。 It says the standard error of the slope is bigger。

 if my noise variance is bigger， that makes sense。 The more noise around the line。

 the less precise the slope。

![](img/f941382afc7835985d9470bfd706ad0d_169.png)

![](img/f941382afc7835985d9470bfd706ad0d_170.png)

This says the more spread out the x's。The more precise the slope is。



![](img/f941382afc7835985d9470bfd706ad0d_172.png)

And that actually makes sense， so I go back to this。Slide， right？

The more spread out these points are， the more I have the slope pinned down， right， Imagine。

 think of it like a teeer totter， right， Imagine I have had the points They were all actually concentrated around 150。



![](img/f941382afc7835985d9470bfd706ad0d_174.png)

![](img/f941382afc7835985d9470bfd706ad0d_175.png)

![](img/f941382afc7835985d9470bfd706ad0d_176.png)

Then this slope could vary a lot， right I could move this thing up and down this line up and down。

 or sorry， I could turn it， change the slope and still fit the points about the same。

 but the more the points are spread out in X across the horizontal axis。

 the better pin down I have the slope。

![](img/f941382afc7835985d9470bfd706ad0d_178.png)

![](img/f941382afc7835985d9470bfd706ad0d_179.png)

![](img/f941382afc7835985d9470bfd706ad0d_180.png)

The less slop it has to turn。

![](img/f941382afc7835985d9470bfd706ad0d_182.png)

So this also says if you have a choice of which observations to measure。



![](img/f941382afc7835985d9470bfd706ad0d_184.png)

And sort in maybe an experiment where you can design， you should pick your predictor values。

 the x is as spread out as possible in order to get the slopes estimated as precisely as possible。



![](img/f941382afc7835985d9470bfd706ad0d_186.png)

![](img/f941382afc7835985d9470bfd706ad0d_187.png)

![](img/f941382afc7835985d9470bfd706ad0d_188.png)

Okay， so that's the formula for the senator of the。Of the slope and for the intercept。



![](img/f941382afc7835985d9470bfd706ad0d_190.png)

And what do we do these， well one thing we can do is form what's called confidence intervals。



![](img/f941382afc7835985d9470bfd706ad0d_192.png)

So。A conference interval is defined as a range。

![](img/f941382afc7835985d9470bfd706ad0d_194.png)

As a range so that it has a property that with high confidence。



![](img/f941382afc7835985d9470bfd706ad0d_196.png)

95% say which is a number that we'll pick。

![](img/f941382afc7835985d9470bfd706ad0d_198.png)

That that range contains the true value with that confidence。



![](img/f941382afc7835985d9470bfd706ad0d_200.png)

In other words， well， to me specific， if you want a conference interval of 95%， we take。



![](img/f941382afc7835985d9470bfd706ad0d_202.png)

The estimate of our slope plus or minus twice the estimated standard error。



![](img/f941382afc7835985d9470bfd706ad0d_204.png)

And this。If errors are normally distributed， which we typically assume， approximately。

 this will contain the true value， the true slope。

![](img/f941382afc7835985d9470bfd706ad0d_206.png)

![](img/f941382afc7835985d9470bfd706ad0d_207.png)

With probability 0。95。Okay。

![](img/f941382afc7835985d9470bfd706ad0d_209.png)

Okay， so what we get from that as a confidence interval， which is a lower point。



![](img/f941382afc7835985d9470bfd706ad0d_211.png)

In an upper point。Which contains a true value with the probability 0。95 under repeated sampling。



![](img/f941382afc7835985d9470bfd706ad0d_213.png)

Now， what does that mean， next can to be a little tricky to interpret that。

 Let's see in a little more detail what that actually means。



![](img/f941382afc7835985d9470bfd706ad0d_215.png)

Let's think of a true value of beta beta 1。

![](img/f941382afc7835985d9470bfd706ad0d_217.png)

Which might be zero in particular， which means there's the slope of zero。



![](img/f941382afc7835985d9470bfd706ad0d_219.png)

And now let's draw a line at beta 1。Now imagine that we withdraw draw a data set like the one we drew。

 and we get a conference interval from this formula。



![](img/f941382afc7835985d9470bfd706ad0d_221.png)

![](img/f941382afc7835985d9470bfd706ad0d_222.png)

And that confidence interval looks like this。So this one contains a true vibe because of've what the line is in between Ne bracket。



![](img/f941382afc7835985d9470bfd706ad0d_224.png)

Now I get a second data set in the same population。

 and I form its confidence interval from that data。



![](img/f941382afc7835985d9470bfd706ad0d_226.png)

It looks a little different， but it also contains its true value。



![](img/f941382afc7835985d9470bfd706ad0d_228.png)

Now I get a third data set。

![](img/f941382afc7835985d9470bfd706ad0d_230.png)

And I did the least squares computation， I formed the confidence interval。Unily。

 it doesn't contain the true value。 It's sitting over here。's it's above beta 1。

 beta 1s blow the whole interval。

![](img/f941382afc7835985d9470bfd706ad0d_232.png)

![](img/f941382afc7835985d9470bfd706ad0d_233.png)

And again， another data set may a miss on the other side at this time。And I get another data。

 and I contain the true value。

![](img/f941382afc7835985d9470bfd706ad0d_235.png)

So we can imagine doing this experiment many， many times each time getting a new data set from the population。

 doing the least squares computation and forming the coffins interval。



![](img/f941382afc7835985d9470bfd706ad0d_237.png)

And what the， the theory tells us is that。

![](img/f941382afc7835985d9470bfd706ad0d_239.png)

If I form， say 100 confidence intervals，100 of these brackets。



![](img/f941382afc7835985d9470bfd706ad0d_241.png)

I will。95% of the time they will contain the true value。

 the other 5% of the time will not contain the true value。



![](img/f941382afc7835985d9470bfd706ad0d_243.png)

![](img/f941382afc7835985d9470bfd706ad0d_244.png)

So I can be pretty sure that the interval contains a true value if I form the Comp in this way。

 I can be sure at probability 0。95。

![](img/f941382afc7835985d9470bfd706ad0d_246.png)

![](img/f941382afc7835985d9470bfd706ad0d_247.png)

So for the advertising data， the confidence interval。



![](img/f941382afc7835985d9470bfd706ad0d_249.png)

For beta 1 is。042 to 。053。

![](img/f941382afc7835985d9470bfd706ad0d_251.png)

This is for， think it's for TV sales。So this tells me that。



![](img/f941382afc7835985d9470bfd706ad0d_253.png)

The true slope for TV advertising。

![](img/f941382afc7835985d9470bfd706ad0d_255.png)

Is first of all， it's greater than zero。 In other words。

 having TV advertising does have a positive effect on sales， as one would expect。



![](img/f941382afc7835985d9470bfd706ad0d_257.png)

![](img/f941382afc7835985d9470bfd706ad0d_258.png)

Okay， so that completes our discussion of standard errors and confidence intervals in the next segment we'll talk about hypothesis process testing。

 which is a closely related idea to confidence intervals。



![](img/f941382afc7835985d9470bfd706ad0d_260.png)

![](img/f941382afc7835985d9470bfd706ad0d_261.png)