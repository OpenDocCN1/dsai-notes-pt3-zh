# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P34：33_广义线性模型.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

Hi and welcome to the lecture on Generalized linear models In this lecture。

 we're going to change gears quite a bit and switch from linear additive response models to the much broader class of generalized linear models。



![](img/04c418ed7f4a37661a27e13d4e6aacab_1.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_2.png)

These models take care of some instances that linear models might struggle with。

 but maybe at the expense of some of the nicety and the mathematical neatness that exist for linear models。



![](img/04c418ed7f4a37661a27e13d4e6aacab_4.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_5.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_6.png)

Before I begin talking about generalized linear models。

 I'd like to review a little bit about linear models and maybe some of their benefits and bad tough spots。



![](img/04c418ed7f4a37661a27e13d4e6aacab_8.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_9.png)

So。To me， the linear model is the single most useful applied statistical technique。



![](img/04c418ed7f4a37661a27e13d4e6aacab_11.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_12.png)

But again， they're not without their limitations。The assumption of addivity is one that is kind of hard to。



![](img/04c418ed7f4a37661a27e13d4e6aacab_14.png)

Hard to apply when you have， for example， binary data。

 it's weird to think of binary data as being additive。

 that air structure would have to be kind of weird in that case。



![](img/04c418ed7f4a37661a27e13d4e6aacab_16.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_17.png)

In addition， if your data is strictly positive， then having additive Gaussian errors presents a problem because that allows for positive mass on negative values now that may not be a problem and I often say that it's not a problem to have strictly positive data where the errors look Gaussian and there's just very low probability down towards negative values。

 that's often okay。

![](img/04c418ed7f4a37661a27e13d4e6aacab_19.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_20.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_21.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_22.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_23.png)

嗯。But on the other hand， if the normal distribution is putting a lot of positive probability on negative values。

 even though you know your response has to be positive， then that's problematic for your model。



![](img/04c418ed7f4a37661a27e13d4e6aacab_25.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_26.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_27.png)

On the other hand， you might try transformation， a common transformation when your data。

 your outcome has to be strictly positive is to take the natural log of it。Natural log is， to me。

 in my mind， perhaps the most interpretable transformation possible， putting that one to the side。

 lots of other transformations that are available to try to make our data more normal。



![](img/04c418ed7f4a37661a27e13d4e6aacab_29.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_30.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_31.png)

s as for binomial data， people often will take a so called arcine square root transformation that often destroys a large amount of interpretability of our model coefficients。

 which is a real problem。

![](img/04c418ed7f4a37661a27e13d4e6aacab_33.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_34.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_35.png)

The log transformation I would say， is in a class of its own and in many ways can make the coefficients more interpretable。

 so we'll discuss that separately。

![](img/04c418ed7f4a37661a27e13d4e6aacab_37.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_38.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_39.png)

There's another reason to perhaps approach generalized linear models rather than doing a transformation of the outcome or to approximate things with a linear model is it's just nice and pleasant to have a model on the scale in which the data was recorded without having a transformation and that really honors assumption the known assumptions about the data。

 so if we have binary data， a model that really honors the fact that the data is binary and really doesn't require us to transform it。

 it has a lot of kind of pleasantness to it and sort of makes a lot of internal sense。



![](img/04c418ed7f4a37661a27e13d4e6aacab_41.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_42.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_43.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_44.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_45.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_46.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_47.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_48.png)

And then I mentioned here on this last point the natural log transformative transformation which is probably the most common transformation isn't applicable for negative or zero values now there's some fixes for that。

 but then that then harms a lot some of the nice properties of that transformation。

 some of the really nice interpretable property。

![](img/04c418ed7f4a37661a27e13d4e6aacab_50.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_51.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_52.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_53.png)

So generalized linear models were from a 1972 paper by Neder and Wederburn。

 a kind of famous paper that if you are a PhD statistician， you've for certain read。



![](img/04c418ed7f4a37661a27e13d4e6aacab_55.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_56.png)

And generalized linear model has three components， first of all， the。



![](img/04c418ed7f4a37661a27e13d4e6aacab_58.png)

Distribution that describes the randomness has to come from a particular family of distributions called an exponential family this is a large family of distributions that includes things like the normal and the binomial and the plusisson。



