# LangChain《使用 LangGraph 构建具备长期记忆的自主智能体Long-Term Agentic Memory with LangGraph》 - P6：6.email-assistant-with-semantic-+-episodic-+-procedural-memory.zh_en - GPT中英字幕课程资源 - BV16oQhYdEjF

![](img/edb9094f067d848ec283d9d6ebbff2da_0.png)

In the last lesson， we added an episodic memory in the form of few shot examples。



![](img/edb9094f067d848ec283d9d6ebbff2da_2.png)

In this lesson， we're going to add in the third and final type of memory， procedural memory。



![](img/edb9094f067d848ec283d9d6ebbff2da_4.png)

This will be in the form of the system props that exist in the main agent and also in the triage agent。



![](img/edb9094f067d848ec283d9d6ebbff2da_6.png)

So as a reminder， procedural memories are instructions about how to do things。



![](img/edb9094f067d848ec283d9d6ebbff2da_8.png)

And the representation that that takes in agents is typically in the form of prompt instructions。

 We've been using hard coded values for these throughout the lesson， so far。In this lesson。

 we're going to make it possible to update those prompts automatically。



![](img/edb9094f067d848ec283d9d6ebbff2da_10.png)

Let's dive in。

![](img/edb9094f067d848ec283d9d6ebbff2da_12.png)

The start should look pretty similar to before。 We're going to load some environment variables。

 We're going to define our profile， and we're going to define our prompt instructions here。

 This is what we're going to be updating over time。

 So these are specific instructions for when to ignore when to notify when to respond and how the overall agent should behave。

And so these are hard coded here and have been hard coded here。

 And we're still going to run this cell。To keep them here。

But we're going to use them in a slightly different way， and we'll dive into that later。



![](img/edb9094f067d848ec283d9d6ebbff2da_14.png)

This email is an example email here。 we're going to load the in memory store。

 the long term memory store， which we're going to use for everything。

 We are going to define our helpers for the triage step。 And now we get down here。

 And here we can see these are where our updated memories for the procedural steps are going to go。

 And so this is our， this is our template。 This is the same as before。

 But I'm just pointing out that this is where they are going to go。



![](img/edb9094f067d848ec283d9d6ebbff2da_16.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_17.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_18.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_19.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_20.png)

We're going to define a bunch of stuff for this triage step。 We've got our LLM router。

 We've got our user prompts。 We're defining the state of the graph。 We're defining some things。

 And then this is our triage router node。 and this is what we're eventually going to modify。



![](img/edb9094f067d848ec283d9d6ebbff2da_22.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_23.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_24.png)

So right now you can see that we're passing in the prompt instructions here。

 what we're going to do is we are going to modify it so that we are retrieving these from the long term memory store and then passing them in。

Why are we doing this？We're going to do this so that we can update them from outside the agent。

 And then that way， if we update them， they're automatically pulled in to future runs。



![](img/edb9094f067d848ec283d9d6ebbff2da_26.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_27.png)

Okay， so how are we going to modify this？First， let's get our Lagra user I。

 and we are going to use this as the name space for the procedural memories。

 So we're getting our La graphft user I from the config， and we're creating this namespace。

 which is a tuple。

![](img/edb9094f067d848ec283d9d6ebbff2da_29.png)

So make sure that you've got this comma here。

![](img/edb9094f067d848ec283d9d6ebbff2da_31.png)

We're now going to try to fetch from the store instructions for when to ignore emails in the triage step。

 And so we're going to get from the store with this given namespace， this key triage， ignore。



![](img/edb9094f067d848ec283d9d6ebbff2da_33.png)

Now， this may not always exist in the store。 And so what we're going to do is we're going to check to see if it exists。

 If it does， we're going to use the value there。 If it doesn't， we're going to add a default。

 This will make sure that when we run this agent with a new user I D。

 even if we haven't already set up the store， it will add the default there。



![](img/edb9094f067d848ec283d9d6ebbff2da_35.png)

