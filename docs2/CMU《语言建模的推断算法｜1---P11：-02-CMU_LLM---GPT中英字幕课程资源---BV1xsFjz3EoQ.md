# CMU《语言建模的推断算法｜11-664 763 Inference Algorithms for Language Modeling (Fall 2025)》 - P11：-02-CMU LLM Inference (11)_ Agents and Multi-Agent Communication.zh_en - GPT中英字幕课程资源 - BV1xsFjz3EoQ

俾恩。Hi everyone I have two homework related announcements before we get started so the first one is homework two is probably going to be released today and by today I mean today anywhere on Earth so it will it will be out by hopefully the time you wake up tomorrow and then。

Number numberumber two is that we would love to have feedback on homework one。

 like some people said it was taking a long time or like certain parts were difficult and we'd like to make sure that we're trying to make the you know the homeworks。

You know， not easy but like informative and helpful to learn about the things we talked about in class and so we have a feedback form we're trying to incorporate some game theory and how we're grading the feedback form which is if 50% of the people in the class fill in the feedback form everyone gets a free quiz so it's an anonymous feedback it's an anonymous feedback form and if everybody fills it in。

 you will get an extra three out of three on your quiz grade so that will make it a little bit easier to get a quiz grade but that only happens if half the people in the class fill it out so you can bug your friends to try to get them to fill it out。

And the reason why we're doing this is we want to get anonymous feedback。

 but we want to get anonymous feedback， but we want people to give us feedback。

 so this is our way to encourage people to give feedback while still being anonymous。Cool。

 any questions？Okay， if not I'll get started， we have two presentations today。

 I think here here who else was presenting Okay， great。上诉了。

So I would like to talk about agents and I'm not going to talk much about training or designing agents in order to improve。

Accuracy through architectural changes or language model changes。

 but rather focus mostly on the things that are related to doing inference in agents because this is an inference class。

 but there's kind of like no way around some of the you know the architecture stuff。

 so I'll be talking a bit about that as well。But basically an agent is a system that iteratively uses tools to achieve a task。

 so it's not just one shot tool use， but it's using tools over and over again。

Almost all agents nowadays are powered by large language models。

 there are possibly some agents that are not powered by large language models still anybody have an idea what those might be。

WhatWhat was an example of an agent that was that existed like。Three years ago or five years ago。

Syria and Corana are good examples。 Yeah， and they're maybe mostly not powered by。

By large language models now， any other ideas？What about the ones you use to get customer service when you call your favorite airline or something those are other ones that are basically based on on trees you know like if if this and classifiers and stuff and those you know you still use。

 but now all the newly developed agents， mostly people are using LLMs。嗯。

Agents are interesting because they pose unique inference challenges in a number of ways。

 the first one is reasoning and planning and because of this。

 you know you have to do extra steps that require inference over them。Environment representation。

 so like how do you represent all of the output from the tool calls that you get？

Long context modeling， so agents are probably one of the biggest long context use cases nowadays in addition to things like summarization or question answering。

Evaluation， I'm going to talk a little bit about this in case people want to use agents and evaluate them。

Another thing that we've been working on you know， kind of more from my personal experiences critic models and critic models are models that are essentially similar to the reward models that we're going to talk about later。

 but I'd like to talk about them now because this is only agent class and then you can remember them when we cover reward models later。

And also multi agent delegation， and I'm not really going to cover this in that much detail。

 but I'll talk about it a little。Cool， so the first thing is some use cases for agents。

 hass anybody like built an agent to do something。Yeah。

This one to simulate users on a search engine so actions like predict what they click and what's the next action game users going okay simulate users and a search engine that sounds good any other。

Interesting use cases。Okay， well thank you for accidentally volunteering to talk about your agent we have a bunch of different use cases。

 one of the biggest ones nowadays is software development so code generation debugging and testing there's kind of popular examples like cloud code Banthropic codex and also open hands which is an open source agent that I'm developing that I'll talk about a little bit。

😊，Also web automation， so things like data extraction。

 form fillinging testing and things like this and there's closed source things like open AI agent mode。

 if anybody has used this， and then there's open source ones that you can download and use in research like browser use is a very popular example of this。

Things for research and analysis so kind of by default a lot of the you know chat bot interfaces like Chat ChiPki or Claude now support things like information gathering and report generation there's also things like perplexity Pro there's open source versions of things like this like openDe research and there's like seven different opende researches so you can find one and pick your favorite one。

And then there's also interactive environments like games， simulations and robotics。

 so you know things play games like Minecraft and work kind robots。

So I have been actually building an open source agent called Open Hand is kind of。

It originally is an open source tool and then is part of a startup that I work with and because of this a lot of my best examples are from my experience with this。

 basically it's a software development agent that also supports web browsing and other varieties of tools it's available here。

 I'd like to show a little example。

![](img/3ba0f8e3d29622df99554be8c773e9d5_1.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_2.png)

