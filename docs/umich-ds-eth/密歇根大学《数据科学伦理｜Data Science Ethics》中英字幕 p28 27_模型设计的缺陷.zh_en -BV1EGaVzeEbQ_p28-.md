# 密歇根大学《数据科学伦理｜Data Science Ethics》中英字幕 p28 27_模型设计的缺陷.zh_en -BV1EGaVzeEbQ_p28-

![](img/3489cd9895cceb0a24f9a04fb42a1edf_0.png)

You could end up with invalid conclusions from your analysis because of errors in model design。

 even if you had perfect inputs， perfect data going in。



![](img/3489cd9895cceb0a24f9a04fb42a1edf_2.png)

There are many ways why the model could be incorrect。You have errors in your model structure。

 you're doing extrapolation。You're doing feature selection。

And there are some more fancy things that we will get to。

 So let's look at all five of these things in turn。First， let's look at a question model structure。

A thing that is important to keep in mind。Is that most machine learning just estimates parameters to fit a predetermined model。

How do you know that the model you have is appropriate。Quite often。

 we end up choosing a very simple model。Not because we know that the simple model is going to work。

 but simply because that's easy。And so if you have a complex nonlinear process that's going on in the world。

And you've decided to build a simple linear model。You can try to fit the data to your linear model。

 and you can learn the best linear fit。It's not going to be perfect。

And you're going to make a decision on whether that correctly represents anything or not。

This kind of。A situation becomes particularly problematic when you have to do things like extrapolation。

So， here's this。Simple data， two dimensional data， where you said you've got a perfectly linear graph in the range from 1 to 4。

And now you want to say， well， y equals 7， Y is x equal to。Well， we really don't know。

Perhaps we can assume since it's so nice and linear between one and 4 that it'll continue to be linear。

From 4 on through 7。But， perhaps not。Maybe the real world is extremely nonlinear。

 and our choice of linear model was wrong。And so extrapolation， in particular。

 is something that can be very dangerous unless we have reason to know that our model is correctly chosen。

There's an issue of feature selection。Did you know， for example。

 that taller people are more likely to grow beards。No， you say。Why is that true。Well。

 here's the logic。Women are generally shorter than men。Women don't grow beards。

So if you look at the population at the universe of people who have beards， we're all men。

Since men are generally taller than women， people with beards are generally taller than people without。

Notice。That this happened because we have a large fraction of about half the population。

Who don't have beards and tend to be shorter。I did a perfectly reasonable， correct analysis。

Came out with a factual statement， which is on the first bullet here of the slide。

 which is completely true。But it doesn't tell us the first thing about taller versus shorter men。

And that actually is the question that's perhaps much more interesting。

Here's a related problem that we have。Often， we have aggregated data。

And so we'll analyze results for a group。And based on this analysis of group data。

 well ascribe results to the individual。For example。

Suppose we have data at the district level that tells us the districts with higher income have lower crime rates。

Well， from here。We may be tempted to infer。That richer people are less likely to commit crimes。

Actually， this inference doesn't follow from the aggregate data。

That is a possible reason why we might have got the aggregate result that we got。

But there are other possibilities， too， having to do with the way。

We have the distribution of people with incomes and crime rates and districts。One particular case of。

This kind of fallacy is something called the Simpsons paradox。 And let's walk through an example。

Let's say that we are worried about。Genner discrimination。And。

I have the simple matrix here of two universities， easyy university and hard university。

And let's look at the acceptance rates of these two places。So reading the first row of this table。

10 men applied to E university， seven of them were accepted， so that's a 0。

7 acceptance rate or a 70% acceptance rate。5 women applied。4 were accepted。So we have a 0。

8 acceptance rate。So if we look at E University。The acceptance rate for women is greater than the acceptance rate for men。

Now， let's look at Harvard University。Hard University is much harder to get into。10 men applied。

 only three garden。So the acceptance rate for man is 0。3。15 women applied。

And 5 got in an acceptance rate of  one third or 0。33， which， again。

 is a little bit higher than the acceptance rate for men。So again， at Hard University。

Women are accepted。At a slightly higher rate than Matt。But now let's look at the last row。

 which is the aggregate data of easy and hard combined。

So if you look at all the universities put together。20 men applied。10 were accepted。And so，50%。

20 women applied， and only 9 would accept it。So it's 0。45。And there are fewer women being accepted。

T man to universities。What's the problem here。This is known as Simpson's Paradox。

And this arises because the aggregate data is reflecting。The combination of。

Two separate ratios where the number of candidates in the two columns isn't the same in the two。

So many more women than men apply to hard you。And since the acceptance rates at hard you are so much lower than the acceptance rates at easy you。

The overall result that we're seeing。Is reflective of more women applying to hard you rather than of discrimination against women in this made up example。



![](img/3489cd9895cceb0a24f9a04fb42a1edf_4.png)