# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p31 31_02_02_使用Click构建CLI工具.zh_en -BV1tz421i7Ev_p31-

![](img/626b88a94bfb8da22ca1aa77becbc3f6_0.png)

We're going to use GitHub。And I'm going to use something called。

Code spaces to build out a command tool。And what codespaces is is it's a dev environment。

That allows you to work right inside of GiHub itself。

 And I'm also going to show how we can use GitHub actions at the same time to build these out。

 and then I'll have a command line tool inside at the same time。

 So we're going to use all of the fancy features of Github here to build out a development environment in a web browser。

 do CicCD。Inside of Gitthub actions and then also build out this command line tool and additionally。

 I think we have some time for a little bit of Docker。

Cme and tool integration as well so got a lot to to tackle and it's all pretty new stuff here so i'm going to get right into this。

 So first up here， let me go to a Github location。

![](img/626b88a94bfb8da22ca1aa77becbc3f6_2.png)

And I'm going to just open up a new shell。

![](img/626b88a94bfb8da22ca1aa77becbc3f6_4.png)

And I'm going to click on this codespaces icon now。Unfortunately， this is beta。

But I think they're going to announce it maybe even like this week because I think there's GiHub universe。

 but let me show you what this does， so code spaces。

I'm going to get rid of one of my old code spaces here。And delete it and and recreate a new one。

 So what codespaces does， which is pretty cool， is allows me to write code inside of a Docker container inside of Github。

 This concept is similar concept in the fact that。AWS Cloud 9， Google Cloudhell。

 which we'll get into in a little bit， can do similar things。But in order to use this。

 then I'm going to need to create a new repo from scratch because we'll do this together so I'm going to go back to GiHub real quick here and just make a new repo so we'll say new and I'll call this。

Codespace。Deops， here we go。 And it's a for description， this is a Python for Devops。

Coode space repo。And inside of here， I'm going to add a readme file。

I'm also going to add a gig ignore for Python， let's go ahead and do that。And additionally。

 I'm going to say create Repo。So once I've done this， and I'll share this with you as well。

So you can get access to this， there we go。Okay， so now that I've created this。

 I can go to Codespace and this is called Codespaceace DevOs。And and play around with it。

 So Ill say new code space and say code space。Deevops。Deevops。There we go， codespace DevOs。

 and if I say the main branch， let's go ahead and create this codespace。

So I think for DevOs in particular， the web based workflow。

 these web browser based workflows are the way to go， I almost never use my laptop anymore。

And I mostly like to use things in a cloud based environment or like in one of these kind of environments。

 just because a lot of DevOs is you're in a web browser anyway。

 so let me make this a little bit bigger。And in particular， what it does is it develop。

 it uses visual Studio code as a shell。Make this a little bit bigger。

And once you're in Vis Studio code， you get this whole structure here。

Where it integrates really nicely with what you're building。

 so the first thing that I'm going to do because this is a。

A codespace shell is I'm going to go back to my repo and I think I can just click on it。Here。😔。

Go home。And I want to keep both open at the same time， so I'm going to click on this one。

And I'll go to codespaces， I'll keep this one open。And then I'm going to go over to this URL。

 So one of the things I'm going to do to start off with is I'm going to create a Github actions integration。

 And so this isn't beta。 You can definitely do this yourself。

 So I'm going to say set a new workflow for myself here。And I've already got some of this set。

In another repo， so I'm going to go to Github actions demo。

And I'm going to grab a something I did earlier， let's I don't know。

 grab this or something like that。Let's see。 Let's go to。Maybe。Scrab。AWSE M all。Sure。

 let's just grab this one。嗯。So I'm going to just take this as like a template。

And I'm going to throw this inside of your。I'm going to change this though to just call this。

You know， code space。And。What I typically will do in my projects is I have a few different steps。

 and I believe in terms of Python。We can probably just say， python 3。I think it has Python 38。

 we'll just do Python 38。We see Python 3，8 here。And then install dependencies。

 I usually use a make file for this。And so we can start with that， we can just say make fileile。