So you can like click through and create a conversation。



![](img/3ba0f8e3d29622df99554be8c773e9d5_4.png)

嗯。

![](img/3ba0f8e3d29622df99554be8c773e9d5_6.png)

Anybody have something interesting I can do。 I usually try to pick something that I。



![](img/3ba0f8e3d29622df99554be8c773e9d5_8.png)

That I want to do recently。嗯。

![](img/3ba0f8e3d29622df99554be8c773e9d5_10.png)

Okay， here's one bind。第五。Find the website for CMU In Als class in fall 2025。

 download the homework assignment and guess how long it will take to finish homework assignment one。

Okay， so let's see how accurate this is。Oh sorry， this is using GP5 and inference on GP5 is really slow。

 so I'm going to stop doing that and use Claude because I'd like it to finish before the class finishes。



![](img/3ba0f8e3d29622df99554be8c773e9d5_12.png)

Yeah， we just haven't updated the interface yet， so。



![](img/3ba0f8e3d29622df99554be8c773e9d5_14.png)

嗯。So like GPP5 has， we run it with the like reasoning effort high and the high reasoning effort takes a long time。

 but it's really good， so it doesn't make as many mistakes。

 but yeah you specify whether it's like a person' itself finishing。



![](img/3ba0f8e3d29622df99554be8c773e9d5_16.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_17.png)

That's a good point if I ask it to guess how long software engineering tests will take it usually says like much longer than it actually takes。

 so it'll probably say like two to three weeks or something but anyway like because this is a demo I'd like to just show you what it's doing so here it's calling a search engine tool。



![](img/3ba0f8e3d29622df99554be8c773e9d5_19.png)

It's calling a search engine tool to try to like find like search for this class。

 it found it taught by me in Amanda and then it see there's an assignments page it's going to that and extracting the information from the page and then it's cloning。

Clonning the code to see where the code is。嗯。It's reading the PDF so you can see that it opened the PDF and it's reading through the assignment and stuff like this。

 scrolling down to read more of it to get gather more information and stuff I won't make you watch all of this。

 I'll like go back to this。

![](img/3ba0f8e3d29622df99554be8c773e9d5_21.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_22.png)

Like to check on it when it's done because they don't want to spend too much time watching the agent work it's kind of a failure mode of agents。

 you shouldn't watch your agent work， you should let it go do things and go back and check on it because it's too like fun to watch the agent do what it's doing。

 but that wastes a lot of your time so。

![](img/3ba0f8e3d29622df99554be8c773e9d5_24.png)

过嗯。Any questions so far？Yeah L yeah so great great question L and Langchain are like tools to build agents we actually decided not to use anything like this and can I can talk a little bit about the design decisions but we have our own agent SDK。

That we designed specifically for this。

![](img/3ba0f8e3d29622df99554be8c773e9d5_26.png)

And。The reason why we did this is L graph and  Lnching basically my。

Description of them and other things like Autogen is they're kind of more fixed agent workflows。

 So it's like I want to do this and then I want to send the information to this and do that and then send the information to this and then do that and so they're particularly good when you have like a more fixed workflow but in software engineering or like the workflow is very various right like I did I did something here that's like a workflow that I've never really done before like you know look at homework and estimate the time And so in order to make things kind of more diverse we basically just wanted to create a single agent that could do lots of different things so we didn't use that sort of scaffolding ourselves So basically what you do is you add tools。

 the tools that you wanted to have available to it and then like framework that we created has all the like inference or all the methods that I basically will talk about me slides implement。



![](img/3ba0f8e3d29622df99554be8c773e9d5_28.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_29.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_30.png)

But it's mostly not like doing delegation between multiple agents。

 which is what La graphph and Autotrogen are good at。こ。嗯。Okay， sounds good。 Let's， let's move。



![](img/3ba0f8e3d29622df99554be8c773e9d5_32.png)

Actually， maybe it's done。好。25 to 35 hours total。 So we'll see if that is also。

 we're going to have the the feedback survey that hopefully everybody will fill out。

 So you can see how， how correct this estimation was。😊。



![](img/3ba0f8e3d29622df99554be8c773e9d5_34.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_35.png)

Cool， let's go。So。First， I'd like to talk about reasoning and planning。 and the basic idea is that。

We talked about reasoning from the point of view of mathematical reasoning。

And the mathematical reasoning there， it's mostly kind of like。

Deductive reasoning where it's like okay I have this math problem I want to apply my principles to perform you know to solve the math problem here it's a little bit different it's like。

Not this is the information I have。 and I want to combine it together to solve a problem in a kind of like fixed way。

 but rather I would like to come up with the best idea of what to do next。

 given my overall objectives。 So this is more open ended。

The standard way of doing reasoning within language models is based on a paper called React。

 which is a framework where you basically do reasoning and then perform actions。