![](img/04c418ed7f4a37661a27e13d4e6aacab_60.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_61.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_62.png)

，So that's the random component right that's the exponential family is the random component。

 then the systematic component is the so-called linear predictor。

 that's the part that we're modeling and we've done this very much so in linear models already。

 the random component was the errorss， the systematic component was the linear component with the regression covariates and coefficients。



![](img/04c418ed7f4a37661a27e13d4e6aacab_64.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_65.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_66.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_67.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_68.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_69.png)

And then we need some way to connect the two and the link function。

 it connects some important mean from the exponential family distribution to the linear predictors。

 so there's three things that we need， we need the distribution。

 which is going to be an exponential family for a generalized linear model。

 we need the systematic component which think of this as the linear predictor。

 we think of this as the set of regression regression variables and coefficients。



![](img/04c418ed7f4a37661a27e13d4e6aacab_71.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_72.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_73.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_74.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_75.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_76.png)

And then we need a link function that links the two， okay， so let's try an example。



![](img/04c418ed7f4a37661a27e13d4e6aacab_78.png)

And we'll go to our most familiar example， which is linear models。



![](img/04c418ed7f4a37661a27e13d4e6aacab_80.png)

The subject that we've been covering the entire class up to this point， so in this case。

 we're assuming that our y is normal with a mean mui andvari sigma squared。

 and this happens to be an exponential family distribution。



![](img/04c418ed7f4a37661a27e13d4e6aacab_82.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_83.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_84.png)

And then we're going to define the linear predictor。

 this ata I to be the collection of covariates xs times their coefficients beta。



![](img/04c418ed7f4a37661a27e13d4e6aacab_86.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_87.png)

Okay and in this case， our link function is just going to be the identity link function。

 it just says that the mu from the normal distribution is exactly this collection。

 this sum of covariates and coefficients。

![](img/04c418ed7f4a37661a27e13d4e6aacab_89.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_90.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_91.png)

And so this just leads the same model that we've been talking about all along。

 we could just write it instead as why YI is equal to the mu component which is summation Xi beta plus the error component。

 so weve simply written out the linear model in a separate way。

 we've talked about the fact instead of saying that the error is normally distributed。

 we say the y is normally distributed， which is a consequence of our other specification。

 we specify a linear predictor kind of separately。

![](img/04c418ed7f4a37661a27e13d4e6aacab_93.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_94.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_95.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_96.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_97.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_98.png)

Okay， and then we just connect the mean from the normal distribution to the linear predictor and you might think this seems like a crazy thing to do when just writing it out as an additive sum with additive errors seems like such an easy thing to do。

 but as we move over to different settings like the plusson in the binomial setting。

 it'll be quite a bit more apparent why we're doing this。



![](img/04c418ed7f4a37661a27e13d4e6aacab_100.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_101.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_102.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_103.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_104.png)

So let's take， in my mind， perhaps the most useful variation of generalized linear models。

 logistic regression。

![](img/04c418ed7f4a37661a27e13d4e6aacab_106.png)

So in this setting we have data that are01， so binary。



![](img/04c418ed7f4a37661a27e13d4e6aacab_108.png)

And so it doesn't make a lot of sense to assume they come from a normal distribution。

 so natural the only distribution available to us for coin flips for zero1 outcomes is a so calledled Bnoulli distribution。



![](img/04c418ed7f4a37661a27e13d4e6aacab_110.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_111.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_112.png)

So we're going to assume that our data， our outcome wise。

 follow a Bnoulli distribution where the probability of a head or the so-called expected value of the y is mu I okay。

 so we're assuming these are we're modeling our data as if it's a bunch of coin flips。



![](img/04c418ed7f4a37661a27e13d4e6aacab_114.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_115.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_116.png)

Only the probability of a head may switch from flip to flip and it's not necessarily 0。5 okay。

 so the probability is given by this parameter mu subbi。



![](img/04c418ed7f4a37661a27e13d4e6aacab_118.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_119.png)

The linear predictor is still the same， it's just the sum of the covariates times their coefficients。



![](img/04c418ed7f4a37661a27e13d4e6aacab_121.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_122.png)

Now the link function in this case， the most famous and most common one is the so-called logistic link function or the log odds。

 and so in this case the way in which we're going to get from the mean from the probability of a head to the linear predictor is to take the log of the odds。

 so the odds are the probability over one minus the probability so in this case we've written it as mu over one minus mu and we're going to take the natural logarith of it。



