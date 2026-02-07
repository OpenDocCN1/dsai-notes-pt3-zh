# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P42：41_第一类错误与第二类错误示例.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Let's discuss some more important terminology to keep in mind when discussing hypothesis testing。



![](img/a6ed0d6446025873b6344fb86eb316a4_1.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_2.png)

So we have you the test statistic。And here we'll be using the data from the sample to calculate a value that allows to determine whether to accept or reject our null hypothesis。



![](img/a6ed0d6446025873b6344fb86eb316a4_4.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_5.png)

An example would be the likelihood ratio that we saw earlier when we were flipping a coin where if it was a certain value。

 we would either accept or reject our null hypothesis that we were working with the fair coin。



![](img/a6ed0d6446025873b6344fb86eb316a4_7.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_8.png)

We have the other rejection region， which is just going to be the set of values for that test statistic for which we would reject the null hypothesis。



![](img/a6ed0d6446025873b6344fb86eb316a4_10.png)

We have the acceptance region， which will be the set of values for the test statistic for which we will accept the null hypothesis。



![](img/a6ed0d6446025873b6344fb86eb316a4_12.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_13.png)

Then finally， we have the null distribution， and that's just going to be the distribution of our test staistic。

 assuming that our null hypothesis is true。

![](img/a6ed0d6446025873b6344fb86eb316a4_15.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_16.png)

So let's go over some business examples， imagine we want to see whether our marketing intervention will have an effect。



![](img/a6ed0d6446025873b6344fb86eb316a4_18.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_19.png)

So for a new direct mail marketing campaign to existing customers。

 the null hypothesis would be that our campaign does not actually impact purchasing。



![](img/a6ed0d6446025873b6344fb86eb316a4_21.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_22.png)

So the null is no effect， the alternative hypothesis would suggest that it does indeed have an impact。



![](img/a6ed0d6446025873b6344fb86eb316a4_24.png)

So again， the null being the no effect and the alternative being that there is an impact of our campaign。



![](img/a6ed0d6446025873b6344fb86eb316a4_26.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_27.png)

Next example is website layout， so imagine we're testing to see whether our change in website layout will have an effect on traffic。



![](img/a6ed0d6446025873b6344fb86eb316a4_29.png)

So for a proposed change to a web layout， we may test the null hypothesis that the change had no impact。



![](img/a6ed0d6446025873b6344fb86eb316a4_31.png)

Or we will look for evidence to reject that null hypothesis in favor of the alternative hypothesis that there is indeed an impact of the website layout on traffic。



![](img/a6ed0d6446025873b6344fb86eb316a4_33.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_34.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_35.png)

Finally， we can think about product quality or size。

 and we're testing whether a product meets expected size threshold。



![](img/a6ed0d6446025873b6344fb86eb316a4_37.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_38.png)

So suppose a product is produced in various factories with an expected size of S。



![](img/a6ed0d6446025873b6344fb86eb316a4_40.png)

To confirm that the product size meets the standard within a margin of error， the company might。



![](img/a6ed0d6446025873b6344fb86eb316a4_42.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_43.png)

First， randomly sample from each production source so it can a bunch。

 it'll have a random sample from each production source。



![](img/a6ed0d6446025873b6344fb86eb316a4_45.png)

It will establish the no hypothesis that the product size is not going to be significantly different from our size S。



![](img/a6ed0d6446025873b6344fb86eb316a4_47.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_48.png)

And the alternative would be that there is a significant deviation in product size from our size S。



![](img/a6ed0d6446025873b6344fb86eb316a4_50.png)

And then we wouldt testest whether our nu hypothesis can be rejected in favour of the alternative。

 So here， the alternative would be bad。 The size is not according to the size that's expected based on the observed mean and standard deviation from our sample from the different products that we pulled from the different sources。



![](img/a6ed0d6446025873b6344fb86eb316a4_52.png)

All right， let's recap what we went over。Here we discuss the tradeoffs between type 1 and type 2 errors。

 as well as some different terminology in regards to hypothesis testing， such as the test statistic。

 the acceptance region， our rejection region， and the null distributions。



![](img/a6ed0d6446025873b6344fb86eb316a4_54.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_55.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_56.png)

We also showed business examples for hypothesis testing to give you a bit of context。



![](img/a6ed0d6446025873b6344fb86eb316a4_58.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_59.png)

And here， I'd like to ask the viewer， what are some hypothees that you have based on your business knowledgeage。

 Is there anything you would like to test for in regards to the challenges your business or your customers face。



![](img/a6ed0d6446025873b6344fb86eb316a4_61.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_62.png)

What would be the data that you would need to collect to answer those questions。

 what would be some EDA that you would do on this data。

 and what approach would you take to test these hypotheses？



![](img/a6ed0d6446025873b6344fb86eb316a4_64.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_65.png)

Now I really want you to take the time to think through these questions as our goal will be for you to be able to leave this course ready to use data to drive business action。



![](img/a6ed0d6446025873b6344fb86eb316a4_67.png)

That is it for this video and the next section we'll discuss significance levels as well as P values。



![](img/a6ed0d6446025873b6344fb86eb316a4_69.png)

![](img/a6ed0d6446025873b6344fb86eb316a4_70.png)