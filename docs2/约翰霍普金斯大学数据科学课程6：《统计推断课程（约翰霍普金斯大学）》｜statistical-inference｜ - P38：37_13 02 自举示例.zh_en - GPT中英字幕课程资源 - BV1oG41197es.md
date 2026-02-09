# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P38：37_13 02 自举示例.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/5718815f1fb09af03fe9e7d8821f2ea7_0.png)

So let's consider data the library using R and then the father。

son data and' just to make my life a little bit easier。

 I'm going to define X here as the son's heights just so I don't have to keep referring to the data frame。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_2.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_3.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_4.png)

Let's let N be the number of observations。

![](img/5718815f1fb09af03fe9e7d8821f2ea7_6.png)

And then I'm going to do 10，000 bootstrap resamples。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_8.png)

So what I'm going to do now is the sample command， so when I say sample X， that means draw from x。

N times B。Numbers of。Reamples where in every case， when I because I put replace equals true。

 every time I take an observation， I take a sun's height out of the bag， I put it back in。 Okay。

 And so what is this， This is simulating from an empirical distribution defined by our data that puts probability one over end on each observed data point。

 This is called the empirical distribution。

![](img/5718815f1fb09af03fe9e7d8821f2ea7_10.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_11.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_12.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_13.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_14.png)

And then I'm going to arrange these in a matrix with number of bootstrap rows and number of sample sizes。

 columns。

![](img/5718815f1fb09af03fe9e7d8821f2ea7_16.png)

And so what that means is every row of this matrix that I'm calling resamples。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_18.png)

Is now a completely resampled data set where I took my original data。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_20.png)

And I drew a sample of size and with replacement from that data set。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_22.png)

And that's exactly equivalent to regenerate a sample of size n from a distribution that places probability 1 over n on each observed data point。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_24.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_25.png)

And then let's suppose that the statistic I'm interested in is the median。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_27.png)

And so I'm going to take for each of these data sets， each of these resampled data sets。

 and I'm going to apply the median。

![](img/5718815f1fb09af03fe9e7d8821f2ea7_29.png)

And that's what this final apply statement does。

![](img/5718815f1fb09af03fe9e7d8821f2ea7_31.png)

So here's a density estimate from the resampled medians。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_33.png)

I've drawn a vertical line for our observed mediumn。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_35.png)

So what we've done in this case。Is we've taken our vector of Sun's heights。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_37.png)

And we've repeatedly drawn from this collection of Sun's Heights。

 a new data set of the same length where we drew with replacement with equal probability on every observed data point。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_39.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_40.png)

Then for each one of these new data sets we calculated the median， we did that 10。

000 times and we got a collection of medians， what this density estimate is。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_42.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_43.png)

Is an estimate of the distribution of medians。

![](img/5718815f1fb09af03fe9e7d8821f2ea7_45.png)

Where we don't know the actual population distribution， we're estimating it from our observed data。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_47.png)

This is the central quantity used in bootstrapping， for example。

 in this case we're bootstrapping the median， and we might want to do something like take the standard deviation of this distribution。

 and that is going to be an estimate of the standard error of the median， right。

 the standard deviation of the sampling distribution of the medium。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_49.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_50.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_51.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_52.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_53.png)

We could do， for example， quantiles to get confidence interval estimates and these are the sorts of things that you do with your bootstrap resample distribution。

 so let's go through a couple of the principles and just rediscus bootstrapping generally and then we'll work through this example a little bit more。



![](img/5718815f1fb09af03fe9e7d8821f2ea7_55.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_56.png)

![](img/5718815f1fb09af03fe9e7d8821f2ea7_57.png)