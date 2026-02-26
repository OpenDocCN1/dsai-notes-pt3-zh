# 斯坦福大学《深度强化学习｜CS224R Deep Reinforcement Learning  Spring 2025》中英字幕 p14 -14- Lecture 14_ Exploration.zh_en -BV1SvmxB3E5e_p14-

![](img/92b4467453d2b29624c0251ce97b632c_0.png)

![](img/92b4467453d2b29624c0251ce97b632c_1.png)

Okay， let's get started today we're going be talking about exploration we're going to be starting by talking about exploration in kind of standard reinforcement learning settings。

 actually primarily in bandit settings and then how that might translate to robotics in large language models and then we're actually going to revisit some of the meta learning topics that we talked about on Wednesday and revisit how we might effectively learn how to explore in metaRl settings。

😊，So what is the exploration problem？

![](img/92b4467453d2b29624c0251ce97b632c_3.png)

If we apply reinforcement learning to some problems， we're able to solve them quite well。

 so for example， if we try to train a reinforcement learning agent to play breakout where the reward is the score of the game。

 you get a pretty performant player that's able to get a high score。



![](img/92b4467453d2b29624c0251ce97b632c_5.png)

But if you instead try to train a reinforcement learning agent to play a game like this one on the right。

 which is called Montezuma's Renge， it's really， really hard for reinforcement learning systems to play。

A。Now， why is there this difference？So in the second game。

You can get a reward if you get a key kind of intuitively if you're getting a key that's useful for being able to progress。

 opening a door is also useful。 And if you there's this kind of skull that's rolling around and intuitively。

 we as humans know that that's probably something you might want to avoid， likewise。

 falling off off of a lead might be something that you avoid。

 but these are things that the agent doesn't know itself。And in general。

 kind of completing the game like these are kind of very sparse discrete events and completing the game only weekly correlates with those rewarding events and so it actually and each of those individual rewarding events are also kind of few and far between so for example。

 at the beginning the agent isn't getting any reward at all。

 and it has to figure out how to even get to the key in the first place which requires quite a long sequence of events。



![](img/92b4467453d2b29624c0251ce97b632c_7.png)

![](img/92b4467453d2b29624c0251ce97b632c_8.png)

That was humans， we kind of know what to do because we understand what each of these sprites in the game mean。

But the algorithm really doesn't know that so if we instead try to imagine ourselves as reinforcement learning algorithms。

 let's think about through that a little bit and we can think through that with a game called Mao。

 it's kind of a it's like half a game half a joke in some ways。

 you aren't told the rules of the game in advance， and if you break a rule then you get a penalty。



![](img/92b4467453d2b29624c0251ce97b632c_10.png)

![](img/92b4467453d2b29624c0251ce97b632c_11.png)

And you don't actually know you get a penalty， but you don't actually know what the rule is。

 and you have to discover the rules through trial and error and when you get a penalty it's not always clear why you got a penalty。

 the rules don't actually necessarily make sense to you。And。

Tasks like Monteezim's revenge are difficult because reinforcement learning methods。

 they don't know about the rules。 They know very little about what's good and what's bad。

 what they can do， what they can't do and。When tasks are become longer and longer。

 this also makes the problem even more difficult because you have to figure out a even longer sequence of actions that might lead to getting reward versus getting a penalty。

And so if you think about kind of what the reinforcement learning agent has to do。

 reinforcement learning agents are kind of analogous to imagining if your goal in life was to win 50 games of Mao。

And you also didn't even know this in advance。

![](img/92b4467453d2b29624c0251ce97b632c_13.png)

You only kind of learn this from actually getting rewards from winning games and getting penalties from losing games。

That's kind of like what the reinforcement learning system。Kind of that's the， the。

 the difficulty that these algorithms are faced with。 It's really， really hard。

 especially in sparse reward scenarios。

![](img/92b4467453d2b29624c0251ce97b632c_15.png)

Now， if we' were to think about this exploration problem。

There's a couple different ways of looking at it。One way of looking at it is we want to discover high reward strategies。

We want to basically seek out rewards and find kind of sequences of actions that individually those actions may not be rewarding。

 but when we seek them together， we're able to find rewards。And another way to view。

To view the exploration problem is deciding whether to attempt a new behavior or continuing to do the best thing that it knows so far。

 You're basically deciding， should I try something new or should I do something that has been good in the past。

These are actually kind of kind of part of a single problem where you need to。

There's kind of this exploitation problem， which is doing what， you know。

 will yield the highest reward， doing kind of the things that you've seen before that have higher reward Act。

 according to your Q function， for example。

![](img/92b4467453d2b29624c0251ce97b632c_17.png)

![](img/92b4467453d2b29624c0251ce97b632c_18.png)

And this exploration problem， which is doing things that you haven't done before in hopes of getting higher reward。



![](img/92b4467453d2b29624c0251ce97b632c_20.png)

And so that's kind of how we can think about this reinforcement learning problem where we need to balance these two objectives if our goal is to maximize a sum of rewards over time。



![](img/92b4467453d2b29624c0251ce97b632c_22.png)

As some examples， if you are in a new city， you kind of move somewhere new。

 exploration would be trying new restaurants， exploitation would be going to your favorite restaurant or the restaurant that you like the best。

One actually very common use of reinforcement learning is figuring out which adds to place and where and exploitation would be taking the ad that has been the most successful and showing that one to the user。

 an exploration would be instead trying to pick a different advertisement at random and instead showing that advertisement to the user。

Or as a kind of a final example in oil drilling， you don't know where you're going to find。

Where you're going to find oil， and so exploitation would be taking the best location that you've found before that it yielded oil versus exploration would be drilling at a new location。

Okay。So exploration is quite hard。If we want to design an algorithm for exploration。

 we might think about what is the best strategy for exploring and the best way to trade off between exploration and exploitation。

And we also need to think about like， what is that。

 What does kind of optimality and exploration even mean。

There's a range of reinforcement learning problems ranging from more simple problems where you can actually analyze whether or not the strategy is optimal or not to more complicated problems where it'stractable to analyze whether or not it's optimal and also in to develop algorithms that are able to do a good job at exploration on the simple side you start with multi-arm bandits。

The kind of one step are all problems that don't have any state。

And then if you want to make that more complicated， you add context。

 you add some sort of features for the state that you're in。

 you could then move to small MDPs to larger MDPs and kind of a lot of the kind of problems that we've been talking about in this course are large MDs without any known structure and those are the ones that are like the hardest for getting good exploration strategy and also theoretically thinking about exploration。



