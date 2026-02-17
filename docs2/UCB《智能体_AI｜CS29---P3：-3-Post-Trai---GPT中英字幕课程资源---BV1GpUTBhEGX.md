# UCB《智能体 AI｜CS294-196 Agentic AI MOOC 2025》中英字幕 - P3：-3-Post-Training Verifiable Agents by Jiantao Jiao.zh_en.mp4 - GPT中英字幕课程资源 - BV1GpUTBhEGX

Good afternoon， everyone。 Very excited to be here to be talking about post training very agents。

 So the agent AI course is a super exciting course。

 I believe that you'll be able to learn a lot from lots of people。😊。



![](img/e87f9e6f09420326af124f5290d73632_1.png)

First of all， that disclaimer that everything I talk about here in a lecture。

 all the views I express are solely those of the guests with me and not represented representative of the company。

 including NVdia or or UC Berkeley。😊，So well be focusing on post training variable agents。

 which is very important topics in building highly reliable agent systems from the basic requirements of building agent models。

😊。

![](img/e87f9e6f09420326af124f5290d73632_3.png)

So how do the agency models different。D from traditional large language models。

But on the very early days when Ms was first produced。

We use a technique called reinforcein learning from human feedback。At that time。

 the language models really trained to align really well with human preference。For example。

 they interact with you， they really understand what you are saying， make you feel better。😊。



![](img/e87f9e6f09420326af124f5290d73632_5.png)

But later， essentially all the frontier labs and all the model vendors started to add this agent capabilities to their models。

😊。

![](img/e87f9e6f09420326af124f5290d73632_7.png)

![](img/e87f9e6f09420326af124f5290d73632_8.png)

And precisely， for an agent model。The model is really aligned with environment feedbacks by environment。

 actually means something very specific later I your detail。

 They are designed to provide interactions to maximize verifiable rewards in addition to human preference。

 So basically， when you after talking to those agent language models。

 They are supposed to really understand your intentions very well because it's designed to first maximize human preference。

 but also at the same time， it's designed to help you accomplish tasks。😊，That's extremely critical。

 And for evaluating the quality of task completion。

 we usually use something different from generic reward models， because for certain tasks。

 maybe there will be a few correct answers and there will be really wrong answers。

 You absolutely cannot do that。 And usually for human preference and the situations that are different。

😊。

![](img/e87f9e6f09420326af124f5290d73632_10.png)

![](img/e87f9e6f09420326af124f5290d73632_11.png)

![](img/e87f9e6f09420326af124f5290d73632_12.png)

So brief recap of earlier models that were trained to be great chatbots。

 So what we trained usually is the following。 say you collect lots of human assistant chats。

 human say something， assistant says something。 Then later you would like to write assistant responses based on human preference。

 Maybe you dosurcing us lots of people。 then you collect this human preference。

 then you try to figure out reward modeling technique to come up with a reward model。

 basically based on the human assistant interactions trying to create whether a certain response from the assistant is good or not。

😊。

![](img/e87f9e6f09420326af124f5290d73632_14.png)

![](img/e87f9e6f09420326af124f5290d73632_15.png)

![](img/e87f9e6f09420326af124f5290d73632_16.png)

Once you get really high quality reward model， we like to start training the language model so that it can actually behave better in terms of maximizing human preference。

😊，There are many algorithms you can use here。 So， I also include the SFT。 Sometimes people say SFT。

 which is the ariation for super fun tuning， is mostly used for strictly mimic mimicking the actual behavior。

 I include here because SFT actually is also being used a lot。

 even when you are given the reward model。 So the intuition that I can use the reward model to grade multiple different responses from the assistant。

 Then basically， I can only choose those assistant responses that rank very high by the reward model Then conduct super fun tuning on those responses。

😊。

![](img/e87f9e6f09420326af124f5290d73632_18.png)

![](img/e87f9e6f09420326af124f5290d73632_19.png)

![](img/e87f9e6f09420326af124f5290d73632_20.png)

![](img/e87f9e6f09420326af124f5290d73632_21.png)

I can also use other reinforced learning algorithms like PP，O and GRPO。

 Any algorithm you come with or you have heard of。 Finally。

 to produce a model to maximize human preference。 hopefully， by talking to that model。

 you feel that iss really engaging model really understands you。 You feel very happy about this。😊。



![](img/e87f9e6f09420326af124f5290d73632_23.png)

Feel free to also stop me when you have questions。

![](img/e87f9e6f09420326af124f5290d73632_25.png)

What more is necessary， So it turns out one of the key applications of IOMs exactly agent tasks。

 Converations is not verifiable。 They are also usually no clear single correct answer。

 use a really sophisticated reward model to model preference and requires the interaction with the user only but in terms of enterprise applications of IOMs。

 many tasks， they have they actually require the deep interaction between the human。

 sometimes multiple people， multiple assistance and many other entities including the environment。

 specific coderepo， specific software system and many different tools。

 So basically you need to make sure that IOMs able to understand the feedback given by many different entities understand the full states of this environment and also make sure that when IM perform a certain task it's able to really produce the correct answer and there's a very clear verifier。

😊。

![](img/e87f9e6f09420326af124f5290d73632_27.png)

![](img/e87f9e6f09420326af124f5290d73632_28.png)

![](img/e87f9e6f09420326af124f5290d73632_29.png)

![](img/e87f9e6f09420326af124f5290d73632_30.png)

![](img/e87f9e6f09420326af124f5290d73632_31.png)

Demonstrating whether the answer is correct or not。

 And you should really not produce the wrong answers。

 because that's not gonna to make the whole system totally crash。



![](img/e87f9e6f09420326af124f5290d73632_33.png)

So sometimes people say that you can use other Tiistic system to help fix that。

 But one thing people have found is that if the IM is not strong enough in producing essentially right answers。

 it's very， very hard to build a reliable system。 even after you do lots of software engineering on top of this。

😊。

![](img/e87f9e6f09420326af124f5290d73632_35.png)

![](img/e87f9e6f09420326af124f5290d73632_36.png)

![](img/e87f9e6f09420326af124f5290d73632_37.png)

![](img/e87f9e6f09420326af124f5290d73632_38.png)

So precisely for today's models， they are trained to be great agents。😊。

The user no longer asks a question saying， how are you， You start very engaging conversations。

 Your user has a very clear target， sometimes even wake。

 but there's something user wants to accomplish。 that I want to achieve this。 I want to book flights。

 I want to talk to my server system。 Then the IM needs to be able to understand this。

 and precisely execute。😊，So there are many different ways to evaluate the outputs of IM and the system。

 There are different rubrics defined by people。 You can also write down different ground truth。

 You have a very clear recording of the environmental states and you also conduct lots of unit tests to check the output of the Is。

 by doing this， you get very good signals。 you understand whether the output of IM in this case is right or not。

 Then you start to use lots of other post string algorithms。 Again。

 super fine tuning PPO GRPO to actually improved model。

 So eventually the goal is that you want to construct a very strong agent model to maximize correctness by interacting with with within sandbox with very complex tools。

 I will try to make everything very precise later when we go into the details of this。😊。



![](img/e87f9e6f09420326af124f5290d73632_40.png)

![](img/e87f9e6f09420326af124f5290d73632_41.png)

![](img/e87f9e6f09420326af124f5290d73632_42.png)

![](img/e87f9e6f09420326af124f5290d73632_43.png)

