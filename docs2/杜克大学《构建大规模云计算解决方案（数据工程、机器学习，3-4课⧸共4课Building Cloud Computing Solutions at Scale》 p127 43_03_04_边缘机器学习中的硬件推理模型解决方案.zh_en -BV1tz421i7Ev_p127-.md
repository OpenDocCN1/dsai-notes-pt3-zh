# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p127 43_03_04_边缘机器学习中的硬件推理模型解决方案.zh_en -BV1tz421i7Ev_p127-

![](img/8802ff0cab42689fd168e625e4e6fb94_0.png)

So in terms of the industry here。Every player， really。

 every major tech company has some kind of inference solution， a prediction， hardware solution。

 So AWS has a bunch of chips here， Google has a bunch of chips here and we're going to get into those Also Apple has a bunch of stuff。

 We just talked about it and then Intel。 So let's talk about just a couple here。

 aren't these aren't all of them。 but in particular the Intel Movidius。Here's an example of it。

 what's nice about this style of。Of chip is that it's USB based so you can just take it。

 plug it into your machine and then now you have a very powerful prediction chip that is just available via USB so I think this is really the style that you're going to see a lot of computer vendors do and this is just emerging we're going to see an explosion of these kinds of chips。

And in particular。What is it well it's a tiny fanless deep learning device for doing AI programming at the edge and you can see here that you download a model。

 you go to that model， you。Go through and do some development with it。

 you know figure out what it is you want to predict and then finally when you're done you put it wherever you want to put it and it could be on a raspberry pie。

 it could be on a physical laptop， it could be on some other you know a drone， it could be wherever。

And the way I've typically done this， if you do want to use the Intel Movidus chip would be to use abuuntu virtual machine and why I like thebuuntu virtual machine is that it isolates your development environment to this physical virtual machine where even if you're on like I have an abuuntu laptop but I still would put it into abuuntu virtual machine so that I have total control over the development environment and I can have different。



![](img/8802ff0cab42689fd168e625e4e6fb94_2.png)

![](img/8802ff0cab42689fd168e625e4e6fb94_3.png)

![](img/8802ff0cab42689fd168e625e4e6fb94_4.png)

Virtual machines that are isolated to different hardware that way I can isolate exactly what's happening。

 make a copy of it once I've got a set up。And I think that is an important thing to think about when you're doing hardware development。

 which this is it's good to have a clean environment that you can recreate。

 And I think a virtual machine is a great way to do it。 So once you get a virtual machine set up。

 you would go through and download the SDK。 And then from here， we。

 we can just look at some of the different。😊，Information about this particular kit。



![](img/8802ff0cab42689fd168e625e4e6fb94_6.png)

Let's see here。I don't know why that's。Blow blowlowing up on me， but maybe that one's down。

 let's look at this one。

![](img/8802ff0cab42689fd168e625e4e6fb94_8.png)

So。This compute stick here， one of the things that's interesting about it。

Is that you can look through their examples and their examples are available here in apps。

And you can see that。There's multi stick examples。 There's also individual examples as well like these little Python scripts here。

 and， and there's not a necessarily even a ton of code to get started。 but this is a good。

kindd of like a hello world to get started with it is run a few lines of code。

 make sure that you can get it to work so that's what I typically do is is I' download the code and's here's one more example repo that's probably better repo I'll go through here find one of these example projects here I think this one has a little more stuff in there。

And then I'll get the Hello world working first and the way you do this is you say make run。

And then if it's not plugged in， it'll tell you that the device isn't connected and this is a lot of times easy to get caught up on is when you get physical hardware is you don't do it just a hello world like does anything work and you could get way down into writing code and then you think that it's your code which your code could be perfect。

 but it's not your code it's actually the fact that you don't have the device connected properly for some reason。

 like the driver is not detected or the library or whatever So I think this is a very。

 very good idea to first make sure that you can connect to it right so you have a hello world。

