# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p128 44_03_05_谷歌的边缘机器学习.zh_en -BV1tz421i7Ev_p128-

![](img/00eb09c89e9cead813efa69c14465817_0.png)

Let's talk a little bit about that workflow a bit next here is to kind of get into the this Google ecosystem。

 So if I go to the。GCP。ACons。Here， the workflow that I've seen most students do is that they will。

 this is probably the the golden path or the easiest way to do things is that。

You would go to Auto Viion。And you would upload some stuff。So here we go。

 Automobil visionion here you had create data。Inside of your， again， this is a flower data set。呃。

You know， train your model。 And when you train your model。

What's very important is to pick the mobile based model。 So if we went through here， we said train。

 we would select this option edge right download your model for offline use。

 And if you say continue really this doesn't matter that much when you're selecting your goals other than。

That you would want to decide how important is the highest accuracy versus the fastest prediction。

 So the smaller it is， it can make very low latency predictions and maybe that is actually important for let's say driving。

 like if you're going to do something with real-time object detection for vehicles。

 maybe you would want to have very low latency where if you're detecting。

 let's say handwriting maybe like this would be better to select。

 but let's just say we pick one of these。And then once you train it。Again， you can use six。

 you can use a bunch of hours for free when you start。

 but what will happen is if we go to test and use。Is that this。

Model will allow you to download it in one of these formats。

And so I think for a student that is going to。Do probably the easiest workflow is either going to be。

This one， T F light。The Corel or the coral， those are probably the three workflows that are the easiest。

Now the， let's just look briefly at this TF light workflow again here is that really the core idea is that。

You train your model in the cloud， and then you go through here and download the train model using this project。

And then it is simple as swapping out the model that they give you with the model that you trained in the cloud。

 so that's really the gist of this particular project and it'll appear as a labels。

 Txt file and a graph dot light file so this would be and I'll just throw this in here it would be you know put another section as devices for example so。

You know， additional。Devices we could we could go to。We have。Android。From。Tf light。That's one。

And then we also have， we go back to this。We could also pick the coremel so we know that we know a little bit more about the Corel now so we could export that ML model and run it on iOS or Mac。

 so we click here and we go to the view documents。 It's the same thing we were just looking at earlier。

 which is that that Apple device we'll accept the model that was exported from Google So Google will export it directly into the coreml format for us which is great and so we can say here。

 we can say iOS。Here。From TF from from， we'll say Google Automail。Right。

 and then the next one would be if we go to this。Would be the container， I think。

 is less relevant for us， but I would say quaal would probably be the next one that I would talk about。

 and I'm going to demo this in a second is how to do this step by step。

 But basically if we go to the products here。 the one that I think is probably the easiest to demo is this USB accelerator and the reason why it's easy is you just plug it into your computer and it works well with Debbieian Linux OSs 10 Windows compatible with raspberry Piboards pretty straightforward process to actually use this particular chip。

 and what's great about it is it has a Tpu physically on the piece of hardware so it has the prediction engine on top of it。

 and you can see here these are the instructions， the quick start on how to implement it on your device so。

How to set up the USB accelerator， how to perform an entrance。

 And then later how to how to create your own model。

 So so I'll just say this would be option another option here， which would be that a。Download。

From Google。Auttoel and put on。ACoral AI。Here's another one。And then yet another。

 what we'll call this additional。Computer vision。Devices and workflows。There we go。

So andll also just save this real quick。

![](img/00eb09c89e9cead813efa69c14465817_2.png)

![](img/00eb09c89e9cead813efa69c14465817_3.png)

So what's neat about the coral one is that。

![](img/00eb09c89e9cead813efa69c14465817_5.png)

It is in a way one of the most straightforward workflows that right because again。

 you can you can just export this and it'll give you the TFL file and you can and you can download it。

 So what I'm going to do is I'm going to shift gears here and just show you that workflow from the the coral products flow So what I can do is。



![](img/00eb09c89e9cead813efa69c14465817_7.png)

Just go to the documentation here and just set up。The accelerator。 So again。

 you can see super small device here is's going to require if I， if you're using O 10。

 you would need to use either Mac ports or homebw。 I think homebw is a little bit better。

 and you need to install the the runtime。 So， so what I can do， I think I can just put this in one。

Window， and then share my screen so that。We we could have the the web stuff on one side and then like a terminal on the other。

 So I'm going I'm going to change that real quick is I will。



![](img/00eb09c89e9cead813efa69c14465817_9.png)

Go like this and just change it so that it's a little bit smaller here。Like that。

 and then Ill open up， I'll stop and reshare again。

And put a terminal right next to it so that we can see both at the same time。Here。

 which I think will， will be a good way to do this。So。I'm going to。Stop my sharear。And reshare。

