# LangChain【中英⚡LangGraph 使用指南｜LangGraph (Python)】 p10 P10 LangGraph： Persistence -BV1vJfMYuEon_p10-

In this video， we'll cover how to add persistence to line graph agents。

So we've added a method in La graph where when you create the graph， you can specify a check pointer。

 and this check pointer will save the state of the graph at each it。

 So if you want to resume from that same state， you easily can。

One really obvious use case of this is giving the agents memory。

 So you can basically resume previous conversations with the agents and it will have the exact memory of everything that they've done up until that point。

 or more precisely， they will have memory of what the state was when they last interacted with that checkpoint。



![](img/e17288511ae078adb97e7126c3048823_1.png)

So let's take look at an example of how to do this。

So in this notebook we can set up our open AI tovily and Langsmith keys we can start and this is just creating a simple message graph agent if you haven't watched the videos on how to create these types of La graph agents before。

 go check those out。 There's much deeper dives on them。

 We'll just create a pretty straightforward one it will have access to one tool a tovily search tool。



![](img/e17288511ae078adb97e7126c3048823_3.png)

![](img/e17288511ae078adb97e7126c3048823_4.png)

![](img/e17288511ae078adb97e7126c3048823_5.png)

We'll create the tool executor we'll be using openaiI for this demo。

 although you can use any model you want。 we'll create we'll bind these functions to the models to the model and now we'll create our graph this is just gonna be a really simple So we're gonna use a really simple message graph down here。

 So we're going have one function that basically takes in a list of messages and determines whether it needs to call a function or whether it should to continue when when we call the model。

 we're just going to invoke it on the model and then return back the response。

 and then we're also going have this node that just calls tools So these are standard these are standard nodes that we're going create we'll create the graph we have this agent node。

 we have this action node， we set the entry point to be agent after the agent。

 we see whether we should continue we either finish or we go to the action and after the action we go back to the agent So this is all standard kind of like。



![](img/e17288511ae078adb97e7126c3048823_7.png)

![](img/e17288511ae078adb97e7126c3048823_8.png)

![](img/e17288511ae078adb97e7126c3048823_9.png)

![](img/e17288511ae078adb97e7126c3048823_10.png)

![](img/e17288511ae078adb97e7126c3048823_11.png)

![](img/e17288511ae078adb97e7126c3048823_12.png)

![](img/e17288511ae078adb97e7126c3048823_13.png)

![](img/e17288511ae078adb97e7126c3048823_14.png)

![](img/e17288511ae078adb97e7126c3048823_15.png)

Page and graph stuff that we've done in other videos。

 What's now new is that when we compile this graph， we're going to pass in a checkpointer。

Specifically， we're going to pass in the SQLite checkpointer。

 So it's called SQLite saver from connection stream or're connecting to it in memory。

 although we could easily connect to a database that's in disk or anywhere else。

So we're going to create this， we're going to pass this in to workflow。

com file and now we have our app。

![](img/e17288511ae078adb97e7126c3048823_17.png)

So now we can interact with this agent so let's create our first message and let's say hi， I'm Bob。

 we'll pass this in and notice that we're passing in this thing right here， which has a thread ID。

 So this is so configurable is basically just ways to configure specific attributes on it and thread ID is a way to configure the checkpointer。

So what will happen is we'll send the inputs in and they'll be associated with this thread ID equals2。

 and so if we want to resume from that， then we can just use the same thread ID if we want to start again。

 we can use a separate thread ID。

![](img/e17288511ae078adb97e7126c3048823_19.png)

So here we'll pass this in。 we'll print out the results。 Here is just Holo Bob。

 how may I assist you here we'll pass in another one And so notice that we're only passing in what is my name And so if we did this and we didn't have this persistence layer here。

 then it wouldn't know what the name is， but since we added this persistence layer。

 we can see that it。

![](img/e17288511ae078adb97e7126c3048823_21.png)

![](img/e17288511ae078adb97e7126c3048823_22.png)

Remembers that your name is Bob。 And this is because we're using the same thread Id。

 If we switch thread Ids and set thread I equals to3 in passing the same question， what is my name。



![](img/e17288511ae078adb97e7126c3048823_24.png)

It doesn't remember it。 And that's because there's nothing in that in that state before。



![](img/e17288511ae078adb97e7126c3048823_26.png)

This video hopefully showed you how to add state or add persistence to your La graph agent。

 We showed how to do it with the message graph， so it's just remembering this list of messages。

 although this works generically for the state graph as well。

 So if you want to save other aspects of state， it can absolutely do that and with this thread I configuration。

 you can easily resume conversations from where you last left off。



![](img/e17288511ae078adb97e7126c3048823_28.png)

Thanks。