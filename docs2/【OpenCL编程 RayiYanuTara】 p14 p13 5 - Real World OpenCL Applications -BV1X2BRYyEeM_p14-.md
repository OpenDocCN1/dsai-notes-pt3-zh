# 【OpenCL编程 RayiYanuTara】 p14 p13 5 - Real World OpenCL Applications -BV1X2BRYyEeM_p14-

Hi， welcome everyone to the OpenCL programminging webinar series。 My name is Joe Comm Degura。

 and today I'll be presenting about real world OpenC applications。Specifically。

 I'm going to be presenting about a multistream video processing application that I've been working on lately。

So let's jump right in。What I'm going to cover today is basically， first。

 I'll describe the application and what we're going to build。And。The different steps。

 the different parts needed。 And then I'm going to go into those different steps and how they relate to open C and。

Mostly about how open CO runtime needs to be used in these steps。

 and I'll be going through decoding a video， uploading and DMmaA， and then applying video processing。

 using events and finally displaying。The final video using Open C and Open G Interop。

I welcome you to all writing questions during the presentation and I'll be able to answer those either at the end or if it's an important question to clarify something on that。

Ging portion and I'll try to answer it then。So what is the application that we want to write。

 I was looking at。Opening up multiple video streams。

 So just to make things a little bit more complicated， not just a single stream。

 but having a possibility of。Four or six or even 12 video streams opened up and then decoding those video streams and then。

Applying video effects to each of those streams， sometimes even combining the streams。

 applying another effect to that combined stream。And eventually since we are only going to be looking at one screen at the end。

 it's going to all come down to one video stream at the very end and that final video stream I wanted to present live Now of course one could have taken out the live presentation and done something else such as writing at ID。

But for this specific application that I'm going to talk about。

 we're just going to be talking about presenting it live。Now to do this， of course。

 we're going to be using openCL， but how we access the openCL API for this demonstration。

 I wanted to use C++， so I'm going to be talking about the open CL C++。APpiI and the different calls。

 I'm not going to go into how you do it in C and how you do it in C++。

 but I'll just give a view of the C++ API calls。So what you see on the right of this slide is the main steps。

 you seedecode a video， then we're going to process the video and display the video and then you see that red line going from backup to decode and this isnt a loop that's going to repeat and repeat as long as we have video to decode and process and display。

So how often is this going to repeat， Well， it depends on the input video because。

Different videos have different frame rates。So if we're going to display， for instance。

 at 30 frames per second， then this loop is going to be called 30 times a second。 Now。

 if we just talk a little bit about performance and performance is going to be one of the main。

Fusees of this talk， if we think about this， if we get through with the decode process and display。

 then basically we're going to have extra time to wait until the next frame。

And the opposite is also true if。We have 130th of a second， and if we， if I decode。

 process and display can't happen in 130 of a second， then we're going to be displaying。

Slower than real time。 And this is what we want to avoid。

 We want to be able to fit everything into a real time presentation。 We want to present it live。

 So that's our performance requirement。U。So we're going to be keeping that in mind as we go through。

So decoding the video， it's essential， of course we have to take our video from some sort of format and we have to turn it into frames that we're going to be able to use and process。

There are a lot of different ways to decode videos。

 a lot of different types of libraries and different ways to work with those libraries exist。

 but that's not really the focus about which library to use or which library not to use。

 we just want to talk about decode and what we need out of it。So。

The main task is to decode from the video format into a single frame。

 into a single two dimensional picture。嗯。And it really doesn't matter how we go about doing that。

 but there's a few things that are important here。 So Decode was part of that main loop of processing we're going to do for each frame。

 And we want to make sure that。In that loop， we can obviously do this as fast as possible。

 just because that's going to be taking away from our performance budget。

 So we want to be able to return that as soon as possible when we call into decode。U。

How we can do that is we can have decode running separate from that main loop。嗯。

And when we call into our Decode functions， we're actually just calling into。

 please give me your last frames result， so the most current frame result。So that way。

 and this is very important when we think about performance and。With multithreading。

 this is very common， we have working threads that are doing some of the slow work and they're off on the side。

 so that way they're not interrupting the main thread and they need to be able to present their results。

Back to the main thread， when the main thread needs them。So this will be important。

 so that way really the decoding is done kind of behind the curtains and then in our main loop we just call give me the latest frame。