Once you do that， then then I would move on to the next step， which again， if we go back to here。

 there's a bunch of examples of projects that you can get started with。

 And this is a good way to get a feel for what you can do with this device and I think this one's a benchmark here。

 which which is pretty neat。 So this one shows how to determine the frames per second or inference per second。

 you're achieving with your current configuration which which is pretty cool。

 So you can go through here and see like if you are going to do a realtime computer vision application。

 here's how to actually run this project and benchmark。

 which could be very helpful if if you were going to build a， let's say。

 a license plate detector or like a trash sorting。😊，Program something like that。

Then a few other ones that I've seen that are pretty neat are。For example， the。Driving， let's see。

 real time。I think there was a real time object。Here somewhere， let's see。Was it。

 was it this one driving。Autonomous Lego driving。 That's pretty cool。 But there。

 there was one that it was。Maybe it was the。Object detection leave that's the one it was。No。

 I I guess I don't know where it is in here， but basically there's a bunch of examples here and gender age is another one that's pretty neat where you can on one chip it can simultaneously do two different types of predictions because of how powerful it is and so this can detect the age in the gender at the same time and it comes with a pre-trained model and this model is from something called model zoo right here。

And so you can see this is the model zoo。

![](img/8802ff0cab42689fd168e625e4e6fb94_10.png)

嗯。In。Here's one I ran a while back using the model zoo is I just took this onto my abuuntu virtual machine。

 put the pretrain model said make run， and then it captured my camera and then I get a pretrain model and I can get access to it。

And what's neat about this is that you can actually。

 it's just Python code so you can wrap that Python code and you could as it's collecting， let's say。

 the labels。You could put the label somewhere else。 You could put them into a text file。

 You could send them to an API somewhere。 You can do whatever you want。

 You could build a gooI on top of it。 You could send it to another device。

 know it's up to you as a programmer to decide what it is that you want to do Now a couple of things I'm going to mention about this。

 just briefly is that additional to this there's another tool called Onyx。

 which stands for the open standard for machine learning Interoperability。

 And so this is another really interesting thing to be aware of is that。



![](img/8802ff0cab42689fd168e625e4e6fb94_12.png)

You can actually use this open format to convert models from one version to another。

 and I was just looking at this earlier today。

![](img/8802ff0cab42689fd168e625e4e6fb94_14.png)

![](img/8802ff0cab42689fd168e625e4e6fb94_15.png)

And if we say Azure onyx。Cormel， this would be a good example， I think it's。



![](img/8802ff0cab42689fd168e625e4e6fb94_17.png)

This one。Is the one I was looking at earlier。Is that。Let's see here deployage。嗯。There was get this。

 get this。 How to you use this is the one。 Okay， so what this does， for example。

Is it shows you a bunch of different examples of how to use onyx。

 And I think the one that I was looking at。Was。This one。Aelti， let's see here。 This was。

Let me look at this if this is the1 I was looking at earlier。Yeah， this is the one。 So。

 so let me actually even put this into a into a maybe I'll just put this into this notebook and save it。

 I'll just put a section here that says。嗯。Onyx。And this is really a pretty。

 pretty interesting new tool here。And we'll go here and just say example。Just do this， A example of。

Cornel conversion。Vers， I think that's how I do。Right， does that work？Oh， I'm missing。 there we go。

And so I think that this should work。Where is it。Why， why am I screwing this up。

Where is it the other way around this？One of these will work where you where you give it the link。

There you go。And then I'll just check this in。Sa a copy and Gitthub so。

Why is this so cool and why why am I showing this， Well。

 the main thing that's interesting about this is that you can take a model that anybody gave you and you can convert it。

Into some other format。 And in particular， this one is a great example of that。 So they say。

 you know this kind of walks you through said okay， what is Yolo。

 it's a realtime object detection using Onyx on Azurel。 you don't have to use Azure Mel， but you can。

 And then what is it， It's an open format for representing machine learning models and what's great about it is it works with a community of partners like Microsoft to Amazon and you could explore more there。

 And then Yolo is you only look once realtime object detection。

 So we've already got a model somewhere。 And if I want to go through and run this。

 what I can do is I can say。😊，Check the SDK version。

