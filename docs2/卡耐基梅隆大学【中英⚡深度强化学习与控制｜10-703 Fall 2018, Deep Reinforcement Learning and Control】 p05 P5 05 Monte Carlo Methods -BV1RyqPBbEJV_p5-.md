# 卡耐基梅隆大学【中英⚡深度强化学习与控制｜10-703 Fall 2018, Deep Reinforcement Learning and Control】 p05 P5 05 Monte Carlo Methods -BV1RyqPBbEJV_p5-

About Monte Carlo methods and the idea of。B Carlo methods is simply。

We collect a bunch of samples and estimate the value function or the control function or quantities related to those from those samples now why would we want to do this？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_2.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_3.png)

The main reason is that even though we like。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_5.png)

The dynamic programming methods that we've talked about already。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_7.png)

And in fact， if we have available the whole MDP that as we know。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_9.png)

The expected reward for every state action transition in advance。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_11.png)

And we know the transition function， the probability distribution on the next state and on the reward。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_13.png)

For any state action pair that we execute， if we know those things in advance。

 then really we may as well use the dynamic programming。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_15.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_16.png)

Eethods that we talked about before。嗯。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_18.png)

Except for one little complication， which is that if the state is very large。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_20.png)

Yes we know。Those dynamic programming methods。Require。N squared computation。

If we have n different states， and so it can get expensive。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_22.png)

But except for that， dynamic programming is really a great idea。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_24.png)

In the real world。Like the one you and I live in。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_26.png)

We don't really know the transition function。You kind of know it， but you don't really know it。

 you don't really know what will happen if you try to stand on your tippy toe on this little piece of black tape that's sitting in the middle of that metal square on the floor。

 maybe it'd be slippery and you'd fall over， maybe it would be like Velcro and hold you。

 there's plenty of stuff you don't。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_28.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_29.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_30.png)

Know about how the world is going to operate， partly because you can't observe all the coefficients ofion。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_32.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_33.png)

So in many cases， we're interested in reinforcement learning。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_35.png)

What we don't really know。我。What the transition function is。And even what the reward function is。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_37.png)

So in this case， it turns out Monte Carlo methods are a great idea。😊。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_39.png)

And so that'll be the first topic for today。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_41.png)

I should say I stole many of these slides and edited them from Rassalli Kutoff。

 who taught the course last semester， who in turn stole them。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_43.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_44.png)

Probably Catarina。Who， in turn。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_46.png)

Got built on ones for M S at Dave Silver。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_48.png)

Okay， so here's the idea。We're going to use sampled experience to calculate our。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_50.png)

Our values and our policy。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_52.png)

We can use that as I said， if we're model free that is。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_54.png)

In this course and in。Papers that you'll read on reinforcement learning。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_56.png)

People use。The term。Model based or model free。 the use return model to refer to。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_58.png)

The transition function。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_60.png)

啊。Literally the probability of the next state。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_62.png)

Given the current state in action。So as I mentioned， if we don't have a model。

 then it turns out Montecarlo methods are going to be good。

 or even if we have a simulation of a world like a video game。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_64.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_65.png)

And we can run that simulation， but we don't actually have。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_67.png)

Access to probability distribution。あ。We can。Can use it in that way， too。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_69.png)

And it's， in fact been very。Successful in those kind of simulator worlds。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_71.png)

啊。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_73.png)

So。They learn from。Complete sample returns。 What do I mean by that What I mean is that by a complete sample。

 I mean， if we want to know， let's say， for example， under policy pie。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_75.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_76.png)

What is the value of being in state S， what is its discounted future reward？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_78.png)

Then one way we can do that is。Get a complete sample all the way from state S following policy pie。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_80.png)

To the。Terminal state。In fact， when we talk about Monte Carlo methods。

 we're going to really restrict ourselves to talking about these kind of。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_82.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_83.png)

Worlds where there is a terminal absorbing state that once you get there。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_85.png)

We reset you into a new place in the world and you live。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_87.png)

A new episode。Okay， so when I say in that context， when I say a complete sample。

 what I mean is if we want to know the value of。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_89.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_90.png)

The discounted future reward of being at state S， then a complete sample for estimating。

Would be a complete trajectory following policy pie。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_92.png)

From that state。To subsequent states until we get to the terminal state。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_94.png)

That'd be a complete sample because it tells us。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_96.png)

All of the actions and rewards that we get along the way。嗯。So that's。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_98.png)

The basis of it。And so a sample then is going to be really just a sequence of state action， reward。

 state， action， reward， et cea， till we get to the terminal state。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_100.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_101.png)

And if we want to evaluate a particular policy pi， then what we're really interested in estimating for any given state。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_103.png)

ST。Is the sum of those。Discounted。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_105.png)

Future rewards。 and obviously， if we have。If we run our agent through the world and generate a complete sample according to P。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_107.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_108.png)

Then。That sum right here will give us one sample。Of the cumulative discounted reward from state。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_110.png)

And if there's non determinism involved either in。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_112.png)

The reward function or the outcome of states， or we have a non deterministic policy。

 any of those sources of nondeminism。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_114.png)

Then starting from the same state T， we might on different。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_116.png)

Attempts obtain us a different。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_118.png)

Some of discounted future awards a different。And since the value function。

 v of s is defined P to be the expected。Some of discounted reward where the expectation has taken over all those probability distributions from the nondeterministic policy。

 the non deterterministic reward， the nondeministic outcome of actions。

By simply collecting a lot of samples like this， calculating the discounted reward。Getting the mean。

 we can。Estimate very well。The expected discounted future reward under policy pie starting from state ST。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_120.png)

So it's a very simple idea。嗯。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_122.png)

And。So basically， we're just going to use the empirical mean of many。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_124.png)

Trajectories that start from state S T and go to the terminal state。 and we'll use them instead of。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_126.png)

The kind of model provided information that we used in dynamic programming。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_128.png)

All right。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_130.png)

I'm going to put the whole slide up here。嗯。So we want to。

 let's say we want to look at the question of policy evaluation that is given a policy pi。

 we want to know the value function V sub pi。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_132.png)

For every state。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_134.png)

嗯。And one complication is that some policies might actually take us in loops so that we visit the same state multiple times。

 for example， we could have a policy that recommended。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_136.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_137.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_138.png)

With 50，50 probability that if we're in state three， weve take an action that gets us to four。

 but sometimes。Instead it gets us to two。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_140.png)

