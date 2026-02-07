# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P48：-048-Statistical Learning_ 7.1 Polynomials and Step Functions.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

![](img/9e75696aca1d77310cc29d7066518f37_0.png)

Well， good to see you again。 sorry， you got two old guys again。



![](img/9e75696aca1d77310cc29d7066518f37_2.png)

In this section we're going to talk about fitting nonlinear functions and nonlinear models up to now we focused on linear models。



![](img/9e75696aca1d77310cc29d7066518f37_4.png)

And what you'll see is that it's actually very easy to bring in non nonlinearity into your model in a somewhat seamless way。

 and you'll see the tools are almost as easy as they were when we were fitting linear models。



![](img/9e75696aca1d77310cc29d7066518f37_6.png)

![](img/9e75696aca1d77310cc29d7066518f37_7.png)

And we'll talk about a hierarchy of methods some。

![](img/9e75696aca1d77310cc29d7066518f37_9.png)

Completely straightforward and some slightly more sophisticated。

And some of the actually what you see today is for Trevor and I somewhat historical。

 the very first paper we ever wrote together was called Generalized Additive models。

 actually here as graduate students here at Stanford and the last part of the section。

 we'll talk about generalized additive models which are a way of using the tools for non nonlinearity for more than one predictor。



![](img/9e75696aca1d77310cc29d7066518f37_11.png)

![](img/9e75696aca1d77310cc29d7066518f37_12.png)

You know， Rob， it just occurred to me that that paper we wrote 30 years ago。It still good，'。



![](img/9e75696aca1d77310cc29d7066518f37_14.png)

There we go。

![](img/9e75696aca1d77310cc29d7066518f37_16.png)

Well。The first fact is， the truth is never linear。It's a shocking thing for a statistics professor to say。

Maybe I should qualify， well almost never。Well， that is the truth。 Linearity is an approximation。

And often linearity assumption is good enough and that's why we like the linear model。

 the approximation is good enough and gives us a nice simple summary。

 but we need to go beyond linearity often， and we have lots of tools to do that。And in this section。

 we're going to talk about some of those。 So there's the list polynomial step function splines。

Local regression and generalized additive models kind of increasing in in complexity as we go down the list。

And as you'll see， they're just as easy to work with as， as linear models。



![](img/9e75696aca1d77310cc29d7066518f37_18.png)

So polynomial regression we've really covered before。

 and we when we introduce these nonlinear methods， we're going to introduce them for the most part。

 except when we get to generalize additive models with a single variable。

 but you know you'll see it's just as easy to do it in many variables as well。

And so here's a polynomial regression model。We've got not only a linear term。

 but we've got polynomial terms as well。 So there's x squared， x cubed and so on。

 And we can go up to whatever degree we like。And for the linear model， it's linear， the coefficient。

 It's linear in the coefficients， but it's a nonlinear function of x。And in the left panel。

 we see on the wage data a polynomial function fitted to age。 that's a third degree， I believe。

 polynomial。And you see the， the fitted function。 and you see pointwise standard error bands。

 That's these dotted bands here。 That's one plus and minus-1 standard error。

And it's a nonlinear function。 It seems to capture what's going on in the data。

 I noticed the standard air bands are wider at the end。0 Trevor。 I it， why is that。

That's a good point， Rob。 And that's that's a result of the it's called leverage。

 The points right at the end。 You notice the data thins out at the end。

 So there's not so much data there。 And， and so the information for fitting the curve at the end is much less。

 So the standard error gets wider。But also points at the end。We call it waggging the tail of the dog。

 right Polynomial is a very flexible function， and it can especially flexible at the end。

 and those tails tend to wag around， and the standard area indicates it。In fact。

In this figure on the right， yeah， we using a polynomial to fit a logistic regression。

And to do that in this section， we just。Turn wage into a binary variable by looking at whether wage is bigger than 250 k or not。

And so that's a logistic regression Act trying to model the probability of that event。

