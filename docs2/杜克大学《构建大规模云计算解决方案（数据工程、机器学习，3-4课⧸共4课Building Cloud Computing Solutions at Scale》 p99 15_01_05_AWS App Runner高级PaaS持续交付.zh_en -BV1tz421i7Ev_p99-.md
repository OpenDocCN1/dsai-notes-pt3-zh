# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p99 15_01_05_AWS App Runner高级PaaS持续交付.zh_en -BV1tz421i7Ev_p99-

![](img/d38333f2e9b457a12d8dc39493f7390c_0.png)

Okay， what is AWS app runner here。 Well， let's take a look。

 This application runner allows you to add a source so you can go to Github。

 you can also go to a container and you can select it and use that as really the source of truth for your application automatically then you can go to configure a build and service setting。

 you can go to configure your containers number of CPUs。

 memory also auto scaling options and then also a health check。 Finally。

 you can go through just double checkck everythings working properly。

 And then this is really the beauty is that you can get a secure URL at the very end。

 So if you're wanting to do， for example， microservices you want to do MLops。

 This is really a powerful new way to deploy Abo applications into production。

 So let's go ahead and get started here and what I'm going do is I'm going start with logging into the terminal and。

I'm going to look at this EW app runner terminal here and show you that I've got two separate app runners running The first one is this one called CAAS here and look if I go to this URL。

You can see that there's a running application here and notice that it says something that's pretty interesting here it says。

 hey if I want to make some change， I can go to this route so let's go ahead and practice that if I go through here and I type in change notice the URL parameters here are setup that allow me to make changes and so I'm going move my browser a little bit lower here so you can see these URL parameters and then what I'm going to do is actually show you that what we can do here is put in 1 and let's say 34 cents this goes through and it gives me back the correct change and if I want to change it to another amount let's say 39 cents and 11 right we've got $45 quarters one dime and 4 pennies right so this is a microservice that is able to be fully directional and allow me to actually go through and and make changes to it now notice if we go back here。

If I click on this service， it gives me a little bit more information about this service so we've got a default domain setup and we also have a link to the source so let's go ahead and take a look at that source and notice here that this is an application that I was previously using for elastic Bestock also I've used the same application for what I call a container as a service which is Fargate and so really all we need to do here is look at this application and notice that it's a pretty small flask application we import flask I go through here and I make the correct amount of change and that's really the core logic of the application and then I just need to create a route here I create a hello world which I think is a very good idea when you're playing around with things is make sure you have a hello world application route so that you can test things and then the more complex route does again what we just showed is it correctly makes a change it shows us。

TheThe dollar parameter and the cents parameter here and then notice that it's running on port 8080 so really this is the first application that we're going to go ahead and get running locally。

And so what I'm gonna do is I'm just gonna to do it again。

 so let's go back into this app runner here and we'll go through and we'll say create service notice that it gives us the ability to go to source and deployment I can pick a container registry that's one option and it could be either the private Amazon container registry or the public Amazon container registry which is really useful because if I was going to deploy something maybe internal to my company this could be an important option now the second thing that I can do is I don't have to just have a container I could also click source code repository and I've already hooked up my Gitthub into there and we can just toggle through and look for a particular repository that I want to deploy in this manner and so I'm going to type in here and say EKS Fargate tutorial which I've kind of hijacked here。

And then notice that there's actually a couple different options to do deployment there's manual。

 which I think is probably the best way to start out with。

 which allows you to manually deploy it either from the console like we're doing now or commandlan tool or automatic now automatic has the advantage of every time I make a change to the application and auto deployys let's go ahead and pick automatic here and we'll go ahead and say next now from here you have two options you can either deploy all your settings inside of the build server or you can use a configuration file for a more mature project I think it's probably a good idea to use a YaAml file for now though we're gonna to do is we're gonna do it all manually in the console I'm gonna pick Python 3 and then it's gonna say okay well how do I deploy my application now because I've already got this setup up here I have some commands that are easy to look at in terms of the make file I can just copy this command here and I can go back。

Or to my console。And just paste that in so I'm going to do a PIip install which will install the software that I need for my application and then it's going to ask for a start command so again we know that in the previous example here that this application is going to be running flask and flask I can just say Python app。

 py so we'll go ahead and do that we'll say Python app。

 Py and then for the port again it would need to correspond to what this says here which is port 8080 so I'm going to go ahead and put that in so port 8080。

There there we go and now I'll go to next and it'll say what's the service name we can just call this change app like that you know whatever it needs to be the specifications here and then here's where I could actually go through and you choose higher options if I had let's say a lot of memory that I was using in this application I could also do environmental variables if I needed to let's say talk to a database or some other resource and kind of swap it out I also can have autoscale capabilities as well so could this in particular can handle 100 simultaneous requests and then what it'll do is actually it could spin up to 100 requests per all the way up to 25 instances right so it could go up to 2500 simultaneous requests。

Also here， this is really a powerful feature is that this app runner itself will allow you to have the ability to do a health check。

 which it'll let us know if there's a problem and finally there's security where I could actually have an IAM role associated with it。

