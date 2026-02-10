# 宾夕法尼亚大学《因果推断速成课程｜A Crash Course in Causality》中英字幕 - P39：39_05_02_存在不依从的随机试验.zh_en - GPT中英字幕课程资源 - BV1Ft42137BF

![](img/aef10ffb39b57281c5f41b6cf00d429d_0.png)

This video will focus on randomized trials with noncompliance。

 so we'll begin by discussing the difference between the assigned treatment。

 which we'll think of as an instrument and treatment received。

 which we'll think of as the observed treatment in a randomized trial。

We'll also discuss what potential treatments are， and we'll think about the causal effects of treatment assignment。

So we'll begin by thinking about randomized trials and here Z will end up being the thing more that we actually randomized so Z is randomization to treatment or you could think of it as randomization to some kind of treatment assignment so for example。

 Z could take value one if you're randomized to treatment and could take zero if you're randomized to say placebo or no treatment or the control condition so essentially we're thinking of Z is something that we'll randomize and then we'll hope that the person will do so if somebody's randomized to treatment then we'll basically SM to take the treatment。

So that that's what Z is， whereas A is what people actually receive， so it's treatment received。

 so it's one if you receive the treatment and zero otherwise。

And then we'll have some outcome we're interested in why。And so in practice in randomized trials。

 Z andA will not always be equal to each other， so sometimes people will be randomized to treatment。

 but then not actually take the treatment， so for example。

 if you are in a drug trial you might be randomized to take some drug and then you might just not take it so sometimes there's non-compliance and so we want to distinguish between this treatment received which is a。

 which is really the thing we're interested in is the effects of actual treatment versus treatment assignment which is where the randomization happens so if you have non-compliance then essentially this randomized trial will starting to look like an observational study in the sense that we might have confounding and here what we mean by that is confounding in terms of treatment actual treatment received。

So there could be variables that both affect what treatment you receive。And the outcome。

 So we'll call those variables X。 So x here are confounders。

And so you'll be assigned some treatment based on Z。

So Z is the thing that we randomize and we're hoping that if you randomized the treatment。

 that you'll take it。But whether or not you actually do might depend on other variables。

 so X are these confounders， it could be you know your age or how healthy you are and for example。

 maybe people who are less healthy might be more likely to take the treatment hypothetically so that's the kind of thing we have to worry about so。

Part of this da over to the right looks very familiar with this sort of classic confounding kind of situation。

 what makes us setup different is we have this randomization Z that's also affecting treatment。

So to think about this problem， what we'll do is we'll begin by first pointing out the observed data are the set Z A and Y。

 so for every person。Will will observe what their treatment assignment is。

 We'll also willll assume here that we observe their treatment received a。

 and we also then eventually will observe some outcome for them。 So that's the observed data。

 Z A and Y。 So essentially。You know，For a given subject。You。

 they're signed treatment Z and they receive treatment A。But of course。

 their treatment might be different than their observed treatment might be different than the one they were actually assigned。

But what we can do now is just like we define potential outcomes in a separate video。

 we could also define potential values of treatment here。 It's the same kind of idea。

 so we could imagine that each person has two potential values of treatment。 So the first one。

Is a with superscripts equal one。 And so you can think of this as a sort of happening before the study even begins。

 So you have。There's some patient or some subject in your study， and if you happen to assign them。

 you randomize them to receive the treatment， so Zze equalL1。Then they would end up。Actually。

 receiving。Some value of the treatment， which what we're calling A1。

 so that could be either the treatment or no treatment。So a here。

 a superscript 1 just means it's the value of the treatment that would occur if they were prescribed or assigned to the Z equal1 group。

So A1 here could end up being treatment or no treatment。

It's just the value of that variable if they happen to get randomized as equal one。

And so also we could think of potential treatment under the control condition so if somebody。

 if the same person instead had been assigned to z zero， what would their treatment be。

 well we'll call that a superscript zero so that's the value of their treatment if they're randomized to z zero so we'll basically think of each person as having a value for a0 and A1 even before the study begins we'll imagine that that exists we don't we'll never see them both simultaneously。

 but we still imagine that they exist。So now we could actually using this sort of potential treatment idea。

 we could actually then think of。A causal effect of treatment assignment on treatment received。 Okay。

 so this is going to look familiar when we were looking at potential outcomes and causal effects。

 But now we're just thinking of the causal effect on treatment received so here。

