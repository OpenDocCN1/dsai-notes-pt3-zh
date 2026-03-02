# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p51 3_示例.zh_en -BV1L9Fde5EXS_p51-

So let's go through some examples。Of ways in which things can go right and things can go wrong so my colleagues wrote this wonderful paper about exactly about the issue of using your data to come up with your hypotheses。

 they work in the area of multiple sclerosis and a common problem in the area of multiple sclerosis brain research with magnetic resonance imaging。

 which is what they work on is actually defining what it means for a lesion which is one of the hallmarks of the disease。

 a brain brain lesion to be so-called enhancing， so it's sort of getting a greater amount of blood in the area。



![](img/5e112a46294155ba01a3448b40a41a48_1.png)

![](img/5e112a46294155ba01a3448b40a41a48_2.png)

![](img/5e112a46294155ba01a3448b40a41a48_3.png)

So they put forward a framework。Necessarily because the hypotheses weren't clear。

 they put forward a framework that both identified the hypotheses and interrogated the hypotheses with the same data set。

And of course， their statistical researchers， so their emphasis was on doing this in a rigorous fashion。

 but it's just an example of a setting where the hypotheses just couldn't immediately be come up with in a clear fashion。

 and so the data had to be to perform double duty of both coming up with a hypotheses and interrogating those hypotheses。



![](img/5e112a46294155ba01a3448b40a41a48_5.png)

Multiple comparisons since we're on the subject of brain imaging， which is the area that I work on。

 multiple comparisons is often an issue。And in one particularly famous example。

 some people put a dead salmon in an FMRI machine， which is there to detect brain activation。



![](img/5e112a46294155ba01a3448b40a41a48_7.png)

And of course， there's no brain activation in a dead salmon。

 and what they found is that if you do lots and lots and lots of tests and you don't account for that correctly。

 you can see brain activation in a dead salmon。

![](img/5e112a46294155ba01a3448b40a41a48_9.png)

A very famous example of randomization that occurred kind of recently， at least in the past decade。

 was from the Women's Health Initiative。

![](img/5e112a46294155ba01a3448b40a41a48_11.png)

The Women's Health Initiative conducted a study， a randomized trial of hormone replacement therapy。

 which at the time was a fairly standard treatment for postmenopausal women。



![](img/5e112a46294155ba01a3448b40a41a48_13.png)

The result of these randomized trials contradicted what was thought of as common knowledge as for the efficacy of hormone replacement therapy and the safety of it。

And so it brought about a lot of soul searching about the value of a randomized trial versus the value of a lot of observational data。

 and I think it's maybe not necessary to go into the weeds of this study for the purposes of this lecture。

 however suffice it to say the randomized trial carried a lot of weight with it because of the randomization。

 all of the previous observational trials where they just saw whether or not women were on hormone replacement therapy and watched them over time。

 that the multitude of those studies was not deemed as rigorous as the one study that had randomization where women were actually randomized to hormone replacement therapy or not and as a side note if you're interested about reading up on hormone replacement therapy。

 I put a website here from the Women's health Iti where you can actually go and look on the frequently asked。



![](img/5e112a46294155ba01a3448b40a41a48_15.png)

Relating to some of the studies that have done since then。

 there's been a decade of work since then to further refine the science on this particular issue。

 the main point for this lecture is the importance how important randomization was in this particular setting。



![](img/5e112a46294155ba01a3448b40a41a48_17.png)

![](img/5e112a46294155ba01a3448b40a41a48_18.png)

So here's an example of a study that I was involved in where you can't actually measure what you'd like to。

 so in two ways in this study you can't measure what you'd like to。



![](img/5e112a46294155ba01a3448b40a41a48_20.png)

So my colleague， Susan Bassett， was interested in studying Alzheimer's disease。

 and what you'd really like to know is， well before people have Alzheimer's disease。

 what do their brains look like with regard to these functional magnetic resonance imaging scans？



![](img/5e112a46294155ba01a3448b40a41a48_22.png)

So well before it， and that would be very useful because if you could see that there were some changes in the brain well before people develop symptoms。

 maybe you could treat it。So this is a big deal， actually in Alzheimer's research。

 is trying to find precursors for the disease。So there's two problems that occur with respect to measurement in this particular study。

 first of all， the FMRI machine doesn't actually measure brain activation。

 it measures a proxy for brain activation through blood oxygenation。

 so it actually we can't actually measure in living humans to the spatial extent that we'd like。

The brain activation in the way that we like。 So there's one sense that the technology just can't measure exactly what we like。

 It only measures a proxy。 But let's put that to the side and then talk about another way in which we're not measuring what we like。

 We can't know in advance who's going to get Alzheimer's disease。 We can only guess。

And so in this case what she looked at was people who were at very high familiar risk。

 they had affected siblings or affected parents， multiple affected siblings and affected parents。

 and then in the other group they had people with no affected siblings and affected parents。

 but that doesn't mean that that everyone in the familiar risk group is going to contract Alzheimer's disease。

 quite the opposite relatively small fraction of them has。

 and that doesn't mean no one in the other group is going to contract Alzheimer's disease and some of them did eventually this was a long study over 15 years。

 so they later on they saw some results for people who actually converted。

But the point being here that she can't actually measure what she needs to。

 she can't prospectively measure who's going to contract this disease in the future because if you did。

 the problem wouldn't be worth studying right that's everything that you like to do so the measurement is a very clear problem in this case and what you have to combat this with is giant sample sizes just having a greater percentage of likely people that are going to get Alzheimer's disease in the one group and a smaller percentage in the other group and you need a much larger sample size to account for the fact that you're going to see much smaller effects from the fewer people of the diseased ventral disease type in the one group and the fewer people of the control type in the other group。



![](img/5e112a46294155ba01a3448b40a41a48_24.png)

So again， this just serves as an example where the measurement that you'd like to have isn't the measurement that you get。

 and this is very common in data science experiments and you need to work around it just like Susan in this case did by conducting one of the largest FphMRIS experiments that anyone had seen at the time just because to combat this issue。



![](img/5e112a46294155ba01a3448b40a41a48_26.png)

So in this class， we're going to dig through various facets of the perfect data science experience versus real life。

 and we'll use this idea of what's ideal versus what tends to happen as our launching point for all of our discussions。

And we'll give some practical recommendations for the messy situations and how you can manage the people doing the data analysis if it's not you and you're the manager。

 how you can manage and help direct them to different solutions for this collection of various problems that arise in data analysis so welcome to the class and we look forward to seeing you in it。



![](img/5e112a46294155ba01a3448b40a41a48_28.png)

![](img/5e112a46294155ba01a3448b40a41a48_29.png)