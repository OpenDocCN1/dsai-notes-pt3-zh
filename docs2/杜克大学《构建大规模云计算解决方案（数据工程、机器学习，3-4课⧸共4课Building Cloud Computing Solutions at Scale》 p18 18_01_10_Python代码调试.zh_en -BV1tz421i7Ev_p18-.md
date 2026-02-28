# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p18 18_01_10_Python代码调试.zh_en -BV1tz421i7Ev_p18-

![](img/c923f3d651971846de82603acb63cbc7_0.png)

I want to talk about really briefly here， just the theory behind some of the stuff I'm going to discuss and to start with in particular。

 there is essentially like a4 by matrix of different topics and testing and so I can just call this testing。

Topics。And what's fascinating about it is you've got a one hand。You have build systems， right。

 you have build systems， which we're going to get into with Gitthub actions。

And then we also have the tools themselves， and this is， I think not as talked about as much。

 but they really can be helpful and then there's debugging code。

 which I'm going to briefly talk about。Really， really quickly and then also we have the concept of。

Continuous delivery。And we'll get into that briefly as well。So in general。

Let's start with the build systems here。You know， in terms of the the topic， so build systems。

 you could think of there are。Really a lot of SaS based options here that are really amazing options。

And you also have things that are open source and in particular。

 probably the biggest open source build system is Jenkins。 And that's almost its own thing。

 We might have a time to get into just a really brief coverage of that。 But in terms of SaS。

You really have third party system and that would be something like GitHub actions。

Or you have a cloud and in terms of cloud， you have cloud native built system。

 So I'm also gonna to get into that a little bit as well。 So a cloud native one would be。

 for example， AWS code build And so those are really the three flavors you got open source Jenkins Saas with Github and then cloud native with whatever cloud platform you're on。

 Now in terms of tools there's a lot of exciting things happening in the tool space。

 but know a lot of the reason for using tools with testing is that you're increasing the quality of your code and in particular。

 one of those that I use a lot is Plin and really the concept here is that it checks things for you like syntax and gives you best practices。

Another one that would fit into that space would be Python black。

 which is like a formatting tool which can you know long termm potentially increase the quality of your codeb there's also these emerging tools that are AId and I'm going to cover a little bit of that today as well it's literally in preview called AWS code guru which can look for different things that potentially you can change in your code and this is trained on pull requests actually in Amazon there's lots of tools in the space but I'll definitely talk about those and then in terms of debugging this comes up a lot especially teaching Python for the first time how do you actually debug I would say the way to debug your code would be print statements PDB some kind of a flavor of it and then testing those are to me the three real flavors of debugging'm。

Just really briefly get into that and then in terms of continuous delivery。

One of the things to keep in mind here is that you also have these options of you could do the third party SAS for continuous delivery and that could be you using we'll call this GA GitHub actions or the cloud native tools like。

 for example， GCP has a way of doing。codeode build。Or sorry cloud build， cloud build and cloud build。

 for example， can push out an application to let's say Google App Engine or with AWS。

 they have elastic bean stock and that could。T up with code built So and in general。

 the concept behind continuous delivery is your code is constantly deployed and it's in a working state either in a staging environment or or if you if you need to it can also go to production So those are the super。

 super high level topics that I'm going talk about。 So let's kind of dig into this step by step here。

 So the first thing I'm going to do is just set up a new environment。

That's optimized for GitHub action。To do that， I'm going to go to GitHub。

Then I'm going to create a new repo and we'll call this advanced testing techniques。Let's do this。

And I'm going to say， this is。A repo for doing advanced testing。

And I'll just give you some of the tips that I typically do at a Readme file is a good idea how a get ignorere for Python。

And then also。Go ahead and create a repo。There we go。So I can share this out as well。Into。

This section perfect。Now that I've got this initial project set up。

One of the things that I'm going to do here is use a new feature of GitHub that I believe just got out of beta where it's emerging out of beta called GitHub codespaces。

 and with codespaces， the idea here is that you can develop in a sandbox。

Right inside of your web browser， and this is really a trend。That is happening a lot。

Inside of cloud environments and inside of all kinds of environments and in particular what's powerful about it is that you can not need to worry about all the things that are happening on your laptop and let me just quickly find my advanced here we go let me just grab this。

And that way I can just paste that into this codespace URL。Let's choose repo。Let's say。

 advanced testing。Here we go。And so what it can do is it can look at the repo that you've set up and then clone it。

 and then you can start to build out your testing environment inside of here and I think these are really powerful ways to develop code。

As I mentioned before， AWS has this， Google has this， Azure has this。

No GitHub itself has it and if you're going to be using GitHub actions to do your testing it's a really good fit。

 it's really like a natural kind of a workflow here and it uses a lot of the bells and whistles of visual Studio code。

 which is one of the best development environments that you can get。

