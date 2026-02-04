# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P57：5_构建用户友好的聊天机器人.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/f9ced88d4256bc0bf6b87eda442164f7_0.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_1.png)

Welcome to the second video of this fourth module。

![](img/f9ced88d4256bc0bf6b87eda442164f7_3.png)

The labs within this course will teach you everything you need to know about how to work with chatbots。

 however， before we get into the nitty gritty details。

 I wanted to quickly mention a couple of guiding principles for building user friendly chatbots。



![](img/f9ced88d4256bc0bf6b87eda442164f7_5.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_6.png)

Whenever you design the chatbot， you should consider the tone and personality of your chatbot。



![](img/f9ced88d4256bc0bf6b87eda442164f7_8.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_9.png)

Consider the audience and purpose of the chatbot and then adjust the chat bot accordingly。



![](img/f9ced88d4256bc0bf6b87eda442164f7_11.png)

If you are targeting a younger demographic， vanilla jokes and emojis might be appropriate。



![](img/f9ced88d4256bc0bf6b87eda442164f7_13.png)

If your chatbot is for a funeral home， perhaps avoid jokes and using slang。

 much like you would if you were to train a human customer service agent。



![](img/f9ced88d4256bc0bf6b87eda442164f7_15.png)

You want to ensure the chatbot issues responses that are appropriate for the circumstances。

 whether a formal or informal tone is in order。

![](img/f9ced88d4256bc0bf6b87eda442164f7_17.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_18.png)

Consider the default chatbot prompt。 Hello， how can I help you。

 It's a default value when we first create the dialogue， so it has to be generic by design。

 but it's not very good。 and it's the first thing I like to change in a chatbot。



![](img/f9ced88d4256bc0bf6b87eda442164f7_20.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_21.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_22.png)

Let's see how we can improve it。

![](img/f9ced88d4256bc0bf6b87eda442164f7_24.png)

In our case， we might change it to say something like，Hello。

 my name is Florence and I'm a chatbot here to assist you with your questions about store hours。

 locations， and flower recommendations， This is a much more user friendlyly prompt for the user。



![](img/f9ced88d4256bc0bf6b87eda442164f7_26.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_27.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_28.png)

Let's see why。We start by giving the chatbot a bit of personality by giving it a name。

 it's no longer a random software in the ether， it's Florence。

 Next we come clean to the fact that we are a chatbot。



![](img/f9ced88d4256bc0bf6b87eda442164f7_30.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_31.png)

This is important because it sets the right expectation with the user。



![](img/f9ced88d4256bc0bf6b87eda442164f7_33.png)

We want our chatbot to be humanlike。

![](img/f9ced88d4256bc0bf6b87eda442164f7_35.png)

But we don't want to falsely pretend that it's actually a human。

 as this will lead to disappointment for the user。

![](img/f9ced88d4256bc0bf6b87eda442164f7_37.png)

Finally， we define the scope of the chat bot by guiding the user on what they might be able to ask。



![](img/f9ced88d4256bc0bf6b87eda442164f7_39.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_40.png)

The worst thing a chatbot can say is a wide open， what can I do for you？



![](img/f9ced88d4256bc0bf6b87eda442164f7_42.png)

It's okay as a reply later on in the conversation after you already declared the chatbot scope。



![](img/f9ced88d4256bc0bf6b87eda442164f7_44.png)

But a hello， what can I do for you off the bat is an invitation to ask the chatbot anything。

 and that will inevitably lead to disappointments。

![](img/f9ced88d4256bc0bf6b87eda442164f7_46.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_47.png)

No matter how thorough of a job we do with our chat bot。

 we are not going to make it capable of answering every question it will receive。



![](img/f9ced88d4256bc0bf6b87eda442164f7_49.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_50.png)

Heck， we wouldn't even be able to make such a claim if we were training a human customer care agent either。



![](img/f9ced88d4256bc0bf6b87eda442164f7_52.png)

But doubly so for a chatbot。On top of the considerations we discussed so far。

 I'd like to leave you with three important rules of chatbot design。



![](img/f9ced88d4256bc0bf6b87eda442164f7_54.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_55.png)

The first one is that you should avoid including yes and no in your answer。



