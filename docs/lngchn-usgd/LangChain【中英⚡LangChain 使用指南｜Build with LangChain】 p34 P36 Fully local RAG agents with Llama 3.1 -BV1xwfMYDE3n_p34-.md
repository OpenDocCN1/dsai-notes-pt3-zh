# LangChain【中英⚡LangChain 使用指南｜Build with LangChain】 p34 P36 Fully local RAG agents with Llama 3.1 -BV1xwfMYDE3n_p34-

Hey， this is Le and Langcha， so Meta launched La of 3。1 today， which was a really anticipated drop。

 and I'm going to show how to run it locally， how to build a corrective rag agent thatll run locally using it and how to benchmark it against a few other models。

So the blog post announces a few different things， so 128 context length。

 a few different versions in 8B a 70B and a 405B。

![](img/b4a524dad6217cb8930d33cfb95458ad_1.png)

Now the 405B is really cool at rivals of a number of larger close source models we can actually look at the blog post here。

 so it shows valuations。 This is the 405 B compared to GT4 omni Cloud 35 sonnet。

 you know comparable performance， this will be hosted by I'm sure Gck fireworks and many other providers and this is fantastic I'm really excited to play with it So that's the 405B。



![](img/b4a524dad6217cb8930d33cfb95458ad_3.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_4.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_5.png)

Now， the8p parameter models I actually really like for local。

 know I'll show my system settings a bit below， but basically I have a 32 gig MacBook Pro。

 and I can run this locally without a problem。 And that's really cool。 performance is quite capable。

 So it's gonna be better than prior Lama 3 and indeed。

 report better than gamma 2 and Mstr 7b instruct。 So that's exciting。

 we're gonna go ahead and look at it today。 here's my setup I have a MacBook Pro 32 gig M2。

 So just so you know what I'm working with。 And I've already done this。

 So basically I'm going to use it with llama。😊。

![](img/b4a524dad6217cb8930d33cfb95458ad_7.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_8.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_9.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_10.png)

Aama pull Lama 3。1。 that's what I need to do。

![](img/b4a524dad6217cb8930d33cfb95458ad_12.png)

So I've already done that and you actually go over to the ma page you can see so this is kind of we can select the all you want to work but you can see the 405 B 231 gigs if you have enough if you have enough space for that。

 but you know look this 8B 4。7 gigs this is like kind of a sweet spot this is size I really like to work with for local。



![](img/b4a524dad6217cb8930d33cfb95458ad_14.png)

So you just have to do a couple things here so I've already done this I an empty notebook so a few Pip installs。

 you're going to see we're going to use Tvi。 that's a nice kind of web search tool。

 We'll use Lnggraft to build our agents use psyit learn to build my little vector store Lang chain llama is the package they're going be using to access llama So those are some things that you need to install and this of course notebook will be shared few API keys。

 if you want to use open Abeddings you're going to set that you set your Tvili API key and these are keys necessary for Langsmith。

 which I'll show that's totally optional if you want to do evaluations you can use Langsmith but it's of course totally optional So here's we're gonna to build and this is kind of my go to vibe test kind of little application I like to build these little subcorive rag agents there's been a lot of cool papers on this theme。

 the big idea simply this with Ra you want the ability to selfcorrect for mistakes and retrieval。



![](img/b4a524dad6217cb8930d33cfb95458ad_16.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_17.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_18.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_19.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_20.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_21.png)

What you do is you retrieve from a vector store， you grade the documents for relevance and if documents are not relevant。

 you can kick out and do a web search， this gives you flexibility if questions are outside the domain of your vector store。

 you can still answer them using web search and so it's a super simple kind of little toy agent that I like to test out different models with so that's all we're going to do here really simple。



![](img/b4a524dad6217cb8930d33cfb95458ad_23.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_24.png)

So first， let's just walk through the code here。 I'm going to build a little vector store。

 I'm going to index a few blog posts from Lin Wang， one on agents， one on prompt engineering。

 one on adversarial tax。 I'm going to load the pages。 I'm going to split them。

 I'll use a chunk size of 250。 This is， of course， arbitrary。 You can tune this as you see fit。



![](img/b4a524dad6217cb8930d33cfb95458ad_26.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_27.png)

Build my splits。 And here's where I set my vector store。 So I'll use SkL vector store。

 I'll use open AI embeddings， and you'll see why a little bit later。

 It's because I've done some other evaluations using openai embedding。 I want to keep it consistent。

 But if you want something that's fully local。 I also encourage you to look at noomic embeddings。

 So this is how you can just use them。 All you have to do again。

 I note up here is basically in your installs nomic local。 So that's all you need。

 So that's if you want fully local embeddings。 I'm going build my retriever here。 that'll kick off。😊。



![](img/b4a524dad6217cb8930d33cfb95458ad_29.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_30.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_31.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_32.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_33.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_34.png)

U。Cool。And just as a little note here， I can kind of call my retriever invoke and basically I can ask any question。

 agent memory and this should return some docs for me， there we go， so we have some docs。

 so we have a working retriever from our blog post that's great。



![](img/b4a524dad6217cb8930d33cfb95458ad_36.png)

So this is going to be my little web search tool， this un'mused Tvily again。

 I set my API key above here， so this just works， I can use this web search tool to search the web。



![](img/b4a524dad6217cb8930d33cfb95458ad_38.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_39.png)

So here's where I'm going to set up a few different things。

 so this is just going to be I'm going to use Lang chain llama import chat Ollma Now here I'm just going to specify Lama 31 again。

 we already grabbed this so if you look above here Alllama pullllma 3。

1 I have llama running in the background that's all you need to do and then this should be available to me as long as I've pulled the model so that's it。



