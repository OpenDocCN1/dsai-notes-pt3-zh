# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P41：P41 StatsLearning Lect8k 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/becdb2ba4412fef65ccc1b32e9322a38_0.png)

So by far， the most famous dimension reduction approach is principal components regression。

And principal components regression involves。A two step procedure in step one。

 we find what are called principal components of the data matrix X。

And we're going to cover principal components in detail in chapter 10 of the textbook。

 and so I'm not going to cover that in great detail here。So in step one。

 we get principal components and then in step two， we're just going to perform least squares regression using those principal components as predictors。

😊，So basically， principal components are an interesting idea。

 and the first principal component is just the linear combination of the variables that has the highest variance。

The second principle component is the linear combination that has the largest variance。

Out of all linear combinations that are totally unrelated to the linear combination that we just got。

And so on， and so the principal components give us linear combinations or dimensions of the data that are really high in variances and that are uncorrelated to the ones that we previously got。

And so the idea is that if you give me a data with 35 variables。

 I can compute a few principal components and those might capture most of the variation in the data。

 but in a very succinct way， involving just a few new variables，1 through Z3A or Z1 through Z4。

So here's an example of principal components analysis on a very simple data set that we saw in chapter three already。



![](img/becdb2ba4412fef65ccc1b32e9322a38_2.png)

And so what we're showing here is a plot where the X axis shows population and the Y axis shows ad spending for 100 different cities。



![](img/becdb2ba4412fef65ccc1b32e9322a38_4.png)

And so those are these purple dots and so this is a simple data set with just p equals two variables and so I can say all right。

 what's the linear combination of these variables that has the most variance or equivalently what's the direction along which this data varies the most and so we can see that the direction in which the data varies the most it actually falls along this green line this is really the direction with variation in the data and so that's actually the first principal component direction。



![](img/becdb2ba4412fef65ccc1b32e9322a38_6.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_7.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_8.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_9.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_10.png)

And then if we say， hey， what's the direction along which the data varies the most out of all directions that are uncorrelated with that first direction。

 that's this blue dashed line here。

![](img/becdb2ba4412fef65ccc1b32e9322a38_12.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_13.png)

And so that's the second principle component in this data so in this example p equals two and there's only two principal components。

 but in general in a data set with lots of variables， if P is large。

 there's a lot of principal components and we can look at the first one or the second one or the third or the fourth。



![](img/becdb2ba4412fef65ccc1b32e9322a38_15.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_16.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_17.png)

And so on。So here's sort of a zoom in a little bit on what's happening here。

 and the idea is in this on the left hand side here。

 we just have about 20 locations shown as purple circles。



![](img/becdb2ba4412fef65ccc1b32e9322a38_19.png)

And the reason that this green line here is the first principle component is because it's the direction along which the data varies the most。

 It's the line such that。

![](img/becdb2ba4412fef65ccc1b32e9322a38_21.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_22.png)

That。

![](img/becdb2ba4412fef65ccc1b32e9322a38_24.png)

TheThe points are the most spread out possible along the line if I drop each point to oops。



![](img/becdb2ba4412fef65ccc1b32e9322a38_26.png)

If I drop each of these locations down to the line。

 then this sum of square distances is really as large as possible。



![](img/becdb2ba4412fef65ccc1b32e9322a38_28.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_29.png)

And so all these little red lines indicate the distance from a location to the principal component line it's actually as small as possible oops yeah this is the I misspoke this green line is the principal component and it's the direction along which the data varies the most and it's also the direction along which the distances from the purple points to the green line which I'm showing in red is as small as possible and on the right hand side here I'm really seeing the same picture again but now it's been rotated so that that principal component line is horizontal just to make it a little easier to see。



![](img/becdb2ba4412fef65ccc1b32e9322a38_31.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_32.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_33.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_34.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_35.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_36.png)

So if I want to understand these principal components better。

 I can actually plot each principal component， so each linear combination of the variables that I got on the X axis and I can plot it against population and against ad spending。



![](img/becdb2ba4412fef65ccc1b32e9322a38_38.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_39.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_40.png)

And what I can see is that the first principal component is really highly correlated with population and highly correlated with ad spending。



