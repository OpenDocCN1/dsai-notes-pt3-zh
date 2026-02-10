# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P8：7_04 01 期望值.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

Hi， my name is Brian Kaho and this is the Exped Values lecture as part of the Sta In Cour on Coursera。

 which is part of our data science specialization This class' cotaaled with my coinstructors Jeff Lee and Roger Pang were to Johns Hopkins Bloomberg School of Public Health。



![](img/5119a9bfc736d41e01f85b238356c463_1.png)

This class is about statistical inference， the process of making conclusions about populations based on noisy data that we're going to assume was drawn from it。

The way we're going to do this is we're going to assume that populations and the randomness governing our sample is given by densities and mass functions。

So we don't have to talk about the whole function， we're going to talk about characteristics of these densities and mass functions that are characteristics then of the random variables that are drawn from them。

The most useful such characterization are so called expected values。

 though we've also covered some other characterizations， for example， sample quantiles。

Expected values the mean is the most useful expected value， it's the center of a distribution。

 so you might think of as the mean changes， the distribution just moves to the left or the right as the mean of the distribution moves to the left or the right。



![](img/5119a9bfc736d41e01f85b238356c463_3.png)

![](img/5119a9bfc736d41e01f85b238356c463_4.png)

The variance is another characteristic of a distribution and it talks about how spread out it is。

And just like before in the way that the sample quantiles estimated the population quantiles。

 the sample expected values are going to estimate the population expected values。

 so the sample mean will be an estimate of our population mean。

 and our sample variance will be an estimate of our population variance and our sample standard deviation will be an estimate of our population standard deviation。



![](img/5119a9bfc736d41e01f85b238356c463_6.png)

The expected value or mean of a random variable is the center of its distribution。



![](img/5119a9bfc736d41e01f85b238356c463_8.png)

For a discrete random variable x with a probability mass function p of x。

 it's simply the summation of the possible values that x can take times the probability that it takes them。

The expected value takes its idea from the idea of the physical center of mass if the probabilities were weights with their。



![](img/5119a9bfc736d41e01f85b238356c463_10.png)

Were bars where their weights were governed by the value of the probability and the x was the location along an axis that they were at。

 the expected value would simply be the center of mass。

 we'll go through some examples of that in a second。



![](img/5119a9bfc736d41e01f85b238356c463_12.png)

This idea of center of mass is actually useful in defining the sample mean remember we're talking about in this lecture the population mean which is estimated by the sample mean。

 but it's interesting to note that the sample mean is the center of mass if we treat each data point as equally likely。

 so in other words where the probability is1 over n and each data point Xi has that probability if we were to then find the center of mass for the data that is exactly X bar。



![](img/5119a9bfc736d41e01f85b238356c463_14.png)

![](img/5119a9bfc736d41e01f85b238356c463_15.png)

So we intuitively use this idea of center of mass even when we use a sample mean。



![](img/5119a9bfc736d41e01f85b238356c463_17.png)

So I have some code here to show an example of taking the sample mean of data and how it represents the center of mass just by drawing a histogram。

 so here I have this data Galton and again the code can be found in the markdown file associated with the slides that you can get from GitHub。

So here in this case we have parents heights and children's heights in a paired data set。

 and here I have a histogram for the child's height。

 and here I have the histogram for the parent' height。

 and I've overlaid a continuous density estimate。

![](img/5119a9bfc736d41e01f85b238356c463_19.png)

So I'd like to go through an example where we actually show how moving our finger around will balance out that histogram and fortunately in our studio there's a neat little function called manipulate that will help us do this。

 so I'm going to load up， manipulate。And then the code， I'm going to show you it here。

 but I think if you go on to take the data products class， which is part of the specialization here。

 we'll actually go through the specifics of how to use the manipulate function。

 but here I'm just going to do it to show you it running。And then we're going to look at the plot。

Okay so here is the plot of the child's heights， it's the histogram and I've overlaid a continuous histogram on top of it and here let's say this vertical black line is our current estimate of the mean so here it's saying that the mean is 62 and it gives us the mean squared error that's sort of a measure of imbalance how teetering or tottering this histogram is now notice as I move the mean around which I can do now with manipulate。

 let's move it more towards the center of the distribution notice the mean is gone up。



![](img/5119a9bfc736d41e01f85b238356c463_21.png)

![](img/5119a9bfc736d41e01f85b238356c463_22.png)

![](img/5119a9bfc736d41e01f85b238356c463_23.png)

Let's move it right here， notice the mean went up to 67。

5 but the mean squared error dropped quite a bit， it balances it helped balance out the histogram that was almost the point where it would balance it out perfectly and you can see as I get here it goes down a little bit more but then at some point it starts going back up again so if I move it all the way over here right this mean squared error or this measure of imbalance gets quite large so again this is just illustrating the point that the empirical mean is going to be the point that balances out the empirical distribution and we're going to use this to talk about the population mean which is going to be the point that balances out the population distribution。



![](img/5119a9bfc736d41e01f85b238356c463_25.png)