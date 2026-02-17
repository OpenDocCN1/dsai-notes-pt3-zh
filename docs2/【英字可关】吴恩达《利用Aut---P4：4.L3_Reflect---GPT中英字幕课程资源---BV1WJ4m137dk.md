# 【英字可关】吴恩达《利用AutoGen的人工智能智能体设计模式｜AI Agentic Design Patterns with AutoGen》 - P4：4.L3_Reflection_and_Blogpost_Writing.zh_en - GPT中英字幕课程资源 - BV1WJ4m137dk

In this lesson， youll learn about the agent reflection framework and leverage its power to create a high quality blog post。

 You will learn how to use the nasty chat conversation pattern to realize a sophisticated reflection process。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_1.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_2.png)

You get to build a system where a set of reviewer agents is nested within a critic agent as the inner monologue to reflect on the blog post written by a writer agent。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_4.png)

Let's make the magic happen。

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_6.png)

In this lesson， let's consider a blog post writing task。

 let's say we want to write a concise but engaging blog post about deep learningning。 AI。

 and I want to make sure the blog post is within 100 words。

So with what we have learned in the first lesson， I guess the first thing that come into your mind is to construct a writer agent to do the task。

And that is true。 So let's do that real quick。So here we could just import autogen and。

Construct model based assistant agent as the writer。Here， of course。

 you could just let the writer agent to do the writing by calling this generate reply function and provide the task as the input。

And then you could check this result from this generate reply function。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_8.png)

Alright， now we have a blog post about deeplening。 AI。 This is good。

 but we want to make it even better。One idea here is to use reflection。

 which is one of the notable and effective agentanttic design patterns。

 one way to realize reflection is to involve another agent to reflect on the work and help improve it。

Following this idea， let's not create a critic agent to reflect on the work of the writer agent。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_10.png)

So similarly， let's use the assistant agent cards from Autogen and create this large long model based agent。

 and here we can prompt this critic to investigate the writing of the writer and provide feedback。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_12.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_13.png)

And with these two agents， we will be able to initiate a chat between these two agents to have a back and forth conversation between the critic and the writer。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_15.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_16.png)

So here you can see that the writer gives a first version of the blog post。

 and then the critic provide some feedback。😊。

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_18.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_19.png)

And then the writer gives another version of the blog post。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_21.png)

From this result， we could see that this agent is reflecting on the work and making suggestions。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_23.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_24.png)

And this is good， but the suggestions are still kind of general。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_26.png)

In many cases， we may want to realize an even more complex reflection workflow as the inner monologue of the C agent。

 for example， we may want to ensure the critic agent to provide criticism regarding certain aspects of the work。

 for example， whether the content will rank well in search engine。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_28.png)

Whether it will attract organic traffic。Whether it has legal problems and ethic problems， etc。

Let's now see how we could use message chat to handle all this。

 Mess chat is effectively a chat registered as the inner monologue of an agent。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_30.png)

So let's first define the chat in this specific blog post writing task。

 let's say we want to create a bunch of reviewers within the C agent to carefully examine different aspects of the writing。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_32.png)

So the first agent we want to include is a SO agent。

 This reviewer is responsible for optimizing the content for search engine to ensure that it ranks well and attracts organic traffic。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_34.png)

And we realize that by setting the system message of this reviewer agent。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_36.png)

And the second reviewer is a legal reviewer， we prompted to be responsible for ensuring the content is legally compliant。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_38.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_39.png)

The other review agent we want to include is the Es reviewer。

 this reviewer is responsible for ensuring the content is ethically sound and free from any potential ethical issues。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_41.png)

And know that in all these three review agents， we are instructing it to Con suggestions and we also want the reviewers to begin the review with the role so that later we can further aggregate the reviews from this reviewers to a final review。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_43.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_44.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_45.png)

Finally， mimic making how a real reviewing process works。

 we may also want a matter reviewer to aggregate all the reviews and give final suggestion。

