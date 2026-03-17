# Stanford CS221 ｜ Autumn 2025 p07 Stanford CS221 ｜ Autumn 2025 ｜ Lecture 7： Markov Decision Processes [2ZtF1j3n6XE [BV1XuPrzwEes_p7]

![](img/37872379786be875ac7b771ae9d09d0d_0.png)

Okay， thanks everyone for coming on this rainy day。This week。

 we're going to talk about Markov decision processes and reinforcement learning。

Just recall where we are last week we talked about search。

So search was our attempt to get into agents that could reason。

And we formalize search as a search problem where you define a start state。

 set of successors from each state， which include what actions you can take， what their costs are。

 where you end up， and finally is end criteria。The main thing about a search problem is that。

An action is deterministic。 you're in a state， you take an action。

 you go deterministically to a separate state。 So remember this tram problem that we had before。

 the start state was one and you're trying to get to location 10。

 So if you look at the successors of a given state you have different actions。

 each action has some sort of cost and associate with each action is deterministically one particular state。

Okay。And so now we're going to make things more interesting and talk about Markov's decision processes。

 so these generalized search problems and the key difference is that now when you take an action。

 it can have a sarcastic outcome。And this shows up in a lot of different places， for example。

 if you're playing a game and you're rolling a dice， or if you're for example。

 trying to figure out how to go to your grocery store and you're trying to find the optimal decision to make you to walk。

 bike or drive， and you need to take into account the uncertainty。

 which includes how much traffic they will be on the road。

 time to find parking and so on and so forth。So most of the time in the real world。

 there's actually uncertainty and search problems won't be able to capture that because everything' is deterministic and mark off decision processes will because it will show you how you can incorporate uncertainty。

Now a lot of the structure that we have from search problems will just carry right over。

 so don't forget last week， we have to kind of build on top of that。

 but we'll see some interesting things that result。Okay， so let's jump in and define what the MDP is。

So Markov decision processes ACs have a very long history going back to operations research in the 1950s。

 the board Markov comes from this theory of Markov chains in probability and statistics and the idea of a Markov chain is that the past in the future are independent given the state right so remember from a search problem。

 the state captures everything that you need about the pass so that you can evaluate actions and costs going forward。

Okay， so that's the Markov part of MDP。 The D part is a decision。

 which means that unlike a Markov chain， which is pure simulation。

 you're just running a chain and seeing what happens。

 A decision means that you're having an action agent that takes actions and trying to find the best action to take。

And finally， process just means something that happens sequentially over time。

 It's a term from probability。 So that's breaking down what Markov decision process is。

So to define our first MDP， let's take the travel problem from before。 Remember。

 we had locations one through N and walking from I to I plus one takes one minute and taking a tram from I to I to I takes two minutes。

 This is all the same， but we're going to add one twist。

Which is that tram can break down with some probability。Okay，So in a search problem。

 we can't model this because either it breaks down or it doesn't。 But in the real world。

 we know that things can break down with some probability， hopefully low。

So the goal is to go from one to n in the least time in expectation。 So again。

 the wording is chosen carefully here， when we had a search problem， we could just say。

 what is the minimum cost path？There's a path， and that's it。

 But now things can break down and sometimes it might break down， sometimes it won't break down。

 And so we have to take an average over possible outcomes。Okay， so let's define the flaky tram MDP。

So we have 10 locations and failure probability is 0。4 so this is a pretty bad tra。

 but I guess if it's magic， it's probably not going to be so reliable。Okay， so we have a start state。

 which is one。Okay， so now let's look at the successors。 This is where a lot of the action is。

 So I've defined the interface to be essentially the same to highlight the parallel between the search problem and MP。

 but it's going to look a little bit different。 So in the search problem， remember we had walk。

 So if you could stay within balance。 then you can have a walk action， this part is the same。

 except for there's a few things that are different。 So the action is walk， probability is one。

 And when I say probability1， that's basically my probabilistic way of saying deterministic。

 if something happens with probability1， that's sure to happen。 instead of saying cost equals one。

 I'm gonna say reward equals minus-1。 That's just by convention。 So cost is the negative reward。😊。

And then state， I go to state plus one。Okay， so that's the walking action。 And now。

If I look at the tram， what happens if I take the tram？If I can stay within bound。

 So if I take the tram， remember， I go to2 I， then there's two successors that I create from this one action。

 The first is what happens if the tram is actually successful。😊。

So with probability 1 minus the failure probability， which is 0。4。

 then I can move to state 2 I and I get a reward of -2。 So that's a cost of2。Okay。

 so that means with probably 0。6， I can go to state 2。Now， what happens if the tram fails？Well。

 if the tram fails and I just stay stay at the same place。Okay， so with probability 0。4。

I am still stuck in state one。Okay， so interesting。

 note that this is actually a cycle which might or may not cause you problems depending on in the search case。

 but we'll show you algorithms that can handle all cycles no problem。Okay。

 so those are the successors。 So I have three successors。For the two actions。

 because I have nondeminism， the number of possible places I can end up might be larger。

 not necessarily， but it could be larger than the number of actions。 and finally， is N。

 this is the same as before。Just test whether the state is reaching n or not。Okay。

 so let we can draw this。Out this song。 let me try to make this a little bit bigger momentarily。

 So it gets a little bit know confusing about。 I'll try to explain it。 So star state is one。from one。

 you can walk and I'm using these dotted circles to represent sort of I'm at a state and I've taken an action。

 I call these chance nodes because at this point there could be multiple places I go but in this case if I take walk action from state1。

 then with probability one， I end up in state two。With a reward of minus-1。

