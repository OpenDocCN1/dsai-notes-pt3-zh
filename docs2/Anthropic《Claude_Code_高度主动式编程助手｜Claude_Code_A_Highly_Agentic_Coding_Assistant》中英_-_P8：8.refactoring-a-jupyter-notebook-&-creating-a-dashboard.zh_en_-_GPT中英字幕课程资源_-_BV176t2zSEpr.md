# Anthropic《Claude Code 高度主动式编程助手｜Claude Code A Highly Agentic Coding Assistant》中英 - P8：8.refactoring-a-jupyter-notebook-&-creating-a-dashboard.zh_en - GPT中英字幕课程资源 - BV176t2zSEpr

![](img/4b2246b9cd2a372c5004c251919f927c_0.png)

Cloudcode has tools for reading and editing Jupiter notebooks in this lesson。

 we'll go through our second example and use cloud code to refactor a Jupiter notebook transform it into a dashboard。

 Let's get to it。 So far， we've seen how to use cloud code to work with Web applications on the front end and back in。

 Now， let's shift gears and showcase how to use cloud code to work with a Jupiter notebook。

 I have a Jupiter notebook here with some ecommerce-commerce data that is fictitious。

 This e-commerce data is reading information from a few Cvs that I have in this ecommerce-commerce data folder。

 I'm using pandas to read data from the Cv。 I'm displaying some information here reading some other Cvs。

 and as you can see here， I'm getting the answers that I want。

 but this data is not really the most organized。 I'm getting some statistical information but the formatting and the display might not be what I'd like out of the box。

 As I go through and take a look at some more of this information。

 I can start to see that I'm beginning to do。😊。

![](img/4b2246b9cd2a372c5004c251919f927c_2.png)

![](img/4b2246b9cd2a372c5004c251919f927c_3.png)

![](img/4b2246b9cd2a372c5004c251919f927c_4.png)

![](img/4b2246b9cd2a372c5004c251919f927c_5.png)

![](img/4b2246b9cd2a372c5004c251919f927c_6.png)

![](img/4b2246b9cd2a372c5004c251919f927c_7.png)

![](img/4b2246b9cd2a372c5004c251919f927c_8.png)

Some more complicated procedures here One of the things that I'd like to get out of this data are some insights around things like how much revenue did we generate year over year specifically 2023 to 2022 I have the necessary operations here to do what I want。

 In fact， there's a little bit of merging between two different csvs and data frames and here I'm working my way towards the answer that I want but there are some warnings that I'm seeing here and at the same time it takes a while just to show visually what I want and how best to display it。

 So while I do end up getting the numbers that I want it's a little bit tedious and messy。

 I want a way to better showcase this information and I want to explore how I can refactor this Jupiter notebook as we see in a few other sections I'm trying to calculate some highlevel metrics like average order values and not only am I looking for this number but this is just for 2023。

 What happens when I want 2024 and so on as we scroll down。

 we'll see some visualizations that are pretty good but I think we could do better as we work our way towards the bottom。



![](img/4b2246b9cd2a372c5004c251919f927c_10.png)

![](img/4b2246b9cd2a372c5004c251919f927c_11.png)

![](img/4b2246b9cd2a372c5004c251919f927c_12.png)

![](img/4b2246b9cd2a372c5004c251919f927c_13.png)

![](img/4b2246b9cd2a372c5004c251919f927c_14.png)

![](img/4b2246b9cd2a372c5004c251919f927c_15.png)

![](img/4b2246b9cd2a372c5004c251919f927c_16.png)

![](img/4b2246b9cd2a372c5004c251919f927c_17.png)

![](img/4b2246b9cd2a372c5004c251919f927c_18.png)

![](img/4b2246b9cd2a372c5004c251919f927c_19.png)

![](img/4b2246b9cd2a372c5004c251919f927c_20.png)

Calculating more of these highlevel values like sales by state we're generating some visualizations again。

 but I think we could do much better as we start to use tools like Cla code。 So with that in mind。

 let's showcase how we can use cloud code to refactor this notebook and better consolidate our business logic from our presentation I'm going to go ahead and open up Cla and I'm going put in a prompt that I have here that references the notebook as well as the other files that I'm working with。

 I'm going go ahead and paste in this prompt。 and then I want to talk a little bit about what's actually happening here。

 So before I paste in this prompt I'm actually going make a new markdown file just to showcase what this looks like and walk through why we've done what we're doing here。

 notice here I'm referencing the name of the file using this sign as well as the name of the folder using this as well if you're ever unsure of how best to prompt or how best to ask Claud for what to do you can always ask Cla as well So many times I find myself using tools like cloud AI or even cloud code and just asking Clade。



![](img/4b2246b9cd2a372c5004c251919f927c_22.png)

![](img/4b2246b9cd2a372c5004c251919f927c_23.png)

