# LangChain【中英⚡使用 LangChain 从零开始构建 RAG 系统｜RAG From Scratch】 p10 P10 from scratch： Part 10 (Routing) -BV1FgfMYLEve_p10-

Hi， this is Lance from Langcha， This is the 10th video in our rack from Sct materials focused on routing。



![](img/19ae6bf2da43f76684260f6335e6439b_1.png)

So we talk through query translation， which is the process of taking a question and translating it in some way。

 it could be decomposing it， using step back prompting or otherwise。

 but the idea here was taking a question， changing into a form that's better suited for retrieval。

Now routing is the next step which is basically routing that potentially decomposed question to the right source。

 and in many cases that could be a different database， so let's say in this toy example。

 we have a vector store， a relational DB and a graph DB that what we' redo with routing is we simply route the question based upon the content the question to the relevantman data source。

So there's a few different ways to do that One is what we call logical routing in this case we basically give an LLM knowledge of the various data sources that we have at our disposal and we let the LLM kind of reason about which one to apply the question to so it's kind of like the LM is applying some logic to determine which data source for example to use alternatively can do semantic routing which where we take a question we embed it and for example we embed prompts。

 we then compute the similarity between our question and those prompts。

 and then we choose a prompt based upon the similarity so the general idea is in our ti and we talk about routing for example。

 a different database， but it can be our general can be routing to different prompt it can be you really arbitrarily taking this question and sending it at different places be at different prompts be at different vector stores。



![](img/19ae6bf2da43f76684260f6335e6439b_3.png)

![](img/19ae6bf2da43f76684260f6335e6439b_4.png)

![](img/19ae6bf2da43f76684260f6335e6439b_5.png)

![](img/19ae6bf2da43f76684260f6335e6439b_6.png)

So let's walk through the code a little bit。

![](img/19ae6bf2da43f76684260f6335e6439b_8.png)

So you can see just like before， we've done a few piippens， we've set up blanksmith。



![](img/19ae6bf2da43f76684260f6335e6439b_10.png)

And let's talk through logical routing first， so in this toy example， let's say we had， for example。

 three different docs like we had Python docs， we had JS docs， we had golan docs。



![](img/19ae6bf2da43f76684260f6335e6439b_12.png)

What we want to do is take a question， route it to one of those three。

So what we're actually doing is we're setting up a data model。

 which is basically going to be bound to our LLM。And allow the LM to output one of these three options as a structured object。

 so you really think of about this as like classification。

Classification plus function calling to produce a structured output。

 which is constrained to these three possibilities。So the way we do that is。

 let's just zoom in here a little bit。

![](img/19ae6bf2da43f76684260f6335e6439b_14.png)

We can define like a structured object we want to get out from our LLM。



![](img/19ae6bf2da43f76684260f6335e6439b_16.png)

Like in this case， we want， for example， you know， one of these three data sources to be output。



![](img/19ae6bf2da43f76684260f6335e6439b_18.png)

We can take this and we can actually convert it into Open AI， for example， function schema。



![](img/19ae6bf2da43f76684260f6335e6439b_20.png)

And then we actually pass that in and bind it to our LLM so what happens is we ask a question our LLM invokes this function on the output to produce an output that adheres to the schema that we specify so in this case for example。

 we output like you know in this to example， let's say we wanted like you know an output to be data source vector store or SQL database。

 the output will contain a data source object and it'll be you know one of the options we specify as a JSON stream。

We also instant a parser from this object to parse that Json string to an output like a pedantic object。

 for example， so that's just one toy example。 And let's show one up here。

 So in this case again we had our three doc sources。



![](img/19ae6bf2da43f76684260f6335e6439b_22.png)

![](img/19ae6bf2da43f76684260f6335e6439b_23.png)

We bind that to our LLM， so you can see do with structured output， basically under the hood。

 that's taking that object definition， turning into function schema and binding that function schema to our LLM。



![](img/19ae6bf2da43f76684260f6335e6439b_25.png)

![](img/19ae6bf2da43f76684260f6335e6439b_26.png)

![](img/19ae6bf2da43f76684260f6335e6439b_27.png)

