# 【比科卡大学】机器学习讲座 ｜ Machine Learning ｜ Moe ｜ Grpah ｜ Rlhf ｜ Llm ｜ Ai Safty ｜ 2024 p12 P12_强化学习基础与算法浅析-Claire_Vernade -BV1XzScBEEdJ_p12-

![](img/317a17805017238441f55189e7b9f180_0.png)

U is for this fourth day of the workshop， for this introduction to reinforcement learning class。

 Its designed to be， like it says， a friendly tasting of， of reinforcement learning。

 It's a one hour class。 So in one hour， we cannot， you know。

 make a view like experts of all of reinforcement learning。

 But I try to choose what I think is important。 And， you know， for that， I also。

 you know to inspiration from great material that exists there online， which I will， you know。

 give give you the references to。😊，And essentially。

 the class is going to cover some basics about Markov decision processes。

 which are really at the heart of what reinforcement learning is about。

And some initial ideas of how we can build algorithms to learn by trial and error。

 to learn by making decisions and getting feedback from the environment and then progressively improve our strategies。

 So this is really what reinforcement learning is about I have heard from pray from colleagues that like many of you already know about reinforcement learning。

 So just a show of hands， how many people here know already about reinforcement learning。😊，Okay。

 cool。 So I think for。Most of you that raise your hand。 A lot of this material is actually quite。

I mean， maybe familiar。 I， I， I kind of。I， I would hope that at least some of it is like because there there's not gonna be anything about deep reinforcement learning in here。

 So it's really going to be the the basics of how reinforcement learning kind of is at the the at the heart of it。

 And then in the second part。 So after a little break， we'll see how well that works。

 It's the first time I do this。 So after a little break quiz will move to like explaining the key algorithms。

 maybe like Q learning and and policy gradients that are。

 maybe the things that are still and being developed and and topics of of open open research。Okay。

 so I mean， Francisco already said quite a lot about me。 so I you know， I skipped the first part。

 Okay， I worked for after my PhD。 I worked for Amazon and I worked for Deep for four years。

 and I work on know， all sorts of things， reinforcement learning theory。 And recently。

 I moved to the University of Chi and where I'm now leading a group。 and recently。

 I've been awarded an ERRC starting grant。 So I'll be growing my group in the next few years。

 So you know， if you're interested in topics like reinforcement learning theory。

 bannedit algorithms and quantification exploration。

 non-stationary environment and continual learning， this is more or less what my group is about。

 And if some of these words are not clear for now， I hope that they will be by the end of this class。

Alright， so。Most of those slides and the content here has been heavily inspired by really high quality material that's online in particular。

 the video lectures by David Silver from like these UC CL lectures that are already about 10 years old。

 but I think still completely relevant。And， you know。

 these lectures are based on like important books and some online。 like， I also like。

 took inspiration for some online courses and tutorial that I。

 I think I think were were worth mentioning。 There are more of these things out there。

 just these other， the references I， I， I felt like were the most relevant for this course。Okay。

With these kind of preliminaries， let's get started。So。

Machine learning is not just about computer vision。

 There's also a lot of problems out there that are actually dynamical systems。

 just fundamentally dynamical systems。 If you and if you interact with them， they will。

 they will change。 They will change states。 They will be modified by your action。

 and you will have to cope with a system that that responds to you。And this is a little bit like。

 what。To some extent， is， is missing in the traditional view of reinforcement learning where。

 you know， you have a problem that is fixed and you need to collect data to estimate what is the right function to you know。

 map like the data to like the output， something like this here， really。

 be it in in the problem of go or in cooling data centers。 when you make a decision in the system。

 you impact it long term。 And so you need to take this into account so that your actions kind of reflect what you want to do in the long term。

And to model this situation。For a while now already， maybe since the 90s， roughly。

 reinforcement learning has converged on studying what we call Markov decision processes。

 And these are very specific， very。Sinnic key， mathematical objects。

 That's why I'm going to spend quite a bit of time at the beginning of this talk to explain to you like how these things work and how we can work with them and how we can actually compute things in these objects that are not。

 you know， your usual。R D， kind of a space。Okay， so in these systems。

 we assume that the system is in at every round at every step T in this learning process。

 The system is in a state。That we denote usually S。 And in this system， I take an action A。

 And following this action， sometimes I observe a reward that depends on the state and the action。

But most of the time the only thing I only observe is a transition to a next state。And。

The goal is to， you know， take all these past take。

 take the state at state at Ramty and construct what we call a policy that is going to go and map like the state to the action。

Okay， so it's， these are just the notation that I just introduced。Just for， you know， to。

 to build a model I of this kind of general， general idea， we have a markov like we it's。

 it's a Markov process。 So everything， you know， all the information about the past is in encoded in the state。

 That's the key assumption in reinforcement learning。

 We assume that we don't actually need memory because everything that we see at at time T is。

 is encoded in the state that we observe。It's a strong assumption that is most of the time non。

 not valid in real systems。 But for now， just to， for the sake of building algorithms。

 we' are gonna assume that this is， this is true。And。We， were here in this class。

 we're going to always assume that there's a finite set of states and a finite set of actions。

 I think I say a little bit at some point about like infinite set of states。 But like， you know。

 essentially， you can think of it as like a finite set of states。

 finite set of actions and like small systems where you can move step after。

 step after step into this， this small system。Okay。So what we want？Is to construct the policy。

 So this thing at the at the very bottom here。So this policy is a function that is going to map states to actions。

And what we want to do is find a policy that has a large， long term return。

And this long term aspect of this definition is captured by this discount factor。

 which is a very important quantity in all the settings that we're going to look at。

 We always assume that the agent has kind of has gives a value to how far in the future it looks。

And here， so how is dis quantsified， The， the return is defined as the expectation， so。

There's always noise in all those processes， because all the transitions or the rewards are a little bit noisy。

 So here we， we can attack the expectation over all of this。And we look at from the state。

 from the initial state where the agent started。We look at the sum of rewards that it got from step 0 from now。

 taking actions all the way to like infinity。 So we assume this trajectory is like an infinite sequence of state action。

 state actions。 And we look at the sum of the rewards。 And as you can see， essentially。

 after roughly a horizon of one over one minus gamma。Ih，So like when， when T is like 10。

 if gamma is something smaller than one already， you know， the reward that you get here is。

 is really like drastically like down weights。 So this kind of returns really gives you an incentive to go and construct policies that have an incentive to go straight to the goal。

