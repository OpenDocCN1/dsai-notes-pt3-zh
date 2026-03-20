# 纽约石溪大学【中英⚡数据科学｜CSE519 2024 Data Science Fundamentals】 p22 P22 Lecture 3 and 4： Python For Data Science (Fall 2024) -BV1s7Gaz5ETS_p22-

so you really see the power of these things when they're used as anonymous functions inside of another function。

 So you're actually going to see this come up a lot throughout the rest of this tutorial。

 particularly in panda do apply function and in list sorting。 So just keep that in mind。



![](img/ef4832726233ec4027a61e30919d4879_1.png)

And那 one you。So hi guys。Any questions till now？Okay， I'm assuming no questions so。



![](img/ef4832726233ec4027a61e30919d4879_3.png)

There is another handedy thing with where you can actually call a function with keyword arguments。

 so for example let's look at the same excite string function。

 but now we have multiple arguments and let's say we have two extra arguments which are excitement level and excitement character and then we do something with them inside here。



![](img/ef4832726233ec4027a61e30919d4879_5.png)

![](img/ef4832726233ec4027a61e30919d4879_6.png)

Now let's say if we run this thing。

![](img/ef4832726233ec4027a61e30919d4879_8.png)

We are getting an error and this has happened like fairly frequently with me whenever I' am using C++ and sometimes also imp Python its just that like if I do not go back to the function definition you don't really remember like which one was before which one like does excitement level come before excitement character I mean people just make this mistakes right so there is a useful way you can actually avoid these kinds of error which is you can pass the keyword argument and then just say what the argument is going to be so even though let's say here。

😊。

![](img/ef4832726233ec4027a61e30919d4879_10.png)

![](img/ef4832726233ec4027a61e30919d4879_11.png)

![](img/ef4832726233ec4027a61e30919d4879_12.png)

Excitement characterter was our card argument。

![](img/ef4832726233ec4027a61e30919d4879_14.png)

I can pass it anywhere I want because I'm just literally telling the function that I want excitement character to be hash and then it doesn't really matter the order of the arguments because we have the names here and it works perfectly fine so this actually really comes in handy like when you were doing some machine learning and there are like 10 different arguments you have to pass so this is just a better way of coding。

😊。

![](img/ef4832726233ec4027a61e30919d4879_16.png)

We have one more stuff here， which I'm not going to go go into detail right now。

 I have just kept it in here because I think this is。Good stuff that you should actually learn。



![](img/ef4832726233ec4027a61e30919d4879_18.png)

So but this is going to take some time so I'm skipping over it for now。

 but if we have time in the end of the class， I might come back here。😊。



![](img/ef4832726233ec4027a61e30919d4879_20.png)

So Dakota。

![](img/ef4832726233ec4027a61e30919d4879_22.png)

Okay， so next within the Python basics， we get to dictionaries and sets。

So this is my favorite data structure。 it's basically what you would consider a hash table in other languages。

 it is mapping a key to a value， so in this case we have a function which is a list to count diict which turns our previous input list into a dictionary and we just count the number of letters within there so we test our list sentence which was remember one must imagine sissyphs happy and then we print the test diict and what it gives us as you can see it's wrapped in these curly braces here。



![](img/ef4832726233ec4027a61e30919d4879_24.png)

We have one count of capital O， two counts of lowercase N， and so on and so forth。

 And then below here， we have some of the functions that you can do on dictionaries in particular。

 so you can get the keys。

![](img/ef4832726233ec4027a61e30919d4879_26.png)

![](img/ef4832726233ec4027a61e30919d4879_27.png)

Which will give you just the capital letters here， you can get the values out of these key value pairs。

And note that these are ordered the same way。 And then you can also get items。

 which items is returning them as pairs or in Pythons。 These are called tuples， which you have。



![](img/ef4832726233ec4027a61e30919d4879_29.png)

Just an unordered。sorry， ordered list of elements here。

 so with the items we can do is typecast that into a list and now instead of the stick items object。

 we have a proper list object and we have a list of these pairs。



![](img/ef4832726233ec4027a61e30919d4879_31.png)

Now， from these pairs now we're going to see the first use of that lambmbda function。 But first。

 let's put those pairs into a list。 Let's just sort it and see what we get and print out。

 So if we just call this sort function on our list， which is just a built in a Python list。

 we see we get this。 So it starts from the end of the lowercase alphabet and moves into the uppercase alphabe。

 And that's because reverse is true。 If we do it false。 it should do it in proper alphabetical order。



![](img/ef4832726233ec4027a61e30919d4879_33.png)