And if I take the tram action， then notice that there's two edges coming out of tram。

 I can go to state 2 with probability 0。6 reward of minus2， or I stay in state 1 with probability 0。

4 and reward minus2。And then from two， I can walk， it goes deterministically to3。

 I can either try to take the tram in which guyss either stay in the same place or I go to four。

And so on。 and you can see the graph and eventually everything goes to 10。O。

 let me pause there to make sure everyone's on board with MPs， how they're defined。

So the outline is pretty much the same。 I have a star state。 I have a set of， you know successors。

 now the successors have probabilities associated with it each one and。

And then the is and is the same。Okay， any questions？

I them where the probability come from free state。So the question is。

 where does the probability come from？So this is the probabilities are part of the problem definition。

 So when I define what the MP is， I have to specify the probability for every possible successor。

In this case， I just made it up， I just put  point。4， you can put  point。3。 It's just an example。

on Wednesday， I'll show you how if you in general， you don't know the probabilities。

 you can try to estimate them or you know， use reinforcement learning。

 which doesn't require you to know what the probabilities are。Any other questions？Okay， let's go on。

So so far I've done this in code on the assignment， you'll see a bit of mathematical notation。

 so let me just try to translate between the two。So from a given state S。

I'm going to let actions of S denote the possible actions here， in this case， it's walk or tram。

I'm going to use reward。S A S prime。So this to explain this。

 so suppose I'm in state S and I take action A and I manage to end up in state S prime。

 what is the reward that I get？ so it's a number that tells me if I took this step。What would happen。

Now notice that in general， these triples encapsulate two things from S to a。

 that's the agent I'm making a decision， and from a to s S prime。

 that's sort of nature making the decision。the agent importantly doesn't control whether the tram is going to succeed or not。

 that's up to chance。And the probabilities of chance are governed by this transition function T。

Again， the same type signature here， so I have S。Which is a state， I took action A。

And then I end up in state S prime with this probability。Okay， so in this example， let's see。

 So this P is a transition probability， so five so transition of  five tram and 5 is 0。4。

 transition of 5， tram and 10 is 0。6。And because this is a probability， something has to sum to one。

 So what sums to one is that for every stage action pair。This， if you sum over all the possible。

Subsequent states， that probability has to be one。So in this example。

 if I look at every state action pair， which is every chance node here， everything that's dashed。

 and I look at all the outgoing arrows。Those probabilities have to sum to1， so 0。4 plus 0。6 is1。

 okay， just a good standard check。All right。So we'll go back and forth between code and this mathematical notation。

 but conceptually we're talking about the same thing。Alright。

 so let's consider another game just for fun。 Okay， so this is going to be a little dice game。😊。

So it proceeds in rounds。So each round， you decide whether you're going to quit the game or to stay in the game。

If you decide to quit， you get $10， and then we send you on your me way。If you decide to stay。

 you only get $4， but then I'm going to roll a six sided dice， and if the dice results in one or two。

 then we end the game。Otherwise， we continue to the next round。So if you decide to stay。

 you get less money， but there's a possibility that you get to continue and the next round you might get four more dollars or you can always quit and get 10。

Okay。So。So let's define this formulaly。 So the start state。Is going to be this constant called in。

 which means I'm in the game。Okay， and the successors。Of this state is。I can quit。

 in which case with probability1， I get re pick up my $10 and go to an end state。

If I decide to stay then with probability  one third， which is the dice coming up1 or 2。

 then I pick up $4 and I， head out the door。ButBut with probability two thirds。

I pick up $4 and I get to stay in the game。Okay， so this is just formally how writing down the game here。

And then is end is， as you might imagine， just a test whether the state is equal to the end state。

 there's only two states in this game in this MDP。And if we dry it out。This is what it looks like。

 So we have in you're in the game。 You have two decisions， two actions you can take。 You can quit。

In which case with probability 1， you get reward of 10， you end up in end， if you decide to stay。

 then with probability one third， you end up in end， pick up a reward of four， and with two thirds。

 you pick up a reward of four and you go back to n。Okay。So just out of curiosity。

 how many of you would decide to stay in the game。Okay， so I'm really。It from betters here。 Okay。

 how many of you would just take your $10 and get out of here。 Okay， smart move， too。

 How many of you would do something else。Maybe it's like stay in for three turns and then quit or something like that。

Okay。No。Well， we'll come back to that point it turns out that there's no point in this case of choosing some hybrid strategy that's either you're going to stay or you're going to quit and I'll maybe explain why towards the end。

 or if I forget then ask me。Okay， so hopefully we've shown two examples of MDPs。

Just to reiterate the comparison with search problems。So there's a lot of similarities。

 both have idea of states and actions， both have a start state and as is in function。

 both have this successors function that returns possible actions and their consequences。

There's a superficial difference between them， which is that the search problem uses costs and the MDP uses rewards。

 but again I stress that you should be able to convene your head easily flip back between them if I say a reward of minus2 that means a cost of two。

Okay，Its this is just kind of pure convention because the folks who develop MPs like to think about。

 you know， I guess， rewards and the people who like to think about a search was all about kind of minimizing costs。

 Just like in machine learning， people look at error rates。 And sometimes you look at accuracy。

 It's really two sides of same coin。Now the deep difference， however， is that in search problems。

 each action has one next state and MDVPs， each action has a distribution over next states。

And that is the difference that's going to cause us to have a lecture on this as opposed to not a lecture on this。

Okay， so。That's MDP。Now， let's talk about policies。So in fact。

 we've already introduced what a policy is。 Remember when we talked about best event。

 but let me try to introduce it again in the context of MDP。 It's actually the same definition。

