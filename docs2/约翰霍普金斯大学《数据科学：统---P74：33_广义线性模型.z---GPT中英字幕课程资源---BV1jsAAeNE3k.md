# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P74：33_广义线性模型.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

Hi and welcome to the lecture on Generalized Linear models in this lecture we're going to change gears quite a bit and switch from linear additive response models to the much broader class of generalized linear models。

These models take care of some instances that linear models might struggle with。

 but maybe at the expense of some of the nicety and the mathematical neatness that exist for linear models。



![](img/dd9e617f7c9eede1b6ff088934156f23_1.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_2.png)

Before I begin talking about generalized linear models。

 I'd like to review a little bit about linear models and maybe some of their benefits and bad tough spots。



![](img/dd9e617f7c9eede1b6ff088934156f23_4.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_5.png)

So。To me， the linear model is the single most useful applied statistical technique。But again。

 they're not without their limitations。

![](img/dd9e617f7c9eede1b6ff088934156f23_7.png)

The assumption of addivity is one that is kind of hard to。Hard to apply when you have， for example。

 binary data， it's weird to think of binary data as being additive。

 that air structure would have to be kind of weird in that case。In addition。

 if your data is strictly positive， then having additive Gaussian errors presents a problem because that allows for positive mass on negative values now that may not be a problem and I often say that it's not a problem to have strictly positive data where the errors look Gaussian and there's just very low probability down towards negative values。

 that's often okay。

![](img/dd9e617f7c9eede1b6ff088934156f23_9.png)

嗯。But on the other hand， if the normal distribution is putting a lot of positive probability on negative values。

 even though you know your response has to be positive， then that's problematic for your model。



![](img/dd9e617f7c9eede1b6ff088934156f23_11.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_12.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_13.png)

On the other hand， you might try a transformation， a common transformation when your data。

 your outcome has to be strictly positive is to take the natural log of it。

 natural log is to me in my mind， perhaps the most interpretable transformation possible。

 putting that one to the side， lots of other transformations that are available to try to make our data more normal。



![](img/dd9e617f7c9eede1b6ff088934156f23_15.png)

s as for binomial data， people often will take a so called arcine square root transformation that often destroys a large amount of interpretability of our model coefficients。

 which is a real problem。

![](img/dd9e617f7c9eede1b6ff088934156f23_17.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_18.png)

The log transformation I would say， is in a class of its own and in many ways can make the coefficients more interpretable。

 so we'll discuss that separately。

![](img/dd9e617f7c9eede1b6ff088934156f23_20.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_21.png)

There's another reason to perhaps approach generalized linear models rather than doing a transformation of the outcome or to approximate things with a linear model is it's just nice and pleasant to have a model on the scale in which the data was recorded without having a transformation and that really honors the assumption the known assumptions about the data。

 so if we have binary data， a model that really honors the fact that the data is binary and really doesn't require us to transform it。

 it has a lot of kind of pleasantness to it and sort of makes a lot of internal sense。



![](img/dd9e617f7c9eede1b6ff088934156f23_23.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_24.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_25.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_26.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_27.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_28.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_29.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_30.png)

And then I mentioned here on this last point the natural log transformative transformation which is probably the most common transformation isn't applicable for negative or zero values now there's some fixes for that。

 but then that then harms a some of the nice properties of that transformation some of the really nice interpretable property so generalized linear models were from a 1972 paper by Neelder and Weburn。

 a kind of famous paper that if you are a PhD statistician you for certain red。



![](img/dd9e617f7c9eede1b6ff088934156f23_32.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_33.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_34.png)

And generalized linear model has three components， first of all， the。



![](img/dd9e617f7c9eede1b6ff088934156f23_36.png)

Distribution that describes the randomness has to come from a particular family of distributions called an exponential family this is a large family of distributions that includes things like the normal and the binomial and the Poisson。



![](img/dd9e617f7c9eede1b6ff088934156f23_38.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_39.png)

