# 卡耐基梅隆大学【中英⚡深度强化学习与控制｜10-703 Fall 2018, Deep Reinforcement Learning and Control】 p03 P3 03 Solving known MDPs -BV1RyqPBbEJV_p3-

So today we're going to talk about。Solving known MDPs。

 and I really want everybody to take part the definition of a Markov decision process。

 So this is going to remain here for the entire lecture。

Because this notation that we're using here on this slide。

 we're really going to use that as the standard mathematical notation throughout this semester。

 so you really do want to learn this。And you really want to become sort of when you read this。

 it should be like reading natural language， you know。When you see R of essay， you should think。

 of course， that's the reward for a particular state taking a particular action。

 but for today just to make sure that as a memory aid， we'll leave this up here。Okay， so today。

 there it is， again。

![](img/55b33118c53ab7ca0f17304e99470923_1.png)

So today we're going to talk about solving MDPs， as we talked about before， there is an MDP。



![](img/55b33118c53ab7ca0f17304e99470923_3.png)

And when we saw them really， what they really means is there are two kinds of questions。

 generally speaking that we're interested in， one of them is given an MDP defined by those five things。

嗯。And a particular policy。呃。Predict the value。For each state or each state and taking each action in each state。

 So figure out what's the value， the discounted future reward。



![](img/55b33118c53ab7ca0f17304e99470923_5.png)

For that state。And the other kind of question is， well， what policy should we follow？

That is what pi loopops， what function should we create for deciding for any given state that we're in。

 which action will be the optimal action and will lead us。To the maximum discounted future reward。So。

We're going to still be considering finite MDPs。Words where they are finite。

Set of states that you can be in， unlike this world and also worlds where there are a finite number of actions you can do。

We can generalize these things to continuous states and actions， and we will。

 but it helps to simplify a couple of ways to get started。And so， we'll talk about。

These algorithms called policy evaluation， policy iteration， value iteration。

 and next time we'll get to some dynamic programming things。



![](img/55b33118c53ab7ca0f17304e99470923_7.png)

But first， it turns out I've taught this material before。And it turns out。

We can talk about a very general setting where we have probabilistic actions with nondeterministic outcomes。

 but that are characterized by probability distributions。

 and we have reward functions that are also nondeterministic。

 and we can even learn policies that nondeterministically predict what action to do next。



![](img/55b33118c53ab7ca0f17304e99470923_9.png)

And we will in the end。 But it turns out that if you take on that problem。

The essence of the idea that you need to learn about the algorithm。

Is exactly the same essence of the idea that we can look at if we simplify down to a deterministic world。

 so we're going to start there with actions that have only one outcome if you're in a state and you do this action。

 there's only one outcome if you do this action in a particular state。

 there's a reward that you'll always get for that state action pair。

 it's deterministic and the policy itself that we're going to learn is also deterministic。



![](img/55b33118c53ab7ca0f17304e99470923_11.png)

And you'll see that the ideas that we can develop here will generalize those two。



![](img/55b33118c53ab7ca0f17304e99470923_13.png)

Nondeterministic worlds in， along several dimensions。



![](img/55b33118c53ab7ca0f17304e99470923_15.png)

Okay， so here's an example I want to start。 and I want to challenge you to have some questions along the way about this example。

 But here's a simple world I want to consider。This world has exactly six states。

 You can think of it as a grid world where。There's a robotic agent who can be in any one of these six locations in its world。

What I've drawn here is arrows indicating the actions。 So for robots in this state。

 the outgoing arrows show that it can go east or it can go north。

Those are the only two actions available in the state。

The little 0 here indicates that the immediate reward。That we will receive。

If we're in this state and do the east action will be an immediate reward of zero。Okay。

 so you can see the world basically， you can move north。

 southeast and west as long as you don't fall off the end of the earth。

And there's this funny state here， which I've labeled G。 You can think of it as the goal state。

You'll notice that the only way to get a reward is to enter the G state。That's the only action。

In a particular state that would give you reward。And furthermore。

 you notice that once you're in this G state， the only action available to you is to hover in the G state。

Just remain there for which you get zero immediate reward。So basically。

 this is an absorbing state once you get to that state。

Your life is over except for sitting there forever。Okay， we'll。

 we'll actually talk about training an agent in this world where once they get to the G state wheel will allow reincarnation。

Place them randomly in some other states so that they can get another。嗯。Life experience。Okay。

 so there's a very simple world， and we can use this deterministic。Simple， small world。

To illustrate a variety of ideas that are really the core ideas for。

Policy iteration and value iteration to。Primary algorithms for solving MDP。Okay。

 so just keep in mind， this is all detererministic。So， now。Suppose I tell you yes。

Does the robot know。Yes， thank you。' I should have said that。

 I also assume the robot can perceive which state exactly it's in。It knows the actions available。

 and it can perceive what state it's in。So， in。The parance that we use in the course will say this is a fully observable。

Markov's decision process。Any other questions。Be sure to ask those kind of questions。

 if I say something up and clear， It's important。 Okay， so what， what I've done here is I've just。

Drawn a particular policy in green。嗯。What is a policy， again， a policy， of course， is just function。

Policy is just a function that maps from any given state to the action that you're going to perform。

And so there are six states。 I've drawn for each of those six states， a particular action。

And so those。I guess I could have put a green circle around this in this state you don't really have a choice。

 so the policy will be do the only action available。And so that's a policy。And as you know。

 from the previous lectures。Each policy has a different value function。And so， we want。嗯。

