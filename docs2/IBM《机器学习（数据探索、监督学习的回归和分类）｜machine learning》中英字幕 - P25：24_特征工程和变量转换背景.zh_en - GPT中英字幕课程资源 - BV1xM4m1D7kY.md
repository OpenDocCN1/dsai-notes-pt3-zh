# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P25：24_特征工程和变量转换背景.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome to the next section of this course and this section will discuss feature engineering as well as variable transformation。

At this point， you've learned to retrieve your data from the available data sources。



![](img/85650779df49fdeeee51c9f80ec29a5b_1.png)

Clean your data set and do some exploratory data analysis EDA on your data。



![](img/85650779df49fdeeee51c9f80ec29a5b_3.png)

Now， before we move to modeling， we'll most likely need to adjust the raw data coming in to optimize model performance。



![](img/85650779df49fdeeee51c9f80ec29a5b_5.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_6.png)

So what are related learning goals that we'll cover in this section？

Talk about feature engineering and variable transformation。

 and we very briefly touched on variable transformations during our data cleansing session and how a log transformation may help you without outliers by changing the distribution of that data。



![](img/85650779df49fdeeee51c9f80ec29a5b_8.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_9.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_10.png)

We will do some feature encoding。Because all inputs for a model must be made numerical。

 so we'll work here to show how we can actually encode our categorical data so that can be included in our models。



![](img/85650779df49fdeeee51c9f80ec29a5b_12.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_13.png)

And then finally， we'll discuss feature scaling as real worldor raw data in our data sets are generally not going to come in on the same scale as one another for each one of the features。

 and this will prove to be an important property for many of our machine learning algorithms。



![](img/85650779df49fdeeee51c9f80ec29a5b_15.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_16.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_17.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_18.png)

So models using machine learning workflows will often be based off of some assumptions about the data。



![](img/85650779df49fdeeee51c9f80ec29a5b_20.png)

A common example is the linear Russian model， and this is going to assume a linear relationship between the observations and our target outcome variable。



![](img/85650779df49fdeeee51c9f80ec29a5b_22.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_23.png)

So I know we haven't discussed linear regression yet， but we will later on。

 all we want to take away here is that if we're going to use linear regression。

 which will be very important as itll be the foundation for many of our machine learning algorithms moving forward。

 we want to assume that there's actually a linear relationship between our predictor variables and our actual outcome variables。



![](img/85650779df49fdeeee51c9f80ec29a5b_25.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_26.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_27.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_28.png)

So an example of a linear model relating a feature， variables x1。

 variables x1 and x2 with a target label variable y is what we see here。

 the function of x equals beta not some intersetss plus some coefficient beta 1 times x1 plus another coefficient beta 2 plus x2。



![](img/85650779df49fdeeee51c9f80ec29a5b_30.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_31.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_32.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_33.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_34.png)

And here beta beta beta1， beta 2 are going to be the parameters that we will hopefully learn with our model。

 an example that you can think of is which we'll use also in the later graphs is box office returns and you can think of x1 as the CA budget and x2 as the marketing budget and then beta 1 and beta 2 determining how much the CA budget in the marketing budget will actually help in predicting what the revenue will be for that movie。



![](img/85650779df49fdeeee51c9f80ec29a5b_36.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_37.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_38.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_39.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_40.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_41.png)

Now， think of linear as just being an addition of each one of the model parameters multiplied by coefficient and as we'll see。

 we can actually transform。

![](img/85650779df49fdeeee51c9f80ec29a5b_43.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_44.png)

Each one of these parameters to ensure a linear relationship。



![](img/85650779df49fdeeee51c9f80ec29a5b_46.png)

So if you think about the different x1s and x2s， we can actually transform x1 and x2 to something else and then still have a linear relationship by using just a coefficient multiplied by that transformed x1 and x2。



![](img/85650779df49fdeeee51c9f80ec29a5b_48.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_49.png)

![](img/85650779df49fdeeee51c9f80ec29a5b_50.png)