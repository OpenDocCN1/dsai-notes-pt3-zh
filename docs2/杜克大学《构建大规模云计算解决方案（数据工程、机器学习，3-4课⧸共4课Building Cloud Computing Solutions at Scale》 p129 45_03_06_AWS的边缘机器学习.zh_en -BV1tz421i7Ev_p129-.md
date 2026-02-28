# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p129 45_03_06_AWS的边缘机器学习.zh_en -BV1tz421i7Ev_p129-

![](img/08d701bccf218cef560f4ce80568b404_0.png)

So the next thing that we'll talk about is we'll get into using。The AWS ecosystem a bit here。

 so what we can do next here。Is。Go。To let me actually just。Reshare my browser。

Which I think will be a little easier to work with because there's too much stuff going on。Here。

 so I'm going to go here。And I'm going to share my browser， only。Okay， so so AWS has。There。

Their system called DeepLs。 So I'm going to go to the AWS console here and I'm going to log in。

And use the blends。And we can just go to。Off here。And I'm gonna put in。

And what's neat about this is that。We're able to， to really kind of tie into。A lot of the power。

That comes with the AWS cloud by using deep lenss。 and let me just go through here and get into deep lens here。

A bit。So the way Deep lens works is that you have this deep learning enabled video camera。

 which again is this this camera right here， this camera and you have to plug it in。

 so we'll go ahead and plug this thing in。And then I'll turn on the power。And if you purchase it。

 you can order one here。Then you can register it as a device。

 So that's that's first step is go through and you register it。 Now， there's， as of this。



![](img/08d701bccf218cef560f4ce80568b404_2.png)

Today， we've got hardware version 1。1， a hardware1， I actually have this one。

Which apparently has been less troublesome than the version of 1。1 has got a little bit more。

Problems， but but I'm assuming they're going to continue making these things。

 So there may be ones after this。 but the first thing typically you would do would be to create a new project。

 so we can maybe make this a little bit smaller here。And in order to create a new project。

 they give you these project templates。And the project templates can it's similar in a way to the TF light ecosystem is that you can do object detection。

 you can do。Artistic style transfer。You can do face detection， you can do hot dog recognition。

 cat and dog action， all kinds of devices， but they're specifically designed to work with this physical piece of hardware。

 probably the more interesting one to play around with first。Would be this object detection template。

Now， you also though， could create a new blank project if you have the raw ingredients。

 but first let's just go through and do this one， so I' say next。

And you can see the overview of the architecture is that you have the camera。

 the camera will look at a video stream and it'll actually split the stream into two pieces。

 you'll have the really like a monitor stream， which you actually can plug a HTML。

 I'm sorry an HTMLI cable into it which actually you know what， I probably should do that very soon。

 which is pretty cool， where you can actually just look at it from an HTMLI cable。

Or you can do this in the browser， which is what we'll do today。 And then also you can。

Call out to a lambda inference function。 and that Lambda inference function will go through and。A。

Do the predictions and then。Annotate the stream， right。

 So so that's really the the gist of things is you have a raw stream。

 You have something that goes through dust predictions by pulling in a model and doing the the predictions。

 And then it annotates that stream。 So for this particular project。

 we'll just call this object detection。 Maybe we'll just say， you know， September。Object detection。

You know， what does this do like detects 20 objects。 So let's go ahead and say create。

And now that I've got this project， I would want to deploy it to device。 So first。

 I would need to look at what is on that device now， and I think I can go here。And take a look at it。

And say， remove this project。And I don't know。 it does say it's offline， which。I don't know。

If I have to reboot this thing or not。But， but if I go back here， let's see if we can。

See we can see if it wakes up。Devices。Yeah， might， I might have to。I might have to reboot this thing。

Yes， should。Yes should it should wake up。They're they're a little bit finicky。

 That's the one problem with with this。Particular device， I think I can actually。

This is a  one I could actually de register because it's an older one。But， but this one， oh， good。

 It's registered。 Okay， there we go。 it woke up。 looks like it's on。 So So what I can do here。

As I can say， deploy a project and select the project that I just registered and say deploy a device。

Select the target。And then go through and do a review。So once I do a deployment here。It takes。

 let's say， 20 seconds， maybe and most to do this。But this will now deploy。

The information that will hook it all up into this ecosystem that will allow me to not only just do some of the stuff that we've been doing earlier。

 which is do predictions on a piece of hardware， but it interacts with the cloud。

 so I think this is really interesting in that this deep lens device allows us to do a lot of things that would typically be very complicated to do without this cloud integration。

And a couple things to point out as well as that。There there are two ways to really monitor two main ways。

 there's a couple other ways as well， but to look at what's happening。

 one is that we can literally look at the video output and actually look at it detecting in real time in my office and seeing what's happening。

 but we also can look at the MQTT。Protocol messages。

And actually look at the Io console and actually see what's happening so I can see the payloads being sent in real time。

 And so we can see here it's still still working。 But if I go to copy this and I copy this。

 I can open up another window。And go to the I O T console。And in this M Q T T client。

 I can subscribe to a specific topic。 So I'll go here and I'll say subscribe to this topic。And。

