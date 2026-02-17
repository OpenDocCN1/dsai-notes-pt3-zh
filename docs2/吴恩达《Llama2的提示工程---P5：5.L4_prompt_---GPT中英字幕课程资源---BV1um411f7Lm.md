# 吴恩达《Llama2的提示工程｜Prompt Engineering with Llama 2》中英字幕（英字可关闭） - P5：5.L4_prompt_engineering_techniques.zh_en - GPT中英字幕课程资源 - BV1um411f7Lm

As you may have noticed by now， the words you choose when you prompt the model affect how it responds。

Prompt engineering is the science and the art of communicating with a large language model so that it responds or behaves in a way that's useful for you。

You will use some tips and tricks for prompting， such as giving the model examples of how you would like it to behave。

You can also add additional information to help it answer fact based questions。

One thing that I think is really cool is prompting the model to perform well on complex reasoning tasks。

You will apply these best practices when you ask Lama to classify， explain， and summarize texts。

 messages， and emails。I'm excited， I hope you are too， let's dive in。



![](img/d440f2f9cd8b3099ca8829fba9c46fcc_1.png)

Lower models can make use of information you include in your prompt when generating text。

 you can guide the model to improve its response for your task by including different kinds of information or context in your prompt。

 for example， you can provide examples of the task that you are trying to carry out to help the model understand what you are asking it to do This is known as in context learning Another type of prompted engineering technique is where you can specify how you want the model to format its response you can ask the model to assume a role or persona so that it will respond to you with a certain voice or personality This is a really fun thing to explore with LLNs。

Lastly， you can include additional information in the prompt like private data to make its response specific to your task。

 this is also how you can overcome the fact that model knowledge of the world cuts off at the moment of its training like in earlier lessons we imported Lama function from U package will do that here as well。

Along with Lama， we will also import。Lma chat， which we saw。Earlier。

So here is an example of a standard prompt。And I'm going to ask the model to tell me what the sentiment is。

 And let's type the response and see what。Our model returns back。

So our model responded by saying the sentiment of the message is positive。

 and it also explains why it is positive。 A pretty good explanation on that。 In this case。

 the model's response looks pretty decent。 You don't always have to explicitly state the instructions。

 One of the most fascinating abilities of LLms is to infer the task you are asking them to do from the structure of the prompt。

 For example， here is a way to ask the LLM to carry out the same sentiment analysis task you just saw。

 but without including the full English language request。

 So you include the message to classify and the sentiment line implies that the model should fill in the sentiment。

 When you pass this to a model， it may understand what is going on and return the answer you expect。

 here it says sentiment is positive。 which is what you want。

 a prompt of this form is called zeroshot prompt because it doesn't include a full example。

 Some LLMs won't be able to do this。 For example， a model may respond with its base behavior and just continue generating text。

Like the one you are seeing here， so you can build upon zero sharp prompting by including one or more examples of what you're asking the model to do。

This can help the model infer the task。 So here you are going to add a complete example of sentiment classification before the message you want the model to classify the prompt starts with an example message that you are 20 minutes late for my piano recital。

 Now， this is typically with the message I get for my daughters when I'm usually late for the piano recital classes。

 This is followed by a completed sentiment In this case， the message is obviously negative。

 Then you finish the prompt with a new message that you want the model to classify with the addition of the example。

 the model now completes the task successfully giving a response that mimics the structure of the example。

 prompting with a single example is called one shot prompting。

 you can include more examples if you need to。 two or more examples are called few short or n shot prompting where n is the number of examples。

 Now， let's go back to the notebook and see this in action。

 Here is how you would structure your prompt for zero shot prompting。 Let's copy the previous cell。

And modify。The prompt。So' going to include message saying hi A it。

 thanks for the talk of about Descars。And then I'm going to add a sentiment with a question mark。

So here's the response we are getting from our zero sharp prompting。

 The response is saying appreciation and gratitude。

 but it's not really telling us whether the sentiment is positive or negative。

 Now what if we want the sentiment to be either positive negative or certain kind of format。

 by giving examples to our LLM。 This may help the model understand the expected output format。

 So let's give additional examples。 Here's my first message。

 hi dad youre 20 minutes late to piano recital， which the sentiment is negative I'll add one more message to it。

 which is can't wait to auto a pizza for tonight， the sentiment is positive because my kids love the pizza on a Friday evening and I'll add one more。

Message with a question mark to the sentiment， and I want the model to tell me what the sentiment is。

So let's。Create the response， and let's print the response。And let's see what our model does。Great。

 so our model is able to give us the right sentiment。

 It looks like the Lm is still repeating the n examples and then choosing the sentiment for the last text。

 Now what if we want to get the entire response in just one single word。

 I just need the sentiment for my last prompt， so let's see if we can do that Let me copy this prompt。

And let me make a small change on addition here， which tells。

The model to give the response in a single word。As you can see here。Our model is not able to。