And if I commit this， I believe it will。Allow me to get this cooking to start with so if I go back to codespace here。

It should if I refresh it。Be able to integrate with a virtual environment。Okay。

 this looks like it's ready to go。So once I've got this set up here。嗯。We should be able to refresh。

And and it should be able to integrate this GiHub actions workflow。

 so you can see here that now it's going to do this build process。

 which will mostly work except for the make install part won't work。 so its says set of Python 38。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_6.png)

GoodOkay， so it failed at the make dependency section， so it can run Python 38。

But it failed here because I don't have。The make file installed yet。

 so if I go back to this code space and I do refresh。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_8.png)

It should have a little bit more stuff inside of here， let's double check。Okay， so it didn't。

It didn't do that Yes， so I'm going to have to create this make file， so I'm going to say touch。

 make file。Here and then I'll go back to my other example。

Project and just grab a make file out of here。And let's go ahead and do this。So grab this。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_10.png)

え。Go to this code space and now because it's inside a visual Studio code。

 I've got a pretty good editor here so I can just paste this in and just get rid of stuff I don't care about I just。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_12.png)

I just care about install。I'm going just change。 I don't need any of this。Just get an installation。

 So so this is the way I typically do a basic Python project is I have a make file that has an installation step and has a L step and then a format and a test。

 So let's go ahead and create those other file so I need to create a requirements file here。

Like this。 And then I need to create a。AHello file that we'll turn into a Ka tool in a second。

And then I need to go to the requirements file and install a few libraries。

 so let's go here and we'll put in click。Py test and pilotyin where those are probably the basics that I would care about。

 So， so now that I've got that， if I say get status here。I can say get add。Make fileile and in fact。

 maybe the hello file。Even I could put something inside。And what we can do here is we can say。

You know， deaf， hell or something like this or high。And we can just。Return high for now。There we go。

 so we got something in there and I'll say get add star， get status， and let's ch at these in。

Adding basic structure。Now that I've got this basic structure and I push it。Notice how。

It's got actually good integration with GitthHub， which is pretty nice。

 So it's going to allow me to merge here。 So let's go ahead and merge this。

We're going to go ahead and say。嗯。What willll say， save。Go ahead and save this。

And then let's go ahead and push it。Now once I push this build， we can go back。Again， to our。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_14.png)

our bill process with actions and actions well run it again。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_16.png)

And so here we go， codespace。Merge。And now we can see that this should， in fact， complete。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_18.png)

Now that I've got the rest of that installed。Okay， so it's still having an issue here installing the dependencies and。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_20.png)

There we go， let's look at what the installation step it says。Okay， no distribution found， oh， well。

 I misspelled it。 Okay， so we can go ahead and fix that。 That's an easy one to fix。

 There we go Py lenss。

![](img/626b88a94bfb8da22ca1aa77becbc3f6_22.png)

So it also proves， and I think we can use Python black as well。

 we can put that in there and I'll do the same thing， I'll just say get status。Get add requirements。

 So you can see how this is a very iterative process that uses the Devops best practices， right of。

 you know， always making things better， automating things。Step by step。Okay。

 let's go ahead and push this。Into our Gitthub actions again， it'll trigger again a build。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_24.png)

And let's take a look at that， here we go。

![](img/626b88a94bfb8da22ca1aa77becbc3f6_26.png)

We should have another build processing。There we go， adding requirements。Build。😔，Yeah。

 pretty fascinating actually， Google or GitHub codespaces is actually a pretty legitimate build environment now for as a developer。

 you could basically develop all your code right inside of GitHub。And it's your IDE。

 which is a fascinating process。Here we go， it's installing dependencies， so we set up Python 38。

And there we go， we're able to successfully get all this stuff working。So。

I guess the big thing here next to do。Is that we want to。Go through and。And you know。

 essentially install these dependencies and we've done it so if I go back to this now and I refresh this。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_28.png)

You should see that that one of the things that we could do inside of here is we could also。