So to start with what I would do is once， once this thing kind of wakes up here is I'll start to build out the steps of the project piece by piece and then check in the code。

 So first， first spot here is。You know have this bass terminal so what do I do。

 I typically you know really briefly create a scaffolding just a basic structure for my project。

 so we'll go through here we'll say make file， I'll create a requirements file。

And then I'll also make just a couple files here like a hello。File。And then a hello test。

And this just gives me a structure so that I can kind of build things out and so once I've got that structure set up。

 I also like to create a virtual environment and if we look here if you see what version of Python there's version there's 27。

 but there's also a Python 3 here we've got 353。And so what I'll do is I'll say virtual environment。

And I will say Tilda slash dot。Advanced testing。I like to create it in a hidden directory in my home directory so that I don't have to remember what I call the virtual environment。

 so we'll go ahead and create that。Rirtual and V。And then I will source it。Here we go。

Advanced testing， bin activate， right， So the way you source a virtual environment is that now if I type in Python。

 you can see that it installs Python 3，8 inside of there。 So it's， its it's built in。To。

It's built into the virtual AV that you can actually create these。Python 38 environment。

 so I'll just add this to read me here so I can just document this step by step。 so you know， set。

So we can just go through here， we can say that you would create a virtual environment。

And then source it， right so this is step one。So create and source。Create and source。

Versual environment。And then we also。Would add some markdown here so that we can get the formatting。

Perfect， and then create Python scaffolding in Excel I just say this setup project like that。And。

Put this one。And then we'll say two here， which would be great scaffolding。Okay。

 so and then for that I just typically do this， I just say touch， we'll do triple quotes as well。

 bash， we'll say touch。Make fileile。And I guess we could just do。All these at the same time。

 test hello。That WPY， and then。Also。Hello。Touch that。And then， also。The requirements。

 so that's pretty much just the start right， so we we have everything kind of kind of ready to go here。

And then， you know， I'll just say populate make make fileile and the reason for a make file。

Is that it's just less work。 So you don't have to remember to put all the stuff in there。

 And so I'm going to go to a file that I've already got here that's probably going to be pretty close。

 and I'm going to go to this make file。In another project and just。

Kind of piece what's inside of your。a second here。There we go。

Now that I've got all this stuff cooking here， we can just put that inside just so like。Bash。

 there we go。Okay， create a big file。I'm going to grab this code here and just put it inside of the make file。

So that's really kind of。Pretty quick setup structure that I use for most of my projects now why would I want to do this？

Well， the reason here， and let's just double check yeah。

 we're sourced inside of here is I can now add in whatever I want in my project and kind of get things cooking。

I would say probably some of the things that I typically use in most projects would be Plin， P test。

 P test coverage， and then also click Cammein tool is probably one of the things I use a lot and maybe flask and to me this is most projects that have something like this inside so let's go ahead and do a make install and if you look here you can see what that does that just upgrades PIip and then installs the requirements。

And there we go。 looks like it's all good to go。 One other thing I'll probably do as well later is probably install I Python to just interactively play around with code。

 but let me just really briefly build out and get into quickly some debugging stuff because that's one of the things I wanted to talk about is is we'll add this step here is okay。

 so how do I debug my code really quickly。 So you know how to debug this comes up all the time。

 as I mentioned before， I would say the three best ways to to do it would be option one would be to prints。

Two would be to PDB。And then three would be testing， right。 And so if you use these three things。

 you're pretty much can get yourself out of any problem。

 So let me demonstrate how we can get into that real quick。 So first up， if I go to hello here and。

I just build some test function out's build。I don't know X like an adder or something like add。

 add this， and I'll say x and Y。And then this will return back， x plus y。

And then if I want to to kind of test this out here， I can just say add this， we'll print out。

Had this。Prince。Add this and then do one and2。And let's see if we can get this thing working。

 so I'll say Python， hello。And notice we already got a bug here because I forgot to put a colon。

 so okay， we fixed that。And we see it says three。 So， so that's not massively tricky to to debug。

 But let's say that there was some kind of a problem going on in here。 Well， you know。

 how would we fix it。 So， for example， like one of the things that could happen would be。You know。

 you pass in the wrong value or you pass in three things or whatever it is you're trying to do。

So one of the things that we could do to initially debug this would be to actually put a print statement so that we print what's coming into the function。

 so if I go through here，And I say Prince。Can I do F string， I can say？This。Is。X。Right。

And this is why。And just this will really solve 80% of the problems that you will encounter when you're trying to debug gos code。

 So if we go through here， now we can see that， oh， great， look。

 I'm seeing what comes into my function。And additionally。

 if I wanted to get into more detail with this as well。

 I could actually put this as the result so we could say results is equal to x plus y。

And then I could say something similar。I could say this is the results。

And then put in the result here。 So notice notice that and I'll change now the return to be result and notice how this F string format really what this does is just allows me to build out templates right so I can put a variable in with just putting these brackets here and so what's nice about this is that it' really easy to you know debug what's kind of happening in my code。

