# 杜克大学《数据科学数学技能｜Data Science Math Skills》中英字幕 - P28：28_04_03_联合概率.zh_en - GPT中英字幕课程资源 - BV12mv6BLEhC

![](img/34fe4c73d1366339ea78854a531973ce_0.png)

Next， we're going to talk about joint probabilities。

 Joint probabilities are the probabilities that two separate events from two separate probability distributions are both true。

So we're looking at the probability that a is true and B is true。



![](img/34fe4c73d1366339ea78854a531973ce_2.png)

And our notation allows us to abbreviate this， simply placing both capital letters together with a comma between them。

 This is read as the joint probability of A and B， or。



![](img/34fe4c73d1366339ea78854a531973ce_4.png)

![](img/34fe4c73d1366339ea78854a531973ce_5.png)

![](img/34fe4c73d1366339ea78854a531973ce_6.png)

The probability that A is true and B is true。

![](img/34fe4c73d1366339ea78854a531973ce_8.png)

An important point here to note is that the ordering does not matter in joint probabilities。



![](img/34fe4c73d1366339ea78854a531973ce_10.png)

So also I want to point out that our standard notation for probability uses capital letters to refer to the entire probability distribution。

 that's the entire collection of exclusive and exhaustive statements。

 and we use lower case letters to refer to the individual statements。

 and we can reference an individual probability the same way。



![](img/34fe4c73d1366339ea78854a531973ce_12.png)

![](img/34fe4c73d1366339ea78854a531973ce_13.png)

![](img/34fe4c73d1366339ea78854a531973ce_14.png)

![](img/34fe4c73d1366339ea78854a531973ce_15.png)

![](img/34fe4c73d1366339ea78854a531973ce_16.png)

![](img/34fe4c73d1366339ea78854a531973ce_17.png)

Okay。So。What we've written here。

![](img/34fe4c73d1366339ea78854a531973ce_19.png)

Suggests that the joint。Probabilities。Are equal。For regardless of which order we write the terms or which order we consider the probability distributions。

And the same is true of each individual probability within。The distribution。

 So the probability of x1 and y1 occurring together is the same as the probability of y1 and x1 occurring together。

This may perhaps seem obvious to you， but it turns out to be a very， very useful principle as well。

Now we're going to talk about the definition of the independence of two probability distributions。

If two probability distributions are independent。Knowing the outcome of one does not affect our belief in the truth of the other。

Therefore， knowing the outcome of one does not change the probability of the other。

When two probabilities are independent， you can think of them as being unrelated and unconnected。

I'm tossing a coin。 It has a 50% probability of coming up heads， and I'm rolling a die。

 and it has a 50 per excuse me。 And it has a one in6 probability of coming up as a three。

The joint probability heads。

![](img/34fe4c73d1366339ea78854a531973ce_21.png)

And3。

![](img/34fe4c73d1366339ea78854a531973ce_23.png)

Is equal to the probability of heads， which is one half。



![](img/34fe4c73d1366339ea78854a531973ce_25.png)

Times， the probability of coming up。

![](img/34fe4c73d1366339ea78854a531973ce_27.png)

Three on a six sided die is 16， and that equals 1，12。



![](img/34fe4c73d1366339ea78854a531973ce_29.png)

So。For probability problems involving independent distributions。

 this is the formula to calculate the probability that both events happen at the same time。

We have a special name for。The product of the two probabilities that is known as the product distribution。

so when the joint distribution equals the product distribution。

 the two probability distributions are by definition independent。We often use Venn diagrams。

 These are diagrams that show the intersection and union of sets。



![](img/34fe4c73d1366339ea78854a531973ce_31.png)

![](img/34fe4c73d1366339ea78854a531973ce_32.png)

To illustrate the intersection of two sets of events。



![](img/34fe4c73d1366339ea78854a531973ce_34.png)

And get develop some intuition about what it means to say that both the probability that both events occur。

 So， for example， if we have the probability of。

![](img/34fe4c73d1366339ea78854a531973ce_36.png)

![](img/34fe4c73d1366339ea78854a531973ce_37.png)

![](img/34fe4c73d1366339ea78854a531973ce_38.png)

Flipping a coin， and it comes up heads。 And the probability of tossing a die。 and it comes up 3。

 Okay， we can represent。

![](img/34fe4c73d1366339ea78854a531973ce_40.png)

![](img/34fe4c73d1366339ea78854a531973ce_41.png)

This area as the product of the two。

![](img/34fe4c73d1366339ea78854a531973ce_43.png)

Okay。

![](img/34fe4c73d1366339ea78854a531973ce_45.png)

You can think of this outer area as the universe of all possible outcomes。



![](img/34fe4c73d1366339ea78854a531973ce_47.png)

Okay。And this gives us the probability that both of the events that we've defined as relevant occur at the same time。



![](img/34fe4c73d1366339ea78854a531973ce_49.png)

![](img/34fe4c73d1366339ea78854a531973ce_50.png)

Perhaps the Venn diagram is even more useful in capturing the concept of or probability。

 What is the probability that our coin comes up heads。



![](img/34fe4c73d1366339ea78854a531973ce_52.png)

![](img/34fe4c73d1366339ea78854a531973ce_53.png)

Or。

![](img/34fe4c73d1366339ea78854a531973ce_55.png)

Now， interestingly， it is written with a plus sign。But in probability。

 what we're doing is we're looking at。

![](img/34fe4c73d1366339ea78854a531973ce_57.png)

The probability that either one event occurs or the other occurs or both occur。



![](img/34fe4c73d1366339ea78854a531973ce_59.png)

So we're interested in the probability that the coin comes up heads or the die comes up three。



![](img/34fe4c73d1366339ea78854a531973ce_61.png)

Okay。

![](img/34fe4c73d1366339ea78854a531973ce_63.png)

Well， if we simply added the two circles together， we'd count the central area twice。



![](img/34fe4c73d1366339ea78854a531973ce_65.png)

So to avoid that， we subtract the central area from the sum of the two circles。



![](img/34fe4c73d1366339ea78854a531973ce_67.png)

![](img/34fe4c73d1366339ea78854a531973ce_68.png)

So we are subtracting。The joint probability， which， as we know。

 is equal to the product probability 1，12。

![](img/34fe4c73d1366339ea78854a531973ce_70.png)

![](img/34fe4c73d1366339ea78854a531973ce_71.png)

So the probability that either the coin comes up heads or the die comes up three would be one half。



![](img/34fe4c73d1366339ea78854a531973ce_73.png)

![](img/34fe4c73d1366339ea78854a531973ce_74.png)

Plus， one6。-1，12。

![](img/34fe4c73d1366339ea78854a531973ce_76.png)

4。6，12。Plus 2，12。-1，12。Equals。7even。12th。