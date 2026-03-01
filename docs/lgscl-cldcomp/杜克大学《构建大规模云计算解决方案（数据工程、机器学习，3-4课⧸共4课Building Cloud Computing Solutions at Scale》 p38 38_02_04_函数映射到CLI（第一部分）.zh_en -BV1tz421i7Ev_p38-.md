# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p38 38_02_04_函数映射到CLI（第一部分）.zh_en -BV1tz421i7Ev_p38-

![](img/b5fe0c4c4138a14247b5cec6bdc8597d_0.png)

So in particular， if we look at functions here。What's interesting is that in a way there's this basis in math。

 so this is one piece， if we say a function here。At the center of the universe。

And what are the things that you can do with a function well one of them is that's that's a very interesting one is just math in general right so you know if you wanted to。

Do some kind of a。You know， X。X to the one right or x squared or do calculus， do derivatives。

You know whatever it is you want to do， there's a direct relationship with a function and Python and mathematical calculations and that's one use case of functions。

 Another one is the ability to do parallel computing so distributed computing。

iss a use case where you'll see functions used all the time and in particular you'll see this with the multipro module in Python。

 there's the ability to map a function to a process or in the case of asynchronous code so we can say maybe put a tab here that says multipro module。

Is one place you can use it also in terms of Async code as well。

 so if you're going to do a network based concurrency， that's a great place to use a function。

Another one is decorators。So in Python in particular， you'll see this a lot。

That people will use decorators to map a function and engulf it and then do something else with it。

 you'll also see functions in data science。 So in particular， with pandas。

 you'll see people use functions。 And because the thing you're dealing with is a data frame。

There really is no other way to apply something to a row other than to apply a function where it processes things step by step。

Another place that you see it is in GPU programming or we could call this high performance computing。

You'll see that pans up pandas。Python has a library called Numbba。

And NumbA allows you to easily write code that talks to a GPU。

 it also does high performance computing as well in terms of making the LLVM just in time compiler work with Python code。

Also command tools， so you can build functions to build command tools。

 you literally map a function to a command tool and then web services is another example so if you think about functions in general。

 they're actually the cleanest way to map a piece of logic to something else in Python and it's interesting because there was a period of time where object oriented programming。

In a way is almost you know， in we'll call this oh oh。

 they're kind of in conflict a little bit in that an object oriented programming approach has advantages in that you can create abstractions。

But in a way， it's not the direct one to one mapping that a function is a function。

Solves a very particular problem and object toient programming solves a different kind of problem。

 which is code reuse。I think mastering functions in general is a very useful thing to think about。

And really with the cloud computing， a lot of the things that we're doing are more focused on functions and more focused on microservices。

 And so I think it's a really good thing to have in mind when you when you're thinking about why should I use a function and what's the point of a function。

 it really is the simplest way to solve a problem。 So in order to get started here。

 let me let me share a。Repo called Fun bikeike Rider。

Do this and in particular what I'm going to do is go through a few examples here of this particular repo so inside of this repo I have a make file here。

 which is something I typically do as I put inside of here the commands to install and to test something to format it to Li it。

And then I also have my command line tool， and so here's a command line tool here。

Or here's a piece of logic。That later I can turn into commandline tool and if I go to Hello CI。

 what I do is I actually import that piece of logic and then build a commandline tool with it。

 So let's go ahead and play around with this。 So the first thing I'm going to do is use something called codespaces right here。

And this is a new feature that I don't know when they're going to release it publicly。

 hopefully this week through GitHub Universe， but what's nice about codespaces is I can go to this repo here and just open it up and start writing code directly against it。

So that's what I'm going to do。And from here， I've already got a virtual environment created。

 so I'll make this a little bit bigger and then I'll source this virtual environment。

 I'll say source tilde slash dot function bike ridder。

And the virtual environment is helpful because it makes sure that I have everything。

Set up in a way that I'm not going to get weird conflicts。And if we look at this make file here。

 you can see that I can run this make install command and it will look inside of this requirements file。

And install all those packages。 So let's go ahead and do that just to double check that everything's running here。

Here we go。Great， so now that I've got this make install set up here。

 the next thing that I can do is take a look at this， again， this hello world function here。

 So notice that this is a really simple Marco Polo function that takes the word Marco。😊。

And or the function Marco and accepts a parameter called name。

And inside I look for that particular parameter and I say if the name equals Marco return back polo。

 otherwise return back， no， so if I go ahead and I run this。

 I can actually first run this using i Python。I like to test out functions first with i Python。

 I think it's a great way to explore code and interact with things。

 So here's an example of I just say from hello。Import Marco。

