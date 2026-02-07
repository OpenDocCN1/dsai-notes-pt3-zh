# IBM数据科学专业证书课程4：《Python应用于数据科学、人工智能和开发》python-for-applied-data-science-ai（中英字幕） - P15：14_Pandas数据处理与保存.zh_en - GPT中英字幕课程资源 - BV1AF411f7yv

When we have a data frame， we can work with the data and save the results in other formats。



![](img/ee5d10cc85db3f503005f0c2c2121297_1.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_2.png)

Consider the stack of 13 blocks of different colors。 We can see there are three unique colors。

 Let's say you would like to find out how many unique elements are in a column of a data frame。

 This may be much more difficult because instead of 13 elements， you may have millions。



![](img/ee5d10cc85db3f503005f0c2c2121297_4.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_5.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_6.png)

Pands has the method unique to determine the unique elements in a column of a data frame。



![](img/ee5d10cc85db3f503005f0c2c2121297_8.png)

Let's say we would like to determine the unique year of the albums in the dataset set。



![](img/ee5d10cc85db3f503005f0c2c2121297_10.png)

We enter the name of the data frame， then enter the name of a column released within brackets。

 Then we apply the method unique。 The result is all of the unique elements in the column released。



![](img/ee5d10cc85db3f503005f0c2c2121297_12.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_13.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_14.png)

Let's say we would like to create a new database consisting of songs from the 1980s。

 and after we can look at the column released for songs made after 1979。

 Then select the corresponding rows。😊。

![](img/ee5d10cc85db3f503005f0c2c2121297_16.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_17.png)

We could accomplish this within one line of code in pandas。 but let's break up the steps。



![](img/ee5d10cc85db3f503005f0c2c2121297_19.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_20.png)

We can use the inequality operators for the entire data frame in pandas。

 The result is a series of Boolean values。 For our case。

 we simply specify the column released and the inequality for the albums After 1979。

 The result is a series of Boolean values。 The result is true when the condition is true and false Otherwise。



![](img/ee5d10cc85db3f503005f0c2c2121297_22.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_23.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_24.png)

We can select the specified columns in one line。 We simply use the data frame's names。

 And in square brackets， we placed the previously mentioned inequality and assign it to the variable D F1。

 We now have a new data frame where each album was released after 1979。



![](img/ee5d10cc85db3f503005f0c2c2121297_26.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_27.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_28.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_29.png)

We can save the new data frame using the method to underscore CSV。

 The argument is the name of the CSV file。 Make sure you include a dot CSV extension。

 There are other functions to save the data frame in other formats。



![](img/ee5d10cc85db3f503005f0c2c2121297_31.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_32.png)

![](img/ee5d10cc85db3f503005f0c2c2121297_33.png)