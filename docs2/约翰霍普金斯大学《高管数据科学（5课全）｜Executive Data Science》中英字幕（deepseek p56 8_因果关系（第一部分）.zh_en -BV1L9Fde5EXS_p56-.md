# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p56 8_因果关系（第一部分）.zh_en -BV1L9Fde5EXS_p56-

![](img/e9f1155a0d16dda7ce2c36b1c5bb9492_0.png)

Hi， my name is Brian Kaho， and this is the lecture on causality。



![](img/e9f1155a0d16dda7ce2c36b1c5bb9492_2.png)

So what is causation and I start with this great XKCD comic， if you don't read XKCD。

 it's this wonderful web comic and you should look it up。And it says。

 I used to think correlation implied causation。 Then I took a  one01 class， and now I don't。

 sounds like the class helped。 and it says， well maybe。

 And so that's what we're going to talk about today is the well maybe part。

So in order to define causality， I'm going to go back to the philosopher David Hume。

And his philosophy really underlies or was the starting point for some of the thinking on causality in the world of statistical analysis。

And I give you this quote here， and it's somewhat of a mouthful。

 But the fundamental idea for for defining a causal effect in statistics。

 or at least one of the major branches of thinking is to think about counterfactuals。So。

 and this is what he describes。 And if you look at the last sentence or in other words。

 where if the first object had not been， the second never it existed， he's talking about。

 or we translate it now to the idea of counterfactuals。

 So as an as an example in the medical world of a counterfactual。

 what we would talk about is whether or not a person would respond to the treatment with what we observed。

 if we gave them to treatment and they responded or not。

And then the counterfactual be what would have happened for that person if we had not given them the treatment。

 so the causal effect is the difference for that person。

 whether they received the treatment or whether they didn't receive the treatment。but of course。

 we only get to see one of those two realities。 and so the counterfactual is the difference between something we observe and something we can't observe。

So again， just to reiterate， that's what this slide says。

 is the causal effect of a treatment on a subject is the change in the outcome from the treatment that the subject actually received and what would have occurred had she or he received the other treatment okay so that's the counterfactual difference。

And again， it requires something we observe， but also requires something we cannot observe。

So let's just go through an example and consider a madeup treatment and in this case。

 I don't know why I decided let's pick an exercise treatment so I picked a silly one so this is in kind of a crazy 70s exercise equipment called the twist and tone where you kind of twist on your hips okay so let's imagine so the causal of the counterfactual right。

 would be the difference between what would happen if a person used the twist and tone。

 let's say for 12 weeks versus they didn't both of these by the and it's the same person and by the way。

 both these person both the person in this images of the same person it's Christian bale from two different roles。

 certainly the amount of weight loss he went through in the right hand roll was a little excessive。

 but the counterfactual difference would be the difference in the outcome in this case some measure of fitness or muscle density or whatever comparing whether or not the person had used it to whether the person had not used it。

So we can't observe that， right， we can observe for this specific point in time。

A person who has both used the twist and tone and not use the twist and tone。

 We could do something like in the in Christian Bale's case。

 look at it if he used it for a while and then had a washout period， and then he used it。

 He didn't use it for a while or something like that。 But that's， again。

 that's that's not at the same point in time。 So whatever effect we see may be alias with time。

 So we can't actually get at。The causal effect for an individual， however we can get at。

 we can estimate at least the average causal effect。

 the average across individuals under some assumptions。

Okay so the average causal effect is not just if we look at whether or not Christian Bale used the twist and tone or not。

 the average causal effect is if we took a bunch of people。

 some of them used twist and tone and another' collection of them didn't they received the control。

And and the comparison between the two。 and if we have things like randomization。

 that allows us under some assumptions to estimate the actual average causal effect。

 so we can get at a real idea of cause。Completely empirically okay and that's the idea of causal statistical inference to get at the idea of cause。

 to understand the assumptions you're making， and to have a formal definition of cause underlying your analysis。

So this way of thinking there's some consequences， one consequences we to talk about cause we have to think about it an assignable treatment or intervention okay so in this case we can assign the twist and tone to some people and not we have to conceptually even if we can't specifically even if we can't randomize it like smoking is something we can't randomize。

 we can't tell people to go smoke that wouldn't be ethical however。

 it's conceptually randomizable I work in a setting brain imaging we're often interested in cause in things that are not assignable。

 for example， does this kind of change in your brain structure change your predilection for a particular kind of neurological disorder and in that case we can't conceptually think about that change actually being randomizable so that's one potential problem with this specific definition of causal statistical analysis that I'm supporting here in this lecture。

Sure。Of course the other one is we can't observe counterfactuals。

 we only get to observe one state of nature at a particular time。

 and that's the crux of the work and causal inferences trying to combat that issue。But we can。

 with assumptions in careful study design， make inferences about average causal effects。

 and that's where the real insight was。And to me， I think there's formal causal analysis。

And then there's。Understanding enough of causal analysis so that you can you can think about the causal implications of your analysis。

 And so to me， I don't know personally， I don't know。 I don't do that much specific causal analysis。

 However， causal thinking underlies a lot of what I'm doing。

 So I think causal thinking is essential for understanding for statistical analysis。

 and it's essential for understanding the causal implications of your analysis。

So what I'd like you to do is now to think about these various study design。

 now that you know this one simple fact， we're going to define cause as the difference as a causal effect as the difference between what a person。

 what we would observe on a person if they had a treatment minus what they would observed or over what they would observed。

 had they not received the treatment where we only get to view one So what I'd like you to do is think about these various kinds of study designs and how they try to get at that questions and in what ways they fail and in what ways they succeed。

So one really obvious example of trying to think this way is a crossover trial。

 give a subject to treatment， then after a suitable washout period， give them the other。



![](img/e9f1155a0d16dda7ce2c36b1c5bb9492_4.png)

So as an example， if you were studying chronic migraines。

 we could give someone some relief medication after a washout period， then give them another。



![](img/e9f1155a0d16dda7ce2c36b1c5bb9492_6.png)

So I think this might work for migraines because I think chronic migraines。

 people tend to continue to have them after a washout period。

 we can assume that the drug isn't carrying over to the next period。

 so I don't but it wouldn't work for something like an ad campaign because you can't unsee the previous ad so crossover trials。

 try to get causal effects by virtue of having the same person actually receive both treatments。

 or I give another example here a weight loss study。

 you couldn't do this kind of thing for a weight loss study。But again。

 I want you to think about crossover trials and the implications with causal and counterfactual thinking。



![](img/e9f1155a0d16dda7ce2c36b1c5bb9492_8.png)

![](img/e9f1155a0d16dda7ce2c36b1c5bb9492_9.png)