One of the inference problems one of the two problems that we're talking about is given a policy。

 what is the value function that goes along with that policy。

 that is what is the discounted future reward for being in each of these states？And so。

 given some policy pie。Given some policy pi， we want to know what's the value function。

 which means for every state。 What is its value， That's just the expected value of the sum of future rewards。

RightAnd since this is a deterministic world， it just means if we start at time T。

Then it's just the reward we receive at time t plus gamma， times the reward we receive at T plus1。

Plus gamma squared times the reward。 we receive at T plus 2。对对对。Okay。

And suppose for the sake of argument， gamma is 0。9。Okay， so given that。

 if you've been following carefully， you should be able to tell me right now。

What's the value of this state？And what's the value of this state for the policy shown in green？Okay。

 let's make it a question that we can answer as a group。

Which state would you rather me ask the question about this state or this state。

The one on the right or the one on the left。Right， I'm with you。

 It's going to be easier to answer the question for this state because if we're in this state and we follow the policy。

 we're going to take this action。What will be the discounted future reward we receive。

 What will be the sequence of rewards we receive。1000，0，0，0，0，0，0，0。Et cetera。Okay， so。

The value function is just 100 plus a bunch of zeros。

 So I would say the value function for this state is 100， yes。Right， so notice the question was。

 do we take the reward for the state we started from or the one we're entering。

 Notice the reward is actually a function of the state and in action。So we're in this state。

 We take this action， and we will say the reward at time。

 if this is state T and we take this action at time T， we'll say the reward at time T is 100。So。

 that's the。Invention will follow for nailing down the timing。And so therefore， if this is S T。

 our sequence of rewards will be 100 will be R subt， R T plus1 will be 0， etter。That makes that 100。

嗯。Similarly， I guess this， Oh， no， no， no， no。 What's the state， What's the value of this state。

Who thinks it， Who thinks it's 100。Good， nobody。 who thinks it's。9 squared times 100。Right， okay。

 so one way to think about this， the easy way to fill out this chart is just to follow the policy backward。

Now， that we know。This is worth 100。We know that this is worth how much。

Notice we'll get a zero immediate reward。Plus， gamma times 100 after that， right。So地。

What's the next easiest state to fit in？The next one upstream in the policy。

Because if we're here and we do the follow the policy， we'll get a0 followed by。Gamma times 90。

Or put another way， followed by0 plus。Gamma squared times 100。Right。

So you see if we're in this state here。Then our reward sequence will be。

The sum of rewards will be 0 plus 0 plus 100。Plus， zero is all the rest of the way。

And so our expected discounted future reward。Will be。Right， and of course。

 since another way to put this is that at 0。Plus。Gamma。嗯。Plus， gamma times the value。Of。嗯。

I'll just say as prime， the next state。Which is。で。Right， so。

 so there's a kind of dynamic programming thing here， thing that I can do that。啊。

I could add up 0 plus。Gammma times 0 plus gamma squared times 100。 Or I could just say， well。

 I already know this。呃。From here， this is0 plus gamma times 100 is 90， though。

0 plus gamma times this gives me the same answer。 And a lot of the algorithms that we'll use for。

Evaluating for calculating。Value functions。 and for learning here will involve that kind of optimization。

Okay， so then I guess that makes the value of this be。81， good。 Thank you。

 And the value of this to be。72， I guess。Or so。And 66。

And that's the value given this particular policy。Right，Because every value。

It doesn't make sense to ask， what is the value function for this world。

 You have to say what is the value function for this MP and this policy。So for the green policy。

 that's it。Okay， what about the optimal policy。Usually we're going to use the notation。

Optimum policy。We'll call that pi star， as we have been doing。And so we'll say the value function。

For。Pi star， we'll call V star。嗯。So， let's see。What's the value of this under the optimal policy？

100 because the optimal policy obviously includes。That action。

What's the value function for this state？100， because obviously the optimal policy involves this action。

 what about here？90， right。And then here。81， right， because here's an optimal policy。はい。

So my purple policy is one of the optimal policies。 There doesn't have to be just one。

 What's the other one。政ジの？こにどだ。Oh， no， the policy handles no matter what the starting point is。

So if I start you here。The optimal thing to do is to do this。 and then that。If I start you here。

 the optimal thing to do is just go right， just go east。

So the optimal policy covers every single state， a policy in general is a complete function。

From all the states to which action you should do in every single one of those states。

Which is why we always use examples with finite numbers of states， it's hard to write down the post。

The Cap， you see。The purple policy。Recommends one action in each state， I claim。

That is optimal that you can't do better。But I will agree with you that there's a second optimal policy with the same values。

 What's that other optimal policy。Yes。So you can start with anyone。呃。Yes。

 so so here's the second policy。 I erase this recommendation， replaced it by this。

 And then you're saying I also could replace this recommendation by that。

That would be yet another policy。 that's also optimal。

Optimmal in the sense that what does optimal mean。It means for every single state you could start in。

This policy tells you。How。To pick a sequence of actions。That give you the maximum possible。Expected。

 discounted future reward， sequence of rewards。Discounted by gamma。In the future， yes。

That's a great question。 I bet you could prove that yes， but I can't prove it on my feet。

But that's a great。 That's a great。Shower question if you have a steamy shower。Thank you。Yesやス。Yes。

 it will。せ？In fact， now you can see that we could make a nondeministic policy that says。

 if you're in this particular state， then with probability 0。7。

 you could go this way and with probability 0。3， you could go this way。

 and it would still be optimal。So does there're always exist。