And then we get that frame back。And。When we do that。

 we might want to think about having a buffer of frames decoded。🤢，So that way if all of a sudden。

 you know we say give me the latest frame， it gives us the latest frame and then it goes off to do。

 find the next frame， if it all of a sudden hits a problem。

 for instance it needs to go all the way down to the hard drive to pull that information in。

That could take a long time and that could impact the performance of the next frame。

 so we just wanted to decode multiple frames ahead of time。

So that's all I really have to say about decoding and as I said there's lots of ways to do it。

 so we're just going to be talking about what we do after we get the frame decoded。Oops。

Hold on one second while the slide to refresh。Okay， so once we get that frame back， we need to。

Move that frame to the GP。 Now， of course， we don't need to。 For instance。

 you could think about having this application run solely on the CPU。 Then once you have that video。

 that frame decodta， then you can。Start working right there because it's in the main memory。

 but really what I'm talking about here in this specific application is that the video is being decoded by the CPUU and all of the image processing happening on the GPU。

 so the CPU is going to be decoding that frame into its main memory， but the GPUs has its own memory。

 so we need to move that frame from the CPU's main memory to the GP's VRAM。U。So doing this in OpenCL。

 what we do is we just call a simple API call to write into that memory for the OpenCL device。

Now there's a C way of doing it and then the C++ way， and they're very， very similar。

So the API calls look very similar， and what you see here is I've taken just one example and this is writing to an image。

And image is a memory object in open C。 So we've already。We already have these image objects。

 we've created them the image objects through OpenCL。

 and now we are writing data into that image object。And if we look at the API call， well。

 the first thing in the API call is it wants to know which image am I writing to。

 now the second thing we see there is a Boolean flag called Blocking Right。

The's blocking right argument。You're telling the API。

 do we want to wait for this right to complete before the API call returns back to the main returns back？

Or do we want it to happen asynchronously？Well， if you're just doing normal data transfers。Then。

YouIt might not make too much of a difference。But there is something that we can use special to make things go on behind the scenes。

And that's DMA。So DMA is。There's a special DMA engine on the GPU devices and what they do is they allow memory to be transferred back and forth between the system's main memory and the GPU's memory without the CPUU needing to do that copying or the GPU。

Running through a copy routine， the DMmaA engine handles that in parallel to free up the resources of the CPU and the GP。

 So this is great because when you think about performance， you think， okay。

 I have limited resources。 I have limited CPU cycles and limited GP cycles。

And the more we can offload or take away the need of CPUU cycles or GPU cycles to do an operation。

 the more performant our application is going to be。So the open CL can use。

Can use DMA to transfer buffers and images。The buffer and image creation may need to have special flags。

 And when we think about。that the data is going to be transferred asynchronously。

 then we also need to think about what does that mean for our program and how do we need to structure our program so it can use the most out of this。

So in other words， if you had a。嗯。If you are writing a buffer or an image or copying data。

And you wanted that to happen asynchronously， but the call right after that copy needed to use the data will then obviously we'll have to still wait for that copy to complete before we can go on ahead。

So we got to think about removing an immediate need of the data after a copy。

 and sometimes we'll need to think about double buffering。

 which I'm going to illustrate in the next two slides。So here's DMA restructuring Part one。

 and this is just a very simple。Restructuring what I've done is I've taken that main loop picture from the beginning and I've added kind of the small detail in between Decode and process。

 which is uploading。So once we decode， we upload the。Upload the file。

 and this might seem like a very small step， but performance wise。

 this could be a lot of the time budget we have in that one frame per second loop。

So we see in the kind of basic approach of Decode and then process that the data is needed directly after and that this will not be good for performance because that process still going to have to wait for that upload to complete。

Now if we think about how things happen， we could restructure that loop。

 as you see on the lower right。To for the next frame， we process。The frame and display it。

 and then we calldecode for the next frame。🤢，嗯。And while we have that extra time from process displaying decode。

 then the upload can happen in that extra time。 This is good， because then。

Depending on how long our process and our decode and upload is。

 then it relaxes the immediate need because we might have extra time。For each frame to upload。

