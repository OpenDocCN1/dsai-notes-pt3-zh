# 约翰霍普金斯大学数据科学课程3：《获取和清理数据课程（约翰霍普金斯大学）》｜data-cleaning｜ - P9：8_数据表软件包.zh_en - GPT中英字幕课程资源 - BV1wu411P7yX

This lecture is about the data dot table package， which is an often faster and more memory efficient version of the data frames that you're commonly using when you're analyzing data in R。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_1.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_2.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_3.png)

So the data do table inherits from a data frame， so all functions that accept data frame should work on data table and there's a pretty steady set of updates to data table in case it doesn't work。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_5.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_6.png)

It's written in C so it can be much， much faster than some of the functions that are done in data frame it's much much faster at subsetting grouping variables and updating variables than。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_8.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_9.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_10.png)

Data frames are， but it requires you to learn a little bit of a new syntax。

 so there's a little bit of a learning curve。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_12.png)

So if we load the data。 table package， we can create a data frame like this is the usual way that we create a data frame and if we look at that。

 we see it has three variables X， Y， and Z stored in each of the columns。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_14.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_15.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_16.png)

And we can also create a data table and we create it in exactly the same way。

 and so we just pass it the arguments for the variables that we want to create and if you look at the top of that data frame。

 you see it looks very similar to what you would expect if you had created a data frame。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_18.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_19.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_20.png)

So one thing that you can do is see all of the data that tables in memory and so you do that with the tables command。

 it has an S at the end it's different than the table command and so what it'll tell you is the name of the data frame。

 how or data table， how many rows， how many megabytes。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_22.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_23.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_24.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_25.png)

How many columns and if there's a key， and so I'll talk a little bit more about what I mean by a key in a minute。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_27.png)

So the first thing that you might want to be able to do is subset rows and so just like with subsetting the rows of a data frame。

 you can subset with the first spot in the square brackets before the comma。

 you can also subset just like you did rows just like you did with a data frame in a similar way by accessing a particular element Y and looking at only the values where y is equal to a。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_29.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_30.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_31.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_32.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_33.png)

One thing that is a little bit different is when you subset with only one index。

 it's subsets based on the rows， so if I do this data table and take the second and third element。

 that's going to take the second and third rows that come out of that data table。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_35.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_36.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_37.png)

What happens when you try to subset columns， if you just try to subset columns the way you're used to in data frames。

 this is where they really diverge data table and data frame。

 it's not actually trying to subset the columns using the same subsetting function that happens with data frame。

 it does something a little bit different。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_39.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_40.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_41.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_42.png)

And so what it's using is expressions to be able to summarize the data in various different ways。

 So any expression is some set of statements that are between curly brackets like this。

 So here's an example of a statement that says print 10 and then 5 and so this actually prints out 10。

 but when you tell K to print， it just prints out the variable 5 at the end。

 So this will come into play in a minute when we try to use expressions to summarize data sets。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_44.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_45.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_46.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_47.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_48.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_49.png)

So for example， you can instead of putting an index here in the second part of the brackets。

 you can actually pass a list of functions that you want to perform where the functions are applied to variables named by column So here x is one of the variables in the data table and Z is one of the variables in the data table and note we don't have to use parentheses or sorry。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_51.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_52.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_53.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_54.png)

Quotation marks， it will just recognize what the variables that you're trying to use are。

 and so this will report the mean of the x values and the mean of the sum of the z values。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_56.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_57.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_58.png)

You can also do that to perform pretty much any function， you can say， for example。

 get a table of the y values and so anytime you pass a list into this second argument。

 it'll perform those functions and return the values that's good for summarizing data。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_60.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_61.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_62.png)

Another thing that it does very fast and very memory efficiently is to add new columns。

 so suppose you wanted to add a new column to your data table where the new column was equal to the Z variable squared。

 you can use this command where it's colon equals to add that variable W to the data table and the nice thing is is usually when you're adding a new variable to a data frame R will copy over that entire data frame and add the new variable to it so you get two copies of the data frame and memory and so when dealing with big data sets。

 this is obviously going to cause lots of memory problems which you don't have with data table because a new copy isn't created。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_64.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_65.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_66.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_67.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_68.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_69.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_70.png)

You have to be a little bit careful with that though so suppose we set a second data table to be assigned to the first data table and then we make a change to the first data table because a copy hasn't been made if we go back and look at the first data table obviously we've made a change to that we've changed the Y variable to be all equal to twos but the second data table was assigned to be the first data table and since a copy wasn't made we've actually change data table to as well so you have to be able to if you're trying to create a copy you have to explicitly do that with the copy function so if you use the function copy you'd be able to copy the data table over。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_72.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_73.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_74.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_75.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_76.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_77.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_78.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_79.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_80.png)

