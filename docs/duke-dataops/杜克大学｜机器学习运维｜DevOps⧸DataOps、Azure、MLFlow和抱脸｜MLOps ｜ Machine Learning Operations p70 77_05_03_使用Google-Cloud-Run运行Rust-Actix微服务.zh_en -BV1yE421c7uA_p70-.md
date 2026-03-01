# 杜克大学｜机器学习运维｜DevOps⧸DataOps、Azure、MLFlow和抱脸｜MLOps ｜ Machine Learning Operations p70 77_05_03_使用Google-Cloud-Run运行Rust-Actix微服务.zh_en -BV1yE421c7uA_p70-

![](img/8822931ca1ee39dbd086b1e8b217bcd7_0.png)

All right， I'm live with assimilate Google cloud， and I'm going to talk about rust here。

And really in a blind way actually， just play around with what you can do with Ru in terms of the Google Cloud platform。

And to start off with one of the things would be to just see if you have the rest compiler install。

 etc cetera， so inside of the cloudJo environment you could actually do this right you could go to rest up。

And you can actually just type this command in and install rust inside of this environment。

 So I think this is not a bad way to go。 Now， obviously this is ephemeral。

 So that's not going to persist between different states。 But again。

 if you just want to do a quick and dirty rust installation。

 this is reasonable in terms of getting things working。

 So let's go ahead and try this real quick And now I can actually just source the cargo environments and try it out。

 So you can see pretty easy actually to install rust inside of Google Cloud。

 And then if I just type in cargo new hello and I want make a hello world CDd into hello。

From you know， VI or whatever， just edit the the the program。

 But I also can just type in Car will run because they already build a hello world for me。

 So we've got hollowo world working inside of。A Google Cloud channel environment now what I'm kind of curious about is if I go to the editor here。

 this is actually a more powerful way to work with Google Cloud because it provisions an editor and has a lot of like neat tricks that you can play around with and in fact。

 if I click on terminal。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_2.png)

This is actually not bad now it is a little bit annoying that it's whites。And。If I go to。Let's see。

 color theme。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_4.png)

Dark visual studio。 There you go。 That's a little bit better。 And also。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_6.png)

The other one that I'm kind of curious about， if I check this off， says when you disable this。

 all files from the session。Will be lost。😔，You'll return to the default experience。

I don't know why would ephemeral to me means， it means ephemeral。 I'm not sure why， why that is。

 is an option there。 But anyway， I just wanted to edit the source code a little bit and play around with it。

 So let's say hello world。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_8.png)

GCP。From rust。And let's recompile it。So let's type in。Cargo， run。Oh。LetSee。

 we need to go the hellello gargo run。There we go， Holello world， so yeah， I mean。

 you can also edit inside of your we could we could even create a make file inside。Example。

 if I wanted to say L。What's interesting once you start getting used to a coppi it's hard to not program with it so that's one downside。

 but i'm going to look at。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_10.png)

I don't know， like a make file from another project and just copy it so I can I can use it and we can go here and we can see。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_12.png)

That we have format L test， run， et cea。 So let's go ahead and do this。

 like and take you make format。There we go。And then we would say make L。It did right。

 and then we can say make run to run it。So that's kind of neat what would be kind of interesting though。

 is to see what are the things that we could do。Inside of here。

 and I believe if I remember correctly， if you click on cloud code here。

It actually will let you do more sophisticated things。

 So we could actually create a Kubernetes sample app。 We could do a cloud run app。

 We could do cloud APIs。 I think the cloud run。😊，Looks。Promising， though， for rust。

And I'm kind of curious what will happen。 So if we just say create a new cloud run app。

 let's try that。No。It is annoying that。It only gives you these language choices。

 but I'm going to pick go and see if I can hack it。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_14.png)

And can we can say display hidden files。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_16.png)

And I'm just going to see if I can just hack together a rust solution here。

 So this is definitely not a。Like a default workflow。 But if we look in here。

We can see there's a Docker file， which is probably the part that's the most important to be aware of。

 And I could probably just figure out how to reverse engineer this thing。

So we have an entry point app。Let's see what else do we have and we have。The code。

 I don't think we really need to do anything。Inside of here。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_18.png)

I think I can just swap it out so I already have a。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_20.png)

A web service in this repo。And so what I'm going to do is I'm going to take like a。

Like a hollow world web service。And here we go。 This looks like a good one。 What is。

 what is this one， So this looks like。This。Web Docker， let's try that。

 let's go ahead and grab that service。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_22.png)

And let's see if we can hack together a solution to get R working in cloud run。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_24.png)

And then I can go to。😔。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_26.png)

We can do cargo new， right so I'm going to say as well。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_28.png)

no， cargo and knit will do and I probably want to delete a lot of these files so I'm going to just delete this。

And we can probably。Also。RMD RFf image。Also， R M。Go。Profiles。And we can also。RM D RFF assets。

