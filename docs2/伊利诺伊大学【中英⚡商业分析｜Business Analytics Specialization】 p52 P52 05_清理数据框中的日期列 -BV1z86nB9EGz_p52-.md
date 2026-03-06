# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p52 P52 05_清理数据框中的日期列 -BV1z86nB9EGz_p52-

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_0.png)

In this video， I'm going to talk about how to deal with calendar dates of a panda's data frame。Now。

 dates are an important topic because they come up a lot， but it's also a frustrating topic。

 and that's because of the inconsistency with which dates are recorded and reported。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_2.png)

And then there's other things like the time zone that we have to worry about。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_4.png)

Fortunately， Padas has some very helpful functions that help us to easily deal with many of these situations。

So in this video， rather than watching me type out code， I'm mostly going to be running code。

All right， in this Jupiter lab environment， I've created a simple data frame that has four rows labeled 0 to3 and three columns。

 date 1， date 2， date 3， importantly， these are all object data types。

 meaning they're string data types。

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_6.png)

And then as we look at the values in those columns。

 we can see that the values in the date one column are all recorded using the same format。

 and this is known as the ISO 8601 format， where we've got the  four digit year followed by a hyphen。

 then the two digit month， followed by a hyphen， followed by the two digit day of the month。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_8.png)

And then the values and columns， date 2 and date 3 are recorded inconsistently。

 So we'll talk about how to deal with those。So let's first just talk about how to convert a string column to a date data type。

 This will be really easy in most situations because Padas has created this very useful two date time function。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_10.png)

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_11.png)

And you can see it's very easy to use。 We'll simply refer to the existing column here。

 set it equal to。 and then we're going to use this pandas2 date time function。

 and then the column again。 and then we'll display the information in the first5 rows。

 you can see that the first five rows don't look any different。

 But if we look at the data type for that date 1 column。 It now says date time 64 N S。

 So this is a date， time， data type。 It records the date and the time and N S for nanosecond。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_13.png)

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_14.png)

So it'll record very specific values in here。

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_16.png)

So with that in mind， let's talk about how you can access various date characteristics like day of the week or month of the year and so on。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_18.png)

So the main thing to keep in mind is that there is a dot Dt accessor。

 And once you add that after the name of a date time data type column。

 you can access a lot of things。 It's very much like the dot SR accessor for string columns。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_20.png)

So in this example right here， I'll just go ahead and run it。

I'm creating a new column D1 underscore D O W。 And this is going to be equal to the values in the date 1 column。

 Then I'm going to type out dot D T and then dot and then day of week。 Okay。

 and it's going to return the number here that's associated with the day of the week。

That this date in date 1 is reporting。So to demonstrate how this works。I'm just going to copy that。

Comment out that line， paste it。And then let's say we're not quite sure whether 0 is Sunday。

 That's what I would think。 And so I can start looking for other methods associated with this。

 And there's this day name。 Now， we can see this is a function rather than an instance。

 So when I select that， I need to include the open and close parentheses。AndNow if I run that。

 I can see that that three is associated with Thursday and0 is Monday， so by default。

 it will return zero for Mondays and you can change that， but anyway。

 those are just an example of two of the date characteristics that you can extract once you have a column that has a datetime data type。

All right， let's go ahead and talk about scenarios that you'll probably see， but maybe not as often。

 but are really important。 So let's look at the date 2 column。 And this column。

 everything is still recorded in kind of this IO8601 format。

 But then we've also got for some of them。 we've got the hours minute seconds。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_22.png)

And then for this last one， hours， minute， seconds and thousands of a second。

And also a situation where we don't have any seconds or hours or minutes after it。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_24.png)

So if we were to try to convert this column to a date time data type， it would give us an error。

And if we go down to the bottom of thearrow， it'll tell us why we've got that problem here。

 And it basically says it looks like they're in the IOA 601 format， but not exactly the same format。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_26.png)

And so what we can do is say， hey， we've got a mixed format here。 And this is really cool。

 So if we copy this。😊。

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_28.png)

And then paste it in here。Just add the format equals mixed， and then run up。

Now you can see that it did， in fact， convert all values to a date time data type。

And it looks like it did it correctly。 Okay， we've got the same dates here。

 If we were to compare these。 They're all the same date。

 and I' even converted those time values appropriately。 All right。

 so just make sure to use that format equals mixed when you have inconsistent recordings of the data。

Now， there are some situations where it's impossible for the panda's two date time function to get it correct。

