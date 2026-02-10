# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P19：18_条件控制循环（while）构建.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/095ec7319324d6904e446940a0879b5c_0.png)

Welcome。In this lesson， we'll be going over while loops。



![](img/095ec7319324d6904e446940a0879b5c_2.png)

In today's agenda， we'll be going over what are while loops。

 and we'll also go over a demo where you'll be able to implement your own while loops in Python。



![](img/095ec7319324d6904e446940a0879b5c_4.png)

![](img/095ec7319324d6904e446940a0879b5c_5.png)

So what are while loops while loops are utilized to execute a set of instructions or lines of code repeatedly as long as the specified condition is met。

When the wild condition is false， the while loop stops executing；

 if the wild condition is never true， the while loop never executes。



![](img/095ec7319324d6904e446940a0879b5c_7.png)

Go ahead and move on to our demo right here。So you can see right over here in this first example。

 we create a program that counts the number of iterations to 10， starting at zero。

 so we create an integer variable called count and we set its value to be0。



![](img/095ec7319324d6904e446940a0879b5c_9.png)

![](img/095ec7319324d6904e446940a0879b5c_10.png)

![](img/095ec7319324d6904e446940a0879b5c_11.png)

Now while the count， our condition is while the count is less than 10， we're going to print count is。

 and then we're going to output the value count， and then we're going to go ahead and increment count by one。



![](img/095ec7319324d6904e446940a0879b5c_13.png)

![](img/095ec7319324d6904e446940a0879b5c_14.png)

![](img/095ec7319324d6904e446940a0879b5c_15.png)

So what happens is while the value of count is less than 10。

 we're going to execute these two lines of code。

![](img/095ec7319324d6904e446940a0879b5c_17.png)

![](img/095ec7319324d6904e446940a0879b5c_18.png)

Once。Count is greater than or equal to the value of 10。

 then this while loop will break and the program will stop running。



![](img/095ec7319324d6904e446940a0879b5c_20.png)

![](img/095ec7319324d6904e446940a0879b5c_21.png)

So here you can see that when we run it， it'll print out count as 0 all the way to count as 9。

 And as soon as it gets to。

![](img/095ec7319324d6904e446940a0879b5c_23.png)

![](img/095ec7319324d6904e446940a0879b5c_24.png)

Count is equal to 10， it'll check count is while 10 is less than 10， which is false。



![](img/095ec7319324d6904e446940a0879b5c_26.png)

Then the program breaks and it won't execute these two lines of code。



![](img/095ec7319324d6904e446940a0879b5c_28.png)

![](img/095ec7319324d6904e446940a0879b5c_29.png)

In our next example for this Y loop， we're going to create a program that counts the number of iterations to 10 while incrementing by  two。



![](img/095ec7319324d6904e446940a0879b5c_31.png)

![](img/095ec7319324d6904e446940a0879b5c_32.png)

So let's create another we've created another variable count2， and we set that to the value of zero。



![](img/095ec7319324d6904e446940a0879b5c_34.png)

Now we're checking， our condition is wild count2 is less than 10。



![](img/095ec7319324d6904e446940a0879b5c_36.png)

Then we're going to print， count2。

![](img/095ec7319324d6904e446940a0879b5c_38.png)

And we're going to increment count two by two。 This is a common way of incrementing。 by the way。

 it's the same thing as writing。

![](img/095ec7319324d6904e446940a0879b5c_40.png)

Count。Underscore2 is equivalent to。Count underscore 2 plus2。 It's。

 it's the same way as writing this expression， but just much more quickly because you're just using this。



![](img/095ec7319324d6904e446940a0879b5c_42.png)

![](img/095ec7319324d6904e446940a0879b5c_43.png)

![](img/095ec7319324d6904e446940a0879b5c_44.png)

Notation plus equals， so we don't need this。

![](img/095ec7319324d6904e446940a0879b5c_46.png)

So you can check so as long as count as a condition is met。

 as long as count2 is less than 10 once count2 is greater than or equal to 10。

 this while statement will break and the program completes so you can see that when I run it。



![](img/095ec7319324d6904e446940a0879b5c_48.png)

![](img/095ec7319324d6904e446940a0879b5c_49.png)

![](img/095ec7319324d6904e446940a0879b5c_50.png)

Give me a second。

![](img/095ec7319324d6904e446940a0879b5c_52.png)

It'll print out zero，2，4，6，8。

![](img/095ec7319324d6904e446940a0879b5c_54.png)

The next iteration itll be count2 will be 10 when it's 8 and when it's。



![](img/095ec7319324d6904e446940a0879b5c_56.png)

10 is 10 less than 10， no it's not， hence the condition is false。

 therefore these two statements won't execute and the program comes to an end。



![](img/095ec7319324d6904e446940a0879b5c_58.png)

![](img/095ec7319324d6904e446940a0879b5c_59.png)