But the performance still depends on the time it takes to upload and process。

 and we're really not using the pure benefits of DMA。

 and I say that just because if you think about performance in this loop。

 then it's the summation of the time for it takes to process the time it takes to display the time it takes to decode。

 and also the time it takes to upload， the uploads not really happening in parallel to the loop。

 and that's really what we want to do when we take advantage of asynchronous transfers and DMA。

So we need to think about this a little bit more and also how when we do upload。

 we don't want to corrupt data that's currently being processed or currently being displayed。

 so we need to restructure it even a little more。So what you see next on the next slide is DMA restructuring Part 2。

 and what I've done is I've gone to a double buffering approach。

So I always have two frames that I'm working on， first frame A， then frame B， then the next frame A。

 then the next frame B。So on and so forth。So what we see here is。I take frame A。

 which has already been decoded and uploaded， I process it and I display it。

 then next I decode the next frame A。And I upload that。😊，That upload。

Is independent or parallel to the processing of frame B？So with the next frame or a second rate。

 then we can start processing and displaying frame B while that upload of the next frame A happens。

 so this is double buffering and we can get away with this because we have two different frames so that upload is not going to contaminate any of the data in frame B。

 it's just going to overwrite the next frame A and frame B can go on process and display。

So since the upload and the processing can happen in parallel。

 so uploading of next frame A and the processing thing of frame B， then our performance is no longer。

Depenent on the sum of time that it takes for a process display， decode and upload。

 but instead the upload portion is parallel and it's just the maximum of the maximum time it takes to upload compared to the maximum time it takes to process display and decode。

So this is a big deal because now if you look at our performance of how many frames per second we have。

 we've taken a whole portion out of that equation and how well we scale will depend on how much processing time we need and how much uploading time we need。

 but not on the sum of both of those。So DMA， very important。

 it can be useful for a lot of performance boosts， but you have to put some consideration into how those asynchronous transfers are happening to get the most out of it。

All right。Let's move on to the processing portion Now in this talk really I'm going to be talking about how were using the runtime and I'm not going to get into specific video processing filters and how they're implemented and how to tweak those kernels。

Instead， I'm just going to be talking about the runtime。

 and we're going to talk about that processing just in a general sense。And here。

 when we talk about Open C and its architecture， we can think of。A two dimensional picture with。

And each of those pixels needing to be processed and then we can write a kernel that just processes one pixel and then we tell with that one with that kernel and our picture that needs to process。

 we can tell open sp out to go and run that kernel on each of those pixels and the way we do that is。

We create an execution domain that is the size of the frame， so the number of pixels。

Once we have our kernel and maybe we'll load it from a file and compile it and build it and link it。

 then going once we have that finished kernel that's ready to execute。

 we need to set the arguments of this。And I bring up processing here just because。

With a lot of the filters that one might use on a video。

 the parameters to that filter may need to be adjusted very rarely， for instance。

 if you think about color correction， we have an input video and we want to give it a special look to it by changing the colors around。

 well then we might set up those parameters just once and then never change them again。

The way that OpenCO works is really that kernel is an object and the arguments。🤢。

Or parameters to that kernel。Are part of that state。

So this means that we can set the arguments of the kernel once， and if we don't need to change them。

 we can leave that alone and each time we need to process then we're just going to say，Okay。

 execute that kernel。And that's good because then we don't always have to be setting up arguments each time we execute。

So what you see here is how we're going to call to do the execution of that kernel。

And I wanted to draw this out and show the full API because we're going to get into later。

 specifically the latter two arguments， which is events and event。

So we are processing now our kernel。And we need to think about how do we call all of these processing Now we could do the same。

To uploading data and how it had a blocking ability in that we could。嗯。

We could process frame A with the first step of processing， perhaps our color correction。

 and then we could wait for that to complete， and then we could move on to the next step of our processing。

 which could be say a blur。Filter， and then we could wait for that to happen and then we could go over to our second stream of video and perhaps do the same two steps and then after those are all complete。

 maybe we're going to be combining video A and video B kind of a split screen and we could call that filter Now we could wait for each of those processing steps to complete before we go on to the next。

And this may be very good for debugging， but this is very bad for performance。U。So first。

 how can we actually do this process and stop？If we look back on slide nine。

 we see the API does not have a flag called blocklocking weight like the transfer API calls do。

Instead， and let's just go back to slide nine。What we see is we are inqueing the kernel from an open Studio command queuee。

