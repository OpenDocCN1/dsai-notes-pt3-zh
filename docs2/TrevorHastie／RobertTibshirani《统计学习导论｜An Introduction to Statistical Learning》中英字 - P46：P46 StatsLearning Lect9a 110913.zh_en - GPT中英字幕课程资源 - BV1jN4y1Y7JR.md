# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P46：P46 StatsLearning Lect9a 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/59900f333dcf4743a8289273bce145db_0.png)

Well， good to see you again。 sorry you got two old guys again。



![](img/59900f333dcf4743a8289273bce145db_2.png)

In this section we're going to talk about fitting nonlinearar functions and nonlinearar models up to now we focus on linear models and what you'll see is that it's actually very easy to bring in nonlineararity into your model in a somewhat seamless way and you'll see the tools are almost as easy as they were when we're fitting linear models。



![](img/59900f333dcf4743a8289273bce145db_4.png)

![](img/59900f333dcf4743a8289273bce145db_5.png)

![](img/59900f333dcf4743a8289273bce145db_6.png)

![](img/59900f333dcf4743a8289273bce145db_7.png)

And we'll talk about a hierarchy of methods some。

![](img/59900f333dcf4743a8289273bce145db_9.png)

Completely straightforward and some slightly more sophisticated。



![](img/59900f333dcf4743a8289273bce145db_11.png)

And some of the actually what you see today is for Trevor and I somewhat historical。

 the very first paper we ever wrote together was called Generalized Additive models。

 actually here as graduate students here at Stanford and the last part of the section。

 we' talk about generalized additive models which are a way of using the tools for nonlineararity for more than one predictor。



![](img/59900f333dcf4743a8289273bce145db_13.png)

![](img/59900f333dcf4743a8289273bce145db_14.png)

![](img/59900f333dcf4743a8289273bce145db_15.png)

![](img/59900f333dcf4743a8289273bce145db_16.png)

You know， Rob， it just occurred to me that that paper we wrote 30 years ago。ItStill good， still good。

 It's still a good paper。

![](img/59900f333dcf4743a8289273bce145db_18.png)

Okay， so there we go。

![](img/59900f333dcf4743a8289273bce145db_20.png)

Well。The first fact is， the truth is never linear。

![](img/59900f333dcf4743a8289273bce145db_22.png)

It's a shocking thing for a statistics professor to say。



![](img/59900f333dcf4743a8289273bce145db_24.png)

Maybe I should qualify or almost never。Well， that is the truth。 linearity is an approximation。



![](img/59900f333dcf4743a8289273bce145db_26.png)

And often linearity assumption is good enough and that's why we like the linear model。

 the approximation is good enough and it gives us a nice simple summary。

 but we need to go beyond linearity often and we have lots of tools to do that and in this section we're going to talk about some of those。

 So there's the list polynomial step function splines。



![](img/59900f333dcf4743a8289273bce145db_28.png)

![](img/59900f333dcf4743a8289273bce145db_29.png)

![](img/59900f333dcf4743a8289273bce145db_30.png)

![](img/59900f333dcf4743a8289273bce145db_31.png)

![](img/59900f333dcf4743a8289273bce145db_32.png)

Local regression and generalized additive models kind of increasing in in complexity as we go down the list。



![](img/59900f333dcf4743a8289273bce145db_34.png)

And as you'll see， they're just as easy to work with as linear models。



![](img/59900f333dcf4743a8289273bce145db_36.png)

![](img/59900f333dcf4743a8289273bce145db_37.png)

So polynomial regression we've really covered before， and when we introduce these nonlinear methods。

 we're going to introduce them for the most part， except when we get to generalize additive models with a single variable。

 but you'll see it's just as easy to do it in many variables as well。



![](img/59900f333dcf4743a8289273bce145db_39.png)

![](img/59900f333dcf4743a8289273bce145db_40.png)

And so here's a polynomial regression model。We've got not only a linear term。

 but we've got polynomial terms as well。 So there's x squared， x cubed and so on。

 and we can go up to whatever degree we like。

![](img/59900f333dcf4743a8289273bce145db_42.png)

![](img/59900f333dcf4743a8289273bce145db_43.png)

And for the linear model， it's linear the coefficient， It's linear in the coefficients。

 but it's a nonlinear function of x。

![](img/59900f333dcf4743a8289273bce145db_45.png)

And in the left panel we see on the wage data， a polynomial function fitted to age。

 that's a third degree， I believe， polynomial。

