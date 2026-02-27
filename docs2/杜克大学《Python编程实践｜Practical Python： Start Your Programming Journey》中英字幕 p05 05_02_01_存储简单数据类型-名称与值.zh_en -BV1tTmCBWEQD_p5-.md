# 杜克大学《Python编程实践｜Practical Python： Start Your Programming Journey》中英字幕 p05 05_02_01_存储简单数据类型-名称与值.zh_en -BV1tTmCBWEQD_p5-

![](img/06e3507ab158935828d7cf2ed6ea2ef6_0.png)

We want to store data in a computer so we can use the computer to solve problems。For example。

 suppose you want to write a story about three friends。

 but you're not convinced yet what their name should be。

Their names would be used over and over again in the story。

Wouldn't it be nice that if you decided to change their names。

 you would only have to change each name in one place instead of having to change it everywhere in your story。

 Well， you could do that。You can store each name in a specific location in the computer and refer to that location to get that name each time you need it。

Then if you decide to change the name， you only change the name in that one location。

That leads us to think about two questions。How do we store a string in the computer？

What other types of data can we store in the computer besides words？

Python supports different kinds of data。 These are called data types。

 knowing the data type you are working with is important。

 since it will determine everything you can do with that piece of data。To better understand this。

 let's look at three common data types now。We will learn about more data types later。

One data type is a string。 You already learned about strings and how to print them。

Python uses an abbreviation for the type for a string， calling it type STR。

A string is made up of letters， digits， and other characters surrounded on either side by single quotes or surrounded on either side by double quotes。

The quilts are not part of the string。Here are some examples。

 Ho is a string that has double quotes on either side of the five letters。

A string can have blanks in it， so it looks more like a phrase。 The string， We to our course。

 is a string made up of 21 letters and blanks surrounded on either side by single quotes。😊。

Our last example is the string， Was't 2019 a great year？

This string shows a single quote as part of the string。Remember。

 in order to have the single quote in the word wasn't， as part of the string。

 we must use double quotes around this string。Otherwise。

 Python would not interpret the string correctly。This example also shows that we can use other characters such as the question mark inside the string。

Next， let's look at two more data types that are numbers。First， let's look at decimal numbers。

Python calls decimal numbers of type float。 A float is made up of the digits 0 through 9。

1 decimal point or dot。 and a dash at the front， if the number is negative。Here are three examples。😡。

38。5， negative 6。0 and 3。14159265。Another type of number Python represents is an integer or whole number。

Python calls them type int。 An integer is made up of the digits 0 through 9。

 and a dash at the front if the number is negative。Here are some examples of ntegers， 89。

 negative 5 and 0。You have now seen three different kinds of data types， strings， floats。

 and integers。All of our data will need to be stored in a computer so we can use that data， so。

How is data stored in a computer？Data is stored at address locations in computer memory。

You know about address locations of buildings， here are three buildings。

All three of them have an address location on Main Street。

Suppose I live in the purple house that has the address， 102 Main Street。

The Orange apartment building beside it has the address 106 Main Street。And if I'm hungry for pizza。

 I can walk down the street to the address， 110 Main Street。

 where I will find the pizza place called Best pizza。

Best pizza is of physical value or building made out of wood and other building materials。1。

10 Main Street is the location or address of this building。

Now let's relate address locations to storing values in computers。

A computer has a lot of memory locations where you can store data。

These memory locations are numbered， we call them numbered address locations。

Here we show three address locations and data that is stored in those address locations。

The address location 1578 is storing the float 68。3。

The address location 2450 is storing the string Kia。That is the name of my cat。There she is。

And the address location 3626 is storing the integer 121。

It is difficult for humans to remember all those address locations。 That is。

 iss difficult to remember that the string Kia， is stored in address location 24，50。So instead。

 we can assign names to those memory locations。Python lets us use a name to refer to a memory location。

I can use the meaningful name， temperature to refer to a memory location that is storing a decimal temperature value。

Remember， temperature is still referring to the address location 1578。

 but I can just use the name temperature to refer to that location。

I can use the nameca to refer to a memory location that is during my cat's name Kia。

I can use the name number to refer to the Energer 121， I am storing。

A variable is a name used to refer to or reference a value that is stored in a computer at some memory location。

Python has rules for the name。 It must be made up of letters， underscores and digits only。

 and it must start with a letter。A variable name should also be descriptive of the value。

If I'm going to store a number， that is a temperature。

Then temperature would be a meaningful name for that variable。

Here are some examples of variable names。Temperature， notice it's made up of letters。Bike price。

 notice this variable name is made up of capital and lower case letters and an underscore。Name 3。

 this variable name is made up of letters and a digit。And three words。

This verbalbri name is also made up of letters in a digit。But wait a minute。

 That last one is not a valid variable name because it starts with a number。

Fearorable names must start with a letter。How do we get values into memory。

 We assign a value to a variable using the assignment operator。

The assignment operator looks like an equal sign， but we will not call it equal sign。

 as that would be confusing with the equal sign that's used in math。

The assignment operator is for assigning a value to a variable。

The format for an assignment is you put the variable name first， then the assignment operator。

 and then the value。The first time a variable is seen。

 Python finds a memory location for it and stores the value in that memory location。

Then whenever you need that value， you can refer to the variable name to access its value。

The second time that variable is assigned a value， Python will see that it already has a memory location and it will change the value stored to the new value。

Let's look at some examples Here we have four numbered lines of some Python code。

 we will execute one line at a time from top to bottom so we can keep track of which line of code has just executed。

A green arrow will point to the line of code that just executed。When we execute the first line。

 we have a variable that has not been seen before。 Python looks for a memory location for it。

 then assigns the variable number to that location， and then stores 89 in that location。

When we execute the second line， Python looks for a memory location。

 assigns value to that memory location， and stores the value6 in that location。

When we execute the third line， Python will notice that the variable number already has a memory location。

It changes the value stored at that location to 3。The value stored in variable number has changed。

When we execute the fourth line， Python will look for a memory location and assign amount to that memory location。

 then it evaluates the item to the right of the assignment operator。

 it looks up the storage location for value and sees6 is stored there。

 it then stores the value 6 in the address location for the variable amount。

When you are working with variables， there are three things you want to think about。Names。

 types and values。What is the name of the variable， What is the type of the variable。

 What is the variable's value。In this example， we see the name of the variable is bird。

To determine its type， we have to see what type of value is being assigned to it。

Since blue J is a string， the variable bird has type string， and its value is the string blue J。

And that is how you create a Python variable。I encourage you to go to your coding environment and try to create some variables yourself。

 And if you are still not sure how to do so， you can watch the demo first。😊。



![](img/06e3507ab158935828d7cf2ed6ea2ef6_2.png)

![](img/06e3507ab158935828d7cf2ed6ea2ef6_3.png)