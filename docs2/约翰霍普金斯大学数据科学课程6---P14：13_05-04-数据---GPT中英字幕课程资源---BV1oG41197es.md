# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P14：13_05 04 数据例子中的方差.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/5efe3746ba069063ac38030731f15aba_0.png)

And so let's actually go through a data example。Here I'm going to use the father son data from the using R data set and I'm going to grab the sun's height and n is going to be the number of observations like always。



![](img/5efe3746ba069063ac38030731f15aba_2.png)

![](img/5efe3746ba069063ac38030731f15aba_3.png)

![](img/5efe3746ba069063ac38030731f15aba_4.png)

If I were to plot a histogram of the sun's heights。

 I get this distribution right here and I overlaid the histogram with a continuous density estimate。



![](img/5efe3746ba069063ac38030731f15aba_6.png)

It's quite Gaussian looking。

![](img/5efe3746ba069063ac38030731f15aba_8.png)

Now this density estimate is an estimate of the population density。

 we don't have the population density because we didn't collect an infinite amount of data。



![](img/5efe3746ba069063ac38030731f15aba_10.png)

![](img/5efe3746ba069063ac38030731f15aba_11.png)

Variability of this histogram， which is what the sample variance is calculating。

 it's estimating the variability of sun's heights from whatever population this was drawn from。

 let's assume that it was a random sample。

![](img/5efe3746ba069063ac38030731f15aba_13.png)

![](img/5efe3746ba069063ac38030731f15aba_14.png)

![](img/5efe3746ba069063ac38030731f15aba_15.png)

Let's just go through a couple of the numbers we can calculate here， so here I took variance of x。

 variance of x divided by n， standard deviation of x。

 standard deviation of x divided by square root n， and I rounded all the numbers to two decimal places。



![](img/5efe3746ba069063ac38030731f15aba_17.png)

![](img/5efe3746ba069063ac38030731f15aba_18.png)

So 7。92 and 2。81， the variance of x and the standard deviation of x are simply talking about the variability in sun's heights from this data set。

 which are estimates of the variability， the population variability of sun's heights if you're willing to assume that these suns are a random sample from some meaningful population。



![](img/5efe3746ba069063ac38030731f15aba_20.png)

![](img/5efe3746ba069063ac38030731f15aba_21.png)

![](img/5efe3746ba069063ac38030731f15aba_22.png)

![](img/5efe3746ba069063ac38030731f15aba_23.png)

![](img/5efe3746ba069063ac38030731f15aba_24.png)

I like 2。81 in this case over 7。92 because 7。92 is expressed in inches squared and 2。

81 is expressed in inches， so I like to work in the units rather than the unit squared。



![](img/5efe3746ba069063ac38030731f15aba_26.png)

![](img/5efe3746ba069063ac38030731f15aba_27.png)

。01 and 0。09 are no longer talking about the variability in the children's heights。

 it's talking about the variability in averages of 10 children's heights。



![](img/5efe3746ba069063ac38030731f15aba_29.png)

![](img/5efe3746ba069063ac38030731f15aba_30.png)

So 0。09 is probably the most meaningful one， and it's the standard error， or in other words。

 the standard deviation in the distribution of averages of N children's height。



![](img/5efe3746ba069063ac38030731f15aba_32.png)

![](img/5efe3746ba069063ac38030731f15aba_33.png)

![](img/5efe3746ba069063ac38030731f15aba_34.png)

And again， in this case， it's an estimate of that， but it's the best estimate we have from the data that we have。



![](img/5efe3746ba069063ac38030731f15aba_36.png)

![](img/5efe3746ba069063ac38030731f15aba_37.png)

So let's summarize what we know because we covered a lot of somewhat complicated topics in this lecture and I would say fundamentally what differentiates understanding statistics from not understanding statistics is understanding variability。

 so if I were to say what's the most important lecture， it might be this one。



![](img/5efe3746ba069063ac38030731f15aba_39.png)

![](img/5efe3746ba069063ac38030731f15aba_40.png)

![](img/5efe3746ba069063ac38030731f15aba_41.png)

![](img/5efe3746ba069063ac38030731f15aba_42.png)

So let's summarize what we know， the sample variance is an estimate of the population variance。



![](img/5efe3746ba069063ac38030731f15aba_44.png)

The distribution of the sample variance is centered at what it's estimating。

 this is a good thing this means that it is unbiased。



![](img/5efe3746ba069063ac38030731f15aba_46.png)

And it gets more concentrated about what it's estimating as you collect more data again。

 this is a good thing， this means if we go to the trouble of collecting more data。

 we get a better estimate that the distribution of the sample variance is more concentrated about what it'sestimating。



![](img/5efe3746ba069063ac38030731f15aba_48.png)

![](img/5efe3746ba069063ac38030731f15aba_49.png)

![](img/5efe3746ba069063ac38030731f15aba_50.png)

We also know a lot about the distribution of sample means。

 we know whether they're centered at from the last lecture。

 but we also know in this lecture that the variance of the sample mean is the population variance divided by n and the square root of it sigma divided by square root n is the so-called standard error。



![](img/5efe3746ba069063ac38030731f15aba_52.png)

![](img/5efe3746ba069063ac38030731f15aba_53.png)

![](img/5efe3746ba069063ac38030731f15aba_54.png)

These quantities represent how variable averages are drawn from this population。



![](img/5efe3746ba069063ac38030731f15aba_56.png)

![](img/5efe3746ba069063ac38030731f15aba_57.png)

And it turns out that we can say a lot about the distribution of averages from random samples。

 even though we only get to look at one on a given data。

 and this gives us a lot to work with and it forms a lot of the foundation of ways in which we can perform。



![](img/5efe3746ba069063ac38030731f15aba_59.png)

![](img/5efe3746ba069063ac38030731f15aba_60.png)