So here we have the logic。 If the result is none。 So if nothing exists in the store for these ignore triage instructions。

 we are going to put something there。 We're going to put something in that namespace with that key。

 and it's going to be a dictionary with one key prompt。

 and the values are going to be those default prompt instructions that we had for ignoregnore。

And then our， we're going to set ignore prompt， which we're going to use later on to that default value。

 If the result does exist， we're going to get the value from prompt。

 and that's what we're going to use。 And so then we're going to pass it in。Down here。

 So let's update this to be ignore prompt。

![](img/edb9094f067d848ec283d9d6ebbff2da_37.png)

We now want to do the same for notify。 so we are going to now use the same namespace。

 but with a different key triage notify， and we're going to get notify prompt。 Similarly。

 we're going to update the formatting down below to use this value。



![](img/edb9094f067d848ec283d9d6ebbff2da_39.png)

And finally， we're going to do the same for the respond prompt。

 So now it's triage Re is the key and respond prompt is the new variable we get。

 and we're going to insert that here。So we've just updated our agent to use prompts that are stored in long term memory。

 Note that there's nothing that updates them yet。 We're going to go over that later on。

 But this just updated。

![](img/edb9094f067d848ec283d9d6ebbff2da_41.png)

This triage router to use。

![](img/edb9094f067d848ec283d9d6ebbff2da_43.png)

Stuff in long term memory， and this is step number one。



![](img/edb9094f067d848ec283d9d6ebbff2da_45.png)

After that， we're going to go on to the rest of the agent。 So we're going to import the tool。

 We're going to create the three different tools we have。

 We are going to import the memory tools and use those。

 We are going to have the system message for the agent。 And now we get down to create prompt。



![](img/edb9094f067d848ec283d9d6ebbff2da_47.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_48.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_49.png)

So create prompt is where we are also going to update。 So right now。

 we're passing in the prompt instructions with agent instructions。

 and we're going to do the same thing as above。 We're going to update it。

 So it looks for these in the long term memory store first。



![](img/edb9094f067d848ec283d9d6ebbff2da_51.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_52.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_53.png)

Allright， so now we've modified it in a few ways。 We've passed in the config and the store。

 We're going to use the config to get the La graph user I D。

 and that's going to create the name space that we look in。

 The key that we're going to use is agent instructions。

 and we're going to do similar logic as before， we're going to first try to get this result from the store。

 If it does not exist， we're going to put a default one in there using prompt instructions as the default。

 If it does， we're actually just going to use the value that's there。

 And then what we're going to do is we're going to update the system message。

 And rather than using the prompt instructions here。😊。

We are going to use the prompt value that we get from above。



![](img/edb9094f067d848ec283d9d6ebbff2da_55.png)

With that now done， we can create our main agent so we can import， create reactact agent。

 We define a bunch of tools， and then we create the email agent。So now this agent is all set up。

It's pulling its instructions from long term memory， rather than from those hard coded values。

 Why does this matter， This matters， Because now we can update those values outside the agent and automatically update the agent's instructions。



![](img/edb9094f067d848ec283d9d6ebbff2da_57.png)

So now let's see how to do that。Let's work with this example， email。



![](img/edb9094f067d848ec283d9d6ebbff2da_59.png)

Hi， John， urgent issue。 Your service is down。

![](img/edb9094f067d848ec283d9d6ebbff2da_61.png)

Let's define the config that we're going to use。 In this case， it has the La graph user I of Lance。



![](img/edb9094f067d848ec283d9d6ebbff2da_63.png)

Let's now run this email agent over this email and we can see that we get a response。



![](img/edb9094f067d848ec283d9d6ebbff2da_65.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_66.png)

If we look through the messages， we can see that we have a human message。

 then the AI message that is calling the right email tool and it's writing this email。

 and then the response from the tool message saying that we sent this email and then a final response from the agent。



![](img/edb9094f067d848ec283d9d6ebbff2da_68.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_69.png)

