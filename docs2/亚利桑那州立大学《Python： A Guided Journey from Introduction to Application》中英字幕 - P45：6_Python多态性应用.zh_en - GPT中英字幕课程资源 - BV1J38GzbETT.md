# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P45：6_Python多态性应用.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/e149be637eb644059570ffb8fb33667b_0.png)

Welcome everyone， today we're going to talk about polymorphism and Python。



![](img/e149be637eb644059570ffb8fb33667b_2.png)

So to start off， we're going to discuss what polymorphism really is and then how does it relate to Python？



![](img/e149be637eb644059570ffb8fb33667b_4.png)

So。When we start talking about polymorphism， we can break it down into two different words。

 First word is poly， meaning many， and then we have morphism that means different forms。

 And so what we're talking about in this situation is is that we can have many different。



![](img/e149be637eb644059570ffb8fb33667b_6.png)

![](img/e149be637eb644059570ffb8fb33667b_7.png)

![](img/e149be637eb644059570ffb8fb33667b_8.png)

![](img/e149be637eb644059570ffb8fb33667b_9.png)

Situations where we're callinging the same method over and over again。

 but maybe we have different forms of how the method operates。 as you can see here in the example。



![](img/e149be637eb644059570ffb8fb33667b_11.png)

I've got a class called Purruit。I have a definition of calories。And here， I said。

 not implemented error。 Please use the calories in your method。

 And I'll explain what this does here momentarily。

![](img/e149be637eb644059570ffb8fb33667b_13.png)

Okay，Because this is referred to as an abstract method。Next I grab my apple。

 oranges and banana fruits。

![](img/e149be637eb644059570ffb8fb33667b_15.png)

Each one of them has their own method called calories。

As you see here and each one who has a specific message to print out， Apple has 95 calories。

 an orange has 45 calories， and of course bananas have 105 calories now you can go and use Google and verify that for that because that's exactly where I got those values from。



![](img/e149be637eb644059570ffb8fb33667b_17.png)

![](img/e149be637eb644059570ffb8fb33667b_18.png)

And then of course， I've got a definition of fruit calories。

 which basically I'm just going to call cow do calories。



![](img/e149be637eb644059570ffb8fb33667b_20.png)

So the first thing I want to do is talk about this thing called an abstract method。 Now。

 an abstract method basically of says that any。

![](img/e149be637eb644059570ffb8fb33667b_22.png)

Thing that I do as far as a class， and I'm calling the parent of fruit。



![](img/e149be637eb644059570ffb8fb33667b_24.png)

If this calories did not exist inside of this method or this， this method or the class。

 it would require that I make that method。

![](img/e149be637eb644059570ffb8fb33667b_26.png)

![](img/e149be637eb644059570ffb8fb33667b_27.png)

And I can show you an example of that later on down the r。



![](img/e149be637eb644059570ffb8fb33667b_29.png)

So as you see here， we've got a1 is equal to apple， so I've created an apple。I've created a banana。

And I've also created an orange。Now， if I go to fruit cow and I'm passing in a1。

 meaning that I'm just calling calories。By default。

 what it's going to do look at is the object that I'm passing in in this case it's going to look at a1。

 which is the apple and it's going to print the calories for that。If I go to banana。B1。

 it's automatically going to identify。Which one of the methods is tied to？



![](img/e149be637eb644059570ffb8fb33667b_31.png)

The object， in this case， it would have been banana。



![](img/e149be637eb644059570ffb8fb33667b_33.png)

And then of course， the third one， which is the oranges。

I see here that it's tied to my orange is going to print out the values of Apple has 95 calories。

 Ban has 105 calories， and oranges have 45 calories。



![](img/e149be637eb644059570ffb8fb33667b_35.png)

![](img/e149be637eb644059570ffb8fb33667b_36.png)

Now polyfmorphism in general is not very complicated。

 especially when you start looking at it in a simple form like this。



![](img/e149be637eb644059570ffb8fb33667b_38.png)

![](img/e149be637eb644059570ffb8fb33667b_39.png)

Now， if you did come from another programming languages like Java C++ C。



![](img/e149be637eb644059570ffb8fb33667b_41.png)

