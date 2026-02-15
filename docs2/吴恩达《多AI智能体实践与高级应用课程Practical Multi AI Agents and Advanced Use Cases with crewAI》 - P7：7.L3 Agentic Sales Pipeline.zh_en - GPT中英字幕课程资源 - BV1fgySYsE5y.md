# 吴恩达《多AI智能体实践与高级应用课程Practical Multi AI Agents and Advanced Use Cases with crewAI》 - P7：7.L3 Agentic Sales Pipeline.zh_en - GPT中英字幕课程资源 - BV1fgySYsE5y

I'm very excited about this use case you're going to use a new feature called Flows and you're going to use it to build an A sales pipeline where we're going to have lead information。

 we're going to enrich it， we're going to score it and then write an email for this lead It's going to be very interesting。

😊，So before we start building this， let's talk about what this looked like。

We're going to start by loading leads and that doesn't need to be a。

 that can be regular Python code tap from a database and loading out this data out then from there we're going to send this to a lead scoring crew that you're going to build that is going to search information about this lead is going to try to understand how to score in and how good of a match this is for the product and business that you're trying to sell them from that point on。

 we're going to save this data back into another database and this again can be regular python code。

 it doesn't need to be necessarily a from here on we want to make sure that you filter out any leads there are not that high score and we keep the ones that are so that we can send to our next crew This crew is going to use out the information that we found about this lead going to write an email to them and optimize it for engagement。

We' are going wrap all this into what we call a flow and the flow is going to basically have events to make sure that we are going through all these different steps and a flow also has a state where we can store information to access during the flow execution or after the flow execution and we're going to show how you can use that as well Now let's zoom in into the crews to talk about that for a second the lead scoring crew is going to start by analyzing the lead data then doing a research on the culture about that company and doing a final lead scoring then if the score is high enough。

 the email crew data is going to do an email drafting and then optimizing it for engagement。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_1.png)

Another thing that I want to point out is that the lead scoring crew is going to output a structured data output and we're going to use this in order to access this information and pass it along for the email writing crew This is going to be super relevant and also super interesting to see how you can have very complex structured data outputs from crews and agents Now let's talk about what is the sales pipeline the sales pipeline is basically going to research the potential lie is going to score them given the person and the company and all the information that it was able to find on them and if the sales lead isqu then the crew is going to write a proper initial email to reach out to this link this is so exciting because you could literally automate a sales pipeline for a company out there using exactly the stamps and then you can train and fine-ts agents for your use case Now let's get our hands dirty and actually build this。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_3.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_4.png)

Let's go into the code。Alright， so let's start by importing or classes that we're gonna need for this。

 It's gonna be a regular agent task and crew classes。 So let's start by importing those。

 Now we can set what will be or open AI model that we're going to be using for this one。

 We're going to be using G 40 mini Keep in mind that this is already default for crew AI。

 but we want to be ver bothse here and make sure that we are setting it up。

 Then the next thing that we need to do is load all our agents and tasks Yamo files in a similar way to like what we have done in the past。

 loading it is very straightforward with one difference。 We are now using two crews。

 So we're loading two set of Ya files。 two kinds of agents and two kinds of tasks So there's gonna be lead agents They are focused on lead scoring and researching an email agents that are focusing on writing the email for that lead。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_6.png)

wayay for the tasks and we're just putting them into this four different variables so that we can use them later。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_8.png)

Now let's create our pedantic models that we're going to use to structure this lead information and this lead data into something that we can use。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_10.png)

So for this， we're going to be using four different models。

 We're going to be using a lead personal information model that holds personal information about the lead itself。

 we're going to use a company info model that holds information about the company like the company name。

 the industry the revenue and then we're also going to use a lead score class that stores the information about the actual score that our agents are going to give for data specific lead and then we basically bring everything together into the lead scoring result model and that brings the personal info。

 the company info and the lead score under one single model and object that we can use Now that we have creator our models let's importpart the tools that we're going to be using for our crews。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_12.png)

For these crews， we're going to be using only two toolss。

 the Surer Daft tool and the scrappe website tool。The tools are going to allow our agents to research the internet using Google and then scrape any URLs that it comes along with it in case they want to learn more about a specific version or any specific website that they get exposed to。

Now let's actually load our YaO agents and YaO tasks to create our first crew。

 the lead qualification crew。This crew is varied to the point。

 We're going to have three agents and three tasks。 We'll have a lead data agent。

 a cultural fit agent， a scoring validation agent。 Each of them are going to be focused on final specific information about our lead The lead data agent is going to try to enrich this lead with information about their role at the company and kind of assessing it to see if they would be a good buyer for whatever we're trying to sell them。

 The cultural fit is going to make sure that this company feels like a good ideal customer profile。

 given what we're trying to sell to them and then the final scoring agent basically bring all this together to give a final score for this lead with all the information around how that score came to be。

 and we can look at those tasks in the Yamo in a second but then we just bring it all together into this one single crew and that's our first crew。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_14.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_15.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_16.png)

