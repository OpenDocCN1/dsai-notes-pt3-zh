# Stanford CS221 ｜ Autumn 2025 p09 Stanford CS221 ｜ Autumn 2025 ｜ Lecture 9： Policy Gradient [lOMNskWVeD8] [BV1XuPrzwEes_p9]

![](img/fad329bc1a8d358a9ecd253427bb8703_0.png)

![](img/fad329bc1a8d358a9ecd253427bb8703_1.png)

So we're in the midst of talking about reinforcement learning last time we introduced the basic reinforcement learning algorithms and this is going to be the second lecture on reinforcement learning where we generalized larger statebased models and we explore policybased algorithms that will allow you to learn the policy directly so this is going to bring us closer to the state of the art of what people are actually doing in reinforcement learning。

 we started with MDPs， we understood with AR， we looked at Q learning and SARSA and all these things and now we're building up to hopefully by the end of the lecture you'll have the key ingredients to understand basically any sort of cutting edge RL algorithm。

Okay， so let's start by reviewing reinforcement learning。So remember。

 reinforcement learning is more of a setting than necessarily a particular algorithm。

And the setting is very elegant， it's in some sense the most general way to I think， think about AI。

 you have an agent， agent takes actions in environment。

 and environment gives rewards and observations back to the agent。

 and along the way the agent is meant to make sense of the reward and observations and choose better actions for subsequent iterations。

So in what we'll study， the environment is defined by a Markov decision process。

Remember the flaky tram MDP problem where the goal is to go from location 1 to location6 in this case。

 where the tram can fail with probability 0。1 walking goes you from i to I plus1。

 tram goes from I to 2 times I。Okay。And the agent in this setting is going to be an RL algorithm and we looked at multiple RL algorithms last lecture in particular。

 we looked at Q learning where you define some sort of exploration policy which might walk or tram randomly。

 and then we looked at epsilon greedy where the exploration the get action function would either choose to explore according to this policy or explore the policy that it's learning along the way。

And then the learning rate governs how quickly the RL algorithm is taking steps to estimate it is Q values。

Okay， so the Ral algorithm。 And here's what an example interaction looks like。

 This is from the agent's perspective。 So remember last time there was a simulateim function which called the environment and called the agent。

 But I'm sort of inlining this trace to see what the agent would be called with。So initially。

 you start in state one。 So the environment says， give me the action at state one。Okay。

 and then the action goes into the environment and then the environment comes back with says， okay。

 here's what happened， you were in state one， you walked to state two。

 you got a minus1 reward and you haven't ended yet。Okay。

 so now the environment calls the agent with get action at state2 and。

And then the the agent might go。And you， return， let's say， it returns walk。

And ignored this tramp that's out of eight。And the environment would say okay， agent。

 here's what happened， you were in state two， you walked， you got into state 3， reward -1。

 you saw I it ended， and then itll call the agent again and say agent in state3。

 what would you do and the agent might say I'm going to take the tram now and then the environment update and say。

 okay， agent in state 3， you took the tram， you end up in state 6 and you got a reward of minus2 and now you're done。

Okay so this is a particular rollout and each rollout generates a utility。

 which is a number which represents the discounted sum of rewards。

 so you take these rewards and if the discount is one， then the utility is minus-4。

 minus-1 minus1 minus2。Okay。😊，Okay， so in particular， it's important to remember the isolation here。

 The R algorithm doesn't see the MDP。 We're not passing the MDP into the RL algorithm。

 It just sees everything it sees is through get action and incorporate feedback。

 In particular incorporate feedback。 That's the glimpse of the world it Cs。

 and it's using that feedback to try to figure out what to do next。Okay。

 so if you generate a ton of rollouts， let's say， 20 rollouts。

And you average the utilities of all those rollouts that defines the value of this RL algorithm。

Against this MP。Okay so remember a policy is a fixed mapping from states to actions。

 our R algorithm is a dynamic object that will update its internal policy as it learns from interacting with the environment。

All right， so that's the O setting。In order to define algorithms， oral algorithms。

 it's useful to define a bunch of different types of values。 we saw all four values。

 Let me just put them here just so we have a reference here。

And a value is synonymous with expected utility。 So we first saw V pi of S。

 This is a number that represents the value of following policy， pi from state S。

If I got dropped into state S and I followed policy pi and I did you know。

 infinite number of rollouts， What would be the expected utility。 That's what that number represents。

Q pi SA is the value of in state S of first taking state action A and then following policy pi。

Remember， the cues are on those chance nodes and these are on the state notes。

And now if you replace a pie with stars。We're basically saying， take the optimal policy and。

 and do that。 Okay， so V star is the value of following the optimal policy from state S and Q star is。

First， taking an action A and then following the optimal policy。Okay。So now。

We define all these values。There's a question of how do you。What is your R algorithm？

To model or not to model。 So if your model based， that means you first estimate the MP。

 and we saw how to do that last time。 you just count the number of transitions and and record the rewards that you see along the way。

 And then you compute the optimal policy using value iteration。

And then what we saw was the first type of model free method。

 which is a value based approach where we don't bother to estimate the transitions and rewards directly。

 We don't estimate the MP。 Instead， we estimate the Q values directly。

 And then once you have the Q values。If you have this Q value。

 you basically look at the action that gives you the highest Q and that's your policy。

 So going from Q to policy is relatively straightforward。

