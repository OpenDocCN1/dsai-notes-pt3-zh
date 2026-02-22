# UCB《数据科学中的计算结构｜CS 88 Computational Structures in Data Science 2022》中英字幕 p14 CS 88 Spring 2022 - Lecture 14 - 3_9_2022.zh_en [BV1516iBfEVY_p14]

![](img/f49e75b250880623fa487fffc43ba1ff_0.png)

![](img/f49e75b250880623fa487fffc43ba1ff_1.png)

Okay， so that's loud， all right。是啊。Computer。对。But a little bit。 Okay， cool， I think。See。嗯。嗯，系。嗯。



![](img/f49e75b250880623fa487fffc43ba1ff_3.png)

![](img/f49e75b250880623fa487fffc43ba1ff_4.png)

![](img/f49e75b250880623fa487fffc43ba1ff_5.png)

嗯。Okay， cool projector or the second projector， I guess is warming up， but we'll go ahead and。

And get started， so today we're going to talk a little bit more about object tound programming。

And again， the ideas of inheritance and the topic of special methods besides in it that we're going to talk about today。

Those will not explicitly be on the exam next week， but。

Hopefully they are helpful topics that give you more practice with object or programming so you know don't。

Don't fall asleeper anyway just quite yet。So just other announcements， mostly about the midterm。

So yeah， next Wednesday evening， if you're looking on Ed。

 there was a form linked for anyone who needs additional time。

 if you need to take the exam remotely for any reason。

 one thing that we will ask you to do is we will ask you to wear masks during the exam。If， of course。

 you're uncomfortable with you， taking the exam in person for any reason。

 you can take the remote option， which will be proctored via Zoom。

But same exam taken online instead of just taken in person。

 So won't be any different there because of the timing of the midterm next week， it makes sense。

 I think， to update the lecture schedule。 So Monday's lecture will be all Q And A style review。

My plan is not to prepare that much for Monday's lecture and for everyone who has questions about the midterm to come to Monday's class with questions we can work through some examples and whatnot then Wednesday we have typically canceled lecture the day of the midterm so use that hour to study to relax to get food you know whatever you need to do since it may be a longer day than normal and then after that will be a spring break and we'll continue on with the next topics when we get back from the spring break so yeah。

Other than that， things should sort of continue on as normal。So。

Getting back into object rate programming， one of the cool things。

About object or programming in Python are some of the ways that Python gives us tools to build code。

That。That allows us to feel more like natural python and and in doing so。

 we also get to understand a little bit more about how python works under the hood so some of these techniques are。

We're not going to try and have you memorize all of the potential special things that Python does。

 but it's good to understand what's there and to think about how we could use these to build our own programs that work better so Python has this construct what they call magic methods and these are the things that end and start with double underscores so。

We've seen the init method and that's perhaps the most important one。

 but today we're going to look at a few additional ones subtraction the stir method and the wrapper method for our objects and the point here is just to look at the kinds of controls and additional functions that。

Yeah， that sort of exists that Python gives us。Of course。

 the most important method here is in it and this is the method by which if we avoid。

 we don't really have objects。In it itself is not the most interesting。

 but it sort of sets up the idea that in Python。As with most programming languages。

 there's machinery and tooling under the scenes or behind the scenes that when we say base account of something。

 Python goes in， finds a special method to call and then continues on executing the rest of our code。

And it is a special method， but it is of course， not the only one。Within our programs。

 we can define a lot of additional special methods and we're going to look at two of them。That。

Sort of control how we inspect and how we view。Our our objects。

So one of these is called Reper and the Reper method in Python is something that actually exists for every object。

 even if we don't implement it， Python will come up with a Reper method for us。