Now in this next example right here， we have an example of an infinite loop。



![](img/095ec7319324d6904e446940a0879b5c_61.png)

So we're saying while true。

![](img/095ec7319324d6904e446940a0879b5c_63.png)

Our condition is true。 We're printing infinite loop。 Now， notice here we're not。



![](img/095ec7319324d6904e446940a0879b5c_65.png)

Ever adjusting the condition to be false whenever telling the while loop， when should it stop？



![](img/095ec7319324d6904e446940a0879b5c_67.png)

![](img/095ec7319324d6904e446940a0879b5c_68.png)

So as long as this condition is true， the statements within that while loop will keep executing and it'll never stop until the entire program crashes。

 so essentially you always want to make sure that when you're running your code unless specified to do so。

 make sure you terminate the while loop just by specifying when the condition should be false。



![](img/095ec7319324d6904e446940a0879b5c_70.png)

![](img/095ec7319324d6904e446940a0879b5c_71.png)

![](img/095ec7319324d6904e446940a0879b5c_72.png)

![](img/095ec7319324d6904e446940a0879b5c_73.png)

If the program requires an infinite loop， you can go ahead and specify it to have a true condition and it'll constantly execute all the lines of code in that program。



![](img/095ec7319324d6904e446940a0879b5c_75.png)

![](img/095ec7319324d6904e446940a0879b5c_76.png)

You can see when I run it， it'll just print out infinite loop constantly over and over and over again until you have to click the stop button or you click the stop button and it'll stop the program for you。



![](img/095ec7319324d6904e446940a0879b5c_78.png)

![](img/095ec7319324d6904e446940a0879b5c_79.png)

Okay， there is one more example we're going to be going over in this lesson。

 we'll be going over a while loop and an L now one of the cool things about the while loop is that you can include an L statement within it or for a while loop as well。

So in this example， we're going to create a machine or create a program that simulates a washing machine lock。

If a break is inserted in the loop， the L statement will not execute since the condition was not completed naturally。

 and you'll understand what I mean to say in just a second。

The al statement will only execute as long as the condition breaks naturally。

 so there is no break statement the condition is met and satisfied without any interruptions。

So here we go。 We create a variable called Mach on and we set that to be true。

 That's a Boolean variable。 We create another Boolean variable called door locked and we set that to have a value of true。

Now we create an integer variable called time limit count， which is set to one。

We have another variable integer variable called rotation per minute， and we set that to zero。Here。

We're creating a time limit variable that prompts the user to enter our time limit for the load that the machine should wash the clothes for。

After the user has input their time limit。We're storing that value into a time remaining variable。

 and you'll see why in just a second。So here we have our while loop while our door is locked。

And the machine is on， and the time remaining is greater than 0。 We're going to perform these。

These following statements， as long as this while statements condition is true。

 if any one of these are false， then the while loop will stop executing and they'll run the L statement。

So here you can see that when we're running it。When we're running it。

And it executes until the time remaining is zero once the time remaining is zero。

 then the program will come to an end as this condition is false and the L statement will then execute where it'll say machine powering down as you can see here。

Keep in mind I didn't include the brake statement in this run and the reason why is because I want the program to execute naturally。

 if I include the brake statement， it'll end abruptly and the program will not end naturally and once that is included this L statement will never run and you'll see that in just a second。

But as of right now， you can see that the user has inputted a time limit of 20 when prompted。

 so when the program is run。It'll check is the door locked， yes， and is the machine on true。

 and is the time remaining greater than zero， that is also true。

 so then it'll then increment the rotation per minute by5hi for every single iteration through the loop。

And it'll subtract the amount of time remaining。 So itll。

 which is 20 minutes minus the time limit count， which is set to a constant of one。

 So we're going to constantly subtract one minute per iteration There's5。And finally。

 we'll print the time remaining with the time remaining variable and we'll have a strain that says the number of minutes left。

Which you can see here。

![](img/095ec7319324d6904e446940a0879b5c_81.png)

Finally， itll once this statement once this condition is false。

 it'll print out this else and it'll print machine powering down and it'll finally execute the last print statement which has the number of cycles executed and with the rotation permit menu Now let's see what happens when I include the brake statement。



![](img/095ec7319324d6904e446940a0879b5c_83.png)

So if I include the brake statement and I run this。

And let's say I want to do it for 20 minutes again。

Now you can see that it'll only execute once because we're telling the program to exit the while loop immediately after the first iteration。

So you can see that the time remaining is 19 minutes left and the number of cycles executed。

 this only gets executed once， which is why the rotations per minute is five。

Once that break hits that break， this Y loop is exited。

 and since we have an unnatural due to this break statement， we have an unnatural end to the program。

 so this L statement will never execute。And it'll finally just enter the last line of the program。

 which is the number of cycles executed， followed by the variable rotations per minute。

That's how the while loop and an L statement work together。Thank you for watching。

