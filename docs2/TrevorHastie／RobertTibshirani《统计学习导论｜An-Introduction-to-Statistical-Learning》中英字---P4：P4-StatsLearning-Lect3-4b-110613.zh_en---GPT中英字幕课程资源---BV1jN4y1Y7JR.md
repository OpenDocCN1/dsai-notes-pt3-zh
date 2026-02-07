# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P4：P4 StatsLearning Lect3 4b 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

Okay， here we're going to see situations where our nearest neighbor averaging doesn't work so well。

 and we're going to have to find ways to deal with that。



![](img/6ca7cd74c7f41973dfadda90ef781638_1.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_2.png)

Nearest neighbor a， which is the one we just saw， can be pretty good for small P。

 small numbers of variables。 Yeah， we had just one variable。



![](img/6ca7cd74c7f41973dfadda90ef781638_4.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_5.png)

But small maybe P less than equal to 4 and largeish n。

 right not large n so that we have enough points in each neighborhood to average to give us our estimate。



![](img/6ca7cd74c7f41973dfadda90ef781638_7.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_8.png)

Now， this is just one version of a whole class of techniques called smoothers。



![](img/6ca7cd74c7f41973dfadda90ef781638_10.png)

And， and we're going to discuss later on in this course。

 much cleverer ways of doing this kind of averaging， such as kernel and sp smoothing。



![](img/6ca7cd74c7f41973dfadda90ef781638_12.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_13.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_14.png)

Now there's a problem though， nearest neighbor methods can be really lousy when P is large。



![](img/6ca7cd74c7f41973dfadda90ef781638_16.png)

And the reason has got the name， the curse of dimensionality。



![](img/6ca7cd74c7f41973dfadda90ef781638_18.png)

What it boils down to is that nearest neighbors tend to be far away in high dimensions。



![](img/6ca7cd74c7f41973dfadda90ef781638_20.png)

So。And that creates a problem。

![](img/6ca7cd74c7f41973dfadda90ef781638_22.png)

We need to get a reasonable fraction of the n values of Yi to average to bring the variances down。

 so we need to average a number of points in each neighborhood so that our estimate has got a nice。

 reasonably small variance。

![](img/6ca7cd74c7f41973dfadda90ef781638_24.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_25.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_26.png)

And let's suppose we want 10% of the data points to be in each interval。



![](img/6ca7cd74c7f41973dfadda90ef781638_28.png)

The problem is that 10% neighborhood in high dimensions need no longer be local。

 so we lose the spirit of estimating the conditional expectation by local aver。



![](img/6ca7cd74c7f41973dfadda90ef781638_30.png)

So let's look at a little example of that。

![](img/6ca7cd74c7f41973dfadda90ef781638_32.png)

In the left panel。We've got values of two variables， x1 and x2。

 and they're actually uniformly distributed in this little cube with edges minus1 to plus1。

 minus1 to plus1。

![](img/6ca7cd74c7f41973dfadda90ef781638_34.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_35.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_36.png)

And we formed two， 10% neighborhoods in this case。The first neighborhood is just involving the variable x1。

 ignoring x2。

![](img/6ca7cd74c7f41973dfadda90ef781638_38.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_39.png)

And so that's indicated by the vertical dotted lines。



![](img/6ca7cd74c7f41973dfadda90ef781638_41.png)

Our target point is at 0。And so we spread out a neighborhood to the left and right until we capture 10% of the data points with respect to the variable x1。

 and the dotted line indicates the width of the neighborhood。



![](img/6ca7cd74c7f41973dfadda90ef781638_43.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_44.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_45.png)

Alternatively， if we want to find enabled in two dimensions。

 we spread out a circle centered at the target point。

 which is the red dot there until we've captured 10% of the points。



![](img/6ca7cd74c7f41973dfadda90ef781638_47.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_48.png)

Now notice the radius of the circle in two dimensions is much bigger than the radius of the circle in one dimensions。

 which is just the width between these two dotted lines。



![](img/6ca7cd74c7f41973dfadda90ef781638_50.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_51.png)

And so to capture 10% of the points in two dimensions。

 we have to go out further and so we're less local than we are in one dimension。



![](img/6ca7cd74c7f41973dfadda90ef781638_53.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_54.png)

And so we can take this example further and on the right hand plot I've shown you how far you have to go out in one。

 two， three， five and  ten0 dimensions。

![](img/6ca7cd74c7f41973dfadda90ef781638_56.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_57.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_58.png)

In10 dimensions， these are different versions of this problem as the dimensions get higher in order to capture a certain fraction of the volume。



![](img/6ca7cd74c7f41973dfadda90ef781638_60.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_61.png)

Okay， and so take， for example， 10% or 0。1 fraction of the volume。



![](img/6ca7cd74c7f41973dfadda90ef781638_63.png)

So for p equals1， if the data is uniform， you roughly go at 10% of the distance， right？



