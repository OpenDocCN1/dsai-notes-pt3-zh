# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p14 P14 通过自监督世界模型进行探索的规划（论文解析） [BV1o3xLznExj_p14]

Hi there。 Today we're looking at planning to explore via self supervised world models by Ramanan Sear Ole Ribkin。

 Costas Danels， Peterre Ail， Danija Hfner and Depaak Paak。



![](img/baf82a5b7956cc2092feb958482b2433_1.png)

So this is a paper that concerns reinforcement learning and specifically sort of self supervised reinforcement learning。

 so what do they mean there's a graphic right here。



![](img/baf82a5b7956cc2092feb958482b2433_3.png)

![](img/baf82a5b7956cc2092feb958482b2433_4.png)

In reinforcement learning， usually you have an environment and an agent， right。

 So you have this environment。

![](img/baf82a5b7956cc2092feb958482b2433_6.png)

And let's ignore the without rewards for now。 And do you have the agent？

And the agent needs to interact with the environment in order to achieve a maximum reward so the reward is given by a certain task right you have to do something in this environment in this case they consider these these types of tasks where I think the top task might be called run forward so your reward is more the further you go with this walker and。



![](img/baf82a5b7956cc2092feb958482b2433_8.png)

How you can influence the walk is you can sort of give a bit of force onto its joints right here and you have a bunch of sensors。

 so the main task is actually to keep it to balance it on its feet and then sort of walk forward such that it never falls over otherwise you get negative reward。

 you lose。

![](img/baf82a5b7956cc2092feb958482b2433_10.png)

So in this case what they want to do is they want to say， wait。

 if we just train a reinforcement learning agent for each of these tasks individually that will use a lot of data and basically we can't reuse the learned reinforcement learning agent for each of these individual tasks。

 it's sort of like if you have many you know image tasks or NLP tasks。

 you don't want to learn one model for each one individually。

 but you might do something like a common joint pretraining and this is exactly this for reinforcement learning。



![](img/baf82a5b7956cc2092feb958482b2433_12.png)

![](img/baf82a5b7956cc2092feb958482b2433_13.png)

![](img/baf82a5b7956cc2092feb958482b2433_14.png)

And it's even called self supervised， right like we are used to in the in the classification setting。

 selfsvised learning。 What does it mean， So it means that at first you're in an environment without rewards。

 So basically the agent is just dropped in an environment and there's no rewards。

 It can just do actions and observes states from this environment。



![](img/baf82a5b7956cc2092feb958482b2433_16.png)

![](img/baf82a5b7956cc2092feb958482b2433_17.png)

And。After that， after a while of that， then the tasks come in， so task A。

 task B and task C are three different tasks all in this same environment。

 but all requiring the agent to do different things like running forward or running backwards or do a front flip or things like this。



![](img/baf82a5b7956cc2092feb958482b2433_19.png)

![](img/baf82a5b7956cc2092feb958482b2433_20.png)

So the how fast the agent can adapt to these individual tasks very much depends on what it has learned during this phase where there were no rewards。

 right， So the agent is tasked to just explore the world via what they call here task agnostic exploration to explore the world。

 to learn something about the world in order then to generalize。To these tasks。And in their case。

 they learn this global world model， so the agent is supposed to learn somehow how the world works。

 right？

![](img/baf82a5b7956cc2092feb958482b2433_22.png)

And this is。

![](img/baf82a5b7956cc2092feb958482b2433_24.png)

This is the way that this agent is then able to adapt really quickly。So in essence。

 what does this agent do， The agent works as follows。 It gets an input observation。



![](img/baf82a5b7956cc2092feb958482b2433_26.png)

And it runs that through an encoder， which is usually something like a convolutional neural network。

 and that will give you a set of features right So this is sort of an embedding of the state that you're in。

And that you can incorporate into a latent state at time T。 Now， usually in these RL algorithms。

 or what can happen is that youll incorporate the last latent latent state。

 So the latent state from the step here also goes into the latent state of the next step， right？

 So here was the， sorry， the last observation observation comes in features， latent state and so on。

Ultimately， and then， and so on and comes in from here。

 And there's usually like an R and N going over the time steps。



![](img/baf82a5b7956cc2092feb958482b2433_28.png)

