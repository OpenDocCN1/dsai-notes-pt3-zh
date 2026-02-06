# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P53：-053-Statistical Learning_ 7.R.2 Splines and GAMs.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

Okay， Karen， right on， we， we fit in linear functions。 We've seen polynomials。

 We're going to now move on to splines， which are more flexible and and。

Offer us a wider scope of possibilities than polynomials。So。

We've got lots of nice built in tools in our forfiing splines。We're going to look at cubic splinees。

 We need to load the package for splinees， which is called。Slines。And， and now we're ready to go。

 So we'll start off with fit a linear model using wage again， same data as we used before。

 and we'll fit a cubic sp with knots at 25，40 and 60。Okay， so let's just do it and。

And we'll produce the plot， okay？嗯。And we'll put in the knots。 So there it is so。

Let me remind you what this means。So a spline is a cubic polynomial but the function B S by default gives you a basis for cubic polynomials。

You're the not。 So these are places of discontinuity。

But they just discontinuity in the third derivative。 So what these are， these blinds， again。

 they cubic polynomials in each of the regions。But they constrained to be continuous at the knots。

 and they constrain to have continuous first and second derivatives， which makes them really smooth。

 In fact， so smooth that the human eye cannot detect the discontinuity there。

They're discontinuconuous in the third derivative。So the idea of sps is that they're more local than polynomials。

So they don't have quite the wgging tails of polynomials and they're a nice way of fitting flexible functions and yeah we've actually specified where the knots are。

And in R， it's really easy to do。 There's a BS function which generates the basis。

 and there's a number of ways of specifying the flexibility。And and how you place the knots。So。Once。

 one step up from what we call fixed not regression splines or smoothing splines。

 Sing splines are convenient because they have essentially knots everywhere。

 and they control how smooth the function is with a roughness penalty。

And years are called to smooth dot sp。 It doesn't use a formula language。

 It just tells that we tell it the predictor is age， the response is wage。

 and here we say we want 16 degrees of freedom。And we'll add the， the。

 the fitted function to the plot。So 16 degrees of freedom is rather a lot。

 and you can see it's picked up some wiggles here。 So this is the effective degrees of freedoms of the smoothing sp。

 So it's allowing quite a little bit of wiggling and it's maybe a little bit too wiggly in this case。

Alternatively， with smooth dot spline， you can use leave1 out cross validation to determine the smoothing parameter。

 If you recall in the in the text， smoothing splinees had a roughness parameter which controlled how rough the function was。

And here we in this first call， we controlled it by specifying the effective degrees of freedom and the roughness penalty was was chosen accordingly。

 here we're going to use， we're going to tell it to use cross validation to pick the tuning parameter or the roughness parameter。

And so there we go， there was a little warning from smooth dot sp that noticed that there were a lot of ties in X。

 but it turns out that's fine for our purposes。 and so there's nothing to be concerned about。

 and we'll include。That fitted function。 Well， they all look the same。

 You have to really zoom in if you want to see any differences。

 the one with with that smoothing sp produced。Had less effective degrees of freedom， says 6。79。

Remember， the effective degrees of freedom don't have to be an integer。 It's a a heuristic for。

 how rough the function is。 And in this case， about 6 to 7 degrees of freedom。

A fixedix note regression spline。嗯。Let's see。 Where is it。That's in foot。No， we've overwritten fit。

 Let's see how many degrees of freedom in this one。 We'll， we'll refit it and， and we'll do。

Summary of foot。And。We can just count the parameters。And well see there's 1，2，3，4，5，6 parameters。

 So it's got 6 degrees of freedom。 So with four knots。It ended up with six degrees of freedom。

And the smoothing sp， using a slightly different methodology。

 ended up with just over  six degrees of freedom。Okay。Well。

 the final topic is going to be generalized additive models。We really want to fit。

A model with just one single predictor。 We usually have more than one predictor。

 So we need a way of mixing these together and also producing nice plots。

