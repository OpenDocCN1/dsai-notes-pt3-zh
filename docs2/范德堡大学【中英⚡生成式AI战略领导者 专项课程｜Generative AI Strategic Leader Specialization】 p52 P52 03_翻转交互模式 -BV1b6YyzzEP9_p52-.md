# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p52 P52 03_翻转交互模式 -BV1b6YyzzEP9_p52-

Let's look at the basis of this eogenictic systems。

 how do we kick off and get generative AI to go and work this way and there is a prompt engineering pattern and I've talked about it my first class prompt engineering for ChaGBT and a paper I did。

 but I think of this as the basis for all this stuff which is a flipped interaction where rather than us telling the system what to do rather than us asking it questions。



![](img/4dc0e47f6cea742d61ce65358166e85e_1.png)

It goes and tells us what to do， it asks us questions。

 or really it goes and asks existing computer systems questions。

 it runs queries and databases to collect information it needs。

 or it goes and tells those systems to run actions that it needs run in order to accomplish some goal that we give it。



![](img/4dc0e47f6cea742d61ce65358166e85e_3.png)

So I want to take a quick look at the flipped interaction pattern and talk about how this works。

So the basic structure of this pattern is we go and tell it that you're going to ask me questions at one at a time in order to get enough information to suggest a restaurant for me to eat at in Nashville。

 Tennessee tonight。You can think of this in this basic pattern as ask me questions one at a time and one at a time is often the best for gen systems。

 it doesn't have to be one at a time， but we'll talk about this in a minute。

 so go and ask me questions or tell me what to do one step at a time。



![](img/4dc0e47f6cea742d61ce65358166e85e_5.png)

And the goal of this is we want to create a situation where it goes and creates things that need to be done。

 tasks that need to be performed or actions that need to be taken。

 and then the system will go and execute those actions on behalf of the agent and tell it what happened。

 and so this rough pattern of prompting， ask me questions one at a time。

 tell me what to do one step at a time， creates this environment where it's being told you're in the driver's seat go and do it。



![](img/4dc0e47f6cea742d61ce65358166e85e_7.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_8.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_9.png)

And then at the bottom I say ask the first question。

 this is a trick that works really well in lots of systems to make sure that we start off with one question only。

 or we say， tell me the first step so that we start off with one step only。

 we want to create a powerful pattern， a behavior where it goes off and it knows what to do that it' going to do this one step at a time。

So let's look at our prompt， ask me questions one at a time in order to get gather enough information to suggest restaurants for me to eat at in Nashville。

 Tennessee tonight， ask me or ask the first question。



![](img/4dc0e47f6cea742d61ce65358166e85e_11.png)

And it comes back， what type of cuisine are you in the mood for tonight？

And I'm going to come back and I'm going to say TM。

 so now I've given it an answer and it has to adapt and part of the adaptation is choosing the next question to ask me that is wildly powerful。

 that simple thing of looking at what information it was given and then choosing the next question in response is critically important because the same thing happens in a task。

 it ask for a task to be run， it looks at what happened and then it adapts what the next task is going to be based on what happened。



![](img/4dc0e47f6cea742d61ce65358166e85e_13.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_14.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_15.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_16.png)

Same thing with questions， so I say text Max。

![](img/4dc0e47f6cea742d61ce65358166e85e_18.png)

And then it says do you have any dietary restrictions or preferences， I say no。

 it adapts the next question then because if I'd said yes。

 it probably would have gone off and then asked me questions about them， but since I said no。

 it' said okay， do you prefer a casual dining experience or something more upscale I say kidf I just give it some you feedback and notice I'm not constraining my responses to any type of format I'm giving it very free flowing。

 it's having to adapt and not only to the information I'm giving it。

 but the format that I'm giving it the information， it's very fluid in what it's doing。



![](img/4dc0e47f6cea742d61ce65358166e85e_20.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_21.png)