![](img/f9ced88d4256bc0bf6b87eda442164f7_57.png)

If you include them， it's very easy to give the wrong answer to the user or come across as less humanlike than would want。



![](img/f9ced88d4256bc0bf6b87eda442164f7_59.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_60.png)

For example， consider this question。We might have a free delivery intent。

 and we might be tempted to answer with yes， it is when the question is phrased like this。

 the reply works。

![](img/f9ced88d4256bc0bf6b87eda442164f7_62.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_63.png)

However， if the user phrases the question differently。



![](img/f9ced88d4256bc0bf6b87eda442164f7_65.png)

The same intent will be detected。

![](img/f9ced88d4256bc0bf6b87eda442164f7_67.png)

And the response will be issued。Only this time， yes， it is， is a pretty bad answer to the question。

 do I have to pay for deliveries？

![](img/f9ced88d4256bc0bf6b87eda442164f7_69.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_70.png)

A much better answer is one that avoids a straight yes or no。By responding with deliveries are free。

 for example， we correctly respond to a question expressing a request for delivery pricing information。

 no matter how it's phrased。

![](img/f9ced88d4256bc0bf6b87eda442164f7_72.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_73.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_74.png)

Related to this first rule， whenever possible， try to incorporate part of the user's question in your response。



![](img/f9ced88d4256bc0bf6b87eda442164f7_76.png)

The user will feel more understood， and the chatbot will be perceived as more intelligent as a result。



![](img/f9ced88d4256bc0bf6b87eda442164f7_78.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_79.png)

For example， the user might ask us if we have a store in a given city。



![](img/f9ced88d4256bc0bf6b87eda442164f7_81.png)

We have stores in Toronto， Montreal， Calgary and Vancouver is an okay response as it answers the question。



![](img/f9ced88d4256bc0bf6b87eda442164f7_83.png)

However， we could improve it by incorporating a bit of empathy and information provided by the user in our response。



![](img/f9ced88d4256bc0bf6b87eda442164f7_85.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_86.png)

If we reply， unfortunately we don't have a store in Seattle， frowning Imoticon。

 to date we have stores in Toronto， Montreal， Calgary and Vancouver。



![](img/f9ced88d4256bc0bf6b87eda442164f7_88.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_89.png)

We are still conveying the same information， but this time we come across are more empathetic with the user。

 and all we had to do is incorporate part of the user input in our response。



![](img/f9ced88d4256bc0bf6b87eda442164f7_91.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_92.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_93.png)

Along with ensuring that the answer we provide to the user is correct。

We should also consider its length。

![](img/f9ced88d4256bc0bf6b87eda442164f7_95.png)

Nobody likes to read walls of text。

![](img/f9ced88d4256bc0bf6b87eda442164f7_97.png)

Instead， people prefer to read answers that are one or two short paragraphs long at the most。



![](img/f9ced88d4256bc0bf6b87eda442164f7_99.png)

If you need to convey a lot of information in your reply。

 you are better off linking to a page on your site where the user can learn more about the topic。



![](img/f9ced88d4256bc0bf6b87eda442164f7_101.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_102.png)

Imagine a financial chat bot trying to respond to the user with the entire terms and conditions for a credit card application directly in the chat。



![](img/f9ced88d4256bc0bf6b87eda442164f7_104.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_105.png)

It would be comical。Liinking to the right page would be more appropriate。



![](img/f9ced88d4256bc0bf6b87eda442164f7_107.png)

And since we can embed HTML in our responses， we can make such links clickable。

 making it more convenient for the end user。

![](img/f9ced88d4256bc0bf6b87eda442164f7_109.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_110.png)

Okay， now it's your turn。By the end of this module。

 you should have a much better understanding of how intents。

 entities and dialogue work together to allow chatbots to provide useful answers to the end user。



![](img/f9ced88d4256bc0bf6b87eda442164f7_112.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_113.png)

In the next module， we'll discuss deployment and finally in the last two modules。

 we'll look into more advanced features that enable us to create smarter and more useful chatbots。



![](img/f9ced88d4256bc0bf6b87eda442164f7_115.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_116.png)

![](img/f9ced88d4256bc0bf6b87eda442164f7_117.png)