，So that's the random component right thats the exponential family is the random component then the systematic component is the so-called linear predictor。

 that's the part that we're modeling and we've done this very much so in linear models already。

 the random component was the errors， the systematic component was the linear component with the regression covariates and coefficients。



![](img/dd9e617f7c9eede1b6ff088934156f23_41.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_42.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_43.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_44.png)

And then we need some way to connect the to and the link function。

 it connects some important mean from the exponential family distribution to the linear predictors。

 so there's three things that we need， we need the distribution。

 which is going to be an exponential family for a generalized linear model。

 we need the systematic component which think of this as the linear predictor。

 we think of this as the set of regression regression variables and coefficients。



![](img/dd9e617f7c9eede1b6ff088934156f23_46.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_47.png)

And then we need a link function that links the tool， okay， so let's try an example。



![](img/dd9e617f7c9eede1b6ff088934156f23_49.png)

And we'll go to our most familiar example， which is linear models。

The subject that we've been covering the entire class up to this point。

 so in this case we're assuming that our Y is normal with a mean mui and variance sigma squared。

 and this happens to be an exponential family distribution。



![](img/dd9e617f7c9eede1b6ff088934156f23_51.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_52.png)

And then we're going to define the linear predictor。

 this ata I to be the collection of covariates x's times their coefficients beta。



![](img/dd9e617f7c9eede1b6ff088934156f23_54.png)

OkayAnd in this case， our link function is just going to be the identity link function。

 it just says that the mu from the normal distribution is exactly this collection。

 this sum of covariates and coefficients。

![](img/dd9e617f7c9eede1b6ff088934156f23_56.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_57.png)

And so this just leads the same model that we've been talking about all along。

 we could just write it instead as why YI is equal to the mu component which is summation Xi beta plus the error component。

 so weve simply written out the linear model in a separate way。

 we've talked about the fact instead of saying that the error is normally distributed。

 we say the y is normally distributed， which is a consequence of our other specification。

 we specify a linear predictor kind of separately。

![](img/dd9e617f7c9eede1b6ff088934156f23_59.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_60.png)

Okay， and then we just connect the mean from the normal distribution to the linear predictor and you might think this seems like a crazy thing to do when just writing it out as an additive sum with additive errors seems like such an easy thing to do。

 but as we move over to different settings like the plusisson in the binomial setting。

 it'll be quite a bit more apparent why we're doing this。



![](img/dd9e617f7c9eede1b6ff088934156f23_62.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_63.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_64.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_65.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_66.png)

So let's take， in my mind， perhaps the most useful variation of generalized linear models。

 logistic regression。So in this setting， we have data that are01， so binary。

And so it doesn't make a lot of sense to assume assume they come from a normal distribution。

 so the natural the only distribution available to us for coin flips for001 outcomes is the so calledled Bnoulli distribution。



![](img/dd9e617f7c9eede1b6ff088934156f23_68.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_69.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_70.png)

So we're going to assume that our data， our outcome wise。

 follow a Bnoulli distribution where the probability of a head or the so-called expected value of the y is mu I okay。

 so we're assuming these are we're modeling our data as if it's a bunch of coin flips。



![](img/dd9e617f7c9eede1b6ff088934156f23_72.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_73.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_74.png)

Only the probability of a head may switch from flip to flip and it's not necessarily 0。5 okay。

 so the probability is given by this parameter mu subi。



![](img/dd9e617f7c9eede1b6ff088934156f23_76.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_77.png)

The linear predictor is still the same， it's just the sum of the covariates times their coefficients。



![](img/dd9e617f7c9eede1b6ff088934156f23_79.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_80.png)

Now the link function in this case， the most famous and most common one is the so-called logistic link function or the log odds。

 and so in this case the way in which we're going to get from the mean from the probability of a head to the linear predictor is to take the log of the odds。

 so the odds are the probability over one minus the probability。

 so in this case we've written it as mu over one minus mu and we're going to take the natural logarith of it。



![](img/dd9e617f7c9eede1b6ff088934156f23_82.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_83.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_84.png)

