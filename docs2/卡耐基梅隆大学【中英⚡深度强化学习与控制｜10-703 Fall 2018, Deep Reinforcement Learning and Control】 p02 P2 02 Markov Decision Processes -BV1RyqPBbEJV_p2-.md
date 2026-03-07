# 卡耐基梅隆大学【中英⚡深度强化学习与控制｜10-703 Fall 2018, Deep Reinforcement Learning and Control】 p02 P2 02 Markov Decision Processes -BV1RyqPBbEJV_p2-

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_0.png)

Okay。So in the previous lecture， we talked generally about learning to act。

 learning to develop goal seeking behaviors。 We mentioned three types of supervision。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_2.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_3.png)

1 from rewards。One from experts and one from specifications given in natural language。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_5.png)

We said that the rewards are what the environment provides to the agent。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_7.png)

At the end of the task， we varies par in time。And we said that the expert demonstrations is what is the when there is a teacher that directly tells the agent what to do。

 So the two types of feedback rewards and expert demonstrations are very different。 One。

 the first is called evaluated feedback。 You're taking options。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_9.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_10.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_11.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_12.png)

And the environment or an oracle tells you whether these actions are good or bad。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_14.png)

In the second case， someone directly tells you what to do。 Let's see how this is different。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_16.png)

Imagine your students and you have an advisor who is an oracle advisor。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_18.png)

And you are trying to suggest good research ideas。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_20.png)

So if the advisor provides evaluated feedback， this means that you will make。

 you will take actions by suggesting those ideas， and the advisor will tell you yes or no。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_22.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_23.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_24.png)

Now， if you'll never get the chance to suggest a good idea， you will never discover it。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_26.png)

So evaluated feedback is much weaker than， you know。

 Instructive feedback in the sense that it depends on your policy。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_28.png)

The second type of feedback， Instructive feedback， The advisor directly will tell you what is a good research idea independent of your policy。

 So it's much， much stronger you know， supervision。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_30.png)

So we will focus in the next few lectures on the first type of supervision and we'll come back to the second type of supervision later。

 The second type ofvision also is called imitation learning， learning by imating an expert。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_32.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_33.png)

Now， why since the second type of supervision is much stronger。

 right and directly leads us fast to the right solution。

 why do we care about this weak form of supervision？



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_35.png)

Well， first of all， learning by words or else learning by reinforcement is biologically plausible。

 The term reinforcement can be introduced by Skinner， who。Who lived from 1904 to 1990。

 and he was a professor in Harvard psychology department。

 So Skinner said that free will is overrated。 We don't act by free will。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_37.png)

And free will is also loosely related to religious and metaphysical connections。

 So he said things are way simpler。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_39.png)

We just act based on reinforcement。 We act。 And once we see a positive outcome of our actions。

 these actions tend to be to receive a positive reinforcement and be repeated while when we act。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_41.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_42.png)

And something is taken from us。 for example， we decrease negative stimulus。

 Then this is also is going to。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_44.png)

Sorry， this， this is not correct。 The the animation here。But he said you just act。

 you observe the result and if the behavior is praised or gets pleasure。

 it gets to be repeated if the behavior tends to in pain or in punishment tends to become extinct as simple as that and this is and this was developed based on animal behavior。

 and this is also， let's say the principle behind reinforcement learning okay。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_46.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_47.png)

So here is the diagram。 We have an agent。That interacts with an environment。

 Whatever is outside of the agent， it cannot be controlled。 Okay。

 the environment cannot be controlled， though you can know about the environment。 For example。

 you know that a big storm is coming， you cannot do anything to control it can prevent it。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_49.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_50.png)

The agent interacts with the environment by emitting options。 Okay， from his end defect。

 The environment respond by sending the agent to a new state and admitting potentially a reward。

 Reward does not need to be admittedted at every time step。

Then the agent takes as input those states and rewards and predicts a new action。Okay。

 so this interaction results in trajectories of the form state action reward， state action reward。

 state action reward。There were questions in Piazza of what is an agent and what is the model。

 Now we will visit the definitions in this diagram in great， great detail。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_52.png)

So why we care about reinforcement learning？Two of the important reasons of the following First。

 it is biologically plausible。 It is very easy， a very cheap form of supervision。 Okay。

 so we don't need to ask humans for expensive annotations。

 But another thing that I would like you to pay attention。

 And this is why I got interested in reinforcement learning is the second bullet because it addresses the task that artificial intelligent cares about。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_54.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_55.png)

In other words， building ages that act in the world from end to end。

 It doesn't consider intermediate cost functions。 And if you're a computer visual researcher like me。

 you may care about task like object detection or pixel labeling or depth estimation or。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_57.png)

S parsing， Okay， but the reason you care about these tasks is because at the end。

 it will lead towards building agents attacking the world。

And the problem with this okay the problem of breaking the end task into intermediate ones is that many times you may just pursuing the own cost function。

 you care to label correct this far away pixels， potentially a car that just wants to learn to drive will never care about these pixels okay so just to make sure that a research stays relevant to the end task。

 it is important to take into account and task from the way reinforcement learning does it Now intermediate task will show later in the course that they help in providing better representations and potentially accelerate okay reinforcement learning。

 but you know considering the task to its entirety is also very， very important okay。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_59.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_60.png)

So I really want you to consider this because this isnt why me and many other researchers。

 for example， in no language or in computer vision or other。

 let's say artificial tele cell fields are getting interested in this。

 how do we build agents to act in the world because many times you are bogged down the details。

 oh I didn't get this last 10% pixels right， but at the end of the day this may be irrelevant。😊。

On top of that， the representations that you're building may be also not in the right direction may not be exactly what eventually an active engine will need to see in the world to act effectively。

 So I think this is very important to， to realize。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_62.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_63.png)

Okay， so here's the diagram again。Let's go and visit every term are we done with the technical problem So let's go and visit every term。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_65.png)

So what is the most important term here is the state。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_67.png)

State aulates whatever the agent knows right now about the environment， okay。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_69.png)

And。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_71.png)

Now， you're going to say in last lecture， we didn't mention not to the word state。

 We only mentioned observations。 The Saturn and Barton book refers to observations as sensations。

 essentially is the input from your input the raw input of your sensors， visual sensors。

 audio sensor， tactile sensors。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_73.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_74.png)

Et cetera。 Now， states is essentially a processing of those observations into some abstract form that will facilitate acting in the world。

 Okay， and making connections between different observations where the action should be similar。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_76.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_77.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_78.png)

Interestingly enough， the book has a specific phrase that says in this book we do not care about how you transform observations to states we do not think that this is important。

 we think this is very， very important it's just that we're not going to tackle it you know in this particular let's say textbook however。

 they're going to be later lecture here exactly on how do we transform observations to states for now well assume states that are completely observable。

 the state is something given ready to the agent without him needing to struggle at all okay and on this basis is going to develop his behavior okay his policy on top of this。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_80.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_81.png)