All right， so for instance， if I look at this date  three column。

 the intention here is that each of these values in this column are representing April 3rd of the year 2027。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_30.png)

Okay， so again， I've got some mixed ways of doing this。 But in each of these first three rows。

 the month comes before the day in this bottom row， it's the day before the month。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_32.png)

And so， if I run this。

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_34.png)

And it really is my intent that these are all April 3。

 You can see that it didn't correctly convert that。 But there's really no way that it can know that。

 That's what I intended。

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_36.png)

So I show you this just so that you're aware of potential situations where it won't work。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_38.png)

And in those types of situations， you may have to split the data frame apart into those observations where the day comes first and then apply the appropriate conversion and then combine them back together into a single data frame。

 But we're not going to demonstrate that here。 So just something to be aware of。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_40.png)

All right， once we have date time data types， let's talk about how we can calculate differences in dates。

 like how much time has passed。So let's go ahead and demonstrate this by calculating。

A new column D1 underscore D2 by simply taking the values in the date 1 column。

 subtracting the values in the date 2 column。

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_42.png)

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_43.png)

We'll run that and this new column， we can see we've got the time differences here。

 So for this first observation， April 3r at midnight， basically 2025 compared to April 3rd at noon。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_45.png)

So just 12 hours later。It reports in a way that I， I think might be。Ioneous。

 it says minus-1 day and 12 hours。I think it's just supposed to be minus 12 hours。Now。

 this this first day is， this first date is 12 hours behind the second one here。For these next two。

 it does report them correctly。 So we've got。Basically， midnight。

 if there's not a time associated with it， it'll assume midnight compared to one second before that。

 And in this case， it's correct。 It says0 days and just one second later。 that's the difference。

And these are the same date here， both midnight， and it correctly reports zero days。

And then this last row， again， we get， I think， what is erroneous because these are both August 9。

2032。 but the second one is  three hours，15 minutes，24 seconds and 325 milliseconds after。And。

It's something that I don't quite understand， but anyway。

 you can calculate the difference between dates。In a way that is very easy。

 just using the minus sign in there。

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_47.png)

However， notice that it's recorded as a time delta and you can see that it's not recorded as just a number。

And so if we want to convert this to a numeric value。

 then we can simply use the two numeric function from the pandas module。 And when we do that。

 it will store it as billions of a second or a nanosecond。 Okay。

 so the difference between these first two dates is， I don't know， many billions of a second。

 and this。Really isn't helpful for most business situations。

 So what we can do is when we convert it to a numeric value is we can divide it by this number right here。

 which is 1 billion。 So billionth of a second Time 60 seconds， times 60 minutes。

 times 24 hours in a day。 And when I do that， it'll tell me the number of days between the dates。

 And so this is correct here， right， It's just a half day before。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_49.png)

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_50.png)

And so it's it's stored correctly。 I think sometimes it just may not report it in a way that I understand or appreciate。

 or maybe it's an error。 I don't know。 You just got to make sure that when you convert it to nu values that you make this conversion from billions of a second to either the minutes。

 hours or days or months， or， whatever it is you want。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_52.png)

All right， we can also calculate the amount of time that has passed since today。

 and so there's a useful function in pandas。And that is the timestamp dot now。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_54.png)

And if you were to run just that function。

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_56.png)

It will return the time of the clock on the computer。

 So if we take that and let's say we want to find out how much time has passed between now and the values in the date 1 column and then save it as a new column day in date 1。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_58.png)

I can。Just use that timestamp dot now function。 And now I can see the number of days since date 1。

 the values and date 1 there。 Okay， so that's really helpful for calculating。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_60.png)

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_61.png)

The amount time this passed relative to today day。 What about the days before or after a particular date。

 In this case， we're going to calculate what the date is。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_63.png)

10 days after the values in the date 1 column。 So the way I'm going to do that is I'm going to add。

 and then rather than just an integer 10， I need to indicate that it's 10 days， right， Otherwise。

 if it's 10， it might be 10 billionth of a second or something。

 So I'm going to use this time delta function in pandas indicate the value and then the unit that I want。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_65.png)

And when I do that， now I can see 10 days after April 3rd， 2025 is April 13， 2025 and so on。

 So there are many more considerations and things that you may need to do when working with dates and times。

 but again， hopefully this is a good introduction and it will allow you to work with many of the issues that you do face when dealing with dates and pandas data frames。



![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_67.png)

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_68.png)

![](img/6aba8c7dd8b85f66e0bd34c788bec1fd_69.png)