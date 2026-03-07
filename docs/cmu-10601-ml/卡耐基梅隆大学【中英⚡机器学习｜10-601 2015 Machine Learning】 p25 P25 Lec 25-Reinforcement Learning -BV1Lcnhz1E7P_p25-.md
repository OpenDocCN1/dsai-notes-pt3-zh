# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p25 P25 Lec 25-Reinforcement Learning -BV1Lcnhz1E7P_p25-

About。Reimforment learning。 So this is a very different type of topic compared to what we've been talking about so far。

 and in particular。It's different in the sense that the decisions will make will be about what actions to take so for example。

 this is useful for robot navigation right the robot has to take certain actions to go in certain directions right so in reinforcement learning the decisions we make will be about what actions to take。

And these， when we influence what examples we see next， what state of we are in。

 So our decision influence what we get to see next。

 which is a bit different from say supervised classification of things that we've been talking about so far。

 Okay， and also So what decisions are gonna influence the next example we see And also our goal we' not necessarily be to just do some prediction like。

 for example， there is a door in front of us or not。

 but wed also want to be able to decide what to do what action to take。 Again。

 in which direction should the robot go。 Yeah， So that's kind of interesting。

 different type of machine learning problem。 And you know to talk about such problems。

 we're gonna use something called a model called Markov decision processes that I'll define in a bit。

😊，Okay， so。Right， and actually， a very cool aspect of this topic。 right。

 a very cool aspect of this topic， actually that is that we have delayed feedback。 and in particular。

 the main impact of our action not gonna come right away。 But instead it could come much later。 Okay。

 just as toy example。 So imagine that we have a robot moving in this。😊，Gade over here。

 So we have 6 cell grid。 right， want you to have a robot moving in that6 cell grid。 Now。

 if the robot is， say in this。😊，Sell here on the upper。I guess upper left。 Yes。

 when no matter of action， our robotics。Other if the robot size to go down or to go to the left。

 his the order will be 0。 No here has only two actions you can take in that position， right。

 if I'm in this position over here。This one here， I can only go down or I can go left right？

 And in both cases， I get reward of 0。 However， if I go to the sorry I said left。

 it should have me right。 Yeah， I can either go right， I can either go down or to the right， right。

 But if I decide to go to the right， it's good because I get closer to my goals because let's assume that the goal is to get into this state G over here。

 That's the goal state， right。😊，And so and as you see if I once I enter that state I get a reward of 100 right so basically again this is a simple example showing that in reinforcement learning。

 the main impact of our action is not going to be right away。

 but it can be in the future right and so like。😊，I give us example here。 If the property is here。

 he can no matter what actually he decides to do now， He gets a reward of 0。

 but one of them gets him closer to its goal。 So we're gonna get a big reward。 Okay。

 or as another example， if reinforce learning is used for helicopter flying。

 And so in helicopter flying a bad move and necessary unnecessary crash。

 the the helicopter right away。 but it can lead to a sequence of really bad moves that will result in a crash。

😊，Okay， cool。So that reinforcement learning。 And just because I have this picture over here。

 So one of the main ideas the reinforcement learning somehow and we see in the lecture is like how how do actually So how to actually act or how decide to do next。

 What policy should we take。 One of the main ideas here is to somehow define something called a value function to somehow be able to come up with some for each state to come up with some number。

 which would be kind of the optimal discounted reward。

 if we have optimally from that state from when we went on And then somehow it turns out that by then being really of respect to these values。

 we're gonna be able to to act optimally we will become much more concrete in a bit。

 but just give you some high level idea about the type of algorithm well be talking about。😊，Great。

 and just to， in terms of applications。 So I mean， some， some obvious ones are like robot navigation。

 That's an obvious application。 But there are other another application。

 but a really cool one that made personal learning really popular。 It's playing games。😊，Okay。

 and in particular， Jareta Zro from IBM Chi is my friend。 So in 95。

 he had a nice application of reinforcement learning for playing back gamon。😊，Okay。

 and so in this case， we so here the。😊，Basically the states or the learning task， right。

 So we have a state of the board， like this one here。

 And when the learning task is to decide which which state moves to next， right And but clearly here。

 So this is we get no immediate reward for doing so。

 but the real reward comes at the end of the game or we win or lose。😊，Right，So it's again。

 delayed feedback。 Okay， and it turns out that Jerrytazaro used reinforcement learning together neural network to。

 to come up with a game playing technique for this game。

 And it turned out that it was competitive with the human players。 It is kind of cool。😊，Okay。

 so it shows the power of these techniques。Okay， cool。 so right。 So that's the outlines。

 So we're going to talk about a little bit about the define the problem formally。

 We're going talk about MP， a model that will allow us to model these problems formally。

 And when we'll talk about learning procedures in within Mps， okay。😊，Okay， so here is formalism here。