And the gam package is going to help us do that。 So again we require gam。

 so the gam package is loaded。And again， we'll use the wage data。

 and here we'll fit a generalized additive model。We call gam。 We tell it the response is wage。

 and here we tell it we want a smooth term in age with  four degrees of freedom。

 a smooth term in year with  four degrees of freedom。Education is a factor variable。

 so we just say we'll have education in as as linear terms。

 it' will make dummy variables for each of the levels and fit constants。

 and we tell it the data is wage。Now this S is a special function known to Gam。

 and what it tells GaAm is it wants a smoothing spline in the variable age with four degrees of freedom。

 and likewise for this term over here， and these two terms are going to be fit jointly and we'll see when we produce the plot。

So before we plot， we' will set up a plot in grid where we want。3 columns。

And this may be a little squash。 Let's see， and。I'll first plot it and see。 yeah。

 it's a little squash。 So let's just squash it down。A little bit。

 so the plot looks a little bit more balanced。Still， we can squash it down a bit further。😔，No。

 that's。Yeah， there we go。嗯。And what this plot functions has done is produce a plot for each of the terms in the gamem。

And plotted those terms， plus the standard errors for each of those terms。

 So this is the shape we've been seen for， for the variable age in in， in all the univevariate plots。

 But now we've got year， as well as education included as well。

 And so we see that salaries tends to increase with with year。

 There seems to have been in a dip around 2000。5。But then continue to rise。And no big surprise。

 salary increases monotonically with education。Now， because we've limited in plot space here。

 normally the plot for a factor variable like this would indicate at the top of the plot each what each of the levels are。

 but there's no room for that。 And so it's。It's only ended up putting the lowest one。

 but these are the levels of age， and they monitorone in the amount of education。

So this is a very convenient。 So this was done using plotted gam。 So this is a very convenient。😊。

Way of fitting nonlinear functions in several variables and having nice ways of producing plots。

GAam also works for logistic regression and other kinds of generalized linear models。

 So yeah we'll use our binary variable for wage and we'll fit the term smooth term in age and a smooth term in year and so we do that and we can plot that gam as well。

 Oh plus education and we plot that gam as well we left off the standard errors here because I happen to know that some of them are really wide and they would have dwarfed the plots。

And so this is plotting the contributions to the logit of the probability each as the separate functions since the model is additive in those。

So you can using GAm， you can do some tests。 So let's see if we need a nonlinear term for the variable year。

So we'll fit another gam where instead of having a smooth term in year。

 we'll just have a linear term in year， the rest is the same。 Well call that gam 2 a。

 And now we can use anovava to test those two models。And。It gives you the two models。

 and it does the test。 And the chi squares。 the， the P value is 082。

 which says we really don't need this non nonlinear term for。 Yeah， a linear term will be fine。

 You can， in fact。Test further and see if you need a term at all for you。

So we've seen GaAM knows how to plot functions nicely。

 It turns out you can use the plot method from GAM to plot models even fit by LM and GLM。

And so we'll demonstrate that now。So here we'll fit a linear model again with wage as a response。

 but instead of using gam， we will just fit LM and we'll generate a spline basis using other spline function。

 which is Ns， which remember we had natural splinees and Ns gives us a basis in natural splines。

So we want a natural spline in age and here we specify instead of the knots。

 we specify the effective degrees of freedom， So this looks very similar to the call to Gam。

 except we're using a fixed basis a reduced set of basis functions to represent the splinees。And。

 and likewise， for year and， and then plus a linear term in education。

So we fit that model and now even though it's an LM， we can use the plot method for gam。 Now。

 since LM is not of class gam， we need to write out plot dot gam to specify that we want to use that particular plot method and we plot that function and it does a similar thing to what it did for a legitimate gam object It plots a fitted function。

And， and it's included the standard errors。So that's just a glimpse of the capability of the gaAM function have a look at the help files for GAM there's documents on gaAM。

 Rob and I actually have a book 1991 book on generalized additive models you can find out lots more details and theres various papers have been written on GAMs and you can also look in the chapter in this introduction to statistical learning to learn a little bit about GAMs and see what the capabilities are。

