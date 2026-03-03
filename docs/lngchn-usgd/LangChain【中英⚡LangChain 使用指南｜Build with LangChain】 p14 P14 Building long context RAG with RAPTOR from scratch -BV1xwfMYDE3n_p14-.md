# LangChain【中英⚡LangChain 使用指南｜Build with LangChain】 p14 P14 Building long context RAG with RAPTOR from scratch -BV1xwfMYDE3n_p14-

Hi， this is Lance from Langch。I'm going to be talking about retrieval and long contact LLMs。

And a new method called Rator。So over the last few weeks there's been a lot of talk about is Ra dead with the advent of new long Con LLMs like Gemini。

 a million tokens， Claude3 now with up to a million tokens， it's an interesting question。

I've recently been using long context LLMs for certain projects。Like， for example。

 this code assistant that I put out last week。Basically use the long context LLM to answer coding questions about our docs on La expression language。

 I'll kind of zoom in here so you can see it so these are around 60，000 tokens of context。



![](img/8f503079fd2a193cb8f8fea934be2a34_1.png)

We take the question， we take the docs， and we produce an answer， and this is really nice。

 no retrieval required， just context stuff， all these docs and perform answer generation directly so I'm a big fan of using long context LLMs in this way。



![](img/8f503079fd2a193cb8f8fea934be2a34_3.png)

But there are some considerations I wanted to kind of point out here。

So I ran evaluations and for those evaluations， I look at 20 questions。

 so basically it's 20 generations。

![](img/8f503079fd2a193cb8f8fea934be2a34_5.png)

Now look here， so this is the Langsmith dashboard that I used for those Evals and you can see something kind of interesting。



![](img/8f503079fd2a193cb8f8fea934be2a34_7.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_8.png)

The P50 latency tells you the 50th percentile latency for each of those generations， so again。

 remember there's 20。So it's around 35 to you 46 seconds depending on the trial。

 this is on the same data set， same 20 questions， there's some variance run to run so that's kind of expected and again the P99 it's up to like okay 420 seconds that's really long in that case。



![](img/8f503079fd2a193cb8f8fea934be2a34_10.png)

But maybe more interestingly， if you look at the cost， again， there's 20 questions。

 so the cost is ranging from maybe like a dollar to know a dollar， a dollar like 30 per generation。

So， you know， constantly are things to think about when you're talking about using really long context LLMs as opposed to like a ragG system where you're performing retrieval of much smaller。

 more directed chunks to your question。

![](img/8f503079fd2a193cb8f8fea934be2a34_12.png)

Now， the other thing that came up is a lot of people asked， hey。

 can you swap this out and use a local LLM？And my go to local LLN is Mil 7b V2。

 which actually has a 32，000 token context window， but that's still a little bit big relative to my docs。

 which are around 60，000 tokens。

![](img/8f503079fd2a193cb8f8fea934be2a34_14.png)

So， you know， I couldn't just context stuff them as I did here。

So these three considerations kind of led me to think about。



![](img/8f503079fd2a193cb8f8fea934be2a34_16.png)

I really like working with long context models and it's absolutely going to be the continuing thing。

But are there retrieval strategies that are like lightweight easy to use with long context models that kind of like preserve the ability to utilize a lot of context but can address some of these limitations in particular this last piece was important because this is something I wanted to do kind of in the near termm and I need kind of like a nice lightweight retrieval strategy that still uses long context。

 but can operate in cases where my documents are maybe just a little bit bigger than my context window in this case like around 2x。



![](img/8f503079fd2a193cb8f8fea934be2a34_18.png)

So I kind of put this on Twitter and said， hey。Has anyone come across like good。

 like maybe minimalist splitting strategies for long context LMs， you know。

 like I wanted to rag with Miral 7B with a 32，000 token context window， but my docs are 60。

000 tokens。I can't just contact St them。But I also don't want some like very fine scale chunking thing。

 like I get it we don't want to mess with all that。

 we want something simple that just can like kind of work across larger documents。



![](img/8f503079fd2a193cb8f8fea934be2a34_20.png)

So one point that was raised， which is a really good one is， well。

 just index at the document level so you can take full documents and just embed them directly。



![](img/8f503079fd2a193cb8f8fea934be2a34_22.png)

It's a fairPo and then you do something like K&N on those embedded documents。

 so again no chunking of any documents， no splitting of documents。

 you have your set of documents embeddedbed each one and just retrieve at the document level that's a pretty good idea that's pretty reasonable。



![](img/8f503079fd2a193cb8f8fea934be2a34_24.png)

Another idea that came up though is this idea of building a document tree。

 and part of the reason for that is when you talk about something like KNN or like know K nearest neighbor retrieval on a set of embedded documents。

 it is true that sometimes an answer requires maybe two or three different documents kind of integrated in order to answer it。



