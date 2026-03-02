# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p67 19_相关的估计目标.zh_en -BV1L9Fde5EXS_p67-

![](img/b9b4eae1349ea1ab3928805667a3404c_0.png)

Hi， my name is Brian Kaho and this is the lecture on estimation target being relevant。

And so I'm going to start with this quote from it's attributed to lots of people I give some examples up there which you can find them Wikipedia。

 but of course many of you have heard the song， but if you can't be with the one you love love the one you're with and that's the idea behind some of these surrogate variables we're going to talk about today。

 if you can't measure the variable you want measure the variable you've got okay so what we're basically talking about in this lecture。

Is when you have an outcome that you're interested in studying， but you can actually measure it。

 you can only measure some surrogate for it。And we're going to talk about the benefits and pitfalls and some strategies that you can do in this very common circumstance。

But even if you don't find that prior quote less even if you don't find that prior quote inspiring。

 even less inspiring is the classic joke that talks about the drunk looking for his keys under the lamppost and the police comes up to him and asks。

 you know what are you doing and the drunk says looking for my keys and the police policeman says。

 well， did you drop them near here and the drunk says。

 no I dropped them over there and he's like well， why are you looking here and the drunk says because this is where the light is okay so let's talk about surrogate variables and hopefully we won't be like drunks looking under the lamp post well hopefully hopefully our keys will be nearby？

So the idea behind what we're talking about today is it's very common to not be able to directly measure what is most germane to your investigation or what you really want to measure。

 so some classic examples， body mass index as a measure of body fat percentage right so body mass index is really just only takes two measurements。

 your weight in your height， but a real measure of body fat percentage is much harder。

 it takes much more careful measurement， so BMI is a surrogate variable for what people really want which is body fat percentage。

It's very common for economists to use GDP as a measure of economic well being。

 even though they fully acknowledge that it's a crude summary of that。

Probably one of the worst examples or not worst， probably one of the hardest examples are food frequency questionnaires for calorie consumptions。

 so if you just ask people what they ate last week to try and ascertain their calorie consumption。

 that's a very noisy measure， but it's very hard to get good data on what people eat either way。

Of course， if you ask people whether they're going to vote， you get likely voters。

 but that doesn't mean you're going to get actual voters， if you measure web traffic。

 that doesn't mean it's sort of actual web traffic。

 you might be getting lots of hits from web crawlers and things like that。

 search engine crawlers and that sort of thing。So in my area， the area that I work in。

 we study something called functional magnetic resonance imaging。

 we would really like to measure people's brain activation。

 we really want to get at let's say neuronal signaling， but we don't get that。

 we get instead a very crude proxy for this called the blood oxygen level dependent or bold signal。

 so this phenomenon of not getting to measure what you want。

 but getting to measure some surrogate that's close or hopefully close is a very common problem。



![](img/b9b4eae1349ea1ab3928805667a3404c_2.png)

![](img/b9b4eae1349ea1ab3928805667a3404c_3.png)

So what are some hallmarks of good surrogates where the best surrogates are going to be unbiased。

 even if they're noisy and they're not completely like the variable that they're measuring。

 they're not systematically larger or systematically smaller？And ideally。

 they have a known variance around the desired outcome。So in that case。

 if you have a good surrogate variable， for example。

 if you don't know let's a very good surrogate is， for example。

 weight right with a nice unbiased scale if you don't know the person's actual weight but you have a scale that's kind of noisy but on average across all people it's as high as it is low and you actually know how variable it is around the truth then you can use that information in your analysis and probably everything will be fine。

 that's a very unusual circumstance， maybe the second best setting which is at some level attainable。



![](img/b9b4eae1349ea1ab3928805667a3404c_5.png)

Is where you have the truth measured on some subset of the people and you can study and understand some amount of calibration。

 and I'm going to give an example， so a very common thing that people do now is they wear I have a picture here of a Fibit。

And this is a little accelerometer that you wear around your wrist and it counts things like steps but it's not measuring steps。

 it's on your wrist， it's measuring acceleration， so they have to use an algorithm to predict how many steps you're making so and sometimes it's accurate and sometimes it's not and maybe even further your software or your Fitbit software or yourrie count your accelerometer on your watch or your cell phone will also not only give you steps but it'll actually give you calorie consumption。

So what could you do well if you were very serious about studying accelometry。

 what you could do is really get people in the lab， put a mask on them。

 really get very careful measurements of steps and calorie consumption while they are wearing a Fitbit or wearing any of these other devices and use that to understand its degree of accuracy you could maybe build up models because you know the truth on that subset of people and using those models。

 employ the strategies from those models in the instances where you only have the Fitbit data and you don't have the gold standard data。

 so doing a gold standard study is probably one of the better things that you can do and if you have that option I would highly recommend taking the time to actually actually study the variables。

 the surrogate variables that you're looking at and I think what often happens at least in my experience in the scientific。

orld whenever we go after these surrogate variables and try and figure out how accurate they are。

 we always seem to come away surprised at how inaccurate they are。

 how much less accurate they were than we thought they were。So any rate。

 that is a strategy that is very helpful， but if you don't have those strategies available to you。

 well the worst case scenario is there's。You have to acknowledge limitations。

 you don't have a real way to validate your surrogate。

 maybe using some external data that you didn't collect， maybe that's an option。

 but let's suppose none of these circumstances are available to you then you want to make sure you use skepticism of your results。

 you want to use skepticism in studying results and think about the noise associated with your surrogate variables。

And another reasonable strategy is to use sensitivity analyses for bias and variability of your surrogate variable。

 so what I mean by sensitivity analysis is come up with some idea of how off it's going to be for the individual measurements and come up with an idea of how bias it could possibly be so if you're studying a food frequency questionnaire you might think okay well what if you know what if these food frequency questionnaires are really underestimating calorie consumption by100 calories per day right think about that and then factor that end the analysis and see what would happen So sensitivity analysis are always at your disposal and they're a good way to sort of poke and prod at you know what are the consequences of not measuring what you really want to measure。

And I have this funny thing that says limitations until you spread your wings。

 you'll have no idea how far you can walk and there's a picture of a penguin I thought that was terrible。

 but I put it up anyway。

![](img/b9b4eae1349ea1ab3928805667a3404c_7.png)

And then when to throw in the towelu。 So I thought a lot about you know recommending when you throw in the towelu and so this is the resolution that I came up with is you know prior to running your analysis。

 think about how you're going to interpret your results and if the variable that you're going to use in lieu of the one that you really want is so unknown and so unreliable an estimate of what of the desired outcome that no results would change your decision or state of knowledge then why bother running the analysis at all。

 so what I I would do is go through the exercise before you perform the analysis before you collect the data and then kind of think about your decision space in the event that the results come out exactly as you would hope or in the event that the results come up the exact opposite of what you would hope is the fact that the。

Serrogate variable is so inaccurate relative to what you're trying to measure if that's true。

That in neither of those extremes， would it really change your decision space。

 then you either need to either improve your surrogate variable。

 do some gold standard studies or get a new variable or something like that because it's probably not worth doing at that point。

 but I do think if you have a really noisy surrogate variable is at least worthwhile to think about whether or not you're actually going to get anything valuable at all out of your analyses before you undertake the costly exercise of actually doing it。

Okay， well thank you for your time and I look forward to seeing you in the next lecture。



![](img/b9b4eae1349ea1ab3928805667a3404c_9.png)

![](img/b9b4eae1349ea1ab3928805667a3404c_10.png)