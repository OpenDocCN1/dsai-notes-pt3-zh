# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p37 37_02_03_使用AWS CodeBuild进行高级测试.zh_en -BV1tz421i7Ev_p37-

![](img/79226208ff337a7992b7d265f23352fc_0.png)

Let me do the next step here， which is since we are already inside of AWS。

 let's go back there and let's also use their build system。 And let's see how that looks。

 So AWS has a build system called。Code build， so if we go to code build here。

And one of the things that we can do with code build is that we can do almost identical things that you could do with。

For example， GitHub actions， and so if I go here and I say create build project。

What it will do is allow me to set things up so that it test the code in the AWS environment。

 and this can be really handy if you're doing things on AWS in particular。

 especially doing deploys on AWS。First up here， I'm going to see。

 I'm going to call this advanced testing。Say this is an AWS version of advanced testing。

And I'm going to go ahead and build a Bill badge here。

And then where do we want the code to come from， You could use their AWS environment or you could actually use GitHub。

 I'm going to use GitHub。And it's going to look through my repository here and find one that I can actually test out with。

So I'm going to do a repository in my GitHub account and we'll call this NOAA gift。Advanced testing。

 There we go。And then。I could go through here and do other things like submods or。You know。

All that stuff， but I'm not going to do that。And then how do you want it to run in this case。

 I want it to run every time I make a change， so I'm going to go ahead and say rebuild every time that change is made and then for event type。

 we'll just say push push events。呃。And。And then， for environments。We can go through here and say。

 well what kind of environment do I want to test this in I can either do a custom Docker environment or I could actually do one that they manage themselves。

 I think this is probably the best option for AWS and so I'm going to go through here。

 I'm going to select Amazon Linux2 which is their their version of Amazon Linux it's a lot like red hot Hat Linux。

And。I'm going to say runtime here， I'm going to say standard。And then for image。

 let's go ahead and say Amazon Linux X8664 standard3。So just pick the latest version。

 always use the latest image environment we want to run in Linux。

 notice though I could test GPU code which can be handy。

 there are some great things you can do with Python and GPU， but I'm going to say just Linux。

And from here， if I wanted to build Docker images， I could do this， I don't need to do this。

For this particular one。I don't need to do anything tricky with AWS like do a deployment so I can just let it use a default service role。

 but it is important to know if you wanted to do like a continuous deployment process you would need to actually create an IM role that would have the privileges to do that action。

 So in this case， we won't do that though。We'll go through it here。You know， set this up。There we go。

And then from here， we have the option here to either use something called a build spec YaAml file or insert build commands step by step。

You know， for example。You know。Inter the commands you want to run during the build phase。

 separate each command with the and and。And so。If I click on build editor here。

 I could actually just kind of build this thing out right inside of this you know repo if I wanted to。

 I think this is probably the better way to do it though is to use this thing called a build spec。

 yaml so in order for this to run， I'm going to need to check that into my project this configuration file so how do we do this Well I'm going to go back to codespaces here。

And I'm going to go ahead and。Set that up， actually you know what， now that I think about it。

Probably because we're on AWS， let me do this in their development environment。

 so I'm going to go to。2。To console here， I'm going to spin up AWS Cloud 9。It will go through here。

And。From here， what I can do is create an environment to test out。

My code and build it out so this is really similar to Gitthub actions is AWS cloud 9。

 so we'll go through here and we'll say advanced testing。In environments。For advanced testing。

Here we go， let me go through the next step here and so in this particular environment notice here that it'll create a new EC2 instance that has a micro。

 I don't need a lot of work or a lot of horsepower and I'm going to say Amazon Linux too because that's what I'm going to build on。

And then notice it'll time out after 30 minutes， so this is a great environment for AWS to do testing on。

 I use it all the time and and in particular if you're going to be building with AWS code build。

 this is a great environment to you so what I'll do is this will take just a second to set up。

 but basically I will create SSH keys so that I can talk to GiHub。



![](img/79226208ff337a7992b7d265f23352fc_2.png)

I'll create my build。yml file here。And then I will then get make this environment my new environment for testing the AWS portion。

 So this is a pretty normal setup as well， where I can see where you could use Github actions for some components of what you want to test。

 but then also use an AWS native environment when you want to get into the AWS pieces。

 So while that's actually spinning up， let me quickly look at a。



![](img/79226208ff337a7992b7d265f23352fc_4.png)

