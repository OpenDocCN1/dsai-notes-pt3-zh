# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p60 12_抽样偏差与随机抽样.zh_en -BV1L9Fde5EXS_p60-

Hi， my name is Brian Caho， and this is the lecture on bias as part of our executive data science specialization。

I want to distinguish the kind of bias that I'm talking about today with some of the other things that we've talked about before。

 like randomization。The goal of randomization is to make the two groups that we're studying as comparable as possible。

So if we randomize a treatment and a control to a collection of subjects。

 then they're otherwise similar other than whether or not they receive the treatment of control。

With high probability， at least。That doesn't mean necessarily that the collection of patients that you're studying。

Are representative of the broader collection of patients that you'd like to draw conclusions on。

For example， patients in clinical trials often are very good at adhering to their medications。

 whereas the general population may be less so。This， of course。

 carries over to discussion of things like A B testing。So why is this relevant。

 well it's relevant because statistical inference， kind of the fundamental component of statistics is the process of making conclusions about a population from our sample。

 it's not enough to just say things about our sample。

 we actually want to generalize that knowledge beyond our sample。

 and that is the process of statistical inference。Well。

 if our sample isn't representative of the population that we'd like to draw inferences on。

 then we have a problem and things can happen like this。



![](img/f2bd5eaecf3193c7c04121fbe4a83f5c_1.png)

When the Chicago Tribune declared that Dewey defeated Truman， when in fact Truman won the election。

The root cause， in this case was a kind of bizarre sampling scheme that LED to erroneous and erroneous conclusion。

Another famous example is a so called Kinsey report。In the Kinsey report。

 the collection of study subjects involved a lot of people with psychological disorders and prisoners。

And then the main criticism of the work was that it wasn't generalizable beyond this somewhat different population that it was studied。

It's interesting to note that Kinsey's response was to collect more subjects， but again。

 not representative subjects。And this of course， doesn't solve the problem。

 simply getting a greater end of a bias sample doesn't correct the bias， in fact。

 in a sense it makes it worse。So what can you do， and that's what we're going to talk about today。

Different strategies for handling buys。 Well I could think of3。

So how do we combat sampling and other forms of bias？



![](img/f2bd5eaecf3193c7c04121fbe4a83f5c_3.png)

One of the best ones is random sampling， here's a picture of an urn。

 urn problems are sort of famous and statistics for sampling。

So random sampling is exactly that we try to draw subjects randomly from the population that we're interested in。

 This can often be quite hard to do， for example， in polling。

 there's an entire science devoted to getting accurate polls and getting your sample random so that they don't have inherent biases and they don't make a Chicago Tribune style mistake。

One， for example， one strategy often used is random dialing， random telephone dialing， for example。

 but nonetheless， this is a good strategy if you can do it。

 but often you can't often it's not on the table。What are some other strategies， Well。

 waiting is another strategy when again， random sampling is off the table。

 The idea of waitinging is something like this。 Imagine in your sample you have twice as many men as you have women。

 however， you know in the population that you're interested in drawing inferences about there's equal numbers of men and women。

In your sample， then when you were doing your analyses。

 you would upweweight the collection of women that you had。

 and you would downweigh the collection of men so that。

As far as the weighted inferences were concerned， the women and men were contributing equally。Okay。

 so that's the process of waiting again， this requires that you know the population demographics with respect to these important characteristics and that you have them measured in your sample。

Finally， the last strategy that I think of one of the important three strategies for dealing with bias is modeling。

In our modeling case， what we would say is we would want to understand why it is that on whatever we were measuring。

 gender made a difference， and we would try to model that and account for it and then use our statistical model to adjust for it。

This has the problem of actually having to build the model。

Whether or not our conclusions are robust to this model building。

 things like having a random sample are quite robust to a lot of assumptions whereas modeling can often be fraught with errors associated with assumptions。

So again， those are three strategies。That you can use to combat bias。So let me summarize。

 so bias comes in many forms and can contaminate your analysis。

 especially your statistical inferences。Sampling and bias。

 which we talked a lot about today is a particularly common one whereby your sample isn't indicative of the population you'd like to make inferences about。

 and we talked about three strategies for combating sampling bias。

 one was random sampling that's at the design stage。may or may not be applicable in your case。

 we talked about reweighting， okay， that's done in the analysis stage。

 but requires you to have specific knowledge about the weights。And then there's modeling。

 which again is done at the analysis stage， however。

 requires the model building exercise and may or may not be sensitive to some of those choices that you make in building the model。

Well， I hope you found this lecture useful and I look forward to seeing you in the next class。

