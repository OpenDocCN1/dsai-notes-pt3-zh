# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P26：25_变量转换.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now， the mathematical theory behind a linear regression is going to assume that our residuals from our model are going to be normally distributed。



![](img/486ced6354effff02d14225023247f6d_1.png)

Now， often the raw data that we get， both the features and the outcome variable can be negatively or positively skewed as we see here。



![](img/486ced6354effff02d14225023247f6d_3.png)

![](img/486ced6354effff02d14225023247f6d_4.png)

And in real life， that data can come in all shapes and sizes。

 and data transformations can help the algorithm find a better solution that will end up having residuals that are actually normally distributed。



![](img/486ced6354effff02d14225023247f6d_6.png)

![](img/486ced6354effff02d14225023247f6d_7.png)

So some ways that we can transform our data， we see here some code bringing in log and log 1p from Numpy log 1p is just going to be log except you add one because you can't take a log of zero so in case you have zero in your data and then the boxcox is just a more complex way that will find the ideal way to transform。



![](img/486ced6354effff02d14225023247f6d_9.png)

![](img/486ced6354effff02d14225023247f6d_10.png)

![](img/486ced6354effff02d14225023247f6d_11.png)

![](img/486ced6354effff02d14225023247f6d_12.png)

From a skewed data set such as the right skewed data we see here to a normal distribution。



![](img/486ced6354effff02d14225023247f6d_14.png)

So we see here an example of how we can apply the log transformation to a positively skewed data set。

 So we start here with a positively skewed data set。



![](img/486ced6354effff02d14225023247f6d_16.png)

And then we see once we take the log of that data， we end up with a data set that is more normally distributed。



![](img/486ced6354effff02d14225023247f6d_18.png)

Now， log transformations can be a useful way to find a linear relationship when the underlying raw data may not actually have a linear relationship。



![](img/486ced6354effff02d14225023247f6d_20.png)

![](img/486ced6354effff02d14225023247f6d_21.png)

So the resulting algorithm will still be a linear regression since the outcome is still linear combinations of the features。

 just the features now have been transformed， feature engineering， variable transformation。

 so that we can input those into the linear regression。



![](img/486ced6354effff02d14225023247f6d_23.png)

![](img/486ced6354effff02d14225023247f6d_24.png)

Now the linear regression involves a linear combination of our new features。

 one of our new features being the log of X rather than just x。



![](img/486ced6354effff02d14225023247f6d_26.png)

![](img/486ced6354effff02d14225023247f6d_27.png)

And this is a common example when we have a relationship maybe with diminishing returns。

 such as a larger box office， probably will not have a linear relationship with the budget。

 but rather it would have diminishing returns， a larger the budget after some time you probably won't get as much return on your box office。

 so that isn't a linear relationship but it may be linear with the relationship of log of X。



![](img/486ced6354effff02d14225023247f6d_29.png)

![](img/486ced6354effff02d14225023247f6d_30.png)

![](img/486ced6354effff02d14225023247f6d_31.png)

Similarly， we can estimate higher order relationships in this data by adding polynomial features。

 so it's another trick in our toolb。So instead of only incorporating budget。

 we can incorporate budget squared as a feature and add more flexibility to our model and fit a linear model using these polynomial features and again we end up with a linear model even though weve taken we've included new features。



![](img/486ced6354effff02d14225023247f6d_33.png)

![](img/486ced6354effff02d14225023247f6d_34.png)

![](img/486ced6354effff02d14225023247f6d_35.png)

And again， this is the idea of at this point， just one inflection point。

 so just rather than straight， it kind of curves off then you would have something like x squared raising the degree to two。



![](img/486ced6354effff02d14225023247f6d_37.png)

![](img/486ced6354effff02d14225023247f6d_38.png)

We can even continue to extend this to three or four or any higher order polynomial。



![](img/486ced6354effff02d14225023247f6d_40.png)

Again， we're changing our features， but maintaining a linear model， an underlying linear model。

 just with features now transformed to x plus x squared plus x cubed。



![](img/486ced6354effff02d14225023247f6d_42.png)

![](img/486ced6354effff02d14225023247f6d_43.png)

And what we see here in the graph would represent not just diminishing returns。

 But now we have two inflection points。 right， It curves up， then it curves down。

 And that would be the idea that after some time， not only is their diminishing returns， but。



![](img/486ced6354effff02d14225023247f6d_45.png)

![](img/486ced6354effff02d14225023247f6d_46.png)

A higher budget may lead to less box office sales at a certain threshold。



![](img/486ced6354effff02d14225023247f6d_48.png)

So we'll dive into this again as we look at more code。

 but here's an example of how we can use SK learn。

![](img/486ced6354effff02d14225023247f6d_50.png)

In order to create a polynomial transformation。So our first step is going to be to import polynomial features。

 import that function from Scalalar not preproces。

![](img/486ced6354effff02d14225023247f6d_52.png)

We will then create an instance of our polynomial features class and call it poly Fe。

Polyfete is now a transformer object。 What this means is that it can fit to a set of data。

 such as X data， which we'll see in a second， and then transform it。

 or it can use that in order to what it's learned from fitting to a certain data set to transform another data set of the same size。



![](img/486ced6354effff02d14225023247f6d_54.png)

So here we see we're doing polyfit dot fit and we're fitting to our X data。

And then the next step is just to， so now we have our polyfeat transformer objects that is now fit to our data and we can use that in order to transform our data from its original。

 so the original would be something like the X that we saw earlier， to x squared。



![](img/486ced6354effff02d14225023247f6d_56.png)

![](img/486ced6354effff02d14225023247f6d_57.png)

![](img/486ced6354effff02d14225023247f6d_58.png)

And that's going to be x poly。 Now x poly is x squared。



![](img/486ced6354effff02d14225023247f6d_60.png)

![](img/486ced6354effff02d14225023247f6d_61.png)