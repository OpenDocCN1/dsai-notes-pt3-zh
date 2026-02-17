# LlamaIndex《事件驱动的智能代理文档工作流｜Event-Driven Agentic Document Workflows》中英字幕 - P7：7.use-your-voice.zh_en - GPT中英字幕课程资源 - BV1boRNYrEiz

![](img/f90e79bd9787a02bc9bfcefbd9b04124_0.png)

In the previous lesson， you gave feedback to your agent as text。

 You'll now provide feedback to the agent in spoken natural language。

 You will add multimodal capabilities to your agent so it can capture the feedback as audio spoken by the user。

 Let's have some fun。😊。

![](img/f90e79bd9787a02bc9bfcefbd9b04124_2.png)

So far， we've set up a moderately complex workflow with a human feedback loop。

 Let's run it through our visualizer to see what it looks like。

 We're going to bring in a couple of things just to get that done。

 Here are all our imports and our cloud keys。 And here all in one step is our entire Warag workflow。

 This is exactly the workflow that we were using in the previous lesson。

 So there's nothing new to walk through。 We'll execute all three of those。

 And then we'll visualize it using the visualizer。😊。



![](img/f90e79bd9787a02bc9bfcefbd9b04124_4.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_5.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_6.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_7.png)

It's pretty complicated。 So it's zoo out a bit。Cool。

 this is a really fun visualization because you can see the entire happy path that we're walking through。

 You start， you set up， you parse your form， you generate questions， you ask a question。

 you fill in the application form。 This is the external step where you get human feedback and then you get feedback。

 And at that point， you can either stop or you can complete the loop and do it again。 Now。

 just for fun。 We're going do one more thing。 You're going to change the feedback from text feedback to actual words spoken out loud。

 to do this。 We'll use a different model from openaiI called whisper。

 Lama index has a builtin way to transcribe audio files into text using whisper。

 Here's a function that takes a file and uses whisper to return just the text。 It loads the file。

 It instantiates the whisper reader。 And then it gets the text out of the document。

 These is the same sort of documents that we were using for ragg earlier。 Before we can use it。

 We need to capture some audio from your microphone。 That involves some extra steps。 First。

 let's create a call。😊，F that saves data to a global variable。

 So we haven't somewhere to store the transcription once we've got it。 Now。

 you're going to use radioio， which has special widgets that can render inside a notebook to create an interface for capturing audio from a microphone。

 When the audio is captured， It calls transcribed speech on the recorded data and calls store transcription on that。

 You can see that happening here。 It's defining your inputs。

 defining your outputs and is running this function， which is the function that we described up here。

 And then we're passing the output of transcribed speech to store transcription。

 which we defined here。 in Grio。 you further define a visual interface containing this microphone input and output。

 And then you launch it。 So we're creating a blocks interface。 We're putting some tabs into it。

 And then we're going to launch it。 Grdio gives us this really cool。😊。



![](img/f90e79bd9787a02bc9bfcefbd9b04124_9.png)

Already set up interface for us。 And it can listen to our microphone。 Let's try that out。Hey。

 computer， can you hear me？We'll submit it， and it correctly transcribes the audio。 Nice。

 Gadio is pretty wild。 You can do all of this and print out the transcription in just a few lines of code。

 Let's make sure that we've got it in that global variable that we set up earlier。😊。



![](img/f90e79bd9787a02bc9bfcefbd9b04124_11.png)

There it is。 We're going to want to run radio again。

 So it's a good idea to shut down the radio interface that you were using。 Otherwise。

 your radio interfaces will compete with each other。 Now。

 we're going to create an entirely new class a transcription handler。

 I'm going to walk through what it does step by step。 First。

 we're going to create a queue to hold our transcription values。 Every time we record something。

 we're going to put it in the queue using this method store transcription。

 This create interface method is the same interface and transcription logic that we were using a little bit earlier。

 except it stores the result in the queue instead of a global。

 You can see that happening because it's calling self store transcription， which we defined here。

 Then we launch the transcription interface just like we did before。

 But the new thing we do is we pull every 0。5 seconds， waiting for something to end up in the queue。

 So this wild true loop will just continue forever。 sleepingep for 5。5 seconds every time。

 But if there's something in the queue。 It'll notice， and it will close the interface。😊。



![](img/f90e79bd9787a02bc9bfcefbd9b04124_13.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_14.png)

And return the result。 Now you have a transcription handler。

 you can use it instead of the keyboard interface when you're getting human input when you run your workflow。

 we don't have to change the workflow at all for this to work。 So just like before。

 we set up our workflow， we pass at our fake resume and our fake application form。

 and we wait for an input required event。Now， instead of getting keyboard input。

 we call our transcription handler。Once our transcription handler has given us a transcription。

 we send that as the human response event。 So with the moment of truth， let's try it out。



![](img/f90e79bd9787a02bc9bfcefbd9b04124_16.png)

A change that I made that I didn't tell you about was to give us a little bit more feedback about what's going on under the hood。

What I've told it to do is to print out every question and every answer that it gets while its's thinking。



![](img/f90e79bd9787a02bc9bfcefbd9b04124_18.png)

So you can see it doing that here。

![](img/f90e79bd9787a02bc9bfcefbd9b04124_20.png)

All right， it's got to the end of the questions。

![](img/f90e79bd9787a02bc9bfcefbd9b04124_22.png)

And now it's spun up a gradio interface asking us for feedback。



![](img/f90e79bd9787a02bc9bfcefbd9b04124_24.png)

We can see from the answers to the questions that it's made the same mistake that it made before。

 The project portfolio is a list of things that the candidate did instead of a URL。

 So let's use the audio feedback to tell it that that's what we need to change。



![](img/f90e79bd9787a02bc9bfcefbd9b04124_26.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_27.png)

The portfolio field should be a URL。

![](img/f90e79bd9787a02bc9bfcefbd9b04124_29.png)

We submit。

![](img/f90e79bd9787a02bc9bfcefbd9b04124_31.png)

And the L L M reads that transcript and correctly decides that I gave it some feedback。

 So now you can see our questions and answers happening。

 Each one of them has this extra feedback field attached。

 Every single question gets the same feedback that the portfolio field should be a URL。

 which is really only useful for one of them。 you can think about how you would improve that。

 If you were doing this in a more production application。 O。

 it got to the end of the questions again， and it spun up another gra interface asking us for feedback。

😊。

![](img/f90e79bd9787a02bc9bfcefbd9b04124_33.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_34.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_35.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_36.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_37.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_38.png)

Let's tell it that it did a good job this time because it did。 The portfolio was a URL。

 just like we asked。

![](img/f90e79bd9787a02bc9bfcefbd9b04124_40.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_41.png)

That's great。 Good job。

![](img/f90e79bd9787a02bc9bfcefbd9b04124_43.png)

The L L M has correctly interpreted my positive feedback as saying that everything is O。

 and it's spaed out the form。 Congratulations， you' have successfully created an AI agent that responds to spoken human feedback。

😊。

![](img/f90e79bd9787a02bc9bfcefbd9b04124_45.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_46.png)

![](img/f90e79bd9787a02bc9bfcefbd9b04124_47.png)