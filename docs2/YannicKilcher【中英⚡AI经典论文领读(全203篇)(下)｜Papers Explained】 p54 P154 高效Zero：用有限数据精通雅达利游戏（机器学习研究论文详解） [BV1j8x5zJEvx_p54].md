# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p54 P154 高效Zero：用有限数据精通雅达利游戏（机器学习研究论文详解） [BV1j8x5zJEvx_p54]

Hi there。 Today we're going to look at mastering Atari games with limited data by Wajrue Shahua Liu。

 Taahhar Pirabil and Yang Gao。 This paper presents the efficient0 model。

 which is a model that can do reinforcement learning with severely limited data。

 So the paper tackles the Atari 100 K benchmark， which means to Atari the Atari benchmark as a reinforcement learning task as for example。

 deep Q networks did， but you only get 100 K transitions。

 This is about it's about two days worth of realtime data to work with。 And after that。

 the model supposedly be able to play Atari So this is a variant on mu0 mu0。

 which is an insanely data intensive reinforcement learning algorithm。

 and it introduces various tricks and at various amendments to mu0。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_1.png)

To make it more sample efficient。So when we look at this paper you can see the gist of it right here。

 if you do this Atari 100k benchmark， you can see that a lot of the other reinforcement learning algorithm。

 they fail to even reach human level performance whereas this new algorithm outcompes not only the other orL algorithms in this low data regime。

 but also the humans here they say。

![](img/5e0f4d2e7404408ba96b3802a8239ad4_3.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_4.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_5.png)

Efficient Ze's performance is close to DQN's performance at 200 million frames while we consume 500 times less data。

 efficientic zero's low sample complexity and high performance can bring RL closer to real world applicability。

They even say we implement our algorithm in an easy to understand matter and it is available at this GiHub address。

 so this code is out there， especially if you want to do reinforcement learning。

 but you don't have as much computer time or money this might be for you so we'll go through the paper we'll see what the improvements are there's not a single improvements there are many improvements three big ones to be exact。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_7.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_8.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_9.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_10.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_11.png)

And yeah， if you like content like this， don't hesitate to subscribe。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_13.png)

And tell your friends and family and professors。

![](img/5e0f4d2e7404408ba96b3802a8239ad4_15.png)

I guess。Alright， so we'll first take a small look at what mu0 does just as a recap。

 I have done a video on mu0， but if you haven't seen that then here is a short a very short introduction to mu0 to the algorithm so in a classic reinforcement learning setting。

 you have your your basic setup of you have the environment。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_17.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_18.png)

And you have the actor and the environment gives the actor some sort of an observation at time step。

 let's call it T， the actor uses that observation to come up with some sort of an action at time step T。

 and then the environment gives the actor back a reward for that time step and the next observation。

 T plus1。And that goes on and on and on。 So the question is。

 how is the actor supposed to come up with this action right here。

 given the past observations that it has seen from the environment in order to maximize all of the reward that it gets。

 Now in a regular reinforcement learning algorithm or regular let's say in the simpler reinforcement learning algorithm。

 what people are doing is they're doing model free reinforcement learning。

 which essentially means that they take the series of observation， observation 1 observation 2。

 and so on that they've seen so far， they take that。

 they stick it in a big neural network and they train it to output some sort of an action。

 and they train the neural network in order to maximize this reward right here。

 usually using some sort of of policy gradient or something like this。

 So this is a rather rather direct way， we call that model free reinforcement learning because you directly predict the action without。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_20.png)

Without an explicit model of the world， now when you have a model of the world。

 so when this environment here is well described， for example， a chessboard in a chessboard。

 you know the rules， you know everything that's going to happen in a chessboard。

 you can use a model of the chessboard。

![](img/5e0f4d2e7404408ba96b3802a8239ad4_22.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_23.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_24.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_25.png)