Okay。But what is needed to train the verifi agent models In particular， it is a very important topic。

 Lots of people in the community are focusing on。 I would say that there are three core steps。

 and each one is actually very challenging these days。

 it really requires the collaboration of many people across industry across academia to contribute to this so that will be able to get a very。

 very strong agency language models in the future。😊，So the first step。

 I say to get good verifiable training data to train agents without high quality training data。

 we simply cannot produce very high quality agent I Ms。

 Ill be talking about the challenges behind getting very high quality training data。😊。

The step2 is actually evaluation。You collect the data， you figure out your are training approach。

 you change the model， but then you need to really understand whether it's good or not。😊。

So generally， there's a very dangerous trend of really entering the in illusion that we feel。

 we collect the data。 The data is comprehensive enough。

 Then we only at the things that are really aligned with our data。

 It really appears that everything's working really well。 Then suddenly。

 we test everything in a wild。 Things start to break。 So how do we define a verifiable agents。😊。



![](img/e87f9e6f09420326af124f5290d73632_45.png)

We actually talking about some concrete examples。 Make least I try to make it even more concrete。

 For example， one thing could be that you're solving a math problem Then the computer I M also has access to certain tools。

 For example， Python coding tool。 Then after accessing to the coding tool， writing lots of codes。

 understanding a problem。 Finally， the I M is supposed to produce an answer。 for example。

 the final answer to the math problem is number 2。😊。

Now I want to make sure it's precisely the right answer。😊，So just one example。

 The other example in software engineering， you're able to produce a code， a code script。

 and then there are many different ways to check the validity of the code。 For example。

 there are so many different union tests I can write。

 You need to be be able to pass all of these tests to make sure that finally is correct。

 turns out it is really complicated the question。 So there are so many different verifiers you can build。

 And the current challenge everybody is facing in the community is that we haven't got enough strong verifiers to really make sure that we captured all all the corner cases of the intelligence。

😊。

![](img/e87f9e6f09420326af124f5290d73632_47.png)

![](img/e87f9e6f09420326af124f5290d73632_48.png)

![](img/e87f9e6f09420326af124f5290d73632_49.png)

So the third step is actually also about training。 So these is also a very complex topics。

 till today， many people community are training very hard to research on this。

 which is that I got very good training data。 I also figured how to evaluate my agents。

 But what exactly is the best way of feeding the data to the models so that the models the intelligence in。

 in fact， actually improves。😊，In some sense， when we think about building the verifiable agents。

 we really think about this essentially as the training a human being。

 So when you are training like engineer in a company。

 what usually you do is that you first gave some instructions。 You say， well。

 maybe you supposed to write code in this way。 or you're supposed to operate the solar system in a certain way。

 Then the person started doing that。 started writing code。

 started interacting with a software system， some making tickets， things like that。

 Then sometimes they will make mistakes。 But they will receive some feedback。😊。

The key challenge is that for human， you can just tell the human Well。

 here's the feedback I give to you。 What about next time you do better。But for the machine。

 the hardest part is to transform this natural human interaction into something that's implementable by algorithm。

 So the algorithm needs to make sure once the IM first attempt something， but it made a mistake。😊。



![](img/e87f9e6f09420326af124f5290d73632_51.png)

![](img/e87f9e6f09420326af124f5290d73632_52.png)

I give the IM very detailed feedback。 How do I guarantee that next time the IM also attempts the same question。

 The quality of its time actually improves。😊，If I'm not able to achieve this， then basically。

 I'm not able to replicate this natural feedback by loop of human learning。

 then we're gonna really hit a plateau of the final intelligence of the system。😡。

So that's why the step 3 is also extremely critical。

 we also be spending lots of time talking about step 3。

 including some approaches people have taken in the past。

 But I really want to emphasize that all all the three steps they require very extensive research at this point。

 So it's actually a fascinating opportunity for everyone to get into the field at this point。😊。



![](img/e87f9e6f09420326af124f5290d73632_54.png)

![](img/e87f9e6f09420326af124f5290d73632_55.png)

O， talking about the first thing， getting good training data。

So agent models maximize verifiable rewards。 What exactly would be the core components of training data that we specify to really make sure that's the actual of high quality。

😊，So I want first of want to emphasize three different things。 They are kind of very。

 very related in certain literature。 Maybe they are combined together。

 but I do think that think that things are slightly different。

 So I want to emphasize three different aspects of the dataset sets。

 The first is called the environment。😊，So how do I think about the environment for the agent。

 So say if you build coding agent， right， So basically， the agent takes in your instructions。

 trying to generate code in well formulas the code rappo。 maybe the code rep has some issues。

 There' are certain bugs， you supposed to fix that the environment basically in codes the whole state of this rappo。

 For example， the prefi and surface of the code script。

 and lots of files we have load lots of downstream tasks we need to deal with they describe the states of the environment。

 and also it includes lots of system prompts， people have already set up for different parts to work together。

😊，The second part I want to talk about is tools。 So basically， the agent I。

 they are trained to generate tokens that are consumed by software tools to provide additional relative information to the model。

 So precisely you should think of this as additional in software engineering language。

 additional APIs provided to the system。 For example， you call the system。

 Well the user asked your question was to whether I M is not supposed to know that But I really knows that it is access to certain APIs that's able to access to this weather。

 The M is supposed to be producing the exact API call to the external system。

 an external system should be able to feedback the concrete information regarding to this whether should be able to internal as that。

 Then finally presents the final answer to the user。😊。

So they could the APIs could be put provide additional information。

 The As could actually also help change the environment states。 So basically。

 your working environments， the state is really complex， has lots of different moving parts。

 then maybe you are given certain tools to help you modify the states because maybe in order to actually accomplish certain task。

 there will be certain states needs to be changed。 Maybe even the user doesn't doesn't know that。

 But as a very strong agent I am， the system is supposed to know that user gives the task。

 Then the agent is supposed to be able to decompose the task。

 figure out what exactly are the right tools to call， change the environment states if necessary。

 and finally produce answer。😊，And point3 is really about checking the answer。 So basically。

 model are trained to generate tokens。 It produced the answer。

 But how do I even know if the answer is correct or not， when need to build so called verifiers。

The verifiers will tell you whether you have really succeeded in conventional tasks。😊，In some sense。

 it's also quite challenging because there are lots of intricate issues related to evaluation。

 Maybe you really produced a right answer。 but you took it took you like so many steps。

 It consumed so many tokens。 Maybe I'm always actually also supposed to panelize YouTube to this。

 So even for that， turns out it's really very good to think about verifiers， not as a single number。

 checking it is correct or not。 Think of this， really as a vector。

 talking about evaluating the quality of the model from many different perspectives。

 It can be unit test for code， which is talk about math check for proofs over web tasks。

 You can also check whether you have really accomplished a certain task on your browser。😊。



![](img/e87f9e6f09420326af124f5290d73632_57.png)

So that the three aspects， then I want to talk about some of the challenges in in preparing the the data。

 So the first step is to get good training data in getting in training these very strong agents。😊。

And in order to really make sure it works in the wild。

 it appears that you need really follow a principle to say。

 I need to understand many different environments。 I need to have a systems that's able to use many different kinds of tools。

 I also need to make sure that system does well under so many different verifiers。

 that actually is a very interesting and it's also the lessons learned by the whole community over the past two years。

 showing that when definitely shouldn't be trick to believe that the whole system is working very well when you actually only working with very few environments。

 very limited verification。 because the system would indeed break once you go beyond the the scope of your data。

 and a key challenge here is really make sure that you got enough coverage。😊。