![](img/becdb2ba4412fef65ccc1b32e9322a38_42.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_43.png)

And so what that means is that I'm really summarizing the data very well if instead of using those original two variables。

 population and ad spending， I instead use just the first principal component。



![](img/becdb2ba4412fef65ccc1b32e9322a38_45.png)

So that kind of suggests the idea， hey， if I want to predict some response like sales。

 instead of using population and ad spending to predict sales。

 I can just use the first principal component， I can just treat that as a predictor in a model。

 fit the model using league squares， and I bet those results are going to be pretty good。



![](img/becdb2ba4412fef65ccc1b32e9322a38_47.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_48.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_49.png)

So now this figure is just like the previous one。

![](img/becdb2ba4412fef65ccc1b32e9322a38_51.png)

But instead of showing the first principal component on the X axis。

 it's showing the second principle component against again。

 population and a spending and we can see that there's very little relationship between population and the second principal component and between a spending and the second principal component。

 so that suggests they really the first principal component here does a great job of summarizing the data。

 in this case that's happened because population and a spending are really correlated with each other。

 and so one new variable which is the first principal component can really summarize both of those two variables very well。



![](img/becdb2ba4412fef65ccc1b32e9322a38_53.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_54.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_55.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_56.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_57.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_58.png)

So the idea is I take my data， I get the first couple principal components as many as I want。

 and I use those as predictors in a regression model that I fit using least squares。😊。

And that can actually， in a lot of settings， give really nice results。

So here's an example on a simulated data set。

![](img/becdb2ba4412fef65ccc1b32e9322a38_60.png)

Where I have a bunch of observations， and I perform principal components for regression with various numbers of principal components。



![](img/becdb2ba4412fef65ccc1b32e9322a38_62.png)

So like over here， I have one principal component all the way through to around 45 principal components in this example。



![](img/becdb2ba4412fef65ccc1b32e9322a38_64.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_65.png)

And so what I'm plotting here is the bias shown in black oops。



![](img/becdb2ba4412fef65ccc1b32e9322a38_67.png)

This is the bias。This is the variance in green， and this is the mean squared error。

And so as I get more and more components in my model， as I use more and more principal components。

 I'm going to get less and less bias because I'm going to be fitting a more and more complex mile。

 but I'm going to pay a price in that my variance is going to increase as the number of components increases。



![](img/becdb2ba4412fef65ccc1b32e9322a38_69.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_70.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_71.png)

And remember， the mean squared error is just the squared bias plus the variance。

 so my mean squared error， which is shown here in purple。

 has sort of approximately that u shape that we've been talking about。



![](img/becdb2ba4412fef65ccc1b32e9322a38_73.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_74.png)

And I can see that my mean squared error is really smallest for a model with around 18 principal components。

So using principal components regression with 18 predictors works really well here。

In this example over here， the situation is a little bit different。

 now my mean squared error once again decreases as I add more components。

 but it doesn't really increase again， it's pretty flat from around here outwards。



![](img/becdb2ba4412fef65ccc1b32e9322a38_76.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_77.png)

So any of these models looks around the same in terms of testamine squared error。

 and since I always prefer the simplest model possible in this context I might choose maybe this model with around 25 components So the idea is to summarize summarize the features by the principal components which are the combinations with highest variance。

 right？

![](img/becdb2ba4412fef65ccc1b32e9322a38_79.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_80.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_81.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_82.png)

I guess why is that a good idea or could it be a bad idea？



![](img/becdb2ba4412fef65ccc1b32e9322a38_84.png)

Yeah， so that's a good question and one thing that we notice here is that when I compute those principal components。

 I'm not actually looking at the response， I'm literally just looking at my predictors， my x's。

 and I'm looking for a linear combination of them that has high variance。



![](img/becdb2ba4412fef65ccc1b32e9322a38_86.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_87.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_88.png)

And it's kind of making this assumption that a linear combination of the predictors that has high variance is probably going to be associated with the response。



![](img/becdb2ba4412fef65ccc1b32e9322a38_90.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_91.png)

And that's kind of a hunch that we often have as statisticians it's an assumption that we often make。

 but really there's no reason that that has to be the case and in fact it might not be well let let me just just draw a picture talk about that a bit more for some space Okay so if we think of our。