And so this is in contrast to only acting so you're given a task and then you have an action which is go to door one and then the door is closed。

 open door one， you know you open the door et ce， but you actually add add the thoughts here and there's two reasons why you would want to do this the first reason why you would want to do this is we've all seen that chain of thought like improves accuracy and agents are no you know exception to that the second reason is it actually gives you updates of like what what it's doing in natural language。



![](img/3ba0f8e3d29622df99554be8c773e9d5_37.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_38.png)

So you can see that it's saying here， I'll help you find the website great。

 I found the website let's access the let's access it， I can see there's an assignments page。

 you can kind of like follow along what the agent is doing without looking at its actual actions here so that's kind of like a major a major advantage of doing things like that。



![](img/3ba0f8e3d29622df99554be8c773e9d5_40.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_41.png)

So。You know， accuracy accuracy and kind of legibility。嗯。So react is a method for。

Basically multistep agents that use reasoning， there's another method called Koak and basically the idea of Ko Act is instead of calling individual tools with an agent。

 you have the agent write code that executes the actions for you。

And the basic idea was like let's say you wanted to extract。

 you wanted to check the price of 10 different items and find the maximum。

 the most expensive item or the least expensive item or something like that。

Original way you would do this is you would make a bunch of individual tool calls。

 you would get the results of all of those tool calls。

 and then you might make another tool call or use LM to pick， you know the。

Like highest price or lowest price item。 but what you can do instead is you can just write a Python program that calls all the tools for you and that was a basic idea behind the Koak framework and what Koak does is it simplifies your action space because now all of your work is basically writing you writing programs in language like Python and it also makes you be able to self-tasks a lot more efficiently So is this is pretty popular nowadays and so now a lot of agents have kind of a like coding style action space where they can run Python programs where they can run bash programs or other things like that。

And this is important for inference， of course， because it's the difference between。

One action that generates a very large output versus many。

 many individual actions that generate a small and less complex output。

 So you could even like trade off between the two， right。

 you could have an even if you're using Koak， you can have an agent that prefers to write small chunks of code and where it's more certain about the result or write very large chunks of code。

 where it's less certain about the result。 So you need to think about trading off between those。Cool。

 any questions about that？Okay， so another thing about planning with agents So react is a very reactive way of doing planning so kind kind of pun intended kind of that。

 but like basically the idea is it plans in very small chunks in that it is usually reasoning about the best next action to be performing。

Another thing that we did。In open hands and， you know。

 other libraries also other libraries and methods have similar ideas is we have a planning system that utilizes tools and that can set out a plan and then update that plan as you start executing the plan。

 So this is something that we introduced relatively recently， but it's a。

 it's been very useful and effective is you have a task tracker tool。

 And this gives you structured task management where it basically will。



![](img/3ba0f8e3d29622df99554be8c773e9d5_43.png)

Like come up with a task。Where。You have different individual steps in that task。

 and then it can update the status every time。 so it will like recall the tool every time a step in the plan changes。

 So let me see if I can get it to do this。

![](img/3ba0f8e3d29622df99554be8c773e9d5_45.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_46.png)

Check all of the classes and see if there are any missing references。References。

 create a plan and check off。Each item。U the plan。 and I actually don't need to write the second sentence here。

 It' will usually do it spontaneously。 but because this is a demo I want to make like。



![](img/3ba0f8e3d29622df99554be8c773e9d5_48.png)

Extra。Extra sure that it will actually call that tool。 Let's see if that works。 Yeah。

 so here it created a plan。 and it says like， examine all starter code files。

 check the shared task example code， verify the requirements。

 And then it updated this to in progress。 So now it's working on this part。

 And it knows that this is in progress。 So it will continue working on that。 when it finishes。

 it will write done。 And then when it writes done， it will make sure to include all of the other elements of the plan。

 And because of that， it kind of like refreshes the more recent context window to include all elements of the plan in the context window。

 and this lets it like not lose track of its plan。😊。



![](img/3ba0f8e3d29622df99554be8c773e9d5_50.png)

And this actually gets stored on the disc too， so it gets stored in like tasks。mds。

 so like the it can't just disappear from the contact window。



![](img/3ba0f8e3d29622df99554be8c773e9d5_52.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_53.png)

Another tool is a thinking tool and the thinking tool basically gives the model permission to take another step to write a really long chain of thought and so this was introduced by Claude when they introduced Cla code and the basic idea is。

Like。You， you tell the agent， if you need to think really carefully about something right like long explanation of what you need to do in this in this tool And that that tool has no effect whatsoever。

 It just like is there for thinking。 And so it outputs this thought。 And then in the next step。

 based on that thought， it can actually take the action is probably technically isn't necessary。

 If you have a reasoning model， but it's a way to turn a like。Moderately。

 like maybe a shorter chain of thought model that wasn't explicitly trained for this into a model that can do this。

 So it's kind of like an inference time trickre， even because you're not changing the model。

 but you're giving it increased capacity to think。

![](img/3ba0f8e3d29622df99554be8c773e9d5_55.png)