Let's take a look at the existing long term memory for these instructions。



![](img/edb9094f067d848ec283d9d6ebbff2da_71.png)

If we look at the lance namespace with the key agent instructions。

 we can see these default instructions。 These are the same as we in the prompt instructions at the top of the notebook。



![](img/edb9094f067d848ec283d9d6ebbff2da_73.png)

Let's look and we should see that the triage respond is also populated。



![](img/edb9094f067d848ec283d9d6ebbff2da_75.png)

As is triage nor。

![](img/edb9094f067d848ec283d9d6ebbff2da_77.png)

And as is triage， notify。

![](img/edb9094f067d848ec283d9d6ebbff2da_79.png)

If we wanted to， we could update these instructions manually and pass in new instructions。

But that's kind of a manual update。 That's not really memory in terms of how we think about it in terms of agents with agents。

 we think about an LLM updating these based on some user feedback。

So that's exactly what we're going to do。So we're going to import from Lngmem。

 this function called create multi prompt Opr。 As the name suggests。

 this is going to create an optimizer that optimizes multiple prompts。

 The reason we want to optimize multiple prompts is that in this assistant。

 there are actually four different prompt instructions that we have。

 and we might want to update any number of them。But we don't get feedback for each instruction。

 Rather， we get feedback for the whole overall agent。

So we're going to take this overall feedback and first determine which prompts， if any。

 should be updated based on this feedback and then update them。



![](img/edb9094f067d848ec283d9d6ebbff2da_81.png)

First， we need a list of the conversations that we're going to use to update the prompts。For this。

 we're going to take the response messages。 So this is the trajectory that we have above。

And then we're going to add in some feedback。 This can be in a few different formats。

 but the simplest format is just a string。 So here we're going to take in this feedback。

 Always sign your emails， John Doe。We now need to define the prompts that we want to potentially update。



![](img/edb9094f067d848ec283d9d6ebbff2da_83.png)

Each entry in this list should have four keys。 First is the name of the prompt。

 Next is the value of the prompt。Next is update instructions。

 These are instructions for how you should update the prompt。 And then finally。

 we have the when to update key。 These are instructions for when you should update the prompt。

 So under the hood， what's going to happen is we're first going to use the when to update value to determine which prompts。

 if any， to update。 If we determine that it's worth updating we're then going to use the update instructions and apply that to the original prompt to get a new updated prompt。



![](img/edb9094f067d848ec283d9d6ebbff2da_85.png)

Here， weve filled these in for the four prompts that we want to potentially update。

 So we have the main agent prompt， which we' are going to get the most current values from this agent instructions key。



![](img/edb9094f067d848ec283d9d6ebbff2da_87.png)

The update instructions are just going to be keep the instructions short into the point。

 and we're actually going to use that for all of them。



![](img/edb9094f067d848ec283d9d6ebbff2da_89.png)

And then when to update updates prompt whenever there is feedback on how the agent should write emails or schedule events。



![](img/edb9094f067d848ec283d9d6ebbff2da_91.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_92.png)

What about triage ignore？Similarly， we're going to name it that。

 we're going to fetch the most recent value from long term memory， update instructions are the same。

 and then update this prompt whenever there is feedback on which emails should be ignored。



![](img/edb9094f067d848ec283d9d6ebbff2da_94.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_95.png)

Triage Notify and triage respond are pretty similar。

 except rather than updating it when there is information about when the emails should be ignored。

 we're going to update it when there's information about when the user should be notified or responded。



![](img/edb9094f067d848ec283d9d6ebbff2da_97.png)

After we do this， we're going to create the multi prompt optimizer。

 We're going to use anthropics Cla 3 sonnet model to optimize the prompt。

 We've found that it's currently the best for this type of prompt optimization。

Kind equals prompt memory is the algorithm that we're going to use to update the prompt。

 This is the simplest one。 And you should look at the API reference of Lngm for more complicated examples。



