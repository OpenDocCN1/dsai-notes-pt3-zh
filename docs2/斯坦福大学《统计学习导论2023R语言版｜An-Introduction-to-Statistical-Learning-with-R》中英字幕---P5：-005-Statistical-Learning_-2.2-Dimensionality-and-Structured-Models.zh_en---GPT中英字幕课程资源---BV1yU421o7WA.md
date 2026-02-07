# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P5：-005-Statistical Learning_ 2.2 Dimensionality and Structured Models.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

Okay， here we're going to see situations where our nearest neighbor averaging doesn't work so well。

 and we're going to have to find ways to deal with that。



![](img/f4b85ee1a862f75908cf60114b1dc066_1.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_2.png)

Nearest neighbor a， which is the one we just saw， can be pretty good for small P。

 small numbers of variables。 Yeah， we had just one variable。But small。

 maybe P less than equal to 4 and largeish n， right not large n so that we have enough points in each neighbour to average to give us our estimate。



![](img/f4b85ee1a862f75908cf60114b1dc066_4.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_5.png)

Now， this is just one version of a whole class of techniques called smoothers。And。

 and we're going to discuss later on in this course， much cleverer ways of doing this kind of aaging。

 such as kernel and sp smoothing。

![](img/f4b85ee1a862f75908cf60114b1dc066_7.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_8.png)

Now there's a problem， though， nearest neighbor methods can be really lousy when P is large。

And the reason has got the name the curse of dimensionality。

 What it boils down to is that nearest neighbors tend to be far away in high dimensions。So。

And that creates a problem。We need to get a reasonable fraction of the n values of Yi to average to bring the variances down。

 so we need to average a number of points in each neighborhood so that our estimate has got a nice。

 reasonably small variance。And let's suppose we want 10% of the data points to be in each interval。

The problem is a 10% neighbour in high dimensions need no longer be local。

 so we lose the spirit of estimating the conditional expectation by local averaging。

So let's look at a little example of that。In the left panel。We've got values of two variables。

 X 1 and x2， and theyre actually uniformly distributed in this little cube with with edges。

 -1 to plus 1，-1 to plus1。

![](img/f4b85ee1a862f75908cf60114b1dc066_10.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_11.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_12.png)

And we formed two 10% neighborhoods in this case。The first neighborhood is just involving the variable x1。

 ignoring x2。

![](img/f4b85ee1a862f75908cf60114b1dc066_14.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_15.png)

And so that's indicated by the vertical dotted lines。Our target point is at zero。



![](img/f4b85ee1a862f75908cf60114b1dc066_17.png)

And so we spread out a neighborhood to the left and right until we capture 10% of the data points with respect to to the variable x1。

 and the dotted line indicates the width of the neighborhood。



![](img/f4b85ee1a862f75908cf60114b1dc066_19.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_20.png)

Alternatively， if we want to find enabled in two dimensions。

 we spread out a circle centered at the target point。

 which is the red dot there until we've captured 10% of the points。



![](img/f4b85ee1a862f75908cf60114b1dc066_22.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_23.png)

Now notice the radius of the circle in two dimensions is much bigger than the radius of the circle in one dimensions。

 which is just the width between these two dotted lines。



![](img/f4b85ee1a862f75908cf60114b1dc066_25.png)

And so to capture 10% of the points in two dimensions。

 we have to go out further and and so we're less local than we are in one dimension。



![](img/f4b85ee1a862f75908cf60114b1dc066_27.png)

And so we can take this example further and on the right hand plot I've shown you how far you have to go out in one。

 two， three， five and  ten0 dimensions。

![](img/f4b85ee1a862f75908cf60114b1dc066_29.png)

In10 dimensions， these are different versions of this problem as the dimensions get higher in order to capture a certain fraction of the volume。

Okay， and so take， for example， 10% or 0。1 fraction of the volume。



![](img/f4b85ee1a862f75908cf60114b1dc066_31.png)

So for P equals 1， if the data is uniform， you roughly go at 10% of the distance， right？



![](img/f4b85ee1a862f75908cf60114b1dc066_33.png)

In two dimensions we saw you went more， look what happens in five dimensions in five dimensions you have to go out about 0。