So。The formalism is as follows。 So we have an agent that lives in some environment。

And the agent is at any moment in time in some state， Right？ So it would be， for example。

 a robot and the robot maybe has some goal， maybe to。

 I don know to open a door to deliver some pizza and so on， right。

 And then so the states the robot could be in is right， state。

 in that case would be where the robot is。 or direction is a pointing to and so on。

 but could be our state。Or in the vacuum on。Playing game。

 then the state would be just which state of the board are we in， right。RightSo basically， again。

 the setta is we have an agent and the agent is in some state of the world。

 right And in any given state， the agent could take an action。😊， for example， if I'm in state a 0。

 I don't have my point me either。 but good。 So if I'm in a state as 0。Right。

 when the the agent could take the action， a 0。For example， some action is 0， right。

 And then when it takes the action， the robot gets to see some reward。

 maybe gets to see the reward are 0， right And when it enters another state state say state is1。😊，啊。

When decides to do another action， say I start speaking some action A want， get through or Dar on。

Then enters another state， potentially in a probabilistic manner。

 because maybe they want to take an action。 The next state could be a probabilistic function of the current state and the current action。

 right， And then so again， our robot is maybe state one action they want get order one enter another state2 and so on。

 Right， So just the agent operative in the world。😊，Okay， and then the goal， from so the setup。

 when what is our goal we doing learning， the goal is to somehow get the robot to choose action to maximize a long term discounted word。

 Okay， there are multiple goals。 But for the lecture today， we're gonna focus on one specific one。

 And that's to maximize to when the robot， the robot wants to choose actions so that he maximizes his long term discounted word。

😊，Okay， and what what do I mean by this， I have a discount parameter gamma。

Can think about gamma being 0。9。So it will be my example throughout the lecture。

So let's think about Gamma as being0。9 and。Right， or the robot once？Is to。Right， to。

Maximize the long-ter discounted reward。 And what do you mean by this like so what is the long- discounted reward。

 So if the sequence of actions that we do is this one over here that I was just describing right so instead a 0 do action00 and so on。

 this one interstate s do action I want get reward R around and so on right if this R is a sequence of rewards we observe。

😊，Or we get then the long term discounted reward discounted by discount factor or gamma will be this expression over here where the reward we get immediately in the very first moment is R 0。

 when the reward at time 1 is discounted by gamma。 The reward at time to is discounted by gamma squared and so on。

 right， So in general， the reward we get we discount the reward we get a time T by gamma to the T。😊。

Okay， and what I say this because recall the reward is sorry， gamma is the number between 0 and 1。

 right， So as the time goes on， I put less and less weight on the reward。

 I get a time T T S becomes larger and larger。 So wanted to think about this objective is that actually。

 we do want to get a lot of reward， right， But we care more about the reward we get immediately。😊。

RightThat's what long term discontinu art captures。Okay， so what's the problem set。So， I mean。

 but basically， this slide pretty much almost defines the problem。 Okay， so we have an agent。

 the agent。 there is okay， actually， let me make it even more formal。

 I think we what I'm gonna on the next slide。 Good。

 So just to be totally clear in this model we have， yes。😊，Yeah， it's an input。