Going from reward or MDP to key values is not as straightforward。Okay， so for them。

 value based methods。The general form of the algorithms。 And this applies to model free Monte Carlo。

 Sarsa and Q learning is。We're estimating some。We're estimating Q essay。

And when we get a piece of feedback。We have some sort of new point of view on what Q of SA should be。

 No one tells us Q SSA directly， but we have some sort of noisy estimate。

 and we're going to call that a target and a target is an estimate of the utility。And then。

And when we do the update， we basically simply take our old QSA and we move it in the direction of the target by amount that depends on the learning rate。

So if the target is already QSA， then this doesn't do anything， but if the target is above QSA。

 then we're going to nudge it towards target in that direction。Okay， so a few more things。

So there's a question of on policy or off policy。Okay， so what does this mean？So in general。

 in our algorithm。You are following some policy。 Let's call that the exploration policy to generate rollouts。

This is a policy that is giving rise to the feedback。Now， using that feedback。

 the algorithm is going to estimate the Q values of a policy， which we call the estimation policy。

So in arm policy， all it means is that the exploration policy and the estimation policy are the same。

So the data that you get comes from the policy that you're trying to estimate and off policy just means that the data that you generate of is from a policy that's not the estimation policy。

So when we looked at SARSSa， that is an on policy algorithm because SARSSA tries to estimate Q pi。

 which is the values Q values of the policy that you're following and Q learning was off policy because you're trying to estimate Q star。

So in Q learning， the really interesting thing is that you could be following a random policy。

 but you're estimating the Q values corresponding to the optimal policy。

So off policy algorithms are very， very nice because then in some sense。

 you can take data that comes from some source and then use it to estimate a policy that you want。

 which is often going to be the optimal policy。Okay， so what to use as targets。 So remember。

 the general form of the algorithm is that you're going to estimate Q and you're going to update towards the target。

So there's two things we looked at， one is full rollouts， which means that from state S。

 you actually roll out all the way to an end state and then you take the discounted sum of rewards and that's a utility and that number is what you use。

But the problem with that is that you have to wait until the end to get a number that you can estimate earlier on and bootstrapping says。

 let's not wait until the end， I'm just going to get initial reward and then instead of rolling out to the end。

 I'm just going to use my current estimate to estimate what kind of future utility I'm going to get。

Okay， so I'm bootstrapping。My utility from a model estimate。Okay， so in light of all these concepts。

 we can now think about the four algorithms that we looked at last time。

We'll first look at model based value iteration where we estimate them MDP first and then compute the optimal policy using value iteration。

We then looked at model3 Monte Carlo。And this says。Basically， you follow some policy pie。

 we're going to just look at the full rollouts from a particular state and taking a particular action。

And set target equal to that utility。 So there's no bootstrapping。

 I'm just using the Monte Carlo estimate of the utility。

Sarrsa says I'm going to still try to estimate Q pi， so I'm on policy。

 but I'm going to use bootstrapping， where instead of using a utility。

 I'm going to take the initial reward and then a discounted in I substitute here the Q value of the successor state。

So I don't bother to roll out and figure out what happened at the end。

 I'm just going to use the Q value。And then Q learning is almost the same thing。

 but with one small change now I'm estimating the value of the optimum policy。

 So this is an off policy algorithm， it's still using bootstrapping。

 which is why it looks like SArsa， and the only difference is I stick a max an over a here instead of letting a prime B pi of pi of s prime。

Okay。So I know that was a lot。 Hopefully what I'm trying to do is。

Try to break it down into the essentially the principal components of policy versus on policy。

 model base versus not model base， bootstrapping versus not bootstrapping and so on so that you can see each of these algorithms not as an isolated thing。

 but see the rich interconnections between them。Yeah， so the question is when would you choose SARSA。

 let's say， versus Q learning， Okay， so the difference between them is on policy you know versus off policy。

So。I think the short answer is it depends on your particular application。

 but the nice thing about off policy is that you can explore more aggressively and still be guaranteed that you're estimating the optimal policy。

 whereas if you use SArsA as you kind of run the algorithm。

 you essentially have to play much closer to the optimal policy。

 because otherwise you would be estimating the Q pi of the wrong， not the optimal pi。

So the question is， yeah， what's the difference between SARSSa and Q learning and what does this really mean？

So。Remember， this target is。What is computed？In the when you do incorporate feedback right and incorporate feedback。

 you compute the target and then you update the Q values。 Okay。

 the get action is actually the same for SARSa and Q learning if you do Epson greedy。

 you either explore or you you take the current Q value and choose the best action from there。

So now if you look at this， in some sense， it's the same difference as if you remember when we looked at policy evaluation and evaluationeration。

In policy evaluation， the recurrence is essentially taking the single action that is given by the policy and in valuation。

 you're taking a max over possible actions。 And this reflects the objective here。

 So if you're interested in。What is the targets supposed to represent， The target represents， okay。

 I'm at a particular point。 I get some reward， and then I'm going to keep pi means I'm following。

The policy pie。So that's why a prime has to come from policy pi。

Whereas Q star means I'm going to follow the optimal policy。

And that's why there's a max over a prime。Because if this were the really true Q star。

Max over a prime would be the best action。And that would be the action taken by the optimal policy。

So Q learning is trying to estimate the optimal Q star Q values Yeah， and the actions it takes well。

 depends on the exploration policy， but it need not be optimal。Okay， let me move on。So so far。