9 on each coordinate axis to get 10% of the data that's just about the whole radius of the sphere and in 10 dimensions you actually have to go break out of the sphere in order to get points in the corner to capture the 10%。



![](img/f4b85ee1a862f75908cf60114b1dc066_35.png)

So the bottom line here is it's really hard to find near neighborhoods in high dimensions and stay local。

🤢。

![](img/f4b85ee1a862f75908cf60114b1dc066_37.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_38.png)

If this problem didn't exist， we would use neighbors in the near neighbor averaging。



![](img/f4b85ee1a862f75908cf60114b1dc066_40.png)

As the sole basis for doing estimation。

![](img/f4b85ee1a862f75908cf60114b1dc066_42.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_43.png)

So how do we deal with this？ Well， we introduce structure to our models and so。



![](img/f4b85ee1a862f75908cf60114b1dc066_45.png)

The simplest structural model is a linear model and so here we have an example of a linear model。

 we've got P features。 it's just got p plus1 parameters and it says the function of x。

 we're can approximate by a linear function， so there's a coefficient on each of the x's and an intercept。

 so that's one of the simplest structural models。We can estimate the parameters of the model by fitting the model to training data。

 and we'll be talking more about how you do that。And when we use such a structural model。

 and of course， this structural model is going to avoid the curse of dimensionality because it's not reing on any local properties and nearest neighbor average。

 it's just fit in quite a rigid model to all the data。那。A linear model is almost never correct。

But it often serves as a good approximation and interpretable approximation to the unknown true function f of x。



![](img/f4b85ee1a862f75908cf60114b1dc066_47.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_48.png)

So。Here's our same little example data set， and we can see in the top plot。

 a linear model gives a reasonable fit to the data， not perfect。



![](img/f4b85ee1a862f75908cf60114b1dc066_50.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_51.png)

In the bottom plot， we've augmented our linear model， and we've included a quadratic term。

 so we put in our x and we put in an x squared as well。



![](img/f4b85ee1a862f75908cf60114b1dc066_53.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_54.png)

And we see that fits the data much better。

![](img/f4b85ee1a862f75908cf60114b1dc066_56.png)

It's also a linear model， but it's linear in some transformed values of x。



![](img/f4b85ee1a862f75908cf60114b1dc066_58.png)

And notice now we've put hats on each of the parameters suggesting they've been estimated in this case from these training data。



![](img/f4b85ee1a862f75908cf60114b1dc066_60.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_61.png)

These little hats indicate that they've been estimated from the training data。

So those are two parametric models， structured models that seem to do a good job in this case。



![](img/f4b85ee1a862f75908cf60114b1dc066_63.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_64.png)

Here's a two dimensional example， again， seniority， years of education and income。



![](img/f4b85ee1a862f75908cf60114b1dc066_66.png)

And this is simulated data， and so the blue surface is actually showing you the true function from which the data was simulated with errors。



![](img/f4b85ee1a862f75908cf60114b1dc066_68.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_69.png)

We can see the Arizona big。Each of those data points。



![](img/f4b85ee1a862f75908cf60114b1dc066_71.png)

Comes from a particular pair of years of education and seniority with some error And the little。

 little line segments in the in the data points show you the error。 Okay。

 so we can write that as income is a function of education and seniority plus some error。 So this。

 this is the truth。 We actually know this in this case。



![](img/f4b85ee1a862f75908cf60114b1dc066_73.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_74.png)

And here's a linear regression model fit to those simulation data。



![](img/f4b85ee1a862f75908cf60114b1dc066_76.png)

So， you know， it's an approximation， it captures the important elements of the relationship。

 but doesn't capture everything。 okay， it's got three parameters。



![](img/f4b85ee1a862f75908cf60114b1dc066_78.png)

Here's a more flexible regression model， we've actually fit this using a technique called thin plate splines and that's a nice smooth version of a two dimensional smoother。

 it's different from nearest neighbor a and it's got some nicer properties。



![](img/f4b85ee1a862f75908cf60114b1dc066_80.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_81.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_82.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_83.png)

And you can see this does a pretty good job if we go back to the generating data and the generating surface。



![](img/f4b85ee1a862f75908cf60114b1dc066_85.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_86.png)

This thin plate spline actually captures more of the essence of what's going on there。