🤧嗯。3。2。1。Okay， now that we've looked through those options。

 I'm going to leave it all by default because I don't need to do anything in terms of changing the defaults。

I'm going to go through here to review just make sure that I've got everything set up here and then once I do this next section。

 it'll deploy the application， so it's go ahead and do this and what'll happen is while it's deploying it'll take let's say five minutes or so。

We can look at in fact the logs and it will show us step by step what it's doing。

 which is great because if I was going to deploy this to a virtual machine。

 I would need to maybe shell into the machine， take a look at everything that's happening but this really lets us see things step by step and you can see here service creation is set to operation in progress。

 here's the service creations that started。And then if you go through here as well。

 it'll show us both the application log and the deployment log so what we can do is just let this thing go through and then when it's done。

 what I'll be able to do is go again back to here and this status will change to a finished status。

Okay， now while this thing is being deployed， let me show you one of the best ways that I would recommend to you know test this thing out and that's using the AWS Cloudhell。

 So I'm going to go ahead and select that。 I'm going open up a new tab here and what we can do。



![](img/d38333f2e9b457a12d8dc39493f7390c_2.png)

Is when I open up this new tab， it'll again take maybe 30 seconds or so I can actually interact with different parts of my application。

 I can change it and I can even trigger continuous delivery operations if I've got that continuous delivery option set up so that's one of the great things about this Cloud shell environment is that it's a way where I can both control things inside the AWS ecosystem and I also can go through and trigger operations to deploy my code。

Okay so now that I've got this terminal set here， one of the things that I think is a great use case for this terminal is to actually curl an existing maybe application that's been deployed and make sure that it's working properly so if we can go back here again we see this there's the app runner。

 we add a source， we do the configuration we review it and then we get a secure URL so we can actually both change it inside of here that's one thing we can do and we can also receive that secure URL so what I'm going to do is。



![](img/d38333f2e9b457a12d8dc39493f7390c_4.png)

I'm going go back to that other application that I already had running right because we know that that is basically the mimic of this one and notice if I click on it。

 I can actually just copy that URL here and I can go back to my Cloud shell environment and I can actually do a curl。

 so let's go ahead and do that let's say a curl here。



![](img/d38333f2e9b457a12d8dc39493f7390c_6.png)

Pate that in and notice says， hey， I can make change at this route okay let's go ahead and do that change route we'll say change 134 there we go and I can test it out so this is one of the most useful aspects of the Cloud shellll in combination with the Azure app runner is it allows us to really verify that everything's working。



![](img/d38333f2e9b457a12d8dc39493f7390c_8.png)

All right， let's go back here， we can go to this service， now we see that it's running。

 look it says status running and if we click on it， we have a new domain here。

And what we can do is also look at the event log it saysC service it's successful。

 this is when the start time was， and so again I can go back here and either click on the browser。

 open it up and that will actually show me that this is working。

 I can go through here and do you know change $1。34 perfect or we can go what we did before here with this new change app and I can copy it and then I can actually test it out in this browserbased environment again go through here。

 curl it。

![](img/d38333f2e9b457a12d8dc39493f7390c_10.png)

Go through。Add that parameter change 134 rate so this is a great feedback loop to be able to use the terminal。

 you know， do things like administer AWS test out services。

 but then also use the console to rapidly develop things so。Now that we've got this set up。

 can we also test out whether the continuous delivery service works and what are a couple ways we can do this。

 well， one of the ways we can test this out。

![](img/d38333f2e9b457a12d8dc39493f7390c_12.png)

Is if I go back to this repo， I'm going to go to code here。

 I'm going to copy this and I'm going to just do a Git clone so I've already created SSH keys here and then put those into Gitthub and so if I type in Git clone paste this in I now have access to this repo I'm going to CD into this EKS repo here and then what I'm going to do is just make a very small change to a readme file so I'm going to use Vim and open this up。



![](img/d38333f2e9b457a12d8dc39493f7390c_14.png)

And I'm going to add a little note here that says， you know， maybe here we go， verified。

 deploy with AWS app runner， okay， let's go ahead and save this。And we'll say get status。

 add this in， we'll say get add， read me， get commit， let's go ahead and add this， adding changes。

And。Now what we can do is we can configure this if you want to not a bad idea。

 I'm going to go ahead and do that， I'm going to say noah。gi， atgmail。

com let's go ahead and do that and then I'm going to do this last thing which is I'm going to put my name in there。

This is a one time thing that you have to do the first time you use GitHub or sorry get on a new environment。

 and then we can go here and just actually say get push and that's going to go ahead and make that change。

And we can again go here and say get status oh I forgot to do the commit here。

 so let's go ahead and do that， let's say commit。And then we can do the Gi push There we go。

 So now we know we're making the change and what' will happen is that first let's verify that that changes is inside of here look we just see that those changes were made this is that comment and then if I go back to this environment look it already trigger the deployment because we told it to listen to changes in Github So this is really powerful because it allows us to do continuous delivery and continuous delivery means that my code is always in a deliverable state and it's ready to deploy those changes here and again now it's gonna to go through and do a new deployment。

 So if this was a new maybe a new route or you know some new functionality to the application this would go through and automatically deploy those changes So there's a lot to like about this Azure app service now that that's a basic microservice here let's move on to a more complex one next let's take a look at Python MLLops cookbook。



