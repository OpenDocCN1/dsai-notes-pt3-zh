# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P38：37_13 02 自助法示例.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

![](img/a038b195de4241c3c7b90bf38c5f7be4_0.png)

So let's consider data the library using R and then the father。son data。

 and' just to make my life a little bit easier， I'm going to define X here as the son's heights just so I don't have to keep referring to the data frame。



![](img/a038b195de4241c3c7b90bf38c5f7be4_2.png)

![](img/a038b195de4241c3c7b90bf38c5f7be4_3.png)

Let's let N be the number of observations。

![](img/a038b195de4241c3c7b90bf38c5f7be4_5.png)

And then I'm going to do 10，000 bootstrap resamples。

So what I'm going to do now is the sample command， so when I say sample X， that means draw from x。

N times B。Numbers of。Reamples where in every case， when I， because I put replace equals true。

 every time I take an observation， I take a sun's height out of the bag， I put it back in。 Okay。

 and so what is this， This is simulating from an empirical distribution defined by our data that puts probability one over end on each observed data point。

 This is called the empirical distribution。And then I'm going to arrange these in a matrix with number of bootstrap rows and number of sample sizes。

 columns。And so what that means is every row of this matrix that I'm calling resamples。

Is now a completely resampled data set where I took my original data。

And I drew a sample of size and with replacement from that data set。

And that's exactly equivalent to regenerate a sample of size n from a distribution that places probability 1 over n on each observed data point。



![](img/a038b195de4241c3c7b90bf38c5f7be4_7.png)

And then let's suppose that the statistic I'm interested in is the median。



![](img/a038b195de4241c3c7b90bf38c5f7be4_9.png)

And so I'm going to take for each of these data sets， each of these resampled data sets。

 and I'm going to apply the median。

![](img/a038b195de4241c3c7b90bf38c5f7be4_11.png)

And that's what this final apply statement does。

![](img/a038b195de4241c3c7b90bf38c5f7be4_13.png)

So here's a density estimate from the resampled medians。



![](img/a038b195de4241c3c7b90bf38c5f7be4_15.png)

I have drawn a vertical line for our observed mediumn。



![](img/a038b195de4241c3c7b90bf38c5f7be4_17.png)

So what we've done in this case。Is we've taken our vector of sun's heights。



![](img/a038b195de4241c3c7b90bf38c5f7be4_19.png)

And we've repeatedly drawn from this collection of Sun's Heights。

 a new data set of the same length where we drew with replacement with equal probability on every observed data point。

Then for each one of these new data sets we calculated the median， we did that 10，000 times。

 and we got a collection of medians， what this density estimate is。



![](img/a038b195de4241c3c7b90bf38c5f7be4_21.png)

![](img/a038b195de4241c3c7b90bf38c5f7be4_22.png)

Is an estimate of the distribution of medians。Where we don't know the actual population distribution。

 we're estimating it from our observed data。This is the central quantity used in bootstrapping。

 for example， in this case we're bootstrapping the median。

 and we might want to do something like take the standard deviation of this distribution。

 and that is going to be an estimate of the standard error of the median right。

 the standard deviation of the sampling distribution of the mediumn。We could do， for example。

 quantiles to get confidence interval estimates， and these are the sorts of things that you do with your bootstrap resample distribution。

So let's go through a couple of the principles and just rediscus bootstrapping generally。

 and then we'll work through this example a little bit more。



![](img/a038b195de4241c3c7b90bf38c5f7be4_24.png)

![](img/a038b195de4241c3c7b90bf38c5f7be4_25.png)