# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p51 P51 04_清理数据框的字符串列 -BV1z86nB9EGz_p51-

![](img/08979f6f388badcb158c7bd5df434f38_0.png)

In this video， I'm going to demonstrate some useful approaches for manipulating and cleaning data frame columns that have an object data type。

 which is the same thing as a string or a character string data type。Now， hopefully at this point。

 you have a pretty good idea for how to type out code。

 and you're familiar with the very helpful pop up menus that appear as you're typing out the code。

 so you don't have to remember everything。Because of that。

 rather than watch me type out the code at this point。

 I'm mostly going to just run code that I have already written。

 and then we can evaluate the output together。 So in this Jupiter lab environment。

 I have created a simple data frame that has two columns， name and category。And both of these。

 as you can see， are character string columns or object columns。 Now。

 there are some things about the data in these columns that need to be cleaned up。

 so you can see that we've got inconsistent capitalization in both of these columns。

 And one thing that you can't see， but you can see if I show you up here where I created it is that we've got leading and trailing white space in the data。



![](img/08979f6f388badcb158c7bd5df434f38_2.png)

![](img/08979f6f388badcb158c7bd5df434f38_3.png)

All right， now before we talk about cleaning the data。

 let me just show you something that's really useful。

 which is combining character strings together either from different columns of data or from a string that you want to add in to every observation in the data。

So to combine strings together。From two different columns， we can simply。

Create a new column by typing out the data frame， and then in square brackets and parentheses。

 the new column name。And then we'll set that equal to the data frame and then the dot and then the name of each of the columns and then just put a plus in between it。

 Okay， just like you would add strings together， even if they're not in a data frame。

 So let's go ahead and run that code cell and you can see that I've got this new column name underscore cat that combines the data from these two columns。

 All right， now， if you just want to add a fixed string to every observation of a column that is already an object or character string column。

 Then you can do something very similar， it's just we add the string right after the plus rather than typing out the data frame name。

 All right， so in this case， I'm going to put underscore wrong after each value in the name column。

And call that a new column name underscore owner。 So I'll run that。

 and you can see that name underscore owner I've got。



![](img/08979f6f388badcb158c7bd5df434f38_5.png)

![](img/08979f6f388badcb158c7bd5df434f38_6.png)

That underscore run after everything。 Okay， so that's an important thing to know how to do。

 Let's now talk about cleaning the string columns of a data frame。

 And we'll start by talking about how to change the case。

 So whether it's capitalized or lowercase or title case。 Now。

 a key thing to remember with all of these string columns is that you can access their functionality by using this dot SR accessor in there。



![](img/08979f6f388badcb158c7bd5df434f38_8.png)

So to demonstrate this， let's say I want to create or convert the columns in the category columns so that they're all lowercase。

 This is something that we often want to do if we're evaluating the text or just analyzing topics。

In the data or seeing if there are matching values。

 and we don't care about whether it's capitalized or not。

So the way we can do that is type out the data frame in the name。

 And then we'll use that dot STR accessor for string。

 And then there will be a lot of different methods available to you。 So let's say， for instance。

 I don't have that typed out。 I'll just hit period。

 And you can see that there's capitalized caseful cat and so on。 And we just want the lower one。

 And it's a function。 So we'll add the open closed parentheses。



![](img/08979f6f388badcb158c7bd5df434f38_10.png)

All right。 when we run that， you can see now that category is all lowercase in there。



![](img/08979f6f388badcb158c7bd5df434f38_12.png)

All right。 So pretty easy。 Let's talk about removing leading and trailing white space。

 Sometimes this is going to be the bane of your existence because you don't know that there is leading your trailing white space。

 When you try to match values from different columns。

 it may not match if there' is that leading and trailing white space。

 So it's a good idea to check for this。

![](img/08979f6f388badcb158c7bd5df434f38_14.png)

You can't usually see it when you visually explore a data frame。

 So there are a couple of ways that you can see it or verify that it exists。

 And that is to just type out the individual column of the data frame that may have leading in trailing white space。

 So D F dot name， you can see that I've got some space in there。