And it turns out that therefore， because of the complication of loops。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_142.png)

In the textbook and in our class， we're going to distinguish between。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_144.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_145.png)

Mate Carlo methods that use only the first visit to a state。

An average returns only for the first time it's visited in each episode。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_147.png)

Versus every visit， Monte Carlo methods， which average returns every time。

And it turns out it's easier to work out the theoretical results and to understand it。

If we think about first visit， but as the slide points out， both of these methods actually converge。

Asyynmptotically is the number of samples。Grows toward infant。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_149.png)

All right， so let's look at first visit policy evaluation。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_151.png)

So here's the algorithm if we want to use Monte Carlo methods。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_153.png)

To。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_155.png)

For a given policy pie， estimate the value function。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_157.png)

For any given state， the first。Time step that that state S is visited。

 we're going to increment a counter which of course starts out at zero。

 and so for every state in our world we're going to have a count of how many times we' visited it。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_159.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_160.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_161.png)

We're also for each state going to keep track of all of the GTs that we。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_163.png)

Observe and remember， GT is just for a particular episode of the somewhatwhat discounted future rewards that we happen to experience。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_165.png)

And so we're going to sum up those over all the different。Episodes that go through as state S。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_167.png)

And then we're just going to estimate the value for S by taking the mean。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_169.png)

Of those different GTs that we observe。And。As that。Number of samples grows， than our value function。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_171.png)

Gives us an unbiased estimate。啊。Which converges toward the true value。The value。

Of that state under policy。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_173.png)

So this should be。Pretty intuitive， yes。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_175.png)

Oh good so the question is， shouldn't we have a gamma in front of G No remember we're defining G is just the immediate reward plus gamma times the x reward plus gamma squared times the second reward and so forth So G itself already has the。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_177.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_178.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_179.png)

Gamma expentiated by the number of steps into the future。Built into it。嗯嗯。

S it's just the sum of all the G that we've seen so far。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_181.png)

So what we're doing is suppose one state is here。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_183.png)

And I might have a policy I'm going to run the policy many episodes when I get to the absorbing terminal state。

I read。Reincarnate the agent。 And so it's going to have many trajectories that start somewhere。

And in the terminal state， let's say。And what I'm doing is I'm counting how many times those trajectories happen to go through state S。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_185.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_186.png)

And each time it does go through status， I'm calculating。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_188.png)

The G for that state TST。And so I'm just taking the means。so I'm just taking the making a please。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_190.png)

s that clear。All right， now if instead this notices is。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_192.png)

Policy estimation， I'm just。Doing this operation。On the first time step that State S is visited in each episode。

 and so if I have an episode where I loop through a state， according to this algorithm。

 ignore I don't do anything the second time I go through the state。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_194.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_195.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_196.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_197.png)

And this converges。 But， in fact， there is another algorithm called every visit。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_199.png)

Policy estimation that looks exactly the same。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_201.png)

Except that。Every time we go through that state S， we update our statistics。 So in fact， even though。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_203.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_204.png)

The mathematical proof that these converge。Is different if you do first visit versus many visit。

 in fact， they both converge。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_206.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_207.png)

Yes。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_209.png)

When you are。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_211.png)

Yes， you don't actually know what the value of GT is until the episode terminates。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_213.png)

And so you have to have a big enough memory to store all this data while youre。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_215.png)

Wandering around the world。Waiting to find out the values of the GTs。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_217.png)

And obviously， you need。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_219.png)

These variables are going to be linear in the size of the state space。It's a big memory。By the way。

 you so far in the course you've probably noticed。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_221.png)

Even representing the value function。We're assuming we're representing it by a table of numbers that has as many entries as the number of states in the world。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_223.png)

So it's kind of a。Rorote learning brute force kind of way of representing the function we just keep track。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_225.png)

Of our estimate of value separately for each state。 We're about to next week。

 consider replacing that table of。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_227.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_228.png)

Tabular representation of functions by instead a neural network。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_230.png)

And that'll be interesting too， and that'll save us the pain of having a data structure whose size is proportional to the size of the state。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_232.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_233.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_234.png)

Okay， so that's the very simple idea of。policy estimation using Monte Carlo methods。

 Monte Carlo simply means that we're running a probabilistic process and sampling it and using that set of samples that we obtain to estimate。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_236.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_237.png)

The function we're interested in。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_239.png)

Okay， so then let's look at a simple example， this is in the textbook too。

 how many people know the rules of Blackjack？

![](img/ecffdb3454754d59e927cc3cc8dad0a6_241.png)

About half so。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_243.png)

Blant check is a very simple card game。If I'm the dealer。I deal you two cards。

Which I don't get to see， ideal me one card which is face down， you don't get to see it， but I do。

 and then ideal one card face up。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_245.png)

Your goal is to have your card sum be greater than mine。And。Every card。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_247.png)

Which is like a two is worth two points， so three is worth three。

And then the face card's Jack King Quier。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_249.png)

AEces are special because you can declare the ACE to be worth either one。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_251.png)

War 11。And you can decide。So the idea is you want to have a bigger sum than I have。

 but if you go over 21， you just lose。好的 man。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_253.png)

So that's the game。And so we can frame the question of how to。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_255.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_256.png)

Learn a policy as MDP based on this， we can frame the question of how to evaluate。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_258.png)

Say a policy or if we have two alternative policies。

 evaluate which is a better one in terms of the total expected。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_260.png)

Reward。And so to do that， let's set it up so that we'll say a reward function。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_262.png)

Notice this is an episode where it terminates when。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_264.png)

I'm sorry。 I didn't。 I didn't say one key rule。 I'm the dealer。 You get two cards。 I get two cards。

 You don't get to see one of my cards。 Then I ask you。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_266.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_267.png)

嗯。Do you want another card？And you have to think， well。Im not up to 21 yet。

 and maybe the dealer has a higher sum。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_269.png)

Maybe I should take a card。If you go over 21， you're going to lose。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_271.png)

So you have to kind of think about what are the cards the dealer might have。

 given that you can see one of my two cards， you have to think about what's the probability that you'll end up over 21 if you take another card。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_273.png)

And what's the probability that if you don't take a card。

 I'm going to end up higher than you given what you can see， so it's complicated。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_275.png)

So we can say the action， the reward function， then we'll say is。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_277.png)

One， when you win zero for a draw， if we both have the same sum。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_279.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_280.png)