![](img/e87f9e6f09420326af124f5290d73632_59.png)

So here I want to give you some more examples talking about what we have been discussing on a high level。

 say you want to train a very strong agent system。 and then there are so many possible combinations or environments。

 tools and verifiers。 For example， in environments that there can be math。 for math environments。

 you are given a problem then interact with a user I provides answer then you could have a math verify verifiers prove checker then in the environments。

 you actually could also have access to different coding tools That why these days。

 sometimes when you useGBT， you see that you ask a math question。

GBT actually would call Python try to write some script to really verify that answer is exactly correct。

😊，Or you are working with underpresss software， for example， here， talk about the sales assistant。

 then it could to access different software API tools。

 Maybe a salesperson wants to ask todays whether I want to get news Maybe I also want to access the database built in my system。

 Maybe I want't understand who actually are my customers。

 What exactly is the progress with customers。 and maybe I want to really write really a precise query language to query the database and also to make sure that I'm able to internalize the outputs from the database。

😊，So many different types of environments， tools and verifiers is very important。

 we achieve very good coverage， and it' always an interesting challenge to make sure that we indeed covered the all the important aspects we care about。

 So that's why it's also a super exciting time to do research。

 because always we got something more to work on。😊。



![](img/e87f9e6f09420326af124f5290d73632_61.png)

One thing I want to really emphasize which is， is very fair quality。 And these days。

 when we look at the open source community is's actually one thing that's that's really lacking at this point。

😊，So， generally。One thing one have one has observed is that it's very easy to think about one rule to verify certain answer and just put it down as a single verifier。

😊，But the thesis that has appeared again， again in the community was that whenever we thought we have built a very high quality verifier in checking the answer of the Is。

 turns out we have missed some corner cases。 So here I'm just showing you something very basic。

 which has already been covered by the community。 but they are way more complex examples showing that it's actually quite difficult。

 for example， let's say， the user has a question， I want to ask how much change when I get back。

 If I buy a drink for 50 cents and give a dollar。😊，Then give multiple different answers， Right。

 So basically can give one half to4。 Then in terms of the ver quality。

 you are really supposed to say that all of these are correct because they actually indeed tell you。

 what's the right amount of change。😊，However， user question could actually also include something more stringent。

 For example， in addition to just asking you， how much change would I get back。

 I have additional request。 Please just give me the simplest form。😊，So once I have that。

 the verifier honestly is supposed to be different because supposed to be one half。😊。

Then in these cases， in particular， it's very easy to make mistakes when you are constructing the verifiers and those those cases are usually very costly。

 because generally， these days alarms are already quite strong。

 You'll give them a very simple question。 You you able to answer it。😊。

And only in those challenging cases would sometimes make a mistake。

 But if you verify it's also wrong， didn't capture the nuance in the， in the question， you。

 you absolutely cannot further improve the quality of A M。

 So that's actually one thing we really want to emphasize。Ts false positive， false negative。

 which is better worse maybe more more significant in in actually， in our experiences。

 I would say that it， it's very important to minimize both types of errors。😊，Because it's sometimes。

 of course， it's also because。In in different applications。

 you assign different ways to different types of errorss。 But in reality。

 you can always find the interesting applications where a particular type of error。

 either force positive or false negative could give produce catastrophic results。

 So you really want to make sure that doesn't really happen。

 You want to conduct minimum software engineering to finally fix the outputs of thes。😊。

So I'm just showing this as example， trying to convince you it's actually quite challenging to write very good verifiers because there are lots of nuance in evaluating the final output。

😊。

![](img/e87f9e6f09420326af124f5290d73632_63.png)

Okay， so。Then we， we talk about the first part， which is how to get very high quality training data Y train very high very。

 very good agency L Ms。 Now， thenll be talking about the the second component。

 which is getting good evaluation data。😊，So it's kind of connected to training data。

 in relative we focus on this。 we do try to view this from a different perspective in some sense。

 even trying to tackle certain aspects that are not really being paid attention to in training。

 because the intuition is that we really wanted training to be generalizable。

 So basically in in connectinging training data， there is actually no way we have collected all the data in the world。

 For， I just think about amount the data， human being who would produce。

 when we are interacting with Internet。 when we are internet interacting with the browser。

 when we are doing math proofs or engineers code。😊。



![](img/e87f9e6f09420326af124f5290d73632_65.png)

That's basic unlimited。 There actually is no way we just cover all of them。

So the whole point is that you want to build a very good pipeline。

To make sure that once you achieve solid coverage of training data its supposed to generalize to many environments you haven't really seen because there's actually no way you you see all of these。

 the different environments。😊，That's actually one task that this good evaluation is supposed to capture。

 For example， here， I'm just list very few like targets of a good agent model。 later。

 I'll be talking about some existing evaluation systems。

 people have already built to capture those targets。 For example。

 one thing I want agents to work with many different tools。 It's so natural。

 If agent currently works a few different tools。 I give a new one。

 Maybe the user motivifies a tool than the system that breaks。 we really cannot tolerate that。

 It's also expected to work for many different use cases。

 It's also very natural because maybe the user today also comes up with a different use case。

 You also do not want the system to break。 It operates with solar system 1。

 but theres server system 2 with slightly mo API。 You want this to continue to work。😊，And also。

 another core aspect in particular， in the human interactions。

 I think it's also being surfaced again and again is that agents are expected to work under weekly specified instructions。

😊，So in the very early days of agent systems， when people are designing evaluation。

 it's always like the user would have a very clear target。 The user would say， please conduct this。

 Then you see that I am behaves very intelligently is really to able to decompose the problem。

 execute the task， calling the APIs in the right way。 But later， in reality。

 people really found in the wild when people started to interact with those agents。

 They have absolutely no idea they want what they want to do。 So basically ask random questions。

 They are actually hoping the agent who tell them what they should do in order to accomplish this task。

 So in some sense really means that you need very smart system。

 The system should be able to understand human intentions。 by proactively talking to people。

 but also at the same time， produce very precisely formatted outputs so that they can actually interact with very rigid rigid formatted the software systems。

😊，So number four， agents as they expect to work under many different software systems。 for example。

 you use cursor in programming。 I build the system for cursor works very well。

 Suddenly you change to another system。 I use the exact thing am completely breaks。

 It's definitely not ideal And if that really happens that also brings people to question。

 the quality and intelligence of of your large language model because maybe it just simply isn't smart enough to understand those changes。

 This generally would be very problematic。 the fifth one is very generic I call here is expected to be robust It's really because there are so many things could actually go wrong in interaction with humans and with systems。

 human beings may not really know what they want and the system could also sometimes produce the issues。

 you want to make sure that I am really behaves as a really smart person just like high quality。😊。

And here's。To be able to debug all different issues that emerge in our daily life。



![](img/e87f9e6f09420326af124f5290d73632_67.png)

So the slide will also be made available online here。

 I just want to give you some more concrete examples of what people have already done in the past。😊。

So those benchmarks they they do map to the specific requirements we have been talking about here。

 for example，1，2 is about different tools and different use cases。 So on the left。

 I'm showing the offsshall benchmarks， which actually cover many different use cases。

 many different tools。 and theres also number four on the different server systems。

 So here I'm I'm talking about different agent harnesses， which have will also described in detail。

 And number 3，5 here is focusing on unit test evaluations Check robustness of the of the outputs。😊。



![](img/e87f9e6f09420326af124f5290d73632_69.png)