And notice how wide the standard errors is are at the end right now。 when I first saw that。

 I thought it was crazy， but then I realized the vertical scale is pretty stretched， right。

 So it's only ranging up to 0。2。 Oh， good point This point。 If you saw that from 0 to 1。

 it would look a lot。More narrow。 That's， that's a very good point。

 And that's something to always bear in mind。 You know， the ploting scales， you know。

 it's important what how you decide and what scales do you use。 And in this case， as Rob said。

 it's only going up to 0。2。What you also notice here is we've got this so-called rag plot。

 We see at the bottom of the plot where all the zeros occur。 That's these little spikes here。

 It's kind of uniformly across the range。 And at above， we've got where all the ones occur。

 And you'll notice there's only there's one sort of in the middle of the range and not many ones at the end。

 So there's really not any data at all to estimate this function right at the end。



![](img/9e75696aca1d77310cc29d7066518f37_20.png)

So in detail， with polynomial regression， what you do is you create new variables。 and in this case。

 theyre just transformations of the original variables。

 So x we make x1 is the original x x2 is x squared and so on。

 and then just treat the problem as a multiple linear regression model with these new derived variables。

And in this case， we're not really interested in the coefficients。

 We're more interested in the fitted functions at any particular value x 0， right。

 We interest in the composed function。😊，So once we fit the model， we might say， well。

 what does the function look like at a new value x0 And， you know。

 And so the coefficients self aren't that interesting。

And since the fitted function is actually a linear function of the coefficients， the beta L's L hats。

Okay， we can get a simple expression for the pointwise variances。

 So you say what is the variance of the fitted function at x0？Well。

That fitted function at x 0 is just a linear function， a linear combination of the parameters。And。

 and so by using the the covariance matrix of the fitted parameters， you can then get an expression。

 a simple expression for the variance of this fitted value。

 We describe this in more detail in the book in somewhat more detail， and。It seems like we。

 in the plot， we actually plot the fitted function plus or -2 standard areas。 I said one earlier。

And so getting these point why standard errors is fairly straightforward。

Pointwise means that the standard error the standard error band is pointwise。

 so the band is showing at any given point what the standard error is。

 this is not to be confused with global confidence bands， which is another story。The other thing is。

 how what degree do we use， So here， we were actually using a fourth degree polynomial。 I said third。

 but we use fourth。So that D is obviously a parameter。

 and often we just pick D to be some small number like two or three，4 in this case。

 or otherwise we can actually select D by cross validation， think of it as a tuning parameter。嗯。

For logistic regression， it's， its the details are pretty much the same in the as I said in the figure。

 we， this is what we were modeling。And so there's our inverse logistic function。

 and it's just a polynomial instead of a linear function。And。

One small detail at's somewhat important is to get confidence intervals。What you do is if。

 if you try and get confidence intervals for the probabilities using sort of direct methods you might get outside the range0 and1。

 So what you do is you get confidence intervals for the fitted logit and then you put them the upper and lower confidence band endpoints through the inverse logit transformation and those give you the。

The confidence intervals or the。In this case， for the， for the fitted probabilities。

 So that's a useful trick to bear in mind。

![](img/9e75696aca1d77310cc29d7066518f37_22.png)

Okay， few other points。With polynom so we've just talked about with a single variable for several variables。

 you can do it separately on each variable right so you just generate these transformations on each variable and then just stack them together in one big matrix and and fit a big linear model in all these new derived variables。

 So if you if you've got a variable x you make x1 x2 up to say x4 if you have another variable Z you can make z1 up to z4 and you just stack them all together and make a big model matrix and fit your linear model and then you have to unpack the pieces to compose the functions and we'll see later on that the gam technology generalized additive model technology helps you do this in a seamless way。

There some caveats with polynomial regression。Polynomials， as I mentioned before。

 have notorious tail behaviour， very bad for extrapolation。 Those tails tend to wiggle around。

 and you really wouldn't want to trust predictions beyond the range of the data or even too near the end ends of the data。