We're estimating a Q value for every state action pair。

So this is called the tabular setting in reinforcement learning。

 and the reason it's called the tabular setting is essentially you have a lookup table。

 literally a dictionary， how we implemented last time for every state action pair。ok。

But now in real world settings， you can't do this。For example。

 if you're trying to learn a robot policy， your state might be an image of what the robot sees and your action is going to be how you're going to move the robot arm。

Or if you're doing things with language models， your state might be an entire sentence or a paragraph。

 let's say。And then your action is to generate the next token。Okay， so in each of these cases。

 the state space is huge。 it's all possible images or all possible sentences。

 so you certainly can't have a lookup table for that indexes by an image。 It just makes no sense。

So how should we deal with this， any ideas？Yeah， so the suggestion is you have to reduce the state space。

 Yes， yeah， you definitely have to reduce the state space to maybe some smaller amount。

 and then you could do you know Q learning or whatever on top of that。U。

That's certainly one thing you could do。 I think what we're going to do is to try to get even more directly at the problem。

 but I think the intuition of state space reduction is right。Okay。

 so so function approximation in the context of reinforcement learning is used to contrast with tabular learning。

 So nowadays with DRL and all of these things， function approximation is already just a given because you have whenever you have a large start sta there is no other choice。

So remember， the tabular setting is you have a lookup table for every SA pair。

 you have a number QA that you're storing。And function approximation says， wait a minute。

What do we learn from machine learning？What we learn from machine learning is that you can actually learn very complicated functions of very high dimensional inputs。

😊，So S and A， let's say they're an image or a sentence， there are very large things。

We know how to map that into a number。Right， so why don't we just parameterize this function。

With some parameters data。And then。And then try to estimate the parameters data directly instead of or estimate the parameters data instead of trying to estimate Q directly。

Okay， so this is the idea behind function approximation。So we'll see some examples。

So now recall the machine learning lecture。 Okay， so what do we have to figure out。

 We have to figure out what are the possible functions。

That's a hypothesis space or a hypothesis class。How do we know whether a particular Q theta is good or not in the context of reinforcement learning now and what algorithm do you use to reduce the loss？

Okay， so this should all seem familiar and essentially we'll be able to incorporate many of the ideas from machine learning now into the R context。

So if you can extrapolate， take everything we learn from RL and everything we learn from machine learning。

 and we're just going to put them together now。Okay。So what possible functions can you choose here？嗯。

You know， S and A are。can be。know sentenceents， they could be images。

 so typically what we're going to do is we're going to map this into a vector of features because machine learning likes taking vectors and matrices and tensors。

And then we could use a linear function。Simply a dot product between some parameter vector theta and a feature vector phi of SA。

Or we can use a multi layerer perceptionron， which we saw before。 We simply take this vector。

 we multiply by a matrix， and then we apply some non nonlinearity。

 and then we multiply by another vector or matrix and keep on going。

I'm not going to talk too much about what are the choices here， but just。

Think about this as a place where you drop in your favorite model architecture。Okay。

 so let's try to work an example of this。 So define the same environment as before with this MP。

And now we're going to define the same exploration policy。

 and now we're going to do parameterized Q learning。And for this。

So what I'm going to do is just for simplicity， we're going to assume that the state action pair just maps into indicator features so we have one feature for every state action pair。

 so this will allow us to use machine learning to simulate the tabular settings so we can just check that everything that's working。

 but just then hopefully you can use your imagination to drop in other more powerful。

Machine learning models。Okay， so here in the class， I'm going to have my linear model here。

 which maps from number of features to a single scalar representing the Q value。

 and I'm going to have my optimizer handy。 Okay， it's just going to be SGD。Okay。

 so let's figure out what this feature vector should look like。 So conceptually。

 I'm just going to map the state action pair into a essentially a number between0 and the number of states times number of actions。

 minus1。Okay so that's all this is doing， states are number one through6。

 so I'm going to make it through0 through5 times number of actions plus the integer representation of that action。

So in that case， this is 0。 I created a one hot vector of length number of features。

 So this is going to be the feature representation of。One walk。

This is going to be the feature representation of one tram， two walk， two tram。

 and so on until I get to six tram。Okay so every state action pair is just a different feature vector Okay so this is all hand coded。

 no learning here。Alright， so now I have， I'm going to compute。Q values。Of a state。And action pair。

And to do that， I'm first going to map this into feature vector space。

And then I'm just going to pass it through the model and I get some number out。Okay。

 so that's going to be how I compute the Q value of a particular state action pair。Okay。

 so now given that I can and I know how to compute Q values， I can compute policies。

 and the policy that I get at state one is going to be compute Q values for all the actions。

And then choose the action that has the highest Q value and that's going to give me my action that I return for my policy。

Okay， I'm showing you essentially how to compute the feature vector， the Q and the pi。

 given a fixed set of parameters now， Okay so now we have the building blocks now we can implement。

 get action and incorporate feedback， which is what every R algorithm needs to do。Okay， so。

What happens now in geta， This is the same as actually before。

 where I run Epsilon greedy with probability Epsilon， I explore。And。

With one minus probability epsilon I don't explore。Hey now let's incorporate the feedback。

 environment says I walk to state two， what should I do with it。Okay， so now。

