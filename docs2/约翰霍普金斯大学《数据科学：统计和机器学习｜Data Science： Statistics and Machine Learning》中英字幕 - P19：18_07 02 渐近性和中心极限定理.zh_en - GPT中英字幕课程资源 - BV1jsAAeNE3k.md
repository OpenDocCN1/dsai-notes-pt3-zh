# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P19：18_07 02 渐近性和中心极限定理.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

![](img/ec986480186d3349a829bd62d9252901_0.png)

Perhaps the most important theorem in all statistics is the so called central limit theorem。

For our purposes， the central limit theorem states the distribution of averages of ID random variables becomes that of a standard normal as the sample size increases。

Because it has fairly loose requirements on the collection of populations that it applies to。

 the central limit theorem applies in a nearly endless variety of settings and will go through several。



![](img/ec986480186d3349a829bd62d9252901_2.png)

The basic result is that if we take an estimate like the sample average x bar。

 subtract off its population mean mu， and divide by its standard error sigma over square root n。

That random variable。Limits to that of a standard normal。

I would also add that replacing the population standard deviation。

 which is unknown by the sample standard deviation， which is known。

 does not change the central limit theorem。

![](img/ec986480186d3349a829bd62d9252901_4.png)

The most useful way we think about the central limit theorem is to say that the sample average is approximately normally distributed with a mean given by the population mean and a variance given by the standard error of the mean。



![](img/ec986480186d3349a829bd62d9252901_6.png)

So let's go through several examples to illustrate the central limit theorem using simulation。First。

 let's start with a standard die。What's interesting about this conceptual experiment and the simulation that we're going to conduct is that imagine。

If you had to simulate random normals prior to the advent of computers， for example。

 if you were a statistician working at that time and you wanted to evaluate the behavior of something like the chi squared statistic。

 which is a function of normal random variables。So let's let Xi be the outcome for di I and remember that the mean of the distribution of di rolls is 3。

5 and that its variance is 2。92。So the standard error of the mean is square root 2。92 over n。

Let's roll N dice， take their mean， subtract off 3。5， and divide by 1。71 over square root n。

And repeat this over and over again， if the central limit theorem is right。

 this should look exactly like a standard bell curve。



![](img/ec986480186d3349a829bd62d9252901_8.png)

![](img/ec986480186d3349a829bd62d9252901_9.png)

So just to remind ourselves what's happening。We rolled the dice 10 times in this first panel。

 We subtracted off 3。5， and we divided by 1。71 divided by square root 10。

We repeated that process over and over and over again。

And the histogram displays the distribution of the different normalized averages that we got。

We know already that this distribution has to be centered around  zero because we've subtracted off the mean 3。

5， so it has to be centered around zero， and we know exactly what the variance of this distribution has to be where we could repeat this process infinitely many times。

However， what the central limit theorem is telling us is also the shape and the shape has to be like that of a bell curve。

 and because we normalize the data， it has to be exactly that of a standard normal。

 and we see that the approximation is actually very good even for just 10 di rolls for 20 it gets even better and for 30。

 it's better still。

![](img/ec986480186d3349a829bd62d9252901_11.png)

Flipping a coin is an interesting case because it goes back to the original development of the central limit theorem as an approximation for the distribution of sample proportions。



![](img/ec986480186d3349a829bd62d9252901_13.png)

So let's let Xi be the 01 result of the i flip of a possibly unfair coin。Then recall。

 we usually give the notation P hat as the sample proportion， which is simply the mean or average。

 the empirical average of the coin flips， coat zero is a tail and one is a head。

Recall that the expected value of X is p and that the variance of X is p times 1 minus p。

Then the standard error of the mean or the standard error of the proportion of heads P hat is square root p times 1 minus p over n。



![](img/ec986480186d3349a829bd62d9252901_15.png)

So if we take the statistic， P hatAT， subtract off its population mean。



![](img/ec986480186d3349a829bd62d9252901_17.png)

And divide by its standard error square root P times 1 minus P over N。

 that should be approximately normally distributed。



![](img/ec986480186d3349a829bd62d9252901_19.png)

If n is large enough。

![](img/ec986480186d3349a829bd62d9252901_21.png)

Now notice if the coin is fair， then P is12。And p times 1 minus p is a quarter。

 which as a square root is12。So the standard error for a fair coin flip is one over two square root n。

So let's flip the coin n times， take the sample proportion of heads， subtract off 0。5。

 and multiply the result by two square root n。

![](img/ec986480186d3349a829bd62d9252901_23.png)

Here's the result of our simulations。 Consider the panel with 10 coin flips here on the left。

This is the result of flipping the coin 10 times。Subtracting off the population mean 0。5。

And dividing by the standard error of the mean square root P times 1 minus P over n。

Doing this over and over and over again， we get a good sense for what the distribution of normalized proportions of 10 coin flips looks like。

It's centered at zero because we subtract it off the mean and its variance is governed by the p times 1 minus p over n。

What this lecture is telling us is that the distribution should be approximately that of a standard normal。

And for reference， I drew the density of the standard normal here。

You can see some of the discreteness， there's only two levels for a coin so that1 the average of 10 coin flips could only take so many different combinations。

 and so some of the discreteness is showing through。But when we get to 20 or 30 coin flips。

 we can see that it actually looks quite Gaussian。

![](img/ec986480186d3349a829bd62d9252901_25.png)

I would like to emphasize that the speed at which the normalized coin flips converges to normality。

Is governed by how biased the coin is。 For example， here。

 I show what the simulations look like for a problative head of 0。9。You can see for 10。

 that distribution does not look very bell shaped by 30 it's getting there。

 but still the probabilities when approximated by the normal distribution would not be perfect。

So just keep this in mind that the central limit theorem doesn't guarantee that the normal distribution will be a good approximation。

 simply that as the number of coin flips limits to infinity。

 eventually it will be a good approximation。

![](img/ec986480186d3349a829bd62d9252901_27.png)

As a fun aside， I wanted to talk about Galton's quinkunks。

 a machine that you might have seen if you visited a science museum。

 Basically the crux of this machine is illustrating the central limit theorem with a game that looks a little like pachko。



![](img/ec986480186d3349a829bd62d9252901_29.png)

So here is an example what would happen is a ball would come down here。And it would fall down here。

 and it would hit this peg。And then it would click go left or right with equal probability。

And then it would go down， let's say if it went in this direction and then it went down there。

 and then it would fall left or right with equal probability。

And eventually the ball would work its way down to a bin， and it would get collected down here。

You can think of each time the ball hits a peg and has to choose left or right as a binomial experiment。

 a coin flip。 If it were to get all successes， let's say it would head all the way over in this direction。

 If it were to get all failures， it would head all the way over in that direction。

 It would be like flipping a coin。 So each row is like another coin flip。

By virtue of the central limit theorem， we know that the proportion of heads from a bunch of coin flips is approximately normally distributed。

 so we could multiply that by n and then also conclude that the sum， the total number of heads。

 will also be approximately normally distributed。And so what you'll see at the Science Museum is that the balls will collect down here。

And they'll actually draw the relevant normal distribution right there。

 and you'll see as the balls collect， they'll collect up into this exactly overlay this superimposed normal distribution。

 and then when it fills up to that point， there's usually a little thing that drops all the balls down and it starts over again。

So at any rate， it's a fun idea you can Google online and see some examples of Galton's Quin Kongs。

 it's a fun application of the central limit theorem。