Okay。And not， they just turn around and wait。 And maybe in the future register the place where the rewards。

So it's， it's， it in， it incentivize being， being efficient。Okay。And。

I'm not sure what I changed to here， okay。And。So， yeah， so the。

 the big question that we are gonna look at in the next whatever five minutes or something is how can we actually optimize in an MP when we know the model。

 So we are not yet solving a learning problem， because the learning problem is really hard。

 But first in in the first place， Like if you， if I give you an MP。

 and I tell you what is the metrics for transitions， And I tell you what is the reward function。

How do you compute this policy that maximize this， maximizes this expected return。In general。

 it's actually not that easy。 So since a lot of you already know about reinforcement learning。

 you probably already know a little bit about how， how we do this。But so in general， the question is。

 yeah， how do we construct these policies。Okay， so as a first step。

 we're going to practice a little bit like this definition of this， this value， right， the， the。

 the expected return that I just， just defined that we also call the value of the policy。

So we here I show you a great world MP。 So this is a typical MP， right。

 We have a finite set of a finite set of states， finite set of actions in each of the states。

 We can go up left， right and south and and， and south and down。😊，And。

So the policy is defined by this， like。Blue arrows。 So I give you a policy for now。

 And I just ask to compute the value of this policy， like this expected return。

There is no reward in every state。 and there's only reward when you reach this thing。

 So here we see that the policy is going to do right， right。U right。 So it's gonna take1， I mean，1，2。

3，4，1，2，3，4，5 steps to reach the goal。 And so when we compute the value。

 we have to compute like the sum of like all these zero rewards that are discounted。

 and eventually the reward that the the policy obtains is just the this like kind of discounted thing。

If the policy would be， for any reason doing like this， this， this and eventually going here。

 the reward that it would obtain would be much much lower。 So we really want to design policies that。

 you know。Kind of go straight as straight as possible to the good。

So that seems like a reasonable reasonable goal。 That's why I'm showing this is like the problem is well posed。

Now， how to， how to solve it is not， is not is not easy。So。Yeah， so like we said， like the value。

 the value function is， is defined like this。 And we， we are going to use kind of an an intermediate。

 an intermediate tool。 This intermediate tool that is going be crucial for the entire class is what we call the state action value function or a Q function。

😊，This Q function gives you for every state and action。 It gives you the。

 the value of like what you get now， plus what you will get in the future。

 If you follow this policy from now on。So。You're here。You're typically like you're。

 you're here in this policy。You get zero reward。 and then gamma times this， this。

 the reward that you get from these states。If you're here。

 you get zero reward plus gamma times what you get in this state。 But obviously。

 what you get in this state， we we just said it's like0 reward plus， plus the value of this state。

 So you， you see that there is kind of this。K cascading effect like the value propagates along the trajectories。

 along the the states， for more or less from the goal to to where you started。

 And the idea that we are going that like Bellman developed is this idea of relying on this。

On this recursive， the recursive aspect of of Markov decision processes to define an optimality condition。

That we call the， the beman optimalality equations。So Bellman proved that the Q function。

 the optimal Q function， meaning the Q function of the optimal policy。Satifies this equality。

Meaning that。The optimal Q function in every state is just the reward that you get now plus gamma times the expectation of the reward that you will get in the future by just like enrolling this optimal policy from。

 from there on。And what this gives us is simply a natural way of computing the。

Like the the optimal value function by exploiting these recursive equations inside the MP。So。

 we are going to。Compute values and then apply the Belman equation to update the values in every state so that we can progressively converge to the optimal value function。

 And then that will give us， give us a policy。 because once you have the Q function。

 the optimal Q function， If you're in a state S， the optimal action is the one that maximizes。Thiscu。

Because this is the one here that maximizes the Q here。So if you follow the Q function， it's your。

 it's your guide through the MP。 So basically solving this， this Q function problem。

 like maximizing the Q function， finding the Q function that maximizes the value in the MP directly gives you access to the policy。

So there are two algorithms to do this。 This is kind of recursive。

 There are two different ways of tackling this problem。The first one is called value iteration。

 So it's really this idea that we that I just described a bit like， you know， with my hands。

So we're gonna leverage the Belman equation。 So initially。

 we are going put something to the values of the states。 Let's say， for example， we。

 we choose like all the values of all the states are 0。And then。We loop over other states。

 And for all the states， we compute what is the maximum over the actions of。Reward plus gamma times。

The expectation of the value at the next stage when you take this action。So this， this。

 this maximum hero is over the entire thing， right， The action is also here。

So what you can do is just in practice， you compute the Q function。

 So the Q function is for each action is exactly this value， right。

 You compute the Q function for each of the， the action that you that are available in this state。

 And then you take the maximum of the Q function。 and you give it to the value here。Right， so it's。

 it's fairly， it's easy。 And why can't we do this， Because we know the reward。

 We are still in this like non learning problem。 We are just optimizing。We have rewards。

 We have the probability of transition so we can compute all these quantities。

 It's just itating over them。And we know that by the Belman Opity equations。

 we know that this converges to the true Q value function to the true right value function。

 So this these Q functions that you will compute eventually after a few iterations are Q star or close to Q star。

 And they will give you the optimal policy。 That's one way of doing this of applying Belman equations。

The other way of doing it is directly to look at the policy。 to say， okay， let's start with a policy。

 whatever it is。 Maybe it's just a random policy that goes like one half，1 half or， you know。

 that goes like one over K in each action。 Okay， and then we compute the value of this policy in each state action pair。

So because we can again， we can do this。 We have access to the reward。 We have access to the P。

 We have access to everything。 So it's very easy。 We just， for each state and action。

 we look at our policy and we compute what would be its return， starting from there。

 taking this action。And then we update the policy。 So we do a policy improvement step where we take this policy and we say。

 now in every state， you're gonna take the action that maximizes the Q value。

And so now this policy is just a little bit better。

 a little bit more satisfying the Belllman equation。And we can reloop again。

 and we can compute the Q function again from this policy and again， update the policy。

 And that after a few iterations， directly converges to the to the optimal policy and for the optimal value function。

So there's something like really efficient， really， that kind of natural in this in， in。

 in these MP that that really relies on， on the， this macro assumption that we that we made at the beginning that all dynamic programming works。

 Dy programming is， is this， this this term that we used to。Like。Say that we can reuse。

 reuse data that was already computed in this， this graph or this， this MP in in in。

 in this case and just update recursively。 So it's a very efficient computation。

