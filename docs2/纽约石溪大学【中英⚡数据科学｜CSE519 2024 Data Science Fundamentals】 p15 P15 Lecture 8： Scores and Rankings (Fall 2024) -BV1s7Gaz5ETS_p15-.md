# 纽约石溪大学【中英⚡数据科学｜CSE519 2024 Data Science Fundamentals】 p15 P15 Lecture 8： Scores and Rankings (Fall 2024) -BV1s7Gaz5ETS_p15-

![](img/23043044be61ca7fcf7fa31ac5c610e7_0.png)

First of all， let's start with how are people doing on the homeworks。

 how many people have made a pass through their homework and you have made a first pass through everything？



![](img/23043044be61ca7fcf7fa31ac5c610e7_2.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_3.png)

I see some enthusiastic waves and some twitching， so that's good。

 and how many people have not yet done that？

![](img/23043044be61ca7fcf7fa31ac5c610e7_5.png)

I see you become more enthusiastic which back there， but okay， so any questions about the homework。

 okay yeah。

![](img/23043044be61ca7fcf7fa31ac5c610e7_7.png)

ForQuestion8， do you want us to do the part I？Like for seven， you have a part I。



![](img/23043044be61ca7fcf7fa31ac5c610e7_9.png)

Essential，Do you want us to break down question8 into part one and two， so we do the same thing？



![](img/23043044be61ca7fcf7fa31ac5c610e7_11.png)

Okay， that seems harmless， although has anybody done part1，71？😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_13.png)

The people that might do good or bad。😡。

![](img/23043044be61ca7fcf7fa31ac5c610e7_15.png)

Seeing terrible， anybody else say good or bad？Bad okay， so in that case。

 maybe you could do both or you could think about why you're doing bad。😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_17.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_18.png)

anybody who did great， somebody did great on Piazza， as I recall。

Did people see that posting or was that just me？

![](img/23043044be61ca7fcf7fa31ac5c610e7_20.png)

And I think that that person used the target variable as one of the features。😡，Okay。

 so that's probably why they did great。

![](img/23043044be61ca7fcf7fa31ac5c610e7_22.png)

So for problem one， you're doing， youre saying for both parts one and two。

 you're doing bed on both of them。😡。

![](img/23043044be61ca7fcf7fa31ac5c610e7_24.png)

a little better on two， that surprises me a little bit because it's in're predicting it from the year。



![](img/23043044be61ca7fcf7fa31ac5c610e7_26.png)

After。Okay。Any comments about this， any ideas or thinking about this？



![](img/23043044be61ca7fcf7fa31ac5c610e7_28.png)

CanHave anybody looked at the features and tried to figure out why you're doing badly on even the first part？



![](img/23043044be61ca7fcf7fa31ac5c610e7_30.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_31.png)

Okay， yeah， there is only one teacher that。

![](img/23043044be61ca7fcf7fa31ac5c610e7_33.png)

Only one feature calculates earnings per share， and what was that？



![](img/23043044be61ca7fcf7fa31ac5c610e7_35.png)

Estimated shares outstanding， okay。

![](img/23043044be61ca7fcf7fa31ac5c610e7_37.png)

Let's think what the variables mean。 Okay， this is what I want people to think about for a second。

 What were the variable， first all estimated shares outstanding， What was that。

 what does that measure。😡。

![](img/23043044be61ca7fcf7fa31ac5c610e7_39.png)

That I'm assuming is a measure of how many shares there are， Does everybody agree with that？😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_41.png)

Okay。

![](img/23043044be61ca7fcf7fa31ac5c610e7_43.png)

What do the other features have to do with？😡，What are the other features that you're using in that one？

😡。

![](img/23043044be61ca7fcf7fa31ac5c610e7_45.png)

What net income and what is net income measured in？😡，Dollars。

What are the rest of the things measured in？

![](img/23043044be61ca7fcf7fa31ac5c610e7_47.png)

Okay， does anybody else look at any of the names of the features。

 what are the features measured in that you're using for the regression problem？



![](img/23043044be61ca7fcf7fa31ac5c610e7_49.png)

Yeah。What？Capital surplus。 And what's that measured in。

 Is that measured in inches or what's that measured in。



![](img/23043044be61ca7fcf7fa31ac5c610e7_51.png)

Comppic。It shared higher price to its results。

![](img/23043044be61ca7fcf7fa31ac5c610e7_53.png)

What's the units on that。Everything is on dollars， okay？😡。

So you're telling me if I'm understanding it and I don't know if you're doing it right or not or anything like that。

 you're telling me that you have a bunch of features that are trying to predict to try to predict earnings per share。

😡。

![](img/23043044be61ca7fcf7fa31ac5c610e7_55.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_56.png)

Okay， all of them are dollars and one of them is the number of shares， right？😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_58.png)

And what is the and you the only one that was useful was the number of shares number of shares。



![](img/23043044be61ca7fcf7fa31ac5c610e7_60.png)

That revenue year and that income， something like that goes to it。



![](img/23043044be61ca7fcf7fa31ac5c610e7_62.png)

