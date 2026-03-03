# LangChain【中英⚡LangChain 使用指南｜Build with LangChain】 p21 P22 Reliable, fully local RAG agents with LLaMA3 -BV1xwfMYDE3n_p21-

![](img/442408c9b7f45e8c326836ae513300da_0.png)

Hi， this is Laancesom Langche。 So Meow's Lama 3 came out today。

 which is super exciting and something that I've been waiting for for a while。

 And I want to hop on here and talk about how to build reliable agents using Lama 3 that can actually run on your laptop。

 so it can run locally。😊。

![](img/442408c9b7f45e8c326836ae513300da_2.png)

![](img/442408c9b7f45e8c326836ae513300da_3.png)

Now just for a quick kind of refresher here， Lama3 just dropped today。

 we can see looking at the performance characteristics for the 8 billion parameter model。

 they're very strong， so I've done a lot of work with Mistral。

 which is previously kind of my go to and it looks like on a number of popular metrics or benchmarks you know Lama3 is indeed a bit better so again I haven't tested this yet。

 this is kind of like a first dry run but it's really exciting。



![](img/442408c9b7f45e8c326836ae513300da_5.png)

![](img/442408c9b7f45e8c326836ae513300da_6.png)

![](img/442408c9b7f45e8c326836ae513300da_7.png)

![](img/442408c9b7f45e8c326836ae513300da_8.png)

So to convince you that we can build local and reliable agents。

 I'm going to pick ideas from three different ragg papers。



![](img/442408c9b7f45e8c326836ae513300da_10.png)

![](img/442408c9b7f45e8c326836ae513300da_11.png)

They're all pretty sophisticated and they're going to kind of roll up in this pretty kind of interesting and complex rack flow。



![](img/442408c9b7f45e8c326836ae513300da_13.png)

Still we're going to do routing from the adaptive rag paper， which will basically take a question。

 route it to either a vector store or do web search based on the content of the question。

 We they going to introduce the idea of fallback。 So basically we're going to do retrieval from our vector store if the questions relevant to the vector store。

 we're going to grade our documents if they're not relevant to the question we're going to fall back and do web search So that's an idea from the corrective rag paper。

And then we're also going to do sub correctionrection or checking of the generations to see if if they contain hallucinations and if they're relevant to the to the original question and if they're not we'll fall back and do web search。

 So the point is we implement an interesting complex rag flow or we're going show we can run this reliably and locally on my laptop。

 I have a Macm 32 gigs， so it is reasonably sized laptop， but it's not insane。



![](img/442408c9b7f45e8c326836ae513300da_15.png)

![](img/442408c9b7f45e8c326836ae513300da_16.png)

![](img/442408c9b7f45e8c326836ae513300da_17.png)

So first and foremost， what's an agent and this is kind of controversial in itself。

 but a really good blog post from Lilyian Wang lays out an agent is something that。



![](img/442408c9b7f45e8c326836ae513300da_19.png)

It has planning， so it can break down tasks into smaller sub goalss or subtasks， it has memory。

 chat history， your long term memory in the vector store， and it can use tools。



![](img/442408c9b7f45e8c326836ae513300da_21.png)

![](img/442408c9b7f45e8c326836ae513300da_22.png)

Now let's just say we want to use an agent to build corrective rag which is that middle blue thing we talked about right so typically when people think about an agent they immediately say oh。

 you react， that's like a very popular framework for building agents。

 and it typically involves a float looks like this for planning the LM will select an action。

 observe the result， think and then choose the next action and again。

 react agents typically will use memories， chat history or vector store and of course can use different tools。



![](img/442408c9b7f45e8c326836ae513300da_24.png)

![](img/442408c9b7f45e8c326836ae513300da_25.png)

![](img/442408c9b7f45e8c326836ae513300da_26.png)

![](img/442408c9b7f45e8c326836ae513300da_27.png)

So if I want to do this above flow as a react agent it would look like this。

 I would take my question， I would first perform an action like use my vector store to get documents。

 I would then observe the documents， I would say okay I need to think about grading them and then I would go back to my action and then I would choose the greater tool and then I would kind of go in this loop until hopefully I followed this trajectory as laid out here right so that's kind of how it work with a react agent。



![](img/442408c9b7f45e8c326836ae513300da_29.png)

![](img/442408c9b7f45e8c326836ae513300da_30.png)

![](img/442408c9b7f45e8c326836ae513300da_31.png)

Now I want to introduce another idea from implementing this that you can basically lay this out as a control flow。

 so instead of having an agent make a decision at every step in like kind of in this loop。

 instead we're going to lay out as the engineer ahead of time。

 here's the control flow I want my agent to take every time it's run so I'm basically taking this kind of like planning away from the LLM and I'm actually creating a control flow that I'm defining and what's nice is that the LLM then only has specific tasks within each of these steps。



