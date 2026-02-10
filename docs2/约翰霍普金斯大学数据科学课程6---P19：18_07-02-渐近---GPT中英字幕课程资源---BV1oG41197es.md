# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P19：18_07 02 渐近性和clt.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/644d00bbe3a985504f7d93b26436dda2_0.png)

Perhaps the most important theorem in all statistics is the so called central limit theorem。



![](img/644d00bbe3a985504f7d93b26436dda2_2.png)

For our purposes， the central limit theorem states the distribution of averages of ID random variables becomes that of a standard normal as the sample size increases。



![](img/644d00bbe3a985504f7d93b26436dda2_4.png)

![](img/644d00bbe3a985504f7d93b26436dda2_5.png)

Because it has fairly loose requirements on the collection of populations that it applies to。

 the central limit theorem applies in a nearly endless variety of settings and will go through several。



![](img/644d00bbe3a985504f7d93b26436dda2_7.png)

![](img/644d00bbe3a985504f7d93b26436dda2_8.png)

The basic result is that if we take an estimate like the sample average x bar。

 subtract off its population mean， mu， and divide by its standard error sigma over square root N。



![](img/644d00bbe3a985504f7d93b26436dda2_10.png)

That random variable。Limits to that of a standard normal。



![](img/644d00bbe3a985504f7d93b26436dda2_12.png)

I would also add that replacing the population standard deviation。

 which is unknown by the sample standard deviation， which is known。

 does not change the central limit theorem。

![](img/644d00bbe3a985504f7d93b26436dda2_14.png)

![](img/644d00bbe3a985504f7d93b26436dda2_15.png)

The most useful way we think about the central limit theorem is to say that the sample average is approximately normally distributed with a mean given by the population mean and a variance given by the standard error of the mean。



![](img/644d00bbe3a985504f7d93b26436dda2_17.png)

![](img/644d00bbe3a985504f7d93b26436dda2_18.png)

So let's go through several examples to illustrate the central limit theorem using simulation。First。

 let's start with a standard die。What's interesting about this conceptual experiment and the simulation that we're going to conduct is that imagine。



![](img/644d00bbe3a985504f7d93b26436dda2_20.png)

![](img/644d00bbe3a985504f7d93b26436dda2_21.png)

If you had to simulate random normals prior to the advent of computers， for example。

 if you were a statistician working at that time and you wanted to evaluate the behavior of something like the chi squared statistic。

 which is a function of normal random variables。

![](img/644d00bbe3a985504f7d93b26436dda2_23.png)

![](img/644d00bbe3a985504f7d93b26436dda2_24.png)

![](img/644d00bbe3a985504f7d93b26436dda2_25.png)

So let's let XI be the outcome for di I and remember that the mean of the distribution of di rolls is 3。

5 and that its variance is 2。92。

![](img/644d00bbe3a985504f7d93b26436dda2_27.png)

![](img/644d00bbe3a985504f7d93b26436dda2_28.png)

![](img/644d00bbe3a985504f7d93b26436dda2_29.png)

So the standard error of the mean is square root 2。92 over n。Let's roll N dice， take their mean。

 subtract off 3。5， and divide by 1。71 over square root n。



![](img/644d00bbe3a985504f7d93b26436dda2_31.png)

![](img/644d00bbe3a985504f7d93b26436dda2_32.png)

And repeat this over and over again， if the central limit theorem is right。

 this should look exactly like a standard bell curve。



![](img/644d00bbe3a985504f7d93b26436dda2_34.png)

![](img/644d00bbe3a985504f7d93b26436dda2_35.png)

So just to remind ourselves what's happening。We rolled the dice 10 times in this first panel。

 We subtracted off 3。5， and we divided by 1。71， divided by square root 10。



![](img/644d00bbe3a985504f7d93b26436dda2_37.png)

![](img/644d00bbe3a985504f7d93b26436dda2_38.png)

We repeated that process over and over and over again。



![](img/644d00bbe3a985504f7d93b26436dda2_40.png)