![](img/59900f333dcf4743a8289273bce145db_47.png)

![](img/59900f333dcf4743a8289273bce145db_48.png)

And you see the fitted function and you see pointwise standard error bands。

 that's these dotted bands here， that's one plus and minus one standard error。



![](img/59900f333dcf4743a8289273bce145db_50.png)

![](img/59900f333dcf4743a8289273bce145db_51.png)

And it's a nonlinear function It seems to capture what's going on in the data。

 I noticed the standard airs are wider at the end trevor it why is that that's a good point Rob and that's a result of the it's called leverage the points right at the end you notice the data thins out at the end。

 So there's not so much data there and so the information for fitting the curve at the end is much less。

 So the standard error gets wider。

![](img/59900f333dcf4743a8289273bce145db_53.png)

![](img/59900f333dcf4743a8289273bce145db_54.png)

![](img/59900f333dcf4743a8289273bce145db_55.png)

![](img/59900f333dcf4743a8289273bce145db_56.png)

![](img/59900f333dcf4743a8289273bce145db_57.png)

But also points at the end。

![](img/59900f333dcf4743a8289273bce145db_59.png)

We call it wgging the tail of the dog A polynomial is a very flexible function。

 and it can especially flexible at the end， and those tails tend to wag around and the standard error indicates it。



![](img/59900f333dcf4743a8289273bce145db_61.png)

![](img/59900f333dcf4743a8289273bce145db_62.png)

![](img/59900f333dcf4743a8289273bce145db_63.png)

In fact。In in this thing on the right， here we in using a polynomial to fit a logistic regression。



![](img/59900f333dcf4743a8289273bce145db_65.png)

And to do that in this section， we just。

![](img/59900f333dcf4743a8289273bce145db_67.png)

Turn wage into a binary variable by looking at whether wage is bigger than 250 k or not。



![](img/59900f333dcf4743a8289273bce145db_69.png)

And so that's a logistic regression act trying to model the probability of that event。



![](img/59900f333dcf4743a8289273bce145db_71.png)

And notice how wide the standard errors is are at they end right now， although when I first saw that。

 I thought it was crazy， but then I realized the vertical scale was pretty stretched right。

 so it's only ranging up to 0。2。

![](img/59900f333dcf4743a8289273bce145db_73.png)

![](img/59900f333dcf4743a8289273bce145db_74.png)

Oh， good point， good point。 if you saw that from  zero to one， it would look a lot。



![](img/59900f333dcf4743a8289273bce145db_76.png)

More narrow。's that's a very good point。 And that's something to always bear in mind。 you know。

 the ploting scales， you know， it's important what how you decide and what scales do you use。

 And in this case， as Rob said， it's only going up to 0。2。



![](img/59900f333dcf4743a8289273bce145db_78.png)

![](img/59900f333dcf4743a8289273bce145db_79.png)

![](img/59900f333dcf4743a8289273bce145db_80.png)

What you also notice here is we've got this so-called rag plot we see at the bottom of the plot where all the zeros occur。

 that's these little spikes here。 It's kind of uniformly across the range and at above weve got where all the ones occur and you'll notice there only there's one sort of in the middle of the range and not many ones at the end。

 So there's really not any data at all to estimate this function right at the end。



![](img/59900f333dcf4743a8289273bce145db_82.png)

![](img/59900f333dcf4743a8289273bce145db_83.png)

![](img/59900f333dcf4743a8289273bce145db_84.png)

![](img/59900f333dcf4743a8289273bce145db_85.png)

![](img/59900f333dcf4743a8289273bce145db_86.png)

So in detail with polynomial regression， what you do is you create new variables and in this case theyre just transformations of the original variables。

 so x we make x1 is the original x x2 is x squared and so on。

 and then just treat the problem as a multiple linear regression model with these new derived variables。



![](img/59900f333dcf4743a8289273bce145db_88.png)

![](img/59900f333dcf4743a8289273bce145db_89.png)

![](img/59900f333dcf4743a8289273bce145db_90.png)

![](img/59900f333dcf4743a8289273bce145db_91.png)

And in this case， we're not really interested in the coefficients。

 We're more interested in the fitted functions at any particular value x0。

 right we interest in the composed function。

![](img/59900f333dcf4743a8289273bce145db_93.png)

![](img/59900f333dcf4743a8289273bce145db_94.png)

![](img/59900f333dcf4743a8289273bce145db_95.png)