![](img/04c418ed7f4a37661a27e13d4e6aacab_124.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_125.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_126.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_127.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_128.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_129.png)

So the logarithm， what that basically means。

![](img/04c418ed7f4a37661a27e13d4e6aacab_131.png)

iss that we're going to transform our mean， our probability of getting ahead。

 we're going to transform it， and then on that transform scale is where the covariates and their coefficients。

 the kind of standard part of our linear model is going to appear。



![](img/04c418ed7f4a37661a27e13d4e6aacab_133.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_134.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_135.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_136.png)

So notice we're transforming the mean of the distribution。

 we're not transforming the Ys themselves okay right that's a big distinction and that's the neat part of generalized linear models。

 what we're transforming we're assuming that the coin has a probability of a head。

 we're modeling our data as if it's a coin， that coin has the probability of getting ahead。



![](img/04c418ed7f4a37661a27e13d4e6aacab_138.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_139.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_140.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_141.png)

And that probability， if we transform it in a specific way。

 then it relates to our covariates and coefficients。



![](img/04c418ed7f4a37661a27e13d4e6aacab_143.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_144.png)

Okay， so we can go backwards from。

![](img/04c418ed7f4a37661a27e13d4e6aacab_146.png)

The log odds to take to get back to the mean itself and so the inverse logit。

 I guess I often call that the x bit， though I don't know how standard that is is e to the a to I over1 plus e to the a to I and that gets you back to mu so going forward it take log of mu over1 minus mu that gives us eta if we take e to the eta over1 plus e to the eta that gets us back to mu and by the way one minus mu the probability of a tail is1 over e to the eta。



![](img/04c418ed7f4a37661a27e13d4e6aacab_148.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_149.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_150.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_151.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_152.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_153.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_154.png)

So we could write out our likelihood as the binomial likelihood right there like this。

 and I think you can see then， well it's through this function。

 through this likelihood like we've talked about in our stat inference class。

 it's through that likelihood that we're going to optimize。

 we're going to maximize that likelihood to obtain our parameter estimates。



![](img/04c418ed7f4a37661a27e13d4e6aacab_156.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_157.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_158.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_159.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_160.png)

Okay， let's go through another example， Poisson regression， or I like to say Poisson regression。

 I know I'm not pronouncing it correctly， but I like to say it that way。



![](img/04c418ed7f4a37661a27e13d4e6aacab_162.png)

So assume that y is Poson mu I where the mu I is the expected value of each of the Poson random variables in this case the mu has to be larger than zero。

 so Poson is extremely useful for modeling count data or that's really what it's for is for modeling counts so if you have a bunch of positive counts that are unbounded right so not like binomial counts where theyre bounded by the number of coin flips you take Poisson counts are unbounded。



![](img/04c418ed7f4a37661a27e13d4e6aacab_164.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_165.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_166.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_167.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_168.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_169.png)

And so it's a very useful model let's suppose you want to count the number of people that show up at a bus stop。

 you don't have an upper limit on that or sure there is some upper limit but you don't really know what it is。

 so you might want to model that as Poson。

![](img/04c418ed7f4a37661a27e13d4e6aacab_171.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_172.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_173.png)

Our link function again is our linear predictor is again the same as it was in every case。

 it's just the sum of the covariates times their coefficients。



![](img/04c418ed7f4a37661a27e13d4e6aacab_175.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_176.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_177.png)

The link function in this case is the log link， the most common link function for the Poson case is the log the log link so and remember。

 so we go from。The mean mu to the linear predictor Eta by taking the log of the mean， okay。

 so again we're not logging the data， we're logging the mean from the distribution that the data is assumed to come from。

And then remember the inverse of the natural logarithm is E to that thing。We can go backwards from。

Eta back to mu by taking e to the Eta， so by doing that we can just simply write out what our likelihood is and again the way GLMs work is they obtain the parameter estimates by maximizing the likelihood。

So I give some technical facts here and it basically we're just saying that the likelihood simplifies quite a bit in all these cases because of the particular link function that we've shown。

 but I want to point out this final point here， which says that the maximum likelihood looks like a kind of least sort of like an equation that we would want to solve。

 not unlike least squares。