So the logarithm， what that basically means。iss that we're going to transform our mean。

 our probability of getting ahead， we're going to transform it。

 and then on that transform scale is where the covariates and their coefficients。

 the kind of standard part of our linear model is going to appear。



![](img/dd9e617f7c9eede1b6ff088934156f23_86.png)

So notice we're transforming the mean of the distribution。

 we're not transforming the Ys themselves okay right that's a big distinction and that's the neat part of generalized linear models。

 what we're transform we're assuming that the coin has a probability of a head。

 we're modeling our data as if it's a coin， that coin has the probability of getting a ahead。



![](img/dd9e617f7c9eede1b6ff088934156f23_88.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_89.png)

And that probability， if we transform it in a specific way。

 then it relates to our covariates and coefficients。



![](img/dd9e617f7c9eede1b6ff088934156f23_91.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_92.png)

Okay， so we can go backwards from。The log odds to take to get back to the mean itself and so the inverse logit。

 I guess I often call that the x bit， though I don't know how standard that is is e to the a to I over1 plus e to the a I and that gets you back to mu so going forward it take log of mu over1 minus mu that gives us eta if we take e to the eta over1 plus e to the eta that gets us back to mu and by the way one minus mu。

 the probability of a tail is1 over e to the eta。

![](img/dd9e617f7c9eede1b6ff088934156f23_94.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_95.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_96.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_97.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_98.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_99.png)

So we could write out our likelihood as the binomial likelihood right there like this。

 and I think you can see then， well it's through this function through this likelihood like we've talked about in our stat inference class。

 it's through that likelihood that we're going to optimize。

 we're going to maximize that likelihood to obtain our parameter estimates。



![](img/dd9e617f7c9eede1b6ff088934156f23_101.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_102.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_103.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_104.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_105.png)

Okay， let's go through another example， Poisson regression， or I like to say Poisson regression。

 I know I'm not pronouncing it correctly， but I like to say it that way。



![](img/dd9e617f7c9eede1b6ff088934156f23_107.png)

So assume that y is Poson mu I where the mu I is the expected value of each of the Poson random variables in this case the mu has to be larger than zero。

 so the Poson is extremely useful for modeling count data or that's really what it's for is for modeling counts so if you have a bunch of positive counts that are unbounded。

 so not like binomial counts where they're bounded by the number of coin flips you take Poisson counts are unbounded。



![](img/dd9e617f7c9eede1b6ff088934156f23_109.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_110.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_111.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_112.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_113.png)

And so it's a very useful model let's suppose you want to count the number of people that shall put a bus stop。

 you don't have an upper limit on that， or sure there is some upper limit but you don't really know what it is。

 so you might want to model that as Poson。

![](img/dd9e617f7c9eede1b6ff088934156f23_115.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_116.png)

Our link function again is our linear predictor is again the same as it was in every case。

 it's just the sum of the covariates times their coefficients。



![](img/dd9e617f7c9eede1b6ff088934156f23_118.png)

The link function in this case is the log link， the most common link function for the Poson case is the log the log link so and remember。

 so we go from。The mean mu to the linear predictor eta by taking the log of the mean， okay。

 so again we're not logging the data， we're logging the mean from the distribution that the data is assumed to come from。



![](img/dd9e617f7c9eede1b6ff088934156f23_120.png)

And then remember the inverse of the natural logarithm is E to that thing。We can go backwards from。

Eta back to mu by taking e to the Eta， so by doing that we can just simply write out what our likelihood is and again the way GLMs work is they obtain the parameter estimates by maximizing the likelihood。



![](img/dd9e617f7c9eede1b6ff088934156f23_122.png)

So I give some technical facts here and it basically we're just saying that the likelihood simplifies quite a bit in all these cases because of the particular link function that we've shown。

 but I want to point out this final point here， which says that the maximum likelihood looks like a kind of least sort of like an equation that we would want to solve not unlike least squares。



![](img/dd9e617f7c9eede1b6ff088934156f23_124.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_125.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_126.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_127.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_128.png)

