# 吴恩达《多AI智能体实践与高级应用课程Practical Multi AI Agents and Advanced Use Cases with crewAI》 - P9：9.L4 Support Data Insight Analysis.zh_en - GPT中英字幕课程资源 - BV1fgySYsE5y

![](img/85ab78bbb9dcdb62faab450c1c540798_0.png)

I'm so excited about this use case because we will use performance optimization to improve or cruise ability to give us consistent result。

 so we just talk about speed and quality and how you want to keep consistent no matter what。In this。

 we're going to use agents to basically load into support data and understand what happened。

 what were the customers saying about it， who were the people from the team that was helping。

 what was the sentiment analysis on it， and everything that is to be known on this data。

For this use case we're going to start with tableular data This is data from support。

 so it will include a lot of information about who were the customers that had problems。

 what are the problems that these customers had and we're going to be able to look into this data to understand patterns or agents are going to try to parse how the different details in all these data points to understand who are these customers who is helping them from our team and what are the issues types that they have we're going to go even beyond that。

 also thinking about the issues descriptions themselves and frustrations that these customers might have。

So the agents will be able to look at out this data and parse it internally in order to create not only suggestions。

 but even plot charts and visualization so that we can parse this data better and even share with others。

To start， we're going to have three agents， a suggestion engine agent， a report generator agent。

 and the chart specialist agent。Diststrict agents are going to perform a series of tasks。

 starting with two tasks in parallel， a Gene Su task in a Gene Ts task。

One ask is going to look through all the issues reports that we have and come up with suggestions on how we can make that better The second one is going to look at all those same data points and now try to organize that into a tableular view grouping the data in ways that make sense After that we want to make sure that we plot some visualization in charts so that we can share this report with others and we can understand better what this looks like this is going to be so fun and exciting because agents that can code and actually plot charts are so powerful。

😊，Then we're going to have a final report being put together by our agents that is going to encapsule everything that these agents have done from their suggestions to the tables to the charts。

 This is a very special use case it's the first time that we're going to see an agent that can code or chart specials is allowed to execute code and it's going to write code on the fly and execute it for us in order to create this visualizations that we will need This is such a nice use case because agents that can code can do so much more in the end of the day the support data analysis use case。

 well do a few different things。 go over a series of the data from support。

 generate suggestions for an improvements based on that then organize this data into tableular insights in groupings that make sense and plot charts so that we can visualize any trends and then wrapping things up by running a full final report on this analysis。



![](img/85ab78bbb9dcdb62faab450c1c540798_2.png)

This is so good we're going to build this and learn how you can use agents static code in order to create very complex use cases that were not possible before。

 so let's dive into it right now and understand how we can build it yourself。😊。

In order to build this use case， we're going to start with load or regular imports this is very borderer plate compared with the other use cases where we're importing all the different libraries that we need。

 including our main C AI classes。Now for this use case we're going to be using GPT40。

 we don't need to even set this model because this is the tool for C AI。

 so let's go ahead and load our agents and tasks with our Classnippet that just look at the YaL files。

The reason why we are using 40 for these agents and tasks is because some of these agents are going to be fairly complex remember we have agents here that are capable of writing code that actually plot charts so we need these agents to use a heavier model in order for them to have a certain level of quality so we're using GT40 for that Now let's take a look at our agents and tasks before we keep going。

So there is three agents for this use case， we have the Su agent agent， the report generator agent。

 and the chart specialist agent。If you look at this。

 all those agents also have the role goes and backstory and again you're invited to change them in any way that you want in order to get different resultss。

 If you look at the task Yamo， you can see that we have four different tasks we have a suggestion generation task that is going over all the issue types。

 historical data， customer certification and customer feedback then we have our table generation tasks that goes over through all the data and tries to summarize key metrics and trends kind of looking into issue classification resultss and the agent performance in order to put together a tableau view on how our agents and issues are doing If you look at the third task we have the chart generation task this task is going to try to plot charts around issue distribution priority levels。

 resolution times and customer satisfaction including agent performance so that we know who from our support team is doing the best work。

On helping our customers。And then as a final task， we have our final report assembly that basically brings everything together into one final singular report as a markdown now that we know what are our agents and what are our tasks。

 let's dive into the code and actually build this crew。

This crew is going to be pulling the support data from a local CSV file。

 so in here we're going to use a file read tool from the CareI tools package in order to read the support tickets data CSV file from here we're going to find all the information about every single support ticket that we have data on so let's look into those tickets right now。

