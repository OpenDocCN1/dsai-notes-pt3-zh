# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P35：34_逻辑回归第1部分.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

![](img/def858b667944612733fbddb1e5f5b61_0.png)

Hi and welcome to the lecture on generalized linear models for binary data in this lecture。

 we're going to focus on instances where the outcome is a 01 random variable。

 so it can only take two levels。

![](img/def858b667944612733fbddb1e5f5b61_2.png)

![](img/def858b667944612733fbddb1e5f5b61_3.png)

And this occurs very frequently in most analyses， for example， in biostatistics。

 we're often doing things like survival analysis where people are either alive or dead at the end of the study。

 for example， cancer study， we can look at winds versus losses like we're going to do today or successes or failures of any kind and our model is going to be we're going to model the data as if it's a bunch of coin flips。

 where the success probability。

![](img/def858b667944612733fbddb1e5f5b61_5.png)

![](img/def858b667944612733fbddb1e5f5b61_6.png)

![](img/def858b667944612733fbddb1e5f5b61_7.png)

![](img/def858b667944612733fbddb1e5f5b61_8.png)

![](img/def858b667944612733fbddb1e5f5b61_9.png)

![](img/def858b667944612733fbddb1e5f5b61_10.png)

Potentially it depends on a collection of covariants。Now。

 for if you have any collection of zeros and ones where the success probability is constant and they're independent。

 then the total number of successes or failures， it's a so calledled binomial random variable。



![](img/def858b667944612733fbddb1e5f5b61_12.png)

![](img/def858b667944612733fbddb1e5f5b61_13.png)

![](img/def858b667944612733fbddb1e5f5b61_14.png)

Okay so binomial random variable is binomial random variables are handled by binary logistic regression in the special case where the covariate is just constant。

 okay， so we're going to cover two cases， binary and binomial by covering the binary case。



![](img/def858b667944612733fbddb1e5f5b61_16.png)

![](img/def858b667944612733fbddb1e5f5b61_17.png)

![](img/def858b667944612733fbddb1e5f5b61_18.png)

So as a motivating example， let's look at this data set that JeffL organized when JeffLak is another one of the instructors in our data science specialization he teaches the practical machine learning。

 getting and cleaning and data and the data scientist toolbox。

 so in this case we have you can get the data here， but it's also in the GitHub repository。



![](img/def858b667944612733fbddb1e5f5b61_20.png)

![](img/def858b667944612733fbddb1e5f5b61_21.png)

![](img/def858b667944612733fbddb1e5f5b61_22.png)

![](img/def858b667944612733fbddb1e5f5b61_23.png)

You can the data here has the Ravens win number coded at ones versus zeros。

 whether or not the Ravens one coded as a factor variable wins versus loss the score raven score and the opponent score now in this case we're just going to look at to what extent the ravens score predicts whether or not they won okay so you can imagine if you were in the front office for the ravens who。



![](img/def858b667944612733fbddb1e5f5b61_25.png)

![](img/def858b667944612733fbddb1e5f5b61_26.png)

![](img/def858b667944612733fbddb1e5f5b61_27.png)

![](img/def858b667944612733fbddb1e5f5b61_28.png)

![](img/def858b667944612733fbddb1e5f5b61_29.png)

Forgot to mention this， the Ravens are a US American football NF National Football League team and based in Baltimore。

 so we all love the Ravens around here。

![](img/def858b667944612733fbddb1e5f5b61_31.png)

![](img/def858b667944612733fbddb1e5f5b61_32.png)

So。You can imagine if you were in the front office for the Ravens wanting to predict wins with a lot of covariance。

 score would be one of them， opponent score would obviously be one of them and so on。

 but you' want home versus a away， and I think you can understand the principles of and binary logistic regression just by looking at this example and I hope extending it given everything that we've learned about multivariate linear models will carry over very easily for you。



![](img/def858b667944612733fbddb1e5f5b61_34.png)

![](img/def858b667944612733fbddb1e5f5b61_35.png)