![](img/92b4467453d2b29624c0251ce97b632c_24.png)

![](img/92b4467453d2b29624c0251ce97b632c_25.png)

So。Before we talk about exploration in the large problems。

 let's talk a little bit about bandits for a minute because they provide a nice way to think about exploration and they're actually used in practice for a variety of problems and specifically the way that we can think about like like what is a bandit It's not kind of someone that runs around and maybe tries to see yourself sub or something it's a formulation of reinforcement learning。



![](img/92b4467453d2b29624c0251ce97b632c_27.png)

Where。Um the horizon is just like one time step for a single episode。There' is no state。

And unlike everything we've talked about in MVP so far， your reward is actually stochastic。

And so if you kind of go back to the examples before。

 you could think about the problem of selecting a restaurant as a bandit problem where you could。

 for example， select to go to one restaurant， you could select to go to a different restaurant。

 you could select to go to a different restaurant。And so forth。

And depending on your experience in previous episodes of selecting restaurants。

 you could inform your choice of whether you want to pick a new restaurant where you know nothing about the reward or go to a restaurant that you've received high reward for in the future and the reward is stochastic in the sense that your experience at that restaurant may not be the same every single time。

 and so yeah， this is kind of what a bandit problem looks like。Now。

 if we want to think about how good is exploration。

And how good is our kind of reinforcement learning algorithm？We want to think about。嗯。

How much reward we're getting relative to if we were acting optimally。And so far。

 we've been thinking about sums of rewards， oftentimes averaged over episodes。The in bandit problems。

 you actually are often thinking about actually the entire reinforcement learning process and the optimality of the reinforcement learning process and the optimality of exploration followed by exploitation。

And so say that you have。You have taken capital T episodes so far。

Then the best you could have done is going to be something like the expected reward of taking the optimal action。

Times T。And this is actually。In some ways， an oracle。

When you haven't taken any episodes at the beginning。

 then you sort of are forced to take a random action because you don't know anything about the MDP so far。

 and so this is kind of in retrospect， what is the best thing you could have done and this is a upper bound on the sum of rewards that you could be getting after T episodes。

And then if we want to think about like how well we've been doing。

 we can think about this subtracted by the sum of awards that we actually observed from the actions that we've taken。

And so that would be something like a sum from t equals one to T of the action。

 like the actual action。That we decided to take。In each particular episode。

And the gap between these two is going to be measuring kind of like basically a form of optimality gap。

 And this expression is something that's called。Regret。And its measuring like basically。

 how much do we regret taking the action that we did compared to taking the optimal action。Now。

 if you were to think about regret over time。 So here， actually。

 time is indexing over episodes because each episode is just a single time step。

So we we think about kind of。As a function of the number of episodes。呃。

Be regret after taking those number of episodes。If you were acting optimally。

 what sort of curve would you get？On this plot。Yes， so I see。I see mostly going straight。

 So if you're actually optimally， this will be 0， and it will be 0。

 even as you have more and more episodes。 Itll be in expectation。 There might be some randomness。

And so you would get。A curve that looks。Like this and so this is like。

Sort of like optimal now in practice actually achieving this。

Is not really possible because at the first time step， like I mentioned。

 you have to take a random action。嗯。Now， does anyone have thoughts on what this curve would look like if you were just taking an episode at random。

Yeah， it'll keep increasing yeah， so if you're taking an episode at random。

 there will now be a gap between these and you would be getting a higher reward from taking the optimal action compared to taking that action at random。

And。If， for example， you are always picking a1 and a1 is not the best action。 then after one episode。

 you would expect to have。Some kind of。Non zero regret， right。

 So you would have a curve that looks like this and then。If you took a1 again， the next episode。

 then you would then kind of incur the same。The same difference in optimal rewards versus the rewards that you took。

 and so then this would increase。And you would actually get something that looks linear and that means that basically every time you theres basically every at every time time。

 there's a fixed difference between the optimal reward and the reward that you took and so whenever you get like a linear regret increasing linearly。

 that means that your algorithm is not actually improving。

 it's not actually using the exploration to get better rewards。It's instead you were。

The blue markers never worked that well， but we can see if instead you were actually having an algorithm that is a bit smarter。

 then you would expect to have sublinear regret， and so you would expect actually not just linearly increase your regret over time but actually have this curve look something like this where it starts it starts looking something more like linear and then eventually if you then get to the optimal behavior after exploring。

 then it flattens out to something like this and you could imagine that this portion is like you're now in the exploitation phase and the phase before that is when you're exploring and gathering information about the problem。

The question is to make these curves， are we running the learning process a lot of different times than then averaging so for these curves。

 this is actually each of these curves is just like one reinforcement learning process and I guess they're very smooth here and in practice。

 they'll be a little bit noisier optimal I guess this is kind of an expectation and so this this is going to be smooth but you might have something where for example。

 in reality maybe you got unlucky kind of one time step and like this kind of went up because you got unlucky。

 maybe at the next time step you still took the optimal action but got lucky and so this will actually have some noise in it in practice。

Yeah， so the question is we have an expectation on the first part。

 we don't have an expectation here why is that the this is basically some measure of like the optimal expected reward after T time steps this is actually just like the actual reward that you observed you could also have an expectation over this over reinforcement learning runs and that would be that would then give you like。

Like as an example here， if you run this algorithm multiple times。

 these regret curves will actually look a little bit different depending on how unlucky you get。

 And then if you were to then measure this in terms of expectations。

 then that would be averaging over different runs of the reinforcement learning algorithm。Yeah。

 so the question is， if we're taking random actions。

 why is it linear and why is it increasing by a fixed amount？

 So this will be noisy if you are taking random actions the。If。And I'll say that。So yeah。

 it will be noisy if you run it multiple times in expectation。

 it will be linear and if you have like a deterministic MDP and you always select action1 through like a very not smart strategy and the rewards are a bit more deterministic then you might actually get a curve that looks like this。

So the question is， if we're always taking a1， then how do we actually know how to measure this formula。

 this is not actually a formula that like sorry。To back up a little bit this is actually not this is like what we're aiming we're aiming to minimize regret。

 we're aiming to get it something that is able to flatten out。

 but this is more of an object that's used for analysis and not our optimization objective because we actually can't measure this without kind of knowledge of the bandit problem or knowledge of the MDP。