When we have- so think way back to our initial lectures on lease squares， we found our estimates。



![](img/dd9e617f7c9eede1b6ff088934156f23_130.png)

By minimizing sum of the squared vertical distances between the fitted line and the outcome。



![](img/dd9e617f7c9eede1b6ff088934156f23_132.png)

Well， if you wanted to。

![](img/dd9e617f7c9eede1b6ff088934156f23_134.png)

Opt to minimize that function in a。In a sort of automatic way。

 you might take a derivative so then that function would no longer be squared the two would come down and so you get to try to find the root of that derivative。

 you just get a linear equation。 Well， this generalization in generalized linear models by solving the likelihood trying to maximize the likelihood you get a very similar equation that you want to set equal to zero with solve that gives you your estimates。

 and I give it right here and it's basically not very similar to the linear model case only there's a set of weights and a variance in the denominator that kind of't that doesn't go away like it does in the least squares case。

 So again， this is not for this class it's just if you're interested in some of the details of the fitting Basically the point of this slide is to say that it's very similar to what's going on at least squares just how we get to that point is a little bit more circuitous。



![](img/dd9e617f7c9eede1b6ff088934156f23_136.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_137.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_138.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_139.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_140.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_141.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_142.png)

For most people in most settings。

![](img/dd9e617f7c9eede1b6ff088934156f23_144.png)

This is all going to be very transparent to you， you're going to mostly concern yourself with the interpretation of your generalized linear model。

 you're not going to concern yourself too much with how the specifics of how it was fit。



![](img/dd9e617f7c9eede1b6ff088934156f23_146.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_147.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_148.png)

There is an important point I'd like to note about generalized linear models。

 especially for some of the cases like the Poisson case and the binomial case。



![](img/dd9e617f7c9eede1b6ff088934156f23_150.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_151.png)

For the linear model， remember we had this assumption of a constant variance。



![](img/dd9e617f7c9eede1b6ff088934156f23_153.png)

However， for the Bernoulli case， remember the variance of a coin flip is p times1 minus p and in the notation we're giving here it's mu times1 minus mu。

 but remember our mu depends on I so what we're saying is the variance actually depends on which observation you're looking at the same unlike the linear model case where the variance is constant across I same thing in the Poisson case so the variance of a Poisson is its mean and so in this case the Poisson has a variance that differs by I now this is a modeling assumption that you can check right so if you have Poisson data。



![](img/dd9e617f7c9eede1b6ff088934156f23_155.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_156.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_157.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_158.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_159.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_160.png)

You can， let's say you have several poisonson observations at the same level of covariance so the mean should be the same。

 then the variances of those should be roughly equal to the mean and if your data doesn't exhibit that then that's a problem So this is a highly consistent this is an important consideration important practical consideration in generalized linear models is that the。



![](img/dd9e617f7c9eede1b6ff088934156f23_162.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_163.png)

The modeling assumptions often put a restriction on a relationship between the mean and the variance。

 and that relationship may not hold in your specific data set。



![](img/dd9e617f7c9eede1b6ff088934156f23_165.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_166.png)

So what can you do， well， there was a way to address this by having a more flexible variance model。

 even though you lose some of the assumptions of generalized linear models。



![](img/dd9e617f7c9eede1b6ff088934156f23_168.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_169.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_170.png)

And these are all standard options in R， and so all you look at are so called quasi。Blank。

Options in the family in the distribution so we're going to go through lots of examples。

 but the point is is that's so if you see an R that you see that you can fit a model that's Poisson with its GLM function。

 but then you see that there's another option called quasi Poson。The same thing with binomial。

 you see an option where you fit binomial， but then you see another option where it's quasi binomial。

 what that's referring to is a slightly more flexible variance model in case your data doesn't adhere to the GLN variant structure。



![](img/dd9e617f7c9eede1b6ff088934156f23_172.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_173.png)

Okay， and so these are all standard options in every statistical language that fits GLMs also automatically will fit these quasi versions of GLMs。



