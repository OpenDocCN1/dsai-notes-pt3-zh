# 【英字可关】吴恩达《利用AutoGen的人工智能智能体设计模式｜AI Agentic Design Patterns with AutoGen》 - P7：7.L6-Planning_and_Stock_Report_Generation.zh_en - GPT中英字幕课程资源 - BV1WJ4m137dk

![](img/b765dd5792364f4d6b17a229726d3de0_0.png)

In this last lesson， you will dive deeper into multiagent group chats and build a custom group chat that collaborates to generate a detailed report in stocks performance over the past month。

 finishing this complex task involves planning which is realized by including a planning agent in the group chat。

 You will also learn how to customize the speaker's transition in the group chat。



![](img/b765dd5792364f4d6b17a229726d3de0_2.png)

![](img/b765dd5792364f4d6b17a229726d3de0_3.png)

![](img/b765dd5792364f4d6b17a229726d3de0_4.png)

Let's dive into the code。

![](img/b765dd5792364f4d6b17a229726d3de0_6.png)

Alright， in this lesson， we're going to learn about one last agent design pattern planning。

 and we're going to also learn a new conversation pattern called Group chatt。Okay。

 let's get started first， let's define our config。To be using G4 turbo。Let's define our task。

So this is a fairly complex task in previous lessons。

 we learn about one conversation pattern called sequential chat that can perform multistep tasks。

 but that requires human to design the concrete steps and the concrete agents involved in each step What if we want to simplify the problem。

 What if we want to simply define agents and make them work together to solve this task without giving them the very specific detailed instructions for every step how can I do that？

In this lesson， let's try a new conversation pattern called Group chat。

 which doesn' require manually designed steps。First。

 let's import allgen and then try to create a few agents that are needed for this task。

 Let's think about what do we need。Initially， we need a user proxy agent that can send other agents about this initial task。

So we' will define a conversible agent named Aime， who will give it a system message about give the task and send instructions to writer to refine the blog post。

And we'll set the code execution configuration to be false and give it a large model configuration and set the human input mode to be always。

 so this agent will always ask for humans input when it is term to speak and if the human skip the input。

 it will send instructions to some writer agent to refine the blog post。

Let's think about what other agents do we need since this is a complex task。

 we probably need a planning agent that can help us decompose the task to simple。

 smaller tasks and send those subtasks to other agents to solve them。

So how about we create a planner agent this is a con agent with name planner we give it some instructions。

 give a task， please determine what information is needed to complete the task please know that an information will all be retrieved using Python code this only suggest information that can be retrieved using Python code after each step is done by others check the progress and instruct the remaining steps if a step fails try to work around You also see I'm adding a field called description what's the difference between the description and system message the system message it is an instruction I'm telling the agent only and only this agent needs to know and for the description I am using that for letting other agent know about the role of this agent and for example a manager could decide when to use this agent based on the description so the description is planner given a task determine。

What information is needed to complete the task after each step is done by others check the progress and instructor the many steps。

 so this is less detailed but more high level and from a different third person point of view we can know what this agent is about。

And we also give it the larger remodel model configuration。

So the planner might suggest some tasks that requires using Python code。

 so we might need some agent thats capable of writing Python code。

So let's define a agent called engineer and we're going to use the default assistant agent from Autogen as a class for this agent。

 this default assistant agent will have a default system message about the detailed instructions for writing code so we don't need to provide additional system message but we will add a description saying that this is an engineer that writes code based on the plan provided by the planner after the engineer writes code we need some agent to execute code so we probably need an executor。

So this is a conversable agent with code execution configuration。

OkaySo we will set the last end messages to be three。

 so this agent will look back in the conversation in history and find first message that contains code in the back of order and execute the code in that message。

 We set the work directionary to be coding and we set use Do to be false。

 Don't forget the task is about writing blog post So we also need a reagent that is in charge of writing So define this writer agent with system message please write blog in markdown format with relevant titles and put content in the markdown code block and we willll also tell it to take feedback from the a and refine the blog。

