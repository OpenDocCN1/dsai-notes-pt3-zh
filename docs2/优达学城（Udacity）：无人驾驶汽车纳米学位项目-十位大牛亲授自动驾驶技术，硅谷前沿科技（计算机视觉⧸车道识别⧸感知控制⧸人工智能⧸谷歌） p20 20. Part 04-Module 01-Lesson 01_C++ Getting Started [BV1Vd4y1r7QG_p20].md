# 优达学城（Udacity）：无人驾驶汽车纳米学位项目-十位大牛亲授自动驾驶技术，硅谷前沿科技（计算机视觉⧸车道识别⧸感知控制⧸人工智能⧸谷歌） p20 20. Part 04-Module 01-Lesson 01_C++ Getting Started [BV1Vd4y1r7QG_p20]

Now we're going to go to C++ C++ is the language of choice for embedded systems like the stuff that runs in small processor inside the stuff driving car。

Now in the beginning， it'll be scary to see a complete different syntax。 a different language。

 almost go from Chinese to Japanese is hard， but as you get more familiar with a different syntax。

 you find out that the underlying tools are exactly the same that they do it in Python on C++ it's just a C++ one faster。

 So in this unit， we're going to turn you into a monkey into a robot so you're going to see things like written in Python and we're going to ask you to translate it to C++ so that you lose any fear of different syntax and become very。

 very fluid in jumping back and forth between two different programming languages and I promise you at the end of the class you find out they're basically the same。

 they're just written differently， but the underlying concepts are equivalent and that's a great way to understand programming languages。

😊，C++ is the language of self driving cars。 It's also a programming language that's a lot closer to what devices like the NviDdia Px2 understand than a higher level language like Python。

So if you want to get a job in this field， it's something you're going to have to learn。

And while C++ is in most ways， similar to languages like Python。

 it also has several features which make it different。In this student handed degree。

 you'll learn C++ over two courses in this course we will focus on all the elements of C++ that it shares with Python。

 variables， loops， classes and objects， etc， and in the next course we'll focus on some of what makes C++ unique。

But the angle of this course is pretty straightforward right working C++ code in particular。

 you'll be asked to translate the two dimensional histogram filter code that you wrote in Python into C++。

 and when you get that to run correctly， you'll have made a hugely important first step towards your eventual expertise in C++。

Now， before we continue， there are some basic housekeeping steps that you'll need to take care of before you start writing and running C++ code on your computer。

Follow the instructions we've outlined below before you move on。Now that you're all set up。

 it's time to start writing some code， but before we jump in。

 we should say a couple things about how these lessons are formatted， right。

 and the goal of this course is simple in some ways， translate Python code to C++。Now。

 there's a good amount you'll need to learn in order to do that。

 but most of it isn't very conceptually heavy。 Yes。

 writing C++ will require you to know the syntax for a for loop， for example。

 but you probably don't need a lecture on what a for loop is Sure， So with this in mind。

 most of the instruction in the next lessons will contain example code and text explanations And when we do run into some unavoidable piece of something new in C plus plus like piling or declaring variables。

 for example， part of the instruction， we'll draw on an interview I got to do with Alicia White。

 who literally wrote the book on embedded systems。 Yeah。

 why don't we show some of that interview now。So welcome Alicia。

 thank you so much for coming in today。 Hi， Andy， thank you for inviting me。

 So I have been trying to learn C++ I am not an expert myself。

 and the first thing I did when I was trying to learn this language was try to convert some of that histogram filter code we had written in the first course of of this nanod。

 I tried to convert it from Python to C+ and that was quite an experience。

 it was not easy but I think that code might serve as a good jumping off point for talking about what this language is Well。

 you let me look at some of it。 So I think yeah， we can talk more about it。

 so let's get into the details to the nitty gritty of the code， but before we do that。

 do you want to just high level what is C++ What's the difference between C+ plus and Python why do we need multiple programming languages。

😊，Well， there are some people who say you should learn lots of programming languages。

 You should learn different languages because they have different uses。 Python is fantastic for。😊。

Problem solving for prototypes， for figuring out what the goal is and how to get there。

But you don't necessarily care about what you're using to get there。

 whether you're using a Moped or a nice car。C++ on the other hand， knows what it's running on。

 it knows about processors， it knows about how it interacts with the world。

 and it's a very tactical language where it has its feet in the computer it's running on。

 it has lots of the Python features that help you implement solutions to your problem。

But it also has ways to do it really fast， and that is the real reason why C++ is important to this sort of development。

So in researching some C++ stuff， I kept seeing this term static typing and language is being referred to as statically typed and C++ was one of those。

 Can you explain what does it mean for a language to be statically typed。When you go to C++。

 you're going to have to tell the compiler what kind of variable you want。

 whether it's a floating point variable or whether it's a character or string。

You need to know ahead of time whether you want a lot of precision like a float 64 or double could give you。

And you do this because it tells the compiler a lot about what it has to do。In Python。

 you don't have to do that。 you can have the variables be whatever they want。

 and they can change halfway through。 It doesn't matter。

But if you declare a variable float F in C plus plus， it has to be。

It has to be a floating point number for as long as F exists。Now， if you go to a different function。

 you can have an int F and a string F， although that seems silly。

 It doesn't matter outside the scope of the name。But inside the scope， it has to always be that type。

 And so it is a fixed type。 It's a static type， and that's what statically typed means。

