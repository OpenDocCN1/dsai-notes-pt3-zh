# 卡内基梅隆大学【中英⚡LLM推理算法｜11-763 Fall2025 CMU Inference Algorithms for Language Mode】 p10 P10 Incorporating Tools -BV1QdSrBfE9v_p10-

Hello everyone so we had a few questions about the assignment the first question about the assignment was were people having trouble with the inference on the like graph problem where it was taking a really long time with your bottles？

Yes。DidI see some people nodding？对。Yes， okay， did you have like the thinking token on for Quenn3 note？

You explicitly turn it off。 Okay， we will need to look into that because I didn't I didn't see that when we ran it ourselves。

 but will'll。

![](img/8dc261275842ee7830b69d91a877006f_1.png)

![](img/8dc261275842ee7830b69d91a877006f_2.png)

Willll see。 And then the other thing is I had a question about when the homework the next homework is going be out。

 I'll let the Ts answer that when they get here， they are running a little bit late。

 I don't know if they stayed up late for the deadline。 I cleared up blind last night or something。

 but yeah， I know at least at least some of them did。嗯。Cool but yeah， I don't want to waste time。

 how many people do we have presenting today， one， two， three， okay。I have a lot of content today。

 so I will get started and try to go quickly。不。Okay。

 so this time I'm going to talk about tool use and。



![](img/8dc261275842ee7830b69d91a877006f_4.png)

The basic idea is that we want to provide the agent with tools that it can use and in terms of the definition of tools。

 we're talking about things that are external to the LM and they're part of an environment that the LM is kind of placed in。



![](img/8dc261275842ee7830b69d91a877006f_6.png)

And they have a functional interface and so we think of them as functions in a programming language。

 colllable with input parameters and output that you get from them。

 and they're generally executable as programs。

![](img/8dc261275842ee7830b69d91a877006f_8.png)

And there's a survey paper that I did together with one of the one of my students who are called water toolsol anyway it's on the site and you can go in and read a lot of the slides here are kind of based on that to some extent。

 but in coming up with that survey we tried to think of like the categories of tools that you use and there's basically three different categories of tools that you might use so the first one is perception and what we mean by perception is basically giving the language model the ability to access information that is not included in its parameters so they can collect information from the web or they can read a file system or you know interact with the user in some way or something like that。

The second thing is taking actions and so actions are things that can directly affect change on the environment。

 so perception is basically you know just gathering information from the environment where action is actually you know making some sort of change to the environment and then the final one is computation and what this is is this is not necessarily interacting with an external environment so you're not providing the agent with or the LM with any more information than it has originally。

 but it can do sorts of computations that like aren't easy to do within a language model。



![](img/8dc261275842ee7830b69d91a877006f_10.png)

![](img/8dc261275842ee7830b69d91a877006f_11.png)

Here are some examples of them and so you can have things that provide additional knowledge so you can like call a search engine。

 make database queries， you can do computation， either using like just a calculator or a Python interpreter you can get information about the world like getting the weather fetching events from a calendar and you can also do other things like calling tools that allow you to interact with other modalities that the LM cant interact with immediately so like doing visual UA over an image。

 converting video to its transcript， playing music on Spotify know other stuff like that。

Any questions about that？

![](img/8dc261275842ee7830b69d91a877006f_13.png)

Okay， cool。So。The basic tool use paradigm， this is now the only way to call tools。

 but this is one of the common ways to call tools and language models is you have a user query and then before you actually generate the output。

 have some way of calling a function and typically what this means is you have a tag that's like something like start tool call or something like this which indicates that you're starting to call a tool。

 you write the tool call and then you you finish。

![](img/8dc261275842ee7830b69d91a877006f_15.png)

And so here this actually this figure might。Not be the best it should be like tool you should have a tool tag and then check whether and then like a closed tool tag or or something like that。

 But this is you know the example of how it works and so then you get the tool call you call the remote server and you return the API output and you can either like concatenate it directly into the stream that the agent is generating or you can give it to the agent as an observation and then based on that observation it can go back and like。



![](img/8dc261275842ee7830b69d91a877006f_17.png)

