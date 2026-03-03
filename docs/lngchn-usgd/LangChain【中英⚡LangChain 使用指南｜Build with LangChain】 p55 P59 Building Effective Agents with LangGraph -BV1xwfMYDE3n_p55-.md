# LangChain【中英⚡LangChain 使用指南｜Build with LangChain】 p55 P59 Building Effective Agents with LangGraph -BV1xwfMYDE3n_p55-

Hi， this is Lan from Langchain。 Anthropic recently about this blog post called Building effective agents。

Where they define what an agent is and also explain what a workflow is。

 So I'm going to build every workflow and agent that they talk about in this blog post from scratch and explain what they all are。

 how to build them and why each one can be very useful。



![](img/6160fd08f325f189c794e8d28c01b46c_1.png)

So here's a simple way to think about their definition of a workflow versus an agent。

Think about a workflow as some kind of scaffolding of predefined code paths around LLM calls。 Now。

 this has been popular for years， and it makes a lot of sense in many cases to take LLM calls and embed them in some fixed set of code paths。

Now， sometimes you can actually have that LM decide what path to take in a workflow。

 and that's kind of this middle category that I drew here。And we'll talk about all these in detail。

 But that's kind of the intuition。 Work flows are kind of like some scaffolding of predefined code paths。

And you can embed LM calls within it。Now， agents remove the scaffolding。

So you're basically let an LLM direct its own actions Now in this particular case。

 actions are typically tool calls。And an LM will receive the feedback from those tool calls and decide what to do next。

 I do want to call out that you can certainly have LLMs that perform tool calls within workflows。

But the difference is that workflows have some scaffolding around them。

 whereas an agent is unbounded。 So an agent just directly receives the output of environmental feedback from tool calls。

 decides to do next without the kind of reasoning scaffolding around it。

 So that's really the differentiation。 Now， just before it gets started here。

 It's important to call out why frameworks。 Okay， so implementing these patterns doesn't require framework。

 right， sometimes this can be done in a few lines of code。 I completely understand that。

 So you might say， okay， why are you talking about this。 Why are you trying to promote frameworks。

 Here's kind of my take on it。 Langra really means aims to minimize the overhead of implement these patterns。

 Okay， it doesn't abstract prompts。

![](img/6160fd08f325f189c794e8d28c01b46c_3.png)

It doesn't abstract architecture。What's really happening with Langgrath is it's supporting infrastructure underneath any workflower agent。

 That's the key point。And really， it's three things。 One is persistence。 This gives you memory。

 This gives you humanme the loops， the ability to pause， for example。

 while an agent is processing and approve a tool call pause interview what the agent is doing。

 This is extremely useful in many cases， streaming。 So， of course， L M Apis of stream tokens。

 we all know that。 But when you build these workflows or agents， Sometimes you want to stream。

 for example， what certain steps， output you might want to stream the outputs of tool calls。

 you often want more flexibility over streaming than just what the L M calls produce。

 And so Langgraff give you a lot of control over what your outputting from your workflow or agent。

 This is very useful when actually building these and putting them in production。

 And the third is deployment。 So testing， debugging and deploying。😊。

That is a big benefit of using Landgraft。 It is extremely easy to go from any workflow or H to implement to a deployment。

 Landgraft doesn't abstract prompts。And it does not abstract architecture。

 It's really giving you low level infrastructure that sits underneath any of these workflows or agents。

 Now we've laid the foundations。 Let's talk through the various patterns laid out in the blog post。

 First， starting with the augmented Lms can be augmented with many different things。



![](img/6160fd08f325f189c794e8d28c01b46c_5.png)

1 is， for example， memory。 We talked a little bit about that。

 That's one of the things that a framework such as Landgra can provide。 Also。

 Lms can interact with tools。 And this is the foundation for building many workflows and agents。

 So let's build this from scratch。 So here's my notebook。 I've just Pip installed a few packages。

 set mythrop API key， createate my L M。

![](img/6160fd08f325f189c794e8d28c01b46c_7.png)

![](img/6160fd08f325f189c794e8d28c01b46c_8.png)

![](img/6160fd08f325f189c794e8d28c01b46c_9.png)

Now， let's show the augmentation for structured output。 I can take a schema in this case。

 a idantic model。

![](img/6160fd08f325f189c794e8d28c01b46c_11.png)

I can bind it to my LLM in this particular case I'm using Lang chain。

 and I'm going to use the width structured output method and Lang chain to do this， but again。

 Lnggra does not require you to use Lang chain。 You can use the raw model API is completely fine。



![](img/6160fd08f325f189c794e8d28c01b46c_13.png)

I run that and the output adheres to my schema which I passed here， so that's great。



![](img/6160fd08f325f189c794e8d28c01b46c_15.png)

Now let's do the same with tool calling。 I'm going to take a tool。

 I'm going to basically define dysfunction multiply as a tool that the LLM has access to。

 I can use the bind tools method in line chain to bind it to my LLM。 Now I have an LM with tools。

 I invoke it with an input that's likely to elicit the tool call。And I get the output。



![](img/6160fd08f325f189c794e8d28c01b46c_17.png)

Great， you can see a tool call is produced。 It takes this input and creates the arguments necessary to actually run dysfunction。

 That's it。 Remember when Lms are creating tool calls。

 they're really giving you payloads how you run that tool。 You could then run the tool。

 pass the output of the tool back to LM and really doing that loop。

 gives you an agent like we saw before。 We've talked about augmented LM as a core building block。😊。



![](img/6160fd08f325f189c794e8d28c01b46c_19.png)