![](img/6ca7cd74c7f41973dfadda90ef781638_65.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_66.png)

In two dimensions we saw you went more， look what happens in five dimensions， in five dimensions。

 you have to go out about 0。9 on each coordinate axis to get 10% of the data。

 that's just about the whole radius of the sphere。

![](img/6ca7cd74c7f41973dfadda90ef781638_68.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_69.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_70.png)

And in 10 dimensions， you actually have to go break out of the sphere in order to get points in the corner to capture the 10%。



![](img/6ca7cd74c7f41973dfadda90ef781638_72.png)

So the bottom line here is it's really hard to find near neighborhoods in high dimensions and stay local。

🤢。

![](img/6ca7cd74c7f41973dfadda90ef781638_74.png)

If this problem didn't exist， we would uses in the near neighbor aver。



![](img/6ca7cd74c7f41973dfadda90ef781638_76.png)

As the sole basis for doing estimation。

![](img/6ca7cd74c7f41973dfadda90ef781638_78.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_79.png)

So how do we deal with this？ Well， we introduce structure to our models。



![](img/6ca7cd74c7f41973dfadda90ef781638_81.png)

The simplest structural model is a linear model， and so here we have an example of a linear model。

 we've got P features。

![](img/6ca7cd74c7f41973dfadda90ef781638_83.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_84.png)

It's just got P plus1 parameters and it says that the function of x。

 we can approximate by a linear function， so there's a coefficient on each of the x's and an intercept。

 so that's one of the simplest structural models。

![](img/6ca7cd74c7f41973dfadda90ef781638_86.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_87.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_88.png)

We can estimate the parameters of the model by fitting the model to training data and we'll be talking more about how you do that。



![](img/6ca7cd74c7f41973dfadda90ef781638_90.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_91.png)

And when we use such a structural model， and of course。

 this structural model is going to avoid the curse of dimensionality because it's not reing on any local properties and nearest neighbor average。

 it's just fit in quite a rigid model to all the data。



![](img/6ca7cd74c7f41973dfadda90ef781638_93.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_94.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_95.png)

那。A linear model is almost never correct。

![](img/6ca7cd74c7f41973dfadda90ef781638_97.png)

But it often serves as a good approximation and interpretable approximation to the unknown true function f of x。



![](img/6ca7cd74c7f41973dfadda90ef781638_99.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_100.png)

So。Here's our same little example data set， and we can see in the top plot。

 a linear model gives a reasonable fit to the data， not perfect。



![](img/6ca7cd74c7f41973dfadda90ef781638_102.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_103.png)

In the bottom plot， we've augmented our linear model and we've included a quadratic term。

 so we put in our x and we put in an x squared as well。



![](img/6ca7cd74c7f41973dfadda90ef781638_105.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_106.png)

And we see that fits the data much better。

![](img/6ca7cd74c7f41973dfadda90ef781638_108.png)

It's also a linear model， but it's linear in some transformed values of x。



![](img/6ca7cd74c7f41973dfadda90ef781638_110.png)

And notice now we've put hats on each of the parameters suggesting they've been estimated in this case from these training data。



![](img/6ca7cd74c7f41973dfadda90ef781638_112.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_113.png)

His little hats indicate that they've been estimated from the training data。Okay。

 so those are two parametric models， structured models that。



![](img/6ca7cd74c7f41973dfadda90ef781638_115.png)

That seemed to do a good job in this case。

![](img/6ca7cd74c7f41973dfadda90ef781638_117.png)

Here's a two dimensional example， again， seniority， years of education and income。



![](img/6ca7cd74c7f41973dfadda90ef781638_119.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_120.png)

And this is simulated data， and so the blue surface is actually showing you the true function from which the data was simulated with errors。



![](img/6ca7cd74c7f41973dfadda90ef781638_122.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_123.png)

We can see the a big。Each of those data points。

![](img/6ca7cd74c7f41973dfadda90ef781638_125.png)

Comes from a particular pair of years of education and seniority with some error and the little line segments in the data points show you the error。

 Okay so we can write that as income is a function of education and seniority plus some error So this is the truth。

 We actually know this in this case。

![](img/6ca7cd74c7f41973dfadda90ef781638_127.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_128.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_129.png)

And here's a linear regression model fit to those simulation data。



![](img/6ca7cd74c7f41973dfadda90ef781638_131.png)

So， you know， it's an approximation， it captures the important elements of the relationship。

 but doesn't capture everything， okay， it's got three parameters。



![](img/6ca7cd74c7f41973dfadda90ef781638_133.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_134.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_135.png)

Here's a more flexible regression model， we've actually fit this using a technique called thin plate splines and that's a nice smooth version of a two dimensional smoother it's different from nearest neighbor aver it's got some nicer properties。



![](img/6ca7cd74c7f41973dfadda90ef781638_137.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_138.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_139.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_140.png)

And you can see this does a pretty good job if we go back to the generating data and the generating surface。



