# LangChain【中英⚡LangGraph 使用指南｜LangGraph (Python)】 p12 P12 Self-reflective RAG with LangGraph： Self-RAG and CRAG -BV1vJfMYuEon_p12-

This is Lance from Lang chain， I'm going to be talking about using Landgraft to build diverse and sophisticated rag flows。

So just to set the stage， the basic rag flow you can see here starts with a question retrieval of relevant documentss from an index。

 which are passed into the context window of an LLM for a generation of an answer ground in their group documents。

 that's kind of the basic outline。And we can see it's like a very linear path。In practice， though。

 you often encounter a few different types of questions。Like， when do we actually want to retrieve？

Based upon the context of the question， are the retrieve documents actually good or not？

And if they're not good， then we discard them， and then how do we loop back and retry retrieval with。

 for example， an improved question？So these types of questions motivate an idea of active rag。



![](img/7bbc8872412b78b5d231191522cb3256_1.png)

Which is a process where an LLMS actually decides when and where to retrieve based upon like existing retrievals。



![](img/7bbc8872412b78b5d231191522cb3256_3.png)

Or existing generations。Now， when you think about this。

 there's a few different levels of control that you have over an LLM。



![](img/7bbc8872412b78b5d231191522cb3256_5.png)

In a RA application。The base case like we saw with our chain is you just use LM to choose a single steps output。

So for example， in traditional rag， you feed it documents and it decides to generation。

 so it's just kind of one step。Now a lot of RAG workflows will use a of routing。

 so like given a question， should I route it to a vector store or a G DB？

And we have seen this quite a bit。Now， this newer idea that I want to introduce is。

How do we build more sophisticated logical flows in a RAG pipeline that you let the LLM choose between different steps。

 but specify all the transitions that are available？

And this is known as what we call it state machine。



![](img/7bbc8872412b78b5d231191522cb3256_7.png)

Now。There's a few different architectures that have emerged to build different types of rack chains。

And of course， chains are traditionally used just for like very basic rad。

But this notion of a state machine is a bit newer and Langgra， which we recently released。

 provides a really nice way to build state machines for RAG。And for other things。

And the general idea here is that you can lay out more diverse and complicated rag flows and then implement them as graph。

And it kind of motivates this more broad idea of like flow engineering and thinking through the actual like workflow that you want and then implementing it。



![](img/7bbc8872412b78b5d231191522cb3256_9.png)

And we're going to actually do that right now。So I'm going to paint a recent paper called CAG corrective R。

 which is really a nice method。

![](img/7bbc8872412b78b5d231191522cb3256_11.png)

For active Rag， that incorporates a few different ideas。



![](img/7bbc8872412b78b5d231191522cb3256_13.png)

So first you retrieve documents。And then， you grade them。Now， if at least one document。

Exceeds the threshold for relevance。You go to generation， you generate your answer。

U and it does this knowledge refinement stage after that。

 but let's not worry about that for right now it's kind of not essential for understanding the basic flow here。

 so again you do a grade for relevance for every document if any is relevant you generate。



![](img/7bbc8872412b78b5d231191522cb3256_15.png)

Now， if they're all ambiguous or incorrect based upon your grader。



![](img/7bbc8872412b78b5d231191522cb3256_17.png)

You retrieve from an external source， they use web search。



![](img/7bbc8872412b78b5d231191522cb3256_19.png)

And then they pass that as their context for answer generation。



![](img/7bbc8872412b78b5d231191522cb3256_21.png)

So it's a really neat workflow where you're doing retrieval， just like with basic RaG。

 but then you're reasoning about the documents， if they're relevant。

 go ahead and at least one is relevant， go ahead and generate if they're not retrieved from alternative source。

And then pack that into the context and generate your answer。



![](img/7bbc8872412b78b5d231191522cb3256_23.png)

So let's see how we would implement this as a estate machine。



![](img/7bbc8872412b78b5d231191522cb3256_25.png)

Using La graph。We'll make a few simplifications。

![](img/7bbc8872412b78b5d231191522cb3256_27.png)

