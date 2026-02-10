# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P18：17_07 01 渐近性和lln.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/cc20a5b7b0a74881982ccd72fa55d99e_0.png)

Hi， my name is Brian Kaho and welcome to the lecture on asymptotics as part of the statistical inference class in the Coursera Data Science Specialization。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_2.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_3.png)

This class is co talk by my co instructors， Jeff Lee and Roger Pang。

 royal the Johns Hopkins Bloomberg School of Public Health。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_5.png)

So asymptotics is the term for the behavior statistics as the sample size or some other relevant quantity limits to infinity。

 or in some cases as something else limits to zero。

 we're going to deal only with the case where the sample size is the quantity that's limiting to infinity。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_7.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_8.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_9.png)

Asymptopia is my name for the land of asymptotics where everything works out well and it should work out well because there's an infinite amount of data in the land of asymptopia。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_11.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_12.png)

So asymptotics are incredibly useful for simple statistical inference and approximations。

 asymptotics are like a little Swiss army knife that you can pull out to investigate the statistical properties of many statistics without having to do much computing。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_14.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_15.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_16.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_17.png)

So asymptotics also form the basis for frequency interpretation of probabilities， for example。

 everyone kind of intuitively knows that if you flip a coin and take the proportion of heads that that should limit to 0。

5 for a fair coin。

![](img/cc20a5b7b0a74881982ccd72fa55d99e_19.png)

That property is the so called law of large numbers that we'll explore here in a minute。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_21.png)

Fortunately， instead of diving into the mathematics of the limits of random variables。

 there's a set of powerful tools that we can rely on。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_23.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_24.png)

These results allow us to talk about the large sample distribution and behavior of sample means of a collection of IID observations。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_26.png)

The first of these we already intuitively know， the so called law of large numbers。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_28.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_29.png)

It says that the average limits to what it's estimating， the population means。So for example。

 the average could be the result of N coin flips， the sample proportion of heads。

As we flip a fair coin over and over， it eventually converges to the true probability of a head。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_31.png)

Let's show the law of large numbers in action。

![](img/cc20a5b7b0a74881982ccd72fa55d99e_33.png)

I'm going to set my number of simulations to be 1000。

Then I'm going to generate 1 thousand random normals， and I'm going to take their cumulative sum。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_35.png)

Then dividing the cumulative sums by one over n gives the cumulative means。 In other words。

 the mean of the first observation by itself than the mean of the first and the second observation than the mean of the first second and third observation。

 and so on。

![](img/cc20a5b7b0a74881982ccd72fa55d99e_37.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_38.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_39.png)

What you see when you plot the cumulative means by the index is early on。

 there's a lot of variability in the mean， but then as time goes on。

 not as time as the number of simulation goes on。

![](img/cc20a5b7b0a74881982ccd72fa55d99e_41.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_42.png)

We get closer and closer to the true population value， which is zero。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_44.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_45.png)

Let's do it again， only this time let's ask R to flip a coin rather than generate standard normals。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_47.png)

So the function sample when I give the arguments 0 and1 samples from the elements 0 and1 with equal probability here I want n of them 100。

 and replace equals true just means that I want to sample with replacement。

 so this command is exactly flipping a coin 1000 times where 0 is a tail and  one is a head。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_49.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_50.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_51.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_52.png)

I'm taking again the cumulative sum and then dividing it by one to n to get the cumulative means。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_54.png)

When I plot the cumulative means。

![](img/cc20a5b7b0a74881982ccd72fa55d99e_56.png)

What I see again is variability in the sample proportion early on。

 but as the number of coin flips going into the sample proportion goes to infinity。

 it converges to the true value。

![](img/cc20a5b7b0a74881982ccd72fa55d99e_58.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_59.png)

Which is 0。5， which is right there。

![](img/cc20a5b7b0a74881982ccd72fa55d99e_61.png)

Let's have a brief discussion， we define an estimator as consistent if it converges to what you want to estimate。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_63.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_64.png)

So for example， the sample proportion from IID coin flips is consistent for the true success probability of a coin as you flip a coin over and over。

 the sample proportion of heads converges to the probability of getting ahead on that coin。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_66.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_67.png)

The law of large number says that the sample mean of IID samples is consistent for the population mean。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_69.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_70.png)

This is a very good property to have， because it's basically saying if we go to the trouble of collecting an infinite amount of data。

 we get exactly the right answer， but it's not only true that sample means are consistent。

 the sample variance in the sample standard deviation of IID random variables are consistent as well。



![](img/cc20a5b7b0a74881982ccd72fa55d99e_72.png)

![](img/cc20a5b7b0a74881982ccd72fa55d99e_73.png)