![](img/becdb2ba4412fef65ccc1b32e9322a38_93.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_94.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_95.png)

I have a plot here says say there's two variables， right？



![](img/becdb2ba4412fef65ccc1b32e9322a38_97.png)

Here's my scatter plot of points in the first principal opponent's direction。



![](img/becdb2ba4412fef65ccc1b32e9322a38_99.png)

's going to be。Along this。

![](img/becdb2ba4412fef65ccc1b32e9322a38_101.png)

On this red line right that's the first principal component。

 so as Daniella said if we summarize these two variables by the principal component。

 we're really assuming that this direction of variation is the important one。



![](img/becdb2ba4412fef65ccc1b32e9322a38_103.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_104.png)

So if we think of why coming out out of the slide， we're really assuming that the regression plane varies along the red line and doesn't vary in the orthogonal direction right because if we choose one component。

 we're going to ignore the second direction。

![](img/becdb2ba4412fef65ccc1b32e9322a38_106.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_107.png)

Is that a good assumption， Well， it's not always going to be the case。

 but it tends to be quite reasonable because one way to think about it is if this is observational data。

 the fact that we've measured the variables at all。

 probably means that they could be they're likely to be important。

 we measure things in experiment to predict something。

 I think things we measure we're more likely to measure things which are important。

 so things that matter are probably going to vary in the direction of the response not always。

 but it's a good hunch that all else equal， let's look in the direction variation of the predictors to find the places where the response is most likely to vary。



![](img/becdb2ba4412fef65ccc1b32e9322a38_109.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_110.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_111.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_112.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_113.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_114.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_115.png)

Okay， so let's go back to。Are we talking about the number of directions， okay？



![](img/becdb2ba4412fef65ccc1b32e9322a38_117.png)

Yeah， so when we perform principal components regression。

 we need to somehow select the number of directions M and we just saw that you know the test mean squared error。

 we want it to be as small as possible， so we've got to estimate the test mean squared error and by now you've probably seen that Rob and I really prefer cross validationation over any other approach。

 so we would select we would suggest using cross validationidation in order to choose the number of principal component directions that you want to use。



![](img/becdb2ba4412fef65ccc1b32e9322a38_119.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_120.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_121.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_122.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_123.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_124.png)

So here that's what we did on the credit data。

![](img/becdb2ba4412fef65ccc1b32e9322a38_126.png)

So on the left hand side， we can just see the results of just performing just plain principal components regression on the data。

 so like for instance， if we want to look at the principal components regression model with six principal components。

 so m equals 6。

![](img/becdb2ba4412fef65ccc1b32e9322a38_128.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_129.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_130.png)

That's this blue line， and so we can see that like you know a few of these coefficients are non zero and then a few others are basically zero。



![](img/becdb2ba4412fef65ccc1b32e9322a38_132.png)

Over here we've got 11 components， and that's actually the full least squares model because when m equals P。

 you've just got regular least squares on the original data。



![](img/becdb2ba4412fef65ccc1b32e9322a38_134.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_135.png)

嗯。

![](img/becdb2ba4412fef65ccc1b32e9322a38_137.png)

And we can on the right hand side see for each of those same models。

 we can see the cross validated mean squared error， so this is an estimate of the test error。



![](img/becdb2ba4412fef65ccc1b32e9322a38_139.png)

And here we actually see something that's pretty disappointing remember we like to pick a model for which the mean squared error is as small as possible and so here the mean squared error is really as small as possible when we have a model with 10 or 11 components and remember when m equals 11 that is just going to be regular squares on the original data so basically principal components regression just tells us when you choose the number of components by。

😊。

![](img/becdb2ba4412fef65ccc1b32e9322a38_141.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_142.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_143.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_144.png)

Cross validationidation on this particular data， it tells us to just forget it and just do least squares on the original data。



![](img/becdb2ba4412fef65ccc1b32e9322a38_146.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_147.png)

So this is sort of disappointing， it means the principal components regression doesn't give us any gains over just plain leaf squares that you guys saw in chapter 3。



![](img/becdb2ba4412fef65ccc1b32e9322a38_149.png)

But this is also something that happens on a lot of contexts， you can try to beat least squares。

 but it might not work on a particular data set。😊。