![](img/4b2246b9cd2a372c5004c251919f927c_24.png)

![](img/4b2246b9cd2a372c5004c251919f927c_25.png)

Here's what I want to do。 Give me the best possible prompt to accomplish this task。 In our case。

 we have some refactoring requirements for how we want the structure to be laid out。

 We have code quality improvements and some asks that we have for a particular python files that we want。

 What we're asking Clade to do here is create a separate python file for loading our data and processing it。

 and then another python file for calculating these metrics。 this separation of concerns。

 it's going to allow us to better test and better understand what the code is that's powering these visualizations that we make in our refactored notebook we're also asking for improved visualizations。

 we're being a little bit more specific with what we mean by that。 Finally。

 we want to have a little bit more configuration around the data that we're working with。 In general。

 it's a good practice to let Claude know what you're expecting here。

 So instead of just refactor this。 Give me an underlying asset for a refactored notebook give me a way to document by functions and calculate my business metrics。

😊。

![](img/4b2246b9cd2a372c5004c251919f927c_27.png)

![](img/4b2246b9cd2a372c5004c251919f927c_28.png)

![](img/4b2246b9cd2a372c5004c251919f927c_29.png)

![](img/4b2246b9cd2a372c5004c251919f927c_30.png)

![](img/4b2246b9cd2a372c5004c251919f927c_31.png)

And then give me some other important files for the dependencies I'm working on。

 as well as a readme explaining how to use this。 So let's go ahead and copy this and paste it in and you'll notice that after you paste a certain number of lines。

 cloud code is not going to show you everything to keep things a little bit more concise in the terminal。

 So let's go ahead and run this prompt as we've done with other kinds of tools we're going to be using a slightly different suite of tooling here instead of reading。

 we're going to be dealing with notebook reading， but the same to do list that we saw before。

 it's going to be executed just like we've gotten very accustomed to with cloudcode here we're using that read notebook。

 we're going to explore those cells， we're going to analyze the structure and create the refactored notebook that we expect once this is done。

 we should expect to see not only some powerful visualizations but also some other files with helper functions for loading data processing data and calculating the business metrics that we need。



![](img/4b2246b9cd2a372c5004c251919f927c_33.png)

![](img/4b2246b9cd2a372c5004c251919f927c_34.png)

![](img/4b2246b9cd2a372c5004c251919f927c_35.png)

![](img/4b2246b9cd2a372c5004c251919f927c_36.png)

![](img/4b2246b9cd2a372c5004c251919f927c_37.png)

![](img/4b2246b9cd2a372c5004c251919f927c_38.png)

![](img/4b2246b9cd2a372c5004c251919f927c_39.png)

![](img/4b2246b9cd2a372c5004c251919f927c_40.png)

![](img/4b2246b9cd2a372c5004c251919f927c_41.png)

![](img/4b2246b9cd2a372c5004c251919f927c_42.png)

![](img/4b2246b9cd2a372c5004c251919f927c_43.png)

Except the changes to these Python files。 And we'll see that Python is being written for us using the right tool。

 We'll then go ahead and write another python file with metric calculations for our eventual data and display as cloud code is working through these individual tasks。

 We can always examine the files that have been created we can give that a look。

 and we can see right out of the box。 this kind of object oriented approach is much cleaner than trying to embed everything directly inside of our notebook。

 We can see the same thing for our business metrics calculation。

 And we can see here the ability to calculate passing in data frames and returning visualizations and validation of that data。

 It looks like we've created our business metrics。 And finally。

 our notebook our requirements Txt and soon to be our read me。 So while this is running。

 let's take a look at the refactored notebooks go ahead and make sure we can run all of these cells as expected right off the bat。

 This is looking a bit nicer visually for us。 I see here that is trying to read the prompt。

 and I'll just let cloud。😊。

![](img/4b2246b9cd2a372c5004c251919f927c_45.png)

![](img/4b2246b9cd2a372c5004c251919f927c_46.png)

![](img/4b2246b9cd2a372c5004c251919f927c_47.png)

![](img/4b2246b9cd2a372c5004c251919f927c_48.png)

![](img/4b2246b9cd2a372c5004c251919f927c_49.png)

![](img/4b2246b9cd2a372c5004c251919f927c_50.png)

![](img/4b2246b9cd2a372c5004c251919f927c_51.png)

![](img/4b2246b9cd2a372c5004c251919f927c_52.png)

![](img/4b2246b9cd2a372c5004c251919f927c_53.png)

![](img/4b2246b9cd2a372c5004c251919f927c_54.png)