嗯。So what we can do is we can talk to that command queue object。And after we have queued that kernel。

 we can say，All right， I know I just gave the command to queue work。

I'm going to call command this command Q command Qs method finish。

 and it's going to block until all of the。U。Pieces of work in that command queue are completed。

So this will wait until that whole command queue is finished and that means also our kernel is completed。

Another way we can do this is if we look back again at slide nine at the API call。

We see the very last。Argument， we are passing in a pointer to an event。🤢。

Now what's going to happen is we will get back an event that is created from this NQ operation and we can then wait。

 we can tell that we can call the weight method from that event object。And we will block。

On that call until that event is completed。U。And these are two ways we can do that。

 but we can also work a lot smarter。So on to slide 11。We see processing in the right order。

That when we do this in queue。The second to last argument a vector of events。

 and what that vector of events is is actually all of the events that we want to happen before this specific operation that we've in queueed executes。

So if you will， these are。What events are this operation dependent on。

And the runtime will actually be doing something similar to event weight。

 and it'll be waiting for all of those。Precondition our dependency events to complete before。

Our operation starts。Now， when the very last argument， if you will kind of like the out event。

 that's going to signal。Where this operation is。There's a few different steps in that and we'll talk about that in a few slides。

 but。That is going to be the output from this。And we can use that object to feed into。Other NQs。

 so that way we can set up a dependency graph。So this is great in that we can set up this dependency graph and work through what filters need to happen in which order。

 set up the graph in that way， and then we can incue the operations。

And let the runtime synchronize when those operations work。Now， when I was creating this application。

 there was one gotcha that I ran into， one kind of surprise， and that is。

We're passing in a pointer to an event。AndThat as the last argument for this NQ operation。

But that actual event object is created inside of the NQ。

 so this might be it was a little confusing for me because I would create an event object passing the reference to it。

🤢，And what I would get back was a different object。

And this is important because when we're creating that dependency graph。Well。

 we need to have the next operation dependent on the event that has been created from this NQ。🤢。

So one just needs to work through that。If you look back to how we were uploading data。

 they were also actually in queue operations。🤢，And。

Those operations also have the same two last arguments。

 a dependency events vector and also an output event reference。 So we cannot not only use this to。

Set up the dependencies of how the。Filters are processed on the frame。

 but we can also use this to set up that the filter is dependent on an upload happening first。

And so on。So this is very powerful and it actually helps tremendously with the code as we're letting the runtime take care of sorting out the correct order。

Okay， on to slide 12， if we think about this。We're having the upload。Operations happen in parallel。

And the filtering operations are also happening asynchronously。Back to debugging。

 if we wanted to look at how long it takes for that， for instance。

 that color conversion processing step， we could go back to a debugging mode that。🤢。

Makes things happen synchronously， that way we could time， how long did that。

Colors conversionversion kernel take to process。And we could set a timer before we incu it。

 then we could incu it， wait for that。Operation to finish and then stop a timer。 But as I said。

 we don't want to do this for performance。 And it doesn't make sense to measure in one mode and actually run or release in a different mode。

 So how can we have everything working asynchronously and yet still get。

Get profiling and performance information out of it。Well。

 it turns out that the creators of OpenSa really thought about this and they created event profiling。

And what this is is an ability to take that event object that we。嗯。

That we get back from those N queue operations。And we need to。Turn on the event profiling。

 we need to turn it on， and this is all written out in the openC spec referenced here paragraph 512。

And what we can then do is we can get timestamps back from the event as to win certain events。

 as to win certain points。And that event's life cyclee happened。So we see here four。Miilestones。

 I guess you could call them of the event， and that's when that event when the operations of the event references was queued when it was submitted。

From the host to the target device to run。 And then when it started running， and finally。

And where it completed the run。 So I drew a picture on。Side 13， just to make this a little bit clear。

 And up top， what I have here。Are the。The gray boxes are actually the status of that event。

 so the event's going to go through different states， if you will。In those states are queued。

 so when we first call into an NQ operation then the event that is created is first in the queueed state。

 when all of， for instance， the dependencies that it relies on have been fulfilled then we can start going ahead to complete it。

 now the first step to completing the first step to executing that operation is we need to。

Tell the device。What it needs to do。嗯。And that is the submitted。Status of an event。

