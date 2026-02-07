# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P22：21_函数的创建与应用.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/4f157a62609c92f705b7ee339db9b374_0.png)

Welcome。In this lesson， we'll be going over functions。



![](img/4f157a62609c92f705b7ee339db9b374_2.png)

So in today's agenda， we'll be talking about what are functions。Why do we use functions？



![](img/4f157a62609c92f705b7ee339db9b374_4.png)

Followed by a brief demo where you will be able to implement functions of your own。



![](img/4f157a62609c92f705b7ee339db9b374_6.png)

What are functions。Functions are modized blocks of code that can be reused in a program to perform a single related action on different pieces of the data。



![](img/4f157a62609c92f705b7ee339db9b374_8.png)

![](img/4f157a62609c92f705b7ee339db9b374_9.png)

Functions allow code to become more readable and reusable。



![](img/4f157a62609c92f705b7ee339db9b374_11.png)

In Python， we use the keyword D DEF to create a function。



![](img/4f157a62609c92f705b7ee339db9b374_13.png)

![](img/4f157a62609c92f705b7ee339db9b374_14.png)

Functions use parentheses and can take in parameters that can be used to process the data。

Return is a keyword in Python that will return the computed value in a function。



![](img/4f157a62609c92f705b7ee339db9b374_16.png)

![](img/4f157a62609c92f705b7ee339db9b374_17.png)

Why do we use functions。Well， functions can be used more than once in different parts of the program。

 which makes it extremely convenient for us， rather than writing duplicate lines of code to process data。

 functions can be called to operate on different pieces of data。



![](img/4f157a62609c92f705b7ee339db9b374_19.png)

![](img/4f157a62609c92f705b7ee339db9b374_20.png)

By using functions， you do not need to duplicate code。

 which saves memory and other programmers can understand your code better and how it works。



![](img/4f157a62609c92f705b7ee339db9b374_22.png)

![](img/4f157a62609c92f705b7ee339db9b374_23.png)

![](img/4f157a62609c92f705b7ee339db9b374_24.png)

Let's go ahead and jump into our demo。All righty。

![](img/4f157a62609c92f705b7ee339db9b374_26.png)

So in our first example， we're going to go ahead and create a program that calculates the total sales earned in a year for a pizza company。



![](img/4f157a62609c92f705b7ee339db9b374_28.png)

![](img/4f157a62609c92f705b7ee339db9b374_29.png)

We're going to implement a function that takes in two inputs the quantity sold and the price per unit。



![](img/4f157a62609c92f705b7ee339db9b374_31.png)

And finally， we're going to return the total sales for that year。

So we first create a variable called total sales and it's an energyger based variable。

 and we set it to have a value of zero， that's called initializing the value。



![](img/4f157a62609c92f705b7ee339db9b374_33.png)

Or variable， and then we create another variable called quantity。

 and we're initializing it to have a value of 200，000。



![](img/4f157a62609c92f705b7ee339db9b374_35.png)

Which is measured in units。Then we're going to create another variable called price。

 and we're going to set that variable price to have a value of 12。50， which is $12。50 per unit。

We're going to create a function called Comp annual sales。

 So here we're calling that keyword def the EF and we're。

Creating a function name called Comp An sales。And we'll pass in two parameters into the parentheses that the function needs to be able to process the data。

 Those parameters are the quantity sold and the price per unit。



![](img/4f157a62609c92f705b7ee339db9b374_37.png)

So using those two parameters that's passing into the function。

 we can compute the total sales by taking the product of the quantity sold times the price per unit。



![](img/4f157a62609c92f705b7ee339db9b374_39.png)

Finally， all we need to do is return the total sales。So here， if we print out。

 print the total sales this year are followed by dollar sign and we add the compute annual sales now keep in mind this will return an integer or a float value。

 so you want to convert it to a string， hence why we're explicitly casting it using the SCR function。

And we pass in quantity variable price variable as the parameters to the compute annual sales。

 what that is doing is we're passing 200，000， which is our quantity into the compute annual sales function。

And then we're also passing our price of 1250 into our price per unit parameter。

 What that'll do is it'll multiply 200，000 times 1250， and they'll return the total sales。

 which in this case would be 2500000 so it'll print out。



![](img/4f157a62609c92f705b7ee339db9b374_41.png)

![](img/4f157a62609c92f705b7ee339db9b374_42.png)

