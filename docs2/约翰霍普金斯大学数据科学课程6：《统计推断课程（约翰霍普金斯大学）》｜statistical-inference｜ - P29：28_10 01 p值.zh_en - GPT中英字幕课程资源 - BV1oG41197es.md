# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P29：28_10 01 p值.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/8054562485b521c6dd232f8abf2ff885_0.png)

Hi， my name is Brian Caho， and this is the lecture on P valuesue in the statistical inference Coursera class as part of our data science specialization。

 This class is co taught with my co instructors， Jeff Leeak and Roger Pang。

 role in the Department of Biostatistics at the Johns Hopkins Bloomberg School of Public Health。



![](img/8054562485b521c6dd232f8abf2ff885_2.png)

![](img/8054562485b521c6dd232f8abf2ff885_3.png)

![](img/8054562485b521c6dd232f8abf2ff885_4.png)

P values are the most common measure of statistical significance。

 basically every statistical software that performs a hypothesis test outputs a P value for you。



![](img/8054562485b521c6dd232f8abf2ff885_6.png)

![](img/8054562485b521c6dd232f8abf2ff885_7.png)

And because they're so popular， and because often they get misinterpreted。

 they're quite controversial among statisticians。

![](img/8054562485b521c6dd232f8abf2ff885_9.png)

![](img/8054562485b521c6dd232f8abf2ff885_10.png)

And so what I give here are some comments both in favor of and some papers and commentaries against P values in this class we're not going to focus too much on these controversies but instead are just going to focus on how do you generate a P value and how do you correctly interpret it。

The basic idea of a P value is to start under the null hypothesis， assume that nothing is going on。

 and then calculate the probability of obtaining evidence as are more extreme than we actually obtained under this null hypothesis。

 basically how unusual is the result we got if the null hypothesis is true。



![](img/8054562485b521c6dd232f8abf2ff885_12.png)

![](img/8054562485b521c6dd232f8abf2ff885_13.png)

![](img/8054562485b521c6dd232f8abf2ff885_14.png)

![](img/8054562485b521c6dd232f8abf2ff885_15.png)

So let's go through the approach through maybe three simple steps and then we'll go through basic calculations in the next set of slides。



![](img/8054562485b521c6dd232f8abf2ff885_17.png)

So first of all， you get the hypothetical distribution of a data summary。

 which we'll just call statistic like our test statistic from the T lecture。



![](img/8054562485b521c6dd232f8abf2ff885_19.png)

![](img/8054562485b521c6dd232f8abf2ff885_20.png)

And figure out its distribution when nothing is going on。

 the so called null distribution of the statistic。

![](img/8054562485b521c6dd232f8abf2ff885_22.png)

![](img/8054562485b521c6dd232f8abf2ff885_23.png)

Then we calculate the statistic with the data that we actually have。

 so for example we calculate our T statistic， we actually plug in the empirical mean。

 subtract off the hypothesized mean and divide by the standard error。



![](img/8054562485b521c6dd232f8abf2ff885_25.png)

![](img/8054562485b521c6dd232f8abf2ff885_26.png)

Then we calculate the probability of obtaining a statistic as or more extreme， in other words。

 we compare what we calculated to our hypothetical distribution and we see how extreme it is。



![](img/8054562485b521c6dd232f8abf2ff885_28.png)

![](img/8054562485b521c6dd232f8abf2ff885_29.png)

In toward the alternative。

![](img/8054562485b521c6dd232f8abf2ff885_31.png)

So if the P value is small， what you're saying is the probability of observing a test statistic as extreme as we saw is low if the no hypothesis were true。



![](img/8054562485b521c6dd232f8abf2ff885_33.png)

![](img/8054562485b521c6dd232f8abf2ff885_34.png)

Okay， let's go over P values with a little bit more formality。



![](img/8054562485b521c6dd232f8abf2ff885_36.png)

So the P value is the probability under the no hypothesis of obtaining evidence as or more extreme than was actually obtained。



![](img/8054562485b521c6dd232f8abf2ff885_38.png)