I'm going to compute the target。So in order to compute the target， I'm going to。

Look at selftop pi of next state。 Remember， pi is going to take the arg max over the Q values。

 and that's going to give me the optimal action， given my current Q estimates。

And then I'm going to compute the target to be the immediate reward plus the discount did。

And I'm using bootstrapping， so I'm just plugging in the Q value of the next state and the next action。

O。So now I have the target。I also have the predictive value of， if I'm in state。

Inter actionction and take action。 What is the value that I expect。

And I want this to be close to target right and remembering regression。

 what do we do when we want two things to be next to each other。

 we defined the loss to just be the standard squared loss。

 which penalizes deviations between the prediction value and the target。

So now that I've defined a loss， I can just compute the gradients with respect to that loss。

 This is just standard pytorrch， and I update the parameters。Okay。

So hopefully you can see now how the machine learning enters the reinforcement learning。

 basically all the skeleton of you know， get action， incorporate feedback and how to cue learning。

Is basically specifying the target now， given the target。

 now all this lost calculation and model architecture。

 that's just within the realm of machine learning。So now I did this for Q learning。

 you could imagine doing this for SArsa or model you know based model free Monte Carlo as well。

 and it would just it sort of plugs in。Okay， so now maybe you go back and you say get action and now one minus epsilon probability。

 I'm just going to choose the optimal action that I have so far and then I incorporate feedback。

 compute the target， compute the predicted reward， form the loss， compute the gradient， optimize。

 update the parameters。And then get an action this time I'm also exploringing and then incorporate feedback I get I'm at the end。

 so there's no next state， no next action， so that's just the reward。

 but nonetheless that's still target that it can update against compute the loss。

 compute the gradient of the loss and update the parameters。Okay， and if you simulate。This。

M100 times。Then you get some weight and you get some value。

 Let's look at the optimal policy that has been computed。 So what I'm doing here is for every state。

I'm going to call the R algorithms P function to get me what is a policy that has in store for me。

And。I guess this time it didn't。 Okay， maybe I got un key here。So this is stochastic。

 so it didn't actually end up with the right policy here because it should have walked， walked。

 walk and then took the tram， but it didn't do that。嗯。But if I ran it for longer， it should。

 it should do something reasonable。Okay， so what I'm doing here with this policy is I'm also looking at the optimal estimate of the optimal values。

 which is taking Q state and pi state。And then I get these values。

Let's compare it with the true values by solving MVP。 So remember I had the original MVP。

 I just call value iteration on it and the original MVP is not available to our algorithm。

 so I can't do this actually in our algorithm so by Im doing outside。And I get the result。

And the result， if you look at the， the actual values， these are the true optimal values of MP。

 This is what the R algorithm came up with。 It's sort of。Kind of doing something reasonable。

 but it's sort of off and this is our actual optimal policy。Okay。Well。

 I think I got unlucky here because in the previous iteration it did get the optimal policy。

So to summarize。What we're talking about is function approximation。

 you have large state or action spaces and you can use the tabular setting。

 you can't just look up all possible images or sentences。

 so what we're going to do is parameterized Q value。

 you buy some either linear or nonlinear mapping from state actions to some value number。

We're first going to maps a state action pair into a vector of features。

And then we're going to define either a linear function or MLP to map that feature vector into a single number。

When we。To incorporate feedback， we're going define the squared loss between the predicted Q value and a target。

 which is given to us by the virtue of。Doing Q learning。

And then we're going to take a gradient of the loss function with respect to data and take a step in that direction。

So the question is， why is the loss function the square difference between。

The prediction and the target。So the intuition here is that。The target。If okay， so。落静。

Maybe the easy way to explain this is that suppose。

Your target in Modelto Free Monte Carlo is just a utility that you get from a full rollout。Okay。

So if you did that a million times and took the average。

That average would be the value you would want。mAnd now so targetrg in some sense。

 is representing a noisy version in general， a noisy version of what you want。

So when you form the square loss， it's saying like you're doing regression。

 you're saying I want the value to be close to target。

So now when you update the parameters of the model。After you out the parameters。

 the loss goes down and the only way the loss can go down is value moves closer to target。

So the question is does this method converge to the optimal value in general no in the tabular setting under there are some conditions in which Q learning will converge usually these things look like your exploration policy needs to just be everywhere and if that's the case then I think generally it will be fine but now if you put in function approximation in general there there's no guarantees you might be able to get show convergence to a local optimum but that's maybe less exciting than showing that it's finding the optimal policy。

So now we're going to move on。To a different way of doing R L。Okay。

 and this is the space of policy gradient or policy based methods。

So if you remember where we started， we start with model based。RL。

 which means we're estimate MDP first and then use that MDP via evaluation to compute the optimal policy。

And then we said， wait a minute don't even we don't need the MVP。

 Why don't we just compute the Q values directly。And then using the Q values。

 we can just get the policy by taking the action that gives us the largest Q value given a state。

These are called value based methods。But now if you're paying attention， you said， wait a minute。

Actually， we don't even need the Q values。 We can just directly estimate the policy。

Why don't we just do that？Okay， am I just wasting your time here， the answer is short answer is no。

 but the little long answer hopefully will become clear later。So the way to think about a policy。

is just a classifier。What is a classifier it maps inputs the outputs。

So everything's a classifier in some sense， So the input here is a state and the output is an action。

