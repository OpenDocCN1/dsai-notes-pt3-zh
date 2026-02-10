# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P75：34_逻辑回归 第1部分.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

Hi and welcome to the lecture on generalized linear models for binary data in this lecture we're going to focus on instances where the outcome is a 01 random variable so it can only take two levels。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_1.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_2.png)

And this occurs very frequently in most analyses， for example， in biostatistics。

 we're often doing things like survival analysis where people are either alive or dead at the end of the study。

 for example， cancer study， we can look at winds versus losses like we're going to do today or successes or failures of any kind and our model is going to be we're going to model the data as if it's a bunch of coin flips。

 where the success probability。

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_4.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_5.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_6.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_7.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_8.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_9.png)

Potentially， it depends on a collection of covaris。Now。

 for if you have any collection of zeros and ones where the success probability is constant and they're independent。

 then the total number of successes or failures， it's a so calledled binomial random variable。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_11.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_12.png)

Okay so binomial random variable is binomial random variables are handled by binary logistic regression in the special case where the covariate is just constant okay so we're going to cover two cases。

 binary and binomial by covering the binary case。

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_14.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_15.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_16.png)

So as a motivating example， let's look at this data set that JeffL organized when JeffLak is another one of the instructors in our data science specialization he teaches the practical machine learning。

 getting and cleaning and data and the data scientist toolbox。

 so in this case we have you can get the data here， but it's also in the GitHub repository。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_18.png)

You the data here has the Ravens win number coded at ones versus zeros。

 whether or not the Ravens one coded as a factor variable wins versus loss the score raven score and the opponent score now in this case we're just going to look at to what extent the ravens score predicts whether or not they won okay so you can imagine if you were in the front office for the ravens who I。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_20.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_21.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_22.png)

Forgot to mention this the Ravens are a US American football NF National Football League team and based in Baltimore。

 so we all love the Ravens around here。

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_24.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_25.png)

So。You can imagine if you were in the front office for the Ravens wanting to predict wins with a lot of covariance。

 score would be one of them， opponent score would obviously be one of them and so on but you' want home versus a way。

 and I think you can understand the principles of binary logistic regression just by looking at this this example and I hope extending it given everything that we've learned about multivariate linear models will carry over very easily for you。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_27.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_28.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_29.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_30.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_31.png)

So I just want to remind ourselves， we don't probably don't want to fit this data with linear regression if we were to model the probability of a raven's win at the event of a raven's win one versus zero as a linear regression。

 we wouldn't be honoring this equation here wouldn't actually hold true for sure right。

 because usually we assume the errors or Gaussian。

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_33.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_34.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_35.png)

It just would not hold now that isn't to say that occasionally fitting binary data with a linear model is the worst thing in the world to do。

 but it's usually only a quick first thing that you do before you then move on to fit something like a logistic regression model。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_37.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_38.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_39.png)

So here we fit the linear regression in R and you get the output and you see what the model is trying to get at。

 the model is the slope is trying to get at the probability of a raven's win。

 however you can get slope estimates that are negative or above one if you fit a linear regression model again。

 it's not the worst thing in the world to do sometimes you if you're doing something of the quick you have to do it。

 but probably preferable would be to model the odds。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_41.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_42.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_43.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_44.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_45.png)

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_46.png)

So just to remind ourselves what the odds are， if we have a binary outcome。

 which in this case is the whether or not the Ravens win。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_48.png)

We want to model the probability that the ravens win， so I'm going to get my pen here。🤢。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_50.png)

The probability that the Ravens win so but it's going to be we're going to model it like it's a bunch of coin flips。

 however， the success probability will differ from game to game depending on how many points the Ravens scored。

Okay， so that's the probability we want to model so the odds。

The odds are defined as the probability over one minus the probability and in a couple of slides I'll describe more about the history of the odds and how people think about it。

You can go backwards by the way， from the odds to the probability in that the probability is equal to the odds over one plus the odds okay so you go forwards from the probability to the odds by taking the probability over one minus the probability。

 you can go backwards from the odds to get the probability by taking the odds over one plus the odds so the two things are exchangeable。