过。Any questions？Yeah， so idea of yet or any these planning you specializedize recently rather than the list。

 this is very long and probably not concept what you are doing。In that case。

 like these pictures don really， they break down for those points。So the question was。

 if you have like a reasoning model with a really long chain of thought。

 do these frameworks break down for the models， I think。Essentially， everybody is doing react。

 There's like no no agents without any reasoning whatsoever。

 So your choice is either to use a short chain of thought or a long chain of thought that was like explicitly trained for reasoning。

 And so in a way the framework isn't breaking down。 It's just like constantly present。

 I think the extra thought tool， I think honestly may not be necessary。 if you do training。

 It's like a way to retro fit。You know， extra thought into a model that was not initially trained for it。

 The task planning， I think， is still useful probably unless you trained a model to do that natively。

 but even if you trained a model to do that natively。

 it's not quite as effective as having like the plan stored on disk and you know being able to recall it without it being in your context window。

 So might not be necessary， but I think it still could be helpful and's at the very least。

 it's helpful for visualization people who are watching your plans。 great question though。Cool。

So the next thing I'd like to talk about is environment representation。

 so like as we learned from the tools class the previous time the tools have actions and they get observations so then the question is how do you represent these observations in your model。

 as I mentioned I want to talk about inference related things and this is important because these can be very large and because they can be very large this impacts how you do inference when you're working with agents。

So。The first type of environment representation， I'm going to maybe specifically talk about representing websites because I work with a lot of web agents。

 but I'll talk a little bit about representing code in files also so the first type of environment representation for websites is textbased and so what this does is this basically takes a website or maybe a PowerPoint presentation or some other thing that's not natively text and just converts it into Markdown and so this is an example of what something like this would look like for the LTI homepage and instead of you know the beautiful LTI homepage that we've newly updated and you everybody knows and loves we get this markdown representation and it's very concise。

 very easy to use I got actually。

![](img/3ba0f8e3d29622df99554be8c773e9d5_57.png)

didn't get this directly from the Tvioli extract function。

 but we use a search engine called Tvioli when we in open hands。

 but there's a whole bunch of other search engines that could be used for this that like kind of create these representations that are specifically for agents。



![](img/3ba0f8e3d29622df99554be8c773e9d5_59.png)

嗯。One problem with representing it a text， though， is you can actually perform actions on websites like clicking and scrolling and stuff like this and。



![](img/3ba0f8e3d29622df99554be8c773e9d5_61.png)

It's not like。In this markdown representation， we don't have a specific。

Representation of the interactable elements on the site so like let's say I wanted to click on natural language processing and there was a link here there's no link or let's say I wanted to enter something in a text box or something like that there's no text no way to represent a text box natively and markdown so you'd either need to come up with representation and markdown or you would need to do something like a textbased representation of the HTML Dom treee and this is the standard way of doing this for web agents it's called accessibility tree and it was originally created for screen readers for vision impaired people so you know if you are not able to like actually see the site you can put it into a screen reader and it will read the site for you and so this is basically just reusing the method that was used there。



![](img/3ba0f8e3d29622df99554be8c773e9d5_63.png)

And so this is what it looks like and importantly it gives you a ID for each of the elements and if the element is clickable。

 you can then click on that element by selecting this ID by calling a tool that basically clicks on this ID。

 so that's another thing you can do。

![](img/3ba0f8e3d29622df99554be8c773e9d5_65.png)

So this is the original way that agents represented websites。

 now it's becoming more and more common to represent websites through vision。

And this is an example from a paper visual web arena。

And the way it works is you take a screenshot of the website and then around every element in this screenshot。

 you put a box and then you put a number next to the box So this is like the ID that I showed before。

 but this number you can then like click on this number and you also get a like kind of summarization of all of the elements with their numbers in text as well just to like reinforce that these are the elements that you have access to。

So this is called set of marks， and this paper applied set of marks to kind of vision based web agents。

嗯。This is actually and sorry one thing I should mention is when we're representing code。

 I think maybe I forgot to add the slide to this slide deck， but when we're representing code。

 another problem or files on your file system， you don't want to read a like 10 million line file by accident and completely destroy your context window。

 so another thing that people do is they either train models or explicitly get models tools that only select like a subset of the like lines of the file and like there are file editing tools that allow you to do that。

So。That's about environment representation， any questions here？Yeah。

 in the visual environments like Mark environment when you this image with the text the level the just a lot more attention to the sector the textual data as opposed to the image Yeah great question won't won't it pay more attention to the textual data than it will to the image。

I。It depends on the LOM One thing I will say is that LMs are not natively good at using understanding web pages。

 This is this was a major problem nine months ago or 12 months ago where certainly most of the open LMs could not understand web pages at all And so you know they would not be able to do OCR they would not be able to do character recognition they would not be able to identify like which elements meant what And so I think basically the good news is you can generate infinite sets of marks by。

