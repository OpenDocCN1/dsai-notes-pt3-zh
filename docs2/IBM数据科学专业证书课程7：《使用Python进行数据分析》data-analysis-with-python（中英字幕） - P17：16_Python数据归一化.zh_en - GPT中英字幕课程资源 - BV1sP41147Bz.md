# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P17：16_Python数据归一化.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

In this video， we'll be talking about data normalization。

 an important technique to understand in data pre processing。

 When we take a look at the used car data set， we notice in the data that the feature length ranges from 150 to 250。

 While feature width and height ranges from 50 to 100。

 We may want to normalize these variables so that the range of the values is consistent。

 This normalization can make some statistical analyses easier down the road。

 by making the ranges consistent between variables。

 normalmalization enables a fairer comparison between the different features。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_1.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_2.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_3.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_4.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_5.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_6.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_7.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_8.png)

Making sure they have the same impact， it is also important for computational reasons。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_10.png)

Here is another example that will help you understand why normalization is important。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_12.png)

Consider a data set containing two features， age and income， where age ranges from zero to 100。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_14.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_15.png)

While income ranges from 0 to 20000 and higher。

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_17.png)

Income is about 1000 times larger than age and ranges from 20000 to 500000。

 So these two features are in very different ranges。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_19.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_20.png)

When we do further analysis， like linear regression， for example。

 the attribute income will intrinsically influence the result more due to its larger value。

 But this doesn't necessarily mean it is more important as a predictor。

 So the nature of the data biases， the linear regression model to weigh income more heavily than age。

 to avoid this， we can normalize these two variables into values that range from 0 to 1。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_22.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_23.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_24.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_25.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_26.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_27.png)

Compare the two tables at the right after normalization。

 Both variables now have a similar influence on the models we will build later。

 There are several ways to normalize data。 I will just outline three techniques。

 The first method called simple feature scaling just divides each value by the maximum value for that feature。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_29.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_30.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_31.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_32.png)

This makes the new values range between 0 and one。 The second method called min max takes each value X underscore old。

 subtract it from the minimum value of that feature。 Then divides by the range of that feature。

 Again， the resulting new values range between 0 and one。

 The third method is called Z score or standard score。 In this formula for each value。

 you subtract the mu， which is the average of the feature， and then divide by the standard deviation。

 sigma。

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_34.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_35.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_36.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_37.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_38.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_39.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_40.png)

The resulting values hover around  zero and typically range between negative 3 and positive 3。

 but can be higher or lower。Following our earlier example。

 we can apply the normalization method on the length feature。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_42.png)

First， we use the simple feature scaling method where we divide it by the maximum value in the feature。

Using the panda's method Max， this can be done in just one line of code。

Here's the min max method on the length feature。 We subtract each value by the minimum of that column。

 then divide it by the range of that column。 The max minus the min。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_44.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_45.png)

Finally， we apply the Z score method on length feature to normalize the values Here we apply the mean and STD method on the length feature。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_47.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_48.png)

![](img/3f48f2c53ad3c7a6686eaf8c2784d123_49.png)

Mean method will return the average value of the feature in the data set。

 an STD method will return the standard deviation of the features in the dataset set。



![](img/3f48f2c53ad3c7a6686eaf8c2784d123_51.png)