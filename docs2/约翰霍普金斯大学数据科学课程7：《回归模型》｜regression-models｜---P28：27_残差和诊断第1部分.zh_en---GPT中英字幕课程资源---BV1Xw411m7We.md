# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P28：27_残差和诊断第1部分.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

Hi and welcome to the class on residualss， Dtics and Vaation。



![](img/c78229d328c55e2f1e670aac289736f4_1.png)

![](img/c78229d328c55e2f1e670aac289736f4_2.png)

Remember， we started out with our linear model。

![](img/c78229d328c55e2f1e670aac289736f4_4.png)

We're also going to assume here throughout the lecture that our errors are normally distributed。

 some of our results require that and some of them don't。



![](img/c78229d328c55e2f1e670aac289736f4_6.png)

Remember how we defined our residuals。

![](img/c78229d328c55e2f1e670aac289736f4_8.png)

And that our estimate of residual variation is the sum of the square the average of the squared residuals。

 where remember we divide by n minus p rather than n for unbiasedness sake。



![](img/c78229d328c55e2f1e670aac289736f4_10.png)

![](img/c78229d328c55e2f1e670aac289736f4_11.png)

![](img/c78229d328c55e2f1e670aac289736f4_12.png)

So it's very easy in R to get a plot of your residuals and several plots that measure aspects of model fit and lack of model fit。

 so let's load up the data Swiss and let's go ahead and fit the linear model that includes all the terms and the easy way to do that is to put a period after the little Tilde symbol so that then it just includes all the terms in the data frame except the outcome of course。



![](img/c78229d328c55e2f1e670aac289736f4_14.png)

![](img/c78229d328c55e2f1e670aac289736f4_15.png)

![](img/c78229d328c55e2f1e670aac289736f4_16.png)

![](img/c78229d328c55e2f1e670aac289736f4_17.png)

![](img/c78229d328c55e2f1e670aac289736f4_18.png)

![](img/c78229d328c55e2f1e670aac289736f4_19.png)

Then the generic command plot actually will just plot the fit。

 it will plot and create a series of residual and diagnostic plots for you。

 I did par MFO equals 22 so that it all fit on one page。



![](img/c78229d328c55e2f1e670aac289736f4_21.png)

![](img/c78229d328c55e2f1e670aac289736f4_22.png)

![](img/c78229d328c55e2f1e670aac289736f4_23.png)

So in this class， we're going to go over what the basics of these plots are。



![](img/c78229d328c55e2f1e670aac289736f4_25.png)

![](img/c78229d328c55e2f1e670aac289736f4_26.png)

So to do that we need to discuss influential points and outlier points and that there's a distinction。

 so here I created a plot where there's a clear linear relationship between most of the data between the predictor and the response。



![](img/c78229d328c55e2f1e670aac289736f4_28.png)

![](img/c78229d328c55e2f1e670aac289736f4_29.png)

![](img/c78229d328c55e2f1e670aac289736f4_30.png)

So there's these four points that I'd like to discuss that are colored in orange。



![](img/c78229d328c55e2f1e670aac289736f4_32.png)

The first point， let's look at the lower left hand one， is right in the middle of the cloud of data。



![](img/c78229d328c55e2f1e670aac289736f4_34.png)

It doesn't really have much influence or leverage， okay， so to describe more on what。



![](img/c78229d328c55e2f1e670aac289736f4_36.png)

![](img/c78229d328c55e2f1e670aac289736f4_37.png)

Influence means or what leverage means， let's look at this point that is in the upper rightmost plot。

 remember that our data has to go through the average of the Y's and the average of the xs in that sense。

 we can think of the average the two averages as a midpoint of afulcrrome。



![](img/c78229d328c55e2f1e670aac289736f4_39.png)

![](img/c78229d328c55e2f1e670aac289736f4_40.png)

![](img/c78229d328c55e2f1e670aac289736f4_41.png)

![](img/c78229d328c55e2f1e670aac289736f4_42.png)

![](img/c78229d328c55e2f1e670aac289736f4_43.png)

And that the bar， namely the regression line， has to move through thatfulcrum and you can think just like a regular physical fulcrum as you move further out。



![](img/c78229d328c55e2f1e670aac289736f4_45.png)

![](img/c78229d328c55e2f1e670aac289736f4_46.png)

That point will have more leverage， just like I think it's probably easier if I draw a picture。



![](img/c78229d328c55e2f1e670aac289736f4_48.png)

Here's。Here's my fallchrome。Here's。My heavy weight right here， let's say it's one ton。Okay。

 if I need to lift up this weight， if I push down right here on my bar。

 it's going to be a lot harder than if I push down over there well that is the same thing that happens in regression models for if you have a bunch of data。

A data point that is， here's the。Natural range of the x's。

 a data point that's far outside of the natural range of the x's will have high leverage。

 a data point that's right in the middle of the x's will have low leverage。

So the concept of leverage is merely a concept of how far away from the center of the x' is the data point is。

 so influence on the other hand， is whether or not that point chooses to exert that leverage。

 so this point that is far along the regression line。

but still adheres very well to the regression relationship that would be observed if it was removed。

 that point has high leverage， but it opts not to execute that leverage。



![](img/c78229d328c55e2f1e670aac289736f4_50.png)

![](img/c78229d328c55e2f1e670aac289736f4_51.png)

![](img/c78229d328c55e2f1e670aac289736f4_52.png)

On the other hand， look at this lower right hand point。

 if that point were included in the regression line， it would probably have a large effect on it。



![](img/c78229d328c55e2f1e670aac289736f4_54.png)

![](img/c78229d328c55e2f1e670aac289736f4_55.png)

Why because it's outside of the cloud of points and it also doesn't adhere to what the rest of the data is saying that point both has high leverage and high influence in this lecture we're going to go over both。



![](img/c78229d328c55e2f1e670aac289736f4_57.png)

![](img/c78229d328c55e2f1e670aac289736f4_58.png)

![](img/c78229d328c55e2f1e670aac289736f4_59.png)

The concepts of both the concept of leverage and the concepts of influence and how you diagnose them using your data。

 one final point to discuss this upper left hand point that is right in the middle of the cloud of the X values。

 so it has low leverage。

![](img/c78229d328c55e2f1e670aac289736f4_61.png)

![](img/c78229d328c55e2f1e670aac289736f4_62.png)

![](img/c78229d328c55e2f1e670aac289736f4_63.png)

And however， it does not adhere at all to the relationship。

 so this upper left hand point while being an outlier is not going to exert the same influence on the model that this lower right hand point is going to。



![](img/c78229d328c55e2f1e670aac289736f4_65.png)

![](img/c78229d328c55e2f1e670aac289736f4_66.png)

![](img/c78229d328c55e2f1e670aac289736f4_67.png)