Example。Huggo project that I have set up that will give me a code build example。

 so let's go through here。 let's just look at something that will let's say this is probably a good one。

That I did recently where this is something where I do continuous delivery for a content management website。

 but it gives you the feel for what a code build type file would look like is that you can see that there's command set run you can set environmental variables if you needed to and then in this particular environment instead of just testing。

 I actually deploy a new website and I deploy that via AWS in this case though I'm going to just use this as the basic structure for how I actually do my testing。



![](img/79226208ff337a7992b7d265f23352fc_6.png)

Okay so we got this thing set up here， so again the first thing that I'll need to do is I will need to create SSH keys so we'll go ahead and do that。

 say SSH key， Gen T RSA。And then I will just print this out to the standard out so that I can。

Look at it。Go here。And inside of this particular repo。I can go to。



![](img/79226208ff337a7992b7d265f23352fc_8.png)

To GitHub and go to my settings and just add this key。So that I can work with this repo。

 So good for this advanced testing。Advanced testing。Paste that in。And there we go。

 so now that I've got that set， I can do a clone of the repo so I can go back to this thing。

 let's see where is this environment。Let's click on。Here， go home。Let's go to code。Copy this。

And do it get clone。Okay， got this thing cloned up。

And what's nice is because GiHub actions and all that is already running。

 it saves me a lot of time because I know that things should work over here and so I just need to create a virtual environment。

 so I'll do that first we'll say Python 3 M V and V， Tilde。

 and we'll call this advanced testing as well。I'll source it。Advanced testing。Be activate。 Okay。

 now that I've got that， I can seed into that directory and notice that this environment here from。

From cloud9， it's pretty nice。 it's got a great editor does， you know syntax highlighting everything。

 So if I want to just get this thing work working， what do I do。

 I can benefit from all that hard work I did before by doing a。😊，A make install。Do make install。

Now do you make tests？There we go。 So things work work here， make Li， everythings。

 everything's going well。 And if I do it make all right， I can just test everything at the same time。

 That's probably the first thing I should have done。So everything's working。

 the only thing I need to do though is add that code build file， which is we see it's right here。

 it's called build spec or sorry build spec。yml。I'm going to do that。

 I'm just going to use this as a template。And I'm going to go back here， put these together。

And I'm going to say touch。Build spec。yMl。Build spec at YM， there we go。So to run this thing。

 I'm going to paste it in here。I'm just going to pull out the stuff that I don't need。

 so I don't need environmental variables。And for installation。Build。Install commands。

 we can just go through here and we can say。Phases， we've got to install， build。Post build commands。

I think we can just say that。We can just say like install。Here， which would be。Make it stall。

And then we can say the rest would be testing right， we can just keep it simple and then we can say。

 you know， testing。Testing completed。So what I'll do here is I will say make Lnt。OrI mean。

 I guess I could break it up into pieces if I wanted to。But I'll be lazy testing Liin。Make links。

 and then we'll do this。 We'll say， make test。So， in theory。This should work。If we do this。

And so if I say get add， build spec。Get commit。Adding build spec。For testing on AWS。

 this should get me。Cooking here。Let's go ahead and do that。And so if I go back to code build here。

 I'm okay with sayingBuild spec。yl because I have all the build commands in this file。

 I personally think it's the way to go because it's less magic。

And it's not hidden inside of this editor。 Okay， so what else do we need to do。

 I could create artifacts， for example。And those could go to S3， I could cast things。

 do encryption as well， like if I need to encrypt the artifacts。

But I think we're ready to go and so we can say。I don't think we can do a space in there if that was the problem。

 so let's go ahead and fix this。Build commands， no， we don't want to do that。

 we want to do build spec， okay。Let's。嗯。Could build advanced。Oh。There we go。

It was not too smart the way it creates the service role。Okay， so。In theory here。

 let's grab this badge first。And we will go to。This project and boy。

 we got a lot of badges in here now。We have Github actions， code climate， let's go to。AWS code build。

Here， and let's throw that in there。That looks。Like a weird badge， though。

 Let's just double check here。 Is that really what they want me to do。Bad URL。

It's kind of looks sloppy， but okay。We'll just throw that in there like this and let's see what it looks like actually。

Commit changes。H， yeah， it doesn't look like a badge to me， it looks like something else。嗯。Yeah。

 I think I would have to do something a little bit trickier to make it into a badge。

 Like I think I have to。Go here and do something like they did before， which is。Say， like。This。

 and then put in。This and say。Bench。Ew badge。Like this and then put in the right markdown syntax。

