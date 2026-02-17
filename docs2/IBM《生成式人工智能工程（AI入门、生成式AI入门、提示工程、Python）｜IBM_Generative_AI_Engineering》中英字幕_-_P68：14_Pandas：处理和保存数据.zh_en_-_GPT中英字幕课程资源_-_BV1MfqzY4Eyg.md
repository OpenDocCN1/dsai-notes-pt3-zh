# IBM《生成式人工智能工程（AI入门、生成式AI入门、提示工程、Python）｜IBM Generative AI Engineering》中英字幕 - P68：14_Pandas：处理和保存数据.zh_en - GPT中英字幕课程资源 - BV1MfqzY4Eyg

When we have a data frame， we can work with the data and save the results in other formats。



![](img/345a0fab8d092030094a06ad81844f06_1.png)

Consider the stack of 13 blocks of different colors。 We can see there are three unique colors。

 Let's say you would like to find out how many unique elements are in a column of a data frame。

 This may be much more difficult because instead of 13 elements， you may have millions。



![](img/345a0fab8d092030094a06ad81844f06_3.png)

Pands has the method unique to determine the unique elements in a column of a data frame。



![](img/345a0fab8d092030094a06ad81844f06_5.png)

Let's say we would like to determine the unique year of the albums in the data set。

We enter the name of the data frame， then enter the name of the column released within brackets。

 Then we apply the method unique。 The result is all of the unique elements in the column released。



![](img/345a0fab8d092030094a06ad81844f06_7.png)

Let's say we would like to create a new database consisting of songs from the 1980s and after we can look at the column released for songs made after 1979。

 Then select the corresponding rows。😊。

![](img/345a0fab8d092030094a06ad81844f06_9.png)

We could accomplish this within one line of code in pandas， but let's break up the steps。



![](img/345a0fab8d092030094a06ad81844f06_11.png)

We can use the inequality operators for the entire data frame in pandas。

 The result is a series of Boolean values。 For our case。

 we simply specify the column released and the inequality for the albums After 1979。

 The result is a series of Boolean values。 The result is true when the condition is true and false Otherwise。



![](img/345a0fab8d092030094a06ad81844f06_13.png)

We can select the specified columns in one line。 We simply use the data frame's names。

 And in square brackets， we placed the previously mentioned inequality and assign it to the variable D F1。

 We now have a new data frame where each album was released after 1979。



![](img/345a0fab8d092030094a06ad81844f06_15.png)

![](img/345a0fab8d092030094a06ad81844f06_16.png)

We can save the new data frame using the method to underscore CSV。

 The argument is the name of the CSV file。 Make sure you include a dot CSV extension。

 There are other functions to save the data frame in other formats。



![](img/345a0fab8d092030094a06ad81844f06_18.png)