![](img/8054562485b521c6dd232f8abf2ff885_39.png)

So。And usually we're talking about evidence here in terms of the test stat。

 so it's the probability of obtaining a test statistic as or more extreme in favor of the alternative than was actually obtained。



![](img/8054562485b521c6dd232f8abf2ff885_41.png)

![](img/8054562485b521c6dd232f8abf2ff885_42.png)

So if your P value is small。Then either， the null hypothesis is true。

 and you've observed something that is highly supportive of the alternative。



![](img/8054562485b521c6dd232f8abf2ff885_44.png)

![](img/8054562485b521c6dd232f8abf2ff885_45.png)

That was quite unlikely。Or the null hypothesis is false。



![](img/8054562485b521c6dd232f8abf2ff885_47.png)

So let's go through a quick just numerical example， so we've covered the T statistic。



![](img/8054562485b521c6dd232f8abf2ff885_49.png)

And simple T test， so imagine if you wanted to test mu equal to mu n versus mu greater than mu n。

 and our T statistic worked out to be 2。5 on 15 degrees of freedom。



![](img/8054562485b521c6dd232f8abf2ff885_51.png)

![](img/8054562485b521c6dd232f8abf2ff885_52.png)

What is the probability of getting a T statistic as large as 2。5？



![](img/8054562485b521c6dd232f8abf2ff885_54.png)

Under this in this scenario。

![](img/8054562485b521c6dd232f8abf2ff885_56.png)

Well， here we can calculate it， it's just PT 2。5。

![](img/8054562485b521c6dd232f8abf2ff885_58.png)

In 15，15 for the degrees of freedom， we want lower dot tail equals false because we want the probability being larger than 2。

5， right as are more extreme in the direction of the alternative。 and that works out to be about 1%。



![](img/8054562485b521c6dd232f8abf2ff885_60.png)

![](img/8054562485b521c6dd232f8abf2ff885_61.png)

![](img/8054562485b521c6dd232f8abf2ff885_62.png)

So therefore， they're probably seeing evidence as are more extreme。



![](img/8054562485b521c6dd232f8abf2ff885_64.png)

TThen actually obtained under the nu hypothesis is 1%。 So either the null hypothesis is true。

 and we've seen an exceptionally large T statistic， or the nu hypothesis is false。



![](img/8054562485b521c6dd232f8abf2ff885_66.png)

![](img/8054562485b521c6dd232f8abf2ff885_67.png)

![](img/8054562485b521c6dd232f8abf2ff885_68.png)

So there's another way to think about the P value as the so called attain significance level。

 and let's go through that really quickly。

![](img/8054562485b521c6dd232f8abf2ff885_70.png)

![](img/8054562485b521c6dd232f8abf2ff885_71.png)

So recall we went through an example where our test statistic was2 for H not mu equal to 30 versus mu greater than 30。

 so test statistics larger than two or I'm sorry test statistics that are larger are going to be more supportive of the alternative where2 here is two standard that our test statistic was two standard errors above the hypothesized mean of 30。

 Let's assume that our test statistic is standard normal distributed rather than t distributed just to make our discussion a little bit easier。



![](img/8054562485b521c6dd232f8abf2ff885_73.png)

![](img/8054562485b521c6dd232f8abf2ff885_74.png)

![](img/8054562485b521c6dd232f8abf2ff885_75.png)

![](img/8054562485b521c6dd232f8abf2ff885_76.png)

![](img/8054562485b521c6dd232f8abf2ff885_77.png)

Now， if we were to set alpha equal to 0。05。

![](img/8054562485b521c6dd232f8abf2ff885_79.png)

![](img/8054562485b521c6dd232f8abf2ff885_80.png)

We know that we would reject because we know the point， the rejection region。



![](img/8054562485b521c6dd232f8abf2ff885_82.png)

And the quantile that we would reject for at 0。05。

![](img/8054562485b521c6dd232f8abf2ff885_84.png)

So that that area was 0。05 would be the quantile would be 1。645 since we know two。



![](img/8054562485b521c6dd232f8abf2ff885_86.png)