If you introduce an expectation here， then you would expect it to be monotonic， if not。

 then because the award is stochastic， you could have scenarios where you。Say the， the， the best。

The best action is like a five and the probability of getting like good reward is like， I don't know。

 like 90% of the time and 10% of the time you get a bad reward then you're going to see like when you get a good reward it will actually。

Relative to the， the expert， which is averaging over that， it will go down。

 But if if you write this as an expectation for the reinforcement learning algorithm。

 it would be monotonic。

![](img/92b4467453d2b29624c0251ce97b632c_29.png)

Cool， so this is the regret formula， regret after doing reinforcement learning for T episodes。

 expected reward of the best action， basically the best we can hope for an expectation if we had kind of knowledge of what the bandit is。

 and then this is the reward of the action that's actually taken。

There's a variety of simple strategies for exploration and including some that you can show that are optimal。

 and you can often kind of analyze algorithms and provide theoretical guarantees on regret。呃。

And then also even the algorithms that you can kind of theoretically make some guarantees about in practice。

 performance can vary。And so to get a little bit more intuition actually， before we do that。

 we're going to play a game in a minute， but before we do that。

 let's talk about different strategies for exploration。So。The specifically in bandits。

 so not in MDPs。

![](img/92b4467453d2b29624c0251ce97b632c_31.png)

So one approach is when you're selecting different restaurants， for example。

If you haven't explored a restaurant， then you could choose to be optimistic about that restaurant。

And that will incentivize you to explore new restaurants rather than always being greedy with respect to restaurants you've tried before。



![](img/92b4467453d2b29624c0251ce97b632c_33.png)

And so the way this could work is you can track the average reward that you have received in the past for each of the actions。

And then if you were to exploit， you would just take the action that has the maximum average reward。

For the things that you've seen so far。But instead。

 if we want to actually encourage the algorithm to visit new things， then we could。

 we still want to visit actions that we think have high average rewards so that if we go to a restaurant that's really bad。

 we maybe don't go to it again。But we're going to add a term that is some kind of variance of our reward estimate。

This is basically like， if this variance is high， that means that we're uncertain about the reward for that action。

And if we're uncertain， then we're going to basically give this sort of bonus。

 this sort of reward bonus on top of our estimate of the average reward to encourage our algorithm to explore things that are uncertain or things that have high variances。

And so the intuition here is that we're assuming that unknown things are going to be good until we actually then observe them and if we then observe them and they're really bad。

 then we'll act accordingly in the future， the variance will go down and the reward estimate will go down and this is a way to kind of balance exploit and exploitation。



![](img/92b4467453d2b29624c0251ce97b632c_35.png)

Yeah， so the question is how would you choose in this case an action that you haven't seen before so if you haven't seen an action before。

 then your variance estimate probably will be something like infinite， for example。

 and then and then this will encourage it to explore basically all of the actions that it hasn't explored first at least once and then from there your variance will go your variance estimate or your uncertainty about an action will go down over time and yeah so this is basically if you haven't done anything before it will incentivize it to to visit that first。



![](img/92b4467453d2b29624c0251ce97b632c_37.png)

![](img/92b4467453d2b29624c0251ce97b632c_38.png)

![](img/92b4467453d2b29624c0251ce97b632c_39.png)

Cool， this is a popular algorithm you can actually kind of derive guarantees for it。

 it's called upperpper confidence Bo or one version of it， it's called upper Con Bo。

There's another approach that you can also take that is actually hard to show guarantees for。

 but can work pretty well in practice， and we actually saw something like this in the last lecture。

 and essentially what you're trying to do is you're trying to estimate the probability of getting good rewards from each of the arms of the bandit。

And so the way this would work is you assume that there's some sort of kind of distribution of rewards for each of the actions。

And this defines kind of a partially observed MDP where you don't know the parameters of the reward function。

 you don't know if you're going to get a good reward or bad reward。

And so you'll then actually try to model and form an estimate of the likelihood of getting rewards。

By trying to model these parameters and your uncertainty over it。

So you'll form an estimate with any data that you've seen so far。Then you'll actually sample。

An MDP from your model of possible MDPs of the world。

And then you'll take the optimal action assuming that your sample was correct。

And then repeat that process to update your kind of beliefs again and then sample a new MVP and repeat the process。

And we'll kind of walk through an example， but the intuition here is that you can kind of iter really improve your model of the bandit and act according to one of the models that is covered by one of the potential kind of sets of probabilities that's modeled by your MDP model。

One last note， these are actually methods that are widely used and studied in industry for recommenders in ad placement。

 the everything we've been talking about so far is for these sorts of like small bandit problems。

 but they are actually quite relevant for a number of practical problems。

 even when you don't have like longer episodes or episodes with state。



![](img/92b4467453d2b29624c0251ce97b632c_41.png)

![](img/92b4467453d2b29624c0251ce97b632c_42.png)

And now let's play like a little game to get some intuition for how this works。 So here is。😊。

A little simulation， say that you are hired as the head of drug development at a prestigious research hospital。

Things are going well and now there's kind of some sort of plague and you need to figure out what drugs are going to be effective for addressing the plague and you want to save people's lives by giving them the drug that's most effective。

Now， you can recognize this as a bandit problem where each drug you don't know how capable it's going to be。

And we can say that maybe there's somewhere around 5。

000 patients and there's maybe around 10 different drugs that you're considering。

And your goal is to try to understand well， try to save lives。

 try to save as many cumulative lives as possible as but also balancing kind of。

Saving lives right now versus saving lives in the future as you learn information about each of the drugs。

Cool， so let's play who wants to suggest a drug。Drug one， okay， so we see that we pre drug one。

 the patient lived， so that's good who wants to pick a drug。Yeah。4， okay。

We also see the patient live is good on the good track。Yeah。1en。D的， okay。Yeah。7even。Lived， okay。

 so one，4， and 7 are looking better than 10 right now。Someone else？Yeah。Six。

 still exploring patient died。5ve。Dive， okay， not so good。R。行。Seven， okay。

 maybe we want to start exploringing patient lived again， so that seems like pretty good。

You to see just。行。2。Patient died。Not so good。啊。Yeah， seven， okay。Patient lived again， pretty good。

What do we want to do next？Seven， okay， do we want to keep doing seven， patient died？行。8。