And then the first thing I do is I download a model someone else created earlier using a different framework。

 and in this case this framework is called QML， which we'll get into in a second。

And then once I download that model， what I can do is I can use OnX tools and also import Corml tools。

 load it into this example convert it into the Onx format。

 puts some additional information in here that the model needs save it out then it's ready to go now it's in OnX format。

 So what could you do with this， well because it's a cross you know platform model format you can put it anywhere that accepts OnyX and so one of the places if I wanted to so let's say that I originally even this was running on an iOS device right I could take that same model or even if I used and we'll get into this。

If I used Apple's training system to develop something。

 I could train it using their autoM system and then dump it to this format and convert it。

You also could then deploy it as a web service as well， so I go through here。

 I set up some cloud stuff in this case， loaded Azure ML workspace。Register the model。

 And then now I go through， and I can， can do a prediction。

 So here's an inference that you do against it。 So， in fact。

 I can even show you the first part of this in action。 So let's go to Azure real quick。

And I'm going to go to their system。Here。And I'm going to。Go to their system called。

What is it called again， it's called a machine learning studio。And in machine learning studio。

 I will go to launch the studio。And then go to a compute node and just run this in their cloud。

 So I'll click on Jupyter。

![](img/8802ff0cab42689fd168e625e4e6fb94_19.png)

And I think I even have this code， here we go， yeah， Onyx conversion， I was just working on the city。



![](img/8802ff0cab42689fd168e625e4e6fb94_21.png)

And in particular， what's awesome about this is that it's pretty straightforward is run this first shell。

And the first shell just downloads this model， which is the corem model。

 The second thing that I would do is optionally install these tools。

These are already preinstalled in Azure but if you needed to do this on your local laptop you'd have to install these and then from here I run this next part which takes the model I downloaded and put it into this utility Corel tools so we'll run that let's see if this works。

Great， it looks like that worked。And then what I'm going to do is I'm going to convert it from。

The Ql format to the Onyx format。 and it's literally a line of code and I just say onyx tools convert。

 and then I go here and I do this。Great， and then I save it out。So I just say。Save it out。

 and then I can double check that it's literally on my machine here， right？And I could。

 I can do this。 If I want to be less geeky， I can just do this。 I can say。DF or I'm sorry。

 LS dash L H。 And then just do this， which will show me it in human readable form。

And verified that I was able to save that out。There we go，61 mega。 So little bit beefy。

 It's a little bit of a big model here。 But， but this is really powerful because what this means is that you can take models from anywhere and kind of go back and forth and put them wherever。

 wherever you want。 So I do think this is the future of what's going to be happening in machine learning in edge based computer vision。

 So so that's onyx。😊，In a nutshell。Now， if I go back to this。

 the other thing I want to talk about was Qmel。Which what's interesting about Cormel again is that。

Apple， because they own the whole ecosystem， there's a very good story for doing machine learning on on their device。

 and they accept a Ml model using Cormel。 They have a framework called Cormel that can interpret that model and it is easy to integrated into your app。

 So this actually， this workflow could be very good for。Doing things from， let's say， Google Autom。

 we also know that other computer vision Autom systems would work very well with this as well。

 but if you do the Google flow，And you train your model。

 One of the ways you can export it is through ML model。

 And then that would get put onto your machine。 So what are some of the key concepts that it' optimized for on device performance。

 so it's really designed to run on the ios device。 There's also low memory as well。

 And you can convert these just like we could with Onyx where we took a coreml model and put it to the Onyx format。

 you also can take some other model and you can convert it to Corml。 And so how would you do that。

 Well， one of the ways you would do this is you would say Pip installstall coreml tools。

 which I think we did over here。Which was， yeah， Corml tools right here。

 so you can go the other direction as well。Then you can say convert model like this。

 save the model to QML format， and then now you've converted it from， let's say cafe。

 like we know that the zoo right the zoo has all these models here that it makes that are in the cafe format why I could take that model from cafe format and then convert it into ML model。

 which again I guess I could take from ML model and I could convert it into Onyx。