Okay。So if you remember the machine learning linear classification lecture。We said that， well。

 these classifiers are actually really hard to optimize because you end up with like 0。

1 loss and the gradient0 everywhere。 you can't do that。So what we do。

 we made probabilistic classifiers， so we have a probabilistic classifier that takes an S， a state S。

 and then defines a distribution over possible actions。And distributions are continuous。

 and therefore we can optimize them。Okay。Okay。So that's the prelude。

Now let's talk about imitation learning for a little bit。So if we had demonstrations of that policy。

 this would be actually， we could just go home and what is the demonstration。

's it's basically having an expert that gives you a rollout of So a death expert came along and said。

 okay， here's what you do。 You walk to state  two， you walk to state three， you take the tram to six。

Okay。And then if you have that data。You could say， okay， well。

I'm going to turn that into a bunch of examples for my training algorithm， I said hm。

If the input is one， I want to walk。 If the input is 2， I want to walk。 If the input is 3。

 I take the tram 3 examples。 And then you could say， I'm going to define。呃呃。know， objective function。

 J of theta， which sums over all the examples and looks at the log probability of an action given the corresponding state。

Okay so this is called imitation learning。Because you're having an expert that shows you what to do。

 and now you just train the classifier to slash policy to just do what the expert said。

So for example， this is actually done in context of what would otherwiseize the RL problems。

 so in robotics you have people that tell or operate a robot that says， okay。

 here's how you pick up the cup and put it on the counter without breaking it and in math。

 companies will hire people who know math to go and solve a bunch of math problems and write nice solutions and those are demonstrations of what an expert would do in a given state。

Okay， so you don't need our algorithms for imitation learning， it's just supervised learning。Okay。

 well， that was easy。But the problem is what happens if you don't have demonstrations。

 Remember the R framework， the environment is not nice enough to give yous here's how what you should do。

 The environment is cruel。 Itll just give you reward or no reward。

So all we have this reward function， So what should we do？Yeah， you can explore， great。

So all you can do essentially is roll out your policy。Get some data。

And but you don't want to just roll out and then just clone that data。

 you just you don't want to do whatever that data tells you。But along with that data。

 it told you essentially how good that。Our comee was。And so a crew thing you might think about is。

 well， I'm going to roll out and some of the trajectories are going to be good and some of them are going to be bad。

 and I'm just going to take the good ones and then do imitation learning and you wouldn to be too far off from what actually happens。

So if you remember， if you just want to remember like kind of the zeroth order thing。

In policy gradient， you basically just roll out your policy， you collect a bunch of rollouts。

 and you take the ones that have high reward and you do imitation learning on them。Okay。

 in the rest of the lecture， I'm going to give you something a bit more nuance than that with more math。

 but the intuition hopefully is clear。Alright， so let's get going here。 So we have this rollout。

There is going to be more math in this section than in previous sections。So are you aware？

Put on your math thinking caps。 Okay， so we have this rollout。

 I'm going to use TO to denote TO stands for trajectory。 I'm using the term rollout。

 I think rollout trajectory episode。 you can maybe think interchangeably。

 So our rollout says it's basically state action reward， state action reward， state action reward。

 state。😊，Okay， so a concrete rollout looks like the thing that we've been looking at before where you have a walk。

 walk tram。And remember， each rollout produces a utility。OkaySo that's standard。 Now。

 what is a probability of a rollout？Okay， what I mean by this is what is a probability that this thing happened？

And by the chain rule， we can write this down as a set of conditional probabilities。

It's the probability of starting S 0 in our settings。 It's been deterministic。

 So this is just one for。If assuming the first element of tau is S0。

And then the first thing is that there is a policy pi theta。

 what is the probability of taking the first action given S？

And then times the transition probability of from S 0 and A1， transitioning into state S1。

And now it's agents turn， probability of A2 given S1， an environments turn。

 probability of S2 given S1 and A2。And then the agents turn and the environments turn and so on。Okay。

 so the probability of a trajectory is this interleaved sequence of probabilities of the agent policy。

The environment transition， agent， transition agent transition。Okay。

So the components are just to say it again。There's a policy term。

 and then there's the transition distribution term。ok。Okay， so now。Now。

 if you just think about what we're。Trying to do and reinforcement learning。

All we're doing is trying to find a policy that maximizes the expected utility。Of a rollout。Right。

So I can just write that down。You， directly。So the sensor value of theta and theta remember are the parameters of the policy is equal to the expectation。

Of the utility of Tao。Okay，Ex utility。And if I write that down， it's basically thinking， well。

 what is the expectation over， Its expectation over all possible trajectories tau。

And the probability of that trajectory times the utility of that trajectory。Okay。

So there could not possibly be a more direct statement of what R L should be doing， right。

 You're literally saying。Oh。Expected utility。And we just want to optimize this。So no MDPs。

 no Q values， this is in some sense the most direct thing you can do。Now， how do you optimize this。

We've only learned one way to optimize a function。开。Graadian descent。 Okay。

 so let's just take the gradient。Okay。Yeah， this is expectation here that might be a little bit annoying。

 but let's do it anyway。 Okay， so let's take the gradient of V theta with respect to theta。Okay。

 so gradient V， I'm just writing out the definition of V。 so far， so good。

I'm going to expand the definition of expectation to be this explicit sum over。P theta。

