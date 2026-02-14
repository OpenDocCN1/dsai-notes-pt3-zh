# 吴恩达《使用 crewAI 的多人工智能代理系统｜Multi AI Agent Systems with crewAI》中英字幕【短课英文均可关闭／拖拽】 - P9：8.L4 Tools for a Customer Outreach Campaign.zh - GPT中英字幕课程资源 - BV1GZ42147am

All right， to get a things this started， let's get some of the boiler plate code in here and let's start But our crew。

So first thing that you want to do is make sure that you import the agent task and the crew class again。

 once that you import that， you're good to go and ready to get started Allright so now that you imported the agent the task and the crew class we can set up what mod that we're gonna be using So for this one we're going to be using G4 So you have been using GT3。

5 up to this point but we are moving to for now because we're gonna to be handling with more data。

 So you're gonna to make sure that you have that extra context window to handle all the information that we're gonna be sending to this agents。

 So let me just cop this and paste it here。 Another thing that you're gonna notice is that we're using Surer API here So Ser is basically an API that allow you to search Google and you're going be provided withfi key that you can use but you can also go into their website and sign up and they offer free credits but honestly there's a lot of other like search to。

that we could use as well。 We just choose to use Serper in this example。

 So let's go ahead and just execute that。 Allright so now we're ready to dive into twos we basically want to make sure that we use some of the prei tools and we also going to make sure that we create a simple custom2 to show you how that looks So let's go ahead and start creating our agents we're going have two agents for this The first one is going to be a sales wrap agent because we' are going to be doing a sales use case this time the sales ramp has one go and that is identify high value leads that match or ideal customer profile people like to call that ICp and sales is a big use case for multiag systems so probably you're gonna see a lot of that around the internet as well you can see that in the backstory we set some context around the fact that the sales agent work at prei in some of the mission around it in everything you're also gonna notice that this agent is not allowed。



![](img/ba9f9b6091e89492008fdc13584866d0_1.png)

To delegate any work or ask any questions is just supposed to do what it's stowed。

 We're also going create a new agent and that's gonna to be a lead sales wrap agent。

 So let's execute this and then create our new one。 So this lead sales rep agent。

 you're gonna see that it builds on top of our previous one。 it has a different go。

 This go is kind of find the actual personalized content and build a personalized communication with this lead that we're gonna to be working on。

 So the idea of the screw at the end of the day。 it's giving a lead find out a way to communicate with them that helps them to get interest on the career AI。

 So let's see how that's gonna to play out。 So let's first execute this agent Allright so now we have those two agents created。

 Now it's take for us to look into the tools that we' are going use。

 we' are going be using the query AI to package again。



![](img/ba9f9b6091e89492008fdc13584866d0_3.png)

So you can go ahead and type that out and import those tools You're gonna to see that we're using three toolss this time we are using a directory read2 we're using a file read2 and we' are using a serper da to so the directory read to we allow your agent to read any directory that it once or again you can kind like confine its options by saying a specific directory that you wanted to run then the file read2 the same thing and the Serp2 we already talking about that in another lesson it allows you to search the internet so let's go ahead and instantiate those three toolss so you can create a directory read to the file read2 and the search to and the one thing that you're going notice is that on the directory read to we're specifying that we want it to be able to read only this local instructions directory so in this directory there are。

A series of instructions as markdown files on how to handle companies from different sizes so we're going to have big companies。

 small companies and medium companies instructions on how to handle them and we landing or agents being able to read this files by setting up this tool that allow them to actually look at that folder So as you can see we now have three toolss that we're using here our directory readto or file reto and our search tool。



![](img/ba9f9b6091e89492008fdc13584866d0_5.png)

And you can see they are like all similar， but the directory agree to actually is passing one attribute called directory。

 These attribute is forcing this two to only allow the agent to read this one single directory In this case。

 is a local directory called instructions。 So this local directory basically hold a set of instructions on how to handle some of those customers if it's a big customer or a small customer or whatever it might be。

 Let's look at those files real quick。 So here you can see that there are three files inside that directory。

 a file that has a set of instructions to how to handle small business on how to handle text startups and on how to handle like more enterprise deals。

 And you can see here there's like a specific and plate。

 there is key strategic points to address Theres introduction。

 So everything that our agent might need in order to actually engage with like a specific。



![](img/ba9f9b6091e89492008fdc13584866d0_7.png)

