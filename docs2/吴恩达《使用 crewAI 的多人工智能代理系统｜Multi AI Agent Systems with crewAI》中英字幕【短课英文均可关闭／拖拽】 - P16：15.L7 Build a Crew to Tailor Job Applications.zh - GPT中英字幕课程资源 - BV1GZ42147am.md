# 吴恩达《使用 crewAI 的多人工智能代理系统｜Multi AI Agent Systems with crewAI》中英字幕【短课英文均可关闭／拖拽】 - P16：15.L7 Build a Crew to Tailor Job Applications.zh - GPT中英字幕课程资源 - BV1GZ42147am

![](img/21e20c9e15fb7f73e3acf247dbc2600b_0.png)

Alright， so you just learned a lot about agents。 We talking about all the different features。

 but this lesson is super important because this lesson we're going full circle。

 we're basically going back into lesson one and talking about that use case that we showed up where we're going to help you build this agent that will help you apply for jobs。

 This agents are going to be able to look at the job postings。

 understanding its requirements and then cross that over with your current resume and your skills and make sure that we are tailorm your resume to apply for this job。

 It's a very interesting use case and we're going to get the chance to apply everything that we learned so far。

 So let's look into that。

![](img/21e20c9e15fb7f73e3acf247dbc2600b_2.png)

So in this lesson we're going to be building a super interesting crew。

 we're going full circle to the crew that we mentioned in the first lesson。

 we're going to be building a crew that will help us to increase our odds of getting an interview by tailor making or resume for a specific job application I'm so excited about thisHonestly by now you already understand that this is the future of work and engineering and I truly believe that AI agents are a key part of the future businesses and how you as an engineer can drive an immense impact on your job and your career。

So let's talk about this crew， what is the process and what is the go。

 we talk about these in other lessons， so let's dive right into that。

So what is the go The goal is to maximize your chances of getting an interview for a event job posting and the process throughout we are able to achieve that is one learning the job requirements。

 then two crossing those requirements with your specific skill set and experiences and then we reshape your resume to highlight the relevant areas and then we rewrite that resume with the appropriate language and then as a bonus。

 we can also have the crew set some talking points for initial interview。

 something that you can read before jumping into the call and that will help you understand how you can better highlight your skills in a way that makes you look good for that job position So let's jump right into the code Allright so let's get the boilerplate code out of the way making sure that we don't get any Warners and that import or treatment main classes。

 the agent， the task and the crew class。Now we have those three classes right for us。

 let's make sure that we also add our environment variables so that we set what models we're going to be working with。

 In this case， we are using GT4 Trbo and you're going to notice that we are using Surer daav again you're going to be provided with a key or you're going to be able to create an account and get a key from there。

Allright， now let's focus on the toolss that we are going to be using and there is a set of different tools that we're going to be using for this one。

 All of those tools are coming from the queryi package tools and you can see there are four of them。

 there is the file re2 There's the scrape website to There is the MDX search tool and there is the Cp dev2 let's go over each one of them So the search2 we already know about that allows us to search the internet The scrape2 we also have used it allows to scrape a website content。

 The read resume2 is using the file re2 and making sure that it only allows the agent to read one specific file In this case is a fake resume that is right as a markdown and I'm going to show you that file in a second and then the final two is the MDX search2 This allows us to perform rag over or fake resume。

So we can do semantic search over anything that is in our resume。

 So let's create those toolss and look at those files。 Alright。

 so let's start by looking at this fake resume file so that we can see what we are working with This is what the fake resume file looks like and all of this is made up So in this case we have or buddy Noah Williams and you can see in here Noah's profile。

 its work history， everything that they have been up to throughout his career。

 you can see that it has an MBA。 it knows a lot about leadership and it has like been calling up his leadership achievements throughout his entire resume。

 you can see that it defines himself as a software engineer leader and talks about how it excelleed in leading both remote and inoff engineering teams So you can see that this is more of a profile for someone that is applying to a manager role is。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_4.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_5.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_6.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_7.png)

Okay but if you look further， you're gonna realize that Noah Williams also is a very good engineer。

 He has experience with Ruby Python， jascript， Typescript。