![](img/edb9094f067d848ec283d9d6ebbff2da_99.png)

This optimizer itself is a graph。So we're going to invoke it by passing in these trajectories and then these prompts。

 and we're going to get back this updated variable。



![](img/edb9094f067d848ec283d9d6ebbff2da_101.png)

Let's take a look at what this returns。We can see that it returns a list of prompts。

These have all the same keys as before， so the name prompt update instructions and went to update。

Now some of these prompts may be different than before。

 and we can actually see that here the first main agent prompt， its prompt is now different。

When sending emails， always sign them as John Doe。 This is the feedback that we passed in。



![](img/edb9094f067d848ec283d9d6ebbff2da_103.png)

Once we have these updated prompts， we can loop through them and update the long term memory if appropriate。

So here you can see that we're comparing the updated prompt to the old prompt and we're comparing the prompt values。

If they're not the same， we're going to update the store with their instructions here。

 I've only added logic to handle what would have happened if the name of the prompt that's been updated as main agent。

 But remember， there's three other prompts that could potentially be updated。 They shouldn't。

 So they shouldn't throw an error。 but for completeness， you'll probably want to implement all three。



![](img/edb9094f067d848ec283d9d6ebbff2da_105.png)

Conditions。And we can see that we print out updated main agent prompt as we went along。

 and we didn't raise any value， so no other prompts got updated。



![](img/edb9094f067d848ec283d9d6ebbff2da_107.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_108.png)

If we now check the long term memory for these agent instructions。

 we can see that it now has this sentence when sending emails， always sign them as John Doe。



![](img/edb9094f067d848ec283d9d6ebbff2da_110.png)

We can now rerun the email agent and see what happens。



![](img/edb9094f067d848ec283d9d6ebbff2da_112.png)

If we take a look at the messages。We can see that when we write the email， we now sign it John Doe。

 so it's remembering and using these instructions。

![](img/edb9094f067d848ec283d9d6ebbff2da_114.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_115.png)

Let's look at another example。

![](img/edb9094f067d848ec283d9d6ebbff2da_117.png)

We now have this email and we invoke the email agent and it responds to this email above。

What if we didn't want it to respond to this？

![](img/edb9094f067d848ec283d9d6ebbff2da_119.png)

We could then create a list of conversations with the response messages as the conversation。

 and we could give the feedback， ignore any emails from Alice Jones。



![](img/edb9094f067d848ec283d9d6ebbff2da_121.png)

We then define the list of prompts。And we're running this again because the old list of prompts that we defined before has the outdated instructions for the main agent。

 And so we're just running it again to get the most updated instructions for the agent at this point in time。



![](img/edb9094f067d848ec283d9d6ebbff2da_123.png)

After that， we can invoke this optimizer agent with the conversations we have above and the prompts。



![](img/edb9094f067d848ec283d9d6ebbff2da_125.png)

We can now run this code snippet to update the prompts in long term memory。

 Notice that we've added this new section， which handles how to deal with the fact。

 If the updated name of the prompt that we're updating is the ignore step。



![](img/edb9094f067d848ec283d9d6ebbff2da_127.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_128.png)

And here we can see that this was the only prompt of the four that we decided to update。



![](img/edb9094f067d848ec283d9d6ebbff2da_130.png)

![](img/edb9094f067d848ec283d9d6ebbff2da_131.png)

And if we rerun the email agent from here， we can see that it actually now ignores it because it's using the same email from Alice Jones。

 and it now has the instructions to ignore emails from there。



![](img/edb9094f067d848ec283d9d6ebbff2da_133.png)

To see what exactly these instructions are， we can look into the long term memory itself in the triage ignore key。

 and we can see that this is now updated to contain ignore all emails from Alice Jones。

This is the end of this lesson。This puts together all the types of memory into this email agent。

Now is a good time to try this out， try passing in other conversations with other feedback and see which parts of memory get updated and what they get updated to。



![](img/edb9094f067d848ec283d9d6ebbff2da_135.png)