![](img/d38333f2e9b457a12d8dc39493f7390c_16.png)

![](img/d38333f2e9b457a12d8dc39493f7390c_17.png)

![](img/d38333f2e9b457a12d8dc39493f7390c_18.png)

This is something that's part of some recipes that I've triggered for the practical MLOs book。

 which is by O'Reilly operationalizing Mach learning into production。

 and what we're going to do is take a look at this general structure here。

You know you can actually pull a container right that's one thing we could do and we could actually test out a lot of this code。

 we also could run it locally in environment， there's a different list of files here。

 these are all the assets I have a make file， I have a requirements file。

 I have a commandline interface， I have a utilities file。

An application file there's a lot of code in here， but basically the key components are the app。

 which is still relatively simple， we use flask。I follow my own advice。

 I always make sure there's a hello world route here。

 and then I have a prediction route that all this does is it calls a library that allows me to predict what someone's height is from their weight。

 so it's an intentionally very simple machine learning application。

And you can see here this is how it works is very similar to the previous application。

 we have GitHub， we trigger a change and then that change goes through and it is able to deploy to some target like Fargate or Azure app services and in particular you can see here that I can also test it out locally in the command line and what we're going to do is we're going to deploy this machine learning application into production from scratch and test it out and see how simple it is to also make changes and deploy things to production with Azure。

I'm sorry with AWS app runner。 So let's go ahead and take a look here first at this console。

 And what I'm gonna do is。

![](img/d38333f2e9b457a12d8dc39493f7390c_20.png)

I'm going go out of this other directory and I'm going to look inside of this Python Emopps cookbook Here we go and what's nice about this EmOps cookbook is that I've also given you the ability to run things locally so if I wanted to for example。

 just test it out we could do this and you can see that it runs locally in this shell and I could kind of play around with it and do things with it locally also I have a utility which we're going to use in a little bit that will actually allow me to test out a running production system so if we go through here and we say us help here。

Notice that it has some options that says one of the things that it can do is it can do a prediction。

 okay， let's go ahead and do that and let's do a help message for it。We'll say predict。

And notice that it gives me the options of changing who the host is。

Also allowing me to put in the weight and then once I have those options I can actually do a prediction to production so again what I'm going to do here is I'm going to say a predict and we'll say host and I can go back to a previous application here let's go we see we have this running here and I'm going to select it and notice this is the URL and so I'm going to go ahead and copy that URL here。



![](img/d38333f2e9b457a12d8dc39493f7390c_22.png)

![](img/d38333f2e9b457a12d8dc39493f7390c_23.png)

And I'm going paste it inside as the host and I'm going to add predict to it right so I've already written some code that lets me test any endpoint often a good idea if we're deploying a machine learning application and then I'm going to add in the weight and let's go ahead and put 300 pounds what would my height be if I was a typical major League Base player that was 300 pounds here we go we got a response from this MLOs endpoint and it says that you probably would be six foot 8。

 what happens if we have maybe someone that's 150 pounds， maybe they're the shortstop。

We go through here and we run it in and it says that typical 150 pounder would be 5 foot11 in Major League Baseball so we've got a full endpoint here that allows us to really test a machine learning application and really the last thing I'll do real quick is just show you how I deploy this application again it's just as simple if we go back to this code here and we look at all the assets here。



![](img/d38333f2e9b457a12d8dc39493f7390c_25.png)

Really the main things that are important are there's a model that I trained earlier。

 there's the flask application here and then there's this command tool which again all it does is make a request to my deploy endpoint。

 so really there's not a lot of code that I need to get things running and then there's also a requirements file that has the specific versions of packages。

 So we can use the same pattern to deploy any kind of machine learning application let me just show you really quick how to set that up so we'll go through here and again we'll go to sign it to the console get into our AWs app runner and I'm gonna go ahead and create a new service and again I could could choose a container registry if I had pushed it to the Amazon container registry I'm going select the source code repo I'm going go through here and I'm going find that in lapps cookbook。

 there we go。Let's go through here， MLl Ops。There we go， Python andlock's cookbook。

And then from here I'm going to select again either manual or automatic。

 let's just use manual for this time and then I'm going to do the same thing。

 I'm going to select Python 3， build command it's going to do the same thing。

 it's going to be Pip install dashR requirements。txt and then the start command will be identical again because it's just a simple flask application。

 you know Python apppyY and then again I can just look at the application to double check what port it's running。

 it looks like it wants port 8080 so we'll go back here and we'll do port 8080 put that in and really that's the hardest part of the application is just pointing it to in application that you've already tested out locally and that it runs again you just call it a new service。

 we'll call this MLOps demo。Like this and we'll go ahead and say next it we go through here and it will deploy this service again it takes just a few minutes to deploy it and I can do everything that I did before so let's go ahead and summarize next everything that we did and why it's a so really a powerful feature for deploying machine learning applications into production。



![](img/d38333f2e9b457a12d8dc39493f7390c_27.png)

![](img/d38333f2e9b457a12d8dc39493f7390c_28.png)