Now I can actually test this out so I can say Marco and put in some kind of a name and we'll say Bob。

And it returns the back no， but if I go through and I say Marco and I put in Marco。

It should return back Polo。 There we go。 Polo。 So I think there's a great way to build out the function。

 So again， if if you're， if you're thinking about。You know， going back to this diagram here。That。

 literally。Anything useful in programming you can do with a function。

I think it's a great way to think about solving problems and it's almost like a paradigm shift which is instead of focusing on building tons and tons and tons of code。

 if you just say what problem am I solving am I doing GPU programming， Okay great， let's do that。

 Am I doing Kamean tools Okay great， let's do that， am I building web apps okay great。

 let's do that or am I doing data science with pandas let's do that if you focus on that very specific logic。

 then you can do things like this， you can build a very small function。

And then play around with it first by building a script and then importing that script into i Python。

In my opinion， this is probably 10 times faster to write code this way。So now that we know the logic。

 right， there's a， there's a couple things that I can do  One， if I wanted to。

 I can go back to writing a test now for this piece of code， right。

 so we know it works from the terminal， so。What I can do here is I can say from Ho。

 import Marco and I write a test here that says assert the word polo is equal to Marco。

 and if I wanted to， I could also say I could write another test。

And I could actually write what the logic is for win this code。

ItHas the negative case as well so if I go here。I could actually cu like this， whoops。嗯。

And I could take the word no here。And I could go back to this test。And， and add another。Test case。

 so I can say deaf test。Not Marco。And。Let's go ahead and do that and we can say a search。

And I can do this， I can say no is equal to Marco and we know that Bob should return that。Now。

 if I want to， I can go through here and say make test and and the make test command。Here。

 all this does is run the test file with PT。So'll go through here and we'll say make test there we go and notice now that what's nice about the way this is run is that I not only get to see that the positive case worked。

 but I also got to test the negative case as well which is pretty useful and then also there's a a command here that shows me this another function later that we'll get into so what I can do to further you know kind of get this this initial part of the project working is also add a test coverage and you notice here that there's a library called P test Co。

And I can go through here。Inside of my make file， actually。

We can say dash such coverage equals and then put in。嗯。Each of these files that I want to test。

 I can say hello to start with， let's go ahead and try that and we'll say make tests。

And notice that you can see that Hlo has got 100% test coverage。

 and I also could test the Kamelan tool， which we'll get into a second。

 we'll say coverage is equal to Hello CLI。And then if I run this again。

You can see that now it shows that that's got 89% test coverage。 So now that we have got。

Not only this little function tested and we're able to interact with it。

 we can start to build out and map a kmelan tool， so let's go to this hello CI kmelan tool here and notice how straightforward it really is what I would recommend is put a sang line in at the beginning so this sheang line is a pound exclamation point user bin Ev Python so that what this means is that。

I don't have to type the word Python to actually run this chamean tool as long as the file is executable。

It'll look for the Python that's in my environment and run the chamean tool。 Now。

 one gotcha here with the sheang line。Is that if you're not using a virtual environment or a Docker container。

 then there could be some issues that could crop up with this， but in general。

 I think this is a decent approach the next thing I do is I use this library called click。

And what all click does is it maps a command here and it gives us the ability to put options inside。

 So notice that。All I need to do to use this other file here， this hello file is I import it。

Let's just move this next here， I import it and then I add in an option right here that says dash name and we know that this is a very simple function that all does is take one keyword parameter here and then I also put in this fancy print statement here that in click you can actually style the results and you can specify the background or the foreground which is a nice little feature and then。

At the bottom， I just add the function， right， which is called Marco。

 So let's go ahead and run that in order to run that again。I could do this。

 just guarantee that it's executable so Chiman plus X would be the way to do that and I do this。

 I say hello CLI。Now that I've got that set up， I can do dot slash。Hello， CLI。

 and then I can run help to see what the help menu will be able to give me。There we go。

 so it shows us that this thing accepts an option that says name。And if I want to then test this out。

 I can just do the uparrow here。And you name。And we can put in the word Marco like this。

AndThere we go。 We can see that the word polo appears。

 So it's a little bit hard to read with the blue background。

 so maybe we can swap it so we can just do this。 We can say。Let's make this white background。

And thenll maybe we'll make the foreground blue， try that。Let's go ahead and run this。

It's a little bit better， but still the background white doesn't really fit。A little about yellow。

And then maybe the foreground can be white， let's try that。Or red。

 maybe yellow and red seems pretty good。 Let's go ahead and try that。And there we go， okay。

 so it's a little bit better we can see that this command is running our polo。I also can。

