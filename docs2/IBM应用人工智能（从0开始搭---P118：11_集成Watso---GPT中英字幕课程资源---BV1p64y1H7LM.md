# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P118：11_集成Watson Assistant Discovery.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

。Watson Discovery is great， but you might be wondering how it relates to chatbots。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_1.png)

As you probably know， Watson assistant allow us to interpret and classify the user input。

 and then according to the rules we defined in the dialogue。

 reply with some predefined responses this approach works really well for common questions The short head in this graph What's much more challenging is handling the long tail of questions the users might have wouldnn't it be great if our chatbot was able to provide a response to these very specific questions as well。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_3.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_4.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_5.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_6.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_7.png)

Most businesses have existing knowledge bases， which are often available to customers and agents who provide them with support。

 these web pages and or PDF documents tend to have a wealth of information。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_9.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_10.png)

It wouldn't be feasible to manually extract all the possible answers provided within these documents and prepare them as thousands of possible responses in the dialogue。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_12.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_13.png)

This is where Watson's discoveryovery magicic enters the picture by connecting Watson Assistant and Watson Discovery。

 we can let Watson Assant handle queries we predefined while leveraging Watson discoveryovery querying abilities for long tail questions。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_15.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_16.png)

When unable to respond to the user， Watson assistantsant will pass along the user query to Watson Discovery。

 Discovery works well with queries expressed through natural language and will allow us to retrieve the relevant answer in the knowledge based collection we'll have defined。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_18.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_19.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_20.png)

Finally， Watson assistantant will relay the retrieved knowledgege base answer in its response to the user。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_22.png)

In other words， we'll be able to create smarter and significantly more useful chatbots by integrating Watson Assant and Watson Discovery Watson Assistant will still handle the whole interaction with the user。

 but it will outsource long tail questions to discovery。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_24.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_25.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_26.png)

The good news is that Watson Assistant and Watson Discovery are easily integrated without the need for any programming。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_28.png)

Much like you add a dialogue skill to an assistant。

 you can add a search skill that connects your chatbot to discovery so that your collection there can be easily queried。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_30.png)

The bad news is that this neat integration is only available to plus or premium plan users if you are using the free light plan like most do during training。

 you won't have the ability to add a search skill fear not， however。

 as we can still integrate Watson assistantant and Watson Discovery through APIs In fact。

 every Watson service provides an API that can be used to programmatically access the service。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_32.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_33.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_34.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_35.png)

So we can query Watson Discovery collections directly from a script or an application。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_37.png)

This， coupled with the fact that Watson Assistance dialo nodes have the ability to make programmatic calls to APIs。

 will allow the two to communicate。

![](img/c7ad889a0733d3b36efc86e0f5eea79d_39.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_40.png)

The easiest way to call a remote API from a dialogs node is actually to use a cloud function。

 a cloud function is exactly what it sounds like。

![](img/c7ad889a0733d3b36efc86e0f5eea79d_42.png)

It's a function that will execute some code and can be invoked remotely， in our case。

 the cloud function will make an API request to the Watson Discovery service and return the response。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_44.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_45.png)

Wattson assistant will then make use of the value returned by the function to issue the final response to the user What I like about this approach is that it's very flexible。

 you might want to connect your dialogue to a different service at some point。

 knowing how to integrate different services will come in handy。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_47.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_48.png)

![](img/c7ad889a0733d3b36efc86e0f5eea79d_49.png)

As a bonus， you'll also become more familiar with the serverless computing model offered by IBM Cloud functions。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_51.png)

In moduleule4， you'll also learn how to integrate Watson's speech to text and text to speech using their APIs。



![](img/c7ad889a0733d3b36efc86e0f5eea79d_53.png)