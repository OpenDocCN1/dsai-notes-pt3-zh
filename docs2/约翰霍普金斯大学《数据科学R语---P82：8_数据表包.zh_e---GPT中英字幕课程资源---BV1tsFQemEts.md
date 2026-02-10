# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P82：8_数据表包.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

This lecture is about the data dot table package， which is a often faster and more memory efficient version of the data frames that you're commonly using when you're analyzing data in R。



![](img/26cfcb0c4412a535f619286d65eef174_1.png)

So the data do table inherits from a data frame， so all functions that accept data frame should work on data table。

 and there's a pretty steady set of updates to data do table in case it doesn't work。



![](img/26cfcb0c4412a535f619286d65eef174_3.png)

It's written in C so it can be much much faster than some of the functions that are done in data frame it's much much faster at subsetting grouping variables and updating variables than。

Data frames are， but it requires you to learn a little bit of a new syntax。

 so there's a little bit of a learning curve。

![](img/26cfcb0c4412a535f619286d65eef174_5.png)

So if we load the data。 table package， we can create a data frame like this is the usual way that we create a data frame and if we look at that。

 we see it has three variables X， Y， and Z stored in each of the columns。



![](img/26cfcb0c4412a535f619286d65eef174_7.png)

![](img/26cfcb0c4412a535f619286d65eef174_8.png)

And we can also create a data table and we create it in exactly the same way。

 and so we just pass it the arguments for the variables that we want to create and if you look at the top of that data frame。

 you see it looks very similar to what you would expect if you had created a data frame。



![](img/26cfcb0c4412a535f619286d65eef174_10.png)

![](img/26cfcb0c4412a535f619286d65eef174_11.png)

So one thing that you can do is see all of the data that tables in memory and so you do that with the tables command。

 it has an S at the end， it's different than the table command and so what it'll tell you is the name of the data frame。

 how or data table， how many rows， how many megabytes。



![](img/26cfcb0c4412a535f619286d65eef174_13.png)

How many columns and if there's a key， and so I'll talk a little bit more about what I mean by a key in a minute。



![](img/26cfcb0c4412a535f619286d65eef174_15.png)

So the first thing that you might want to be able to do is subset rows and so just like with subsetting the rows of a data frame you can subset with the first spot in the square brackets before the comma。

 you can also subset just like you did rows just like you did with a data frame in a similar way by accessing a particular element y and looking at only the values where y is equal to a。



![](img/26cfcb0c4412a535f619286d65eef174_17.png)

![](img/26cfcb0c4412a535f619286d65eef174_18.png)

One thing that is a little bit different is when you subset with only one index。

 it's subsets based on the rows， so if I do this data table and take the second and third element。

 that's going to take the second and third rows that come out of that data table。



![](img/26cfcb0c4412a535f619286d65eef174_20.png)

![](img/26cfcb0c4412a535f619286d65eef174_21.png)

What happens when you try to subset columns， if you just try to subset columns the way you're used to in data frames。

 this is where they really diverge data table and data frame。

 it's not actually trying to subset the columns using the same subsetting function that happens with data frame。

 it does something a little bit different。

![](img/26cfcb0c4412a535f619286d65eef174_23.png)

![](img/26cfcb0c4412a535f619286d65eef174_24.png)

![](img/26cfcb0c4412a535f619286d65eef174_25.png)

And so what it's using is expressions to be able to summarize the data in various different ways。

 So any expression is some set of statements that are between curly brackets like this。

 So here's an example of a statement that says print 10 and then 5 and so this actually prints out 10。

 but when you tell K to print， it just prints out the variable 5 at the end。

 So this will come into play in a minute when we try to use expressions to summarize data sets。



![](img/26cfcb0c4412a535f619286d65eef174_27.png)

![](img/26cfcb0c4412a535f619286d65eef174_28.png)

![](img/26cfcb0c4412a535f619286d65eef174_29.png)

So for example， you can instead of putting an index here in the second part of the brackets。

 you can actually pass a list of functions that you want to perform where the functions are applied to variables named by column。

 So here x is one of the variables in the data table and Z is one of the variables in the data table and note we don't have to use parentheses or sorry。



![](img/26cfcb0c4412a535f619286d65eef174_31.png)

Quotation marks， it will just recognize what the variables that you're trying to use are。

 and so this will report the mean of the x values and the mean of the sum of the z values。

You can also do that to perform pretty much any function， you can say， for example。

 get a table of the y values and so anytime you pass a list into this second argument。

 it'll perform those functions and return the values that's good for summarizing data。



![](img/26cfcb0c4412a535f619286d65eef174_33.png)

Another thing that it does very fast and very memory efficiently is to add new columns。

 so suppose you wanted to add a new column to your data table where the new column was equal to the Z variable squared。

 you can use this command where it's colon equals to add that variable W to the data table and the nice thing is is usually when you're adding a new variable to a data frame R will copy over that entire data frame and add the new variable to it so you get two copies of the data frame and memory and so when dealing with big data sets this is obviously going to cause lots of memory problems which you don't have with data table because a new copy isn't created。



![](img/26cfcb0c4412a535f619286d65eef174_35.png)

![](img/26cfcb0c4412a535f619286d65eef174_36.png)

![](img/26cfcb0c4412a535f619286d65eef174_37.png)

![](img/26cfcb0c4412a535f619286d65eef174_38.png)

You have to be a little bit careful with that though so suppose we set a second data table to be assigned at the first data table and then we make a change to the first data table because a copy hasn't been made if we go back and look at the first data table obviously we've made a change to that we've changed the Y variable to be all equal to twos but the second data table was assigned to be the first data table and since a copy wasn't made we've actually changed data table to as well so you have to be able to if you're trying to create a copy you have to explicitly do that with the copy function so if you use the function copy you'd be able to copy the data table over。



