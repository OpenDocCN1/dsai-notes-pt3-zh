# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P10：9_04 03 pdf的期望值.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/eeddd8791d00f872bd821eda2c58a345_0.png)

For continuous random variable， you want to think about perhaps cutting the density out and say a piece of wood and then trying to figure out where you would balance out that piece of wood if you were to have to put your finger on the bottom This is exactly the center of mass of a continuous body。



![](img/eeddd8791d00f872bd821eda2c58a345_2.png)

![](img/eeddd8791d00f872bd821eda2c58a345_3.png)

![](img/eeddd8791d00f872bd821eda2c58a345_4.png)

You might think about it in our probability mass function as the bars get smaller and smaller and smaller。



![](img/eeddd8791d00f872bd821eda2c58a345_6.png)

We'll go over an example next。

![](img/eeddd8791d00f872bd821eda2c58a345_8.png)

So consider a density that's1 between zero and 1 and I have this question here。

 is it a valid density， the answer is yes， this is a well known density called the uniform density。

 and then what is its expected value？

![](img/eeddd8791d00f872bd821eda2c58a345_10.png)

What's expected value？Is going to be if I were to say cut this density out of a piece of wood。

 where would I put my finger to balance it out and of course the answer would be 0。5 right here。

 which is of course exactly the expected value of the uniform density。



![](img/eeddd8791d00f872bd821eda2c58a345_12.png)

![](img/eeddd8791d00f872bd821eda2c58a345_13.png)

![](img/eeddd8791d00f872bd821eda2c58a345_14.png)

I'd like to head more towards the real topics of inference。



![](img/eeddd8791d00f872bd821eda2c58a345_16.png)

So let's。Cover some facts about expected values， so first recall that expected values are properties of the distributions。

 they're the center of mass of the distribution。

![](img/eeddd8791d00f872bd821eda2c58a345_18.png)

![](img/eeddd8791d00f872bd821eda2c58a345_19.png)

Then also notice that the average of random variables is itself a random variable。

 if I roll six dice and take their average， that is itself a random variable。

 I could repeatedly sample from it by repeatedly rolling the six dice and repeatedly taking the average。



![](img/eeddd8791d00f872bd821eda2c58a345_21.png)

![](img/eeddd8791d00f872bd821eda2c58a345_22.png)

Because it's a random variable， it also has a distribution and that distribution has an expected value。



![](img/eeddd8791d00f872bd821eda2c58a345_24.png)

![](img/eeddd8791d00f872bd821eda2c58a345_25.png)

The center of this distribution， the center of mass of this distribution。

 is the same as that of the original distribution， and I'm going to go through some simulation examples because this is a very important topic to the subject of inference。



![](img/eeddd8791d00f872bd821eda2c58a345_27.png)

![](img/eeddd8791d00f872bd821eda2c58a345_28.png)

But the conclusion of this is that the expected value of the sample mean is exactly the population mean that it's trying to estimate。

 so in other words， the distribution of the sample mean。

 the population distribution of the sample mean is centered in the same place as the original population that the data is drawn from。



![](img/eeddd8791d00f872bd821eda2c58a345_30.png)

![](img/eeddd8791d00f872bd821eda2c58a345_31.png)

![](img/eeddd8791d00f872bd821eda2c58a345_32.png)

![](img/eeddd8791d00f872bd821eda2c58a345_33.png)

When this happens when an estimator has this property， we say that the estimator is unbiased。



![](img/eeddd8791d00f872bd821eda2c58a345_35.png)

But let's try some simulation examples to see if we can get a handle on this。

So let's consider an example。The blue density I have here is the result of thousands of simulations from a standard normal。

 because there's so many simulations。 This is a very good approximation to the truth。

 And what this is simply telling me is if I collect lots and lots and lots of data from a population。

 in this case， the standard normal distribution， if I collect lots of data from it。



![](img/eeddd8791d00f872bd821eda2c58a345_37.png)

![](img/eeddd8791d00f872bd821eda2c58a345_38.png)

![](img/eeddd8791d00f872bd821eda2c58a345_39.png)

![](img/eeddd8791d00f872bd821eda2c58a345_40.png)

I can well approximate the distribution that it comes from。



![](img/eeddd8791d00f872bd821eda2c58a345_42.png)

Now， and of course the center of mass of this distribution。

 the place that would balance it out is zero and that's exactly what it kind of looks like and if I were to simulate infinitely many data it would be exactly zero。



![](img/eeddd8791d00f872bd821eda2c58a345_44.png)

![](img/eeddd8791d00f872bd821eda2c58a345_45.png)

![](img/eeddd8791d00f872bd821eda2c58a345_46.png)

Now， let's imagine that instead of taking。

![](img/eeddd8791d00f872bd821eda2c58a345_48.png)

A bunch of single normals。 I were to simulate 10 standard normals。

 take their average and then repeat that process over and over again。

 and are to plot the histogram or the density estimate for that set of simulations of averages of 10 normals。



![](img/eeddd8791d00f872bd821eda2c58a345_50.png)

