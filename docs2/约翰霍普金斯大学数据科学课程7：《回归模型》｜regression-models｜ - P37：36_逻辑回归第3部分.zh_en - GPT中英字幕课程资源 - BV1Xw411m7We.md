# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P37：36_逻辑回归第3部分.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

![](img/d40da7bb150e538827b082b65e7d30c3_0.png)

Okay， now that we've looked at fitting logistic regression curves。

 why don't we go ahead and see the output when we fit our ravens data？



![](img/d40da7bb150e538827b082b65e7d30c3_2.png)

So you fit the ravens data with the GLM function。

![](img/d40da7bb150e538827b082b65e7d30c3_4.png)

Here it operates just like the LN function， the outcome is on the left hand side of a tilde and then the predictor is on the right hand side in this case the only difference is now we have to specify family equals binomial and that's telling the GLN function that we have01 data if we had count data。

 the bounded count data， real binomial data then we would also have to give it a sample size also。



![](img/d40da7bb150e538827b082b65e7d30c3_6.png)

![](img/d40da7bb150e538827b082b65e7d30c3_7.png)

![](img/d40da7bb150e538827b082b65e7d30c3_8.png)

![](img/d40da7bb150e538827b082b65e7d30c3_9.png)

![](img/d40da7bb150e538827b082b65e7d30c3_10.png)

![](img/d40da7bb150e538827b082b65e7d30c3_11.png)

By default for the binomial and binary case， it's going to assume that the link function that you have is the logistic link function。

 which is what we want， so that's fine。

![](img/d40da7bb150e538827b082b65e7d30c3_13.png)

You see the output when you do summary summary works just like it did for LM。

 you see the output below you get the coefficients in this case negative 1。

68 and for the ravens coefficient 0。1 in this case on the Loit scale you want to look， for example。

 with the score variable， the raven score variable。

 you want to see whether or not the coefficient is close to 0 or not on the Loit scale on the expd scale you want to see whether or not it's close to1 then it gives it a standard error and a z value and a P value and we're going to interpret those just like we would in our linear model。

 though acknowledging that these are derived in a different way。



![](img/d40da7bb150e538827b082b65e7d30c3_15.png)

![](img/d40da7bb150e538827b082b65e7d30c3_16.png)

![](img/d40da7bb150e538827b082b65e7d30c3_17.png)

![](img/d40da7bb150e538827b082b65e7d30c3_18.png)

![](img/d40da7bb150e538827b082b65e7d30c3_19.png)

![](img/d40da7bb150e538827b082b65e7d30c3_20.png)

![](img/d40da7bb150e538827b082b65e7d30c3_21.png)

![](img/d40da7bb150e538827b082b65e7d30c3_22.png)

![](img/d40da7bb150e538827b082b65e7d30c3_23.png)

So here's the fitted curve the。

![](img/d40da7bb150e538827b082b65e7d30c3_25.png)

Predicted responses。

![](img/d40da7bb150e538827b082b65e7d30c3_27.png)

Put back on the probability scale。 So we plugged in so what our did is it plugged in the X values associated with the coefficient。

 so it took the scores。

![](img/d40da7bb150e538827b082b65e7d30c3_29.png)

![](img/d40da7bb150e538827b082b65e7d30c3_30.png)

Multipliied them times the coefficient for the scores。

 added the estimated intercept and then took E to that value over one plus E to that value。

 And that gives us the probabilities。 Now， this is this。

 this is only part of the fitted S curve because the。



![](img/d40da7bb150e538827b082b65e7d30c3_32.png)

![](img/d40da7bb150e538827b082b65e7d30c3_33.png)

![](img/d40da7bb150e538827b082b65e7d30c3_34.png)

![](img/d40da7bb150e538827b082b65e7d30c3_35.png)

