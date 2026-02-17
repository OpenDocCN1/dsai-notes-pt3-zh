# 吴恩达《使用smolagents构建代码智能体｜Building Code Agents with Hugging Face smolagents》 - P5：5.monitoring-and-evalutating-your-agent.zh_en - GPT中英字幕课程资源 - BV1twLZzwE6o

With the help of your agents， you've now set up your ice cream truck。

 But as word spread of what you've done， you start getting more and more calls。

 mostly with ice cream preorders for people who want to skip the line when they come to collect their ice cream。

 But this can also be more complicated requests like I want to set up an ice cream truck。

 how do I do this。 So in this lesson， you will learn how to build a strong agent to help you triage this flow of requests。

 And most importantly， I will show you how to record agent runss to monitor how they went。 All right。

 let's go。 let us first set a name for our project。 Well let make customer success。

 Since this is about answering customer requests。 Then we can set up the tracing。

 note that we use our project name here。 And in this specific case。

 we use a custom endpoint to redirect you to the correct URL。 But if you are running this locally。

 you would have a simpler code。Let's run this Now instrumentation is ready。

 That means that whenever small agentss related code is running。

 it will be recorded in the tracing interface。 Now let us set up the small agents side of this we start by logging into the hub with our API key。

 then we can try to display a very simple trace， let us just record a model answer。

We run this and get the answer。 Now I will show you how to go and display this trace。

 Here is the link。 We click it。 Now you can see the interface in which you can find your new project by its name。

 customer success。 Let's click it。 then here you can see your model call displayed。 It has a latency。

 It has token counts。 It has input and output messages。

 This interface is very efficient to display model runs， but it can also display agent runs。

 I will now show you how to do this。 Let's switch back to the notebook。

 Now we will define a full agent based on the model above。

 So we give it the same model and an empty list of tools。 Let's ask it a math question。



![](img/1860ae3c17cb090a15b03c0e11841b6b_1.png)

![](img/1860ae3c17cb090a15b03c0e11841b6b_2.png)

![](img/1860ae3c17cb090a15b03c0e11841b6b_3.png)

Okay， actually the agent once shoted this one， let's see what it looks like in the interface。

 so we're back in the interface from within here we will travel back。



![](img/1860ae3c17cb090a15b03c0e11841b6b_5.png)

![](img/1860ae3c17cb090a15b03c0e11841b6b_6.png)

To the agents and the agent run displays here。

![](img/1860ae3c17cb090a15b03c0e11841b6b_8.png)

So as you can see， the agent did quick work of this one with only one step。

 but the interesting part is that you had this hierarchical structure with untop the agent run and within the step you have first a model call similar to the other one that I've shown you earlier and a tool call when you have several steps they will be chained together on the step level and if you have multiple agents。

 the treela structure will be extended to show all the different agent runs now that you've learned how to trace an agent run。

 I'll show you how to set up your production system for your full customer support agents you want to define several tools that will help customers place orders or get information about the prices now you're ready to set up the final agents using the tools above and we can test runnet with a simple order。



![](img/1860ae3c17cb090a15b03c0e11841b6b_10.png)

As you can see， the agent properly uses the tool to place an order now that the agents is ready。

 requests will come stream in， have made a small dataset sets of fake client requests to test the agents。

 each of these is a tuple with on left the request and on the right the expected tool call。

 which sometimes is none， we can now run each of these requests and all the processing done by the agents will be traced within the platform Phoenix that we've just defined above。



![](img/1860ae3c17cb090a15b03c0e11841b6b_12.png)

![](img/1860ae3c17cb090a15b03c0e11841b6b_13.png)

And once all the requests are processed， you can just get all the traces from Phoenix as a data frame of the different spans。

 Let us see how this looks like as you can see here。

 all the individual spans have been traced beats on the top level the agent run and an intermediate level the different steps logged as chains and then even more fine grain we also log tool and LLM calls。

 these data frame will be consequent， especially as you have many requests。

 so we need to do a bit of processing to extract the information that we want from this here what we want to check is that each request was followed by an appropriate tool call So for instance。

 we want the request how did you start your ice cream business to be followed by no tool let us process the spans data frame to extract for each request the corresponding tool pro by the agent。

And this will allow us to get a final data frame of the results。

 and if the toolco were correctly performed。 as you can see。

 sometimes the toolco performed well the right one， and sometimes they weren't， For instance。

 the question how did you start your ice cream business was followed by the tool called get prices which was not appropriate for this request。

 Of course， for your production system， you would need to check for additional elements as well。

 For instance， the question what's the weather at the Louuvre right now。

 was not one that we could have answered properly with the tools given to your agent So here。

 no tool was called， which is correct according to our scoring craterion， which is very basic。

 did we call the correct tools or not， But if you inspect more closely the answer。

Here the agent has defined a simulated weather API call before running it。

 which means that the answer given to the client was hallucinated。

 The client was answered that the weather was sunny with 22 degrees Celsius whereas in fact the agent knows nothing about this because it has no available information So this is the kind of behavior that you would want to monitor with a more fine grain assessment。

 For instance， using LLM as a judge to rate the agent trace compared to the requests and the expected answer。

 So， of course， your own implementation may vary depending on the results that you want to achieve。

 but now you've got all the tools to build it let's take a step back and recap what you've just learned you've learned how to set up the tracing for your small agent objects and how to trace an agent run before finally obtaining the traces and assessing them to check that your agent is running properly in the next lesson I will show you how to set up a multiag。



![](img/1860ae3c17cb090a15b03c0e11841b6b_15.png)

![](img/1860ae3c17cb090a15b03c0e11841b6b_16.png)

Then to tackle extremely complex tasks。

![](img/1860ae3c17cb090a15b03c0e11841b6b_18.png)