Okay， I don't do that people have any other experiences with this。



![](img/23043044be61ca7fcf7fa31ac5c610e7_64.png)

Yeah。You're saying there were ratios there。😡，Okay， there were some ratios there that made a difference。

 Those were not measured in dollars， right？Any other experiences people had？



![](img/23043044be61ca7fcf7fa31ac5c610e7_66.png)

Okay， you know， neitherless say I don't actually do any of this stuff。

 but but I'm wondering to myself when I hear look at this。😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_68.png)

Is there some way is what are you trying to predict in earnings per share， right？😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_70.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_71.png)

Now what happened to this company， to the earnings per share if there was a stock split right before it？

😡。

![](img/23043044be61ca7fcf7fa31ac5c610e7_73.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_74.png)

Let's say that there was a stock split where the earnings per share。

 where they did a two for one split。

![](img/23043044be61ca7fcf7fa31ac5c610e7_76.png)

What's going to happen to earnings per share？decrease by what？So is that going to be able to be seen。

 for example， in your model？😡，No。Is there any way that you guys can think that maybe you can make those dollar figures into something features。

 into something that might be better？

![](img/23043044be61ca7fcf7fa31ac5c610e7_78.png)

At predicting earnings per share。Any ideas？

![](img/23043044be61ca7fcf7fa31ac5c610e7_80.png)

What happens if you're telling me what happens if you had these earnings numbers？😡。

Would the earnings numbers be likely more valuable if they were by the number of divided by the number of shares。



![](img/23043044be61ca7fcf7fa31ac5c610e7_82.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_83.png)

Okay， this seems to me to be an A A A something I haven't done anything。 How do I know。



![](img/23043044be61ca7fcf7fa31ac5c610e7_85.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_86.png)

But I do know that when you're doing that， you're now starting to build your model out of features that are of comparable things to it。

 Is everybody going to see that。Can anybody see why linear regression doesn't pick up on this？😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_88.png)

Can anyone give me an idea why linear regression wouldn't pick up on this。

 you know the fact that dividing by the number of shares might be a useful thing？



![](img/23043044be61ca7fcf7fa31ac5c610e7_90.png)

It's because it's linear， okay， and maybe if you you know a transformation like something being one variable divided by another is not something that falls out of that features。

 okay？😡。

![](img/23043044be61ca7fcf7fa31ac5c610e7_92.png)

Any questions about that， do people see an idea possibly？😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_94.png)

Or was I too opaque， how we see what I was saying？Nobody how people don't see what I was saying。



![](img/23043044be61ca7fcf7fa31ac5c610e7_96.png)

A few people twitching， okay？Again， you've got variables where you're trying to predict a ratio of what you call it。

 the earnings per share。😡。

![](img/23043044be61ca7fcf7fa31ac5c610e7_98.png)

And you've got features that are earnings and you've that are basically earning dollar things。😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_100.png)

And you've got sheer things， okay？

![](img/23043044be61ca7fcf7fa31ac5c610e7_102.png)

One possibility is to change the。

![](img/23043044be61ca7fcf7fa31ac5c610e7_104.png)

See what happens if you air to transform the dollar things into dollars per share， okay。

 that might be an interesting thing。

![](img/23043044be61ca7fcf7fa31ac5c610e7_106.png)

So another way to accomplish the same thing。😡，Maybe more easily。

IfWe want to get the effect that recognize it that that you have unwashed dollars and you've got shares。

 is there some way to change so we could change the features， perhaps？



![](img/23043044be61ca7fcf7fa31ac5c610e7_108.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_109.png)

Is there anything else you could change？What does normalization mean， what do you normalize？😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_111.png)

So Z scores might be something， does's a beta think of z score before you've normalized it though by share。



![](img/23043044be61ca7fcf7fa31ac5c610e7_113.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_114.png)

justのら。

![](img/23043044be61ca7fcf7fa31ac5c610e7_116.png)

Just to normal it may， Z scores will well maybe we'll talk a little bit about Z scores did more today。

 but still Z scores will transform the variables。

![](img/23043044be61ca7fcf7fa31ac5c610e7_118.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_119.png)

So they are comparable in magnitude and range， that's kind of what Z scores will do。😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_121.png)

Now they won't do nonlinear transformations， a translation where I convert from feet to meters is a linear transformation。

 I'm multiplying it by a constant， right？😡。

![](img/23043044be61ca7fcf7fa31ac5c610e7_123.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_124.png)

If I multiply it by a constant and subtract the mean。

 that's still going to be a linear transformation。😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_126.png)

Now， sometimes the variables might have a need for nonlinear transformations， okay？😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_128.png)

And I think that's what's happening here is that there is probably an obvious incompatibility。😡。

Between your variables and your target， okay？😡，And so one proposal if you're trying to predict earnings per share。

 might be to manipulate the variables， so they are by share， right？😡。



![](img/23043044be61ca7fcf7fa31ac5c610e7_130.png)

![](img/23043044be61ca7fcf7fa31ac5c610e7_131.png)