Yeah。Now， let's take our agents real quick。 And here you can see their role。

 their goals and their backstory。 The agent definition for this agents are very straight to the point。

 The whole goal is for them to find information about this lead in order to make an informed decision on if this is a good lead or not。

 If we look at the tasks， we can see what kind of information we are trying to extract for every single lead。

 So there is personal information is like the name， the job title， the role。

 the professional background。 But then there is also company information like the industry。

 the company size， the revenue， and even the market presence。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_18.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_19.png)

You can see that we are presing what is the company and product that we are trying to sell in this case we're trying to sell them into C AI in the product it's a moy agent orchestration platform we tell them about what is our ideal customer profile and how we would pitch this platform and we then bring in the lead data to interpolate within this task definition and we could be also interpoolating the company and the product information in here。

 but for the sake of this example we can just have it defined directly in the task definition。

 given this is a qualify specifically for the query AI use case you can see that our other tasks go along trying to find more information about the culture value strategic alignment and a qualitative scoring around how good if the lead this actually is now that we have seen a little bit about our agents and tasks let's go back into our code。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_21.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_22.png)

Now let's create our second crew。 That's going to be an email engagement crew。

 That crew is the one that is actually is going to write the email for our lead onces that it's scored and classified。

 So this crew is very to the point。 We basically have two agents。

 an email content specialist and an engagement strategist and they're going to go through the steps of drafting the initial email and then optimize it to make sure that it's engaging。

 This crew is only going to focus on the very high score leads that we get to make sure that we can engage with them。

😊。

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_24.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_25.png)

Now that we have both crews created， we are ready to start creating our flow。

 flowlow is a brand new feature for a crew AI， and I'm so excited to show you this because flows allow you to do things that were just not possible before you now can execute regular Python code before your crew during your crew or after your crew execution。

😊，That allows you to have more control and basically to build different and more complete automations where you have all the agency that agents bring into the table。

 but also our ability to execute regular Python code if you really need to。

So let's start by importing our classes and functions that we're going to use for this one you can see that I import our flow class and then two functions。

 listen and start this is going to be a very straightforward flow。

 but it's going to allow us to understand how powerful it is。

The way that you create a flow is basically creating a class that inhers from the flow class from Cr AI。

And you can define the initial function that is going to be executed by using the S annotation。

So in this case， the that leads function， it's going to be our initial function because we annotated that with this start annotation。

And the fact leads here could be pool our leads from a database， for example， or doing anything else。

 In this case， I'm mocking it with some fake data for myself and a previous position that I had in a company called Cl bit。

 Now that we have that， we want to make sure that we score whatever leads that we fetch it。

 in order for us to do that we can create a new function called score leads。

 and you can see that we' are using a different annotation on this one called listen。

 And we're refer seeing the fact leads function。 What that means is that the score leads function is going to be executed after fact leads is done。

 So after we pull the leads from our database， we're going to get this information and then run the score leads crew for each of the elements in that array。

😊，You can see whatever the that leads function returns， in this case。

 an array of leads is going to now be passed on the score leads function。

 and we can use that to kick off our crew for each one of those leads。

Another thing that I want to point out is how every flow has a state and you can access that by doing self dot state。

In this case， we are throwing our scores inside selftain so that we can tap into those later for do some analysis on the information that was gathered。

 how much that costs and everything else。 So we can save this one for later。

 After we have a score or leads， we want to do two different things。

 We want to store them in our database and also future to get only the ones that have a very high score。

 both 70。 in order to do that， we create true new functions。

 I store leads score in a future leads function。 And you can see that both of these functions are actually listening to score leads。

 So once a score leads execution is done， both of these functions are going to be executed in parallel。

 So the store leads function could actually store this information back into database if we want to。

 And if future leads function， actually futures the list to remove。😊。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_27.png)

Anything that has a score under 70 so now we know that the return of this future leads function is going to be only the very high score leads that we got and for those we can add a new function to write the email with our second crew so let's do that。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_29.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_30.png)

Here we are adding a new function called write email that is listening to the future leads。

 So once future leads is done， this right email is only going to get the leads that have a score above 70 and then for a dose。

 we're going to call or email writing crew We're calling kickoff for each again because this is an array of leads and we want to perform this crew for every single one of them And this is going to return a list of emails。

 So those emails should be ready to send。 So if we wanted to send them right away。

 we could add a new function that is listening to write email that we can call send email that basically we can send all these emails to us。

 This is the final function off the flow So whatever it returns is going to be the final return off the flow itself for the sake of making them simple。

 we're just going return the emails。So this is a flow and it's very straightforward to set。

 as you can see in order for you to execute this， you can basically start by creating an instance Off flow。