If we go through here again。Right there you go， this is the result three or you know， and yeah。

 could you could put more you tricky stuff in there。

 however you want to format it to make it look a little bit cleaner， you know。

 whatever's intuitive to your eye here。So it's just worth pointing out that this really does get you out of trouble let's say though。

 that you're still something's going on and you're like what what is I really。

 you know I'm still having problems， well one of the things that you could do as well because Python is a dynamically typed language it's also not a horrible idea。

To potentially add a little more context to this， so what you could do。Is you could say this is X。啊。

And the type is。 and you can actually even print out like essentially like what the type is of the thing that's being passed in。

 So if we go here and we say maybe like X。We'll call this X type。And then we could put like this。

 we could say type X。And then we could say this。And maybe I'll actually bring this over。

So that we make this into two print statements now。And then I say。Prince， another print。And say。

 this is why。Like this， this is why。You know， end the white type。

Is and then put in you know type and this really can be surprisingly effective when you're debugging your code is that you have just put the wrong type in right and you weren't expecting that that was the problem And let's see here the white type oh I accidentally put a。

A quote where didt need to be。There we go， so we can see that in fact。

Now we see that these are integers so what happens if I change this， what happens if I go one。

 for example， if we go through here， oh it blew up right because but notice look it says this is one and the type is string oh well we actually weren't expecting there to be a string passed in right and so we can easily debug what's happening and in fact in this particular case。

We see that there's actually an issue here and we need to fix it。

 now there's even more ways to handle this if this was something that was know widely occurred。

 for example， let me just show you a couple other things that we could do。 Well。

 one of the things that we could do is you could in theory。嗯。Wrap this thing into a try accept。

 And so what you could do is you could say try。And then you could say。Actually。

 let's just put this just this in there because that's where all the hard stuff's happening and we'll say accept type error。

And what you could do is you could say。You know， print。The wrong type。Is entered。

I think I can just say。Exception， I think this will， if I remember correctly。

And we can just put in the actual exception。The wrong type。Past in。Like this。

And now that I've handled that， potentially what I could do is I could say results。You know。

Is equal to int。呃。X plus int y， right， just to kind of fix， fix。

 fix that problem for for at least one of one of the use cases。 And just to make it kind of simple。

 So let's， let's go ahead and see what happens if we do that。 So in this case， yeah。

 I think in this case， type error。X。I it as exception， I forget how they just changed the Python。

Well， let's not print in the print exception， I'll just say type past in and I'll just not print that in。

Okay， so let's just do this and then we see that in fact， during the exception。

 another exception handled， so we know that that actually won't work。

 so we know that there's actually an issue。In terms of you can't just change that。

 So what if we change it to this， we could see that that would in theory。You know。

 go through and work。 anyway， the whole， the whole idea here is that with printing。

And or a little bit of exception handling here， you could。Really debug a lot of code。

 So I'm going to go ahead and check this in。 So's let's go ahead and say get status。And actually。

 I'm going to Im going to。嗯。Go ahead and。Add each of these things in。

 so we'll say star or get at star。Can then get commit。Adding in simple， simple tests。Simple debug。🤧。

All right， so we've got some basic debugging， we've got the code working here。

And and if I actually wanted to do a little bit more debugging， like， for example。

 that real weird problem I had where， you know， I was getting another exception or whatever。

This is where the PDB comes in and can be pretty helpful。

 And so this would be the last debugging thing that that I'll briefly show is so let's say again you're you know。

 in this case， it is working， but if I go back to。The other example here where I had the one put in。

Right where we know that that won't work， what I could do is inside of this function。

 this is basically you know the ACce card right where like if you're really stuck you type in import PDB semicolon PDb do set tracece and I should be able to walk through step by step and see what what the heck is going on So if I go through here I say print。

 this is X and this is type u oh let's see well this seems to be working let let's actually go ahead and do do the next statement and then it says there we go and I can actually you know print out X here and I can print out y and I can see exactly what's happening and this hopefully gives me the hint that u oh that's actually the issue is that I put in the word1 and you can't convert one to an integer。

And then I can kind of walk through， and I can exactly find out。Where it blows up and then it says。

 in fact， right here， it says， you cannot。Can only concatenate string。

 not int to string and so we've got a second type error that occurred here that I would need to fix and I could even you know try it myself。

 I could try x plus Y we know that doesn't work but what if I changed it and I said。

 you know for example one。If I said int。In one。Plus， y。 there we go。 we see that that is the thick。

 So this doesn't， in my opinion， and then you can just do a exit。In my opinion。

 it doesn't happen that often that you need to use PDB， but when you do need to use it。

 it can be really helpful and it' it's fairly straightforward to you。

 So just want to get that really basic debugging thing out of the way since a lot of people ask me about debugging code and Python thought I would。



![](img/c923f3d651971846de82603acb63cbc7_2.png)

Cover that real quick。