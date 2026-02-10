# 谷歌数据分析师第五课《通过数据分析回答问题》analyze-data（中英双字） - P15：15_02_05_电子表格中的字符串.zh_en - GPT中英字幕课程资源 - BV1q14y1o7Yj

![](img/71ec6d906123ee3335b42ffd287ffabb_0.png)

Hey， welcome back。 So far， we've worked with strings in both sequel and spreadsheets before。

 and we've learned that they usually have similar functions。 And this video。

 we'll take another look at Ly， left， right， and fine。😊。

You've come across these functions used in SQL， but now you'll find out how they work in spreadsheets。

 Going back to our bike sharing data set。 Let's check out one of their spreadsheets。

This is one of the trip data spreadsheets in the start time and stop time columns。

 There are strings that contain information about date and time of each ride。This is all useful data。

 but chances are will only mean part of these strings to make a formula or answer a question。

For example， these strings contain multiple data points like date and time。

 But if we're trying to find the average time between start times， we won't need the date。

 We can actually use L， left and right and find to split the time stamps into separate columns if we want。

Let's build a simple formula to separate the dates in these strings。

 We know that Lyn tells us the length of a string。Let's check how long these date time strings are now。

 To start， we'll input the first part of the formula。

And then we'll just select one of the cells with the date time string in it。

These strings are 19 characters long。 We can use the fine function to locate specific characters in a string。

 Keep in mind， this is case sensitive。 So if you're using fine to pull a sub string。

 make sure that you've input the sub string correctly。😊。

We notice that all of the date time strings have a space separating the date and the timestamp。

 so we can actually use F to figure out where the date ends。Okay。

 seems like the space is the 11th character in this string。

 So the timestamp substr will start at character 12。

 We can use the left and right functions to select which part of the string we want to isolate in a new column。

 We'll use right on one of these cells to indicate that we want to grab the right side。😊。

And like we've come across before， left actually works exactly the same way。

Now we can apply that to the rest of column C to pull those timestamps。As a data analyst。

 being able to work with strings is a key skill， especially when you find yourself working with data from outside sources。

Hopefully， you're a little bit more comfortable applying L， right。

 left and fine functions in both SQL and spreadsheets。 Later on。

 we'll use these functions to perform even more complicated formulas。

 So feel free to try them out on some data yourself。😊。



![](img/71ec6d906123ee3335b42ffd287ffabb_2.png)

Maybe even some open data like we've been using today。 See ya later。