There always exists in optimal policy for every MDP。There always exists。嗯。An optimal policy， and。

There always exists a value function over the states。That you can use。

To calculate the optimal policy just by greedily following the arrows toward the highest value。Like。

From here， we， if we wanted to greedily follow， our possible actions。

 There are three possible actions， then we should either go east or north， but we should not go。West。

And so in that sense， once I know the value function for the policy。

If I know the transition function， that lets me。Predict， well， if I go west。

 which state will I end up in？And if I go north， which state will end up in if I know that transition。

Probability。And I know the value function， then a simple way to。

Read the policy off of the value function is to just look ahead at what state will I be in for each of my possible actions and then just greedily take the one with the highest。

Value function， score。And so there always exists an optimal policy， at least one。 plus。

 there always exists for each policy， a unique。A set of values that you'll get for if you follow that policy。

Con of an MP would you ever。on the state。But where you came from。The M in MDP is Markov。

So the Markov assumption is precisely that no， the history does not matter。And。Of course。

 in the real world， if you can't observe the state very well。

Like if I don't have eyes in the back of my head。And I don't know whether there's a gorilla there。

 And I don't know whether my optimal action is the bolt for the door。嗯。

Then I have a partially observable MDP。And in that case， one strategy for trying to deal with it。

Is to。modelel it is a non Markovvian process where I could do this and then come back and assume that the grillilla is still not there。

走。But the M and MDP really means Markov process， and therefore history is not。Informative。

That all of the information you need is bundled up。In the representation of the current state。



![](img/55b33118c53ab7ca0f17304e99470923_17.png)

Okay。😊，Good。Allright， so here's the summary。Just for fun。And now a few questions。

Here's a good question。Suppose I have an agent who does not know in advance。

These immediate rewards that are written on the arrows。It does know the actions it can do。

 and it does know the transition probabilities for getting from one state to another。

But it doesn't know the rewards， and it doesn't know the value。

 and it doesn't know the optimal policy。If it randomly roams this world。This world， which， again。

 has deterministic actions， deterministic rewards。And it's trying to learn a deterministic policy。

 And firstmore， this is a world in which there is a single non negative absorbing goal state。

In this restricted deterministic world。Can you think of an algorithm？That if this agent could use。If。

It doesn't know what the policy is。 It doesn't know what the value function is。

 And so what it's going to do is it's just going to uniformly at random， whatever state it's in。

 pick one of the available actions。So if it's here， it'll pick 50， 50， if it's here it'll pick 33。

 33， 33。Probability， just pick something and move。 and I'll keep going around until it gets absorbed。

 And then we will allow it to reincarnate， and we'll put it uniformly at random in one of the other five states and let it。

Continue to randomly roam。Okay， so the experience it's going to get is purely random roing。



![](img/55b33118c53ab7ca0f17304e99470923_19.png)

My question to you is， can you think of an algorithm。



![](img/55b33118c53ab7ca0f17304e99470923_21.png)

That agent could use to learn the optimal policy and the optimal value function。

The easier those two is learn the optimal value function。After that， you can just。

Calculate the optimal policy。So can you think of one。Yes。Right， right。

 So it could just roam around and keep very careful records about。

When it took actions in particular states， what reward it really did receive。

And then it could build this map。And then it could do what we did before of calculating。

 So that would be possible。There is a more direct thing it can do。Which is to iteratively。

Reestimate the value function。Suppose it it it， it decides it's going to estimate the value function。

 I'll put a little。Ht over here to indicate it's just an estimate。

So suppose it it follows a strategy of every time it takes a random step。

It's going to update its estimate of the value function and initially starts with a value function that has 0。

Estimated value in every state。And this agent does know that the actions are deterministic and that there's a single non negative reward state。

So do you see what it can do。Yes。I guess there are value functions of this。かこ。可以系。very low estimated。

RightMmhmm。理由。してくられな。Theres a higher value function that at any。そして。That's right。

 Gamma couples the values of these adjacent states。 Like if one state is worth something。

 then this state， you can。Come from to reach that state is worth gam at times， its value。

 plus whatever reward you get on the way there。That was what we talked about a moment ago。

 So if you think about it。Here's an interesting learning algorithm。

The ancient just randomly moves around the world， and we let it be reborn randomly in some other state if it gets absorbed into the Gaulll state。

And I propose this algorithm。After each step that it takes， say from here to here。

What it does is it updates。It updates。It's moving from here to here。

 I'll call this state S and this S prime， the new and S prime。

What it's going to do is update its estimate of the value of the state it just departed from。

To be either what it thought before。It's old estimate of the value or whichever is greater。

 either that old value or the reward it just received。

 plus what it thinks what it estimates the value is for the new state that it enters。



![](img/55b33118c53ab7ca0f17304e99470923_23.png)

![](img/55b33118c53ab7ca0f17304e99470923_24.png)

So when it moves from here to here， initially， all it is assuming。Values of zero for every state。

 I what does in。So here's the initial value function。Now， moves from。Oh let's start here。

 suppose moves from here to here。

![](img/55b33118c53ab7ca0f17304e99470923_26.png)

So now， what's greater， V old is 0。Or the reward that it receives will it receive zero reward plus V old of the new state。

 Well， that's 0。 So it doesn't matter。Okay so。It's going to leave this at zero。Intuitively。

 that makes sense because it didn't get any reward and it doesn't know anything about the other states。