![](img/04c418ed7f4a37661a27e13d4e6aacab_179.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_180.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_181.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_182.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_183.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_184.png)

When we have so think way back to our initial lectures on lease squares， we found our estimates。



![](img/04c418ed7f4a37661a27e13d4e6aacab_186.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_187.png)

By minimizing sum of the squared vertical distances between the fitted line and the outcome。



![](img/04c418ed7f4a37661a27e13d4e6aacab_189.png)

Well， if you wanted to。

![](img/04c418ed7f4a37661a27e13d4e6aacab_191.png)

Opt to minimize that function in a。In a sort of automatic way you might take a derivative so then that function would no longer be squared the two would come down and so you get to try to find the root of that derivative。

 you just get a linear equation。 Well this generalization in generalize linear models by solving the likelihood trying to maximize the likelihood you get a very similar equation that you want to set equal to zero with solve that gives you your estimates and I give it right here and it's basically not very similar to the linear model case only there's a set of weights and a variance in the denominator that kind of that doesn't go away like it does in the least squares case So again。

 this is not for this class it's just if you're interested in some of the details of the fitting basically the point of this slide is to say that it's very similar to what's going on in least squares just how we get to that point is a little bit more circuitous。



![](img/04c418ed7f4a37661a27e13d4e6aacab_193.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_194.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_195.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_196.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_197.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_198.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_199.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_200.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_201.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_202.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_203.png)

For most people in most settings。

![](img/04c418ed7f4a37661a27e13d4e6aacab_205.png)

This is all going to be very transparent to you， you're going to mostly concern yourself with the interpretation of your generalized linear model。

 you're not going to concern yourself too much with how the specifics of how it was fit。



![](img/04c418ed7f4a37661a27e13d4e6aacab_207.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_208.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_209.png)

There is an important point I'd like to note about generalized linear models。

 especially for some of the cases like the Poisson case and the binomial case。



![](img/04c418ed7f4a37661a27e13d4e6aacab_211.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_212.png)

For the linear model， remember we had this assumption of a constant variance。



![](img/04c418ed7f4a37661a27e13d4e6aacab_214.png)

However， for the Bernoulli case， remember the variance of a coin flip is p times1 minus p and in the notation we're giving here it's mu times1 minus mu。

 but remember our mu depends on I so what we're saying is the variance actually depends on which observation you're looking at the same unlike the linear model case for the variance is constant across I same thing in the Poisson case so the variance of a Poisson is its mean and so in this case the Poisson has a variance that differs by I now this is a modeling assumption that you can check right so if you have Poisson data。



![](img/04c418ed7f4a37661a27e13d4e6aacab_216.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_217.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_218.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_219.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_220.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_221.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_222.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_223.png)

You can， let's say you have several poisonson observations at the same level of covariance so the mean should be the same。

 then the variance of those should be roughly equal to the mean and if your data doesn't exhibit that then that's a problem So this is a highly consistent this is an important consideration important practical consideration in generalized linear models is that the。



![](img/04c418ed7f4a37661a27e13d4e6aacab_225.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_226.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_227.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_228.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_229.png)

The modeling assumptions often put a restriction on a relationship between the mean and the variance。

 and that relationship may not hold in your specific data set。



![](img/04c418ed7f4a37661a27e13d4e6aacab_231.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_232.png)

So what can you do， well， there was a way to address this by having a more flexible variance model。

 even though you lose some of the assumptions of generalized linear models。



![](img/04c418ed7f4a37661a27e13d4e6aacab_234.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_235.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_236.png)

And these are all standard options in R， and so all you look at are so called quasi。



![](img/04c418ed7f4a37661a27e13d4e6aacab_238.png)

Blank。

![](img/04c418ed7f4a37661a27e13d4e6aacab_240.png)

Options in the family in the distribution so we're going to go through lots of examples。

 but the point is is that's so if you see an R that you see that you can fit a model that's Poson with its GLM function。

 but then you see that there's another option called quasi Poson。



![](img/04c418ed7f4a37661a27e13d4e6aacab_242.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_243.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_244.png)

The same thing with binomial， you can see an option where you fit binomial。

 but then you see another option where it's quasi binomial。

 what that's referring to is a slightly more flexible variance model in case your data doesn't adhere to the GLN variant structure。