And let's go ahead and save that。Hopefully， that makes our badge appear。

Not kind of spend a lot of time on that， but anyway there's we can get that working later。

 but next step here。You've successfully created the project， let's go ahead and start the build。And。

Let's see what happens， so it's building。And we can look at this thing in action here and we can actually tail it and if we get lucky。

 it'll all work on the first try。

![](img/79226208ff337a7992b7d265f23352fc_10.png)

Okay， so it looks like invalident build spec name testing and Linting expects build， install。

 post build， prebu， okay so it looks like you have to call the build spec a very particular name。

 which is not a problem， so let's go ahead and fix that。



![](img/79226208ff337a7992b7d265f23352fc_12.png)

So it wants。嗯。A very particular name for this， so we'll just call this build and I'm going to go ahead and make that change。

Get add。Commit。Now this should automatically trigger。Here， and。Thisし。

So I believe this should automatically trigger。Because we told it to automatically trigger。

Let's go back。Here。😔，And look， there we go， so we see it automatically tests again because of the push changes。

Whihi is nice so I can also take a look at this project and we should be able to look at the tail and also。



![](img/79226208ff337a7992b7d265f23352fc_14.png)

See it in action。Okay， so we went to install， it's going through and it's installing the code。

So so far so good。And then for the build phase， right。

 we look we can see that it was able to successfully test it。

And we're good to go so we we we've got this process completely working， we can see this successful。



![](img/79226208ff337a7992b7d265f23352fc_16.png)

And。We can we can look at all the different build details。 So this is a nice option as well for AWS。

 especially if you're going to do deployment to somewhere like elastic bean stock， you know。

 to a virtual machine to。😊，EWbus Lambda is to set up the process with code build。Here。Really。

 the last thing I need to do here is potentially。Just shut this thing down because I don't need it it accomplished the job that I needed to do。

So we've been able to successfully get it to work on the AWS environment and so really what of the last things that we can do is to。

Potentially get it into a slightly more complex。You know， testing structure。

 so what I can do is if I go to advanced testing techniques here。I've already got AWS set。

 I've got the formatting， I've got all this stuff set up。

 but we're only testing the Hol world script， what if I want to do some something like test the command line tool。

 let's get into that next here and build out that'll probably be the last thing that I can cover is how do I test a functional test for a command line tool using the Python ecosystem。

Fortunately， that's pretty straightforward。Once this code space wakes up， And if this。

 if this code space is taking too long。Give it maybe a few more seconds， I can also use Cloud 9。

know either one， it doesn't matter to me which one I use。Just for I'm almost giving up on it。

What I might just do。Is just use cloud 9 again because cloud 9 is actually just as good。

 so let's go back to cloud 9 here。And just wake that one back up again that I was just in。

 here we go。Because I don't think it's shut down yet。There we go。

 So it's still we'll just use cloud9。 Okay， so the next thing that I can do is use a build a command lane tool。

 So to do that I'll say test。Hello， C I。So we've only tested initially here some really basic things like this thing like you know。

 doesn't really do a lot， but a command tool I think is one of the funnest things to play around with and so I'm going to look at a previous example project here。

That I had。That。That we can just take a little bit of code from， so this function bike ridder repo。

If I look at this Ho Camle tool here。You can see here a very basic commandmein tool， I import click。

 I import a function， and I call it like this。I can actually do something similar here。

And I'll just tweak it， though， to change it the way I've got the code set up here。

 So I'm going to just paste this in and just change everything。

 So I'm going to say from hello import add。Like this。And then。I'm also going to。

Just clean things up here a little bit， and。Notice that it says no add because it's add this， right。

 So it's it's the syntax highlighting is helping you here。 And this one， I'll just say。Call add。

I'll add this and I'll see the options that pass in would be。Click。Click that option。And we'll do a。

Why？And an x。And we can add even a help message here that says。First numbered add。Number2 add。

And then we can do help is。Second number to add。Like this。

 and then we know that it's going to take an x a y in here， so we pass those in。

And then we just get the results will'll be。Add this。And it will be x and Y like that。

And what we can do as well。Is that I can actually add some fancy like syntax highlight or some output with click。

 that's one of the cool things that it does。Is that。It will let me do some。

Some stuff that makes it look a little bit prettier。

 So I'll say call add this right So this is I'm able to reuse that existing code that's well tested and has everything set up。

 And I've got now a command line tool that that I can actually use。

 So' this looks like it would probably work。 So how do I run this， I'm going to say。Well。

 first I'll make it executable， so I'll say chma。Plus X。Hello， C I。

