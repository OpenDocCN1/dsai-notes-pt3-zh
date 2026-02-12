# LlamaIndex《事件驱动的智能代理文档工作流｜Event-Driven Agentic Document Workflows》中英字幕 - P6：6.human-in-the-loop.zh_en - GPT中英字幕课程资源 - BV1boRNYrEiz

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_0.png)

The workflow you set up in the previous lesson identified all the fields in the form and generated plausible answers to all of them。

 But there are a couple of fields where the answers could be better In this lesson。

 you will give feedback to the agent on the returned answers and ask it to re answer when necessary。

 Let's get to it。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_2.png)

L Ms are amazing， but they are best used to augment rather than replace a human。

 Your current form filler does an excellent job figuring out what fields need to be filled in and gets most of the fields right。

 But there are a couple where it needs a little help to take care of those。

 You're going to create a human in the loop workflow where you can optionally provide feedback to the agent you've created and have it incorporated into the results。

😊，So let's get started on that。First， we'll need our imports as usual， and we'll need async IO。

And we'll need our API keys。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_4.png)

The changes we're going to make to our workflow。Are pretty significant。

 We're going to use the input required and human response event。

 These are new special events specifically designed to allow you to exit the workflow and get feedback back into it。

 You used to have a single step， which parse your form and fired off all of the questions。

 Since we now might loop back and ask questions several times。

 you don't need to parse the form every time。 So we'll split up those steps。

 This kind of refactoring is very common as you create a more complex workflow。

 Your new generate questions step， will be triggered either by a generate questions event triggered by the form parser。

 or by a feedback event， which is the loop that we'll take after getting feedback。

 Then we emit an input required event。 And in the same step。 you'll wait for a human response event。

 This will pause the whole workflow waiting for outside input。 Finally。

 you'll use the L L M to parse the feedback and decide whether it means you should continue and output the results。

 or if you need to loop back。 That's a lot。 So let's get started。 First， we bring in our new event。😊。



![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_6.png)

タイs？

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_8.png)

And now as usual， we set up our events。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_10.png)

There's a new one here， the feedback event。Let's put in our workflow and walk through it line by line。



![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_12.png)

This stuff is all the same。 Your setup remains the same， and your parse form has changed。 Now。

 we have separated the form parsing from the question generation。

 So after we have parsed the form into fields， when in the context， we set our fields to fill。

 and then we send it to the Gene questions event。 The generate questions step， like I said。

 can be triggered by a generate questions event， but it can also be triggered by a feedback event。

 We'll see how that happens in a bit。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_14.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_15.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_16.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_17.png)

The first thing we do is we get the list of fields to fill from the context。

 Then for each of those fields， we fire off a query event just like we did before。

 and we store the total number of fields so that our collect events will know how many fields it should be waiting for。

 Our ask questions event is unchanged。 But now in our fill an application form。

 we're going to o an input required event。 Just like before， we're going to wait for collect events。

 It will return none until all of the events have been collected。 And once it's done。

 we're going to turn it into a list of questions。 The new thing we're doing here。

 is we're going to set our sets of questions into the context to use later。

 And now we're going to emit an input required event。

 This is going to send a message to the human asking how things look and asking the human to give some response in our next step。

 which is called get feedback， we accept a human response event。 So unlike our previous steps。

 which were always triggered by the event from the step before。😊。



![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_19.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_20.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_21.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_22.png)

Now have a gap。 The input required event isn't being emitted by anything。

 It's going to have to be emitted later。 The input required event is being captured by something else。

 and the human response event isn't being emitted inside of the workflow。

 It has to come from outside the workflow。 We'll see how that happens in a second。

 once we get the feedback。 what will do is we will ask the LL M to decide whether or not the feedback is good or bad。

 if everything is fine， the LL M will read the feedback and say that things are okay。

 but if there's any other feedback， it will respond with the word feedback。

 and we will use that to decide what to do next。 If the L M said everything was okay。

 then we'll emit a stop event and will be done。 If the L M emits feedback。

 then we are going to emit a feedback event。 Cool， So now your workflow is ready to get some feedback。

 But how do we actually get it。😊，Turns out you already know how the input required event is an event in the event stream。

 just like progress events and text events that you sent previously。

 You can intercept it the same way that you did those and use the send event method on the context to send back a human response event。

 So all of this happens in the code where we execute the workflow。

 Let's walk through it line by line。 This part is the same as you've seen before。

 We get a handler by executing the workflow。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_24.png)

And this part is filtering the events just like we did before， except this time。

 we're waiting for an input required event。 When we see an input required event。

 we're going to print out the form so the user can see what's up。

 And then we're going to use the input method to get。

Keyboard feedback Once we've got the feedback in the response variable。

 we'll send it as a human response event using the send event method。

And then we'll await the handler。 So let's execute these and see how that looks。 Co。

 So here is the combined list of fields and succinct factual answers that the L L M has given us。

 just like before， it's done a good job of numbering everything。

 But project portfolio is still a list of things that the applicant did instead of a link to their portfolio。

 So let's say that。😊。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_26.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_27.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_28.png)

Portfolio。Should be。Hey， URL。The L L M says the verdict was feedback。

 So now that's going to trigger the loop。 It's going to try everything again。

 but we haven't actually found a way to incorporate the feedback yet。

 So it's just going to do everything exactly the same way it did。

 We'll incorporate the feedback In our next change。 In the meantime， Let's just say this is fine。



![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_30.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_31.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_32.png)

The L N says the verdict was O。 So the workflow halts。 Co。

 So now let's further modify things to actually do something useful with that feedback that we've generated。

 This involves checking if there is feedback and appending it to the questions In this simplified example。

 we're going to append the feedback to every question in case it's relevant。

 But a more sophisticated agent might apply it to only the fields where the feedback applied。

 Here's our modified workflow。😊。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_34.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_35.png)

Set up is the same。 Parse form is the same。 but generate questions is changed。

 Now we're going to check if the attribute feedback exists on our event。

 If the attribute feedback exists on our event。 That means that it's a feedback in it。

 And we're going to use it。 So we're going to modify each question that applies to each field to include the feedback。

 We're going to say it might not be relevant to this particular field so that the L of M doesn't get confused about why we're applying feedback to every single event。

 then just like before， we generate query events and we store the total number of fields。

 ask question remains the same till an application remains the same。

 and get feedback remains the same。 So let's execute this cell。



![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_37.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_38.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_39.png)

And then run our workflow。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_41.png)

Everything hair is exactly the same as it was last time。

 except now it's going to understand what to do with the feedback。 Okay。

 we've got the first attempt at the form。 as before。

 product portfolio is a description of the things that the applicant has done。



![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_43.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_44.png)

Now we'll give it the feedback。Portfolio should be a URL。 We hit enter。

 The L L M has worked out that the verdict was feedback。 Now it's going to try again。

 and it's going to append that feedback to every single question。 So that the L L M knows what to do。

 Cool。 here's the new modified version。 And as you can see field 6。

 the portfolio has correctly been turned into a URL。 That's exactly what we wanted。 So let's tell it。

 that's great。😊。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_46.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_47.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_48.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_49.png)

One of the fun things about giving feedback in natural language is you can just say anything。

 And it'll figure out what you meant。 The L M says that that's great。 means the verdict was O。

 And so it stops the workflow and gives us the output。 Succs。

 Our agent now responds to human in the loop feedback and produces more accurate filled forms as a result。

 congratulations。😊。

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_51.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_52.png)

![](img/8f209c9e3ecea0f0b8855ebce1a4bb10_53.png)