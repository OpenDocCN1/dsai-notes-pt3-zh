# 杜克大学《Python编程实践｜Practical Python： Start Your Programming Journey》中英字幕 p13 13_02_01_让你的程序具有交互性.zh_en -BV1tTmCBWEQD_p13-

![](img/35a25247d94b0a16e0dc244eb312dd1f_0.png)

In order to have your program be versatile， that is have your program produce different meaningful results。

 you would need to get input into your program。If you do not have any input。

 your program would do the same thing every time you run it。Well， not quite true。

There are ways to have your program generate random results。But you haven't learned about that yet。

There are several ways to get simple data into your program。

One way is to use the Python input function。When you run your program。

 the input function allows you to enter data that can be used with your code。

Every time you run your program， you can type in something different if you want。

How will you know when to type in your data？You would need to provide a phrase that will appear in the console。

So you would know that it is time to type your input。This phrase prompts the user for the input。

What do I mean by user？Most programs are intended for someone to use or run the program。

That someone is called a user。Programs should be designed， so they are easy for users to run。

When using the input function。Your code provides a prompt to explain what the user needs to enter。

The input function will convert the value that you type into a string data type。

This process is also known as reading and user input。Since the user is using or running the program。

An entry and input when prompted。Once your program reads in input。

 the program can then use that value somewhere in your program。

Here is a syntax of using the input function。Since input gives you a value。

 it is best to store that value into a variable knee。

The variable name goes to the left of an assignment operator because you're assigning a value to that variable。

The input function is to the right of the assignment operator。And has the name input。

 followed by parentheses and a string prompt inside the parentheses。

The prompt is what the user will see when you execute the input function。

It is good to practice to write a descriptive prompt。

 so the user is now left guessing what they should type in。Let's look at an example。

Here you have a variable called name。This variable will be assigned the results of the expression to the right of the assignment operator。

To the right of the assignment operator we have the Python input function。

The input function has a prompt strength。What is your name？

Let's see what happens when this code runs。First， let's expand this example by adding two more lines of code。

Let's step through the code。When the first line of code executes。

 there are several things that happen。The first line is an assignment statement。

 so the value to the right of the assignment operator executes first。

The input function displays the prompt in the terminal。You can see where it says in the output。

 what is your name？And then the program pauses， waiting for you to enter the input。

Notice that by just reading the prompt， you can determine what type of information the program is asking for。

In this case， the program is asking you to type in your name。

Nothing will happen until you type in something。 Let's say you typed in the name， aemla。

Then you press enter。Otherwise， the program won't known when you have stopped typing。

Now the assignment statement can complete and the name aemla is stored in the variable name。

Let me point something out here。There is a space at the end of the line。

In the code and also below in the same output line。That is so when the user types in the name。

 there will be a space between the prompt and what the user types。

You will notice it if you forget the space， let's move on with the execution。

When you execute the second line， the print function looks up the value of name。Sees it is Aemla。

 combines a string， hellello， followed by a blank with the value of name and print， Hello， Aemla。

And it is advantageous for you to store the input in a variable name。

 so you can refer to that value multiple times。When you execute the next line of code again。

 Python looks up the value of the variable name and builds a new string to print the string that is output is aemla is a nice name。

In summary， we have three lines of output， the first line prompted the user to type in a name。

Which the user did。The name Ademla was stored in the variable name。

 and the remaining two lines use the information stored in the variable name to build strings to print。

What about the numbers。

![](img/35a25247d94b0a16e0dc244eb312dd1f_2.png)

How do you get the numbers into your program so you can do the calculations with them？

As we said earlier。All input is read into a program as a string。If you type an integer。

 that integer will come in as a string， but you can use type casting to convert that string to an integer。

Similarly， if you want to type a float as the input。That float number will come in as a string。

But you can use type casting to convert that string to the float value of the string。

Let's look at an example。Suppose you want to purchase several tickets to a movie for you and a group of friends。

Here is a line of code that asks you how many tickets you want to purchase。No matter what you type。

 the variable tickets will be assigned to string value。If the value type is a whole number。

 then you could use the in function to convert that string version of the integer into an actual integer。

Let's trace through this example to see what actually happens。We show the output below。

When the first line of code runs， youll be prompted by the question how many tickets？

Suppose you type in the number four。So you're thinking that you are  type in in a number。

 but the program is treating that value as a strength。

If you look at the values stored in the variable tickets。

You can see that tickets value is the strength for。If you want to use this value as a number。

 you need to convert that string to a number。The second line of code takes a string from the variable tickets and converts it to the integer 4。

And then stores the inte of 4 in the variable named tickets underscore int。

Notice I name this variable to emphasize that it is the integer version of tickets。

You can see that tickets underscore int value is an integer。

Let's expand this example by adding three more lines of code so you can calculate how much four tickets will cost。

L3 of the code has a lot happening。You read in the cost of one ticket and immediately convert that string to a float。

Let's step through that line more slowly。So that we can see what happens。

Whenever there is an assignment statement， you always calculate the expression to the right of the assignment first。

But this expression is complicated。When you have the parentheses。

The inside of the parentheses are always calculated first。In this case。

 the input function is executed and you can see in the output that you're being prompted for the price of one ticket。

Suppose you enter 10。50 as the price of one ticket。Remember。

 this value is read into the computer as the string 10。50。

To emphasize that the value is the strength 10。50， we can replace the code in the blue rectangle。

With the value that is read in。You can see that it is the string 10。50。

Now that we know the value produced by use input。We can now convert the string value into a float。

We calculate the float of the string， 10。50。And get the flow value 10。50。

That value gets stored in the variable price， as shown here。Note。

 if you convert the number to the correct type all in one line。

 then you don't need an additional variable。That you would only use once。

As we did with the variable tickets。Which we then converted to tickets underscore int。

Now that tickets underscore in and price are both numbers。

You can multiply them together to get the cost。Of the four tickets and store that number into variable amount。

 Let's watch that happen more slowly inside the blue rectangle。First。

Look up the value of tickets underscore ins。The value is 4。Then look up the value of price。

The value is 10。50。Multiply4 times 10。50。And the F 42 is stored in the variable amount。Finally。

 you can print the float amount。42。00。So you would know how much money you would need to buy movie tickets for you and your three friends。

Now， that might look funny。42。0。It doesn't look like money， which would look like 42。00。By default。

 when Python prints flow values， it prints only digits that are non zeros。

And always at least one digit to the right of the decimal。

There is print formatting you can use to specify how many digits to the right of the decimal to print。

But we won't go into that here。What happens when the user types in bad input？

And the user will do this。Here's an example。The program asks the user how many tickets and the user types in the word for。

It is not really clear what type of input the user wants。It just says how many tickets？

The word4 gets stored in the variable tickets。When the next line of code executes。

 the code tries to convert the string of the word4 to an integer。That won't work。

The conversion of strings to integers work only if the string is made of digits。

What could we do to fix this？We could give the user a better message。

 possibly an example so they know what the program wants。Here in the input function prompt。

 we give an example of what type of input the program is expecting。

Here we add an example of the digit2 for the input。Note。

 this doesn't prevent the user from typing the word for。

 but hopefully steers the user in the direction to type a digit。

We will later learn how to force the user to type the correct type of input。Wrapping up。

What is the most important message to take away in this video？Remember。

 all values are read in as a string。And if those strings represent a number。

 you would need to convert them to number types if you want to do calculations with them。

I hope you enjoyed this video。

![](img/35a25247d94b0a16e0dc244eb312dd1f_4.png)