And finally， fitting a polynomial in R is very simple yes。

A simple expression for fitting a polynomial in x to Y。

 this is the model formula that you'd use as a poly function that generates these transformations for you。

 and it's as simple as that。And we'll see in the， in the lab we， we'll get some experience with that。

Step functions。 that's another way of fitting non nonlinearities。

 especially popular in epidemiology and biostatistics in the last 20 or so years。And。

 and that what you do is you cut your variable， your continuous variable into， into， into。

 into discrete subranges。 For example， here， we've， we've cut age at 35。And again， at at 65。

 there's actually a cut at 50 as well， conciia。And then the idea is you fit a constant model in each of the regions。

So it's， it's a piecewise， constant model。So you can see here so the function of when you fit it and plot them all together。

 you see the constant in the first range， the second range。

 the third range is hardly visible that it's different and thenre in the fourth range。

 and so this becomes when put together as a nonlinear function， it's a piecewise constant function。

And this， this is often useful if there's some natural cut points that are of interest， you know。

 so what is the average income for somebody below the age of 35， you know。

 so you can read it straight off the plot。This is often good for summaries in newspapers and reports and things like that。

 which has led to its popularity。And， you know， to do it is just as easy as as as it was for polynomials。

If， if you think of this function over here， it's。It's's a binary variable。

 you make a binary variable is x less than 35。If yes， you make it one， if not， you make it a0。

 And for each of these， it's the same。 And so you create a bunch of dummy variables。0，1 variables。

 And you just fit those with a linear model。 You can always see the advantage this has over over polynomials。

 right， This is local。 Remember with polynomials。It's a single function for the whole range of the x variable。

 so for example， if I change a point on the left side。

 it could potentially change the fit on the right side quite a bit for polynomials。

 that's a good point which I forgot to say but for step functions。

 a fit a point only affects the fit in the partition it's sitting in and not the other partitions。

That's a great point and thanks for reminding us。Well polynomial。

 the parameters affect the function everywhere and， and， and can have dramatic effects。Yeah。

 we've done the same thing as we did before for the logistic regression。

 but with a piecewise constant function， everything else is the same。 but the。

 the fitted function is kind of blocky and。You， may be considered not as attractive。



![](img/9e75696aca1d77310cc29d7066518f37_24.png)

Step functions are easy to work with， as I said， you make a bunch of dummy variables and just fit the linear model。

It's also a useful way of creating interactions that are easy to interpret。 So， for example。

 think of the an interaction effect of year and age in a linear model。So what you can do is。

 for example， make a dummy variable of year。 so let's say cut year less than or equal to less than 2005。

And and have another one year bigger than equal to 2005。 And then if you multiply that with age。

 what you've done is create an interaction and that'll fit a linear different linear model。

As a function of age for the for people who worked before 2005 and those after 2005。And。

 and so that visually， that's nice。 You'll see two different linear functions。

 It's the easy way of seeing the effect of an interaction。And in R。

 creating these dummy variables is really easy。Creating an indicator function is。

 is that pretty much the same expression we've shown at colonel。 Theres a there is a function I in R。

 which is basically an indicator。And year less than 25 turns into a logical。

 But when wrapped in the indicator， it's essentially a 0，1 variable。

And if you want to cut in more than one place there's a function called cut。

 so you can cut age and you give it the cut points。

 you need to give cut the two boundary points as well。 and so in this case， 18 and 90。

 those are the ranges of the ages will be on the range actually。

 and then the interior cut points and it'll create a factor for you。

 an audit factor that cuts the variable into those bins。Now， the choice of the cut points or knots。

 as we're going to call them， can be little problematic。For creating linearities。

 smooth alternatives are available。 and we're going to talk about them next。

 You might just pick an unfortunate choice of cut points。

 and it doesn't show the non linearity at all。 And so there， there's somewhat of an art。

 So usually these。

![](img/9e75696aca1d77310cc29d7066518f37_26.png)

Peacewise constant functions are especially good if they are natural cut points that you want to use。