Essentially taking the web page and some automatically writing the set of marks on it and then you can say。

 okay what is the 41st element on this webp page and then you'll train the model to be able to do this and we actually have a paper called where we created a data set called multiuI that explains like 10 different auxiliary training tasks that you can use to improve web a page understanding and so once you start doing that the models start to be like very good at understanding webp pages and I think most of the kind of like foundation model companies are doing that sort of thing then。

It said it marks like the actually mark really， really close to from the labels overlapping。不对。

Theres that urge mon。嗯。It does not hurt more than it helps so people have have tried doing this without set of marks and doing it with set of marks is definitely more effective。

 So that's why people do it but is this the optimal way of doing things maybe no one other thing I should mention actually which is。

Actually， maybe I'll mention it in the next section， but yeah。

 that's a great question and there's certainly more that could be done there， I think。Cool。

 I'd also like to talk about efficiency optimization。

 So like one really big challenge with agents is context length。

 so we have long conversation histories。In a typical evaluation of something like。

Swee benchch or web arena， which are some of the the like benchmarks I'm going to talk about in a bit。

 I would say the conversation history can go up to as much as like 100 steps， for instance。

 so like you know。100。Like maybe 50 tool calls 100 actions and observations， this can be very long。

 this can get over hundreds of thousands of tokens。嗯。In practical usage。

 I have used agents for up to 2000 steps， and so that's like tens of millions of tokens in your context length。

And so most language models cannot handle this， even if they can handle this。

 it becomes very expensive。It's particularly bad if you're doing something like web because web pages can be very big and so you need efficient context management strategies。

嗯。Number one， which is really， really important。 we're not going to talk about this until later in the class。

 but is prompt caching or KV caching and basically the way this works is when you。

Send a first output， you。Or when you send the first prompt。

 you can send the system prompt the observation and get in action。 and then。

Here you need to calculate the representations for all of them。

 but the next time you calculate the representations you have the system prompt observation in action and you've already calculated the autoaggressive representations for these and so then you just need to feed in the next observation in the action and then the next time you have all of these precomputed and then you calculate the next observation in action and so what this means is you can basically save all the compute that you use to calculate these and that saves you a lot of money and time when you're running these。

In reality， a lot of services will only cash the things that you had in your prompt。

 so some of them will only cache the system the system message and the observation。

 but in reality you can also cache the action as well if you're clever about it。

And we're going to talk about more details about this。

 so I'm not going to talk about all the details system。嗯。

Another thing I'll talk about a little bit is context condensation。

 and this is a way of taking in the previous context and removing some of it。

 basically summarizing it or removing it so that you can get better results。

Within Open hands we have a number of different ways that we do this that are kind of representative ways that are used pretty broadly including another like coding CLIs like Gemini and C code。

 but I'll just cover both of them here， so the first one is summarization。

And so the way we do this is we。After we have done a certain number of steps。

 we take a previous like a portion of the previous steps。

 and we feed it into an LLM and we summarize what happened in the previous steps。

And what this allows us to do is this allows us to basically remove， you know。

 half of the context while still keeping most of the relevant information。 It's not perfect。

 Sometimes you lose information that would be useful later。

 But after a certain amount of prompt engineering， we have been able to， you know。

 do this successfully。 And you can see like our prompt。Within the code base。

 if you're interested in the details about this。嗯。So， from the。

From the kind of experimental results we did， we were able to see like two X or even more cost reductions while maintaining performance on Swedch。

 We actually have a few kind of like war stories about this。 So we did like experiments on。😊。

We did experiments on。Swe benchch， which is， you know。

 the very common benchmark that people use for evaluating coding agents。

 And then we like actually started using it。 and it worked pretty well。

 but it did some really stupid things。 So like， for example， it would send a pull request。

 to like update code on Github。 It would forget that it had sent a pull request。

 And then it would send another pull request over and over and over again。

 So it needed to modify the prompt to say， okay， remember if you've sent a pull request before。

 And like other stuff like this。 So it's not as simple。

 like it demonstrates the difficulty of like benchmarking in real use。 But you know。

 basically this overall idea works。Another thing that's really common in agents。

 this started out in the agents for Webarna， which is the benchmark that I'm going to talk about in a bit。

 but is web context condensation so webp pages are large and noisy there's actually two methods that I'd like to talk about I only have one on the slide。

 but one method is after you have already processed the webp page after you've already sent it to the agent once you can keep only the most recent accessibility tree or image and so what that means is like after you've looked at it once then you basically just removed it entirely from the history。

嗯。So on the challenge here I wrote prompt caching is less effective。

 You lose one of your you lose one of your inputs when you're doing prompt caching Another problem with this。

 though， is like you。You still need to process the big web pages and the big web pages can be pretty expensive。

 So there's another method in a paper called mindd to web。Which isn't in the references。

 like most of these references are on the webage， but this particular one is not。嗯。

And this is only a minor part of the paper， but they have an interesting inference time technique there where basically what they do is they try to guess which parts of the webpage are going to be useful first。