And we call our prompt， you're an expert at routing a user question based on you know programming language that user are referring to。

 so let's define our router here。

![](img/19ae6bf2da43f76684260f6335e6439b_29.png)

![](img/19ae6bf2da43f76684260f6335e6439b_30.png)

Now what we're going to do is we'll ask a question that is Python code。



![](img/19ae6bf2da43f76684260f6335e6439b_32.png)

So we'll call that and now it's done and you can see the object we get out is indeed it's a route query object。

 so it's exactly it adheres to this data model we've set up。



![](img/19ae6bf2da43f76684260f6335e6439b_34.png)

![](img/19ae6bf2da43f76684260f6335e6439b_35.png)

And in this case， it's correct， so it's calling this Python dooxy we can extract that right here as a string。

Now， once we have this， you can really easily set up like a route so this could be like our full chain where we take this route or which should define here and then this choose route function can basically take that output and do something with it。

 So for example， if Python docs this could then apply the question to like a retriever full of Python information or JS same thing So this is where you would hook basically that question up to different chains that are like you know retriever chain one for Python retriever chain2 for Js and so forth。

 So this is kind of the routing mechanism， but this is really doing the heavy lifting of taking an input question and turn into a structured object that restricts the output to one of a few output type so we care about in our like routing problem so that's really kind of the way this all hooks together。



![](img/19ae6bf2da43f76684260f6335e6439b_37.png)

![](img/19ae6bf2da43f76684260f6335e6439b_38.png)

![](img/19ae6bf2da43f76684260f6335e6439b_39.png)

![](img/19ae6bf2da43f76684260f6335e6439b_40.png)

![](img/19ae6bf2da43f76684260f6335e6439b_41.png)

![](img/19ae6bf2da43f76684260f6335e6439b_42.png)

Now， semantic routing is actually may a little bit more straightforward based on what we've seen previously。



![](img/19ae6bf2da43f76684260f6335e6439b_44.png)

So in that case， let's say we have two prompts， we have a physics prompt， we have a math prompt。



![](img/19ae6bf2da43f76684260f6335e6439b_46.png)

We can embed those prompts。

![](img/19ae6bf2da43f76684260f6335e6439b_48.png)

No problem。 We do that here。Now let's say we have an input question from a user like in this case what is a black hole。

 we pass that through， we then apply this run of a Lambda function， which is defined right here。

 what we're doing here is we're embedding the question。

 we're computing similarity between the question and the prompts， we're taking the most similar。

And then we're basically choosing the prompt based upon that similarity。

 and you can see let's run that and try it out。

![](img/19ae6bf2da43f76684260f6335e6439b_50.png)

And we're using the physics prompt and there we go， black holess region and space。

 so that just shows you kind of how you can use semantic routing to basically embed a question。

 andbed， for example， various prompts， pick the prompt based on semantic similarity。



![](img/19ae6bf2da43f76684260f6335e6439b_52.png)

![](img/19ae6bf2da43f76684260f6335e6439b_53.png)

![](img/19ae6bf2da43f76684260f6335e6439b_54.png)

![](img/19ae6bf2da43f76684260f6335e6439b_55.png)

So that really gives you just two ways to do routing one is logical rout and the function calling it can be used very generally in this case we applied it to like different coding languages but imagine these can be swapped out for like you know my Python my like vector store versus my GraDB versus my relational DB and you can just very simply have some description of what each is and you know then not only will the LLM do reasoning but it'll also return an object that can be parsed very cleanly to produce like one of a few very specific types which then you can reason over like we did here in your routing function so that kind of gives you the general idea and these are very very useful tools and I encourage you to experiment with them thanks。



![](img/19ae6bf2da43f76684260f6335e6439b_57.png)

![](img/19ae6bf2da43f76684260f6335e6439b_58.png)

![](img/19ae6bf2da43f76684260f6335e6439b_59.png)

![](img/19ae6bf2da43f76684260f6335e6439b_60.png)

![](img/19ae6bf2da43f76684260f6335e6439b_61.png)

![](img/19ae6bf2da43f76684260f6335e6439b_62.png)