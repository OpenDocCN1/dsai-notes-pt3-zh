# LangChain《使用 LangGraph 构建具备长期记忆的自主智能体Long-Term Agentic Memory with LangGraph》 - P4：4.email-assistant-with-semantic-memory.zh_en - GPT中英字幕课程资源 - BV16oQhYdEjF

![](img/d107fa768e67d52e0c22404bae03a686_0.png)

In this lesson， we're going to start with the email agent that we created previously。

 and we're going to add in tools to allow it to operate on semantic memory。



![](img/d107fa768e67d52e0c22404bae03a686_2.png)

![](img/d107fa768e67d52e0c22404bae03a686_3.png)

Now， as a reminder， semantic memory normally stores facts about a user。

 So we're going to use these tools to learn facts about users。

 We're then going to store them in a long term memory store。

 and then we're going to add a separate tool to search over these facts。 Let's see it in code。



![](img/d107fa768e67d52e0c22404bae03a686_5.png)

So here we have a lot of setup from the previous lesson， and this should look all the same。

 We're going to load some environment variables。 We're going to define our profile。

 we're going to define our prompt instructions， an example email， we're going to set up the router。

 Nothing's changed here。 We're going to import some prompts。

 We're going to define our three tools that we had before。



![](img/d107fa768e67d52e0c22404bae03a686_7.png)

![](img/d107fa768e67d52e0c22404bae03a686_8.png)

![](img/d107fa768e67d52e0c22404bae03a686_9.png)

![](img/d107fa768e67d52e0c22404bae03a686_10.png)

Now we're going to start to define our tools for managing memory。

The first thing we're going to want to do is properly set up our long term memory store。



![](img/d107fa768e67d52e0c22404bae03a686_12.png)

And so for this lesson， we're just going to use an in memory store。

 a store that will store everything in memory， and so we're going to import that from La graphra。

When we initialize it， we're going to want to make sure that we pass in this index parameter Ram here we're passing in an embedding model to use to index the memories that we store。

 so we're going to use the Open AI T embedding3 small model。



![](img/d107fa768e67d52e0c22404bae03a686_14.png)

Afterwards， we're going to import two functions from Langmum。

 Lngm is a wrapper on top of lang graph for working with memory。

These two functions are going to be called Create Man Meory toolol and Create Search memoryory tool。

 and these will be tools for managing and searching over memories。



![](img/d107fa768e67d52e0c22404bae03a686_16.png)

To create them， it's pretty simple， we're just going to define the namespace that we want these tools to operate on。

So the namespace that we're going to use for both is email assistant as the first value。

Then this templated La graph user ID， and I'll come back to that as a second value。

 and then collection as the third value。So what exactly is this？When we invoke the agent now。

 we're going to pass in a Lagra user ID as part of the runtime configuration。

 and that's going to be used to name space this memory。That way。

 if we're dealing with emails for multiple users， we can pretty easily just have different collections of memories for different users。

 we wouldn't want them to be the same， and so here is where we define that we store them separately。



![](img/d107fa768e67d52e0c22404bae03a686_18.png)

Because these are just lane chain tools， we can inspect them and see what attributes they have。

So they should have a name so we can see that manage memory tools's name is called manage memory。



![](img/d107fa768e67d52e0c22404bae03a686_20.png)

They should also probably have a description。

![](img/d107fa768e67d52e0c22404bae03a686_22.png)

So we can see that this is the description of how to use the tool。

 Let's print it out to make it a little bit more legible。



![](img/d107fa768e67d52e0c22404bae03a686_24.png)

Here we can see that it contains instructions for creating， updating。

 or deleting persistent memories。

![](img/d107fa768e67d52e0c22404bae03a686_26.png)

We can also take a look at the arguments to this tool。 we can see that it takes in content。

Then an action， so the action can be create， update， or delete。

And then an ID And so basically what's happening is these memories are managed by IDs and so when we call to this tool。

 we can pass in the ID。Of a memory。The action we want to take on it。

 whether we should update it or create it or delete it。And then the content of that memory as well。

If we look at the search memory tool， we can see that called search memory。



![](img/d107fa768e67d52e0c22404bae03a686_28.png)

The description is pretty simple as just search your long term memories for information relevant to your current context。



![](img/d107fa768e67d52e0c22404bae03a686_30.png)