So does this all make sense。Yes。I'm gonna make a， So I have a little like kind of exercise that we are going to do together。

So I drew perhaps the simplest MP I could think of。So this is an the deterministic MP。Typically。

 I'm gonna put you at the beginning in the state 1 or in the state 2。 Let's say。

 let's say in the state 2。And you can do right or left。 If you do right。

 you transition to the right state。 If you do left to the left state with probability  one。

 So it's a deterministic MP。On the left side， there is a reward of one。And on the right side。

 there's a reward of5。So already， you kind of。Quickly in treat that， you know。

 the optimal policy is when youre in state 2 is just to transition to state 3。

And if you're in stage 3， you stay there， you continue looping and you collect this5 reward every time。

And if you're here， well。What do you do。Do you stay here or do you go to the right。Yeah。

 I heard it over there。 It depends on gamma。So to know whether you stay here。

 whether you collect this small reward or you're gonna move all the way here。

You need to compute the value function for this particular state here。

 You actually need to do it here， but it's super trivial。 right， Like first iteration。

 you're gonna immediately see that like this， this。

 this state is has a larger value all the time than than this one。

 But like for this state on the left is going to depend on gamma。

 And we want to find what is the condition on gamma for this to work。Okay。

So this is the Belman equation。And so we start。 So I wrote down like kind of drafty wrote down the initially。

 I kind of thought I would be doing on the board for you。 But like eventually。

 I think it's actually faster。 And you all get the intution anyway。 So okay， were here。

 we compute the value function for， you know， at the first iteration at the beginning。

 everybody has0。 right？ So the value function of state 1 and making a left is reward one。Plus。

 gamma times。The current value， which is 0。 So it's just one。

Then the value of one and the state 1 and making right， Well， it's 0 plus 0。 So 0。

 And we do that for all of them。 So V 2 is0 everywhere because everybody has a 0 for now and V3。

 Well it's 5， or it's 0。Okay， so the value function is now 5 because we take the maximum again。

So now we've updated this value function to one on the left，5 on the right and 0 in the middle。

And now， second iteration of value iteration。No。For the left state。

We're going to have to count plus one when we get the reward。

 But gamma times the current value of the less states， which is one。 So we have one plus gamma。Okay。

 and on the right side， same， we have 5 plus  five types of gamma， right。

 because we discount the current value。And this one in the middle。Gets。Well， it gets。

The value of this guy， because it's 0 plus the value of this guy or 0 plus the value of this guy。

But 5 time5 plus 5 Gamma is always larger than one plus1 gamma。

 So this is the value of the state now。And that gives us a condition long term。 So like。

 at the next round。Basically， when we ask， what is the value here。

We are going to compute the value of this state， when you do left。Which is this kind of discounted。

 you know， adding one reward here versus。Making rights and discounting twice what is here。

 So this is kind of what happened in Gamma times the gamma that is here。

And so we get an equation here。 And at this roundm already， we need to decide。What， for what。

 you know， for my value of gamma， what is the maximum， What is the action that is the maximum。

 Should I go right or should I go left， maybe。You know。

 the only gamma that verifies this maybe there's no solution to this equation。 And so like for now。

 maybe you need to stay left。 But as we continue iterating。

 we always have to ask ourselves like what are the value of gammas for which the optimal policies to go。

 right。Okay。This was like to make it a little bit more concrete that in general， value iteration。

Is gives you this answer to， in every state， do you want to plan ahead。

 Do you want to collect long term rewards or do you want to be greedy and collect the local rewards。

And this， this plays a crucial role in like， literally like all， all of reinforcement learning。

It also， you know， kind of quantifies how， how kind of risk averse you are。

 like as soon as you introduce some sort of nondeterministic things like， okay。

 maybe it's actually risk not risky， but it's like you don't come。

 you don't transition to the right every time。 Maybe sometimes you stay here。

 you need to take this into account because if transitioning here is only probability one half。

 then it it affects your， your thebelman equation。And so now the value of gamma that you need to really value this state is actually really。

 really high。 You need to be able to like， plan ahead many， many moves and not just two moves。Okay。

 and that also show you shows you the， the very important role of the discount factor in this problem。

 Dis factor is a property of the agent。 It's not given by， I mean。

 you can think it's given by the environment， but intrinsically， it's really you as a。

 as a designer of an of an R algorithm that is gonna say。

 I want an agent that looks into the future or or not。 And like this。

 this affects the optimal the optimal solution in your MP。O。

 problem in reinforcement learning in general， we don't know the model。We don't know R。

 We don't know P。 So there's no way we can compute the， the value iteration， like exact updates。

So we are gonna have to deal with this。So the question one is。

 how can we evaluate the policy if we don't know the reward function and we don't know the transition probabilities。

 And the question too is， okay， once we have a policy and we can roughly evaluate it。

 maybe with some stochastic， you know， estimates， How can we improve it， How do I have a gradient。

 You know， How do， how do I take into account this feedback and try to。Maybe try a different action。

 You know， if my policy was going this way。Like， what do I know about the value of a policy that would go this way。

This is， this is like the problem of in reinforcement learning is that there is only the data you have。

 There's only the data you collected。 Your dataset set is not a given。

 Your dataset set is is something that you work for。 and you need to take actions for。And。

That's where we're gonna， that's what we're gonna try to see now in， in like。

 more or less like the entire rest of this class。Are there questions on like this whole value iteration and。

 you know， the definition of， of the good in， in， in reinforcement learning and in Markov decision processes。

Just。哦。然吧。Is gamma fixed for all the steps。That you， you have。 Did I repeat all the question。 Okay。

 is gamma fixed for all the steps。 So， yes， gamma is fixed for， for all the steps。In general。

 you know， it's like。How can I say this？ It's almost like you're defining a loss function here with this gamma。

 right。嗯。Yes。So this， this is this is imposed by the environment R。

 and all the transition that result from this state and this action are imposed by the environment。

 So somehow this gamma kind of parametermets your goal。 It's your loss function。 It's your your。

 I mean， in our L， we talk about rewards， right， So like we really always opt for some of of rewards。

 But really， like intrinsically， your gamma is what you're optimizing for。 but。Choosing gamma。

 like in， in a， you know， in a real， real scenario where you would， you would have， you know。

 some problem and you don't know what should be your gamma。That's not so obvious what you should do。

 And that's， that's a problem that came， I think that came into like the the， the interest in。

 in the reinforcement learning community a bit late。 David Silver has worked on this。 Like。

 what's the role of gamma。 How do we choose gamma。 Can we like meta learn it there。

 there's the work there， But it's Yeah， the gamma is really like your， your parameter。

 And you keep it for the entire learning。I think it would be， you know。

 it would be also interesting to explore I like kind of situations where somehow at the beginning。

 you're willing to plan ahead a lot。 And then eventually， you kind of readdress for some criterion。

 But I， I wouldn't know how to do this。 Like I think this is kind of an an open question， yeah。Okay嗯。

