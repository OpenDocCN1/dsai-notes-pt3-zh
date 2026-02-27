# 杜克大学《Python编程实践｜Practical Python： Start Your Programming Journey》中英字幕 p22 22_03_03_if-elif与if-if的区别.zh_en -BV1tTmCBWEQD_p22-

![](img/4550de8e060fbbc46945d54977b09ccc_0.png)

So you know what an I statement is。 Let's pause and talk about how there are different ways to do the same thing using I statements。

Here is the generic code for an if statement with an if， El and else clause。

 When Python executes this statement， If it reaches a true condition。

 it executes that code block that belongs to that condition then skips to after the if statement。😊。

It does not execute any more code in it。And if it does not reach a true condition。

 it will arrive at the else clause and execute its code。In contrast。

 here is the generic code that is using three if statements。With this code。

 Python will check every if statement condition。 and if it is true， itll execute the code block。

And even if a prior if statements condition is true。

 Python will check the next if statements condition because they are separate， if statements。

What this means is that the if statement with the LF and else clauses will only ever execute one kbook。

 no more and no less， only one。On the other hand， the code with the three if statements could execute 0 to 3 of the code blocks。

 Why， Because if all of the conditions are false， none of the code blocks will execute。

 but if all of the conditions are true， then all of the blocks will execute。

Here is our example from before on what to bring based on the temperature。But now it's in a table。

I don't bring anything if it's above 65。If it's between 65 and 50， I bring a sweater。Otherwise。

 I bring a coat。Here is the coat that could print the correct string corresponding to this table。

But I've purposely removed the stuff between asking for the user input and printing out what to bring。

 because I wanted to emphasize that there are different ways to write this code。

And as long as the correct string at the end is printed， it doesn't matter how you implemented it。

Let's talk about what I mean。Here's the code from before using one if statement that uses L if and else。

 But what if I didn't want to use L if and else， Is it possible to implement code so it behaves the same way but only uses if clauses。

Remember， how I do it doesn't matter as much as whether or not Python prints the right string at the right time。

The answer is yes。 Here is the code that prints out the same string。

On the left is the code we had before that uses one if with Elith and else。

 On the right is the code that uses two if statements that each only have an if clause。

Before we walk through from side by side， let's talk about the intuition of the new version。

The first line is just like before and asks for the input。

 The next line assigns what to bring to nothing， rather than a question mark。

The idea here is we are just setting the default value to the string， nothing。

The rest of this code is basically checking the temperature as it gets colder and colder and changing the value of what to bring accordingly。

Let's go through an example to make this concrete。Let's give the coat a temperature cold enough to bring a coat。

For example， 45 degrees。On line 2， we set what to bring to the string nothing。

When we get to the is on line 3， the condition evaluates to true。

So we execute line4 and assign the value of what to bring to the string sweater。

Then we get to line five's if statement， which also evaluates to true。

So we execute its code block and reassign what to bring to code。 So if now assign the variable。

 what to bring three times， regardless， though， when the code reaches the print statement。

 it will only print code， even though we change the value of what to bring multiple times。

So let's go back to the side by side view of the one if statement using if EF and else and our new code that uses two if statements。

 I've added some extra lines to make things line up。When it comes to bringing nothing on the left。

 we have the if clause of the if statement， But on the right， we don't have any if statement at all。

 We simply make the value of what to bring the string， nothing。

The coat dealing with sweater is also different。 On the left， we have an e clause。

 checking if the temperature is above 50。 Well， on the right。

 we have an if statement that checks if the temperature is 65 or below， because if it is。

 we can't do the default of bringing nothing。For whether to print coat on the left。

 we have the else clauses that only executes if the prior conditions are all false。

 So if the temperature is 50 or below。On the right。

 we have a second estimate statement that just directly checks if the temperature is 50 or below and assign what to bring to count。

 So even though the implemented things differently， the code will print the same thing。

 given the same input， which is perfectly fine。😊，So which one do you do。

 a single if statement with if， Elith and else clauses？



![](img/4550de8e060fbbc46945d54977b09ccc_2.png)

Or a bunch of estimates。It's up to you。 The point of this video is to show you that there are different ways to do the same thing。

 and that's okay。 For some people， the single I statement with all of its clauses。

 makes more sense for other， it， it's only using if statements。

 What matters is the code prints out what it is supposed to print out Given the temperature ranges in this table。

 And that's actually one of the things I find awesome about coding。

 we can all aim to achieve the same goal but can be creative in our own way in how we achieve it。😊。



![](img/4550de8e060fbbc46945d54977b09ccc_4.png)