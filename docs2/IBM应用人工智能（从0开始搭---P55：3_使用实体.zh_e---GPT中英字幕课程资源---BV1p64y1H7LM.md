# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P55：3_使用实体.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_0.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_1.png)

Welcome to the third module of how to build chatbots In the previous module we mastered Ins This module is entirely dedicated to entities。

 the second key component of our dialogue skill， as you know by now， In capture the user goal。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_3.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_4.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_5.png)

Entities allow us to capture specific values within the user utterance。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_7.png)

You might recall this example from the previous module。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_9.png)

You'll notice how the chatbot is correctly detecting the intent。

 but completely ignoring the specifics of the question， In other words。

 when is your Toronto store open and when is your Vancouver store open are the same as far as our chatbot is concerned。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_11.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_12.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_13.png)

That's because we haven't defined an entity to capture that specific bit of information。

 namely the location of the store， so what we could do is create a location entity。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_15.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_16.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_17.png)

Notice how we use an at symbol rather than a pound symbol for entities。

 we can then define multiple values for our entity， such as Toronto， Montreal， Vancouver， etc。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_19.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_20.png)

One value for each store location that we have。 you'll notice that we can also define synonyms for a given entity value。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_22.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_23.png)

These can be dictionary synonyms， but are often synonyms in the sense that the user might refer to the entity value in that way。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_25.png)

Imagine， for example， our Toronto store is located on Wden Avenue。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_27.png)

People might ask about hours of operation of our Toronto store。

 or they might phrase it as what are the hours of operation of your Warden Avenue store。

 either should lead our chatbot to detect the same entity value synonyms are optional but are a useful feature and worth defining when applicable with our location entity defined we can now detect the intent and the specific location。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_29.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_30.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_31.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_32.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_33.png)

With these two pieces of information， we can provide an appropriate and specific answer to the user note that although entities values can have spaces in them。

 we need a special syntax to represent them if the entity value has a space in it。

 we simply wrap it in parentheses to refer to it， when later on we'll define the rules of our dialogue。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_35.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_36.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_37.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_38.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_39.png)

Much like Ins， we can also import entities from CSV， in fact， in the labs for this module。

 you will import them in this way and learn how to export them to CSV as well。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_41.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_42.png)

Other than entering them manually in Watson Assant and importing them from CSV。

 there is also a third way to add entities to your chatbot。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_44.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_45.png)

In fact， there are some predefined system entities that you can enable if needed by your chatbot。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_47.png)

As you can see， there are quite a few options。

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_49.png)

Ciss currencyency allows us to detect mentions of currencies within the user input。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_51.png)

Ss date mentions of dates For example， the user might reply to a question with next Monday。

 and S date will allow us to capture that piece of information as an actual specific date。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_53.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_54.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_55.png)

Ciss personson allows us to detect common names， an easy way to collect people's names to make your chatbot more personal。

 as you'll see later on in the course。

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_57.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_58.png)

System entities are quite handy， and they are constantly being improved upon。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_60.png)

Make sure you check the system entities available in your dialogue skill before you jump right to implementing your own entities。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_62.png)

All right， now it's your turn， by now you should know the drill。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_64.png)

In the rest of this module you'll find a series of guided exercises that will teach you how to work with entities。

 you'll also find some graded quizzes。

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_66.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_67.png)

In the next module， we'll see how to put the intents and entities we defined to good use to provide accurate and specific responses to the user。



![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_69.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_70.png)

![](img/61c4cf3aca6cd44cb9b73c2ab869f8a1_71.png)