Let me just make this larger。 the audience in the back。So this is expectation over all trajectory。

 So this is some overall trajectories， probability of that trajectoryy times utility of that trajectory。

 Okay， so these are just definitions。 I'm going to move the。

The gradient inside the expectation or the sum because gradients are a linear operation。Okay。

 so now I'm going to do something。Okay， so what is the gradient of。피셀。Okay， and you're。

 you're probably like， well， I mean， it didn't depends on what P theta is。 It's just like some。

 it's the gradient of P theta。 But what I'm gonna do is something that might look a little bit strange at first。

I'm going to rewrite it as。P theta times the gradient of log P theta。ok。So。Okay。

 just so you're wondering， okay， where did that come from。It comes from。嗯。Let's see。

WellLet's do it this way。 Okay， so what is the gradient of log of。Okay， let me just write it down。嗯。

Okay。So what's the gradient with respect to this？So remember， a gradient of a log is。1 over that。

Quantity times the gradient of whatever's inside。Right。

And then all I do is move this over here and that's。

That's how I write this in terms of p theta times this。Okay， and there's a reason to this madness。

 Why am I doing it like this， It's because now I have something that's some over trajectories times P theta of the trajectory。

 And I can neatly wrap that back in into expectation。So whenever you see this expectation。

 you should think about it as summation over trajectory times probability of that trajectory。ok。

So now。I have the gradient of this thing above， which， you know， wasn't maybe obvious how to。

differentiate now I've written it into this expectation where I have the gradient of this quantity。

And this identity is called the policy gradient theorem， but I mean， it's sort of elementary。

 So I just call it that identity。 It's not really a it doesn't deserve to be called a theorem。U。Okay。

So。So this is actually。You know， good because。In general。

 whenever you see an expectation and you want to compute it and you can't because it requires summing over like all possible trajectories。

 you can think。Maybe I can just take a random sample from that。Okay。

 so that's what we're going to do here。 We're going to replace this expectation with just a sample。

So instead of summing over all possible trajectories and waiting by the probability of that trajectory。

 I'm just going to sample a trajectory。 and then I'm going to define an objective function。J now。

 which is just。This thing on the inside， log。P theta tau times utility ta。

And then I just can just take update data by taking a step in the direction of this gradient。Okay。

 let me just pause here， just I'll just kind of summarize。We started with this。

Undisputable goal of maximizing the expect utility。 I did some。 took the said， okay， we。

 we only know how to optimize things by taking the gradient right now。

 So let's just take the gradient。 The gradient is actually an expectation of stuff。 And it said。

 you can just take a sample to approximate the full expectation。And now。

We're going to define this objective function whose gradient is exactly the thing kind of inside。So。

 so maybe just to foreshadow some stuff。What this is basically saying is that go ahead， explore。

 do your rollouts once you get a rollout。I'm looking at basically this term and waiting by the utility of that。

And then just updating it。 So if I didn't have this utility。

 I would just be doing imitation learning。Just maximize the probability of the trajectories I saw。

 but now with the utility， it's sensitive to essentially how good this trajectory is。Okay。

 so I think something got。A bit messed up in the formatting here， but。

If you think about unpacking this gradient term。This is going to be utility times。

A summation over all time stepss of the probability of an action given the preceding state。

Of overall action， overall time steps。And this is known as a reinforcement learning。

 reinforce algorithm， which comes from Williams 92。

 is an instance of this general class of policy gradient algorithms。

 but reinforces perhaps earliest and simplest one。And like I said before。

The intuition here is that we're essentially performing imitation learning on demonstrations which we know and understand。

From demonstrations come from our own policy， but they're weighted by the utility。

And if the utility were just zero or1。Basically， success or failure。

 Then this is just imitation learning。On the successful demonstrations。

So the intuition that I mentioned earlier， which is do a bunch of rollouts of your policy。

And then just take the ones that are good and do imitation learning is exactly what reinforced would do in this special case where all the utilities are 0 and1。

Okay， now if they're not 01， then you have a little bit more。 if it's like fugility is 0。5。

 then it's saying， well， I'm sort of having a weight of 0。5 on that example， a trajectory。

 and if utility is minus 10， then I'm like running away from I'm saying like don't do that。

 don't do that。So yeah what is this utility where does it define So the utility of a rollout if you remember is the sum of the discounted rewards。

 so when you have a rollout it's just minus1 times discount times minus1 plus discount squared times minus2。

Okay， so hopefully this should be pretty intuitive policy gradient。Now， just to summarize。

 optimize policy directly to maximize expected utility。Due to the policy gradient。

 theorem or identity， we can compute an unbiased estimate of the gradient by sampling a single trajectory and then just updating that。

And the algorithm is。You know， you sample a rollout。Which means that you're。

As yourre on policy and then updating each state action pair in the rollout weighted by the utility。

Okay。So now that we've gone through the math， let me try to implement it now okay。

 so we start with our same MDP and now I have reinforce。嗯。Note that we don't need the。 okay。

 so reinforcers， I now I have a model that is is going to essentially classify from map from states to actions。

So it's a problembil to classify over a number of actions。

 so that's why it's a matrix now because I'm multiclass。And then I have the optimizeizer as before。

Now， like in Monte free Mon model free Monte Carlo， we're going to。

Keep track of the current rollout as we get incorporate feedback because in the current algorithm as I define。

 you have to wait until you get the utility。Okay， so notice that we don't need an explicit exploration policy。

