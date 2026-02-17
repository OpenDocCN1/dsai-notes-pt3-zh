# 吴恩达最新《面向开发者的ChatGPT提示工程》｜chatgpt-prompt-engineering-for-developers｜中英字幕 - P7：8_prompt_eng_08_chatbot_v3.zh_en - GPT中英字幕课程资源 - BV1e8411o7NP

![](img/c108a1a802fa35f3869e421ada174fb8_0.png)

One of the exciting things about a large language model is you could use it to build a custom chatbot with only a modest amount of effort。

 chat GT， the web interface is a way for you to have a conversational interface。

 a conversation via a large language model。 But one of the cool things is you can also use a large language model to build your custom chatbot to maybe play the role of an AI customer service agent or an AI order taker for a restaurant in this video。

 you learn how to do that for yourself。😊，I'm going to describe the components of the Open AI chat completions format in more detail。

 and then you're going to build a chatbot yourself。😊。



![](img/c108a1a802fa35f3869e421ada174fb8_2.png)

So let's get into it。So first， we'll set up the open AI Python package as usual。

So chat models like ChaGBT are actually trained to take a series of messages as input and return a model generated message as output。

And so although the chat format is designed to make multi-t conversations like this easy。

 we've kind of seen through the previous videos that it's also just as useful for single turn tasks without any conversation。

 And so next， we're going to define two helper functions。

 So this is the one that we've been using throughout all the videos。

 and it's the get completion function。😊，But if you kind of look at it， we give a prompt。

 but then inside the function， what we're actually doing is putting this prompt into what looks like some kind of user message and this is because the chatTBT model is a chat model。

 which means it's trained to take a series of messages as input and then return model generated message output So the user message is the input and then the assistant message the output。



![](img/c108a1a802fa35f3869e421ada174fb8_4.png)

So in this video， we're going to actually use a different helper function。

 and instead of kind of putting a single prompt as input and getting a single completion。

 we're going to pass in a list of messages and these messages can be kind of from a variety of different roles。

 so I'll describe those。😊。

![](img/c108a1a802fa35f3869e421ada174fb8_6.png)

So here's an example of a list of messages and so the first message is a system message which kind of gives an overall instruction and then after this message we have turns between the user and the assistant and this will kind of continue to go on and if you've ever used chat GT。

 the web interface， then your messages are the user messages and then chat GT's messages are the assistant messages。

So the system message helps to kind of set the behavior and persona of the assistant。

 and it acts as kind of a high levell instruction for the conversation。

 So you can kind of think of it as whispering in the assistant's ear and kind of guiding it responses without the user being aware of the system message。

 So as the user， if you've ever used chat GBT， you probably don't know what's in chat GBTs system message。

 The benefit of the system message is that it provides you。

 the developer with a way to kind of frame the conversation without making the request itself part of the conversation So you can kind of guide the assistant and kind of whisper in its ear and guide its responses without making the user aware。



![](img/c108a1a802fa35f3869e421ada174fb8_8.png)

So now let's try to use these messages in a conversation。



![](img/c108a1a802fa35f3869e421ada174fb8_10.png)

So we'll use our new helper function to get the completion from the messages。



![](img/c108a1a802fa35f3869e421ada174fb8_12.png)

And we're also using a higher temperature。So the system message says you' are an assistant that speaks like Shakespeare。

 so this is us kind of describing to the assistant how it should behave and then the first user message tell me a joke。

 the next is why did the chicken cross the road and then the final user message is I don't know。



![](img/c108a1a802fa35f3869e421ada174fb8_14.png)

So if we run this。The response is to get to the other side， let's try again。To get to the other side。

 first， Sarah Madame tis an olden classic that never fails。 So there's our Shakespearean response。😊。



![](img/c108a1a802fa35f3869e421ada174fb8_16.png)

![](img/c108a1a802fa35f3869e421ada174fb8_17.png)

And let's actually try one more thing because I want to make it even clearer that this is the assistant message。

 So here， let's just go and print the。The entire message response。



![](img/c108a1a802fa35f3869e421ada174fb8_19.png)

So just to make this even clearer， this。

![](img/c108a1a802fa35f3869e421ada174fb8_21.png)

Response is an assistant message， so the role as assistant and then the content is the message itself。



![](img/c108a1a802fa35f3869e421ada174fb8_23.png)

![](img/c108a1a802fa35f3869e421ada174fb8_24.png)

So that's what's happening in this helper function。

 we're just kind of passing out the content of the message。So now let's do another example。

 So here our messages are the is message is Euro friendlyly chatbot and the first user message hi。

 my name is Ea and we want to。Get the first user message。

 So let's execute this or the first assistant message。And so the first message is，Hello Isa。

 it's nice to meet you， how can I assist you today？



![](img/c108a1a802fa35f3869e421ada174fb8_26.png)

![](img/c108a1a802fa35f3869e421ada174fb8_27.png)

Now let's try another example。So here our messages are。System message。

 your a friendly chatbot and the first user messages。Yes。Can， can you remind me， what is my name。

And let's get the response。And as you can see。The model doesn't actually know my name。



![](img/c108a1a802fa35f3869e421ada174fb8_29.png)

So each conversation with a language model is a standalone interaction。

 which means that you must provide all relevant messages for the model to draw from in the current conversation。



![](img/c108a1a802fa35f3869e421ada174fb8_31.png)