Patient died。7even。Patient live， should we just keep on going7 at this point。

 Are we happy with seven？Try9。Patient live。Try one。Paient dies。Or patient live。For again。

 patient dive。9ine patient live。Three， patient died。9ine patient live。Okay， we like nine。ote。

 maybe let's keep on doing nine。Patient is living a lot。 Great we one patient die。😊。

So let's say that we kind of kept on going with nine for a while。And then we can plot actually。

 well with 5000， which I could just say， like keep on doing9。 Maybe we'll stop there。

 We can actually plot their regret， so。This was the true efficacy of the drug and we can see that nine actually was the best one。

 so we actually found the best one， which is good，7 was also pretty good。

 and then we could also plot the number of lives that are saved by different algorithms and so higher here is better and we see that the posterior sampling approach in this case。

 what posterior sampling would be doing is modeling the probability of the efficacy of each drug and then based on his estimate of that picking something that thats better and we can see that how well we did right here is in purple it's a little bit hard to tell it just because it's a little small but we can see that generally like looks like we're doing pretty well relative to the algorithms。

😊，嗯。And then you can also plot regret over time and actually here we can see that we're actually doing better than all the algorithms so you guys are pretty good nice maybe there's some luck involved there so this is just a single run and what these different algorithms are is you see greedy is showing green greedy is just picking the best thing you've seen so far over time especially with more and more trials that you might be running like more and more patients。

 more and more ad placements whatever it's getting a lot worse in this case we saw that posterior sampling in yellow is like by far the best algorithm and then the other algorithms red is showing epsilon greedy blue is showing UCB so that's the first algorithm we talked about with being optimistic about uncertain actions so this is basically showing that kind of the tradeoff between different algorithms one of the thing to note that epsilon greed it's a bit more greed and so we see that with when you have fewer patients it actually is doing better than UCB but then in the long run UCB is doing better because it's actually optimizing a bit more for making sure。

😊，That you're exploring more actions， and so in the long run。

 it's able to take more optimal actions in the future。



![](img/92b4467453d2b29624c0251ce97b632c_44.png)

Is there a mathematical reason why posterior sampling does better than UCB and Epsilon greedy？Yeah。

 so the I don't want to go too much into the math and actually posterior sampling for this MDP。

 you probably could analyze it and but in general， it's actually pretty it can be hard to derive like general theoretical guarantees for it with regard to Epsilon greedy the。



![](img/92b4467453d2b29624c0251ce97b632c_46.png)

It。I guess some of it comes down to that value of epsilon and like tuning it to be and generally with epsilon greedy。

 you often choose epsilon to be like smaller and smaller over time and that hyperparameter would probably like drastically impact performance because at this point in training if epsilon is constant。

 you're going to be keeping on you're going to be still occasionally taking random drugs and at that point you already know a lot about the drug and prescribing a random drug is a very poor choice。



![](img/92b4467453d2b29624c0251ce97b632c_48.png)

![](img/92b4467453d2b29624c0251ce97b632c_49.png)

![](img/92b4467453d2b29624c0251ce97b632c_50.png)

![](img/92b4467453d2b29624c0251ce97b632c_51.png)

Okay， cool， so also if you want to play more， you can I'll put the website in the slides。Okay。

 so that's exploration and bandit。Now， what does this look like for robotics。

 language models and larger MPs。

![](img/92b4467453d2b29624c0251ce97b632c_53.png)

Different people have different opinions on this I have a somewhat pessimistic opinion on it and in particular there's actually a lot of research that try to translate these ideas to larger MDPs for example。

 you can try to formulate some estimate of whether you've taken an action or not and give reward bonuses for novelty for visiting new states for taking new actions and similarly like posterior sampling。

 you can try to figure out kind of models of different dynamics and so forth and act accordingly。



![](img/92b4467453d2b29624c0251ce97b632c_55.png)

![](img/92b4467453d2b29624c0251ce97b632c_56.png)

![](img/92b4467453d2b29624c0251ce97b632c_57.png)

But at the end of the day， when you're in a very large MP。

 explorationlor from scratch is generally intractable。 So， for example。

 if you randomly initialize a transformer language model and try to。😊。



![](img/92b4467453d2b29624c0251ce97b632c_59.png)

Figure out how to make a user happy or some other reward function like like up votes or something like that。

 actually like just using upvos to train a language model from scratch isn't going to work。

 there's just like the sheer vastness of the possible space of tokens is way too large at least relative to the patients that most users will have likewise in robotics if you're trying to even just learn how to I don't know。

 kind of pour water from one cup to another cup you're going to be stuck in around where you're just kind of randomly moving arms around rather than actually doing things that are useful if you're starting completely from scratch。



![](img/92b4467453d2b29624c0251ce97b632c_61.png)

Instead。Generally， what exploration looks like in these larger domains is to rely heavily on demonstrations or on base models that were pretrained on data and demonstrations。

 so for example， reinforcement learning has been quite successful in language models because and particularly in scenarios where you have a strong base model that already knows how to write coherent sentences and already knows kind of roughly how to approach certain kinds of prompts or certain kinds of problems and likewise。

 in in robotics， if you have demonstrations of example behavior that achieve high reward。

 then using that as a starting point for reinforcement learning is very powerful。



![](img/92b4467453d2b29624c0251ce97b632c_63.png)

![](img/92b4467453d2b29624c0251ce97b632c_64.png)

And generally these models are like they're providing an initialization that's really excellent for exploration and seeking out potential potential things wherever feasible it's also quite useful to use shape rewards because that can guide any sort of exploration process as well and this could be if you're in simulations。

 you can hand code sparse like dense rewards or if you're learning like single step rewards from preferences that actually also provides a fairly dense reward signal。

😊。

![](img/92b4467453d2b29624c0251ce97b632c_66.png)

This isn't to say you could also kind of combine some of these ideas with demonstrations and base modelss。

 but。Generally， you get a lot further from starting with this kind of initialization。



![](img/92b4467453d2b29624c0251ce97b632c_68.png)

Okay， that said， there is still like potentially an exploration problem that we started to talk about last time。

 and I want to revisit that now that we've actually started to learn about exploration in kind of standard MDPs。



![](img/92b4467453d2b29624c0251ce97b632c_70.png)

Yeah exactly so the idea here is that if you're in these kinds of MDPs。

 this state space is enormous and all of the possible actions you can take is enormous as well。

 and this is a way to bias the model towards a part of the state space that that is going to get high reward。



![](img/92b4467453d2b29624c0251ce97b632c_72.png)

