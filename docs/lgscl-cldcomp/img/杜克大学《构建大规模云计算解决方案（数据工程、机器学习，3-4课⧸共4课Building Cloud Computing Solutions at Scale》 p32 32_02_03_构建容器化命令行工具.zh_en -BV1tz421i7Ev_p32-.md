# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p32 32_02_03_构建容器化命令行工具.zh_en -BV1tz421i7Ev_p32-

![](img/e899b155cf3cb165ce9797afe945b667_0.png)

Now， the other thing that might be interesting is I think， yeah， this runs Docker as well。

What we could do。Is I believe I have another project that does kmein tools in a slightly different way。

Which is called container from scratch。end。What we could do is basically。嗯。

Play around with this project as well。HereHere is a。Let me just briefly talk about some of the。

The reasons why you would want to use a container now。And then I'll get into that project。

 So in terms of a container。For commandlan tools， so we showed how a CLI is a great tool to build a feedback loop really quickly with GitHub。

 but also container is pretty interesting for commandlan tools in that you can package up the runtime。

Into a container， you know， very easily。And actually。Package that runtime into a CLI。嗯。

How can you this where you can push that code into something like Docker Hub？And let me show you。

 you know how this would actually work inside of that code space。 let's just keep cranking on this。

 So what I'm going to do。Is I'm just going to start building。

I'm going to take some stuff from that other project step by step。

 so I'm going to first go to this Docker file and I'm going to。Throw that in。Actually。

 before I even do that， let me just run it。 so first up， if you notice that there's a command here。

That allows me to， to。To run this command locally， so let's go ahead and take a look at this。

So if I go back to codespace。We can actually go like this。

And I'm going to run this remote command as a command line tool。 Let's go ahead and do that。

So it downloads this， runs it local。Usually takes a second to download a container。

Once you download it， notice this is a step that we actually ran that command line tool。

 so what's neat about this is。It's actually running click and it's doing all kinds of stuff but。

Big Joe， here we go。 Let's run。 So basically whatever all it does is it does a hello world。 You know。

 this is my container。嗯。Hello， this is my container right just it echoes out something that I have inside of here。

 So to me， this is actually one of the awesome ways to distribute command tools is。

Someone just runs this right you just pass this command to somebody at your work you say， hey。

 I built a commanding tool that does some job， don't even worry about what I did here we go just run this this piece of code So let's go ahead and like piece this application together ourselves and kind of tweak it a little bit and see if we can get the rest of this working in this this environment So what I'm gonna to do next here。

Is I'm going to。Create a Docker file that' that's how you create a container and so we can go here。

And go to this Docker file。And I'm just going to copy it。



![](img/e899b155cf3cb165ce9797afe945b667_2.png)

And let's go back to this。

![](img/e899b155cf3cb165ce9797afe945b667_4.png)

And let's go to this Docker file， notice how it recognizes it as well。So if we go here。U。It says。

 do you want to install the recommended extensions for Docker， sure？Let's， let's do that。 Let's。

 let's， let's。Okay， didn it， I don't know why it has a problem。

 maybe I don't need that extension anyway， but basically let's go back to Docker file。

And it looks like it's already recognized in it。 I'm going to say from Python 37，3。

 although because this is running which Python here。And if I say Python， this one's 383。

 let's actually just run the same version of Python， so let's change this to 383。Like that。

 and I'm going to create an apps structure in my container and I'm going to copy an application。

To the dot PY file。And then I'm going to install my packages。

 So I guess I'm missing this appt Py file here， so let's go ahead and create that one as well。

 So let's go ahead and say touch app Py and this is a really simple Kamelan tool here。

 So let's just look at what this one does。This one is here。It does almost nothing。

 so let's go back to this container。AndOr this this file and notice。

 let's even run it real quick so you can see what it does if I just say Python app。pyy。And I say。

 you know。Dawin again。I think it needs dashes name， yeah， dashsh name， so dashs name。There we go。

 it just echoes out。What's inside of here？I've got this simple command tool。

 I got this simple Docker container， so how do I test this out locally and containerize it？Well。

 what I can do is do a Docker build and I think I have this。Here is well。Which is。