No need to read the prompt。 just finish making the readname As I take a look at this notebook I can see right out of the box。

 This is much， much nicer and getting analysis into what data I'm looking at and also some configuration to work with I can specify the years and comparison data and even any month if I want as well I'll be using these constants across the notebook I can see the data loading that's required here the custom modules that I have from my classes as I'm running all of these cells looks like things are pretty good so far but if I scroll down a little'll actually see that there's an error can see right off the bat the problem here appears to be some kind of key error'm going ask cloud to fix that me''m getting key error when I run a particular cell I could try to have cloud code figure that out for me but I'm actually going to give cloud code the code that I used it has a little more context Cloud code is going take a look at what needs to be done see what the issue is and make the change for's go ahead and run these cells now that changes have been made let's go make sure that things are looking a bit better can see here as I scroll down I not seeing。



![](img/4b2246b9cd2a372c5004c251919f927c_56.png)

![](img/4b2246b9cd2a372c5004c251919f927c_57.png)

![](img/4b2246b9cd2a372c5004c251919f927c_58.png)

![](img/4b2246b9cd2a372c5004c251919f927c_59.png)

![](img/4b2246b9cd2a372c5004c251919f927c_60.png)

![](img/4b2246b9cd2a372c5004c251919f927c_61.png)

![](img/4b2246b9cd2a372c5004c251919f927c_62.png)

![](img/4b2246b9cd2a372c5004c251919f927c_63.png)

![](img/4b2246b9cd2a372c5004c251919f927c_64.png)

![](img/4b2246b9cd2a372c5004c251919f927c_65.png)

![](img/4b2246b9cd2a372c5004c251919f927c_66.png)

![](img/4b2246b9cd2a372c5004c251919f927c_67.png)

That I was before。 And now let's take a look at some of the business metrics that it's returning to me。

 Getting nicer displays of summaries， information on customer satisfaction。

 That's a little bit easier to work with than what I had before as we shift gears towards our revenue analysis。

 we can start to see clear values displayed information and a little bit of work to more easily display the data we're working with visualizations appear to be more pleasant looking we can see as we look at category performance。

 we've got some even better tools to analyze categories and revenue associated with them as we look at our geographic performance。

 We're seeing a nice visualization by state。 we can hover over that to get even more information on a state by state basis as we work our way to the bottom。

 we take a look at initial delivery analysis， things are looking good as expected。

 So we've done a nice job refactoring this notebook to more visually display information and separate our。

 But what I'd like to do now is move from a notebook to a webbased interface with a nice dashboard powered by streamlit if you're not familiar with streamlit。

 It's a Python library that's useful。😊。

![](img/4b2246b9cd2a372c5004c251919f927c_69.png)

![](img/4b2246b9cd2a372c5004c251919f927c_70.png)

![](img/4b2246b9cd2a372c5004c251919f927c_71.png)

![](img/4b2246b9cd2a372c5004c251919f927c_72.png)

![](img/4b2246b9cd2a372c5004c251919f927c_73.png)

![](img/4b2246b9cd2a372c5004c251919f927c_74.png)

![](img/4b2246b9cd2a372c5004c251919f927c_75.png)

![](img/4b2246b9cd2a372c5004c251919f927c_76.png)

![](img/4b2246b9cd2a372c5004c251919f927c_77.png)

Dissplaying interfaces， particularly dashboards。 and it's very easy to seamlessly transition from notebooks to these Python files。

 So let's go ahead and make a new markdown file with our prompt that we'll call convert to dashboard M。

 and let's walk through what we're gonna to put in here。

 We're gonna ask Claude to convert our refactored notebook into a professional streamlit dashboard with this exact layout。

 We could start just with this purse line。 But in order to avoid lots of back and forth。

 let's just tell Cla what we want We want a header with a title and filter we want Kpis with cards for revenue growth toward average order value and total orders。

 and then we want some charts revenue categories， revenue by state and a bar chart with satisfaction at the bottom row。

 we want two cards。 and we want to be specific for the way in which we display our data and render this information。

 So with that in mind， let's go ahead and give us a shot。

 let's migrate from notebooks to visual interfaces using streamlet。

 We can see that is created our dashboard。 And as it's going。

 we can take a look at what's being done here。😊。

![](img/4b2246b9cd2a372c5004c251919f927c_79.png)

![](img/4b2246b9cd2a372c5004c251919f927c_80.png)

![](img/4b2246b9cd2a372c5004c251919f927c_81.png)

![](img/4b2246b9cd2a372c5004c251919f927c_82.png)

![](img/4b2246b9cd2a372c5004c251919f927c_83.png)

![](img/4b2246b9cd2a372c5004c251919f927c_84.png)

![](img/4b2246b9cd2a372c5004c251919f927c_85.png)

![](img/4b2246b9cd2a372c5004c251919f927c_86.png)

