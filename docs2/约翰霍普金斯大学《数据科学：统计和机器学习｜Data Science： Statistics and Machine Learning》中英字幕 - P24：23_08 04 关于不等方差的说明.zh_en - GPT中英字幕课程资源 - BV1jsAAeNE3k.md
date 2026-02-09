# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P24：23_08 04 关于不等方差的说明.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

So hopefully the formula for the unequal variance case looks pretty familiar to you。

It's the difference in the means。Plus or minus a t quantile times a standard error。

 the standard error is calculated assuming there's a different variance in each of the two groups。



![](img/13414a886d93f54cef5af9a60c8d770c_1.png)

It turns out that if the X observations and the Y observations are II normal。

 potentially with different means and potentially with different variances。

The relevant normalized statistic does not follow a T distribution。



![](img/13414a886d93f54cef5af9a60c8d770c_3.png)

Instead， it can be approximated by a T distribution。

Where we choose a rather elaborate formula for the degrees of freedom。



![](img/13414a886d93f54cef5af9a60c8d770c_5.png)

![](img/13414a886d93f54cef5af9a60c8d770c_6.png)

Now no one remembers this degrees of freedom calculation and it's a very odd calculation because it doesn't just involve the sample sizes。

 but actually the estimated standard deviations and variances from the two groups。



![](img/13414a886d93f54cef5af9a60c8d770c_8.png)

![](img/13414a886d93f54cef5af9a60c8d770c_9.png)

Nonetheless， if you plug in this potentially fractional degrees of freedom， you get a T calculation。

That very closely approximates the relevant distribution， which is not actually a t distribution。

 And it turns out that it works well enough that I can give the statement that when you're in doubt。

 just use the unequal variance interval。

![](img/13414a886d93f54cef5af9a60c8d770c_11.png)

![](img/13414a886d93f54cef5af9a60c8d770c_12.png)

On this page， I simply show churning through the calculations for the oral contraceptive example from earlier。

You might want to go through this calculation just so you can at once convince yourself that you can plug into the standard deviation formula。

Particularly the degrees of freedom that you get in this case is 15。04。Nonetheless， typically。

 when we want unequal variance T test， we simply use the R command T dot test with Vard out equal equals false。

 and that'll do the relevant T test with unequal variances and produce the relevant t quantile with unequal variances。



![](img/13414a886d93f54cef5af9a60c8d770c_14.png)

![](img/13414a886d93f54cef5af9a60c8d770c_15.png)

So let's summarize what we talked about today。We talked about creating intervals using the T distribution。

 some of the handiest intervals in all of statistics。

When we have single observations or paired observations for which we've taken the difference。

We use the T interval to create intervals that are highly robust to the underlying assumptions regarding the distribution of the data。

 However， we have talked about a couple of cases where it's probably preferable to use something other than the T distribution and T intervals。

 For example， we talked about when the data are highly skewed。

 you may either want to take a log or look for different procedures。In addition。

 when your data is binary， you might consider something like looking at odds ratios。

 which we will cover in our generalized linear model component of the regression class。

 the same can be said for count data， where we'll talk about Poisson models and generalized linear models for rates。



![](img/13414a886d93f54cef5af9a60c8d770c_17.png)

Again， in our regression class。For several of the other two group special cases。

 the Class Mathematical Bitatistics Boot Camp2， also on Coursera， covers many of them。



![](img/13414a886d93f54cef5af9a60c8d770c_19.png)