And the Repper method is the method that actually controls what that string when we saw something like base account defined at Ox 1 blah。

 blah， blah， blah， that method was Python's default Reper method that gave us some basic information about the objects that that we have so in our own classes now that we know that the Reper method is a thing we can build our own method to better control and understand and inspect。

 debug objects so。On this slide we're continuing with our account example。

 we have a Re method which starts and ends with angle brackets and it gives us the account number and the account name in the wrap method and the goal of our Re method is to provide some unambiguous and distinguishable form of our object that can be used later on so one of the things that we don't get a chance to experiment with too much in CS 88 is this idea of。

debugging really large programs or reading through what's typically called a log of all the things that happen in your program and the Re method is meant to say。

 if I'm trying to figure out what the heck went wrong。

 there's some kind of information that will tell me very clearly how this one object over here is different from this one object somewhere else。

And in Python's case， you know， the programmers decided that， well。

 the best way to do this is to stick some information about the computer's memory in the wrappper method。

 but that's often not the most helpful so we can define。Our own wrapper methods， so okay。Let me get。



![](img/f49e75b250880623fa487fffc43ba1ff_7.png)

Well， things out of the way。We'll come back to our point and the sub method in a bit。嗯。Yeah。

 so in this file， the base account class right now is just named count to make things a little bit easier。

But our count here has a wrapper method so。Same based on the slides。呃， a。

Denoting with ankle brackets to suggest that this is sort of a particular representation of our object and in our slides here。

So what we're going to do is run through this code and let me。



![](img/f49e75b250880623fa487fffc43ba1ff_9.png)

Actually。Okay， here we go。So Python 3- I 14。So CS 88 right now is going to be an account。

And our account takes in a name。And。Let's give us a lot of money。So when I evaluate CS 88。

 what Python is going to do is say， okay， there's some object here。

 how do I display that object to the terminal。In a way that tells the user what's going on。And this。

This action right here of saying evaluate CS 88， turn it into something displayable is what the wrappper method is used for。

 so whenever I say。You know。Like one。Plus four I get the value five。

 the wrapper of a number five is of course just the value because five is five there's not anything particularly interesting about it so some objects。

 the representation is just their value in Python but something that we make on our own like an account that could have a name。

 it could have a balance right it could have perhaps an opening date。

 our accounts have an account number we could imagine that they have any number of really sort of complicated perhaps properties。

And so Python allows us to define these methods， this one happens to be called Reper that says this is sort of the internal representation of our account so we have base account。

The account name。And the current balance if I say oh no， I'm not sorry， that is the account number。

 which I probably should have made a different string。

 but I could now make a new account called data eight。Well， we don't have a data nine but。Count。

Data 8。Data a's a good class， but they're like not as cool as us so they only get $100。

And when we evaluate that now we see that we have data eight as the name and the account number as 101 so again。

 we're continuing with the same example here where in our code。



![](img/f49e75b250880623fa487fffc43ba1ff_11.png)

We have。An account number defined at the top of our count class。



![](img/f49e75b250880623fa487fffc43ba1ff_13.png)

And。Why is this useful to think about how we evaluate objects。

 it's because if I am looking at a piece of code right and。

I'm trying to understand what it is having a clear form here that is unambiguous is really useful that this account number in particular tells me that these two things should be。

You know， should be different objects， so maybe perhaps I say thing is equal to CS88。

Thing is perhaps。The worst variable name that you could imagine because it tells you nothing about what that object is。

 But if I evaluate thing， I still have a representation。Of my object。

 that is a little bit more clear about what it is。 And importantly， if I go over。And。

I'm now going to run。The oh not that way， that way。In this terminal， I'm going to open up。

The lecture 13 example for Monday that doesn't have this this representation。

 so if I say CS 88 is equal to。In this case， it's base account。Of CS 88。And some money。In this case。

 right， if I don't define that wrappper method， what Python decides to give me is saying main。

Main itself is another special method in Python base account object at and then sub memory address。

 so this is definitely unambiguous in the sense that if I now say data eight。Is it equal to。

ABase account。Of data8。Right， what's going to be printed here， this number。

And this number are different pieces of information but。