So here we have our flaky tram MDP。So the first question is what does a solution to MDP look like？

Okay， so in a search problem， a solution with just a sequence of actions。 Everything's deterministic。

 you start to say， you can just preplan everything， I'm going to take this action， take this action。

 take this action， and I'm done。But this for MDP， this is not going to work because when you take an action。

 you could go either to state 3 or state5， and then depending on where you end up。

 different actions might be applicable。Okay， so this isn't going to work。So in MDP， instead。

 we have to define a solution as a policy。So a policy， remember。

 is a function that maps a state to an action。And this is important because now no matter where I end up。

 which state I'm in， I always look at the policy and the policy is going to be my guiding light and tell me what action to take。

 and that's what the solution looks like。 It's not just one action path， but really for every state。

 what should I do。Okay， so。Let's explore some simple policies。So here's a policy for the tram case。

 always walk， okay， remember policy takes a state， returns in action。

 So in this case it just ignores the state and always returns walk。And。Dale。

 clearly the action is Walk here。Here's another policy。

Take the tram if it's possible to okay so this policy is going to say if Im I may be able to stay within bound。

 then take the tram otherwise， and then okay， so I took the tram and that for say3。

 but if I pass in state6， then I have to walk because six times two is greater than a number of locations。

Okay， so that's what a two policies and there's you know。Potentially other policies， you can imagine。

Okay， so now you know what a policy looks like， how do you evaluate a policy。

 how do I know if it's any good or not？So a rollout is a simulation of a policy in MDP。

 which means pick up your policy and go at it on MDP。

 and then that gives you a sequence of steps and then we can see what happens。

 Sos let's take an example。 So let's take that policy that always walks。

Okay so I'm going to have this function generate rollout that takes MDP。And takes a policy。

And then I'm just going to roll out that policy。So you might have heard of the term rollout in the context of reinforcement learning。

 the same idea， which is that you run a policy on your environment and you get some sequence of steps。

Okay， so I start with state one， and then while I haven't reached the end state。

 I'm going to choose an action， in this case， walk because I mean it's always walk policy after all。

And then so if the policy does this， choose action， what does the MDP do。

 the MDP is responsible for actually choosing the successor according to that action so in this case。

It's kind of boring。 so I'm basically looking at the successors and I'm only taking the ones that have the appropriate action that was chosen。

 So the subset of successors with this action。Look at the probabilities， there's only one action。

 so there's only probability one， I sample a successor according to the probabilities。

And then I that's my step。Okay。In this case， this is going to be somewhat boring because sampling from one choice is just choosing that option。

 but you can see kind of how this algorithm goes and at the end。I get a sequence of walk actions。And。

嗯。Each action has a reward。And。In general， you can sum the rewards and you get the utility。

Now there's a one caveat， so you see this discount thing， MDPs all have some discount factor。

 and I'll explain what that discount does。So each rollout， which is a sequence of steps。

Has generates a utility。And that utility is a discounted sum of rewards。

 So let me explain what that means。 So the discounting is a way to capture how important we think the future is。

And this is represented by a number between zero and1， often written as gamma。So in the normal case。

 you would say discount equals one， which corresponds to no discounting。

And that says the future is just as important as the present。So if I look at a compute utility。

 I give it a sequence of steps and discount one， what does that do？So I look at each of the steps。

And I look at the reward。And I multiply that reward by discount to the if power for the I step。

So the step zero will just have the reward， step one will have the reward time discount。

 step two will have reward time discount squared and so on。So in this case， because discount is one。

 this term doesn't do anything， and I get my rewards， I sum them up， I get my utility， and that's it。

Okay， so notice that each。Every step has reward one。

And each step contributes to the utility just the same number as any other step。Okay。

 so this is no discounting。Now， what happens if I discount。With zero， this is full discounting。

In this extreme， the future doesn't matter。And so if you compute utility， notice。

 remember I multipied by discount to the I， if discount is0， that means essentially if I is not zero。

 then I get a bunch of zero， zero is out the future。so when I sum that， I get a utility of minus1。

And then finally， usually， you put the discount as something in between。

 So if you do half discounting， the next step will matter as much of。TheAs much as the present step。

So you might think of。This is， a dollar today is only worth 50 cents tomorrow。

So if you compute the utility with a discount of 0。5， you'll see that every subsequent step。

 I hit the reward with 0。5。So even though this used to be a reward of minus1。

 this has been kind of really squashed to something quite small。Okay。Yeah。Square discount squared。

 or is there other functions。So the question is whether discount always looks like this。

 so the form of the discount is discount raised to the power and in general， certainly in this class。

 that's the only type of discounting that we're going to look at。

 it happens to be mathematically convenient for some algorithms。

 there are other forms of discounting that you can look at that， don't factor in this format。

 but yeah， happy to talk about after。Okay。So just the recap。I have MDP， I have a policy。

 I smash those together， I get a rollout。And the utility of that rollout is the discounted sum of the rewards where discounting captures how much I'm going to pay attention to the future。

So normally， discount is going to be one or very close to one。

Usually you don't see things like discount like 0。5 or smaller because that's like saying I don't really care about the future and the whole point of doing MDVPs is that we're trying to make this kind of long term decision making so that the future does matter。

Yeah。Sorry， what do you mean by whether the future matters or how important？

So a question is what do I mean by the future mattering or not， Okay， so let's go back here。嗯。

So when I roll out a policy。I have at every time step， a reward。RightAnd generally。

 you would look at the sum of all the rewards。 and that's the value basically how good that policy is。

