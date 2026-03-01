# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p65 17_阴性对照.zh_en -BV1L9Fde5EXS_p65-

![](img/e297dc69f6ef8968c62097ce19363462_0.png)

Hi， this is the lecture on negative controls， so this is part of our discussion of looking at statistically significant or non significant results and adding meat to our hypothesis testing。



![](img/e297dc69f6ef8968c62097ce19363462_2.png)

And in this case， what we're concerned with is the problem of。

Did the process that we executed the hypothesis in。

 Was that what created the significance or was it a real， intrinsically true effect。 Okay。

 so let's restate the problem。 You're worried that your results are more due to process than a real effect。

 Well， how do you check。 Well， there's a lot of ways。

 and and a lot of the mechanisms of statistical significance are trying to check against that。

 they're evaluating your results relative to the uncertainty in your data and so on。 But this。

 what I'm about to present is a very practical solution for that。

 just to sort of a real sort of more data scienceency way to think about it。

 And the idea is to perform a negative control。 And you're basically going to repeat the study for a variable that is known to have no association。



![](img/e297dc69f6ef8968c62097ce19363462_4.png)

![](img/e297dc69f6ef8968c62097ce19363462_5.png)

So let me give you a very famous example in the area that I work in。



![](img/e297dc69f6ef8968c62097ce19363462_7.png)

What everyone is talking about in brain activation studies now is in this idea of connectivity。

 that two different areas of the brain， their brain activity tends to track with one another。

And that's the idea of so called connectivity。It's interesting to note that。

What someone did at one point is they used all of these tools that people like me and other people that work in the area have developed。

And they looked at them in an area of the brain where there is no brain， the ventricles。 Okay。

 so in the ventricles， there's nothing but cerebralpinal fluid。 So there's nothing there。

 And they used for two locations in the ventricles。

 They used the same techniques that we used for two locations in the brain to study correlations or connectivity。

 as we like to call it。And what they found is significant results。

And that's an interesting finding because there's no brain there。 So it's not brain connectivity。

 They're finding it's purely has to do with process。

 And what they found out is that this was due to a couple of interesting artifactual components of the data。

 One， it was due to sort of head motion as people moved their head。

 it created similar patterns in the two locations in this area of the ventricles and that caused correlations。

 those effects permeated the rest of the image， So it's a lot of what people were reporting as connectivity was really due to head motion。

 it's also true that as we breathe。 and as our heartbeats。

 that changes the character of the signal dynamically。

 and those were also related to creating spurious correlations。 The broader point， though。



![](img/e297dc69f6ef8968c62097ce19363462_9.png)

Is that what these investigators did is they used some they repeated an analysis that everyone was excited about。

 everyone was excited about finding remote correlations in the brain that were putatively brain networks and understanding how they related disease and stuff like that。

However， what these researchers did is they said， okay， well。

 let's just study the process by looking at an instance where we know there can't be an effect。

 but in every other sense， we've replicated the analysis in exactly the same way。

 and they found an effect。So these kinds of negative controls offer a very simple way to investigate spurious effects due to things like confounding or multiplicity。

 In this case， it was confounding the correlation between these two voxels was actually confounded by head motion。

 for example。So what are the characteristics of a good negative control well they are variables that are realistic but known to have no association so in this case they had a perfect one。

 they had something that was in the image already that they could look at it was subject to the same all the same processing experience that the rest of the brain got and so you know this was a good version of a negative control if there's one criticism of negative control。

 it's often very hard to find something where you know for sure there can't possibly be an effect。

So another strategy that people employ rather than executing things like negative controls is they do things like permutation tests。

 they actually formally break the association by permuting one of the variables so that there can't be an association they've broken it so that's a little bit more of an advance of a topic。

 but the idea is quite similar so this is a simple technique and if you're feeling queasy about a process that one of the people you're managing went through a very long complicated set of data muing and analysis and several models being built ask them to just repeat the whole process for something that is on face value can't possibly exhibit an association and see what comes out and it is a great way to you know just to offer a sanity check and to check influences due to process。



![](img/e297dc69f6ef8968c62097ce19363462_11.png)

![](img/e297dc69f6ef8968c62097ce19363462_12.png)

![](img/e297dc69f6ef8968c62097ce19363462_13.png)