And the histogram displays the distribution of the different normalized averages that we got。



![](img/644d00bbe3a985504f7d93b26436dda2_42.png)

We know already that this distribution has to be centered around zero because we've subtracted off the mean 3。

5， so it has to be centered around zero， and we know exactly what the variance of this distribution has to be where we could repeat this process infinitely many times。



![](img/644d00bbe3a985504f7d93b26436dda2_44.png)

![](img/644d00bbe3a985504f7d93b26436dda2_45.png)

![](img/644d00bbe3a985504f7d93b26436dda2_46.png)

![](img/644d00bbe3a985504f7d93b26436dda2_47.png)

However， what the central limit theorem is telling us is also the shape and the shape has to be like that of a bell curve and because we normalize the data。

 it has to be exactly that of a standard normal， and we see that the approximation is actually very good even for just 10 di rolls for 20 it gets even better and for 30 it's better still。



![](img/644d00bbe3a985504f7d93b26436dda2_49.png)

![](img/644d00bbe3a985504f7d93b26436dda2_50.png)

![](img/644d00bbe3a985504f7d93b26436dda2_51.png)

![](img/644d00bbe3a985504f7d93b26436dda2_52.png)

Flipping a coin is an interesting case because it goes back to the original development of the central limit theorem as an approximation for the distribution of sample proportions。



![](img/644d00bbe3a985504f7d93b26436dda2_54.png)

![](img/644d00bbe3a985504f7d93b26436dda2_55.png)

So let's let Xi be the 01 result of the i flip of a possibly unfair coin。



![](img/644d00bbe3a985504f7d93b26436dda2_57.png)

Then recall， we usually give the notation P hat as the sample proportion。

 which is simply the mean or average， the empirical average of the coin flips coat zero is a tail and one is a head。



![](img/644d00bbe3a985504f7d93b26436dda2_59.png)

![](img/644d00bbe3a985504f7d93b26436dda2_60.png)

Recall that the expected value of X is p and that the variance of X is p times 1 minus p。



![](img/644d00bbe3a985504f7d93b26436dda2_62.png)

Then the standard error of the mean or the standard error of the proportion of heads P hat is square root p times 1 minus p over n。



![](img/644d00bbe3a985504f7d93b26436dda2_64.png)

![](img/644d00bbe3a985504f7d93b26436dda2_65.png)

So if we take the statistic， P hatAT， subtract off its population mean。



![](img/644d00bbe3a985504f7d93b26436dda2_67.png)

And divide by its standard error square root P times 1 minus P over N。

 That should be approximately normally distributed。



![](img/644d00bbe3a985504f7d93b26436dda2_69.png)

![](img/644d00bbe3a985504f7d93b26436dda2_70.png)

If n is large enough。Now notice if the coin is fair， then P is12。



![](img/644d00bbe3a985504f7d93b26436dda2_72.png)

And p times 1 minus p is a quarter， which as a square root is12。



![](img/644d00bbe3a985504f7d93b26436dda2_74.png)

So the standard error for a fair coin flip is one over two square root n。



![](img/644d00bbe3a985504f7d93b26436dda2_76.png)

So let's flip the coin n times， take the sample proportion of heads， subtract off 0。5。

 and multiply the result by two square root n。

![](img/644d00bbe3a985504f7d93b26436dda2_78.png)

![](img/644d00bbe3a985504f7d93b26436dda2_79.png)

Here's the result of our simulations， consider the panel with 10 coin flips here on the left。



![](img/644d00bbe3a985504f7d93b26436dda2_81.png)

This is the result of flipping the coin 10 times。

![](img/644d00bbe3a985504f7d93b26436dda2_83.png)

Subtracting off the population mean 0。5。And dividing by the standard error of the mean square root P times 1 minus P over n。



![](img/644d00bbe3a985504f7d93b26436dda2_85.png)

![](img/644d00bbe3a985504f7d93b26436dda2_86.png)