嗯。Now。When you have discounting， you're saying that the rewards you get later on don't matter as much。

Because they're essentially artificially squashed down。Right， bym multilying by。

 I'm multiplying by the discount。So suppose you had to make a decision。

 your policy you're trying to think about， you're trying to find the optimal policy。

 so a policy could say I'm going to pick up $2 now or I can pick up $2 in the future。

 and the higher sorry， the more discounting you do。

 the smaller the value of gamma means that I'm going to try to capture the reward now as opposed to try to get it later because it's not going to be worth as much later。

Yeah， example use case from。Can I come up with a different use case besides calculated present value？

I mean， for every MDP you have。A notion of discount， right？ So depending on your application。

 this is。I mean you think the present value calculation is like the economic kind of motivation for this。

 and so that's the right intuition to have。But we're doing this in the context of trying to find optimal policy。

Yeah。Yeah， so in some definitions on MDP， the reward function is based on the state in itself。

 so if there an advantage you're doing it this way where the reward is dependent on like state action and the next state。

Yeah， so the question is， let me go back。Let's see， to the definition of this MDP。So the question is。

 sometimes you see a formulation of MP where the reward。Just depends on the state。

Or it just depends on the state and the action。I've written it to be dependent on both S A and S prime。

Turns out that these are all。More or less equivalent and what I mean by that is that。

 if I had written down a form， that was like in this，Space。

 I could make it not depend on S prime by introducing other states。

 So I could make a dummy state that says， okay， well， I'm gonna transition to that dummy state。

 And then I'm gonna pick up my reward。 So there's games you can play to essentially have the。

 the formula， a simpler formulation。The reason I do it this way is that it's much more natural to define MDPs because you you're giving more flexibility。

 and it doesn't change the algorithms。Yeah。Yeah， sorry it's discounting。For always right， white。

If there's a question that we really need。TheThe steps that in the future are we set a very。

Big discounting factor。Does that make that we will pivotiate from the right answer？

So the question is， like， is this countanting always right or maybe a good idea。

 so suppose you're going to get the right answer in the future？Right。

 so if you imagine you need to have a policy that thinks a lot and comes up with an answer to a problem。

You probably don't want discounting or you want discounting to be very， very small。 So。

 it's always confusing。 More discounting means smaller value。 So discounting to be like 099。

 for example。So 0。99 discounting will say you're not discounting your future that much。

 but it applies a little bit of pressure to say like， come on。

 let's get on with life and try to short make sure your action sequence is as small as possible。Yeah。

So it's kind of a length penalty。 is another way to think about it， if you want。Okay。

So good questions。 Let's， let's move on。 Okay， so we have MDP， we take a policy。

 We smash them together to create a rollout。 and that generates a sequence of。😊，There steps。

 and that defines a utility。So if I do this multiple times。

 I'm going to get potentially different utilities。So for example， this time。

 I took the tram and I got stuck and I'm in state one， but this time I managed to go through。

For example， and you can imagine， you know， there's exponentially many different things that can happen。

So notice that the same policy yields differents of different rollouts。O。So now the question is。

 how do you going back to the question， how do you evaluate a policy？The answer can't be just。

A random number。I can't just say my minus 10 here。So what should I do？第二。Yeah。

 so you can look at the expected value。 So in this case， it's very intuitive。

 You roll out many times， and use just average。And formally， the expected utility。Of a policy。

 also known as the value of the policy， is defined as the average or expected utility。

So you might have heard of like value functions and reinforcement learning。

 which I'm going to talk about later and also next time。 This is basically the value is this value。

So notationally in math， often write that as v sub pi of s。

 and this is the expected value or expected utility or value of starting in state S and following policy pi。

So I'm generalizing this a little bit to say I can start in any state， not just the start state。Okay。

 so some of you who kind of remember last week in dynamic programming should be thinking this is a little bit。

Starting to look a little bit like future cost， it's not quite future cost for various reasons。

 but the idea of defining from a given state some sort of quantity that involves going to the end。

Okay， so let's implement this very naive algorithm for estimating the value of a policy。嗯。

So it's called Monte Carral policy evaluation。 you pass in a MDP and a policy and a number of rollouts that you want to do。

And it basically calls that generate rollout function that we saw before and takes the utility and number rollouts times。

And then just compute the average， and that's it。So。For W， I only did one rollout， why is that？

doesnYeah， it's deterministic。 So I only need one rollout。 Okay， so for the tram， if possible policy。

I'm going to do 20 rollouts and just in case this partial notation basically says this function takes two arguments。

 partial applies it to the one argument and the resulting is a function that takes the second argument。

嗯。Okay， so let's do this， so I do a number of rollouts and each time I get a different value。

 those are the utilities for each of the rollouts。And then I average them。And again， minus-11。7。Okay。

 and if I cre the number of rollouts， eventually， this will get more and more accurate。Okay。

All right。Maybe just one comment on this is that it will converge to the correct answer。

 but what rate does this estimate converge？So if you remember kind of probability in statistics。

 the error in your estimate is roughly one over the square root number of rollouts。

So if you have 100 rollouts， then your error is like one over 10， roughly。Okay， so， you know。

 it's not bad， but we're going to see that we can do a lot better。

 Yeah I can't really why it's always conver。ほい。If a map is going to have two results with simple ability。

Then it's likely to have two results separately， right？So the question is。

 why does this Monte Carlo policy evaluation always return one number？你在什么。嗯。

So maybe it just to simplify this。 So imagine you're trying to estimate the probability of heads of a coin。

