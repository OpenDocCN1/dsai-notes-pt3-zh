# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P46：45_假设检验演示（选修部分）第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/103e9e9dd39e50654b9cc4718059d53e_0.png)

Welcome to our notebook on Hyth testing。The objectives for this notebook will be to know the difference between a null and alternative hypothesis。

 as well as learn to write your own set of hypotheses for testing and how to do so within Python。



![](img/103e9e9dd39e50654b9cc4718059d53e_2.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_3.png)

So first we'll import the necessary libraries， we'll import Matplotlib。pyplot splLT。

That will just be for our plots， import nuy as NP， that will be for quick numerical analysis。



![](img/103e9e9dd39e50654b9cc4718059d53e_5.png)

From S pi we'll import stats， which will be for statistical analysis and then will also import math。

 which will just give us some extra functionality in regards to doing some basic math。



![](img/103e9e9dd39e50654b9cc4718059d53e_7.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_8.png)

So we want to come up with our personnel null hypothesis。

So let's say that I claim that I can use mystical abilities to predict the outcome of coin flips。



![](img/103e9e9dd39e50654b9cc4718059d53e_10.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_11.png)

You don't think that I can。 so how can we test it， What we do is we conduct an experiment in which I call 100 coin fls。

 and when we do that I get 57 correct。

![](img/103e9e9dd39e50654b9cc4718059d53e_13.png)

Now our question is， am I special or not？

![](img/103e9e9dd39e50654b9cc4718059d53e_15.png)

So with this in mind that I got 57 right， let's pause and think。

 what is the null and alternative hypothesis given what we have here。

 given the data that we have here。

![](img/103e9e9dd39e50654b9cc4718059d53e_17.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_18.png)

Our no hypothesis should be that I'm not special。 My true rate of flip prediction is actually just 5050 that every time you flip a coin I have equal chance of getting it correct or incorrect。



![](img/103e9e9dd39e50654b9cc4718059d53e_20.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_21.png)

And even under this hypothesis， I could get 57 out of 100， right。

 So we want to determine did I get lucky and get 57 by random chance。

 or am I truly mystical and can predict above the 50，50 chance。



![](img/103e9e9dd39e50654b9cc4718059d53e_23.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_24.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_25.png)

The alternative would be that my true rate of flip prediction is actually greater than 0。5。



![](img/103e9e9dd39e50654b9cc4718059d53e_27.png)

So that I actually can do better than a 50，50 guess。



![](img/103e9e9dd39e50654b9cc4718059d53e_29.png)

And the thing that we're measuring from the experiment or our test statistic。

 which allows to decide whether to reject or accept the null。

 will depend on the number of correct flip predictions out of 100。



![](img/103e9e9dd39e50654b9cc4718059d53e_31.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_32.png)

Now， if the null hypothesis is correct， the test statistic is binly distributed with parameters n equals 100 number flips and p equals 0。

5。

![](img/103e9e9dd39e50654b9cc4718059d53e_34.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_35.png)

That is if we repeated this whole experiment many times。

 kept flipping 100 coins and seeing how many we got correct？



![](img/103e9e9dd39e50654b9cc4718059d53e_37.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_38.png)

We would see such a distribution for all of the results。So if the null hypothesis is correct。

 how likely is it that I would get 57 or more coin flips correct。

 that's by chance the question that we're trying to ask。



![](img/103e9e9dd39e50654b9cc4718059d53e_40.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_41.png)

Before we check， we want to put a marker and say anything above this marker or below this marker in regards to his chance of me getting a certain amount correct。



![](img/103e9e9dd39e50654b9cc4718059d53e_43.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_44.png)

Will convince us that I had ESP。

![](img/103e9e9dd39e50654b9cc4718059d53e_46.png)

And the choice of that cutup will be 5% probability since that's just common practice。



![](img/103e9e9dd39e50654b9cc4718059d53e_48.png)

So since we have two outcomes， one with probability P and the other with probability1 minus P。

 we know that we are working within a binomial distribution and that's the right tool for this analysis。



![](img/103e9e9dd39e50654b9cc4718059d53e_50.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_51.png)

And also because we're working with a binomial distribution。

 that makes it easier for us to just quickly come up with what the actual probability is of a certain amount of heads or guessing the certain amount correct。



![](img/103e9e9dd39e50654b9cc4718059d53e_53.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_54.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_55.png)

So our first line of code here is we import from sippi。tts the bynome。



![](img/103e9e9dd39e50654b9cc4718059d53e_57.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_58.png)

Library。Functionality。And we are going to set the probability equal to1 minus byome and byome is going to have the method Cf available to it。

 Cf is the cumulative distribution function， and that will be all values up until that first value。

 So we see 56。 So given that we're working with a binomial distribution with n equals 100 and p equals 0。

5， those are the second and third values。

![](img/103e9e9dd39e50654b9cc4718059d53e_60.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_61.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_62.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_63.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_64.png)

The probability of getting 56 or lower。Now， if we're working with 50，50 flip。

 that's probably a very large value。 the idea being that we take one minus that value to see the probability of getting 57 or greater。



![](img/103e9e9dd39e50654b9cc4718059d53e_66.png)

And then we print out that percentage。 All we're doing here is we're converting it to a string after we。



![](img/103e9e9dd39e50654b9cc4718059d53e_68.png)

So it's going to be 0。097， we multiply by 100， we round it to one decimal place。

 and then we just add on a percentage， so we're actually outputting a string here。



![](img/103e9e9dd39e50654b9cc4718059d53e_70.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_71.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_72.png)

So the probability of getting 57 or more correct is about 9。7%。

 given that we're working with the null distribution with a fairco。



![](img/103e9e9dd39e50654b9cc4718059d53e_74.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_75.png)

So this is more than 5%， so we can't just reject the null hypothesis and we conclude that I probably don't have mystical powers。



![](img/103e9e9dd39e50654b9cc4718059d53e_77.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_78.png)

Conversely， we can also figure out what the 95% cutoff is beforehand before actually conducting the tests assuming that we're going to use the null hypothesis that we are using as well as。



![](img/103e9e9dd39e50654b9cc4718059d53e_80.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_81.png)

That we are working with the binomial distribution。So think about the exercise。

 I know the answer is right there， but take some time and try and come up with why this actually works and get a better understanding of the code that we're working with here。



![](img/103e9e9dd39e50654b9cc4718059d53e_83.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_84.png)

![](img/103e9e9dd39e50654b9cc4718059d53e_85.png)