# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P45：44_显著性水平、p值和F统计量.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/7910dfbf9918bece9384dc84f17a5b5c_0.png)

Let's start here with the F statistic。The nu hypothesis for the F statistic。

 which is just a test statistic for regression， is that the data can be modeled by setting all of our betas to zero。



![](img/7910dfbf9918bece9384dc84f17a5b5c_2.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_3.png)

Now， when we think back to linear regression， each one of our betas is a parameter that's going to say the coefficient for each one of our features。

 So the question being， does adding the features actually give us an extra indicator of what the outcome will actually be compared to just taking the mean of that outcome variable。



![](img/7910dfbf9918bece9384dc84f17a5b5c_5.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_6.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_7.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_8.png)

So to the right， these will be typical results that you'll see when you run stats models for linear regression。

 so you'll get all of these statistics。

![](img/7910dfbf9918bece9384dc84f17a5b5c_10.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_11.png)

And the idea being that you will reject the null hypothesis。

 the null hypothesis being that you are not getting any better than the mean value。



![](img/7910dfbf9918bece9384dc84f17a5b5c_13.png)

If your P value is small enough for your F statistic。



![](img/7910dfbf9918bece9384dc84f17a5b5c_15.png)

So you see here we have the F statistic， which is a number。

 and that number is going to relate to some probability， that probability being very， very low。

 and that's going to be the probability of coming up with the data that you came up with。



![](img/7910dfbf9918bece9384dc84f17a5b5c_17.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_18.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_19.png)

Given that the coefficients are not actually going to have any effect。



![](img/7910dfbf9918bece9384dc84f17a5b5c_21.png)

So the probability of just using the mean and coming up with values that you did is going to be very。

 very low， so you would reject the null hypothesis and assume that those coefficients actually do have an effect on the outcome variable。



![](img/7910dfbf9918bece9384dc84f17a5b5c_23.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_24.png)

Now let's talk about power and sample size， if you think about it many 5% significant tests looking for a significant results。

 the chances are if you do many tests that you'll get at least one type1 error type 1 error again meaning that you accidentally reject the null when the null was true。

 so incorrectly rejecting the null。

![](img/7910dfbf9918bece9384dc84f17a5b5c_26.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_27.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_28.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_29.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_30.png)

So the idea being if you run 10 tests， you are likely to get at least one time where you accidentally reject the null because you will come up with extreme data at least once in one of these 10 samples。



![](img/7910dfbf9918bece9384dc84f17a5b5c_32.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_33.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_34.png)

The probability of at least one type1 error is approximately 1-1-0。

05 to the power of the number of tests。 Think here， starting with just one test。

 there's only a 5 per cent chance， of incorrectly rejecting the null， right。

5 per cent chance of if there's no effects， given whatever changes you've made。



![](img/7910dfbf9918bece9384dc84f17a5b5c_36.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_37.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_38.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_39.png)

Of accidentally saying there is an effect。

![](img/7910dfbf9918bece9384dc84f17a5b5c_41.png)

But once you do two tests， then you have 0。95 square chance of。



![](img/7910dfbf9918bece9384dc84f17a5b5c_43.png)

Correctly sticking with the null and one minus that value of coming up with an extreme value。



![](img/7910dfbf9918bece9384dc84f17a5b5c_45.png)

At least one time in one of these two results。 And as you add more and more tests。

 you are more and more likely to come up with at least one type one error。



![](img/7910dfbf9918bece9384dc84f17a5b5c_47.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_48.png)

And an approximation to keep in mind is this is roughly 0。05 times the number of tests。

 If you have 10 or fewer tests。 So if you imagine you are just going to look at this graph and say I ran 10 tests。

 you have approximately a 50% chance of at least one type on error。

 at least accidentally rejecting the null when it was indeed true。



![](img/7910dfbf9918bece9384dc84f17a5b5c_50.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_51.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_52.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_53.png)

So how do we account for this？We use what's called the boon Ferrai correction。

 and that says choose a P threshold so that the probability of making a type 1 error sum no effect is 5%。

 So I're going to adjust that P threshold according to the number of tests that you have。



![](img/7910dfbf9918bece9384dc84f17a5b5c_55.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_56.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_57.png)

So typically you use a peak threshold that is equal to， let's say it's rather than 5% rather 0。05。

 you do 0。05 divided by the number of tests that you're going to do。

 and that will lower that value to the point that you won't have the same issue of if you run a bunch of tests that you'll be very likely to have a type1 error。



![](img/7910dfbf9918bece9384dc84f17a5b5c_59.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_60.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_61.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_62.png)

And that allows for the probability of a typey1 error to be controlled。

 but again at the cost of power， power being the idea that we discussed earlier in regards to correctly rejecting the null。

 we're going to be less likely to be able to correctly reject the null。



![](img/7910dfbf9918bece9384dc84f17a5b5c_64.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_65.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_66.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_67.png)

And effects either need to be larger or the tests need larger samples to be detected given the boonfroni correction。



![](img/7910dfbf9918bece9384dc84f17a5b5c_69.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_70.png)

And the best practice is to limit the number of comparisons done to a few well motivated cases。

 so you don't want to necessarily be running all of these tests that you see here。

 but trying to limit it down to well motivated cases。



![](img/7910dfbf9918bece9384dc84f17a5b5c_72.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_73.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_74.png)

So to recap everything we learned in this section。

![](img/7910dfbf9918bece9384dc84f17a5b5c_76.png)

We went over hypothesis testing and it's。

![](img/7910dfbf9918bece9384dc84f17a5b5c_78.png)

Frequent his sense with choosing P values and finding the significance levels。



![](img/7910dfbf9918bece9384dc84f17a5b5c_80.png)

And we discussed how that plays in with sample size as well as power trade offs with the Benfroni correction。



![](img/7910dfbf9918bece9384dc84f17a5b5c_82.png)

All right， with that， I look forward to seeing you in the next lecture。

 which will go over the notebook in regards to how to do hypothesis testing in Python。



![](img/7910dfbf9918bece9384dc84f17a5b5c_84.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_85.png)

![](img/7910dfbf9918bece9384dc84f17a5b5c_86.png)