So now we've told the device what operation we want to do。And once that starts。Doing that operation。

 then the event status turns from submitted to running。

So it's going to run until the operation completes and finally it will be at the completed status。

So up in the gray we see those event statuses and we're able to pull the event status during the lifetime of an event。

But even more useful than polling what is the current status is looking at the event profile data。

 So what happens there， the event profile data。The green boxes are the four event。

For event profile points that I just described on the slide earlier。

 And what these are are timestamps。 So the first one， the queued timestamp is。

Specifically at the beginning of when that event got queued， it's that timestamp and then again。

 once all of the preconditions for that operation are completed。

 then we get a submitted timestamp so in other words you could look at the difference between queued and submit as how long did it take for the openCO runtime to ensure that the preconditions were。

Fulfifilled before the。Operation could be submitted to the GPU。And then very important is。

For performance is looking at how long did it take that operation to run on the GPU？

So the start time stampamp and the end time stampamp are going to be critical for that。

 So this is going to be really our way specifically looking at。

Start to end of knowing how long that operation took。

 and that operation could again be our uploading of data。

or our processing of a kernel and then we could find out， oh wow。

 this blurring filter is taking way too much time， I need to either go in and fix how I've written that kernel or change something in the algorithm。

 or we could also see oh wow， we're taking a long time to upload data， perhaps there I have。

Some larger problem。So this is how we're going to be able to look back on performance。

And figure out where we need to improve things。Okay。So。Going on to display。

We've seen now how we take a decoded frame and upload it and process it and look at that's working correctly。

 Now， what we want to do in this specific application is。Watch that live video。

 which is getting processed。So again， if we think about dependencies here。

 then we can think about that。Our kind of graph of what。Filters are effects we need to run。

On the different video streams。And we can think about how those video streams are getting combined together and we can eventually think we eventually look at that graph。

 see how the final output stream is created then whatever effects are done on that and from that last step in that process。

 that event is going to be important that we need to wait for that event to complete before we can display to the screen。

 otherwise if we start displaying to the screen before that event happens or before that operation completes。

 then we might be presenting a。Garbage from an in between step。

 or we might just be displaying the wrong information altogether。

 so again we need to take that event and we need to wait on that before we can start displaying。

So next， what are we going to do， so we have that final frame up over on the GPU。🤢，And eventually。

 it needs to get displayed out。 But if you think about how。

 what Apis do we need to call to display it out well。For some of those APIs。

 it might be that we need to draw into a rectangle or a view on the screen and the way we might call such APIs is really a copy from memory。

But then if you think about that， then we'd have to go get that data out of the GPU。

 perhaps bring it down to the CPU's main memory， and then copy that and then。

Call into an API which is going to copy that from main memory。Then perhaps that API is going to。

Do some processes into it somehow and then push it back up to the screen。

But it'd be great if we could skip all of those steps of pulling the data back from the GPU and copying it unnecessarily back and forth。

🤢，So luckily there is a way of us being able to skip those steps。

And that is the OpenCL and OpenGL Interop。So this is。

 of course specifically if you are using OpenGO to display the final video。

And if you're using direct X， then there's also some。Interrup that is written into the spec。 Now。

 what I must say about this is these are optional portions of the spec。

 These are added functionality to the original spec， and not all implementations must。Sup point them。

U。So what we're talking about here is Interop meaning that OpenG and OpenCL can share certain information and the specification describes this in section 9。

7 and 9。8 and if you look at the OpenCL specification then you'll see actually the entire section 9 of that specification is talking about optional extensions since they are optional。

 we need to of course ensure that，That they exist on the openC platform that we're running。

 So we do that actually by querying the information of the openC device to get the device extensions。

 And then we need to just look through there to make sure。With the。

The extension that we want to use is supported。Once we've checked that。Then。

Specifically for Open Sa and OpenGO Interop， we need to actually create the context。U。

In openC with certain flags to turn on that openC Opengo interruptop。

 And that's all described really in Section 97。And one can go into the details there。

 but I just wanted to give an overview here about what one needs to do。 So checking that the。

Extension is there。 And then that one has to。Create the context accordingly。

 And then what happens next after we've created that we've told the context to use open。