And the arguments are also pretty simple， it's just to query a limit for the number of memories that we want to return。

 some offset， and then some filter if we want。

![](img/d107fa768e67d52e0c22404bae03a686_32.png)

Let's now go on to define the agent here。 we're going to take the agent system prompt。

 and we're actually going to modify it a little bit because now we need to add in these two extra tools。

So this is slightly modified from the previous lesson。



![](img/d107fa768e67d52e0c22404bae03a686_34.png)

We're still going to have the similar create prompt function。

 which basically creates this message and appends it before the list of messages in the state。



![](img/d107fa768e67d52e0c22404bae03a686_36.png)

![](img/d107fa768e67d52e0c22404bae03a686_37.png)

After that， we can build our agent as normal。We'll import this Create React agent function。



![](img/d107fa768e67d52e0c22404bae03a686_39.png)

We'll create our list of tools， which now contains this manage memory tool and the search memory tool。

And then we'll create our react agent， which we'll now call a response agent and notice that we're also passing in the store to ensure that this is passed to the agent。



![](img/d107fa768e67d52e0c22404bae03a686_41.png)

Let's now test the agent。The first thing we're going to want to do is actually define a config that we're going to pass to the agent with some runtime configuration。

 and it's going to have to have this Langgra user ID。So let's create that first。

 you can change this value， which I'm calling Lance to be anything you want。



![](img/d107fa768e67d52e0c22404bae03a686_43.png)

Let's now call it with a message that has some information that we should probably remember。

 like Jim is my friend。 And notice here I'm passing in the config as a second parameter。



![](img/d107fa768e67d52e0c22404bae03a686_45.png)

Let's take a look at the response， if we print out the list of messages。

 we can see that we have this human message which we pass in， and then we have the sayI message。

 it calls the Manage memory tool with the arguments content Jim is John Doe's friend。



![](img/d107fa768e67d52e0c22404bae03a686_47.png)

Notice that we're not specifying an action because the default is to create and we're not specifying an ID because it will create one by default。



![](img/d107fa768e67d52e0c22404bae03a686_49.png)

We get back a message that we created this memory with this user I。

 and then the final message is that is just recorded this information about Jim。



![](img/d107fa768e67d52e0c22404bae03a686_51.png)

Let's try this with another input。 Let's ask now who is Jim and notice that we're passing in the same config as before。



![](img/d107fa768e67d52e0c22404bae03a686_53.png)

Let's take a look at the list of messages that we get back as a response。Who is Jim。

 This is our user message。 We then get a message from the AI， which calls a tool。

 It calls a search memory tool with a query parameter of gym。



![](img/d107fa768e67d52e0c22404bae03a686_55.png)

![](img/d107fa768e67d52e0c22404bae03a686_56.png)

We get back this list of messages。 In this case， we only have one message， which is。

This namespace memory at this value。This key is the ID。

 and then the content is Jim is John Doe's friend。

![](img/d107fa768e67d52e0c22404bae03a686_58.png)

And then we get back a response from the AI message that summarizes the above interaction。

 so it says based on my memory search， I can see that Jim is John Doe's friend。



![](img/d107fa768e67d52e0c22404bae03a686_60.png)

![](img/d107fa768e67d52e0c22404bae03a686_61.png)

If we want to inspect the stored directly， we can。We can call list namespaces and we can see that this one namespace exists。

And remember， this is the template that we defined above where this is the La graph user ID。

 and we passed in Lance for that value。

![](img/d107fa768e67d52e0c22404bae03a686_63.png)

If we now call search on this namespace， we can see the different items that exist there。

So we can see that we only have one item because we've only remembered one piece of information and it's value。

Has this content， Jim is John Doe's friend。Notice the score here is none。

 that's because we haven't passed in a query parameter。

Let's pass one in and let's see what the score is。If we pass in a query of Jim。

 we can now see that the score is 0。5 something。The score is calculated as cosine similarity using the embedding model that we passed in when we created the store in the first place。

Now is a good time to pause， use this response agent directly。

 try querying it with different things after to see if it remembers。

 and you can also inspect the store itself。

![](img/d107fa768e67d52e0c22404bae03a686_65.png)

Now let's go on creating the rest of the agent。So this should all look very similar to the previous lesson。

 because not much is changing， we've mostly just added these tools to the response agent。

So first we're creating the state， this is the same as before， we're making some imports。

 same as before， we're creating this triage router node， same as before。