But now suppose keeps going east。Now it goes from here to here。

So that's going to update the value associated with this state。

To be the maximum of either what it used to think， which is 0。Or the immediate reward，100。Plus。

 the value it。S suspectuspects this date is worth。So now what's the new value here？Okay。

 now it's absorbed。In the goal state。 So we let it be reborn somewhere。嗯。

Suppose we let it be reborn here。And suppose it chooses to go here。

Then what's the update to this value？Nothing。Right。It thinks this is worth zero。

 It got an immediate reward of zero。 so it still is going to leave this at  zero。From here。

 if it's unlucky， it'll go this way。But suppose it goes that way， then it'll update this state。

But what's interesting is if it's reborn in this state。Now。

 if it goes east the way it did the first time。What's going to be its updated estimate here？Well。

 it's going to be the maximum either of what it used to think it was worth zero or the immediate reward zero。

Plus， what it thinks is the value of that state，100。Times gamma。So， now， it'll。If it does this。Next。

 now that will be replaced by a 90。So you see what this algorithm is doing is pretty cool。

 This very simple algorithm。😊，Although that might take a bit of random。Moving around the world。

But all the algorithm is doing is。When it makes a transition and it encounters a state that it thinks。



![](img/55b33118c53ab7ca0f17304e99470923_28.png)

Has some non zero value。 Then it's going to be propagating that value back。

Discounted by the discount factor， gamma。嗯。Further and further。 So next time。

 if it starts here and goes here， now it'll call this gamma times 90。

And if it's here and it goes this way， then what will it think the value of this is？73， right？

So if it does this action， then it'll replace that by 73 and so forth。Now。Why do I think， oh。

Let's just leave it at that。 So you get the algorithm。Okay。This algorithm is very similar。

 this algorithm has the essence。Of what we're going to do when we move to probabilistic MDP。

 We're going to use this same key idea。Of updating your estimate from the state we just left。

By using the immediate reward we just experienced plus the value that we think the new state has。

And each time we。Update V。We're updating。 were。We're updating the V old and the V， you know。

Be new becomes real。 Be old becomes be new， yes。えき？Yes。Yeah， good point。 So the point is， you know。

 if you have a memory， if the agent has a memory， it can。嗯。

Keep track of a lot of this information and not have to actually act in the world。

You could just think about it in its head。 And that's an very important distinction that we're going to get to because so far。

 we're assuming。Except in this particular example， I was this， well， even in this example。

 I'm assuming the agent。

![](img/55b33118c53ab7ca0f17304e99470923_30.png)

![](img/55b33118c53ab7ca0f17304e99470923_31.png)

Knows the transition function。And so。In a sense， the agent can do a lot in its head。

 If it knows the transition function and the reward function。

And the discount factor and the actions in the states， it has an MP。

Then it consulted all in its head。 But later in the semester， we're going to be very interested in。

 as we should be， situations where the agent doesn't really know the transition function perfectly or maybe not of it all。

 initially。

![](img/55b33118c53ab7ca0f17304e99470923_33.png)

In which case it's going to have to act in the world。In order to gather that information。

And so what's interesting about this algorithm is if the agent knows only these things。That。

 for example， in this case， there is a non negative reward。Then。

Here's a pretty interesting algorithm。I want to ask you a question or two。Yes。

one what things go down。嗯。なっちゃうわけ。okay， if you have a suggestion， I'm all ears。😊，Yes， yes， yes。

 If the environment keeps changing。For example， it rains over here and now the road's slippery and it didn't used to be that kind of change。

We call that a nons stationary environment。Because now the state transition probability is no longer a fixed thing over time。

If you try to walk on the icy road of the outcome， the probability of you end up plant on your back is much higher than it used to be before the ice came。

So。We very carefully。Stated that we're solving MPs。 and between the lines， that really means。

There is a fixed。Transition function here。 So the world cannot change。

In ways that change this transition function。Now， depending on how we formulate the world。

 like we could say the transition function is fixed。

 but the state includes either there being ice here or not ice here。In that case。

 my transition function can have a different probability for the state where there's ice in this physical location。

 which is a different state from where there is no ice in this physical location。So if， theres。

 it's not that every physical location has to be a state。 It's that every。Discernible， distinct。

Situation。Is the state。And that's when my grid world kind of conflates the two physical location and state。

 But in fact。State really means。Just是。Discernably different situation。Okay。

 let me come back to some questions。 But I want to ask these to get everybody on the same page。

 Tru or false， Our estimate if we use this algorithm that we just talked about。

Will always be non negative for every state S。True。False。Okay， true， it's true because。

We initialized this to zero。And。Of course， in our example。Every time we updated。We took the max。

Of the old value。And something else。But initially， all these were 0。

 So we're always taking the max of something where one of the values is at least 0。

So there's no way that this update could give us something below zero。All right。Tru or false。The V。

 S estimate。For every state will always be less than or equal to。The immediate reward 100。

For this algorithm。True。Fuse。Okay， a little more dissension。

 somebody who believed true want to give us the reason。True is the right answer。G the discount。Good。

 yes， I agree。 And in this case。Because we have the。

Special case where there's a single non negative reward。Then in that case。

 the maximum value of VS will always be there。If we had a couple rewards， like。

 what if I put a plus 100 here also。Then it wouldn't necessarily be true that it would stay below 100。

If I change the world in that way， because then I might get 100 plus some discounted 73 or even more times gamma。

 if I go that way。But in this world where I carefully said there's a single non negative reward state。

 then both of these are true。So true， true。Okay， but the reason I asked these questions。

 I want to kind of draw out what's really going on here， which is what this algorithm is doing。

