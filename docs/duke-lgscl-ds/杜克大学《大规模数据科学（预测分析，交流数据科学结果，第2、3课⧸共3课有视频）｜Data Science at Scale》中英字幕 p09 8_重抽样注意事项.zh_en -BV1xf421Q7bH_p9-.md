# 杜克大学《大规模数据科学（预测分析，交流数据科学结果，第2、3课⧸共3课有视频）｜Data Science at Scale》中英字幕 p09 8_重抽样注意事项.zh_en -BV1xf421Q7bH_p9-

![](img/53e74e430ec38dd3cecb474bb1c4ec68_0.png)

So。Backing up a step， you know we talked about the shuffle test for significance。

 and that was kind of that had a reampling method， it was a little different because we shuffled the labels。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_2.png)

And then we talked about bootstap samples to drive a confidence interval and really any other kind of statistic you may need。

 One question is， why do we even need that Josh shuffle test at all。

 Why can't we just use the confidence interval itself， After all， you know。

 it's possible to reason about significance even when the confidence interval， you know。

 you can see where there's zero falls within the。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_4.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_5.png)

Within the company several or not。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_7.png)

The reason is is that there's a sort of a subtle reason about what you're starting from if you compute the confidence interval。

 you're already asserting that there is a significant difference。

 say in the means or the statistic is significant。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_9.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_10.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_11.png)

When you're testing significance， you're starting with a null hypothesis and you're deciding whether to reject that or not。

 and you can see。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_13.png)

Intuitively， when that might make a difference， consider a immediatelyly contrived case where you only have two data values。

 one treatment and one placebo。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_15.png)

Sorry， I said placebo in this case。 let's go with placebo。 So one is a treatment。

 the other is a placebo。 we're trying to measure the difference between them。 right。

 So the and let's imagine this is still survival days。 So with the treatment they survived long。

 the one patient survived longer， 36 days。 and with the placebo， they only survived 27 days。

 So a 95% covennce interval will range from the value 9 to the value 9。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_17.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_18.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_19.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_20.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_21.png)

Meaning， meaning a sort of very， very tight interval with a shuffle test。

 you'll shuffle the labels here and do a bunch of experiments and quickly determine that the P value is about 0。

5， which is， of course， not significant， right， halflf the time it's the difference is 9。

 The other half， it's negative 9。 and so。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_23.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_24.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_25.png)

The P value wheat will be quite high。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_27.png)

So you always want to start with the null hypothesis that there is no difference。

 test the significance of that with a shuffle test and then measure the confidence interval as a second step。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_29.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_30.png)

Okay， so caveats about the bootstrap， when is it dangerous to use this Well really it is pretty robust it actually makes fewer assumptions than a lot of the classical methods made as we've described。

 it may underestimate the confidence interval for very small samples。

 usually in these data science regimes in these big data regimes。

 very small samples is not the concern that we typically have to worry about。

 we usually we usually we often have many data sets。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_32.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_33.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_34.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_35.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_36.png)

Bootrapping can't be used to estimate the minimum or maximum of a population。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_38.png)

So you should consider why that might be。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_40.png)

So when we're taking averages。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_42.png)

嗯。It works pretty well。But the minimum maximum is very， very sensitive to outliers， to very local。

 local values。 right， If even one one more value as you scan through this as you scan through the data is higher。

 then that will be the maximum。 It could have an arbitrarily large effect on the statistic。

 and the bootstrap is。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_44.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_45.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_46.png)

Not going to if you take a bootstrap sample width replacement。

 you might miss that one outlier that really dramatically changes the value and so。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_48.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_49.png)

You'll get a distribution that doesn't match the distribution of the maximum。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_51.png)

Okay， and so in more generally， outliers can cause trouble with bootsropping。

 but they sort of can with any method， so it's not。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_53.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_54.png)

That's not a significant weakness of resampling methods in general。

 and in fact we'll see in a moment we'll see one thing you can do about outliers。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_56.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_57.png)

Okay， so it is a little bit sensitive where sampling can be done kind of incorrectly with more complex examples。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_59.png)

That failed to preserve the original sampling structure。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_61.png)

Okay so we saw this a little bit with the example of the confidence interval just now where you need to do a bootstrap sample of one cohort and a bootstrap sample of the other cohort as opposed to bootstrap sample where you pull them together。

 there are ways to actually do it in kind of a pooled way， but in general。

 you need to respect the structure needs to match the experiment you're trying to do in other cases if the data are not independent。

 you can't use the bootstrap sample。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_63.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_64.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_65.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_66.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_67.png)

You or and you can and it may be tempting to do so because it may not be obvious that it's not valid。

 There are sometimes tricks you can play。 So the trick is if you have a sequence of mutually dependent。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_69.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_70.png)

Values。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_72.png)

So that the independent assumption doesn't hold， what you can do is break those into subamples that don't overlap。

 So let's say time series of like stock prices or something， take a which are not independent。

 of course， every value of stock price depends on the value previously。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_74.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_75.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_76.png)

Take sub sequenceequences of these stock prices。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_78.png)

Non overlapping。Break a long history into chunks and then treat each chunk as an individual observation。

 compute some statistics on that， and then do resampling on those chunks。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_80.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_81.png)

And that's been shown to work。 So there are sometimes ways to apply this general technique in kind of creative ways。

 so it's not it's not particularly limited to a few examples。

 certainly not the one few examples that I'm going to show。

 but think of it as a very general approach。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_83.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_84.png)

know write a program， do the simulation to simulate the experiments that you want。

 you may have to think creatively about how to apply this in a safe manner。

 but but it's a very general approach okay。

![](img/53e74e430ec38dd3cecb474bb1c4ec68_86.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_87.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_88.png)

You know， as we mentioned， the maximum doesn't work， and then of course。

 you know nonrepresent samples will always cause trouble and they do with the boostri as well。

 it's not going to magically cure issues you have with the data。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_90.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_91.png)

Okay and you know one quote here that I cop down that I sort of liked is you know it's tempting to someone to say。

 oh you know you let the data speak for itself and Nate Silver has this quote。

 you know the numbers have no way of speaking for themselves。

 there's always going to be an interpretation about them。

 there's always going to be some knowledge about where that data came from。

 there's always going to be biases lurking in there but only the source of the data can tell you about only the context in which it was done can tell you about。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_93.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_94.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_95.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_96.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_97.png)

Okay， so it's so， you know， putting the statisticians hat on as opposed to。

 say the machine learning or computer science hat on。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_99.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_100.png)

Understanding the source of the data， understanding the experimental design that led to that data。

 or if you weren't aware for the experimental design。

 understanding the other kinds of biases or context in which it was sampled is always going to be crucially important whether or not you're using reampmbling methods or classical methods。



![](img/53e74e430ec38dd3cecb474bb1c4ec68_102.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_103.png)

![](img/53e74e430ec38dd3cecb474bb1c4ec68_104.png)