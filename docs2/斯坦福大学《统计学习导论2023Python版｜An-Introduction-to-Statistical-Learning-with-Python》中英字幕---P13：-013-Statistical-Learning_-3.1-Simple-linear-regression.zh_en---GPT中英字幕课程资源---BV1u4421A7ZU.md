# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P13：-013-Statistical Learning_ 3.1 Simple linear regression.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_0.png)

Hello everyone。We're going to continue now our discussion of supervised learning。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_2.png)

Linear regression is the topic。 And actually， as we'll see， it's a very simple method。

 but that's not a bad thing。 Simple is actually good。

's as we' see it's very useful and also the concepts that we learn in linear regression are useful for the a lot of the different topics in the course。

 So this is chapterpt 3 of our book。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_4.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_5.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_6.png)

Let's look at the first slide。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_8.png)

As we say， linear regression is a simple approach to supervised learning that assumes the dependence of the outcome Y on the predictors x1 through xB is linear。

Now，' let's look at that assumption。 So in this little cartoon example。

 the true regression function is red。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_10.png)

And it's not linear， but it's pretty close to linear and the approximation in blue there。

 the blue line is it looks like a pretty good approximation。

 especially if the noise around the true red curve， as we'll see is substantial。

 that the regression curve in blue can be quite a good approximation。So。

Although this model is very simple， I think there's been sort of a。

A tendency of people to think simple is bad， we want to use things that are complicated and fancy and impressive well actually I want to say the opposite simple is actually very good and this model being very simple。

 it actually works extremely well in lot of situations。And in addition。

 the concepts we learn in regression are important for a lot of the other supervised learning techniques in the course。

 so this is it's important to start slowly to learn the concepts of this simple method。

 both for the methods self and for the future methods in the course。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_12.png)

So what is？

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_14.png)

The regression model。 Well， before I define the model， let's actually look at the advertising data。

 which we。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_16.png)

I've got on the next slide this data is。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_18.png)

His looks at sales as a function of three kinds of advertising。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_20.png)

TV， radio and newspaper。And here I've got scatter plots of the sales versus each of the three predictors individually。

 and you can see the approximations。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_22.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_23.png)

By the regression line are pretty good， looks like for the most part。

 there are reasonable approximations on the left side， maybe for low TV advertising。

 the sales are actually lower than expected。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_25.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_26.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_27.png)

Which we can see here。Right。But for the most part， the linear approximation is reasonable。

 partly because， again， the amount of noise around the curve around the line is quite large。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_29.png)

So even if the actual regression function was all linear。

 we wouldn't be able to see it from this data。 So this example of how it's。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_31.png)

This crude approximation， which is potentially quite useful。

So what are the questions when we might ask this kind of data and which you might ask the regression model to help us to answer？

Well， one question is is there a relationship between the budget of advertising and sales。

 that's sort of the overall global question is do these predictors have anything to say about the outcome？

Furthermore， how strong is that relationship， the relationship might be there。

 but might be so weak as not to be useful。Now， assuming there is a relationship。

 which media contribute to the sales？Is it TV？Radio or newspaper， or maybe all of them。

If we want to use this model to predict， how well can we predict future sales？

Is the relationship linear， And we just discussed that already。 If it's not linear。

 maybe if we use a nonlinear model， we'll be able to make better predictions。

 Is there synergy among the advertising media， in other words。

Do they media work on their own in a certain way or do they work in combination。

 and we'll talk about ways of looking at synergy later in this section。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_33.png)

Okay， well， what is linear regression， well let's start with the simplest case where have a simple model with just a single predictor。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_35.png)

And this is the model here， it says that the outcome is just a linear function of the single predictor x with noise。

 with errors， that have the epsilon， so this is is just the equation of a line where we've added some noise at the end to allow the points to deviate from the line。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_37.png)

The parameters， the constants beta 0 and beta 1 are called parameters or coefficients。

 they're unknown。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_39.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_40.png)

And we're going to find the best values to make the line fit as well as possible。

 So you see a lot of terminology。 those parameters are called the intercept and slope respectively。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_42.png)

Because they're the interceptent slope of the line。 And again。

 we're going to find the best fitting values。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_44.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_45.png)

To find the line that best fits the data。Now， and we'll talk about that on the actually the next slide。

 But suppose we have for the moment some good values for the slope and intercept。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_47.png)

Then we can predict the future values simply by。Plugging them into the equation right So if we have we have a value of x。

 we want for which you want to predict， the x might be， for example。

 the amount of the advertising budget for TV。And we have our。Our coefficients that we've estimated。

 We simply plugged them into the equation and our prediction for。

 for future sales at that value of x is given by this equation。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_49.png)

And you'll see throughout the course， as in standard as statistics， we put a hat。

 this little symbol over top of a。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_51.png)

A parameter to indicate。The estimated value， which we've estimated from data。

 so that's a looks sort of funny but that's become a standard。It's convention。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_53.png)

So how do we find the best values of the parameters？Well， let's suppose that we have our。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_55.png)

The prediction for a given value of the parameters at each。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_57.png)

Each value in the data set。Then the residual， what's called the residual， is the。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_59.png)

Discrpancy between the actual outcome and the predicted outcome。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_61.png)

So we define the。The residual summa squares as a total square discrepancy。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_63.png)

Between。The actual outcome in the fit。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_65.png)

Or equivalent， if we write that out in detail， it looks like this， right， this is the error。

 the residual for the first observation， square， second， et cetera。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_67.png)

So it makes sense to say。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_69.png)