![](img/d107fa768e67d52e0c22404bae03a686_67.png)

![](img/d107fa768e67d52e0c22404bae03a686_68.png)

We then create the email agent。 This is the same as before with two changes。 First。

 I've changed this to be response agent。 So before in previous lesson 2， this was called agent。

 I've just updated the variable name。 And so it's changed it here。 Nothing， nothing big。



![](img/d107fa768e67d52e0c22404bae03a686_70.png)

But next， I'm going to change the compile step， so I'm going to pass store equal store when I create the email agent。

 This is giving it access to that long term memory store that our memory tools are going to use。



![](img/d107fa768e67d52e0c22404bae03a686_72.png)

If I display the email agent， I get the same graph as before， so nothing's changed here。



![](img/d107fa768e67d52e0c22404bae03a686_74.png)

I can create this example email input。And then when I call the email agent。

 this is now also going to change slightly。 I'm going to remember to pass in my configuration。

 This contains the La graph user ID that we will use in the memory tools。

We can see that it runs and that it first classifies that it should respond。

 and then it continues down that path。

![](img/d107fa768e67d52e0c22404bae03a686_76.png)

Once it's finished， let's take a look at the list of messages that are in the agent's trajectory so we can see what it does。



![](img/d107fa768e67d52e0c22404bae03a686_78.png)

So the first message there is a human message， this is the input of the email。



![](img/d107fa768e67d52e0c22404bae03a686_80.png)

We then get back an AI message where it's writing an email so it has a tool call with this right email。

 and it's passing in all these arguments and so you can see the content of the email that it writes here。



![](img/d107fa768e67d52e0c22404bae03a686_82.png)

![](img/d107fa768e67d52e0c22404bae03a686_83.png)

We then get back a tool message saying that it sent that email successfully。

 we then call the AIM message again， and we see that it calls the Man memory tool and it creates this memory with this content follow up needed。

 Alice Smith inquired about missing API endpoints。

![](img/d107fa768e67d52e0c22404bae03a686_85.png)

![](img/d107fa768e67d52e0c22404bae03a686_86.png)

We get back a tool message that it created that memory。

 and then we get back the final response from the agent that it's taken two actions。

 It's sent a response to Alice， and it's created a memory entry。



![](img/d107fa768e67d52e0c22404bae03a686_88.png)

Yeah。So this is the agent with the semantic tools in place。



![](img/d107fa768e67d52e0c22404bae03a686_90.png)

Yeah。Let's try out another example that requires some of the memory that was saved as part of this previous email。



![](img/d107fa768e67d52e0c22404bae03a686_92.png)

So let's pass in this new email from Alice Smith as well to same author， and it says，Hi John。

 any update on my previous ask？

![](img/d107fa768e67d52e0c22404bae03a686_94.png)

When we invoke it， we can see that it correctly classifies it as an email that it needs a response to and it continues from there。



![](img/d107fa768e67d52e0c22404bae03a686_96.png)

Let's take a look at the Age trajectory。

![](img/d107fa768e67d52e0c22404bae03a686_98.png)

So we can see that we have the human message with the new email。

 and we can see that it now first calls the search memory tool。With this query。

 Alice Smith previous request asked communication。 So it was trying to figure out what information it has。

 It gets back this memory that it saved before。 We can see its logic。



![](img/d107fa768e67d52e0c22404bae03a686_100.png)

![](img/d107fa768e67d52e0c22404bae03a686_101.png)

![](img/d107fa768e67d52e0c22404bae03a686_102.png)

And then it calls this right email tool and it writes this email。

 and we can see that Anna's responses says thanks for following up regarding the API endpoints documentation。

 So this is remembered from before， even though it's a completely separate email。



![](img/d107fa768e67d52e0c22404bae03a686_104.png)

![](img/d107fa768e67d52e0c22404bae03a686_105.png)

We can see the tool message that it sent a response to Alice， and then we can see the final response。



![](img/d107fa768e67d52e0c22404bae03a686_107.png)

This is an example of how you can see that the memory tools are saving relevant information and then also searching over it in the future。

This is it for this lesson， so now is a great time to pause and spend a few more minutes playing around with different emails。

 trying out different questions and seeing if it can remember different facts。



![](img/d107fa768e67d52e0c22404bae03a686_109.png)

See you in the next lesson。