![](img/e87f9e6f09420326af124f5290d73632_70.png)

Okay， so maybe I've start from the left。 So in the past a couple of years。

 the community has developed some really significant benchmarks。

 trying to push the intelligence IMs higher and higher。 The benchmark is getting harder and harder。

 generally people have achieved tremendous progress and indeed， for our observations。

 certain tasks that in the past were believed to be very hard for IMs。

 is they can actually solve them。 turns out they really produce a very significant productivity。

 I'm talking about a couple of them， for example， a sweet bench。

 really it's really challenging the IMs to really solve this very， very sophisticated Github issues。

 many times really needs to involve so many different tools to solve these issues。

 And also through solving sweet bench， also many people understand that you actually supposed to be interacting with different harnesses。

😊，I want to really emphasize this because there's very complex like you have issue into solve。

 But to solve it， many people actually operating in different environments。 For example。

 in one environment， maybe you have a function called open this file。

 You can you are supposed to just call this function to open the file。 Maybe in another environment。

 You do， you do not have this function。 You have some other command line tools。

 You call to actually accomplish the same task。😊，So the whole point is that in order to check your capability in solving Swve。

 you're actually not supposed to be only sticking to a particular harness。

 You're supposed to be trying so many different ones。 showing that for this particular task。

 Maybe wna give you this set of different tools。 another set of different tools。

 slightly different formula tools。 are you able to solve it in all circumstances。 If you can。

 It really means that your intelligence has already achieved certain threshold。😊。

That's actually a extremely important point。 They are also have different other benchmarks like Tao Bennch。

 BFCL， also from Berkeley， a complex function bench covering a very wide variety of different tools。

 different application scenarios， just to make sure that you do not overfi to a particular application。

😊，And there are also different unit test evaluations for some of those actually could be would be the focus of many community members from a long time ago。

 saying that I want to check the structured output adherence， which means that maybe in many cases。

 I wanted to produce Json output。 I really want to make sure it is really exactly right Json。

 So I want to make sure you do not really need to later write a very complex software engineering code to correct the mistakes produced by Is。

 there has been lots of attempts in the past to produce such software engineering tools somehow to reduce the burden on Is。

 but later essentially what everybody observed that if the IM itself is not intelligent enough is not able to produce very high quality Json or structured outputs it becomes essentially impossible for anyone to fix the issues later。

 because lots of issues really involve very nuanced understanding。😊，System。

 it really requires a system with very high level intelligence。 So basically。

 you cannot easily fixes using very simple rules。

![](img/e87f9e6f09420326af124f5290d73632_72.png)

So one point to summarize what they talk about， which is the holistic environments。

 We want to make sure we check all kinds of capabilities humanities last exam general scientific knowledge。

 a and math， sweep bench coding， it's supposed to be combined with different harnesses and I want to make sure that we really create a super strong。

 super intelligent model that's able to solve all of these tasks under all kinds of combinations of evaluations to convince ourselves that indeed we have made progress in terms of enhancements of intelligence So keeping the definition of intelligence holistic。

 is extremely important because these days we are trying to utilize the systems to increase our productivity and one thing has come up again the game is that the system we are dealing with in practice as a scientists。

 as engineer， as a researcher。😊，It's just so complicated。

 So in order to make sure the system M can actually help us， we want to make sure it is smart enough。

😊。

![](img/e87f9e6f09420326af124f5290d73632_74.png)

Okay， so to continue what we talk about good evaluations。 need to count for all of these things。

 evaluate how many different tasks and verifiers， many different ways of letting an agent explorer in benchmark sandbox by seeing how the accuracy changes as you swap out the harnesses。

 you make sure that if you see sometimes a very significant performance job。

 maybe means they would do something wrong in the in training。

 Then you need to figure out new ways of training to to fix this。

 you also need to deal with many different tools， how to use different tools in different action space。

 ideally， you really stick to the same model。 So that model needs to itself， figure out what to do。😊。

So in summary， evaluation is extremely important。 Lots of people here are also working on very significant topics in evaluation。

 It is definitely something we need to help from， from the whole community on。

 because only by collectively working on this Can we really understand the limitations of existing agency system and make progress。

😊。

![](img/e87f9e6f09420326af124f5290d73632_76.png)

So it really needs to be holistic and good measure。

One last thing I want to talk about before we go into the training aspect is actually also about maybe approaches to combine different tasks and harnesses to evaluate。

😊，So basically， say you have already come up with lots of different evaluations。 right。

 F I checking the quality of math， quality of codes， swapping the harnesses。

 making sure things are actually good。 Well， then you you saw some good numbers。 So are you。

 are you still really sure that you didn't really overfi all these benchmarks。

 because maybe in this process of iterating on your post training。😊，You have collection data。

 which is really similar to some of the data you in， or in the whole community。

 maybe certain models have already been contaminated。

 Maybe certain evaluations should no longer really work。 Are you really sure it's not happening。

 When you see a high number on certain benchmarks say on Swben。

 Are you really sure you are exactly very strong。😊。



![](img/e87f9e6f09420326af124f5290d73632_78.png)

So I would to emphasize that there's also a very important community efforts to continuously train to check the quality of evaluations。

 which is also important aspects of research。 So basically several aspects。

 one could consider one thing is about harness。 So basically suppose and very early days。

 maybe I are not intelligent enough。 there will be a certain benchmarks。

 maybe all the Is would score very low on this benchmarks。 but maybe these days。

 for example like GSM8k。 Everyone scores very high on this benchmark。

 Now you say well I achieved five point improvement on this benchmark。

 It's really unclear you have actually made some progress。

 because there's also maybe likely for the specific base model you work on。

 the model has already been exposed to certain data that's very similar to a GSM8k evaluation。

 you really do not know what's going on。 you need to continuously the monitor harnessness。

 you also need to continuously the monitor separability。 by。😊，I mean， that's when you ask a question。

They ask many different ads， the same question。Ideally。

 you are supposed to see that I am that's supposed to be stronger。 They answer the question better。

 The I thats supposed to be weaker。 They they do not answer as well。😊，In that case。

 we would like to say that the benchmark is able to separate the capabilities of ours。

 because if that does really happen， or you observe that while the weak armss and strong armss they produce very similar scores。

 Maybe the reaction should be that you abandon this benchmark。

 because there must be something that has has gone wrong in in the past。

 either in training or in some other types of evaluation that has maybe has hurt the credibility of this particular benchmark。

😊，There's also， of course， issue of diversity， which is also the the topic we have been talking about again and again。

 which is that you need to have very good coverage。 So if you do not have very good coverage， you。

 you produce high number， maybe on data sets， you only have like 50 different prompts。

 They are very similar to each other。 you produce a high score doesn't really mean that your system actually is be very well。

 So all these are very important topics。 and these really a very significant community effort to make sure that we do not fall into the pitfalls。

😊，So many benchmarks are really public。 So all the data is available are there attempts people have to create the private benchmarks to really track the progress。

 clearly they are。 So actually lots of individuals， community members and companies。

 they would like to create the private benchmarks to really check that。 So in some sense。

 maybe they the situation， everyone wants to see would be that we need to see way more benchmarks being proposed。

 because private benchmark is good， but if you have a very static benchmark then people try to fit it so many times。

 maybe still would lose credibility。😊，And ideally， let's say for public benchmarks。

 if the community can continue to produce more and more benchmarks in all kinds of different environments。

 then it's actually very hard for everyone to over feeded to all of them。😊。

