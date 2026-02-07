# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P37：P37 StatsLearning Lect8g 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/2beab32f0a7a882b1b6e1154ba206066_0.png)

So welcome back， so we've talked about a For stepwise selection and backward stepwise in all subsets as well as some techniques for choosing the model size。

All those methods fit by least squares， so whenever we consider model a subset。

 we always fit the coefficients by least squares Now we're going to talk about a different method called shrinkage。

Namely two techniques， Ri regressionion and laso。And as we'll see that these methods do not use fully squares to fit。

 but rather different criterion that has a penalty that will shrink the coefficients towards typically zero。

And we'll see these methods are very powerful， in particular they can be applied to very large data sets。

 like the kind that we see and more often these days where the number of variables might be in the thousands or even millions。

So。And one thing that's worth mentioning is that like Ri regression Lasso and shrinkage messages like this are a really contemporary area of research right now。

 I mean there's papers every day written by statisticians about variants of these methods and how to improve them and that sort of thing as opposed to some of the other things that we've covered so far in this course where you know the ideas have been around for 30。

 40 years although actually Ridge regression I think was invented in the 70s but it is true that it wasn't very popular for many。

 many years is only sort of with the advent of fast computation in the last 10 years that it's become very very popular along with the LaSso so。

Some of these methods are old， some are new， but they're really quite hot now in their applications。

So Rige regression， well let's first of all， just remind ourselves what least squares is。



![](img/2beab32f0a7a882b1b6e1154ba206066_2.png)

The training error。嗯。

![](img/2beab32f0a7a882b1b6e1154ba206066_4.png)

So RSS or training error is the sum squares deviation between y and the predictions。



![](img/2beab32f0a7a882b1b6e1154ba206066_6.png)

So when you do these squares， we simply find the coefficients that make this as small as possible。



![](img/2beab32f0a7a882b1b6e1154ba206066_8.png)

Now。With rich regression， we're going to do something a little bit different。

 We're going to use training error RS。 we're going to add a penalty to that， namely。



![](img/2beab32f0a7a882b1b6e1154ba206066_10.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_11.png)

A tuning parameter， which we'll choose in some way， and you'll as you can guess。

 it we by cross foundation， times a sum of the squares of the coefficients。



![](img/2beab32f0a7a882b1b6e1154ba206066_13.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_14.png)

So we're going to try to make this total quantity small。

 which means we're going to try to make the fit good by making the RSS small。

 but at the same time we're going to have something which is going to pushes the other direction。

 this is going to penalize coefficients which get too large right the bigger the more non-zero coefficient is the larger this is。

 so we're going to pay a price for being non-zero。

![](img/2beab32f0a7a882b1b6e1154ba206066_16.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_17.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_18.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_19.png)

It we'll pay a bigger price that the larger the coefficients are。



![](img/2beab32f0a7a882b1b6e1154ba206066_21.png)

So it's basically fit versus the size of the coefficients。



![](img/2beab32f0a7a882b1b6e1154ba206066_23.png)

And that apparently is called a shrinkage。

![](img/2beab32f0a7a882b1b6e1154ba206066_25.png)

A shrinkage penalty because it's going to encourage。The parameters to be shrunk toward zero。

And the amount by which you're encouraged to be0 it will be determined by this tuning parameter lambda。



![](img/2beab32f0a7a882b1b6e1154ba206066_27.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_28.png)

If lambda 0， let's go back to this lambda 0， of course。

 we're just doing least squares right because this term will be zero， but the larger lambda is。



![](img/2beab32f0a7a882b1b6e1154ba206066_30.png)

This tuning parameter， the more and more of a price will pay for making these coefficients non zero。

 If you make Lada extremely large， then at some point the coefficients are going to be very close to 0 because they'll have to be close to0 to make this term small enough。

 right no matter how good they help to fit， we're going to pay a large price in。



![](img/2beab32f0a7a882b1b6e1154ba206066_32.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_33.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_34.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_35.png)