As a programmer and really more importantly like as a human。

 this is kind of a terrible way of saying， are these two things the same or are these two things different because what's communicated by the string of numbers is not super useful and so。

What we're doing with some of these representation methods it's trying to clear up that format and this is just one of the tools that that Python gives us。

And so that's a really useful kind of method that you'll see on some objects。However。

 Python likes to make things a little bit complicated as most programming language do。

 so there is a second type of textual representation for objects that exists and this is the ST method and this is one of those cases where if you've wondered why sometimes in the interpreter。



![](img/f49e75b250880623fa487fffc43ba1ff_15.png)

When you evaluate something， you don't see a result， but if you print that result， you see none。

 this is what's happening behind the scenes is the stir method in Python is another text format。

 but this is what happens when we call print so if I over here say print。



![](img/f49e75b250880623fa487fffc43ba1ff_17.png)

C S 88。啊。

![](img/f49e75b250880623fa487fffc43ba1ff_19.png)

What is my。Well， why？That I define the same method here， that's not useful。All right。

Now I have to remember what the heck。是。呃。All right， we'll do something else we'll say。Okay。

 so if you define your print or your ST method and your wrapper method to be exactly the same。

 that's totally valid， although it makes a very useless demo。嗯。So。See， self that balance。



![](img/f49e75b250880623fa487fffc43ba1ff_21.png)

That should all be correct。So now what we'll do is we'll reload our program。And will'll make。

A new account C CD8。And we'll make a new where to data echo data it account。

 So now now here's what we should see。 So if I say CS 88 I evaluate it I get a wrapper method if I type print。

Of CS 88。What I now get back is a different form of representation。 This format is designed for。

For humans in a sense to debug to view something to give information that they think is useful so in some programs these are different and some programs are the same。

 but in python these are just the kinds of methods that exist so if I。Again。

 say print of data 8 this time。What I'll now see is that data 8 is a base account。

 it still has an account number， but now in this format I've decided to show the balance。And。

One of the things that you'll see hopefully in the anT project， which will happen after spring break。

Is that？The information that is contained in these methods is going to be a useful tool for debugging and understanding what's going on in in the ants project you won't necessarily need to work with I believe we usually only give you the Reper method that's probably all you'll need but it is useful to have a sense of as I'm building a program as I'm thinking about the objects what is the information that someone might want to know so in this case for a bank account perhaps a balance attribute is useful。

To expose but but you don't have to so those are the first two magic methods that that we're really going to see in python and what's just interesting about Python is that behind the scenes right it is deciding whether or not you say print。

呃。Let's say CS88。Or if you just evaluate which of those methods to call。

 so the fact that print calls our STR method， when you evaluate is Reper。

 that's just a little implementation detail that you know you sort of have to know in Python or to look up and I'll show you the list in a moment。



![](img/f49e75b250880623fa487fffc43ba1ff_23.png)

![](img/f49e75b250880623fa487fffc43ba1ff_24.png)

But these two methods sort of give us control over over different kinds of things。

 so before we continue on questions about either in the room or from zoom what these two methods sort of do yeah right up front。

Yeah。

![](img/f49e75b250880623fa487fffc43ba1ff_26.png)

You mean you mean like when we deposit money or or the。



![](img/f49e75b250880623fa487fffc43ba1ff_28.png)

Let me go back to terminalmoil do you mean like this value right here or？家。Oh yeah。

 so so the value that's being increment over here is the account number property， so if I say data。8。

Dot。Account。Number， let's see， is。So this is the property which is。

Set whenever we make a new account so。Our main class right now is called count and you'll note actually that the。

The class itself， if we evaluate it。Is missing a its own re method， which we typically never define。

 but this account class。Has a property called。Account number seed。

And every time we make a new account。This value is used as the value that becomes。

The account number in in our new account， if I say CS 61 B is equal to an account。again。

 I'll call it CS 61b。With $100 in their account。And I print CS62 and B。

What I get back is telling me that this is a base account from CS62b with the account number $1002。

 a balance of $100 and all of this comes from the fact that when I make a new account。