Then there was a saying that， well， suppose you have only five benchmark in the world。

 you have a benchmark max them。 So basically， you claim your model is really the best on the five。😊。

Maybe it may not really work on all other benchmarks。

 But if the community has collectively produced 1 billion benchmarks， right。

 covering essentially everything we do in reality， math coding， computer use， whatever。

 then say that someone comes I say that I have an overfis to all be1 billion benchmarks。😊。

Then maybe you have already achieved AI because they they really have already covered everything that you care about。

 So in some sense， benchmarking efforts is really a very strong community effort。

 So we really would only be able to succeed where more and more people are producing very high quality benchmarks covering their use cases。

 So that's actually also an aspect I personally feel that academia can really make a very strong contribution to because。

😊。

![](img/e87f9e6f09420326af124f5290d73632_80.png)

There are many people working on so many different topics。

 So trying to really capture what is exactly missing in the existing training of the agent systems。😊。

Great， and then we'll be talking about the third part， training while。



![](img/e87f9e6f09420326af124f5290d73632_82.png)

What does the training agent mean， So training is a very complex topic。 These days。

 we still have new algorithms coming up every day。 But generally。

 I want to talk about the principle of training。So in terms of training。

 you want the agent Is to attempt different actions in your specific environment and see what gets it to the final answer the best。

😊，Whichever gets you the best results， you want the model to reinforce and repeat。😡。

So here I'm talking about this paradigm。See that on the left， theres agent I M。

 which is supposed to be smart。 Okay， you got training the agent I M。

 So you give the agent I a certain task。 You say， well， please complete certain task。 Try to do it。

 Then I would make lots of attempts。 attempt here I'm showing  one to 5。😊，Go to environments。

 maybe in each attempts， it tries to call different tools， try to chew different information。

 try to make a final decision。 Now finally iss a verifier saying， oh。

 for each attempt is correct or not correct。 How much cost has it incurred。😊，Then ideally。

 even without demonstrating how we choose this， we already't know the the target。

 The target would be that I want to make sure at the very end after training。

 the M is able to generate the correct trajectory。 So the attempt is successful。

 Maybe ideally also with the minimal costs。 and there could also be other aspects I care about in final evaluation。

😊，So what， what are some aspect some core characteristics you you focus on in the whole training process。

 I'm talking about two here。 There could be many others。

 One thing I want emphasize that you want each attempt to be very different from each other。

Since you want the model to reinforce or discourage many different styles of attempts。

 just like a human being， right， Suppose I want to teach a kid to do something。Then ideally。

 if the person is able to come up with multiple different approaches。

 they are very different from each other。😊，Then ideally， some of them is correct。

 Some of them is incorrect。 after I give very detailed feedback。😊。

I hope the person can learn very fast。 But the issue is that if the person is only able to come up with a single answer and it's wrong。

Then by telling the person it is wrong， it did give some information。

 then it really appeared that slightly harder actually for the training algorithm to work App that you didn't provide enough amount of information。

 I this， for many algorithms to be able to improve the quality of agency systems。😊。

And a second aspect I also want to emphasize is that every attempt would cause compute to sample and process。

 You ask I am as a person to say， oh， what about you， try this。 They tried it。

 and it's totally wrong。 You ask， try 100 times。 All of them are totally wrong。

 that wouldn't be very satisfactory because each attempt cost lots of money， lots of resources。

 you do not want very silly attempts。 So somehow we are really in a delicate situation。

 So if we give I am a question。 It's super easy。 All the attempts are exactly correct。

 It didn't learn anything。😊，But ask to attempt many times with all failures cost lots of money resources。

 And you also need to spend lots of time figuring out how to make an learn。

 So it it's a really complicated process till today。

 the whole community is still trying to figure out what's the right way to deal with this。

 But I think that by connecting this better with the human learning process。

 It did raise lots of really fascinating questions about that。😊。



![](img/e87f9e6f09420326af124f5290d73632_84.png)

So。We have to talk about some of the existing approaches taken by the community。

 And I really want to emphasize that the existing approaches may not really represent the best approaches one can take。

 So lots of research to be done in in general， also from from a certain point of view if we。

 we really go back to machine learning theory， certain approaches being proposed here。

 I also not exactly right。 So one big issue we are dealing with in trainings is that the theoretical foundation usually cannot connect very well with existing practices。

 So it's really I believe the task of whole community to come together to figure out how we can propose better formulations。

 But to connect what I talk about before。😊，There generally would be two stages in training the agent systems。

 The first stage we call a super fun tuning or SFT。So it is basic imitation learning。

 I would about to imitate demonstration trajectories that achieve correctness。

 What that really means is that suppose at very beginning， the an doesn't know anything。😊。

You'll give the I am a task。 A to out with some garbage。

That's exactly what the situation we talk about of the silly attempts that cost lots of money and resources。

 We didn't make any progress。 In that case， usually to jumpstar the whole system。

 what you would do is that you would to connect some demonstration trajectories。 You say， well。

 there's a particular query。 I wanted to show you as a human being。

 the right set of actions you need to take Maybe access this database。

 Also access another API talk to another system， final this whole trajectory。

 I show you that what about you try to replicate this。 Next time I ask you exactly the same question。

 What about you try to produce exactly the same answer as the demonstration I've just shown to you。😊。

So the hope is that I want to minimize any silly or not no meaningful attempts。

The second stage is that well， maybe you are already entered the stage where I give you a question。

 sometimes still make mistakes， but is they are not totally wrong。

 At sometimes you are reasonably correct。In this case， I would like to let you explore。

 because the more you explore by yourself， the better you learn， in some sense。

 very similar to the philosophy of human learning。 say in school。

 if the professor only gives us the precise answer to the question。 So you just copies this。

 We are not allowed to produce any homework to be graded by the professor and we don't get any feedback。

😊，Then maybe different people who make mistakes in different ways。 right。

 I have this particular type of mistake。 I want to know it is wrong。

 Nobody gave me that because professorfess only gave me the exact right answer。

 There's new question coming up。 I have no idea that I actually tend to make certain type of mistakes。

So the real way to learn is to let model explore and reinforce trajectories to achieve correctness and discourage the ones that do not。

 going back to the previous point， you actually also want the model to produce very diverse trajectories so that if you go wrong。

 I want to see you go wrong。 Then I tell you， it goes wrong。 Instead of you say， well， essentially。

 everything is correct。 But they are always the same。

 Then you didn't really learn too much about this。 You want to reinforce diverse。

 great attempts from the current model and discourage diverse and bad attempts。

 Both sides maybe need to be diverse because diversity really accelerates learning process。😊。



![](img/e87f9e6f09420326af124f5290d73632_86.png)

So to really talk about the details SFT stage and R stage。

 I personally feel it's very intuitive because the math really well to human being learning。

 at SF stage is basically maximum likelihood of sampling the demonstration trajectories and minimize likelihood of sampling anything else。

 give you the particular trajectory。 say what about your samples。

 hopefully it really works very well。 It just here so that we can sample meaningful trajectories。

 So one key aspect of SFT is that demonstration samples needs to be diverse。 So basically。

 if you give me very few SF samples， very similar style。

 then maybe what has happened is that the model is not able to generate diverse attempts later in R stage。

 which is bad。 and similarly for the second requirements。😊，Here。

 I wrote a requirement which is SF should be light。

 The intuition is also exactly the same because if you have conducted very heavy SFT。

 which means that you have basically tried to teach the model for every question I collected in training set。

 I tell you what is the right answer。 And I tell you， please remember this。

 it is exactly only right answer。 And later， the model will lose the ability to figure answers by its own。

 And in reality， the real issue is that no matter how big the collection of your training data is。

 It can never cover every aspect of of our interaction withs。 and these humans。

 So if you really only teach the to exactly follow your demonstration answers。

 generally it would really fail for task that have actually auto auto distribution。😊。

