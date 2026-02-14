# 吴恩达《Llama2的提示工程｜Prompt Engineering with Llama 2》中英字幕（英字可关闭） - P4：4.L3_multi_turn_conversations.zh_en - GPT中英字幕课程资源 - BV1um411f7Lm

As you saw earlier， if you ask a model a follow up question。

It won't remember what you asked or how it answered your earlier question。

To get a large language model such as Lama， to act like a chatbot and remember your conversations。

 you'll practice prompting for multit conversations。

You'll get to ask the model to suggest fun things that you can do on the wechat。

 and then you'll be able to ask follow up questions based on the fun activities that it proposes。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_1.png)

Let's try it out。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_3.png)

As we have seen in the previous lessons， we will first import Lama from our u package。

 so let's do that。And we are going to ask a simple question to our Lama model ands。Create that。

I'm going to put in。What are some of the fun activities I can do this weekend？

And let's see the response from our model。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_5.png)

So Lama has responded with bunch of。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_7.png)

Nice activities I can do this weekend， outdoor activities， cultural events。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_9.png)

嗯。My favorite would be。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_11.png)

Spending a day at a spa with a massage。 But as you can see， the response is pretty good。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_13.png)

Now let's add another prompt。And I'm going to number this as Pro number two。I'm going to ask Lama。

Each of these would be good for my health。And I'm going to run this now。

 what do you think will happen？

![](img/76e4d5c6ce0415e3386ff82242e7b14d_15.png)

As you can see the output， the output says it talks about caffeine， it talks about alcohol。

 and it gives me a very generic output。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_17.png)

![](img/76e4d5c6ce0415e3386ff82242e7b14d_18.png)

Taking into account like what is good for my health？



![](img/76e4d5c6ce0415e3386ff82242e7b14d_20.png)

But what it did not do is it did not take into account these。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_22.png)

These was related to the fun activities I was going to do this weekend。 So here's what we did。

 You asked the model for some fun ideas to do this weekend。

 It generated a response with lots of good ideas， including hiking spa day and so on。

 makes you ask a followup question which of these activities is good for my health。 This time。

 Lama gave an answer that seems to have changed the topic。

 It's not referring back to its previous list of ideas。

 And instead talks about how caffeine alcohol are bad for health。

 Why did Lama change the topic Because it doesn't remember what you just asked it。

 The model is stateless。 So what do you need to do to get the Lama to follow the conversation and chat with you。

 So since the model isn't keeping track of our previous conversation。

 you can keep track of those prior prompts and responses to help Lama keep track We need to build up the context of the conversation。

 This means explicitly stating what has happened in previous。Of the chat。

 let's call the original question you asked as prompt1 and the response that Lama generated as response1。

 Now let's call the new question prompt 2 to get Lama to give the response that understands the previous turn。

 we pass prompt1 response1 and prompt2 to the model all as a single prompt。

 Now with all the context Lama generates a sensible answer that has stayed on topic letting us know that hiking is the healthy option。

 So this is how chatting with Lama words。 you need to keep track of all the back and forth of the conversation and pass it to Lama with each new prompt。

 Let's take a look at the general form of a chat prompt。

 You can see that the oral prompt is built up of a set of prompt response pairs。

The chat prompt always finishes with the latest prompt from the user。

 letting the model know it should respond。 Note that you are always passing a single prompt consisting of multiple parts。

 And with each turn， you will add in a new prompt response pair。 for Lama chat prompts。

 you have to use some special tags。 as you did with a single prompt。

 As before you wrap this user prompt and instruction tags。 So here you see the instruction tag。

 which we learned in previous lesson in square brackets。

 remember that a chat prompt ends with the latest input from the user。

 So youll wrap that with an instruction tags too。 then you wrap each prompt response pair with a new set of characterss called start and end tags。

 you open this last prompt with a start tag。 But this time you don't close with an end tag。

 That's because the turn isn't over。 you want the model to respond。

 Let's go back to the notebook and try this chat prompt format。Out in the code。

 So let's implement this in the code。Here's a prompt one。And。And our response。To pro one。