Does this make sense。 So instead of talking now about observations。

 we're going to be talking about state and forgetting about the pain that is required to go from observations to states。

We post on this for a little lecture。By the way， I need to tell you that this is a very typical thing。

 It happens to all the courses。 First Western were God and oracle and everything is easy okay。

 and we we show the theory and the main concepts。 and later we say， okay， but here is the real world。

 and the same thing we're going follow this course。😊。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_83.png)

A question in Pierto was what is an agent。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_85.png)

Agent is this entity that has sensors to you know fill the environment and has any effectors to interact with the environment。

 And also has goals that wants to achieve。 Okay， is this entity that interacts with the world。

 and you know， agents can be animals or people or body cages or seakits or our mobile phone or Alexa right now。

 Alexa， the mobile phone do not really carry out reinforcement learning。

 but they do have sensors and they do have effect and they have goals to satisfy their the users。

 and potentially if they want to become intelligent， they also need to run some type of you know。

 this type of learning in the future。 Let's say， okay。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_87.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_88.png)

O so。Actions is the interface between the agent and the environment。😊。

They can have many different granularities。 Okay， and in fact， it is， as I said。

 more overt as opposed to science to decide the right interface between the agent and you know the world。

 the environment and what type of abstraction to choose for your states。 For example。

 once you have a gripper， you may choose to be your actions。 You may have a gripper。

 the actions may be the voltage， the torques， or it may be the D X， D， Y D Z。

 essentially instantaneous translations and rotations of your end defect。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_90.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_91.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_92.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_93.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_94.png)

The problem is that if you choose the first， the tos。

 which is way more direct and way more had to say。Controlling the grip in a reactive way。

 you don't need to solve inverse kinematics to figure out what are the torques for me to move and rotate in that direction。

 The problem is you cannot generalize across different robots Okay so the more you choose your actions to be closer to the environment and further away from the agent。

 the better you can generalize across agents Okay essentially what can you the learn policies that's what I mean。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_96.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_97.png)

But then less direct， you can let's say， command the particular agent。

 and it needs to be a low level controller that will take you from the talks to this external interface of actions。

 Okay， and you will get the chance to see this in the homework later。Now， by question。

 here is the following。What should be the temporal granularity of actions。Okay。

 action can be milliseconds or it can the actions may last few seconds or even more。

 Why do you think we don't choose very long you know， actions。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_99.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_100.png)

I'm sorry。Right， exactly。 So the longer the action。

 essentially here I want you to understand that this loop that we showed means that I receive。

 I'm the agent。 I receive the state and I see the reward and I see the state and then I choose the action。

 And then I execute the action。 And when I execute the action is as if I switch off my sensors。

 So now I'm just executing the action。 and then the environment response and then sense my new state and a new reward and now I switch on again my sensors。

 So while you are executing essentially your your sense of switch office if you close your eyes。

 how often or not only your eyes also your tactile sensing everything。

 How often do we act without with switching off our sensors a little bit you want to pick up chewing gum。

 if you close your eyes， you're not gonna to pick the chewing gum。

 So our excellent visual motor skills， much depend on this continuous loop。

 Okay and now you're gonna say， but of course， it is a loop。 Well， yes， it's a tight loop。

 It cycle its very， very fast。 so。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_102.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_103.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_104.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_105.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_106.png)

Conenuously， look and sense the environment and update our actions。Okay。E， if we care about man。

 for example。Now。This is the case for robotics。 Now the same framework。

 theoretical framework can have actually can be much， much longer for example， I decided to do a PhD。

 This actually in fact， is impractical because you will not have the chance to do many PhDs in your life and reinforcement learning essentially means I try something many times I look at the reward I have my policy Okay so to be practical in that setup and action should be able to be carried out many。

 many times during the lifetime of the agent。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_108.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_109.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_110.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_111.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_112.png)

Okay。So now something that is so simple that we may not even realize when we talk about goals。 Okay。

 and when in the previous get people are talking about with the goals and the agents seeking goals。

 right， this sounded very abstract。 Okay， how do you formalize this。

 I' would say notion of an agent having a goal and reinforcement learning says。

 you know what it's extremely easy。 We're just going meet a scholar every now and then。

 this scholar is gonna be emitted is not a positive sign If the goal is achieved and is's gonna be0 or  minus-1 if the goal is not achieved。

 Is't this extremely simple， extremely simple formulation of this abstract notion of goal。

Although you would expect this not to be flexible， In fact。

 it is surprising flexible well be able to do a lot of things。With this type of definition。Now。

 again， going back to this。Evaluative versus instructive feedback。

 Instructive feedback Tell you what to do。Evaluative feedback tells you if what you did is good or not。

 okay。So evaluative feedback rewards depend on your actions。 Okay。

 you may have fantastic oracles in the environment they really want to guide you。

 But if you never get to explore those states and look at those rewards。

 you will never get to to your goal。 While the expert， once you see you failing。

 It will push can tell you， okay， do this now。 Okay， and guide you to the。

 That's why both forms of supervision are important。😊。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_114.png)

And in fact， right now， in robotics， you will never see the one used without the other。 All right。

 So demonstrations and reinforcement are couple， okay。O。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_116.png)

嗯。Now， this is a very important notion because this is exactly our loss function。

 This exactly our not loss function。 reward function。

 This is exactly what we're gonna be seeking to maximize。

 We do seek to maximize instantaneous rewards。 We seek to maximize the cumulative the expectul of long termm rewards。

 whatever is going to happen from this state to eternity。 If I keep using my current policy。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_118.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_119.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_120.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_121.png)

Okay케。So what is the return well。If you interact， there are two types of you know interaction modes you may have。

 One is called the episodic task。 I give you a horizon。 And I tell you， okay。

 interact now with the world。 And at the end of that temporal horizon。

 there is an ending absorbing state that you stay there and you cannot go out。 Okay。

 you just stay there。 And this is called episodic type of interaction。

 And then what you try to seek to maximize it's just the sum of the reward during that temporal horizon。

 right， Ex simple。Now， there is another type of mode of interaction。

 which goes on forever and ever and ever。 Now， the previous form is exactly is both episodic tasks is mostly what we visited in their previous lecture。

 all the games， are episodic each time the game stops。 you know。

 everything starts from the beginning， right， everything is wiped off your mistakes。

 nothing you start again， the interaction with everything have been forgotten。

 Okay while many times we may want our agent to continue you know， working without you know。

 stop any erase of its memory and is history。 and this is， you know， the continuing task。Now。

 the return that we try to maximize in this continuing task is， again， the summation of the rewards。

 but it's an infinite sum is going to blow up。 So what do we do。

 We multiply with a small discounting factor， which is smaller than one。

 make so this sum now does not blow up。 Okay， Also。

 discounting factor potentially means that I want you to get the rewards as soon as possible。

 if you succeed later。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_123.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_124.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_125.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_126.png)

