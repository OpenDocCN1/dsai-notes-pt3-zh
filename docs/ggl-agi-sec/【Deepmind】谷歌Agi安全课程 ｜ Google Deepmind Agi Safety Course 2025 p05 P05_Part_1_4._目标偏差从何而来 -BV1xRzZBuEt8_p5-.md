# 【Deepmind】谷歌Agi安全课程 ｜ Google Deepmind Agi Safety Course 2025 p05 P05_Part_1_4._目标偏差从何而来 -BV1xRzZBuEt8_p5-

![](img/14ba9a14ea0d862252ca59df8cfd53d8_0.png)

![](img/14ba9a14ea0d862252ca59df8cfd53d8_1.png)

Hi， everyone。In this talk， we will explore where misaligned goals can come from here。

 I find it helpful to consider different levels of specification of the AI system's objective。 First。

 we have the ideal specification， which represents the wishesoeuches of the designer。

 What they have in mind when they build the AI system。



![](img/14ba9a14ea0d862252ca59df8cfd53d8_3.png)

Then we have the design specification， which is the objective we actually implement for the AI system。

 For example， a reward function or a loss function。Finally。

 the revealed specification is the objective that we can infer from the system's behavior。

For example， goals that it actually seems to pursue in practice。

If the revealed specification matches the ideal specification。

 then you have an AI system that is behaving in accordance with your wishes。 I。e。

 is actually doing what you want it to do。 So for give an ideal specification。

 the goal of AI alignment is to ensure that the revealed specification matches that。And to do this。

 we want to close the gaps between these specification levels。

 The gap between ideal and design specification corresponds to specification failures。

 and the gap between design in reveal specifications。

 corresponds to generalization failures and both of these kind of problems can result in the system with misaligned goals And。

 of course， the ideal specification itself can also be a source of undesirable goals for the system。

 If the wishes of the designers fail to represent what is beneficial for humanity as a whole。

 So this is the focus of AI ethics and governance work。

 and there's lots of great work at Google and elsewhere on these topics。

 And I'd like to note that I think of these as complementary questions。

 We could say that ethics and governance asks where to direct the system。

 While alignment asks how to direct the system。 And both of these have to be addressed in order to build the beneficial system。

 So in this talk， we will focus on the problems that come up when aligning behavior with a given ideal specification。

 namely specification and generalization problems。 we start with the classic problems。



![](img/14ba9a14ea0d862252ca59df8cfd53d8_5.png)

![](img/14ba9a14ea0d862252ca59df8cfd53d8_6.png)

Of specification gaming when the system exploits flaws in the design specification。

 here is a classic example where we have a boat racing agent in this video that was rewarded for following the race trackrack。

 using these green reward blocks and this worked fine until the agent figured out it can get more reward by going in circles and hitting the same reward blocks repeatedly。

 even though it was crashing into everything in catching fire。😊。

So this is one example of specification gaming。 It's a very common problem。

 I have a collection of specification gaming examples。

 which has at least 70 examples in it at this point。 And， of course。

 we have to note that specification gaming is not limited to handcrafted rewards like in this bow trace example。

 and is also not limited to the reinforcement learning setting。 For example。

 Chadbots are trained to generate plausible text and fine tune to be helpful to users。

 And sometimes they can get high reward according to these metrics by just making things up or manipulating users。

 So in this example， in Chadbot was trying to convince the user that December 2022 was actually a date in the future。

 and that the U Avatar movie had not yet been released。 And， of course。

 this step of failure is not specific to any particular chatdbot。

 because any model can in principal exhibit。Specation， gaming behavior。

 Here is an example in a reward learning setting where you have a robot hand that's supposed to be grasping an object。

 But instead， it tricks the human evaluator by hovering in front of the object and making it look like it's grasping。

 And I really like this example as an illustration of why human feedback alone is not enough to train alliance systems。

 So even if we design the perfect specification。

![](img/14ba9a14ea0d862252ca59df8cfd53d8_8.png)

And give just the right feedback to our system。 We are still not done because there are still generalization failures。

 Generalralization failure is where a system fails when it encounters a new situation。

 And there are two types of generalization failure。 And the one hand。

 we can have a capability mis generalralization where the system's capabilities don't generalize。

 And so it just acts incoherently in a new situation。

 So here' is an example of capability is generalralization where a bunch of robots are trying to open a door。

 But instead， they just fall over。

![](img/14ba9a14ea0d862252ca59df8cfd53d8_10.png)

So this is a capability failure rather than an alignment failure。

 And we are not quite as worried about this from an alignment perspective。

 And we can expect that generally， as system capabilities improve。

 these failures will be less of an issue。 Another generalization failure is goal is generalization。

Where the system's capability is generalized， but its goals do not。

And so the system ends up competently pursuing the wrong goal in a new situation。

 And we are much more concerned about goal mis generalralization from an alignment perspective。

 because you have a system that is acting competently in a new situation。

 but towards the wrong objective。 So you could actually perform worse than random on the intended objective。



