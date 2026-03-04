# Langchain初学者入门2025 p14 P14_#14_链基础 -BV1jgeWzYEey_p14-

Hello guys， welcomee to the first example in chains for La chain。

 So as you can see I've already prepared the code here as well。

 So let's walk through this step by step Allright so the first section is very similar to what we did in the previous sections So all that we've done here is we've initialized our open AI chat model and then we are also creating a prompt templates basically creating prompt templates using a list of tus right so this is another method that piece saw right Also we know that we are doing it this way because we want to include a lot more information inside of the template right so we want to include the system message AI message human message So that is why we are doing the tus way right we also have a system message here saying you are a f expert who knows facts about any animal it could be cats dogs elephants right and the human message saying tell me it count could be two。

3，4 by any number of facts So here is the first task that I want to do first off I want to populate all these plays。

😊。

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_1.png)

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_2.png)

olders and create the final prompt and then pass that prompt to the model as well to the LLM as well right So what did we do earlier in the first few sections we basically did invoke on the prompt template and then again we did an invoke on the model so it was a separate the the tasks were separate separate right it is the same sequence but we had to repeat a few things right but using change though we can do it very easy without seeing invoke invoke every single time。

😊。

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_4.png)

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_5.png)

So we say prompt template which is going to be the first task and then we use the pipe operator that is going to be the chain for us very。

 very simple just the pipe operator is going to connect different tasks together。😊，So。

 once this particular task is done， we pass the result to the next task， which is the model。😊，Now。

 when the response comes back from the LLM， it is then passed into another task which is basically just a function called string output parsel。

 so what is it going to do？😊。

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_7.png)

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_8.png)

It is just going to extract the content property alone from the whole object。

 you know that you know the response of the LLM is going to be its going to have a lot of properties right in that object which is this function is just going to extract the content property。

 That is it。😊。

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_10.png)

So you can see I'm using this method from here。😊，Up here， right。



![](img/0091c8e5d860bb356abcd0bf84aa2e0f_12.png)

You can also do the same。You know what let me just remove this for now and show you the output first next how do we invoke this entire chain we say chain dot invoke and then we pass the object with values that the prompt template needs you know the prompt template requires a lot of these placeholders right we are passing all of that here So whatever we pass in here will be available across the chain So if we have another prompt template here as the fourth task let's say we can pass in a third or the fourth property in this object as well right so whatever we pass in here it will be available across the chain So even if there is like a 15th or the 20th task is going to be a prompt template whatever we pass in here is going to be available there as well right so let us now quickly run this file。

😊。

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_14.png)

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_15.png)

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_16.png)

Right and yeah and perfect we asked for just two facts and we got just that but along with that we also have a lot of other stuff as well right。

 which is why we need to add the string output parser task or the method right and what this is going to do is this is going to select only the content property from the response from the previous task the response from the previous task was the response from the alright So if I change something here also like let's say change the animal to let's say elephant。

😊。

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_18.png)

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_19.png)

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_20.png)

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_21.png)

And make the count to one right and run the file。Great。



![](img/0091c8e5d860bb356abcd0bf84aa2e0f_23.png)

Let's give it some time。Right perfect。 So we get exactly one fact about elephant。

 So I hope that you are starting to see the power of chains and how simple it makes the code look and how readable it looks right compareare it to the other the previous sections where we did it step by step separate separate right So let me actually put this side by side。

😊。

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_25.png)

![](img/0091c8e5d860bb356abcd0bf84aa2e0f_26.png)

So that you can actually see how much less code that we had to write this time。😊。

So with chains right here， we chained a prom template and then sent that to the LLM and then printed that with just a few lines right。

 whereas without chains。😊，On this side， there were a lot of additional steps that we had to do。

 right？ So this is the difference。 chains simplify a lot of things， right。 So in the next section。

 let us see how chains sort of work under the hood So that， you know。

 I'd be able to write my own tasks like custom tasks。 So， for example， right here。

 we used a pre built method that only extracts the content property right。

 But what if I want to write my own method that， you know。

 I can configure it to do pretty much anything that I want。 And I can change that as well。 right。

 So to do that we need to understand how chains work under the hood。

 And that is exactly what we are going to be seeing in the next section。😊。



![](img/0091c8e5d860bb356abcd0bf84aa2e0f_28.png)