![](img/eeddd8791d00f872bd821eda2c58a345_51.png)

![](img/eeddd8791d00f872bd821eda2c58a345_52.png)

Now that would be a different distribution。Because it's no longer the distribution of standard normals。

 it's the distribution of averages of 10 standard normals。

 and that's the salmon color distribution we see it has some interesting properties。

 one is that it's become much more concentrated about zero we'll talk about that later。



![](img/eeddd8791d00f872bd821eda2c58a345_54.png)

![](img/eeddd8791d00f872bd821eda2c58a345_55.png)

Right now， all we want to say is that it happens to be exactly centered at the00。

 and this is all the point from the previous slide was trying to make that the distribution of averages from a population will be centered at the same place as the distribution from the original population itself。

 so the distribution of averages of 10 standard normals will be centered at zero。

 we don't have to do any calculations or simulations。

 though they are useful for our understanding conceptually。



![](img/eeddd8791d00f872bd821eda2c58a345_57.png)

![](img/eeddd8791d00f872bd821eda2c58a345_58.png)

![](img/eeddd8791d00f872bd821eda2c58a345_59.png)

![](img/eeddd8791d00f872bd821eda2c58a345_60.png)

![](img/eeddd8791d00f872bd821eda2c58a345_61.png)

![](img/eeddd8791d00f872bd821eda2c58a345_62.png)

Let's go through some more examples。

![](img/eeddd8791d00f872bd821eda2c58a345_64.png)

Imagine if I were to roll a die several thousand times， and in fact in R。

 that's what I did right here in the first panel。

![](img/eeddd8791d00f872bd821eda2c58a345_66.png)

If I were to plot a histogram of their results， about 1/ sixth。

Of the roles would occur for each of the numbers one through six。

 and if I were to roll it more and more and more， these bars would balance out。

This center of mass for this distribution， well it's 3。5。

 not exactly because I haven't simulated infinitely many di rolls， but if I did。

 it would balance out at 3。5。

![](img/eeddd8791d00f872bd821eda2c58a345_68.png)

![](img/eeddd8791d00f872bd821eda2c58a345_69.png)

Now， imagine if I were to take the die， roll it twice， take the average of the numbers。

 and then do that over and over again。 Then I wouldn't have a distribution of die rolls。

 I would have a distribution of averages of two die rolls。

 And that's what we see here in the second panel。 Notice it looks more Gaussian， more on that later。

 notice that it's more concentrated More on that later。 but also notice most importantly。

 it's centered at the same location。 The population mean of averages of two die rolls is exactly the same as the population mean of die rolls。



![](img/eeddd8791d00f872bd821eda2c58a345_71.png)

Then I go on to do three and then four， one more example。



![](img/eeddd8791d00f872bd821eda2c58a345_73.png)

If I were to flip a coin a lot of times， I would get zero about 50% of the time tails about 50% of the time。

 and heads about 50% of the time are one， and we know that these bars would balance out at about 0。5。

Now if I only flip it a couple of times， my sample proportion may be kind of far from 0。5。

 but if I flip it enough， I know that the simulation variability will be meaningless and that'll get nearly exactly 0。

5。Now what if instead I were to flip the coin 10 times， take the average？

And then repeat that process over and over again。 Then what my simulation would give me is an idea about the distribution of averages of 10 coin flips。

 And here I do that for the distribution of averages of 10 coin flips。

 averages of 20 coin flips and averages of 30 coin flips。 And what we'll see in each case is。



![](img/eeddd8791d00f872bd821eda2c58a345_75.png)

As the average is comprised of more coin flips， its distribution gets more concentrated about the mean；

 however its distribution is always centered at the same place，05。

Let's go over what we know so far from this class。Expected values of properties of distributions。

The population mean is the center of mass of that population and as it moves around。

 the distribution would move around。

![](img/eeddd8791d00f872bd821eda2c58a345_77.png)

The sample mean is the center of mass of the observed data。



![](img/eeddd8791d00f872bd821eda2c58a345_79.png)

The sample mean is an estimate of the population mean。



![](img/eeddd8791d00f872bd821eda2c58a345_81.png)

And the sample mean is unbiased， and what this means is the population mean of the distribution of sample means is exactly the population mean that it's trying to estimate。

And it's good that we know this because。We can actually estimate the population distribution quite well if we collect a lot of data。

 but we only get one sample means so we don't get information about distributions of sample means from the data itself。

 we only get one sample mean， so the fact that we know these properties about sample means is quite useful。



![](img/eeddd8791d00f872bd821eda2c58a345_83.png)

![](img/eeddd8791d00f872bd821eda2c58a345_84.png)

![](img/eeddd8791d00f872bd821eda2c58a345_85.png)

And then the final bullet point is that the more data that goes into the sample mean。

 the more concentrated its density mass function is around the population mean。

 and we also saw that at the more Gaussian issue it was looking even in these odd cases like flipping a coin and rolling a die。

 and so we'll talk more about those in the subsequent lectures。



![](img/eeddd8791d00f872bd821eda2c58a345_87.png)