So what you can do is this， you can take these observations and these observations would correspond to some defined state。

 or let's， let's say tick ta to。 Tto is a better example。 So， you know， with the observation。

 I can actually construct the board of T ta toe that I'm in。

 And then what I can do is I can actually search。 So I can try out， I can say， okay， what if I put。

 you know， something here。 Oh then my opponent's certainly gonna do that right here。

 And then what if I put something here。 And then my opponent is gonna do that and then they win right。

 So that is one。That is one way to do it and usually you visualize this as a tree so you are here at a root note that's your state and you have several options to do things and in the several options your opponent has several options or if it's a one player game you have several options again and so on so what you want to do is you want to search this tree for the best possible path and this is what things like Al go Al0 and so on did。

They have these explicit model and they search through it and now the neural networks no longer predict actions directly。

 the neural network help you search through that tree。

 which means they vote essentially on which paths of the tree to explore because the tree quickly becomes too large to explore as a whole you can't like if it's more than three moves ahead the possibilities just get giant。

 even like especially in a game like go So the neural networks are here to guide the tree search and that was in general。

 the techniques of that center around the Monte Carlo tree search because at some point you abort the search and you simply play one game to the end as sort of an approximation of what happens and so on I'm not going to go into that superduper right here but what muzero does is muzero says well this whole tree。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_27.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_28.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_29.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_30.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_31.png)

Research stuff essentially only works if I have an explicit model of the world。

 such as the take ta toe board is clearly defined how it works， right， Also， I can I can have。

 I can have have a simulator for it。 I can rewind， I can try again。

 This doesn't happen when you're interacting with any sort of。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_33.png)

Real world thing， let's say， or even the Atari benchmark。 So in Atari， I know there is。

 there is hacks where you can save the rom and so on。 But essentially。

 you're not supposed to go back in time or go forward in time。

 You're not supposed to be able to try something out and then say， well。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_35.png)

Now that didn't work I'm going to search for a different path in the tree instead。

 so what people do is they try to learn a model of the environment。

 so in absence of the model of the environment they try to learn one and there are many。

 many different ways of doing this and what muzero does is it learns a latent model of the environment。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_37.png)

So how does that look so here you have the current observation observation T what mu0 does is it uses a neural network。

 I think they call this H or something to get this into a hidden state。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_39.png)

So they map the current observation into a hidden state。And then they plan using the hidden state。

They plan， they say， okay， I'm not going to predict what the next observation is going to be。

 like in the Ttac toe board。 I'm only going to predict what is the next hidden state going to be T plus1。

Table is one， like this is one。 This is 2。 This is。re。So you know depending on which action I do。

 which which is going what is going to be the next hidden state of the environment。

 sorry of yeah of the environment，'s going to be the next hidden state and from that hidden state I always going to predict what's going to be the reward for transitioning there。

's going to be my own policy which is a bit weird that you have to do this。

 but you have to and which is going what's going to be sort of the value and the value is。

What is going to be my future reward when I go from here？

So these are the sort of things that mu 0 predicts。 And with that。

 it is able to search this latent tree。 Note， the addition to mu 0。 sorry， Yeah， the addition。

 sorry to Al 0， which is this run right here。 So we might， we might label this。

 This is something like reinforce。😊。

![](img/5e0f4d2e7404408ba96b3802a8239ad4_41.png)

This is alpha 0， and this is mu 0。

![](img/5e0f4d2e7404408ba96b3802a8239ad4_43.png)

So the difference to alpha0 being that we no longer have an explicit model。

 so in order to do treese we have to learn a model and the model that muzero learns is in the latent space purely it doesn't predict future observations and it only learns all of this from the signal that so it predicts the reward。

 it predicts its own policy and it predicts the future value and those are the only learning signals for the world model。



![](img/5e0f4d2e7404408ba96b3802a8239ad4_45.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_46.png)

![](img/5e0f4d2e7404408ba96b3802a8239ad4_47.png)