In pen in。In the penalty term。

![](img/2beab32f0a7a882b1b6e1154ba206066_37.png)

So in other words， this term has the effect of shrinking the coefficients towards zero and y zero。

 while zero is a natural value， member zero， of course， if a coefficient is zero。

 the feature is not appearing in the model。So。

![](img/2beab32f0a7a882b1b6e1154ba206066_39.png)

If we're going to shrink towards some value， a zero。Is a natural place to shrink towards。

And the2ning parametermeter。The size the swinging parameter。

 it trades off the fit versus the size of the coefficients。So as you can imagine。

 choosing good valueda for the team parameter Lada is critical and cross validation is what we're going to use for this。

So， let's see。

![](img/2beab32f0a7a882b1b6e1154ba206066_41.png)

What happens for the credit data？Well， let me just go back here。



![](img/2beab32f0a7a882b1b6e1154ba206066_43.png)

If we think of this for a fixed value of Lada， we have to find the smallest value of this criterion。

 and again， it's just an optimization problem with actually a very simple solution。



![](img/2beab32f0a7a882b1b6e1154ba206066_45.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_46.png)

And there are computer programs for doing that。 So I've view such a program。

 and we'll talk in the actually in the our session about。



![](img/2beab32f0a7a882b1b6e1154ba206066_48.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_49.png)

And R function root Ri regression。 but let's see what it looks like in this example in the credit example。

 So here we plot of the coefficients。

![](img/2beab32f0a7a882b1b6e1154ba206066_51.png)

Standardized coefficients versus Lambda。

![](img/2beab32f0a7a882b1b6e1154ba206066_53.png)

For the credit data and let's see what happens well first of all， on the left hand side。



![](img/2beab32f0a7a882b1b6e1154ba206066_55.png)

Lambda is close to zero， so there's almost no constraint in the coefficients。

 so here we're pretty much getting the full least squares estimates。



![](img/2beab32f0a7a882b1b6e1154ba206066_57.png)

And now as Lada gets larger， it's pushing the coefficients towards zero because we're paying more and more of a price for being non zero。



![](img/2beab32f0a7a882b1b6e1154ba206066_59.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_60.png)

In the extreme over here were lambdas maybe more than 10，000。

The local coefficients are all essentially zero。

![](img/2beab32f0a7a882b1b6e1154ba206066_62.png)

In between， they're shrunken towards 0 as lambda gets larger， although not not uniformly so。

 right like this the rating variable。

![](img/2beab32f0a7a882b1b6e1154ba206066_64.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_65.png)

It actually gets bigger for a while and then shrinks back down to zero。



![](img/2beab32f0a7a882b1b6e1154ba206066_67.png)

And I remember when I was a student seeing this figure again and again actually was in a class that Rob was teaching and being totally confused for like three lectures。

 so I just want to spare everyone this confusion in case anyone shares the confusion I had so like if we look here this red line indicates the spot at which lambda equals 100 and at that spot。

 the income coefficient takes on a value of like negative 100。



![](img/2beab32f0a7a882b1b6e1154ba206066_69.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_70.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_71.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_72.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_73.png)

These other six coefficients here are all around zero。 student takes on a value of around 100。



![](img/2beab32f0a7a882b1b6e1154ba206066_75.png)

Limit and rating take on values for around 250， and so the point is what we're plotting here is a ton of different models for a huge grid of lambda values and you just need to choose a value of lambda and then look at that vertical cross section。



![](img/2beab32f0a7a882b1b6e1154ba206066_77.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_78.png)

Good and so as Danielle said if we chose if I have lambda about was at 100。

 then it would it seems like it chooses about three nonzero coefficients， the black。

 the blue and the red oh maybe four and then these guys here are basically essentially zero the gray ones so they're not quite zero but they're small right exactly so an equivalent picture on the right now we've plotted the。