You will get the reward， but it's going be much discounted， right。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_128.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_129.png)

So if you write a good paper， tomorrow iss better than if you write a good paper in four years from now。

 even if it's。Identical paper， okay。Allright， so returns。 This is going to come up。

 This is exactly what we're trying to minimize to maximize。 Now。

 another question that came up in Piazza is what is the model， Well， this is the model， the dynamics。

Essentially， is this function。 Okay， this probability distribution that given the current state and the current action tells you the probability over the next states and the rewards you' are going to receive。

😊，All right。if you have the deterministic environment。

 you don't need to care about this one state is gonna have one probability。 only the R is going be 0。

 But for now， we just consider stochastic environment。 Again， the rewards here。

 we consider this most general case where the rewards also are stochastic， okay。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_131.png)

Now， you can marginalize out the rewardwords and end up with a transition function。

 given the state and this action where I'm going to go next。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_133.png)

Now， an agent has a model。 A model does not have an agent。 They are completely different things。

 right， The agent is the entity that they actually with the environment。

 and the model is this super important， you know， probability distribution。

In all the examples we saw in the previous lecture。

 this dynamics was known from the simulator that we were were playing the games， okay。

Now why the model is important， so let's here let's discuss more about the model。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_135.png)

So model based reinforcement learning is when the dynamics are either known and used or they're estimated。

 okay， and they are used to learn the policy。 Modelel free reinforcement learning is when we do not know the dynamics and also we do not attempt to learn those dynamics。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_137.png)

Alpha go0 is what model based or model free。What is it。Model is well， I didn't hear。

 You said a lot some model list。Which one would like to say something。Yes。Model free。

 Why it was model free。Yes， you don't know what the person is going to do， but， you know。

 given the board configuration， which is your current state。

And what action're going to put where you're going to put the stone， correct。

 what's going to be the resulting state？

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_139.png)

And then you can also， you know， marginalize across what the other opponent is going to do。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_141.png)

And in fact， we did use those dynamics when we did this Monte Carlo look ahead research， right。

 each time you use a search。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_143.png)

Each time you use a search， you query the model to send you from the current state and action to the next state。

 Who is going to send you the model。 O， Al right， So you were using the simulator。To to think， right。

 and to， to look ahead， Does this make sense， It's just that this simulator。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_145.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_146.png)

You didn't need to learn it because it was given to you。 correctect， Yes。

 So you think that the reinforce。You think some。No。

I'm saying the following every time maybe I should talk about the policies first let me think。

Every time when we are about to act and to choose an action。

 when we do a look ahead search to do a look ahead means that you use a model。

 Either a model that you learned from samples and you fit it in can be a linear models and approximation subnet。

 whatever you like， or it can be given to you like alphago in every game， you know all the games。

 I know exactly what's gonna happen。 if I roll the dice inga and if I move the。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_148.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_149.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_150.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_151.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_152.png)

Stone in Bagama， exactly what's going to be the next state， okay。So if I use this in a look header。

 So did Gama also had to look at head search， also is using a model， okay。Does this make sense。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_154.png)

But thiss a good， Yes， So the difference is that like a model3 R out。to generate an internal model。

Slying it with the model before。So model3 is not even， is not even attempting to learn a model。

 is trying directly to learn in this state。 What should I do。 And in this state， now。

 what should I do。 And Q learning is one form of this and we're gonna to see。

 once you have the Q function， directly， you can do maximization of your actions and pick the best one。

 The one that has the highest Q， correct。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_156.png)

And even to learn that Q， you didn't do any look aheadset。 you could。 and you will do better。

 And then you become model based。 But if you don't， and you just say， okay。

 let me just explore this way。 or let me just explore this way。 and let me just run this way， Oh。

 here is my resulting Q。 This means you just interacted with the environment。

 The environment is a model。 Okay， but you're not trying to build our own and mental model。

 So it's different when you take actions， then you interact the environment。

 when you run a carlo research is mental。 So you use a model to mentally say， oh， what if I do this。

 What if I do that， Does this make sense。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_158.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_159.png)

Yes， so。原房的。对这一站。What is the probability of next states， Yes。

 so this probability maybe have the opponent also there。 Oh if your opponent you know， does this。

 then you gonna to end up there。 If your opponent does this， you may end up there。The。

 the stoist from the opponent。Okay， but this is a good question。 Now。

 let me tell you what I read on a paper and I thought it make a lot of sense。

 We say that deepQ learning is model free because it interacts with the world and come up with this Q function。

 and then you just take a max of your four actions and you have your policy However。

 to end up to end up using this queue， you have to query the simulator millions of times Okay and the simulator is essentially a model。

 if you could do that with small number of queries in the real world， Yes。

 maybe you call it model free。 but if you do it in the simulator and you have millions of queries on that simd model。

 are you still model3， how can you call yourself model free。

 since if I tell take away your simulator， you gonna be able to do anything Like you cannot apply this in the real world。

 Does this make sense， So I would say it is a little bit confusing。 okay。😊。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_161.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_162.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_163.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_164.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_165.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_166.png)

嗯。I mentioned that in Mar。自分にバレしていく。You want to select an action。

You don't know you don't know when you're going to end up。

 The environment is going to tell you where you ended up。

actionWell very good question you may randomly choose an action or you may use your current policy。

 which is not going to be rather great to choose that action or you may do a mix sometimes choose from your current policy and sometimes a random action right with what's called Epsilon gradient with Epson probability I choose my best current policy what I know and one minus steps on a random action。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_168.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_169.png)

这嘛在这。Yes， now， we're going to see what is a policy。 Yes， but but model is it exactly。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_171.png)

This transition function， right， state and action give you next state and reward， correct。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_173.png)

TD Gamon is also model based。 There was also look ahead search。嗯。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_175.png)

Now， here is the problem with model base so far。As long as you learn a model。

 this model will never be perfect。 Okay， And if you use that model to learn your policy by querying it。

 you may end up having a suboptium policy than a method that did not use such err use model。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_177.png)

And this is the reason why many model based approaches suffer and cannot outperform model3 approaches if you allow them。

 if you， if you don't penal them for the number of samples。

 because as the number of samples decrease， the model  three approach will win。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_179.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_180.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_181.png)

Now， there has been excellent， recent， very recent work like the last1 or two years of how do you use both motivation based and model free without suffering at the end one。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_183.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_184.png)

choicehoice， which is very often， is that you initialize your policy from a model bias method。

 Al right， So in this way， you are much faster。 And then you find you with a model 3 method。

 So in this way， you have both。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_186.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_187.png)