![](img/becdb2ba4412fef65ccc1b32e9322a38_151.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_152.png)

So as Rob mentioned， with principal component regression。

 we're just coming up with these new transform variables。

 which were the principal components just in a totally unsupervised way。

 we're just looking at the x variables and we're just going to cross our fingers that the directions on which the x variables really vary a lot。

 are the same directions in which。

![](img/becdb2ba4412fef65ccc1b32e9322a38_154.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_155.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_156.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_157.png)

The variables are correlated with the response why。

 but if we don't want to just have to keep our fingers crossed and hope for the best。

 we can instead perform what's called partial least squares。



![](img/becdb2ba4412fef65ccc1b32e9322a38_159.png)

And partially squares is just like principal components regression。

 but it selects these new predictors z1 through Zm。😊，In a supervised way。



![](img/becdb2ba4412fef65ccc1b32e9322a38_161.png)

It's going to choose Z1 through ZM that are linear accommodation combinations with the original features。

 that are directions along which the original features vary a lot。

But there are also directions that are related to why。

So instead of just looking for a direction on which x varies。

 we're going to look for a direction on which x varies。That also has to be related to the response。

And so the goal here is to be able to more effectively predict the response because we explicitly think about the response when we're choosing these new features。

 Z1 through ZM。So the idea behind partial squares is。



![](img/becdb2ba4412fef65ccc1b32e9322a38_163.png)

I we get the first direction of partial least squares by doing a regression of y onto x1 that gives us phi11。

 we do a regression of y onto x2 that gives us phi12 and so on。

 until we do a regression of y onto XP and that gives us phi1p。And so in fact。

 the first principal component direction，1， the first partially squares direction that we get。

 Z1 is really proportional to the correlation between y and the data matrix x。



![](img/becdb2ba4412fef65ccc1b32e9322a38_165.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_166.png)

So that's how we get C1， and then we get the other partial least square its directions just by sort of iterating this procedure。



![](img/becdb2ba4412fef65ccc1b32e9322a38_168.png)

And so in principle， Pa least squares seems like it should be a huge gain over principal components regression because we're choosing those z's in such a clever way that actually involves looking at the response。

 which seems like it can only help us。

![](img/becdb2ba4412fef65ccc1b32e9322a38_170.png)

But in practice， we have found that partial least squares often does not give us a huge gain over principal components regression it's very similar to Rige regression and PCR principal components regression。

 so although some people do like partial least squares。

 I've never found it very useful and found that Ri。



![](img/becdb2ba4412fef65ccc1b32e9322a38_172.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_173.png)

Pri components regression is work as well and is simple both simpler and actually one thing that's interesting is Rob mentioned Rige regression and it might seem like you know going back Rige regression is really different from principal components regression and partial least squares。

 but it turns out that mathematically these ideas are all very closely related and principal components regression。

 for example， is kind of just a discrete version of Rige regression。

 Rige regression is kind of continuously shrinking variables whereas principal components is doing it in a more choppy sort of way exactly。



![](img/becdb2ba4412fef65ccc1b32e9322a38_175.png)

So we've covered a lot today。And now you've seen a lot of different model selection methods。😊。

Wwhich are really useful in settings where you might have a lot of observations。

 but you have a lot of variables， so you know if someone comes to you with some data with a million observations and four variables。

 then do least squares， knock yourself out or even use some of the approaches that you're going to see in chapter78 and9 which are even more flexible and more complex alternatives to least squares but if someone comes to you with data with know 400 observations and 300 variables or even 30。

000 variables you're going to need ways to simplify the problem and to fit really simple models that are even simpler than what least squares is going to give you and those are really some of the ideas that we covered today。



![](img/becdb2ba4412fef65ccc1b32e9322a38_177.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_178.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_179.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_180.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_181.png)

So this is a really exciting topic and a lot of modern statistical research really focuses on how we can improve prediction in settings like the ones we covered today where we just want a simple model that's simpler than least squares because the least squares fit is really going to overfit the data。



![](img/becdb2ba4412fef65ccc1b32e9322a38_183.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_184.png)

![](img/becdb2ba4412fef65ccc1b32e9322a38_185.png)