And we need to provide the description as well。Okay so now we have created these agents。

 you can see that when I'm creating each agent I mainly think about what role this agent needs to play and to start this task what are some of the roles I need to create these agents but I don't need to provide detailed instructions about which agent should do what first I simply put them together in the group chat here I'm creating a group chat with the agents I just created。

 there are five agents of them I provide some initial message empty initial message list and says an next round to be 10。

That's all I need before I make these agents work。 or I need to create a group chat manager。

 as' a special agent in alsogen to manage this group chat。

 This group chat manager also needs a larger model configuration。

So I simply define these agents and put these in the group chat and then I can start the conversation by initiating the chat between the user proxy and the manager because the first message I want it to be from user proxy and the message content will be the task we defined earlier try that。

So after I start the conversation， all these agents will automatically work together and there's no need to specify a Spr speaker order from the developer。

The first message will be sent from the enemy， the user proxy to the chat manager， about the task。

 and the chat manager will broadcast this message to every other agent。

 so every agent in the group chat will see this message and then the chat manager will pick one agent to speak next using its large general model and when deciding who to speak next the chat manager will look at the current conversation history and the roles of each agent and decide which one is the best so we see that the planner is picked as the first agent to speak okay the planner is suggesting a few steps including retrieve the stock data。

 analyze the stock data， research contactual events。

 draft the blog post and in last reiterate on the step one and suggest some actions。



![](img/b765dd5792364f4d6b17a229726d3de0_8.png)

![](img/b765dd5792364f4d6b17a229726d3de0_9.png)

![](img/b765dd5792364f4d6b17a229726d3de0_10.png)

![](img/b765dd5792364f4d6b17a229726d3de0_11.png)

![](img/b765dd5792364f4d6b17a229726d3de0_12.png)

![](img/b765dd5792364f4d6b17a229726d3de0_13.png)

Again， the chat manager now needs to pick the next speaker， it picks engineer。

 so the engineer will follow the suggestion by the planner of the first step and suggest a code to retrieve the sub data。

Next， the executor is picked by the trend manager to execute the code and output the data and now the planner is picked again by the trend manager after the first step is finished。

 so its suggesting the next steps about analyze the stock data， research contact events， etc。

 so it actually suggests one Python code example to get started with the second step so the engineer will complete that Python code。



![](img/b765dd5792364f4d6b17a229726d3de0_15.png)

About this stopnet analysis and the executor is picked by the chat manager to run the code and output the result you can see not only the stock prices output but also the daily change and when first two steps are finished we see that the writer is picked by the chat manager to start drafting the blog post because writer already has good enough information to begin writing so it writes the blog post in the markdown format。



![](img/b765dd5792364f4d6b17a229726d3de0_17.png)

Has an introduction section， analysis of stock price， a stock performance section。

 significant events and their impact and conclusion。



![](img/b765dd5792364f4d6b17a229726d3de0_19.png)

![](img/b765dd5792364f4d6b17a229726d3de0_20.png)

Now the admin is picked by the chat manager so this admin will ask for users feedback if I'm not satisfied with this blog post I can provide my input here I'm going to skip my feedback and let this user proxy agent to suggest some change on behalf of myself。

Now， this user process agent is using large memory model to come up with a reply。

 This right should contain some suggestion about what needs to be improved in this blog post。



![](img/b765dd5792364f4d6b17a229726d3de0_22.png)

![](img/b765dd5792364f4d6b17a229726d3de0_23.png)

So the aime comes up with some refinements。

![](img/b765dd5792364f4d6b17a229726d3de0_25.png)

Including adding videos， detailed analysis， interactive elements。



![](img/b765dd5792364f4d6b17a229726d3de0_27.png)