Is it's monotonically。It's starting out with assigning a zero to every state。

And then as we start doing these random actions， what this algorithm is doing is moving some of its estimates to a higher value。



![](img/55b33118c53ab7ca0f17304e99470923_35.png)

But it will never move them higher than 100。And， in fact。

Will it ever move them to a value higher than。The value associated with the optimal policy。No。

 because the， the update rule is basically taking our definition of expected discounted future reward right here。

And so。Not only is it。Is the value function monotonically。Increasing as we train more and more。

 but it will also never exceed the。嗯。V star， the， the value associated with the optimal policy。 And。

 in fact， if we allow the agent to roam。More and more times。

 as that amount of training experience approach as infinity， this value function will approach。



![](img/55b33118c53ab7ca0f17304e99470923_37.png)

The value function for the optimal policy。I shouldn't have told you that because that was a final。

 true， false question。 But， but it's true。 you see， and you see why， right， You can see that like。

What if it wasn't true， What if。One of the values was still below what you could get for the optimal policy。

 That means there exists in action you could take。That we get to and， and。嗯。Another state。

Where gamma times value， the true value of that state。呃。

Was higher than what you currently believe your state is worth and so you'd update it。

And if that other state didn't have the correct value yet。

 eventually it will find a way to with an infinite number of moves around the world。

 eventually you will find accidentally a path that is the optimal path。

 and so eventually these things will all move up to their optimal values。Okay。

So the reason I like this example， then I'll get your question。

 The reason I like this example is I didn't have to say anything about probabilities。

The simple idea that we just illustrated。Is the idea of this kind of backup operator where we know that the value of some state is related。

To the value of its successor state， if we take some particular action。In this way。

It's the immediate reward we receive plus gamma times the value of the next state。 And we。

 we talked about this in the previous lectures because we just pointed out that this is just a recursive way of stating the definition of the value。

But we can use that recursive definition as a very convenient， incremental update。

Algorithm in this simple， deterministic world。And for the rest of the lecture。

 we're going to look at， well， what if it isn't deterministic， What if it's probabilistic， then。

 What does this have to extend to， But the essence is going to be exactly the same idea。Okay。

 questions。Yesス。When we say value。は。哦。四加わるば。Oh， in this case。

 what I meant is the algorithm is exactly this。Here's a procedure。 It's an algorithm。

 Iize all of your VS estimates to zero， and then roam forever every time you move from a state through an action to a new state and receive a reward。

Apply this update and then repeat forever。So that's the algorithm that I had in mind。Does that help？

Okay， another question。It about how general this is。え輩さエテ二げ一こボ三。

That that's still work is we just proved that。Everything positive is con to。美味し？

But I'm not sure it still does。那中さ。Yeah， yeah， things can be， I pick this example very carefully。

 and there are a lot of ways of loosening the constraints that I wrote down that will break this theorem。

the general idea hold but the general idea does hold in， as we'll see。Yeah， one more。有用。AhYes。

 it is useful to learn the reward function。Here I'm just assuming we're experiencing， you know。

 we're sensing what the reward is for particular。Transition that we take。And so in this algorithm。

 there's no attempt to learn the reward function。 But in general， that is。Helpful。Okay， one more。

 and then we'll move on。About the common that。え？你是。it's not a stationary。 It's really。Let's just say。

It's， it's hard to get any kind of theoretical guarantee on convergence of your algorithm if you're in a world where the transition function is changing。

 because what what would have been an optimal policy under the old transition function no longer is once it changes。

Because that sounds like an interesting problem。It is。And so。

So there is a big body of literature and we'll get to some of it in the course on partially observable Markov decision processes。

People usually try to treat。Changing dynamics， changing transition functions as a problem that can be repaired by having a more。

Elaorate state representation， like I did with the ice， right， I said， well。

 that if I say each location is a state， but sometimes theres ice in this position， sometimes not。

 then I'm going have to model it as a different transition function。 But instead， what I did。I。

 I carefully wiggled away from。Being forced to say the transition function is changing。 Instead。

 I said， I'm going to redefine the state to be not just my X， Y coordinate。

 but also what's the physical condition of that。And now there is a more elaborate transition function that I'm going to have to deal with that has to capture the effect of ice and coefficients of friction。

Stuff， but at least I can treat that physics of the world is fixed。And so that's usually what。

We'll try to do is still assume the transition function is stationary。

Technical term people use stationary or non stationationary。

 Stationary means the transition function does not change over time。

So we'll try to maintain that as much as possible。 And sometimes that'll force us to。

Make more elaborate representations of the state。Okay， these are all great questions， but in。

In the interest of covering the next thing， I'm going to put a hold on those。

 and we can cover more questions during office hours， which， if you have not noticed。

 are immediately after class right here。And out in the hallway， once the new next class happens。



![](img/55b33118c53ab7ca0f17304e99470923_39.png)

OK。So I think that's a helpful example to I keep that on my head all the time because it's so simple you can。

Understand exactly what's going on。 You can see why that algorithm converges。And it's good。

 but now we're interested in what if some of these things are probabilistic instead？



![](img/55b33118c53ab7ca0f17304e99470923_41.png)

Okay， so now。嗯。In the deterministic world。嗯。In the deterministic world， we had a simple。

Equation for the value of some policy at a particular state。

 We said it was just the reward we receive if we take that action。Plus。The value associated with。嗯。

