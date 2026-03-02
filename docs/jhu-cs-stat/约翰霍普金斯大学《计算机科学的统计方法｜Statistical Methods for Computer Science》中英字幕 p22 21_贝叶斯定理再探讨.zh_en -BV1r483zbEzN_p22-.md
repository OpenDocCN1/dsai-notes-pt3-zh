# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p22 21_贝叶斯定理再探讨.zh_en -BV1r483zbEzN_p22-

![](img/924315ce17dd4f43c31f1babe08e220a_0.png)

All right， we're going to revisit Bays rule， right， so revisit Bays rule， and I want to revisit。



![](img/924315ce17dd4f43c31f1babe08e220a_2.png)

Bes。

![](img/924315ce17dd4f43c31f1babe08e220a_4.png)

Right we've done， I've thrown out Bays rule for you。

 I kind of showed it to you with that table of language and music and I want to we did some problems with it to try and give you some intuition。

 but I want to try and get some better ideas right So if I draw a space here。



![](img/924315ce17dd4f43c31f1babe08e220a_6.png)

![](img/924315ce17dd4f43c31f1babe08e220a_7.png)

![](img/924315ce17dd4f43c31f1babe08e220a_8.png)

I draw a space and we have。Two circles here。

![](img/924315ce17dd4f43c31f1babe08e220a_10.png)

two circles。And I call this sample space A and this B。



![](img/924315ce17dd4f43c31f1babe08e220a_12.png)

![](img/924315ce17dd4f43c31f1babe08e220a_13.png)

Okay， then this is。

![](img/924315ce17dd4f43c31f1babe08e220a_15.png)

This is。AB， that's the AB space。 and this is， if I say that a。



![](img/924315ce17dd4f43c31f1babe08e220a_17.png)

![](img/924315ce17dd4f43c31f1babe08e220a_18.png)

Equals A B。

![](img/924315ce17dd4f43c31f1babe08e220a_20.png)

Yunyian a。😔，B complement， right， So this is the complement like what's not included in Bay， B。

 This becomes A B complement， right， A B complement。



![](img/924315ce17dd4f43c31f1babe08e220a_22.png)

![](img/924315ce17dd4f43c31f1babe08e220a_23.png)

So in this case， AB。

![](img/924315ce17dd4f43c31f1babe08e220a_25.png)

![](img/924315ce17dd4f43c31f1babe08e220a_26.png)

And。A B complement are mutually。Mute mutualch Wal。Exclusive。



![](img/924315ce17dd4f43c31f1babe08e220a_28.png)

If you have an observation in AB， it cannot be an AB complement because by definition。

 the complement is outside of B， you can't be in both spaces。

 so there's a picture of what that looks like。

![](img/924315ce17dd4f43c31f1babe08e220a_30.png)

![](img/924315ce17dd4f43c31f1babe08e220a_31.png)

So。When I look at the probability of A， given this definition。



![](img/924315ce17dd4f43c31f1babe08e220a_33.png)

![](img/924315ce17dd4f43c31f1babe08e220a_34.png)

I'm saying， is the。Probability of a is going to equal the probability of A and B。



![](img/924315ce17dd4f43c31f1babe08e220a_36.png)

Plus。The probability of A。

![](img/924315ce17dd4f43c31f1babe08e220a_38.png)

B complement。 what's not in A B， right， And that would give me probability。

 So that's a way that we can kind of list out that probability。 Well。

 I know from Bay's rule that the probability of A and B is equal to the probability of a given B。



![](img/924315ce17dd4f43c31f1babe08e220a_40.png)

![](img/924315ce17dd4f43c31f1babe08e220a_41.png)

![](img/924315ce17dd4f43c31f1babe08e220a_42.png)

Right times the probability of。

![](img/924315ce17dd4f43c31f1babe08e220a_44.png)

Big。And I can do something similar here， and I can say the probability of a given B compliment。

Is the probability of B complement times the probability B complement。



![](img/924315ce17dd4f43c31f1babe08e220a_46.png)

![](img/924315ce17dd4f43c31f1babe08e220a_47.png)

That can also be written， probability of B。plus probability of a given。



![](img/924315ce17dd4f43c31f1babe08e220a_49.png)

B compliment。Times1 minus the probability of b。

![](img/924315ce17dd4f43c31f1babe08e220a_51.png)

1 minus the probability of B。 And let me see if I want to do anything else there。



![](img/924315ce17dd4f43c31f1babe08e220a_53.png)

![](img/924315ce17dd4f43c31f1babe08e220a_54.png)

Given this。We're going to work a problem。

