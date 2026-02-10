# 谷歌高阶数据分析4：《统计的力量》the-power-of-statistics（中英双字） - P39：39_04_02_置信区间介绍.zh_en - GPT中英字幕课程资源 - BV1yk4y1G7Qm

![](img/f3364c4f1f12d972df50c25a6ff86734_0.png)

Earlier， we talked about how data professionals make point estimates about population parameters。

 for example， based on a sample of 100 penguins， a data professional might estimate that the mean weight of a population of 10。

000 penguins is 31， or based on a poll of 100 voters。

 a data professional might estimate that 55% of all 100。

000 voters prefer a certain candidate in an upcoming election。

A point estimate uses a single value to estimate a population parameter。In contrast。

 an intervalch estimate uses a range of values to estimate a population parameter。

A confidence interval is a type of interval estimate。For example， for penguin weight。

 you might construct a 95% confidence interval between 28 and 32 pounds， or for the election poll。

 you might construct a 99% confidence interval between 51 and 57%。In this video。

 we'll go over the main components of a confidence interval and discuss how confidence intervals help you express the uncertainty of an estimate。

 Typically， data professionals use confidence intervals rather than point estimates to share their results。

A point estimate can be useful， but a single value like 30 pounds does not express the uncertainty built into any estimate。

This uncertainty is due to the method of random sampling。 For the purpose of our example。

 let's imagine that the mean weight of all 10000 penguins is 31。

 Although you wouldn't know this unless you weight every penguin。In practice。

 data professionals usually select one random sample because repeated random sampling is often expensive and time consuming。

Since the sample is random， the mean of any given sample will likely not be equal to the actual population mean。

For example， you may happen to weigh a sample of penguins that have recently struggled to find food。

 so they only weigh 28， or you may weigh a sample of penguins that recently fed on a fish buffet and are above average at 32。

Either way， your sample estimate will not equal the population mean of 31 pounds。

So if you only provide a sample statistic or point estimate， it won't be as accurate。

Confidence intervals give data professionals a way to express the uncertainty caused by randomness and provide a more reliable estimate。

Along with the sample statistic， a confidence interval includes a margin of error and a confidence level。

 Let's explore our penguin example to get a better idea of each component。

We'll start with our sample statistic。 The sample mean of our group of penguins is 30。 Next。

 will'll determine the interval for our estimate， which is defined by the sample statistic plus or minus the margin of error。

The margin of error represents the maximum expected difference between a population parameter and a sample estimate。

In other words， this is the amount that a data professional expects their estimate might vary from their actual amount。

So if our sample sta for our penguins is 30 pounds and our margin of error is plus or minus2 pounds。

That means that the lower limit of the interval is 28 pounds and the upper limit is 32 pounds。

The upper limit of the interval is 30 plus 2 equals 32 pounds。

This range of values expresses the uncertainty in your estimate due to random sampling。

 Calalculating the margin of error involves multiplying the standard error by a Z score。 Remember。

 a Z score measures the distance of the data point from the population mean in a standard normal distribution。

 Typically， you'll use a computer for these calculations。

Along with a sample statistic and margin of error， a confidence interval also includes a confidence level。

 The confidence level describes the likelihood that a particular sampling method will produce a confidence interval that includes the population parameter。

For example， say you use a 95% confidence level to calculate a confidence interval between 28 and 32 pounds。

Technically， this means that if you took 100 random samples from the penguin population and calculated a 95% confidence interval for each sample。

 then approximately 95 of the 100 intervals or 95% of the total would contain the actual population mean。

One such interval will be the range of values between 20 and 32 pounds。

If this explanation seems rather abstract right now， don't worry in a later video。

 we'll discuss confidence level in more detail。As a data professional。

 you can choose your own confidence level based on the desired accuracy of your estimate。

Common confidence levels are 90，95 and 99%。95% is a popular choice。 For example。

 most selection polls report a 95% confidence level。

 and most A B tests recommend using a confidence level of 95%。

Note that there is nothing magical about 95%。 This is a choice based on tradition in statistical research and education。

 You can adjust the confidence level to meet the requirements of your analysis。

Let's explore another example。 Imagine you're a data professional working for a fashion company。

 Your manager asks you to estimate sales revenue for the new line of spring clothing。

When you meet with stakeholders， you might say。I think we'll do $1 million in sales。

 or you might say， based on a 95% confidence level。

 I estimate that our sales revenue will be between $950000 and $150000。

The first statement offers a point estimate， the second statement provides a confidence level and an interval estimate and communicates the uncertainty in the estimate。



![](img/f3364c4f1f12d972df50c25a6ff86734_2.png)

It gives your stakeholders more information and helps them make more informed decisions about issues related to future sales revenue。

As a data professional， you also have to make sure your stakeholders understand your results。

 so it's your job to clearly communicate how to interpret a confidence interval。

 We'll discuss interpretation more later on。