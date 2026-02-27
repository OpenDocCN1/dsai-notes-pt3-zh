# 杜克大学《Python编程实践｜Practical Python： Start Your Programming Journey》中英字幕 p29 29_03_01_复合布尔表达式.zh_en -BV1tTmCBWEQD_p29-

![](img/dc7e0571b319d2d7ff777073bda82aa8_0.png)

By now we've had the chance to play around with some Boolean expressions。This time。

 let's look at different ways we can combine them to create compound expressions， in other words。

 combined Boolean expressions。Now， suppose you're trying to determine if a number is a natural number。

Let's define a natural number as any positive integer。

So the number must be a positive number and it must be an integer for you to be able to conclude that the number is a natural number。

Both conditions must be true for the number to be natural。Let's take a look at a table。

The first row in the table is the header row， the header row contains a title for each column in the table。

 giving us a hint as to what information to expect in each column。

This table just so happens to have four columns where the first column is a number titled nu。

 the second column is titled is positive， which contains a Boolean value for whether the number is in the first column is positive or not。

The third column is end will continue boolean value for whether the number is an integer or not。

Finally， the last column is natural， will continue boole in value for whether the number is a natural number or not。

Let's look at one example in the table where the number is negative 3。5。So for this example。

 nuM is negative 3。5 what about the second column？Based on the columns header is positive。

 we need to ask ourselves is negative 3。5 of positive number， well since it's no。

 well write falls as a Boolean value in row2 under that columns header。Moving on to the third column。

 ask yours cells， is numb an integer？😊，Well， negative 3。5 is a decimal number， not an introder。

 so we will write false。Now for the last column。Is negative 3。

5 in natural number let's think about this。We know that a natural number must be positive and an integer looking at column2。

 we know that negative 3。5 is not positive additional looking at column 3， we know that negative 3。

5 is not even an integer since both rules are broken， we can say with certainty that negative 3。

5 is not a natural number therefore we will write false as a boolean value。

Well let's take a look at another example， specifically negative6。

Can you fill in the row of the table with the correct bullolean values for negative6 to fully benefit from this video。

 go ahead and pause the video now and try to guess what the values for this table row will be once you've committed to your answer un pauseuse the video and we will go over the solutions together。

Okay。Let's go over the answer now， negative6 is not positive。But it is an integer。Unfortunately。

 you need both conditions to be true since only one is true and not both negative6 is not a natural number。

Seeme problem happens。When considering 2。4， 2。4 is positive， but it is not an introder。

 therefore it is not a natural number。Well， what about eight？8 is positive。

 so that condition is true and 8 is also an integer making the second condition true as well。

 and since both conditions are true， you can conclude that8 is indeed a natural number。

Considering the code on the slide that will determine the variable nuun is a natural number or not。😊。

In line one， the variable nu is assigned the value 10。In line two。

 the result of the boolean expression is assigned to the variable is positive。

But what is the Boolean expression， well， numb greater than zero？

Which is actually 10 greater than zero since nu is 10。So is it true that 10 is greater than zero。

 yes， so this expression of value is to true？😊，That means when line two of our code executes is positive。

 willll be assigned the Boolean value true。In line three。

 we have another booleing expression where we are checking if the data type for two different pieces of data match。

I went ahead and put this bulloleying expression in parentheses just to make it easier to read。

Recall that two assignment operators together means equal to in Python。

Is the data type of the nu the same as a data type for the value5 well。

 nu is an integer and five is an integer， so these two data types do indeed match。As a result。

 Pythgon will assign the value true to the variable is int。Now let's slow down a bit。

You're probably wondering why we used five， what's so special about five could any other integer value work instead of five？

Well， the value itself doesn't really matter just as long as the data type is an integer。

 since that is what we are looking to determine。Now let's analyze line four of the code notice that there is a keyword on line4 it's the word and I've highlighted the word in blue as well as making it bold to make it easier and clear that in Python the word and has a special meaning so what does line four of this code do in line4 we check if nu is both positive and an integer notice how the keyword and is a logic operator being used in line4 to combine two different Boolean expressions creating one compound expression。

Here is positive and is end are being combined in such a way that the compound expression will evaluate to true if both is positive and is end are true。

Well， we know from line two that is positive is true and we know from line three that isin is true。

 so what does true and true evaluate to？True and true in values are true。

The value true is assigned to the variable is natural letting us know that 10 is indeed a natural number now what if you have two conditions and you don't necessarily need both conditions to be true just one is enough。

Well consider the example on this slide， you will wear some type of coat if it is cold or it is raining。

 if either condition is true， then you will wear the coat， if both conditions are true。

 then you will also wear the coat， you will only choose not to wear the coat if both conditions are false。

Now consider the following table recall that the header row this table should hint as to what type of information to expect in the respective columns for the first column the header is is cold if the weather is cold then we will fill in the row under that column with Dr。

If it is not cold， we will use falses。Moving on to the second column， if it is raining。

 then we will fill the row under column2 with true， if it is not raining， we will use false。

What about the last column well， if either column one or column two are true。

 then we will fill in the row under the last column with true。If both columns1 and two are false。

 then we will use false instead to fill in the row under the last column。Let's look at an example。