嗯。We're going to first decide if any documents are relevant， we'll go ahead and do the web search。😡。

To supplement the output so that's just a kind of one minor modification we'll use Tt search for web search we'll use query writing to optimize the search for to optimize the web search。

 but it follows a lot of the the intuitions of the main paper。Sll note here， we set the Tla API key。

And another small mode， I've already set my Langsmith API key。

 which we'll see is useful a bit later for observing the resulting traces。



![](img/7bbc8872412b78b5d231191522cb3256_29.png)

Now I'm going to index three blog posts that I like。I'm going to use ChroatDb。

 I'm going to use open eyebeddings， I'm going to run this right now。

 this will create a vector store for me from these three blog posts。



![](img/7bbc8872412b78b5d231191522cb3256_31.png)

![](img/7bbc8872412b78b5d231191522cb3256_32.png)

🤧And then what I'm going to do is define state。

![](img/7bbc8872412b78b5d231191522cb3256_34.png)

Now， this is kind of a core object that's going be passed around my graph that I'm going to modify。



![](img/7bbc8872412b78b5d231191522cb3256_36.png)

And right here is where I define it， and the key point to note right now is it's just a dictionary。

And as we contain things that are relevant for RAG like question documents generation。

 and we'll see how we update that in a little bit， but the first thing to note is。

We define our state， and this is what's going to be modified in every node of our graph。😡。



![](img/7bbc8872412b78b5d231191522cb3256_38.png)

Now here's really the crux of it， and this is the thing I want to zoom in on a little bit。



![](img/7bbc8872412b78b5d231191522cb3256_40.png)

So。

![](img/7bbc8872412b78b5d231191522cb3256_42.png)

When you kind of move from just thinking about prompts to thinking about overall flows。

 it's like kind of a fun and interesting exercise， I kind of think about this as it's been mentioned on Twitter a little bit more like flow engineering。

So let's think through what was actually done in the paper。

And what modifications to our state are going to happen in each stage， so we start with the question。

 you can see that on the far left and this kind of state is represented a dictionary like we have。

 we start with the question we perform retrieval from our vector start which we just created。

 that's going to give us documents。So that's one node。

We made an adjustment to our state by adding documents。That's step one。

Now we have a second node where we're going to grade the documents and in this node we might filter some out。

 so we are making a modification state， which is why it's a node。So we're going to have a grader。

Then we're going to have what we're going to call a conditional edge。

So we saw we went from question to retrieval， retrieval always goes to grading。

 and now we have a decision。If any document is irrelevant。

We're going to go ahead and do web search to supplement。And if they're all relevant。

 we'll go to generation， it's a minor kind of a minor kind of logical decision that we're going to make。

嗯。If any are not relevant， we'll transform the query。

And we'll do web search and we'll use that for generation so that's really it and that's how we can kind of think about our flow and how our states can be modified throughout this flow。



![](img/7bbc8872412b78b5d231191522cb3256_44.png)

Now， all we then need to do。 and I kind of found spending。



![](img/7bbc8872412b78b5d231191522cb3256_46.png)

10 minutes thinking carefully through your flow engineering。Is really valuable because from here。

 it's really just implementation details。And it's pretty easy， as you'll see。



![](img/7bbc8872412b78b5d231191522cb3256_48.png)

So basically。I'm going to run this code block， but then we can like walk through some of it。

 I won't show you everything so it'll get a little bit boring， but really all we're doing。



![](img/7bbc8872412b78b5d231191522cb3256_50.png)

![](img/7bbc8872412b78b5d231191522cb3256_51.png)

Is we're finding functions for every node。

![](img/7bbc8872412b78b5d231191522cb3256_53.png)

That take in the state and modify in some way， that's all that's going on so think about retrieval。



![](img/7bbc8872412b78b5d231191522cb3256_55.png)

We run retrieval， we take in state， remember it's a diict， we get our state dicked like this。

 we extract one key question from our dic。We pass that tour Retrir。

 we get documents and we write back out state now with Do key added， that's all。