The component of the S curve where the data actually are observed was restricted。

 so the S curve up here is one， so the S curve looks something like this。

 and then it would go down zero notice that this ends at 00。4 and not0。

 so that's the actual curve that it's fitting， though here on the fitted values we're only showing part of it。



![](img/d40da7bb150e538827b082b65e7d30c3_37.png)

![](img/d40da7bb150e538827b082b65e7d30c3_38.png)

![](img/d40da7bb150e538827b082b65e7d30c3_39.png)

![](img/d40da7bb150e538827b082b65e7d30c3_40.png)

![](img/d40da7bb150e538827b082b65e7d30c3_41.png)

If we were to expentiate the Ravens coefficients， we get 0。1864 for the intercept and 1。

1125 for the score， so that suggests an 11% increase in the probability of winning for every additional points that the ravens score okay that's how you would interpret it this。



![](img/d40da7bb150e538827b082b65e7d30c3_43.png)

![](img/d40da7bb150e538827b082b65e7d30c3_44.png)

![](img/d40da7bb150e538827b082b65e7d30c3_45.png)

![](img/d40da7bb150e538827b082b65e7d30c3_46.png)

![](img/d40da7bb150e538827b082b65e7d30c3_47.png)

Logistic regression coefficient， you can get confidence intervals。



![](img/d40da7bb150e538827b082b65e7d30c3_49.png)

For these these two coefficients very easily with the compf int operator so on the output from the fitted model we do compfant and then because most people myself included we prefer to look at these things on the expentiated scale you just expiate the two endpoints with the X function so what we see now is that our interval does contain one。

 it goes from 0。99 to 1。3 so it's saying that even though。



![](img/d40da7bb150e538827b082b65e7d30c3_51.png)

![](img/d40da7bb150e538827b082b65e7d30c3_52.png)

![](img/d40da7bb150e538827b082b65e7d30c3_53.png)

![](img/d40da7bb150e538827b082b65e7d30c3_54.png)

![](img/d40da7bb150e538827b082b65e7d30c3_55.png)

![](img/d40da7bb150e538827b082b65e7d30c3_56.png)

Even though we for sure know that scoring points is what causes the ravens to win the game。

 this coefficient turns out to not be significant。

![](img/d40da7bb150e538827b082b65e7d30c3_58.png)

![](img/d40da7bb150e538827b082b65e7d30c3_59.png)

The Inova function works just like it does in LM， you put the output of the fitted model。



![](img/d40da7bb150e538827b082b65e7d30c3_61.png)

![](img/d40da7bb150e538827b082b65e7d30c3_62.png)

And you can put multiple models in there， for example。

 nested models and Anovavo will give you a series of sequential tests and so here in this case the variable is for the score。



![](img/d40da7bb150e538827b082b65e7d30c3_64.png)

![](img/d40da7bb150e538827b082b65e7d30c3_65.png)

![](img/d40da7bb150e538827b082b65e7d30c3_66.png)

Just the one variable that we're kind of interested in， so it just has a one degree of freedom test。



![](img/d40da7bb150e538827b082b65e7d30c3_68.png)

This isn't that useful in this particular example， but if you had several models that you were interested in。

 you put them into the AOA function or I think also especially this is especially useful if you have a factor variable because sometimes you want the factor variable included or the factor variable。

 all levels of the factor variable removed and you might want to test whether or not that all levels of them are as a。



![](img/d40da7bb150e538827b082b65e7d30c3_70.png)

![](img/d40da7bb150e538827b082b65e7d30c3_71.png)

![](img/d40da7bb150e538827b082b65e7d30c3_72.png)

![](img/d40da7bb150e538827b082b65e7d30c3_73.png)

![](img/d40da7bb150e538827b082b65e7d30c3_74.png)

![](img/d40da7bb150e538827b082b65e7d30c3_75.png)

In total are necessary in the model。Notice that when you do summary and just get the coefficient table out from our that test each one of the levels of the factor independently and doesn't test them all as a whole。

 so something like the Anovo function is useful for putting a factor in and out of the model。