The next state。 But now we have a more complicated expression because if， in fact。

 our actions have only probabilistic effects。Like if our action is to go north。

 but we end up maybe north plus or minus5 degrees。Then we can be in different states。嗯。And so， now。

We're back to the Belllman equation， which Kaarina talked about before。But just to review it。Now。

 of course， if our actions are probabilistic and our policy might be probabilistic and a reward。

here I guess。Here're assuming the reward is， this is the expected value of the reward。嗯。

Then we can write the value function in more general。No deterministic situation this way。

The recursive definition still says that the value of the state we started from depends on the immediate reward plus the value we assign for the successor state。

 But now there are other things in between。 Now， we have to say。Well。

 we're going to sum over all the possible actions。 and pi here is taken to be the probability。

Distribution on the action that we're going to take。So this could be， in general。

 Pi could be a nondeterministic。Action， And so you can think of。Pi of。A given S。Is the probability。

Of taking action A。Given us。Right， in the same spirit as our transition function。

Is also outputting a probability， the probability there next state will be S prime。

 given that we started in the state S and took the action A。So， if you want to make a。

Non deterterministic policy。That 70% of the time goes this way and 30% goes that way。 It's okay。

We'll accommodate that by taking the expected value of this quantity with respect to that distribution of actions。

And then this quantity looks very familiar。It's just the immediate reward we received。

 just like in our deterministic case。Plus， the value of the next state。 But now， again， we。

 since the next state is a nondeterministic thing， we want to take the expected value。

Of this over the different states we might appear in。So you see that's what we're doing here。

 We're just summing over the different states， the probability of ending up in S prime。

Given that we started in S and took an action A times the value of S。

So these are just expected values of。The value of the outcome。The expected value of the reward。

Starting an S and taking a。And then the expected value over the different actions that you could take。

So that， that's totally sensible if， if you're in a probabilistic world， I just want to。

 and our goal， our stated goal。Is to maximize。The expected value of the sequence of rewards。Yep。嗯。

あ那个。いさを？If you start from a。successor state you still get。We kind of fudged on that。 I'm。

 I'm not 100% comfortable this。 But yes， that's the way we what we put here is that the function R of S is the expected reward we'll get if we do this。

嗯。If I had to do it again， I would， I would edit this slide and say R is the function of S A and S prime。

And。But then somebody who is astute would raise their hand and say， can we still have nondeterminism。

 even if we have S and S prime in A and I would have to say， yeah， it's okay。

 the math will all go through and the algorithms will still work。But you're right。 I mean。

I'm uncomfortable with， with。Doing this because it's kind of sloppy to。

Pretend that we're observing this expected reward。 Were， we're not really。

 We're getting a sample from the distribution of rewards。 I don't make。I mean， this is still correct。

 it' just that。To use this in an algorithm， the agent now needs to know what that expected value of reward is。

And can't just use the sample Dboard。Unless we。At least if。

We'd have to prove that it could get away with using the sample report。Okay。

 so now let's look at what we can do in this situation。嗯。

So now I'm going to go a little more quickly and I strongly。

 strongly encourage you to read the Sutton Barto chapter， which is the reading for today。

 because it goes as quickly or slowly as you like to read through the same material。

 So if this is going by quickly， you you can read it at your own pace。

 but here are a couple different ways of。

![](img/55b33118c53ab7ca0f17304e99470923_43.png)

![](img/55b33118c53ab7ca0f17304e99470923_44.png)

![](img/55b33118c53ab7ca0f17304e99470923_45.png)

Annotate of， of notation that we're going to be using again through the course。

 So here's what we had before we said， well， the value function is just the expectation of policy action。

Times the reward plus the expected value of the next state。嗯。We can。嗯。We can write that。

Let's go here。We can rate that here as。In general， we're going to be。Sliding back and forth between。

Talking about these as functions， and。In our algorithms。

 using vectors and matrices to represent these things。So。嗯。You can think of R alternatively。

 as a vector。

![](img/55b33118c53ab7ca0f17304e99470923_47.png)

That we're going to have。 And the vector has。 if we have n different states。

 then the reward could have。And different values for a particular policy pie。The case value would be。

嗯。If we're in state K and follow a policy pie， what's the rewardboard？And similarly。

 T could be thought of not as function。A probability distribution。

 but we can represent that probability distribution as a matrix。嗯。And。For example。

 the IJ entry could be the probability of transitioning to state S prime。

 given that we start in state S。Under policy pie。So anyway， this is just kind of a notation slide。



![](img/55b33118c53ab7ca0f17304e99470923_49.png)

Let me。Not overly dwell on this。But just say this。The essence of that idea we saw in our algorithm before and that we're going to continue to use in this nondeterministic case is that we want to back up these values。

 That is， if we make a transition starting in state S， we do action A and receive reward R。

 we might end up with different probabilities in different outcome states。

But we're going to say that we can express the value of our original state as this kind。

 this function of our。Next day。And its value。 So it's the same idea we had before。

And here I'm switching partly to vector and matrix notation here， just too。Say the same thing。

This is useful， to go through because， again， in our algorithm。

 sometimes you actually just want to implement these transition。



![](img/55b33118c53ab7ca0f17304e99470923_51.png)

Functions as matrices。Okay， so if we do it this way。Then， we can see that。

The problem we really want to solve。Is that。嗯。Now， if I represent V。say V is also a vector。

It's if I have this many states， then I can think of V as just a vector where there is many states and the vector as。