![](img/def858b667944612733fbddb1e5f5b61_36.png)

![](img/def858b667944612733fbddb1e5f5b61_37.png)

![](img/def858b667944612733fbddb1e5f5b61_38.png)

![](img/def858b667944612733fbddb1e5f5b61_39.png)

So I just want to remind ourselves， we don't probably don't want to fit this data with linear regression if we were to model the probability of a raven's win as the event of a raven's win one versus zero as a linear regression。

 we wouldn't be honoring this equation here wouldn't actually hold true for sure， right。

 because usually we assume the errors or Gaussian。

![](img/def858b667944612733fbddb1e5f5b61_41.png)

![](img/def858b667944612733fbddb1e5f5b61_42.png)

![](img/def858b667944612733fbddb1e5f5b61_43.png)

![](img/def858b667944612733fbddb1e5f5b61_44.png)

It just would not hold now that isn't to say that occasionally fitting binary data with a linear model is the worst thing in the world to do。

 but it's usually only a quick first thing that you do before you then move on to fit something like a logistic regression model。



![](img/def858b667944612733fbddb1e5f5b61_46.png)

![](img/def858b667944612733fbddb1e5f5b61_47.png)

![](img/def858b667944612733fbddb1e5f5b61_48.png)

So here we fit the linear regression in R and you get the output and you see what the model is trying to get at。

 the model is the slope is trying to get at the probability of a raven's win。

 however you can get slope estimates that are negative or above one if you fit a linear regression model again。

 it's not the worst thing in the world to do sometimes you if you're doing something of the quick you have to do it。

 but probably preferable would be to model the odds。



![](img/def858b667944612733fbddb1e5f5b61_50.png)

![](img/def858b667944612733fbddb1e5f5b61_51.png)

![](img/def858b667944612733fbddb1e5f5b61_52.png)

![](img/def858b667944612733fbddb1e5f5b61_53.png)

![](img/def858b667944612733fbddb1e5f5b61_54.png)

![](img/def858b667944612733fbddb1e5f5b61_55.png)

So just to remind ourselves what the odds are， if we have a binary outcome which in this case is the whether or not the ravens win。

 we want to model the probability that the ravens win， so I'm going to get my pen here。



![](img/def858b667944612733fbddb1e5f5b61_57.png)

![](img/def858b667944612733fbddb1e5f5b61_58.png)

![](img/def858b667944612733fbddb1e5f5b61_59.png)

The probability that the Ravens win so but it's going to be we're going to model it like it's a bunch of coin flips。

 however the success probability will differ from game to game depending on how many points the Ravens scored okay so that's the probability we want to model so the odds。



![](img/def858b667944612733fbddb1e5f5b61_61.png)

![](img/def858b667944612733fbddb1e5f5b61_62.png)

![](img/def858b667944612733fbddb1e5f5b61_63.png)

![](img/def858b667944612733fbddb1e5f5b61_64.png)

The odds are defined as the probability over one minus the probability and in a couple of slides I'll describe more about the history of the odds and how people think about it。



![](img/def858b667944612733fbddb1e5f5b61_66.png)

![](img/def858b667944612733fbddb1e5f5b61_67.png)

You can go backwards by the way from the odds to the probability in that the probability is equal to the odds over one plus the odds okay so you go forwards from the probability to the odds by taking the probability over one minus the probability。

 you can go backwards from the odds to get the probability by taking the odds over one plus the odds。

 so the two things are exchangeable。

![](img/def858b667944612733fbddb1e5f5b61_69.png)

![](img/def858b667944612733fbddb1e5f5b61_70.png)

![](img/def858b667944612733fbddb1e5f5b61_71.png)

The log odds then is just the log of the odds， and we use that so commonly that we gave it a name and it's called the Loit。



![](img/def858b667944612733fbddb1e5f5b61_73.png)

So the logit is simply the log of the odds， so what we're going to do is put the model on the log of the odds。



![](img/def858b667944612733fbddb1e5f5b61_75.png)

![](img/def858b667944612733fbddb1e5f5b61_76.png)