So in the RL stage， so here I'm talking about the technical details。

 you can find the details in essentially every paper in RL in the raw the stage。

 I want to sample very meaningful but very different actions for the tasks。

 the environment and tools， you have limited the compute。

 you want to make sure you get as diverse answers as possible as meaningful as possible。

 then you figure out how correct each each action sequences， how real and useful certain actions are。

 then you try to figure out how to update who I am so that the next time when you try to generate answers。

 you generate more the correct answers， you generate less the incorrect answers。

 that appears to be the hardest parts。 So in some sense。

 it's also similar to what we observe in human learning。

 which is that when the professor give the students a task， then everyone submits the homework。

 the hardest thing is really to make sure that the next time。😊，When theres a new task coming up。

 everyone is asked to submit homework again。 how to make sure that you really have produced a better answer。

 So generally， for human beings， people actually differ in in this way。

 So many people by giving me the same feedback。 actually， they produce many different answers。

 once given a new set of tasks。 That's exact the same situation for our algorithms。

 use different our algorithms give you same amount of data。

 Then later turns out the quality of the system actually is different。😊。



![](img/e87f9e6f09420326af124f5290d73632_88.png)

Summarize I I teach here to discourage minimalless and low quality rollouts。

Atts andarrows here to truly reinforce intelligence。



![](img/e87f9e6f09420326af124f5290d73632_90.png)

So I indeed have prepared some more slides talking about details on RL。

 because I do believe that it's a very critical research topic。

 The question that has been a certain work actually also work from coming from media talking about maybe in certain cases。

 one can remove the SF stage。 We conduct more RL。 By the way。

 it's also a trend demonstrated by many frontier labs。 Con more computes。😊。

So that I can also go back close back to one of the core things I talk about when we are talk about training algorithms is that this thing is。

 is really unclear what is actually the correct training algorithm。😊，So because in some sense。

 for those of you who are very familiar with the machine learning theory。😊。

You know that the current algorithm formulation， fixed combination， SAT T and RL。

 They actually do not align very well with machine theory。😊。

If you started from a theoretical perspective working on simplifyified models。

 you wouldn't be doing this。Youll be doing something else and simpleified models。

 something else work so much better than these approaches we currently take ons。

 So that's a very big issue。 So that's why we believe that more exploration in terms of different architecture。

 different algorithms better with utilizing data， both pre traininging and training data is' very critical in a community。

 because currently it would be very nice if we can move closer to the theoretical principles。

 while doing something that's implementable in practice。

 these are actually currently really important research topic So I personally would encourage everyone to really dive very deep into this because I believe we definitely have not converged in terms of what's the right algorithm to use as you be you see when I talk about later certain issues related to the。

😊，reasons I by no means mean that those are the maybe the really right approaches we follow。

 that they will continue to be right， even 10 years from now。

 But maybe the my purpose is really to show you certain observations people have made in the past in running certain algorithms hopefully it can motivate you to design new algorithms that's actually work better。

😊，Maybe one perspective I could be considered as like pattern matching。

 then you want to train the system to be。Able to conduct critical thinking and also be able to implement something new。

😊，First of all， my feeling that it's it's generally very difficult to understand what exactly I is doing。

😊，Because when you really think about how do human beings learn。In many cases。

 suppose when we are actually trying to solve exam questions， right， we are attending a class。

 we are also doing pattern matching。😊，Right we went in school prepare show that one problem。

 And there answer that here has the next problem very similar。 we also doing very similar things。

 So me personally， I feel that it will be fascinating to combine everything related to human learning with I learning。

 which is exactly what's the way Ire trying to show here。

 So we have got some good inition with human learning， we figure out how humans can learn better。

 But the issue is that many humans have no idea how the actor learn。😊，Right， they did something。

 They got some feedback。 Next time， they did something else。But here。

 we need to write on the algorithm。That's actually the hardest thing。

 We have no idea how to write an algorithm。And in terms of human learning。

 there are so many things we want to learn。 And there are so many ways to evaluate a person。Right。

 just like these days， students take exams from all courses， right。

 Are we really sure all the exams are really fair。 They evaluate person the students in the right way。

 is super interesting， So one point I'm trying to make here is that it's a so fascinating area to think about we actually absolutely at the infancy of the area。

 We really haven't figured out what's the right way to train those systems。

 and also deploy them in certain other critical applications。

 but we have made interesting observations， which is what I'm trying to show here。

 Hopefully the observations are insightful and can stimulate some of the research the people do in people in this course can actually do in the future。

😊，Okay， so now then let's dive slightly deeper into reinforcement learning。

 I want to talk about three four aspects。 I believe that we still to do a lot more research around those aspects。

 potentially new aspects。 But the community has made interesting observations。

 I want to share the observations here。😊，One idea is to train for longer。

So one intuition you do hit situation you do want hit is that you got some datas。

 you get to attempt to solve the problems。 You attempt once or twice。 Then later。

 you found that it can no longer attempt。 So every time it makes attempt produces exact the same answers。

 sattuates okay， not able to train longer。 not ideal。 because for human beings。

 we really get constant feedback。 We given a task， we propose a solution。

 we get feedback next time we propose a better solution， ideal later。

 we come up with really amazing maybe answers， maybe inventing something really new。

 conducting cutting and research， inventing general theory of relativity。

 Right there's a very high part here。 but not be very good。 You say that it plateaus like very。

 very quickly。😊，The second aspect observation people have made is that somehow you need to train on more difficult prompt tasks。

So intuitive also makes sense， says as for a human， supposeupp you are given a task to learn。

 You're only given really simple tasks。 You already know how to solve it， really， really well。

 You didn't really learn anything new。That's for arms，'s also exactly the same。

 But we did talk about some of the intricacy related to this。

 because if the I M is only given really difficult tasks like solving a Ri hypothesis。😊。

Nobody can really solve and nobody can make any progress。

 So that's actually also a very big challenge。 Turns out it's important to convert the intuition we have in human learning to I learning。

😊，Which is also very big ongoing research project。 I've been talking about some observations people have made。

 The third aspect I want to emphasize is to train on more diverse responses with high quality reward feedback。

 So which is very natural as for a human。 if you only interact with very limited subject。

 For example， you only study a single subject， only take one course。

 And you certainly would not be able to answer the questions in in the exams of other courses。

 you need to do that。 see many different meaningful answers per prompt as as many answers as possible。

😊，So it the good our algorithm should rely on those pillars and add even more pillars in practice。😊。



![](img/e87f9e6f09420326af124f5290d73632_92.png)

So I will very briefly talk about those pillars。 One pillar we talk about is train longer。

 being able to train longer。😊，So there has been many observations in the community talking about the this entropy mechanism or entropy collapse collapse mechanism。

