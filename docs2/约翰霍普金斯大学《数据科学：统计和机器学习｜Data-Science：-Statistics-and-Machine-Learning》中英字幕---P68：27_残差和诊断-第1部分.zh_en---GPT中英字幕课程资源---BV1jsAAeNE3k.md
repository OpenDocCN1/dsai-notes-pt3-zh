# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P68：27_残差和诊断 第1部分.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

Hi and welcome to the class on residualss， Dtics and Vaation。



![](img/76972bc98e91a2564b96a78380a6119d_1.png)

![](img/76972bc98e91a2564b96a78380a6119d_2.png)

Remember， we started out with our linear model。We're also going to assume here throughout the lecture that our errors are normally distributed。

 some of our results require that and some of them don't。



![](img/76972bc98e91a2564b96a78380a6119d_4.png)

![](img/76972bc98e91a2564b96a78380a6119d_5.png)

Remember how we defined our residuals。

![](img/76972bc98e91a2564b96a78380a6119d_7.png)

And that our estimate of residual variation is the sum of the square the average of the squared residuals。

 where remember we divide by n minus p rather than n for unbiasedness sake。



![](img/76972bc98e91a2564b96a78380a6119d_9.png)

![](img/76972bc98e91a2564b96a78380a6119d_10.png)

![](img/76972bc98e91a2564b96a78380a6119d_11.png)

So it's very easy in R to get a plot of your residuals and several plots that measure aspects of model fit and lack of model fit。

 so let's load up the data Swiss and let's go ahead and fit the linear model that includes all of the terms and the easy way to do that is to put a period after the little Tilde symbol so that then it just includes all the terms in the data frame except the outcome of course。



![](img/76972bc98e91a2564b96a78380a6119d_13.png)

![](img/76972bc98e91a2564b96a78380a6119d_14.png)

![](img/76972bc98e91a2564b96a78380a6119d_15.png)

![](img/76972bc98e91a2564b96a78380a6119d_16.png)

![](img/76972bc98e91a2564b96a78380a6119d_17.png)

![](img/76972bc98e91a2564b96a78380a6119d_18.png)

Then the generic command plot actually will just plot the fit。

 it will plot and create a series of residual and diagnostic plots for you。

 I did par MFO equals 22 so that it all fit on one page。



![](img/76972bc98e91a2564b96a78380a6119d_20.png)

![](img/76972bc98e91a2564b96a78380a6119d_21.png)

So in this class， we're going to go over what the basics of these plots are。

So to do that we need to discuss influential points and outlier points and that there's a distinction。

 so here I created a plot where there's a clear linear relationship between most of the data between the predictor and the response。



![](img/76972bc98e91a2564b96a78380a6119d_23.png)

![](img/76972bc98e91a2564b96a78380a6119d_24.png)

![](img/76972bc98e91a2564b96a78380a6119d_25.png)

So there's these four points that I'd like to discuss that are colored in orange。



![](img/76972bc98e91a2564b96a78380a6119d_27.png)

The first point， let's look at the lower left hand one， is right in the middle of the cloud of data。



![](img/76972bc98e91a2564b96a78380a6119d_29.png)

It doesn't really have much influence or leverage， okay， so to describe more on what。



![](img/76972bc98e91a2564b96a78380a6119d_31.png)

![](img/76972bc98e91a2564b96a78380a6119d_32.png)

Influence means or what leverage means， let's look at this point that is in the upper rightmost plot。

 remember that our data has to go through the average of the Y's and the average of the xs in that sense。

 we can think of the average the two averages as a midpoint of afulchrome。



![](img/76972bc98e91a2564b96a78380a6119d_34.png)

![](img/76972bc98e91a2564b96a78380a6119d_35.png)

![](img/76972bc98e91a2564b96a78380a6119d_36.png)

![](img/76972bc98e91a2564b96a78380a6119d_37.png)

![](img/76972bc98e91a2564b96a78380a6119d_38.png)

And that the bar， namely the regression line， has to move through thatfulcrum and you can think just like a regular physical fulcrum as you move further out。



![](img/76972bc98e91a2564b96a78380a6119d_40.png)

![](img/76972bc98e91a2564b96a78380a6119d_41.png)

That point will have more leverage， just like I think it's probably easier if I draw a picture。



![](img/76972bc98e91a2564b96a78380a6119d_43.png)

Here's。Here's my Facrrome。Heres。My heavy weight right here， let's say it's one ton。Okay。

 if I need to lift up this weight， if I push down right here on my bar。

 it's going to be a lot harder than if I push down over there。

 well that is the same thing that happens in regression models for if you have a bunch of data。

A data point that is， here's the。Natural range of the x's。

 a data point that's far outside of the natural range of the x's will have high leverage。

 a data point that's right in the middle of the x's will have low leverage。

So the concept of leverage is merely a concept of how far away from the center of the x' is the data point is。

 so influence on the other hand， is whether or not that point chooses to exert that leverage。

 so this point that is far along the regression line。

but still adheres very well to the regression relationship that would be observed if it was removed。

 that point has high leverage， but it opts not to execute that leverage。



![](img/76972bc98e91a2564b96a78380a6119d_45.png)

![](img/76972bc98e91a2564b96a78380a6119d_46.png)

![](img/76972bc98e91a2564b96a78380a6119d_47.png)

On the other hand， look at this lower right hand point。

 if that point were included in the regression line， it would probably have a large effect on it。



![](img/76972bc98e91a2564b96a78380a6119d_49.png)

![](img/76972bc98e91a2564b96a78380a6119d_50.png)

Why because it's outside of the cloud of points and it also doesn't adhere to what the rest of the data is saying that point both has high leverage and high influence in this lecture we're going to go over both。



![](img/76972bc98e91a2564b96a78380a6119d_52.png)

![](img/76972bc98e91a2564b96a78380a6119d_53.png)

![](img/76972bc98e91a2564b96a78380a6119d_54.png)

The concepts of both the concept of leverage and the concepts of influence and how you diagnose them using your data。

 one final point to discuss this upper left hand point that is right in the middle of the cloud of the X values。

 so it has low leverage。

![](img/76972bc98e91a2564b96a78380a6119d_56.png)

![](img/76972bc98e91a2564b96a78380a6119d_57.png)

![](img/76972bc98e91a2564b96a78380a6119d_58.png)

And however， it does not adhere at all to the relationship。

 so this upper left hand point while being an outlier is not going to exert the same influence on the model that this lower right hand point is going to。



![](img/76972bc98e91a2564b96a78380a6119d_60.png)

![](img/76972bc98e91a2564b96a78380a6119d_61.png)

![](img/76972bc98e91a2564b96a78380a6119d_62.png)