The good of both worlds， let's say， okay。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_189.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_190.png)

Now， here is， here is the model。 Here， we can understand the model。 If you have a model。

 you can throw away the world and put the model there。

 And then we when we can run this loop mentally without reacting in the world。 just mentally。

 if I do this， I'm going to do this。 But if I'm going to be there， I'm going to be late。

 And then maybe I should not go there。 Maybe I should go that way。

 Does this make sense without interacting at all in the world， it takes the place of the earth。😊。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_192.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_193.png)

We asked also in last question in last lecture， what is planning。

 Well planning is exactly running this loop using your model。

 the an unlearned model as opposed to interacting with the world。

 So you plan ahead and a plan is the result of plan is a sequence of actions。

 right We say I have a plan。 I have a sequence of actions that will give us the goal。 Allright。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_195.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_196.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_197.png)

So here is the agent and here is the model completely different， right， and here is the policy。

 The policy sits right there like is the mapping of the states to the actions。

 And here we here policy pi， we usually use the pi notation。😊。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_199.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_200.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_201.png)

A policy is a distribution of actions given the current state。 A police can also be deterministic。

 in which case， only one action is probably even a corresponding state， right。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_203.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_204.png)

啊。When we talk about policy， let's not be confused。 We don't mean a reactive policy。

 It can be reactive。 That is a direct mapping from the observation of the state to the action。

 or it can evolve a look ahead search。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_206.png)

Based on the resulting， please， you choose the corresponding action here in the beginning of the trip。

 All right， in both cases， it's a policy。And here is a collection of the definitions that we saw。

Are there some questions？

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_208.png)

Yes。Is mono equivalent to transition。Yes， it is。 So the transition function usually is used to estimate the probability of the next state。

 given the current state in action。 The model in its most general 4， Okay。

 also has the probability to see that reward because the reward also can be stochastic。 Okay。

 in the current state and action， what's the probability of seeing reward and ending up a particular state。

 And if you marginalize out the the reward， the probability of the reward。

 Then you have the transition function。 And for the one who use the P or the raw and the other。

 we use the top。Yes。とレた。研究？Yes， so policy is a function。 and plan is just a sequence of actions。

 not a function。 It's just the result of of over alook ahead， right， It's not a mapping function。

 It's a plan。 It's a sequence of actions。 a 1，8，2， a，3， 4。 So now my plan to go up the stairs。

 turn left and then go the rest。😊。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_210.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_211.png)

ok。There is not that something to learn is the result， or right？での不安せ。行てく来。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_213.png)

So my policies， each time I see that is quiet in class， I will go to rest。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_215.png)

Do you see what I。Okay。Is a magnet function。Yes。ましたが。Yes， thank。Much stronger。

Th that given a few examples。It very nice， so what you're saying is the following。

If you use theive feedback。You probably will never get better than your expert that taught you what to do。

 correct。That's right。 That's why what we do In the first years of the Ph G D， You hear your advise。

 Then you become better than your advise that stop here your advisor and you choose your own。 And。

 you know， you choose your own research and sometimes gonna fail。 It doesn't matter。

 You just choose your own。 If you always do what your advise tells you。

 you'll never do better than than her on him。😡。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_217.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_218.png)

Yes， we allow infinite number。AVery good question。 of course， infinite yes， in general， yes。

 in the next three lectures， absolutely not。 It's gonna be finite。

 and don find for these lecture is also gonna be small so that you can estimate， you know。

 the value functions by you are able to fit all the states in the table and you know。

 visit every state many times and estimate their value。😊，And what about action。

Actions also are finite and small here。 And later， they are gonna be continuous。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_220.png)

We haven't gone to that more formal part yet。 But， but it's good。 So that's why Bagamon comes here。

 lots of states， of course， find it。 But many。 Okay。

 and the different moves that you can do with the stones and the rewards are a win lose else。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_222.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_223.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_224.png)

Actually， in Bagamon， you also have different reward if you win double game or versus winning single game。

 But as you see， you may play long， go long， long。 The reward is gonna come only at the very end。

 okay。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_226.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_227.png)

Or at here again， learning to drive the actions you steer the wheel， you press the brake。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_229.png)

At the end， if you reach the goal and you are not overtired。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_231.png)

It's good。 Once you get the ho。 It's bad。 Once you collide， it's pretty bad。 The carpo。

 you can move it left and right。 These are。Stand are little problems for enforcement learning。

 They may come up in the homework also， okay。The rewards are zero while balancing my for imbalance。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_233.png)

And here is an interesting example。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_235.png)

So the robots will tell you， here is the robot。 You try to put the peg inside the hole。

 There is a hole， and you're holding a wooden pole and you need to put that pole into the hole。 Okay。

 what should be your states。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_237.png)

Many papers say it's going to be the joint configuration of the of the robot， al right。

Is that right or no？So I want this example is exactly to understand how we should define our states。

Now， what is the problem if the state is defined based on the configuration of the robot arm only。

Yes。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_239.png)

Exact， so you learn a policy where all the time the whole will be exactly at the same place if the whole moves you cannot do anything because is not part of your state。

 This means that you don't sense it state is whatever the agent knows about its environment if you throw away the environment and you only use your own you know or then as soon as the environment changes。

 you cannot act so you cannot act in a dynamic environment。

 you'll be able to solve the dark to the task in this particular setup。

 but you won't be able to generalize a different setup。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_241.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_242.png)

ok。Now， the truth is only later， we'll see methods that use this type of configuration for and they vary quite a bit where the policy they learn this type of very simple policies for different place of the whole。

 and then they train a general policy with always consolidating and distilling information from all those solutions。

 Okay we will see this later。 but this is the problem with this data representation。

 and usually when we talk about manipulation， we also put a penalty about jerkiness。

 we don't want the arm to go like this。 even if it's success on the and could make sure that you know the Army's All right。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_244.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_245.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_246.png)

ok。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_248.png)

嗯。No， let's forget the first bullet， because we haven't talked about Markov yet。

 So this is what's coming。 The， the main limitation is that to be able to succeed through。 reinforce。

 we may be able to try things again and again。 Okay， and see this little。么搜。

If you can safety the concerns。For example， that's the biggest problem of the selfdriving car companies。

 They say I cannot really learn or behave of my car because I cannot try。

 oh what if I do this and what if I go very mostly the pedestrian and what if I go faster。

 maybe I'll get the chance cut across because there are safety concerns。

 you are not free to interrupt with the environment that's the problem so this is what I said earlier that for now will consider cases where the state space is finite and also small and same thing with actions are finite and also small small set of actions Allright and in the last later lectures we will。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_250.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_251.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_252.png)

Loing up those constraints， so this is how I finite Mark decision process looks like it's just a set of actions。

 a set of states， the dynamics model which probably here only considers the probability of our next state and assumes that the reward is deterministic okay this is going to be updated the only reason is we're trying to be consistent with the notation of the book okay。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_254.png)