The log odds then is just the log of the odds， and we use that so commonly that we gave it a name and it's called the Loit。

So the logit is simply the log of the odds， so what we're going to do is put the model on the log of the odds。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_52.png)

So I think we've talked a lot about linear versus logistic regression。

 both in the last lecture and in this lecture describing what are some of the considerations for why we want to probably do this with logistic regression。

But the main thing is that the model assumptions clearly don't hold for linear regression。

 they're obviously the inferences probably are not anywhere near correct。Or we have no faith in them。

For but let's just draw the connection between the two so that we can。

Relate what we're doing in logistic regression back to what we did in linear regression so for linear regression we built models like this where the outcome was the intercept plus a slope parameter times the predictor plus an error term。

which is a nice way to write out the model in convenient。

 but another way to write out the same model was just to say that the expected value of the outcome was this linear relationship。

So。Instead of so the expected value of the outcome， in this case。

 the expected value is of a 01 random variable， the expected value of a 01 random variable is the probability。

 so the expected value of a fair coin is 0。5。So。Instead of doing what we do in linear regression。

 which is to model the expected value of the outcome directly on that scale。

 why don't we model the expected value of the outcome， which is the probability。

 why don't we model that with something like this， E to the linear regression over one plus e to the linear regression。

Well， this。Right here， this equation， if we invert it and if we。Go back。

 we work with it a little bit， we get that it says that the log of the odds is the linear regression relationship so what we're doing in binary generalized linear models is in this particular logistic regression。

We are taking a we're modeling our data as if it was a bunch of coin flips where the success probability changes with I。

And we're relating the coin， that success probability to our regressors by taking the log of the odds of that probability。

Associated with that probability。 so you can go backwards， This is the log of the odds。 Okay。

 you could go backwards。To the probability using this equation up here。

 and I like to call you E to the a over1 plus e to the a。

 this function that inverts the log of the odds。Back to the probability， I like to call it the exp。

 so the log of the odds is called the logit， I like to call the function that goes backwards the exp。

Okay， so that's all we're doing， that's all we're doing。

 but that's the clever bit of generalized linear models。

 we're not actually putting the model on the scale or we're not actually putting the linear regressions。

Pameters defining inequality between the outcomes and the linear regression parameters instead。

 we're saying that the outcome depends on a probability distribution。

 that probability distribution depends on the success probability， that success probability。

 then depends on the regressors。Okay。

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_54.png)

So interpreting logistic regression。Is。Pretty straightforward。

 and I should mention all the logs that we do in these notes， these are natural log， LOG。

 meaning natural log in this case， most mathematicians when they write LOG， they mean natural log。

So in this case。What happens， So if I plug， if I were to plug in。😡，A0。For the Raven score。

 I would just get beta B0。So B0 is the log odds of a raven's win if they score zero points。

E to the b0 over 1 plus e to the b0 would be the probability。

That the Ravens won the S the model based probability of the Ravens win if they score zero points。

 Now， in this case， this is maybe。呃呃。know， a not perfect component of this model because it gets estimated to be non zero and we know that the team can't win if they score zero points。

 they could tie， but they can't win。So B1， okay， so remember。Let me get。

Remember how we interpreted our slope coefficient from before， we have B0 plus B1。

 and let me put in the raven score。Plus， one。Okay， and subtract off B0 plus B1。

Times the Raven score by itself。Okay， and then when we put brackets around that， okay。

Then that equation， if you work it out。That equation works out to be B1。Okay， so what is this？

This is the Loit。Of the probability that the Ravens win， given the score plus one。

And this is the logit of the probability that the Ravens win， given the score itself。So what is B1？

It's the increase or decrease， depending on whether it's positive or negative。

In the log gods of the probability that the Ravens win。

Associated with a one unit increase in the regression variable。

 or in this case a one point increase in score。Okay。And if we expentiate this。

 remember that if this is a difference on the log scale， so if we expentiate it。

 we get a ratio back on the original scale， so if we expentiate this。

 we get that E to the B1 is then the ratio of the odds comparing。