So we did all of this。Okay， so like I said， we're gonna start with policy evaluation。

 So I give you a policy。And now the question is， how do you evaluate it。

 So we saw at the beginning of the talk that it's super easy in an MP。

 Usually you just count like the rewards on the way。 you discard them， you discount them。

 And that's it。 But in a real MP where you don't know the reward function and you don't know the transition probabilities and everything。

 Well， the only thing you can do is just roll it out， like roll your policy in your environment。

And obtain a trajectory。 So we always assume that we can。 We can do this， that we have a simulator。

 We have an environment where we can run our policy and get data。 This is kind of the， you know。

 this is where our L， you know， that's what our do does， that we can collect data。

And we can collect data in， in this， like episodic way， you。You take your policy。

 you roll it in your environment。 You obtain this like trajectory。 It's。

 it's only one policy that did this。 You obtain。This like rewards on the way and all those things that you've observed。

 you compute the value， and then you can update for the next for the next episode。

 you could update if you want it， or you can run another episode。 And， you know， it's like， for now。

 what we say is were， because we're just evaluating this policy。 Were going to keep it。

 We're just going to run trajectories， collect data and then run it。

 run it until we feel like we have a value that converged。Okay， so again， the value or the。

 the definition of the return。 Like if this one， I've really。Kind of insisted on it。 Okay。

 there are two ways， two major ways of computing a value， evaluating a policy in an MP。The value。

 the， the method number one is what is called Monte Carlo estimation， meaning。I have right now。

 like a policy that starts in S 0。 I can enroll it every time I unroll it。

 What I obtain is a random evaluation of this entire sum。 So G。

 like my G here or G of S 0 is the entire， you know， value from S 0 all the way to the end。

Then at S1 from S1 on， I can compute。The discounted rewards from there。 And I have the。

 I have a random estimate， a random sample from this random variable here。Right， so here。

 here we have a random variable， and the value is an expectation。

 So we need to compute a meeting over those things。 kind of。 we need to eventually update。

 update this thing。So we are going to obtain samples from this entire thing for each state。

Along the trajectory。So we enroll this trajectory。 And for each of the state in intermediate states。

 we compute these these values。And we update。 So the。

 we maintain these like value estimates for this policy and for this current， you know， MP。And。

We update， we update the at the end of this trajectory。 We update the value by just。Kind of in。

You know， here look curve。 Okay， we by simply。All one plus some learning rate times the error。

 the error we make being the one that we just collected。

 collected minus what we thought the value was。So it's a very simple， you know， update。

 update system。Except that we need to collect an entire trajectory and to compute the entire gain from every state until the end to obtain an estimate。

So this is the main problem of Monte Carlo estimation。 It works， and it is unbiased。 So it's。

 it's a nice way of computing this expectation。😊，Just sampling random variables and updating the mean in a kind of a progressive way。

O， except that like， we need these complete sequences before we can update the mean。And somehow。

 we also rely on having for sure episodic environment。 So here it's not a big， you know。

 I have assumed that we have episodic environment。 So like fine。 But in， in general。

 in reinforcement learning， you can do a lot of things or so outside outside of episodic environment。

 So that would be a big constraint for you。 You could not use this method。Okay， so people were like。

 maybe a Monte Carlo estimation， not so efficient。 Let's do something else。

Let's use what they called or a rich Sa called temporal difference learning。

So temper difference learning is saying that， like。Actually， on this trajectory。

 you can cut it in in pieces because because it's a Markov process。 So on the way。

 you have state actions， reward and next date。Okay， and。At every time， at every time T。

 every step T in your， in your trajectory and in your learning process。

 you have an estimate of the value。And you're going to update it by its current value plus the learning rate times the error。

 again， kind of this a gradients。 It's like a gradientcent kind of argument。

 except that T D is not the gradient of anything。 It's like people keep repeating this。 Its very。

 it's very important。 TD is not the gradient of anything。

But it's still like this gradient kind of a idea that that you can have in the back of your head。

What we do here is we're going to say， what is the current value that I believe in。

 It's the bellman value。 It's reward。Plus， gamma times the value of the next state that I currently have stored in my dynamic programming in my。

 you know， in， in my system。So this R plus gamma V is kind of this estimate of the bellman current bellman value of my policy。

Minus。What I believed so far was the value of the states。So for every state action reward next date。

 I have an update。Of the value of the policy， just using this kind of bellman thing。

This new update is biased。 It's biased because this thing doesn't really estimate the true value。

 right， as opposed to the gain that we had before。 This gain here is the true value of the state。

 It estimates the true value of the state。Here， no， it's like your current estimate， and it's biased。

But you have a much lower variance because you don't accumulate all the random reward on all the rest of the trajectory。

 You kind of stabilize your estimator by only taking the local estimates what's going on at these states in this area of of the MP。

 if you will。So this idea has been pretty successful and is gonna be quite， you know。

 at the heart of a lot of things that we are going to see afterwards。😊。

And I think I wanted to give an intriition of the difference between those two things。 Yeah。

 maybe I have time。 I I have until like 1015， right。Yeah， okay。 Should be good。Okay， so I again。

 made some computations for you。 So we take this like。Great world that we had that we had earlier。

And。So the question is going to be to， to compute the value of this state using this Monte Carlo estimation。

So typically， like at the beginning， all the estimates are 0。 You know， like we don't know that's。

 that's our policy。 that's the policy I fixed。 So my policy always does this。

 So every time I run my policy， it goes up and write。 and it collects a reward of one。

 So it's super easy。 The G of S T is one every time。Except that， no， it's not one every time it's。

The G of S T here is one。 This is the I the reward you get。

 But the G of S T here is 0 plus gamma times 1。 So it's gamma。