![](img/7bbc8872412b78b5d231191522cb3256_57.png)

Generate it's going to be similar， we take in state， now we have our question and documents。

 we pull in a prompt， we define an LLM， we do minor postprocesing on documents。

 we set up a chain for retrieval or sorry for generation， which is just going to be take our prompt。

 plum that to an LLM， parse the output to a string， and we run it right here。

 invoking our documents in our question to get our answer， we write that back to state。



![](img/7bbc8872412b78b5d231191522cb3256_59.png)

That's it。

![](img/7bbc8872412b78b5d231191522cb3256_61.png)

And you can kind of follow here for every node， we just define a function that performs the state modification that we want to do on that node。



![](img/7bbc8872412b78b5d231191522cb3256_63.png)

Grading documents is going to be the same in this case I do a little thing extra here because I actually define a pantic data model for my grader so that the output of that particular grading chain is a binary yes or no you can look at the code make sure it's all shared and that just makes sure that our output is very deterministic so that we then can down here perform logical filtering。



![](img/7bbc8872412b78b5d231191522cb3256_65.png)

![](img/7bbc8872412b78b5d231191522cb3256_66.png)

![](img/7bbc8872412b78b5d231191522cb3256_67.png)

So what you can see here is we define this search value， no。And we iterate through our documents。

 we grade them。If any document is graded as not relevant。We flagged this search thing to yes。

That means we're going to perform web search。We then add that to our state d at the end and run web search now that value is true。

 that's it。

![](img/7bbc8872412b78b5d231191522cb3256_69.png)

![](img/7bbc8872412b78b5d231191522cb3256_70.png)

And you can kind of see we go through some other nodes here as web search node Now here is where our one conditional edge we define right here。

 this is where we decide to generate or not based on that search key so we again get our state。

 let's extract the various values so we have this search value now if search is yes。



![](img/7bbc8872412b78b5d231191522cb3256_72.png)

We return the next no that we want to go to。So in this case， there'll be transfer query。

 which will then go to web search。Else， we go to generate。



![](img/7bbc8872412b78b5d231191522cb3256_74.png)

So what we can see is。We laid out our graph。😡。

![](img/7bbc8872412b78b5d231191522cb3256_76.png)

Whatch you can kind of see up here。And now we define functions for all those nodes as well as the conditional edge。



![](img/7bbc8872412b78b5d231191522cb3256_78.png)

And now。

![](img/7bbc8872412b78b5d231191522cb3256_80.png)

We scroll down all you have to do is just lay that out here again as our flow and this is kind of what you might think of as like kind of flow engineering where you're just laying out the graph as you drew it。



![](img/7bbc8872412b78b5d231191522cb3256_82.png)

Where we have set our entry point as retrieve， we're adding an edge between Rettri and grade documents。

 so we went retrieval， grade documents， we add our conditional edge depending on the grade。

 either transform the query， go to web search or just go to generate。

 we create an edge between transform the query and web search， then web search to generate。



![](img/7bbc8872412b78b5d231191522cb3256_84.png)

And then we also have an edge generated to end and that's a whole graph that's it so we can just run this。



![](img/7bbc8872412b78b5d231191522cb3256_86.png)

And now I'm going to ask a question， so let's just say， how does agent memory work， for example。

 let's just try that。And what this is going to do is going to print out what's going on as we run through this graph。

So first， we can see output from retrieve。This is going to be all of our documents that we retrieved。

 so that's fine， this is from our retriever。Then you can see that we're doing a relevance check across our documents。

And this is kind of interesting， right， you can see we are grading them here。

 one is grade is not relevant。

![](img/7bbc8872412b78b5d231191522cb3256_88.png)

and okay， you can see the documents are now filtered because we' removed the one that's not relevant and because one is not relevant。

 we decide， okay， we're going to just transform the query and run web search。

And you can see after queryer transformation， we rewrite the question slightly。