So once we fit the model， we might say， well， what does the function look like at a new value x0 and so the coefficients themselves aren't that interesting。



![](img/59900f333dcf4743a8289273bce145db_97.png)

![](img/59900f333dcf4743a8289273bce145db_98.png)

And since the fitted function is actually a linear function of the coefficients， the beta L's L hats。



![](img/59900f333dcf4743a8289273bce145db_100.png)

Okay， we can get a simple expression for the pointwise variances。

 so you say what is the variance of the fitted function at x0？



![](img/59900f333dcf4743a8289273bce145db_102.png)

![](img/59900f333dcf4743a8289273bce145db_103.png)

Well， that fitted function at x0 is just a linear function， a linear combination of the parameters。



![](img/59900f333dcf4743a8289273bce145db_105.png)

And so by using the covariance matrix of the fitted parameters， you can then get an expression。

 a simple expression for the variance of this fitted value。

 We describe this in more detail in the book in somewhat more detail and。



![](img/59900f333dcf4743a8289273bce145db_107.png)

![](img/59900f333dcf4743a8289273bce145db_108.png)

![](img/59900f333dcf4743a8289273bce145db_109.png)

![](img/59900f333dcf4743a8289273bce145db_110.png)

It seems like we in the plot， we actually plot the fitted function plus or -2 standard areas。

 I said one earlier。

![](img/59900f333dcf4743a8289273bce145db_112.png)

And so getting these point why standard errors is fairly straightforward。



![](img/59900f333dcf4743a8289273bce145db_114.png)

Pointwise means that the standard error the standard error band is pointwise so the band is showing at any given point what the standard error is。

 this is not to be confused with global confidence bands， which is another story。



![](img/59900f333dcf4743a8289273bce145db_116.png)

![](img/59900f333dcf4743a8289273bce145db_117.png)

![](img/59900f333dcf4743a8289273bce145db_118.png)

The other thing is， what degree do we use？ So here we were actually using a fourth degree polynomial。

 I said third， but we use fourth。

![](img/59900f333dcf4743a8289273bce145db_120.png)

![](img/59900f333dcf4743a8289273bce145db_121.png)

So that D is obviously a parameter， and often we just pick D to be some small number like two or three。

4 in this case， well otherwise we can actually select D by cross validation。

 think of it as a tuning parameter。

![](img/59900f333dcf4743a8289273bce145db_123.png)

![](img/59900f333dcf4743a8289273bce145db_124.png)

![](img/59900f333dcf4743a8289273bce145db_125.png)

![](img/59900f333dcf4743a8289273bce145db_126.png)

嗯。For logistic regression， the details are pretty much the same in as I said in the figure。

 this is what we were modeling。

![](img/59900f333dcf4743a8289273bce145db_128.png)

![](img/59900f333dcf4743a8289273bce145db_129.png)

And so there's our inverse logistic function， and it's just a polynomial instead of a linear function。



![](img/59900f333dcf4743a8289273bce145db_131.png)

And。

![](img/59900f333dcf4743a8289273bce145db_133.png)

One small detail， at's somewhat important is to get confidence intervals。



![](img/59900f333dcf4743a8289273bce145db_135.png)

What you do is if you try and get confidence intervals for the probabilities using sort of direct methods you might get outside the range0 and1。

 so what you do is you get confidence intervals for the fitted logit and then you put them the upper and lower confidence band endpoints through the inverse logit transformation and those give you the。



![](img/59900f333dcf4743a8289273bce145db_137.png)

![](img/59900f333dcf4743a8289273bce145db_138.png)

![](img/59900f333dcf4743a8289273bce145db_139.png)

![](img/59900f333dcf4743a8289273bce145db_140.png)

The confidence intervals， or the。

![](img/59900f333dcf4743a8289273bce145db_142.png)

In this case for the fitted probabilities， so that's a useful trick to bear in mind。



![](img/59900f333dcf4743a8289273bce145db_144.png)

Okay， few other points。With polym so we've just talked about with a single variable for several variables。

 you can do it separately on each variable right so you just generate these transformations on each variable and then just stack them together in one big matrix and fit a big linear model in all these new derived variables so if you've got a variable x。

 you may make x1 x2 up to say x4 you have another variable Z。

 you can make z1 up to z4 and then you just stack them all and make a big model matrix and fit your linear model and then you have to unpack the pieces to compose the functions and we'll see later on that the gam technology generalize additive model technology helps you do this in a seamless way。