elixir and you're going to find that in his work history There's a lot of amazing gems of technical work that he has build throughout his career but is not being highlighted in the right way again。

 depending to what job he might be applying all let's go back to our code So now that we have or two let's start creating our agents and for this crew。

 we're going to create four different agents The first one it's going to be a researcher agent So let me copy this and just pasted in here。

 So this agent is a tech job researcher It goes is to make sure that it's doing analysis on the job posting It's basically trying to understand what are the needs behind that job posting What are their。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_9.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_10.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_11.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_12.png)

What are the company trying to achieve with that job posting。

 what is the kind of person that they're trying to hire so this is what this agent is going to be responsible for now let's create our second agent or second agent is a profiler。

So this profiler basically do a research on the job applicants and try to understand some of the crossover。

 So looking at the resume and the job posting。 What are the things that stands out in there that makes this person actually looks like a good match for this job opening。

 So this agent is going to be very important in this crew because it's going be the one that's going to highlight the things that we want to really pop up。

 So now let's go for a third agent or third agent is a resume strategist。

 it's the one that's an actually updated resume。 It's going learn about the job posting。

 It's going to learn about the ss that the person has and it's going to have found around the intersection So it's not going to write that down。

 You can see that among our three agents， all of them have access to a few set different of twos。

 The resume strategist one is going to be able to。the Internet， search the Internet。

 read the resumes and do a semantic search over the resume so it's a very capable agent On top of that。

 we need one final agent。 We want one agent to help us to prepare for the coming interview so this is the engineering interview preparer This agent is gonna one set of things wrap up make sure to put together questions and answers and talking points that we want to come prepared to when going to this interview assuming we get it it's a great way for us to make sure that we are feeling confident and that we know that we can highlight our skills in a way that makes sure that the employer understands that we are a good fit for that job opening so now that we have created or four agents we are ready to create our tasks and were going use four different tasks one task for every agent and you can already see some of the interpolation going on here。

 you can see that we expect a job posting URL。The second task is the profiling task is the task that is actually responsible to cross some information about you that you're trying to apply to this job and the actual job position。

 So you can see that in here， there are other variables that are being interpolated like a Github URL and even like a personal note on some of the things that you have been doing as a professional。

 So that is also something that we're going leverage in here。

 Now for the third task we're gonna do a resume strategy task。

 This task is gonna to be the one responsible for actually updating the resume。

 And you can see here that we're outputting a file out of this task。

 So we're going have a new file at the end of the screw that is going be your tailored resume so we are going to start from your actual resume and we're gonna have a new one that is now optimized for that job posting so we can go ahead and create that task。

And now our final task is the one that is going to help you prepare for the interview it's going to put together the talking points relevance to the job posting so that you feel ready for that and you're going to notice that this task is also writing its results into a file in this case the interview materials marked down file and you're going to be able to look into that later once that this group finishes up。

Okay， we created all of our tasks， now it's time for us to put this crew together。

 so let's start by creating our crew and bringing all the agents and all the tasks within it。

Now that we have the screw before we quick it off， we learn to make sure that we cover all the inputs and all the interpolations that we expected through all of it。

So in this case， that's quite a few， let me paste them here。

So you can see that we expect a job posting URL， a Github URL in a person writeup where you can explain a little bit about yourself with a few words and the things that you think that make you suitable for this job posting Allright so now that we have our inputs ready before we kick this crew off let's go back to the tasks just so that we fully understand what is happening with the crew this is going to be a very interesting exercise for us。

So let's look at our tasks。 if you look at the research task。

 you're going to notice that it's allowing us to execute that task in parallel。

 What means that we're going to have one agent working on that at the same time that we're going to have another agent working on the next task。

 the profile task because you can see that also has the S execution set to true so you can see that in this case we're going to have one agent doing research and the job posting at the same time that we're going to have another agent doing a research on your profile So this is great because we're saving on time by making this crew execute faster because those two tasks can be executed in parallel but then for or task the resume strategy task we want to make sure that it's using the output from both tasks that happen beforehand so that these tasks can get the result off the resume research。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_14.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_15.png)