I have another application that I'll pull into this that'll show me the build steps。

 but basically what I did。What I typically do。Is。Is I like？

I like to put like a shell script together。 I'm going to put this shell script in here that will that will let me run Docker right so I could do something similar to this like I could just say。

 you know like。Duck or build， make it like a bass script。And let's go ahead and do this。

 So let's just say like touch build essays or something like this。 And inside of here。

 I could just put whatever steps I wanted to run in this case， we'll call this one。

We'll call this click hello or something like this。Or click Echo maybe is better， click Echo。

And you don't need to do this per se， but it can be kind of nice to like。You know。

 have like a process where like list containers。呃。Where where you don't have to look up all the commands all the time。

 So we can say Docker image Ls。 So， so if I just， if I just basically， you know。

 make this executable。Like this。I can say build dosh， right， and we can see that in fact。嗯。

So it says it can't find。That Python 38， so let's use Python 37。Let's try that。There we go。

 so it was able to find Python 37 we're going to build up locally。After it's done。

 it should show us that there's a container local here。There we go。And。

We can see that there's now a container called click Echo。

 So now now that I have this local container。What I can do is do that same command that I did earlier so I can just do a history here and let's see it was like this。

 so let's just do let's even put this into the build process here。U。And we can see a run container。

Right like this。And so I say Docker run in this case， though。

 we know that the container's name is something different， it's called click echocho。

 so I just swap this part out here。Click echo。There we go and then this this should in theory。

 do the same thing that I did before， so I can actually just run this。Like this， refresh this。

And run this Docker command。 So this should run the same app。 And there we go。

 So now now we know that in theory， I could push this into， let's say。

 Docker hub or Amazon container registry or some other registry。

 So in a nutshell this is one of the you know great things about using an environment like。

GitHub code spaces is that it really does speed up development and also using containers in the click tool。

 so let's let's go ahead and check these in。Here we go， so Docker file， get add app。And get add。

 build。Check it in。Adding。Project。With Docker。And even to be nice here。

 I could ask them read me like I could say， you know。What it does。 So we have， you know。

 example we have click。CLI tool。Tool with full。Full continuous integration。And we also have。A。

A Docker command tool。呃。And we'll just say this is。A basic cookbook。For building。Cmeing tools。

For the modern era。There we go， so we got this documentation here。Perfect， get status。Get add readme。

 there we go， and let's just double check that everything works， adding changes。

And you could do more fancy stuff too。

![](img/e899b155cf3cb165ce9797afe945b667_6.png)

For example， Docker can be builted programmatically。



![](img/e899b155cf3cb165ce9797afe945b667_8.png)

I believe inside of Github actions， you could actually create a new workflow。 and in fact。

 I thought there's containers。Was a workflow here， I think you can search。

For different workflows but but you I believe you can actually build a container automatically if you wanted to。

You could， you could also。Push this to Docker Hub programmatically， I believe。Here we go。

 build a Docker container and publish it to the Google container reisttry。

If I wanted to deploy to Amazon or deploy to Google Cloud or whatever。

 it would actually be pretty straightforward。 So let me just show you that real quick so if I wanted to deploy to GKE I would just need to have my secrets which can be stored safely inside of here and then what I would do is I would。

Push this to Google's container registry。Build the project right here， here we go。

And then once it's been pushed to the container registry。

 then you could actually deploy it with Kubernetes and then actually have that running in in process。

 So this is pretty close what what this has already got set up here to being， you know。

 you could do a lot of things with this sandbox project here。



![](img/e899b155cf3cb165ce9797afe945b667_10.png)

![](img/e899b155cf3cb165ce9797afe945b667_11.png)