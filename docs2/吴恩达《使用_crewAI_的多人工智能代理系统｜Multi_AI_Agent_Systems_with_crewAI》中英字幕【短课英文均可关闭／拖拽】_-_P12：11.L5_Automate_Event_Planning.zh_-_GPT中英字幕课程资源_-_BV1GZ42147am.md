# 吴恩达《使用 crewAI 的多人工智能代理系统｜Multi AI Agent Systems with crewAI》中英字幕【短课英文均可关闭／拖拽】 - P12：11.L5 Automate Event Planning.zh - GPT中英字幕课程资源 - BV1GZ42147am

Alright， so let's start by adding the mother plea code getting warnings out of the way。

 And now what you can do is import your crew agent and task classes。

 So now that you have imported your agent crew and task classes。

 we can set our environment variables。 So in order to do it， I'm going copy this code here。

 keep in mind that we are also going use Serper in this example。

 So you're going need the Serp API key。 that's going be provided to you。

 but you can also find it going on their website and they do offer free credits。

 So now that we set up the keys and the model that we are going be using let's go ahead and import our twos were going be using two toolss in this case。

 the scrape website to and the Serper dev tool。 So think about how those two will fit together。

 The Serp dev tool， we allow you to search the internet using Google and getting resultss back。

 And then the scrape website， we allow。Agents to go into those websites that it finds and getting their contents so that it can use them during the execution。

 so you can see here how planning out the tools goes a long way on how your agents are gonna behave。

 Allright so let's create your first agents now。 let's first create venue coordinator and that kind gives away what we're building here。

 The example for this lesson is a crew that is able to organize an event or a meetup for us。

 This first agent has one single go identify and book an appropriate venue。

 So giving an event circumstances and requirements。

 It's gonna search the internet for venues that it can support that and find this venues for us。

 Now we can create that agent。 Allright， so our next agent is gonna be a logistic manager agent。

 So this agent make sure to think through the logistics of the event。



![](img/9838fae71b260e6a118ce9b1f1bfa653_1.png)

Now that the first agent already found a few options for the venue。

 It's going to think about how will this work out and making sure that the venue is appropriated for us to do whatever we're trying to do with this conference or this meetup So let's go ahead and create this agent as well or third agent is kind of like different It's a marketing agent It's supposed to work on top of the venue and the logistics and figure out how can we market this event how we can market this meetup so then we can get as many people as possible showing up to this So this agent is gonna to try to be creative and thinking about the event that we're putting together in the venue and the location and bring all this together into something that we can use for marketing So let's go ahead and create that agent as well you can see here how this can be pretty interesting too We have a system now that is not only finding things about the event but thinking about logistics。



![](img/9838fae71b260e6a118ce9b1f1bfa653_3.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_4.png)

Thinking about marketing everything in one go and this would be extremely hard to pull it off with like conventional programming if you're not building an AI application so now that we have this three agents we're going do something else something differently that we haven't done yet we're going to create a pantic object that is going to hold our venue details this is interesting because it's going to show off a new feature for tasks that we haven't discussed yet so in here you can see that we are importing the pantic base model and we're creating a class called venue details that it inherits from the base model and you're saying that this venue details is going have four different attributes a name an address a capacity and a booking status the reason why we're creating this model is so that our agents can work with it and populate this model create instances of this as they work so this is a very interesting。

Use case on how you can use agents to transfer the fuzzy outputs into actual strongly typed outputs that you can use on a regular code So before we start creating a tasks I want to spend a few seconds to talking about pganic pentic it's a library that has been getting a lot of attention allows you to create models and work with strong typed of variables in a very easy way。

 So you can see here that instead of like what you would do with classic python where you would declare a class and then you would need to declare a initial method and in that method。

 you would need to receive a bunch of arguments and then set a bunch of variables。

 it gets away from all of that and creates this synthetic sugar that allows you to create models in a very simple way now it's not only a class that you're creating but you're creating a model a reserve that has attributetro。