And then I will also put a Shiang line at the top。So do this， so say here user bin EV。Python。

And then we'll go ahead and run this thing。With help， just to see the help menu。

 notice that I don't have any help so it's good and change that。Sa啊。This is a CLI that adds X and Y。

Right sot doesn't have a lot of stuff going on， but notice that can I can check this out so now。

If I go through here and I say。D's just x is1。And that's just y is2。

We can see that we've got everything。In theory， working， although。That is not。

What I think should be happening。 So it says here's one， here's 2。 So this is x and it's a string。

 Well， the reason why。Is that。Well， this helps us debug things， right， that。

And this is actually a pretty tricky bug here is you can add two strings together。

And so in this particular example， we have to figure out a fix here。

You know you could do a bunch of different things， you could say if it's a string。

 do this or whatever， but in our particular case， just to keep things simple。

 maybe what I could do is I think that click you can convert it to a integer so let's say click。

Can integer。Arguments。So if we go to click here。😔，出出。Let's see type inch integer， there we go。

So we could do this right， so we could go back here。

 There's a bunch of different ways we could fix this， but let's just do this。Let's just say。

Type it's required and it's type integer。So now what happens？There we go。

 we were able to fix it just by using the click tool themselves。 So we got that cooking。

 let's really quickly build a test。 So if we go to test here， we can say。And again。

 I'm going to leverage some code I've got earlier。Just to make things simpler。And I'll say。

We want to do something like this。So I want to do import the click runner。So let's do that first。嗯。

Do that。 And then。We just need to add a functional test for this and so to do that。

 I'll do something like this。And what this will do is it'll say test。We'll just say test CLI。

We invoked the。Commandline tool runner。And then I'll need to call the function itself。

 so I need to look at what did I call that function， I call it call add this。

So we'll put that in there。Call add this and we know that it's going to take two things。

 so it's going to take。Can x。Of one。And then we also know it's going to take a Y。

With a dash dash on it。And then it's also and we'll give that a one and so the status code should be zero and we should see assertt。

That， too。Is in the output。And let's just double check this， why is it complaining？No， oh。

 because we need to。嗯。Import it from the Camme tool。 so we can say from。Hello， CI。Import。

Call at this。 Call at this。Like that。 There we go。 So that's why this editor is pretty handy to have syntax highlighting。

 Okay， everything looks good here。 Let's go ahead and say make tests。Boom， we got it。

 things are working now。What we don't。Have， though。

 is the test coverage report for the chamelean tool。Let's go ahead and do that。 Let's go to the。

Make fileile here or just tweak it。Go through here and say D Cove。Equals test hello。Like that。Okay。

And make tests， there we go。嗯。That。Should have shown the test coverage report， I'm not sure。

Why the test coverage， O， module test ho was never。Imported because Hello CLI is the name of it。

 Hello CI。There we go。There we go， so we see that CLIs got good test coverage。

 hellellos got good test coverage， let's go ahead and come in all this stuff， get status。

 we'll add in。All these changes。Adding in testing for。CLI。

And the great thing about the way we set all this stuff up。Is that。Because of the make file style。

We're not doing weird things in different projects and putting hidden commands in AWS and hidden commands and Gitub actions and everything's brutalri is that whenever I make a change to this。

If we go back to code build， for example。And we look at it， everything should be the same， right。

 So if we go to code build。Even though I did a bunch of changes here。

 I didn't have to change one thing in this project because it's doing the same thing right。

 It's just doing the the test of。

![](img/79226208ff337a7992b7d265f23352fc_18.png)

，Make install， make li， make test and likewise， if we go to what， that thing really hung。

 I'm glad I abandoned ship if we go to。

![](img/79226208ff337a7992b7d265f23352fc_20.png)

Get up actions here。And I go to advanced testing here。And we look at。The GitHub actions。

Let's go to actions。We can see that that works。All this stuff worked here and also this code build。



![](img/79226208ff337a7992b7d265f23352fc_22.png)

It looks like it's working as well right so we didn't have to change anything it can work with multiple build systems at the same time so。

There's a lot of advantages to using this make file setup up here and hopefully this shows why it's so helpful。



![](img/79226208ff337a7992b7d265f23352fc_24.png)

![](img/79226208ff337a7992b7d265f23352fc_25.png)