![](img/4f157a62609c92f705b7ee339db9b374_43.png)

Total sales this year are 2 million and500 thousand00。



![](img/4f157a62609c92f705b7ee339db9b374_45.png)

That's how useful a function is Now we can honestly just change up the values of these two variables and run this program over and over again and it'll make your life so much simpler knowing that you have a function that does all of this rather than writing duplicate lines of code that would have to compute it every single time。



![](img/4f157a62609c92f705b7ee339db9b374_47.png)

![](img/4f157a62609c92f705b7ee339db9b374_48.png)

![](img/4f157a62609c92f705b7ee339db9b374_49.png)

Okay， so in our next example。

![](img/4f157a62609c92f705b7ee339db9b374_51.png)

We have another function that determines the maximum number of two numbers given user input。



![](img/4f157a62609c92f705b7ee339db9b374_53.png)

So let's say we have a first variable user input one。

 which where the user enters the first integer after calling the input function and that's。



![](img/4f157a62609c92f705b7ee339db9b374_55.png)

![](img/4f157a62609c92f705b7ee339db9b374_56.png)

Explicitly cast as an integer because we want to make sure that both the values entered by the user are integers and no longer strings。

 hence' why we cast them and the same thing is repeated for the user input2 variable。



![](img/4f157a62609c92f705b7ee339db9b374_58.png)

![](img/4f157a62609c92f705b7ee339db9b374_59.png)

![](img/4f157a62609c92f705b7ee339db9b374_60.png)

From there define what max we create a function called maximum number and we explicitly call de。

 so our maximum number will take in two parameters， number1 and number2。

 which is just number one and number two， and we're going to check if number1 is greater than number2。

 we're going to return number1， which is the greater number。



![](img/4f157a62609c92f705b7ee339db9b374_62.png)

![](img/4f157a62609c92f705b7ee339db9b374_63.png)

![](img/4f157a62609c92f705b7ee339db9b374_64.png)

![](img/4f157a62609c92f705b7ee339db9b374_65.png)

L if number2 is greater than number1， we're going to return number2， which is a greater number。



![](img/4f157a62609c92f705b7ee339db9b374_67.png)

Finally， we're going to go ahead and print the largest number is。

 we're going to call the maximum number function， and we're going to pass in the user input that the user entered into the program。

 user input one， user input2。

![](img/4f157a62609c92f705b7ee339db9b374_69.png)

![](img/4f157a62609c92f705b7ee339db9b374_70.png)

Once they pass that into the program， then the maximum number function will be called and it'll operate on these two user inputted data and itll return what the largest number is so if the user enters one and then the user enters two for the second integer。

 then the largest number is two， that's what it's going to compute when the maximum number function is called。



![](img/4f157a62609c92f705b7ee339db9b374_72.png)

![](img/4f157a62609c92f705b7ee339db9b374_73.png)

![](img/4f157a62609c92f705b7ee339db9b374_74.png)

![](img/4f157a62609c92f705b7ee339db9b374_75.png)

![](img/4f157a62609c92f705b7ee339db9b374_76.png)

So if I were run this and let's say。I'll give another example。



![](img/4f157a62609c92f705b7ee339db9b374_78.png)

If I enter 100。

![](img/4f157a62609c92f705b7ee339db9b374_80.png)

And 2000。It will return the largest number being 2000。



![](img/4f157a62609c92f705b7ee339db9b374_82.png)

Righty， in our last example for functions， we're going to create a function that takes a list of integers and multiplies each item in the list by two。



![](img/4f157a62609c92f705b7ee339db9b374_84.png)

![](img/4f157a62609c92f705b7ee339db9b374_85.png)

![](img/4f157a62609c92f705b7ee339db9b374_86.png)

Then we're going to return the updated list values and print it to this screen。



![](img/4f157a62609c92f705b7ee339db9b374_88.png)

So list of integers in this case are one， two， three， four， and five。



![](img/4f157a62609c92f705b7ee339db9b374_90.png)

![](img/4f157a62609c92f705b7ee339db9b374_91.png)

We create our multiply by two function， which takes in one parameter called numbers。



![](img/4f157a62609c92f705b7ee339db9b374_93.png)

Here we're going to create a four loop that says for each index in the range of the total length of numbers。

 so basically what this represents is range will start from zero by default and it'll end at the length of the list so in this case one。

2，3，4，5 our list is a five elements so it'll go from  zero to5。



