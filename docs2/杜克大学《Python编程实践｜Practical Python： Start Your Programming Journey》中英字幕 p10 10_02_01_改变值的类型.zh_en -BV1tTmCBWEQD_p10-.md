# 杜克大学《Python编程实践｜Practical Python： Start Your Programming Journey》中英字幕 p10 10_02_01_改变值的类型.zh_en -BV1tTmCBWEQD_p10-

![](img/5456acf0174166be30d5e9b55166398b_0.png)

In this video， we'll be looking at typecasting， which is an effective way to convert between data types。

 We've discussed the different data types in Python。

 and some of the neat things you can do with them。 One data type we have discussed is strings in Pyon。

 a string might be denoted by the abbreviation S T R。

 An example of a string is the word hello enclosed in quotes。

 or even the word Python We also have talked about integers。

 which might be denoted by the abbreviation int Exles of integers are the whole numbers 10 and 20500。

 Not inython， there's no comma used to represent 2500。😊，Lastly。

 we discussed decimal numbers in Python， a decimal number is usually denoted by the word float。

 Exles of decimal numbers are 3。78 and 0。049。You can assign values from any of these data types to a variable。

As you continue in your programming journey， there will be times when you will not know a particular variables type。

Maybe when you first created a variable， it was of type string。 For example。

 we created a variable named var and assigned it the string。 Hello。

 var is an abbreviation for variable。Then somewhere later in the program。

 Vr became an integer type by assigning it the value 20。Now， at the end of your program。

 you're no longer sure what data type the final value of a variable is。

 var is assigned the value of another variable。 In this case。

 var is assigned the value of the variable x。If your variables have a usefulable variable name。

 then you might have a good idea on what data type to expect。 For example。

 a variable named X won't hint at much， but a variable named age would provide some much needed context。

 Now， we can make an educated guess that the data type will be an integer representing a person's age。

 The variable var doesn't give you much of a hint either。 without actually the point of this example。

 Now， suppose， despite all of that， you still don't know the data type of a variable。

 How can you find out。 Well， in Python， there's a really neat function called type。

 which will determine the data type of any variable or value for you。😊，To use the type function。

 youll need to write the word type followed by parenttheses， inside your parenttheses。

 write the variable name or the value whose type you are trying to determine。

Let's look at some examples of this。 type with the word hello enclosed quotes。

 This line of code will determine that hello is of type string。Type with a value 7。75。

 this line of code will determine that this number is a float。Next， we have type with the value 50。

 This line of code will determine that this number is an integer。

Now we have type with a variable named word。 You can guess at the variable name that the data type for this variable will most likely be a string。

Finally， we have type with the value 10 enclosed in quotes。

 This line of code will determine that this number is a string。

 recall that numbers enclosed in quotes are interpreted as strings in Python。😊。

These are some examples of how to use the type function。

 but to use the result of using this function， we can combine it with a print function。

By placing the type function inside the print function。

 the resulting calculation will printed to the console for you to see。

Let's dissect the first example。Inside the print function， we have the type function。

 Then inside the type function， we have this string， hello。Recall that in Python。

 you solve what is in the innermost parentheses First。 That just so happens to be this string， Hello。

 which doesn't need any calculations so we can step out to the next set of parentheses。

 which is the type function。😊，The type function will calculate the data type of the string Ho。

 which we know is a string。Once that is figured out， we can move on to the outermost proheses。

 which is the print function。 The print function will print the resulting evaluation from the data type function。

 which we can see in the second column。What was printed exactly class S T R surrounded by angle brackets。

 recall that in Python， S TR is the abbreviation for the string data type。

 The type function was able to determine that Ho was indeed of type string。😊。

Within the scope of this course， you can consider the term class to be synonymous with data type。

 so class STR is the same as saying data type STR。Similarly。

 let's take a look at the second example inside the print function。

 we have the type function with this value 7。75 inside。

The type function will determine that this value is a float type。

 which is another way of saying decimal number， and the print function will display that conclusion to the console。

Taking a look at the third example with the value 50。

 the type function will determine that this value is an int， which is short for integer。

 and the print function will display that conclusion to the console。

Consider the next example with the variable named word。

Let's say that variable actually had a string in it， like the word cat。

The type function will determine that this variable is type stir， which is short for string。

And the print function will display that conclusion to the console。Now。

 let's look at the last example with 10。 The type function will determine that 10 is type stir or type string since it is enclosed in quotes。

 the print function will display that conclusion to the console。

 We encourage you to combine print and type together whenever you see a variable or value and you're not sure what data type it is。

 knowing the data type to a variable or value is important since it dictates what you can do with that piece of data。

