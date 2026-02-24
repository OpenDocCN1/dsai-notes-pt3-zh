# 密歇根大学《数据科学伦理｜Data Science Ethics》中英字幕 p26 25_属性与指标的选择.zh_en -BV1EGaVzeEbQ_p26-

![](img/0800bca53719ea95d9f2410b995bb479_0.png)

We have to choose what attributes we use and how we'll measure them。



![](img/0800bca53719ea95d9f2410b995bb479_2.png)

And what metrics we will have for our objectives。And these are important things as we set up our data analysis。

Let's begin by looking at what attributes we choose。

This is something where our choice is usually limited by what is available。

If there are only some properties that we know of the things that we are trying to deal with。

That's what we have。Well， it's possible that additional attributes can sometimes be purchased or collected。

And determining what that might be requires a cost to value trade off。

And it's important to think about what attributes are missing。In other words。

To make this less abstract。Let's say that we're trying to decide。Whether to hire someone。

And we look up what we know about them on the Web。And from their application。

And whatever else we know about with respect to their record。The question is。

Do we know anything about， let's say， what time they go to bed。

 And perhaps that's important because of the nature of the job that they're being hired for。

 And that is something that maybe one could determine if one had a smart electric meter in their home from which we could buy data。

 but otherwise is something that is an attribute。 we probably do not have access to。

There are many choices of this type that a data scientist has to make in just setting up。

The problem that they're trying to solve。There are also attributes that they may decide to leave out。

And sometimes what they are going to leave out is something that's dictated by law。

 So for many purposes， you cannot consider the race of a particular individual。 if that is the case。

 then even if you know a person's race， that is something that you would not consider as input to your algorithm or your analysis。

Just as you're making choices with respect to your attributes。

 you're also making choices with respect， to。The metric against which you're going to evaluate your output。

So let's consider an example。 This is a real life example。

 Kim Kardashian has 15 million followers on Twitter and a particular company X paid her to tweet about its products。

 Now， here's what happened。 She had 15 million followers。

 of15 million people presumably saw her tweet about company X。

1wel00 of these visited the company Act's website。30 of these 1200 placed orders。

Worth $30 each on average。So the company got 900 in sales。

And there's still some question of whether all 90 of these were attributable to a Kardashian tweet。

 maybe some of these would have bought。Product from the company anyway。

 it's also possible that there were people who saw her tweet didn't immediately visit the company's website and came by later and and they're not accounted for in the 900。

 Let's worry about these things later。 Let's sort of ignore these。

 This is a very standard kind of how data analysis gets done。 We just made a big assumption about。

 oh， yeah， there are these questions。 We don't know the answers to these。

 Let's assume those things are0。And do I know that's a good assumption， No， I don't。

And if those assumptions are bad， my results of the analysis are going to be bad。

But sticking with that assumption for a minute。The question is。

 if we want to figure out the value of。Buying Kcors time for this tweet。

There are many ways you can do this。 You can say， hey。

 I got 15 million people to have an impression to see my a。Okay， and it's worth， let's say。

 a 10th of a cent per view。So。Havingaving kim kian do this for me is worth fifteen thousand dollars because she has fifteen million followers。

Another way to do it is。It's worth a dollar to me。For every new customer who comes through my store。

So Kim Kdaian was able to get 1，200 people to visit my website。

And since each new visitor is worth a dollar， that is worth $1200。The third way to do it is to say。

Well， I wna measure how much profit I got because of this。So I got $900 in sales。

And let's say I have a 20 per cent profit margin。So I got 1 hundred80 of extra profit because of this week。

And so if I've got to do a contract and the question is。

 how much should I be willing to pay for her to tweet？About my company's product。

The answer could be anywhere from some fraction of $180 to some fraction of $15000。

 depending on what the measure is that I'm using。As the thing that I'm looking for。Well。

 here I kind of set up this problem。To make clear that what one is really looking at is the sales。

 and often one may not have that。 And therefore， one is pricing things on things like page views or impressions。

 and the results can be astonishingly different。