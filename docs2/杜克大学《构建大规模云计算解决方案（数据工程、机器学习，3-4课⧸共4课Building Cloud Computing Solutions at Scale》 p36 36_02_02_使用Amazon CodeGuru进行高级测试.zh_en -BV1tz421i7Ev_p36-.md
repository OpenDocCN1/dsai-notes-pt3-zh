# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p36 36_02_02_使用Amazon CodeGuru进行高级测试.zh_en -BV1tz421i7Ev_p36-

![](img/7811338b54ec14c05905206c7b938a17_0.png)

So the next thing that I'll cover is what else can we do。

 what else can we do to do advanced things so we can use advanced code quality tools so what I'm going to do is look at something called code guru。

So here is code guru。And in particular with code Guru。

 what you can do is you can actually associate a repository and it can go through and check the quality of your project。

 so I'm going to first step here， go to Asiate Reository。

And I'm going to say GitHub or GitHub Enterprise cloud， there we go。

And then I can connect to my GitHub account。Once I've done that。

 I can go to advanced testing techniques。And then I can associate it。Now that I've tested。

 I've associated this， what it will do will allow it'll allow me to。

Go through and do advanced analysis on this。 And so let me show one that I've done before。

So in this particular one， this one I've actually associated it before。

 and so one of the things that I can do with this is actually go to profiling。And I believe。

Or I's see code reviews， code reviews here。Repository analysis。

And I actually had it and analyzed a repository that I had some code in。

 and you can see what it does is it says code， guru reviewer successfully finished reviewing your source code。

 it looked at 658 liness of code and it has two recommendations inside。

And one of them that I found out was in this project that I told it to talk to。

It appears that you're using a string to construct a shell command that invokes the shell explicitly via shell equal true。

 this might be shell injection We recommend that you use S H Lex quote function to properly escape white space and shell Medicare so I have a security hole in my code that it was able to find and if I go here。

We can look at that exact line of code， in fact it is a security hole and that it's not a huge security hole because essentially it's internal to my tool。

 but if this was embedded in somebody else's project and they weren't aware of exactly what's happening。

 there could be some issues in that there could be an injection attack here where you could put other commands in as well。

And so so this is something that potentially I would want to change。

 you know it's optional depending on where this would be used。

 but it was able to flag this as something to look at if I look at the second one。

 we can see analysis of the code showed that this resource may not closed properly the context lib module can be helpful so if I go here and I look at a setup file here we can see that actually they raise a good point that。

In fact， it isn't closed that this。Basically file handle inside of here。

 I could I could add and a you know， a close handle or use the width context as well。

 so it actually did find two。2， two bugs here potentially that can work with my code。

 So if we go back to this repository that I had associated before， I can click on it now。

And if I wanted to， I could actually go through here and something do something similar。

 so if I go to code reviews。I could say create repository analysis and I can say analyze the code for code quality recommendations。

Or do code and security recommendations。And this will create a build artifact in an S3 bucket as a result。

 let's just go ahead and do code recommendations， keep it simple and I'm going to go here and say advanced testing techniques。

 I'm going to say create repository analysis it'll ask for the branch。

I can say the master branch and then it'll go through and it'll look at this and this says a review typically will be completed in five to10 minutes so in a nutshell。

 something like this， this these code analysis tools I think are absolutely part of the process for improving the quality of your code。

and that they flag things in advance for you so that you can then go through and either write test for it or change the code and so this just gets into this concept of improving the quality through testing so let me just briefly talk about this while this is doing the analysis。

So if we look at you what is the point of this， you know， why would we want to set this up， Well。

 it's really， in my opinion， part of the same thing and with with testing。

It goes into the word kyzen and so if I go to here I say kiszen plus。Continuous delivery or CICD。

 continuous integration， continuous delivery。And the idea。

 the word Kaisin is Japanese word that means continuous improvement and they use this in they used this actually initially with the Japanese automobile industry after World War II。

 and a lot of people now refer to this with testing as well， and this idea。

Is that you have a feedback loop where you're constantly improving things。

 so you have a continuous improvement mindset， so we'll go through here and we'll say continuous improvements。

And the idea here is that there's many ways to improve your code and so one way to improve your code would just be to set up continuous integration。

 which is what we set up with， for example， GiHub actions right so we've got GitHub actions。And。

That's one way to improve our code。 We， we could also。呃。

And we could say testing rights that's what we're doing there。

 we could we could include Linting right so that could be another step is the Lint will will will improve the code we could also add in these these emerging AI tools right so we know that AWS code guru is an emerging AI tool which it found two bugs that are that are legit bugs that I didn't know existed in my code and。