![](img/59900f333dcf4743a8289273bce145db_146.png)

![](img/59900f333dcf4743a8289273bce145db_147.png)

![](img/59900f333dcf4743a8289273bce145db_148.png)

![](img/59900f333dcf4743a8289273bce145db_149.png)

![](img/59900f333dcf4743a8289273bce145db_150.png)

![](img/59900f333dcf4743a8289273bce145db_151.png)

![](img/59900f333dcf4743a8289273bce145db_152.png)

![](img/59900f333dcf4743a8289273bce145db_153.png)

![](img/59900f333dcf4743a8289273bce145db_154.png)

There some caveats with polynomial regression。

![](img/59900f333dcf4743a8289273bce145db_156.png)

Polynomials， as I mentioned before have notorious tail behavior， very bad for extrapolation。

 those tails tend to wiggle around and you really wouldn't want to trust predictions beyond the range of the data or even too near the ends of the data。



![](img/59900f333dcf4743a8289273bce145db_158.png)

![](img/59900f333dcf4743a8289273bce145db_159.png)

![](img/59900f333dcf4743a8289273bce145db_160.png)

And finally， fitting a polynomial in R is very simple yes。



![](img/59900f333dcf4743a8289273bce145db_162.png)

A simple expression for fitting a polynomial in x to Y。

 this is the model formula that you'd use as a poly function that generates these transformations for you。

 and it's as simple as that。

![](img/59900f333dcf4743a8289273bce145db_164.png)

![](img/59900f333dcf4743a8289273bce145db_165.png)

And we'll see in in the lab， well get some experience with that。



![](img/59900f333dcf4743a8289273bce145db_167.png)

![](img/59900f333dcf4743a8289273bce145db_168.png)

![](img/59900f333dcf4743a8289273bce145db_169.png)

Step functions， that's another way of fitting nonlinearities。

 especially popular in epidemiology and biostatistics in the last 20 or so years。



![](img/59900f333dcf4743a8289273bce145db_171.png)

And， and that what you do is you cut your variable， your continuous variable into， into。



![](img/59900f333dcf4743a8289273bce145db_173.png)

InInto discrete sub ranges， for example， here， we've cut age at 35。



![](img/59900f333dcf4743a8289273bce145db_175.png)

![](img/59900f333dcf4743a8289273bce145db_176.png)

And again， at 65， there's actually a cut at 50 as well， conciia。



![](img/59900f333dcf4743a8289273bce145db_178.png)

And then the idea is you fit a constant model in each of the regions。



![](img/59900f333dcf4743a8289273bce145db_180.png)

So it's a piecewise constant model。

![](img/59900f333dcf4743a8289273bce145db_182.png)

So you can see here so the function of when you fit it and plot them all together。

 you see the constant in the first range， the second range。

 the third range is hardly visible that is' different and then in the fourth range and so this becomes when put together as a nonlinear function。

 that's a piecewise constant function。

![](img/59900f333dcf4743a8289273bce145db_184.png)

![](img/59900f333dcf4743a8289273bce145db_185.png)

![](img/59900f333dcf4743a8289273bce145db_186.png)

![](img/59900f333dcf4743a8289273bce145db_187.png)

And this is often useful if there's some natural cut points that are of interest， you know。

 so what is the average income for somebody below the age of 35， you know。

 so you can read it straight off the plot。

![](img/59900f333dcf4743a8289273bce145db_189.png)

![](img/59900f333dcf4743a8289273bce145db_190.png)

![](img/59900f333dcf4743a8289273bce145db_191.png)

This is often good for summaries in newspapers and reports and things like that。

 which has led to its popularity。

![](img/59900f333dcf4743a8289273bce145db_193.png)

And， you know， to do it is just as easy as as as it was for polynomials。

If you think of this function over here， its。It's a binary variable。

 you make a binary variable is x less than 35。

![](img/59900f333dcf4743a8289273bce145db_195.png)

![](img/59900f333dcf4743a8289273bce145db_196.png)

If yes， you make it one， if not， you make it a zero。 and for each of these， it's the same。

 And so you create a bunch of dummy variables。

![](img/59900f333dcf4743a8289273bce145db_198.png)

0，1 variables。 And you just fit those with a linear model。

 You can already see the advantage this has over over polynomials， right， This is local。

 Remember with polynomials。

![](img/59900f333dcf4743a8289273bce145db_200.png)

![](img/59900f333dcf4743a8289273bce145db_201.png)