![](img/2beab32f0a7a882b1b6e1154ba206066_80.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_81.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_82.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_83.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_84.png)

The standard coefficients as a function of the。

![](img/2beab32f0a7a882b1b6e1154ba206066_86.png)

Of the。The L2 norm， the sums of the squares， the square root of the sum of the squares of the coefficients divided by that。



![](img/2beab32f0a7a882b1b6e1154ba206066_88.png)

The L2 norm of the fully square coefficient so Rob， what's the L2 norm？



![](img/2beab32f0a7a882b1b6e1154ba206066_90.png)

The L2 norm， so the L2 norm beta of the vector beta 1 through beta P。



![](img/2beab32f0a7a882b1b6e1154ba206066_92.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_93.png)

It's written this way。So they all too norm。

![](img/2beab32f0a7a882b1b6e1154ba206066_95.png)

So it's a square root of the sum。A beta2 squared。

![](img/2beab32f0a7a882b1b6e1154ba206066_97.png)

Right， so this is the。That's the L2 norm， and so its sentence。そ。That's it。

We see here when the L2 norm is0。 So when the coefficients are all 0， the L2 norm is 0。

 that corresponds to the。

![](img/2beab32f0a7a882b1b6e1154ba206066_99.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_100.png)

The right side of this picture， so the lamb is very large here。



![](img/2beab32f0a7a882b1b6e1154ba206066_102.png)

It's large enough that it's driven the L2 norm down almost to zero。

 so the coefficients are basically zero。

![](img/2beab32f0a7a882b1b6e1154ba206066_104.png)

And then on the right。Lambda is very small and we get the full e squares estimates。



![](img/2beab32f0a7a882b1b6e1154ba206066_106.png)

And in between， we get again a shrunken coefficient， so these two pixel are very the same。

 but they've been flipped from left to right。

![](img/2beab32f0a7a882b1b6e1154ba206066_108.png)

And the x axisxes are parameterized in a different way so Rob why does this x axis on the right hand side go from zero to one why does it end at one Oh because we just plotted this it ends at one because we're plotting as a function of this standardized L2 norm so at the right hand side。



![](img/2beab32f0a7a882b1b6e1154ba206066_110.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_111.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_112.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_113.png)

we have the full least squares estimates， so these numerator denometer are the same right so on the right hand side here on this right hand plot。

 lambda is zero and so your rid regression estimate is the same as your least squares estimate and so that ratio is just one。



![](img/2beab32f0a7a882b1b6e1154ba206066_115.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_116.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_117.png)

Exactly， okay。

![](img/2beab32f0a7a882b1b6e1154ba206066_119.png)

I think we've。I actually just said all this。Thanks for the questions from Daniela。



![](img/2beab32f0a7a882b1b6e1154ba206066_121.png)

Right so there's the L2 norm defined， I wrote it in the previous slide and that's what was used for the poly axis。



![](img/2beab32f0a7a882b1b6e1154ba206066_123.png)

One important point with Rige regression is that it matters whether you scale the variables or not now just remind you if you do do standard deviation squares。

 sustainabilityity squares is what called scale variant， if I multiply a feature by constant。

 it's not going to matter because I can divide the coefficient by the same constant and I get the same answer。

In least squares， the scaling of the variable doesn't matter。

 so whether I measure a length in feet or inches is not going to matter because the coefficient can just account for the change in units。

But it's a little bit subtle here now for Rige regression and penalized methods like Rige regression。

 the scaling does matter in an important way。And that's because we go back to the definition of Ri regression。

系。These coefficients are all put in a penalty together and they。



![](img/2beab32f0a7a882b1b6e1154ba206066_125.png)

There's a sum of square。 So if I change the units of one variable。

 it's going to change the scale of the coefficients well。



![](img/2beab32f0a7a882b1b6e1154ba206066_127.png)

If I change the units of one variable， the coefficient has to change to try to accommodate for that change。

 but it's competing against the coefficients for other features。