So I think we've talked a lot about linear versus logistic regression。

 both in the last lecture and in this lecture describing what are some of the considerations for why we want to probably do this with logistic regression。



![](img/def858b667944612733fbddb1e5f5b61_78.png)

![](img/def858b667944612733fbddb1e5f5b61_79.png)

![](img/def858b667944612733fbddb1e5f5b61_80.png)

But the main thing is that the model assumptions clearly don't hold for linear regression。

 they're obviously the inferences probably are not anywhere near correct。



![](img/def858b667944612733fbddb1e5f5b61_82.png)

![](img/def858b667944612733fbddb1e5f5b61_83.png)

Or we have no faith in them。

![](img/def858b667944612733fbddb1e5f5b61_85.png)

For but let's just draw the connection between the two so that we can。



![](img/def858b667944612733fbddb1e5f5b61_87.png)

Relate what we're doing in logistic regression back to what we did in linear regression so for linear regression we built models like this where the outcome was the intercept plus a slope parameter times the predictor plus an error term。



![](img/def858b667944612733fbddb1e5f5b61_89.png)

![](img/def858b667944612733fbddb1e5f5b61_90.png)

![](img/def858b667944612733fbddb1e5f5b61_91.png)

which is a nice way to write out the model in convenient。

 but another way to write out the same model was just to say that the expected value of the outcome was this linear relationship。



![](img/def858b667944612733fbddb1e5f5b61_93.png)

![](img/def858b667944612733fbddb1e5f5b61_94.png)

So。Instead of so the expected value of the outcome， in this case。

 the expected value is of a 01 random variable， the expected value of a 01 random variable is the probability。

 so the expected value of a fair coin is 0。5。

![](img/def858b667944612733fbddb1e5f5b61_96.png)

![](img/def858b667944612733fbddb1e5f5b61_97.png)

So。

![](img/def858b667944612733fbddb1e5f5b61_99.png)

Instead of doing what we do in linear regression， which is to model the expected value of the outcome directly on that scale。

 why don't we model the expected value of the outcome， which is the probability。

 why don't we model that with something like this。

![](img/def858b667944612733fbddb1e5f5b61_101.png)

![](img/def858b667944612733fbddb1e5f5b61_102.png)

![](img/def858b667944612733fbddb1e5f5b61_103.png)

E to the linear regression over1 plus E to the linear regression。



![](img/def858b667944612733fbddb1e5f5b61_105.png)

Well， this。Right here， this equation， if we invert it and if we。



![](img/def858b667944612733fbddb1e5f5b61_107.png)

![](img/def858b667944612733fbddb1e5f5b61_108.png)

Go back， we work with it a little bit， we get that it says that the log of the odds is the linear regression relationship so what we're doing in binary generalized linear models is in this particular logistic regression。



![](img/def858b667944612733fbddb1e5f5b61_110.png)

![](img/def858b667944612733fbddb1e5f5b61_111.png)

We are taking a， we're modeling our data as if it was a bunch of coin flips where the success probability changes with I。



![](img/def858b667944612733fbddb1e5f5b61_113.png)

![](img/def858b667944612733fbddb1e5f5b61_114.png)

And we're relating the coin， that success probably to our regressors by taking the log of the odds of that probability。



![](img/def858b667944612733fbddb1e5f5b61_116.png)

![](img/def858b667944612733fbddb1e5f5b61_117.png)

![](img/def858b667944612733fbddb1e5f5b61_118.png)

associated with that probability so you can go backwards， this is the log of the odds。

 okay you could go backwards to the probability using this equation up here。

 and I like to call you know E to the a over1 plus e to the a this function that inverts the log of the odds。



![](img/def858b667944612733fbddb1e5f5b61_120.png)

![](img/def858b667944612733fbddb1e5f5b61_121.png)

![](img/def858b667944612733fbddb1e5f5b61_122.png)

![](img/def858b667944612733fbddb1e5f5b61_123.png)

Back to the probability， I like to call it the exp， so the log of the odds is called the logit。

 I like to call the function that goes backwards the exp。