😊，Or flow is called sales pipeline， so I'm going to create an instance of that and assign that to a flow variable。

Now， before we execute this flow， we can actually plot it out so that we can see what this flow actually looks like。

 so let's do that next。😊，Bloting the flow is super straightforward All you got to do is call the plot function in your flow instance。

 and that will automatically generate an HTML that has your entire flow for you to look at。

 so let's go ahead and do it。Now that we have plotted our flow。

 we can actually load this HTMLM in here so we can see what that looks like， so let's do it。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_32.png)

In here， you can see your entire flow。 You can see how it start with the that leads function。

 then it calls the score leads。 After score leads， it does two things。

 It store the leads into a database and filter leads for the ones that are above 70 After that。

 it writes the emails and then send them。 you also have a nice legend in here that it shows you how to read this entire chart so that you understand everything that is going on with your flow。

 This is very good for you to export and have it on your flow to attach it to your Github repository or even to understand or export to others what is going on with your flow execution。

 We are very excited about the fact that you can export your flows visually if you want to。😊。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_34.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_35.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_36.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_37.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_38.png)

Now let's look at actually running this flow and then checking some of the metrics behind it。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_40.png)

Kicking off your flow is very similar to kicking off a crew All you got to do is call the kickoff function on your flow variable and we're using a weight here to make sure that we wait for the flow execution and the reason why we're doing this is because a lot of these functions can be executed asynchronously and you want to make sure that we assign the Finder result into this emails variable so that we can actually inspect some of the round numbers so let's go ahead and kickoff or flow。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_42.png)

So ourfo very quickly facts data from the database and then we can already see its processing to do the lead enrichment and lead scoring So you can see that it got the information about myself。

 my job title， the company and from that point on， it starts to search the internet to find more information about the time that it was at Clbe。

 Let's tang along this execution。

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_44.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_45.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_46.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_47.png)

Here you can see the final answer for our lead data specialist。

 you can see there is a very comprehensive data report with my name， the title， the road relevance。

 some professional background， and some detail about the company including the industry。

 the company size， the revenue and even the market presence let's keep tagging along the execution。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_49.png)

Our second agent， the culturaltrofe analyst， give us also another assessment。

 including a culturaltrofe score and then some tasks to support the analysis and overall comments about ClB Now our final agent。

 the lead score validator comes in。 so let's check that out。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_51.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_52.png)

So our lead score validator give us a full blown report on the final score of 85 and then some scoring criteria。

 some information about the company， about the market presence。

 the cultural fit and even some validation notes。 All this information is going to be turned into those objects that we created early on in the beginning of the lesson。

 So we have a very structured output of everything that we learn about this lead and this company。

 Now， let's keep tagging along our flow execution。😊。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_54.png)

Here we can already see our second crew kicking off with the email content rid and then follow up with the E optimization specialist。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_56.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_57.png)

So we got our final email in here， we can look at that in a second。

 let's first look at some of the metrics and how much it cost us to actually execute Du flow。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_59.png)

So let's first look at how much it costs to execute our score crew。

 so we're going to be looking into that flow state variable and this is very interesting because your flow state is persisted on your initial flow。

 so whatever information was added to the state during the flow execution can now be accessed afterwards as we are doing here。

 assessing the initial score crew results to look into how many tokens were used to get to that data enrich Richment in lead scoring process。

And here we can see that the value was 0。015， and we can see how many tokens were used for pro and for completion tokens。

Now that we know how much it costs for quarterly， let's see how much it costs us to actually write the email This is basically looking at the final result offer flow into that emails variable so that we can see how many tokens were used and we can see that for the email it costs us 0。

0003 cents to actually generate the email so it's very cost effective in a way。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_61.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_62.png)

Now， let's explore all the data that we're able to get for this lead so that we can see some of the information that our agents were able to infer and define。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_64.png)

So before we do this， I'm going to be throwing our score query results into this variable called scores。

 so it's easy for us to access and to plot things out。

 Now let's basically convert all the data that we found in the pentic models that we created into appendda data frame so that we can actually plotted out and see everything that we found about this lean。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_66.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_67.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_68.png)

So in here you can see some information like the job title， the role relevance。

 you can see the market presence， the lead score， and even like some information around the scoring criteria and the validation。

 so this looks very interesting and if we spend some extra time with our agents and tasks。

 we can definitely tune this to be even better so that we can get all the information that we need into this final result。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_70.png)

Now let's look at the actual email。

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_72.png)