It's a single function for the whole range of the x variable， so for example。

 if I change a point on the left side， it could potentially change the fit on the right side quite a bit for polynomials That's a good point which I forgot to say but for step functions。

 a fit a point only affects the fit in the partition it's sitting in and not the other partitions。



![](img/59900f333dcf4743a8289273bce145db_203.png)

![](img/59900f333dcf4743a8289273bce145db_204.png)

![](img/59900f333dcf4743a8289273bce145db_205.png)

![](img/59900f333dcf4743a8289273bce145db_206.png)

That's a great point and thanks for reminding us。

![](img/59900f333dcf4743a8289273bce145db_208.png)

Well polynomial， the parameters affect the function everywhere。



![](img/59900f333dcf4743a8289273bce145db_210.png)

And can have dramatic effects。

![](img/59900f333dcf4743a8289273bce145db_212.png)

Yeah， we've done the same thing as we did before for the logistic regression。

 but with a piecewise constant function， everything else is the same。

 but the the fitted function is kind of blocky and。



![](img/59900f333dcf4743a8289273bce145db_214.png)

![](img/59900f333dcf4743a8289273bce145db_215.png)

You， may be considered not as attractive。

![](img/59900f333dcf4743a8289273bce145db_217.png)

Step functions are easy to work with， as I said， you make a bunch of dummy variables and just fit the linear model。



![](img/59900f333dcf4743a8289273bce145db_219.png)

![](img/59900f333dcf4743a8289273bce145db_220.png)

It's also a useful way of creating interactions that are easy to interpret。 So， for example。

 think of the interaction effect of year and age in a linear model。



![](img/59900f333dcf4743a8289273bce145db_222.png)

![](img/59900f333dcf4743a8289273bce145db_223.png)

So what you can do is， for example， make a dummy variable of year。

 so let's say cut year less than or equal to less than 2005。



![](img/59900f333dcf4743a8289273bce145db_225.png)

![](img/59900f333dcf4743a8289273bce145db_226.png)

And have another one year bigger than equal to 2005 and then if you multiply that with age。

 what you've done is create an interaction and that' will fit a linear different linear model。



![](img/59900f333dcf4743a8289273bce145db_228.png)

![](img/59900f333dcf4743a8289273bce145db_229.png)

As a function of age for people who worked before 2005 and those after 2005。And。

 and so that visually， that's nice。 You'll see two different linear functions。

 It's the easy way of seeing the effect of an interaction。



![](img/59900f333dcf4743a8289273bce145db_231.png)

And in R， creating these dummy variables is really easy。



![](img/59900f333dcf4743a8289273bce145db_233.png)

Creating an indicator function is pretty much the same expression we've shown at trial now。

 There is a function I in R， which is basically an indicator。



![](img/59900f333dcf4743a8289273bce145db_235.png)

![](img/59900f333dcf4743a8289273bce145db_236.png)

And year less than 25 turns into a logical， but when wrapped in the indicator。

 it's essentially a 01 variable。

![](img/59900f333dcf4743a8289273bce145db_238.png)

![](img/59900f333dcf4743a8289273bce145db_239.png)

And if you want to cut in more than one place there's a function called cut。

 so you can cut age and you give it the cut points。

 you need to give cut the two boundary points as well， and so in this case 18 and 90。

 those are the ranges of the ages will be on the range actually。

 and then the interior cut points and it'll create a factor for you。

 an audit factor that cuts the variable into those bins。



![](img/59900f333dcf4743a8289273bce145db_241.png)

![](img/59900f333dcf4743a8289273bce145db_242.png)

![](img/59900f333dcf4743a8289273bce145db_243.png)

![](img/59900f333dcf4743a8289273bce145db_244.png)

Now， the choice of the cut points or knots， as we're going to call them， can be little problematic。



![](img/59900f333dcf4743a8289273bce145db_246.png)

For creating nonlinearities， smooth alternatives are available。

 and we're going to talk about them next。 You might just pick an unfortunate choice of cut points。

 and it doesn't show the non linearity at all。 And so there's somewhat of an art。 So usually these。



![](img/59900f333dcf4743a8289273bce145db_248.png)

![](img/59900f333dcf4743a8289273bce145db_249.png)

![](img/59900f333dcf4743a8289273bce145db_250.png)

Peacewise constant functions are especially good if they are natural cut points that you want to use。



![](img/59900f333dcf4743a8289273bce145db_252.png)