# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P15：P15 StatsLearning Lect6b 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

Okay， logistic regression。 So now we're going to get a little bit more mathhy。

Let's for short shorthand， write P of x for the probability that y is 1 given x。



![](img/8716f1943b52f5a942c66a122663311e_1.png)

![](img/8716f1943b52f5a942c66a122663311e_2.png)

And。And we're going to consider our simple model， a simple model for predicting default。 Yes or no。

 using balance， one of the variables。 So single variable。



![](img/8716f1943b52f5a942c66a122663311e_4.png)

![](img/8716f1943b52f5a942c66a122663311e_5.png)

So here's the form of logistic regression。

![](img/8716f1943b52f5a942c66a122663311e_7.png)

So that E is the， is the。

![](img/8716f1943b52f5a942c66a122663311e_9.png)

The， the scientific constant， the， the exponential value。



![](img/8716f1943b52f5a942c66a122663311e_11.png)

And we raise E to， to the power of a linear model。 We've got a beta 0， which is the intercept。

 and beta 1 is the coefficient of x。

![](img/8716f1943b52f5a942c66a122663311e_13.png)

![](img/8716f1943b52f5a942c66a122663311e_14.png)

And。You see that appears in the numerator and in the denominator。

 But there's one plus in the denominator。

![](img/8716f1943b52f5a942c66a122663311e_16.png)

So it's a somewhat complicated expression， but you can。



![](img/8716f1943b52f5a942c66a122663311e_18.png)

You can， you can see straight away that the values have to lie between 0 and one。



![](img/8716f1943b52f5a942c66a122663311e_20.png)

![](img/8716f1943b52f5a942c66a122663311e_21.png)

Because in the numerator， we eat anything is positive。



![](img/8716f1943b52f5a942c66a122663311e_23.png)

And。And the new and the denominator is bigger than the numerator。

 So it's always going to be bigger than 0。

![](img/8716f1943b52f5a942c66a122663311e_25.png)

![](img/8716f1943b52f5a942c66a122663311e_26.png)

And you can show that it's got to be less than one when， when beta 0 plus beta x gets very large。

 this approach is one。

![](img/8716f1943b52f5a942c66a122663311e_28.png)

So this is a special construct， a transformation of a linear model to guarantee that what we get out is a probability。

😊。

![](img/8716f1943b52f5a942c66a122663311e_30.png)

![](img/8716f1943b52f5a942c66a122663311e_31.png)

So that's called the logistic regression model。

![](img/8716f1943b52f5a942c66a122663311e_33.png)

And actually， the name logistic comes from the transformation of this model。

 So this called this is a monotone transformation。 We take log of P of x over 1 minus P of x。



![](img/8716f1943b52f5a942c66a122663311e_35.png)

![](img/8716f1943b52f5a942c66a122663311e_36.png)

And out pops our linear model。 And that transformation is called the log odds or the logit transformation of the probability。



![](img/8716f1943b52f5a942c66a122663311e_38.png)

And this is the model that we're gonna talk about right now。 to summarizemar。

 we've got a linear model stool。

![](img/8716f1943b52f5a942c66a122663311e_40.png)

![](img/8716f1943b52f5a942c66a122663311e_41.png)

But it's modeling the probabilities on a nonlinear scale。



![](img/8716f1943b52f5a942c66a122663311e_43.png)

And so back to our picture， again， there's the， the。

 the picture on the right was produced by a logistic regression model。 And。

 and that's why the probabilities lie between 0 and 1。



![](img/8716f1943b52f5a942c66a122663311e_45.png)

![](img/8716f1943b52f5a942c66a122663311e_46.png)

So。We've written down the model。 How do we estimate the model from。



![](img/8716f1943b52f5a942c66a122663311e_48.png)

From data。Well， the popular way is to use maximum likelihood。



![](img/8716f1943b52f5a942c66a122663311e_50.png)

Maximum likelihood was introduced by Huro。

![](img/8716f1943b52f5a942c66a122663311e_52.png)

Or me actually， this last week， did you reinvent it I didn't realize it was actually yeah。

 because the correct answer is Fisher back in the 1920s， Ronald Fisher， Fisher。



![](img/8716f1943b52f5a942c66a122663311e_54.png)

![](img/8716f1943b52f5a942c66a122663311e_55.png)

Ronald Fisher， a very famous statistician， invented a lot of the tools that we use in modern applied statistics。

 and maximum likelihood is one of them。

![](img/8716f1943b52f5a942c66a122663311e_57.png)

![](img/8716f1943b52f5a942c66a122663311e_58.png)

Well， the way maximum likelihood it works is you've got a data series of observed zeros and ones。