So the next thing that you can do is you can actually perform multiple step functions to create new variables so for example here I have an expression see it starts with a curly bracket and it ends with a curly bracket and each statement is followed by a semicolon so the first statement is I'm going to assign to the temporary variable。

 the values of x plus Z and then I'm going to take the log base 2 of that temporary variable plus5 and so as you remember the last thing that gets returned from this expression is the evaluation of this last statement and so what ends up happening is you this variable M will be assigned to be log based2 of x plus z plus5 So those sorts of multistep operations can be handled very easily with data table。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_82.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_83.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_84.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_85.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_86.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_87.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_88.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_89.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_90.png)

You can also do plier like operations。 so for example， we can add to this data table of variable a。

 which is greater than0 when equal to true when x is greater than0 and false when x is less than0。

 So now we have a binary variable A that we can work with。

 So suppose we want to summarize another variable by the cases where when x is greater than0 versus the cases when x is less than0。

 So for example， we can take the mean of x plus w and we can do it grouped by a variable A。

 And so what that's going to do is it's going to take the mean of x plus w when a is equal to true。

 and it's going to place that mean。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_92.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_93.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_94.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_95.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_96.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_97.png)

In all the rows where a is equal to true。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_99.png)

Then it's going to take the mean of x plus w where a is equal to false and place that mean in all the rows where a is equal to false。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_101.png)

So it creates a new variable that's equal to the aggregated mean aggregated over the variable that you use by for。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_103.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_104.png)

There are some special variables in data table that allow you to do some things really fast。

 so one is dot n it's an integer linked one and it's containing the number of times that a particular group appears and so for example。

 if I create a data table that has a large number of A's， Bs and C's in it so about 100。

000 ABs and C's。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_106.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_107.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_108.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_109.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_110.png)

Then what I can do is if I want to count the number of times each of those letters appear。

 I can use data table comma。 n， and then grouped by the X variable。

 and what that'll do is it'll count do n is just count the number of times divided by grouped by the X variable。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_112.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_113.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_114.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_115.png)

So it does that very fast compared to say the equivalent operation。

 which is just doing a table of Dt dollar sign X a unique aspect of data tables is that they have keys and so if you set the key。

 it's possible to subset and sort a data table much more rapidly than you would be able to do with the data frame。

 So here I'm going to create a data table and it's going to have a variable X and it's going to have a variable Y。

 and I'm going to set the key for the data table to be the variable X。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_117.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_118.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_119.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_120.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_121.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_122.png)

Then if I want to subset on the basis of x， or if I put in a quoted a here。

 it knows to go and look in the key and the key is x and it very quickly subsets the data to only the values of x that are equal to a。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_124.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_125.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_126.png)

You can also use keys to facilitate joins between data tables， so for example。

 here I've created two data tables where they have a variable X and a variable Y。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_128.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_129.png)

And in this case， the second data table has a variable Z。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_131.png)

And so I can set the key in both cases to be equal to x， so the same key for both data tables。

 and then I can merge them together。 This is actually quite a bit faster than merging with the data frame as long as you have the same key for both operations or for both data tables。

 it can be very fast。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_133.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_134.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_135.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_136.png)

It can also be advantageous to use data tables if you want to be able to read things fast from the disk so here I've created a big data frame。

 so it's a data frame with two very large variables in it and then I set up a temporary file with this command right here and I write our big data frame out to that file。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_138.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_139.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_140.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_141.png)

Then I'm going to time how long it takes to read it in using the F read command。

 the F read command can be applied to read in data tables。

 just like it's basically a drop in substitute for a read dot table with a a tab separated files。



![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_143.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_144.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_145.png)

And so you can see it takes about 0。32 seconds if I tried to do that same operation。

 if I just tried to read do table that file， it would come in quite a bit slower well well more than 10 times slower to be able to read that file in so it's actually much faster to read files with data。

 table as well。

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_147.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_148.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_149.png)

![](img/ae3bcb4937e6ac3242e5b0aa5a0f9106_150.png)

To summarize data table can be both faster and more memory efficient than data frames。

 although it requires you to learn a little bit of new syntax and sometimes to be a little bit careful in terms of copying over data tables。

The latest developments can be found on the development version of the package which can be found at this website right here。

 they've already started to develop meltlike operations and deccast like observations for data tables and they're going to continually update that package it's a very rapidly developing package and then this website here is very nice because it gives you a comprehensive ish list of all the differences between data。

 table and data frames and so that will be very useful if you're transitioning from using data frames to using data table。

The notes that I've used today are very largely based on the notes that Raphael Guardo has put up here on GitHub。

 and they were originally from Kevin Uhi and I think that both of them deserve credit for the excellent notes that I've largely copied here for this lecture。

