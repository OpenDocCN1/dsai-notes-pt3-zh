# 密歇根大学《给所有人的Python课》课程3：《使用Python访问Web数据》｜python-network-data｜ - P10：10_02_02_特别访谈_Bjarne_Stroustrup_C++.zh_en - GPT中英字幕课程资源 - BV1Hu4y1e7WS

🎼你。🎼。🎼宝宝。🎼，🎼こ包。I was trying to characterize what is C+ plus particular useful for。

 what did I actually build it for。And what is its strength today after？Almost 30 years of revolution。

And so and also where's the limits to where it is。 So the way I see it is there's a core domain for C++ and。

That's what you call traditional。Systems programming， but that's not the right term。

 because it's just a style of language and a style of programming。 So I go a little bit further。

 I said， what is it that that that。Requires the kind of services that C plus+ has what。

Is the sum of all these applications I've been dealing with。

 where did would work and where was it essential， and I came up with the phrase infrastructure。

 and I roughly define it as if it breaks。Somebody gets hurt or somebody gets ruined。

These are the kind of foundational things in our systems that must work。f。

The system for the society to work。The the question I'm trying to phrase is what matters in those areas。

I've come up with some notions of compact data structures。

 very strongly typed interfaces for maintainingability and for minimizing errors。

A heavier emphasis on algorithms or。Random code because we need reliability。

 we need the stuff to be comprehensible， azable， we want to make sure that it's actually correct。

And so the paper I was writing come from from that kind of of thinking。

 what is the right style and what are the。Supports for that style we need for infrastructure software。

 for software that must be dependable， and we can get real examples。

Sort of the keys of some of the modern Albra systems， the basics of our foam system。

 the brakes in my car。😔，How do we make that dependable。

 how do we make sure that the space probes don't get the logical equivalent of your blue screen of death halfway to Mars where we can't send that。

A repairman， how do we make sure that they actually go into the right orbits？JPL lost。

A probe of Mars， because two groups。Had communicated nicely， they thought what in fact。

 one of them spoke imperial Me and the other one spoke the SI system， the MKS system。

 and the result was a misnavigation that sent。More than five。

10d million dollars worth of equipment into the wrong orbit。Not a good idea。

The work of 200 good engineers， lifetimes work。Down the drain。

And that could have been avoided by ever so slightly the improvement in the interfaces between the parts of that program。

 so things like that I'm interested in， so there's the core area where I think the facilities for C++。

 the kind of they're not perfect， the kind of things I would like the kind of things I work on are essential。

And then there's a huge gray area where。You have choices。 They can help， in my opinion。

 but they're not essential。 And then you have areas where it probably is unsuitable to apply that kind of。

Of stringency technique， I mean I want to essentially get 100% reliability if I'm putting up a small application for my own use or if somebody is trying to push out a little acute web app。

 they don't need that kind of reliability and maybe what I'm talking about in terms of programming is not for them。

But I think the really important thing here is to realize that。There are different techniques。

 different languages that apply to different areas， and we have to recognize this。 We can't。

Have a simple language for everybody， a simple technique of using that language for everybody。

We can't have a single tool chain or a single kind of system。

 and from there we can go a little bit further we probably don't need the same kind of training for education。

For for everybody。Engineer， software develop or whatever。 that is building infrastructure， say we。

Mechanism that automatically updates the software on a cell phone。Has to have a different education。

 different knowledge， different training from the one that makes a little game。

Because the one can actually destroy。A whole day or。

Or a whole week for millions of people by a little slip。

Maybe even somebody gets hurt if the 911 cores don't get through， bad things happen't。

And it's not just the software that runs on it。 It's the update software。

 It's anything in the chain of， of。Safety， critical issues that has to be dealt with， but。

Somebody doing that has to think differently from somebody who writes a little application。

 maybe to make a couple of bookss quickly， there's nothing wrong with that。

 but they have to think different as a matter of fact。

 if you apply this very strange Indian oriented thinking to little commercial apps。

You'll probably be a year late to market。 and it'll be irrelevant。 On the other hand。

 if you took the attitude of a first to market is the only thing that happens and apply them to the steering wheel of my car。

 No， that's not a good idea。 These people have to think differently。

 And the way you get people to think differently is to。I so to give them different educations。

 we don't have an N standard programmer and we shouldn't have。If it was， we should have several。

And I think the field has to， in some sense clean is of its act before somebody else comes in and try and cleans it up for us this notion that you can sort of make your own constants and have the seconds after the constants is that feature that you added at some intermediate stage or is that simple sort of operator overloading？