If you want the model to draw from or quote unquote remember earlier parts of a conversation。

 you must provide the earlier exchanges in the input to the model and so we'll refer to this as context so let's try this。



![](img/c108a1a802fa35f3869e421ada174fb8_33.png)

So now we've kind of given the context that the model needs。

 which is my name in the previous messages and we'll ask the same question。

 so we'll ask what my name is。

![](img/c108a1a802fa35f3869e421ada174fb8_35.png)

![](img/c108a1a802fa35f3869e421ada174fb8_36.png)

And the model is able to respond because it has all of the context it needs in this kind of list of messages that we input to it。

😊，So now you're going to build your own chatbot。This chatbot is going to be called Autobot and。😊。

We're going to automate the collection of user prompts and assistant responses in order to build this order bot。

And it's going to take orders at a pizza restaurant。

 So first we're going to define this helper function。

 and what this is doing is it's going to kind of collect our user messages so we can avoid typing them in by hand in the same in the way that we did above and this is going to kind of collect prompts from a user interface that will build below and then append it to a list called context and then it will call the model with that context every time。



![](img/c108a1a802fa35f3869e421ada174fb8_38.png)

And the roal response is then also added to the context。

 so the kind of model message is added to the context， the user message is added to the context。

 so on， so it just kind of grows longer and longer。This way。

 the model has the information it needs to determine what to do next。

And so now we'll set up and run this kind of UI to display the autobot。



![](img/c108a1a802fa35f3869e421ada174fb8_40.png)

And so here's the context and it contains the system message that contains the menu。



![](img/c108a1a802fa35f3869e421ada174fb8_42.png)

![](img/c108a1a802fa35f3869e421ada174fb8_43.png)

And。Note that every time we call the language model。

 we're going to use the same context and the context is building up over time。



![](img/c108a1a802fa35f3869e421ada174fb8_45.png)

And then let's execute this。Okay， I'm going to say， hi， I would like to order a pizza。

And the assistant says， great， what pizza would you like to order， We have pepperoni。

 cheese and eggplant pizza。😊，嗯。How much are they？Great， okay， we have the prices。

I think I'm feeling a medium eggplant pizza。

![](img/c108a1a802fa35f3869e421ada174fb8_47.png)

![](img/c108a1a802fa35f3869e421ada174fb8_48.png)

So as you can imagine， we could continue this conversation and let's kind of look at what we've put in the system message。

😊。

![](img/c108a1a802fa35f3869e421ada174fb8_50.png)

So you are order about an automated service to collect orders for a pizza restaurant。

 You first greet the customer， then collect the order， and then ask if it's a pickup or delivery。

 You wait to collect the entire order， then summarize it and check for a final time。

 If the customer wants to add anything else。 If it's a delivery， you can ask for an address。 Finally。

 you collect the payment。 make sure to clarify all options。

 extras and sizes to uniquely identify the item from the menu。 You respond in a short。

 very conversational， friendly style。 The menu includes。 And then here we have the menu。



![](img/c108a1a802fa35f3869e421ada174fb8_52.png)

![](img/c108a1a802fa35f3869e421ada174fb8_53.png)

So let's go back to our conversation and let's see if the assistant kind of has been following the instructions。

😊。

![](img/c108a1a802fa35f3869e421ada174fb8_55.png)

Okay， great， the assistant asks if we want any toppings。

 which we kind of specified in the system message。

![](img/c108a1a802fa35f3869e421ada174fb8_57.png)

![](img/c108a1a802fa35f3869e421ada174fb8_58.png)

So I think we want no extra toppings。Sure thing， is there anything else we'd like to order？

Let's get some water， actually。Fries。

![](img/c108a1a802fa35f3869e421ada174fb8_60.png)

Small or large。 And this is great because we kind of asked the assistant in the assistant message to kind of clarify extras inside。



![](img/c108a1a802fa35f3869e421ada174fb8_62.png)

![](img/c108a1a802fa35f3869e421ada174fb8_63.png)

So。

![](img/c108a1a802fa35f3869e421ada174fb8_65.png)

And so you get the idea and please feel free to play with this yourself。

 you can pause the video and just go ahead and run this in your own notebook on the left。😊。

And so now we can ask the model to create a JSON summary that we could send to the order system based on the conversation。

So we're now appending another system message which is an instruction and we're saying create a JSO summary of the previous food order。

 itemize the price for each item， the fields should be one pizza include side。2 list of toppings。

 three lists of drinks and four list of sides。 And finally， the total price。 And you could also。

Use a user message here， this does not have to be a system message。So， let's execute this。

And notice in this case we're using a lower temperature because for these kinds of tasks we want the output to be fairly predictable for a conversational agent you might want to use a higher temperature。

 however， in this case I would maybe use a lower temperature as well because for a customer' assistant chatbot you might want the output to be a bit more predictable as well。



![](img/c108a1a802fa35f3869e421ada174fb8_67.png)

![](img/c108a1a802fa35f3869e421ada174fb8_68.png)

![](img/c108a1a802fa35f3869e421ada174fb8_69.png)

And so here we have the summary of our order。And so we could submit this to the order system if we wanted to。



![](img/c108a1a802fa35f3869e421ada174fb8_71.png)

So there we have it， you've built your very own order chatbot。

 feel free to kind of customize it yourself and play around with the system message to change the behavior of the chatbot and kind of get it to act as different personas with different knowledge。

😊。

![](img/c108a1a802fa35f3869e421ada174fb8_73.png)