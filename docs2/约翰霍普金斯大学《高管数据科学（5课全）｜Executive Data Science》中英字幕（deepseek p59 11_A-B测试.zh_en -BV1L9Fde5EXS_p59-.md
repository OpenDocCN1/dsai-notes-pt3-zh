# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p59 11_A-B测试.zh_en -BV1L9Fde5EXS_p59-

Hi， my name is Brian Cathho and welcome to the lecture on A B testing as part of our executive data science specialization。

I'm going to start this lecture by posing one of the most fundamental questions of our time。

And that is。

![](img/18abae09a03470358b9cf728a8e1b36a_1.png)

How can Jeff sell more books， So Jeff is another one of the instructors in our specialization。

 and he does have a book called The Elments of Data Analytic style。It's a great book。

 Get it Off of Leo。😊，So imagine if Jeff had two Twitter's ad campaigns he'd like to compare to see which one was more effective。



![](img/18abae09a03470358b9cf728a8e1b36a_3.png)

The first one says a practical but non technical guide to data analysis， pay what you want， yada。

 yada， yada。And the other one says a book of non technical tips for analyzing data the right way。

你 cea。So he wants to compare these two ad campaigns。

 what are some possible strategies he might use to do that？



![](img/18abae09a03470358b9cf728a8e1b36a_5.png)

Well， one is he could run the ad serially。He could run for a couple of weeks， the first ad。

 then run the second one for a couple of weeks， maybe after a little bit of a washout period。

And then compare the conversion rate during the time periods of the two ads。Now。

 that has the problem that anything that he found， whether it's an effect of ad type or absence of effect。

 could also be attributed to whatever's alias with the time periods that he was studying。

 For example， imagine if the first ad ran during Christmas or major holiday。Then of course。

 people's purchasing patterns are different during that time of year than during a time where there isn't a major holiday。

 so he wouldn't be able to conclude that there's a difference or absence of a difference because of ad campaign because of this lurking variable。

And that's what we're going to study today。I think this idea of lurking variables and confounding underlies a lot of the issues with observational studies and why in particular in nutritional studies。

 we see kind of，Opposite results。 so often chocolate is good for us one week。

 and it's bad for us another week。And I saw this。Great article where it's a。A blogger， E magazine。

Written by healthcare journalist for healthcare journalist and the title of it wasDon't Fudge you the factsact on Cholate studiesudies。

 and it actually goes through many of the topics we're going to talk about today such as confounding。

 but chocolatelate is one of these examples where frequently it's associated with cancer。

 it's not associated with cancer etc， so I'd like to use chocolate today to discuss the issue of confounding and how randomization as is used in AB testing and randomized controlled trials。

 how that can help combat some of these issues。

![](img/18abae09a03470358b9cf728a8e1b36a_7.png)

And I made up a little data set and it's a little bit contrived。

 but kind of purposefully so so we can just focus on the concepts。

In this case we have two groups to the left， the group of people who eat chocolate and to the right。

 the group of people who don't eat chocolate， we're interested in ascertaining whether or not chocolate lowers our blood pressure for whatever the reason。

So everyone who has a smiley face， has low blood pressure and everyone who has a frownie face has high blood pressure。

 and if you were to look at this data set where we just observed people's chocolate eating patterns and compared the two groups。

 you'd see five out of eight for the chocolate group and three out of eight for the non-chocolate group had low blood pressure。

Or had normal blood pressure。And so you might conclude that if there was enough subjects of this sort。

 maybe let each smiley face represents a thousand people or something like that。

 then you would conclude that there's a significant difference associated with chocolate。However。

 imagine if there is a lurking variable in this case。

Imagine that the lurking variable is whether or not the subject is taking antihypertensive medication。

 something that's clearly related to blood pressure， and in this case。

 the group of people who are naturally eating chocolate happen to have a much higher percentage of people who are taking these antihypertensive medications and if you count five out of seven for the red faces。

 the people on the medication， three out of nine for the blue faces of being happy there's a greater percentage of people with lower blood pressure on the antihypertensive medications likely due to their medications so in this case。

 you can't really ascertain whether this effect is due to the chocolate or due to the antihypertensive medications we haven't you know for this madeup example I think we'd all probably conclude it's likely due to the antihypertensive medications。

So how can we combat this ideally we'd like to compare two groups with an equal mixture of people who are on medication versus not。

 or we could fix medication and compare just among those taking medication。

 their chocolate eating habits and just among those not taking medication。

 their chocolate eating habits， of course that latter strategy requires us to know what variables we need to control for and have measured them。

Rranandomization， on the other hand， is an attempt to try to balance the observed and unobserved variables that may contaminate our results in randomization。

 we simply randomize every subject in this case， you randomize them and say。

 go eat a bunch of chocolate and randomize the other group and say you're not allowed to eat chocolate The problem。

 the fundamental problem， of course， with randomization， in many cases， like this one。

 you can't ethically carry out a ethically or practically carry out a randomized trial。

So the goal of randomization again is to compare like with like。

 get apples to apples and oranges to oranges， in other words the groups that you're comparing have roughly equal proportional mixtures of all the lurking variables that are associated that are typically associated with the predictor and with the outcome。

 and you've broken that associated with the treatment by virtue of the randomization。

And I'll give you this wonderful quote that I think summarizes this idea very neatly。

 it's by R Fisher， one of the early pioneers on the subject of randomization。

And he said randomization properly carried out， relieves the experimenter from the anxiety of considering and estimating the magnitude of the innumerable causes by which his data may be disturbed。

 this quote， by the way， I found in a wonderful paper by Armitage on Fisher Bradford Hill and randomization。

 a discussion of some of the early thinking on randomization。😊，Let's return to our example。

And see what would likely have occurred if we had randomization。Well。

 it would make at least with high probability， the treated and untreated groups having roughly equal proportions。

of people on antihytensive medications and people not， and in this case we got the opposite result。

 three out of eight for chocolate and five out of eight for no chocolate so as an example。

 now the effect actually reverses itself when we perform the randomization。



![](img/18abae09a03470358b9cf728a8e1b36a_9.png)

I'd like to close this lecture by asking the question， is randomization of cure all。

 is it all we need to think about for trying to solve some of the problems with observational studies？

And the answer， of course， by posing this question is no。



![](img/18abae09a03470358b9cf728a8e1b36a_11.png)

And one particular way in which bias can creep back into randomized studies is through missing data。

And I concocted an example where in this case， for the chocolate group， it's just like before。

 three out of eight， it's the same set of smiley faces in Friday's faces as before。

 but for the noncholate group， almost every person who was not taking antihysive medications dropped out of the study。

They said for whatever the reason most of them were frowning faces， so they were saying I've got。

You know， I've got high blood pressure， I feel like eating some chocolate， whatever。

 they dropped out of the study。And so now the comparison is contaminated again by the fact that the groups aren't directly comparable。

 the mixture of antihypertensive medication folks is different in the two groups。So。

Just as a and again， the specifics of all the different ways in which AB test or a randomized trial can fail is perhaps out of the purview of this class。

 but I just want to emphasize the fact that just because you've randomized the necessary things to think about don't just end there。



![](img/18abae09a03470358b9cf728a8e1b36a_13.png)

So at any rate I'd like to summarize this lecture and the fundamental point of this lecture is the main characteristic of AB testing。

 which is the main characteristic of randomized trials in the medical literature。

 is the idea of using randomization to balance these confounding factors in lurking variables that would otherwise contaminate your results and the benefit is that they hopefully at least with high probability will balance both the known confounding factors and unknown ones as well。

So I hope you enjoyed today's lecture and I look forward to seeing you in the next class。