![](img/f49e75b250880623fa487fffc43ba1ff_30.png)

The value that I'm looking up is this class variable called account dot account number see so it's something that lives outside of each object when I say account number seed account do account number C plus equals one。

 it's changing a value。That exists not in our individual object， but in the class itself。

 and that allows us to have some information which is shared across all of our objects and some information which just lives within a single object。

 so this account sort of tracks how many accounts have been opened in a sense。这。Yeah。

 so you can think of this as as just a way for。This class to keep track of information about potentially all of the existing accounts in CS61 B。

 if you continue on to take the course， what you'll also learn is that oftentimes in this case we might instead of making an account directly we might have a separate class called a bank which manages all the accounts so there's a lot of different ways that we could keep track of this information by using multiple classes we'll talk a little bit about using inheritance which typically wouldn't help in this case but。

There's different ways that we could organize our data， but in this case。

 this is just a counter essentially that gives us a unique number for every account that is created。

Yeah， good question other questions on the account example so far。Questions on zoom。Not yet， okay。



![](img/f49e75b250880623fa487fffc43ba1ff_32.png)

不什一次。就。So magic methods in Python do a whole bunch of stuff the point here really is not to tell you to go and memorize an exhaustive list。

 but to be aware that a when you see something that has double leading and ending underscores that there is a specific meaning behind that so after the midterm and after spring break。

We'll actually see a couple more examples when we get to another topic called iterators and generators but。

呃。Youre going okay， there we go。嗯。But in Python， if you open up the Python documentation again。

 which is sometimes a little bit wordy， but generally quite helpful， there is quite a long list。

Of methods on this page that are defined and that have specific meanings。

So some of those are built into to just Python itself and with objects。

 let's see if we scroll all the way down here。Don't know why you can't link to a specific section。啊。

Yeah， so down here there's a whole bunch of different things that if you're curious。

 you could look at and define so what happens when you want to delete something。

 there's descriptions of our Reper and stirR methods。

Different formatting what is also particularly interesting in Python as a tool is it gives us things like all of our standard operators as as methods so less than greater than comparisons and some of those you can。

Sort of intuit from the name what they do。 So things like addd and sub are built in methods or。

Are defined methods that map to the built and operators like addition and subtractions。 So in our。



![](img/f49e75b250880623fa487fffc43ba1ff_34.png)

In our file here。We have our version of our point that we did with the abstract data this time implemented。



![](img/f49e75b250880623fa487fffc43ba1ff_36.png)

As a class， so if I go back to terminal， we can just demo what why we might want to do this so actually if I say origin is equal to point。



![](img/f49e75b250880623fa487fffc43ba1ff_38.png)

Zero， comma zero。And we said campus before。With something like point。8。Nine， although again。

The values that we use don't necessarily matter in this case。

If we don't have any special methods in Python， what we might do is say origin。嗯。Dot subtract。

Some oops， new。Some particular not point。If we subtract two points from each other like we did a few weeks ago in the abstract data types lecture。

 we could write some method called origin dot subtract， this will take the x values， the y values。

 subtracting from each other， it returns a new point。And in this case， one thing to note and why。

 again， this is another pretty good example of why representation and STR methods are useful。

Is that this doesn't really tell us anything about the subtraction that just happened。

 but this is a valid point so I could say you know dot x and zero minus8 is of course negative 8。

You know， I could get negative nine for the y value。

 but what our methods allow us to do is really write code， which is。

Hopefully more natural in many cases， so I could say origin minus campus。In this case。

 what I do get is。Is a point back。 It is a new point。

 but allows us to use syntax and structures which feel a little bit more native。

 And so one of the goals here of object printed programming is to start to build。

Ways of using programs that makes sense so not every method necessarily or not every type of object is going to say I need an addd method or I need a subtract method or I need a multiplication method right。

 but sometimes。Yeah， sometimes it makes sense with our classes to to define them。

 So all that's going on here when I say origin。