So when designing a programming language， if I'm making my own programming language and I have the choice to go with a statically typed language or a non dynamically typed language。

 I think， is the phrase， how do I make that trade off's what's going on in making that trade off Staally typed language is more likely to be faster because you know ahead of time what you're doing。

A dynamicynaally typed language is likely to be more flexible and to let the user decide later what it was they wanted to decide。

 So it's a flexibility versus speed trade off。 Okay， so I think I have some understanding of this。

 but。If， for example， doubles are more precise than floats， why not just always use doubles。

Because they're bigger。It doesn't really matter if you were doing a small program。

 but if you needed to do a program where you had a million variables。

Douubles are twice the size of floats。And our computers have so much memory now。

 It's amazing what comes in our laptops。😊，But when you go to an embedded system。

Sometimes you don't have the memory。And you need to be aware of your limitations of your resource constraints。

 so you choose to use floats or you even choose to do fixed point。But a self driving car。

 I can put a lot of computer into the trunk。Every computer you put into the trunk is a power of waste。

 which means it's another mile it can't drive。You said the header files。

 they have function declarations。 they can have a lot more if you wanted to define a type。

That was the grid type。Instead of using this vector vector float because you get kind of tire of saying that。

 I was writing that a lot。 Yeah you could instead do type def vector vector float grid T T grid is usually sort of indicated it's a type。

And then you don't have to type it。 You can just do T grid everywhere。 would have been nice。

 It would have been nice。 much lesstyping。 It's good to know。 you know。

 any time you find yourself really typing the same thing over and over again， it's。

 there's a good chance somebody solved this problem for you。 finding it's not as easy。

 but there's a good chance it exists。 Okay， Well， thank you。😊。

Something else I noticed interesting about。Methods or functions in C++。

I actually found this one out by accident when I wrote two functions that had the same name。

 let me see if I can find them。So I wrote two functions that were both called close enough and one was meant to compare two floats to you know solve for that like floating point。

 they're close， but they're not exactly equal。 I wanted to return true if two floats were close enough。

 and another was for two grids and I wanted to return true if those were close enough to being equal。

 which just meant that all of their actual values inside were close enough。

And I was actually able to do this， I couldn't believe this worked。

But I wrote close enough once or took to vector vector floats or grids and another version or took two floats。

 what's going on here， Why is this allowed Well， the compiler doesn't see those as the same thing。

 They have entirely different signatures。 I mean， if you signed something and I signed something。

 they would be different。And what it does is it takes these functions with their types that it takes。

 and it takes this close enough vector vector grid。And it makes that all part of the function name。

 You don't see that。 but if you， if you looked inside the compiler。

 you would be able to see where it started to treat all of the functions。Defined。

With the name and all of their arguments so this is something called overloading。

 it can be very useful if you want to hey， have a function that is close enough on floats or close enough on integers。

 you don't have to do everything specifically different you don't have to have lots of different function names you want it to know if it's close enough This is a feature of C+ no it felt really it was nice to be able to do it that way。

 So what is a function declaration and why is it important。😊。

A function declaration has multiple pieces。 And this is a little easier to look at encode code。

 So maybe let's look at your test normalized function。 when you look at just the way the。

Function is defined。 There's the bo， and then the test normalize in the open print and the close print。

And that bo says that it's going to return true or false。Very similar to Python。

 you can return whatever you want， except in C++ you have to tell it the type you're going to return。

has some advantages。 For example， in Python， if you accidentally returned just the row instead of the whole grid。

 it wouldn't tell you， you wouldn't know until。It ran， and there was an error。

 maybe three hours into what you were doing。 It would suddenly get to a place in the code。

Where there was a bug and you wouldn't know。But C plus plus， it tells you right away。

 you can't even compile if you didn't return something and return something of the right variety。

 Something I do in Python a lot is actually forget the return statement entirely。

 And then I' am working with a nu type object forever。

 and that's actually can be a really hard bug to debug。 so I can see how this might be valuable。

 exactly， you're at least guaranteed that the parts fit together correctly。

 not necessarily that they do what they're supposed to do， but that they fit right。

 the Lego blocks go together。😊，And that you didn't forget one。

 It's so easy to forget the return or to return just the wrong thing because you were thinking about something else。

Hopefully C++ has a few safety checks for you Okay so with the test normalized function。

 we had the return type pool， the name test normalized open and close parentheses。

 but I imagine this isn't the total picture because this function didn't take any arguments。

 It's true。 And if it was in a header file instead of that open curly brace。

 you would have a semicolon to say。This is the function declaration instead of the definition。

And if we wanted to take arguments， it would be in those open parentheses。 Take this other function。

 normalize where you you have this kind of complicated signature function signature where you have vector vector float and then normalize and vector vector float。

And what that says is that you want to return this vector vector so the grid of floats。

And you want to normalize。 that's just your function name。 And then inside， you have another grid。

 when you switch it so that you are not necessarily passing it the same way and copying it。

 you'll find that you don't need all of those parameters。 So I guess。

The misconception I had was that。The unique identifier to the function was the name close enough。

 but it's not。 It's the signature。 It's this whole。 It's the， the return value。

 the name and all the inputs in their types。 Yes， okay， that's helpful， good。Great job。

 you've reached the end of the lesson and you don't have to memorize all the things you learned here and you can look them up。

 but it's good that you get an understanding of how functions work and C++ and similar constructs。

Pad yourself with the shoulder， okay， you got to this point and then tomorrow morning。

 let's forge on。