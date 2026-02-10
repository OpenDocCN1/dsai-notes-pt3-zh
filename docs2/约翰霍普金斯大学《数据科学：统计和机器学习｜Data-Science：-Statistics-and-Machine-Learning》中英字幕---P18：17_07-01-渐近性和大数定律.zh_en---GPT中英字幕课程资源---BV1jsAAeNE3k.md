# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P18：17_07 01 渐近性和大数定律.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

Hi， my name is Brian Kaho and welcome to the lecture on asymptotics as part of the statistical inference class in the Coursera Data Science specialization。

This class was co taught by my co instructors Jeff Lee and Roger Pang。

 royal to Johns Hopkins Bloomberg School of Public Health。



![](img/2921ade37a96930f72b63d3c012c81bf_1.png)

So asymptotics is the term for the behavior statistics as the sample size or some other relevant quantity limits to infinity。

 or in some cases as something else limits to zero。

 we're going to deal only with the case where the sample size is the quantity that's limiting to infinity。



![](img/2921ade37a96930f72b63d3c012c81bf_3.png)

![](img/2921ade37a96930f72b63d3c012c81bf_4.png)

Asymptopia is my name for the land of asymptotics where everything works out well。

 and it should work out well because there's an infinite amount of data in the land of asymptopia。



![](img/2921ade37a96930f72b63d3c012c81bf_6.png)

![](img/2921ade37a96930f72b63d3c012c81bf_7.png)

So asymptotics are incredibly useful for simple statistical inference and approximations。

 asymptotics are like a little Swiss army knife that you can pull out to investigate the statistical properties of many statistics without having to do much computing。



![](img/2921ade37a96930f72b63d3c012c81bf_9.png)

![](img/2921ade37a96930f72b63d3c012c81bf_10.png)

So asymptotics also form the basis for frequency interpretation of probabilities， for example。

 everyone kind of intuitively knows that if you flip a coin and take the proportion of heads that that should limit to 0。

5 for a fair coin。

![](img/2921ade37a96930f72b63d3c012c81bf_12.png)

![](img/2921ade37a96930f72b63d3c012c81bf_13.png)

That property is the so called law of large numbers that we'll explore here in a minute。



![](img/2921ade37a96930f72b63d3c012c81bf_15.png)

Fortunately， instead of diving into the mathematics of the limits of random variables。

 there's a set of powerful tools that we can rely on。



![](img/2921ade37a96930f72b63d3c012c81bf_17.png)

These results allow us to talk about the large sample distribution and behavior of sample means of a collection of IID observations。



![](img/2921ade37a96930f72b63d3c012c81bf_19.png)

The first of these， we already intuitively know， the so called law of large numbers。



![](img/2921ade37a96930f72b63d3c012c81bf_21.png)

It says that the average limits to what it's estimating， the population means。So for example。

 the average could be the result of N coin flips， the sample proportion of heads。



![](img/2921ade37a96930f72b63d3c012c81bf_23.png)

As we flip a fair coin over and over， it eventually converges to the true probability of a head。



![](img/2921ade37a96930f72b63d3c012c81bf_25.png)

Let's show the law of large numbers in action。I'm going to set my number of simulations to be 1000。

Then I'm going to generate 1 thousand random normals， and I'm going to take their cumulative sum。

Then dividing the cumulative sums by one over n gives the cumulative means。 In other words。

 the mean of the first observation by itself， than the mean of the first and the second observation than the mean of the first second and third observation。

 and so on。

![](img/2921ade37a96930f72b63d3c012c81bf_27.png)

What you see when you plot the cumulative means by the index is early on。

 there's a lot of variability in the mean， but then as time goes on。

 not as time as the number of simulation goes on。

![](img/2921ade37a96930f72b63d3c012c81bf_29.png)

We get closer and closer to the true population value， which is zero。



![](img/2921ade37a96930f72b63d3c012c81bf_31.png)

![](img/2921ade37a96930f72b63d3c012c81bf_32.png)

Let's do it again， only this time let's ask R to flip a coin rather than generate standard normals。

So the function sample when I give the arguments 0 and1 samples from the elements 0 and1 with equal probability here I want n of them 1000。

 and replace equals true just means that I want to sample with replacement。

 so this command is exactly flipping a coin 1000 times where 0 is a tail and one is a head。

I'm taking again the cumulative sum and then dividing it by one to n to get the cumulative means。

When I plot the cumulative means。What I see again is variability in the sample proportion early on。

 but as the number of coin flips going into the sample proportion goes to infinity。

 it converges to the true value。Which is 0。5， which is right there。



![](img/2921ade37a96930f72b63d3c012c81bf_34.png)

Let's have a brief discussion， we define an estimator as consistent if it converges to what you want to estimate。

So for example， the sample proportion from IID coin flips is consistent for the true success probability of a coin as you flip a coin over and over。

 the sample proportion of heads converges to the probability of getting ahead on that coin。

The law of large number says that the sample mean of IID samples is consistent for the population mean。



![](img/2921ade37a96930f72b63d3c012c81bf_36.png)

This is a very good property to have because it's basically saying if we go to the trouble of collecting an infinite amount of data。

 we get exactly the right answer， but it's not only true that sample means are consistent。

 the sample variance in the sample standard deviation of ID random variables are consistent as well。



![](img/2921ade37a96930f72b63d3c012c81bf_38.png)

![](img/2921ade37a96930f72b63d3c012c81bf_39.png)