Because we're defining these probabilistic policies now， and that should give us some exploration。

 Now， you could also add additional exploration as you want， but we don't absolutely need to here。

Okay， so。Let's define let's peek out what get action and incorporate feedback do。So good action。

 I'm going to。Compute。Of feature representation of the state。Okay。

Which is going to be a one hot vector representing to the state here。

 I'm going to pass this feature vector through my linear matrix。

 And that's going to give me some logics。And then I'm going to take the softm。

 That's going to be give me a probability distribution over these actions。

 and then I'm going to sample。According to those probabilities。

 and then I'm going to take get the action and return it。Okay so all get action is doing is。

know what you would do in classification where you compute the logics， get the distribution。

 and now I'm sampling from that distribution。So now what does In feedback do。

 like in Model Free Monte Carlo， we're just going to remember the rollout for in general。

 so remember the start state， keep track of the utility。

 add to the rollout if I'm not at the end I don't do any updates。I'm going to get action。

 incorporate feedback， get action and now。The last time when I incorporate feedback， I'm at the end。

So here is my rollout。And now I want to update the parameters。 Okay。

 so I'm going to keep track of the loss。 I'm going to go through each step of the rollout。

Each step of the roll goes from some state。To particular action。

So the first time it will be state one to taking walk。嗯。So remember。

 this is the input and this is the output of the classifier。So， I'm going to now。嗯。

Compute the model's prediction of。The action given the state， so compute the feature vector。

 compute the logics。And now remember in multiclass classification， I compute across entropy。

Between the logics and the target。Which is just the one hot encoding of the action in this case walk。

And then I add that loss。Okay， so I want these logtettes to match the target here。

The the form of the algorithm is the， is the， is the same。 So you go through the step second step。

You add your cross entropy term for the second step。

 and then you go through the third step and then you add the cross entropy term for the third step。

Okay， I should be multiplying the loss by the utility。So now you update your parameters。

 compute the gradients of this loss， and then take a step， and now these are updated parameters。Okay。

 so let's see what happens if I run it。And so I get some here the weights， get some value。I think it。

Seems to have worked， even though I messed up the algorithm。 Interest。 Okay。

 so I learned a distribution where in state 1， I should walk say 2， I should walk。Say three。

 I should take the tram， stay four walk， say five， walk， say six walk。

 or I guess six state6 is the end state。 So these values are just kind of arbitrary。Okay。

 so in summary。Get action， just samples from the policy。

And incorporate feedback updates the parameters， state action in the rollout and waiting by utility。

 which I didn't do， but you should do。Yeah， this is online。

 All RL algorithms are generally online unless it's offline R algorithm because。

Whenever you're doing this， it's online， you're getting action， you incorporate the feedback。

 you get action， and incorporate feedback， and so on。And here， this is just one rollout。

 and I'm already updating the parameters。Sometimes you might want to batch。

 like have a bunch of rollouts and you batch them up， so it looks a little bit more offline。

 but the spirit is online。So the question is does initialization of theta matter in general it does。

 even in the standard supervised learning case， if you're training a neural network that has is nonlinear。

 then initialization will affect the outcome， I think in reinforcement learning matters even more because as currently implemented。

The initial exploration policy is given by pi theta。

 so the data you collect will also be governed by the goodness of your initial policy and in general you want theta to be set probably small so that you get a kind of a uniform distribution over yours。

Okay。So let me talk through a bunch of bells and whistles here。So recall the objective。

 maximize expected utility。So we can just write it down and。The policy gradients theorem says。

 here is the gradient。And we can't compute the gradient exactly because that would involve sum over all possible trajectories。

But。What we've done is use reinforcefor to say I'm going to take get an estimate of that gradient by just taking one sample。

And computing the gradient of that， this one sample。But can you get better estimates？

So to talk about what better means， I'm going to go through this quick detour of talking about variance reduction。

Okay， so let's consider a simple setting where you're just trying to estimate the mean over a set of numbers。

Okay， so I is the index into the list。Every number has a particular probability。

 so there's four numbers。Okay， this should be 0。25。25， probably do sum to one。

 and the points are minus4， minus6，6 and  eight。And so you want the， the true mean to be。You know。

 basically the do product between these vectors， and we'll just pretend these sum to one for now。

I'll fix that later。Okay， so an estimate estimator to be formal is any random of variable that。

Tries to get close to mu。 So remember， mu is this thing that you。

 let's say it's expensive to calculate here you'， it's easy to calculate because you sum over four thingss In general。

 you're taking the mean over all possible trajectories， which is hard。

So each estimator has some sort of bias and variance and maybe some also computation cost and computing it。

So the simple estimate of mu is you just sample a single index and you return the point at that position。

Okay， so you might sample an index。And then you get the point and then you return it。

 So every time you compute the estimator， you might get a different value。And then。

How do we know if estimator is good， we have to compute its bias and variance。

 so going to let's just try 1000 times， we're going to call the estimator function and then we look at its mean and variance。

Okay。😊，So here for this particular estimator， the mean is one， which is what it should be。

 so I guess everything normalizes so just imagine this is 0250。25 and then the variance is 36。

 which is not great if you think about it。So normally if you're doing stochastic gradientage descent。

 high variance means that you're just going to take more iterations to get to the right answer。Okay。

 so here's another estimator。 why don't we just sample， two points？And then just average them。Okay。

 so if you look at that estimator， the mean is roughly the same， but the variance is a lot smaller。