So there should be a lot less stuff here， and we can also Rm。The index。No。

I should be able to do cargo。A knit。same name， I'll just name it the same web， we'll call web Docker。

嗯。There we go。 Now that I've got web Docker， I can go back to this project。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_30.png)

And just basically copy something I've already built before， so I'm going to。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_32.png)

I think this is just a random fruit demo。 So I'm going to do。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_34.png)

Exsource。Bibdt R S。And then I'm going to paste this in。Which is the code for the random fruit。

 I'm then going to go to the main， which will be the main function for this web app。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_36.png)

![](img/8822931ca1ee39dbd086b1e8b217bcd7_37.png)

Which is right here。And let's go ahead and do thats。What's good in here。

And then let's go to the cargo file。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_39.png)

Which also， I'm going to have to tweak， which doesn't look that complex。 Actually。

 I just need to do a couple dependencies。 Let's go to my cargo file。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_41.png)

Put those in。And now， I think。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_43.png)

We can even。Put a mig file in here， just to be lazy。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_45.png)

And because I like to be lazy。Let's copy this。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_47.png)

What do you lunch in。And。Install， build， run Docker， format， Li， test， all this stuff。

That's another one。At， I think， is。Good to， to play around with this to linknt it now。

 So I'm kind of optimistic， actually， that this is going to work for cloud run。

Because there's no technical reason it shouldn't work。 So if you。

 I guess if you want to containerize something。It's possible it should be easy with rust to build a containerized cloud run application。

 so kind of curious is still compiling here。And we'll see if this will actually work。Okay。

Still running。😔，Now， this might be a situation to where。

The more powerful your environment is the better but。Maybe I don't care for right now。

I don't think the Cloudhell editor is necessarily like super， super performance。

And I don't know how you open up another shell here。Unless you can do oh new terminal。Split terminal。

 How about that， Split terminal。So if I just do H top。We can see her that。It's definitely compiling。

Or yeah， it's compiling the software as it does the li。Or doing some kind of a partial compile。

But you can see here it's just pegging the machine， which is not that powerful。

Well' well it's doing a compilation。It isn't using a lot of memory， though。

 which which is kind of interesting， but not not a bad idea to。You know。

 check out the stats of the system。Wirred you a compilation。 I guess I'm getting。

Spoiled by using the code spaces from Github that are 16 core they're they're pretty fun to play around with because of how fast and powerful。

 So yeah， if you're compiling code a lot。Having a very powerful machine is actually quite helpful。

Like a Mac that has， you know， 12 core is definitely not bad to have。But so this is， this is finally。

Still compiling here， we'll just let this thing keep cranking。Here we go。 So， yeah， wow。

 that's a good sign。 And then if I say， you know， as well， like a format or something like that。

 let's， let's do make that。problemSo if I say cargo run， let's let's kill this for a second。

 let's say cargo run。It's going to then go and do the compile。And I'm curious。What will happen here。

😔，Once we do the compile。And。Only a couple more steps left。All right， well， that appeared to be。

Working fine。 Now， if I do。Split terminal。And I say， curl。Local host。E。There we go。

 Hollow world random fruit。And I also could do。I think is it fruit。 There we go。 Yeah。

 So if I just keep doing this， you can see it getting random fruits。 So not bad。

 That was actually pretty easy。 I mean， it is just a container， so it shouldn't be too tricky。 Now。

 the trick is， how do I deploy this。So now that I'm in cloud Run。We can do oh run app on Iulator。 Oh。

 let's try that。 That's kind of cool。So it's going to go through。

 It's going to verify that that dependencies。We'll close that。Which is is kind of interesting。

And build environments。 So you could。Tell local build， Docker。Let's run it。 let's see what happens。

Dependencies check successful。 That's a good sign。And。I don't。😔，No。😔，Oh， here we go， oh。

 so it's going to now run it in mini cube。Which is kind of cool。So， this is a very。You know。

 interesting environment for Google Cloud。And I think it works pretty well for， for rust。

 which is pretty interesting。 So it's， it's going to get mini cube installed here。Such that。

It's able to。Iulate what would happen in a more of a production deploy so it's going to create a docker container with two CPUs。

4000， you know， four gigs of Ram。And it'll take a little bit of time。Okay， starting mini cube。

Boooting up control plane。All right。MiniC has been scheduled to stop automatically after cloud exitit update initiated。

Yeah。あ。え。All right。So now it's configuring this deployment。And。Build started。

And we can see that it says it's running。Now what does that do， oh， that's for debugging。No。

 I don't know。Next year。If I have to， I think it's still it's still building。 So。

 so I think I need to wait a little bit longer。 But this is kind of neat。 So it's got。

The ability to restart。Stop， debug。嗯。What is this do debug console？The call stack。

So a pretty interesting little environment here。And if we go。2。😔，These toggled。