Yeah， giving the bias of like， these are the kinds of things I want you to do。Okay。So in particular。

 what I'd like to talk about is like say you have some model that has been trained and you can do a variety of things。

 but there's scenarios where when you're actually deploying that policy， you actually。

 even if you have a lot of prior experience， you might need to explore at test time because you might not have all the information you need to get high reward。



![](img/92b4467453d2b29624c0251ce97b632c_74.png)

![](img/92b4467453d2b29624c0251ce97b632c_75.png)

And so we talked about a couple examples on Wednesday where， for example。

 you might need to find ingredients in a kitchen and to do that you can't just like start cooking。

 you need to open drawer， open cabinets and so forth to try to seek out information and second in language models for reasoning。

 you might need to explore different strategies that might lead to a solution to a problem rather than simply trying to start like writing tokens that you think might lead to the solution。

Now we talked about this kind of metal problem where we're optimizing a policy with history or with memory。

 and generally memory should allow agents to be able to explore and exploit because they're able to kind of try different actions and remember what they did and then use that information about where ingredients are to then solve the problem。



![](img/92b4467453d2b29624c0251ce97b632c_77.png)

![](img/92b4467453d2b29624c0251ce97b632c_78.png)

But we talked about how if we optimize exploration and exploitation together with an end to end objective。

 this is hard because we have this chicken and egg problem where if we haven't yet learned how to explore。

 then we can't actually get high rewards because we haven't found the ingredients。

 and likewise if we don't yet know how to solve the task。

 then we get low reward for any sort of exploration behavior。There's this coupling problem。

And we also talked about some alternative exploration strategies that are easier to optimize。

 but can lead to suboptimal performance。And the。

![](img/92b4467453d2b29624c0251ce97b632c_80.png)

What I'd like to talk about is iss actually a method that can。

Both get optimal exploit and exploitation trade off and also be efficient to train so it sort of gets the best of both worlds。



![](img/92b4467453d2b29624c0251ce97b632c_82.png)

And the idea for this is actually going to build upon this last alternative exploration strategy。



![](img/92b4467453d2b29624c0251ce97b632c_84.png)

Let's write this right here。So。The idea here is that。



![](img/92b4467453d2b29624c0251ce97b632c_86.png)

You can try to for different environments or different tasks。

 you could try to fit a dynamics model and a reward model。

And then try to explore in ways that tell us more information about our model of the environment。

And this should incentivize the agent or the policy to actually seek out additional information to explore in a way that's decoupled from executing executing on the task。



![](img/92b4467453d2b29624c0251ce97b632c_88.png)

![](img/92b4467453d2b29624c0251ce97b632c_89.png)

And so and if you do this and you have different MDPs that are correspond to like navigating to different circles。

And then you try to incentivize it to take trajectories that lead to a better model of reward and better model of dynamics。

 you'll actually get a trajectory that looks something like the purple trajectory where it's explicitly tried to visit states that allow it to learn where the reward function is going to be。

Now， this can learn efficient exploration strategies。

 but it has its downsides and it can be suboptimal in some scenarios。For example。

 if there's distractors， like if there's like pictures on the wall， for example。

 then it's going to be looking at all the pictures on the wall to learn a good model of those different environments。

So we can build upon this idea and try to learn how to explore without learning a model。And。

 in particular。Instead of trying to learn a dynamics and reward model。

We can instead try to be able to predict what the task is。

So we're going to label each task with a identifier mue。

 this could be either like a one hot like an index or it could be a language description or it could be kind of some more continuous description of the task。

 like continuous vector。

![](img/92b4467453d2b29624c0251ce97b632c_91.png)

And。Then what we could do is we could try to explore in a way that allows us to predict what the task is at hand。

So， for example， we'll have。Ourre。Say that we have two policies an explorationation policy and exploitation policy in practice you could combine these but。

It's helpful to think about them as separate， so we'll have our exploration strategy。

 this is our exploration policy， this is going to produce some experience in a particular task。😊。

And our goal is for it to be able to explore， to be able to discern different tasks。

 And so we could separately train a model that's going to be predicting。

The task identifier from the experience that we've collected so far。



![](img/92b4467453d2b29624c0251ce97b632c_93.png)

And if we do something like this， then。

![](img/92b4467453d2b29624c0251ce97b632c_95.png)

This sort of exploration objective is completely separate from actually executing on the task。

 This is the goal here is to be able to predict the task identifier。And then separate from this。

 we could train a policy。That's trying to execute on the task。Just using the identifier for the task。

And this is just multitask learning or multitask reinforcement learning。

 and this we can train just with optimizing reward and it doesn't rely on having good exploration。

So here we're able to decouple the objective for execution so it doesn't rely on exploration and have an exploration objective just based on identifying the task that isn't dependent on how well you do the task。



![](img/92b4467453d2b29624c0251ce97b632c_97.png)

So on the slides we trade policy in a task identification model so that we collect data that allows for accurate task prediction。

And then we'll also trade a policy that's conditioned on the task， the task ID D。

In order to yeah maximize reward for each task。

![](img/92b4467453d2b29624c0251ce97b632c_99.png)

So which part of this is the exploration， is it the model that predicts the identifier？

So the exploration is really this policy right here and this model is actually just going to be used for the reward for this。

 and so we're going to be the reward for this policy will be basically how well this model at is identifying the task or basically the negative error of this task identifier model。

Good question。 The question is， do this generalize to new unseen task categories。😊。

Can actually struggle with generalization and we'll talk about that。

 Let's go through meta testing and then we'll talk about that。

 So this is how roughly how training works。 and then test time if you've trained all of these different things。

 then you can take your exploration policy， run it to collect experience。

 then feed that experience into your task identifier model to get a task ID and then take that task ID and feed that is input to your execution policy to then execute the task so you'll then explore and then identify the task and then exploit。



![](img/92b4467453d2b29624c0251ce97b632c_101.png)

no。Getting back to that question， the upside of this is you don't need to model dynamics or rewards。

 you're just like learning this model that's predicting the task identifier。

 but if the task identifier is just a like one hot vector， for example。

 this probably like isn't going to generalize to new tasks very well and we'll see a solution to that on the next slide。



![](img/92b4467453d2b29624c0251ce97b632c_103.png)

The question is what is the main difference from blackbox meta Rl that we talked about before so we are still sampling different MDPs the main difference is simply the objective for the exploration part so well I guess there's two main differences one is the objective for the exploration part and then the second is that here we're going to be maximizing reward similar to blackbox Me Rl but we're actually going to be giving it this task identifier so that it doesn't need to rely on exploration or a good exploration strategy when trying to learn how to do the task。