嗯。Here's a core function。And this is the discounting factor that we said that we use to estimate the returns。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_256.png)

That's it， we just put all these elements that we saw together。

 let's give a few examples of MDPs and we'll go what is the new word here， the new word is Marco。

 so we'll go back to this work in one second。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_258.png)

Let's consider this example for the Barton and。Ston andbardo。

 okay we have a robot that is trying to do recycling。

 but you know it also has a battery so it should not run out of battery。

 so it's trying to decide given charge level whether you should go to recharge himself or whether he should search for a can in his neighborhood or whether you should just wait for a human to give him a can Now if you search。

 you find more cans but you waste more battery， you just wait， you'll have fewer cans。

 but you're not going to waste battery that that's the idea all right。So， yes。

 the reward is the number of accountss that you collect。Well。

 that's the number of cut and you get negative word if you run out of battery because then we need to bug humans to go to reset you。

 so we're try not to run out of battery here。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_260.png)

And this is how the MP looks like。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_262.png)

Those circles are the states， so here in a state of high。

Batter charge and this is low battery charge。And what are the tiny little bullets where here is the actions with take。

 you say from a high state？With some pro， they take the search action and with some pro that take the weight action。

And there are these two little arcs that tell you， okay。

 now the stochastic environment will throw you in this state with some probability and will throw you in that state with some probability。

 okay？啊，Yeses。Yes， like for example what like how many cans have you have used this is very good we're going to come back on this again and again because the cans can just be the number of cans is just adding over time so if you're there and you take an action。

 you take the word。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_264.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_265.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_266.png)

And hope you take the reward， does this make sense， so you are accumulating。

 you're stay the same state， but your reward keeps increasing， okay？



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_268.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_269.png)

So if you're in a particular state， it doesn't mean that your turn is the same as you act and you stay in that state you can always accumulate more reward。

 the reward seeds on the arcs， do you see what I mean， you get rewarded。

 given a state in an action so if I'm in this state let me seek how。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_271.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_272.png)

嗯。So imagine that each time I ask a question and somebody replies， I get a reward。

 now my staying is extracting a class， each time I ask a question。

 I have some probability of getting a reward despite the that I'm in the same state。Okay。No。

 let me start thinking a little better example。 So what you're asking is why don't we parameterize states from a number of ks I have because you don't need to because the number of cans that you collect is additive over time。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_274.png)

Each time you get some number of kinds it's added and it's added and it's added。

 and you just try to maximize this cumulative sum。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_276.png)

Yes， John， yes， please。 I think maybe another way say that。房。You would like to learn。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_278.png)

Its really。エ事悪い。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_280.png)

Basically， if you have five hands， you want to do the same thing as you good one。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_282.png)

We want to get where kids。And therefore。see？なで。日本で。Very good， excellent， exactly。😊。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_284.png)

say at the following， this is not always the case。 If you're a policeman。

 you try to collect funds need the， but however， you have a number limit on the number of funds you need to look per month so your local。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_286.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_287.png)

more reward if you do more fines。 In that case， there were the state would be parameterized by how many funds you've collected that far。

 right， Do you agree， But in this case， this simple robot does not say， oh， come on。 I have 50 can。

 Let me just relax now。 No， each time， no matter how much it has succeeded。 You know。

 it just it tries exactly the same things。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_289.png)

Yes。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_291.png)

Probleistic。P of， which could happen on the。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_293.png)

Or if like we want to say after several， so if you recharge for sure you're going to go high better。

 you agree？

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_295.png)

Okay， great。 Now， if you decide to search for a can。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_297.png)

You may still have low batteries。You mix。Or what happens here is you take these minus trees that you know。

 you completely run out and somebody came and charged you。 And now you are in the high。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_299.png)

High butter level。 Does this make sense。 So there is some intervention there in the ministry happening from a human being that goes to。

 to reset you because you really run out of butter。Does this make sense。

Sometimes after one or two immediately。在 here这个。Instead of like 13。No， there's nothing something。

 There's nothing here like searching for x number of that。 Each time you are in the high。

 and you decide to search， no matter how many accountss you have and how many times。

There is prohibition that your but is going to go over。Okay。

Maybe it's confusing because you know what， the battery is not high low。 It is high， lower， lower。

 lower， lower， lower， low。 Okay， so here you just， it's a little bit simplified in that sense。Okay。

 so it doesn't matter how many times you search each time you pick a search with a sample。

 you may end up in low battery。Yes。変な？There set on the room right。No。

 I think that would make sense that you end up on you need to be mild reset It's just that this it is equivalent to just putting this reward there。

 right。Lny， then if you have this extra state。There is no policy you can do from there。

 The human is going to pick you up and put you So since there is nothing that you can act。

 you don't have any choices So why should you model as an。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_301.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_302.png)

Different state， right。你。Yes。😊，でれば願。ちすね。Yes的。Well， like the time become。I mean。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_304.png)

But this is a good point with a number of camps， in my opinion。Okay。

 let me see few few examples of Marov。 and then we'll decide what is Markov what's not Marovs。

 That's another example given by David Silver。 And this called the student MP。

 So this is each one of you， alright。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_306.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_307.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_308.png)

That you choose to study and this time you study， you know， you undergo a tiny little pain of-2。

 you study a little bit of pain。 but then you study again， and that's it。

 get you do well in the course。 You just need to stain the effort okay Now the problem is that if you decide to Facebook。

 I think the research shows that you get depressed because I people around the beach and stuff like this。

 And then you become addicted and stay there and checking what other people are doing。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_310.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_311.png)

And then you come back。And once you're tired。But by the way， here， these guys don't exist why。

 because so far the environment is deterministic。 Okay， so each action will go exactly to that state。

 That's why we don't have this little brown bullet。 but here is interesting because。If you。

From this state， if you decide to go to the pub， then you go to an immediate node。

 it iss not a state， and the environment can throw you in one of those three states with those probabilities。

 so this is a stochastic environment， all right。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_313.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_314.png)

O。嗯。That's it。 And then once you studies absorbs it， nothing happens there。Okay， the square。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_316.png)

那。Let's discuss about this mark of property。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_318.png)

啊。Markov means that our our state should summarize all the past experience on the agent。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_320.png)

So that the probability of the future only depends on the current state。

And not on the previous history， we can throw away the previous history。

So all depends how much information you are willing to sustain on that state representation。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_322.png)

For example， if your state wants to be oh， three papers， let's say in CVPR。

 this means that if the one person made a huge effort to get there or a small effort to get there is forgotten you just care about the final state all right it like this is your evaluation right now this is your state now the truth is the following。

😡。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_324.png)