![](img/dd9e617f7c9eede1b6ff088934156f23_175.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_176.png)

With a more flexible variance structure。

![](img/dd9e617f7c9eede1b6ff088934156f23_178.png)

And I give here， I actually give the equation that it's trying to solve in order to get the fancier。

 more flexible variance structure。

![](img/dd9e617f7c9eede1b6ff088934156f23_180.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_181.png)

So just some odd ends about the fitting before we go through the specific cases we're going to do separately the Poson case and the binomial case。

 we're not going to go through a full treatment of GLMs， just Poson and binomial。



![](img/dd9e617f7c9eede1b6ff088934156f23_183.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_184.png)

But these equations have to be solved iteratively， so unlike the linear model where you can just do strict linear algebra to find solutions。

 GLMs actually have to be optimized， which means sometimes the program fails， for example。

 if you have a lot of zeros in a binary regression， or zeros are ones， these things can happen。



![](img/dd9e617f7c9eede1b6ff088934156f23_186.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_187.png)

But other than that， then I think most of the analysis should be pretty familiar to us if we want to get our predicted predicted response。

 we're just going to take our coefficients， our estimated coefficients beta hat。

 multiple them apply them our regressiongressors and that will give us our predicted response Now notice this is going to be on the logit scale if you're doing for example。

 logistic regression or the log scale if you're doing poisonson regression so you'll have to convert it back to the natural scale if you want it to be on the same scale as the original data so if you're modeling coin flips and you get your coefficients in your regression coefficients and out and you come up with predicted response。

 those will be on the logitt scale and if you want them to be back on the scale of the coin flip。

 the zero or1 between zero or1， you're going to need to take it inverse logit and again we're going to go through a lot of examples。

 I just want to outline these facts before we do the examples。



![](img/dd9e617f7c9eede1b6ff088934156f23_189.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_190.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_191.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_192.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_193.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_194.png)

The coefficients are interpreted very similarly to the way that our coefficients were interpreted in linear regression。

 they're the expected change in the change in the expected response per unit change in the regressors holding the other regressor' constant。

 the only difference is now this interpretation is done on the scale of the linear predictor so in the binomial case it's on the scale of the logit on the Poson case it's on the scale of the log mean and so on。

 so it's a slightly more complicated interpretation。

 but again we are gaining the benefit of modeling our data naturally on its own scale and we haven't had to transform the outcome at all。



![](img/dd9e617f7c9eede1b6ff088934156f23_196.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_197.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_198.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_199.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_200.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_201.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_202.png)

So the inference， we also lose the nice collection of closed form normal inferences that you get。

 we don't get t distributions anymore，'t and so but largely this is transparent there's a body of mathematics where statisticians and mathematicians have figured out what the right distributions are to compare all the coefficients from you the output of your GLM to in order to get things like the P values and all of those are going to be tested or hypothesis test for the coefficients are just going to be tested and interpreted in the same ways in our linear regression just the background that's going on is a little bit harder one thing I would say though is all of these results are based on asymptotics which means that they require larger sample sizes so if you have a GLM setting with a very small sample size then it's possible that things like your P values aren't really。



![](img/dd9e617f7c9eede1b6ff088934156f23_204.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_205.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_206.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_207.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_208.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_209.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_210.png)

![](img/dd9e617f7c9eede1b6ff088934156f23_211.png)

覚ぼ？

![](img/dd9e617f7c9eede1b6ff088934156f23_213.png)

And so many of the ideas can be brought over from GLM so this was just a whirlwind overview of GLMs now for the next two lectures。

 let's just dig into the two specific two most important cases of binomial in Bernoulli regression via logistic regression and Poson regression so we're going to do spend a lot of time with those and then if you want further material in GLMs there's some more advanced classes that you can take Okay well thank you for attending this lecture and I look forward to seeing in the next one where we're going to cover logistic regression for binary outcomes。



![](img/dd9e617f7c9eede1b6ff088934156f23_215.png)