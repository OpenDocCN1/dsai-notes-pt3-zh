# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p55 7_实验设计与观察分析.zh_en -BV1L9Fde5EXS_p55-

![](img/7324e97a6d66eebe1dcbf937dd90ea3b_0.png)

Hi， my name is Brian Kaffho and this is a lecture on experimental design and observational analysis。

I'm going to begin this lecture with a quote from RA Fisher。

 one of the forefathers of modern statistics， and probably the greatest thinker ever about experimental design。



![](img/7324e97a6d66eebe1dcbf937dd90ea3b_2.png)

And he said to call in the statistician after the experiment is done may no more than asking him to perform a postmortem examination。

 he may be able to say what the experiment died of。

So in this lecture we're going to talk about the difference between experimental design and observational studies and so let me go a little bit deeper into what these two subjects are really talking about experimental design is the case where you have tight control over several aspects of the experiment。

So good experimental design can do things like account for known important factors through things like blocking and stratification。

In addition， it can account for unknown factors through randomization willll have an entire lecture on randomization。

Experimental design in terms of getting a good sample via random sampling can help us get an unbiased sample for extrapolating to the population that we're interested in extrapolating to。

If you execute good experimental design and everything goes well。

 often it eliminates the need for complex analysis。

 simple analyses usually suffice and are better in these settings。

And they help us isolate the effects of interest。In contrast in an observational experiment。

 this is the opposite setting where you don't have tight control over the experiment at all and you can't have good control over the sample。

 you can't randomly assign treatments and these sorts of things in a purely observational experiment。

 you're just observing the data collecting it as it occurs okay and this has some benefits as well。

 for example， it's often feasible when designed experiments or not。 you can't， for example。

 ethically。Randomize people in a smoking trial， right。

 You can't randomize some people to have to smoke and other people to not。

As a consequence of just getting the data as it rolls in。

 often both by necessity and just by happenstance， observational studies often have very large sample sizes。

They're usually a lot cheaper to execute as well， the process of designing experiment and if you're collecting data on。

 for example， medical trials， clinical studies are extremely expensive。

 thousands of dollars per subject， often observational studies can get much larger sample sizes and thus by having a much lower dollar cost per record。

However， on the negative side， in order to get things out of observational data analysis。

 you often to need much more complex modeling because you haven't been able to do things like control for known important factors as part of the design。

 you haven't been able to inject randomization into your analysis to help control for the unknown factors so you have to try to figure out and measure everything possible。

Okay， so it's often the case， it's almost always the case that an observational study needs these larger sample sizes to accommodate the much more complex analysis that you have to do to study them。

And by the way， this picture here on the slide， statistical methods。

 experimental design and scientific inference by RA Fisher is sort of a classic in this area。

 Fisher was one of the forefathers of the thinking on modern experimental design。

So all I want to do is really set the stage for the next couple of lectures where we're going to cover several key topics of experimental design versus observational analyses。

As an example， we'll do to talk about sampling and bias。

 and we'll give the specific example of when the Chicago Tribune announced errantly the Dewey defeated Truman in the presidential election。

 and much of their error was in his particular form of bias sampling。

 the collection of people that they pulled weren't the right collection of people to make the conclusions that they were interested in。

We'll talk about randomization in AB testing， so randomization is the process when you have a treatment or something that you're interested in studying that's say has two levels of randomly assigning the observational units to those two levels。

And the benefit so the classic example of this is in a medical trial where you have a drug or something like that and you give a random set of people the drug and you give another random set of people。

 the placebo and the idea is that the group of people that receive the drug and the group of people that receive the placebo other than receiving the drug or the placebo are otherwise similar so you're comparing apples to apples or oranges to oranges if you will。

 because the randomization is help ensured that everything else that might contaminate our results was at least equally distributed among the groups with high probability。

 so we'll have a lecture on randomization and this forms the basis of so-called clinical trials and AB testing which are bedrock methods in data science and biostatistics。