![](img/baf82a5b7956cc2092feb958482b2433_29.png)

![](img/baf82a5b7956cc2092feb958482b2433_30.png)

![](img/baf82a5b7956cc2092feb958482b2433_31.png)

But ultimately here， the agent has to decide on an action using this policy network。

Now how is this trained， this policy network it has to come up with an action。

 but there are no rewards， so usually we would train this policy network with like an actor critic method。

 so we would also train some sort of a value function and then the policy would try to maximize the value function and but if we don't have rewards how are we going to do that？



![](img/baf82a5b7956cc2092feb958482b2433_33.png)

![](img/baf82a5b7956cc2092feb958482b2433_34.png)

![](img/baf82a5b7956cc2092feb958482b2433_35.png)

So people have thought about this for a bit and people have come up with things like intrinsic motivation。

 intrinsic motivation is a term where you're trying to say something like if you're in a room right here。

Like this， your agent is right here， then you just you know， you do something。

And maybe your agent goes down here。If your agent were to go down there again。

 it would sort of not really learn anything because it has now already gone there and is already learned from those states。

 so you might want to explore some different space right like here。

And in the next episode you might want to explore this room right here。

 so this this notion of intrinsic motivation to explore。

 it has a bunch of different formulations of how exactly you can formulate it。

 but just imagine basically the entire state is filled with a bunch of coins and I'm going to draw this as green dots。

Sosr of like packman and。Everything is filled with these green dots， right？

And what the agent wants to do if it has no rewards。

 it will simply collect those green dots and once one is collected。

 so if I go here I'll collect all these green dots。

 these are now no longer there right so that area doesn't give me any reward anymore so you can imagine sort of like this。

So as an intrinsic reward， you simply reward the agent every time it finds itself in a new state that it hasn't seen before。

 so you train it to seek out novel states。Now usually when you just have like an actor critic method and that's what this paper here criticizes if you have it's called retrospective novelty。

That means if you train a Model 3 algorithm， which is an actor critic。

 right if we just plug in in to hear something like A3C。That will simply。

Have a policy and a value function。 and in this case， if we train it on intrinsic reward。

 policy will simply tell you where to go to find more green stuff。

 but you can only train it so you use this to run an episode。

And then you observe how many green things you found in that episode， right。

 if your episode goes here and then you put that back into your buffer to learn from。

 But at that point you've already collected the green things， right so。

The reward signal is actually a bit off， because。You'd want to train your agent that theyre that it should seek out novel things。

 but as soon as you've explored them， they're not really novel anymore because you have now explored them。

 but still you're gonna train your agent。Telling your agent that this area right here has lots of has given me lots of rewards。

 So the agent' is gonna be encouraged to repeat that。They， they say this right here。

 the retrospective novelty model free exploration methods not only require large amounts of experience to adapt to downstream tasks。

 they can also be inefficient during exploration。 These agent usually first act in the environment。



![](img/baf82a5b7956cc2092feb958482b2433_37.png)

Collect trajectories and then calculate an intrinsic reward as the agent's current estimate of novelty。

 This approach misses out on efficiency by operating retrospectively。 That is。

 the novelty of inputs is computed after the agent has already reached them。Hence。

 it seeks out previously novel inputs that have already been visited and would not be novel any more。

 Instead， one should directly seek out future inputs that are expected to be novel。Now。

 so what this paper is doing， it's basically saying。

 can we build a model that estimates the future novelty of a state that we maybe haven't seen so far？

And here is where that goes。

![](img/baf82a5b7956cc2092feb958482b2433_39.png)

So what do they do in this policy， so the policy isn't just trained to maximize the novelty in the world instead。

 sorry， it uses planning。

![](img/baf82a5b7956cc2092feb958482b2433_41.png)

It uses planning in latent space。 So what this model does is it。



![](img/baf82a5b7956cc2092feb958482b2433_43.png)

Learns a world model in latent space。 The world model takes as input these features that you saw right here that the encoder gives you。

 and it predicts the future hidden latent states。 These are the things you saw here。



![](img/baf82a5b7956cc2092feb958482b2433_45.png)

![](img/baf82a5b7956cc2092feb958482b2433_46.png)

![](img/baf82a5b7956cc2092feb958482b2433_47.png)

So these things that are always made by。