![](img/08979f6f388badcb158c7bd5df434f38_16.png)

![](img/08979f6f388badcb158c7bd5df434f38_17.png)

Or I just。Comment that out and uncome out this other approach where I can use the Lo method and indicate the row and column names。

 I'm just going to get a single value。 So I get this ball value from right here。

 And from the quotation marks， I can now tell that there is leading and trailing white space in there。



![](img/08979f6f388badcb158c7bd5df434f38_19.png)

![](img/08979f6f388badcb158c7bd5df434f38_20.png)

All right， so to deal with that， we can use the strip method。

So what I'm going to do is I'm going to re save this cleaned column as itself。

 and I'm going to first convert it to all lowercase。

And then I'm going to use the dot STR accessor again， and then this dot strip function。Or method。

 And when I run that。You can see that everything is lowercased。

You can't tell that I've removed the leading and trailing white space。

 but if I just print out the name of that column again。

 you can now see that there is no trailing white space。

 at least Another cool thing to point out here is that you can just chain methods together。 Okay。

 so let's talk about how we can subset string columns。 and I'm going show different examples here。

 So I've commented out some lines of code。 But the first example I'm going to show is how we can create a new column name sub and set that equal to the first six characters of the name column。

 So if I run this。😊。

![](img/08979f6f388badcb158c7bd5df434f38_22.png)

Then you can see for comes that don't have six characters in it， just reports all of them。

But for these last two， it's just reporting the first six characters， including spaces。 All right。

 So you can see those six there and those six there。



![](img/08979f6f388badcb158c7bd5df434f38_24.png)

All right， I'm going to comment that line out now and uncomment out the next line。

And I just want to highlight that we can access characters starting at any position in here。

 So I want to start with the second character and go up to the third character。 So if I run that。Now。

 you can see I'm getting just the A and the L from ball， the A and the T from bat and。

 and so on in there。And one other demonstration。Is， I'm gonna。

Comment out that second line now and uncomment out the last line of code here。

 And I can start from the right hand side。 So if I want the last six characters。

 then I can say negative 6 colon。 And then if I leave it blank to the end。

 it'll just go all the way to the end。Alright， so if I do that。

 you can see I've got ball and bat again。 but for these last two rows。

 I've got the last six characters。 So S E E， B A L L and N D space， B A。Al right。

 so that's how you can subset string columns by using just the index location of the characters in that column。

 So there's a few other methods that I want to highlight that are very useful for string columns。



![](img/08979f6f388badcb158c7bd5df434f38_26.png)

Let's evaluate whether a string contains a substr。So let's create a new column name underscore ball and evaluate whether a string contains ball anywhere in it。

 So if I run this， you can see that I get this new column that's true， false， true， true。

 So you can see for the second row， It's false because ball is nowhere in that name。



![](img/08979f6f388badcb158c7bd5df434f38_28.png)

![](img/08979f6f388badcb158c7bd5df434f38_29.png)

Whereas for the first， third and fourth throws， we've got balls somewhere in there。



![](img/08979f6f388badcb158c7bd5df434f38_31.png)

Okay， so that can be really useful。What if you want to replace a substr with something else。

 Oftentimes with nothing， you just want to remove it。 I can use the replace method。 Okay。

 so I'm going to type out the data frame， the column name， then the string accessor。

 Then I'm going to use this replace method。

![](img/08979f6f388badcb158c7bd5df434f38_33.png)

![](img/08979f6f388badcb158c7bd5df434f38_34.png)

And the first argument is the substr that you're looking for。

 and then the last argument is what you want to replace it with。



![](img/08979f6f388badcb158c7bd5df434f38_36.png)

So let's go ahead and run this。And now you can see in this last column here。

 I'm going to remove ball from each row in here。 So now the first row has nothing in it。

 The second row is unchanged， but the third and fourth rows now have that ball removed from。

 All right， let's say I want to split the values of a string into multiple columns。

 I can use the split method。 So let me just illustrate how this split method works。 I'm going。