We found having to go through the hassle of creating a niche method and setting them up individually。

 Pyentek is a huge library and goes way beyond that。 So if you're curious about it。

 you can check it afterwards。 but for the purpose of this lesson we're going be using that in order to transform some of the fuzzy outputs that we get from our agents into strongly typed outputs that we can use in code Allright so let's get ahead and create our first So this task is pretty interesting。

 It's a task responsible to find a venue for our event So you can see that it expect a few inputs in here expect an event city and expect an event topic and look on how we are using a few different attributes that we haven't used before So in here you can see that we are saying that we want to output a Json and in order to output this Json we're passing our penttic object So what is happening behind the scenes is that our agents are going。

Converge their fluzzy output into this very strong type model and then convert that into JSson and then we are outputting that result into a file。

 a Json file that we can actually use So this is just to showcase some of this attributes that you get on the task class that you don't use very often but are superpowers in certain cases。

 people use this a lot when you're trying to integrate agents into existing systems without doing a true APIs So instead of having an API that is going kick off your multiag system if you want to have this agents with your code。

 this would be a great way to get an output out of them that you can already use on like function or anything else。

 So now let's create a second task or second task is pretty interesting。 It's a logistic task。

 This task is responsible for coordinating catering the equipment for event。



![](img/9838fae71b260e6a118ce9b1f1bfa653_6.png)

You can see that in this it's expecting a few different variables。

 looking for what is the number of participants and what is the tentative date for this event to happen you can also see as using a few different attributes in here so you can see that we are using human input in here this means that before this task is completed the agent is going stop and ask us the operator if we want to give an input if we like the task result if we wanted to change anything with it。

 you can also see that we are doing a synchronous execution so that means that this task is going to be executed in parallel with any other task that comes after that so this is a very other good use case because if you think about it this logistic task depends from the result from the venue task because the location is going to influence how you're going to coordinate the catering in the equipment and everything else but as you're going to see a second。

It has nothing to do with our final task。 So our final task is going to be or marketing task。

 is the task responsible for creating the marketing campaign that will help us promote this event。

 So you can see in the description here that again， we are talking about the even topic。

 the expected participants and we want to report on all the marketing activities that we can do in order to promote this event。

 And you can see that this task is also allowed to execute in parallel。

 So what that means is that the first task， the task that selects the venue。

 it's going to be executed by itself alone as all the other tasks that have been that we have seen so far。

 But after that， the logistic tasks and the marketing tasks are going to be executed in parallel。

 because if you think about it， one doesn't rely on the other。

 the output of the logistic task don't necessarily matters for the marketing task。



![](img/9838fae71b260e6a118ce9b1f1bfa653_8.png)

Poor so we can have them run in parallel without too much trouble And in here we can see that we are outputting the results of the marketing task into a file and in this case is a markdown file。

 And because in the expected output were mentioning that we expect the result to be formatted as markdown。

 all this should work just fine Allright with that we created or three tasks。

 were using a bunch of new attributes for the tasks and you can see how you can leverage a lot of those for different use cases in here。

 we are gonna to like forcing ourselves to use some of these attributes just as a way to showcase how useful they might be in the real world。

 but you're probably already thinking about all the use cases that you can support thanks to some of these attributes that a query AI brings into the table So now that we have our tasks let's make sure that we create our crew and creating the crew is pretty straightforward It's the same thing that we have done so far we have a set of agents。



![](img/9838fae71b260e6a118ce9b1f1bfa653_10.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_11.png)

ASe of tasks we set the ver mode to true and everything is ready and we can now kick it off So let's keep in mind that there's a bunch of variables that we use through all the tasks and the agents that needs to be interpolated so let's start by setting those up so this is the event that we are organizing it's a tech innovation conference trying to gather tech innovators it's going to happen in San Francisco it has a date。

 we expect to have 500 people and we have a $20000 budget on it。

 we would love to have a conference hall that we could use for this so these are all the inputs that this crew needs in order to do its research and actually fulfill its tasks so let's kick it off and see how that goes so from the ga go you can see that the venue coordinator kick things off and starts by trying to find a venue in San Francisco because that's where we mentioned that we want this conference to happen。



