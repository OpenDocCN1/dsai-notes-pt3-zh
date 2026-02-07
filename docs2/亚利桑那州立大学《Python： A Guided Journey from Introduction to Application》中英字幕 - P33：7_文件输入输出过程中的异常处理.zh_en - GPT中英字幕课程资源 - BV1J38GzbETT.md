# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P33：7_文件输入输出过程中的异常处理.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/d901016903a1bbb0caeb320d9a3167f1_0.png)

Welcome everyone， today we're going to talk about using exceptions in this demo and like we said before。

 mainly what you want to do is you want to try to use a try catchch statement to catch as many of your errors or possible errors that could occur in your application that way it doesn't cause the application to crash on its own。



![](img/d901016903a1bbb0caeb320d9a3167f1_2.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_3.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_4.png)

So one of the most common ones that you end up getting is what they refer to as a divide by zero。

 a user inputs data， and then when they divide that denominator is zero and most times it crashes the program。



![](img/d901016903a1bbb0caeb320d9a3167f1_6.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_7.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_8.png)

And so to do this， what we can do is we can use a try catch statement。



![](img/d901016903a1bbb0caeb320d9a3167f1_10.png)

So as you can see here， I'm going to try， I'm going to print this value 14 divided by zero。



![](img/d901016903a1bbb0caeb320d9a3167f1_12.png)

If I take this out。

![](img/d901016903a1bbb0caeb320d9a3167f1_14.png)

没有。Now， if I try to run this。

![](img/d901016903a1bbb0caeb320d9a3167f1_16.png)

Notice what happens， notice the program crashes and when it crashed。

 I get the divide zero division error。

![](img/d901016903a1bbb0caeb320d9a3167f1_18.png)

Division by  zero。

![](img/d901016903a1bbb0caeb320d9a3167f1_20.png)

But my application itself crashed。And sometimes we don't want that to happen。 So again。

 we want to try to use。

![](img/d901016903a1bbb0caeb320d9a3167f1_22.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_23.png)

I try catch statement。And so now if I run this， notice here my application exited successfully。

 there was no crashing in this。

![](img/d901016903a1bbb0caeb320d9a3167f1_25.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_26.png)

Process， what it did do is it said that I tried this program。 There was an error in it。

 And then I said the exception， the zero division error。



![](img/d901016903a1bbb0caeb320d9a3167f1_28.png)

Then I just printed out a message you can't divide by zero。



![](img/d901016903a1bbb0caeb320d9a3167f1_30.png)

And I displayed that out to the screen that saved me from having to do that。

 Another area that most commonly that you would want to use this is when you're trying to open a file。



![](img/d901016903a1bbb0caeb320d9a3167f1_32.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_33.png)

As you can see here from this example。

![](img/d901016903a1bbb0caeb320d9a3167f1_35.png)

I'm opening a file。 Can't find my file dot text。 I'm doing it as a re。

 If I go over here to my file list， I can look in here。 there's no file of that name。



![](img/d901016903a1bbb0caeb320d9a3167f1_37.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_38.png)

This is going to cause my application to crash。

![](img/d901016903a1bbb0caeb320d9a3167f1_40.png)

And so in this case， I'm going to get an I error。 And so what I wanted to do is I wanted to display that there was an error that had occurred。

 and then I wanted to display what that error message was。



![](img/d901016903a1bbb0caeb320d9a3167f1_42.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_43.png)

So if I run this real quick， as you can see， I got an error message occurred。

 and it gave me no such file in the directory。 Can't find my file。



![](img/d901016903a1bbb0caeb320d9a3167f1_45.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_46.png)

Now， let's go and take a look at another example instead of writing to a file， let's try to。

 I mean reading from a file， let's go and try to write to a file。



![](img/d901016903a1bbb0caeb320d9a3167f1_48.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_49.png)

And if I do that。In this example。

![](img/d901016903a1bbb0caeb320d9a3167f1_51.png)

I've got。Create a new file dot text。 I'm doing it right。 Welcome to Python。

 and then I've got my exception。 The error occurred， just like before。



![](img/d901016903a1bbb0caeb320d9a3167f1_53.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_54.png)

Now this time I don't expect that there will be a problem。

 the reason why is because I'm actually writing to the file， so I'm going to create that。



![](img/d901016903a1bbb0caeb320d9a3167f1_56.png)

Now。

![](img/d901016903a1bbb0caeb320d9a3167f1_58.png)

There is a thing called finally。 Finally means that。No matter if it succeeded or failed。



![](img/d901016903a1bbb0caeb320d9a3167f1_60.png)

Basically， this statement will print。 It's the final statement after the application。



![](img/d901016903a1bbb0caeb320d9a3167f1_62.png)

So if I go and run this。

![](img/d901016903a1bbb0caeb320d9a3167f1_64.png)

It says closing the file now。

![](img/d901016903a1bbb0caeb320d9a3167f1_66.png)

If I come over here and I look。I've got that file that was created， if I double click on it。

 it says welcomelcome to Python in that file。

![](img/d901016903a1bbb0caeb320d9a3167f1_68.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_69.png)

So as you can see here， that worked just well for me。And then， of course。

 my last one that I want to do is。

![](img/d901016903a1bbb0caeb320d9a3167f1_71.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_72.png)

One more example， where。I'm using a for loop， this for loop is going to go through each one of the elements in an array。

 notice I have different data types， I have a variable。



![](img/d901016903a1bbb0caeb320d9a3167f1_74.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_75.png)

Which is an a。 I have 0， and then I have2。

![](img/d901016903a1bbb0caeb320d9a3167f1_77.png)

Now， in this for loop， basically I'm going to go through each of one of these items and I have one divided by my ant value and item。



![](img/d901016903a1bbb0caeb320d9a3167f1_79.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_80.png)

Now my item。

![](img/d901016903a1bbb0caeb320d9a3167f1_82.png)

In this case， is going to be one of these three elements。Now， as you're looking at this， we can say。

 okay， well， A is not going to work for this， obviously。



![](img/d901016903a1bbb0caeb320d9a3167f1_84.png)

Because it's a character， we also know that zero won't work because we're going to do a divide by zero error。



![](img/d901016903a1bbb0caeb320d9a3167f1_86.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_87.png)

And then we're going to do two。So in this case here， in the other examples。

 I've specified kind of what my exception was。

![](img/d901016903a1bbb0caeb320d9a3167f1_89.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_90.png)

In this case here， what I'm going to do is I'm just going to do my exception。

And then use my systemsem。X info to get that information of what type of error had occurred。



![](img/d901016903a1bbb0caeb320d9a3167f1_92.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_93.png)

So let's go ahead and take a look at this example。

![](img/d901016903a1bbb0caeb320d9a3167f1_95.png)

Notice in the first one， oops。A value error， meaning that I put in an A instead of a actual number。



![](img/d901016903a1bbb0caeb320d9a3167f1_97.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_98.png)

The second one， oops。Division by zero error。

![](img/d901016903a1bbb0caeb320d9a3167f1_100.png)

Of course， the last element， which was two。 as I ran that through， the entry is a2。

 The reciprocal of 2 is 0。05。

![](img/d901016903a1bbb0caeb320d9a3167f1_102.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_103.png)

This is an example of how you can run the application without a crashing and still have it succeed in completing its tasks。



![](img/d901016903a1bbb0caeb320d9a3167f1_105.png)

![](img/d901016903a1bbb0caeb320d9a3167f1_106.png)

Thank you。 Look forward to seeing you in the next video。

