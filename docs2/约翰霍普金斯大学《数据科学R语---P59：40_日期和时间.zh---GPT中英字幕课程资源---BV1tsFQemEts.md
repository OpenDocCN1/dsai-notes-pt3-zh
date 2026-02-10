# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P59：40_日期和时间.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

I want to talk briefly about dates and times in R， which is' a very special topic and could require a lot more time and I'm just going to talk a little bit about how R represents dates and times and how you can use them in arithmetic and data analysis types of computations。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_1.png)

R has a special way to represent dates and times and they're represented using special data classes so in the past we've talked about different data types like lists and character vectors and numeric vectors and so this is just another type of data on top of those kinds of classes so dates are represented by the date class and times are represented by two separate classes。

 the Poss CT and the Poss LT class so dates are basically don't have times attached them they they represented a day in a year in a month and you can think of them in the kind of a year month day format so for example this date。

Is 1970， January and then January 1。 And so internally。

 the dates are stored as as the number of days since 1970 January 1。

 that particular detail is not very important， but in case you're wondering you don how how how R actually does calculations based on dates。

 times are stored internally as the number of seconds since 1970， January 1。 And so that's again。

 another underlying detail that's not very important， but may be useful to know sometimes。

 So the way dates in our work is you can take a character string like this following 19700101。

 and convert it into a date using the as dot date function。

 that's probably the most common way that you'll start your begin working with dates。

 And you'll notice that if you print out this object。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_3.png)

It'll get something that looks like a character string。 Now it's not actually a character string。

 but it will print out that way because there's a special print method。😊。

Now if I unclass the object here， you'll see I get the number zero。

 remember because the dates are stored internally as the number of days since 1970。

 January 1s and since 1970 January 1st， zero days from that point you'll get zero if I input January 2 1970。

 then you'll see that underlying is represented as the number one because that's one day after 1970。

 January 1t if you had a date that was before 1970。

 then they would be represented as negative numbers so but Dutch this for your little background you don't have to worry about the underlying representation ultimately what you need to know them is that dates are stored as objects of the date class。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_5.png)

Times on the other hand are represented as two possible types。

 one is called Pos CT and the other one's called Poss LT。

 So Poss is a family of computing standards for how things should be done on certain types of computers or how data should be represented。

 and so there's a family of standards for how to represent dates and times and so that's part of the Pos standard。

 so in the Pos CT class times are represented just as very large integers。

And so it's a useful type of class if you want to say store times in a data frame or something like that because basically it's like a big integer vector Pos Lt stores a time as a list underlying and so and it stores a bunch of other useful information about a given time。

 for example， what's the day of the week of that time what's the day of the year。

 the day of the month or the month itself and there are a number of generic functions that operate on both dates and times that you can use such as so the weekdays function tells you what day of the week a given time is or a given day is the months function tells you what month that date or time is and the quarter function gives you the quarter number so for example Q1 would be January through March。

 Q2 would be April through June etc like that So these generic functions operate on on objects of class Pos CTt Pos LT or date。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_7.png)

![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_8.png)

So for example， you can coerce things back and forth between Pos LT and Po CT if you want using the as dot Pos LT or the as dot Pos CT function。

 so for example， the S dot time function here just gives you the current time as it's known by the system and you can see that whens it prints out in a year month day format and then an hour minute second format。

And then the time zone， which is Eastern standard time right now。

So you can convert this to a Po LT using as that Pos LT and Pos L remember underlying is a list。

 so you can look at the names of the elements in this list if you uncl it you can see that there's an element called seconds。

 that's the seconds and the minutes， the hours， the M day is the day of the month。

Which in this case would be 23。The month is just the month you're in。

 so that's January and then the year， the weekday， so the day of the week， the year day。

 which is the day into the year， and then are we on daylight savings or not？

So if I extract the seconds element of this list， you'll see it's 11。

86 and so this actually gives you the seconds in fractional seconds， so it's 11 seconds and then 0。

86 seconds， so that's the number of seconds in the time。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_10.png)

The Pos CT format you can see is you can also get it from the S time function。

 and you can see that if I uncl this Pos CT object。

 I get this very large integer because that's just the number of seconds since January 1st， 1970。

Now if I try to apply the list operator， the dollar sign to this object。

 you'll see I'll get an error because objects of Pos CT don't have these list elements in them。

 if you want to get those list elements out， you have to convert it to Pos LT using the as dot Pos LT function。

 and then I can get the seconds out in this case it's 11。88 seconds。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_12.png)

So finally there's a the stir P time function which converts dates that are written in character string format into date or time objects in this case it converts them into time objects and they use what's what are called format strings so here I've got a string that says January 10th comma 2012 and then 1040 meaning 10 hour 10 and minute 40。

And then I have another string that is December 9 2012 910。

 so if I want to convert these strings to time objects。

 I can use the stir P time function what I do is I pass it the character vector。

 character vector and then I pass it a format string so in this case I got and so you'll see all these percent signs followed by letters and then you can figure you can look up what these symbols mean in the help page for stir P time。

So percent B means the month is the unabbbreviated month name， percent D is the day。

 then comma and then percent capital Y is the four digit year。

 and then percent capital H is the hour because I colon followed by percent capital N。

 which is the minute， and so that's the format of the times here。

You can see that after I call  third P time when I print out X， I get these time objects。

That are formatted that are printed out in the standard format。

 When you look at the class of this object， you'll see it's in apo LT format and so。😊。

That's the so you can look at that's the kind of underlying list format here now I personally can never remember what those formatting strings are like percent B。

 percent D， percent Y I can never remember what those are。

 and so I always have to look at the help page for St time to remember what those details are。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_14.png)

Now， once you've got data in the date or time format and you can do operations on them。

 which can be very handy， for example， you can add and track dates， you can compare dates。

 you can see is one date less than another date or are these two dates equal to each other。

So one thing you need to be careful is that you can't always mix different classes。

 so if you're here I have x， which is a date object and then a Y which is a Pa LT object。

If I try to subtract the two， you'll get an error because they're not the same type of object。

 but if I convert the date to a Pos LT object so I can do as that Pos LT on it。

 then if I take the difference it'll say that there's a difference of 356。3 days between the two。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_16.png)

The nice thing about date and time operators is that they keep track of very tricky things like leap years。

 leap seconds， daylight savings and time zones， so just this first example here。

 you can see that so 2012 there was a leap year and so there was a February 29th and so the difference between March 1s and February 28 is actually a difference of two days。

 not a difference of one day like it is every other year。Similarly， I can take two times1。

 which is in my x， which is in my kind of current time zone。

 and then y which is in the time zone of GMT， so Greenwich mean time and take the difference between those。

 so even though it looks like it should be a five hour difference。

 it's actually only a one hour difference because of the change in the time zones。

So one of the advantages of using the datetime classes is that it will automatically take care of these kind of irregularities。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_18.png)

So now it's just a quick kind of overview of the dates and the time classes in R。

 so just to summarize there are special classes in R that represent dates and times and allow you to do in numerical miracle and statistical calculations dates use the date class times use either the Pos CT or the Pos LT class and then character strings can be coerced to either a date or a time class using the thirdp time function or as dot date as do Pos LT and as dotpos CT the other thing to note that I haven't really talked about here is that a lot of the plotting functions will recognize date time object。

 so when you try to plot an object that's a date time class it will recognize that object and then format the X axis in a special way so that it will have a time kind of element to it so you might want to try to experiment with that a little bit to see how plots change when you use a date time class。



![](img/a096fa4d8d43d385d54c0ae2a2a2cfab_20.png)