Then the G of S here is 0 plus gamma plus gamma square times 1。 So it's gamma square。Okay。😊，Alright。

 and now。I wanna get I want to get to the next step。 So now I have my estimates， right。

 whatever they were，0。576 and 0。9。 So these are the two things。

And seems like I've already spoiled the answer。 I know。

 this whether this was the intermediate one that I didn't write because didn't have space。 Okay。

 so like， this is like the current estimate that we have of the value of these states。

And now we run another trajectory， and we observe another one here。

 And we' are going to update all the states on the trajectory。So once we have a trajectory。

 we can make an update of all the states。 but this update is really gonna take like the。

 the whole reward。 you know， we wait， and then we take the one all the way to the end。

 So then what we get is like， well， this guy is gonna get 0。

9 plus whatever is alpha Al times the difference，1 what I thought the state was 1-0。1。 This is-0。9。

 This is 0。1。 So 0。99。 So were， we're getting really close to 1 immediately。😊，Right， and the。

 the question is， what would be the value here。So the value here。

 we're gonna just apply this formula。 So I think I have written it。

Value here is pre value plus alpha。Times。Gmma times 1。So gamma minus the current value。

 And this gives gives me already like a pretty good， pretty good estimate。 You know。

 we are very close to the open already。 So in one iteration in two iterations in this very simple MP。

 we get super close like values to the， to the policy。 So it's a fairly efficient kind of system。

 But I need to generate an entire trajectory before I can update all the states。

And on the other hand， temporal difference。 So temporal difference， you know， similar。

 I rewrote all the things。 So here， you know， every time I make a step in this MP， I update。

So I'm here。 I'm going to update the value here。 It' is gonna be updated by 0。

 because nothing happens。Then I will move here。 I update the value of here。

 and it's going to be updated by 0 because nothing happens。This 0， the 0，0。 And then。

 so these all these states here， they all get 0。 So that's what I wrote here。 except this guy。

 this guy gets 0 plus。Alpha times what I thought minus the true value。 And then like， you know。

 this is the this， this equation here gives me the open night。 So now， after one trajectory。

 I have already one state that has been updated。And now I restart。 And， at the end。

 when I arrive at this date and I transition to this state。I can already update its value。

So you're gonna tell me， yeah， it's great。 But like in your previous example。

 we were updating the entire states on the way。 And you're right。

 in like a short episodic environment， like the 1 I presented before， do Monte Carlo， for sure。😊。

But you can see that like， if you had a very big environment and you had intermediate rewards。

Like on the way you could like collect， I don't know， apples。 And then then the end。

 you have to get out of the thing。 Like T T certainly makes a lot more sense because every time you make a step in the MP。

 you， you update your value and so you can progressively update your policy as you go in a way。

 you don't do it because you， you need to wait for the end of the episode。 But， you know。

 you update the value on the go and you can you can make you can have better。

 better estimates of of the value of the policy on the on the trajectory。

And this is exactly the idea that is exploited by Sasa。So subsize this old algorithm。

 But that's still， I think， fairly relevant。 that's like。Or at least， you know， yeah， I mean。

 I don't know how relevant it is。 but I think it's， I think it's a good illustration of。

 of like how to use TD learning on on policy in an MP。 So it's exactly what we just did。

 But now we're gonna use these like iterations， these。

 these TD learning iterations to learn a better policy on the way。 like as we repeat episodes。

So I introduced this new thing to this little like orange box here。

 introduces this notion of epsilon greedy policy。 Epsilon greedy is what we do in reinforcement learning or what a lot of people do in reinforcement learning to do exploration。

When you have a value， like we said， when you have a value of a state， a Q value in a state。

Like we said， this guides your policy。 You want to follow this Q value。

 But if you only follow your Q value， you never explore。

 You never explore what you could have got if you were to go to the other side of the MP。

And this is important。 If you don't collect this data， you never get to observe what。

 what you could have had in the， on the other hand of the MDP。 And so， you know， you， you。

 you kind of feel that like， you can't get accurate estimates of a value if you don't have samples。

 right， So that's how that's why we introduce Epson ingredient。But。Yeah。

 so we're gonna use this epsilon greed policy to act in our environment。

And what the only thing we want to do now is。Update our Q function to update our policy and get a better and better policy。

In the same way as we did value iteration before， except that now we cannot compute the exact value update value We。

 we have to sample it from the， from the， the trajectory。Okay， so。For each episode。

 we're going to sample this state action， reward， state and action。 So next action。

The depends hence the name of the algorithm。We start in a state S。We get。

 we take an action from Eps greed。 We get a reward。Then we observe the next state。

 And in this next state， we ask our policy， what would be the action you would take。

So we asked this policy what， what action they would take。 And we， we use this action here to。

 to compute the update。So the Q function gets updated by the usual， like TD learning。

Update that here estimates， you know， the discounted value of。

 of the current like state minus what we thought it was。Okay。So if you reiterate this， it's been。

 it's been proved that there are convergence results of these things as long as you cover the state value well。

 So as long as you have an epsilon in your Epsilon greed。

 So this is just applying the value iteration algorithm or the TD learning updates to。

 to obtain the the value of the in the MP。So， I mean， there is a。

I guess I don't know if I can do this。Yeah， so this is kind of what happens when you run it。

As you see， like the， the values， they start updating from the， from the end， right。

 at the beginning， you only get updates from where the rewards are。 And as you run episodes。

 these updates， they propagate。 And because you're doing a son greedy。

 sometimes you take this other pass， but not so often。

The values on the main path that you initialize are kind of more often updated。 But eventually。

 you know， you also get estimates on the on the other path that like what， what you should do。And。

 you know， this is just 100 iterations， but you already get a fairly， you know， good idea。 you know。

 in every state， you have a fairly good idea of what you should do。 right， so 100 itration。

 you already know everywhere， what should be your， your， your best policy。Okay。So。With like。

 this is kind of， I would consider， you know， the， the， the， the most。

 the most basic but kind of necessary knowledge about reinforcement learning。

 We work with Markov decision processing processes。 And the first problem。

 the first challenge is to compute optimal policies。

And once we know how to do it in a Markov decision process， when we know everything。

 we can ask the question of how would we know or how would we do if we would actually not know this。

 these models， And then we compute we， with sample trajectories and by kind of smart updates of our estimates。

 we compute two values， and we， we end up with like the the optimal policies。Okay。The question is。

 like， can we do better than Sasa and what if the， the state's action pace state action space would be。

 for example， very large or structured or infinite， typicallyy， So this is like kind of what。

 what has been achieved over the past the past few years， I actually。

 I'm not sure how much time I had for it is this interit also so。Maybe笔。Yeah， I don't know。 okay。