Give us the right sentiment。 In fact， what it spit out is not even useful for us。

 We are using the 7 billion parameter model。 Maybe we can try a larger model and see whether we are getting a better response。

 So let's take the this same。Code and put it in our cell， but now we will select。



![](img/d440f2f9cd8b3099ca8829fba9c46fcc_3.png)

Our 110 billion parameter model， and now let's see whether we get the right response。Alright。

 so this looks much better。 We got a one word response， which is positive。

 The large 70 billion parameter model appears to follow the instruction and give us a response in one word。

 but we want the prompt to work with our smaller model as well。 So let's try and。Modify a prompt。

To make it work with our smaller models。So instead of giving a one word response， what if we ask the？

马头。To respond with。Either。Positive， negative。A neutral。Allright。

 so we are getting the right sentiment。 It is repeating the sentiment and prompt what we had entered。

 but it is giving us the last sentiment where we had question mark it is coming in as positive in a later lesson you will get to try out a small medium and large sized Lama2 models to learn when it makes sense to go with a larger model。

 Okay， so let's talk about role prompting roles give context to the LLM on what type of answers are desired and Lama2 often gives more consistent responses when given a role So let's try this out。

 Let me add a prompt。Which says， how can I answer this question from my friend。

 what is the meaning of life？And let's see what it responds back。

iceIt has given us a pretty detailed response giving different perspectives of life Now what if we give the LLM a particular wall with areas of expertise and also a tone of voice let's see whether the LLM is able to respect that and give us a more refined answer so I'm going to type in a prompt here where I'm going to say your role is a life coach who gives advice to people about living good life and you attempt to provide unbiased advice and you respond in the tone of an English pilotrate which is pretty interesting so we need to wrap this up into our prompt so let's do that。



![](img/d440f2f9cd8b3099ca8829fba9c46fcc_5.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_6.png)

And。Well， put it in ourcur braces。They're all。Next， which we created。And then we will。

Append this with our question， the same prompt which we。Didad before。And。Now let's see the response。

Alright， so you can see the response is quite different than what we saw before and the tone and the style is because we asked it to be an English pilot so as you can see our LLM our Lama model is able to respect the role and is able to give us a response back in that tone now let's go and see our next use case。

Which is summarization summarization is a common and helpful use for LLMs。

 because these days we just have so many emails and documents to read。 For example。

 my friend Andrew sends me a personal email every Wednesday where he tells me how he thinks about some topic usually related to AI if I'm in a hurry I might ask Lama model to summarize Andrews letter to me so let's write this in a code。

 So I'm going to copy my email which Andrew sends it to me。



![](img/d440f2f9cd8b3099ca8829fba9c46fcc_8.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_9.png)

And I'm going to create the prompt。

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_11.png)

So here I'm telling the model。

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_13.png)

To summarize this email。And extract some key points。

 and I'm also asking the model to tell me what did the author say about Lama models specifically？

And I'm appending the text here， the email， which I just wrote into my prompt。Now， let's see。

What the response is， let's print it。

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_15.png)

All right。So it's able to give us a full summary of the email It's talking about specifically about Lama models and it's talking about prompting allowing developers to build a prototype in minutes and hours without a training set and you can see right here it says the author also mentions that a member of deep learning AI team has been trying to fine tune a model to sound like them which they find amusing So our response included and respected everything we basically asked it to do let's move on to other things which our models can do one thing to note that our models are not like search engines these models are typically trained on data that ends on a particular date and beyond that date they don't have any information about what is happening Lama was launched on July 18 of 2023 So let's take an example where an event happened after July 18 so I'm going to。



![](img/d440f2f9cd8b3099ca8829fba9c46fcc_17.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_18.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_19.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_20.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_21.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_22.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_23.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_24.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_25.png)

A prompt here which says who won the 2023 women's World Cup。

 and I think the women's World Cup happened in late July。

 so let's run this example and see what we get。

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_27.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_28.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_29.png)

All right， so our model assumes that women's World Cup has not yet taken place so how do we get this kind of information into our prompts now there is a Wikipedia article which talks about 2023 FiA women's World Cup so we can copy that context and add it to our prompt so let me do that。



![](img/d440f2f9cd8b3099ca8829fba9c46fcc_31.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_32.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_33.png)

So here's where it talks about Spain， had won the World Cup and and talks about different teams and so forth and let's。



![](img/d440f2f9cd8b3099ca8829fba9c46fcc_35.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_36.png)

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_37.png)

Add the prompt。So we were basically ask that。

![](img/d440f2f9cd8b3099ca8829fba9c46fcc_39.png)

The model， given the following context。Who won the 2023。Rmans。Workup。And we will。

Add the context here in cur braces like we did before。And now print the response。All right。

Now as you can see。It is able to give us the right answer， Spain won the 2023 World Cup。

 so what is happening here？We are actually appending the context。

 getting it from Wikipedia and sending it to our model and model is able to take that context into account and give us a response so even though the data the model was traineded on is older than July 2023 it is still able to extract additional context from the prompt and give us a better response。

 so it would be great if you can try few things here as well， I'll give you a sample。

