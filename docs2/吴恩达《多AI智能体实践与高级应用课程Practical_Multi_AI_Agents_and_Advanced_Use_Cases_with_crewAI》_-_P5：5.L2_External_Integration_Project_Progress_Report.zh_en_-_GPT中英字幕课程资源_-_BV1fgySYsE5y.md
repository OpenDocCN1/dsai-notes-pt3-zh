# 吴恩达《多AI智能体实践与高级应用课程Practical Multi AI Agents and Advanced Use Cases with crewAI》 - P5：5.L2 External Integration Project Progress Report.zh_en - GPT中英字幕课程资源 - BV1fgySYsE5y

Now let's talk about our second use case where we are going to be building a progress report for a project。

 so in comparison with for last news case， this is what happens on a day to day basis If you have worked in a software company in any capacity you probably are familiar with the fact that every now and then you need to write a report on how is the project going People going to have some clarity around progress and what is being done。

So for this crew， we're going to be automating data as a process that will take emotions out of the equation。

 making sure that you can see a project for what it is。For this use case。

 we're going to be using two agents， the data collector and the project analyst in these two agents are going to be doing a series of three tasks。



![](img/e9002ddb7524fa39f637e6c63d9af37a_1.png)

Understanding a project， then analyzing its progress and compiling a report。In order to do this。

 these agents need to be able to talk with an external system in this case it's going to be a trello board。

 so this is a great example of how this integrations with external systems can actually unlock new use cases so this is something that would not be possible if we had not integrated with that external to and we're going to show how easy that is。

😊，Once that our agents are able to do it， we're going to have a markdown report。

 This markdown is going to include things like a sprint overview， a task summary。

 identifying issues and blockers and also progress and delays but it's not going stop there。

 we're going to talk about a team performance review and also action items and recommendations including anything else that might be relevant for this project。

 So this is going to be a great use case for the day to day of any company out there。

 and this is a use case that we are also seeing people do in order to get updates on project without having people going down and tracking every single ticket and comment in every single one of them。

 Now let's dive into the code and but it ourselves。😊。



![](img/e9002ddb7524fa39f637e6c63d9af37a_3.png)

So the first thing that we will do is importing the libraries that we're going to use。

 We're also going to load our environment variables to make sure that everything is set up。

 we're using the same libraries then our previous lesson the Json the YaO and our three major query AI classes so let's go ahead and do that After that we're going to load our open AI model and for this one we're also going to be using GPT40 minii and I love to use 40 minii because it's search a small model in so cheap but it's still so powerful but let's see what that's going to look like onces that we actually run the crew。

So let's load our agents and task Yal。 This code is the same snippet that we use on our previous lesson。

 pretty straightforward， load the Yal files and assigning them into an agent's config and a task config variable。

 So once that we're done with this， we have everything that we need to build our agents。

 but now it's where we're going to build our first ever external integration tool for our agents。

 Let's dive into that。For this crew， we're going to be integrating with Tello and we're going to use two toolss for that。



![](img/e9002ddb7524fa39f637e6c63d9af37a_5.png)

If we look at those two， they're fairly easy to put together。

 you can import from CAI toolss package the base2 class。

 and you can create any class that you like as long as it inhers from that。

All your class are going to have a name in a description and also an underscore run method。

 This method is where the integration will leave。 So all your code is going to be inside this single method。

 And as long as you return an object or a string， you should be good to go。 Now。

 let's look at this two tools real quick。 The first one is a board data thatcher tool。

 And what it does is fetch cards， data， comments and activities from a single board。

 This is gonna to be a public board that I'm going to show to you in a second。

 But in here you can see that we' are basically calling an API to get information around this board in a few different fes that we care about。

 Then once that began the response。 we return this response to our agent。😊。



![](img/e9002ddb7524fa39f637e6c63d9af37a_7.png)

You can see that we also added a fileback in here， just in case we have timeouts or anything。

 we are hard coding a response right in there。

![](img/e9002ddb7524fa39f637e6c63d9af37a_9.png)

The second tool is a card data Thatcher tool。 and this is also pretty straightforward。

 It basically f information around a specific card。 And you can see that again。

 all our code leave inside the underscore run function。

 And this is where if you're integrating with any external tool。 you can do an API call。

 you can do a database connection， you can do a GRPC call whatever you need。

 this is regular Python code that you can write down in your agent is gonna to be able to choose it to execute it or not as it's trying to accomplish a task。

 So this is how you can build any integration。 both internal ones and external ones。

 and it's pretty straightforward。 Now， let's put this two tools to the task and see how our agents are going to use them。

 It's pretty fun to see how these agents actually use this tools in order to accomplish an automation that we build。

😊。

![](img/e9002ddb7524fa39f637e6c63d9af37a_11.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_12.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_13.png)

Before we kick off our crew， let's check this board。



![](img/e9002ddb7524fa39f637e6c63d9af37a_15.png)

This is what ourboard looks like you can see that we have a few different tasks one of them has a common and is actually late。

 it has passed its due date， so with this information we know a little bit about the project but this could be hundreds of tickets and would be pretty hard for us to keep a reasonable track of it。



![](img/e9002ddb7524fa39f637e6c63d9af37a_17.png)

Now let's put together our crew， agents and tasks。

