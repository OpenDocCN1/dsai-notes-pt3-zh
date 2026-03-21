# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p29 P29 07_反应式提示 -BV1b6YyzzEP9_p29-

Large language models as powerful as they are， they can't do everything on their own。

 they're going to have to reach out into other data sources and they're to have to learn how to use other tools to be really effective over time。

So one of the things we have to learn how to do is build prompts that can allow the large language model to essentially reach in and query new information to use other tools that can help it do reasoning or computations that it fundamentally is not designed to do And so how do we go about doing that。

 So one way of doing that is with an approach called react。

 So the idea behind this is that we want to teach essentially the large language model how to think through a process and understand steps where it needs to go and use some other tool to take some other action outside of it and get the result of that tool and bring it back in。

😊，As some type of computation or result that it can then incorporate。

 And so there's a specific way of writing prompts to do this。

 Now this is similar to chain of thought prompting like we saw before。

 we're going to use some of those same concepts from chain of thought prompting。

 but we're going to expand the approach to have this concept of certain things that the large language model knows it needs to use some external tool to perform。

 So let's take a look at this。 Now bear with me because this is a longer example。

 we're going to do a single example that we're going to teach。The language model with。

 and then we're going to ask it to perform the same task so in this example。

We have a task which is calculate when I need to arrive at the Music City BMX National race for my son to be on time verse 9 to10 open race so BMX is a bicycle racing sport。

 some of my examples lately have been around BMX and Music City BMX is a local BMX track here in Nashville the house one of the big national races for BMX racing and so one of the things I need to figure out when do I need to show up at the track because these are all day multiday events and sometimes you may want to figure out how late can I sleep before getting in the car and driving then in order to arrive and what happens is in these races。

You have hundreds of inreigual little races that are essentially like 30 seconds each these are called Motos that are run and you want to figure out when you're Moto 87。

 for example， well how long do I need to wait after the start before that race is going to start and so sometimes there's a balance there of trying to figure out when do I need to be at the track actually as opposed to when does the race start？

And so what we're going to do is we're going to have it solve this problem for us。

 so we're going to pretend to solve this problem。 this isn't actually solving it。

 but we're going to show you how this process works。

So we give it a task and we give it an example which is calculate when I need to arrive at the Music City BMX National race for my son to arrive on time for his nine to 10 open race。

And then we say think。I need to find out what time the first race begins。

 I can use a web search of the Music City BMX site to get that information。

 So remember this is our example。 So we're saying here's the thought process。

 I need to first figure out the first step Now you can you remember back to chain of thought where we're trying to have it explain its reasoning when we're kind of doing the same thing we're explaining the reasoning behind it So we're saying I need to find out what time the first race begins。

 we're explaining what we're trying to do。😊，I can use a web search of the Music City BMX site to get that information。

And then we have the next thing we do which we we say action， search。

And then we give the Music City BMX website。And so action here in the search is basically a tool。

That it's learning to use， it's learning to use some external tool， in this case， a web search。

 So it knows that there's certain information it does not have。And so we're teaching it。

When you need information that you don't have， go and search for it and you can search for it with a website。

And then it says the result we tell it is all races start at 9 a。

So then we say think I need to find out how many Mos run before the nine to10 open Mos are essentially the individual races that are going to run before that race。

 I can use a web search of Music City BMX site to get that information and then we show it again another example of searching assuming there's a search tool available to it for the Music City BMX site。

And then result， we show it the result， there are 30 Mos that run before the 9 to 10 open race。

And then we say think。I need to find out how long each Moto took last year。

 I can use the video live stream from the USABMX website and record how long the first 10 Mos took。

 and then we say action video and we give it some fake video and pretend that hey。

 we were able to go and pull this video down in time something。And then result。

 the first 10 Motos took five minutes。Think if 10 Motos took5 minutes，30 Motos will take 15 minutes。

 The race starts at 9 a。 so I need to arrive before 9ine。50 AMm。 when the race starts。

 I will arrive 30 minutes early at 8，45 a to be safe。 So remember， this is our Rfo example。

We've could have imagined a scenario where I need to solve this problem and I'm using a series of web searches and then watching a video from a prior year to figure out how long things took。

 and I'm trying to teach the large language model in this case。

 chatGBT to use these same tools to solve the problem。So then I ask it， you know。

 here's the new task。Calculate what time my 36 to 40 novice race will end at the USA BMX Grand Nationals。

 and then I say think to prompt it to start thinking what is the next step。

