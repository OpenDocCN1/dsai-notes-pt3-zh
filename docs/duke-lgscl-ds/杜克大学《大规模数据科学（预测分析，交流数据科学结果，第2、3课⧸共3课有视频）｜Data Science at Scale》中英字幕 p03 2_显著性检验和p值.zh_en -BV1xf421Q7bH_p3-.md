# 杜克大学《大规模数据科学（预测分析，交流数据科学结果，第2、3课⧸共3课有视频）｜Data Science at Scale》中英字幕 p03 2_显著性检验和p值.zh_en -BV1xf421Q7bH_p3-

。

![](img/35422e4a14f1085e780c76816743a7a3_1.png)

So in the last slide， we said that comparing two groups。

 the control group with the experimental group is the name of the game。

 and we said that we're trying to take some test statistic and。

Measure the difference between those two groups。 But how different is different enough to be significant。

Okay， so， in other words， how do we know that the difference that we saw in the experiment is not attributable to just chance。

 Well， the answer is we don't， but we can calculate the probability that that。

That is attributable to chance。 And that's what the P value is。 Okay， so the P value is。

The following， if you would repeat the experiment over and over and over again at the same sample size。

What percentage of the time would you see results that were at least as extreme？

As the ones you got in this experiment。And this is all assuming the noll hypothesis is true。

 so let me say that again。Assuming that there is no difference between the groups。

The control group really is the same population's experimental group， the treatment has no effect。

If I were to do the same experiment over and over again。What percentage of the time would I would I？

See a difference in the treatment group anyway， just by chance， and that's what the P value is。F。So。

More terminology， you know， you mean， you need to think about two sided versus one sided。

 So two sided is if we're measuring something in terms of the absolute value。

 so the P value is two times the probability that x is greater than the absolute value of the measured value。

 And if the test is one sided， it's either greater than or less than。 And here。

 the notation that we're using is。Mu， which is the mean and mu muus sub zero。

 which is the mean of the population under the null hypothesis。

So this screenshot is taken from a nice applet that you can find。Online。And play with here。

 but here if the null hypothesis is that the mean is 325。And we're doing a。

Two sided test where mu is not equal to 325。 we're saying it must be something different than that。

Either high or lower。Right。And the sample size is 10。And the observed sample mean is 328。

Then when you click the showP button on the applet。

 what you get is it computes the P value for you and shows this colored region。

And so these color re gems。And so these colored regions， the area of that curve is。The P value。Okay。

So that's the probability。That it's at least as extreme as the measured value。

And if you get know here， the only change I've made is that the sample mean was 329 instead of 328。

 which means it's even less likely that you would see this by chance。

 and so the area of those curve is even smaller and you notice the P value change。

 the P value went from 0。0574 to 0。0114。So in order to make some sort of a decision， you know。

 did this treatment work， right， do we invest in this treatment。

 do we move on to the next stage of trials？We need some sort of a threshold。

 some sort of a cutoff for the P value。So what does that cut off？Well， it's 0。05。Why， no good reason。

 it makes the math work out。Okay， so this is a  one in 20 chance if you can show it。

More rare than a 1 in 20 chance。Then that's deemed to be。Good enough。Okay。

 this is the subject of a lot of。Controversy， depending on what circles you。

What sort of literature you're reading？And we'll talk a little bit more about this in a few segments。

That's all I'm going to say about it right now。 So 0。05 is what people are。



![](img/35422e4a14f1085e780c76816743a7a3_3.png)

Looking for。All right。