If it is not cold and it is not raining， should you wear a coat？No。

 both conditions are false so no code is needed let's look at it another example。

 if it is not cold but it is raining， should you wear a coat go ahead and pause this video to guess the answer。

😊，Yes。😊，You just need one condition to be true for you to wear the coat what about the next two rows pause this video to try to solve the last column for these two unsolved rows and once you're ready。

 reason the video we will go over the answers together。If it is indeed cold， but it is not raining。

 then you will still choose to wear a coat if it is cold and it is raining。

 then you will undoubtedly choose to wear a coat。So how did he do？

If you didn't do as well as you'd hope， you can always rewind this video and watch it again。

 sometimes it helps to listen to a concept multiple times before you truly understand it。Now。

 what does this table look like in code？Well， in line one。

 we can assign the string cold to the variable temp。Which is short for temperature in line two。

 we assign the string sunny to the variable weather。In line three， we have a boolean expression。

 which is in parentheses just to make it a little easier to read。😊。

The bulloleyan expression is checking if temp is equivalent to the string cold。

 given line1 of the code， this expression evaluates it true。So is cold assigned the value to？Now。

 in line four， we have yet another boolean expression。

The expression is checking if weather is equivalent to the string raining。Given line two。

 this expression evaluates too false。That means is raining is assigned the value false？Well。

 what about9 5？Line five contains the logic operator or。This compound expression is checking if。

It either is cold or is raining as true， or if both of them are true。And from line three。

 we know is cold is true。Also from line four， we know is rainigning as false。

That means we have true or false。What does this expression evaluate to？

Take a moment to think about it before I reveal the answer。😊，True or false evaluates to true。

Since the first condition is true， remember， we only need one to be true for the whole compound expression to evaluate the true。

Thus， the value true is assigned to the variable wear coat。

 letting us know that you should wear a coat。Logic operators and as well as or can work with any combination of Boolean expressions here we will use A and B to represent arbitrary Boolean expressions。

That means you can replace A and B with any booleying expression you can think of in this table。

We'll still apply to the example you just came up with。Looking at the first row on the table。

 we will consider the example of when the Boolean expression A evaluates to false and B evaluates to false。

The compound expression A and B will then be false why is that well A and B will evaluate to false when either A or B are false。

Or even when both are falses。What about the expression A or B？What does that evaluate to。

Feel free to pause this video if you need a moment to think。A or B evaluates to false why？Well。

 using the or operator， A or B will evaluate to false when both A and B are false。

 it's not just them if one of them is false， both must be false for the expression to be false。

Let's take a look at the second row on the table。Here you have A is false and B is true。

 what is A and B？Feel free to pause this video if you need a moment to think about the answer。

A and B is false。If you're confused。Take a look at the rule under the table， since A is false。

 then the expression A and B is also false。What about the expression A or B？

Well the rule under the table for the or operator lets us know that in order for the expression to be false。

 both A and B must evaluate to false。Since B is true， then the expression A or B is also true。

More generally， A or B evaluates a true when either A or B are true。Or even if bull are true。Now。

 let's move on to the next row on the table。We have A evaluates to true and B evaluates to false。

A and B evaluates to false since B is false。Likewise， A or B evaluated true since A is true。

What about the last room at the table？Here we have A evaluates the true and B evaluates the true。

 what does A and B evaluate to？A and B evaluates the true。Why。Well。

 we know that in order for A and B to be false， either A or B must be false。

 but since A is true and B is true， then A and B must also be true。As a general rule。

 A and B is true only when both A is true and B is true as well。

Now we have all that we have left is A or B for the last row， since A is true and B is true。

 then using our knowledge of the or operator， we can deduce that A or B is true as well。

A third logic operator we will look at is the not operator。

The knot operator reverses the evaluation of a boolean expression。So for example， if a is false。

 then not A is true。Likewise， if a is true， then not A is false。Let's take a look at an example。😊。

In line one， we have 10 greater than five， which evaluates the true。

The value of true is assigned to the variable variable。And then looking at line two。

 since variable is true， not verbal will be false。Since a knot operator evaluates to the opposite of the Boolean expression。

As a result， Python will assign the value false to the variable reverse bar。

Now let's do a quick review here are all the logic operators we have covered so far feel free to pause this video if you need time to study the table。

Given any Boolean expressions A and B， as shown in the columns one and two in the table。

 the following holds true。The expression A and B will only ever be true if both A as well as B are true。

Any other combinations of A as well as B cause the expression to evaluate two false。Alternatively。

 the expression A or B will evaluate to false when both A as well as B are false。

 any other combinations of A as well as B will cause the expression to evaluate to true。😊。

The knot operator flips the Boolean expression so not a will always be the opposite of a and that is how you use logic operators to create compound Boolean expressions here's the challenge for you think of ways to use compound Boolean expressions in your own coding projects only through practice will these concepts become easier and faster for you to understand。



![](img/dc7e0571b319d2d7ff777073bda82aa8_2.png)

![](img/dc7e0571b319d2d7ff777073bda82aa8_3.png)