Nothing is really Markov in that sense， but with enough information。

 So if you sustaining enough information in the state instead of putting three papers you saying okay。

 whatever all the efforts that every person has done is also part of the state。

 how many are spent working is part of the state， how many times you go to the movies is part of the state。

 So if you put enough information of the state， Everything is Markov。

 It's all a matter of the information you're trying to sustain。 Okay For example。

 let's see this very simple。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_326.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_327.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_328.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_329.png)

H T P， this is the robot。 It's deployed。 It's trying to pick up this object。 Okay。

 so it's trying to pick it up。 He's moving like this trying to do the right actions。

 But at some point， it's forecast。 either it succeeds or it fails and needs to reset。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_331.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_332.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_333.png)

Okay， now here's the problem。 If somebody is watching。

If you succeed to pick up the object after three， have to say trials， of course。

 you're not going to get reward of 10。 I mean， the person waited for you so long。

 Does this make sense。 So by making this mark is essentially forgiving the fact that you tried again and again。

 And you know what， each time you achieve the state that you are about to grab the object。

 everything is forgotten everything is forgiven and you get a reward of 10， This is not really true。

 All right。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_335.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_336.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_337.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_338.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_339.png)

Second， that goes by in our lives， our lives are short short。

 we all counts and it all discounts are reward to be honest。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_341.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_342.png)

I mean， that's how I understand this thing with a Markov。

 That's another case where things are not Markov。 You're here。You decide to drink or to work。Now。

 if you' are in a good working state， you have high chance of have friendship and be internally happy。

😡。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_344.png)

And if you're here on the drinking state， no， eventually， you know， you die。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_346.png)

And here is the problem。That。嗯。These intermediate states remember how many times you went down to alcoholism okay so these are not equivalent if you decide to put the states as one in me so the person went in a good working habit it's okay no it's not okay whatever you have endured is there and should be remembered so the more states you have and the more diverse and the more information to keep in that state the more you you know model reality better and the harder of course is to learn to act because then you cannot how to say make the state understand that the state is similar to the state if all states are dissimilar there is nothing to transfer across your states So it's all about future learning is all about understanding what in this state is important and should be remembered and what is not important should be forgotten so that I can transfer information from another state that is different in the you know no matter what it is factors and similar and the important factors okay now unfortunately because here we somehow。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_348.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_349.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_350.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_351.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_352.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_353.png)

were given the states， all these important questions are kind of gone。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_355.png)

For the first lectures of the course。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_357.png)

Andhow， so these are MDps and why we care about the MDps。

 Well MDP are very simple set of state set of actions， we have the dynamics。 What we want to do。

 we want to solve the MDP， which means what I want to find the optimal policy。

 which means what I want to find okay the distribution of our actions given every state so that I maximize my expected cumulative reward。

 my expected return， Allright and these。Vue functions will help us to do that。啊。Okay。

 so what is a value function， Well， a value function。And given a state。

 it tells us how good is this particular state， Okay。

 how good will be the expected equivalent that we， the agents will。

Encounter if given the state will continue using his particular policy。 That's why the action。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_359.png)

The state value function and the state action value function are parameterized by the policy P。

Because they depend on the policy whenever you see the star means that is the independent of the current policy pi okay is the best possible you know expected cumulative reward。

 you can get from the particular state or state action pair and they're all possible policies Allright。

 now of course you understand why these are important all right from the way we hear them because if you have estimated already the V star and the Q star。

 you can straight away use them to choose actions okay。And this misestimate your optimal policy。好了。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_361.png)

Now we will use so yes， prediction is we want to estimate the state and state the functions control is we want to estimate the optimal state and state action value functions and we will use those lo letters to denote mathematical expected quantities and the capital wants to denote estimation。

 the actual estimation of those quantities。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_363.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_364.png)

So why we use expectation in the first place。What is stochastic and we take expectation across。Well。

 a lot of things are stochastic， your policy can be stochastic， The policy pie in the first place。

 and this goes for the first two because those are dependent on the policy。

 your dynamics are stochastic。 We're going to end up in the next set the wordss are stochastic， okay。

 which are part of the dynamics。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_366.png)

O。啊，收。Value functions are expected， returns。The state value function is the expectation under the current policy of by return。

 given that on the corresponding state S。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_368.png)

And。😊，The option value function is the expectation under my current policy or my future instead third。

 given that I the current state and I take the corresponding option。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_370.png)

And we said that star means optimal means maximization across all policies。

 so these are the very simple connections between expected value functions and optimal value functions and expected action value functions and optimal action value functions。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_372.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_373.png)

State action， sorry， state action value functions， okay。We just take Mac。

 So we we'll go on those you know， a lot of details。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_375.png)

So， value functions are expected returns。嗯。Here are all the definitions。

 V P Q depends on the policy of the agent。 Alright， and in the expectation， there is the policy。

 which means there is schistic caused by the actions you choose that Q star。

 the V star and Q star do not depend。 In fact， theres a max over all policy， okay。Now。

 why we care about value functions， Because this is exactly what we care to maximize。AV functions。

State value functions and state action value functions and code knowledge of the agent。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_377.png)

And there is a very big distinction between these instant reward。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_379.png)

And the value functions， value functions are distilled knowledge that somebody acquired by interacting the world Imagine a young professor that doesn't have any experience and has the spontaneous reward of getting pleasure when it has a very long conversation with the students with the students and then imagine mature true professor that says。

 you know what if you spend too much time with the students。

 I have seen that you know the expected returns， the long-ter returns are not great。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_381.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_382.png)

Especially you waste time on know maybe reading papers or writing proposals， et cetera。

 you better minimize this so the knowledge that humans transmit across each and agents will transmit across each other are state value functions and state action value functions what I have seen in my experience okay of course using my current policy that you know has been the trend of you know following those instantaneous rewards does this makes sense and we'll see how you know essentially value functions are propagated rewards and we'll see it in this particular example here is a great world。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_384.png)

There are two states where you get a lot of reward， plus 10 and plus 5。And all the others。

 there is nothing， you don't get any reward。All right。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_386.png)

那。If you estimate the state value function。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_388.png)

Now， for a reprobable random policy， a policy that with the same probability jumps to the left to the right。

 up and down。This is what you get。 You see that the reward has been propagated to the neighbors essentially knowledge is propagating those false rewards in time earlier and knowing that。

 oh， if now I go and play with Facebook， I know that eventually thiss not going to turn up well right so the people that are very good on。

You know the wise people， the people have knowledge are those that disregard spontaneous rewards and look at their value functions right and the even wiser people are those that did not interact themselves with the world to figure it out but rather look at other people and look at their results so you learn from the mistakes and the successes of others so you don't need to yourself suffer。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_390.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_391.png)

Okay， so， and in fact， I'm going to add in the resources an excellent paper from， you know。

 research Saturn that says exactly this， how we can encode the knowledge about the world into many。

 many， many。State value functions and state action value functions。All right。Now， if I want do。