![](img/04c418ed7f4a37661a27e13d4e6aacab_246.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_247.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_248.png)

Okay， and so these are all standard options and every statistical language that fits GLMs also automatically will fit these quasi versions of GLMs with a more flexible variance structure。



![](img/04c418ed7f4a37661a27e13d4e6aacab_250.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_251.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_252.png)

And I give here， I actually give the equation that it's trying to solve in order to get the fancier。

 more flexible variance structure。

![](img/04c418ed7f4a37661a27e13d4e6aacab_254.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_255.png)

So just some odds ends about the fitting before we go through specific cases we're going to do separately the Poson case and the binomial case we're not going to go through a full treatment of GLMs。

 just Poson and binomial。

![](img/04c418ed7f4a37661a27e13d4e6aacab_257.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_258.png)

But these equations have to be solved iteratively， so unlike the linear model where you can just do strict linear algebra to find solutions。

 GLMs actually have to be optimized， which means sometimes the program fails， for example。

 if you have a lot of zeros in a binary regression， or zeros are ones， these things can happen。



![](img/04c418ed7f4a37661a27e13d4e6aacab_260.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_261.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_262.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_263.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_264.png)

But other than that， then I think most of the analysis should be pretty familiar to us if we want to get our predicted predicted response。

 we're just going to take our coefficients， our estimated coefficients beta hat。

 multiple of them apply them times our regressors and that will give us our predicted response Now notice this is going to be on the logit scale if you're doing for example。

 logistic regression or the log scale if you're doing poisonson regression so you'll have to convert it back to the natural scale if you want it to be on the same scale as the original data so if you're modeling coin flips and you get your coefficients in your regression coefficients and out and you come up with predicted response。

 those will be on the logit scale and if you want them to be back on the scale of the coin flip the zero or1 between zero or1。

 you're going to need to take it inverse logit and again we're going to go through a lot of examples。

 I just want to outline these facts before we do the examples。



![](img/04c418ed7f4a37661a27e13d4e6aacab_266.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_267.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_268.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_269.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_270.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_271.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_272.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_273.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_274.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_275.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_276.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_277.png)

The coefficients are interpreted very similarly to the way that our coefficients were interpreted in linear regression。

 they're the expected change in the change in the expected response per unit change in the regressors holding the other regressor' constant。

 the only difference is now this interpretation is done on the scale of the linear predictor so in the binomial case it's on the scale of the logit on the Poson case it's on the scale of the log mean and so on。

 so it's a slightly more complicated interpretation but again we are gaining the benefit of modeling our data naturally on its own scale and we haven't had to transform the outcome at all。



![](img/04c418ed7f4a37661a27e13d4e6aacab_279.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_280.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_281.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_282.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_283.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_284.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_285.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_286.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_287.png)

So the inference， we also lose the nice collection of closed form normal inferences that you get。

 we don't get t distributions anymore，'t and so but largely this is transparent there's a body of mathematics where statisticians and mathematicians have figured out what the right distributions are to compare all the coefficients from the output of your GLM to in order to get things like the P values and all of those are going to be tested our hypothesis test for the coefficients are just going to be tested and interpreted in the same ways in our linear regression just the background that's going on is a little bit harder one thing I would say though is all of these results are based on asymptotics which means that they require larger sample sizes so if you have a GLM setting with a very small sample size then it's possible that things like your P values aren't really。



![](img/04c418ed7f4a37661a27e13d4e6aacab_289.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_290.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_291.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_292.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_293.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_294.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_295.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_296.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_297.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_298.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_299.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_300.png)

覚ぼ？

![](img/04c418ed7f4a37661a27e13d4e6aacab_302.png)

And so many of the ideas can be brought over from GLM so this was just a whirlwind overview of GLMs now for the next two lectures。

 let's just dig into the two specific two most important cases of binomial in Bernoulli regression via logistic regression and Poson regression so we're going to do spend a lot of time with those and then if you want further material in GLMs there's some more advanced classes that you can take okay well thank you for attending this lecture and I look forward to seeing you in the next one where we're going to cover logistic regression for binary outcomes。



![](img/04c418ed7f4a37661a27e13d4e6aacab_304.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_305.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_306.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_307.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_308.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_309.png)

![](img/04c418ed7f4a37661a27e13d4e6aacab_310.png)