You could say that this discovers bugs。嗯。You could also。

Look at other things like source code metrics as well， and let me just show that as well。

 we'll say source metrics。There's another tool that I've developed called DevML。

That I'll briefly show you that looks at different things like churn and other metrics。

 but the whole idea here is that each of these things they're not static。

 they're constantly being being performed on your code and making your code better right you're just you're constantly improving your code。

In addition to this。This the continuous delivery by putting it into production is another step in improving your quality of code。

 So it's not just one of these things。 They all work together。 and there is no one perfect solution。

 It's this process of I want to make my code better。

 how do I do it I want to do continuous integration I want to do Linting， I want to do logging。

 I want to do you know code tools that improve things。 And so when I was a CTO。

 these are all the kind of tools that I would use when I was actually setting up you a process for a company that I managed of let's say 100 developers。

 So let's move over to this devml tool really quick。 just to show you example。

Of why I built this tool here。 So what this tool does is that it allows you to get metrics on your code。

 And so one of the things that you can do， for example。

 is that you could look at the active days that developer was working on your project。

 So this happened to be run a while back here but this shows that the developer。

 the developers around flask and click that they're active ratio is that on any given day of the week。

 including weekends， there's a 26% chance that they're working on the code。

 So that could be something that you could look into it like， maybe people are getting burn out。

 They're working too much or know， maybe they're getting pulled into meetings too much。

But this another thing that could improve your quality of code is look at the behavior of the people in your company。

Another one as well is the churn and so this is a key metric that is important to look at if you look at flask for example。

 here's the top 25 absolute and relative churn and what the churn means is that how often is a file being changed relative to its size and in this case we can see that this a knit file is changed all the time。

 it's possible there could be some bugs in there because it keeps getting changed。

 although it's a configuration file， maybe that's not that important but we can see like templating like this file maybe that's another one that could have some bugs associated with it flask views looks like it's got some potential issues。

 so it doesn't again mean that there is a bug it just allows you to get more insights and so that you can go through here and you get this constant continuous improvement process So that's really the idea。

Behind these behavioral metrics and or these ADB code guru bugs here。

Let's go back to this analysis here and see if it's been able to find anything。

 so I believe that it failed， so let's go ahead and take a look at this and says。嗯。

The request repository commit does not exist， so maybe there's just not enough code for it to。

To actually analyze there's just nothing for it to do。

 but the concept here you can see from the other example here， which is。That， you know。

 the general idea is you build these tools on top and they analyze。

Your code and show the quality of it now there's a there's another tool that I'll just show you really briefly called code Cl is another similar tool there's a bunch of different these kind of tools and so this does a similar thing。

Where it'll look at the quality your code。 and so let's see if I can just set this up。

 I believe there's probably like a free。There's probably like a free trial for this。

 maybe let's go ahead and try this out， sure， let's authorize code climateage。And there we go。

And if I point this at open source。Let's go to Add a repository。And we'll say authorize it。

And this will do a similar thing， it'll go through and look at the code quality of my code and I think。

That's。I should be able to find the advanced testing in here。It should give me that in a second。Okay。

 let's go to advanced testing techniques， there we go。Whoops， advanced testing techniques。

Here we go so this is going to go through here， it's going to clone it out and actually look at the quality of this of this particular code as well so there's not a lot in there so we should be able to see this。

And we can see that there's it'll go through here and give me all these different you know analysis of the code so maintainability。

 you know test coverage， all this stuff， and I believe there's even a report GitHub integrations that。

If I wanted to， I think it has a badge as well。Let's see GitHub， there's a way to do Irigo badges。

 so I could also add a markdown badge and throw that in as well， so here we go maintainability。

Let's go ahead and copy this， put this inside。So we're basically doing。

We're tricking off this repository and adding every kind of bell and whistle。That you can add。

 so we'll say。嗯。Coode climate。Maintainability。Like this。

And then I thought what was the other one that they had。Which was。Let's see， where is that。

Test coverage。It'll also allow me to copy this。Test coverage， and we'll say。Coclimate test coverage。

There we go。Perfect。There's's a lot， there's a lot of things that， in my opinion。

 add value beyond just doing the。The continuous integration。

 also these behavioral things where look at the behavior of the team and you also look at the security holes for your code and all those things can be part of an advanced testing technique。



![](img/7811338b54ec14c05905206c7b938a17_2.png)

![](img/7811338b54ec14c05905206c7b938a17_3.png)