![](img/e9002ddb7524fa39f637e6c63d9af37a_19.png)

This is very similar to what we did in the previous lesson where we are referring to the configuration coming out of the EMO file the big difference here is that this agent now has a set of tools and were giving it two tools。

 a tool that allows it to get data from a board in Tello and Tello is our project management tool and another tool that allows it to get data from a specific card in Tello so whatever tasks we have in our project management tool。

 this agent is going to be able to read them in understanding their comments。

 their context and every data point associated with that。

With query AI you can set tools both on agents and tasks if you set them on agents。

 the agents are going to be able to use those tools to perform any task that it gets assigned to。

 but if you assign these tools on a task， whenever an agent' is going to do it。

 it's going to only be able to use the tools there are in the task。

Now before we actually run this screw， let's look at what are these agents and tasks in the YaL file so in here you can see that we have two agents。

 a data collection agent in an analysis agent and the two of them have a role a goal in a backstory you can also see that the two of them don't allow delegation in our sector run on a verbos mode that will make sure that these agents don't delegate work to each other so that they run on a streamlined way and that we can see everything about how they are trying to accomplish their tasks。

Let's take a look at the task itself。We have three tasks， we have a data collection tasks。

 a data analysis task， and a report generation task。

 and for any of these tasks we have a description and an expected output。

Feel free to play around with the descriptions and expected outputs after you run this notebook。

 it's pretty fun for you to change it around and see how that impacts the crew output for now。

 let's keep what it is and let's execute this crew。😊。



![](img/e9002ddb7524fa39f637e6c63d9af37a_21.png)

This crew takes no input， so kicking it off it's as simple as just calling the kickoff matter。

 Once that we do， we're going to be able to tag along its execution and see how these agents do the work that we expect them to do。



![](img/e9002ddb7524fa39f637e6c63d9af37a_23.png)

So in here we can see our first agent， the data collection specialist creating an initial understanding of the project。

 first thing that decides to do it's called OrTello board data Thatcher。

 one of our custom external integration tools and you can see that we get back this whole JSN object with every single information there is to know about our project。



![](img/e9002ddb7524fa39f637e6c63d9af37a_25.png)

Now that already understand the Tello board it would analyze individual information about certain cards and you can see that it's using or second to the Tello card data Thatcher keep in mind that Trello is management project tool so it allows us to track progress of our project so by looking at this board and cards these agents are going to get a pretty deep understanding on what is happening with this project let's take along the execution further down the road。



![](img/e9002ddb7524fa39f637e6c63d9af37a_27.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_28.png)

If we scroll down， the final answerr of our first agent is actually an overview of this project。

 so it now fully understand the project and gave all the information that it could find about it back to our second agent so we can see all the tasks。

 the commons， some of the team ens and everything that we need to know。



![](img/e9002ddb7524fa39f637e6c63d9af37a_30.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_31.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_32.png)

Now the project analysis Exp kicks off and it's going to use this previous information from our agent to build a fullblown report and here we can see the report being outputted now let's see how much running this cost us and then let's look pretty closely at this comprehensive report。



![](img/e9002ddb7524fa39f637e6c63d9af37a_34.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_35.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_36.png)

For checking the usage metrics and costs， we're going to be using the same math from our previous lesson because we are still using GPT40 minii。

 we know that it costs 15 cents per million tokens so we can tap into the usage metrics for the crew to do some simple math。

You can see that this costs us 0。0053 cents and that's pretty cheap and this time the amount of tokens was over 35。

000 tokens。 Now let's take a look and what this report actually looks like Now let's s this report and we're going to be using markdown for this because we expected our crew to outputput a markdown file。



![](img/e9002ddb7524fa39f637e6c63d9af37a_38.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_39.png)

And there we go。 Here's our sprint report。 You can see that theres a sprint overview talking about a few key issues。

 There is a summary of things that needs to be done。

 Things that are in progress and things are in review。

 And then it goes into identified issue and blockers。 It identified a lack of detailed descriptions。

 and also a few tasks that is tailed。 There's one we a deadline。

 And there's only a single team member working on this。 And that's myself。 Now， if we scroll further。

 we can see some more comments around progresses and delays。

 and even a team performance overview going over on how I'm the only active participant on this board。

😊。

![](img/e9002ddb7524fa39f637e6c63d9af37a_41.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_42.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_43.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_44.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_45.png)

![](img/e9002ddb7524fa39f637e6c63d9af37a_46.png)

It also gives us some action items and recommendations on how we can improve this project and making sure that we keep it on track。

 and then even gives us a conclusion paragraph explaining about how we can implement some of these recommendations and what is the value on doing it。

😊。

![](img/e9002ddb7524fa39f637e6c63d9af37a_48.png)

This is a very interesting project。 You can definitely see how this can be valuable for not only managers。

 but teams out there。 they're trying to understand how is their project going without having to dive into every single specific card and reading every single specific comment。

 This is a pretty good automation that allows you to get a deep understanding on the project and have agents actually do all the work for you pretty damn fast。

 Now， let's go into our next lesson where we're going to dive even further we're going to learn a new features and build a fairly complex screw。

 I'm so excited about that。 so make sure that you stick around and I'm gonna to see you in the next lesson。

😊。

![](img/e9002ddb7524fa39f637e6c63d9af37a_50.png)