![](img/def858b667944612733fbddb1e5f5b61_125.png)

![](img/def858b667944612733fbddb1e5f5b61_126.png)

Okay， so that's all we're doing， that's all we're doing。

 but that's the clever bit of generalized linear models。

 we're not actually putting the model on the scale or we're not actually putting the linear regressions。



![](img/def858b667944612733fbddb1e5f5b61_128.png)

Pameters defining inequality between the outcomes and the linear regression parameters instead we're saying that the outcome depends on a probability distribution。

 that probability distribution depends on the success probability， that success probability。

 then depends on the regressors。

![](img/def858b667944612733fbddb1e5f5b61_130.png)

![](img/def858b667944612733fbddb1e5f5b61_131.png)

![](img/def858b667944612733fbddb1e5f5b61_132.png)

![](img/def858b667944612733fbddb1e5f5b61_133.png)

Okay。

![](img/def858b667944612733fbddb1e5f5b61_135.png)

![](img/def858b667944612733fbddb1e5f5b61_136.png)

So interpreting logistic regression。

![](img/def858b667944612733fbddb1e5f5b61_138.png)

Is。Pretty straightforward， and I should mention all the logs that we do in these notes。

 these are natural log， LOG， meaning natural log in this case。

 most mathematicians when they write LOG， they mean natural log。



![](img/def858b667944612733fbddb1e5f5b61_140.png)

![](img/def858b667944612733fbddb1e5f5b61_141.png)

So in this case。What happens， So if I plug， if I were to plug in。😡。



![](img/def858b667944612733fbddb1e5f5b61_143.png)

A0。

![](img/def858b667944612733fbddb1e5f5b61_145.png)

For the Raven score， I would just get beta B0。So B0 is the log odds of a raven's win if they score zero points。



![](img/def858b667944612733fbddb1e5f5b61_147.png)

E to the b0 over 1 plus e to the b0 would be the probability。



![](img/def858b667944612733fbddb1e5f5b61_149.png)

That the Ravens won the as the model based probability of the Ravens win if they score zero points。

 Now， in this case， this is maybe。

![](img/def858b667944612733fbddb1e5f5b61_151.png)

![](img/def858b667944612733fbddb1e5f5b61_152.png)

呃呃。know， a not perfect component of this model because it gets estimated to be non zero and we know that the team can't win if they score zero points。

 they could tie， but they can't win。

![](img/def858b667944612733fbddb1e5f5b61_154.png)

![](img/def858b667944612733fbddb1e5f5b61_155.png)

So B1， okay， so remember。

![](img/def858b667944612733fbddb1e5f5b61_157.png)

Let me get。Remember how we interpreted our slope coefficient from before， we have B0 plus B1。

 and let me put in the raven score。

![](img/def858b667944612733fbddb1e5f5b61_159.png)

Plus one。Okay， and subtract off B0 plus B1。Times the Raven score by itself。Okay。

 and then let we put brackets around that， okay。

![](img/def858b667944612733fbddb1e5f5b61_161.png)

Then that equation， if you work it out。That equation works out to be B1。



![](img/def858b667944612733fbddb1e5f5b61_163.png)

Okay， so what is this？

![](img/def858b667944612733fbddb1e5f5b61_165.png)

This is the Loit。Of the probability that the Ravens win， given the score plus one。



![](img/def858b667944612733fbddb1e5f5b61_167.png)

And this is the logit of the probability that the Ravens win， given the score itself。



![](img/def858b667944612733fbddb1e5f5b61_169.png)

So what is B1？

![](img/def858b667944612733fbddb1e5f5b61_171.png)

It's the increase or decrease depending on whether it's positive or negative。



![](img/def858b667944612733fbddb1e5f5b61_173.png)

In the log gods of the probability that the Ravens win。



![](img/def858b667944612733fbddb1e5f5b61_175.png)

Associated with a one unit increase in the regression variable。

 or in this case a one point increase in score。

![](img/def858b667944612733fbddb1e5f5b61_177.png)