We were observing that we were getting a hold。Zux of little suffixes out of the various fundamental types。

 so。The use of fix for honeststein and ill is folks。Long， I think。

 and I can't remember the morning anymore and you thought， you know， you can do anything in C++。

 but you can't make your own literals。And then I'd observed separately that there was techniques that。

Were effective except that people have not used them because the notation was too ugly。

The UniX example is one UniX example is one of those you've been able to do everything in the UniIX example I showed。

 not quite as elegant， but you can do everything showed for the last 10 years libraries have been available there was a nice one from Fermi labs back to nice places and nice people again。

 but it wasn't used as much as it should because the users didn't believe in the notation they didn't like it。

And so we were looking at how can you basically clean up people's source code？

How can we make code look the way it would look in an ideal language， How can we make code look？

Much as it does in the textbook。 So the units sound is simply a way of getting your code to look。

The way equations look in your physics textbook， I mean we know how to avoid that Mars climate orbit a problem。

 everybody have been taught it in physics in high school， first make sure your units match。

 then do the detailed calculation。So why didn't people do it。

 It was too cumbersome and it was too ugly when they did it。

Or too costly if they used runtime techniques。So， I。Together with friends。

 we thought this problem was worth addressing， tried to figure out what solutions we had。

 went through several evolutions， I think the last finishing touches was done by David。

And it's now standard， this is one of the features that is not shipping height today。

Wait a year and that example will probably your computer too is are there other kind of examples where you've let people from within a class create their own literals beyond sort of suffixes？

When I started out with C++， I provided constructors。

 which allows you to construct objects of a certain type from arguments。

And that has been very effective and people have used constructors as。嗯。As if they were girls。But。

 they weren't。There was a runtime cost。So the first thing we did with C+ plus X。

 C++ 11 was we introduced。Constant expressions as a more fundamental unit。

This was work between me and my colleague， Gabriel Tosre。

And we have constant expert functions that can be evaluated at compile time and we have constant expert types so that you can use type rich programming at compile time this is very important in sort of the high performance computing and in the embedded systems work that was what we did to address that constant expression evaluation is much more general。

 much easier to use and yes more pretty in CGL+ 11 than an earlier versions so that just strengthens what the direction we've gone before。

So you could write complex one comma。2 to make a complex number in。C plus+ in 1984。

Today you can write the same thing and have the complex number created at。く만ゃ。

And therefore say put in wrong， I don't know why you want a complex number on wrong。

 but you might want a point， which is the same thing， point of1 number two。

Now you still have to write point or complex。And the other threat of thinking is C++ which was to generalize and make safer the initialization。

And so it happens that if you know the type you need like you have a function returning a complex number。

You can simply write open curly on Kama2 and he says， oh。

 one Kama2 is supposed to make you a complex number and it will make a complex number and return it。

And if you happens to be a compile time you'll do that at compile time， so things work together。

 you get better notation， you get better performance。

 and anything you can do at compile time works even better in a concurrent system because you can't get a race condition on a constant if it's been calculated before the program starts。

 you can't get the threading problems so open curly means。

Find a constructor for the thing that i'm about to put this in it looks at where the destination is and it says is there a two parameter constructor or a three parameter constructor or whatever or if it's just a it'll take the first element put in the first element and it does it for a struck as well see I I haven't played in C++ in a while that's a great idea this。

And。The呃。Uniform initialization。Itll initialise if it can。And if there's any ambiguity， of course。

 finds the ambiguity。If you're in a context where the like you're calling a function and the target could be a point or a complex number。

It's a tough line。Tell me or tell me， so the arrow shaking has actually been improved。

C+ plus 11 is slightly better at finding bugs than C++。98 was I mean。

 I come from the School of Philosophy that says that the compiler is your best friend when you generate。

Co when you build programs。And。To make it your best friend。

 you actually have to have more types if everything is an integer。

What can the type system help you there no it can't if everything is a floating point number but I can't tell you whether it's imperial or Ii units and youll get bug so you need type rich interfaces and for that you need to be able to build。

Cheap types， basically， and flexible types and convenience that's easy to use simple。

And so we worked from complex of one commce 0 one comma 2 or something like that。 So cur is1 comma2。

 and the type is optional， it's only needed and it's needed。

 And then finally we can now write if we wanted to。One plus2I。

Define I as the unit for the imaginary parts， and you get complex arithtic without ever saying complex。

It's down in the definition of the isopphx。🎼？