# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p63 15_效应大小、显著性建模.zh_en -BV1L9Fde5EXS_p63-

![](img/448b02c6759c46685d1ac15936e47628_0.png)

Hi， this is the lecture on effect size， significance and modeling。



![](img/448b02c6759c46685d1ac15936e47628_2.png)

In every statistics course ever taught， they go over this exact phrase。

 statistical significance is not practical significance。



![](img/448b02c6759c46685d1ac15936e47628_4.png)

![](img/448b02c6759c46685d1ac15936e47628_5.png)

And that's a discussion of the fact that。Just by reasons of having a large and you can detect very minuscule but unimportant effects。

 but I think the picture is a lot more complicated than that。And in this lecture。

 we're going to talk about these instances， what does it mean to get a significant or a non significant result in hypothesis testing？

And here we have two funny if you want to find more cartoons like this。

 I highly recommend looking up research Mark Walllberg and statistics， Ryan Gosling， anyway。

 they're very funny。So let's go through some thought experiments。

 so a very large epidemiological study of nutrition finds a slightly significant result， P of 0。049。

 so a P value right under what is the typical standard of evidence in this area associating hot dog consumption to colorectal cancer incidence。

So the question I would ask for you is does the larger sample size bolster the evidence or hinder it？

 So in this case， does the fact that they have a giant study， Does that suggest， oh okay， well。

 that means that it was really powerful or really powerful study， and we should trust it。

 or does it mean a weight， they barely achieved significance despite having a giant study。

 are we only getting at some sort of quirk of the large sample size， And in fact。

 this is kind of an unresolved question in statistics。

 It's not clear in this setting or many settings， what the information that the study was a very large study and was very large how that contributes to the strength of evidence for this specific P value。

So if it seems confusing， it's because it is confusing。

 I think you could probably go ask know all the top statisticians and you would get different answers。

Let's consider another thought experiment， a well done AB test， you had nice randomization。

 there wasn't a lot of missing data， the sample was very good。

 finds one ad campaign is not significantly better than another。

 a P value that's just above the standard threshold for significance for online purchases。

And in this case， does the good studies design bolster confidence in the lack of significance or not。

 Okay， it's basically the same question。 Does the fact that you have this really good study design say。

 okay， well。you know， we had a really good study design and the P values is really just right around marginal。

 So it's not significant， and it should have been significant because this design was so good。

 That's one way you could think about it。 Another way to think about it is， well， you know。

 it's really borderline。 And maybe if N had been a little bit larger， we might have rejected。

 So again。The point I'm trying to make here is that context is important。

And we cannot simply interpret the result of hypothesis tests outside of the context。

 it's basically the idea that P values and results of hypothesis tests are not portable across settings。

 they're not kind of a unit free context free quantities that you can just take from one experiment and interpret a P value of 0。

04 and interpret it in the same way in the next experiment。So among other things。

 the size of the effect matters and the size of the effect is lost when you just report the result of a hypothesis test or the P value by itself。

 So the size of the effect matters， so usually you want。

 in addition to the P value to actually see the actual estimate if there's a difference in means you want to see the difference in means So if the number of purchase of the percentage of clickthrough purchases for ad campaign 1 minus the percentage of clickthrough purchases for ad campaign 2 is an example。

 you actually want to see that effect and not just see the P value but also the context of the problem matters。

 what strength of evidence is required in this setting。

 what constitutes strong evidence in highly controlled physics experiments is very different than what constitutes his evidence in very large epidemiological studies of nutrition。

Another question is what level of error is tolerable。

 You may be in a circumstance where you're testing A versus B。

 but you have to make a decision between the two。 So you can tolerate a different level of evidence because you're going to have to pick one or the other。

 So unless the evidence is perfectly equivocal， you're going to take evidence slightly in favor of A and go with a or evidence slightly in favor of B and go with B。

 contrasttrat this with something like the a regulatory agency like the Food and Drug Administration that has to prevent。

Dangeous drugs from going to market there， they put very high degree very high scrutiny on the amount on the amount of information and evidence required to bring a drug to market because they don't want dangerous from drugs to go to the market。

 So the standard of evidence in those two circumstances is very different。

 So the result of a hypothesis test just can't be interpreted in the same way。

Another question is of course， what biases are likely present。

 if you have a giant sample that's very biased， then you might be finding an effect。

 but that effect may just be detecting that bias。And another thing that comes up often is multiple comparisons。

 Did someone just fish around until they got a significant result， Okay。

 they kept testing different hypotheses until they got a significant result。

 and we'll talk about some of these various concepts in subsequent lectures because I think they're important enough to drill down on。

So let's just summarize， so hypothesis testing is a tool， but it rarely should be used in isolation。

 so if you're managing someone and they're just reporting P values by themselves or the result of hypothesis tests。

 you need to push them to go further， you need to push them to give you effect sizes。

 you need to push them to give you confidence intervals。

 to put the results into the proper context of what's being studied to contrast the results with other other related studies and that sort of information。

So in other words， there is no substitute for a critical review of results in context。

 conference intervals， studies effects and。And other tools like this should be used in addition to hypothesis tests。

So three tools we're going to discuss specifically is we're going to talk about evaluating multiplicity concerns to make sure that the person you're managing hasn't fished through hypotheses until they found that one that was significant。

Another really useful tool is comparing effect sizes to other known effects。

And then a third very useful tool is negative control analyses。

 so we're going to go over all three of these in the next couple of lectures。



![](img/448b02c6759c46685d1ac15936e47628_7.png)

![](img/448b02c6759c46685d1ac15936e47628_8.png)