Okay。And if we expentiate this， remember that if this is a difference on the log scale。

 so if we expentiate it， we get a ratio back on the original scale， so if we expentiate this。

 we get that E E to the B1 is then the ratio of the odds comparing。



![](img/def858b667944612733fbddb1e5f5b61_179.png)

![](img/def858b667944612733fbddb1e5f5b61_180.png)

![](img/def858b667944612733fbddb1e5f5b61_181.png)

One unit a one point increase in score the ratio of the odds of the ravens winning for a one point score increase okay。

 so and we don't have multiple regressors like we。

![](img/def858b667944612733fbddb1e5f5b61_183.png)

![](img/def858b667944612733fbddb1e5f5b61_184.png)

Studied a lot in linear regression we don't have that for this particular example。

 but the extension is pretty direct everything just like in linear regression multivariable regression everything is just interpreted presuming the other regressionors are held fixed so remember our interpretation and multivariable regression was that。



![](img/def858b667944612733fbddb1e5f5b61_186.png)

![](img/def858b667944612733fbddb1e5f5b61_187.png)

![](img/def858b667944612733fbddb1e5f5b61_188.png)

![](img/def858b667944612733fbddb1e5f5b61_189.png)

![](img/def858b667944612733fbddb1e5f5b61_190.png)

The increase associated with the one unit change in the regression are holding the other regression variables fixed。

 that same interpretation carries over in logistic regression E to the B1。

 if we had a bunch of other covariates added in this let's say whether or not it was a home or a away game。

 if we had that one extra covariate added， then。

![](img/def858b667944612733fbddb1e5f5b61_192.png)

![](img/def858b667944612733fbddb1e5f5b61_193.png)

![](img/def858b667944612733fbddb1e5f5b61_194.png)

![](img/def858b667944612733fbddb1e5f5b61_195.png)

![](img/def858b667944612733fbddb1e5f5b61_196.png)

E to the B1 would be the odds ratio for a one unit increase in score。

 the odds ratio of a ravens win for a one unit increase in the score。



![](img/def858b667944612733fbddb1e5f5b61_198.png)

![](img/def858b667944612733fbddb1e5f5b61_199.png)

Holding whether or not it was in a way or a home game fixed。



![](img/def858b667944612733fbddb1e5f5b61_201.png)

Okay， so。Logistic regression coefficients are pretty easily interpretable。

 the log is a nice function that allows us to sort of invert additive things and turn them into ratios and people like the tokins in terms of ratios。

 so it's a very nice interpretation。

![](img/def858b667944612733fbddb1e5f5b61_203.png)

![](img/def858b667944612733fbddb1e5f5b61_204.png)

![](img/def858b667944612733fbddb1e5f5b61_205.png)

I want to talk a minute about the history of odds。So and it goes back to this idea of a fair game。

 so imagine if you're playing a game where if you flip a coin with success probably P。



![](img/def858b667944612733fbddb1e5f5b61_207.png)

![](img/def858b667944612733fbddb1e5f5b61_208.png)

And if it comes up heads， you win x dollars， and if it comes up tails。

 the person you're playing against wins Y dollars and you lose Y dollars， okay？



![](img/def858b667944612733fbddb1e5f5b61_210.png)

![](img/def858b667944612733fbddb1e5f5b61_211.png)

So what should we set X and Y in order for the game to be fair？



![](img/def858b667944612733fbddb1e5f5b61_213.png)

Okay， where in this case， the coin isn't necessarily a fair coinist。P is not necessarily 0。5。

So what is your expected earnings well if you took the inference class。

 you would know that your expected earnings is how much you would win。How much you would win。

 given the coin came up heads minus。How much you would lose？



![](img/def858b667944612733fbddb1e5f5b61_215.png)

If the coin plus given the coin came up tails， okay， and if we want it to be a fair game。

 we want our expected earnings to be equal to zero。Well， if we solve that。

 we get y over x equals p over 1 minus p。So in other words。

 the odds can be said is how much you'd be willing to pay for a P probability of winning a dollar。