![](img/92b4467453d2b29624c0251ce97b632c_105.png)

Now we have this generalization problem。And we actually also have a way to address this。



![](img/92b4467453d2b29624c0251ce97b632c_107.png)

Instead of using this task identifier directly， we can actually try to learn a more compressed representation of the task that will generalize more effectively than like a one hot vector。



![](img/92b4467453d2b29624c0251ce97b632c_109.png)

So as an example。When we learn the execution policy。

 we're also going to identify information that's needed for solving the task。

And so say that our identifier consists of a few things that are relevant and a few things that are not relevant。

 so it contains things like wall color and decorations。

 but then it also contains information about where the ingredients are。

Then we'd like to use and similar， if you had a one hot vector would also contain information that might be irrelevant because you might have two kitchens that have ingredients in the same place。

 but then have other things that are spurries。And we'll try to then bottleneck this representation to compress away the stuff that's not needed for solving the task。

And if we can do this， then this sort of representation should generalize better。

And then when we learn to explore， instead of learning to explore to be able to predict the identifier here。

 we'll learn to explore so that we can recover this compressed task representation。

And so try to be able to explore so that you're able to predict what this Z representation for the task is。

Now， how do you actually compress representations in neural networks。

 so before we go into the details of this algorithm， let's talk about that a little bit。So we have。

Yeah。We have our task identifier。

![](img/92b4467453d2b29624c0251ce97b632c_111.png)

New， new I。 And then we'd like to。Have a neural network that uses that to。Predict ZI。

And then we'll then have a policy that takes this and the state and outputs the action。

And if we train this whole thing and end it may not like it it's not necessarily incentivize to actually compress information here。

 to actually remove information about decorations， for example。So one thing we could do is we could。

Simply add noise to this representation。And so if you take this and。

Instead of feeding it directly here， you could take this output Z I。 And then right here， you could。

Basically add some noise。 So this would right here what you're doing is your。

Adding some noise where the noise is kind of sampled from。



![](img/92b4467453d2b29624c0251ce97b632c_113.png)

A Gaussian distribution。And if you add noise， then this is going to discard information because adding you're kind of corrupting this signal。

But you might discard some good information。Especially if you do this only at test time。Now。

 in principle， you could also train with this noise to encourage it to discard information from Z。



![](img/92b4467453d2b29624c0251ce97b632c_115.png)

But if you train the policy with this noise as input， then。



![](img/92b4467453d2b29624c0251ce97b632c_117.png)

What it could just do is it could just increase the magnitude of Z here so that the magnitude of the noise is a lot smaller in comparison。



![](img/92b4467453d2b29624c0251ce97b632c_119.png)

And so if you just add noise， the model can compensate and still pass in a lot of information through this task representation。



![](img/92b4467453d2b29624c0251ce97b632c_121.png)

So that's not a great solution。But。What we can do is we can just also prevent the model from increasing the magnitude。



![](img/92b4467453d2b29624c0251ce97b632c_123.png)

We can just add a loss that。We can kind of modify our training loss for the policy to include a term that's going to minimize the magnitude of Z。

And if you do this， you're kind of then now if it kind of blows up the magnitude of Z。

 then it will have a high loss here， and so itll be forced to keep that magnitude down to be lower so that it is actually forced to remove information that isn't needed and any sort of magnitude it does introduce which it will be incentivized to only have information that's needed for predicting the action。



![](img/92b4467453d2b29624c0251ce97b632c_125.png)

This is called a variational information bottleneck。

 which is kind of a fancy term for saying that you're adding noise and then also modifying your lost term to have this L2 penalty on your representation。



![](img/92b4467453d2b29624c0251ce97b632c_127.png)

One of the reasons why this called a variational information bottleneck is that this objective is actually equivalent to minimizing the kale divergence between your。



![](img/92b4467453d2b29624c0251ce97b632c_129.png)

![](img/92b4467453d2b29624c0251ce97b632c_130.png)

If you think about this as a distribution， because there is now kind of a Gaussian distribution with a mean ZI and a variance according to the variance of epsilon。

That's equivalent to minimizing the kale divergence between that distribution and the unit Gausian distribution。

Yeah so the question is why are we creating a representation of a one hott vector So if we go back to the algorithm we talked about before where we are exploring to generate experience。

 then trying to identify the task and then condition it on that task。

 if we then want to quickly solve a new task， then we'll be able to use our policy to explore but then。

😊，After we explore it。If our representation is a one hott vector here， if it's a new task。

 then that new task may not cleanly fit within one of the previous one hot vectors。

 and so we'd like to have a more continuous space that's more compactly representing the task and essentially learn like this latent task representation that will generalize two new tasks。

Yeah， so the question is dont we need more information about the tasks。

 like whether or not two tasks are related to each other now， I guess。

So when you think about a one hot， it doesn't really seem like it is necessarily capturing that much information。

 but a one hott vector actually cap is is actually less compressed than something that is。That is。

Something that's like a more continuous or less discrete representation。 So say， for example。

Let's see， let's say say for example that one of your tasks is like to go here。

 this is like task one， taskask two is to go here， task three is to go here and task like four is to go here。

Then task1 and task 4 are very similar。 But when you use one hot vectors to represent them， they。

They are not， they're kind of represented completely separately and if you try to learn a task representation that's compressing these。

 then it will actually learn a representation that puts these much closer to each other。

The question is， do you need to add epsilon to the loss， so it doesn't end up。coming into the loss。

 but you do need to add it when you're actually training the neural network。

 so you're adding the noise and you sample the noise every like resample the noise every single time and the epsilon is sampled from this distribution and you can sort of think about this distribution as coming into the loss。

But yet you don't need to add epsilon to anywhere and to the loss， it just comes out to this。



![](img/92b4467453d2b29624c0251ce97b632c_132.png)

Okay， so let let's like walk through actually like what this algorithm looks like more completely。So。

You。First let's talk about just like executing on the task separate from exploration。

 so our goal is to learn this task representation， this latent task representation。

 and how to solve the task。

![](img/92b4467453d2b29624c0251ce97b632c_134.png)

And to do this， we're going to have we have our task identifier and we're going to have a network that。

That produces Z I。 We're going to add noise to get Z I plus atla。 and then the。