And minus one for losing。And then we'll say the actions that are possible are。

To say stop receiving cards， we'll call that a stick。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_282.png)

Or a hit， which just means you ask for another card and then ideal you a random。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_284.png)

So we have two possible actions。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_286.png)

And the reward function is。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_288.png)

Straightfor to see。Okay， so。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_290.png)

Here's one policy。That we could try to evaluate with Monte Carlo methods。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_292.png)

Suppose the policy， of course， the policy is just for every state。

 a recommendation of which action to perform。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_294.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_295.png)

So here's a deterministic policy that says。The sum of the cards that you hold is 20 or 21。

 you should stick， you should not request another card。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_297.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_298.png)

But。If you're below 20， then you should request another card。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_300.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_301.png)

There might be a good policy or a bad one， but we can use Monte Carlo methods to find out。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_303.png)

And we're going to use a gamma of one， so there's no discount here。

 either you win or you lose the game。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_305.png)

It doesnn't matter how long it takes you to win or lose。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_307.png)

Because our discount after is one。Okay， so。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_309.png)

If we simply run Monte Carlo sampling， that is。We simulate lots of gains。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_311.png)

On a computer。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_313.png)

Where two cards are dealt to。Imaginary player and to the imaginary dealer。

 and then that imaginary player follows that policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_315.png)

If the two cards sum to less than 20， it requests another card to hit。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_317.png)

If the sum with the three cards is still below 20， it requests another card。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_319.png)

If it gets up to 20 or 20 when it stops。And。We can lots of examples like that。

 and then for each state。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_321.png)

State is going to end up being characterized by three variables。

What is the card that you can see the dealer has， remember the dealer has one face up card and one hidden card？

DoThey have an ACce or a two or a three or at dot dot1？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_323.png)

What is your sum so far in the current state？And the third dimension is。Do you have a usable ace？Now。

As I mentioned， AC can be worth one or 11。But usable ace means that you have an ace， and furthermore。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_325.png)

Either value， the one or the 11。ItCan be chosen and still keep you under 22。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_327.png)

If you have a king。If you have two kings in an Ace that we don't call that usable ace because you don't get to choose whether to call that A so one。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_329.png)

Or an 11， and 11 would obviously put you over 21。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_331.png)

So。In fact， all of the information in the state is summarized by those three variables。

 do you have a usable a？AndThen what is the dealer's showing card and which are some？

And so here are on the left。After 10000 episodes of playing random trajectories and running。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_333.png)

Policy Monte Carlo policy evaluation algorithm。Here you can see。What the value function is。

 So each state。Corresponds to some point in one of these two。Uable lace。

 not usable Ace Steelers card， your some。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_335.png)

And you can see what the value function estimate is from Monte Carlo sampling from 10。

000 and half a million episodes。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_337.png)

For that particular policy。Okay so you get an idea of how it converges。

 sometimes you have to run a lot of simulations。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_339.png)

嗯。However， if you run enough simulations， you do get a good estimate。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_341.png)

That does converge toward the true value function。For the given policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_343.png)

Okay。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_345.png)

One kind of interesting way to compare this Monte Carlo approach to the kind of dynamic programming approach as we've talked about。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_347.png)

Previously。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_349.png)

Is that。Here we really。We only。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_351.png)

Consider one action choice at each state we're sampling。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_353.png)

呃。You know， we choose an action according to the policy if it's not deterministic。

 we do a random draw according to the。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_355.png)

Distribution of that non deterministic policy， but we pick one action。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_357.png)

We play that action and we get some reward if it's a nondeterministic reward。

 we still just get one sample。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_359.png)

Value from that。Probability， distribution over rewards。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_361.png)

And so。It's different。From。Dynamic programming and other model using methods in that way。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_363.png)

We're not really。Getting the information about the range of options at each point。

 we're simply generating a single trajectory。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_365.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_366.png)

And using this。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_368.png)

One common efficiency optimization。Is instead of doing what I showed in the original algorithm of。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_370.png)

Keeping all these sums and calculating the mean each time we update。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_372.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_373.png)

Each time we get a new trajectory。There's a simple way to calculate the mean incrementally。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_375.png)

So that if you already know the sum from。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_377.png)

嗯。Of the the mean over the first K -1。嗯。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_379.png)

Samples of trajectories that you have。 Then you can update that to get the mean for the cafe。

According to the following simple rule， and this arithmetic is very direct。

But you can see you can use the mean of the first k minus1 samples。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_381.png)

To get the mean for the。All K samples just by updating it this way。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_383.png)

So this is a nice efficiency。Optimization。That really leavess you from having to calculate the whole mean over。

500，000 samples that you have so far each。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_385.png)

Okay。So。That using that idea of the mean， it turns into this equation if we apply it to the question of what is the mean of our？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_387.png)

G values， given that we have an estimated value function so far。

 which is literally the mean over the first k minus1 samples， and then we get a new sample。

 this is just the other the equation on the previous slide re'written in terms to show us。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_389.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_390.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_391.png)

How this plays out if it's the value function that we're。Estimate。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_393.png)

And it is， of course。Okay， so that's just a nice optimization to be aware of。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_395.png)

Now。We can also use。Monte Carlo， obviously not just to calculate the V function。

 but also the Q function。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_397.png)

And the nice thing about that about using the Q function as we talked about before。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_399.png)

Is that。嗯。If we know the V function， we want to get the policy that。

Is consistent with that V function。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_401.png)

呃。We don't know what to do in any given state unless we can look ahead one step and see， well。

 is going east。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_403.png)

Going to put me in a better。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_405.png)

Value state or going north。But if we have the Q function。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_407.png)

We don't have to do that one step look ahead。Because the Q function。For a given policy。啊， just。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_409.png)

I again， the sum of discounted future rewards just like the V function。

 but now we're conditioning on both a state and an area。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_411.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_412.png)

And so we can also write that expression。In terms of the value function as we've。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_414.png)

About before。But it's basically the summ of futureture rewards is。

The immediate next reward we're going to receive plus gamut times the sum of future rewards from state S+1。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_416.png)

And so if you think about it， if you don't have a model of the world。

 you don't know the next state function。And I give you。The value function。

You still can't calculate the policy。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_418.png)

Because you maybe going north is better， it'll get you to a better valued state。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_420.png)

Or maybe going east， but if you can't predict what state you're going to be in。

 you can't use that value function。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_422.png)