Sorry， many positions。比。Jth entry just gives me the value for pi of being in state J。And。T， again。

 is the transition matrix now， map where the。I J JK entry gives me just the probability of transitioning from state J to state K。

And then R， again， as we said， is just。The expected value of reward。

 if we start in state J and follow our policy。So I can write the Bellllman equation。

In this kind of matrix notation。And then a can solved as the matrix equation。And you can solve this。

 It involves taking an inverse。And the only sad part is this is order n cubed where n is the number of states。

It's the number of states。Okay， but。You see what we're doing here。 This。

 this is the same kind of back propagation。Recursive。



![](img/55b33118c53ab7ca0f17304e99470923_53.png)

I shouldn't use the word bad propagation， different meaning。



![](img/55b33118c53ab7ca0f17304e99470923_55.png)

It's the same recursive equation that we were using in our simple， deterministic world。



![](img/55b33118c53ab7ca0f17304e99470923_57.png)

But now that we've expanded it to non deterministic policies， actions and rewards。

It's the same essence of the idea。 And In fact， if we express it in matrix form。

 it becomes an equation we can solve。 There are known algorithms for solving it。And so in that sense。

 we can solve the problem of given an MDP， well defined MP。



![](img/55b33118c53ab7ca0f17304e99470923_59.png)

Find the value function。For a particular policy。And。It will require order of N cubed。Computation。

 but it can be done。Our research。No。哦呃。No。No， we're not， because。

The key places where the policy enters are here。 If I have been non deterministic policy。

 I can take the transition probabilities for each action。And if the policy has a probability。

 nonzero probability for three different actions， I can just take the weighted combination of the transitions for each so this can be a nondeterministic policy and it's often insane with the reward。

So given a policy， deterministic or non and a non deterministic transition function and reward。

 we can express it in this way。

![](img/55b33118c53ab7ca0f17304e99470923_61.png)

可以。ionOn the right side where。value function for S。The major。啊，各 yeah。The question had to do is。

 why is this v pi and also v pi instead of。E pie of something else。The answer is that。嗯。

In this matrix and vector notation， we're talking about simultaneously the relationship between every。

嗯。Pair of states that can be reached from every。Via every action。And so。呃。In in a way。

 because these are vectors， this is like a set of simultaneous equations having to do with every single transition that can be made between any pair of states and the。

That constraint that。V of this thing times gamma needs to be equal to v of that thing。

So the gamma is still in there， but it's effectively a notation that gives us simultaneous equations。

Okay， again， there's I。It's kind of unavoidable that there's just。

Some learning of notation that we have to do here， but it's worth it。

 and the good thing is we do have a pact， Ketterine and I have a pact to use this notation consistently through the semester。

 and it's also the notation in the Sutton Bareaau book。

 which again I strongly recommend you read the reading for today。

So at least we'll be using this consistently through the semester。Okay。

 so what we just saw is that we can， given in a policy we can solve for the value function for that。



![](img/55b33118c53ab7ca0f17304e99470923_63.png)

But now。What if we actually want to learn。The best policy。Then。These slides kind of reay what。

I was saying before。 So what I want to do is just move to this instead。There is an efficient way。Of。

Given a policy solving for the value function。And。为。I want to go through that and in the abstract。

 it just involves the same kind of iterative re-estimation of the value function that we were doing before in our simple deterministic world。

 but on every iteration， we're going to actually look at every state transition that's possible and in one fell swoop update them all。

Let's see what that looks like。Again， an example helps。嗯。So， here's another。Example where。嗯。

I have two absorbing goal states。The shaded in ones。I have 14 other states。嗯。对。

Actions that are available are to move north， southeast west， but not off the， off the world。

And the reward in this case， I'm gonna to say， is -1。Everywhere。

 except in the shaded where the reward is zero。Okay， now we have negative reportss。And。Ah， okay。

So here。Here's the algorithm that we're going to apply。 It's basically。

Given our casefe estimate of what the value function is。We're going to go through every state。

And we're going to update it to have a K plus one estimate。Using this equation， which， as we agreed。

 is just the non deterministic version of what we had used in our simple world。And。嗯。

So if we actually do that in this simple world。What we find is。Again。

 I'm going to initialize the value function。For the， for a particular。Policy to be zeros everywhere。

 And our policy is。嗯。In every state you have， you can move equally probable in every legal direction。

So from here， you can move north， south， easts west。 from here， you can move north or east or south。

And so forth， equal probability。 So that's our policy。 Notice it is a non deterterministic policy。

And we want to know the value function for that。So。And again。

 the immediate reward is- one for every one of those transitions。

 except for transitions into the absorbing goal state。So what this shows here。

Is the entire set of state values。We initialize them to zero。 then on our first iteration。

 when we do this backup from every possible state。Now we're going to say， well。

 what's the value of this state？

![](img/55b33118c53ab7ca0f17304e99470923_65.png)

Let's go back to our equation。 our equation tells us。We're gonna。

 we're going to use our old value function。We're going to update the value for that state as the sum over all actions that our policy will allow。

 So those are equal probable， nondeterministic actions。

Times the word reward we receive for whatever that action is。Times the。

Values associated with each of the possible outcome states。Wighted by their probability。

So we're going to take those expected values。And so if we apply that。To every state。

On our first iteration， these are the new values we end up with。



![](img/55b33118c53ab7ca0f17304e99470923_67.png)