And then we're going to pass this and the state into our。

 this is our execution policy that's going to produce。In action。And。

We can think about this as having two parts。 so we have the execution policy right here that takes us input the noisy Z I and the state to produce the action。

 And then we also have this part right here， and we'll write this as some encoder F that maps from mu I to。

Zi。TheWe can write this as a distribution because if you kind of。

Fold this noise into a distribution like this。 This will be some distribution that is let's call this now call this Z bar。

 This is a distribution that is a Gaussian with mean of。Of Z bar I and the Ansom variant。

Let's just write it as variance like that。So we have these are the two things that have parameters。

 F and pi， and we're going to train both of these neural networks to maximize reward so that we're actually learning our representation such that we can solve the task and predict actions that maximize reward。

And then we're also going to add the regularization on， on Z。

And so our objective here will be maximizing the sum of expected rewards under our execution policy。

And since we're maximizing here， we're also going to be minimizing this term right here。

 which is the equivalent to the K divergence。 So we'll be maximizing the negative K L divergence between。

F of。Z， I given。New eye。And this。Unit Gaussian。So on the slides。

 there's the objective and this is just trying to solve the task and also learn latent task representation based off of the task ID。



![](img/92b4467453d2b29624c0251ce97b632c_136.png)

![](img/92b4467453d2b29624c0251ce97b632c_137.png)

It's going to be a vector。 So Z is going to be a vector。 And so this should be an I。 The Yeah。

 it'll be a vector。 and you yeah。Yeah， so the question is why are we adding this information bottleneck or this kale divergence The reason is that we want to learn like a nice task representation that's throwing away information and if we don't add that term then this Z right here。

 this representation of the task might still contain a lot of information that are irrelevant for actually solving the task and so it might contain like if for example you have two tasks that have the ingredients in the same exact place。

 but something has changed about the environment like the wall color is different or different objects are in different place。

 but those are irrelevant to solving the task， then Z will include those things that are irrelevant and then when you go to explore you're then going be exploring things that are irrelevant to the task。

😊。

![](img/92b4467453d2b29624c0251ce97b632c_139.png)

Yeah， so the question is。We are given the task ID during training we actually don't need it at test time so what does this look like to generalize to new tasks when you are faced with a new task。

 you're going to use your exploration policy to explore and then predict a instead of predicting UI you're actually going to be predicting ZI。

 your latent task representation and then feeding that into your execution policy to then like execute or exploit on the task。

The question is can you train the execution policy to attend to the relevant parts so if you have a really good task representation that doesn't have irrelevant irrelevant parts of the like irrelevant things in it。

 then you can skip this stuff。And basically， like zero out those parts of the task representation。

 This would be in scenarios where you don't have a one hot vector， but you already know like。

Like maybe one task， maybe if you have like language strings， for example， and one task is。Turd left。

One task is turn right， another task maybe is the same as turn left。

 it's like and you have the task string for it， it's basically the same as that task another task is to like move forward。

呃。If these are your different tasks， you can get away with like this is probably already a very compact representation because it's telling you like are you turning。

 are you moving and so it's already telling you about the relationship between different tasks and so if your task representation is telling you about those relationships then or for example。

 if you had a task representation that's like the coordinates of where you're trying to go then you're gonna to have a task ID that's very similar between these two tasks and that will already be quite compressed in those cases you can skip this step because those representations will already exclude irrelevant information but then if you instead have a task ID that's one hot or that isn't very informative then you need to compress that out and otherwise there isn't like。

This is one of the better mathematical frameworks for encouraging it to attend to like the relevant parts。

 yeah。I guess in principle， if you had a way to like。

Change the way that this is making decisions based on UI。 you might also be able to do that。

Yeah so what's the advantage of outputting a distribution so the distribution here is what allows us to compress and so by adding noise or by making this a stochastic neural network we're able to remove information from it whereas if you are outputting like if you're passing a continuous vector through the there are kind of heuristic ways to try to compress。

 for example， like by compressing the dimensionality， but you can still pass。

Like infinite information through even like a one dimensional continuous variable。

 And so this is one way that can that can。Like even in theory， reduce information。

So now let's talk about exploration。 So our goal in exploration is to be able to try to predict disease。

And the。We will I don't know what notation I used， so our goal is to try to be able to collect data that's predictive of Z and practice by the way。

 you can train both of these policies at the same time。U。

And we need to think about how we would formulate a reward function that encourages it to be predictive of Z。

I don't know if I'll just pick some notations。 So say that we have。

We're going to be learning some model that's trying to be able to predict Z from the data that we have collected。



![](img/92b4467453d2b29624c0251ce97b632c_141.png)

And if we have some exploration policy that's been exploring。

Then we need to figure out how to reward it accordingly。

And one thing that you could do is you could collect some data， and then at the end of a trajectory。

 for example， see how well you can predict Z。And then have the reward be the negative prediction error for Z。

And then zero everywhere else。But if we did that， we'd have a very sparse reward。

 We'd only have it at the end of the trajectory。And what we can do is we could actually。

 like incrementally at each time step， look at how much information we're gaining about Z。

And that's going to give us a more dense reward and so specifically the when we're trying to train our exploration policy by exploration。

 the you can think about the reward。😊，For ST T 80。We could have it be the negative。Prediction error。

呃。Time step T。 And that would be something that's like fairly reasonable。But。The action。

 like this particular time up。We're only at this time step we're actually gaining just like one time step worth of information。

 and if we wanted to quantify that information， we could actually look at what was our prediction error at the previous time step。

And look at the relative like difference in the era。

 the previous time step versus the era at the current time step。

 And that's how much information we gained from taking this action。

And so we could define the reward to be the prediction error。At t minus1。

Mine is the prediction error at time T。And so how much like。

 this is something that will should be decreasing over time。

And there's basically how better are we at predicting ZI at the current timeup relative to the previous time step？

Where prediction error is something like。Is like Z hat。



![](img/92b4467453d2b29624c0251ce97b632c_143.png)

Mineus the true。Z I。And so we're training this model。

 we want this to be kind of perd up information gain。

 and so if we look at all of the states up until the current time stop。

Versus all the time steps stepss of the previous time step。

 we could measure this notion of information gain。

![](img/92b4467453d2b29624c0251ce97b632c_145.png)

I guess maybe also to make this a little bit more clear， if this is prediction error at time T。

 then this means that。Zhat is the estimate from。Predicting the。From the data。Up until。Time T。

 So everything in the trajectory up until time T。