GL interop well， when we go to create those images。The openCO images。

 it turns out images are the way that the OpenCO and OpenGO interruptop work together。

 so an OpenG texture， a 2D texture maps to an openCL 2D image。

 so what happens here is when we go to create that image we need to tell，The runtime。

Create that image from an open Ge texture that we've already created。

 So that way the texture is not actually the image isn't created in that a new image is allocated。

 but instead it knows to use the same data for that open Ge texture and this open Ge image。 Now。

 if you look。At the API call， you see that this is an openCL image 2D but it is a relative of that and it is an image 2DGL。

 so this is a little bit different image 2D creation call， but actually it's very similar， however。

 as you see I've bolded， it's going to need to know the target。

The MIP level and the texture object from OpenGL that we are referencing target in this case is going to be we're going to be telling it that it's a 2D openGL texture。

 the MIP level we could then say，Do we want the full resolution or half the resolution quarter of the resolution and so on。

 and then the texture object is actually the reference to which texture are we going to want to share。

So once we've created our openCL image using this interop。

 we can then use it pretty much as if it was a normal openCL image。

 I say pretty much because since OpenCL and OpenGL are going to be both using this data。

 we need to do a little bit of handhaking to make sure that we don't step on each other's toes。

So how we do this is there's a call called N Q acquire GL Ob， and we're going to need to。

If you will acquire that openGL texture， then kind of like we have the keys to that texture。

 then we can do manipulations on that texture slash image data。

 once we're finished with that then we can release the openGL objects so that way。

The open GeL side of our application can then use that texture， so this is really what happens。

And for this application， everything is all the video streams are a normal open CO image。

 and it's only that final output video stream which。Does't come from a file， but instead it is。

Created by a composition of the input streams is a special open image 2DGL stream。

 and it's only on that final video stream that I need to do these acquire GL objects and release GL objects when I'm doing any filtering on them。

嗯。And。Then by using this。createdOnce we've completed the Decode portion and pushed the data up to the GPU device。

 we've done all of our processing on it and then the final result stays on the GPU device and is turned over to OpenGL。

 which handles the display of it and turns it into our live video stream。

So that completes all of the steps and now we're at the final video stream and this actually concludes my talk。

 so if you have questions，Please write them in。You can learn more at developer。amD。

 Com in our open C zone。And I thank you all for attending and listening to this presentation。Again。

 you can ask a question by just typing it into the AskA question window and then clicking on Ask a question to submit。

😊，And I'll just pause for a few moments to queue up any questions。

Let does not look like we have any questions today。😊，So you have any closing remarks。 Well。

 and here's one question that real quick。 Somebody asked， well， what about for a video， One oftens。

 for instance， transitions from one input stream to the next。

How could one do that in this application， well， if you think about that。

The filter that's going to be creating a transition from， say，Stream number one to stream number two。

 it might be just doing a swipe from left to the right。

 and if you think about the position of that swipe， that could be an input into the filter。

And we could just say， where does that swipe need to be at a certain time？

So when one changes that kind of to decide when the swipe happens and also how quickly the swipe happens。

 then what we're doing is when we're processing that， when we're going through each frame。

 then we look at the time marker of that frame and say，You know。

 we look at the setting of that swipe and there might be a keyframe to designate when it's going to start and when it's going to end。

 and one could then from that keyframe interpolate where the position of that swipe needs to be and then in the processing main loop。

 one would just，Set that specific parameter。For that swipe kernel。

And it would go on and then the next loop around that parameter would get updated and continue。Okay。

Another question about profiling。The question is concerning profiling。

 will the time between CO profiling command queued and CO Profiling command end？

Always correspond to some external high resolution timer。And a call to， for instance。

 CO finishish for the queue， or can there be a difference somehow。So first。These timest are， yes。

 dependented on a high resolution timer。 and that high resolution timer is going to have。

A certain resolution， how granular it is。哎。Let me just read through this a second time。U。

But what those timestamps are going to be saying is。From the main。Loop。

 when did we incue this operation。And that's going to be the command queued timestamp。

 and then when our OpenC device finished。Executing that。 And that's going to be the command to end。

 Now， if you think about this， will they always correspond high to some external high resolution timer before and after the NQ and a call to。

 for instance， CO finish。They're going to be dependent on that high resolution timer。

 but it's not going to be dependent on。A call to see how finish。

 because it's really going to be when that specific。Colonel， how long it took to。To。