Create a virtual environment and test things out， right。

 because if I go here and I want to test this locally， if I just say， you know， make。Make Li。

 for example， or whatever it is that I need to do。One thing that I always need to check out is which version of Python？

And I'm running， I'm running the system Python and typically。That's not a great you know。

System wait way to develop my code。 And so what I what I like to do in an environment like this is create a virtual environment。

 so I'll say。嗯。First， double check which version of Python we have， we have Python 35 here。

And what I'm going to do is say。You know， which Python。And again， we know that the Python's there。

 so I'm going to create a Python three virtual environments， so I can say virtual environments。

And say tilda slash dot codespace。what this will do is create a new location for me and I can source this virtual environment to develop in so here we go。

 Codespace band activateate and the idea here is that now if I say which Python you can see that it's going to use this particular Python now notice that because this particular version of Python is 35 what I might want to do is match up。

The code space version and notice how。That it also gave me the correct version of Python as well。

 so in a nutshell。By creating this virtual environment。

 I was able to isolate to the correct version of what I'm going to be testing later in my project。

Now that I've got this set up here inside of my code space。

I can actually start building out a command land tool。

And what I can do is look at another command tool that I've had previously。

 let's just kind of grab one and keep a basic one here so here we go here's a hello one。嗯。And。

 in fact。I don't think that's the  one I want to use。I w to use a。Command line。's look。

 let's look at， I think I have it in this Devops course repo。 I can just grab an existing。

Commeline tool。 Let's do this。 This looks like a good one to use。Here we go。 Yeah。

 this looks pretty good。 so I I'm just going to grab this code。And I'm going to throw this into。

My code space in the hellello file， so I'm going to go here。And paste this in now， notice if I。

 if I just run this here， this import， click all this stuff that。嗯。Let's just do this。

 we'll say Python hello。Notice that it says no module name click Fo and the reason why is because I never did the make install local right so even though I have a virtual environment what I need to do is say make install like this。

And once I do a make install， it'll go back and do the same thing that the build server is doing。

 so the build server is actually more ahead of where I'm at。Then I am。

 and now I'm going to catch up and I'm going to get the same workflow。

And let's just take a look at this command line tool that I'm building here， what it does。

 so I import the click。Command， I also import the Gloob library， which we talked about earlier。

And then I put this path inside， so I'm writing a command a tool that can search for things inside of a file system。

And so with decorators here， it really is handy because it allows me to put the options on top of this function than a building。

 so let's look at this function what it does， it says search for a path and search for a file type and look for those results。

And then inside when you find a match， print out what's inside in red and then at the beginning and then iterate through each result and then print out you know blue or white。

 And then at the bottom here， I just run this search command。

 So let's go ahead and and do that command。 So now that I've got the installation working。

 I can do hello like this。 I can make it executable first。

And then go to Ho and do dash help and what this will show me is that it shows me the options and it also shows me the usage right here。

And and so what's nice about this is I can also go in if I want to and add additional documentation。

 so let's say I want to be friendly and say。This is a tool。That searches for patterns。Like asterisk。

csv or something or whatever。Like or actually like CSV。Yeah， perfect。 Okay。

 so let's go ahead and save that and now if I do the help again， notice that the help menu。Should。😔。

Let's do here， lined。Unexpected anddent line 18 Oh， I think I somehow that's weird。

 I must have mixed tabs and spaces or something crazy like that， but that looks good。Okay。

 so let's go ahead and run this。And。Yeah， I think that this got screwed up。

Which we can fix real quick。So let's go here。LetsSt that and then just delete these。

Sometimes it's easy to get a。An indentation issue。In， in Python。

Because the tabs and the spaces are jacked up。But let's see if that fixed it。Oh， that's your opinion。

I believe that we might be able to。嗯。Let's see here， do I see this space issue？

I don't see that issue。But let's list travel one more time， L 17。Maybe here。Let's try that。

Oh irritating。 Well， what I can do that's easy is that， yeah。

 not sure whether that well we could also。Just do this and just try it one more time。

 just re pastste it inside of that's a problem with cut and paste code is not necessarily the greatest idea。