And so what they do。

![](img/3ba0f8e3d29622df99554be8c773e9d5_67.png)

Is they get this accessibility tree。 They try to guess which elements in the accessibility tree are the most important ones to be looking at using a very lightweight cheap model。

 and then they take all of those in all of the parents of those elements and feed only that into the language models。

 So that might also be a method that could be used to keep around more history while like not you know。

 not hurting performance。 So I've not heard of I've not heard of a lot of people using it from in this context。

 but it might be an interesting thing to try if you're if you're interested in web agents。



![](img/3ba0f8e3d29622df99554be8c773e9d5_69.png)

Cool， any questions here，啊。poor action and environment changes and I suppose a lot of elements would change。

example example do you that's a good question so like the question was do the environment representations change like if you retrieve the same web page over and over and again do you like repro that web page every time as far as I know the answer is yes。

 you reprocess it every time。But。哎。Think there might be situations where you could save compute by not doing it every time。

 Like， especially like if you were running a really high volume search engine。

 like perplexity or chat E or something like that。 I could。 I could definitely。

Think of wanting to precompute the representations for those web pages and getting them to work。

 So it seems like an interesting thing to try。Cool， any others？Okay。嗯。

So the next thing I'd like to talk about is evaluation。

 There's many agentic evaluation benchmarks I actually。I'll talk about a few specific ones first。

 and then I'll talk about a place where like many benchmarks are kind of aggregated together。

So the first benchmark that I personally pay a lot of attention to is Subench and I think a lot of other people pay attention to this as well。

 this is basically a benchmark for fixing issues on GiHub so the input is a GiHub issue and a codeb and so it's like there's a data leak this is the codebase and then the agent needs to generate modifications to the codebase in order to fix the issue and then the way this is evaluated is with together with this issue。

 there were some unit tests that were introduced to check the correctness of the fix and all of the unit tests that were introduced together with the issue must pass in order for you to get full credit。

And a select number of unit tests from the testing harness that existed before the PR also must pass。

 so basically you need to fix the issue while not breaking things， so that's how it's evaluated。嗯。

So there's 2000 GitHub issues from 12 popular Python repositories。

Theres because this is very popular， there have been a number of extensions。

 there's an extension called Swbench verified， which is 500 issues that were specifically verified to be like solvoable based on the input to the issue。

Sorry， based on the issue description and the reason why is because a lot of issue descriptions are kind of vague and you wouldn't necessarily be able to come up with the like quote unquote correctr answer from the vague issue description and so Sbech verified is an attempt to make like all of them solvable this is what everybody evaluates on nowadays because it's just like this we don't really know what the upper bound on performance is but on Sbench verified we think the upper bound is close to 100。

 so that's what people use on the other hand it takes a lot of the fun out of like trying to resolve ambiguous issues and stuff like that So you know just because you get a good score on S benchch verified doesn't mean you've solved all all github issues which would require like interacting with a human you know to clarify as clarifying questions or something but there's that Another thing is this is all on Python and so there's also things like multisbench which have different programming languages and。

Swe bench multimodal， which has multimodal data where you need to like fix a front end and stuff like that。

 so a lot of different examples。Well， so Sue Rebench， which is updated every month with new issues。

 so a lot of examples here。A second one is Web Arena and Webarna was actually one that we created here。

 but in my lab at CMU but a lot of people use it to evaluate webag and basically the way it works is you set up you know a bunch of different websites and these are all open source versions of something you might think are like popular websites so there's one stop shop which is an open source version of basically Amazon it's you know a shopping site you have a content management system so this is the content management system for onetop shop so basically you go in and like add you know。

Like items items to a store and other stuff like that we also have an open source version of Reddit called Postm an open source version of GitHub called Gitlab so like these are kind of like production grade open source sites and then we have a lot of other information sources like Wikipedia and stuff and then the agent goes through and tries to answer questions like tell me how much I spent on food purchases in March 2023 or create Nolan fans repo listing Nolan's Oscar winning films in a Readme file。

And。There are lots of tasks， complex multi web attraction。

 so this is kind of a standard web agent evaluation benchmark。

Another area where people use agents like I talked about before is research and so a kind of standard version of this is Gaia and Gaia is basically a research benchmark where you need to find things like or it's kind of a general assistance benchmark with like leaning towards research and so it's like what is an enrollment count of clinical of this clinical trial you know read this label and tell me tell me about it。

 read about NASA's astronomy picture of the day， and so a lot of you know the idea is that this allows you to do research this was created by hugging face and meta and they actually just released about last week Gaia to which I haven't tried out yet but it's supposed to be kind of a modernized version of this so you can also check that out。



![](img/3ba0f8e3d29622df99554be8c773e9d5_71.png)

嗯。There's a lot of other evaluation benchmarks that you can use。 and I would maybe like to highlight。



![](img/3ba0f8e3d29622df99554be8c773e9d5_73.png)