To perform its operation itself and not when C finish was called on the command queue。

 So I guess what I'm trying to say is， for instance。

 if that was the first filter and it had almost no dependencies then it operated real quick and its command and timestamp would be very early compared to the other processes。

 other filters that are dependent on it and at the very end of those filters would be when we're calling to finish the cues to that way。

We can move on to displaying it。Hope that answered your question。So another question is。

I've thought that for an order。For in order execution cues， you do not need to wait for events。

Is it not true So because the。This is true， so what this is talking about is we are inqueing different filters to happen。

And。One of the get info parameters that tells us about the OpenCL device and the runtime that we are working on。

We'll actually say， how are the in operations handled， are they handled in order or out of order？U。

So most of the open CL。Runtime and devices。Are currently in order。

 and that would mean that if we in queuee Op A， then B， then C。

That we're very much guaranteed that Op A happens first then B and then C。

 but if you think about it when we move to perhaps using multiple GPUs or if we move to a runtime that's not going to be using in order execution。

 then that's really where we need to look at when the event how the event dependencies are related and。

How we need to link them up。 So it's。It's true that currently on some of the devices we won't have to look so much about the interdependences of the middle steps and we would just need to look at the last step and make sure that that happens before we can go on。

 but it's just a good practice to look at the steps in between to make sure everything happens directly。

 specifically again， if you're using a multiG multi openCO device approach。Okay。

 here's a great question， so this is talking about the OpenCL and OpenGL Interop but kind of looking at it from a different perspective of not using it just to display with information but to process it and the question is。

 if you have an algorithm that could be written using shaders in OpenGL。

 are there any cases where it would make more sense to use OpenCL？

What about performance for OpenCO versus OpenGL， they should be similar。Question mark。 So true。

 if you have a filter that is currently written in open Gl using Open Gl shading。 and for instance。

 you're very happy with that performance， then yes。

 it might make a lot of sense to continue using that。😊，Open geo shader。

 And then using that the Openco Opengo interrupt to let。

That shader happened in OpenGL and then do the handtaking to then do further operations in OpenCL and perhaps back to OpenGL and back and forth。

Sure， it could make sense to do that now if think about writing those shading programs。

People have different backgrounds and some people might feel more comfortable writing a shader program in OpenGL。

 but I think those people are very rare because just from the syntax of the language and how the language looks and the different operations one can call from OpenC。

 I think it is much easier if you're writing a new。New kernel。

 new filter to do it from Opense just from a language perspective。

But taking the language perspective out， what about performance， well。

 you have to look at what OpenCL and OpenGL exposed hardware wise。

And there are some parts where OpenCL allows you to do more。Then open GL and。

To learn also more about the hardware， so it could also be more advantageous。

To write things in OpenCL。And I'm not an expert on OpenGL。

 but I'm just thinking about different areas。诶。Of what you're telling OpenCL to do， for instance。

 with local data shares， how one can set those up and one really tells the runtime how execute the kernel and telling it not only larger domain to the kernel in。

 but also creating a local domain。To execute together。 So that way。

 work items are shared together in a work group， and that allows。Certain capabilities。

If you already have something in OpenG and would like to be able to use it together with OpenCL。

 I think that makes a lot of sense， but if you're going forward and creating something new。

 I think it might be very advantageous to create that in OpenCO。嗯。Finally， the last question is。

 is there some example code somewhere Currently the application that I created is not available anywhere。

 there is tons of example code though in AMD's OpenCL SDK。

And it really includes everything that I've talked about in this presentation。🤢，In different areas。

 for instance， if you want to look at which extensions are available through openC。

 then there is C infofo sample。 and for us， we have all the samples put together in our SDK so you open up that individual。

Sample， and that shows how to query the。The device and the runtime to get。Extensions。

 there's also another。There's another sample that deals with the OpenCO OpenGO Interop。

 and yeah there's a lot of example code out there and sample code out there for this specific application which I've created and talked about today。

 no， it is not currently available， but that might change in the future。

So good if there aren't any more questions， and again I thank you very much for your time and for attending this。

 thank you。 And thank you everyone for joining us。 The recording of this webinar will be made available to you。

 and this concludes our presentation。 You may now disconnect。😊。