And rest around this。Here's a prom two。Now let's create our chat prompt。

And we have to make sure that we are putting the right。Tags in place。We'll put the prompt one here。

End it with our。Instruction tags。And。We'll get the response from our prompt one。

 and then we'll end it with R。Stop tag and for our next turn。We will again start with a new tag。

 well start tag an instruction tag。And we'll add our prompt you。

So let's print this prompt and see what do we get？Okay。So we got the full prompt。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_24.png)

Which we want。Now pass to the LLM。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_26.png)

But you can see our request prompt has instruction tags， it has a starter tag。

 and this is the response which we get from the model。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_28.png)

![](img/76e4d5c6ce0415e3386ff82242e7b14d_29.png)

And this is the end tag。 So this is the end of our first turn。

And this is the start of our second turn。 And we are asking sending a prompt to our Lama model。 Now。

 let's in this chat prompt。To the model。So the reason why we are sending。

Add lets go instant as false is because our helper function has instruction tags already inbuil。

 but those are for single turn chat。 And here we are constructing the prompt from multi turn chat。

 So we want to turn off the instruction tags addition from our helper function and we will add ver equals to true。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_31.png)

So that we can see our prompt。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_33.png)

So what we are seeing here is our。Well formatted prompt。 Here's the input prompt to the model。

 Here's the response， and here's the end of our single turn。

 and then here's our second prompt to the model。 Okay， so now let's print out the response。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_35.png)

![](img/76e4d5c6ce0415e3386ff82242e7b14d_36.png)

And see what happens So here's the response and you can see that the response is pretty good。

 it's related to our first prompt and it stores the previous contact。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_38.png)

![](img/76e4d5c6ce0415e3386ff82242e7b14d_39.png)

![](img/76e4d5c6ce0415e3386ff82242e7b14d_40.png)

And some of these activities look really good and maybe you can try out with your friends over the weekend Now let's move on to building a helper function for our multit chats for this lesson we have provided a second helper function that will format your chat history and prompt and we are calling this as Lama chat。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_42.png)

So let's import Lama chat。From us。And let's try to use that helper function here。

 so we will create the same prompt。What we did before。😔。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_44.png)

And let's create our pro 2。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_46.png)

The helper function takes in a list of prompts and responses。And so let's create that first。

Now as you can see， our number of prompts will be always be one greater than the response because we are passing the prompt response pairs to the model and expecting a response back。

 Okay， now let's create our response to。And we will pass in the prompts and responses。

And we'll turn on the ver true so that we can see。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_48.png)

The response， so we are setting the word equals to true so that we can see the prompt。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_50.png)

And here's the prompt， which looks pre accurate based on everything we have learned so far。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_52.png)

And let's print the response。

![](img/76e4d5c6ce0415e3386ff82242e7b14d_54.png)

![](img/76e4d5c6ce0415e3386ff82242e7b14d_55.png)

Great， now we can see。That we are getting a similar response。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_57.png)

Great， using our。Lma chat helper function Okay， as a next step。

 I would like you to try this yourself， try adding a follow up query to this conversation so you can add additional query right here。

 additional prompt You can ask like which of these activities would be fun with friends or any other question you might want to So I'm going to give you some starter code and you can try it by yourself。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_59.png)

So here's our prom three， which of these actors would be fun with friends。And as you can see。

 I've added additional prompt three in my list。And。We have now added a response。

 which we got response to。When we had called it prior to this running this cell and so I want you to try this and run it and see what response you get in the next lesson we will go over prompt engineering best practices that will help you prompt the LLM to perform a range of tasks including sumization and much more so let's go on to the next lesson。



![](img/76e4d5c6ce0415e3386ff82242e7b14d_61.png)

![](img/76e4d5c6ce0415e3386ff82242e7b14d_62.png)

![](img/76e4d5c6ce0415e3386ff82242e7b14d_63.png)