😊，And actually， many different papers have also very many other correlated metrics capturing something similar。

 But idea is the following。 So on the left， I'm showing you a plot。

 X X is the number of training steps， Basically you training longer or longer。

 What X is showing performance skin。 So basically， how much the has actually improved。😊，So and yeah。

 I'm also it' showing this wax wax I have two curves。 One is showing performance skin。

 The other is showing entropy left。 by entropy， actually means that when I is trying to generate its next token as being specified in literature is probabilistic inference because next token is sampled from a distribution right。

 So by entropy， I means that I basic compute the entropy of the token generation probability by large entropy。

 it means that there will be high uncertainty in sampling the next token。😊。

Then if we have a high entropy， then very likely if you sample the trajectory toys。

 you'll be able to get two very， very different trajectories。😊，If the en is very low。

 think of the situation that whenever you are given a prompt。

 then you ask model to predict next token， that model is always super sure next predict token is certain token with 99% the probability。

 Then even if you run this I， you sample it so many different times。

 you wouldn't be able to sample many different trajectories because only a single trajectory。😊。

Has has very， very high probability。So what this plot has shown that if you do not intervene。

If you follow many different algorithms， what's going happen that as the number of steps increases。

 the performance would gain indeed you see in terms of reward。

 the model started to produce very high quality answers entropy started to decrease so basically later only learned that I'm able to only produce one answer。

😊，So then we ask a question。 Is it really possible that we produce。

 we still produce really high quality answers， but at the same time。

 do not achieve this entropy collapse。 So later， answers is all correct。

 still diverse being able to explore but ideally， for every question。

 I'm able to come up with five different correct answers。

 that's so fascinating because even even for human exactly very hard for very hard task come up with five different correct answers。

😊。

![](img/e87f9e6f09420326af124f5290d73632_94.png)

So there has been some observations in literature here。

 I talk about two approaches people have taken in the literature to alleviate this issue on the left。

 I'm talking about this on policy versus our policy issue。😊，Okay， so。Basically。

 I'm I increased number of training steps。 Then I observe that in terms of training rewards。

 which is the leftmost figure。 I observe that for。Either on policy or our policy algorithms and the rewards actually increase in a similar manner。

 which means that I do get a better and better policy。But precisely by on policy。

 I want to emphasize that it's really exactly emphasize refers to the setting that。

Whenever I ask the reward model or a verifier to judge the quality of the attempts。

 I only judge attempts produced by the I itself。😊，So it is called on policy。

 which means that I do not try to give you rewards or feedback based on the answers produced by other Is or produced by different ways。

 I really want to give you feedback produced by you at this point。

 so that you can really learn the best。 So on policy really means that I want you to learn from your current mistakes。

 not the answer produced by other people。 intuitivetuly from the perspective of human learning。

 If the answer is produced by the students then we。

 the professor give the students very detailed feedback， the student can really learn the most。

 But if the student didn't write on the answers themselves。 copy it from somewhere else。

 you give feedback， maybe the student can still try to learn but may not learn as well。

 So that's actually intuition we are trying to borrow here。😊，Showing that if you use on policy。

 the care divergence between the policy you train to the original initial policy is small。

 and also the entropy still stays high。There's another Yes。

 so basically that that is a very detailed description showing that on different benchmark benchmarks thats like math 500。

 Amy 224，2025 on policy generally produces much better answers。😊。



![](img/e87f9e6f09420326af124f5290d73632_96.png)

![](img/e87f9e6f09420326af124f5290d73632_97.png)

The second approach， which we call balanced the ugly strength called adjusting the clipping threshold or encouraging exploration。

 So we are getting a very technical here。 Maybe I I wouldn't be spending too much time here。

 It is from the paper。 double。Maybe is a specific variant of GRPO。

 the precise formulation given here。 So intuitive， this R ITta is basically the likelihood ratio we use in training。

 then generally to make GRPO stable。 We need to clipping to this likelihood ratio is supposed to be fluctuating around one you clip at below1 minus epsil low clip at above1 plus epsilon high。

 one important observation made by the paper is that you need to decouple those to epsilon。

 make epsilon high， even higher， bigger than epsil low。

 So basically idea that you would to encourage the model to increase the probability assigned to low probability tokens So the model is able to explore very well。

 as you probably can see here we are talking about lots of hacks in the whole system。

 So that's reason why I want to really emphasize that different hacks may not really represent the。😊。

state of arts in particular， many years later。 But I hope the insights conveyed by the hack。

 exactly that you said if this is motivated by PPO。 indeed， PO also had this clipping approach。

 heres the the core observations that you actually wanted to decouple this clipping thresholds。😊。

So somehow， indeed， strikes some people as a as a hack does perform quite well in particular。

 based on the the picture I show here with the clip higher， you see on the purple line。

 generally for the performance， it gets higher。 And in terms of generation entropy is also。

 is' also high。 doesnn't really collapse。😊。

![](img/e87f9e6f09420326af124f5290d73632_99.png)

Okay， another aspect people have actually considered in the past in terms of train longer is actually to add a loss to encourage entropy directly。

 because we have been talking about this entropy collapse issue when you train longer。

 The model only learns to produce one answer is not ideal。 Then naturally。

 you could also add a loss function。 You say that what about I try to maintain the entropy at certain level。

 then there also load of different tricks in constructing the loss。

 make sure that entropy always stays high。 For example， you have a certain entropy level。

 You want to make sure that the loss。 steers the generation entropy to the particular level of the entropy。

😊，There are many things you can do。 Still lots of explorations that's necessary。

 but I hope that the intuition is actually is clear。😊。



![](img/e87f9e6f09420326af124f5290d73632_101.png)

So precisely to encourage entropy directly， following this paper， Skywork or open reasoner。

 what they have done is that they have a particular like entropy loss。

 So the loss would actually encourage you to increase entropy along training so that entropy doesn't really collapse and hopefully you also achieve a higher test accuracy as being shown on the picture on the left。

😊。

![](img/e87f9e6f09420326af124f5290d73632_103.png)

Okay， so that's one aspect of train longer。 There's also another aspect of。

Ting on more difficult prompts and tasks。So in the same antroic mechanism paper， actually。

 along with many different papers in the community。

 people have been thinking about how to actually capture the aspects of of separating the models performance on hard prompts and on a simpler prompts。

 So they have a quite interesting plot here。😊，So basically on the left and we。

 we'll be talking about what exactly way we are plot in terms of it coers， so。

The intuition is that I want to track something which is related to the correlation between the generation likelihoods of。

Of the sequence with the sequence quality or the advantage。 So basically。

 I would like to use this covariance between low probability of the whole sequence to the advantage reuse in reverse learning we getting selective technique here。

 But without look at too much details is basically trying to figure out whether I'm able to align the confidence of generating certain high quality answers with the with the final performance。

 Ideally， what's supposed to happen is that the model is supposed to be very confident in generating the right answers。

😊，It's supposed to be quite uncertain in generating the wrong answers。

 it would be fantastic because next time I prompt the one model。

 the model is more likely to generate the right answer， because it's more confident。😊。

So on the right， I'm showing a picture basically listing the training curves of subsets of data sets corresponding to the different levels of accuracy。

 So basically one can see that for the curves corresponding to very low accuracy。

 which is purple curve， accuracy 0。1。11125。 You see that dis correlation。 stay very low。

 It really means that the model is not able to very confidently generate the right answers。

 So for the model for the question that's actually very easy you've able to see generate the correlations higher。

 So that's actually also important metric。 we are trying to track。 And on the left。

 I have another figure， which is also very interesting observation made by people in the past。

 it's really about how you actually construct interesting training sets。😊。



![](img/e87f9e6f09420326af124f5290d73632_105.png)