![](img/ef4832726233ec4027a61e30919d4879_34.png)

Yeah， starting with capitals and then moving on to lowercase， however。

One thing we can do is we can pass an argument into this sort function to sort it by something different。

 so this is a pair， so this is perfect for our lambmbda function。

 were passing in a pair a two tuple into x， and now we say we want to sort by the element number one or second element in x。

And with reverse equal true now if we do it we see we're sorting by the counts instead of the letters themselves。

 so all the three counts are on top all the one counts are on bottom so this in particular oftentimes with dictionaries you will have this sort of setup where you have you care about the keys but you need to order by the values so in doing it in this way you can。

Using a Lada function， you can keep them together and do that efficiently。



![](img/ef4832726233ec4027a61e30919d4879_36.png)

这是 you。Most data structures in Python are usually by default unordered。

 so by unordered I mean those are hashables， some kind of hash table or something。

 so the keys are not in order so as an example let's see so this is a random set and if we run this code again。



![](img/ef4832726233ec4027a61e30919d4879_38.png)

You can see like when we are printing the set， the sets elements are not in any kind of order。

 it's not like by value or it's not ordered by the way I define the set， its unordered。

But if you need ordered data structures， you can have them。

 there are some separate libraries which you can use and they sometimes come in handy。



![](img/ef4832726233ec4027a61e30919d4879_40.png)

![](img/ef4832726233ec4027a61e30919d4879_41.png)

So， okay。Let's move on to the next topic， which I personally think is a pretty important topic。

 especially for people who are just starting in Python。



![](img/ef4832726233ec4027a61e30919d4879_43.png)

So before going into this， how many of you use Python as your primary language。

 can I see a show of end？

![](img/ef4832726233ec4027a61e30919d4879_45.png)

Okay， a lot of folks， what other languages do you guys use？Java C plus plus， anything else， anyone？

Ctlin okay nice okay so let's go into the tan complexity of different operations of data structures in Python and this is particularly useful in the data science fundamentals class because I remember while I was a T for this course like two years ago the most common problems students faced was there were just they were。

😊。

![](img/ef4832726233ec4027a61e30919d4879_47.png)

Starting in Python and doing something and they were like okay。

 this is one line of code and why is this taking so long。

 I don't really understand why this assignment is taking just to like run the code is taking like hours or days。

So you really need to understand what's happening behind that one line of code you don't really need to go into the very specific details but you should still have some idea how things are happening or what's the expected time complexity or memory complexity of the comments or instructions you are giving so let's go into some code now。

So for example this here we are creating a list using list comprehension which Dakota just explained before and which is like a list containing zeros and we have I believe 10 to the power112345678 so that's like what100 million so we have a list that has 100 million integers and all of them are0 so we are just creating that list and this list creation is definitely going to be order of n and lets see how long it takes。



![](img/ef4832726233ec4027a61e30919d4879_49.png)

So this took around a little bit less than5 seconds。 Okay， cool。

 so let's look at the other stuff here。😊。

![](img/ef4832726233ec4027a61e30919d4879_51.png)

Now we want to append something to the end of the list and this is an order of one operation because we were just like appending something at the end and how long did this take so this one take like 0。

08 millisecond not even second 0。08 millisecond because this is fairly this is a fairly for a fast operation。



![](img/ef4832726233ec4027a61e30919d4879_53.png)

![](img/ef4832726233ec4027a61e30919d4879_54.png)

![](img/ef4832726233ec4027a61e30919d4879_55.png)

Now if we wanted to insert something in the middle of the list， like at the this is like 500。

000 or something like that so。Its in the middle of the list were inserting like a single integer in there。

😊，Now this insert operation is ordered in。And why it is orphain。

 you should actually read about it or have some basic understanding of why it is orphain。



![](img/ef4832726233ec4027a61e30919d4879_57.png)

And this order in operation is taking like 56 milliseconds， So which is like。Almost a thousand times。

 I want to say slower than the Atend operation。

![](img/ef4832726233ec4027a61e30919d4879_59.png)

And。Let's look at some other operation here。This one。So now we want to convert our list into a set。

And this conversion operation is going to take order of n。 So in here。



![](img/ef4832726233ec4027a61e30919d4879_61.png)

And this converting a list to a set is taking like。1。5 seconds almost。 so again this is order of n。

And if finally， we have another order of one operation where we are adding or inserting a number into the set。

 and that's taking 0。13 millisecond here。So the point I'm trying to make it here is this you should have an understanding of the worst case complexity or like。



![](img/ef4832726233ec4027a61e30919d4879_63.png)