![](img/2beab32f0a7a882b1b6e1154ba206066_129.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_130.png)

Because they're all put together in a penalty in a sum。



![](img/2beab32f0a7a882b1b6e1154ba206066_132.png)

The scale of the features matters。And as a result。

![](img/2beab32f0a7a882b1b6e1154ba206066_134.png)

It's important to standardize the predictors in regression before applying wage regression。

 so in most cases。Before you do rigid regression， you want to standardize the variables。

 What does that mean to standardize the variables while you take the。

The variable are feature and you divide it by the standard deviation of that feature over all the observations。

And now the standard deviation of this guy is one。And you do that for each feature。

That makes the features comparable and makes their coefficients comparable。

So that's an example of Ri regression compared to least squares。

 here's a simulated example with 50 observations and 45 predictors in which all the predictors have been given non zero coefficients。



![](img/2beab32f0a7a882b1b6e1154ba206066_136.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_137.png)

So we see on the left， we see the。

![](img/2beab32f0a7a882b1b6e1154ba206066_139.png)

The bias in black， the variance in green and the test in purple for rigid regression is a function of lambda。



![](img/2beab32f0a7a882b1b6e1154ba206066_141.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_142.png)

And the same thing on the right as a function of the standardized coefficients sorry of the two norm。



![](img/2beab32f0a7a882b1b6e1154ba206066_144.png)

Of the rid regression divided by the twoome of full squares， so again。

 these are the same pictures essentially， but the x axis have been changed。



![](img/2beab32f0a7a882b1b6e1154ba206066_146.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_147.png)

Let's look over here， we can see that。嗯。What happens well the？



![](img/2beab32f0a7a882b1b6e1154ba206066_149.png)

The bias， as we move so fully squares is over here on the left， lambda is close to zero。



![](img/2beab32f0a7a882b1b6e1154ba206066_151.png)

As as you make lambda larger， the bias is pretty much unchanged， but the variance drops。



![](img/2beab32f0a7a882b1b6e1154ba206066_153.png)

So rigid regression by shrinking the coefficient towards zero controls the variance。

 it doesn't allow the coefficient to be too big。

![](img/2beab32f0a7a882b1b6e1154ba206066_155.png)

And it gets rewarded because the mean square error， which is the sum of these two， goes down。

So here's the， here's the place where the mean square is minimized。

 and it's lower than that for than the fully squared estimate。 So in this example。

 Rige regression has improved the error， the mean square error of。



![](img/2beab32f0a7a882b1b6e1154ba206066_157.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_158.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_159.png)

Fully squares by shrinking the coefficients。By a certain amount and we see the same thing in this picture and actually this u shaped curve that we see for the the mean square error in this figure in purple comes up again and again where when we're considering a bunch of different models that sort of have different levels of flexibility or complexity there's usually some sweet spot in the middle that has the smallest test error and that's really what we're going for so that's what's marked as an X in these two figures。



![](img/2beab32f0a7a882b1b6e1154ba206066_161.png)

So I want to go back to this picture of Ridge。Let me clear the。



![](img/2beab32f0a7a882b1b6e1154ba206066_163.png)

And one thing you might have noticed here that we mentioned is that the coefficients are never exactly zero。

 they're close to zero like here， these gray guys are all closer， but they。



![](img/2beab32f0a7a882b1b6e1154ba206066_165.png)

They're never exactly zero。 matter of fact， you can show mathematically that they're unless you're extremely lucky。

 you're not going to get a coefficient exactly of zero so read regression shrinks things in a continuous way toward zero but doesn't actually select variables by setting a coefficient equal to zero exactly but it seems like a opinionity in this example right because all those gray variables are so tiny it would just be more convenient if they were zero right which is a great setup for the next method。



![](img/2beab32f0a7a882b1b6e1154ba206066_167.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_168.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_169.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_170.png)

![](img/2beab32f0a7a882b1b6e1154ba206066_171.png)

Call the Lasso。