Components gives you some other things。I'm not sure if it's going to work。

100% for Rus because this was originally a go config but。We'll see in a second。

 so I guess it's building。The container， which， which could take a little bit of time because if we remember。

The container， I did do something a little bit tricky， which is， I say from rust dot a rust latest。

Go ahead， and。Build into another smaller container。

 This is a fairly new technique that I've been using with with rust。

 which is that you use a bigger image first。And then you push the bigger image into a smaller image。

 which in this case would be the Debian busster slim。嗯。And。So it may take a little bit of time now。

 I don't know what happens if you click this。Oh， I see。Maybe it's， it just shows。

What it's doing here。And。Development session。😔，Kubernetes。

 so it looks like it's connecting some kind of Kubernetes。Set up here。

We can still see this thing going。But we， again， we see it's still building the container here。Yeah。

 what I don't。Select and start running。😔，Now， I don't know if it's just running， actually。

 that's the that's the good question here is is it do I do anything else？Or， or not。

Although the fact that it's said is still building in the container。Makes me think that。

I should let it。Do a little bit more work here。Because I don't see。😔，Other steps run locally。

So there is this， this is the demo。Switch project， no cloud run service found。😔。

So I guess once this thing is finally done， if it's done， you would then select this button。Which is。

 you'd say， deploy to cloud。 Now， I could try that。As well。And let's see what that does。

Show detailed logs here。Because really， that's what I wanted to do was deploy this to。Cloud run。

Getting Google Cloud login states。Checking the API status。Oh。So。Service name。😔，I think fully managed。

 this would be if you wanted to do anthos， which is extended。Version。嗯。This looks okay， local。

Doctor Bill deploy， Let's try that out。So， it looks pretty。Point and clicky， right。

 is I just go through。To cloud run here， and I just click。Theloy， it gives me a default window。

And then it's going to push this。Into。Into the into the cloud let's。Let's check this out。

So I guess it's just showing me the Docker build process， which。

Is at least reassuring because it makes it。 so I don't。Feel like you have to wait too long。 So。

 so this is the part that I was curious about， which is this rust builder。I don't know how long that。

 oh， actually， the first phase of it was only 28 seconds。嗯。And you can see here。

 it's this stuff's that I was wondering if it would take a long time。

And it's already done that now it's going to install all of the dependencies。Inside。

Which is it basically is it's going to put the binary。Because the binary was already built。

 it should just push it right inside of here。And it looks like it's going to put it in user。

Copy from。To user local bin。What's interesting is， why is it a user source web Docker。Not sure。

But we'll find out in a second。And we can see。I don't think there's anything else this will show up。

But。We're about to find out if Cloud Run works for rust， if it does， that'll be a good live stream。

Updating the Cates index。So we， we can see that the。

Other parts of the build process were pretty quick。The， the builder。

 which is what I thought would take a long time up。 Here we go。 So now it's actually。Compiling。

 h I thought the compile would have been here， but。So it's now compiling， I think。

 could take a little bit of time。We're about to find out how long it's going to take。

it could take a few minutes to compile actually， we'll find out。Now， Tokyo。

Is the Eync library that a lot of people use。Extremely common for rust。And then。

Actics is the web service， kind of like fast API for Python。And。We see some other libraries here。

This Jason parsing library。Is one， I don't totally understand all the features of it， but I。

 but I do use it when I use it with。Jason。Number CPUs。

 It must be something that is able to keep track of the number of CPUs。Available to rest。

 potentially。And that's a thing that I might look into later。Okay。

 now it's actually compiling the actual Acts server。Which is again， one of the more popular。

 if not the most popular web framework for rest， I think this is dominates by quite a bit。

From what I've seen in at one point， it was the fastest web service in the world。It just depends on。

Whether people are are how much they're hacking unsafe code， I guess， at least with my understanding。

Okay， we can go a little bit more here。And。There we go， compiling Acttics。Compiling Web Docker。Okay。

Now， I think what this means is that it's。It's just making the binary。

Because web Docker is my project。And if we look at the code。😔，Yeah oh。Okay。

 maybe thought was going to have a problem， but it didn't。Deploying new service。Well， so far。

 no major problem setting the security policy， well， there we go。There's according。

 it says that it's running。

![](img/8822931ca1ee39dbd086b1e8b217bcd7_49.png)

And does it work？Oh。😮，So that was surprisingly easy。There we go。

 so we see we've deployed a publicly accessible web service。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_51.png)

Inlist to DCP。 So I guess the end of the。The story is that， yeah。

 it's not bad if you want to deploy cloud run services again right here。You want to deploy cloud run。

 you can just make containerized rest application， and I had zero problems deploying this inside of this cloud shell environment。

 So I want to just call it a day I was successful and I'll pick this up later All， talk to you later。



![](img/8822931ca1ee39dbd086b1e8b217bcd7_53.png)