![](img/8f503079fd2a193cb8f8fea934be2a34_26.png)

Now if you context stuff everything that's not a problem because it's all there。

 if you're doing retrieval， well you're setting your K parameter to be some value。

 it's kind of brittle， do you need to be like four or five or six to capture all the content needed for certain particular questions。

 so it's kind of hard to set that。

![](img/8f503079fd2a193cb8f8fea934be2a34_28.png)

So this idea of building a documentary is kind of an interesting way to potentially address this challenge with like basic KNN。



![](img/8f503079fd2a193cb8f8fea934be2a34_30.png)

So a paper Rator came out recently on this exact idea。



![](img/8f503079fd2a193cb8f8fea934be2a34_32.png)

And their code recently opened source， which led the folks atllma Ined to come out with Alllama Pack Fre it。

 which is great。

![](img/8f503079fd2a193cb8f8fea934be2a34_34.png)

And the idea is pretty interesting， so I wanted to kind of lay it out here and talk about how it might benefit this exact case of kind of long context retrieval。



![](img/8f503079fd2a193cb8f8fea934be2a34_36.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_37.png)

So the intuition is pretty simple。First， we take a set of documents。

Now note that these documents can be any sized， so in their case they're just chunks。

 so they're like 100 tokens。But it doesn't matter， so we start with a set of raw documents。

Now what we do is we embed them。And then we cluster them。

So this clustering process groups together like documents。

 and then we do one important thing We summarize information in that cluster into what we call kind of like a more abstract or higher level summary of that content。

And we do that recursively until we end up with one cluster。

That's it So what's happening is you're starting with this set of what they call leavess or like raw documents。

You do a grouping。V clustering， you do summarization steps you're kind of compressing。

 and then you do it again。And the idea is that these kind of mid level or eventually。

 like root level or highest level summaries can consolidate information from different places in your documents。

Now what they do is they basically just embed those summaries along with the raw leafs and they perform retrieval and we'll talk about that a little bit later。

 but what they show is actually just doing retrieval on all these together like as a whole Po performs best and that's kind of a nice result it's pretty easy then to basically just index that and use it。



![](img/8f503079fd2a193cb8f8fea934be2a34_39.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_40.png)

I will make a note that their paper talked about you know these leafs being chunks。

 which I didn't love because look I want to work with lung context models and like I don't want to deal with chunking at all and I've replied you know I've replied to Jerry's tweet on this and Jerry made a fair point that you know this can scale to anything so for example those leafs can be full documents they don't have to be chunks that's completely reasonable point so again you can kind of think about this as if I one was let's just take each document and embed it。



![](img/8f503079fd2a193cb8f8fea934be2a34_42.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_43.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_44.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_45.png)

Idea2 is well let's embed each document like we did and we can also build kind of like a document abstraction tree on top and embed those so we have these like higher level summaries in our embeddings which we can retrieve from if we need an answer to can information from like a small set of documents right so it's a little bit more robust maybe to this problem which is that if I'm just doing K andN on raw documents and I need information from like two or three documents。



![](img/8f503079fd2a193cb8f8fea934be2a34_47.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_48.png)

I'm not guaranteed to always get that because of this K parameter that I sit。

 I'm only retrieving K docs， whereas here I'm building these docs that contain information from multiple leavess or multiple subdocs。

 so to speak， and it can actually at least just capture that information in kind of a nice way such that it can basically integrate information across different individual leaps or individual documents。



![](img/8f503079fd2a193cb8f8fea934be2a34_50.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_51.png)

So that's the key point。

![](img/8f503079fd2a193cb8f8fea934be2a34_53.png)

U and so we can kind of see when you think about like lower and long context models， of course。

 context stuffing is a great option if you can do it， but there are some other interesting ideas。

 one is actually just embedding full documents and another is this idea of again documents and an abstraction tree。

So let's go ahead and just build Rapttor because it's pretty interesting。



![](img/8f503079fd2a193cb8f8fea934be2a34_55.png)

And to do this， I'm actually going to look at Cla3， which just came out today。

 it's a new set of models stranthropic， really strong performance and should be really good for this use case because what I want to do is I want to perform summaries of individual documents and I don't really want to worry about the size of those documents。



![](img/8f503079fd2a193cb8f8fea934be2a34_57.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_58.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_59.png)

so I'm going to use same set of documents that I previously did with the cogen example that video came out last week and I have an empty notebook here。

 we just do a few P installs， I'm setting a few environment variables for Langsmith and now I'm just going to say grab my docs。



![](img/8f503079fd2a193cb8f8fea934be2a34_61.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_62.png)

![](img/8f503079fd2a193cb8f8fea934be2a34_63.png)

So that's right here。