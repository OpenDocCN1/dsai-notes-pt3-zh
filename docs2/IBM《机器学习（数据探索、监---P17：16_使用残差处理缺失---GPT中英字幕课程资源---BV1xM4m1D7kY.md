# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P17：16_使用残差处理缺失值和异常值.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/a33ffcfbadedf1ac8049973076f948d4_0.png)

Now， what are residuals， that's going to assume that you have a model and it'll be the difference between the actual value and the predicted value given your model。

 and they're going to represent model failure。

![](img/a33ffcfbadedf1ac8049973076f948d4_2.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_3.png)

So what are some approaches that we can use in order to leverage residuals in order to detect outliers？



![](img/a33ffcfbadedf1ac8049973076f948d4_5.png)

We can use the standardized residual， which is just going to take our residual and divided by the standard error。

 The idea being here， if you have outcome variables between 10 million and 100 million versuss between 0 and 5。

 being off by4 means a much different thing， given those different outcome ranges。

 So we want to standardize it according to those ranges。



![](img/a33ffcfbadedf1ac8049973076f948d4_7.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_8.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_9.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_10.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_11.png)

Next， we can use deleted residuals。

![](img/a33ffcfbadedf1ac8049973076f948d4_13.png)

And what you can do here is you remove that observation from the data frame， and once you do that。

 you see what the new model will predict and see if there's a big difference between the original model and the model with this deleted observation。



![](img/a33ffcfbadedf1ac8049973076f948d4_15.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_16.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_17.png)

Finally， there's going to be the studentized residuals or sometimes called the externally studentized residuals。

 and this is essentially just going to take our deleted residuals and standardize them as we saw in our first standardized residual discussion。



![](img/a33ffcfbadedf1ac8049973076f948d4_19.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_20.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_21.png)

So it'll take out one of those observations。 Once you take out that observation。

 you see the effect on the model and you standardize that according to the range of that model。



![](img/a33ffcfbadedf1ac8049973076f948d4_23.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_24.png)

So what are some things that you can do once you do detect an outlier。

 you can remove them altogether， The pro to this is that you no longer need to worry about their effects。

 but you may have lost not only an important value but the entire row related to that value。



![](img/a33ffcfbadedf1ac8049973076f948d4_26.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_27.png)

You can assign a different value to that outlier again。

 then you don't have to worry about the effects of this outlier on your model。 But again。

 you will be。

![](img/a33ffcfbadedf1ac8049973076f948d4_29.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_30.png)

Losing what may have been an important value。 but this time not having to lose the remainder of the row。



![](img/a33ffcfbadedf1ac8049973076f948d4_32.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_33.png)

We can transform the column that actually had the outlier。

 and once you do something like a log transformation， that outlier， given the new range。

 may no longer be an outlier。

![](img/a33ffcfbadedf1ac8049973076f948d4_35.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_36.png)

We can also predict what that value would have been。



![](img/a33ffcfbadedf1ac8049973076f948d4_38.png)

We can do that either by using similar observations， so looking at the other observations。

 the other features that were not outliers and see what that outlier would have been if it's similar to those observations。



![](img/a33ffcfbadedf1ac8049973076f948d4_40.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_41.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_42.png)

We can also use regression， and that can do a good job of also predicting what that value would have been。

 given the other features。

![](img/a33ffcfbadedf1ac8049973076f948d4_44.png)

And this may do a good job of seeing what that value should have been if we have enough other data。

 but we may lose important value again， similar as we discussed with all the other ways of replacing our outlier。

 And it' going to require a lot more work than any of our other methods of working with outliers。



![](img/a33ffcfbadedf1ac8049973076f948d4_46.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_47.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_48.png)

And then finally， we can just keep that value， the idea being here that you will probably want to use a model that is resistant to outliers and we'll discuss some of those later on as we get into modeling in later courses。



![](img/a33ffcfbadedf1ac8049973076f948d4_50.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_51.png)

So a quick recap of what we discuss。 We discuss the different factors of why data cleaning is so important。

 Remember， there's no way for our algorithms to learn from the data If the data lacks the underlying information。



![](img/a33ffcfbadedf1ac8049973076f948d4_53.png)

We discuss issues that arise with messy data， we touched on a lack of data， too much data。

 missing data， inconsistent text， and how that all ties into this idea of messy data。



![](img/a33ffcfbadedf1ac8049973076f948d4_55.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_56.png)

We discuss how we want to ensure that we identify duplicates and unnecessary data correctly because they play a role in getting a strong model。



![](img/a33ffcfbadedf1ac8049973076f948d4_58.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_59.png)

We also discussed the pros and cons of different methods of working without wires。



![](img/a33ffcfbadedf1ac8049973076f948d4_61.png)

And in this next lesson， we'll be taking the next steps in regards to machine learning workflow and dive into doing exploratory data analysis。



![](img/a33ffcfbadedf1ac8049973076f948d4_63.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_64.png)

![](img/a33ffcfbadedf1ac8049973076f948d4_65.png)