![](img/92b4467453d2b29624c0251ce97b632c_147.png)

Cool， so this has like like many research algorithms， this has a somewhat mangled forced acronym。

 so decoupled reward free exploration and execution in Meal or dream。

 and you'll be implementing this algorithm in homework 4。😊，So。嗯。

We talked before about how if you train end to end。

 like if you train metaal methods end to end and you're trying to optimize for both exploration and execution。

 you have this coupling problem and。

![](img/92b4467453d2b29624c0251ce97b632c_149.png)

The benefit is that you can get optimal exploration and the downside is that you're very。

 very inefficient。

![](img/92b4467453d2b29624c0251ce97b632c_151.png)

And you can show that this algorithm under fairly mild assumptions。

 will actually recover optimal exploit and exploitation。And then if you look at the efficiency。

 which is where end to end optimization struggled， you can think about it。

 You can construct a simple bandit problem where。Abandit like problem where you have these different arms。

And arm zero， instead of being a typical action， is going to tell you what is the optimal action。

And so if you， for example， learn the strategy of taking action zero and then taking the optimal action。

 then that's like optimally exploring and then exploiting。And in end to end optimization。

 you can actually like quantify how many samples it needs for the meta learning process。

 you get something like a squared log A where a is the number of arms or the number of actions。

 whereas the dream algorithm requires only a log A and some assumptions here in terms of using key learning uniform exploration in the in kind of the outer loop of the algorithm and you can look at basically the kind of the efficiency like。

How how efficient is the algorithm you can see that dream is able to get is able to kind of reach the optimal behavior in many。

 many fewer samples than if youre to use end to end optimization。

 which is shown in orange as a function of the number of arms So as the problem gets more and more complicated。

 you。😊，Kind of dream is able to do kind of far， far better than end to end optimization。

We can also kind of empirically look at things， so here's an example of a metal problem where different taskss correspond to going to different objects with different colors。

And the color of the object is written on the wall and so and the agent starts over here and it needs to walk around the wall。

 rock around the wall， read read the color and then go to the correct object so it's exploring and then or seeking information and then exploiting。

gets pixel rewards and if you compare end to end algorithms that are shown here， they really。

 really struggle to do this sort of end to end like learning to explore problem。

If you use one of the alternative strategies that we talked about on Wednesday。

 you can do better in theory， but you still have a suboptimal exploration strategy。

 whereas with this algorithm you're able to actually learn how to explore like go find the sign and then go to the correct object actually by trying to kind of decouple exploration for identifying the task and exploitation of solving the task。

Cool， and then you can actually see this， so here's a video of the exploration episode where it's walking around and going to read the sign on the wall in this simple environment and then after it reads the sign。

 it's able to go to the blue key。

![](img/92b4467453d2b29624c0251ce97b632c_153.png)

Yeah， that's a great question so this is the question is like this is a setting where like exploitation and exploitation you can kind of first explore and then exploit you might also have tasks where you need to interleave exploitation and exploitation where you first need to like find some information that use that to like accomplish a subtask and then find some exploration again we have done some work that tries to combine them and you can for example。

 trade a single policy that uses the reward to identify the task combined with the task reward and if you're interested I can kind of point you to a relevant work there。



![](img/92b4467453d2b29624c0251ce97b632c_155.png)

Okay， so to summarize learning to explore and learning policies that know how to explore end to end can learn optimal exploration and exploitation。

 but if exploration is hard， it's pretty hard to optimize and we saw an example of that where all of the methods were kind of flatlining and not learning good exploration。



![](img/92b4467453d2b29624c0251ce97b632c_157.png)

![](img/92b4467453d2b29624c0251ce97b632c_158.png)

Alternative strategies are easier to optimize and can be principled。

 but can also be suboptimal by large amounts and be very inefficient about exploration。

And this decoupled approach leads the optimal strategy is also easy to optimize so it sort of gets kind of the best of both worlds。

 it does require this task identifier you need to at least be able to enumerate your tasks and know which of those tasks you're in and that's kind of the key thing that it's using in order to get the benefits。

Cool， we have a little bit of time and so you can actually。

 I wanted to briefly talk about one application so you can take this algorithm and use it in a domain that's a little bit different from what we've seen before。



![](img/92b4467453d2b29624c0251ce97b632c_160.png)

![](img/92b4467453d2b29624c0251ce97b632c_161.png)

This domain is trying to find bugs in different computer programs。And in particular。

 in Introcomputer science courses， although this is probably applied to other programs as well。

 it's really cool for students to be able to like make computer programs。

 it's like very rewarding for them to like write a program as they're learning how to code then that creates like a program like this so on code。

org students code up this game called Boun that looks a bit like Pong or one side of Pg where the goal is to hit a ball into the goal。

😊，In CS 106A at Stanford students code up breakout and so they might code up a program like this。

 this is an example of a buggy game where the ball actually kind of gets kind of sort of skeweered by the paddle。

 it kind of bounces off the paddle rather than going and losing a point or losing a life。

And we can basically treat different student programs as different tasks。

 where our goal is to explore and find the bugs that might exist。

 and our ultimate goal is to then be able to provide feedback to the student on the different bugs in their program。

One of the other things about this is it's really time consuming for Ts or instructors to actually grade and give feedback on these assignments because you often end up playing the game in order to figure out and find the bugs。



![](img/92b4467453d2b29624c0251ce97b632c_163.png)

![](img/92b4467453d2b29624c0251ce97b632c_164.png)

Cool， so we can use Me R。 We can actually use exactly the dream algorithm and train it to be able to identify a different different kind of。

😊，Distinguishing factors from different students and it can learn exploration strategies like what happens if the ball hits the goal so here it's trying to actually play the game successfully。

 it can also check and act so that like what happens if the ball hits the floor is actually purposely trying to like not hit the ball or also try to hit the wall instead of the goal and this is an example of a buggy program that creates lots of different balls as soon as the ball hits the wall。

😊，And then there was an experiment in 106A two years ago in the spring 2023 quarter where TAs actually used the MeRL algorithm and the policy to basically grade and prepopulate the rubric for grading。

 and then they kind of just verified that the rubric answers were correct from watching the videos of the meta RL agent playing the game。

And it led to 44% faster grading and also 6% more accurate grading。

 and the TAs generally liked using it， they also used it in at least one subsequent quarter because they liked using it so much。

😊。

![](img/92b4467453d2b29624c0251ce97b632c_166.png)