![](img/f49e75b250880623fa487fffc43ba1ff_40.png)

Minus campus。Is that this finds a method called sub so it's looking for origin dot sub and the second argument is the thing on the right side of the minus sign and Python when it sees a minus B。

 it translates that into the syntax of。Of our magic methods， so we should actually be able to do。



![](img/f49e75b250880623fa487fffc43ba1ff_42.png)

Something like。If Python will let me。I believe this should work。

Yes it will so we can't really tell that the values are the same。

 but what Python is doing when we have magic methods is essentially turning one syntax which is nice and readable into another form of syntax which is a little bit less pleasant to write so that's why magic methods exist in Python they're really useful tool。

😊，And yeah， that's all I have to say about those any questions on on the idea of using built in magic methods again。

 don't memorize the whole list， but they're useful to understand when you come across them how to look them up and we'll see a couple of uses in a few weeks as well。

 but any questions so far on。A these。Cool， so。

![](img/f49e75b250880623fa487fffc43ba1ff_44.png)

啲。The last example and we'll spend a little bit more time with this after the midterm that we want to talk about is this idea of inheritance so when we build our objects。

Our goal is always to build in some structure and code that reflects something about。

The relationship that those objects have and you could sort of say real life or in a way that we want to represent them and so inheritance is a tool that will allow us to take the idea of let's say one account and extend that to multiple types of accounts and in that process what we'll learn is how to manage that relationship and we'll learn a particular tool in Python which is a method called super。

That allows us to access a classes' parent class， so we'll see examples of what that is。

When we define a new class or when we use inheritance what we're going to be doing is defining a new class that takes our existing class and overrdes some particular attributes in general all of our classes should be。

Should be specializations of the parent class that whenever。

 let's say go from account to checking account， that a checking account is a more specific version。

 a really common example is if you think about biological taxonomies right。

 kingdom order phyellum class， species， whatever it's been a while since I've been in a biology class。

 that each of those things takes a bigger concept right that you have a kingdom and a phylum is a refinement where each things get more similar all the way down to an individual species。

Where each level gets a little bit more detailed and typically in our class structure we're going to refine and modify the specific type of structure so another sort of generic representation that we might have is to think of anything that's a vehicle any type of object that can get you from point A to point B。

 we could say is a vehicle of some sort。We could break that down into so many different types of categories。

 but in this chart we might say you have vehicles， you have vehicles that have wheels and of course wheeled vehicles could be cars and bikes and trucks and scooters and all other things and within a car you could then have multiple different types of cars and so inheritance will allow us to take something generic specialize that and reuse the code so。

How does this work in Python well in Python when we make a new class we now have this additional option where after the class name in parentheses rewrite what the parent class will be and we'll think about and see how that works。

In our example today what we're going to do is take our account right now our accounts have had a name。

 an account number and a balance。And now we're going to extend our basic account to a checking account and a savings account。

And when we do this， we don't want to re implement all the details of our account。 We just want to。

Say I'm going to take some of the properties of the parent account and refine them so we say our class checking account inherits from our class account。

And inside there， this allows us to do a couple different things is we can still reference the parent account by its name。

 so account dot in it of some method。And and this can be a really nice and explicit way or Python gives us this new keyword called super and what super will do in Python is it says find me the object which is my parent so perhaps you have a ton of code this won't really happen in CS 88 in CS88 you can almost always swap between these two styles。

Because the examples that we give you are you know are fairly constrained， but in big systems。

 you start to to use super a little bit more， but you say。

When you use the word super Python will try and figure out what is the right parent class？

For my object so in this case with our checking account it's always going to be that account class。

 and so this super method just translates the。呃。Calling it translates this into the that account class and once we have access to our parent class we can use all of its properties so a really common thing to do is say super dot in it of some parent account and what that will do is it will set up all of this stuff that a normal account has without rewriting the code and so。



![](img/f49e75b250880623fa487fffc43ba1ff_46.png)