To do that， we here we create a meta reviewer and the meta reviewer will aggregate all the reviews from the reviewers。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_47.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_48.png)

The next step is to define the chats to be registered here we further use the sequential chat conversation pattern learned in the last lesson to construct a series of chats between the critic and the reviewers。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_50.png)

Here we are effectively having a list of four charts。

 each one of them involve a particular reviewer as a recipient。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_52.png)

Later， we will register this chatlist to the C agent。

 so the C agent will be used as a send by default， and we don't need to further specify the send here。

And also for the first three chart sessions， we also use a large long model to do summary following the desired format。

 so that's why the summary method is set to be reflection with LRR and the summary we provide a summary prompt so that each of these review could return the review in adjacent format。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_54.png)

Which includes a field of reviewer and of a field of review。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_56.png)

And in all of these chat sessions， we set the max turns to be one。

One other thing worth mentioning is that we need to set up the initial message properly so that the nest reviewers can get the content to be reviewed on。

One commonly used way to do that is to get the content from the summary of the outer chat session。

 That's why we define the initial message to be a function reflection message。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_58.png)

So this functions responsibility is to get the summary from the agents in the alter chat session。

 And here we are calling the chat messages for summary as the initial message。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_60.png)

Finally， we could register the review chat to the critic agent as a NA chat。

 and in this Reg NA chat function， we also set the trigger to be the writer by doing so。

 whenever the critic agent receives a message from this writer agent。

 it will automatically route the message to this nest chat session for careful reflection。

And after this registration step， we can now initiate the chat between the critic and the writer。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_62.png)

And note that this step is basically the same as what we did when we do a reflection between the critic and the writer agent。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_64.png)

And this the difference is that this time we are registering this next chat session on top of this critique to do more careful reflection。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_66.png)

And here we kick up the charge session。 As we can see。

 the first step is for the writer to generate a first version of the blog post。 So basically。

 this is the same as we we have seen before。

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_68.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_69.png)

And here， instead of directly giving feedback， the critic agent will route the message to the message chat here。

 for example， you can see that we are starting a new chat between the critic agent and the SEO reviewer and the SEOO reviewer will investigate this content and give suggestions on how to optimize the content forchan by incorporating relevant keywords such as AI courses depending the AI in。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_71.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_72.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_73.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_74.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_75.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_76.png)

And then we move on to the legal reviewer， and the legal reviewer will investigate potential legal risks。

 For example， this legal reviewer is suggesting to review to investigate this title。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_78.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_79.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_80.png)

And now we move on to the ethics reviewer after investigating on the blog post。

 the ethics reviewer investigate potential ethics issues and conclude that no modification or concern is raised regarding ethical implications。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_82.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_83.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_84.png)

And finally， we move on to the matter reviewer。 So basically。

 the matter reviewer will investigate all the reviews we received from the previous reviewers。😊。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_86.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_87.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_88.png)

And because we have instructed the chat sessions to summarize the chat。

 each of these chat in this next J format， so we have these nice reviews and reviewsers。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_90.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_91.png)

And finally， meta reviewer will give the final aggregated suggestion through the critic agent to the writer agent。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_93.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_94.png)

Yeah。And after this writer agent receive the suggestion from this critic agent。

 it will refine the blog post accordingly。

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_96.png)

So this is basically how we leverage message check to realize reflection。

 especially careful reflection with a dedicated workflow。

And now let's further check the result from this chat session here we are calling the summary to check the result。



![](img/5cd2f4163b96b4ce9d4a7307f8b01399_98.png)

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_99.png)

And here you can see that it is returning the final refined version of the blog post。

Feel free to pause here and try your own task。 For example。

 you can as agent write a blog post on a topic that you are interested in。Alright， in this lesson。

 we have learned how to realize the reflection agent design pattern with NA chat In the next lesson we will learn how to further leverage to using in NA chat to further level up the e design patterns。

 Stay tuned。

![](img/5cd2f4163b96b4ce9d4a7307f8b01399_101.png)