![](img/924315ce17dd4f43c31f1babe08e220a_56.png)

So if I look at example， I believe this is 3 a in your book， the problem says that。



![](img/924315ce17dd4f43c31f1babe08e220a_58.png)

30%。

![](img/924315ce17dd4f43c31f1babe08e220a_60.png)

Of people are accident。

![](img/924315ce17dd4f43c31f1babe08e220a_62.png)

Prone，30% of people are accident prone。嗯。

![](img/924315ce17dd4f43c31f1babe08e220a_64.png)

Accident prone people， accident。Prone。

![](img/924315ce17dd4f43c31f1babe08e220a_66.png)

Pibo。Or。

![](img/924315ce17dd4f43c31f1babe08e220a_68.png)

40% likely， 40% likely to have an accident。

![](img/924315ce17dd4f43c31f1babe08e220a_70.png)

Within one year。

![](img/924315ce17dd4f43c31f1babe08e220a_72.png)

Within one year。20%。

![](img/924315ce17dd4f43c31f1babe08e220a_74.png)

Of non accident prone people。

![](img/924315ce17dd4f43c31f1babe08e220a_76.png)

![](img/924315ce17dd4f43c31f1babe08e220a_77.png)

20% of non accident prone people are going to have an accident within one year。



![](img/924315ce17dd4f43c31f1babe08e220a_79.png)

What is the probability， what is the probability？

![](img/924315ce17dd4f43c31f1babe08e220a_81.png)

A new driver。

![](img/924315ce17dd4f43c31f1babe08e220a_83.png)

We'll have an accident。

![](img/924315ce17dd4f43c31f1babe08e220a_85.png)

![](img/924315ce17dd4f43c31f1babe08e220a_86.png)

Okay。So we're going to take advantage of this basic framework here。

 So the probability that a new driver is going to have an accident is going to be equal to the probability that there is an accident。

 a new driver accident given their accident prone。

![](img/924315ce17dd4f43c31f1babe08e220a_88.png)

Times the probability their accident prompt。

![](img/924315ce17dd4f43c31f1babe08e220a_90.png)

Well， the other part is the compliment that they're not accident prone， right？



![](img/924315ce17dd4f43c31f1babe08e220a_92.png)

So。

![](img/924315ce17dd4f43c31f1babe08e220a_94.png)

That's going to be added to the probability that they have an accident。



![](img/924315ce17dd4f43c31f1babe08e220a_96.png)

Right， given the compliment that they're not accident prone。



![](img/924315ce17dd4f43c31f1babe08e220a_98.png)

Times the probability that they're not accident prone， right So look at the same structure， right。

 We have P right instead here we have one thing given another times the probability of that right That's the bayes rule plus。



![](img/924315ce17dd4f43c31f1babe08e220a_100.png)

![](img/924315ce17dd4f43c31f1babe08e220a_101.png)

Probability， right。Compliment times of probability to complement。



![](img/924315ce17dd4f43c31f1babe08e220a_103.png)

So with this， we can start putting in some values right。

 So what is the probability you're going to have an accident given your accident prone。 Well。

40% of people that are accident prone have an accident。 So given that they're accident prone。

 that is going to be point。

![](img/924315ce17dd4f43c31f1babe08e220a_105.png)

Four， okay？And well， what's the probability or accident prone point？3。Right， plus。

What's the problem that you're going to have an accident if you're not accident prone， right。

 and 20% of non accident prone people。

![](img/924315ce17dd4f43c31f1babe08e220a_107.png)

Now what's the probability youre not accident prone， well， if it's 30% likely you are accident prone。

 then it's got to be 0。70 that you're not because that's the compliment。



![](img/924315ce17dd4f43c31f1babe08e220a_109.png)

![](img/924315ce17dd4f43c31f1babe08e220a_110.png)

Okay， and so when you work that out， you end up getting 0。26。

 So what we're able to do is we're able to kind of break down a problem into there's two different factors here。

 whether or not you have an accident。

![](img/924315ce17dd4f43c31f1babe08e220a_112.png)

![](img/924315ce17dd4f43c31f1babe08e220a_113.png)

![](img/924315ce17dd4f43c31f1babe08e220a_114.png)

And whether or not you're accident prone， two different things。

 But we understand that they are dependent on one another。

 There's some sort of conditional dependence。 So when we're evaluating the probability。

 we have to evaluate both the likelihood that your accident prone and the likelihood that you had an accident and they're related。

 So we kind of have to treat that in a little more intricate way。

 The way we do that is with Bays rule。 So to calculate the probability that you have an accident。

 we understand that that is going to be with this rule。