The best way to do that is to take a look right now at what is going on in in our two different objects。

 so this is our account class， we have an our in it constructor。

 we have a name we set an account number， we increment。



![](img/f49e75b250880623fa487fffc43ba1ff_48.png)

The account number seed for all of accounts that are created。And then we of course。

 set our initial deposit。When we scroll down to our checking account。

You'll notice that what we do here is we call our account class and we call in it with the same argument self name and initial deposit。

And。What this is doing。Is it's allowing us to reuse all of that code。

In the same way that makes sure that every time we make a new account。

 we still have the proper account number set up， notice that there's no line that says self dot account number equals whatever。

 but by calling this init method we take advantage of the fact that we're using inheritance and in this case。

Our account is fairly simple， right， This is。About four lines of code。

 it's mostly just setting some properties， but you could imagine that in you know in a real bank so to speak。

 this might be quite a bit more complicated。 So what does this look like in practice。嗯。

Where did I scroll too far here one thing to note is that when we say capital account in it we have to pass in if we use super we don't but what I'm going to do now is make a new account called checking。



![](img/f49e75b250880623fa487fffc43ba1ff_50.png)

And this is going to be。A new checking account。This can still be called CS88 and it can have an initial balance of let's say1000。

And this time when I evaluate our checking account。What I get back is。

A wrap method that says this is a checking account， CS88， the account number is 1003。



![](img/f49e75b250880623fa487fffc43ba1ff_52.png)

And what was being taken advantage of here is all that logic that existed in our。In our main account。

U。What we can also notice although it's you kind of have to trust me because I can't put all the code on one screen。

 but I never defined a wrapper method that was new to our checking account so if I and I never defined a stir method either so if I say print。



![](img/f49e75b250880623fa487fffc43ba1ff_54.png)

I say print of our checking account， I still get a checking account。

It says CSC 81003 balance $1000 these two methods， even though I never defined them within our checking account。

 because they existed on our parent class， Pythlon went ahead found the right method to use and called it and so the real advantage of inheritance is that we get to specialize。

The the behaviors of a particular kind of object， but also leverage the fact that we have all of these attributes。

 all of these methods which might be shared between between multiple objects and if we have just an account and a checking account。



![](img/f49e75b250880623fa487fffc43ba1ff_56.png)

You know perhaps this isn't the most complicated system。

 leveraging inheritance might not bias that many lines of code that we're saving。

 but as we add things like a savings account，Where a savings account might end up having something where it earns interest in a bank and the more money you save the more interest you earn。

 you can start to refine some of those properties between our two accounts。



![](img/f49e75b250880623fa487fffc43ba1ff_58.png)

嗯。That's really sort of the main goal there and in each of our methods primarily here our constructor method we get to choose whether to call super whether to call count but anywhere within our count class we get access to the super method so this is really just mostly for debugging but I can say here。



![](img/f49e75b250880623fa487fffc43ba1ff_60.png)

![](img/f49e75b250880623fa487fffc43ba1ff_61.png)

![](img/f49e75b250880623fa487fffc43ba1ff_62.png)

Checking。诶。And I can ask to show our superclass。And when I call this method。

 this is just Python's own representation of what I call super。

That it tells me what the super account or excuse me it tells us the representation of of the super account or excuse me of the super class and I can then access things like。

Can I not access？嗯。Actually。That's's not going yeah。Oh okay yeah。

 what Python does is actually a little bit weird with super。

 it does a bunch of things behind the sand so this is not the exact object itself。

 but it is a way of looking at the way that it inherits a class。



![](img/f49e75b250880623fa487fffc43ba1ff_64.png)

Super super gives you basically in Python a special kind of class that。



![](img/f49e75b250880623fa487fffc43ba1ff_66.png)

That is set up in a way where you don't have to handle passing self that you can access all those properties soon。



![](img/f49e75b250880623fa487fffc43ba1ff_68.png)