![](img/08979f6f388badcb158c7bd5df434f38_38.png)

Refer to the data frame， the column name， and then the dot string accessor， and then the split。

 And what I want to do is in this argument here， as I'm indicating what I want to split on。

 So if I want to split on a space， then I just type out quotation marks with a space in there。



![](img/08979f6f388badcb158c7bd5df434f38_40.png)

And you can see that it's going to take ball and not split it bad and won't split it it either。



![](img/08979f6f388badcb158c7bd5df434f38_42.png)

But these last two rows， I'm going to split into three different components。

 So I've got lists here that have three components split by the space。 Okay。

 so hat and baseball and ball and bat。 I wanted to split by something else like the letter A。



![](img/08979f6f388badcb158c7bd5df434f38_44.png)

Then I could do that。 And now every one of those columns is divided into a list with multiple parts in it。

 And you can see that the value that is being split on is not included in there。

 So you might be wondering， why would I want to use this split method。Well。

 you may have a situation where you want to divide a column into multiple columns。



![](img/08979f6f388badcb158c7bd5df434f38_46.png)

And to do that， we can do something like this。 We can type out the data frame name and then two sets of square brackets。

 So we're going to create a list here。And then the name of each of the three columns。Alright。

 so this is nice。 I can define each of those names in a single expression right there。And then。

 I'm going use the。The column or the data frame， the column name， the string accessor。

 the split method。 What I want to split on。And when you don't have the same number of splits in every column。

 you need to include this expand equals true。 And if you do that， then you'll get a good result。

 name  one， name  two， name 3。

![](img/08979f6f388badcb158c7bd5df434f38_48.png)

![](img/08979f6f388badcb158c7bd5df434f38_49.png)

And if there's only one string in there， it's not going to split it into three different substrs。

 Then it'll just put none in theirs， Okay， so。These last two rows have strings in each of those。

 but the first two do not。

![](img/08979f6f388badcb158c7bd5df434f38_51.png)

The last thing I want to introduce you to are regular expressions。

 and regular expressions are really helpful when you want to search for specific patterns。

 So let's say I want to remove everything up to the last space that is observed for every row in my data for a specific column。

 Let me just go ahead and run this and we'll talk about it。So I've created a new column named Regg。



![](img/08979f6f388badcb158c7bd5df434f38_53.png)

And in here， I have used this replace method， but rather than replacing for a an exact value。

 I'm using this regular expression notation。 Now regular expression notation takes a little bit of time to understand。

 but there's a lot of tools that you can use to help you out with it。



![](img/08979f6f388badcb158c7bd5df434f38_55.png)

Just as an example here， what I'm doing is I'm starting at the beginning of the string。

 so first character。And then this period is like a wild card ats saying。

 doesn't matter what character we see after that。Identify it。

 Then the star means as many times as it appears。 Okay， so any character。Up to a space。

And including the space。 And then I can indicate what I want to replace it with。

 and I'm going to replace it with new first word and then a space in there。

And then I have to make sure to include this argument。 Regg X equals true。 Okay。

 so by including that and running it， you can see that third and fourth rows。

 everything up to the last space has been replaced with new first word and then a space。



![](img/08979f6f388badcb158c7bd5df434f38_57.png)

Okay， so hat and and then the space are replaced。 then ball and and the space are replaced again with new first work。

 So most of the time， I use this just to remove elements from a string。 But anyway。

 that's an introduction to regular expressions。 They can be really powerful。 Now。

 this isn't an exhaustive list of things that you can do with string columns。

 But I think these are some of the most important and most frequently use tasks that I perform when cleaning string columns of a data frame。

 Again， you can look up how to use these things。 So you don't have to remember them。

 But I hope that by watching me go through them。 you have a better understanding of the principles and for how to work with data that is stored in a panda's data frame。



![](img/08979f6f388badcb158c7bd5df434f38_59.png)

![](img/08979f6f388badcb158c7bd5df434f38_60.png)

![](img/08979f6f388badcb158c7bd5df434f38_61.png)