On the other hand， if you don't know the model， you still don't know the transition probabilities。

 and I give you the Q function。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_424.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_425.png)

You're fine。You just say， well， I'm going to， I could go northeast， south or west from this state。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_427.png)

Of those four， which one has the best from the current state with the Arg maps over those four possible actions of the Q value？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_429.png)

So the beauty， the importance of the Q function， is that we can use it。

To derive a policy consistent with it。Even without knowing the transition。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_431.png)

So we can also use MC estimation to estimate these in a way that's pretty much identical。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_433.png)

We're just going to play out a whole bunch of trajectories except that now instead of using that to get the mean over all those sampled trajectories of the value of being in a state。

 instead we're going to get the mean of all trajectories that begin with a state action pair。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_435.png)

But it's the same algorithm otherwise。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_437.png)

And so it converges asymptotically too， as long as we have a way of roaming around the world。

 it assures that every state action parent actually gets visited。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_439.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_440.png)

And。Sadly， but theoretically， if we want this to really converge。

 it has to be each state action pair actually has to be visited。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_442.png)

啊。Asymptotically an infinite number of times。Right， that's just。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_444.png)

Kind of simple。Okay， so now we can。Derve an algorithm， not just for giving a policy to evaluate it。

 but we can also have a policy for learning。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_446.png)

The optimal sorry， an algorithm for learning the optimal policy。

And we're going to use the same kind of iterative， evaluate the current policy and then improve it。

 evaluate the new one， improve it。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_448.png)

嗯。And we talked last time about。Value iteration。As a way to。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_450.png)

嗯。Interlieve。Our update。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_452.png)

嗯。We take one step to update our value function， then we take one policy improvement。

 and we update the value function again。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_454.png)

And we can do the same thing。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_456.png)

It's just that now when we do our updates， we're going to use these empirical estimates based on the Monte Carlo samples instead of using the。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_458.png)

Backing up of future estimates of values。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_460.png)

Of our values。So。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_462.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_463.png)

Just say it this way。 then so if we want to learn。嗯。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_465.png)

Control policy and we don't have an action model we don't have a transition function known to us。

 we learned the Q function instead of V， but we still do this policy iteration。

 so we use our samples from the trajectories available to us to update our estimate of the Q values for each state action pair and then at each given state we use the current estimate of the Q function。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_467.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_468.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_469.png)

Whi is updated every trajectory。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_471.png)

To simply say in state X as we're just going to pick the actione that has the greatest。嗯。Q value。

 the greatest expected future payoff。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_473.png)

And so basically we're just doing the policy improvement step by being greedy with respect。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_475.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_476.png)

So this is all actually very straightforward。Like flipping coins a lot of times gives you the probability of the heads。

 But here we're taking trajectories a lot of times to get the expected。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_478.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_479.png)

The average expected。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_481.png)

Discounted future reward if we start from。And follow。A policy。

 and then in the case of learning control， of course。

 we're going to update that policy each time because we're updating Q and here's our definition of a policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_483.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_484.png)

All right， so this converges。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_486.png)

I'm going to skip this because I'm going to move on。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_488.png)

And so here's a concrete example of an algorithm。嗯。And this says Monte Carlo， exploring starts。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_490.png)

But this is an algorithm for learning the optimal policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_492.png)

And when I say exploring starts。And I'm referring to the following issue。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_494.png)

If we want to have a good empirical estimate from sampling different trajectories。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_496.png)

Of the value of each the Q value for each state action pair。

Then obviously we need a lot of samples from and we need to visit every state action pair。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_498.png)

Multiple times so that we can get good estimates of those。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_500.png)

嗯。By exploring starts we mean。嗯。This line in particular。That when we begin a new episode。

 start a new episode。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_502.png)

We're going to do it in a way that forces us to explore。All the state action appears。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_504.png)

And so put another way， when we start a new episode， we're going to choose a state and an action。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_506.png)

Such that all pairs of state actions have a probability above zero。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_508.png)

So that means asymptotically as we sample more and more trajectories。

 we're going to eventually start。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_510.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_511.png)

See an example where we start everywhere。 so it's just a simple way to guarantee。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_513.png)

Then in fact， we do explore the whole space。Okay， so that said， let's look at the algorithm。

 first we're going to initialize our Q function to anything。Also。

 our initial policy could be anything。啊。And returns is going to be。Aable that keeps track of the Gs。

 the discounted future rewards that we sample。And so now we're going to repeat forever。

 generate a new start position for our trajectory。Generate an episode starting there and following our policy pie。

And then we're going to evaluate the policy and improve the policy。The evaluation is just simply。

Follow that policy， get our Gs。For each SA pair。Append them to this variable that's keeping track of every time we go through that particular state action。

What's the discounted future reward？And then。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_515.png)

Assign a Q value， which is just the mean of those。So it's simply the Montete Carlo。

Policy evaluation algorithm we talked about， but apply to Q instead of P。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_517.png)

And then for the update of the pie， all we're going to do is say， well， our new policy。

Is just to follow the maximum。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_519.png)

Action in any given state according who art。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_521.png)

Updated Q function。 so this is a lot like policy iteration that we talked about last time。

 except here we're now。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_523.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_524.png)

Depending on empirical samples of what those returns are， rather than。呃。Fludtping our estimate of。

The value or Q function to get the estimate， our target is instead what we actually observe in the mean of those。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_526.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_527.png)

Okay， so it's closely related。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_529.png)

Algorithm that does policy evaluation empirically instead of based on the model and then policy improvement。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_531.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_532.png)

And it converges。If we then apply this to the blackjack world， this is what we get。

 This is the learned。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_534.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_535.png)

Now， instead of evaluating a particular policy that said you're going to stick if you're 20 or 21 score。

 and otherwise hit drawn who card。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_537.png)

Here's just a learned policy that is the optimal policy for playing blackjacks。

 so if you go to Las Vegas。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_539.png)

Bring this slide with you。嗯。And you can see what it's saying is， for example。

 if you don't have a usable ace and the dealer shows an eight。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_541.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_542.png)

And your sum of cards is 14， say a king and a four， then you should hit。It's the optimal thing to do。

But if your sum is above 17， you should not。But if instead the dealer is showing a five。

 you should not hit。Because the dealer， by the way， also the hes that remain under。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_544.png)