So here is a quick glimpse on our tickets data， you have T ID， customer ID。

 issue type and so much more， this is a file that our agents are going to be using in order to extract information from and it's more of a bigger file than usual。

😊，So let's start by creating your agent， tasks and crew In here you can see that we are pool the agent's config with the Yal config data in order to create our agents and we're giving for our suggestion generation agent in our reporting agent access to CSv2 that is able to load that ticket information and then for our chart generation agent we're setting a new attribute that we haven't used before that is allowed code execution with this attribute is set to true this agent now able to write and execute code in a protected environment using Docker So whatever this agent does。

 it's isolated from your local machine and can execute code only in that sendbox。😊。

Now that we have our agents， let's make sure that we create our tasks。Yeah。For our tasks。

 we have four different tasks， as we said， the suggestion， the table generation。

 the chart generation， and then the final report， you can see that in the final report。

 we're also using our context attribute because we want this final report to put information from all the other tasks in order to build this final one so it's going to pull the resultss from all the other three tasks before it actually writes the final report now that we have both our agents and tasks we can just put them out together into a crew。

And the crew is super straightforward， is just bring all the agents and all the tasks into one。Now。

 before we kick off the screw， let's test it by running crewIT to make sure that we understand how good the screw and agents actually are。

So let's test our crew During the last we mentioned that you have a common line interface with the C AI task command。

 but in here because we're using a Jupyter notebook。

 we're going to call the task method directly so you can just put your crew's name and call the test on it and you can pass a few attributes to that in this case how many iterations you want to test this with in what model you want to act as LLM as a judge Now let's execute this。

So here you can see that our crew starts executing as usual， or initial agent。

 the suggestion engine agent， starts to work on generating actionable suggestions based on the data。

 and you can also see that it's using a read files content tool and loading that CSV right there and it loads all that data so it starts to parse it and understand it。

 let's take along and see how this agent execution goes。



![](img/85ab78bbb9dcdb62faab450c1c540798_4.png)

![](img/85ab78bbb9dcdb62faab450c1c540798_5.png)

And here you can see the final answer from your agent。

 it went over all the tickets and gave pretty actionable resultss for every single one of them。

 Now let's see how our next agent will pick up this work。



![](img/85ab78bbb9dcdb62faab450c1c540798_7.png)

![](img/85ab78bbb9dcdb62faab450c1c540798_8.png)

So here you can see our next agent， the report generator starting to generate tables that summarize some of the key metrics and trends that are observed in that support data and here you can see that it's loading that data again and then parsing that data in order to create the right tables that you want to show in the spinal report。



![](img/85ab78bbb9dcdb62faab450c1c540798_10.png)

In here you can see some of the final resultss for this agent that includes an issue classification resultss and even an agent performance agent here。

 meaning that person that actually helped with the support ticket and gave us good summarization numbers across everything Now let's see or chart generation agent that going write code in order to plot some visuals。



![](img/85ab78bbb9dcdb62faab450c1c540798_12.png)

Here you can see our chart specialist agent that will go through the data trying to plot visuals around priority levels。

 resolution times， customer satisfaction and Asian performance。

 you can see that it has a plan around loading the data and creating the charts and everything and actually writes the code you can see the code in here importing pandas and mapplli and kind of like loading the data in order to create this charts。

 you can see that the images were generated and we're going to look at what that file looks like in a second。

😊。

![](img/85ab78bbb9dcdb62faab450c1c540798_14.png)

![](img/85ab78bbb9dcdb62faab450c1c540798_15.png)

![](img/85ab78bbb9dcdb62faab450c1c540798_16.png)

Now let's go towards our final agent that puts together the entire report。



![](img/85ab78bbb9dcdb62faab450c1c540798_18.png)

And here you can see your final agent， the reporter generator。

 and it's going to use all the other tasks results in order to put together that find no report。

 and this is so interesting because it's going to now bring the charts， bring in the tables。

 the suggestions， everything into this one final single report。

 So let's see what that will look like。

![](img/85ab78bbb9dcdb62faab450c1c540798_20.png)

Here you can see the final result where you can see the overall issues。

 you can see the charts being displayed， the agent performance。

 another visual about the agent performance， and then customer satisfaction and everything that we asked about。

 including suggestions on how to make some of these issues better。

 and key trends that were ob during the execution。

![](img/85ab78bbb9dcdb62faab450c1c540798_22.png)