So every time you flip a coin， you're going to get either heads， let's say a1 or tails。

 which is zero。Right， so if you flip this 100 times and compute the number of heads。

 that gives you an estimate for the probability of heads。So does that make sense？そ。

Sorry for the direction， but let's just take this example。 you do have a hat at the tail。

 So next time it's going to be half possibility tail， half possibility add。

So it won't converge to any one or zero， right？Gos21 or0。So okay， so first of all。

 this is the exact same principle as a heads and tails example。

 So I'm glad we have something simpler to think about。

 So it is true that the sequence of heads and tails doesn't converge， right。

 You've run a million times it's still gonna to be heads， heads， tails， tails， heads， tails。

 whatever it is。😊，But if you average。Over。That time horizon。

 if you run a while million times and you look at the number of heads you have。

 it's probably going to be something around like 500000 if it's a fair coin。

And so I'm interested in the fraction of heads。Not in any individual outcome。Okay。

 I'm happy to address that later yeah。Okay。But the average utility is just the average of the utilities naturally。

😊，Okay， so that was the flaky tram example。Now let's do this for the dice game。Okay。

 so this is this is going to be the the moment where you we reveal which is the better option。

 Do you quit or stay okay people。Can change their mind if they want。U。Okay， so let's say we。

Do you always quit。So what's the value of always quitting？Actually， we don't even need to run this。

 but hopefully it should be fairly clear。10， right， okay， but just to go through the algorithm。

You generate a rollout and you collect a utility of 10 and only you to do it once because it's deterministic and that's it。

Okay， so what about stay？So I'm going to do this 20 times。And。Sometimes I get four。Right。

 so this happens with so this is like I stay and I get kicked out。

 so that's happens with probably one third，8 happens with probability two third times one third。

 So you know I stay， but then I got kicked out and sometimes I get well， 60。

 I got really lucky there， but often I get four okay。So if you take the average。Okay。You get 12。8。So。

How many of you would still stay？I mean， sorry， how many will you work with Quid？Wait， okay。

 so staying gives you an average utility of12。8， and quitting gives you a。Value of 10。Okay。

 so how many of you would quit？Okay。Maybe you don't trust the simulation here。 Okay， fine。

 That's fine。 If you trust this， then I think you should probably， probably stay。

If you're trying to maximize utility， if you want to lose money， that's another story。Okay。

 so this is just a kind of example of in some sense， like we haven't introduced any algorithms。 Yeah。

 it's just trying to introduce the concepts of a policy。

 policy you rollout gives you utility and you can average utilities。

 and if you are only comparing two policies， you can just estimate the utilities or the values of these two policies and choose the better one。

Okay。Now， of course， these are only estimates。And。So can we compute them exactly or more exactly。

 if that's a thing you can say？Alright， let's talk about。Policy evaluation。So， so far。

We've performed multiple rollouts of a policy that gives us multiple utilities。 I average them。

 and that gives me the value of a policy。So is there a way to compute this more efficiently and the answer is yes。

 and the key is going to be using recurrences。 So remember how we look at dynamic programming for search problems。

 an idea of future cost， it's going to be the same form here。

The details are going to be different because I have probabilities involved。 But really。

 the structure of that recurrence is the same here。So first I'm going to introduce idea of Q value。

Okay， so what is a Q value？So a Q value， which takes three arguments， a state， an action。

 and a value function， this is a little bit nonstandard。

 but hopefully it'll become clear why I do this。This is the value of taking action A in state S。

And then。Obtaining value V based on whatever state I end up in。Okay， so the idea is that。And。

 let me try to draw this here。 Okay， So the Q value is the idea is that I'm in state S。I take。

An action。And that leads to SA A。 so chance nodes are I've taken an action in state S。

 and then I'm going to remember this can lead in multiple places and to some state as prime。Okay。

 so the Q value is a function of these chance nodes。 So I have a Q S A。

And this is going to be whatever reward。I pick up by。You know。

 takingak this action and going somewhere plus whatever。嗯。You know， value， I'm going to pick up。Next。

 so hopefully I'll finish writing this。 so I get some reward。

And then I get whatever happens afterwards。Okay， so remember in future costs， it was always。

 you take a first step， something happens， and then there's the rest of the problem。

So the first step is taking getting some reward and then there's the V。

 which specifies how much value I'm going to get。Okay。

 hopefully this will become clear with an example。 So let's consider our flaky tram example again。So。

Let's suppose we just come up with initial set of values that corresponds to just。Doing nothing。

 essentially。 Okay， so this is going to be for every state。I have， if it's an end state。

 I get zero because if it end state， I'm done and I just get reward0。And I'm going to put。-100。

 this is a little bit arbitrary for every other state that is not the end。

 It's minus100 because you know I haven't even figured out how to get to that state or from that state what to do so minus100 is kind of like just saying it's invalid。

Okay， so let's。Warm up with computing the Q value just for one state。

 so let's choose state 9 and state 9 is right before the end state。And。

Let's consider the policy of always taking the tram if possible。In that state， state nine。嗯。

That action is going to be walk。Because I can't actually take the tram。So now。The successors。

Are this， so one successor going to stay 10？And now I'm going to have this function called compute the Q value。

And that's going to take the successors， the discount， and the values。Okay， so what does this do？嗯。

This。I is going to look at all the successors。So remember， think about this as I'm out of state。

 I took an action and here are the successors， so these are these arrows。

 each of these are successors， three successors on the board。For each one， I'm going to compute。

The utility of， if that were to be chosen， which means that theres a reward。

That it got plus the discount times values of the subsequent step。Okay， so this is this reward。嗯。