So in some sense， this is a better estimate of the mean。You can also make it worse if you。

 let's say you choose a point and then you just add some random noise to it。So if you do that。

 then the mean will still be roughly right。 it's unbiased， but the variance is going to be worse。

 even worse than the original one。Okay， so now。Here's from the fun part。

 So now suppose I have this magic function offset I。😊，Okay， and this is going to have mean zero。

Which means that if I subtract this offset。This is the same as this by linearity of expectation。

And then this part is 0。 So that is the same。 It has the same me。Okay。😊，So let's suppose I just。

Define this offset to be-6， minus-6，6，6。Okay， so I'm going to sample a particular index。

 and instead of taking just that point， I'm just going to that remove an offset。

and I'm going to return it。So if I do this one。You'll notice that the mean is good and the variance suddenly goes down a lot。

Okay， so this is magic， right， So I managed to reduce the variance by a huge amount without affecting the mean。

😊，Right，It's easy to make the variance go down if you don't care about the mean， you just return 0。

 And then that's going to give you not a correct answer。 But here， as long as I pick some function。

That where the mean is 0， I can add it to my estimator and hope that I can reduce a variance。

 So this is in statistics， called control variances， It this general idea that's quite powerful。😊。

Okay， so let's see。HowSo going back to the reinforcement learning setting， how do we find an offset。

That has0 mean。And hopefully it can reduce the variance。and just to provide some intuition。

 why is this working？This is working because if you think about the mean is one， right？

 So the ones over here are sort of too far down and the ones that are over here are too far up。

 So what this is doing is is it's sort of pulling up the ones that are sort of like。

Too far down and pulling down the ones that are too far up。

So if I have some prior knowledge about where the mean might be relative to my point。

 then I can hope to reduce the variance。Okay。So here's the key identity。Okay。

 so I'm going to claim that。I'm going to define a function B of S。

 It can be any function that only depends on the state， but not the action。Okay。

 then I'm going to claim that。This quantity holds。 So what is this， This is， remember。

 this is the expectation of the gradient of the log policy times this the baseline。

And this holds for all S and A that's drawn from this policy。I haven't proven this。

 but I'm just wanting you to stare with this for a moment。And if you think about。Why this is helpful。

 if you look here， the policy gradient theorem is this thing。So that means if this is zero。

 I can just add this or subtract this from that。And I don't affect the mean。

 but I have the chance of reducing the variance。So if you remember a star。

 there is this idea that the heuristics and A star are using domain knowledge to improve the algorithm。

 and if it can estimate the future cost， I can really get a very fast algorithm。

So this is kind of an analogyy here where if I can figure out the right baseline。

 this is called this B is going to be called the baseline function。

 I can actually vastly reduce the variance as well。Okay， so the proof is is fairly， you know。

 straightforward。 It goes like this。 Okay， so let's just take the expectation of B of S。

That is some constant。OkayThat doesn't you depend on， in particular， it doesn't depend on theta。

 And now I'm going to take the gradient。With respect to theta of this quantity and the gradient is no zero。

嗯。And now actually in the interest of time， I'm just going to skip this and just trust me that this works out。

 basically it's the same math as used for the policy gradient theorem but just going in the other direction。

And so using this idea， there are a few things。 I just want to highlight them。

 I'm not going to have time to go into them in detail。The first is that using baselines。

So I can just subtract a baseline from the utility and as long as that function doesn't depend on the action。

 then I'm free to do whatever I want， and I can come up with， it can be a model。

 it can be some sort of heuristic and that can reduce the variance。

 Another thing I can do is instead of using the utility at each step。

 I can use only the rewards from that point on。And this is valid because。The previous。

 the past doesn't depend。 doesn't affect the the future。And then finally。

I can also plug in a bias estimate of the value function。

 So I'm going to estimate I'm going to bring back cues。I'm going to say I am doing policy gradient。

 but instead of using the actual utility， which is what I did in Model free Monte Carola。

 I'm going to bring back the cues， which is what I did in these bootstrapping methods。

And these methods are called actor critictic methods because they allow you to estimate a value and also estimate the policy at the same time。

 and in deep learning you can even tie the parameters together。Okay， so summary， summarize。

The game here is to find an estimate of this。The gradient of the expected utility that has low bias and low variance。

 So by using baseline。This is a pretty general purpose strategy to reduce the variance。

 but it's still unbiased， which is good， bias is zero。

And you can also use bootstrapping to reduce the variance at the cost of some bias。嗯。

And then finally， let me summarize this whole lecture on MDPs and RL。

 so we look at three classes of methods for doing reinforcement learning。Model based， estimated MP。

Compute of optimal policy value based directly estimate the Q values and derive the optimal policy。

 Policy base， just directly estimate the policy。The form of the algorithm is similar in all three cases。

 You roll out with some exploration policy。You form some sort of loss function。

It could be in terms of the parameters of MDDP Q values or the policy。

And you update the parameters using a gradient step。Okay， so that concludes MDPs and R。

 where we're trying to maximize the expected utility。

 So what we're going to look at is what happens if there are adversaries in the environment and you can't really use expectation anymore。

 You have to consider what happens in the worst case。



![](img/fad329bc1a8d358a9ecd253427bb8703_3.png)