And so on so after that the writer is supposed to take that feedback and automatically suggest a refine blog post so we see that in during this conversation all the agents are triggered automatically by the group chat manager and following the predefined rows and descriptions usually the rows and description need to be carefully designed to make sure they can follow the right order and okay now we see that the writer has made some revision to the blog post。



![](img/b765dd5792364f4d6b17a229726d3de0_29.png)

It also summarized the enhanced elements in the blog post If we increase the round of in this group chat。

 there can be more conversations and the conversation stops here because we set next round to be 10 So if we review this conversation we will find that the planner does play the role of suggesting an initial plan and after some step finished it will review the progress and suggest followup steps but not all the steps are followed exactly after the first two steps。

 I think the writer skipped the third step and started writing the blog post this is downside of using the library model to decide to speak order always。

 but there are a few ways you could add more control to the conversation For example。

 you could set constraints about the speaker's order Ill show you how to do that first let's repeat the same definition of agents。



![](img/b765dd5792364f4d6b17a229726d3de0_31.png)

So these are the same agents I used。define them again。

 and I will demonstrate how to add some constraints in the speak order。

So in this example I create a group chat with additional constraints。

 this is a dictionary calledlo or disallouded speaker transitions。For each agent， you could specify。

Which agent is allowed to speak after this particular agent。For example。

 we restrict the speaker after engineer to be either user a proxy or executor。

And we restrict the speaker after the executor to be either either proxy or engineer or planner。

So after we impose this constraint， we are not supposed to see the writer to follow up executory agent immediately。

 so that gives the planner a chance to review the plan before the writer starts writing the blog post you could either specify allowed or dislowed speaker transitions in this case we are setting only allowed transitions。

I think of that。So， after defining that。We're supposed to see a speak order that conforms better with。



![](img/b765dd5792364f4d6b17a229726d3de0_33.png)

Our desire。The first few steps are the same。 But now after the excor finish the second step。

 we're supposed to see。The planner take over， it reviews the previous steps and suggest the next steps。



![](img/b765dd5792364f4d6b17a229726d3de0_35.png)

So this fixedes the problem I mentioned earlier。

![](img/b765dd5792364f4d6b17a229726d3de0_37.png)

You see that although we added some constraints。The， the overall task completion is still nonlinear。

 so it still keeps the flexibility of having a some agent back and forth and chimeming when they they need to。

 So this still has more flexibility than the sequential chat。



![](img/b765dd5792364f4d6b17a229726d3de0_39.png)

And this。Way of specify on the speaker transitions can simulate the finance state machine transition in the group chat。

 so its advanced functionality to allow developers to add more control。

 It could also add some natural language instructions in the descriptions of the agent so that you not only specify the constraint。

 but also has more details about when to translate to what which agent。



![](img/b765dd5792364f4d6b17a229726d3de0_41.png)

![](img/b765dd5792364f4d6b17a229726d3de0_42.png)

And in addition， you could also define a precise transition order using programming language。



![](img/b765dd5792364f4d6b17a229726d3de0_44.png)

I will not cover that in this lesson， but you can find that information from Algen's website。

To summarize， groupchat provides a more dynamic way for multiple agents to solve a task together and without human developers to design very detailed plan for execution。

 you could also add some planner agent for helping with making plans and task decompositionation。

 In general， there can be multiple different ways for doing task decomposition and planning and where we only showed one particular example。

 That's all the lessons we covered about the basic introduction to autogen。

 There are many other advanced functionalities in autogen such as teaching agents to improve over time。

 having multimodality， having vision capability to understand images。

 using open assistant as a backend for agents and so on and so forth。

 We also have agentbased evaluation tools and benchmarking tools and other new interesting research。

 for example， helping users design。

![](img/b765dd5792364f4d6b17a229726d3de0_46.png)

aggents for a particular task please find those advanced new features or ongoing research from our website and read the blog posts We hope you enjoyed the lessons so far and youll explore many more interesting use cases with your own experience。



![](img/b765dd5792364f4d6b17a229726d3de0_48.png)