Plus， gamma times this。And I'll just write it like this。그。Okay。

 so I'm considering all of the possibilities that can happen。Okay， and。So those are the utilities。

 I'm going to weight each utility by the probability。And then， sum them all up。

And that is going to give me some value minus-1。嗯。Okay。So I can also。

 maybe I should also write this in math just too。Make sure people are aligned。QSA。

This is supposed to be the value of taking action A and state S and then seeing what happens。

 so in order to figure out what happens， I have to sum overall possible successor states。

The probability of that successor state happening， which is a T of SAS prime。

And then I have the reward。Of SAS prime。Plus。This is an immediate reward plus gamma times v of S prime。

Yeah， each of these S primes are different prime Yeah yeah， so each of these S primes are different。

 each of these R's are different， I'm just I could write one two as well。Yeah， how is this。

Do you just experience again how this is different from how we are evaluating？So the question is。

 how is this different from how we're evaluating it before？So what we were doing before is simply。

You're out of state， you take an action， and then I'm going to just pick a successor。

Based on these probabilities。 So just choose one。And now I'm looking at all of them。Yeah。

And the reason you might hope that this does better is that if you choose one。

 then you have like sampling noise， whereas here I'm just like looking at all of them and that'll give me a more exact testament。

Okay， so any questions about this equation on the board here？So， I'm。At a chance note。

 I've already committed， the policy has committed to an action， and I'm trying to figure out。

How good is this？Consider all possible futures。Waied by the probability of that outcome。

 and then the reward。Of endingy up in one of those successors。And then you consider this V。

 which is the value of whatever happens afterwards。O。So we're almost there to policy evaluation。嗯。

One thing I need to do is I need to do this for all the states instead of just state 9。

 And then then the key step is that。I need to repeat this。Instead of just V being。You know。

 this sort of terminating set of values。But I'm going to compute the values。 And then I'm going to。

Put them back into the， I'm going to take these values。

I'm going to use these compute a new set of values。

 and then I'm going to replace these values with a new set of values and continue iterating。

 So let me kind of explain this a bit better。So there's this idea called bootstrapping。

And so after zero steps， which is in the very beginning。

These values are denoting essentially the value of just terminating。

And that's why they look like this because if I terminated。

 then I get zero reward at the end state and then this is know everything else is like invalid essentially。

After one step， what I want is that the value to represent the value of following the policy for one step and then terminating。

 and after two steps， the value of following policy for two steps and then terminating and so on。

Okay， so so let me run this okay， before I run the algorithm， I want to talk about one other thing。

 which is convergent。 So if I'm running this， this algorithm， how do I know when to stop。

So in gradient descent， obviously， there's also the problem。 How do I know when to stop。

 And I just sort of said， well， you know， running for 100 iterations or whatever。 Now there， there's。

And these MDPs， you can actually do a little bit better because the optimization is。

I guess more exact here。 So if whenever you have an iterative algorithm。

That computes a set of values and then a set of values and set of values and a set of values。

 you look at the maximum change between iterations。

 so you look at these values compared to these values and suppose you started with these values。

And then after one iteration， you update it to these values。So you compare a distance。

 compute the distance between a set of values。And that so element wise， you look at the distance。

And you take the maximum you know distance between them。

 So this is also called the L infinity distance， and there happens to be two here。

 and that corresponds to the fact that despite state one having a really awesome estimate。

 state  three is still pretty far away。 So you want to make sure all the state values are close。

 so that's why you take the maximum。And when the distance is maximum distance is less than some tolerance。

 say 10 to the minus5。Then we can say we're done。Okay。

 and this this primitive will be useful for both policy evaluation and evaluation later。Okay。

 so I'm finally ready to introduce the policy evaluation algorithm。

 Hopefully you've seen all the moving parts I just need to assemble the pie。Okay。

 so let's take up our flickicky MDP， flicky tram MP。 I'm going look at the tram， if possible policy。

 and I'm gonna to run policy evaluation。Okay， so let's jump in here。So first。

 I initialize the values。 So every state， I assign of initial value。

 which is0 if it is end and minus100， if not。Okay， so。

This array is just going to keep track of the distances between successive iterations to see how much progress we're making。

 so now I'm going to start iterating。Okay， so。This one turn of the loop is going to essentially take whatevers and values and turn it into update the values to get new values。

 and I'm going to replace values with new values。Okay， so values remember。

 is supposed to be the value of a policy at a given state。Okay。

 so I go through all the states if it's at the end then。The value is always0， if not。Then I only。

 I consider the。The policy action。 So apply the policy to stay get an action。In this case。

 it's tram here。I'm going to look at all the successors。Of taking action tram in state 1。

And this gives me the two possibilities。And then I'm going to look at this compute cube value。

 which I。You know presented before。 And that's going to give me a new values of state。 Okay。

 so compute Q values considers these two successors。And weights them by the probabilities。

 looks at the rewards， and then also values of the resulting state。So I do this for all the states。

And then， and after I'm done here， I。Compute the distance， the distance is pretty high。

 so I'm not going to break out of this loop。 and now the updated values look like this。

So let's pause a moment and try to understand why the values look like this。 Okay。

 so before they look like this。And now after one step。

 remember which corresponds to following the policy and then just terminating， they look like that。

Okay。So notice that 9 has now updated to -1。So what does that correspond to？嗯。

That corresponds to walking， right， if you're in state9。You can take a walk。Get a reward of minus1。

 cost one， and you end up in state 10， and thats if you're picking up the zero from before。

And notice that five also got updated。So why is it like minus 42？Any ideas。