Change this to test out a different use case right， we know that this should return no。

 there we go and it returns no。So there's a lot to like about this workflow and if we look through what that workflow is。

 I can actually describe it。In this readme file。 So what I can do is is maybe say here。You know。

 this is a building community and tool workflow， so building a CLI workflow。 So how would you do it。

 So step one。Is write a function or actually first create scaffolding for your project like I did。

Scafffolding。And Python。So that would be。You know， like a make file， virtual environments。

That kind of stuff， step two。Write a function。In a script file。

And then step three would be to test it out。And I Python。

Step four would be to then once you know it works， write a test。Using P test。And tests。You know。

File like that， and then step five， write a Kameion tool。Commanline tool and then six test all of it。

Using。I'll put this right to click Cammelan tool。And then test all using the click Test runner。

There we go so really there there's these six steps which in my opinion。

 really allow you to build things very， very quickly if you follow this pattern and instead of again going into just writing a bunch of code what's nice about this is that it's building these safety mechanisms that protect you from making mistakes so what I'll do here next is。

Go back to this test file here。And notice that I have this test called test search。

And we can probably rename this。 That's not a great name for it。 we'll call this test。CLI。

And notice what I do is I say from click dot testing。

 they have their own test runner here and this test runner what's nice about it is that it allows me to invoke it with the exact way I would call it from the command line and so notice here it says runner invoke call Marco Dach's name is equal to Bob now I could actually if I wanted to go you know really into detail and test even more stuff let's write another test so。

One of the things that we notice here。That this is only testing the positive。

 So we'll call this or the negative。 So we'll say test。嗯。Not Marco。There。

 and we also could verify that。We can write a positive test as well， so we can say test Marco， CI。

 and we'll go ahead and put Marco and notice that in this case。This would not be the output。

 let's go ahead and run it because it's a mistake and just we'll see what happens。

 So if I go through here and I say make test。Oh notice that there's a failure here and in particular the failure that occurs is that it says that the assertion error is no does not appear in fact Polo appears and so now we've got an assertion error and that's a great aspect of the way this testing framework works is it's really easy to go oh oh。

 I made a mistake how do I fix this mistake well。We know that， in fact。That's not what appears。

 we know that polo appears so we can go ahead and change that。And it should exit cleanly， right。

 it should be a zero exit status。And let's go ahead and run this。We'll say make test and there we go。

 we've added another test case here， so we've got both positive and negative test cases for the function and then positive and negative test cases for the command line tool Now you know maybe some of this is overkill because you could probably get away with just writing these but you know it's really depends on the use case that you're using when you're building the command line tool。

 but let's actually expand this a little bit and make it a little bit fancier so。And test more。

 so if I go back to this Ho CLI here。The other thing that we can do。Is I can actually look for。

add a little more logic and do different things depending on what logic is in place。If I say。

 you know， if results。呃。Is not。😔，Marco。Then what I can do is say， you know。

 maybe take this result and do something slightly different right。

 so maybe what I could do is I could say。Am。We'll just only do the background。Red。

And we'll have no foreground color， let's try that。And then， otherwise。Let's try this use case。

 so if I go through here and I say。Make tests and then I go and I say。Bob。Notice that。

I'll need to exit out of here so what I can do。Is。嗯。I can say。Import cis。And then I could say。嗯。Sist。

exit。Zero， for example， right， so I could go through here and just say。Go ahead and。

Exit if I wanted to， you know if this is in fact the case， that's one way to do it。

Another way to do it as well could be to just do a return， so we could just say， you know， return。

True， right， and we could we could exit， so let's try both approaches so first one。

If I go through here， now we exit properly， if I do the other one。

 that's another approach that I can use， I could also just do a ciss exit and return it really there's not necessarily one advantage to doing this it's really up to you how you want to exit it out。

 let's just leave the cis dot exit in here for now。う。And then notice with this one as well。

 maybe instead all I want to do is do the background and we'll say green。

So we know that it gives us a signal。That our command land tool。

 when it's doing what I expect it to do， it returns back。The right thing。

So if I go through here and I say a Marco。We can see that it returns back polo， did I？That should be。

Background。If results。😔，Not sure。 Wa's turning back。

It's kind of strange that it's not giving me the right color， but basically the。

This is going to be you know。We can also do an L statement to kind of clean this up and we should be able to see a background。

As well， you don't need an L statement because it's implicit that。That。You know， in this case。

The the。It will say that if in this particular case。The result is not Marco， that'll do an exit。

 otherwise it'll do a a。The other test case。So let's go ahead and reload this window。Yeah。

 so when you reload one of these windows here， it's important to make sure that you。