We then run web search。And you can see from web search， it searched from some additional sources。

 which you can actually see here， it's appended。As a so here it is。

 so here it's a new document appended from web search， which is from memory knowledge requirements。

 so it may seem looked up some AI architecture related to memory web results so that's fine that's exactly what we want to do。

😊，And then we generate a response。

![](img/7bbc8872412b78b5d231191522cb3256_90.png)

So that's great and this is just showing you everything in kind of gory detail。

But I'm going to show you one other thing that's really nice about this。If I go to Langsmith。



![](img/7bbc8872412b78b5d231191522cb3256_92.png)

Okay。I have my AP AI key set， so all my generations are just logged to Langsmith and I can see my Lng graph run here。



![](img/7bbc8872412b78b5d231191522cb3256_94.png)

![](img/7bbc8872412b78b5d231191522cb3256_95.png)

Now what's really cool is this shows me all of my nodes。 So remember we had retrieve grade。😊。

We evaluated the grade because one was irrelevant， we then went ahead and transform the query。

 we did a web search， weend that to our context you can see all those steps are laid out here in fact you can even look at every single grade and its output I will move this up slightly。



![](img/7bbc8872412b78b5d231191522cb3256_97.png)

![](img/7bbc8872412b78b5d231191522cb3256_98.png)

![](img/7bbc8872412b78b5d231191522cb3256_99.png)

So you can see the different scores or grades， okay so this particular retrieval was graded as not relevant so that's fine that can happen in some cases and because of that we do a  query transformation so we modified the question slightly how does memory how does the memory system and artificial agents function so it's just a minor rephrase with the question we did this heavily web search this is where it queried from this particular blog post or medium so it's like a same grab query we can like Sandy check it and then what's neat is we can go to our generate step look at open AI and here's our full prompt。



![](img/7bbc8872412b78b5d231191522cb3256_101.png)

How does the memory system in our official agents function and then here's all of our documents so this is this is the web search as well as we still have the relevant chunks that were retrieved from our blog posts and then here's our answer so that's really it you can see how really moving from the notion of just like。



![](img/7bbc8872412b78b5d231191522cb3256_103.png)

I'll actually go back to the original moving from。

![](img/7bbc8872412b78b5d231191522cb3256_105.png)

I will try to open this up a little bit。

![](img/7bbc8872412b78b5d231191522cb3256_107.png)

啊。

![](img/7bbc8872412b78b5d231191522cb3256_109.png)

Yeah， I can see my face still。

![](img/7bbc8872412b78b5d231191522cb3256_111.png)

。The transition from。Laying out simple chains。

![](img/7bbc8872412b78b5d231191522cb3256_113.png)

To flows is a really interesting and helpful way of thinking about why graphs are really interesting because。



![](img/7bbc8872412b78b5d231191522cb3256_115.png)

You can encode more sophisticated logical reasoning workflows。But in a very。

Like clean and well engineered way where you can specify all the transitions that you actually want to have executed and。



![](img/7bbc8872412b78b5d231191522cb3256_117.png)

I actually find this way of thinking and building kind of logical like workflows really intuitive。

 we have a blog post coming out tomorrow that discusses both implementing selfRG as well as CRAG for two different active Ra approaches using this idea of state machines and Landgra so I encourage you to play with it。

 I found it really intuitive to work with。

![](img/7bbc8872412b78b5d231191522cb3256_119.png)

![](img/7bbc8872412b78b5d231191522cb3256_120.png)

![](img/7bbc8872412b78b5d231191522cb3256_121.png)

![](img/7bbc8872412b78b5d231191522cb3256_122.png)

![](img/7bbc8872412b78b5d231191522cb3256_123.png)

I also found inspection of traces to be quite intuitive using Lagra because every node is enumerated pretty clearly for you。

 which is not always the case when you're using other types of more complex reasoning approaches。

 for example， like agents。

![](img/7bbc8872412b78b5d231191522cb3256_125.png)

So in any case， I hope this was helpful and I definitely encourage you to check out kind this notion of like flow engineering using Lagrara and in the context of RAG it can be really powerful。

 hopefully as you've seen here， thank you。