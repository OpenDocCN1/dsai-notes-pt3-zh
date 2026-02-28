# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p51 51_03_12_AWS Lambda Hello World.zh_en -BV1tz421i7Ev_p51-

![](img/98628112bdffe3f3677cc5bc862225f0_0.png)

Let's dive into building an AWS Lambda function that returns back a result through API Gateway to get started。

 I'm going to go to a repo NOAAGt AWS Lambda here and I'm going to clone this。

 so go ahead and copy that。And type in git clone。Now notice that it said I can't connect because I don't have an SSH key。

 so I'm going to go ahead and create those SSH keys， SSH keyGin。Dash T RA。

Press return a few times and then I can actually print out this public key here to give it to GitHub。

 so I'm going to go through and say cat。Paste that out。

 and I'm going to grab this whole block of text up to the end here， which is SSH RA。

Next I'll go over to my Github profile and I will select settings here。

 so if I go ahead and select settings over that got it open， I can scroll down to SSH and GPG keys。

 create a new one， we'll call this AWS Lambda。Deev。Here we go， paste that in。

And it lasts for my password and now that it's set up。

 I can go back here and actually just type in the up arrow until I get to that command。

And then clone it。Now what I'll want to do is CDd into this AWS Lambda directory because there's a script here that may or may not be useful depending on how much you use your Lambda environment。

 notice it's called resize here。And in particular， if you type in DF Space dash H。

 it will show you that there's only a couple gigs available by default with AWs Lambda on Cloud 9 when you're developing。

 and if you run this resize command， if I say chmod plus x。

And then run it what'll happen is that it'll resize the disk to be a 20 gig disk。

 so M gives me a little bit more room for work where I would be using things like containers。

 which can take up a lot of room。Now， if I run this DFS H command again notice that there's a lot more room。

 so this is just a nice trick to be aware of and it's something you can get from this repo。

 Now the next thing I'm going to do to get started here is I'm going to run a command called Sam and knit。

And if I type in Sam， space， I IT。This will actually initialize a new Lambda function for me。

 so I'm going to go ahead and say yes， I want to do that。

 I want to do a quick start template so I'll select one。

And then which kind of package would you like to build。

 you know either a zip an artifact is a zip uploaded to S3 or an image artifactact is an image uploaded to an ECR image repository Now with this one。

 this is actually a containerized version of a lambmbda and it would live in elastic container registry。

 I'm going to go ahead and select two here。And then notice it gives me some options for base images so you know what do I want to do there's lots of different programming languages I'm going to select four here if we scroll you know down here you can see there's several options。

 I'm going to select Amazon Python 38 base so go ahead and select that。

And then what do we want to call this， Let's go ahead and call this Hello world。Lambda。

And we'll call this 2021。There we go。And it's gonna go through and give me some additional information here So do I want a quick start。

 let's say maybe a psychic learn project which which is pretty neat or do I want to go through and build just a regular hello world application。

 I'm going go through here and say hello world Lambda image application there we go and then the next steps can be read out here and readme file So here we go I'm going to go to these next steps here inside of this project and let's go ahead and look at this if I go to this hello world Lambda project you can see there's a readme that goes through and tells me step by step what I need to do So these might change slightly in the future there might be slightly different versions but Sam and it is a great way to get started So I'm going to go through and just do exactly what it says so it's gonna say Sam build so let's go ahead and run that first so I'm going to seed into this directory that I created。

And then I'm going to type in SamBuild。There we go and now it's going to go through and it's going to dockerize a Lambda environment for me and what's great about this is I can even test things locally by using this new containerized workflow for AWS lambda so really you can think of a container as a way of emulating what's going to happen in production。

So there we go， we've got this thing created now if I want to look at the actual application here itself it's going to be inside of this。

 this Hello world and notice here that it really is a very simple application that just you basically returns backHello world。

 if I wanted to change this I can change this into other things。

 but here we go we've got this hellello world application， and now if I want to invoke it。

 I can do what it says I can say Sam local invoke。And this will actually go through here and test this out right so it'll give me the ability to invoke it there we go we can see that it actually called it so really we're done in a sense in testing this locally so the next step would be to do a deploy so let's go ahead and scroll back you know through here and see you know how we would do this。