Let's say we had an excellent question。 and Tom follow up about how the agents should you know。

 give you information to each other。 I mean， me， once you give me your value function。

 I would also ask you， okay， what policy have you been using How many times you have to try this to know what are your set and the estimate behind this state value function。

 right so that I know how to mingle it and how to say combine it with my knowledge and my current value functions。

 Okay， so value function such a propagatory words in time， Great。

 we will see the exact dynamic programming solutions in the next course。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_393.png)

So， this is。This is the expected value function。 and this is the optimal value function。 Okay。

 this is the V star that does not depend on the police， but this is the best you can do。

So let's see why we star。 it's important because once you have V star。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_395.png)

Wwhichch essentially says from this state， what is the best return okay that I can get under any policy then if you're in this state。

 for example， okay， you want to say， how should I act。

 how should I act look at the different actions you have look at your actions set。

 look at the resulting states and what is the restart and based on this just pick a policy that essentially you know based those here all of these three are the same So you have equal equal probability of going in all possible directions Allright。

 so from this star， you can rid off a policy of how you need to act。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_397.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_398.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_399.png)

Now， the important thing you need to keep in mind is that to do that。 essentially。

 we said to solve the NPT to come up with the policy from this star。 you need one step look ahead。

 I'm in a particular state， I need to say， okay， if I take this action。

 what's going to be the resulting state So I read off it this star and see if it's higher when that particular action so I can do this one So this look ahead means that you know the dynamics。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_401.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_402.png)

Alright， you know the dynamics。 So this is a problem when we assume that we know the dynamics。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_404.png)

Now， you Sir。It's even better。 Okay， if you have it。Why， because from Q star。

 if you have the value Q star， you can go directly to the optimal policy without doing a look ahead without doing the dynamics right that's why Q is called model3。

 you can rid off the test， you say okay。A probability of star is the best the optimal policy for a particular action as well。

 if width action is the artifacts of my two star escoma alpha， all right？



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_406.png)

Q star Es coal tells you what is the best return I can get。

 especially when I can get if from this state I do this action。

 so if you have always values for all the actions， of course， for a particular state。

 you can just take a maximization across them and you're done This is not clear how very simple from Qstar。

 you can go to you know your optimal policy， essentially mapping of the state to the action。

 that's the policy versus if you have only the V star， you need to do one step look ahead。

 we need to know how the states are related to each other， given the actions。

 you need to know the dynamics。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_408.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_409.png)

Okay。All right， so now let's see how。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_411.png)

Since we know and they're very useful， as we said， all these value functions how we're going to estimate them。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_413.png)

Well， the important thing to realize is how returns of different time steps are related to each other a return is this expected discounted reward。

 this taal R， by the way， are random variables， the lowers is this particular instantis， all right？

So here are random variables。 Now， if you take this gamma outside。

 what you see is that when we up is the return of the next time step。

 So the return in one time step is the immediate word。 Okay， whatever it is。 plus。

 the discarded return on the subsequent time step。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_415.png)

It very clear， very simple， right， do you agree？So this means that if I take expectations。

 the expectation under a policy。Of this particular GT random variable， my returner。

Will be the immediate word plus the the value function of the next time step。

 you see we have a recursive relation now between value functions on states or consecutive time steps。

All right。RightThis is the definition by that this is the state by function by definition。

 So we just substitute。啊。In the relationship of the returns。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_417.png)

Now one thing which I find confusing and that's why I'm going to tell you when you see Epsilon pi。

 this expectation is not just of the policy， expectation。

 there's also the dynamics and whatever is schastic about the environment， okay， makes sense。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_419.png)

Great， so now we come up with these very nice recursive relationships between then state value functions。

 which is going to be used to estimateim those。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_421.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_422.png)

O。Let's see what has been inside the expectation。Here this。Yes。

 we do that have to say the policy is stochastic so it will be a sum across the actions。

 but here is also the transition dynamics the dynamics are also stochastic so you need to sum across all possible future states and future words。

 all right。So if you want to take out the Eps pie to the expectation operator。

 essentially that's how this is the relationship we end up。So what is this， You have one such。

Equation for every state。 so far， we said that we have a small number state， let's say1。 All right。

 what is this equation， It's essentially just a linear equation。

 You have a system of linear equations and you can just solve it。

 and this is how you are going to end up having the state body functions right if your state set is small enough。

O。These are just numbers this probability big deal of actually give the state。

 probably you have the next state and R， you just can anumerate those。

 everything is very reward you can imagine that has a few discrete values and that's it。

 the state also have this one of a small number of state set， so you just write down the equation。

 the set of equations and because there are very few you can just hold the linear system。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_424.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_425.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_426.png)

No。Because it seems to be confusing， let's see how this sum exactly can be read by looking at this diagram。

 you remember earlier that we were showing the MDP examples。

 we would see circles which are the states and dots which where you end up was we take an action right so here is the state。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_428.png)

You take an action you add up in the black dot， and then the srcastic of the environment kicks in and sends you in different states and emitids corresponding rewards。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_430.png)

Correct。对。So now what we're seeing here， what thisson relationship says is that the state value function up there in the white circle essentially is the expected sum of whatever you're going to find in this bottom circles。

 all right。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_432.png)

信一次。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_434.png)

Given the initial。Circle on the state， you have a probability distribution of all actions here。

 you only see two actions but can con they you have three or four actions going to be four different branches。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_436.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_437.png)

So you multiply with the probability of every branch。

So you'll take the leaves and each leaf will have particular word and then you sum those rewards。

 multiply with the probability of reaching the particular leaf that's what it is very simple。

 so let's see what's the probability of reaching a particular leaf well is the probability of taking that particular action here we are and the probability of the environment sending you in that particular state and emitting the corresponding rewards it。

O。So you take a word that sits on the edge。You also consume the value function of the re leaf。

 but don't forget to put the discounted factor。All right。所我就是。Some across， you know。

 the values of the list。Plus， the words that you get along the way on the branches。偶然。O。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_439.png)

Let's see the similar backup diagram， not for state value functions。

 but for state action value functions。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_441.png)

You' are sitting now at the black node。 This means you've already taken an action。

 you're seeing at a particular state comma action。 Allright。

 this means that now the environment will emit every word。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_443.png)

Scastically and will also send you in a particular state。Allright。

 now you see the reward there being R as a scholar， you can imagine that the reward may have。

 let's say three different values， it can be know sum of those three with some probability there all right of your dynamics。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_445.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_446.png)

Then sitting on this new state is again， you can choose an action and now you are coming back to your black node。

 you are in the situation that you're in particular set an action。收。

The value at the original dark node is the words that you received during the branches plus those that you're going to receive。