Hlow the OS 10 instructions。 So I would do this first， I would I would run。This。

 I would go to a different directory， for example。Like my source directory。

And then I would run this curl command， and this would just download the package that has the runtime in it。

And then I would unzip it。So， edge。TPU run time。Q2。The zip。Let's see that。There you go。

 unzip that and we'll say replace it。Okay。Okay， so I got this thing replaced and then the next thing that I'll do。

Is that I will see the into that directory。T you on time。 and then I will run this bash install。

 So'll say pseudo bash install。Dot S， H。 Here we go。 So it goes through， Ask me for pseudo password。

And it says a few things， it says when you first install this， it's going to tell you。

 do you want it？to get really hot because if it runs at full capacity。

 then it'll be a little bit hotter and so I sure why not， we're playing around。

 let's do a maximum frequency and so I'll go ahead and do that。And this is typically not too bad。

 and it goes through and installs the libraries that I need。 And so while that's working。

 I'll go to the next step here。Which is。It's going to say now connect the USB to your computer。

Using the provided cable， so in this case， I've already done that so I can just leave it installed there。

And then I'm going to go to this next step， which is install the Tensorflow light library。

And this is a little bit tricky because。Anytime you install Python。

You can get yourself under trouble。On a machine like your laptop。

 And so what I would recommend is anytime you're installing libraries is you create a virtual environment first。

 And so let me just actually also make this a little bit。More like this。 Okay， so next up。

 what I will do is I will create a virtual environment。 And for here， it's fine。

 I'll just put it in some somewhere around here。 So I'll say Python 3。Tilda slash dots。

Or I say dash M for virtual environments。And then call this TPU。September or something like that。

There we go。And that creates this。Virtual environment。And then maybe make this a little bit。Bigger。

That looks pretty good。And then the next thing that I will do。Here is that I will。See here I will。

 I will go through and say Pip install to to Pip install the right thing。

 And I'll first all'll source it and then do a Pip install， so。I'll say source tilde slash dot。嗯。TPU。

In activate。There we go。 And then I will。Inside of this directory， I'll do these two things。

 so I'll make a directory called coral and Cd into it。S go ahead anddo that。And then， I will。

Get this TF light directory， which will contain the models and also will contain some examples as well。

 right， So this this basically will give me the the model file。

 the TFL model file plus it'll give me some classification examples。

 but but this could be very similar to what would be downloaded from Google Automail。

 So go through here and I clone it。Okay， great。 and now I would just see the into this directory。

 which would be the Python examples here。So let's say CD。我皮。Here。😔，Once I have Cdn into here。

 I can run their install script。And。That looks pretty good。Okay。

 and what's great about this next is that I can run the image classifier with a bird photo。

And so what will happen？Is that it will run this command line tool called Classify image and maybe we can just look at this real quick。

 in fact， as if we say vim classify image， we can take a look at what the script is that's always a good idea before you run some code is just see what it's doing so it's got some documentation that says how to use it。

And what it does is that it。Has some labels inside of here that it loads， it finds the interpreter。

 which would be the TF light interpreter， which will allow it to talk to the physical hardware itself and really that's it then this part of the code is just a argument parser that accepts different things。

And then from here， we would get the prediction result。

 and you can see that it puts some print statements in here。

 so you could change this and make it do whatever you want， right。

 This is just like an example piece of code that they have。 and so we'll quit that。

And then I'll run this example， so let's go ahead and just copy this。

And what this should do is it should。Pop open a parrot and predict it if we have the TF light runtime now。

What I don't know is did we not install the runtime， I think I didn't install it。Okay。

So I need to go to here where we skippped a step， Okay， so I'm going to go to the runtime。

And I'm going to say。That。I didn't click on this link， which is TF install the runtime for Python。

 so I need to select the right environment and in this case。It's going to be OS 10。Actually。

 here we goes。 says run an inference using TF light at runtime。

 So I'm going to need to select this particular binary。 And what I would do is I would say。

Pip install。呃。And then。Because it's in a virtual environment。

 it'll put it in this virtual environment。And then will we would just need to download this binary right here。

And install it。 so we'll go here。 that looks good。And。We've installed it， that looks successful。

 so in theory。That's all I needed to do to go back to this other step， which I think was right。

It's one of these。Which well， I'll scroll down here。 I think it's， yeah， right here。 So。

 so this is the step。 let's go ahead and run this again now。 And this this in theory。Should work。

Let's see。There we go， so was it was able to。To detect that that was a parrot and give me。

And told me exactly what kind of parrot it was。 It was a scarlet Macaw parrot。

 and it said it was 77% Sure。 So， so we can let's look into this a little bit more， though。

 and see what it's doing。 So one thing it's doing。Is in the models directory。

 notice it says there's the labels， so we should be able to see all the things that it's got inside of here。

 So if I go。Into the models。Diirectctory here。 we can look into a little bit more detail。

