# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P24：23_08 04 关于方差不等的说明.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_0.png)

So hopefully the formula for the unequal variance case looks pretty familiar to you。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_2.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_3.png)

It's the difference in the means。Plus or minus a t quantile times a standard error。

 the standard error is calculated assuming there's a different variance in each of the two groups。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_5.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_6.png)

It turns out that if the X observations and the Y observations are II normal。

 potentially with different means and potentially with different variances。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_8.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_9.png)

The relevant normalized statistic does not follow a T distribution。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_11.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_12.png)

Instead， it can be approximated by a T distribution。

Where we choose a rather elaborate formula for the degrees of freedom。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_14.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_15.png)

Now no one remembers this degrees of freedom calculation and it's a very odd calculation because it doesn't just involve the sample sizes。

 but actually the estimated standard deviations and variances from the two groups。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_17.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_18.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_19.png)

Nonetheless， if you plug in this potentially fractional degrees of freedom， you get a T calculation。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_21.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_22.png)

That very closely approximates the relevant distribution， which is not actually a t distribution。

 And it turns out that it works well enough that I can give the statement that when you're in doubt。

 just use the unequal variance interval。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_24.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_25.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_26.png)

On this page， I simply show churning through the calculations for the oral contraceptive example from earlier。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_28.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_29.png)

You might want to go through this calculation just so you can at once convince yourself that you can plug into the standard deviation formula。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_31.png)

Particularly the degrees of freedom that you get in this case is 15。04。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_33.png)

Nonetheless， typically， when we want unequal variance T test。

 we simply use the R command T dot test with Vard at equal equals false。

 and that'll do the relevant T test with unequal variances and produce the relevant t quantile with unequal variances。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_35.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_36.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_37.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_38.png)

So let's summarize what we talked about today。We talked about creating intervals using the T distribution。

 some of the handiest intervals in all of statistics。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_40.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_41.png)

When we have single observations or paired observations for which we've taken the difference。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_43.png)

We use the T interval to create intervals that are highly robust to the underlying assumptions regarding the distribution of the data。

 However， we have talked about a couple of cases where it's probably preferable to use something other than the T distribution and T intervals。

 For example， we talked about when the data are highly skewed。

 you may either want to take a log or look for different procedures。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_45.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_46.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_47.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_48.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_49.png)

In addition， when your data is binary， you might consider something like looking at odds ratios。

 which we will cover in our generalized linear model component of the regression class。

 The same can be said for count data， where we'll talk about Poisson models and generalized linear models for rates。



![](img/dfd4e19e04b1d05b14a39feb2adc3aba_51.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_52.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_53.png)

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_54.png)

Again， in our regression class。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_56.png)

For several of the other two group special cases， the Class mathematicalthematic Bitatistics Boot Camp2。

 also on Coursera， covers many of them。

![](img/dfd4e19e04b1d05b14a39feb2adc3aba_58.png)