21。And a five is kind of an awkward card。There are a lot of face cards that are worth 10。Anyway。

 for whatever reasons， I won't try to explain Black Jack。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_546.png)

This is the optimal policy。 This will give you the best expected。Gambling returns if you gamble on。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_548.png)

Bla Jack， and here's the value function。And so you can see there's high value if your current set of cards is 21。

It's going to be hard for the dealer to beat you。嗯。But as it goes away from 21。

 it's kind of interesting。嗯。It's good in here。😡，So I guess it's good for you if a dealer is showing something like a six。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_550.png)

It's kind of an awkward thing。If the card you conceive from the dealer is a six。

The most probable leather card is worth。It's a face car her attend， and so 16 is a。

Awkward thing for the dealer to have。 And so in that case， your reward is。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_552.png)

So all this is just done with Monte Carlo sampling， so you can see there is value to this。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_554.png)

By the way， the state space here is pretty small， it's just a couple hundred。States。Which helps。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_556.png)

嗯。O。So there's one subtlety that I want to talk about in Monte Carlo sampling。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_558.png)

嗯。Which is。嗯。About how we're going to sample the state space。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_560.png)

This slide says， how do we get rid of exploring starts？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_562.png)

If we want to avoid the need to。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_564.png)

Sample everywhere in the state space。But we assume that instead there's some probability distribution over where we're going to start。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_566.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_567.png)

And it might not be uniform。And furthermore， it's not even known to us。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_569.png)

But if we are。Reincarnated according to that unknown probability distribution on each episode。嗯。Then。

Here is an algorithm。That we can follow that。Guarantees convergence。嗯。

And what it does is it says it's a soft policy。 And the idea is。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_571.png)

嗯。We might have， let's say pi is a deterministic policy to make it easy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_573.png)

Then we could say we're going to follow that policy with probability1 minus epsilon。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_575.png)

And then with probability epsilon， we're just going to choose uniformly at random。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_577.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_578.png)

So you can think of this as。With probability 1 minus epsilon。

 we're going to choose a trajectory that exploits what we currently believe about the value function。

 We're going to take an action that we think is going to give us the most reward。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_580.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_581.png)

But with probability epsilon， instead of exploiting。

 we're going to choose uniformly at random in action with the idea that we will explore。

Instead of exploit。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_583.png)

And what we need to do is we need to explore enough。

That we sample all the estates and actions because there might be a really good。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_585.png)

That we don't yet know about and if we just keep exploiting our current policy。

 we may never go over to that part of the state base and find out about it。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_587.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_588.png)

And so， this idea of a。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_590.png)

Epsilon soft policy。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_592.png)

Just the way of taking any。Policy that we do have that we think characterizes our current best estimate of。

What we should do if we really want to exploit and maximize our reward。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_594.png)

But adding in a component that is。Is really not targeted to maximizing our reward。

 it's targeted toward maximize our learning rate。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_596.png)

And to assure that we actually learn。A better policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_598.png)

Okay， can so the way this comes out， I said with probability epsilon。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_600.png)

We choose action uniformly at random and with one minus epsilon。

 we choose the one that we think is give us the maximum reward。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_602.png)

And so you see here the 1 minus epsilon plus this， oh。

 this is just from the other option of choosing uniformly at random。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_604.png)

So if they。This many possible actions， one of them is the one met。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_606.png)

We think is optimal， and so that might get chosen on the exploration。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_608.png)

啊。So those are the probabilities。And this is a nice thing because。You can again。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_610.png)

Run the same kind of control learning algorithm we talked about， generalized。

Policy improvement where we。Update our Q function， update our policy， update our Q function。

 update our policy。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_612.png)

But this will now converge to the best。Epsilon soft policy。And furthermore， once we know it。

 if we know we've converged， we can get rid of the epsilon and just beat。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_614.png)

Exploiting all the time instead of exploring。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_616.png)

And here's an algorithm for doing that。嗯。So if we want to learn the policy this way。Again。

 we start out with arbitrary。Policies。And Q functions generate an episode as we did before。

 but now we can allow the world to reincarnate us in some state according to its own unknown to us probability distribution。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_618.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_619.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_620.png)

And then。As we generate trajectories。We update our G estimates and get the average just like before。

 but now when it comes to choosing the next action we do。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_622.png)

We figure out what's。What we think is the optimal policy， and then with probability epsilon。

 we choose one。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_624.png)

uniformly at random， as I said。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_626.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_627.png)

Ks are really the only difference here from the previous algorithm。

We're still learning the Q function。 It's just that we're following。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_629.png)

嗯。です。This policy， which is a mixed。Exploit， exploreer policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_631.png)

And again， it still converges。So again， the nice thing about Monte Carlo is we don't need to know these models of what's going to happen if we do a particular act。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_633.png)

We can simply sample that in the environment。嗯。The bad thing。Is that。嗯。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_635.png)

Once we start。Sampling our trajectories， using a policy different from the policy we want to learn。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_637.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_638.png)

Then we're not really getting correct estimates of the expected。🤢。

Discounted reward for the policy we're interested in。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_640.png)

If we're sampling according to a different policy。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_642.png)

They be like saying， here's a coin， I want you to flip it a lot of times and see what the probability of heads is。

 but I'm not going to let you flip it， here's a different coin instead。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_644.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_645.png)

Flip it and then tell you can't。You're sampling。If you're using policy B。To generate trajectories。

 to estimate the value for policy A。You've got a problem。And so that's the。That's the subtlety。

to carlo methods。嗯。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_647.png)

And so we'll call the policy we're interested in。Learning the target policy pi。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_649.png)

And we'll say the one we're going to use to generate trajectories will cloud out the behavior policy mu。

And you know for example， P might be the greedy policy while mu is。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_651.png)

Some epsilon soft policy instead state。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_653.png)

That we use to make sure we explore enough。But we really want to learn is the value under the optimal policy so what can we do？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_655.png)

And。The nice thing is there's a very general technique。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_657.png)

That you may already know if you took 701 called important sampling。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_659.png)

Which allows us to。Collect our samples of returns according to behavior policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_661.png)

But then calculate correctly。And。The estimate for the return not for the behavioral policy。

 but for the target policy。And we can do that as long as we know those policies and the probabilities that they would assign to each。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_663.png)

So the idea of important sampling is shown here。🤢，嗯。So in his general form， we can use this。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_665.png)