That's the advantage of using the word super， although I think for most types of work that you might do。

 directly referencing the parent account can be a little bit more clear in this case。But you can see。

 yeah， actually， before we continue on， questions on this idea of a checking account。



![](img/f49e75b250880623fa487fffc43ba1ff_70.png)

![](img/f49e75b250880623fa487fffc43ba1ff_71.png)

That。And sort of handle or inherit from its parent methods， yeah。必须。

Yeah so this is a good question what if you so the question is for those on zoom。

 what if you have two different parent classes that have the same kind of arguments？



![](img/f49e75b250880623fa487fffc43ba1ff_73.png)

This is and I'm actually just going to see if I can find the best diagram。嗯。

So one thing I'll say is I think this article' is okay this gets into a topic which you'll spend a lot of time on and CS61b is dealing with multiple parent classes in CS88。

 we're only going to have the single linear chain where the closest parent is the one that Python uses。

 but Python has this entire complex structure。Of resolving conflicts between multiple parent classes and so this is often referred to as multiple inheritance。

 no I don't。Thanks， okay， that's a problem with generic websites but。

There's there's sort of this whole pattern that Python will use to resolve things。

 so the details aren't。AndIn some ways they're not terribly interesting if you program a lot in Python they are worth understanding。

 but for the purpose of this class， things will hopefully just always resolve to the most recent parent class that you've defined I don't think we give you any。

Any examples in projects or homework where there is。



![](img/f49e75b250880623fa487fffc43ba1ff_75.png)

You know， sort of an ambiguous type of thing that could be resolved。

 but if you look through if you look through the Python documentation the examples online there's some interesting you know problems that that can arise。

But yeah， that's a good question， other questions about classes and parent classes。



![](img/f49e75b250880623fa487fffc43ba1ff_77.png)

Or， so。Cool。That。

![](img/f49e75b250880623fa487fffc43ba1ff_79.png)

Is okay， yeah， so in terms of new content， that's all that I think is really know the two things to know are defining a parent class here。

And then using using super to override something。 So what is also worth just mentioning in our example。



![](img/f49e75b250880623fa487fffc43ba1ff_81.png)

Is that we can now。Let's move Zoom out of the way for the last few minutes。

Is if I make a savings account。Again， we can call this our CS88 savings account starts with another balance of $1000。

Is that what well often see in our。In our sets of inheritance。

Is making sure that as we specialize a class。We also update。Other kinds of properties。

 So in this case， our savings account has a wrapper method。Which now instead of writing in。

Just the account number and the account name， it includes a property unique to our savings account。

 which is this interest rate so for our savings account we might include the interest rate inside the representation string。



![](img/f49e75b250880623fa487fffc43ba1ff_83.png)

And again， this file just。It uses the format string syntax， which is I think a little bit cleaner。

 but just another way of combining strings together。And inside our classes。

 sometimes what we might do is refer to another method if we want to so I could say self。

repper would just call that method anywhere else， so our savings account has you know a little bit of a weird demo in that I can say print。



![](img/f49e75b250880623fa487fffc43ba1ff_85.png)

savings。You get the same result back in this case， but we've defined we've defined that behavior so yeah that's really the gist of what we want to do with objects next week you know lab and homework will be delayed or you'll have a little bit more time because the midterm so we won't pick up playing with a bunch of object render programming until。



![](img/f49e75b250880623fa487fffc43ba1ff_87.png)

After the midterm， but keep this in mind， this will play pretty heavily into the ants project。

 which is I think one of the more fun projects if you take computer science or data science classes you'll get to do it's a riff on the game plants versus zombies so hopefully you can look forward to that and otherwise that's it for today and yeah you can have a couple minutes back。



![](img/f49e75b250880623fa487fffc43ba1ff_89.png)

Thanks everyone。Yeah。

![](img/f49e75b250880623fa487fffc43ba1ff_91.png)

![](img/f49e75b250880623fa487fffc43ba1ff_92.png)

See you Zoom。