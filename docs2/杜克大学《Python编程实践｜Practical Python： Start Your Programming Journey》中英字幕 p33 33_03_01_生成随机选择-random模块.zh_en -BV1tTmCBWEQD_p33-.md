# 杜克大学《Python编程实践｜Practical Python： Start Your Programming Journey》中英字幕 p33 33_03_01_生成随机选择-random模块.zh_en -BV1tTmCBWEQD_p33-

![](img/4985897f7b917ec2888d066aa2dd7bd3_0.png)

![](img/4985897f7b917ec2888d066aa2dd7bd3_1.png)

Suppose you are playing a video game and you're controlling a person named Terry。

Terry is supposed to avoid a cat that turns slightly either left or right， before jumping forward。

Your task is to move Terry either left or right at the same time and hopefully avoid the cat。

What if the cat always turns in the same direction every time you play the game。

Suppose it always turns to the right before jumping。The game wouldn't be much fun。The second。

 the third time you play， as you already know what the ca is going to do。Each time you play。

 you just move Terry to Terry's right。 and the cat misses Terry。That is not much fun。

The game would be more interesting and more challenging if the cat's movements were unpredictable。

Meaning the cat moves in a random direction each time you play。Sometimes the cat misses。

 and sometimes the cat gets tear。A simpler example of randomness is flipping a coin and making a decision based on which side of the coin is facing up。

Suppose we have a US quarter。That has George Washington the first US president on one side。

The other side could be many different things。In this case， we have Ellis Island， New Jersey。

 on the other side。You are trying to decide if you should go for a walk today。

So you decide to flip the coin up in the air。When it lands on the ground。

 if the with George Washington's face is facing up， you go in a walk。

And if the side with Ellis Island is facing up。You do not go on a walk today。Looks like it is heads。

 So you're going on a walk today。How do we write Python code to make this decision。

There is no coin flipping in Python。But Python does have a way to generate random numbers in a specified range。

Randomly generating the number one or two is essentially the same as flipping a coin。

If one is randomly generated。Then that would be the same as the quarter's side with George Washington's。

Facing up。And we can go for a walk。But if instant 2 is generated。

 then that will be the same as the quarter side with Ellis Island facing up。

And we don't go for a walk。Python generates random numbers with the Python library random module。

What is that？Well。In the real world， a library is typically thought of as a place to borrow books。

You check out a book that someone has written。 You read it。

And then you bring the book back to the library。A Python library is a place to borrow code。

 called modules。A module is like a book。But it's really a file with a lot of code that is related。

A module typically has functions in it that you can use in your program。

Using functions from a library module that someone else has written the code for will save you time in writing your program。

How do you access a library module？You access it by using an import statement。

You use the word import。Followed by the name of the module。

The import statement goes at the top of your program。Then anywhere below the import statement。

 you can use any function from that module。So how do you access a function from a module？

You have to give the modules name first。Followed by a dot。And then， followed by the function name。

Left parentheses。Any values that the function needs， we call those arguments。And finally。

 the right parentheses。Here's an example。In line1， the code imports the random model。

That means we can now use any function from the random module。In line 2。

 the code caused the random end function from the random module to generate a number that is either the integer 1 or 2。

Notice the word random。For the random module followed by the dot。

 followed by the random int function， followed by the values 1 and 2。

 meaning generate an integer from  one to 2。And finally， followed by the right parentheses。

Before we look at the random module in more detail。

 let's talk more about the buildin functions in Python。



![](img/4985897f7b917ec2888d066aa2dd7bd3_3.png)

That we have already been using。A built in function is already in Python。

 and we can just use the function。We don't need to import a module in order to use built in functions。

Since we don't import a module， there is no module name in front of the function。

Another name for using a function is call a function。

Both of these mean that the function is associated with additionalal code that will run when the line of code dysfunction is on executes。

The format to call a function is the function's name， followed by the left parentheses。

 followed by0 or more arguments。And then， a write parentheses。

Just like your code might sometimes require user input in order to execute。

 most functions do as well。Think of the arguments as the input to the function。

You can use or call the function with different arguments。

Here are some examples that should look familiar。As we look at them。

 you should think about what is the function name。And what are the arguments。

Let's look at the first one。What is the function in the line of code。Y gets SR parentheses，6，9，3。

4 parentheses。The function is the STR function。That function takes an input value or argument and converts it into a string。

What is the argument。The integer 6，9，3，4。In this case， the argument is a constant。

The STR function would assign the strength 6，9，34 to the variable y。

What is the function on the next line。That is the type function that tells what the type is of its argument。

What is the argument。The variable Y is the argument。 In this case， the argument is a variable。

T stores the type of the y variable。What about the next slide。What is the function。

That is the print function。What is the argument。The variable T is the argument。In this case。

 the value printed is class SR。 S T is the type of Y and y is a string。What about the next line。

 What is the function。That is the input function。What is the argument to the input function？

It is the strength。 How many。Let's suppose the user types 3。What is the function in the next line。

Remember， the function always has parentheses。That is the in function。

The in function creates an integer from its argument。What is its argument。The variable X。

The in function takes the value of x， which is the string 3 and converts it to the integer 3。

And stores3 in the variable X underscore int。What about the last line， What is the function。

The print function。We have seen that before。What is the argument。While in this case。

 there are two arguments， the print function allows you to print multiple items。

 It can have zero more arguments。If it has zero arguments， it prints a blank line。In this case。

 the first argument is string x times 2 is。And the second argument is an expression。X and times 2。

When the argument is an expression， Python first evaluates the expression。

 and then that value is sent as an argument to the function。In this case。

 the first argument is the string x times 2。And the second argument evaluates to6。

Then the function will print x times 2 is 6。Most of the functions we have seen have one argument。

 but the print function has zero or more arguments that each。Get printed。

In looking at these examples， notice that the argument could be a constant。

 a variable or an expression。Let's style look at the random module in more detail。

The name of the module is random。 and to use the module， you need to import it。

We will look at two functions from the random module that will help us in generating random numbers。

The first function is named Rand end。It has two arguments name No 1， and number 2。

This function generates a random integer between nu 1 and nu 2， including nu 1 and nu 2。

Note that both nu 1 and nu2 must be integers。Here's an example。Note when the function is called。

 we also have to give the name。Of the module， it is in。In this example。

 the call to the function is random， dot， R int， left parentheses，1， comma 3， parentheses。

This call evaluates to one of the numbers， one，2 or3。Every time this code runs。

 it evaluates this function。It generates one of those three numbers and returns that number。

Sometimes it will be one。 Sometimes it will be2， and sometimes it will be3。

Here's another function from the random module。This function is called random。

It generates a random float between 0。0 and 1。0。Including the number，0。0。

But not including the number 1。0。Every time our code calls the function。

 it would generate a different random number。Notice the random function has no arguments。😮。

That's because it was designed to only do this one task and does not need any inputs to change what it does。

Here's an example。It looks a little strange because the module name and the function name are the same in this case。

Here， the code caused to function random dot random。And maybe it evaluates to 0。34。

 or maybe it evaluates 0。987 or some other number。We don't know what number it will evaluate to。

We just know the number will be between 0 and 1。 Note that this function has no arguments。

It doesn't need any input。It just generates a number between 0 and1。

Let's now look at some example code that uses the random module。



![](img/4985897f7b917ec2888d066aa2dd7bd3_5.png)