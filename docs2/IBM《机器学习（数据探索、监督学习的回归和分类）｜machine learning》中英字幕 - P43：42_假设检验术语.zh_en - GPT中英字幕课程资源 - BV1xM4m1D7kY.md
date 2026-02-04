# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P43：42_假设检验术语.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Let's discuss some more important terminology to keep in mind when discussing hypothesis testing。



![](img/2baafef49e2ef9968bb2571965fde00d_1.png)

Who we have here at the test statistic。

![](img/2baafef49e2ef9968bb2571965fde00d_3.png)

And here we'll be using the data from the sample to calculate a value that allows to determine whether to accept or reject our null hypothesis。



![](img/2baafef49e2ef9968bb2571965fde00d_5.png)

![](img/2baafef49e2ef9968bb2571965fde00d_6.png)

An example would be the likelihood ratio that we saw earlier when we were flipping a coin where if it was a certain value。

 we would either accept or reject our null hypothesis that we were working with a fair coin。



![](img/2baafef49e2ef9968bb2571965fde00d_8.png)

![](img/2baafef49e2ef9968bb2571965fde00d_9.png)

We have the other rejection region， which is just going to be the set of values for that test statistic for which we would reject the null hypothesis。



![](img/2baafef49e2ef9968bb2571965fde00d_11.png)

![](img/2baafef49e2ef9968bb2571965fde00d_12.png)

We have the acceptance region， which will be the set of values for the test statistic for which we will accept the null hypothesis。



![](img/2baafef49e2ef9968bb2571965fde00d_14.png)

![](img/2baafef49e2ef9968bb2571965fde00d_15.png)

AndThen finally， we have the null distribution， and that's just going to be the distribution of our test statistic。

 assuming that our null hypothesis is true。

![](img/2baafef49e2ef9968bb2571965fde00d_17.png)

![](img/2baafef49e2ef9968bb2571965fde00d_18.png)

So let's go over some business examples， imagine we want to see whether our marketing intervention will have an effect。



![](img/2baafef49e2ef9968bb2571965fde00d_20.png)

So for a new direct mail marketing campaign to existing customers。

 the no hypothesis would be that our campaign does not actually impact purchasing。



![](img/2baafef49e2ef9968bb2571965fde00d_22.png)

![](img/2baafef49e2ef9968bb2571965fde00d_23.png)

![](img/2baafef49e2ef9968bb2571965fde00d_24.png)

So the null is no effect， the alternative hypothesis will suggest that it does indeed have an impact。



![](img/2baafef49e2ef9968bb2571965fde00d_26.png)

So again， the null being the no effect and the alternative being that there is an impact of our campaign。



![](img/2baafef49e2ef9968bb2571965fde00d_28.png)

![](img/2baafef49e2ef9968bb2571965fde00d_29.png)

Next example is website layout， so imagine we're testing to see whether our change in website layout will have an effect on traffic。



![](img/2baafef49e2ef9968bb2571965fde00d_31.png)

So for a proposed change to a web layout， we may test the null hypothesis that the change had no impact。



![](img/2baafef49e2ef9968bb2571965fde00d_33.png)

![](img/2baafef49e2ef9968bb2571965fde00d_34.png)

Or。We will look for evidence to reject that null hypothesis in favor of the alternative hypothesis that there is indeed an impact of the website layout on traffic。



![](img/2baafef49e2ef9968bb2571965fde00d_36.png)

![](img/2baafef49e2ef9968bb2571965fde00d_37.png)

![](img/2baafef49e2ef9968bb2571965fde00d_38.png)

Finally， we can think about product quality or size。

 and we're testing whether a product meets expected size threshold。



![](img/2baafef49e2ef9968bb2571965fde00d_40.png)

So suppose a product is produced in various factories with an expected size of S。



![](img/2baafef49e2ef9968bb2571965fde00d_42.png)

To confirm that the product size meets the standard within a margin of error。

 the company might first randomly sample from each production source so it bunch it'll have a random sample from each production source。



![](img/2baafef49e2ef9968bb2571965fde00d_44.png)

![](img/2baafef49e2ef9968bb2571965fde00d_45.png)

![](img/2baafef49e2ef9968bb2571965fde00d_46.png)

It'll establish the no hypothesis that the product size is not going to be significantly different from our size S。



![](img/2baafef49e2ef9968bb2571965fde00d_48.png)

And the alternative would be that there is a significant deviation in product size from our size S。



![](img/2baafef49e2ef9968bb2571965fde00d_50.png)

And then we would testest whether our null hypothesis can be rejected in favor of the alternative。

 so here the alternative would be bad， the size is not according to。

 besides that's expected based on the observed mean and standard deviation from our sample from the different products that we pulled from the different sources。

All right， let's recap what we went over。

![](img/2baafef49e2ef9968bb2571965fde00d_52.png)

Here we discuss the tradeoffs between type 1 and type 2 errors。

 as well as some different terminology in regards to hypothesis testing， such as the test statistic。

 the acceptance region， our rejection region， and the null distributions。



![](img/2baafef49e2ef9968bb2571965fde00d_54.png)

![](img/2baafef49e2ef9968bb2571965fde00d_55.png)

![](img/2baafef49e2ef9968bb2571965fde00d_56.png)

We also showed business examples for hypothesis testing to give you a bit of context。



![](img/2baafef49e2ef9968bb2571965fde00d_58.png)

And here， I would like to ask the viewer， what are some hypotheses that you have based on your business knowledge。

 Is there anything you would like to test for in regards to the challenges your business or your customers face。



![](img/2baafef49e2ef9968bb2571965fde00d_60.png)

What would be the data that you would need to collect to answer those questions。

 what would be some EDA that you would do on this data。

 and what approach would you take to test these hypotheses？



![](img/2baafef49e2ef9968bb2571965fde00d_62.png)

![](img/2baafef49e2ef9968bb2571965fde00d_63.png)

![](img/2baafef49e2ef9968bb2571965fde00d_64.png)

Now I really want you to take the time to think through these questions as our goal will be for you to be able to leave this course ready to use data to drive business action。



![](img/2baafef49e2ef9968bb2571965fde00d_66.png)

That is it for this video， in the next section we'll discuss significance levels as well as P values。



![](img/2baafef49e2ef9968bb2571965fde00d_68.png)

![](img/2baafef49e2ef9968bb2571965fde00d_69.png)