Well， I want to choose the values of these parameters。

 the intercept and slope to make that as small as possible。

 So that was I want the line to fit the points as closely as possible。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_71.png)

See this next slide， I'll come back to the equation in the previous slide。

 but this next slide shows it in pictures。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_73.png)

So here are the points。Each of these residuals as health is the is the。

The distance of each point from the line， and I square up these distances。

 I don't care if I'm below or above， I'm not going to give any preference。

 but I want the total square distance of all points to the line to be as small as possible。

Because I want the line to be as close as possible to the points。

This is called the least squares Line。Yet， there's a unique line that fits the best in this sense。

And equations。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_75.png)

For the slope interceptor given here， here's the slope。And the intercept。

 so just basically a formula involving the observations。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_77.png)

For the slope intercept。And these give a the least squares estimates。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_79.png)

These are the ones that minimize the sum squares。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_81.png)

Okay， so and of course a computer program like R or pretty much any other statistical program will compute that for you。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_83.png)

You don't need to do it by hand。So okay， so we have our data for single a single predictor。

 we've obtained the least squares estimates， well we want to know one question we want to know is how precise are those estimates？



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_85.png)

In particular we want know what we want to know， for example， is a slope  zero， if the slope is zero。

 that means there's no relationship between y and x。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_87.png)

Suppose we obtained a slope of 0。5。 Is that bigger than0 or're not， Well。

 we need a measure of precision。 How close is that actually to  zero。

 We're nots maybe maybe if weve got a new data set from the same population。

We get a slope of minus 0。1， then the 0。5 is not as impressive as it sounds。

So we need what's called a standard error for the slope。And interceptWell。

 here are the forms for the standard errors of the slope and intercept。

Here's the one we really care about， this is the square standard error of the slope。

It's sigma squared。 where sigma squared is the noise， the variance of the the of the。

Of the errors around the。The the line。 and this is interesting。

 It says this is the spread of the x's around their mean。This actually makes sense。

 It says the standard error of the slope is bigger。 if my noise variance is bigger， that makes sense。

 the more noise around the line， the less precise the slope， this says the more spread out the x's。

The more precise the slope is。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_89.png)

And that actually makes sense， so I go back to this。Slide， right？

The more spread out these points are， the more I have the slope pinned down， right。

 imagine think of like a teeter totter right， imagine I have had the points that were all actually concentrated around 150。

Then this slope could vary a lot， I could move this thing up and down this line up and down。

 or sorry， I could turn it， change the slope and still fit the points about the same。

 but the more the points are spread out in X across the horizontal axis。

 the better pin down I have the slope。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_91.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_92.png)

The less slop it has to turn。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_94.png)

So this also says you have a choice of which observations to measure。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_96.png)

And sort in maybe an experiment where you can design， you should pick your predictor values。

 the x' is as spread out as possible in order to get the slopes estimated as precisely as possible。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_98.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_99.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_100.png)

Okay， so that's the formula for the standard of the。Of the slope。 and for the intercept。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_102.png)

And what do we do these， well， one thing we can do is form what's called confidence intervals。So。

A conference interval is defined as a range。As a range so that it has a property that with high confidence。

95% say which is a number that we'll pick。That that range contains the true value with that confidence。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_104.png)

In other words， well， to me specific， if you want a conference interval of 95%， we take。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_106.png)

The estimate of our slope plus or minus twice the estimated standard error。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_108.png)

And this。If errors are normally distributed， which we typically assume， approximately。

 this will contain the true value， the true slope。With probability 0。95。Okay。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_110.png)

Okay， so what we get from that as a confidence interval， which is a lower point。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_112.png)

In an upper point。Which contains a true value with the probability 0。95 under repeated sampling。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_114.png)

Now， what does that mean， next can to be a little tricky to interpret that。

 Let's see a little more detail what that actually means。Let's think of a true value of beta， beta 1。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_116.png)

Which might be  zero， in particular， which means there's the slope of zero。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_118.png)

And now let's draw a line at beta 1。Now imagine that we withdraw a data set like the one we drew and we get a confidence interval from this formula。

And that conference interval looks like this。So this one contains a true value because they've got the line is in between Ne bracket。

Now I get a second data set in the same population。

 and I form its confidence interval from that data set。It looks a little different。

 but it also contains its tree value。Now I get a third data set。

And I did the least squares computation， I formed the confidence interval。Unlily。

 it doesn't contain the true value。 It's seeing over here it's above beta1。

 beta1s below the whole interval。And I again another data set。

 maybe I miss on the other side this time。And I get another data， and I contain the true value。

So we can imagine doing this experiment many， many times each time getting a new data set from the population。

 doing the least squares computation and forming the coffins interval。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_120.png)

And what the， the theory tells us is that if I form say 100 confidence intervals。

10 of these brackets。I will。95% of the time， they will contain the true value。

 the other 5% of the time they'll not contain the true value。

So I can be pretty sure that the interval contains a true value if I form the Comp in this way。

 I can be sure at probability 0。95。

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_122.png)

So for the advertising data， the confidence interval。For beta 1 is。042 to 。053。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_124.png)

This is for， think it's for TV sales。So this tells me that。The true slope for TV advertising。

Is first of all， it's greater than zero。 In other words。

 having TV advertising does have a positive effect on sales， as one would expect。



![](img/36c78e6a75be5f3c2e6d4931e46d46fe_126.png)

![](img/36c78e6a75be5f3c2e6d4931e46d46fe_127.png)

Okay， so that completes our discussion of standard errors and confidence intervals in the next segment we'll talk about hypothesis testing which is a closely related idea to confidence intervals。

