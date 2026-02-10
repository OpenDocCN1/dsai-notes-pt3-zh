# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P20：19_计数控制循环（for）构建.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/cd35fe433fdb17fb80a98ed1eb324517_0.png)

Welcome， in this lesson we'll be going over four loops and lists。



![](img/cd35fe433fdb17fb80a98ed1eb324517_2.png)

So we'll be talking a little bit about what are for loops， what are lists。

 and then finally we'll get to the implementation where you'll be able to create your own for loops and your own lists。



![](img/cd35fe433fdb17fb80a98ed1eb324517_4.png)

So what are four loops， four loops are utilized for sequential traversal。

 they are loops that are utilized for this purpose。



![](img/cd35fe433fdb17fb80a98ed1eb324517_6.png)

F loops can iterate over a range of values。Python allows the L keyword to be used with four and wire loops as we've seen before。

The ELS block can be used after the body of the loop and the statements in the ElL block is executed after all iterations have completed in the loop。



![](img/cd35fe433fdb17fb80a98ed1eb324517_8.png)

What are lists。So just so you know， more on this would be covered in course2。But as of right now。

 we'll be going over the basic concept。Lists are data structures that are mutable。

Ordered sequence of items， which consist of values or elements。List can be indexed。

 meaning you can access each element or value in a list based on its index value。

Ls can have items or different data types and can also have items of the same data type。

 that's what makes it so powerful。To create a list， all you need to do is use the square brackets。



![](img/cd35fe433fdb17fb80a98ed1eb324517_10.png)

Let's jump to our demo。Okay。So。In this script， you can see that I have first created a for loop where I've specified the number of iterations I want this for loop to perform are 22。

 which is why I created a variable n， which is set to 22。



![](img/cd35fe433fdb17fb80a98ed1eb324517_12.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_13.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_14.png)

Now I create the for loop， so for every index in the range0 to n。

 we're going to print what the index is。

![](img/cd35fe433fdb17fb80a98ed1eb324517_16.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_17.png)

Now keep in mind， when we are using the range function。

 what we are saying is basically we want for every integer or every index in this range from 0 to 22。

 we want to print this out， but when we're using range you have to understand that range will print out from the starting index to the n minus1 index。

 so it'll start at zero and it'll iterate all the way till 21。



![](img/cd35fe433fdb17fb80a98ed1eb324517_19.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_20.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_21.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_22.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_23.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_24.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_25.png)

That's something that you always want to make sure you keep in mind moving forward so when we start counting from 0 and we're going to 21 we still have 22 integer values we are working with it's just that we're starting from zero and we're going to n minus1 element。



![](img/cd35fe433fdb17fb80a98ed1eb324517_27.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_28.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_29.png)

So here you can see that。I'm printing out every single index by starting from zero and finishing at 21 because it's the n minus1 value of the 22 minus1 index。

 which is 21。

![](img/cd35fe433fdb17fb80a98ed1eb324517_31.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_32.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_33.png)

Moving to the next example。So here's another example that I'll explain why I mentioned before。



![](img/cd35fe433fdb17fb80a98ed1eb324517_35.png)

So let's say I want to iterate from the integer value 5 to 11。



![](img/cd35fe433fdb17fb80a98ed1eb324517_37.png)

So what I can say is for some integer I or some variable I in the in range 5 to 12 print the index value。

 so what this will do is it'll say for every index I in the range 5 to 12。

 so 5 to 12 minus1 because it's keep in mind we're accessing the value of the n minus1 element。



![](img/cd35fe433fdb17fb80a98ed1eb324517_39.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_40.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_41.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_42.png)

We want to print index I。 so I'll print 5，6，7，8，9，10，11。 Now， if we want to include 12。



![](img/cd35fe433fdb17fb80a98ed1eb324517_44.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_45.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_46.png)

All we would need to do is just increment this by one because we're accessing the n minus1 element。

 so we have to increment 12 to 13 Now if I were to run this。



![](img/cd35fe433fdb17fb80a98ed1eb324517_48.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_49.png)

You can see here， the index values are 567-8910，11，12， 12 is now included。



![](img/cd35fe433fdb17fb80a98ed1eb324517_51.png)

Okay。Now let's go ahead and iterate through a list of fruits， as I mentioned before。

 a list is a data structure that you can pass values to。Here in our list we have values of strings。

Where we have a string of apples， a string oranges， a string bananas， and a string grapes。



![](img/cd35fe433fdb17fb80a98ed1eb324517_53.png)

In our for loop， we're saying for every fruit in the list of fruits。



![](img/cd35fe433fdb17fb80a98ed1eb324517_55.png)

We want to print the fruit purchased is， and then it's going to we're going to access that fruit。

 So in this case， the fruit purchase is app are apples。 The fruit purchased are oranges。

 It's going to print this out for every single element in the list。

 That's what loops are so useful for rather than having to access every single element within this list and write a print statement。



![](img/cd35fe433fdb17fb80a98ed1eb324517_57.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_58.png)

A total of one， two， three， four times， or even more if you have a much larger list。

 you can just utilize a for loop that basically in two lines of code will go through every single element in the list and print it out for you rather than writing so many lines of code that do the same thing。



![](img/cd35fe433fdb17fb80a98ed1eb324517_60.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_61.png)

That's why loops are so powerful， they can help you save time， avoid writing duplicate lines of code。

 and just write a more stronger optimal program。

![](img/cd35fe433fdb17fb80a98ed1eb324517_63.png)

![](img/cd35fe433fdb17fb80a98ed1eb324517_64.png)

Thank you for watching。