So what this one is is been has been showing the following。

 So I would like to train on multiple different training sets。 I'm。

 I'm showing a couple of data sets， double math， GSM 8 K。

 yours error data your error difficult are difficult is more difficult data set。 And on the right。

 I'm basically checking the validation accuracy on exactly the same validation sets。

 I'm trying to see by training a different data sets what is the final validation accuracy what's the pattern of evolution。

😊，And the paper did observe something very interesting。 For example。

 GSM8K actually refers to the curve at ver bottom。 So what that process shows that while when we are able to train is we we found different data points corresponding to different entropy。

 one trend or clearly when the entropy is higher， the final performance is better。

 which is which is a very good trend， But the second thing。

 one wants to see that if you only train on GSM8 K。

 it really appears as your final validation accuracy is low。 In some sense。

 is really because GSM 8 K is too easy。 your train is too easy data set。

 you shouldn't really expect model to be here very well on some very challenging tasks。😊。

But another really interesting observation you can make is thats the users are data and your are data difficult。

 Then looking at the curve actually the users are data difficult。 also is。

 is below the curve of yours I data。😊。

![](img/e87f9e6f09420326af124f5290d73632_107.png)

And U error data contains the difficult data set， also contains something that's actually not that difficult。

So somehow it also shows something about the current learning paradigm。

 which is that you basically bluntly throw in super hard prompts。

 You say that while I really hope you're able to learn， I give very good feedback。

 hopefully you'll be able to solve it。 Unfortunately， the I itself。

 order exist algorithms and not smart enough to really capture this。

 It did really learn how to actually do very well。 So somehow you need to somehow combine very well。

😊，Different types of data really make sure it can learn very well。

 So many different approaches have been proposed in the past here。

 I'm talking about one approach proposing a GRP orD paper。

 which is very intuitive still strikes some people as hacks。

 but I think the intuition is interesting has many intuitions when intuition was basically saying that while maybe in order to provide a signal to the Is。

 suppose it is very hard prompt and you got it right。

 I'm supposed to reward you even more because it's supposed to be very hard。

 it is very simple prompt， you got it right， maybe it should be rewarding rewarding you that much because it' simple you're supposed to have already captured this。

😊。

![](img/e87f9e6f09420326af124f5290d73632_109.png)

And there are many aspects captured by the paper。 For example， there's one answer。

 You got this question correct， but unfortunately， you produced a answer that too long。

 I also would like to penalize you because you are supposed to give a very simple answer。

 The question isn't， isn't that hard。😊，Of course， also， if you give something wrong。

 I also give you really negative answer really negative feedback。 So many things we can do。

 So in the paper， it did show that it has many different approaches to actually adjust the corresponding reward。

 one can see that if you really adjust the the weight for different samples。

 corresponding to advantage or corresponding difficulty then performance gets improved。

 explicitly penalized and very long generations。 Many others， Then the quality also becomes better。

 So could really give rise to lots of interesting ideas。😊。



![](img/e87f9e6f09420326af124f5290d73632_111.png)

![](img/e87f9e6f09420326af124f5290d73632_112.png)

Okay， so that's on the on the harder prompt side。 very clearly。

 you can see that this problem is open。 It's really not clear in the community that people have figured out the right approach。

 ultimate approach in solving this。 There's the one last aspect I want to emphasize。

 which is called sample better。😊，That also appears to be a very important aspect of our algorithm。

 The whole idea is that you should sample better so we can train on more diverse responses with high quality rewards goes back to original intuition。

 If you're not able to sample lots of diverse queries answers with with high quality。😊。

Then then you'll be in trouble。So two things I want to talk about on the left。

 I talk about so- calledled parallel reasoning。Ideas could be very simple。

 There are so many variant of this approach。 I'm talking about this paper calledlet idea is that well。

 so I actually do have this slide here。 So basically when you finally ask I to produce answer。

 You say that what about you to not just directly give me answer。

 always give you a very complex prompt on the right。

 maybe ask you to come up with like 32 different answers right they do different answers then give prompt。

 I say that what about you basically select one of the answers from the 32 then ideally here as you can see from the answers generally it the final accuracy becomes so much better because I really is given more time to figure out。

😊。

![](img/e87f9e6f09420326af124f5290d73632_114.png)

![](img/e87f9e6f09420326af124f5290d73632_115.png)

That the right answer。 I is able to pick the better one。

 Another one I want to talk about is another recent paper called promotion algorithm called deep conf。

 So that intuition is also about improving majority voting。

 So the point is that say without this quite sophisticated sampling method。

 say you want to sample I am like 32 times to produce an answer。 You just give the same prompt。

 try32 times， get answer， conduct final majority voting。

 But one potential issue is that among the 32 times of sampling。

 maybe certain trajectories of very low quality。 Maybe you should just know at very beginning or very early on。

 that tra is wrong。 If you knew this， you actually not supposed to include that in final majority voting。

 You are supposed to only include those trajectories thats that that's actually likely。😊。

become part of the right answer。So the idea of deepcom is to say that I would like to track the generation confidence of its trajectories for those trajectories with very low generation confidence。

 I just believe that model isn't even sure what it's doing when the model isn't even sure what it's doing。

 I basically would not include the model or very low weight in the final majority of voting so that it should be able to produce a better answer。

 So the right。 I I'm showing some of the results For example， on the on the same model。

 G S S 120 B if you use the deep con compared to the consensus。

 which is basically majority of voting is actually improves。😊，Because indeed。

 you are able to discard some of the bad outputs of the model。😊。



![](img/e87f9e6f09420326af124f5290d73632_117.png)

So that's essentially what I wanted to talk about。 Let me summarize the， the all the。

The content putting everything together in the SFT data。

 you need to have very good expert demonstrations。 R every recipe。 you need to focus on train longer。

 simple better， train harder。 and ideally， what community is supposed to be doing is really to solve everything as a whole。

 You want to have a collection where have accurateate environments and verifiers。

 give up intelligence。 You need to figure out the best definition what intelligence it is。

 you need to be able to be to release algorithm to train longer。

 harder problems with diverse responses。 you want to cross sources。

 community with all the community efforts。 You also to make sure analyze the strength and weaknesses or benchmarks。

 including in the collection， everyone I use it and also release good algorithms for everybody to experiment on。

😊。

![](img/e87f9e6f09420326af124f5290d73632_119.png)

![](img/e87f9e6f09420326af124f5290d73632_120.png)

![](img/e87f9e6f09420326af124f5290d73632_121.png)

![](img/e87f9e6f09420326af124f5290d73632_122.png)

![](img/e87f9e6f09420326af124f5290d73632_123.png)

![](img/e87f9e6f09420326af124f5290d73632_124.png)

It's gonna to be my final final slide。 hopefully after today's lecture。

 we have shared some interesting observations we have made。

 but my real hope is that we have a stimulate your interest in this area。

 because one thing I really want to emphasize is that this area is still very immature。

 Lots of things we really haven't figure out and the general perspective we have is that we really want to bridge the gap between human learning and system learning。

 humans engage in many different environments， focus on some lessons more than others。

 we can explore ourselves or learn from teachers。 we often evaluate for our intelligence on different tasks。

 how do we exactly do that fors。😊，In many cases，s really unclear。

 So we really have to like to encourage convention efforts to join us in this whole effort。😊。

To collectively produce the strongest agent intelligence。



![](img/e87f9e6f09420326af124f5290d73632_126.png)

Thank you。