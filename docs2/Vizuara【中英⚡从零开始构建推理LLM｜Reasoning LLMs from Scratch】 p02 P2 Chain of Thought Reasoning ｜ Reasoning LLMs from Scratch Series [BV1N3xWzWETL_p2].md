# Vizuara【中英⚡从零开始构建推理LLM｜Reasoning LLMs from Scratch】 p02 P2 Chain of Thought Reasoning ｜ Reasoning LLMs from Scratch Series [BV1N3xWzWETL_p2]

![](img/c7695f2fc984fcb1de303d16a38bb596_0.png)

🎼Yeah。

![](img/c7695f2fc984fcb1de303d16a38bb596_2.png)

Hello everyone and welcome to this second lecture on the reasoning based La language models。

If you have missed the first lecture， I strongly recommend you to go back to the introduction video where we have properly introduced the series and how we are going to be structuring this entire course。

In today's lecture， we will start with the first method which can be used to impart reasoning capabilities to large language models。

Imagine that the timeframe that we are starting from is December 22 when GPPT 3。5 was released first。

Remember that it was made to answer like humans， but it was not made to think like humans。

It was not a reasoning， a large language model。Slowly from there on。

 we have come to a stage where we have large language models that can actually reason。

That can give you the series of steps which they go through before they give you the final answer。

Open AI's O model was the first reasoning based model after that there have been a number of reasoning based LLms which have come into the picture。

 for example deep sea carbon。So whenever you are listening to this lecture。

 keep in mind that the time frame is 2022 onwards。Because that is the time after which people started to think about reasoning based LLM seriously。

And nowadays， a lot of companies and。Almost all LLM providers have a reasoning LLM in their armor。

Okay， so now we are going to cover method number one， which is inference time compute scaling。

So let us understand what is inference time compute scaling。诶。

All of us are humans and we know that we tend to give better answers when we think about the answer for more time。

Remember when you are writing an exam？Sometimes you are stuck in a question because it involves layers of thoughts only after you spend enough time on that problem are you able to answer the question correctly？

Some other examples of these type of problems where remote thinking is required is complex math problems or even puzzles like Sudoku I'm sure all of us have played some kind of crossword puzzles which appear in newspapers。

Well you can't answer all the puzzles at once right， there are some horizontal answers。

 there are some vertical answers and many of them are connected with each other。

 so unless you have an idea of all the clues in the horizontal and vertical columns you will not be able to fill each and every single entry in the crossword puzzle。

Another example is of a mathematical problem where we ask the question。

 are the number of prime numbers？😊，finite or in finite。

 this is also not very easy to answer and it is probably going to require a fair amount of thought before you come to the answer。

Let's think of chess。 Chess is an example where whenever a player makes a move。

 the move is never made immediately。 You might have seen matches where grandmas are playing against each other。

 and sometimes they take。1ens or 20 minutes or even more than that to play their next move， why。

 because they are thinking through all possible scenarios before they make their next move。

So generally， we have observed that as humans。When we think more about a problem， we tend to。

Come to the correct answer。Now similarly， we apply the same logic to large language models and we ask the question。

What will happen if large language models think more before they give you an answer？

Just pause here for some time before you proceed with the video and and try to answer this question do you think LLms will give a better answer if you just。

Ask them to spend more time before they give you the answer。

That is a very interesting question and we are going to find out the answer soon in this lecture。

Let us take a very simple example。Roger has five tennis balls and he buys two more cans of tennis balls。

Each can has three tennis balls each each and the question we are asking is how many tennis balls does he have now？

Now let's look at the answer given by a regular LLM over here。So you can see that when。

When a regular LLM tries to answer this question。The answer it gives is answer is 11。

 which is in fact the correct answer and the number of tokens it uses is only 3。Now。

We will force the model to think more before the model gives an answer。

So instead of directly giving the answer which is 11 the reasoning based large language module comes up with a series of steps the first step is Roger started with five balls this step uses four tokens the second step is two cans of three tennis balls each is six tennis balls this step uses 11 tokens and the last step is。

5 plus 6 equal to 11， this step uses five tokens。So when we ask the model to think more。

 it certainly uses more number of tokens before it gives you the answer。

So this is called as test time compute。The amount of computational resources the model uses before it gives you an answer。

Is called a test time compute which is illustrated in this figure。From the above example。

 you can clearly see that reasoning based tele lamps。

Have significantly higher test time compute compared to regular LMs， almost its 3 and 23。

 so it's maybe somewhere between 7 to eight times。But why are we spending so much compute in the testing time？

How does that make sense because in the previous example， even the accuracy stayed the same。

 both the LLMs gave the correct answer anyways。Well， it turns out that。

If you spend more computational resources in the testing time and you ask the model to think more。

The model starts to reason for。Other questions as well。

And the accuracy of the model significantly improves。

And this is what well be looking at in detail in the remainder of this course。

The main thing which we'll look at is。Why does allocating more computational resources in testing？

Help increase the accuracy of the model to answer complex reasoning based questions。

Wch is very similar to what happens in the case of humans right humans also tend to give better answers when they think more about the problem。

 It turns out that exact same thing happens with large language models as well。In this picture。

 you can see that。In the reasoning based LLMs， there is a significant computational resources being used in the inference。

 which I will mark with my pen over here。And in the regular LLms inference happen pretty much instantaneously it's very fast。

And there is a reason why people do this。The reason is that。

We see a scaling which looks like this as the test time compute increases。

The accuracy of the model also typically tends to increase。

There are a lot of nuances when I say this sentence。However。

 I want you to get an idea of why is the word scaling in inference time compute scaling。

 The reason is that。As you increase the number of resources。

 computation resources in the testing time， we see that the accuracy of the large language model typically tends to increase。

We will look at。More nuances about this statement as we follow this lecture。Okay。

 so this sounds quite intuitive， right？Giving more time to thinking leads to a better answer when did we think of all of this？

So the first paper which came out， which。Sure that。If you tell an LLM。

 if you give an LLM a series of prompts where they are not just input output prompts。

 but you have given them a chain of thought。Wwhich links the input to the output。

 then the LLM learns to reason for all other prompts which are not given in the example prompts by the user。

So have a look at what they say in the paper， we explore how generating a chain of thought。

 which is a series of intermediate reasoning steps。

 significantly improves the ability of LLMs to perform complex reasoning。

So what does this mean we are evaluating large language models on the ability to perform complex reasoning tasks？

And it turns out that。