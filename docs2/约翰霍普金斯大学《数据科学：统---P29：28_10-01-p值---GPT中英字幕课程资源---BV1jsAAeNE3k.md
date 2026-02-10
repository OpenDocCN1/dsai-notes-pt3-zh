# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P29：28_10 01 p值.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

![](img/4e3c9bf69de5606663cfe3a9864b188b_0.png)

Hi， my name is Brian Caho， and this is the lecture on P valuesue in the statistical inference Coursera class as part of our data science specialization。

 This class is co taughted with my co instructors， Jeff Leeak and Roger Pang。

 role in the Department of Biostatistics at the Johns Hopkins Bloomberg School of Public Health。



![](img/4e3c9bf69de5606663cfe3a9864b188b_2.png)

P values are the most common measure of statistical significance。

 basically every statistical software that performs a hypothesis test outputs a P value for you。



![](img/4e3c9bf69de5606663cfe3a9864b188b_4.png)

And because they're so popular， and because often they get misinterpreted。

 they're quite controversial among statisticians。

![](img/4e3c9bf69de5606663cfe3a9864b188b_6.png)

And so what I give here are some comments both in favor of and some papers and commentaries against P values in this class we're not going to focus too much on these controversies。

 but instead are just going to focus on how do you generate a P value and how do you correctly interpret it。

The basic idea of a P value is to start under the null hypothesispo， assume that nothing is going on。

 and then calculate the probability of obtaining evidence as are more extreme than we actually obtained under this null hypothesispo。

 basically how unusual is the result we got if the null hypothesispo is true。



![](img/4e3c9bf69de5606663cfe3a9864b188b_8.png)

So let's go through the approach through maybe three simple steps。

 and then we'll go through basic calculations in the next set of slides。



![](img/4e3c9bf69de5606663cfe3a9864b188b_10.png)

So first of all， you get the hypothetical distribution of a data summary。

 which we'll just call statistic like our test statistic from the T lecture。

And figure out its distribution when nothing is going on。

 the so called null distribution of the statistic。Then we calculate the statistic with the data that we actually have。

 so for example， we calculate our T statistic， we actually plug in the empirical mean。

 subtract off the hypothesized mean and divide by the standard error。



![](img/4e3c9bf69de5606663cfe3a9864b188b_12.png)

Then we calculate the probability of obtaining a statistic as or more extreme， in other words。

 we compare what we calculated to our hypothetical distribution and we see how extreme it is。

In toward the alternative。So if the P value is small。

 what you're saying is the probability of observing a test statistic as extreme as we saw is low if the no hypothesis were true。



![](img/4e3c9bf69de5606663cfe3a9864b188b_14.png)

Okay， let's go over P values with a little bit more formality。



![](img/4e3c9bf69de5606663cfe3a9864b188b_16.png)

So the P value is the probability under the no hypothesis of obtaining evidence as or more extreme than was actually obtained。

So。And usually we're talking about evidence here in terms of the test stat。

 so it's the probability of obtaining a test statistic as or more extreme in favor of the alternative than was actually obtained。



![](img/4e3c9bf69de5606663cfe3a9864b188b_18.png)

So if your P value is small。Then either， the null hypothesis is true。

 and you've observed something that is highly supportive of the alternative。That was quite unlikely。

Or the null hypothesis is false。

![](img/4e3c9bf69de5606663cfe3a9864b188b_20.png)

So let's go through a quick just numerical example， so we've covered the T statistic。



![](img/4e3c9bf69de5606663cfe3a9864b188b_22.png)

And simple T test， so imagine if you wanted to test mu equal to mu n versus mu greater than mu n。

 and our T statistic worked out to be 2。5 on 15 degrees of freedom。

What is the probability of getting a T statistic as large as 2。5？Under this in this scenario。



![](img/4e3c9bf69de5606663cfe3a9864b188b_24.png)

Well， here we can calculate it， it's just PT 2。5。In 15，15 for the degrees of freedom。

 we want lower dot tail equals false because we want the probability being larger than 2。5。

 right as are more extreme in the direction of the alternative， and that works out to be about 1%。



