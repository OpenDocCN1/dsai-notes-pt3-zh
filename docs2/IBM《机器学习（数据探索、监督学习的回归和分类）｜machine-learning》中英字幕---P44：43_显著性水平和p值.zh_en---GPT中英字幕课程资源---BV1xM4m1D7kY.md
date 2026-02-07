# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P44：43_显著性水平和p值.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this next section， we're going to discuss significance levels as well as P values and how to apply them in practice。

So the learning goals for this section。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_1.png)

Will be to discuss the classical frequencies version of hypothesis testing that you'll see most often using significance levels and P values。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_3.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_4.png)

And with that， we'll also discuss the importance of sample size and its effect on the power of your test。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_6.png)

Now we know the distribution of the null hypothesis， such as the odds， the coin is 5050。

 or the distribution of our campaign assuming absolutely no effect。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_8.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_9.png)

For our difference in campaign。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_11.png)

Now to get a rejection reason， we have to calculate the test statistic。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_13.png)

And we'll choose before testing the data， the level at which we're going to actually reject our null hypothesis。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_15.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_16.png)

So to make this clear， we have to choose the significance level beforehand。

 That significance level should tie closely with how important to you it is to avoid a type 1 or type 2 error。

 as we discussed earlier。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_18.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_19.png)

The idea being a lower significance level。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_21.png)

A lower alpha value means that we would only reject the null if the probability of the data that we see is extremely low assuming the null hypothesis。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_23.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_24.png)

So we must choose an alpha before computing the test statistic if we don't we might be accused of P hacking。

 which is changing the P value for which we will accept or reject the null。

 and if you need to be absolutely certain that you can reject the null so you want to avoid a type 1 error of incorrectly rejecting the null。

 you choose a very low alpha， for example， if a medication has dangerous side effects and the null is that it will not aid in recovery from a disease。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_26.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_27.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_28.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_29.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_30.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_31.png)

And the alternative is that it would aid in the recovery from the disease。

 You want to be very certain that you can reject the null。

 the null being that there's no effect and the alternative being that there maybe is an effect。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_33.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_34.png)

On the other hand， it may not be as strict for deciding whether to increase the font size for advertisements。

 which。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_36.png)

And seeing whether that would have an effect with a null being no effect。 and a type 2 error。

 a failure to reject the null is not as dangerous。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_38.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_39.png)

And it's worth noting that common values that are used for the P values are 0。1， 0。050。01 or even 0。

001 if you want to be really safe as in the example with medication。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_41.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_42.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_43.png)

So what exactly is the P value？

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_45.png)

The P value is the probability under the null distribution of a result as or more extreme than what was actually observed。

 so it's the smallest significance level at which the null hypothesis will be rejected。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_47.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_48.png)

And the confidence interval， on the other hand， are the values for which we accept the null hypothesis。

 essentially the other side of the P value from this rejection region。

 and this will be made clear in the images that we'll see in the next slide。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_50.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_51.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_52.png)

Now， to make our point clear， we'll look here at P values。

 as well as significant levels in relation to the null distribution。

 which will often take on the form of the normal distribution we see here。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_54.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_55.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_56.png)

So if our P value is 0。05， then what we're saying is that we will only reject our null hypothesis of。

 say， no effect when we're running an ad campaign。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_58.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_59.png)

If the value we obtain from our sample data is about two full standard deviations away from the mean value。

 which is here zero， which would signify no effect。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_61.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_62.png)

Now we can see if we look at that top horizontal line on this graph that 95% of our values will fall between two standard deviations in either direction。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_64.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_65.png)

So the idea being， again， if we set P20。05， we had need for this data to fall to the right or to the left of two standard deviations from what we would have assumed for no effect。

 So if we think again to a marketing campaign， this would be the odds。 Now。

 assume we didn't run any campaign。 This would be the odds， given our past data of randomly getting。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_67.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_68.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_69.png)

The sample data that we get。Given that no ad was ran。 So this would happen 5 per cent of the time。

 So it's possible that it could happen just by chance， but it only happened 5 per cent of the time。

 And if we see something as extreme as 5 per cent away， when we actually ran the campaign。

 then we reject the k null that that campaign had no effect。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_71.png)

So let's think about our coin tossing example that we discussed earlier。

 so suppose we roll three heads or we sorry， flip three heads in 10 rolls and 10 flips。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_73.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_74.png)

We see that the odds of getting value as extreme as three heads or less are highlighted here。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_76.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_77.png)

We can add up the probability of zero heads， one heads， two heads， and three heads。

 and say that if we had a fair coin， we would have a 17% chance of getting three heads or less。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_79.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_80.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_81.png)

So under the null hypothesis of a fair coin， a value this extreme would actually occur 17% of the time。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_83.png)

And we wouldn't reject the k null。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_85.png)

So in this coin tossing example， our null hypothesis was that we have a fair coin。

 the probability of heads is equal to 0。5。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_87.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_88.png)

And our alternative is that the coin is unfair and the probability of heads is less than 0。5。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_90.png)

So how can we test the nu hypothesis if we observe three heads in 10 flips？



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_92.png)

So to test the null hypothesis first， we know our null distribution。

 our null distribution is distributed as a binomial distribution with 10 flips where each one has a 50% chance of landing heads。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_94.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_95.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_96.png)

We choose a P value cutoff。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_98.png)

We say that 5% is going to be our cutoff in terms of if it is an extreme value or not。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_100.png)

We calculate the cumulative distribution function of three heads from binomial with a distribution of 10 and 5050 chance of landing heads。

 What this means is we want the cumulative sum of our area for that curve that we saw earlier。

 of getting three heads or less， which also lines with that chart that we saw earlier by adding up the probability of three heads。

2 heads and shorter and shorter。

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_102.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_103.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_104.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_105.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_106.png)

Our cumulative distribution function is equal to 17。1%， which is above our cutoff of 0。5。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_108.png)

So we decide not to reject the null hypothesis of a fair coin。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_110.png)

So we're going to stop here and we'll pick back up with some important implications to keep in mind when you start to use P values yourself。



![](img/a40aaa4c6cf8c958d7d0c70592e2d372_112.png)

![](img/a40aaa4c6cf8c958d7d0c70592e2d372_113.png)