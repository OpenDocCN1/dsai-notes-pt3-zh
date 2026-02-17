# 杜克大学《大型语言模型实践（生成式AI简介、Azure的LLMs（1、2课，共6课）｜Large Language Model Operations》 - P91：14_01_05_LLM运维简介.zh_en - GPT中英字幕课程资源 - BV1Ef421m7zD

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_0.png)

So let's talk a little bit about LLM ops or operations for large language models let's start here with the data which you may or may not have at all you may want to do for example summarization of text and that case you might not necessarily be relying on data。

 but if you have something specialized let's say for example you have data that talks about a vast amount of wine and descriptions about wine and you want to provide some service that will do something about wine well data is going to be required here now for that for that to work and be interesting then you will then need to go right here to select your actual models so you may。



![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_2.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_3.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_4.png)

Be probablybably going to be reusing some existing models and you might be choosing something specific that fits your needs for the specific task ahead there are many different models out there with many different types of specialized tuning I mentioned one before but it could be for example a good example is the codex a large language model which is specifically trying to address code and developer type of tasks that deals with coding tasks and generating code which some other language model that doesn't concentrating coding might not be a good a good example of that so then you will have some sort of testing right here and that testing will do some evaluation of what you're trying to do while you're trying to accomplish。



![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_6.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_7.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_8.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_9.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_10.png)

Now depending on number one here with the data that you have。

 that might represent some sort of interaction， but you won't see that unless you are going to be using some sort of search。

 so if you require some data and you want to have something that is continuously updated。

 so say for example， data is getting every day things that are getting new or coming in there。

 youll have to have some way to make these data communicate with search and start storing your data in the search and have some process to do that。



![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_12.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_13.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_14.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_15.png)

So all of these things that are happening， probably not the models one。

 but the data and the search for retrieval augmented guidance， which well go into details later。

 that requires some sort of automation and steps to make that seamless。



![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_17.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_18.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_19.png)

Now number five right here was going to be your prompt and your prompt engineering and how you are prompting and crafting these prompts to make that interaction with a large language model seamless。

 then we're going to go here to number six which is your deployment and deployment。

 well you have to do packaging， you have to ensure that these things are working correctly that you're scaling。

 you'll probably want to go to the cloud somewhere and deploy those things there。



![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_21.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_22.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_23.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_24.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_25.png)

That will also have to have some automation and some checks and steps in place to prevent things from not working right after all that hard work。

 you've defined your models， you've done a little bit of testing you've been working with a lot of data you've been working on on your prompt and your prompt engineering and you have your data here in search and all of these things are working well you want to now make that model useful and finally of course having the ability to monitor the performance and how this model is behaving once it has been deployed and its serving actual clients and people are interacting with these model that you've selected that you've perhaps fine tune or done a little bit of search。

 implemented a search engine so that you can provide meaningful meaningful responses all of these components and all of these steps and all of these pieces need to be automated。



![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_27.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_28.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_29.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_30.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_31.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_32.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_33.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_34.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_35.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_36.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_37.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_38.png)

need to be continuously monitored and checked and continuously improved This is a never ending process where things will have to be continuously taken care of even if you have everything fully automated it is quite possible that your data might get into trouble and might not be as good as it was before and you will have to deploy some checks and deploy some automation so that it will take care of those problems so that they don't come back again all of these things。

 all of these deployment processes， packaging validation。

 inferluencing and monitoring metrics data drift and trying to get all these repeatable patterns and pipelines and steps is what large language model operations or LLM ops is all about。



![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_40.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_41.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_42.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_43.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_44.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_45.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_46.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_47.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_48.png)

![](img/2c093a9aad4e3238b6d0fe165e4fb9cc_49.png)