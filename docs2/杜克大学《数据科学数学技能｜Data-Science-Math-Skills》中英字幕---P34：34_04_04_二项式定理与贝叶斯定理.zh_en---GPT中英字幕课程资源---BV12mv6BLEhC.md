# 杜克大学《数据科学数学技能｜Data Science Math Skills》中英字幕 - P34：34_04_04_二项式定理与贝叶斯定理.zh_en - GPT中英字幕课程资源 - BV12mv6BLEhC

![](img/63eb191f4c2bc0db5f8e1f25472817fd_0.png)

We have only one more topic to complete our basic probability modules。

This is something very special called the binomial Ethereum。

 It's binomial because it's used when there are two possible outcomes。A success or a non success。 So。

 for example， if I'm flipping a coin and I consider heads to be a success。

 the number of heads that I get would be the number of successes。

The number of coin flips would be the number of trials。

 so I'm interested in trials and I'm interested in successes， and I'm talking about a binary outcome。

 There are only two outcomes like heads or tails okay。

The individual probability of success with a fair coin could be 0。5。

 but using the binomial theorem I'm not limited to fair coins or situations where the probability of success is 0。

5。The probability can be any value greater than 0 and less than one。

So let's say I want to know what is the probability of getting a certain number of heads in a string of。

Coin tosses。The binomial theorem will tell me the answer。And this is the binomial theorem。

It's n choose S。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_2.png)

Times the probability raised to the number of successes。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_4.png)

Times 1 minus the probability note that this is also the probability of failure。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_6.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_7.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_8.png)

It's raised to the n minus S， and this would be the number of failures。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_10.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_11.png)

So we have。The number of ways in which you can have S successes in N trials。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_13.png)

Multiplied by the probability of an individual success。Raised to the number of successes。

Multipied by the probability of failure raised to the number of failures。Okay。

So let's try an example。Let's say that I have。72 heads。Out of 100 coin tosses。Of a fair coin。Okay。

What is the probability that that outcome will occur， in other words， with 100 coin tosses。

 I will get exactly 72 successes or 72 heads。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_15.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_16.png)

Well， my。N is equal to 100。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_18.png)

My S or number of successes is equal to 72， and my probability is equal to 0。5。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_20.png)

And my formula will be 100。 choose 72。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_22.png)

Times 05。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_24.png)

To the72。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_26.png)

Times 1-。5， or also 。5 to the。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_28.png)

100-72。Or 28。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_30.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_31.png)

Okay， we'll just pause here for a minute。 if you'd like to try this on your calculator or Excel。

 you can do so， and I'll give you the answer in a moment。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_33.png)

We have。100。Choose 72。5。To the 72 times 0。5 to the 28th。And this is equal to。3。94。Times 10。

The minus6。Okay。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_35.png)

So we have an extremely small probability of getting exactly 72。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_37.png)

Heads in a series of 100 heads。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_39.png)

But now let's ask a little bit more interesting problem or question。Let's say here is our question。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_41.png)

Either。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_43.png)

We have a fairer。Coin。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_45.png)

Its probability is 0。5 of heads。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_47.png)

Or。We have a bent coin。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_49.png)

It has a probability of 055 of heads。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_51.png)

Kai。We've observed the 72 heads out of 100， and we want to know what is the probability that we've observed the fair coin and what is the probability that we've observed the bent coin。

And this is how we would set this problem up using bayes theorem。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_53.png)

We say。Probability of observing the fair coin。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_55.png)

Given 72 heads of 100。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_57.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_58.png)

Is equal to。Probability of observing 72 heads of 100。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_60.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_61.png)

Given the fair coin。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_63.png)

Times the probability that the coin is fair and because we have no basis for knowing whether it is not。

 whether it's fair or not， we are going to start with a prior probability of one half by the principle of indifference。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_65.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_66.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_67.png)

And then we're going to divide to this by the total probability of the data。

 which since we are limited to only the two possible coins。

 is going to be equal to the probability of 72。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_69.png)

![](img/63eb191f4c2bc0db5f8e1f25472817fd_70.png)

Heads out of 100。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_72.png)

Given the fair coin。但昨天。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_74.png)

Plus， the probability of 72 heads。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_76.png)

Of 100。Given the bent coin。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_78.png)

Times1 half。Okay。So as I mentioned before。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_80.png)

The probability on the top。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_82.png)

Is 3。94 times 10。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_84.png)

To the minus6。

![](img/63eb191f4c2bc0db5f8e1f25472817fd_86.png)

And a quick application of the binonial theorem will tell us that this probability is 0。0001972。



![](img/63eb191f4c2bc0db5f8e1f25472817fd_88.png)

So we take this divided by this plus this。And what we're finding out is that。

The probability that we are looking at the fair coin。Is less than 2%。

And the probability that we are looking at the bent coin。Is greater than 98%。

So Bay's theorem has allowed us to determine with near certainty。

Which process with its known parameter。Is responsible for the data that we have observed。

And this is the power of Bays theorem， combined with the binomial theorem。