That you notice that it has a， I think the model we're using is E TPU。

And then it also has this inat bird labels。 So if we do this。



![](img/00eb09c89e9cead813efa69c14465817_11.png)

We can see that these are all the different birds that it knows how to detect， right。

 which that's a lot of birds I don't even know what most of these birds are， but what we could do。

Is actually look into this a little bit more and maybe find one of these birds on the Internet and test it out a little bit more to just get a better feel for how this system works so。

I don't know how about。Cliff swallow， let's try that。

And so I'm going to go here and I'm going to see if I can find。A picture， American cliff swallow。

And Wikipedia has a picture here， I guess in theory， I could even call。

Programmatically called a Wikipedia and grab this。 But， but let's。

 let's go go ahead and download this。

![](img/00eb09c89e9cead813efa69c14465817_13.png)

Image。And I will say save image as。And I'll put this onto my desktop。



![](img/00eb09c89e9cead813efa69c14465817_15.png)

And then what I can do is I can。Potentially go up here。And I think there's a， yeah， it says images。

 I can maybe move it into that image directory， so I'll just say。Mvy tilde。Desktop。And then。

 something。This thing。Sure， I'll move this into images here。And then。

 but let's call it something a little less。Big， so I'll just call it the first part of it。

And then dod JPG like that。And did that work。 Okay， that looked like it work。

 And so now I can try to predict a different， a different bird。 And so let's see here all any need。

 All I would need to do is just go to。This last section here。Which would be this。

And then passing in the name of this thing， which would be a PE， there you go。

 and let's see if that works。And。It goes through， it tries this prediction。

 and it was able to detect or predict。That it was 82% probability that it's a cliff swallow。

 So pretty powerful， actually， that again， my， my laptop couldn't do this。 This。

 this is a very powerful chip that's doing all this work。 Now， what， what also is cool about this。😊。

Is that in theory？We could just grab the model from Coml。

 I'm sorry from Google Autol right and train a model， download it。

 put it on here and do the exact same thing。Or we also could download one from the TF light hub as well。

 and so to do that， we could actually go to this。And。

See if we can find one from TF light here that we could use。呃。Let's see what this is。

 This is a collection of ML light compatible ML kit compatible TF light。Models， so this one。

Let's see。 What is it contained。There's a bunch of models here。

 I think we can just download one of these。And， and。And see， see what we can find。So， maybe。呃。

Let's let's see if we can find oneness。 maybe plants。 that looks like a good one。

 So if I click on this。And I want to download it。 I should be able to just。And。

An updated version here。Okay， maybe make this a little bit bigger， so I know what's going on here。



![](img/00eb09c89e9cead813efa69c14465817_17.png)

I should be able to go to this project。And download it， where do I download this thing？😔，Tif。

Download mobile Plan classification model。 Okay， let's download this。



![](img/00eb09c89e9cead813efa69c14465817_19.png)

All right， we'll put this onto my desktop。

![](img/00eb09c89e9cead813efa69c14465817_21.png)

And let's on， on。Compress this thing。And then again， in theory。That I could。

Let's just look inside of here。Let's see what happens if I just move。That from my desktop。 And。

 and I think it was called。Let me just grab this thing。 Here we go。 It's got。

I can just put this in this window。Move this。To here。And then if I look inside of this。

 we can just see what's inside of there。 So what is in here， we've got。A。T F hub module。

We've got some assets。Some variables。 So this one might be in a slightly different format。That I'm。

 that I'm。That I'm， oh， you know what it is。 I downloaded the wrong version because I think that's the。

 the proto buff format。 And so I would need to download。



![](img/00eb09c89e9cead813efa69c14465817_23.png)

The the TF light format。 so maybe I need to get less complicated here and I need to do a filter for TF light。

Or even， I think you even since say quaal。 Here we go。 This is， this is the one that we're using。

And let's just take。Just to make it simple。I'm going to go to Coral。

And I'm just going to try to get any of these to work。If I can't get this figured out in a second。

Then I'll just move to the next section， but I think this looks good。s let's see。 So coral edge TPU。

 this looks good。

![](img/00eb09c89e9cead813efa69c14465817_25.png)

Let's download it。Again， I will uncompress it。

![](img/00eb09c89e9cead813efa69c14465817_27.png)

Okay， so this looks like it's just got a， oh， and then here's a labels file。Let's download that。Okay。

 this looks good。Let's。Imagenet labels， let's just do this。So。Let's just copy this。



![](img/00eb09c89e9cead813efa69c14465817_29.png)