![](img/ba9f9b6091e89492008fdc13584866d0_8.png)

![](img/ba9f9b6091e89492008fdc13584866d0_9.png)

![](img/ba9f9b6091e89492008fdc13584866d0_10.png)

![](img/ba9f9b6091e89492008fdc13584866d0_11.png)

So now that we have our tools here， we can create a custom tool just to see what that would look like。

So every framework out there is going to give you a pattern to create a custom2 and query AI is no different。

 It offer a couple different ways that you can use to create a custom2 So in this case the way that we are going to be using is by inheriting from a class inside query AI we can import this class it's called base2 and now that we imported it we can create our own class that's gonna to be our tool that inherits from that。

 So in this case our class will be called sentiment analysis tool So you can envision that this two would do some sort of sentiment analysis but this could be anything this could be an external API call or whatever you want but in this case we're just going fake it a little bit to make sure that we build a custom2 and we learned how to do it So one thing that every tool needs to have in query AI is a name in a description。

We are setting the name of this two to sentiment analysis to in a description tells the agent when it should use this two and what is its purpose So here were saying that it analyzes a sentiment of a text and then in order to actually implement the two all you got to do is create this run function inside that class so as long as you have this underscore run function in there you can add anything code that you want So in here is where you would call an API or where you would take an action or send a me or anything you wish your to to do in this case we're keeping it very simple because it is just an example and we're just returning the word positive so this is a sentiment analysis to that always return that the sentiment is positive so now that we create this to we can actually instantiate it so that we can。

Use it the same way that we did with the tools above with the directory。

 the file and the search tool so you can go ahead and just do that and now you have the sentiment analysis tool and you can pass that to your agents and tasks So now that we essentially our tools let's create our tasks and assign them properly here we are going to be able to see how we can focus in specific and clear goes on what we want to achieve by using these tools So the first task that we're going create is a lead profiling tasks So the lead profiling task basically conduct an analysis on a given lead in order to understand its sector how big it is information that might be useful for us to engage with this potential customer So in here you can see that we are providing it with a set of tools our director read to our file read in our search tool So with these tools。



![](img/ba9f9b6091e89492008fdc13584866d0_13.png)

![](img/ba9f9b6091e89492008fdc13584866d0_14.png)

Agent when performing this task are going to be able to look at those instruction files that we saw before。

 read them and then using the Serer API， search the internet for more information about this lead so let's go ahead and create this task Now we're going to need a new task this new task is being help with creating a personalized message to outreach for this specific lead so I can paste it in here and you're going to see that this task has a different set of tools。

 it doesn't need to read the directory any longer because by now we already knows if is a big or small company and already has done some research on then this task is focused specifically on doing a sentiment analysis and doing any further search that might be necessary in order to make sure that we talk with this customer in an appropriated manner so you can go ahead and also create this。



![](img/ba9f9b6091e89492008fdc13584866d0_16.png)

![](img/ba9f9b6091e89492008fdc13584866d0_17.png)

So now that we created the two tasks， you can create your crew。

 The crew is pretty straightforward the same way that we have been doing so far。

 we passing the agents， we passing the tasks you can set the ver mode to two and you also set the memory so that this crew is using the memory functionality and features you don't necessarily need to if you don't need but I think it might be a good use case so let's go ahead and render this Now you can kick off this crew and kicking it off should be pretty straightforward so in this case we're passing a set of inputs remember that these inputs are going to be interpolated in any place that we use them both in the tasks and in the agents so these inputs are going to be used into any place in the task descriptions or the agent's definitions anywhere where we try to interpolate these variables we can now pass their bads in here So in this case we're simulating that the lead。

Ne is deep learning and AI in their industry the industry is online learning platform。

 the key decision making maker is Andrew and he is the CEO of the company。

 and the basic milestone that they have as a product launch so we can go ahead now and kick off this crew So everything starts before sales representative。

 and it's going to start by conducting this ind analysis of the deep learning AI company and basically trying to learn more about it。

 So you can see here that it started by searching the internet trying to understand more about deep learning AI。

 So in here you can see all the search results that it got from Google。 And if you scroll further。

 you're going to see that it by mistake decided to try to read one of the websites as a file and you know that we just talk about how tools need to gracefully fail。

 This is a great example。

![](img/ba9f9b6091e89492008fdc13584866d0_19.png)

![](img/ba9f9b6091e89492008fdc13584866d0_20.png)