A few of those so the in the open hands repo。We have an evaluation。Benchmarks。Directory。

 which has like 25，25 different benchmarks， which are all implemented。

 And these cover things like coding all the way to like general assistance to Web navigation。

 other stuff like this。 So this is one example， Also recently a company called Prime intellect。



![](img/3ba0f8e3d29622df99554be8c773e9d5_75.png)

Released。A environment hub。

![](img/3ba0f8e3d29622df99554be8c773e9d5_77.png)

Which has a bunch of environments。

![](img/3ba0f8e3d29622df99554be8c773e9d5_79.png)

The environments could be used for training or evaluation。

 but I would say that most of these are more like evaluation environments。

 They're not like training environments， but this is another another place that you could like to find lots of environments。

 The ones in the Open hands hub will skew towards being like practical ones that like immediately。

 you could see the usability the ones in the Envis hub for Prime Intellect will be more on the ones that are like more sandbox and like simpler to run。

 So if you want to do like a research project。 I think the ones on the Envis hub might be a good place to start。

 and then when you want to graduate to things that are more complex or kind of real world usage。

 The ones on the open hands are are probably better。 and they kind of like。



![](img/3ba0f8e3d29622df99554be8c773e9d5_81.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_82.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_83.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_84.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_85.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_86.png)

Overlap to some extent， there are some that are included in both。



![](img/3ba0f8e3d29622df99554be8c773e9d5_88.png)

![](img/3ba0f8e3d29622df99554be8c773e9d5_89.png)

Cool。Any questions here？Another thing is this is very expensive to evaluate。

 so if you want to work on inference and make this faster for me， I would be very happy。嗯。

The next thing is critic models and I'd like to talk a little bit about this so critic models for agents。

 the motivation here is it can help to have a second opinion about how well your agent is doing。

And there's a couple of use cases for this， the first use case is to rera multiple candidates to increase accuracy。

Another is to audit to ensure safety and so safety or maybe just like performance。

And so to give an example of a paper on reranking， this is a paper that we did with people in collaboration with people at UC Berkeley。

 it's called Su， and basically there were two parts to this paper。

 the first part of this paper was just training software engineering models through reinforcement learning or software engineering agent models through reinforcement learning。

 but the second part was training a critic model to rerank multiple candidate trajectories。

 agent trajectories。And the basic idea is that you want to perform inference where you roll out n times and then pick the best output。

And basically what we showed is that if you started out with a model that had2 about 20% accuracy at the time。

 every time you double the number of rollouts you do。

 you see in approximately constant gain in the amount that the score increases on Sbech and we were able to get from around 20 to up to 32 here。

And so basically， if you really want the best benchmark score。

 this is super effective at getting the best benchmark score at the cost of having to run inference like 16 times。

 which is very expensive because running agents is expensive already。



![](img/3ba0f8e3d29622df99554be8c773e9d5_91.png)

And if I haven't convinced you that this is something like important。



![](img/3ba0f8e3d29622df99554be8c773e9d5_93.png)

嗯。We were just talking about Claude sonnet 4。5 coming out。嗯。And if you look at their results here。

 the dark bar is single instance inference， and the light bar is where they did lots of rollouts。

 and then they reraked them。 And so this is this is what everybody does when they want to when anthropic wants to beat open AI and then open AI wants to beat anthropic or you know。

 we want， we want to beat you know， whoever else。 So in reality。

 I don't know if there's that many people， that many people who use this in like a production setting。

 But like， let's say。

![](img/3ba0f8e3d29622df99554be8c773e9d5_95.png)

Let's say you were working on an agent to run like a machine learning experiment or something like this。

 and you really wanted to succeed and you could spend $10，000 on making sure that it succeeded。

 then this could be a viable option for something like that。

And then the way it is the way it's trained actually， sorry， I totally。

This is the first time I made the slides so I forgot a few slides。

 but basically the way it's trained is pretty simple what you do is you do a rollout of the trajectory。

 you evaluate the rollout using the like unit tests that you have to evaluate the output and then after you've evaluated the output。

 you train a model to predict whether the output was correct or not。

So this is the simplest way to do this when we talk about reward models in the future classes。

 this is an outcome reward model。 Another way you can do this is。

An outcome reward model predicts only the the final outcome。

 so you basically predict the final outcome another way you can do this is come up with some sort of intermediate reward step by step and try to predict how successful each step is this is called a process reward model but coming up with a supervision for this is much more complex and we'll probably talk about that in the reward models class。

Cool， any questions here？Yeah， you can also like just to verify if the agent solve an issue or not you can also use test then like why do we want to like why don't we generally take models that can correct tests。