We're importing streamlit， bringing in pandas， bringing in some visualizations， including plotly。

 And then here you can see we're displaying some custom CSs for our styling。

 setting up our page configuration。 Most of this really comes from that S object that I have to work with streamlit。

 We update our requirements TXT and here we're actually going create or read me displaying everything that's going on in the dashboard。

 In fact， I'll just tell Cla right now， don't make a new readme。

 just modify the one we have in many of these longer plans it's very easy to just let cloud go。

 But sometimes you want to stop the process。 and have it navigate the way that you will Now that we've created this dashboard let's open up a new terminal window to start our server in this terminal window on the left。

 I'll start the server using streamlit run and then the python file that's going to be displayed dashboard。

 We can see here that I don't have the streamlit command。

 So I can see here in order to get everything up and running。 I need to install these dependencies。

 So let's go ahead and do that。 I'll run my Pip install。😊。



![](img/4b2246b9cd2a372c5004c251919f927c_88.png)

![](img/4b2246b9cd2a372c5004c251919f927c_89.png)

![](img/4b2246b9cd2a372c5004c251919f927c_90.png)

![](img/4b2246b9cd2a372c5004c251919f927c_91.png)

![](img/4b2246b9cd2a372c5004c251919f927c_92.png)

![](img/4b2246b9cd2a372c5004c251919f927c_93.png)

Command， install all the necessary dependencies and make sure that when the server loads。

 I don't have any issues with the dependencies in this application Once that's done。

 I'll go ahead and run my server and I'll do that using the streamlit run command so let's go ahead and type in streamlit run in the name of our Python file just like it suggests right here back in the browser Here's what things look like I've got some revenue I've got some growth as we scroll down a little bit we're definitely going want to verify that these numbers are what we expect and we see that some things are still missing a little bit when we take a look at this dashboard it's a pretty good start but we can see that we're missing a couple things。



![](img/4b2246b9cd2a372c5004c251919f927c_95.png)

![](img/4b2246b9cd2a372c5004c251919f927c_96.png)

![](img/4b2246b9cd2a372c5004c251919f927c_97.png)

![](img/4b2246b9cd2a372c5004c251919f927c_98.png)

![](img/4b2246b9cd2a372c5004c251919f927c_99.png)

![](img/4b2246b9cd2a372c5004c251919f927c_100.png)

![](img/4b2246b9cd2a372c5004c251919f927c_101.png)

It looks like these cards here are empty and actually redundant because we're getting the information that we want。

 At the same time， it's a little difficult to start with 2024 because we're not seeing much information year over year。

 So maybe we should ask Claude to not only clean up these pieces。

 but also start with a default year of 2023。 So we can have some slightly nicer visualizations。

 but also make sure we have the ability to filter based on the month as well。

 The reason why we'll want to start with 2023， is because we don't have data for every single month for 2024。

 So as we start to look at this， the monthly growth is a little bit。



![](img/4b2246b9cd2a372c5004c251919f927c_103.png)

![](img/4b2246b9cd2a372c5004c251919f927c_104.png)

![](img/4b2246b9cd2a372c5004c251919f927c_105.png)

![](img/4b2246b9cd2a372c5004c251919f927c_106.png)

![](img/4b2246b9cd2a372c5004c251919f927c_107.png)

![](img/4b2246b9cd2a372c5004c251919f927c_108.png)

Confusing and the data here we just don't have yet。



![](img/4b2246b9cd2a372c5004c251919f927c_110.png)

So let's go make those asks。 put them back in Claude。 This is a good start。

 but I want to implement the following changes。 Let's go ahead and make a new line here。

 And first we'll start with making sure the default year is 2023 next ask Cla to add filters for months as well。

 And then finally， we'll make sure to remove the empty card for each。

 So let's update the code in our dashboard for these particular husks。

 We'll set the default year to 2023， which looks good。 And here we'll add some filters for months。

 Now let's take the revenue chart to handle the case where we're filtering by a specific month。

 We can see the Cs is changing as well。 So it looks like this chart container should be a little bit cleaner than before。

 Let's go back to the browser see what things look like。 We can see that 2023 is the default。

 which is a good start。 We can also see that those empty cards are gone， which is great。

 We'll stop here for now， but you can imagine as you keep prompting。

 you can create more powerful visualizations but in a short period of time。

 we started with a notebook that was a bit。😊。

![](img/4b2246b9cd2a372c5004c251919f927c_112.png)

![](img/4b2246b9cd2a372c5004c251919f927c_113.png)

![](img/4b2246b9cd2a372c5004c251919f927c_114.png)

![](img/4b2246b9cd2a372c5004c251919f927c_115.png)

![](img/4b2246b9cd2a372c5004c251919f927c_116.png)

Disorganized was a little hard to read and understand。

 and we've migrated now to a dashboard that we can deploy。

 share with team members and iterate on quickly in the next lesson we'll build a next JS application and use Cloud code to connect to MCP servers for Figma and playwright to take a mockup and build a powerful web application with cloud code quickly。



![](img/4b2246b9cd2a372c5004c251919f927c_118.png)