![](img/4e3c9bf69de5606663cfe3a9864b188b_26.png)

So therefore， they're probably seeing evidence as are more extreme。

Then actually obtained under the nu hypothesis is 1%。 so either the null hypothesis is true。

 and we've seen an exceptionally large T statistic or the nu hypothesis is false。



![](img/4e3c9bf69de5606663cfe3a9864b188b_28.png)

So there's another way to think about the P value as the so called attain significance level。

 and let's go through that really quickly。

![](img/4e3c9bf69de5606663cfe3a9864b188b_30.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_31.png)

So recall we went through an example where our test statistic was2 for H not mu equal to 30 versus mu greater than 30 so test statistics larger than two or I'm sorry test statistics that are larger are going to be more supportive of the alternative where2 here is two standard that our test statistic was two standard errors above the hypothesized mean of 30。

 Let's assume that our test statistic is standard normal distributed rather than t distributed just to make our discussion a little bit easier。



![](img/4e3c9bf69de5606663cfe3a9864b188b_33.png)

Now， if we were to set alpha equal to 0。05。

![](img/4e3c9bf69de5606663cfe3a9864b188b_35.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_36.png)

We know that we would reject because we know the point， the rejection region。

And the quantile that we would reject for at 0。05。

![](img/4e3c9bf69de5606663cfe3a9864b188b_38.png)

So that that area was 0。05 would be the quantile would be 1。645 since we know two。



![](img/4e3c9bf69de5606663cfe3a9864b188b_40.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_41.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_42.png)

Since we know two。

![](img/4e3c9bf69de5606663cfe3a9864b188b_44.png)

Lies above 1。645 we would reject。

![](img/4e3c9bf69de5606663cfe3a9864b188b_46.png)

Now， imagine if instead of 0。05， imagine if we did 0。04。

 then we would have another line that was a little bit closer than 1。645。



![](img/4e3c9bf69de5606663cfe3a9864b188b_48.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_49.png)

So what if we were to find the exact error rate where the line fell exactly on2。

 well that would simply be calculating this probability right here of two or larger and that's nothing other than the P value we just did that calculation that's the probability of getting a test statistic as large or larger than  two under the no hypothesis。



![](img/4e3c9bf69de5606663cfe3a9864b188b_51.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_52.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_53.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_54.png)

So at any rate， another way to think about the P value is it's the smallest value for alpha for which you would still reject a nu hypothesis。

 and so because of that they call it the attained significance level。

 and what this means is that the P value is an extremely convenient test statistic to communicate to people。



![](img/4e3c9bf69de5606663cfe3a9864b188b_56.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_57.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_58.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_59.png)

Because when you give it to them， they can test it versus whatever alpha level they would like。



![](img/4e3c9bf69de5606663cfe3a9864b188b_61.png)

Let's reiterate some of the points we made on the previous slide。



![](img/4e3c9bf69de5606663cfe3a9864b188b_63.png)

So by reporting a P value， your reader or whoever you're giving the P value to to interpret it can perform the hypothesis test at whatever alpha level he or she chooses to。

The simple rule is if the P value is less than the alpha level， then you reject the no hypothesis。

 if the P value is greater than it， then you fail to reject。

Now we calculated our P values for one sided hypothesis test， T and Z test。



![](img/4e3c9bf69de5606663cfe3a9864b188b_65.png)

In order to get the two sided hypothesis test， you have to account for the evidence as or more extreme too large or as or more extreme to small negative。

 so because the equal probability in either tail， you wind up doubling the P value I would give a cautionary note that the software automatically interprets for most test automatically interprets the test as a two sided test。

 most of the time they'll denote this as P value for a two sided test。

 but if they don't they're always calculating the P value for a two sided test。

 the other thing I would note is that。

![](img/4e3c9bf69de5606663cfe3a9864b188b_67.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_68.png)

If you happen to take some more advanced classes and statistics that cover things like chiI squared test。

 those P values are automatically in a sense two sided， you would not have to double them。



![](img/4e3c9bf69de5606663cfe3a9864b188b_70.png)

![](img/4e3c9bf69de5606663cfe3a9864b188b_71.png)