There's that chance to just keep the training folks straight too。Yeah， so there's， I think it's。

60% chance of。Taking the tram and going to 10。 So that's why you have -2。

 And then there's also a 40% chance that you ended up in the same state。And remember。

 what was the value before it was like minus10 minus100。So it's like minus 100 times。Point4 plus。0。

6 times minus minus2。I think that gives you the right answer。Okay。

So then if I keep on iterating this。You'll see that over time。The values kind of get updated。

And notice that the ones over here are kind of interesting because。

These are the ones where you can only walk。So that means there's no decimal。

 There's no randomness here。 So it's just like， okay， well I'm say 6， I walk and I， you know。

 if I keep on walking， I get a reward of -4 and I end up in the end state。 But these ones。

 they take a bit of time to converge， but eventually， they， they should converge to。

So you see the distance is going down over time。Which means that the values are changing less and less。

 and eventually I get to minus-12。0005。And then at some point， I just， if I get， I just exit out。

After 27 iterations， the distance has fallen below the 10 to the minus5 tolerance。

And so the value of this policy is minus 12。Which means that it costs 12 to go from the start to the end。

 on average。So remember what was an estimate I got from before？It's like -11。

7 or something like that。 So you see the estimate is， you know， somewhat in the ballpark。

 but it's not exactly right。Okay。Maybe pause there， So this is policy evaluation。

Let me just kind of review this one more time， So policy evaluation takes MDP and a policy。

And it starts with some initial values。And then， for each iteration。I'm computing。

Updating the the values。By。Considering。Let's see。 I iterate over all the states。

And consider the action taken。And then do this kind of Q value computation。Okay， actually。

 let me write this down。In math， I think， sometimes it's easier to explain this in math and sometimes it's easier to explain than code。

Value， sorry， policy evaluation will say at。So at a particular。Iteration T。So this is an iteration。

This is the policy。So this is going to be。嗯。This essentially， let me see if I want to just。

Write this down。 Actually， let me just expand this。 So basically， this is I'm going to be equal to。

The summation over。S prime over T S A， O， so。What should I put in for a， I should put in pi of S。

 because I'm looking at the value of a particular policy。嗯。And then this is Rs pi of S S prime。Plus。

 gamma， hopefully， people can still see that。 Let me， let me write it over down here。 Plus。

 gamma of V pi of。T minus-1 of S prime。Okay， so this is what's being computed in， in code here。

And this quantity here is。Q。Of us。Pi S。 and using the notation I had。

 I'm putting in V pi of T -1 here。So why do I just to make things explicit？

We're going to change that。Okay。So if I'm going to see how good is this policy in state S？

I look at essentially the Q value， where the action is just。So this is an action。Under the policy。是牌。

I plug into action here and I do this， which is equivalently this thing。

Any questions about the recurrence here？有。Then what the convergence take like maximum？The number of。

that theが。Allrry， my much is a clear。Yeah， I think the question is like how long does it take to converge。

 So actually this is a good segue into the next thing I'm going to talk about。

 So if you look at the distance，嗯。Over a number of iterations。

 you see that the distance starts at 100 just because I've initialized the policy to be。

 the values should be minus 100， and it doesn't move for a long time and then it starts going down exponentially。

Okay， so the theme that's going on is that there's two phases here。

AndOne is that the first phase where I think this is what you were trying to say is that you're essentially just trying to reach all the states because if a state isn't even reach you can't even reach the end state from a given state。

 then that value of that is going to be essentially minus 100， and once you can reach everything。

 then now you're trying the second phase is you're trying to refine all the values。And that part。

 the distance decreases exponentially。So if you remember back here。

 if we just go and rewind time here。Okay， so if you remember。Here， this is where it started， right？

 And then so look at the -100s。 So if the walking。So if this is still， I can't。

 I don't know how to go from you know， state 1 to state 10 in two steps。 That's impossible， right。

 So this is still like you know，-106。And then eventually， I'm able to figure out how to get there。

 And now things start decreasing kind of exponentially from there。O。So let me go on now。

So we can also play the dice game and run policy evaluation， let's just see what it looks like。

 the code is the same so remember here there's only two states in and out and and is sorry in and end and I'm going to have a value of zero in minus 100 and I'm just going to skip down and try to see what the values look like oops。

嗯。And you see that in。You know， converges to。12。Let me just go here， so it converges to 12。Okay。

 and remember the。The estimate we had was around 12。 It wasn't exactly 12。

 but policy evaluation gives you the exact answer in the limit。All right， so to summarize。

 policy evaluation computes the value of a given policy。And remember。

 the value is defined as the expected utility of doing these rollouts。

 but we don't have to do the rollouts。 We can just use math and write down our recurrence。

The key quantity in writing down the recurrence is the Q value。

Which is the value of taking an action A in state S and then following V in the subsequent state。

And this idea of bootstrapping。Which means that you start with a set of values。

 and then you iterate a recurrence， produce a new set of values。

 and then you take those values and you keep on iterating is a common thing in reinforcement learning algorithms。

Okay。So we've only 10 minutes left in a class， and I still haven't told you how to solve MDP。

You might wonder， okay， Percy's really bad at time management now I'm going to run out of time。

 but actually， that might also be true， but。The valuationu is actually going to be quite similar to policy evaluation。

 So we've actually done most of the work here。 And I've argued that it's only a four character change。

 Actually， Okay， Allied。 It's a little bit， maybe a one line change to。

Policy evaluation to give evaluation it。So policy evaluation says compute the value of a given policy。

And value iteration is going to compute the value of the optimal policy。Okay。

