# LangChain《使用 LangGraph 构建具备长期记忆的自主智能体Long-Term Agentic Memory with LangGraph》 - P5：5.email-assistant-with-semantic-+-episodic-memory.zh_en - GPT中英字幕课程资源 - BV16oQhYdEjF

![](img/e62126eba5260231f249d573a77d218a_0.png)

In the previous lesson， we added in semantic memory to our agent。



![](img/e62126eba5260231f249d573a77d218a_2.png)

We're now going to add in episodic memory。We're going to add it in in the form of few shot examples。

 and we're going to add it into the triage step。

![](img/e62126eba5260231f249d573a77d218a_4.png)

So as a reminder， episodic memory is experiences， and in agents。

 this is generally best represented as past agent actions and as few shot examples that will pass into the prompt。



![](img/e62126eba5260231f249d573a77d218a_6.png)

![](img/e62126eba5260231f249d573a77d218a_7.png)

Let's see this in action。This should hopefully look familiar to you by now， this is the basic setup。

 we're going to load some environment variables， define our profile， define our prompt instructions。

 and define an example email。

![](img/e62126eba5260231f249d573a77d218a_9.png)

![](img/e62126eba5260231f249d573a77d218a_10.png)

![](img/e62126eba5260231f249d573a77d218a_11.png)

Now is where we normally define the triage logic。But let's take a pause here and talk about few shot examples。



![](img/e62126eba5260231f249d573a77d218a_13.png)

The first thing we need to do is define our long term memory store。

 This is the same as we used in lesson 3。

![](img/e62126eba5260231f249d573a77d218a_15.png)

After this， we can define the data that we want to load as few shot examples。So first。

 we need to decide on the email content that we want to store。

 So this is actually the same as the example input above。



![](img/e62126eba5260231f249d573a77d218a_17.png)

But we will use this now as a few shot example。We then put this as part of a larger data model that contains the email this is generally the inputs。

 and then the outputs in this case we'll call it label and we'll call it respondspon。

And these outputs are also going to be in the few shot examples that we format。

 so this is going to help change the behavior of the agent。



![](img/e62126eba5260231f249d573a77d218a_19.png)

We can now put this example into the long term memory store。We can do this by specifying a namespace。

 and so this is similar to before， email As Lance。But then notice that here is examples。

Whereas what we use for the semantic search over facts is collection。We pass in the ID。

 which is just a UU ID， and then we pass in this data up here。



![](img/e62126eba5260231f249d573a77d218a_21.png)

Lets add in another data point。So that we can do search over multiple data points and see which ones are returned。



![](img/e62126eba5260231f249d573a77d218a_23.png)

So here we'll add in a separate one， this one is a new email sent by Sarah Chen。



![](img/e62126eba5260231f249d573a77d218a_25.png)

Let's now simulate searching and returning these examples in a formatted way。Before that。

 we're going to define a simple helper function， which is going to take in the few shot examples that we retrieve directly from the store and format them nicely into a string。



![](img/e62126eba5260231f249d573a77d218a_27.png)

This is great because it will allow us to easily see what we retrieved。

 and this is also a better format to pass into the LLM than the raw examples。

We can see that once we get the examples back from the store。

We are going to format them into this template， which just contains information about the email subject。

 email from email to， So it's putting it in a nice human readable way。

And then it has this triage result。This is the outcome of the triage step。

 and we're now going to be putting this as part of the prompt。

And so here you can see that for each example， we're taking the email part， this is the input。

 and we're formatting this above。And then we're putting the result is the label， this is the output。

That we put as part of the data that we stored in the store。

 So these are just helper functions to take that data and format it nicely。



![](img/e62126eba5260231f249d573a77d218a_29.png)

![](img/e62126eba5260231f249d573a77d218a_30.png)

So let's now simulate searching over。 This is the exact same email that we passed in above。

 and I'm going to change something small just so that it's not doing an exact match。

I'm then going to search over the namespace that we had， and I'm going to pass in as query parameter。

 this email data。I'm going to set limit equals once。

 so remember I've stored two pieces of information in the store already。

 so it should just fetch the one that is most similar to this。



![](img/e62126eba5260231f249d573a77d218a_32.png)

I get back some results， and now let's format them with the helper function we had above。



![](img/e62126eba5260231f249d573a77d218a_34.png)

![](img/e62126eba5260231f249d573a77d218a_35.png)

We can see that it got back the data point that we stored。

 which is slightly different from the data point we passed in。

 but it's still semantically very similar。

![](img/e62126eba5260231f249d573a77d218a_37.png)

![](img/e62126eba5260231f249d573a77d218a_38.png)

Let's now start putting this together into a new triage step that does this few shot example search。