Now suck by some of the workflow of patterns covered in the blog post。 starting with prompt chaining。

 Here's the intuition。 Each L M call processes the output of the previous one。

 When you want to do this。 When you would test， you can decompose into a few different L M call。

 So in this little example they show there's an input， call 1。

 you can have some gating on the output of call 1 output goes the call 2。

 That output goes the call 3。

![](img/6160fd08f325f189c794e8d28c01b46c_21.png)

![](img/6160fd08f325f189c794e8d28c01b46c_22.png)

So let's basically build this from scratch and let's do an example where we build a chain that takes a topic from a user。



![](img/6160fd08f325f189c794e8d28c01b46c_24.png)

The El makes a joke。 We check to make sure the joke has a punch line。

 and we improve it twice with two subsequent L call。 Now， when I'm working in Lagra。

 all I need to do is basically define a container for everything that I want to modify over my workflow。

 So in this particular case， I'm just going to create a di。

 and it's going topic that's we'll get from the user。 The joke of the output of that first call。

 improve joke of the output of the second call。 Fi joke of the output of the final call。 Now。

 when laying out workflows， I actually like to draw them out anyway。

 So this is kind of cool that the blog puts has all these laid out。

 And we draw these out think about， for example， each of these calls or steps is just a different function。

 So for this particular workflow， I'm going to create a function， generate joke， improve joke。

 Polish joke。😊。

![](img/6160fd08f325f189c794e8d28c01b46c_26.png)

![](img/6160fd08f325f189c794e8d28c01b46c_27.png)

![](img/6160fd08f325f189c794e8d28c01b46c_28.png)

![](img/6160fd08f325f189c794e8d28c01b46c_29.png)

![](img/6160fd08f325f189c794e8d28c01b46c_30.png)

![](img/6160fd08f325f189c794e8d28c01b46c_31.png)

And those are all going to be just simple LLM calls。



![](img/6160fd08f325f189c794e8d28c01b46c_33.png)

Now， what's interesting is with Lagra， this container or state that I define is passing into every one of these steps。

 and I can extract whatever I want from it。 In this case。

 I go state topic to get the topic that written to state by the user。

And I can write things back to state both by basically returning this joke key。The output of。

 my allm call。Impprove joke。 I populate improved joke。Final joke。 I populate final joke。

 So what's happening is Ed you G， these steps are making L M calls。

And I'm populating my state or this container in the workflow with the output of each LM call。

 That's really all's going on。 Now， notice in this workflow， there's a gate here。 So in this case。

 I'm just going to create some gating logic。 So what's interesting is I can take in the state and I can just check。

 hey， does a joke have a question mark or an exclamation point。 That's just some arbitrary criteria。

 And what I can do is I can pass。😊。

![](img/6160fd08f325f189c794e8d28c01b46c_35.png)

Anything I want here， Just two strings pass or fail。 Now。

 this can be used as conditional edge or gate in langra。

 So now I have a container that has everything I want to modify my workflow。

 I've defined each step in my workflow as an independent function。

 I've defined a gate that's going to serve as that check on the output of the joke。

 And now I lay this out in Lagraff as a simple workflow。

 So on need to do here is just take in my state， initialize the workflow。

 Add those three steps to it。 We added。

![](img/6160fd08f325f189c794e8d28c01b46c_37.png)

![](img/6160fd08f325f189c794e8d28c01b46c_38.png)

![](img/6160fd08f325f189c794e8d28c01b46c_39.png)

![](img/6160fd08f325f189c794e8d28c01b46c_40.png)

Generate Jo and prove joke， Po joke。And this is where I defined find the connectivity of my graph or workflow。

 So I'm going to start。 I'm going to go to generate Jo first。

 and you can see then I want to check the output of my first call to see whether or not it has a punch line。

 So I add a conditional edge that connects generaterate Jo。And based on the output of this function。

If it's pass， I go to improve joke。 That's math node。 If it's fail， I just end。

 Then I create the edges from improved to polishlish， Polish to end。 compile that as a workflow。

 And there we go。 So that's the exact same workflow that they drew out in the blog post applied to joke generation。

 Now， once I have this workflow， I can very simply just run chain dot invoke。

 That's a very simple way to invoke any chain workflow or whatever you have in Lagra。

 I pass in a topic from the user。 we can see the L O M's create an initial joke。

 They improved it and clo creates final joke。 So this is a very simple example of a chain great。

 So we've covered the augment L M。 We've covered basic pro chaining。

 Now let's get into some more interesting in complex workflows like parallelization。 Now。

 let's talk about parallelization。😊。

![](img/6160fd08f325f189c794e8d28c01b46c_42.png)

![](img/6160fd08f325f189c794e8d28c01b46c_43.png)

![](img/6160fd08f325f189c794e8d28c01b46c_44.png)

Do this when you， for example， have multiple perspectives that you want for a single task。

 So I've done this quite a bit with things like multi query rag。 If I have a question。

 I want to fan it out into like three or four different sub questions。

Or when independent tasks can be performed with different prompts or different LMs。

 So lots of cases where you want just paralyzed tasks in workflows。 So let's just build this。

 Let's take a topic， createate a joke， story and poem all in parallel。

 So in the same way I do before。 I create my state。 again。

 this is just a container for everything I'm going to modify my workflow。 In this case。

 all have a topic from a user， and I'll have the joke。 the story， the poem。



![](img/6160fd08f325f189c794e8d28c01b46c_46.png)

![](img/6160fd08f325f189c794e8d28c01b46c_47.png)

![](img/6160fd08f325f189c794e8d28c01b46c_48.png)