![](img/26cfcb0c4412a535f619286d65eef174_40.png)

![](img/26cfcb0c4412a535f619286d65eef174_41.png)

So the next thing that you can do is you can actually perform multiple step functions to create new variables。

 so for example here I have an expression see it starts with a curly bracket and it ends with a curly bracket and each statement is followed by a semicolon so the first statement is I'm going to assign to the temporary variable。

 the values of x plus Z and then I'm going to take the log base 2 of that temporary variable plus5 and so as you remember the last thing that gets returned from this expression is the evaluation of this last statement and so what ends up happening is you this variable M will be assigned to be log base2 of x plus z plus5。

So those sorts of multi step operations can be handled very easily with data table。



![](img/26cfcb0c4412a535f619286d65eef174_43.png)

![](img/26cfcb0c4412a535f619286d65eef174_44.png)

You can also do plier like operations， so for example， we can add to this data table of variable a。

 which is greater than0 when equal to true when x is greater than 0 and false when x is less than0。

 So now we have a binary variable A that we can work with。

 So suppose we want to summarize another variable by the cases where when x is greater than0 versus the cases when x is less than0。

 So for example， we can take the mean of x plus W， and we can do it grouped by a variable A。

 And so what that's going to do is it's going to take the mean of x plus w， when a is equal to true。

 and it's going to place that mean。

![](img/26cfcb0c4412a535f619286d65eef174_46.png)

![](img/26cfcb0c4412a535f619286d65eef174_47.png)

In all the rows where a is equal to true。Then it's going to take the mean of x plus w where a is equal to false and place that mean in all the rows where a is equal to false。



![](img/26cfcb0c4412a535f619286d65eef174_49.png)

So it creates a new variable that's equal to the aggregated mean aggregated over the variable that you use by for。



![](img/26cfcb0c4412a535f619286d65eef174_51.png)

![](img/26cfcb0c4412a535f619286d65eef174_52.png)

There are some special variables in data table that allow you to do some things really fast。

 so one is dot n it's an integer linked one and it's containing the number of times that a particular group appears and so for example。

 if I create a data table that has a large number of A's， Bs and C's in it so about 100。

000 ABs and C's。Then what I can do is if I want to count the number of times each of those letters appear。

 I can use data table comma。 n and then grouped by the X variable。

 and what that'll do is it'll count do n is just count the number of times divided by grouped by the X variable。



![](img/26cfcb0c4412a535f619286d65eef174_54.png)

So it does that very fast compared to say the equivalent operation。

 which is just doing a table of Dt dollar sign X a unique aspect of data tables is that they have keys and so if you set the key。

 it's possible to subset and sort a data table much more rapidly than you would be able to do with the data frame So here I'm going to create a data table and it's going to have a variable X and it's going to have a variable Y and I'm going to set the key for the data table to be the variable X。



![](img/26cfcb0c4412a535f619286d65eef174_56.png)

![](img/26cfcb0c4412a535f619286d65eef174_57.png)

Then if I want to subset on the basis of x， or if I put in a quoted a here。

 it knows to go and look in the key and the key is x and it very quickly subsets the data to only the values of x that are equal to a。



![](img/26cfcb0c4412a535f619286d65eef174_59.png)

You can also use keys to facilitate joins between data tables， so for example。

 here I've created two data tables where they have a variable X and a variable Y。



![](img/26cfcb0c4412a535f619286d65eef174_61.png)

And in this case， the second data table has a variable Z。

And so I can set the key in both cases to be equal to x， so the same key for both data tables。

 and then I can merge them together， this is actually quite a bit faster than merging with the data frame as long as you have the same key for both operations or for both data tables it can be very fast。



![](img/26cfcb0c4412a535f619286d65eef174_63.png)

It can also be advantageous to use data tables if you want to be able to read things fast from the disk so here I've created a big data frame。

 so it's a data frame with two very large variables in it and then I set up a temporary file with this command right here and I write our big data frame out to that file。



![](img/26cfcb0c4412a535f619286d65eef174_65.png)

Then I'm going to time how long it takes to read it in using the F read command。

 the F read command can be applied to read in data tables。

 just like it's basically a drop in substitute for a read dot table with a a tab separated files。



![](img/26cfcb0c4412a535f619286d65eef174_67.png)

And so you can see it takes about 0。32 seconds if I tried to do that same operation。

 if I just tried to read do table that file， it would come in quite a bit slower well well more than 10 times slower to be able to read that file in so it's actually much faster to read files with data。

 table as well。

![](img/26cfcb0c4412a535f619286d65eef174_69.png)

To summarize data table can be both faster and more memory efficient than data frames。

 although it requires you to learn a little bit of new syntax and sometimes to be a little bit careful in terms of copying over data tables。



![](img/26cfcb0c4412a535f619286d65eef174_71.png)

![](img/26cfcb0c4412a535f619286d65eef174_72.png)

The latest developments can be found on the development version of the package which can be found at this website right here。

 they've already started to develop meltlike operations and deccast like observations for data tables and they're going to continually update that package it's a very rapidly developing package and then this website here is very nice because it gives you comprehensive ish list of all the differences between data。

 table and data frames and so that will be very useful if you're transitioning from using data frames to using data table。



![](img/26cfcb0c4412a535f619286d65eef174_74.png)

The notes that I've used today are very largely based on the notes that Raphael Guardo has put up here on GitHub。

 and they were originally from Kevin Uhi and I think that both of them deserve credit for the excellent notes that I've largely copied here for this lecture。



![](img/26cfcb0c4412a535f619286d65eef174_76.png)

![](img/26cfcb0c4412a535f619286d65eef174_77.png)