So the first thing we're going to do is define a triage system prompt。

 so previously we imported this from a helper file。

 but now we're actually going to define it in code so that we can modify it if we want。



![](img/e62126eba5260231f249d573a77d218a_40.png)

And we can see down here that we have this few shot examples section where we are going to format the examples and then also add some more instructions here that basically is your say to pay close attention to these examples。



![](img/e62126eba5260231f249d573a77d218a_42.png)

Let's import a bunch of stuff for the routing step。So this is all the same as before。

 We have some imports。 We're going to initialize a chat model。 We have this output schema。

 We're going to attach that and get this LM that now generates structured information。

 and then we're going to import our triage user prompt。

 We don't need to import the triage system prompt because we've defined that above already。



![](img/e62126eba5260231f249d573a77d218a_44.png)

We then have some code that should look pretty similar to before。

It's used to set up the triage router node， so we're going to create our state and we're going to have some imports here。



![](img/e62126eba5260231f249d573a77d218a_46.png)

![](img/e62126eba5260231f249d573a77d218a_47.png)

This is the previous definition of the triage router node。



![](img/e62126eba5260231f249d573a77d218a_49.png)

So how are we going to modify this to account for this few shot example prompting First。

 we're going to take in a config and a store into the input。

 These will be passed through by the main agent。We're then going to add some logic before the system prompt gets formatted to basically add in the few shot examples here。



![](img/e62126eba5260231f249d573a77d218a_51.png)

![](img/e62126eba5260231f249d573a77d218a_52.png)

This is the logic that we're going to add。 First， we define the name space。

 This is where to search for the few shot examples。



![](img/e62126eba5260231f249d573a77d218a_54.png)

![](img/e62126eba5260231f249d573a77d218a_55.png)

It's going to be email assistant。 and then this is where we're going to use the config and we're going to pull in the La graph user I from there and then examples。

 And so this is the namespace。 We're then going to use this to search in the long term memory store。

For the query， which is just a strified version of the email。

We're then going to format these few shot examples into a string。

 and we're going to update this to pass in the example string into the system prompt。



![](img/e62126eba5260231f249d573a77d218a_57.png)

![](img/e62126eba5260231f249d573a77d218a_58.png)

After that， we can go about creating the rest of our agent。

 so we're going to create all the same tools that we had before。

We don't need to redo this because we already created the store so we can get rid of that。



![](img/e62126eba5260231f249d573a77d218a_60.png)

![](img/e62126eba5260231f249d573a77d218a_61.png)

We're going to create the tools for managing and searching memories。

 We're going to create this prompt and the function for creating it。

 we're going to create this response agent and we're going to have this config that we're going to use。



![](img/e62126eba5260231f249d573a77d218a_63.png)

![](img/e62126eba5260231f249d573a77d218a_64.png)

![](img/e62126eba5260231f249d573a77d218a_65.png)

We're then going to put together this email agent， same as before， and again。

 we're passing in the store to make sure that it's covered。



![](img/e62126eba5260231f249d573a77d218a_67.png)

Let's now test this email agent out and see the effect of few shot prompting。

 So here we have an example email input from Tom Jones， Hi John wantanna buy documentation。

Let's call it and let's pass in the config with the Lgraph user ID of Harrison。

 and we can see that by default， this email requires a response。



![](img/e62126eba5260231f249d573a77d218a_69.png)

![](img/e62126eba5260231f249d573a77d218a_70.png)

But what if we don't like that， What we can do is we can add a few shot example in to our long term memory。

 and then that will be pulled in at runtime， and it will handle future similar emails in a similar way。

So here we can add that。With a label of ignore。 So let's now say we want to ignore these types of emails。

 We'll put that in a store。 Our namespace is email assistant Harrison。

 because this is the Langgra user I D examples。And then we store it in there。



![](img/e62126eba5260231f249d573a77d218a_72.png)

If we run this again， we can now see that it's classified as ignore。

 It's pulling in this fusot example and learning that this should be ignored。

 We can also change it slightly。So I've now added more question marks and added in Jim。

And we can see that it still gets classified as ignored。

 so it's learning to treat similar emails in a similar way。



![](img/e62126eba5260231f249d573a77d218a_74.png)

If we pass in a different La graph user ID， we can see that it's Respon。

 that's because these few shot examples are scoped to this individual La graph user ID。

We've now added in episodic memory to help with updating and learning user preferences for triaging。

This is the end of the lesson， so it's a great time to pause and play around with different examples and different L graph user IDs and just generally play around with it and better understand all the fun and all the learning that it can have。

See you in the next lesson。

![](img/e62126eba5260231f249d573a77d218a_76.png)