![](img/ba9f9b6091e89492008fdc13584866d0_21.png)

![](img/ba9f9b6091e89492008fdc13584866d0_22.png)

The file content read to is not meant to read a website but actually a file from your file system。

 so if you didn't plan for that， you would draw an exception in your execution would stop but career AI automatically handles that so that it fails gracefully so you can see that despite of it showing an exception it tells the agent that it got this error so the agent kind of like now understands that it can directly access the external links using the read files content so it's learning from the tool that it tried to use so it then go back into search the internet to try to find more information about deep learning AI So if you're building your own thing or depending on your choices or framework。



![](img/ba9f9b6091e89492008fdc13584866d0_24.png)

![](img/ba9f9b6091e89492008fdc13584866d0_25.png)

![](img/ba9f9b6091e89492008fdc13584866d0_26.png)

![](img/ba9f9b6091e89492008fdc13584866d0_27.png)

![](img/ba9f9b6091e89492008fdc13584866d0_28.png)

You might notice that if your two finds an exception the decision there is let that exception actually blow up and when that exception blow up。

 it stops the execution of your agent so that means that our that was completed so far is gone and your agent execution stop so you can move forward that means that you would then need to add an extra layer so that you can treat for that either kind of like kick off your agent from the scratch or do something else with that error so for crew。

 it was a conscious decision early on that we would prevent exceptions from start execution but you might find other frameworks that choose it otherwise and choose to let exceptions actually stop executions and that is a conscious choices that you can make and if you're doing something from the scratch because again。

 you don't need to be using a framework you can be。

ing this agents yourself is just going to be a lot more coding。

 but it's something that you need to be mindful of how you want to handle exceptions when using tools is a big thing of agents。



![](img/ba9f9b6091e89492008fdc13584866d0_30.png)

So you can see that again， it finds a bunch of different researchers and put together a deep learning AI company profile with a background。

 one are the key personal， recent business development potential needs engagement strategy everything that we need to know about the company now or next agent kicks in they'll lead sales representative where using the research that your agent did before。

 it's going to try to come up with a good way to engage with deep learning。

 So in here you can see that again， it's doing some research online。

 Keep in mind then this is where some of that caching strategy that we talked about comes in if this agent tries to do the same research or the same search online that another agent did it's gonna hit a caching layer instead of actually doing the search So you're gonna to be saving on rate limits and on a request and basically is。



![](img/ba9f9b6091e89492008fdc13584866d0_32.png)

![](img/ba9f9b6091e89492008fdc13584866d0_33.png)

![](img/ba9f9b6091e89492008fdc13584866d0_34.png)

![](img/ba9f9b6091e89492008fdc13584866d0_35.png)

![](img/ba9f9b6091e89492008fdc13584866d0_36.png)

![](img/ba9f9b6091e89492008fdc13584866d0_37.png)

![](img/ba9f9b6091e89492008fdc13584866d0_38.png)

just work faster and here you can see that it come up with an email where we can send to Andrew the subject is and haste deep learnings AI educational impact with crew AI advance and analytics and then it goes on and explaining and you can see that even references the batch the batch is actually a newsletter from deep learning AI and we never told this agents anything about it they learn about it automatically through the research that they made so now we have an email that we could engage and we actually have a few other options here so you can see that it gives another option now a little bit more focus on AI drive toolss and another one talking more about a partnership so you can choose what email you want to use to actually engage with this company This is such a great use case throughout or interactions with the community that has been beauty multiag systems independently of what framework they are using we realize。



![](img/ba9f9b6091e89492008fdc13584866d0_40.png)

![](img/ba9f9b6091e89492008fdc13584866d0_41.png)

![](img/ba9f9b6091e89492008fdc13584866d0_42.png)

![](img/ba9f9b6091e89492008fdc13584866d0_43.png)

![](img/ba9f9b6091e89492008fdc13584866d0_44.png)

![](img/ba9f9b6091e89492008fdc13584866d0_45.png)

![](img/ba9f9b6091e89492008fdc13584866d0_46.png)

ThatThere's a few verticals that are very common and sales is a big one because a lot of the sales process involves reporting。

 involves researching， involves engaging and all that are things that can now be automated through agents so it's going to be common for you going out there and talking with other people they are building agents to see that they' are doing things in this verticals and this is honestly a very interesting space in general。



![](img/ba9f9b6091e89492008fdc13584866d0_48.png)