![](img/d40da7bb150e538827b082b65e7d30c3_77.png)

![](img/d40da7bb150e538827b082b65e7d30c3_78.png)

![](img/d40da7bb150e538827b082b65e7d30c3_79.png)

So for interpreting our odds ratios， remember that our odds ratios are not probabilities。

 they're functions of probabilities， but they're not probabilities。

 and odds ratio of1 means no difference， okay， but on the logit scale or the log odds ratio。

 zero means no difference。

![](img/d40da7bb150e538827b082b65e7d30c3_81.png)

And odds。Often if we have an odds ratio below 0。5 or above 2， that's considered a。



![](img/d40da7bb150e538827b082b65e7d30c3_83.png)

I would consider kind of a strong effect it depends that's very context dependent so if you're working in the field of epidemiology or something like that。

 you often get very small odds ratios， 1。01 might be significant you're looking at giant studies and the reason that these small odds ratios are important is because they're studying rather noisy things like nutrition or something like that how nutrition impacts health or something like that and you wind up with because of the all the various factors that incorporate influence the study。

 you wind up with very small odds ratios that are still meaningful even if significant。

 on the other hand you might run a very tightly controlled experimental clinical clinical trial or something like that and then the odds ratios that you would want in order to declare something kind of meaningful would have to be much larger so again this is just less than 0 less than 0。

5 or bigger than two is's a little bit of a benchmark but remember。



![](img/d40da7bb150e538827b082b65e7d30c3_85.png)

![](img/d40da7bb150e538827b082b65e7d30c3_86.png)

![](img/d40da7bb150e538827b082b65e7d30c3_87.png)

Like all benchmarks， they only have a certain amount of utility。

 really how strong an odds ratio is relative to the scientific setting is incredibly dependent on the contexts that you're looking at it in。

So the relative risk is another entity that's often thought of in the same vein as the odds ratio and many people like it。

 so the relative risk is just the ratio of the two probabilities。

And many people like it because they tend to instinctively think a little bit better in terms of probabilities rather than odds。

And relative probability seems like a reasonable thing to do。 The problem with the relative risk。

 unlike the。

![](img/d40da7bb150e538827b082b65e7d30c3_89.png)

Unlike the odds is it puts in some model constraints that are quite hard。

 so we don't see relative risk regression for binary variables is a very common thing due。

 though some software languages I know R has some packages to do it and SAS has some packages to do it。

One thing that is pretty common， if you happen to have small probabilities。

 then the relative risk approximates the odds ratio， this is an old， very classic result。



![](img/d40da7bb150e538827b082b65e7d30c3_91.png)

So that people go ahead and fit the odds ratios， but then interpret them as if they're relative risks。

 so if you've seen that before， then that's where that's coming from。



![](img/d40da7bb150e538827b082b65e7d30c3_93.png)

![](img/d40da7bb150e538827b082b65e7d30c3_94.png)

So I give you a couple more references here on odds ratios。

 but I think that's enough to get you started on generalized linear models for binomial data。

 I'm hoping that you can use all of your knowledge you got from linear models and help you work that into your use for generalized linear models next lecture we're going to consider Poson data that's sort of the last real lecture of the series that we have kind of some bonus fun content is the last lecture the very last lecture so I look forward to seeing you next week where we're going to talk about Poson random variables。



![](img/d40da7bb150e538827b082b65e7d30c3_96.png)

![](img/d40da7bb150e538827b082b65e7d30c3_97.png)

![](img/d40da7bb150e538827b082b65e7d30c3_98.png)

![](img/d40da7bb150e538827b082b65e7d30c3_99.png)

![](img/d40da7bb150e538827b082b65e7d30c3_100.png)

![](img/d40da7bb150e538827b082b65e7d30c3_101.png)

![](img/d40da7bb150e538827b082b65e7d30c3_102.png)