Yeah， maybe I'll keep it for the end。 Okay， we're gonna， I'm。

 I'm gonna just stop for a second just to get questions， maybe。And we I keep the little。

 the little intermediate。B for the end。No questions。Your questions。

You a questionSo what is Turkey here。Did anyone actually use Sasa。Ever。What。

 so I'm guessing that like people use here if you， okay， maybe， maybe one here。

 like maybe some people here use more Q learning。We pot gradients。Yeah。So， yeah， I think。

The reason why I presented SARSa。Is because it's so similar to Q learning， but not quite。

Was it clear for all of you who know Q learning， Was it clear for you。

 What is the difference with Q learning like。Do you know like how Q learning is different from this。

C， yes。So what， what， how， what's the big difference with Q learning。So what。

 so what of policy means， I haven't said so much， What is the on policy part on this slide。 So like。

 maybe like， what's， what's of policy， what's on policy and what's of policy， As far as I remember。

 with cool learning， it's updated based on the best value。

 not on the value that we got on this specific run。Yes， exactly。 So I'm gonna repeat that。

So what is very important here in Sarsa。 and what was。

 it was the original idea that people had is that。Okay。

 if you wanna know in which state you end up next and what is the value of this next state。

 you need to get a Q value。And what is Q， What Q value do you w to put here。

 You w to put the Q value of a next action that you policy， your policy would take。

 So you have to sample from your policy。 the next action A prime。 That's why we call it on policy。

We say we ask the policy to generate what would be the next action。Whereas in。In Q learning。

 it's of policy。And it's of policy in the sense that this action here。 Why do you need。

 Why do you need it to be the action of your own policy。

 It could be just the best action or your current believer what the best action is。 typicallyy。

 So you would kind of more immediately like more directly take what is like the optimal the decision here and update this value if something that's like is a little bit biased towards the optimal policy in a way。

And this is the idea that was proposed in the end at the end of the the 80s。

 I think in 1989 or something by Chris Watkins and Peter Diane。And that kind of completely， you know。

 even if it's a small modification of the algorithm， it really come completely changes the the So we。

 we just said all of this completely changes how we， how we construct the algorithm。

 And it will allow us to leverage either like other logged data and do all sorts of leverage supervised learning。

So this is the， this is really the， the， the， the thing that's at the heart of， of Q learning。

 and that really differs from， from this naive maybe idea of Saa。

 which was to just use your own policy tool only like never， never bootsrap from something else。

 always use your only your own policy。 But why not， you know， why。

 why not bootsrapping from something there something else。Okay， so Q learning， we just。

 we just said it， you know， without， without the images。 But like， essentially。

 Q learning is the same as SArsa。 You start， you， you're going to run this Epsilon gradienty policy。

Start from some， some star some states。 And then from this Epsilon greed， policy， take an action。

Observe a reward。 Oberve a next state。 And in this next state， you update the。

 you update the value with the best action。 What， what you believe for now is the greedy best action in this next state。

And。Well， a priority this is kind of what another policy would do， not yours。

 Yours is excellentps greedy， right， but like another policy would do。 But in general， it could be。

Any other policy。 I this like of policy ideas， this， this update here。

 you could kind of use something else。 And this is what deep reinforcement learning is going to leverage。

 Eventually， I have a couple of slides afterwards。 But like what you put here for your TD update can be something that you decide you stabilize you design with。

 with previous data。And this is going to help with， you know， with learning。Okay， so we just。

 we just went over this。 The， the only difference between。

 between Q Sasa and Q learning is what you put in here in， in the， in the update of the。

 of the Q learning， correct。So function approximation， Why is it important， Why。

 Why is this of policy learning giving you this new power to kind of leverage some。

 some other knowledge or some other things that you could do。So typically， I'm gonna， you know。

 for the sake of making simple slides， I'm gonna imagine that this function approximation is a linear function。

 But in all generality， you can always assume that there is a parametermetized function。

 So typically a neural network that approximates this Q function。

 So in every state and action you have a function that。Approximates the value of the。Or yeah。

 the the Q function。 And here is gonna be this this linear thing。 And the goal now。

 instead of directly estimating a Q Q of S and a entry is going to be to estimate the weights。

 the weights of this neural network that approximate that is supposed to approximate your policy。

So you wanna do this like least square， least square minimization， where you。

Try to minimize the error between what is the true value of your policy that you're gonna need to use data to like sample trajectories。

 as we just saw， right。And what is the current estimates that you maintain by， by。

 by estimating these weights。So the nice thing with least square is that like。

 this gives us a very nice gradient so we can compute the gradient with with these like linear functions。

 So linear functions， it always makes things look nicer。

 But like you could prior just do the same and compute the gradient as well for your neural network as long as different differentiable and nice。

😊，So here I， I look， I estimate what is the compute to what is the the true gradient。

 the true gradient is the expectation of like the feature vector times the error between the true value and the estimated value and what you want to do is update like update the weights towards like this kind of gradient like using this gradient。

 But you're gonna need to estimate this because we don't know what is this Q pi of S and A。

So to estimate this， this is where we use the TD update or the TD evaluation。

The T T evaluation is gonna say， you're gonna generate the trajectory， right， So that's。

 that's still allowed。 You can compute like， for each state。

 You can compute actions and generate this trajectory。But in this trajectory， you。

 at every state in action， you are going to。Estimates this Q pi using the reward plus gamma times the maximum of the current estimate that you have for the Q function。

The trick is。 And this is kind of what， I mean， I， for 1， I understand。

 this is what really made this whole deep R work。 One of the things that made it work。Even if。

 you know， I'm， I think I， I don't think， I don't know how much we have like a strong understanding of how this works。

 but like。The trick is to use。A different set of weights for this estimate here that you would strap from for your TD update。

And the weights that you actually， you know， use in this other， you know， the kind of the old。

 the old estimate that you're that you're using that you're bootstping from like I said bootstrapping toys。

 But like this， this， like this weights here are called target weights and they。Typically would say。

 they would stay what table。 You would use all weights。

 or you would only update these things every other， every， I don't know how many episodes。 Like。

 this is kind of your own。Cooking and how you， when you code up these， these things， how you。

 you decide to do it， But it's very important to stabilize your TD update。 your TD estimate to。

 to stabilize your gradient estimation in the， in， in the， the update of the weights。