But also from the job application research and you can see that we do this here on this context argument where we basically say that the context for this task。

 it's actually those two tasks that were executed above so even if the profile tasks finishes executing earlier and the research tasks is still going on the resume is strategy task is going to wait until both of those tasks finish it before it can actually move on and use those context in order to come up with a new strategy for your resume。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_17.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_18.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_19.png)

All right， so now that we understand what is going on， let's go ahead and kick off our crew。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_21.png)

So in here you can see that two tasks are initiated in parallel or tech job the researcher is to start to doing its work and the personal profiler for engineer it also started to doing its work。

 so both are doing the work in parallel as expected let's see how they're doing。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_23.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_24.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_25.png)

So you can see that one of them are doing the compilation on the profiles for NOAA it's basically trying to check GitHub's contributions。

 looking at the website to kind of like do some scraping on that and you can see that it's going to try to get as much information from that URL as possible you can also see that our other agent is actually scraping the job posting and trying to learn as much as it can about what are the actual posting and the actual needs for that job so let's take along and see how that goes。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_27.png)

Alright， so you can see here now that one of the agents finish up its work。

 it now understands all the necessary skills for these job posting。

 it understands the qualifications that this person must have， the experiences that are expected。

 and also the characteristics of what would be a good match for disposition position。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_29.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_30.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_31.png)

So now that we understand all that， we can see if our other agent already finished its research as well。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_33.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_34.png)

All right， we can see that our other agent also finished up the research inOAA and now it knows everything think about NOAA。

 it knows its excuse what it has been up to what are the languages that it's most proficient about and what are the things thatOA's interest in so now we can have or resume strategy agent kind of bring those two set of informations together to write you a tailormade resume for this job posting so let's see how that goes。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_36.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_37.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_38.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_39.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_40.png)

So in here we can see that our agent starts by reading the original resume so it understands everything that's in there and it's going to use that as a starting point you can see that it now rewrote the resume to highlight the main things that's going to make no one look like the best match possible for this job posting and by the end of this you can see that now the engineering interview preparere is kind of building the questions and some of the talking points that you're going to be able to use to prepare yourself for the interview if you get it Allright so this should be most of crew execution let's look at what the actual end files are so let's look at what the tail-made resume looks like。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_42.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_43.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_44.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_45.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_46.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_47.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_48.png)

![](img/21e20c9e15fb7f73e3acf247dbc2600b_49.png)

So you can see if we put it side to side with the fake rasme that it changes things as likely before Noah was highlighting how he was an amazing softwareer engineering leader。

 but now he's highlighting how he is a full stack developer that has a lot of experience with software engineering。

 you can see that he was mentioning some of like the Skus in European Python。

 but it was kind of like buried in there， but in here it's being very clear that he's proficient in multiple programming languages and talking about all of them。

 you can see that before Noah didn't mention some of his knowledge and databases。

 but now it does it mentions that it knows my SQL and MongoDB。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_51.png)

And if we dive into NOAA's work history， we can see how now it's more trimed down to the things that are actually matter for disposition。

 highlighting NoAA's excuse that are better matching the better match the job posting and that make sure that increase his odds of actually getting an interview。

 and we're going to see these changes throughout the entire resume。

 just making sure that it highlights the things that makesOAA looks good。

Now let's check the interview materials， the things that you're going to use to prepare in case you do get the interview。

 This is so good。 you can see in here that it simulates some questions and talks about how you can pre to them and even give you some talking points that would allow you to showcase your experience with specific frameworks or specific languages or database management how things that are deemed relevant for that job posting So with this you should be able to go into this interview feeling confident and prepared to answer any questions that might be thrown your way Now let's go back towards slide real quick so that we can recap。

😊，So we just put together an amazing crew and the reason why I like this crew so much is because it's so practical。

 it helps you directly if you are trying to apply for jobs。

 this is something that you can actually use today and that would increase your odds of actually getting interviews so you should be feeling very proud of yourself from learning everything that you learned so far throughout all these lessons and I'm looking forward to see whether you're gonna to be able to keep beauty with this now that you learn so much about multiple agent systems。

 All right， let's wrap this lesson here and I see you in the next one。😊。



![](img/21e20c9e15fb7f73e3acf247dbc2600b_53.png)