So to look into the email， I'm going to actually just print out what was the final result of our flow and you can see that I got my name right and it mentions Cr AI。

 it talks about the orchestration platform and even talks about streamlining workflows and more you can see there's also some links to schedule demo or download use cases now that is very interesting and we would need to replace that with the actual links but we can also spend some time with our agents at tasks to make sure that outputs exactly what we want but in here you can see how super fast and straightforward that is to build an entire sales pipeline that can not only enrich data and score leads but also write emails for them Now this was a very interesting use case for flows but you can do way more complex use cases So how complex can it get let's take a look on if we build a more。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_74.png)

What that would look like？

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_76.png)

So for this use case， we're going to be building a more complex flow。

 It's going to start similar to our initial one， but we're going to be expending it in a few different ways to show how capable flows are。

 Let's start by importing the classes and functions that we're going to need。

 One thing that you're going to notice is that we importing new functions。

 the end the or in the router function， and we're going to use all of them in our new sales pipeline flow。

So this flow is going to start exactly like our initial one。

 where we're going to have a start function that is fetching the leads。

 we're going to have a score leads function that's going to be executed right after that。

 and then a stored leads a score that's going to be executed right after that as well。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_78.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_79.png)

Now we're going to make sure that we filter our leads and that's going to be exactly like what we did on our initial sales pipeline。

 where are filtering out for anything that has a score less than 70。

 But here is where things get a little more complex。 We're actually going to add a new function。

 and this function is going to be using this end function annotation that allows you to wait for two other functions to be done before it kicks off。

 So this long leads function is going to wait for the future leads function to be done。

 and the stored leads score to be done before it gets executed。

 This allows for very interesting use cases because let's say that the future leads happens super fast。

 Reoring the leads score into a database takes a little longer。

 You don't have to worry about that because this long leads function is only going to get executed。😊。

After these two functions are done， so you can see how that unlocks more complex use cases that you could do in there。



![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_81.png)

Now we're going to add another function that is going to be a router and the router here is super interesting because it allows you to give multiple pathways for your flow to go。

😊，So you can see that we are still listening to the future leads function。 So once that is done。

 discount leads function will kick off and it can go in three different paths。 We call this high。

 medium and low。 We could call it anything else。 We just choose this name for the sakes of an example。

You can see that we are getting our scores here after they being filtered and what we' are checking is how many leads we got with such a high score If there are more than 10。

 then we want to return high if it's more than5 then return medium and if it's five or less leads。

 then we return low， then allows us to listen to those different paths to execute different functions。

 so let's look at that。

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_83.png)

Here you can see that we are listening to those three different paths。

 so if our count leads actually return high， then we're just going to execute the store in Salesforce function where we're just going to push these leads into salesesforce is to return medium because we have more than five leads by less than 10。

 then we're just going to send them directly to the sales team。

But if there is not too many leads like five or less。

 then it's going to go to the low path where we're going to write the email using our crew the same way that we used to do before。

And if we go the path of writing the email， let's not forget to add a final function that will listen to that and then actually send those emails out。

This is very interesting and you can see how the combination of routers， listenings。

 ends and Rs allows you to build super complex flows。

 and then you can bring crews in the middle of to do everything that you have been doing with crews throughout the entire course。

 This allows you to execute regular Python code before， during or after your crew executions。

 unlocking so many interesting use cases。 Now， let's plot this new flow so that we can see how it looks like。

😊。

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_85.png)

To plot this flow， we're going to do the same thing that it before where we create an instance off your flow class。

 and then we call the plot function into that， so let's do that now。

Now that generated an HTML that we can actually plot in here in order for us to see what that flow looks like。

 So let's check it out。 You can see that this flow is way more complex there's a lot going on in there we start with fetching the leads and then scoring them after we score them we store them in the database and with future for the leads with a high threshold after these two functions are done we log the leads so we get confirmation that things worked out and you can see that this is an end condition because of the dot lines you can also find out this information by looking at the legend here below so you can see this is an end trigger that is waiting for these two functions to be done before actually executing the log read function。

😊。

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_87.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_88.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_89.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_90.png)

And then it execute our count leads function that is actually a router。 And depending on how it goes。

 it can go three different paths。 either store them in Salesforce。

 send them to the sales teams or write an email。 But once it writes the email。

 it' is gonna execute the send email function。 Honestly， this is so exciting。

 because you can build so many different use cases in here。 And this is the best of both words。

 where you have crews disc scoring or leads and writing or email。

 But now it's easier than ever to execute regular Python code before during or after your crews executions。

 So this is very exciting。 Now， I want to show you more and how you can build more with crew。

 So let's jumping to our next lesson where we're gonna dive even further。

 And you're gonna learn more on how you can unblock complex use cases in production using crew AI。

 I you see in a second。😊。

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_92.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_93.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_94.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_95.png)

![](img/d4e05605ddc4eb0f5b18ffc1cb17a648_96.png)