Polymorphism is amazing， it allows you to do something like this。



![](img/e149be637eb644059570ffb8fb33667b_43.png)

As you can see， I've got a class called Car。 I've got a method called car care。

 I'm passing in only the parameter of the object。The second one， the car， and I'm passing in color。

 my third one。I'm passing in the color and the type。Now。

If I wanted to print or pass or create an object of each one of these。

 I would do see one car that'll create a base object with the default settings。

If I wanted to validate one object meaning I'm just going to pass in the color， I would simply do c1。

car care and pass in blue。But if I wanted to do specify the color and the type， I could do C1。 Carca。

 red， and Ford， and I can identify which values I wanted to set。



![](img/e149be637eb644059570ffb8fb33667b_45.png)

![](img/e149be637eb644059570ffb8fb33667b_46.png)

Unfortunately， Python does not allow us to do polymorphism， and you can see from this error。

 so what I'm going to do is I'm going to show you a way to work around that to where you can do polymorphism with different methods inside of Python。



![](img/e149be637eb644059570ffb8fb33667b_48.png)

![](img/e149be637eb644059570ffb8fb33667b_49.png)

![](img/e149be637eb644059570ffb8fb33667b_50.png)

So what I've done here is on this side， I just kind of brought it over so you guys can kind of see how it was originally set up。



![](img/e149be637eb644059570ffb8fb33667b_52.png)

![](img/e149be637eb644059570ffb8fb33667b_53.png)

And now I'm going to move over to this。And kind of explain what I've done。



![](img/e149be637eb644059570ffb8fb33667b_55.png)

So now I've got my class car， I've defined my。Charac characters。I do this self。

 and then I've done the asterisk as。 The asterisk arg is basically an array that's going to be able to hold the number of elements。



![](img/e149be637eb644059570ffb8fb33667b_57.png)

![](img/e149be637eb644059570ffb8fb33667b_58.png)

Of items that I'm passing in。So if my length as， meaning it's going to check the array to see how many elements are in there。

 if it's equal to0， then I can define my color as none and type is unknown。



![](img/e149be637eb644059570ffb8fb33667b_60.png)

![](img/e149be637eb644059570ffb8fb33667b_61.png)

If my length is equal to1， then I can sit them say my color is equal to arg0。

 so whatever value that I passed in for that color would be identified in that situation。



![](img/e149be637eb644059570ffb8fb33667b_63.png)

![](img/e149be637eb644059570ffb8fb33667b_64.png)

If the link is equal to two， then I know I passed in two different values。

 and then I can go and assign the color and the type based off ag 0 and arg1。

So here's the examples that I' had used before。I set a default C1 for my car for my object。

 I called c1。carca， passed in no objects。

![](img/e149be637eb644059570ffb8fb33667b_66.png)

![](img/e149be637eb644059570ffb8fb33667b_67.png)

I printed out the color is equal to none and the type is equal to unknown。

Then I went ahead and did c1。carca， I passed in the value blue。My color is set to blue。

 my type is unknown。

![](img/e149be637eb644059570ffb8fb33667b_69.png)

C1 dot care car， I passed in red and Ford in this situation here。

 now you can see that I have the color set to red and the type is set to Ford。



![](img/e149be637eb644059570ffb8fb33667b_71.png)

![](img/e149be637eb644059570ffb8fb33667b_72.png)

So this is referred to as overriding。

![](img/e149be637eb644059570ffb8fb33667b_74.png)

Now overloading is what we were doing earlier in the previous slide。



![](img/e149be637eb644059570ffb8fb33667b_76.png)

When we're calling the grandmother， notice here I've got a definition of the constructor and then I've got get name。

Anytime you use the word super？Dot。This means that I am overriding the method。

And utilizing the one that's in the grandmother class and not specifically the one that's here in the mother class。



![](img/e149be637eb644059570ffb8fb33667b_78.png)

And so。Hopefully that's just a quick understanding of overloading and overriding。

 I think it's going to be better when I go and give you a demo of how this works。



![](img/e149be637eb644059570ffb8fb33667b_80.png)

![](img/e149be637eb644059570ffb8fb33667b_81.png)

So I look forward to seeing you in the demo。