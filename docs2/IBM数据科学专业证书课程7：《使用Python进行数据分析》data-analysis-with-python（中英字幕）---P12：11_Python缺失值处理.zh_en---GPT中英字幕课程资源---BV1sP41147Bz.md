# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P12：11_Python缺失值处理.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_0.png)

In this video， we will introduce the pervasive problem of missing values。

 as well as strategies on what to do when you encounter missing values in your data。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_2.png)

When no data value is stored for feature for a particular observation。

 we say this feature has a missing value。Usually missing value in dataset set appears as question mark and a0 or just a blank cell。

In the example here， the normalized losses feature has a missing value。

 which is represented with NAN。But how can you deal with missing data。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_4.png)

There are many ways to deal with missing values， and this is regardless of Python。

 R or whatever tool you use。

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_6.png)

Of course， each situation is different and should be judged differently。 However。

 these are the typical options you can consider。

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_8.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_9.png)

The first is to check if the person or group that collected the data can go back and find what the actual value should be。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_11.png)

Another possibility is just to remove the data where that missing value is found。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_13.png)

When you drop data， you could either drop the whole variable or just the single data entry with the missing value。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_15.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_16.png)

If you don't have a lot of observations with missing data。

 usually dropping the particular entry is the best。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_18.png)

If you're removing data， you want to look to do something that has the least amount of impact。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_20.png)

Replacing data is better since no data is wasted。 However。

 it is less accurate since we need to replace missing data with a guess of what the data should be。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_22.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_23.png)

One standard replacement technique is to replace missing values by the average value of the entire variable。

 As an example， suppose we have some entries that have missing values for the normalized losses column。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_25.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_26.png)

And the column average for entries with data is 4500。

While there is no way for us to get an accurate guess of what the missing values under the normalized losses column should have been。

 you can approximate their values using the average value of the column 4500。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_28.png)

But what if the values cannot be averaged， as with categorical variables。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_30.png)

For a variable， like fuel type， there isn't an average fuel type。

 since the variable values are not numbers。 In this case。

 one possibility is to try using the mode the most common， like gasoline。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_32.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_33.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_34.png)

Finally， sometimes we may find another way to guess the missing data。

This is usually because the data gatherer knows something additional about the missing data。

For example， he may know that the missing values tend to be old cars and the normalized losses of old cars are significantly higher than the average vehicle。

 And， of course， finally， in some cases， you may simply want to leave the missing data as missing data。

For one reason or another， it may be useful to keep that observation。

 even if some features are missing。Now， let's go into how to drop missing values or replace missing values in Python。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_36.png)

To remove data that contains missing values， Pada's library has a built in method called droprop N A。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_38.png)

Essentially， with the drop N A method， you can choose to drop rows or columns that contain missing values like N A N。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_40.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_41.png)

So you'll need to specify axis equals0 to drop the rows。

 or axis equals 1 to drop the columns that contain the missing values。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_43.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_44.png)

In this example， there is a missing value in the price column。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_46.png)

Since the price of used cars is what we're trying to predict in our upcoming analysis。

 we'd have to remove the cars， the rows that don't have a listed price。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_48.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_49.png)

It can simply be done in one line of code using data frame， dot drop， N A。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_51.png)

Setting the argument in place to true allows the modification to be done on the data set directly。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_53.png)

In place equals true， just writes the result back into the data frame。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_55.png)

This is equivalent to this line of code。

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_57.png)

Don't forget that this line of code does not change the data frame。

 but it is a good way to make sure that you are performing the correct operation。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_59.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_60.png)

To modify the data frame， you have to set the parameter in place equal to true。

 You should always check the documentation if you are not familiar with a function or method。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_62.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_63.png)

The pandas webpage has lots of useful resources。To replace missing values like NNs with actual values。

 Panda's library has a built in method called replace。

 which can be used to fill in the missing values with the newly calculated values。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_65.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_66.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_67.png)

As an example， assume that we want to replace the missing values of the variable normalized losses by the mean value of the variable。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_69.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_70.png)

Therefore， the missing value should be replaced by the average of the entries within that column。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_72.png)

In Python， first we calculate the mean of the column。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_74.png)

Then we use the method replace to specify the value we would like to be replaced as the first parameter。

 in this case， NAN。

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_76.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_77.png)

The second parameter is the value we would like to replace it with I。e。 the meme in this example。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_79.png)

This is a fairly simplified way of replacing missing values。 There are， of course， other techniques。

 such as replacing missing values for the average of the group。 instead of the entire data set。



![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_81.png)

![](img/4a2f14a1b3091f952c1cb6e5542b2bb7_82.png)

So we've gone through two ways in Python to deal with missing data。

 We learned to drop problematic rows or columns containing missing values。

 And then we learned how to replace missing values with other values。

 But don't forget the other ways to deal with missing data。

 You can always check for a higher quality data set or source。Or in some cases。

 you may want to leave the missing data as missing data。

