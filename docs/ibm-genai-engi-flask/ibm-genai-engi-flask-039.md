# 039：IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p39 9_在Python中数据归一化.zh_en -BV1NAq6Y9E7z_p39-

In this video， we'll be talking about data normalization。

 an important technique to understand in data pre processing。

 When we take a look at the used car data set， we notice in the data that the feature length ranges from 150 to 250。

 While feature width and height ranges from 50 to 100。

 we may want to normalize these variables so that the range of the values is consistent。

 This normalization can make some statistical analyses easier down the road by making the ranges consistent between variables。

 normalization enables a fairer comparison between the different features。



![](img/3decebb1710cdda843c2ae7b56e7718f_1.png)

Making sure they have the same impact， it is also important for computational reasons。



![](img/3decebb1710cdda843c2ae7b56e7718f_3.png)

Here is another example that will help you understand why normalization is important。

Consider a data set containing two features， age and income， where age ranges from zero to 100。

 while income ranges from  zero to 20，000 and higher。

Income is about 1000 times larger than age and ranges from 20，000 to 500，000。

 So these two features are in very different ranges。When we do further analysis。

 like linear regression， for example， the attribute income will intrinsically influence the result more due to its larger value。

 But this doesn't necessarily mean it is more important as a predictor。

 So the nature of the data biases， the linear regression model to weigh income more heavily than age。



![](img/3decebb1710cdda843c2ae7b56e7718f_5.png)

To avoid this， we can normalize these two variables into values that range from 0 to 1。

Compare the two tables at the right after normalization。

 Both variables now have a similar influence on the models we will build later。

 There are several ways to normalize data。 I will just outline three techniques。

 The first method called simple feature scaling just divides each value by the maximum value for that feature。



![](img/3decebb1710cdda843c2ae7b56e7718f_7.png)

This makes the new values range between 0 and one。 The second method called min max takes each value X underscore old。

 subtract it from the minimum value of that feature。 Then divides by the range of that feature。

 Again， the resulting new values range between 0 and one。

 The third method is called Z score or standard score。 In this formula for each value。

 you subtract the mu， which is the average of the feature。

 and then divide by the standard deviation sigma。The resulting values hover around 0 and typically range between negative 3 and positive 3。

 but can be higher or lower。

![](img/3decebb1710cdda843c2ae7b56e7718f_9.png)

Following our earlier example， we can apply the normalization method on the length feature。 First。

 we use the simple feature scaling method where we divide it by the maximum value in the feature using the pandas method Max。

 This can be done in just one line of code。

![](img/3decebb1710cdda843c2ae7b56e7718f_11.png)

![](img/3decebb1710cdda843c2ae7b56e7718f_12.png)

Here's the min max method on the length feature。 We subtract each value by the minimum of that column。

 then divide it by the range of that column。 The max minus the min。



![](img/3decebb1710cdda843c2ae7b56e7718f_14.png)

![](img/3decebb1710cdda843c2ae7b56e7718f_15.png)

Finally， we apply the Z score method on length feature to normalize the values Here。

 we apply the mean and ST D method on the length feature。😊。



![](img/3decebb1710cdda843c2ae7b56e7718f_17.png)

Mean method will return the average value of the feature in the data set。

 an STD method will return the standard deviation of the features in the data set。



![](img/3decebb1710cdda843c2ae7b56e7718f_19.png)