![](img/def858b667944612733fbddb1e5f5b61_217.png)

Where in other words， setting x equal to1。And then if P is bigger than 0。5。

 you'll have to pay more than you lose and P is less than 0。5。

 you'd have to more than you pay less than if you lose than if you win。



![](img/def858b667944612733fbddb1e5f5b61_219.png)

![](img/def858b667944612733fbddb1e5f5b61_220.png)

And so this is why if you go to the， a betting horse horse track like Pimliccoat here in Baltimore。



![](img/def858b667944612733fbddb1e5f5b61_222.png)

They'll give you the odds against a horse winning， so they'll say 10 to one。



![](img/def858b667944612733fbddb1e5f5b61_224.png)

Why would they do that？Because if you bet a dollar， that would mean if the horse won。

 you got $10 so you can do the calculation very quickly in your head because they're giving you fair gain。



![](img/def858b667944612733fbddb1e5f5b61_226.png)

And some interesting side about the horse betting analogy in that。



![](img/def858b667944612733fbddb1e5f5b61_228.png)

The way in which they set the probabilities for horse betting is they do it in a way adaptively as the bets come in。

 if more people bet on a horse， the probability of it。

 that their odds that they say that it's going to win goes up。

 the odds that they say it's going to lose goes down is more people bet on it。



![](img/def858b667944612733fbddb1e5f5b61_230.png)

And they do it that way， not because they think it's an accurate reflection of whether or not the horse will win。

 but just to balance the actual money coming in and out so that if that horse wins or loses。

 they know exactly how much they would win or lose and they can balance it out that way so they are guaranteed to neither win nor lose money。



![](img/def858b667944612733fbddb1e5f5b61_232.png)

So， but what's interesting about that is over a long period of looking at horses that。



![](img/def858b667944612733fbddb1e5f5b61_234.png)

Agreggate。Ods that winds up from the betting， that winds up being a fairly accurate representation of the percentage of times the horse wins。



![](img/def858b667944612733fbddb1e5f5b61_236.png)

![](img/def858b667944612733fbddb1e5f5b61_237.png)

Which is interesting， that just says that people are somehow wise as a collective and they create an efficient fair market for gambling by virtue of betting correctly in aggregate。



![](img/def858b667944612733fbddb1e5f5b61_239.png)

![](img/def858b667944612733fbddb1e5f5b61_240.png)

![](img/def858b667944612733fbddb1e5f5b61_241.png)

And also I would say， know so you might wonder how the casino or how the track makes money。

 they make money by taking a little bit a fee for every bet and that's so they are basically guaranteed to win so when。



![](img/def858b667944612733fbddb1e5f5b61_243.png)

![](img/def858b667944612733fbddb1e5f5b61_244.png)

You know the phrase the House wins， is literally true。

 it means that the House is basically guaranteed to win。

 they set up the odds so that whether the horse wins or loses。

 they're monetarily neutral and they take a little money off of the each bet that's an interesting fact and of course it's more complicated than that because you've got a big complex organization。

 thousands of people running so of course it's far more complicated than that but that's the gist of it。



![](img/def858b667944612733fbddb1e5f5b61_246.png)

![](img/def858b667944612733fbddb1e5f5b61_247.png)

![](img/def858b667944612733fbddb1e5f5b61_248.png)

![](img/def858b667944612733fbddb1e5f5b61_249.png)

![](img/def858b667944612733fbddb1e5f5b61_250.png)

![](img/def858b667944612733fbddb1e5f5b61_251.png)

So if you want a good risk free predict position， you know， become a bookie。



![](img/def858b667944612733fbddb1e5f5b61_253.png)

![](img/def858b667944612733fbddb1e5f5b61_254.png)

So next up， I'm going to show us how to visualize fitting logistic regression curves using a computer experiment。

 so I look forward to seeing you in that lecture。

![](img/def858b667944612733fbddb1e5f5b61_256.png)

![](img/def858b667944612733fbddb1e5f5b61_257.png)