An idea of important sampling to estimate。The expected value of any function over any distribution。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_667.png)

So for example， suppose I have a function F of Z， and I want to know its' expected value。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_669.png)

And there's some probability distribution over Z。嗯。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_671.png)

Then the expected value is just the。Sort of weighted average all the FOCs weighted by their probability。

 that's what that integral is saying。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_673.png)

And we can。呃。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_675.png)

We can estimate it this way， just by collecting。Samples。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_677.png)

Of Z。And。Counting summing up their values and dividing by hand。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_679.png)

And that gets us the。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_681.png)

This， for example， is exactly what we're doing in our Monte Carlo sampling。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_683.png)

Of trajectories。 in that case， what's the function F？Right， the Q function。Or the value function。

 either one。 we're just trying to estimate， get the expected value of F for every。

Possible state action pair。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_685.png)

we can and we already talked about doing it by summing up all the Gs and dividing by an the number of samples we have。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_687.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_688.png)

其实是 just。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_690.png)

Straightfor expected value。But。And furthermore， this way of estimating it is unbiased。

In the sense that if we run that estimation algorithm many times。

 the expected value of our estimate equals the true value。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_692.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_693.png)

Of the function。 So this way of just taking the de meanan of。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_695.png)

IID sample is of course， an unbiased estimatea。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_697.png)

So this is。Mean and unbiased the variance of that estimate。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_699.png)

That is how far can it deviate from the truth？

![](img/ecffdb3454754d59e927cc3cc8dad0a6_701.png)

You can think of it as the squared error。Of our estimate， compared to the。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_703.png)

Truth。In this case， the expected value of F is。点了。嗯。

That variance decreases as one over and the number of samples， so that's good。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_705.png)

Vance goes down with samples。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_707.png)

嗯。And interestingly， this is important to us too。The accuracy of this estimator does not depend on the dimension of Z。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_709.png)

This variance doesn't even。M成自己。So if we have some high dimensional。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_711.png)

Description of the state space， like all the pixels we can see。That's okay， even if it's。

Million dimensional。State space， we're still going to get。It's decreasing itss one over n。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_713.png)

Okay， so that's just straightforward Monte Carlo， assuming that we're actually generating samples。

 the key thing here is we're assuming that the samples that we're generating here are actually drawn from P ofC。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_715.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_716.png)

Okay， but now the question is if we have an off policy。Setting， where we're using。

The behavior policy to generate。Sample trajectories。

 but we're trying to learn the value function for the optimalimo policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_718.png)

Then the problem is。嗯。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_720.png)

We're sampling these samples not from P of Z， but from some other。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_722.png)

Behavioral policy。Okay， so。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_724.png)

That leads to the idea of ordinary important sampling。Which we can think of this way， suppose it。嗯。

P of Z， so Z in this case would be a trajectory。F is our value function。

Or I guess he could be a state。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_726.png)

嗯。And F of Z is。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_728.png)

The discounted future reward for that state or for that state action pair。嗯。

The samples we're getting。Or。Drawing from。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_730.png)

Let me do it this way。 The samples we're getting are drawn from。嗯。

Not the probability distribution over trajectories for the target policy， but instead for。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_732.png)

This other behavior policy， essentially。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_734.png)

Generating our trajectories。So we can think of。嗯。P is the distribution。For the。Target policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_736.png)

Whereas Q is the distribution。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_738.png)

That we're going to see from the behavioral policy。

The one we're actually following is generating our behavior。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_740.png)

And so if I take my original definition of the expected value of F， it's just。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_742.png)

で。But now if I'm sampling according to Q of Z instead of P of Z。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_744.png)

嗯。Notice is just an equivalent。 I just multiply by Q of Z and divide by Q of Z。

 but now if I rearrange。If I follow that， then I can see that if I'm actually choosing my samples from cu。

 the behavioral policy。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_746.png)

Then what I really want to do is I want to take all the observed samples that I get。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_748.png)

And I want to reweight them。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_750.png)

By what？By the relative probability that I would see that trajectory under the。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_752.png)

Target policy。Compared to the probability that I'll see that trajectory under the behavior policy of I'm following。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_754.png)

And so the mean that I want to take。As my empirical estimate for the expected value of F is really the mean of weighted examples。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_756.png)

And why should I think that way， take at this way suppose？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_758.png)

The behavioral policy， is generating data Q。Aigns probability 0。2 to this action。

And I happen to take it in this trajectory， so I know that that's my sample。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_760.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_761.png)

But suppose instead of 02， the target policy assigns 0。4。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_763.png)

Then effectively， we want to count this rarely explored because it's only probability 0。2 sample。🤢。

As worth two double。Because it will be twice as probable under the target policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_765.png)

So our empirical distribution under the target policy， we can kind of。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_767.png)

by readjusting pretending that we see in the if this of 0。4 and 0。2。

 we want to treat this as though we saw this sample twice because it's going to be twice as probable in the optimal policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_769.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_770.png)

So that's the idea of important sampling， essentially a very straightforward idea。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_772.png)

Makes a lot of sense， and so you can do this as long as you know。What P and Q are。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_774.png)

For us， the beauty of it is we do。 that's what the policies are。

 the policies are the probability that will' choose this action。Stay。

And so you can simply look at the two policies and see what the ratio。

Of the probability for each action。Okay， so this is the idea。Of ordinary important sampling。

Those ratios of probability， some people call them important weights。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_776.png)

By the way， the terminology in this field is a little messed up。In many cases in technology。

 because it's a social process， different groups of people make up different terminologies and when you put them together。

 they're inconsistent， they happened to occur here。These are called importance weights。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_778.png)

本。This is called ordinaryary important sampling and on the next slide we'll see something called weighted important sampling。

 I apologize， it's a different technique and it's not my fault that we call these important weights。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_780.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_781.png)

But just beyond the lookout for that， if you read the literature， because you'll see。

The term weights is used in a couple different ways here。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_783.png)

Okay， so let me go through this and I'll get to some questions。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_785.png)

嗯。So anyway， that's the whole idea and we can apply this and we'll see in a second what the algorithm looks like if we do。

 we can apply this directly to。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_787.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_788.png)

The situation where we are generating trajectories and we want to estimate means from those。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_790.png)

Observed G values。We're generating them according to one policy。

 which is a distribution on actions and action sequences。And instead。