But you see here， you kind of leverage the fact that you're off policy and you have the right to put not anything here。

 Like anything would be， you know， I wouldn't have a result of convergence for anything。

 whereas there is a result of convergence for exactly the max of the Q function。

 right this is this is the whole thing。 But like in deep Q learning。

 Were not really fundamentally interested in like convergence result。 We're interested seeing how。

 how to make an algorithm that that really works。 And here， like this is， this was the。

 this was a strategy the strategy that people use and that eventually made things work。

Leveraging a Q function。 that is of like another different policy， not exactly the。

 the maximum of the one you're following。Okay。So as we said。

 true learning is enough policy algorithm， and it kind of leverages like。

 it can leverage other types of estimates。 You can plug plug in like in this this part of the update。

 kind of other things。 That's the magic of， of true learning。😊，嗯。And it's based on， it's。

 it's based on this like value iteration kind of process， right， I try to compute the value。

 and I infer the policy from it。And the， the next question I'm gonna， you know。

 I'm gonna cover before， you know， before we finish is the question of。

BPice iteration and how we can do like this。Evaluation， and then policy improvement step in when we。

 when we directly optimize policies。Okay， are questions on queue learning or anything that's。Yes。

 over there。Yeah， one question to the selection of this other policy。 So if I speak like a physicist。

 you would choose it to cover the whole face base or like to have a good， Yeah。

 good cover of the face base。 Is there any techniques to do something like that in the realm of reinforcement learning。

So I didn't understand the wh which space， the face space。 So the phase space in physics， you know。

 it's the set of possible states that a physical system can attain。

 And I thought that it's kind of an analogous of what did do hear， right。

 you want to have the a variety in the states of。I see a system where you wouldn't be entirely sure which state you're in。

Or is that like that like that you have several potential states where you could be。 Yeah， normally。

 you start with an initial state and then the dynamics of your physical activation that describe the model after the process you are watching describes you how the tra trajectory of the state will evolve through the phase base。

Okay， and so you have these equations that describe how you're going to like。

 how this trajectory is gonna。 And so you can already predict it kind of like。

 if you're in a certain state， you have equations that would allow you to predict where you go。

Afterwards， ideally， yes。 And what you usually want to do is like to cover a broad range of the space so that you have a broad cover of the physical model of the states you' are like observing in an experiment or something like that。

Yeah， so， okay， I， so this might be。If I understand a question correctly， it might be related to。

 to what is called model based reinforcement learning。 So where， you know， here I。In。

 in nowhere in these algorithms。I try to estimate the。

 the model or to have a good way of predicting where my。

 my agency is gonna go next or where what is the the the next， the next steps of the trajectory。

 I don't have。I mean。I， I am not even trying to。To get this model， and。

This is something that people have， you know， there essentially the devised reinforcement learning in two kind of paradigms。

 This is what we call model free reinforcement learning。 Just go with trajectories。

 You don't know what is this system。 Who knows and estimate value functions。

 But then there is a whole of other kind of。A way of looking at the problem that is like， okay。

 this is， this is actually a real system。 This is， this has like dynamics that I can。

 that I could estimate。 And as I observe my， whatever your agent。Doing trajectories in the system。

 I can estimate the model， and I can start predicting what is going happen and maybe use these predictions to guide my system。

And that is one of the solution， or maybe one as one way to go to solutions for a better exploration。

 And I think you're gonna be told more about this in the next couple of hours。 But essentially。

 here you see， my exploration is completely naive。Because I don't know anything about this system。

 I can only， when I want to explore， I can only say。You know， with probability Epsilon。

 I'm just gonna do something completely random。 But if you start having a notion of how your system works and how。

 you know， how you， your， you could guide it or where predict where you're gonna go。

 then it becomes a little bit more natural to say， oh。

 then maybe I should go this way or I should go that way。

 I should try this because I could imagine that my system goes like this。

 I don't know if like that entirely like answers your problem。 But like when I。

And so' was your question， But I。Does it。Yeah， thank you。Right， so， so in physics。

 what you want to do is you' not want to get stuck in a certain region of the phase base because that we would mean you could not cover with your model the observation you made。

 And probably from what you explain now， you do it just with statistics。To get a variety or。So you。

 if you don't have an， the question is like kind of the initialization， like how， like in physics。

 you don't wanna be， you don't wanna be initialized in some。

 some parts of the state space or get stuck so that you miss some part of the dynamics of the system。

 So you want to have a like cover of everything that could potentially happen so that you have a whole description of your dynamical system。

And so I was wondering how you can bring the variety into your Yeah I， that's like。

 that's the question in reinforcement learning。 It's like at least from my perspective。Right now。

 we don't yet have a very good understanding of exploration， meaning like how to。

D diverseversely explore the space in a way that covers well the diversity of the state space。 Okay。

 in like， if you have a great world like this one。Sure， you know。

 you can compute in every state like how many times you visited and stuff。

 But like if you're a very large system and maybe some states are like。

 maybe with like some geometry that's complex。 how do you really cover the state space。

 This is just a super hard question。 And in deeper reinforce learning。

 it poses all sorts of of problems。 And you know， I'm far from having all the answers to this to this question。

 because it's really an open one that a lot of people are trying to address in different ways。

 And I think， tello， you're gonna talk a little bit about this from what I understood。Yes， okay。

 So yeah， you're gonna have a little bit more about this。 But。

 this is like a super one point question。Okay。Last stretch， policy gradient。

 bear with me for another five minutes。It's gonna be relatively quick because I gave up on doing all the proofs。

 It was hard。 But yeah， no， I mean， so there is， there is policy gradient is this like super interesting kind of。

Paraigm of algorithms that somehow was much less explored。 And I don't know。

 I think there was a phase where all of reinforcement learning was essentially key learning。 And now。

 like most it's kind of rewiing to like switching to this。 And， and。

 and a lot of people start like people that had a background in optimization。

 start being interested in those methods because we it's a non complex problem。

Of optimizing policies， parametermetized policies。 And there is interesting theory to do also like convergence of these methods。

 so。Okay， what are we talking about。We are gonna assume that we have a policy that is parameterized。

 So that is directly the policy that's parameterized。 It's not the value function。

 We assume that the policy obeys some， you know， representation of the state space and some parameter theta。

 So typically， you can think of it as like， it's a soft max。 You know， if it's a nice， great world。

 you have for each state and action。 you have a parameter theta。

 And what your policy does is it it takes a policy。

 it takes an action According to this probability soft max probability distribution。