![](img/8dc261275842ee7830b69d91a877006f_18.png)

![](img/8dc261275842ee7830b69d91a877006f_19.png)

![](img/8dc261275842ee7830b69d91a877006f_20.png)

![](img/8dc261275842ee7830b69d91a877006f_21.png)

![](img/8dc261275842ee7830b69d91a877006f_22.png)

You know， generate the response to you。过。Everything good。So the first。



![](img/8dc261275842ee7830b69d91a877006f_24.png)

Example of this kind of in the large modern large language model era。

 actually one thing I should mention is before the modern large language model era。

 this existed in lots and lots of cases like Siri and you know Alexa and all of your personal assistance but they did it in a different way the way they did it is they had classifiers and they would have a classifier that says I need this API called So like the user says something you classify into over all of the APIs that you were calling and then after that for each API you would then fill in the arguments So you would have like an argument filling models。

 So that's the way you would do it now previously now you usually do it by just having the language model directly generate the code to call the tool。

😊。

![](img/8dc261275842ee7830b69d91a877006f_26.png)

![](img/8dc261275842ee7830b69d91a877006f_27.png)

![](img/8dc261275842ee7830b69d91a877006f_28.png)

So the first example of this that I'm aware of in the modern LM era is WebGBT。

 and this was basically taking the GPT models and giving them a tool to do web search。



![](img/8dc261275842ee7830b69d91a877006f_30.png)

![](img/8dc261275842ee7830b69d91a877006f_31.png)

So if it sounds familiar because every large language model provider chatpott does this nowadays。

 it actually was a research paper four years ago， so it came from this。



![](img/8dc261275842ee7830b69d91a877006f_33.png)

![](img/8dc261275842ee7830b69d91a877006f_34.png)

And so the issue is language models lack access to current information so they do text based web browsing as a tool。



![](img/8dc261275842ee7830b69d91a877006f_36.png)

They had a text based interface that allowed the GPT model at the time。

 which I think was maybe GPT2 to search， click scroll in quote。



![](img/8dc261275842ee7830b69d91a877006f_38.png)

And so they could search for a webpage， click on links， scroll， and then extract quotes from them。



![](img/8dc261275842ee7830b69d91a877006f_40.png)

And they actually trained it using reinforcement learning from human feedback。

 so not from verifiable rewards， but directly from a feedback model。



![](img/8dc261275842ee7830b69d91a877006f_42.png)

![](img/8dc261275842ee7830b69d91a877006f_43.png)

And I'm not going to cover RLHF a whole lot in this class。 Hopefully。

 most of you have seen it somewhere before。 But the basic idea behind it is they started out with behavior clo。

 So they created a web interface where humans could actually like。



![](img/8dc261275842ee7830b69d91a877006f_45.png)

![](img/8dc261275842ee7830b69d91a877006f_46.png)

Search for things and click on links and scroll and gather information and information gathering tasks。

 they instrumented it so they could gather all the data of how humans were doing it and then train GPT with that data。



![](img/8dc261275842ee7830b69d91a877006f_48.png)

![](img/8dc261275842ee7830b69d91a877006f_49.png)

They then did reward modeling so they had the behavior clone model you know generate two outputs and then humans would pick which one they like the best and so that would give you preference data and then based on that they would train the reward model and then the reward model would be used to grade like essentially WebGBT generations。



![](img/8dc261275842ee7830b69d91a877006f_51.png)

So you know， every time you're in Ch ET and you get the two things side by side and you press。

 you know， I like this one better or I like this one better you're basically doing number two for them so thank you for your service。



![](img/8dc261275842ee7830b69d91a877006f_53.png)

嗯。So。Here here were the results and one interesting thing that they showed was they compared the small models with each other and then they also compared small models with medium models with big models and then they also compared models without search and with search。

 but they finally compared with like human demonstrations that they got from their annotators and the best answer on reite so here their baseline was a random Redor who got up voteded so which in 2021 was pretty impressive that they could they could beat the random Redor that got up voteded but they evaluated it I think manually evaluated。



![](img/8dc261275842ee7830b69d91a877006f_55.png)

![](img/8dc261275842ee7830b69d91a877006f_56.png)