![](img/9838fae71b260e6a118ce9b1f1bfa653_13.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_14.png)

meet the criteria for making a tech innovation conference so in order to find that you can see that it decides to search the internet so it searched for tech conference venues in San Francisco so it finds a bunch of results as you can see in here and then it decides to scrape one of these results among the results it found tag venue co specifically mentioning listening conference venues for rent so it decides that it's a good call to kind of scraped that content and here you can see the whole content that was scraped from that website it's quite large but now it's ready to give its final answer the detailed content from the tag venue website helped it to kind of understand what are be the options so the selected venues have different sizes and types and wants us to say what easier feedback if we agree that for a large conference like this it should go for the main hall arellis。



![](img/9838fae71b260e6a118ce9b1f1bfa653_16.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_17.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_18.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_19.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_20.png)

The second floor at Do Patch Studios， I'm going to keep it simple and I'm going to say， yeah。

I like this options。

![](img/9838fae71b260e6a118ce9b1f1bfa653_22.png)

So now that I gave it the input， it's going to move on from that and going to keep executing the code。



![](img/9838fae71b260e6a118ce9b1f1bfa653_24.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_25.png)

When look at what happens after this， it's going to pass on to the next agent that is now going to figure it out how to come up with not only the catering。

 but also the marketing from this so you can see the final answer in here now that it took into account what we said and look how cool is that the output from our task is now valident Jasonson it's not tax any longer so you can see how or pantic output there is working its charm。

 we could use this to integrate with anything else， we could save this into a database。

 we could save this into a file there's just so many options here。

 the ability to convert like agents output into regular objects that we know in programming it's super helpful and allow us to bridge the gap between AI applications in regular applications and you can see that even though this is Jasonson this is being sent as Jasonson to our next agent。



![](img/9838fae71b260e6a118ce9b1f1bfa653_27.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_28.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_29.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_30.png)

The logistic manager to try to coordinate catering in the equipmentment for that so you can see that this agent now kicks off together with for new agents so you can see there's two crew agent executed runnings here because we told that the last two tasks could be executed in parallel asynchronously so why we have one agent kind of looking into the。



![](img/9838fae71b260e6a118ce9b1f1bfa653_32.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_33.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_34.png)

Caing， the other one is looking into how to promote this and what would marketing look like for a conference like this。

 So again， they're both searching the Internet and trying to come up with everything that they need。

 Allright， let's skip to the end and see what we end up with。

 So now let's look at some of the outputs of this agents。

 as they are wrapping up their work and coming up with their final answer。

 we can actually look at some of the files that got generated during the execution。 First of all。

 you might remember that we asked the venue details to be outputted as Json。

 and written in the Json file。 So this is the Json file。 This is the name of the place。

 This is the address， This is the capacity and it seems to be available for renting。

 And now we can also look at what the marketing strategy could be。

 because it also got written down in here。 So in here we can see that is a fully flged marketing campaign plan thinking about the digital marketing。

 the content marketing。

![](img/9838fae71b260e6a118ce9b1f1bfa653_36.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_37.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_38.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_39.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_40.png)

The partnership， the networking， the on site， the tools and even doing some budget allocation and how we could use our budget to actually market this so think about how amazing it is you basically create a moyag system that is capable of not only finding like a good venue and figuring out how to organize things and bring the equipment and everything but also capable of thinking about a marketing strategy and blend it out for you so that you can act on it This is just the tip of the iceberg on why you can achieve with multiple agent systems in a great use case an example on how this agents can be deployed outside in the world and not only in engineering。



![](img/9838fae71b260e6a118ce9b1f1bfa653_42.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_43.png)

![](img/9838fae71b260e6a118ce9b1f1bfa653_44.png)