Um， would you like a restaurant with outdoor seating or indoor seating or does it not matter and I say。

 well， it doesn't matter it's raining， so I'm probably not going to eat outside。



![](img/4dc0e47f6cea742d61ce65358166e85e_23.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_24.png)

And then it goes further and it says， do you have a specific preference for a specific area and I say near Vanderbilt。

 great， how far are you willing to travel， I say， well is short drive five to10 minutes。



![](img/4dc0e47f6cea742d61ce65358166e85e_26.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_27.png)

And then it saysGot it， you have any preference for a restaurant that takes reservations are you okay with walk in and I say walk ins fine but I don't want to have an insane weight and you notice this is totally fluid each time I respond to one of its questions it's adapting that is the agent part beginning to happen that is the agent magic It's also adapting to all the different formats and ways that I can specify my input and this is one of the important parts of large language models is that they can handle input in so many different formats so many different ways of expressing the information and the idea without us having to go and build some complex thing to be able to handle all these crazy ways that I'm responding。



![](img/4dc0e47f6cea742d61ce65358166e85e_29.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_30.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_31.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_32.png)

And then after I give it the walk in sing， it says， okay， based on your preferences。

 I recommend rose pepper cantina。

![](img/4dc0e47f6cea742d61ce65358166e85e_34.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_35.png)

And I go and Google map this。 And I'm like， well， right now from my house。

 that's actually about 13 minutes with traffic slightly farther than I want to drive。

 So I just go back and I say， hey， Google Maps says it's 13 minutes away。

 feeling a little lazy for that t。 And it comes back and it says， okay， in that case， go to Sco。

 Sco happens to be right across the street from Vanderbilt。 And so。😊。



![](img/4dc0e47f6cea742d61ce65358166e85e_37.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_38.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_39.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_40.png)

Now， that's something really powerful and valuable that I can go and employ to help me solve a problem。

 right， Now， I can solve a problem like this。 Like where should I go， I help make a decision。

 help guide me as a human being。

![](img/4dc0e47f6cea742d61ce65358166e85e_42.png)

And it's collecting information from me there's no difference between it collecting information from me and it collecting information from a database it's just the interface to collect that interface changes or interface to collect that information changes so asking the human being is much easier right because the human being can adapt to whatever it says the difference is is when it goes and collects information from a real computer system like a database。

 it's going to have to speak the language of that database。

 it's going to have to speak the language of that computer system so it's going to have to translate。



![](img/4dc0e47f6cea742d61ce65358166e85e_44.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_45.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_46.png)

The goal to whatever the target language is， and if you think about something these models and large language models are supremely good at。

 it is translation。

![](img/4dc0e47f6cea742d61ce65358166e85e_48.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_49.png)

Absolutely good at translation， excellent experts at language， so that piece is again。

 one of the huge benefits is that we go and express what we want。



![](img/4dc0e47f6cea742d61ce65358166e85e_51.png)

In our human language， it decomposes it into a plan to go and accomplish it。

 it interactively begins executing its plan。

![](img/4dc0e47f6cea742d61ce65358166e85e_53.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_54.png)

And when it's a human on one side， it'll ask it in human language。

 but when it needs to go and it needs to talk to you know a database。

 it can go and begin speaking that database language， just kind of like in Star Wars。

 that protocol droids it spoke all these different languages and could communicate with all these different systems and they acted as the interface to those systems。

 that is what generative AI is doing and aic AI is working very similarly。

 but rather than just asking it a question in us really directing everything one step at a time。

 agent AI we're giving it the ability to go and perform many different steps and adapt。

 it chooses the step， we perform it， it gets information back about what happened as a result of the step and then it adapts and that continues on and on。



![](img/4dc0e47f6cea742d61ce65358166e85e_56.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_57.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_58.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_59.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_60.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_61.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_62.png)

![](img/4dc0e47f6cea742d61ce65358166e85e_63.png)