to learn it for the other policy question。偏为电脑。I， well， if we know with the。呃。Well。

 think of the epsilon soft policy。 So the idea there is that。嗯。We have a Q function。

And I would say the target thing we're trying to estimate is the value of the policy for that Q function。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_792.png)

I mean， the policy for that Q function is just as over A。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_794.png)

For whatever statementward。 So if we know the Q function， we know the。

And we know the distribution on actions， right？

![](img/ecffdb3454754d59e927cc3cc8dad0a6_796.png)

嗯。In fact， we can just make it a deterministic policy so the distribution in action is one or zero。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_798.png)

For every action。嗯。And。嗯。We added in that epsilon soft component， why。

 Because we want to make sure we explored the space sufficiently to discover。

Good regions of the space。 So we might have overlooked if we just greedily followed this policy。

 So we actually do know the Q function and the entailed。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_800.png)

Target policy。 but the behavior policy we're following is this epsilon distorted。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_802.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_803.png)

Version of that policy， so in this case， we actually do know the probabilities for both。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_805.png)

And they'll be different by maybe like epsilon， for example。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_807.png)

Yes。It actually means the whole trajectory， and so we have to turn this into an algorithm for our use。

 we're going to have to play with that recursion。You'll see it works out beautifully and simply in the end。

 but that's a very ast point and you're right。One more， yes。イちェなま。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_809.png)

Well， you can see for the blackja case， it's a small enough state space that you can do it。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_811.png)

If you're in a very big space。Like playing go。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_813.png)

You can。Pretty much forget about it。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_815.png)

But。What we're going to see is what we're doing here。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_817.png)

Is we're building up a toolbox。So we've talked about dynamic programming as a way of using a kind of bootstrapping approach where we don't really know the value function。

 but we have an estimate of it and so if we want to update our estimate we can take a step and use the estimate of that state to refine our estimate of this thing so one tool in our toolbox is this idea that if we know the next state function we can do that a different tool in our toolbox is Monte Carlo sampling it's still a way of trying to get。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_819.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_820.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_821.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_822.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_823.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_824.png)

Information target values for updating our value function， but it's a different scheme。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_826.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_827.png)

啊。We're talking next week， we're going to start talking about using neural nets and function approximators to represent the value function。

 That'll be another tool in our toolbox。 And the way to think of this course and to think of these different。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_829.png)

Schemes we're talking about is they're really just illustrating different dimensions of tools that are at our disposal and so。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_831.png)

Even though。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_833.png)

Montic Carlo sampling in his pure form is hopeless for something the size of a go。

 trying to learn the optimal policy for plain go。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_835.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_836.png)

It turns out that。A kind of Monte Carlo sampling is used。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_838.png)

In the。呃。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_840.png)

In the go game that beat the human champion。So we can use these ideas and mix and match them in different ways。

 and so we're kind of looking at pure versions of each of these ideas。

 but part of your job in the project is going to be to figure out how to mix and match。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_842.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_843.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_844.png)

And maybe design your own algorithm from these different ideas。

In a domain that we're going to give you。Okay， one more。Yes。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_846.png)

Yeah， yeah， so if in is deterministic， many of these will be zero n。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_848.png)

Kind of makes sense。 you don't want to。呃。Couned。嗯。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_850.png)

Often this， if you think about using this with an epsilon greedy policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_852.png)

And then over。A typical thing is to use this with an epsilon greedy policy for them。

Every action has some nonzero probability。And then use a different behavioral algorithm that might be。

 let's say， more aggressive about exploring。Then the epsilon greedy policy。

 and that way you end up with very few no zeros。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_854.png)

But you're right， in general， if this is deterministic， you will have a lot of heroes。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_856.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_857.png)

Okay， so let's keep going。Because there is a thing called weight and important sampling。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_859.png)

嗯。Which is based on the following idea。 S we。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_861.png)

Think of our probability distribution Q。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_863.png)

For example， generated by the behavior policy。As some term plus divided by a normalizing constant。

 like most probability distributions。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_865.png)

Some kind of normalizing constant， which is hard to calculate shift to some overall the possible。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_867.png)

嗯。States or values of Z。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_869.png)

And see what the total probability mass is and to make sure that all the proities sum to one。

 you have to calculate this normalizing constancy。啊。But if we think of it as this way。

And actually calculating。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_871.png)

Til for trajectories is problematic。You could say， well I run this policy。

 it's more probable that I'll go this way than that way。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_873.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_874.png)

This ratio but I don't know the actual probabilities of generating those two trajectories because there are a million other trajectories I could have followed。

 so it's hard to calculate these normalizing constants。

 even though it's easy to see with the ratio of the probability of this trajectory to that。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_876.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_877.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_878.png)

Okay， but whatever the case， suppose we think of Q is。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_880.png)

This kind of Q squiggle divided by the normalizing constant。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_882.png)

Then。A variant。Called weighted important sampling， not my term。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_884.png)

Sometimes called normalized important sampling too。嗯。Is to look at it this way。

We could say if Q is represented that way and if's also P of Z。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_886.png)

Is a similar kind of。Peace squiggle over。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_888.png)

C片。Then。I can write out， I can expand this in this way where those two normalizing constants。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_890.png)

I end up looking at their ratios。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_892.png)

But then if I work through the arithmetic， what I find。Is that。嗯。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_894.png)

Again， again， an important sampling， this is the same。Ideas before。

 it's just that I'm writing it in terms of these P&Q squiggles and they're normalizing constants explicitly。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_896.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_897.png)

And the weights here are just these fractions。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_899.png)

好嘞，我意。So I should say。This is a W。嗯。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_901.png)

So the thing is now。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_903.png)

嗯。If I want to use this important sampling， I don't really know what these constant Z P and ZQ are。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_905.png)

But it turns out it's easy to calculate them。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_907.png)

嗯。So。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_909.png)

The ratio。Of Z to ZQ。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_911.png)

Pretty straightforwardly ends up being just the sum over all the trajectories I have。

Of their weights。The weights being these ratios。So for every example， remember before I said。

 suppose the action was 0。2 probable versus 0。4， so that weight'll be a two。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_913.png)

嗯。Some cases would be below one， but if I sum them all up and get their mean。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_915.png)

It actually turns out to be the ratio。And the nice thing about that is it means that。

I can use these kind of unnormalized probability distributions。

 where I really don't know what the normalizing constant is。嗯。

Because it's easy to estimate with the ratio of their normalizing constant。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_917.png)