Doing this over and over and over again， we get a good sense for what the distribution of normalized proportions of 10 coin flips looks like。



![](img/644d00bbe3a985504f7d93b26436dda2_88.png)

It's centered at zero because we subtract it off the mean。

 and its variance is governed by the p times 1 minus p over n。



![](img/644d00bbe3a985504f7d93b26436dda2_90.png)

![](img/644d00bbe3a985504f7d93b26436dda2_91.png)

What this lecture is telling us is that the distribution should be approximately that of a standard normal。



![](img/644d00bbe3a985504f7d93b26436dda2_93.png)

And for reference， I drew the density of the standard normal here。



![](img/644d00bbe3a985504f7d93b26436dda2_95.png)

You can see some of the discreteness， there's only two levels for a coin so that1 the average of 10 coin flips can only take so many different combinations。

 and so some of the discreteness is showing through。



![](img/644d00bbe3a985504f7d93b26436dda2_97.png)

![](img/644d00bbe3a985504f7d93b26436dda2_98.png)

But when we get to 20 or 30 coin flips， we can see that it actually looks quite Gaussian。



![](img/644d00bbe3a985504f7d93b26436dda2_100.png)

![](img/644d00bbe3a985504f7d93b26436dda2_101.png)

I would like to emphasize that the speed at which the normalized coin flips converges to normality。

Is governed by how biased the coin is。 For example， here。

 I show what the simulations look like for a problative head of 0。9。



![](img/644d00bbe3a985504f7d93b26436dda2_103.png)

![](img/644d00bbe3a985504f7d93b26436dda2_104.png)

You can see for 10， that distribution does not look very bell shaped by 30 it's getting there。

 but still the probabilities when approximated by the normal distribution would not be perfect。



![](img/644d00bbe3a985504f7d93b26436dda2_106.png)

![](img/644d00bbe3a985504f7d93b26436dda2_107.png)

So just keep this in mind that the central limit theorem doesn't guarantee that the normal distribution will be a good approximation。

 simply that as the number of coin flips limits to infinity。

 eventually it will be a good approximation。

![](img/644d00bbe3a985504f7d93b26436dda2_109.png)

![](img/644d00bbe3a985504f7d93b26436dda2_110.png)

![](img/644d00bbe3a985504f7d93b26436dda2_111.png)

As a fun aside， I wanted to talk about Galton's quinkunks。

 a machine that you might have seen if you visited a science museum。



![](img/644d00bbe3a985504f7d93b26436dda2_113.png)

![](img/644d00bbe3a985504f7d93b26436dda2_114.png)

Basically the crux of this machine is illustrating the central limit theorem with a game that looks a little like Pachko。



![](img/644d00bbe3a985504f7d93b26436dda2_116.png)

So here is an example what would happen is a ball would come down here。And it would fall down here。

 and it would hit this peg。And then it would click go left or right with equal probability。

And then it would go down， let's say if it went in this direction and then it went down there。

 and then it would fall left or right with equal probability。

And eventually the ball would work its way down to a bin and it would get collected down here。

You can think of each time the ball hits a peg and has to choose left or right as a binomial experiment。

 a coin flip。 If it were to get all successes， let's say it would head all the way over in this direction。

 If it were to get all failures， it would head all the way over in that direction。

 It would be like flickping a coin。 So each row is like another coin flip。

By virtue of the central limit theorem， we know that the proportion of heads from a bunch of coin flips is approximately normally distributed。

 so we could multiply that by n and then also conclude that the sum， the total number of heads。

 will also be approximately normally distributed。And so what you'll see at the Science Museum is that the balls will collect down here。

And they'll actually draw the relevant normal distribution right there。

 and you'll see as the balls collect， they'll collect up into this exactly overlay this superimposed normal distribution and then when it fills up to that point。

 there's usually a little thing that drops all the balls down and it starts over again。

So at any rate， it's a fun idea， you can Google online and see some examples of Galton's Quinks。

 it's a fun application of the central limit theorem。