AndWhy is that， Well you can see it like this one。With probability in this state。

 with probability one third will go east or west or north。And each of those， remember。

 the immediate reward is -1 for every action。Except the actions that lead us to the goal states。

And so that update will say， replace the zero。By the expected value of immediate reward plus。

Previously assumed values。From the previous time， so。



![](img/55b33118c53ab7ca0f17304e99470923_69.png)

If we say take this state。You're going to consider。Those three possible actions。Which have。

Put us in these three states。嗯。All of whom have zero value。And plus the immediate reward。

 which is -1， no matter where we go。 And that's why this ends up being a -1。And similarly， if we're。

If we're in the terminal state， we just stay there。 So there's no negative one reward anymore。

 But if we're adjacent to it， we could move。

![](img/55b33118c53ab7ca0f17304e99470923_71.png)

To there or or there， we're still experiencing a -1 reward on our way。And so， the expected value。

There is a -1 reward in all cases plus。

![](img/55b33118c53ab7ca0f17304e99470923_73.png)

As before。Assumed zero value of the next state。

![](img/55b33118c53ab7ca0f17304e99470923_75.png)

Okay， if we continue this。

![](img/55b33118c53ab7ca0f17304e99470923_77.png)

Then you see over time， what happens。Like on this next iteration now。



![](img/55b33118c53ab7ca0f17304e99470923_79.png)

These ones in the middle， they're going be a -2， because。Again。

 here I can take four possible actions。 So the。Expected value of the next state is going to be -1 in each case。

And here， I'm using a gamma of one。I should have said that。Here I'm using a gamma of one。嗯。

And so here I'm going to add。 I'm going to reest this。That will be reestimated this。

 because I'll get the -1 immediate reward， no matter where I go。Plus。

 gamma1 times the expected value over those possible things， actions。

 but all the actions lead me to a state whose is value， I believe， is -1 anyway。So that becomes a -2。

 The only place where that doesn't happen is in these regions that are close to the corners。

 because now I believe this one's worth 0。And so when I update this one。with some probability。

 I go north and west， but with some probability， I go east。

And I'm going to get my -1 reward immediately， no matter where I go。

 But now I believe that if I go with one third probability ease， I'm going to be。

In a state whose value is 0， not minus-1。And so this is actually 1。666。Okay。

 then on the next iteration this and so forth。Okay， so you can verify this by hand。

 but you get the idea of what's going on。

![](img/55b33118c53ab7ca0f17304e99470923_81.png)

On every iteration， we're updating not just one state like we did in our simple deterministic。



![](img/55b33118c53ab7ca0f17304e99470923_83.png)

![](img/55b33118c53ab7ca0f17304e99470923_84.png)

Roam around the world thing。 But we're updating the entire value function for every state。

By looking at， well， from that state， where could we go and what values would we back up and what immediate reward should we consider there to？

不晓得。 how would you know when to stop？开庭张。Yeah， this is good， so。



![](img/55b33118c53ab7ca0f17304e99470923_86.png)

Notice we have K infinity here。This does converge to a fixed point。And it can be proven， though。

 not today。

![](img/55b33118c53ab7ca0f17304e99470923_88.png)

嗯。So， the good news is。There is theory that tells us that for a given policy。

 if we iterate this procedure， it will converge to a。To a fixed point。 And in practice。

 what we often do is just define a pragmatic threshold that says from iteration to iteration。

 if the maximum change of any of these values is less than delta then we're going to stop。Alright。

 so before we end， I wantan to just。Pop to the top， and point out。What have we seen。

So we've seen this core idea， which we're going to use。Rampantly through the rest of semester。

 that a way to learn these value functions is this kind of backup operation。

Based on the recursive definition of the value phone。

We saw how to use that to actually build an algorithm that an agent could use while it's roaming the world。



![](img/55b33118c53ab7ca0f17304e99470923_90.png)

Infinitely long。To learn the optimal value function。 But here， if we actually know the MDP。

 which means we know the state transitions and we know their expected rewards。



![](img/55b33118c53ab7ca0f17304e99470923_92.png)

![](img/55b33118c53ab7ca0f17304e99470923_93.png)

Then we can actually just solve this。Either by a matrix。Form solution。 Or， in fact。

 this is often more efficient。Alrithm through this iterative value iteration algorithm。



![](img/55b33118c53ab7ca0f17304e99470923_95.png)

If。We'll say more about this next time， but it turns out to be a very simple step to go from the answer to this question。

 which was the question was given a policy， how do we discover its value function。

 It's very easy to go from that question and this solution to an algorithm that answers the other control question。

 which is given an MDP， how do we find the optimal policy。And。That's。



![](img/55b33118c53ab7ca0f17304e99470923_97.png)

That involves again， in iteration。But here where we were keeping the policy fixed and iterating to get the value function。

 we're now going to iterate。 this will be the inner loop。



![](img/55b33118c53ab7ca0f17304e99470923_99.png)

Where we'll have a policy， we'll find out its value， given those values。

 we will be able to create a new policy that's at least as good as the one we started with and then find out its value function and just iterate that。

You could think about that in a shower， too。 That's。

 you probably can see what that algorithm is going to look like。嗯。And again。

 it's going to turn out that there are convergence proofs that show that these things。

 these iterative algorithms really converge。Okay， final quick sentence。

 There is a homework coming up。 We will get it out by Monday。 If we're lucky。

 we're going to try to get it out by Friday。 So if we do that。

 we'll send an email to everybody who's on piazza。

![](img/55b33118c53ab7ca0f17304e99470923_101.png)