![](img/f4b85ee1a862f75908cf60114b1dc066_88.png)

And for thinplace blinds， we're going to talk about them later in chapter7。

 there's a tuning parameter that controls how smooth the surface is。



![](img/f4b85ee1a862f75908cf60114b1dc066_90.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_91.png)

Here's an example of a thin plate splinee where we basically tune the parameter all the way down to zero。

 and this surface actually goes through every single data point。



![](img/f4b85ee1a862f75908cf60114b1dc066_93.png)

In this case， that's overfiing the data， we expect to have some errors because the true function。



![](img/f4b85ee1a862f75908cf60114b1dc066_95.png)

Generate data points with errors。 So this is known as overfitting。 We overfiing the training data。



![](img/f4b85ee1a862f75908cf60114b1dc066_97.png)

So this is an example where we've got a family of functions and we've got a way of controlling the complexity。



![](img/f4b85ee1a862f75908cf60114b1dc066_99.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_100.png)

So there's some trade offs when building models。One trade off is prediction accuracy versus interpretability。

 So linear models are easy to interpret。 We've just got a few parameters， thin plate splines are not。



![](img/f4b85ee1a862f75908cf60114b1dc066_102.png)

They， they give you a whole surface back。 And if you get given a surface back in in 10 dimensions。

 it's hard to understand what's what it's actually telling you。



![](img/f4b85ee1a862f75908cf60114b1dc066_104.png)

We can have a good fit versus versus overfoot or underfit。 So in this previous example。

 the middle one was a good fit。 the linear was slightly underfit and and the last one was overfit。

 So how do we know when the fit is just right。

![](img/f4b85ee1a862f75908cf60114b1dc066_106.png)

We need to be able to select amongst those。Psimony versus black box。 Parsony means。



![](img/f4b85ee1a862f75908cf60114b1dc066_108.png)

Having a model that's simpler and can be。That can be transmitted with a small number of parameters and explained in a simple fashion and involve maybe a subset of the predictors。

嗯。

![](img/f4b85ee1a862f75908cf60114b1dc066_110.png)

And， you know， and so those models， if they do as well as say a black box predictor。

 like the thin plate spe or somewhat of a black box predictor， we'd prefer the simpler model。



![](img/f4b85ee1a862f75908cf60114b1dc066_112.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_113.png)

Uses a little。

![](img/f4b85ee1a862f75908cf60114b1dc066_115.png)

Schematic， which shows a variety of the methods that we're going to be discussing in this course。



![](img/f4b85ee1a862f75908cf60114b1dc066_117.png)

And they ordered by interpretability and flexibility。And at the top。

 there are two versions of linear regression。Subset selection and lau， which we'll talk about。

 then actually even think the linear regression models too complex and。

Try and reduce it by throwing out some of the variables。Linear models in least squares。

Slightly more flexible， but you lose some interpretability because now all the variables are thrown in。



![](img/f4b85ee1a862f75908cf60114b1dc066_119.png)

Then we have generalized additive models which allow for transformations in an automatic way of each of the variables。



![](img/f4b85ee1a862f75908cf60114b1dc066_121.png)

And then at the high flexibility， low interpretability and bagging boosting and support vector machines。



![](img/f4b85ee1a862f75908cf60114b1dc066_123.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_124.png)

We we'll discuss all these techniques， but later on in the course。



![](img/f4b85ee1a862f75908cf60114b1dc066_126.png)

Okay， so we covered linear regression and we covered nearest neighbor averaging。



![](img/f4b85ee1a862f75908cf60114b1dc066_128.png)

And we talked about ways， places where those where that's not going to work。 And so we've。



![](img/f4b85ee1a862f75908cf60114b1dc066_130.png)

Briefly introduced a number of other different methods， and theyre all listed on the screen。



![](img/f4b85ee1a862f75908cf60114b1dc066_132.png)

Different methods that we can use to solve the problem when the dimensions high and when linearity doesn't work。

 but we have to choose amongst these methods。 and so we need to develop ways of making those choices。

 and that's what we're going to cover in the next segment。



![](img/f4b85ee1a862f75908cf60114b1dc066_134.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_135.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_136.png)

![](img/f4b85ee1a862f75908cf60114b1dc066_137.png)