![](img/8054562485b521c6dd232f8abf2ff885_87.png)

![](img/8054562485b521c6dd232f8abf2ff885_88.png)

Since we know two。

![](img/8054562485b521c6dd232f8abf2ff885_90.png)

Lies above 1。645 we would reject。

![](img/8054562485b521c6dd232f8abf2ff885_92.png)

Now， imagine if instead of 0。05， imagine if we did 0。04。

 then we would have another line that was a little bit closer than 1。645。



![](img/8054562485b521c6dd232f8abf2ff885_94.png)

![](img/8054562485b521c6dd232f8abf2ff885_95.png)

So what if we were to find the exact error rate where the line fell exactly on2。

 well that would simply be calculating this probability right here of2 or larger。

 and that's nothing other than the P value we just did that calculation that's the probability of getting a test statistic as large or larger than  two under the no hypothesis。



![](img/8054562485b521c6dd232f8abf2ff885_97.png)

![](img/8054562485b521c6dd232f8abf2ff885_98.png)

![](img/8054562485b521c6dd232f8abf2ff885_99.png)

![](img/8054562485b521c6dd232f8abf2ff885_100.png)

![](img/8054562485b521c6dd232f8abf2ff885_101.png)

So at any rate， another way to think about the P value is it's the smallest value for alpha for which you would still reject a nu hypothesis。

 and so because of that they call it the attained significance level。

 and what this means is that the P value is an extremely convenient test statistic to communicate to people。



![](img/8054562485b521c6dd232f8abf2ff885_103.png)

![](img/8054562485b521c6dd232f8abf2ff885_104.png)

![](img/8054562485b521c6dd232f8abf2ff885_105.png)

Because when you give it to them， they can test it versus whatever alpha level they would like。



![](img/8054562485b521c6dd232f8abf2ff885_107.png)

Let's reiterate some of the points we made on the previous slide。



![](img/8054562485b521c6dd232f8abf2ff885_109.png)

So by reporting a P value， your reader or whoever you're giving the P value to to interpret it can perform the hypothesis test at whatever alpha level he or she chooses to。



![](img/8054562485b521c6dd232f8abf2ff885_111.png)

![](img/8054562485b521c6dd232f8abf2ff885_112.png)

The simple rule is if the P value is less than the alpha level， then you reject the no hypothesis。

 if the P value is greater than it， then you fail to reject。



![](img/8054562485b521c6dd232f8abf2ff885_114.png)

![](img/8054562485b521c6dd232f8abf2ff885_115.png)

![](img/8054562485b521c6dd232f8abf2ff885_116.png)

Now we calculated our P values for one sided hypothesis test， T and Z test。



![](img/8054562485b521c6dd232f8abf2ff885_118.png)

In order to get the two sided hypothesis test， you have to account for the evidence as or more extreme。

 too large or as or more extreme too small negative， so because the equal probability in either tail。

 you wind up doubling the P value I would give a cautionary note that the software automatically interprets for most test automatically interprets the test as a two sided test。

 most of the time they'll denote this as P value for a two sided test。

 but if they don't they're always calculating the P value for a two sided test。

 the other thing I would note is that。

![](img/8054562485b521c6dd232f8abf2ff885_120.png)

![](img/8054562485b521c6dd232f8abf2ff885_121.png)

![](img/8054562485b521c6dd232f8abf2ff885_122.png)

![](img/8054562485b521c6dd232f8abf2ff885_123.png)

![](img/8054562485b521c6dd232f8abf2ff885_124.png)

![](img/8054562485b521c6dd232f8abf2ff885_125.png)

![](img/8054562485b521c6dd232f8abf2ff885_126.png)

![](img/8054562485b521c6dd232f8abf2ff885_127.png)

If you happen to take some more advanced classes and statistics that cover things like Chi squared test。

 those P values are automatically in a sense two sided， you would not have to double them。



![](img/8054562485b521c6dd232f8abf2ff885_129.png)

![](img/8054562485b521c6dd232f8abf2ff885_130.png)