Well what I could do is I could say Sam deployy guided， so I'm going to go ahead and do that。

 I'm going to say Sam deployy guided， and then this will go through and ask me what I want to call this stack。

 we'll again call this hellello world stack maybe maybe 2021。

And then it'll ask me to select the region， we'll say US East， that's good， what image repository。

 sure let's go ahead and use that。Leave the default here for image repository for hello world function。

 Now， notice that。It will it will actually want me to give it a location to put this containerized image so what I can do is actually go to the container registry here real quick and create a new repo just for this and what we just call this hello world repo like that。

And let's go ahead and create this repository。And by the way， it doesn't want uppercase。

 so I'll go ahead and change that， we'll just say hello world。Repo， there we go。

And we'll scroll down here。And there we go， and I can just copy this UI。Or copy the repository name。

 let's go ahead and try that so we'll say。Does that work Oh it doesn't like that one。

 so let's go ahead and do it again。 This time we'll put in the the full UI。

 so I'll go ahead and copy this。And from here， again， we can just say hellello world。呃。2021。

Go through here， paste this in。Are you sure you want to deploy Yeah， we'll go ahead and do that。

 allow Sam to create the necessary permissions， we'll go ahead and do that that's fine。

 we don't care about authentication and then also we want to save the arguments to a file and then create this config file。

There we go， so basically what's happening now is it's taking this local container and it's pushing it to the Amazon container registry。

And then once we do this， it will then be able to deploy it from that containerized environment。

 so let's go ahead and watch the thing in action， and this is also one of the great things about using the cloud9 environment is that allows me to have fast interaction between services that are in AWS and so in particular inside of AWS you're able to push push your code into a new environment。

 go through and get access to you really data center to data center speed because it's not my laptop which could be let's say on a wireless network or something like that。

Okay， it looks like it's。Getting close to being done here， there we go pushed。

 and now notice that it's uploading this now。To the final location。

 right so it's putting these final changes here。Perfect， and it says。

 do you really want to deploy if we scroll out and look at the output。

 you can see it's using a infrastructure as code service called cloud formation to deploy it。 Yes。

 we do we want to deploy this change and what will happen is that I can actually after this goes through and deploys I can actually go through and look at that Lada application in production as well and so that's one of the useful things about using this whole end to end feedback loop is that it really solves the production deployment aspect of deploying a Lambda function So this really is using best practices from AWS they're all combined inside of this tool and then it goes through and just with a couple commands allows you to deploy this to production So once this is deployed what will happen。

I I'll be able to invoke it by using this tool over here。

 AWS Explorer and also I'll be able to invoke it by using the function itself in AWS Lambda notice that it's available now with API gateway as well it's hooking up all these final components and so let's give this just a second longer here and then what will happen is that I'll be able to test it out so now notice here that it gave me this endpoint so if I just scroll here because again it's a get function it just returns back a result。

We can actually curl this。And we'll return back a payload for us there we go。

 we can see that hellello world is working and so even if I put this into a web browser as well。

 you can see there we go， hellello world so we've been able to go full in and deploy it if we want to look at it inside of the AWS environment I can also go to that Lambda function and we should be able to see it as well。

 there we go there's a hellello world function it's been deployed you can see it's been last modified and I can actually invoke it if I wanted to directly inside of here so if I go through here and just give it an empty payload doesn't accept anything we can actually say invoke and notice that it says same thing says hellello world and and even further notice that here's the trigger。

 this API gateway trigger is that it'll give me the URL as well I can invoke it that way。

Yet one more way to invoke it is， again， if I go to AWS here and I go to Lambda。

I could go through and find that hollowello world function and invoke it。

 it's I think it's here here we goHello world 2021 if I right click， I can say invoke on AWS。

And notice that it gives me back this neat little widget here and I can say do I want to give it anything。

 no we don't care just invoke it there we go， we can see that it works so there's several ways to test your Lada function including basically builtin integration into the terminal personally I like the command line I think that's one of the better ways to test a hello world application。



![](img/98628112bdffe3f3677cc5bc862225f0_2.png)

![](img/98628112bdffe3f3677cc5bc862225f0_3.png)