One unit a one point increase in score the ratio of the odds of the ravens winning for a one point score increase Okay。

 so and we don't have multiple regressors like we。Studdiied a lot in linear regression we don't have that for this particular example。

 but the extension is pretty direct everything just like in linear regression multivariable regression everything is just interpreted presuming the other regressionors are held fixed so remember our interpretation and multivariable regression was that。

The increase associated with the one unit change in the regressionor holding the other regression variables fixed。

 that same interpretation carries over in logistic regression E to the B1。

 if we had a bunch of other covariates added in this。

 let's say whether or not it was a home or a away game， if we had that one extra covariate added。

 then，E to the B1 would be the odds ratio for a one unit increase in score。

 the odds ratio of a ravens win for a one unit increase in the score。

Holding whether or not it was in a way or a home being fixed。



![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_56.png)

Okay， so。Logistic regression coefficients are pretty easily interpretable。

 the log is a nice function that allows us to sort of invert additive things and turn them into ratios and people like the tokins in terms of ratios。

 so it's a very nice interpretation。

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_58.png)

I want to talk a minute about the history of odds。So and it goes back to this idea of a fair game。

 so imagine if you're playing a game where if you flip a coin with success probably P。

And if it comes up heads， you win X dollars， and if it comes up tails。

 the person you're playing against wins Y dollars and you lose Y dollars， okay？

So what should we set X and Y in order for the game to be fair？Okay， where in this case。

 the coin isn't necessarily a fair coin。P is not necessarily 0。5。So what is your expected earnings。

 well， if you took the inference class， you would know that your expected earnings is how much you would win。

How much you would win， given the coin came up heads minus。How much you would lose？

If the coin plus given the coin came up tails， okay， and if we want it to be a fair game。

 we want our expected earnings to be equal to zero。Well， if we solve that。

 we get y over x equals p over 1 minus p。So in other words。

 the odds can be said is how much you'd be willing to pay for a P probability of winning a dollar。

Where， you know in other words。X setting x equal to1。And then if P is bigger than 0。5。

 you'll have to pay more than you lose and P is less than 0。5。

 youd have to more than you pay less than if you lose than if you win。

And so this is why if you go to the， a betting horse horse track like Pimliccoat here in Baltimore。

They'll give you the odds against a horse winning， so they'll say 10 to one。Why would they do that？

Because if you bet a dollar， that would mean if the horse won。

 you got $10 so you can do the calculation very quickly in your head because they're giving you fair gain。

And some interesting side notes about the horse betting analogy in that。

The way in which they set the probabilities for horse betting is they do it in a way adaptively as the bets come in。

 if more people bet on a horse， the probability of it。

 that their odds that they say that it's going to win goes up。

 the odds that they say it's going to lose goes down is more people bet on it。

And they do it that way， not because they think it's an accurate reflection of whether or not the horse will win。

 but just to balance the actual money coming in and out so that if that horse wins or loses。

 they know exactly how much they would win or lose and they can balance it out that way so they are guaranteed to neither win nor lose money。

So， but what's interesting about that is over a long period of looking at horses that。Agreggate。

Ods that winds up from the betting， that winds up being a fairly accurate representation of the percentage of times the horse wins。

Which is interesting that just says that people are somehow wise as a collective and they create an efficient fair market for gambling by virtue of betting correctly in aggregate。

And also I would say know， so you might wonder how the casino or how the track makes money。

 they make money by taking a little bit a fee for every bet and that's so they are basically guaranteed to win so when。

You knowThe phrase the House wins， is literally true。

 it means that the House is basically guaranteed to win。

 they set up the odds so that whether the horse wins or loses。

 they're monetarily neutral and they take a little money off of the each debtt that's an interesting fact and of course it's more complicated than that because you've got a big complex organization。

 thousands of people running so。Of course， it's far more complicated than that。

 but that's the gist of it。So if you want a good risk free predict position， you know。

 become a bookie。

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_60.png)

So next up I'm going to show us how to visualize fitting logistic regression curves using a computer experiment。

 so I look forward to seeing you in that lecture。

![](img/ebbfc8df46dec27b4c9cd55bdc056eaa_62.png)