![](img/7324e97a6d66eebe1dcbf937dd90ea3b_4.png)

Confounding is another core topic that occurs in observational data analysis when you don't have randomization and you need to think about variables that can contaminate your results。

 you have to think about confounding， and here Jeff came up with this funny example of the number of people who drowned by falling into a pool。

 how it correlated with films that Nicholas Cage appeared in。



![](img/7324e97a6d66eebe1dcbf937dd90ea3b_6.png)

![](img/7324e97a6d66eebe1dcbf937dd90ea3b_7.png)

And finally， we're going to talk about causal inference and counterfactual。

 So causal inference is the idea of trying to use observational or experimental data to get a true statistical cause rather than just association。

 And we're going to only consider one particular way of thinking about causal inference。

 and that's the idea of a counterfactual。 where you consider two states of existence。

 One where a person has received the treatment， for example， and one where a person is not。

 And in this case， the same person is in both these pictures。

 This is Christian Bale in both in both pictures。 So counterfactuals are the idea of thinking along the lines of。



![](img/7324e97a6d66eebe1dcbf937dd90ea3b_9.png)

What would happen to each of my observational units if they didn't get the treatment that they actually received？

 So， of course， you don't actually get to observe this。

 You only you know if you give a person a drug， you only get to observe them after they've had the drug。

 You don't get to observe what would have happened had they not received the drug okay but counterfactual thinking forms the basis of causal thinking so we'll have a lecture on that That way of thinking will help us a。

 and I think I hope after that lecture， you'll see this will help us a improve the way we come up with statistical designs to to analyze data because we'll be thinking causally。



![](img/7324e97a6d66eebe1dcbf937dd90ea3b_11.png)

And B， it'll help us think about observational data analysis in a way that will will help us question our assumptions so that we can think about if we're going to try to make the leap from associations to causation。

 What sort of assumptions are we making to do it。 So hopefully you'll get a lot out of that lecture。

 The final thing I'd talk about is blocking。

![](img/7324e97a6d66eebe1dcbf937dd90ea3b_13.png)

And in blocking， this comes from the idea of agricultural experiments where you have a field where there might be some sort of gradient。

 for example， the water is distributed differently along rows of the crops or the soil is distributed differently and crops are tend to be conveniently actually sectioned into rows anyway。

 I have a picture of one here。So RA Fisher worked in agricultural experiments。

 so we actually talk about blocking， we tend to think in terms of these sorts of agricultural experiments。



![](img/7324e97a6d66eebe1dcbf937dd90ea3b_15.png)

So the idea， if you know that something like the soil or the water along rows of your crops may impact the outcome that you'd like to study like your crop yield。

Then if you're going to do something like randomization， why not do it within the rows。 Okay。

 so make sure you condition on the row， Okay， and and randomize within within the rows。

 So and this is the process of blocking。 Another example that occurs often in genomics is。

 let's say suppose you're studying mice。 and the mice have litters。 Okay。

 so every collection of parents of a litter， they might have five or six mice in a litter。 Okay。

 there's genetic inheritance that occurs from the litter。 So if you're studying something。

 why not randomize it within litters of mice rather than to all the little mice regardless of what parents they had。

The reason for blocking on parents right is to control whatever genetic factors are associated with the parents。

 So that's another example。 Blocking is another example of experimental design that we'll cover。

So hopefully this has given you a bird's eye view of some potential techniques that you can use that to think about observational data now and experimental design and hopefully after this lecture。

 you know that there's a dichotomy between instances where you have the idealized setting where you have complete control over the whole experimental process versus the other end of the spectrum where you have no control and you have purely observational data and of course there's lots of gray areas in between。

 but hopefully this will get you thinking about the strengths and weaknesses and potentials and pitfalls of each of the different sorts and in the next couple of lectures we're going to go over some of the details。



![](img/7324e97a6d66eebe1dcbf937dd90ea3b_17.png)