We have a causal effect where so we're just contrasting the treatment that you would have received if you were assigned z equal 1 versus the treatment you would have received if you were assigned treatment z equals 0。

 and then we take the means so we average over the whole population。So this， in words。

 it's a proportion treated if everyone in the whole population had been assigned to receive treatment。

 which is equal1 minus a proportion。Who would have received treatment if no one had been assigned to receive the treatment or equal zero so this contrast。

 if there was perfect compliance， if everybody did what they were told would be equal to one so a1 would equal one for everybody and a0 would equal zero for everybody so in the world of perfect compliance that would be。

What you would get。So this is a causal effect right because we're contrasting potential outcomes on a common population。

 so that's all a causal effect ever is is a contrast of potential outcomes on a common population so this and this is a population level causal effect because we're not conditioning on anything so we're looking at the population as a whole Now it turns out we can actually estimate this from observed data。

Since we have we've randomized Z and as long as we can assume consistency， again。

 where consistency just means， for example， that a1 would just be equal to your value of a if you happen to be assigned z equal1。

So the potential outcome。That you would receive。If you were assigned z equal1 corresponds to your treatment received。

 if you did happen to be randomized to z equal1 okay so that's a pretty basic assumption there and we also have randomized so assuming that we've actually randomized then we can estimate this from observed data so for example。

 the expected value of the potential treatment under z equal1 would just be equal to the expected value of treatment given z equal1 so if we restrict to the subpopulation of people who are actually assigned z equal1。

 then we just take the mean of a for that group， and that should be the same as the expected value of a1 and the whole population and that's because of randomization so if I stratify if I only look at the subpopulation who were assigned treatment that subpopulation should be have the same characteristics as the whole population because we randomized。

So and I say it's estimable because you'll notice this expectation only involves observed data。

 so we observe a， we observe Z， So a simple way to estimate this， for example。

 would just be to look at the subpopulation that has equal1 and take at the sample mean of a so this is something we can estimate same kind of thing for a0 we could just look at the subpopulation that we assigned the control condition and take the expected value of a so that's the causal effect of assignment on receipt of treatment and this is observable from the data so you can estimate this you can identify it。

We also can think of the causal effect of treatment assignment on the outcome itself。

 then this would be known as an intention to treat effect。

 so we could contrasttras the outcomes had everyone been prescribed or assigned z equal 1 versus the outcome had everyone been assigned z equal0。

So this is an intention to treat effect because it's basically contrasting outcomes based on what you intended to do so you know our intention was for people assigned Z1 to get treatment you know so whether they did or not that was our intention so that's what's meant by intention to treat effect and if there was perfect compliance then this would be an actual effect of causal effective treatment itself right because Z equal1 would always directly exactly correspond with a equal one。

And again， so this is actually something we can estimate from observed data as well。

 so this is identifiable， as long as we have randomization。

 so for example the expected value y superscript z equal 1。

 so this is the average value of the outcome had everyone in the population been assigned z equal 1。

 but we' randomized z equal1 so therefore we could just condition on z equal1 and then take the mean of the observed outcome and so again it's identifiable because both y and z are just observed data。

And so we could estimate that。So because we've directly randomized Z。

 then we can estimate a causal effect of Z on anything really。

 so on treatment received or on the outcome。So these， those two things are relatively easy to do。

 So getting a causal effect of assignment on treatment and getting a causal effect of。

Assignment on the outcome。 But what about the causal effect of treatment received on the outcome。

 So rather than treatment assignment on the outcome， what about treatment received on the outcome。

 So that's this might be of greater interest to us is how what was the causal effective treatment itself on the outcome So we could think of of Z。

As encouragement to receive the treatment and in a randomized trial like this。

 you could think of it as strong encouragement because typically。

 even though there will be some noncompliance。In a randomized trial。

 a lot of times there's various kinds of blinding and so on。 And you know。

 compliance tends to be pretty good。 So you could think of this as strong encouragement in that most people will end up doing what they're told。

 So So Z here is an instrumental variable。 we think that。

It certainly should affect treatment received， so treatment assignment should affect treatment received。

But we don't think the random assignment necessarily would affect the outcome directly。

 so this sort of process of randomizing treatment， we don't think in general should affect the outcome directly。

 so we could think of this as an instrumental variable。

 but the question then is does that actually help us estimate the causal effect treatment itself？

So this is really the main goal of instrumental variable methods is to use this instrument。

 this randomization to exploit that， to try and estimate the effect of Friman itself。

 so this will be a topic for another video。