There you go， so the help shows up again。Just so I don't screw things up。

 I'll just not put the documentation in there， but basically you can put additional documentation by putting it inside of here。

Now， if I want to run this thing， what I would do is I would just say path。

It will say path and say dot。And then dash's file type， and we could say Py。

And so you can see here that look it found's it's not the output's not great because it's in blue。

 but maybe we'll change this to。I don't know what colors Click has， let's see does yellow work。

 let's try that。Maybe that would be a good color there we go。

 so that's a little bit better so I can you can see that if I just put in the pattern。

 we can find things I if I do type make file，It could find make files or。

I guess there's no extension to the make file but it could find TXDs。Right， there we go， finds DXtss。

Whatever whatever expensess I want to look for， so I have a neat little command line tool here。

And I also could do make Lint on it to see if it is able to run。 And there we go， we got。

 we got a li as well。 So I've got installation， I've got Ly， and I've got I've got a test here。

 So I've got a pretty。Well， I don't have a test yet， so I need to build a test next。

 so I'm going to say touch。Testaello。And to build out a test， pretty easy in click。If I go back here。

What I can do is。Is， is steel a test that I wrote earlier。And I'll show you how this one works。

 And so the way this works。Is that。Inside of inside of this。

 let's just make this a little bit bigger。Inside of here。I would need to say from click testing。

 import CLA runner。And then say from CI import search。And then what will happen is I can import。

This Excel say from hello。Import search because that's the name of the Kamelan tool。

 And then what I do is I build a。A test that invokes that Kamelan tool with an argument。

And what I'm going to say is that。I want to look for a Python file and it should return back a successful error code。

So let's go ahead and do a make test now， if I say make test。

One of the things that it has a problem with。Is there's no coverage option。

And so what I need to do is install another tool called Pi test Cove， which is a coverage tool。

 there we go。That looks good。And。嗯。In this case。In order to install it， I have to say make install。

And this will install the P test coverage tool， there we go， you saw it just installed it。

And now if I say make test， itll it'll show me as well that the test coverage。

 let's look at the command that I just ran， the make test command。Notice it says Python。

 run the Py test testing library， pass in。Coverage report for Ho and then run this test file。

So now I basically covered this， this one is somewhat self-explanatory。

 I've done a li which makes me able to detect syntax errors and I've done a test。

 this is one that's kind of an neat one to do as well is that there's a formatting tool that cleans up your code a little bit。

 So if I type in make format。This will run Python black and it will actually just kind of clean up the code。

And it may even have cleaned up the spaces or the problem that I had earlier。

But basically it reformats so your code looks a little bit better so it doesn't have as much weird。

You know， styling essentially， so it makes it look a lot more professional so now that i've got that thing cooking what I what I can do is is check this into。

The build system， so let's go ahead and do this， we'll say Gu get status actually before I do that though。

 let's go to GitHub actions here。Notice this workflow and I can change it。

And what I can say is that not only do I want you to do an installation。

 but I want you to do these other steps as well， so I want you to do a。Let's do a。A li。Right。

 so we'll say run。And then I can just pipe this command here like that and say make Li。

And I can add another step that says。Name。Tests。And then， we can do。Make tests。And then if I want to。

 I can even format the code just so that I see if there's a formatting error that needs to occur。

Or formatting that needs to occur so I can say format。And then I can say make format。

So what's nice about this whole setup here？Is that I can actually go through。And build this。

Step by step。Locally and then have the build server automatically check it。

 so let's go ahead and check this， so we'll say get add。github。Get add Ho， get add requirements。

 get add test Ho。Go， and。Adding the tests。Okay。Great， so this will kick it off locally。

And I believe that。I don't know what this does， but。Looks interesting。

 I guess you can remote show ports。But。The other thing that we can do here。

 I wish they had a link to the get to the， I guess this is a link to the Giub。 but the build system。

 I don't see the link to it in here yet。 Maybe it isn' in here。 I don't know it is。

 But if I go back to here。