Longter continuing to act from each one of those black node to etity or to the termination of your episode。

 Okay， So here it is the reward that you get on the branches plus the probability of reaching each of those different leaves will multiply with the value that you're going to get from that leaf and the value is summarized there on the Q function。

 This is the beauty of the Qq function。 The Q function summarizes your future for every state or state and action。

 depending if it's a state value function or state and action value function。 Allright。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_448.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_449.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_450.png)

So once you have done this you know propagation， backward propagation of the reward to all the states。

 then the value functions is all you need and you're going to act greedily with respect to that value function you have optimal policy it's greedy because the value function already summarizes the future for you。

 it already tells you that from that stage if you move on。

 this is going to be your expect cumulative reward， all right， yes。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_452.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_453.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_454.png)

This is my mistake because this was different from a different book。

 and I update this based on the current book。So。This needs to be around or E。

 or I need to put it inside the sum and put s primeamma， R， b， the we work。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_456.png)

I was trying to hide and。就能这知道。第 is是分데。嗯，哼。😊，Okay， so these microograms are very comfortable because they let you to do all the connections between the value functions and the state value functions here you're in a particular state you you end up now in this cumulative return right in the beginning you haven enacted。

 So this state value says okay this is if you follow this particular policy p that's going to be your expected cumulative return and here tells you given also you took this action what's going to be your expected cumulative return and here is the again connection between the two values again。

 the probability of every branch and the value of every branch。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_458.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_459.png)

Okay。诶。Make sure there's no reward that there。 The reward is going to start right after the black no。

 Okay， that's why there are no rewards there。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_461.png)

Okay， so it's very easy to see how these look like。 Let's look at， for example。

 the state value function and just put it。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_463.png)

The expected state value function had just dump there the equation。

 and indeed you will see that it is it holds for this particular values or this student mP。

 so this value function 7。4 equals 0。5。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_465.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_466.png)

P this is plus 0。5 y， because this is an equilibrium probable policy。

 every arc will be taken with a 0。5 probability。 Okay。

 this is by construction under these policies that you've got these state value functions。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_468.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_469.png)

Allright， and I mean， the first one is easy。 you just take a reward of plus and then that's it。

 there's nothing you're going to take。 there's no cumulative return out of the square。 you're done。

 The other you're going to end up in this node。 Allright， and from this node， you take a。

Expectation over dynamics of the environment we can throw you either here or here or here。

 so you have three terms in that sumation， all right？Plus， they corresponding。

Resulting value functions of the states that we ended up。

 So now instead of having this abstract back a drawing you have grip on this particular endpy。

 Do you see how the corresponding value which inside the circles satisfied the dominant equation。

Okay。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_471.png)

嗯。So I think we saw this already。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_473.png)

No。So far， our backup journalism was about expectation。 So if it's about ex， you just sum。

Now it's about optimal value。 So you take max。Instead of some。

When you're branching based on the action， not when you're branching based on the dynamics， Okay。

 the dynamics still， you have some h， all right。But you're in particular state now and you're about to take an action and you are going this。

で。Optimal return will be there there you get into one of these two branches。

 al right not all of it because you're going to take the best action as opposed to expectation overall okay so that's the only thing that changes。

 you take the max across the alphas instead of sum and you consume the corresponding reward which again you should have been in there and you should be a double sumation over state and rewards with the corresponding probabilities smaller of the state and reward and the corresponding optimal value function。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_475.png)

Yes。コストで。我也。One more time。台。は。然后。H see。 So what you're saying is that is it probable that the word does not depend on the action。

 It just depends on the state that we end up in。Yes， they。そど是れた。さあ。

How old the trees in the boat artist to be face？好好对。Yes， I see your problem。No。

 then the report will be completely deter as。If you know which state and what action and where you ended up。

 right， and then where is spontaneous deter？啊，你。いけるで。Even that。

I mean sure your reward process can be completely for。

 You may have an environment completely nonsens， right。

 An adviser that tomorrow is upset tomorrow is happy independent on how what you're doing。 Oh， yeah。

 it's good。 Oh， no it's but it's completely relevant to。You know， you cannot control the environment。

一。嗯。Yes。This is the state value function， not the state action value function， y through A term。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_477.png)

这个。Cause that's not been caused by it。So like the first part and selecting a over I think this much should。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_479.png)

In the breath。You choose one of the two branches， right？嗯哼。Oh， I need to end。

 Are you really need to end now。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_481.png)

Yes， we talked about this that to go to from V star to a policy you have one to look ahead where from Qstar its the you you don't even need that look ahead。

 the optimal value function is very easy to look from the student MDP is the best possible return youll get from vertical set under all optimal policies what's going to be there of course you jump now you're not conditioned you cannot move because we need to we switch between instructors here right so don't forget about this。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_483.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_484.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_485.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_486.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_487.png)

Let me just say one thing。啊你你想我个姓。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_489.png)

How do we solve those equations， These are linear equations。

 You can just solve them with as a linear system of equations。

 This will never work if you have lots and lots of states。

 We'll see approximations that I will propose in the next lecture。

 And the important thing to know is that this particular approximations take into account the visitation on the states。

 They will say for states that I visit， I want to be much。

 much more accurate states that I never visit。 So this is a particular approximation on this you know。

 state value function estimation， Allright。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_491.png)

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_492.png)

And we will see that other set of like optimal control does not consider this type of approximation。

 consider very different approximations，So don't should we discuss think。你完没来我。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_494.png)

Yes，Yes。So again， what we're trying to do here is again。Remember the other person。

Or Q if the ends to kind of raise it。So the issue I want to raise。えい選府が。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_496.png)

Is what do you think about this model that we just saw？



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_498.png)

Or。あてする。Where one of the assumptions。Is that the external world when you do action？

Gs you a that state plus a reward。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_500.png)

And I want you to consider the possibility that it's the wrong mode。For people。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_502.png)

Because， for example when I。我土弟。It's not because they serve world。きに。We work or something。

 there's actually a nerve inside you。Goes out in my stomach。And when it notice。

is they bothering my brain。千人でいる。正いです。And when I eat， then it stops doing that。

And so I would suggest that。Here is an example。Where the reward is not being administered by the outside the world。

And。It's actually inside my body。And I think it's an interesting question to consider because it's really a foundational assumption we're making。

😊。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_504.png)

呃In as we。So I just want you to think about。

![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_506.png)

For example。呃。ive you other examples where it's not a nerve in my stomach。

 but it's a nerve in my head that's sensing my mental。So can within my brain。

And what are the implications of that？There kind of。Learning， say it sub quotes。

 the goal of evolution。giving us through。Instead of the external world。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_508.png)

Having been frozen out。今日？And there's a whole set。Philosophical， but also important。Issue is。

I just want to you all to think about okay， shower time。



![](img/2ecc84ab8d2caf164c6a5ecd8f66917c_510.png)