![](img/442408c9b7f45e8c326836ae513300da_33.png)

![](img/442408c9b7f45e8c326836ae513300da_34.png)

![](img/442408c9b7f45e8c326836ae513300da_35.png)

![](img/442408c9b7f45e8c326836ae513300da_36.png)

![](img/442408c9b7f45e8c326836ae513300da_37.png)

![](img/442408c9b7f45e8c326836ae513300da_38.png)

So， you know， in terms of planning， I'm laying out a control flow ahead of time in terms of memory。

 I can basically use what I'm going to call a graph state to persist information across this control flow and of course it can be relevant things relevant to Ra like documents question。

And in terms of tool use， you know each graph node like we talked about can use a different tool like the vector store retrieval will just use our retr tool。

 the greater we'll use a greater tool know the web search lose a web search tool so you know again thinking about this what are the tradeoffs react of course one of the big challenges is that you get lower reliability when you have this react style flow the agent has to make the correct decision at every point and this is kind of when you can see things go off the rails and get off track particularly with small LLMs whereas with La graph you're actually laying out this flow ahead of time so the agent effectively always traverses this path every time the LLM doesn't have to make choices about which node to go to next。



![](img/442408c9b7f45e8c326836ae513300da_40.png)

![](img/442408c9b7f45e8c326836ae513300da_41.png)

![](img/442408c9b7f45e8c326836ae513300da_42.png)

![](img/442408c9b7f45e8c326836ae513300da_43.png)

![](img/442408c9b7f45e8c326836ae513300da_44.png)

![](img/442408c9b7f45e8c326836ae513300da_45.png)

In kind of an unconstrained way。Now in terms of flexibility， a react agent would be more flexible。

 so it could choose any sequence of actions through this given these tools。

 whereas the control flow that I lay out with Lagrara is constrained。

 so it only ever traverses this path。😊。

![](img/442408c9b7f45e8c326836ae513300da_47.png)

![](img/442408c9b7f45e8c326836ae513300da_48.png)

![](img/442408c9b7f45e8c326836ae513300da_49.png)

But we'll see because of this constrained kind of control flow。

 these land graph agents are compatible and actually quite reliable with local and smaller LLMs and that's kind of one of the main benefits I want to kind of bring home to you today。



![](img/442408c9b7f45e8c326836ae513300da_51.png)

![](img/442408c9b7f45e8c326836ae513300da_52.png)

So let's actually get to the code let's kick this off and start with the corrective rag piece that's kind of the middle piece of this overall agent we want to build and what I'm going to do is I'm just going take a few of these components and just test them individually so you can see them working so I have a notebook here a few PP installs here's again my flow tool reference now for local models for embeddings I'm going to use GP for all which is from Lang chainnomic we have a partner package them with Noic and I really like these embeddings arere really good。



![](img/442408c9b7f45e8c326836ae513300da_54.png)

![](img/442408c9b7f45e8c326836ae513300da_55.png)

![](img/442408c9b7f45e8c326836ae513300da_56.png)

![](img/442408c9b7f45e8c326836ae513300da_57.png)

![](img/442408c9b7f45e8c326836ae513300da_58.png)

Now O just came out， it's available sorry3 just came out it's available on Oama。

 and all I have to do is Oama pull Laama 3。

![](img/442408c9b7f45e8c326836ae513300da_60.png)

And the only other thing I'm going to reference is occasionally Me Lama3 has a particular prompt format。

 which we have to pay attention to， so that's really it。😊。



![](img/442408c9b7f45e8c326836ae513300da_62.png)

![](img/442408c9b7f45e8c326836ae513300da_63.png)

And let's kick this off， I'm going to choose a local M， I'm going to say Lama 3。

And first I'm going to do I'm just going to build an index。

 so I'm going to build an index of three web pages， blog posts that I like。

 and I'm going to kick that off， I'm setting a chunk size， I'm using Chroma。

 local vector store and that all ran so cool now I have an index So that's this piece right Basically the index is the key component of my ragg flow I need to be able to retrieve documents。

😊。

![](img/442408c9b7f45e8c326836ae513300da_65.png)

![](img/442408c9b7f45e8c326836ae513300da_66.png)

![](img/442408c9b7f45e8c326836ae513300da_67.png)

![](img/442408c9b7f45e8c326836ae513300da_68.png)

![](img/442408c9b7f45e8c326836ae513300da_69.png)

Then。Now I'm going to get into some fun stuff here。



![](img/442408c9b7f45e8c326836ae513300da_71.png)

I want a retrieval grader so that is this piece I want to build your retrieve documents and grade them for relevance relative to my question so that's what's happening here Now here's where Lama 3 comes in and I'm going use something really convenient I set my local L L' Lama 3。