Or it's a neural soft max。There is a neural network that kind of embeds the state action space And you take the softms of this neural or presentation。

That's ways to parametermetize your， your， your policy。

And then we still want to optimize this value here in expectation over the the first states。

 So maybe that's also sort like a point that I had not I highlighted too much。

 but often we assume that we have an initializing measure。

 And we all the take expectations over this initializing measure。

 So it's a fixeding every time we restart our environment。

 we restart in a state thats sampleed from mu and mu is fixed。And Meu is often a di mistake。ok。

And now we have a function that is a function of pi of theta。 So it's just a function of theta。

So we can optimize it。 We can try to directly optimize this function of theta。

 The theta is hidden in here。Because a of T is a function of theta in every state。And we're going to。

 you know， collect trajectories。With the goal no longer to， to estimate the， the。

 the police to estimate the value as we did before， but to estimate the gradient。

Of this function at the current theta。Right， the one thing we need to do is great and decent。

Is this gradient here。Now， you're going tell me wait， you just said it's non convex。

 Why are you doing great and decent。Because。Because like， there is not so much else that you can do。

 like that you can try。 There are other things that you can try to like， you know， try to leave the。

 the local optima and things。 And this is kind of an again， an open research questions。

 And I'm sure there are like experts in the room， like better experts in the room than than me on this topic。

But like， for now， we are going to assume that。Provided some initialization， maybe some no， some。

 some something。 We are gonna assume that stochastic gradient is is an O algorithm to reach some at least local minima of this function。

Okay， so how do we compute the gradient of a gain function or of a function that is look that looks like this where theta appears in every single action and every single next state depends on my previous action。

 right， We have a long， complex random sequence that all depends on theta。

 So how do we compute a gradient for this。So we are going to use a very smart trick。

 I don't know if people call it like the policy gradient trick or it's like just the policy gradient theorM。

 but it's this like log trick。 So look at hits。 It， it just happens in like two lines。

We're going to say that this gradient of the policy at state action， at this state action pair is。

We multiply and divide by the policy itself， the value of the policy itself。

And then we notice that this thing， this gradient over pie is the gradient of the log of the policy。

So now we can say that just to compute this gradient here。

 we can have this like pi times the gradient of the log。Why is this useful。Well。

 because we're taking， you know， generally like expectations over this type of， you know。

 over what Pi is doing。So it's going to really nicely rewrite my。

 the gradient of the policy as an expectation of the total reward of this trajectory。 So remind。

 remember， we generated the trajectory。 So we have state action， state action reward。

 state action reward like this for like an infinite sequence。So we can' compute this R of T。

 It's distinct thing， right， The return， the total return。And then for every step in the trajectory。

We compute this gradient of。Pie， as like。The sorry， wait to what did they do。

 I think it's the log here。 Yeah， that， that's， that's a big mistake。The gradient of the log here。

Right。Okay， so。This， obviously， we don't have the expectation of it。

 but it's okay to just have a stochastic estimate of this gradient using the you know。

 just the trajectory that we have and the one step of gradient descent。

 And this is what people have been doing。 And the power of this methods is this like scalability and generalizability to。

Almost any functional approximation that you can think of and for which you can easily compute log gradients here。

 if you compute the log here and you compute the gradient。

 you end up with just the gradient of this thing。So it's。

 you directly play with the gradient of the function approximation。So this is。

 this is why this type of methods has been like really， really successful and really interesting。

 And even from a theoretical point of view， like， has a lot of， you know。

 open problems and super interesting questions to， to be working on。Okay， so， you know， this is for。

 this is all for reinforcement learning。 I'm exactly on time。 so I will not take too long for。

 for the rest of， you know， this I， I just want to say that like。This is， this， like I said。

 this is like just a friendly tasting of what， what are the different aspects of reinforcement learning。

 There are so many things out there， like between model free， model based on policy and of policy。

 I try to give you like some， some initial understanding of。

 of what's what's going on and and how these， these algorithms work and how we deal with these dynamical systems where we don't know the the dynamics。

 actually。One thing we've mentioned a little bit through the question is this， this like exploration。

 we've， we've relied on Epsilon greedy， and like I said。It's probably not the best thing to do。

But to do better。You cannot need to be able to direct this exploration。

 How do you direct exploration。 You need to kind of tell your algorithm， Hey， over there。

 I know already what's going on。 Don't go there over there， I don't know。

 And there might be a reward。 I have some， I have some measure of uncertainty that tells me that。

 you know， I don't know enough to discard this path。 So let's go there。

 And it's like uncertainty quantification guiding exploration is has seen like a lot of progress over。

 let's say the past 10 years， but it's still like a very important open problem。And， you know。

 how to combine them with perhaps model free algorithms， So not。

 not necessarily using the entire model。 and all these questions are are， are really important。嗯。

I've mentioned come like this like convergence guarantees。

 We have convergence guarantees for a lot of the R algorithms Ive， I've told you about。

 but it nondeep， right， like all the lies linear or tabular settings， we have convergence results。

 But there are， for most of them asyotic convergence results。

 meaningan if you run this thing for like ever。 And we're talking millions and millions of iterations。

 eventually， you can prove that you end up in the right， you have the right optimal policy。

But nony result， efficiency of these policies， How many iterations， How many samples。

 How many episodes do you need to actually identify the best policy。

 And we high probability or in expectation， all these like important questions in theory are kind of we only scratching the surface。

 We have initial results like the， the， the actual nony analysis of Q learning。Came out in 2018。

 right， And this is just the first result。 So I think there is just a lot of super interesting question in RL theory。

 So， I mean， this is what I work on， but just to say， like theres。

 there is a very important community working on Ral theory and trying to understand how these algorithm works and how we can make them more sample efficient。

 This is like how can we make R not just a big， like large simulator kind of kind of tool。

 but something where that we can work with with like smart algorithm that could be used for applications such as drug discovery and you know。

 places where you can't just simulate forever， you know。

 things like like with compute like problems where there is like collecting the the sample。

 the trajectories are is actually hard。And with this， I think I will just conclude。

 Thank you so much for your attention and your questions。



![](img/317a17805017238441f55189e7b9f180_2.png)