![](img/b4a524dad6217cb8930d33cfb95458ad_41.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_42.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_43.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_44.png)

Now this is going to be a simple rag prompt， you're an assistant for question answering tasks。

 use the following documents to enter the question if you don't know the answer。

 just say you don't know okay， so that's just like a really simple basic rag chain I'm going to build and we're done so that's our rag chain。



![](img/b4a524dad6217cb8930d33cfb95458ad_46.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_47.png)

嗯。Now， here is another component we're gonna to need。 We're gonna need a retrieval greater。

 So if you kind of think about the flow we did above here。 we just defined our rag James。

 that's going to be this kind of piece right here。 We also need a greater piece。

 We build our vector store。 we have a web search tool。 And now we need the grader。

 That's the final thing we need。 So for this， I'm going show I'm going use something that's very convenient。

 JO mode from Oama。 And in my greater pump， I'm basically going say your' greater assessing the relevance of retrieve document to use your question。

 Here's the document， here's the question。 If it contains keywords later。

 The question grade is relevant。 it is not going to be stringent。

 You're just trying to kind of filter out erroneous retrievals。 Give a binary score of yes， no。

 return it as Json。 That's it。 So super simple。 we have a greater。 So that's really it。😊。



![](img/b4a524dad6217cb8930d33cfb95458ad_49.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_50.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_51.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_52.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_53.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_54.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_55.png)

No we have a grader。

![](img/b4a524dad6217cb8930d33cfb95458ad_57.png)

So we can go ahead and go down here。 And now I'm just going build my little land graph。

 And so you're going to see all we need to do。 So Lagra is a really nice way to lay out control flows。

 They can be kind of custom flows that you want to express some kind of agent reasoning， right？

 So we're going to set up a graph state， our graph is can attain a few relevant things per of chain a question。

 a generation， search， whether not to search yes or no documents retrieved and the steps we're taking throughout our chain。

 So that's all we need to persist through state。😊。

![](img/b4a524dad6217cb8930d33cfb95458ad_59.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_60.png)

We have this retrieve node， so basically each node is just a function。

So Ive set it in the retrieve node， it pulls in state from state， I can get anything I need。

 so all these things are accessible to me when I pull in state to each node。

 so I can get the question I can get the documents from my retriever。



![](img/b4a524dad6217cb8930d33cfb95458ad_62.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_63.png)

I can note that basically pull in the prior steps I've taken。

 append this particular step retrieve documents and then return documents。

 question and steps back to state So that's all I'm going to do and I'm just going to walk through my flow so I going have a retrieve step。



![](img/b4a524dad6217cb8930d33cfb95458ad_65.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_66.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_67.png)

And we can go back to our diagram here， we can kind of see this vector store retrieval is basically going to be retrieve。



![](img/b4a524dad6217cb8930d33cfb95458ad_69.png)

So that's kind of our first node is retrieve。

![](img/b4a524dad6217cb8930d33cfb95458ad_71.png)

Our generate node then is going to is going to be this one right here， so again。

 just we're going to get the question， the documents before call the rag chain with the documents in question。

 append， generate answer to the steps and return。

![](img/b4a524dad6217cb8930d33cfb95458ad_73.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_74.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_75.png)

Same with grade documents。 So this is going to be the step here。 In this particular case。

 you know same kind of flow。 We take the state。 we get the question， we get the documents。 Now。

 initially， we say we are not going to search。 and we iterate through our documents。

 we grade each one for relevance to the question。 and get we get the grade back。 Now。

 if the grade is yes， we just append the documents So that means it's relevant。 If the grade is no。

 then we basically set our search flag。 we say， okay， one of the documents is irrelevant。

 we're going to search and we keep going。 So we iterate through all of our documents。

 we assess the relevance and we keep going。 And finally， we have this web search node。

 which is down here and this just calls our search tool。 So web search tool invoke with the question。

 get get the search results， add them to our documents and return the state。😊。



![](img/b4a524dad6217cb8930d33cfb95458ad_77.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_78.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_79.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_80.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_81.png)

This fine this final thing is basically just this edge we set right here。

 So basically we get the search state， which is either yes or no。 If it's yes。

 go to search if it's not go to generate。 So that's basically this logic right here。

 and you're going to see。

![](img/b4a524dad6217cb8930d33cfb95458ad_83.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_84.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_85.png)

In one second here， this is the whole control flow。 So this is where all those pieces come together。

 and expresses exactly what we kind of drew out here in our cartoon。

 but this is in Landgra as a kind of lagra custom agent or custom control flow。 So you start。

 you do retrieval。 do the grading step we just talk through to look at each document。

 Is it relevant to the question。 if any is not relevant， we kick out， we do web search。

 we add the search results to our documents。 We send the documents to the generate step and then we end that's it super simple。

 but I've used this in a whole bunch of different tests it like a really nice vibe test for different models。

 So anyway， I like that we have our little agent laid out here。 So cool we've copied all that over。

 We just walked through it。 And now we can just run it。 Let's test it out So we can see right here。

 I have a little function。 So basically this config is something I can use with lagra。

 So thread I is not really relevant here。 but if you ever want to， for example。

 save the state of a particular execution。 you can use threads to do that and I talk。😊。



![](img/b4a524dad6217cb8930d33cfb95458ad_87.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_88.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_89.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_90.png)

![](img/b4a524dad6217cb8930d33cfb95458ad_91.png)

That in some other videos so I'll link them below if you're interested in how threads work。

 but for this， all we need do would take our custom agent。

 we're going to invoke it with basically a question we'll send that in we'll kind of send in a question as an example di here we'll pass it into our function and then we're going to go ahead and return the response and that's it so let's go ahead and test that out。



![](img/b4a524dad6217cb8930d33cfb95458ad_93.png)

So。