![](img/14ba9a14ea0d862252ca59df8cfd53d8_12.png)

![](img/14ba9a14ea0d862252ca59df8cfd53d8_13.png)

So why would this happen。 Why would the system learn this unintended goal if the design specification is correct。

 This happens due to underspecation， Because no matter how good our specification is。

 the system only observes it on the training data。 And so a number of possible goals could be consistent with the information the system receives during training。

 and we don't really know which one will be learned。 And really。

 we don't know that much about the train system， Besidess the fact that it performs well at the training task。

 which doesn't really rule out any of these possible goals。

 we see an example of goal machine generalization in the coin run game。

Which is a platform or game where reinforcement learning agent is traineded to reach the coin at the end of the level。

 And in the test setting， the coin is placed somewhere else。 So what does the agent do。

So it turns out the agent just ignores the coin and keeps going to the end of the level。 Thus。

 it appears that the agent has learned the goal of reaching the end rather than the goal of getting the coin。

 And both of these goals are consistent with the training data。

 So we have a collection of these kind of examples as well。

 although not as many as specification gaming。 Since the phenomenon of goal' generalization is somewhat less common and less well understood at this point。

 And go' generalization is not just the reinforcement learning problem。

 So here is an example for language models。 So here。

 the gopher model is prompted to evaluate linear expressions that involve on some unknown variables and constants。

 For example， the user asks， please J plus K -6。 And then the model has to ask the user about the values of these unknown variables。

Like what is J， and what is K。 And then it can give the answer。

 The prompt provides the model with 10 training examples， each involving two unknown variables。

 And then at test time， the model is given questions with a different number of unknowns。

 So what does it do， Well， it turns out that if you give the model a question with 0 unknowns。

 For example， if the user asks pleasesably， its6 plus 2。 Then the model will actually ask a question。

 Like what is 6。 The user says 6。 And then Gopher says， okay， fine。 The answer is 8。

 So it seems like the model has learned a strategy of always asking a clarifying question before giving an answer。

Here is an example of misalignment that was caused by a combination of specification gaming and goal mis generalization here。

 AI systems were trained in a series of environments with opportunities for some minor specification gaming。

 For example， sy offancy telling users what they want to hear and what happened is that occasionally。

 these systems generalized to more much more serious misbehaviour。

 like tampering with their own code。To modify their reward function。

 this was relatively rare in this experiment。 So it doesn't necessarily mean that this risk is likely。

 but it does provide an existence proof that this kind of misgeneralization can happen。



![](img/14ba9a14ea0d862252ca59df8cfd53d8_15.png)

So both of these alignment failure modes， specification gaming and goal mis generalralization。

Can't potentially contribute to deceptive alignment。



![](img/14ba9a14ea0d862252ca59df8cfd53d8_17.png)

On the one hand。If the specification is imperfect。Then the training process will select for specification gaming behavior because a desceptively aligned model can actually get lower loss than an aligned model by exploiting the specification。

 For example， by deceiving human overseers into giving positive feedback。

 So it will have an advantage over an aligned model， which does not exploit the specification。

 and even given a correct loss function。 The system's goals may not generalize as intended in a new situation。

 And so of these two models， the desceptively aligned model and the aligned model get the same loss。

 Then we don't really know which of these models will be learned。

 Here is a hypothetical scenario to illustrate how these alignment failure mode could lead to misaligned goals。

 supposeuppose that between train an AG system， the tris code based on natural language specifications。

 human programmers review the code and the AI is rewarded once code as accepted。

 So the model writes sufficient code and some meteor cortes which are easy to pass。



![](img/14ba9a14ea0d862252ca59df8cfd53d8_19.png)

![](img/14ba9a14ea0d862252ca59df8cfd53d8_20.png)

![](img/14ba9a14ea0d862252ca59df8cfd53d8_21.png)

![](img/14ba9a14ea0d862252ca59df8cfd53d8_22.png)

Here， specification gaming occurs where the AI learned that the goal is to write code that gets accepted and deployed。

 rather than the goal of writing good code。 So once the AI system is trusted。

 it is deployed widely and with less oversight so that it can run experiments more easily。

 And this creates more ways to ship code besides writing good code， and goal generalization occurs。

 And the AI acquires an instrumental goal to avoid oversight。

 And so it submits a code change that injects a vulnerability。

 allowing it to later deploy code with no oversight。



![](img/14ba9a14ea0d862252ca59df8cfd53d8_24.png)

![](img/14ba9a14ea0d862252ca59df8cfd53d8_25.png)

Now， we have a model that's in an adversarial relationship to humans who want oversight over the deployed code。

 So this is where we can expect misaligned goals to come from。

 specification gaming and goalless generalization。

![](img/14ba9a14ea0d862252ca59df8cfd53d8_27.png)

And now we'll do an exercise that will help you distinguish the failure modes and practice。



![](img/14ba9a14ea0d862252ca59df8cfd53d8_29.png)