![](img/8802ff0cab42689fd168e625e4e6fb94_23.png)

And so here's a bunch of examples of how to do that。

 Like if I just wanted to play around with this in here， you know， Piip and install Corel tools。



![](img/8802ff0cab42689fd168e625e4e6fb94_25.png)

Go through here。And。Import Corml tools and then and then I could I could basically play play around with the object so I could I could。

Do this， like make an instance of it。 And if you did a question mark， it will show you the help menu。

 And I think the help menu will show us that。This。Well accept a bunch of different。

 this is the documentation on it。 It'll show you all the different formats and how and even examples of different libraries and all kinds of stuff just by doing this help menu thing here。

 which is this question mark right so you can get the help on it or you could also do this。

 you could do dot。And then tab。 So convert dot。And it'll show you the different formats that you can convert with。

So anyway that's how I would convert now how do I use this inside of a machine learning application well this demo project here is one of the best ways to get started。

 which is the classifying images with with vision and Cormll so you don't have to do anything it already comes with the a model that can do1000 classification categories and。

Over here， you would just download this， set up a core vision vision model and then load it up into your project and。

 and， and run it now the。That's that's if you wanted to pretrain a model， the second option here。

Would be， which I think is also very interesting。 And this is a fairly new one。

 And I'll just put this as a link in here as well。 So let's just maybe say option。Qiuhi。😔。

We'll just do a。我 say。Create him。And this would be like， you can also build。

Automal solutions that work the same way。 So you don't have to necessarily。Do things。By。

By downloading the model， you also could just train it yourself by going through organizing some images。

 putting them into a classifier， training the classifier， and then building it into an application。

 And so really again， the core idea with Autom and we've got Google's got it， Amazon's got it。AWS。

 Google's got one。Amazon has these and Azure has this and Apple has this that that you can train these things by really just clicking buttons。

 And then once it's trained， you would create an email model format like we just discussed。

 and then you can build an ios app around it。 So what is interesting is that you could actually build this here。

And then put it into the cloud if you wanted to。 so the device isn't necessarily the only place that this model could actually live。

m，So that's that's really the。TheThe gist of this and if you look inside of this particular project。

 you'll see that the coreel model lives inside of here。 And so you'd say mobilenet。

 email model and then compile it and then you'll get a prediction like this。 And again。

 so you have a couple different options here， you could just download the model from this location or train it yourself if you want to stick in the Apple ecosystem。

 Now there's another thing that I'll mention here as well， which I'll just minimize this real quick。

So let's minimize this， let's minimize this is that there's also the TF hub。

Which we'll get into in a second。T F hub。And inside of here。What's cool about it if we go to。T F hub。

Is that the TF hub。Is。A way of looking through models that have been created by other people。

 and again， if I wanted to go through here and do image detection or image classification or whatever。

 I could just download this and put this onto a device because it would come in this TF light format and what's neat about this is with TF light。

Is that I could potentially build a bunch of different， you know， we could say。You，Con to Cormel。

I'll put a link to it here。Maybe also you could do。Comes in this format。

And what you could also do again， convert to and put a link here。So， here's this。

So you can convert to the Corel format。I don't know why I'm， I'm having problems with this。

There you go。YouConverse in the Corl format， it also could do the other way could you you could convert to Onyx。

You could also deploy。Directly。To the。The coral hardware as well， coral hardware。RightSo this is。

 this is kind of an interesting toolkit that when you're building solutions， you don't necessarily。

As well， even needs to train your own model， you could use something like TF hubub， download it。

 put it onto device， then run it， and that might be good enough。 that might be good enough for you。

 So you almost treat it like it's an open source library。

 but in this case it would be open source machine learning model。



![](img/8802ff0cab42689fd168e625e4e6fb94_27.png)

![](img/8802ff0cab42689fd168e625e4e6fb94_28.png)