😊。

![](img/442408c9b7f45e8c326836ae513300da_73.png)

![](img/442408c9b7f45e8c326836ae513300da_74.png)

Oama has JSON mode， which confirms that the output from the LLM is JSON。

 so my prompt basically just says grade the documents。And return a Json with score Yes， no。

 that's it。 So I'm going to do a mock retrieval。 so I'm going to say my question is agent memory。

 I can just call invoke here actually on my vector store it's a little bit more convenient I can kick that off So this is now running Now one other thing I did I set tracing in Langsmith So I actually and that already finished but what's nice is you'll see me reference over here when this runs as this is running。

 I can actually inspect what's happening under the hood So we've called it Cha Ollama and we get this nice JsonN out that's great that's exactly what we want。

😊。

![](img/442408c9b7f45e8c326836ae513300da_76.png)

![](img/442408c9b7f45e8c326836ae513300da_77.png)

![](img/442408c9b7f45e8c326836ae513300da_78.png)

![](img/442408c9b7f45e8c326836ae513300da_79.png)

![](img/442408c9b7f45e8c326836ae513300da_80.png)

![](img/442408c9b7f45e8c326836ae513300da_81.png)

Cool， so that's our grade。Now for generation I'm just going to do good old rag so again I have some custom rag prompt here。

 nothing too unusual， I'm still going to use Lama 3 of course and I'm basically just taking my documents and my question I'm plumbing them into Lama 3 there we go so you can see it runs pretty quick let's actually check over here。

😊。

![](img/442408c9b7f45e8c326836ae513300da_83.png)

![](img/442408c9b7f45e8c326836ae513300da_84.png)

![](img/442408c9b7f45e8c326836ae513300da_85.png)

![](img/442408c9b7f45e8c326836ae513300da_86.png)

So I can see my the time is around four seconds， not bad and this is pretty cool so I can look at my my prompt which contains the documents and the output great。

 so we're rolling here this is pretty good。

![](img/442408c9b7f45e8c326836ae513300da_88.png)

嗯。And okay we got our index， we got our greater， we got our generation done I'm going to find a search tool as well so this is basically just a tool that I'm going to use to query the web I like Tly for this it's kind of a really nice quick search tool and here's where I'm going to basically define my graph so all it's happening here is each of our shall go up and show you here So each of these pieces these green things let's call them nodes so each of these is just a function Okay so this first node retrieve documents I'm just going to wrap that as a function that's called retrieve。

😊。

![](img/442408c9b7f45e8c326836ae513300da_90.png)

![](img/442408c9b7f45e8c326836ae513300da_91.png)

![](img/442408c9b7f45e8c326836ae513300da_92.png)

![](img/442408c9b7f45e8c326836ae513300da_93.png)

![](img/442408c9b7f45e8c326836ae513300da_94.png)

![](img/442408c9b7f45e8c326836ae513300da_95.png)

![](img/442408c9b7f45e8c326836ae513300da_96.png)

![](img/442408c9b7f45e8c326836ae513300da_97.png)

This generate， I'm just going to wrap as a function generate。



![](img/442408c9b7f45e8c326836ae513300da_99.png)

Grade documents again is just going to be a function。

 Now what you're going to see here is each of these functions。

 These are basically the node to my graph。 I'm going to take in the state。

 I'm going to modify it in some way。 So in the retriever node。

 all that's happening is I'm taking the state。😊。

![](img/442408c9b7f45e8c326836ae513300da_101.png)

![](img/442408c9b7f45e8c326836ae513300da_102.png)

Which I've defined up here， this is a placeholder dictionary that containss my state。

 so the way to think about this is。😊，The state is information that I want to persist across my agent so again it's kind of that notion of memory it's based short- termm memory that lives over the lifetime of my agent and it contains everything I want my agent to be aware of throughout this control flow right so for Rag it's like question generation web search intuitive stuff right so my retrieve node is just going to take in my question and this is going to be passed from the user and it's just going to do a document retrieval so I'm actually going to use invoke for this it's slightly kind of a nicer way to do it。



![](img/442408c9b7f45e8c326836ae513300da_104.png)

![](img/442408c9b7f45e8c326836ae513300da_105.png)

![](img/442408c9b7f45e8c326836ae513300da_106.png)

![](img/442408c9b7f45e8c326836ae513300da_107.png)

![](img/442408c9b7f45e8c326836ae513300da_108.png)

That's my retrieval node， generation same deal， I'm just going to use that rag we defined above。

 I'm just going to call it but I'm going to invoke it now on my graph state。

 my question and my documents， and you can see at every node here we just write in this case we write the question and the documents back out to state。



![](img/442408c9b7f45e8c326836ae513300da_110.png)

![](img/442408c9b7f45e8c326836ae513300da_111.png)