Instead of training models that can make predict common trajectory because that be systemscript。

 Yeah， that's a great question。 So we can。We can。Tell success from whether unit tests pass or not。

 So why don't we just train a model that's really good at generating unit tests and then use the unit tests to decide whether it passed or not。

 I think we should do that。Honestly， I think that would be that would be great。 but unfortunately。

 models are not all that great at generating unit tests。

 And then like let's say some unit tests didn't pass。 you might still be successful。

 There are some tasks that are not necessarily easily unit testable。

 like a research task or something like that。 So like there are situations where this would not be an appropriate solution。

 but I think overall for software engineering。 It is a very appropriate solution。

 and we should work more on it。 there's a benchmark that I didn't talk about called SwT bench。

 which is software testing bench that tests and also test genovl。 there's other benchmarks like this。

 And I really wish that these benchmarks get more love like I think software tests。

Testing sounds boring until you realize that if you can write a really good unit test agent can usually solve the problem for you and so I think we can focus more on that sort of stuff。

Cool， any other？Okay， great， I'd like to talk a little bit about multi agent systems。

And so there's a number of reasons why you'd want to use multiple agents。The first reason which。

At least until about。6ix to 12 months ago was a very popular reason to use multiple agents is specialization and the idea is you can have different agents use solve different tasks and。

There's usually an analogy which is like。In a software company， you don't have one person who is。

Planning and implementing and doing quality assurance and other stuff like that。

 so we should have different agents to do these things。

I kind of agree that this is true in a software company or I definitely agree that it's true in a software company。

 but on the other hand， we have an LOM that can do all of these things well and LOMs kind of like absorb all the specialized knowledge and can memorize like things that far beyond what humans can memorize。

 so I'm a little bit less convinced that this is a good motivation for doing multiageent systems you know especially now that we have language models that are pretty good at at doing individual tasks。

On the other hand， there is a really strong argument for doing multi agent systems when you have complex tasks that can be easily parallellyzed because you can have one agent do one part of the task。

 another agent to another part of the task， another agent do another part of the task。

 So I think this is a strong argument to use multiple agents。

One comparison you can make if you subscribe to both chatGT and Claude is try to do a research task for open on the open AI chatt deep research and then also do it on the clod deep research and the Quad deep research does this sort of task parallelization it will have a kind of like master agent delegate a whole bunch of different research tasks to different agents and youll then open AI will be doing everything in serial and you'll see open AI will look up like 30 references and Cude will look up like 300 references or something like this and you can see the results from ClD are much more comprehensive。

 So this is a good example。 this is hard for software engineering tasks for instance。

 because like very often it's hard to decompose the task together without having like conflicts between the code you write and other stuff like that。

 but it is it's still possible there。 It's just harder。嗯。😊。

Another reason could be for robustness and so like for example。

 you might delegate you might delegate four different tasks to four different agents and then have another agent like double check。

 So it's kind of like the agent is doing。Like。The agent is acting as a critic model。

 So after one agent has finished the task you go back and double check its work。

 So there are benefits there as well。 And so why not use multiple agents。

 there's more components to manage and integrate taskky composition can be tricky。

 Another issue is communication difficulties And what I mean by this is when you're implementing a system with multiple agents talking to each other you want to make sure that exactly the correct context is passed So you don't necessarily want to pass too much context because there's kind of an advantage of an agent。

Like。嗯。Solving a task and then kind of that task summary just being passed back to the main agent。

 But on the other hand， a very common failure case that we saw is one。

Like we used to have a web browsing agent with an open hands that was separate now we just have one agent that does web browsing。

And the web browsing agent would do a whole bunch of information gathering and then it would give a very brief report back that wasn't like sufficient and like the coding agent would be like missing information that the web browsing agent actually discovered during its process of web browsing so you need a really good effective way of passing context together。

Yes。😊，Our next pass will always inform blanket of tros and not say whatever。

Los even even deeper is the so good question， why is the context not passed in the form of logits or deeper representations？

I there。I think that would be possible， I think probably the biggest reason why is because many of the best models for being agents are proprietary models and you're not able to easily do that with proprietary models through an API。

 but I think if you could demonstrate that that was very useful with open models that you could use for something like that。

 then that could be valuable and that might convince people who are building proprietary models to support that。

好了。Finally， feedback the output into the next hidden state is always weaker than you go to feed in the hidden hidden state of one state next one and that's because of this information information loss so yeah yeah I agree good idea。

So there's a bunch of frameworks we talked a little bit about La graphra。

 I'm going to talk a little bit about autogen， but basically there are frameworks for building multi-ageent systems and usually what they do is they kind of give you the scaffolding to do this sort of context passing implementation of tools and other stuff like this。

 so I think for quickly bootstrapping a system especially in agentic system with a very fixed workflow not something more complex like you know research or like arbitrary research or coding but something more like I want to process。

I want to process this。File that a user has uploaded， extract this fixed set of information from it。

 and then upload it to a database， then these sorts of fixed workflows are quite helpful and so they give you things like customizable agents。

 flexible conversation patterns， they can also pass things to humans if you want。



![](img/3ba0f8e3d29622df99554be8c773e9d5_97.png)