codeode here and you can paste in the context here。

 you can write your own query and see what the Lama model returns back。

 Another cool thing we can do with our models is ask them to solve complex reasoning problems but to do that well we have to provide good instructions to our models just like people LLs can some time perform complex tasks better when they are broken down into smaller steps writing instructions in your problem that ask the model to reason through a problem in multiple steps is known as chain of thought prompting to get Lama to respond in this way you can try phrases like think step by step or explain your reasoning This guides the model to break the problem down into smaller chunks and to tackle them one at a time chain of thought prompting is a powerful technique that can really improve the performance of LLNs at reasoning problems and problems that involve carrying out multiple math operators。

Patients。So let's head back to the notebook so you can see how this works for yourself。

Here we are going to give a prompt， which will be a complex word problem。So， let's。

See the word problem， so here's our prompt。Which says 15 of us want to go to a restaurant。

 Two of them have cars。 Each car can seat 5 people。 Two of us have motorcycles。

 Each motorcycle can fit two people。 Can we all get to the restaurant by car or motorcycle。

 That's the question we are asking our model。 Now， let's see what it responds back。So it says yes。

 all 15 people can get to the restaurant by car and here's how so it's showing us different steps but as you can see each car seats five people and we have two cars or 10 people and then two motorcycles each can fit two people So at the most you can have 14 people go to the restaurant So our model is able to calculate correctly that it's total 14 people but then it's saying the remaining one person can either walk or find another mode of transport this is not something which we ask the model to do So what if we modify our prompt to think step by step。

So let's add that。Let's see what it responds back。Okay。

 so now it has done a further detailed breakdown， but unfortunately it says you have three more people who want to go to the restaurant。

 so it gets the math wrong when we ask it to think step by step。

 so let's rephrase the request to be more specific。And we can change the our previous prompt itself。

And let's add some more。Instructions。So we basically add explain each intermediatem step。

And we also tell only when you are done。With all your steps。Pide the answer。

Based on your intermediate。Steps，So we are applying more instructions to the model and let's see what it does。

So it again， gives a pretty long answer does。Logical reasoning， and。

It seems like it got the right answer because it says 14 people can fit in the car and the motorcycle and it does say that it is not possible to accommodate all 15 people by car or motorcycle and the answer is no it is not possible to take all people So it got it gets the math correct。

 It understands that the cars and motorcycle can fit 14 people。

 It understands that 14 is less than 15。 It remembers that the question is whether all 15 can go by car or motorcycle and it correctly states that not all 15 can go by car or motorcycle So that was much better。

 So giving more instructions in your prompt can lead to better desirable results。

 Now what if we ask it to answer first and explain later So let's modify or prompt a little bit more。

 So I'm going to copy or prompt。Into a new cell。And I'm going to change a few things here。

Going to keep。Thinkhings step by step， but I'm going to change a few things here。

 what I'm going to say。Provide the answer。As a single。Yes， no。Answer。F。

Then explain each intermediatemedia。Steps。So we are asking the model to give me an answer before calculating all the intermediate steps。

And let's see whether it gives us the right answer。Giving us the answer first， yes。

 all 15 people can go to the restaurant， which is not correct。

 and then it's giving us step by step instructions and then it's giving us the conclusion。

So it first answers yes and then think through step by step。

 it gets lot of math correct actually in the end it still concludes with its initial incorrect response。

 so the key takeaway here is that the LLM predicts its response one token at a time if we ask the model to give the answer first。

 then it will give that answer but any of the work and the step by step thinking that it does。

After giving the answer can no longer influence the answer that it already gave。

 So as the model to think step by step， explain the interative steps and only then give its answer based on its inter steps。

 So as you saw in all of the examples in this lesson。 Proing is part science and part art。

 it's helpful to think of prompting as an iterative process where you end up with the best prompt for your particular task through trial and error。

 It may take several tries to get the model to respond in the way you want。

 This diagram shows one way you can think through this process。 based on what you are trying to do。

 you start by coming up with an idea of prompt that you think might work。

 then you just try it pass your prompttu Lamma， then see how the model response。 Next。

 take a close look at the response from the model and assess if it has completed the task in the way you wanted it to if it has fantastic you can。

Use the output or use the prompt response pair in a multiton chat prompt If it didn't respond in the way you were expecting try changing the prompt。

 try making your instruction a little bit clearer or being more specific about the output format you would like from the model try including an example to help the model understand what you want to do once you have come up with a revised prompt pass it to the model again and continue working through the steps。

 This is the part that makes prompt engineering and art there is no single prompt that works for all situations or all models so explore try revise and eventually you will find something that works so that's an overview of prompt engineering one thing we haven't discussed in detail yet is the importance of the model size in determining how well prompt engineering will work in the next lesson you'll see a more detailed comparison of Lama2 and code Lama models of different sizes to have a better understanding of when to use which model。



![](img/d440f2f9cd8b3099ca8829fba9c46fcc_41.png)