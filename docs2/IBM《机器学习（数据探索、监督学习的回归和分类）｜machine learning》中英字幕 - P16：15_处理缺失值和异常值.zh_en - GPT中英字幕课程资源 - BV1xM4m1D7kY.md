# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P16：15_处理缺失值和异常值.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's go over some best practices in handling missing values and working without outliers。Now。

 let's start off with dealing with missing data。 Now。

 our models will not accept just blank values in our data as they lack any information。

 We therefore are going to have to decide how to ensure that there is some information given for every single feature and label within our data set。

So our first option is to just remove the data altogether in order to do this we either have to remove an entire row or an entire column。

 let's think that all of our columns are useful so we stick to removing rows。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_1.png)

And if we think about the pros and cons of removing a full row。

The pro here is that it'll quickly clean your data without having to guess an appropriate replacement value。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_3.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_4.png)

On the other hand， the con is that if certain columns are missing values for many rows。

 we may end up losing too much information or biasing our data set to some reason that the data is not collected for a particular field。

So again， the pro is that we can easily remove it and if it's smaller amount of data that we're missing values for。

 it won't have as much an effect。 if has a lot of rows。

 it could end up bias our data set in regards to the model that we're trying to predict。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_6.png)

We can impute our data， and that means that we would be replacing our null values with either the mean or the median or even a more complex estimation。

 the value。

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_8.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_9.png)

The pro to this is that we don't lose full rows or columns that may be important to our model。

 as we would have when we tried to remove full rows， like we said。

 the con is that we add another level of uncertainty to our model。

 as it now based on estimates of what we think the true value for that missing value should have been。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_11.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_12.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_13.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_14.png)

Final option we have is to mess the data so that all of our missing values are their own category。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_16.png)

This would be under the assumption that missing values are actually indicative of useful information。

 If we imagine a survey given by phone and the last question is repeatedly blank。

 That may mean that the person hung up before getting to that last question and marking that as missed last question may actually provide extra information for our model。

 So the pro to this is that， again， we don't lose any rows or columns that may be important to our model。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_18.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_19.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_20.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_21.png)

The con is that we again add another level of uncertainty to our model。

 as is now based on the assumption that all our missing values are alike。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_23.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_24.png)

So if you need to pause on this slide， I would say it's worth doing if you want to go over the pros and cons。

 you can go back to the beginning， listen to me， list out the pros and cons again。

 but with that in mind you should be able to look at your own data， see your missing values。

 and decide what is the best way to address your missing values moving forward。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_26.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_27.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_28.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_29.png)

Now， it's such on outliers， an outliers and observation and data that is distant from most other observations。

 Typ， these observations are aberrations and do not accurately represent the phenomenon we are trying to explain through our model。

 So imagine we're trying to predict sales and all of our values are between 10 and 50 and then we have one week where our value is 3000。

 If our model is just to take the average。 We may end up with values between 10 and 50 will put us somewhere around 30 when we're trying to predict moving forward。

 that 3000， assuming we have a smaller data set， can push that average value up to 200。

300 whatever it is， which is much higher than the value we'd actually predict。

 Given our historical values。 So that outlier will throw off what our actual prediction would be。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_31.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_32.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_33.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_34.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_35.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_36.png)

So if we don't identify deal with outliers， like we just mentioned。

 they'll have a significant impact on our model。

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_38.png)

And itll be important to remember， though， that some outliers are informative and provide insights into the data。

 So you don't want to just remove that 3000 value and not look into it。

 There's often very useful information， probably more useful than your other values between 10 and 50 to tell you why that 3000 happened and give you extra information that may explain what's actually happening in the real world。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_40.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_41.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_42.png)

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_43.png)

So how do we actually find outliers we can use plots here we see both a histogram and a density plot。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_45.png)

We can also use a box plot in order to see the intercotile range， the median。

 a defined minute max value for which outside of that。

 we will have outliers and we'll show you how to define that in a little bit。

And we can use our residuals， we'll have standardized， deleted and studentized residuals。

 which we'll define in just a few slides。

![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_47.png)

So how do we create these plots， The code is going to be assuming we're using Cborn and we imported Cborn as SNS。

 We use SNs do discpl。 We pass in the data as well as the number of bins。

 and then we are able to get the histogram， there's other arguments besides bins that you can pass into your disc plot and you can look into the documentation。

 and then for boxpl， we use SNs do box plot and pass in the data。

 and we're able to get the output that we see below。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_49.png)

Now， how do we end up mathematically getting to what we see here。

 these outlier points instead of the Min Max going all the way to the range of the full data set？

So the way to think about this， we're going to import NI as NP。

 we're going to use NP do percentile to define from our data， the 25th percentile。

 the 50th percentile and the 75th percentile， and we'll label them accordingly。The variables that is。

Then IQR is going to represent our inner quartile range， which will be just the 75th percentile。

 which we save as Q75 minus the 25th percentile， which was Q25。

We're then going to define the variables min， which is this going to be our 25th percentile minus1 and a half times our inner cotile range。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_51.png)

Then our max will be Q75 plus one and a half times our inner quatile range。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_53.png)

And the idea will be that our lines on our box plot should represent both that min and max defined and anything outside either the min or the max here we just have the max will be counted as outliers。

And then assuming that we were working with the unemployments column this entire time。

 we can use our list comprehension and say x for x and data unemployment。

 And if x is greater than that max value， then we will define that as an outlier。

 That max value being Q75 plus 1 and a half times that inner quartile range。



![](img/5f0a9d0d46818dade54dc1f6cd7f67dc_55.png)

Another way that we can detect out wires is to work with residuals。