![](img/85ab78bbb9dcdb62faab450c1c540798_23.png)

![](img/85ab78bbb9dcdb62faab450c1c540798_24.png)

Now， before we actually plot this markdown so that we can tag along on what exactly it looks like in all this visuals。

 let's look on how our testing came about。

![](img/85ab78bbb9dcdb62faab450c1c540798_26.png)

You can see here a table that shows for every single task of crew from reading the data and doing suggestions to actually adding and creating tables to then plotting charts and then putting the whole report together from the first task that loads the data and comes up suggestions to the second one that actually group this data into tableular views to the third one that actually write the charts and create visuals for us to the final one that put the entire report together we got different scores for every different run and we have a final score for the total crew and you can see the total execution time as well on how fast this was This is a pretty interesting report and we can run this multiple times as well As a matter of fact I recommend you to render this multipleot integrationerations at least two or three so that you can pick up on。

And you can have a better understanding on how well your agents are actually behaving。

 but now that we have this course， let's do some training so that we can get our agents to perform better on here on and then we can run task again to make sure that we have better resultss overall so let's train this group。

For you to train your crew agents， we mentioned in the lesson that you have a CLI where you can use the crew AI train command to train or crew directly on your terminal as we're running this on a Jupyter notebook we' arere going to be using the train method directly。

 but this is work the same way you can pass how many iterations you actually want to train the screw for and where you want to save the training data as long as it's a pickle file you should be good so let's run Cr AI train and see how we can train this agents to do better。

I'm so excited about this because you can see that our agents are executing the same way。

 the same way that we had during tasks， but there's one major difference whenever it finishes a task and lets us scroll to the bottom of this。



![](img/85ab78bbb9dcdb62faab450c1c540798_28.png)

![](img/85ab78bbb9dcdb62faab450c1c540798_29.png)

It's going to give us the final answer， but now it's going to access for feedback so that we can actually provide feedback on how good this answer is or think that we believe it should have done differently so let's actually give it some feedback here。

😊。

![](img/85ab78bbb9dcdb62faab450c1c540798_31.png)

So in here we can type whatever feedback we want this is very useful if you are trying to have your agents to do better work in general or trying to comply with a very specific format or trying to get longer resultss or anything in between in here I'm going to say that I want to better suggestions so let me type that out。

In here you can see that the feedback that I'm providing is that I want this agent to do better suggestions。

 I want them to be more thoughtful and meaningful so that we can improve the overall support quality so I can just press enter and my agent is going to do the same task again。

 but now taking into account that feedback。And this is going to repeat for every task of the crew。

 so let's sta along data for a second。Now our second agent just wrapped up the second task you can see that the final results include the three tables that we asked it for。

 including issue classification resultss， agent performance and customer satisfaction。

 let's give it some feedback that we want an extra table with actual comparisons。

So the feedback that we are providing for this agent is that it needs to make sure to include an extra table that have great comparisons and we can actually use so let's give this feedback to see how this agent is going to update its answer。

😊，So in here you can see how the agent now updated its answer to include our feedback。

 it still offers the initial tree tables including issue classification resultss。

 agent performance and customer satisfaction， but now has an extra table with comparative analysis that didn't have before。

So here you can see Rio time how the agent picked up on the feedback and updated its task output and the best thing is that your agents are learning from this。

 so it's not only that it's updating its results right now but it's actually learning to always give this new results in the future so it's going to learn from this and never forget you're essentially onboarding your agents and teaching them how exactly you want them to do the job that you're giving them to do Now let's look at our last agent' results。

😊，So this agent generated all the images， it executed the code。

 it has every single PNG that we need So honestly I don't have much feedback on this one。

 I'm just going to let it know that this is great。😊。

So you can see my feedback is that this is great and that this agent generated all the necessary images so we should move along。

Now our final agent finish up its work。 It gave the full summary， including the tables， the visuals。

 the suggestions， and everything that you need， but I didn't like that it put out the charts towards the end instead of having them tag along the tables that we had at above。

So I'm going to give it some feedback about that。So you can see that the feedback that I'm providing here is that this agent needs to make sure to always include the chart visuals close to the information related to them。

Like the tables and make sure that the report is super complete and it's not missing any necessary information nor great suggestions that we might need so let me send this pin back to this agent。

😊，Now you can see that our final agent updated its response to include not only the tables。

 but the chart to be closed to it， and even the report itself is now a little longer。

 including more suggestions and informations that help us to make a better report overall。