And so it leads to a very。嗯。Nice estimate。Which is the expected value of the function。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_919.png)

P over the expectation taken over P。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_921.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_922.png)

Of x。It's the sum of my samples。And again， I'm having waiteded。嗯。

Versions of those weighted by the ratio of the probabilities。 but now I'm dividing by this。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_924.png)

Which is interesting。 Remember， we agreed before that this W is like。

The ratio tells us the effective number。Samples we should use if we were really using policy P。

 even though we're using policy Q to derive to sample。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_926.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_927.png)

So this number。Is the sum of all of those effect if we think for any given sample N。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_929.png)

The weight N tells me how much we should upweight or down weight that sample。

 This sum is telling me sort of on average， what's the total number of effective samples。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_931.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_932.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_933.png)

And so the only difference between this weighted important sampling。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_935.png)

And ordinary important sampling on the previous page。Is that。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_937.png)

Here。How5。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_939.png)

啊啊。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_941.png)

K let me do this水。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_943.png)

嗯。So this is weighted， important sampling， but ordinary。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_945.png)

Important sampling。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_947.png)

Looks the same except that。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_949.png)

The expectation is now1 over M， the number of actual samples we drew。Times the sun。Of the weight。

Ts F of Z。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_951.png)

So the way I think of the difference is in ordinary sampling。

 we're really taking the mean of these weighted samples。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_953.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_954.png)

But in。Normalized or weighted important sampling。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_956.png)

This quantity substitutes for 1 over m。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_958.png)

Instead， we're taking one over this constant。Which is the number of effective samples。

 we think we really should be。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_960.png)

Thinking that we're using， if we were。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_962.png)

Observing these samples generated under probability distribution P instead of Q。

 and here we're taking the number we actually observe under Q。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_964.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_965.png)

So the difference is simply how we think of the mean is that。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_967.png)

You know， is it the sum divided by the number of samples we actually have or the sum divided by the weighted sum divided by the number of effective samples？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_969.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_970.png)

So both of these schemes are used。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_972.png)

嗯。This one has the advantage that's an unbiased estimator。

It has the disadvantage that its variance is unbounded。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_974.png)

This has a disadvantage that it's a biased estimator。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_976.png)

Although as the number of samples grows toward infinity， the bias disappears。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_978.png)

And has bounded。啊。Nice variance properties。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_980.png)

So I want to give Kaarina a chance to talk， and I just want to maybe end by putting up。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_982.png)

Doing it this way。Here's an example of the。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_984.png)

Use of important sampling here。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_986.png)

So we're going to in this algorithm。We're doing an off policy so we have。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_988.png)

Q is our。Defins our target policy and then we're going to use new， any other policy。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_990.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_991.png)

Has non zero probability wherever pi has it。You're going to use mute to generate it。And so we do is。

 again， we're going to。Calculate G the sample， we're going to generate some samples。

 and then we're going to go through them and update the G's。

keep account of how many times we visit each state action。W is initially one， so every time we visit。

 we're going to add one。But now。We're going to。嗯。And here's our。

Optimization for doing the inement calculation of the mean。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_993.png)

Right。This is our new mean estimate based on the old mean estimate。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_995.png)

Plus。One over the count contribution from the new estimate。

But now here we're updating those weights by the relative probability under pi and under mu of taking that action from that state。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_997.png)

And so this is the answer to your earlier question about are we talking about trajectories or actions。

 We're actually talking about trajectories， but if we do this。😊。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_999.png)

And we cycle through every step in the trajectory， then that turns out to be the right way to。

The probabilities over the trajectory。So this part is all about the important sampling。

 this clever equation here is about calculating means incrementally。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1001.png)

And the rest is。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1003.png)

So this is a beautiful and simple algorithm that shows how we can use policy mu to generate trajectories。

😊。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1005.png)

Have those estimate for us。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1007.png)

The value function。For the policy pie instead。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1009.png)

Okay， so I'm going to end there because I want to give Katerina a chance to。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1011.png)

Do her。Spotly。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1013.png)

定在问。The black jack。 So what struck me a little bit was like， okay， this is the optimal policy。

 So this made me feel really。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1015.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1016.png)

Unintelent because we spend many summers not playing blackja and wide we discover so fast the optimal policy。

 so there are a couple of very important assumptionss behind this first the dealer always has a fixed strategy which cannot change throughout the game okay。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1018.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1019.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1020.png)

And the second is that the cards are taken from an infinite pack， which is。A good replacement。

 which means that you camping cards was not going to help you。 So the reason that for us。

 potentially playing but junk is because， you know， we try to count cards and。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1022.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1023.png)

We get out more than this。 and second， because the dealer can b off and change the strategy how they can。

 Okay， so just keep track of the time of the simplifying assumptions that there are behind the。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1025.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1026.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1027.png)

Every example that we present makes sense okay great。

 so the second which is kind of a bit more important is the following we've been discussing what is our reward of what is our policy trying to maximize trying to maximize the sum of expected returns okay？



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1029.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1030.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1031.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1032.png)

Somehow we said here， you know， yes， that's exactly what we want。

 Then here is our deterministic position that does this。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1034.png)

But at the same time， to explore， we're going to out。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1036.png)

Excellent， whichch is not very principle because if。

This means that potentially your objective was not correct in the first place。

 if we cannot use that policy directly。So it turns out there is another of objective。

 which we're going to see in。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1038.png)

F lectures later， which takes into account both the fact of trying to maximize expected returns as well as not committing to a particular strategy。

 so if there are multiple strategies that are equally good the policy。

 the optimal policy under that new objective should should have equal probably under all this alternatives and that new objective is you know some of expected returns plus you know some weight there and then the entropy of the policy okay we want our policy not to overcom to one particular strategy if we choose that let's say better objective highly more complex but。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1040.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1041.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1042.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1043.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1044.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1045.png)

Better than you don't need to alternate between。 Yeah， that's the policy I care about。

 But that's what I'm going to use to explore。 You know， we just can use the same policy for。

 for both because this what is going to be stochastic and it's going to allow you to explore widely。

 And it turns out that you can drive sample complexity below。



![](img/ecffdb3454754d59e927cc3cc8dad0a6_1047.png)

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1048.png)

Under this you know， different objective and resulting boing， but we'll see all boing。Next lectures。

Right。

![](img/ecffdb3454754d59e927cc3cc8dad0a6_1050.png)