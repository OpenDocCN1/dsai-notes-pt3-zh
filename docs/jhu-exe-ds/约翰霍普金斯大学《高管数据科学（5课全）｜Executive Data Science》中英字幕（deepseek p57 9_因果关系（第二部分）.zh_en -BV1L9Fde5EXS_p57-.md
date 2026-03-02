# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p57 9_因果关系（第二部分）.zh_en -BV1L9Fde5EXS_p57-

![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_0.png)

Another way that people get at this is natural experiments。So a great example of natural experiments。

Is where smoking trials， so you can't randomize people some to smoke and some not to smoke。

 so you can't get the kind of Cadillac version of a causal effect via randomization What you can look at is。

 for example， places that put in smoking bans。And smoking bans impact smoking behavior。

So you could maybe get aggregate numbers smoking related cardiac of cardiac issues in a city or some other geographic unit and before and after a smoking ban went into effect and that gets at the idea of causality for the same reasons we were talking about before。

 but of course it fails with some fundamental assumptions you have to aggregated at a high level you don't get individuals you certainly don't get individual counterfactuals and everything that's alias with the timing of before the law to after the law could contaminate our results so if in the same election cycle where the smoking ban was passed that broadly impacted people's smoking behaviors。

If that same election cycle had other policies that also impacted things。

 those other policies still would also be associated with whatever cardiac decline in cardiac issues that you saw from your hospital records。

So again， natural experiments， something where some external manipulation。

 like a band going into effect， those are another way you can try to get at causality。Again。

 but with a lot of assumptions and again the entire field of causal inference is trying to outline those assumptions and again in this case the assumptions I think are quite strong。

Matching is another great one and that so matching is this idea of finding doppelgans。

 So here I have a picture of President Obama and then I looked up Doppelganger for President Obama on Google and they found this fellow。

😊。

![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_2.png)

![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_3.png)

So what's the idea of matching so if I have a collection of subjects that receive the treatment。

 I find people who have very close are very close in every other respect。Control subjects。

 and match them up。 So as an example， this is very commonly done in medical studies。

 So if you found you know， for example， you could look retrospectively if you found a bunch of cases of people that died of lung cancer right and you had a complete medical history and a lot of other history on these subjects then you would find some other people to match and contrast them with that that that never had lung cancer but that had the same weight。

 same age， et cetera， et cetera， et cetera。 So so any rate。Think。When you think about matching。

 think about why， when people do this， why they're thinking causally。

 they're trying to get that counterfactual idea by saying， okay。

 I can't observe this person twice in two states of nature but I can observe this person in their close doppelganger。

 Of course， the real problem with matching。 Well， there's a couple。

 but the main problem with matching is you're only as good as those things that you can match on right。

 And then there's also the problem of finding matches。

 You may not be able to find the data set to match enough enough characteristics。

 but you're only as good as those things you match on everything you fail to match on。

 then you haven't found a real， you haven't found the same person in the important respects。

 there's other problems often， if you have a data set and you can find matches for some people and you throw out the remainder。

 because you can't find good matches for them， Well。

 then you've kind of destroyed some of the generalizability of your sample。

 If you have a really good sample and then now you're only analyzing the people that are have matches。

 Well those that new。Sample may not be generalizable in the way the the original sample was so again。



![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_5.png)

In all cases， when you're trying to make causal assumptions。

 you're going to have to bite some bullets， but I would hope that you can see the connection of how people are trying to think causally and think about counterfactuals when they do matching。



![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_7.png)

Randomization is our best tool and it's our most effective tool for estimating average causal effects。

 so we have an entire class in lecture randomization and AB testing。

 but the idea of randomization is to make the treated in untreated groups as directly comparable as possible so if you have a group of people and you randomize the twist and tone to half of them and the other half of them don't get anything。

 well yes， you don't have exact matches of people who receive the controls to people who didn't but in all other respects by virtue of the randomization。

 they should with high probability， the groups should be directly comparable and you can show via some mathematics that if the sample is large enough and it's a random sample you do really get to average causal effects。

 This doesn't mean that randomization is a panacea， there can be issues， for example。

 there might be dropout people get randomized to the twist and tone but they realize they。



![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_9.png)

kind of ridiculous doing it so they stop doing it so the collection of people that complete the treatment are different than the people that were randomized to the treatment。

 so there's lots of issues that can come up even in our Cadillac version randomized trials but this is to date the best way that we can get at causal effect。



![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_11.png)

So what are some other examples of things we can do？Instrumental variables are a very clever idea。

 and we're not going to go through the details， but imagine if you wanted to understand whether or not oral contraceptives had a relationship with ovarian cancer。

 very reasonable question so and let's suppose you looked at something like reimbursement rates as those relate to ovarian cancer。



![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_13.png)

Well， the fact that there's no direct link between reimbursement rates and ovarian cancer。

 you know how we elect to reimburse oral contraceptive usage through insurance plans can't possibly have any real relationship with ovarian cancer。

 So any any effect of reimbursement rates on ovarian cancer has to go through contraceptive use。

 Okay， so people have used this idea。 So reimbursement rate have is an instrumental variables。

 So people have used this idea to try and come at causal effects without without actually having randomization。

 there's a big assumption and instrumental variables that the only way in which reimbursement rates could get to ovarian cancer is through oral contraceptive use again that。

That assumption is often that the only link between the instrumental variable and the outcome is through this variable that you're interested in。

That assumption is often suspect and it's very hard to find instrumental variables。

 but this was an incredibly clever idea it underlies a lot of causal thinking。

 modern causal thinking， and it's a pretty interesting approach。And then there's always modeling。

So in modeling you're trying to， for example， build up a model that explains why people respond to the treatment or not and if that model is sort of all encompassing。

 then you don't need to see the person in two states of nature。

 you have in a sense the two states of nature because you've built up the system you understood the system through the model again this is only as good as the model is it's fraught with assumptions and so。

And I would just say the most well known modeling technique and causal inferences uses so called propensity scores。



![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_15.png)

So what I've given you in this lecture is one definition of causality。

 this counterfactual definition of causality， one generalization of the idea。

 the average causal effects， and how different ways of statistical thinking try to get at this。

 and we try to understand both that these ways of statistical thinking get at causal effects。

 but they come with a lot of assumption and baggaging that there's often no perfect way to get at causal effects and the best thing we have going is randomization。

So if you'd like to read more about causality， actually the Wikipedia page on causal inference is pretty good。

 and I think any of the survey papers by， for example。

 Donald Rubin are wonderful reads on causal inference。

 he's one of the modern forefathers of the renewed interest in causal thinking and statistics。Well。

 thanks for listening， I look forward to seeing you in the next lecture。



![](img/e463a4d1fc3f9e3e1139b7aeb74e7cbd_17.png)