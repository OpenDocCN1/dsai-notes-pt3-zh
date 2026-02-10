# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P3：2_02 02 概率质量函数.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

So probability calculus is useful for understanding the rules that probability must follow and forms the foundation for all thinking on probability。



![](img/b79df388089bd5d031f6bfb1bc4662f1_1.png)

However， we need something that's a bit easier to work with for numeric outcomes of experiments where here I'm using the word experiment in a broad sense。

So densities and mass functions for random variables are the best starting point for this。

 And this is all we will need。 Probably the most famous example of a density is the so called bell curve。

 So in this class， you'll actually learn what it means to say that the data follow a bell curve。

You'll actually learn what the be curve represents， among other things。

 you'll know that when you talk about probabilities associated with the bell curve or the normal distribution that you're talking about population quantities。

 you're not talking about a statement about what occurs in the data。

How this is going to work and where we're going with this is that we're going to collect data that it's going to be used to estimate properties of the population。



![](img/b79df388089bd5d031f6bfb1bc4662f1_3.png)

![](img/b79df388089bd5d031f6bfb1bc4662f1_4.png)

Okay， and that's where we'd like to head， but first before we start working with the data。

 we need to develop our intuition for how the population quantities work。

A random variable is the numeric outcome of an experiment。

 So the random variables that we will study come in two kinds， discretereet or continuous。

 Discreet are ones that you can count like number of web hits or the number the different outcomes that a dye can take。

 or even things that aren't even numeric， like hair color， And we can assign the numeric value。

1 for blonde，2 for brown，3 for black and so on。

![](img/b79df388089bd5d031f6bfb1bc4662f1_6.png)

Continuous random variables can take any value in a continuum。

 The way we work with discrete random variables is we're going to assign a probability to every value that they can take。

 The way that we' are going to work with continuous random variables is we' are going to assign probabilities to ranges that they can take。



![](img/b79df388089bd5d031f6bfb1bc4662f1_8.png)

Let's just go over some simple examples of things that can be thought of as random variables。

So the biggest ones for building up our intuition in this class will be the flip of a coin and we'll either say heads or tails or0 or1。

 This is a discrete random variable because it can only take two levels。

 The outcome of the role of a die is another discrete random variable。



![](img/b79df388089bd5d031f6bfb1bc4662f1_10.png)

Because it can only take one of six possible values。

 These are kind of silly random variables because they the probability mechanics is so conceptually simple。

 Some more complex random variables are given below。 For example。

 the amount of what the website traffic on a given day。

 the number of web hits would be account random variable will likely treat that as discrete。 However。

 we don't really have an upper bound on it。 So it's an interesting kind of discrete random variable。

 We'll use the Poson distribution likely to model that。



![](img/b79df388089bd5d031f6bfb1bc4662f1_12.png)

![](img/b79df388089bd5d031f6bfb1bc4662f1_13.png)

The BMI of a subject four years after a baseline measurement is a somewhat random example I came up with。

 and in this case we would likely model BMI body mass index as a continuous random variable。



![](img/b79df388089bd5d031f6bfb1bc4662f1_15.png)

![](img/b79df388089bd5d031f6bfb1bc4662f1_16.png)

The hypertension status of a subject randomly drawn from a population could be another random variable Here。

 we might give a person a one if they have hypertension or were diagnosed with hypertension and a 0 otherwise。

 So this random variable would likely be modeled as discrete or would be modeled as discrete。



![](img/b79df388089bd5d031f6bfb1bc4662f1_18.png)

The number of people who click on an ad， again， this is another discrete random variable。

 but an unbounded one。So but still， we would still assign a probability for zero clicks， one clicks。

 two clicks， three clicks， and so on。So intelligence quots are often modeled as continuous。



![](img/b79df388089bd5d031f6bfb1bc4662f1_20.png)

When we talked about discrete random variables， we said that the way that we're going to work with probability for them。

Is to assign a probability to every value that they can take。

 So why don't we just call that a function。 We'll call it the probability mass function。

 And this is simply the function that takes any value that a discrete random variable can take and assigns the probability that it takes that specific value。

 So a PM F for a di roll would assign 1，6 for the value 1，1，6 for the value 2，1，6 for the value 3。

 and so on。

![](img/b79df388089bd5d031f6bfb1bc4662f1_22.png)

![](img/b79df388089bd5d031f6bfb1bc4662f1_23.png)

But you can come up with rules that a PMF must satisfy in order to then satisfy the basic rules of probability that we outlined at the beginning of the class。

First， it must always be larger than zero because we larger than are equal to0。

 because we've already seen that a probability has to be a number between zero and1 inclusive。

But then also the sum of the possible values that the random variable can take has to add up to one。

 just like if I add up the probability of die takes the value 1 plus the probability that it takes the value 2。

 plus the probability that takes a value 3， plus the value it takes4， 5。

 and 6 that has to add up to1 otherwise。

![](img/b79df388089bd5d031f6bfb1bc4662f1_25.png)

![](img/b79df388089bd5d031f6bfb1bc4662f1_26.png)

The probability of something happening， right， that the die takes one of the possible values would not add up to one。

 which would violate one of our basic tenets of probability。

 So all PMmF has to satisfy is these two rules。 We won't worry too much about these rules。 Instead。

 we will work with。

![](img/b79df388089bd5d031f6bfb1bc4662f1_28.png)

Probability mass functions that are particularly useful， like the binomial one。

 the canonical one for flipping a coin， and the Poisson one， the canonical one for modeling counts。



![](img/b79df388089bd5d031f6bfb1bc4662f1_30.png)

Let's go over perhaps the most famous example of a probability mass function。

 the result of a coin flip， the so called Bernoulli distribution。

So let's let capital X be the result of a coin flip where x equal0 represents tails and x equal 1 represents heads。

Here we're using the notation where an uppercase letter represents a potentially unrealized value of the random variable。

 so it makes sense to talk about the probability that x equals 0 and the probability that capital x equals 1。

Whereas a lowercase x is just a placeholder that we're going to plug a specific number into。

 So in the PMmF down here， we have Px equals1 half to the x，1 half to the1 minus x。

 So if we plug in x equal to 0。

![](img/b79df388089bd5d031f6bfb1bc4662f1_32.png)

We get12。 and if we plug in x equal to 1， we get one2。

 and this merely says that the probability that the random variable takes the value 0 is12 and the probability that the random variable takes the value 1 is also12。

This is for a fair coin。 But what if we had an unfair coin。

 Let's let theta be the probability of a head。

![](img/b79df388089bd5d031f6bfb1bc4662f1_34.png)

And 1 minus theta be the probability of a tail where theta is some number between 0 and 1。

Then we could write our probability mass function like this P of x is theta to the x。

1 minus theta to the 1 minus x。

![](img/b79df388089bd5d031f6bfb1bc4662f1_36.png)

Now， notice if I plug in a lowercase x of 1， we get theta。 and if I in a plug in a lowercase x of 0。

 I get 1 minus theta。 Thus， for this population distribution， the probability。

 a random variable takes the value 0 is 1 minus theta。

 and the probability that it takes the value 1 is theta， This is incredibly useful， for example。

 for modeling the prevalence of something。 For example。

 if we wanted to model the prevalence of hypertension。

 we might assume that the population or the sample that we're getting is。



![](img/b79df388089bd5d031f6bfb1bc4662f1_38.png)

Not unlike flips of a biased coin with a success probability theta。

And just to connect it to what we'll be doing in the future， the issue is that we don't know theta。

 so we're going to use our data to estimate this population proportion。



![](img/b79df388089bd5d031f6bfb1bc4662f1_40.png)