You actually go through here and resource the virtual environment。

 so if I go through here this double check out do that， there we go， we got Bob。Marco。Yeah。

 I'm not sure what's there must be some kind of weird bug in here why its the background is not changing it really。

Not that big of a deal， but if I go back here and I say make tests。

Here we can go back and double check that everything still works。

 So it it just gives us a little bit more flexibility if we want to do different things based on actually what I can do real quick to debug this is why don't I just do this。

 I just say。嗯。Let's actually just say comment this out。And say。Click。t echo。Result。Just like that。

Let's make it simple。Yeah， weird， weird that it' it's sticking it really wants to。

To give us that particular result， which is very strange。 That's a very weird behavior。

 There might be something subtle going on with。That once you set this in code， we discovered a bug。

 but in a nutshell， the core concept here is that we can test different use cases in this function。

Now that I've got that working， I'm going to do a git status and I'm going to add in this make file。

I'm going to add in this readme file。And then I'm going to add in this celllo CLI and then add in this testta low。

 and then I'm going to commit it。 So adding。Fully tested。Application。There we go。Perfect。

And one of the things that we can do because it's in GitHub here is I can actually go back to GitHub and look at GitHub actions。

 so let's go ahead and look at this function bike ridder here。



![](img/b5fe0c4c4138a14247b5cec6bdc8597d_2.png)

![](img/b5fe0c4c4138a14247b5cec6bdc8597d_3.png)

And look at GiHub actions。And I'll walk through how we could also use that to test our code。

 so notice that this queuees up a job here。

![](img/b5fe0c4c4138a14247b5cec6bdc8597d_5.png)

And in particular， what it does is it goes through and runs the test。

 it just runs the make test commands here， so let's go ahead and take a look at this。Okay。

 so it sets up Python 38 installs out of dependencies。And。😔。

We can kind of watch this thing and we can look at the output of any of these jobs by typically refreshing it。

Here。😔，There we go and dependencies Liing it looks like everything' is done， right。

 so it was able to successfully run through test our code。In each one of these。

 I can actually go through and look at the output。Right and we see all of the different tests that have actually been passed。

Now， let me show you。

![](img/b5fe0c4c4138a14247b5cec6bdc8597d_7.png)

What all of this code does， so if we go back to this repository here。



![](img/b5fe0c4c4138a14247b5cec6bdc8597d_9.png)

What I can do is look at GitHub workflows。And in particular。

The Python application test with Gitthub actions， we say on push events。

 I want to run this in abuuntu latest and I want to set up Python 38。

And here's actually the Python version， which is 3。8。

 and then I just go through the steps that I set up in my make file， I make I install software。

I linked the code， which we didn't go into， I'll go through in a second。And then in addition。

 I will make the test and then I'll do make format， so if I go through here and do the same things。

 let's go ahead and do those so we've already done we did make install。

And that one's pretty easy and let's just look at all the steps in the make file。

 then there's make test， which we had done multiple times。

There we go we also do make Lint and if all the Li does is it looks for the files and it linkss them so we can say make Ly。

 Now we probably could add some other files here so we know that there's Ho CI。As well。

 so let's go ahead and link that one。And there we go， that one passes Li as well。In a nutshell。

What's nice about this is that I can have this repeatable automated process that tests everything。

 So we actually have a very。Structured project here that allows us to kind of expand and build more complex command line tools。

 And it all started again with this function。 The other thing we can do is Github actions if I click on。

This link here。And you click on this this three dots， you can say create status badge。

 and I also can take this and put this into。The Readme file。

 which is which is not a bad idea so that we can see what the status is of the build so I think this is a nice feature of GiHub actions here。

And let's go ahead and do that， let's just throw this up there。

 there we go and now we've got a build process as well。Now if I go back to this location。

I can say get pull。And get the latest changes and if I say get status， notice I made a small change。

To the make file， so I'll go ahead and add this。And also notice that this is a virtual environment here。

And so what I'm going to do is I'm going to add that to my git ignorere。Right here。

 and I'm just going to say。If was that called again， it was called Python 38。Virtual environment。

 let's just get rid of this and add it to our get ignorere so I don't accidentally check it in。

There we go。And if I say get status。There we go， we can say get add dot get ignore。

Adding ignore Pers。Okay， so we've got pretty much a full working command line tool and we started with something really。

 really tiny。

![](img/b5fe0c4c4138a14247b5cec6bdc8597d_11.png)

![](img/b5fe0c4c4138a14247b5cec6bdc8597d_12.png)