Moving along， one thing we have yet to discuss is type casting。But what exactly is typecasting。 Well。

 it is how you can convert a variable from one data type to another。Let us look at an example。

 Suppose you have a string data type with the number 10 in it， like we did In our last example。

 we know that we cannot use many math operators with strings。

 So we will want to convert this string into an integer。 This is where type casting comes in。

By typing int parentheses 10， you have just converted the string 10 to integer 10。

Another example is float parentheses 20， which converts the integer 20 to the data type float。

 which looks like the decal number 20。0。Now， there are two main categories of type casting。

 implicit and explicit。 believe it or not， you have already been practicing implicit typecasting。

 This happens automatically when Python knows that doing so will not cause you to lose any unnecessary data。

 It does not require any action but understanding when this happens can save you a lot of time when you write complex programs and realize your program is not behaving as you intended。

😊，Consider the example X is assigned 8 divided by 4， which results in the value 2。0。

 Diding any integer is a common example of implicit type casting。 Why， Well。

 recall that the division operator always returns a float。 in this way。

 the division operator implicitly type casts the integers into a float。

 by dividing integers 8 and 4 in the example， we create the decimal number 2。0。

 instead of the integer 2。😊，Consider the next example where y is assigned 0。0 plus 9。

 which results in 9。0。You may recall that by adding an integer in a float。

 the result will be a float。 The same is true for most mathematical operators as well。

 This is because Python will implicitly type cast the integer into a float。 In this case，9。

 then perform the mathematical operation。😊，Explicit type casting is a manual process where you will need to specify what you would like to convert and the data type you would like to convert it to。

This can potentially cause you to lose some data， but don't worry。

 we will talk more about that later。In order to explicitly typecast。

 you can follow this general format where you first specify the data type you are trying to end up with。

 then parentheses inside your parentheses， you enter the value or variable you were trying to convert。

Let's take a look at some examples。 In the first example， we are converting 5。9 into an integer。

 That means we lose the 09 and you just keep the phi。Python will not round the number for you。

 It'll just remove anything that comes after the decimal point。 Thus。

 the integer 5 is stored into the value。 variable X。 This is an example of how we lost some data。

 by explicitly type casting， specifically， we lost everything after the decimal。Next， we convert 0。

045 into a string， then store that string into the variable Y。 The variable Y is now of type string。

The integer 3 is converted into a float， making it 3。0。 We then store that value into variable Z。

Notice how all these examples follow the general format。 First。

 we have the desired data type we want to end up with。

 Then the parentheses where we place the value or variable we are trying to cast inside the parentheses。

😊，Let's take a look at a slightly more complex example。 Here we have the variable T X T nu。

 which is assigned 50。5 as a string。On line two of the code。

 we typecast T X T nu to afloat and assign the resulting value to the variable nu。The string， 50。

5 converted into a float results in the float value，50。5。 So 50。5 is assigned to nu。

Let's dive deeper into the possible loss of data with explicit type casting。

This usually refers to when you are converting between integers and floats。

 Fs represent decimal numbers， and therefore Eds numbers before and after the decimal point。

 integers， on the other hand， only represent whole numbers。

 so has no numbers after the decimal point。Converting from an integer to a float will not result in a loss of data。

Let's take a look at an example。 Suppose we have a variable named nu， and we store this value。

5 into it。We convert numb into a float by following the general format mentioned in the previous slide。

The variable nu now contains the value 5。0。 So what happens if I cast numb into an integer again。

Well， I go back to my original value of 5。 I do。 So going from integer to float did not make me lose any data。

 But what if I originally had a float and wanted to convert it into an integer。

This is where you may run into problems。Let's take a look at an example。

Suppose we have a variable named nu， and we store the value 2。6 into it。

We convert a nu into an integer。 So a nu now contains the value 2。

 So what happens if I cast numb into a float again， Will I get back my original value of 2。6。

 Let's find out。Looks like it returned 2。0， not 2。6。 When we convert 2。6 into an integer。

 we narrowed this value， Thus， losing our data on 0。6。 This is not necessarily a problem。

 This was what your intention。 Maybe you only wanted to keep the two and discard the rest。

But if that is not what you wanted your code to do。

 this might cause errors or lead to incorrect math。

Typecasting can be a very useful tool to use as you program。

 I hardly write any programs myself without typecasting at least one value。

 Just be sure to keep possible data loss in mind whenever you are explicitly typecasting。😊。



![](img/5456acf0174166be30d5e9b55166398b_2.png)