We'll call this image。 So So yeah， I think I can do this now。 I think I know what's going on。

 So I'm gonna， I'm gonna just remove that other model。



![](img/00eb09c89e9cead813efa69c14465817_31.png)

Here。And then I'm going to create a new inside of the models directory。

I'm going to create a new labels file。 So I'll say touch。

 and I and I'll do it the same name that they have， which is called this， which is。Image， image net。



![](img/00eb09c89e9cead813efa69c14465817_33.png)

Labels。t TxD。Okay， then I'll open that up and put these labels inside。

 so this will give me the ability to do predictions based on this model that I download here。Okay。

 so let's do this。 We'll say set paste， and I will copy this。And。There we go。 That looks pretty good。

So it looks like it， it's able to detect a bunch of different things。

 like just kind of a bunch of images。 Okay，100 images。 I will save this。 That looks good。

 And then the only other thing I will need is。

![](img/00eb09c89e9cead813efa69c14465817_35.png)

That model， where， wherever it put it。Which I think I already downloaded。



![](img/00eb09c89e9cead813efa69c14465817_37.png)

Which in theory， is on my desktop somewhere called。Called T F light。 Oh， I think I see it。Yeah。

 so I'm just going to Cp this model。Into here like that。

 And I'm going to just copy it to the directory。 So I got label， got model。And so， again， in theory。

 I should be able to do that same command line tool that I ran earlier。

 So I I can even look at history and do like。This command here， like this。So I could。

 I could even do。Exclamation point。This is one way in history， you can actually run an older command。

In fact， let me just do this， I'll put this higher up。I'll go like this。

So this is the way in history you can run any command。That you ever run again。

 you can you can just call back， call back， which is pretty helpful。 if it's a big command like this。

 and I'm just going to swap out。The label for the， the other label， right。

 So I think we called this thing。

![](img/00eb09c89e9cead813efa69c14465817_39.png)

嗯。What did we call this？

![](img/00eb09c89e9cead813efa69c14465817_41.png)

Imagenet labels dot TXD， so。Image there we go。 that that auto completele。 That looks pretty good。

And then， this one。We haven't downloaded that yet， so we also need to change this to the mobile net model。

 so I need to swap that one out。 so I have to change three things here。So we， we need to。Copy this。

This model。We'll go here。And。Swap this one out， which would be the 1 I downloaded from TFhub。Okay。

That looks good。And so the one thing we're missing。

 I don't know if it'll know how to detect this bird because it looks like it knows how to detect。



![](img/00eb09c89e9cead813efa69c14465817_43.png)

Like a tiger shark and all this。 So let's， I like tiger sharks。 Let's， let's get a tiger shark here。

 So I'm gonna I'm going move this over。

![](img/00eb09c89e9cead813efa69c14465817_45.png)

And I'm going to find a tiger shark。So I'm going to go here。Find a tiger shark。 and then。



![](img/00eb09c89e9cead813efa69c14465817_47.png)

Here we go， this looks pretty good。 this looks pretty big as well。 I don't know what that is。

 but that looks interesting。

![](img/00eb09c89e9cead813efa69c14465817_49.png)

And I'm going to download it to my desktop。

![](img/00eb09c89e9cead813efa69c14465817_51.png)

And then。I'm going to move it into this location， into the images directory。

 so I'll just open up another tab here。And just and in fact， say PwD。



![](img/00eb09c89e9cead813efa69c14465817_53.png)

And I can say M V。Tilda slash desktop。Tiger shark。Two images like that。There we go。

And then from here， I can actually just swap out。The thing that I'm gonna do the prediction on。

 which is this。Perfect。Here we go， Tiger shark。All right。

 so I'm going to go through and run this and let's see if it works。So pretty cool。

 99% prediction accuracy。What's awesome about what we just went through is that what this means is that。

Now that I've got this physical device， not only can I download things from the Autom model that I train myself。

 but I can get any model anybody created。AndAs long as I have the labels。

And I also have the TF light image。Or TF light file from TF hubub。 I can I can do anything I want。

 right， So so this is this is a pretty pretty powerful workflow that we were able to。

 to work through here with with again， with T TF hubub here。

 so I could I could go to any of these models as long as they're in this particular。😊。



![](img/00eb09c89e9cead813efa69c14465817_55.png)

Format。Let's go back here， TensorFlow。As long as I say。I think coral。

 I think it'll work either way because this will accept TF light。

 but just specifically because we know we have a coral device， I just select coral。And。

I can go through here and down look， it looks like there's only two right now， but。

It appears that this is probably going to be something that's going to be filling up quite a bit with people creating these models and hosting them and it's a great way to really leverage the power of really open source。



![](img/00eb09c89e9cead813efa69c14465817_57.png)

![](img/00eb09c89e9cead813efa69c14465817_58.png)