And then the process construct the optimal policy as a side effect。So you might think this is。

 this is pretty hard， right， because think about if you have a function F of x computing it is can be trivial and finding the minimizer is can be you know。

 intractable。So how is it possible that for this problem。

 evaluating a policy and finding optimal policy are actually not that different？

So evaluator Shin goes back to Richard Belman's work on Dmic programming for the '50s。

 and let's look at the- I'll just declare what the recurrence is。So this is a recurrence for。

Policy evaluation， which I have on the board。 And this is the recurrence for evaluationeration。

So notice that the only thing that's different is now I have this max over a。And I have before。

I had a fixed policy， so the actions I chose were just given by the policy。

Now no one's giving me a policy。So I'm just going to take the maximum。

 the best policy or the best action in some sense。 So for every state。

 I'm just going to take the best action。Okay， so all I have to do is implement this recurrence。

 and I， I'm done。Okay， so let's do that。So Flaky Tram MVP。I'm going to get the initial values。

 this part is the same as before， and the key operation is going to be computing the value of a given state。

Okay， so let's do it for state nine。hi is one step of the end state。Okay， so another way to write。

The optimal value V star is just the maximum of action over Qs V star。Okay。

So what I'm going to do is now for every action， I'm going to consider， well。

 how good is that action？And they're going to put in those arrays。 So for every action。I'm going to。

Compute the Q value。Of that action。And now。I'm going to just take the max over all these Q values。

And I'm going to take the AG max to get the action， and then that's it。Okay。

 so just to kind of write this on the the board here。So V star of S。So for value。

 let me write it over here， actually。Okay， so this is。Value iteration。So V star of S。

Is going to be the max over all possible possible actions that are valid in S。

 and this is going to be Q， S A， and then。Ne know Var。Okay so this is a sort of fixed point version。

 if you're writing an iterative algorithm， then this would be like t minus1， and this would be T。

Okay。So like I said， I've done most of the work here because computing the Q values is actually where most of the action is。

 and then either for policy evaluation， you just plug in the policy action or evaluation。

 you just take the max over actions， and that gives you the right answer。Okay。

 so now let's run value iteration。Get the initial values。

 I'm going to have a pi to give record what the best action is given state。

And then I loop over all the states and I。Call this function valuation for state。And you， that's。

 and I check for。Convergence to see if the new values that have computed are close enough to the old values。

 If they are， then I stop。 Otherwise I keep on going。 and you can see。That。The values。

 let me track the values that are computed。 So this is for that flaky tram problem。

 Now I'm computing the optimal policy。嗯。And over time。

 you'll see that the optimal policy will converge to。This。Okay， I guess I didn't update this。

 but you can see the values so the。Optimal policy is actually used -7。3。

Which is better than the the value of。Taking the tram if possible， which is also better than walking。

Okay。So which is， which is to be expected because。We can find a better policy using。

Using value iteration。Okay， and if you look at the convergence for evaluationeration。

 it looks kind of very you know similar to policy evaluation where it's sort of high until it figures out how to even do anything。

 and then it exponentialplanatory decreases。 Okay， so here is the actual policy。

 which is optimal for the flaky train problem。So it is to walk。

Until you get to five and then take the tram or try to take the tram。Okay。So intuitively。

 this makes sense。Because remember the tram is flaky。 So if you try to take the tram early on。

 then you're probably going to waste a lot of time and else also takes two minutes。

Whereas the calculation， it just works out。 so if you're at five。

TheThe best thing to do is to take the tram， to risk it because you get multiple tries to take the tram and there's 0。

6 probability of having you succeed， which saves a lot of time。

So the math kind of works out that this is the optimal thing to do。So in general。

 this should not be necessarily obvious for a given the problem。

 that's why we have these algorithms that can just compute the value for us。Okay。

 any questions about value iteration。Yeah， so the resulting of course is almost。So the question is。

 is the resulting policy always deterministic and the answer for MDPs is yes。

 and the reason is that if you take a max， so the value is just a max over a， right？

You can always obtain the max through some point。Now。

 it's possible that a stochastic policy could reach the same at value if you have two actions that have the same value。

 then you can take any combination of those and that's fine。Turns out that for games next week。

 that's not always the case and randomness does help for games， but for MDPs。

 you're fine with just choosing the deter policy。Okay， so to summarize。

 value iteration computes the value of the optimal policy。

 we take a max over actions compared to the policy evaluation， which just takes the policy action。

And then the same idea of bootstrapping where you can start with initial set of values。

 and then you iterate some recurrence to produce a new set of values and you keep on going until the distance between successive value computations is below some threshold and in your stop。

 that part is。The same。Okay， to summarize this lecture， so Markov decision processes。

 they generalize search problems because actions can now result in a distribution over the next state as opposed to just a single next state。

The solution to MDP cannot be a sequence of actions。

 it has to be a policy that maps each state to a given action。We defined a utility of a policy。

 sorry， if you take an MP and you take a policy and you perform a rollout。

That produces a number called the utility。If you take the expected or average over those utilities。

 then you get the value of that policy， which is determinants like a non random number。

And we saw two algorithms。Policy evaluation， which computes the value of a given policy and valuation。

 which computes the value of the optimal policy， and as we've stated before。

 both algorithms are very， very similar。 So what I recommend is really kind of study the recurrences and understand how they work as opposed to just trying to memorize the algorithms as is。

Okay， so that's all for this lecture next time we're going to do reinforcement learning and talk about how we've confined policies when we don't know the transitions or the rewards or the successor states okay。

 see you next time。

![](img/37872379786be875ac7b771ae9d09d0d_2.png)