![](img/924315ce17dd4f43c31f1babe08e220a_116.png)

![](img/924315ce17dd4f43c31f1babe08e220a_117.png)

![](img/924315ce17dd4f43c31f1babe08e220a_118.png)

![](img/924315ce17dd4f43c31f1babe08e220a_119.png)

![](img/924315ce17dd4f43c31f1babe08e220a_120.png)

You know， this equation that we see right here and so you can。



![](img/924315ce17dd4f43c31f1babe08e220a_122.png)

Add this one to your list of formulas that you need to kind of keep track of。

 and this kind of gives you some intuition to help you understand and believe that that is the case okay。



![](img/924315ce17dd4f43c31f1babe08e220a_124.png)

![](img/924315ce17dd4f43c31f1babe08e220a_125.png)

Well， let's do， let's do 3 B here。 Let's， let's change the problem a little bit。 What is。



![](img/924315ce17dd4f43c31f1babe08e220a_127.png)

![](img/924315ce17dd4f43c31f1babe08e220a_128.png)

Probability。Your accident prone。

![](img/924315ce17dd4f43c31f1babe08e220a_130.png)

Given。

![](img/924315ce17dd4f43c31f1babe08e220a_132.png)

Given。You had an accident。

![](img/924315ce17dd4f43c31f1babe08e220a_134.png)

Well， let's write that down right？😊，We want to get at。

What is the probability your accident prone we want to know the probability。Your accident prone。

 given that you had an accident using my notation that I used up here。



![](img/924315ce17dd4f43c31f1babe08e220a_136.png)

All right。😊，嗯。What we want to know is we know that the probability。

Of having an accident and being accident prone， right。

 what's the probability of an accident and being accident prone is going to be equivalent to the probability of having an accident given your accident prone。

Times the probability of having an accident。Divided by， sorry。



![](img/924315ce17dd4f43c31f1babe08e220a_138.png)

And that is equal to the probability of having an accident。



![](img/924315ce17dd4f43c31f1babe08e220a_140.png)

Given your accident prone times the probability of A by Bay's rule， that's that and。



![](img/924315ce17dd4f43c31f1babe08e220a_142.png)

So if I divide both sides of the equation by something like probability N。

Then the probability that I have an accident given。I'm accident prone。

Can be reflected by the probability of AN。Divided by the probability of n， right。

Prob of A N divided by n。 and I can replace the probability of an by the equation over here。

 the probability of n。Give an A。Times the probability of a。 Now what am I doing here？



![](img/924315ce17dd4f43c31f1babe08e220a_144.png)

What I'm doing is I'm taking essentially two relationships， right， the relationship that we had here。



![](img/924315ce17dd4f43c31f1babe08e220a_146.png)

Right I'm taking the relationship that we know here。 I'm taking these different relationships。

 and these are kind of like my tools， my little you know building blocks。

 I'm figuring out what information do I have and then I'm trying to make a decision as far as what I'm going to use。

 So I want to find out the probability of an accident given I'm accident prone。

 So by shuffling the data in this way， I know the probability of N given A because I have it up here。



![](img/924315ce17dd4f43c31f1babe08e220a_148.png)

![](img/924315ce17dd4f43c31f1babe08e220a_149.png)

![](img/924315ce17dd4f43c31f1babe08e220a_150.png)

So that equals 04。Do I have the probability of having an accident Yes， times 0。3？



![](img/924315ce17dd4f43c31f1babe08e220a_152.png)

![](img/924315ce17dd4f43c31f1babe08e220a_153.png)

Being accident prone， right， Wait a minute。 I do that right， I need to make this an n， sorry。



![](img/924315ce17dd4f43c31f1babe08e220a_155.png)

![](img/924315ce17dd4f43c31f1babe08e220a_156.png)

嗯。And I now know。 I now know the probability of end because I worked it out in 3 a。



![](img/924315ce17dd4f43c31f1babe08e220a_158.png)

So I know that that is 026 right so I'm able to take the pieces that I do have and I'm able to work that out to613s because fractions are your friends right and so we're able to answer some of these conditional probabilities by taking the probabilities we know kind of modeling out some of those relationships with Bay's rule and then we can solve more problems。



![](img/924315ce17dd4f43c31f1babe08e220a_160.png)

![](img/924315ce17dd4f43c31f1babe08e220a_161.png)

![](img/924315ce17dd4f43c31f1babe08e220a_162.png)

![](img/924315ce17dd4f43c31f1babe08e220a_163.png)

![](img/924315ce17dd4f43c31f1babe08e220a_164.png)