![](img/626b88a94bfb8da22ca1aa77becbc3f6_30.png)

![](img/626b88a94bfb8da22ca1aa77becbc3f6_31.png)

We can look at the latest build。Sego actions。Adding tests and something。Something happened。

 what do we do？Oh， every step must use a users or run command， so I think I screwed up。嗯。

Something here in the way I created the make the Github actions， which can fix real quick。

 So let me just see how I did it before。If I go here， it looks like what did I scrub up？Name， run。

not sure。 Well， I can be lazy and just copy what I did before I must have。Done something we in fact。

I believe I can just do this。Just do this。Overwrite this whole section。Which is， I think。

From steps down。Let's just， let's just do that， is that right？Steps， steps。Get。

 I don't know what I did differently。But。Oh， I forgot a run step， that's what I screwed up。

 but looks like steps uses。Name。In fact。Just to be extra safe。

 let's just copy this whole thing because that's exactly what I want。 I'll just copy this。

So basically it's Python continuous integration steps for Gitthub actions on push。

Use the Auntu operating system container。Check out Python3。And install the dependencies， doing。

 make install， make the li， make the test， make the format。 Okay， that looks good。

 Let's go ahead and。Check that in。And we'll do GiHub。 There we go。Adding Github actions。Steps。Okay。

So we've got GitHub actions here。Cooking， let's go back again to the build system and ensure that this latest workflow is building。

There we go at Gitthub A steps。It's queued up。

![](img/626b88a94bfb8da22ca1aa77becbc3f6_33.png)

Perfect， so this thing is on build and it looks like it's building the dependencies。Lentine， testing。

 everything works。Great， so this， in my opinion， is not a bad development environment。 and in fact。

 we can also do another step further here。

![](img/626b88a94bfb8da22ca1aa77becbc3f6_35.png)

By going to this link。Notice how we say create status badge。

And I can just copy this and also put this into the repo right here， so let's go ahead and do that。

Let's put this build status here inside， so this is essentially like a。Like a showroom for Google。

Google， I keep saying Google GiHub code spaces here where I've got a full working project step by step that has the build process with continuous integration。

And also the structure of a Python project， I call this the Python scaffolding and a commandlan tool。

 so this really would be a good thing to potentially fork and build you know based on the structure。

 so let me show you a couple of the things here that are important。

One thing to point out is that why am I using this lint process。

 well if we go to this code here and let me just put in a bad variable here and let's just say I just have a variable that I forgot I was busy somebody distracted me and in notice if I say make L it blows up right it says oh oh。

 unexpected， well first of all it says unexpected anddent。As well online， but anyway。

 it notice which is true actually， let's leave that because that's actually a good。

A good it caught two things right， it caught the fact that there was something wrong and it caught that there was an indentation error。

What I can do is say get status and add this in and the build server will catch this。

 so you know we'll call this bad anddent。And push this to Gitthub actions。Well。

 first I need to pull because I。呃。Because I was able to。Make that change to the status badge。

 so if we go back here though。We can can see that。The bill process should be。should be back again。

There we go， merge。

![](img/626b88a94bfb8da22ca1aa77becbc3f6_37.png)

And we've got this build process。This time， though when it gets to the L step， it's going to fail。

So this is really the benefit of having continuous integration as。

Why would you ever want to check in bad code somewhere where you know。

 it would later go into production。 So this is really a big gotcha that we're we're helping to solve by。

By， you know。You know， messing around with this so the you know。

 now that this li is is is got a problem and I can even look at this li and it should。

It should let me see the output there we go。 It says that oh unexpected anddent right so I could go and debug it if I go back here easy to fix right just to fix this。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_39.png)

Right this is bad code。 we run make Li again。We fixed it， I said， get status。Get add hello。

 commitmit this。Adding a fix。Okay， so assuming that all works， this thing pushes。

You know we've basically got continuous integration set up。



![](img/626b88a94bfb8da22ca1aa77becbc3f6_41.png)

![](img/626b88a94bfb8da22ca1aa77becbc3f6_42.png)