![](img/85ab78bbb9dcdb62faab450c1c540798_33.png)

So now that we have this and our agents are fully trained。

 let's run C AI task again to compare our last task results with new ones that it would get。

 now that we train as agents。Now let's run tasks again to make sure that we can compare the results from the testing before the training with the task after the training。

 so this is going to be the exact command that we executed before where we're testing this crew just once using the same model that we used before。

 so let's kick this off。So now you can see the task results from running or CT after running Cr AI train。

And we're going to go over it in a second and compare with the previous tasks that we had。

 but one thing that I want to call out is that we're running this only once。

 ideally you run this multiple iterations so that you can get a more accurate average review of how well your agents and your crew is behaving。

If we compare this with our private resultss， what were going to see is that there was a bump on test number one and on test number two。

 but then test number three and test number four fell a little short execution time remains roughly the same。

So ideally， we would run this for multiplepole times and even do a few different number of iterations of the training to make sure that our agents are getting closer and closer to what we expect them to do。

 but this is a great use case on how you can optimize a few tasks in order to get them to perform better over time。

Okay， so we just finished running tasks and you can see that this time we run multiple iterations。

 so we actually have three iterations of testing our agents。

 and we have scores for every single task for each iteration and we also have averages at the end。

 We can see how our agents have been doing throughout all the iterations and how much time it took them forget this work done。

 Now， let's compare this for old crew task execution。

 and I have taken a screenshot behind the scenes so that we can see one this will look like for this use case that we were running here。

 you can see that test number one had quite a bump on the average。

 in test number two was roughly the same Test number 3 was also roughly the same。

 but then the test number4， and the overall crew score， both got big bumps。 So on average。😊。

We have better results for the tasks for the crew and time is just roughly the same。

 So here you can see how you can make a difference on getting very consistent results every time that you run a crew and having them behave on the exact way that you want them to by following a specific format or by doing a specific things whenever you want your crew to do create a train and testing are such a great features that allow you to really fine tune your agents and understand everything that they are doing this is so excited and then lock so many use cases out there you can use this to make sure your agents follow specific format or make sure that your agents are never leaving data out of their final reports there's a lot of use cases and guess what now you can build them yourselves so now before we wrap this up let's run this crew one final time and let's plot the final results so we can see what this report actually looks like。

Okay， for us to kick off this crew， it's going to be our usual thing where we just call the kickoff on our crew because we have no variables being interpolated in the tasks or the agents we don't need to pass any inputs in here。

 so let's kick this off。Now let's check out the result of our final execution。

 and I'm just going to print this as a markdown。If you look into this we got our whole final report you can see tableular view from organ issue types and the frequency and the priority levels and even a chart with all the distribution for all the different issues that we have you can see that everything seems to be very balanced out when you look at priority levels you can see that API issues have a lot of like high priority problems and bill issues as well。



![](img/85ab78bbb9dcdb62faab450c1c540798_35.png)

![](img/85ab78bbb9dcdb62faab450c1c540798_36.png)

![](img/85ab78bbb9dcdb62faab450c1c540798_37.png)

When you look at agents performance and what agents are doing better。

 we have some tableableular view on what agents are helping with what kind of issues and how well they're doing。



![](img/85ab78bbb9dcdb62faab450c1c540798_39.png)

But by looking at the chart you actually have a better understanding。

 so you can see that agent number one， for example， is doing a lot of tickets。

 but also is not getting a very good satisfaction rating Age number two on the other side take as much time as agent number one but has a way higher satisfaction rating so this is a very interesting way for you to actually explore the data think to this agent actually writing this code for you。



![](img/85ab78bbb9dcdb62faab450c1c540798_41.png)

And if we keep scrolling now， we can see the distribution of satisfaction across all the months so you can see how things have been trending up but since then got a smile bumped down。

 And then we have all the different suggestions on how we can actually improve our support and our features based on all the ticket supports that we got。

 This is a very interesting report。 and you can definitely see how useful this could be for a company setting。

 You could be using this in your company。 you could be using this in your team。

 and this is just a showcase。 You could be doing this for HR for coding or so many other use cases within your company。

 I'm so excited about this one because this shows you a practical use case on how you can actually use AI agents out there。

 I hope you really enjoyed this one。 but hey， don't go anywhere。

 Let's jump in the next lesson right now。😊。

![](img/85ab78bbb9dcdb62faab450c1c540798_43.png)