![](img/4f157a62609c92f705b7ee339db9b374_95.png)

![](img/4f157a62609c92f705b7ee339db9b374_96.png)

![](img/4f157a62609c92f705b7ee339db9b374_97.png)

![](img/4f157a62609c92f705b7ee339db9b374_98.png)

![](img/4f157a62609c92f705b7ee339db9b374_99.png)

So once。

![](img/4f157a62609c92f705b7ee339db9b374_101.png)

Were in our we're iterating through the list， we're going to access the value of each L index in the list by calling the numbers list and passing in the index value is equivalent to the numbers list index value times 2。

 Now what this is doing is it's accessing the index value within that list。



![](img/4f157a62609c92f705b7ee339db9b374_103.png)

![](img/4f157a62609c92f705b7ee339db9b374_104.png)

And that will give the element or the value and it'll multiply it by two。

 So in this case at let's say within our numbers list， we want index one right。

 so we start counting at zero and then we go to one。



![](img/4f157a62609c92f705b7ee339db9b374_106.png)

![](img/4f157a62609c92f705b7ee339db9b374_107.png)

![](img/4f157a62609c92f705b7ee339db9b374_108.png)

That's that at that index， it has a value of two。 So we're going to do two times 2， and basically。



![](img/4f157a62609c92f705b7ee339db9b374_110.png)

At that index， that's going to be four now。So if we were to print that out。



![](img/4f157a62609c92f705b7ee339db9b374_112.png)

And we were going to， if we call this function on our current list up here。

 what it'll do is it'll print out the newly updated list 246，810。



![](img/4f157a62609c92f705b7ee339db9b374_114.png)

![](img/4f157a62609c92f705b7ee339db9b374_115.png)

That's how useful a function is， it can perform a set of instructions and operate on a list of values rather than doing it for individual numeric values。



![](img/4f157a62609c92f705b7ee339db9b374_117.png)

![](img/4f157a62609c92f705b7ee339db9b374_118.png)

![](img/4f157a62609c92f705b7ee339db9b374_119.png)

Now， one thing I want you to know this is a little bit more advanced is that if we were to print the original list of integers。

 then you will see that it's been updated as well， it prints out 246810 now we don't want that。



![](img/4f157a62609c92f705b7ee339db9b374_121.png)

![](img/4f157a62609c92f705b7ee339db9b374_122.png)

![](img/4f157a62609c92f705b7ee339db9b374_123.png)

And the reason why that happens is the previous list gets updated too because the original list and the modified list reference both reference the original list。



![](img/4f157a62609c92f705b7ee339db9b374_125.png)

![](img/4f157a62609c92f705b7ee339db9b374_126.png)

So to solve that problem， we can use the copy function。



![](img/4f157a62609c92f705b7ee339db9b374_128.png)

Which is a pre or inbuilt function that Python has that you don't need to implement。



![](img/4f157a62609c92f705b7ee339db9b374_130.png)

![](img/4f157a62609c92f705b7ee339db9b374_131.png)

So basically， we use a copy function to solve the problem with the original list by changing it since your copy refers to a new list as opposed to the original list。



![](img/4f157a62609c92f705b7ee339db9b374_133.png)

![](img/4f157a62609c92f705b7ee339db9b374_134.png)

So let's say we create another list with the value 67，8，910。



![](img/4f157a62609c92f705b7ee339db9b374_136.png)

Now we create a variable called updatedated L which takes a copy of the original list list of integers too。



![](img/4f157a62609c92f705b7ee339db9b374_138.png)

And now if we call this function multiply by two on our newly updated list or our copied list。

 then you can see that the updated values。😊。

![](img/4f157a62609c92f705b7ee339db9b374_140.png)

![](img/4f157a62609c92f705b7ee339db9b374_141.png)

Right here。Are going to be these values multiplied by 2， which is 12， 14， 16， 18 and 20。



![](img/4f157a62609c92f705b7ee339db9b374_143.png)

And if we wanted to print our original list， we can see it's unchanged because we're not modifying our original list anymore。

 we're only modifying a copy of our original list。

![](img/4f157a62609c92f705b7ee339db9b374_145.png)

![](img/4f157a62609c92f705b7ee339db9b374_146.png)

So our original list was 678910 and our problem is solved。



![](img/4f157a62609c92f705b7ee339db9b374_148.png)

Thank you for watching。

![](img/4f157a62609c92f705b7ee339db9b374_150.png)