![](img/6ca7cd74c7f41973dfadda90ef781638_142.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_143.png)

This thin plate spline actually captures more of the essence of what's going on there。



![](img/6ca7cd74c7f41973dfadda90ef781638_145.png)

And for thin space blinds， we're going to talk about them later in chapter7。

 there's a tuning parameter that controls how smooth the surface is。



![](img/6ca7cd74c7f41973dfadda90ef781638_147.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_148.png)

Here's an example of a thin plate spe where we basically tune the parameter all the way down to zero。

 and this surface actually goes through every single data point。



![](img/6ca7cd74c7f41973dfadda90ef781638_150.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_151.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_152.png)

In this case， that's overfi in the data。 We expect to have some errors because the true function。



![](img/6ca7cd74c7f41973dfadda90ef781638_154.png)

generateenerate data points with errors。 So this is known as overfitting。

 overfitting the training data。

![](img/6ca7cd74c7f41973dfadda90ef781638_156.png)

So this is an example where we've got a family of functions and we've got a way of controlling the complexity。



![](img/6ca7cd74c7f41973dfadda90ef781638_158.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_159.png)

So there's some trade offs when building models。

![](img/6ca7cd74c7f41973dfadda90ef781638_161.png)

One trade off is prediction accuracy versus interpretability。 so linear models are easy to interpret。

 We just got a few parameters， thin plate splines are not。



![](img/6ca7cd74c7f41973dfadda90ef781638_163.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_164.png)

They give you a whole surface back and if you get given a surface back in 10 dimensions。

 it's hard to understand what it's actually telling you。



![](img/6ca7cd74c7f41973dfadda90ef781638_166.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_167.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_168.png)

We can have a good fit versus overfoot or underfit， so in this previous example。

 the middle one was a good fit， the linear was slightly underfit and the last one was overfit。

 so how do we know when the fit is just right？

![](img/6ca7cd74c7f41973dfadda90ef781638_170.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_171.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_172.png)

We need to be able to select。Amongst those。

![](img/6ca7cd74c7f41973dfadda90ef781638_174.png)

Psimony versus black box parsimony means。

![](img/6ca7cd74c7f41973dfadda90ef781638_176.png)

Having a model that's simpler and can be。That can be transmitted with a small number of parameters and explained in a simple fashion and involve maybe a subset of the predictors。



![](img/6ca7cd74c7f41973dfadda90ef781638_178.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_179.png)

嗯。

![](img/6ca7cd74c7f41973dfadda90ef781638_181.png)

And you know， and so those models， if they do as well as say， a black box predictor。

 like the thin plate spline or somewhat of a black box predictor， we'd prefer the simpler model。



![](img/6ca7cd74c7f41973dfadda90ef781638_183.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_184.png)

Here's a little。

![](img/6ca7cd74c7f41973dfadda90ef781638_186.png)

Schematic， which shows a variety of the methods that we're going to be discussing in this course。



![](img/6ca7cd74c7f41973dfadda90ef781638_188.png)

And they ordered by interpretability and flexibility。



![](img/6ca7cd74c7f41973dfadda90ef781638_190.png)

And at the top， there are two versions of linear regression。



![](img/6ca7cd74c7f41973dfadda90ef781638_192.png)

Subset selection and lau， which we'll talk about that actually even think the linear regression models too complex and。



![](img/6ca7cd74c7f41973dfadda90ef781638_194.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_195.png)

Try and reduce it by throwing out some of the variables。Linear models in least squares。



![](img/6ca7cd74c7f41973dfadda90ef781638_197.png)

Slightly more flexible， but you lose some interpretability because now all the variables are thrown in。



![](img/6ca7cd74c7f41973dfadda90ef781638_199.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_200.png)

Then we have generalized additive models which allow for transformations in an automatic way of each of the variables。



![](img/6ca7cd74c7f41973dfadda90ef781638_202.png)

And then at the high flexibility， low interpretability and bagging boosting and support vector machines。



![](img/6ca7cd74c7f41973dfadda90ef781638_204.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_205.png)

We'll discuss all these techniques， but later on in the course。



![](img/6ca7cd74c7f41973dfadda90ef781638_207.png)

Okay， so we covered linear regression， and we covered nearest neighbor averaging。

 And we talked about ways places where those where that's not going to work。 And so we've。



![](img/6ca7cd74c7f41973dfadda90ef781638_209.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_210.png)

Briefly introduced a number of other different methods， and they all listed on the screen。



![](img/6ca7cd74c7f41973dfadda90ef781638_212.png)

Different methods that we can use to solve the problem when the dimensions high and when linearity doesn't work。

 but we have to choose amongst these methods。 and so we need to develop ways of making those choices。

 and that's what we're going to cover in the next segment。



![](img/6ca7cd74c7f41973dfadda90ef781638_214.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_215.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_216.png)

![](img/6ca7cd74c7f41973dfadda90ef781638_217.png)