![](img/8716f1943b52f5a942c66a122663311e_60.png)

And you've got a model for the probabilities。 and that model involves parameters。 In this case。

 beta 0 and beta。

![](img/8716f1943b52f5a942c66a122663311e_62.png)

![](img/8716f1943b52f5a942c66a122663311e_63.png)

So for any values of the parameters， we can write down the probability of the observed data。



![](img/8716f1943b52f5a942c66a122663311e_65.png)

And since each observation is meant to be independent of each other one。

 the probability of the observed data is is is the probability of the observed string of zeros and ones。



![](img/8716f1943b52f5a942c66a122663311e_67.png)

![](img/8716f1943b52f5a942c66a122663311e_68.png)

So wherever we observed a1， we write down the probability of a 1， which is P of x。

 So if X I of observation， I was a1。

![](img/8716f1943b52f5a942c66a122663311e_70.png)

![](img/8716f1943b52f5a942c66a122663311e_71.png)

The probability is P of Xi。

![](img/8716f1943b52f5a942c66a122663311e_73.png)

And we write that down。And since they're all independent， we just multiply these probabilities。

 And these are the probabilities of a 0， which is  one minus the probability of a  one。



![](img/8716f1943b52f5a942c66a122663311e_75.png)

![](img/8716f1943b52f5a942c66a122663311e_76.png)

So this is the joint probability of the observed sequence of zeros and ones。



![](img/8716f1943b52f5a942c66a122663311e_78.png)

And of course， it involves the parameters。And so the idea of maximum likelihood is pick the parameters to make that probability as large as possible。

 because after all， you did observe the sequence of zeros and ones。



![](img/8716f1943b52f5a942c66a122663311e_80.png)

![](img/8716f1943b52f5a942c66a122663311e_81.png)

And so so that's the idea， simple to say， not always simple to execute。

 but luckily we have programs that can do this。 And， for example， in in R。

 we've got the GLM function， which in in a snap of a finger will fit this model for you and estimate the parameters。



![](img/8716f1943b52f5a942c66a122663311e_83.png)

![](img/8716f1943b52f5a942c66a122663311e_84.png)

![](img/8716f1943b52f5a942c66a122663311e_85.png)

![](img/8716f1943b52f5a942c66a122663311e_86.png)

And in this case， this is what it produced。

![](img/8716f1943b52f5a942c66a122663311e_88.png)

The coefficient estimates were -10 for the intercept and 000，5，5 for the slope for balance。

 That's beta and beta 0。

![](img/8716f1943b52f5a942c66a122663311e_90.png)

![](img/8716f1943b52f5a942c66a122663311e_91.png)

It also gives you this， So they're the coefficient estimates。

 It also gives you standard errors for each of the coefficient estimates。



![](img/8716f1943b52f5a942c66a122663311e_93.png)

It computess E statistic and it also gives you P values Oh I think I realized something。

 So you had a picture a couple slides ago of this the curve Yes。

 and is that how you found the it was wondering how you found the parameters for that curve。

 I that how you That's exactly right Rob。

![](img/8716f1943b52f5a942c66a122663311e_95.png)

![](img/8716f1943b52f5a942c66a122663311e_96.png)

![](img/8716f1943b52f5a942c66a122663311e_97.png)

So。

![](img/8716f1943b52f5a942c66a122663311e_99.png)

This curve over year。Is the curve corresponding to those estimates that we just produced in the table。



![](img/8716f1943b52f5a942c66a122663311e_101.png)

And you might be surprised because the slope is very smaller。



![](img/8716f1943b52f5a942c66a122663311e_103.png)

Rob。Yet it， it seemed to produce such a big change in the probabilities。



![](img/8716f1943b52f5a942c66a122663311e_105.png)

There may be a typo？I certainly hope not。

![](img/8716f1943b52f5a942c66a122663311e_107.png)

But let's， let's look a bit closer。 Look at the units of balance。



![](img/8716f1943b52f5a942c66a122663311e_109.png)

They in dollars， right， So we are $2000，$2500。

![](img/8716f1943b52f5a942c66a122663311e_111.png)

And so the values of the coefficients， which are going to multiply that balance variable。



![](img/8716f1943b52f5a942c66a122663311e_113.png)

They， they sort of take into account the units that are used， right。



![](img/8716f1943b52f5a942c66a122663311e_115.png)

So this， this is 0。0，05。

![](img/8716f1943b52f5a942c66a122663311e_117.png)

Per dollar。Right， but it would be 5 per thousand dollars。 right， So slopes。

 you have to take the units into account。

![](img/8716f1943b52f5a942c66a122663311e_119.png)

![](img/8716f1943b52f5a942c66a122663311e_120.png)