And you'll notice what it does， it then says I need to find out what time the first race begins at the USABMX Grand Nationals。

 I can use a web search of the USABMX site to get the information。Action search。

 USABM X events grant。 So notice it's picked up on a couple of things。

 It's picked up on the idea that it has this tool called search that it can use to go and pull in information。

 You'll notice it's also picked up on the format of the URL。 Now。

 this format I had was just completely fictitious in this example。 but it's picked up that， oh。

 there must be this formatting。 There must be a pattern behind these URLs that I can use so I can go and search and use some knowledge of。

😊，The structure of those URLs to pull in the right information。

 So it's learned essentially how to go into a web search and then it says result note as an AI language model I or order to perform web searches。

 please assume a hypo paththetical result of the purpose of this exercise。

 The first race begins at ADM。 Now what's interesting here is if we were actually integrating this into a real system。

 we can have the system whenever it sees a result， stop， pull in the actual result。

Put it in there and then basically feed this first sec chunk back to the language model to then continue the process。

 so we don't actually have to worry about if it's going to fake the rest of this。

 We could just have it go and we could incrementally get to every each time we get a new result out。

That we actually need to fill in we could go and run the web search and fill in that result It then keeps going it says I need to find out how many Motos run before the 36 to 40 Novice race at BMX Grand Nationals I can search and it goes in searches on the grounds and then it has a hypothetical result there are 120 Mos。

Goes and thinks again， I need to find out how long each moto took last year。

 I can use the video live stream， and then it picked up on the URL pattern。 So， you know。

's it's learning a lot of things。 it's learning how to use the tool and how to input data in a particular format for it based on what I showed。

 It then says， okay， here's the result from that。😊。

And then it says think if 10 Mos took six minutes each or took 106 minutes。

 then each mo took an average of 。6 minutes therefore 120 Mos will take approximately 72 minutes the first race starts at8M so the 36 to 40 novice race will start around 912 a I need to find out how long the 36 novice race itself will take and it goes and does that and then it says if the 36 to novice race starts around 2912 then it will end around 15。

 this is the approximate time my race will end at the USABMX nationals and so what's interesting is that it actually end up in the end getting slightly off track it gave me the and end so it's telling me the begin time but it also went and calculated the end time which I may or may not want but the more important thing is is that along the way it followed my pattern up here I taught it this concept of searching so I had。

Action search musiccitybmX。com， I had another action search for musiccitybmx。com。

 I had an action video right here。And it learned how to use these tools。

 and then it's applying the exact same tools down here， it'sApp search， it applies it again。

 then it applies video， and it's applying it using the format so you can imagine it's essentially learning to run a web search to watch a video but again。

 these are tools so it could basically go and send some information off to the tool。

 get an answer back and then pick up in its reasoning。Now。

 the way that we would do this is we would have to have a way if we're going to use this to。Actually。

 when it gets to the point where it says here's what I'm going to do。

 we would stop it and go give that data to the real tool。

 get the answer and then come put it in for the result。

 and then we would feed this whole thing back in with the correct answer as the prompt。

It then hopefully will run through up until it gets another action in which case we would go and get the real result from that tool。

 put it into the prompt and continue and we we continue down until we got to a point where we had an output now a better way of doing this would be to have some you way of it saying okay。

 I'm done and I should have put that into the prompt here。

 but this is doing basically it's teaching it， here are some tools that you can use if you use this format so you can go and run this particular tool and you describe the tool to it。

Now， other ways to do this， you can also， if I didn't have every tool used。

 I could have edited this prompt and I could have had a description of each tool and the format and other information that it could use to help it figure out which tool to use now my simple example I did it just based on giving it patterns that I had directly in the sort of few shot examples that I provided but you can also have other ways of sort of catalogs of tools in their description so it can think about which ones to use at the appropriate time and you see how it's beginning to reason and know know which tool do I need to use at which point in time to get which type of information so you can teach it to do this sort of problem solving so you can go and integrate it with other tools and you can build these prompts that allow it to tap into other tools and you see this in a variety of different。

Frameworks， there is a tool you may have heard about called Lng chain。

 which is a framework for writing these types of automation processes。

 and they use reactact underneath the hood in order to be able to go and do some of the interesting things like this that they do。