From here， what will happen is once it starts recognizing the things that are in my office。

 I will actually get those the messages will will actually pop up right here。

 So let's let's kind of wait for this thing。 Okay， look， it looks like it's succeeding。

 And so in theory， this thing。Should。B。There we go。 Look， notice how it's seen things now， right。

 They're popping up。So why what is it seen， well， this is pretty cool because I could write Python code right that talks to this and accepts it and does some other thing with it。

 but we also can look at it in real time。And if I go to this console here。

I can actually look at the project output。And view video output here。Which will go to。

Select my browser。Chrome。And then say view the stream So so again there was two ways to connect this I could put an HDMI cable and I actually have a couple monitors in my room so I could just put one somewhere look at it or was great because I can show this is I can just view the stream here。



![](img/08d701bccf218cef560f4ce80568b404_4.png)

And then go to advanced and then proceed。And from here。I can go through and I would have to type in。

My。My password to accept this。

![](img/08d701bccf218cef560f4ce80568b404_6.png)

And then what happens is it shows me the project stream so this is again， my office。

 look it sees the sofa， it sees a potted plant， it sees a person and in real time it's detecting all of these labels and then these labels are also getting sent into the IoT system right so pretty cool that it's able to maybe even take a little screenshot。

hich is pretty neat here。And I can put that into our notebook， but in a nutshell。

 this is pretty awesome because not only do I get access to it there。

 but I also can get access to it from this， right？

![](img/08d701bccf218cef560f4ce80568b404_8.png)

Maybe even take a little screenshot here。 So so so what I typically do if I want to put these into a notebook。

 this is just a neat little trick is I do an issue。And then I'll just say images， for example。

 more images。And then I'll take screenshots and I just throw them into。Into like this here。

And then here， and then I can just throw these， I can make these like a ticket。

 and then I can go back to my notebook and say， like， for example。

I want to make some more stuff here。AWS deep lens。Examples like this。I can。

Do this and paste those in and look now they show up。Which is pretty cool。

And then I can just save it。Like like this。 And then check it， check it into Github。

 So that's just a neat little trick if you want to share things with with other people。 All right。

 so， so now that I've got that that working， the only thing that maybe you know you can shell into it if you want。

 you can do all things with it。 but but the main thing to be aware of is that it has a function that's a Lambda function。



![](img/08d701bccf218cef560f4ce80568b404_10.png)

![](img/08d701bccf218cef560f4ce80568b404_11.png)

That you could later， if you wanted to go into AWS Lambda。And actually。

Literally modify the code yourself so you could go through here and change anything you wanted。

 like notice that it's got the same thing it's got the labels associated here and it's looking to see if it matches any of those labels and then both sending the data to IoT but also annotating the image itself so that。

You're able to see what it is。And then the other thing that it does that's in this project content is also the model itself and the model lives。

 it literally tells you where it lives， the artifact path is it stored in S3 so it literally sucks this out of S3 so if you wanted to train this yourself。

 you could train your own model and in fact with some of the tricks that we've done today。

 maybe you could even use a model from another library。



![](img/08d701bccf218cef560f4ce80568b404_13.png)

![](img/08d701bccf218cef560f4ce80568b404_14.png)

Or framework， use onx converted or use M X Nd convert or whatever。 And then go through in。

Tweak this particular function here and make make it do the prediction。

 But so maybe the last thing that I'll do is。I'm going to go back to the projects and I'm going to create one more project。

 and I'll do a different one。 This one will be artistic style transfer。

And if I this is an interesting one because style transfer， what it does is it actually in real time。

It changes the video image to be a different image。

 So this is basically like augment augmented reality format。And so if I， if I select this。

We can go next and notice what it'll do is it'll grab the scene。

And it will it will constantly be frame by frame， actually changing the frame and making it look like a Van Gogh painting in real time。

 So， so again， this is augmented reality。 So if I go here。And I name it something。 So I'll just say。

September。Artistic style transfer。I can go here and then say。We've got that working。

 and I want to deploy it to the device。 so I would go back to my device。And grab this particular。

Project。And remove it。And then deploy a project and pick this one and then say deploy。

And then put it onto this。 Okay， so yeah， we want to replace it， sure。

So this will take just a second， and then this will be a totally different style because it won't be something where I'm going to be looking at the labels。

 it's going to just frame by frame， replace。The output and put this new output inside of here。O K。

 looks like its working deployment in progress。Here。This will take just a second。 Okay。

 it looks like it's working。 So now how do we look at this。

We can again look at the video output stream so I can go to the browser， view it。



![](img/08d701bccf218cef560f4ce80568b404_16.png)

Go through here。Put in some credentials。

![](img/08d701bccf218cef560f4ce80568b404_18.png)

Okay。And now well get a real time。Transfer， rest transfer， right， so pretty cool。 I can walk back。D。

P my hands up。Rightice。You can see that it。It it's a little bit laggy， right， but it does show。

The same thing， it does show that you're able to kind of frame by frame build out。Something。Yeah。

 I guess in a nutshell， the main takeaway here is that really there's a lot of ways to do computer vision。

including fully integrated solutions to the physical hardware， like the Coral device。

 and probably one of the best workflows would be the AutoM2 Coral or AutoML to a physical device。



![](img/08d701bccf218cef560f4ce80568b404_20.png)

![](img/08d701bccf218cef560f4ce80568b404_21.png)