And so the Z statistic， which is a kind of standardized slope， does that。

 And then if we look at the P value， we see that the the chance that actually this。

 this balanced slope is 0 is very small， less than 0。001。 So both intercept and slope。

 strongly significant in this case。 How do I interpret that P value for the intercept。

 Do I care about that。

![](img/8716f1943b52f5a942c66a122663311e_122.png)

![](img/8716f1943b52f5a942c66a122663311e_123.png)

![](img/8716f1943b52f5a942c66a122663311e_124.png)

![](img/8716f1943b52f5a942c66a122663311e_125.png)

We usually don't care so much about the the P value for the intercept。



![](img/8716f1943b52f5a942c66a122663311e_127.png)

Yeah， the intercepts largely to do with， with the， the preponderance of， of zeros and ones in the。

 in the data set。

![](img/8716f1943b52f5a942c66a122663311e_129.png)

![](img/8716f1943b52f5a942c66a122663311e_130.png)

And， you know， and that's。And， and so that's of less importance。

 That's just inherent in the data set。 It's a slope。 that's really important。



![](img/8716f1943b52f5a942c66a122663311e_132.png)

What do we do with this model， We can predict probabilities。



![](img/8716f1943b52f5a942c66a122663311e_134.png)

And so let's suppose we take a person with a balance of $1000。



![](img/8716f1943b52f5a942c66a122663311e_136.png)

Well， we can estimate their probabilities。 so we just plug in the100 into this formula over year and notice I've put hats on beta 0 and beta 1 to indicate it that theyve now been estimated from the data。

 put a hat on the probability。

![](img/8716f1943b52f5a942c66a122663311e_138.png)

![](img/8716f1943b52f5a942c66a122663311e_139.png)

![](img/8716f1943b52f5a942c66a122663311e_140.png)

![](img/8716f1943b52f5a942c66a122663311e_141.png)

And yeah， we've plugged in the numbers and we use our calculator or computer and we get 0006。



![](img/8716f1943b52f5a942c66a122663311e_143.png)

So somebody with a balance of $10000 has a probability of 0。0，06 of default in。 in other words。

 pretty small。

![](img/8716f1943b52f5a942c66a122663311e_145.png)

![](img/8716f1943b52f5a942c66a122663311e_146.png)

What if they got a credit card balance of $2000。

![](img/8716f1943b52f5a942c66a122663311e_148.png)

That means they， they owe $2000 rather than $1000。 Well， if we go through the same procedure。

 now the probabilities jumped up to 0586。 So it's got much higher。



![](img/8716f1943b52f5a942c66a122663311e_150.png)

![](img/8716f1943b52f5a942c66a122663311e_151.png)

And you can imagine if we put in $3000， we'd get home higher。



![](img/8716f1943b52f5a942c66a122663311e_153.png)

Let's do this again， using some of the other variables。 We haven't seen students yet。

 but one of our predictors is student。 and it's a， it's a binary variable in this case。

 It's a yes or no variable is， is the， is the。

![](img/8716f1943b52f5a942c66a122663311e_155.png)

![](img/8716f1943b52f5a942c66a122663311e_156.png)

![](img/8716f1943b52f5a942c66a122663311e_157.png)

The credit card owner， a student or not。And so we code that as a 01 variable。

 and we fit a simple logistic regression model。 and it gets a。



![](img/8716f1943b52f5a942c66a122663311e_159.png)

![](img/8716f1943b52f5a942c66a122663311e_160.png)

Coe of 0。4049。

![](img/8716f1943b52f5a942c66a122663311e_162.png)

And that's also significant。Okay， let's do it again using the variable student as a predictor。

 This is a binary variable。 Is the， is the credit card holder student or not。



![](img/8716f1943b52f5a942c66a122663311e_164.png)

![](img/8716f1943b52f5a942c66a122663311e_165.png)

And we find we get a coefficient of 。4049 in this case， which is also significant。



![](img/8716f1943b52f5a942c66a122663311e_167.png)

So this is another variable in our database and just like before we can evaluate the probability of default is yes。

 given that the card old is a student， it comes out to 04。

04 and if theyre not a student it comes out to be a bit lower 0。029 close to 0。03。



![](img/8716f1943b52f5a942c66a122663311e_169.png)

![](img/8716f1943b52f5a942c66a122663311e_170.png)

![](img/8716f1943b52f5a942c66a122663311e_171.png)

![](img/8716f1943b52f5a942c66a122663311e_172.png)

And we're going to examine the the interactions between student and and balance and the other variables in a little while。



![](img/8716f1943b52f5a942c66a122663311e_174.png)

![](img/8716f1943b52f5a942c66a122663311e_175.png)