# 吴恩达《通过Guardrails实现安全可靠的人工智能｜Safe and Reliable AI via Guardrails》中英字幕deepseek翻译 - P7：7.Lesson 6 - Keeping a chatbot on topic.zh_en - GPT中英字幕课程资源 - BV1kEUtY5ELM

![](img/233976ccb526499a3b61ece201c0f889_0.png)

So you just build a fairly complex guardrail to handle hallucinations in a rag chatbot。

 let's now move on to see how you can handle other failure modes。

You'll start by building a gar that helps you make sure that your chatbot only discusses topics relevant to your use case or your business。

This helps make sure that users can't abuse your chatbot by using it for other tasks。

Let's head over to the notebook。 So in this lesson。

 we're actually going to see how we can create validators to make sure that our Lm rank applications stay on the topic that they're intended for。

 we saw an example of this happening in the intro lesson that we did。

 So I'm actually going to just remind you all of how we send that up and set up all of our warnings and imports。

 So you've seen this before。 I am using the exact same。😊。



![](img/233976ccb526499a3b61ece201c0f889_2.png)

Unguarded client， vector database and system message。And using all those。

 I am setting up a simple Ra application and I am going to get this Ra application to go off topic。

So let me get my pizzeria chatbot to tell me about the differences between a Ford F150 and a 4granger All right。

 so it actually gave me this amazing detailed list about versatility and convenience etc ce right and it's a pizzeria chatbot so it really shouldn't be doing that so now let's go into how we can create a validator to avoid this。

And as we do that， the first thing that we're actually going to do as part of this validator is to understand the underlying model that we're using。

 which is going to be a zeroshot topic classification model。

 So the specific name of the model that we're using is Bart。

 which was created by Me Las and how it really works under the hood is actually pretty similar to the natural language inference or NI model that we've seen in our previous lesson on hallucination。

Except that instead of passing in a hypothesis and a premise directly。

 we end up using this specific formulation of NLI， where our premise is our input text and the hypothesis is that the text is about specific topics and if entailed or contradictory we end up getting information on how likely it is that those topics belong to the specific text。

So let's see this topic classification model in action and use it to create our zero shot classifier so same as before we are actually going to use hugging face and hugging face pipelines to create zero shot classification。

Using the Facebook bart large emi model and the hypothesis template。

 which we've seen in the slide as well is this sentence above contains discussions of the following topics where all of the topics we care about will go in here。

 Let's see how well this classifier performs on a toy example where the sentence is chickfillets closed on Sundays and the potential topics we send to this model are food。

 business and politics。 perfectf。So we can see that four chickfillays closed on Sundays。

Food business and politics each come with these likelihood scores， so food is like 0。672 business。

 it is about business so 0。179 and then politics 0。027。

Shes pretty close to how we'd expect you know the sentence to perform on specific topics and this classifier。

 this zero shot topic classifier forms the core of our topic guardrails， so before we get too far in。

 let's actually take a look and compare how well this zeroshot classifier does versus an LLM。

 you can use an LLM to do classification， and depending on the model and infant service you use。

 this can be a good option， especially at your POC phase， let's actually look at this in action。

So here we're using GPT 40 minii， the latest model as of the time of filming to classify。

 and we can't get the details scores， but let's see how it goes。

So you can see here that the LLM returned food nine times out of 10。

 but this one time it also returned business。So that's one limitation Lms are stochastic。

 so you may get different answers each time you run them and how good the classifications will be depends on the model you use and with bigger models generally leading to better results。

The other issue here is that your application will be constrained by rate limits up time。

 all of that of the hosted third party server here it took about 30 seconds to run all of these requests and that will vary depending on traffic。

 terms of service changes， etc。Now let's compare this to our zero shot classifier。

 running the exact same experiment。In the learning environment， you only have access to basic CPUUs。

 so computer is very limited and this will actually take about five minutes to complete。

 but if you run this exact same code in your own computer with advanced CPUs or GPUs。

 the model will be much faster and this also reflects the actual production settings that you'll deploy your guardrails in。



![](img/233976ccb526499a3b61ece201c0f889_4.png)

Here I'm showing the results of running the model on a MacBook Pro with an M1 chip。

 and as you can see， the 10 iterations complete in just a few seconds。



![](img/233976ccb526499a3b61ece201c0f889_6.png)

And beyond just speed， the results are exactly the same each time， so performance is consistent。

 which is important for reliability。And you can run this small model on a server or private environment。

 allowing you not to send user messages to a third party and making sure that your data is contained with a neural environment。

Allright， now that we understand how our topic classifier works。

 let's create a topic guardrail that will make sure that our chatbot stays on topic the first step of doing that is actually to make sure that we implement a function that detects topics and we're going to use the same classifier that we just use so all we're doing in this function is getting some text getting a list of topics and then getting a threshold score and then this function returns a list of strings which is the detected topics where each topic must have a score that is greater than the threshold now that we have our topic classifier function that's actually use that function to implement our validator where we're calling this validator the constrained topic validator。

And we basically taken a list of band topics and a threshold value and then in our validate function。

 recalling our detect topics function that we implemented earlier and if any band topics are detected。

 we raise a fail result otherwise we raise a past result pretty straightforward and similar to what we've done in our previous lessons and finally using the validator that we just created。

 let's actually build a guard that uses this validator and test it out on some examples。

 So here's our initialized guard and now let's try running this guard on a statement that is clearly very political。

Again， this we take a few seconds to run。 All right。

 And as we see our guard failed because the politics topic was detected， which is what we expected。

 and automobiles weret detected。 All right， now that we see how we can create a topic guardrail。

 let's now try using a state of the art topic classifier from within a guardrail server and see if we can prevent the failure that we saw earlier in our chatbot。

 So in order to use the state of the art topic classifier。

 you'll actually need to download and install this specific guardrail from guardrails hub in your local environment。

 But for the learning environment， we've already done it for you。 same as before。

 we are going to use the server as we'd seen it in our previous lessons。

 and we're going to use the topic guard that we'd created in the server。

 which is running in this URL。 and then let's create a guarded chatbot that uses your guarded client。

 which is basically your open AI client。 but it is sandwich between the guard that is running a topic classifier on the output。

 Now， using this。😊，Ged chatbot let's see how well we do in getting our pizzeria chatbot to talk about Ford vehicles。

 so this is the exact same prompt as what we used before Alright so as expected we know that our output talks about you know Ford F150 trucks which is a banned topic for us and so we end up getting this output where we're basically raising a validation error instead of returning the raw output back to the user。

And once again， you don't actually have to use this exact same validation error message。

 you can just catch this exception as we've seen in previous lessons and do much more graceful error handling to let your users know that they can't talk about these topics with your chatbot Let's now take a look at handling the next type of failure that we saw in our intro lesson which is leaking and improper handling of personal identifying information。

 so join me in the next lesson as we make sure that we're handling PII correctly。



![](img/233976ccb526499a3b61ece201c0f889_8.png)