# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p09 P9 策略迭代（视角2） -BV1YsZHBZEyM_p9-

Okay。This is where we were last time。 we started talking about a policy iteration and the algorithm。

 you know， unlike value duration， where get a sequence of real value functions。

 So here you get a sequence of policies。 and， and in each iteration。

 which you do is that you evaluate the Q function of the last policy and then just take the greedy policy with respect to it。

And then you get a new policy。And we verify that as a very basic sanity check。

 If you ever arrive at pi star， the optimal policy， you'll never leave leave there， right。

 Because when you evaluate it。This is just Q star， and we know that we never gratify over Q star。

 you get optimal policy， so it would just loop of there forever。😡，Okay。

 then one of the most important properties of policy iteration is this property called monotone policy improvement that says like your policy will never get worse。

 in this iteration， like every iteration until you hit pi star where you can' improve anymore because there's no room for improvement。

 But before you hit pi star， your performance will be just better in every single starting state or like at least not worse。

 and itll be strictly better in at least one of the starting state。Okay。

So this is what we're gonna prove， which kind of like gives you a some intuition for， you know。

 and this provides justification for why polar may be a reasonable or good algorithm to consider。

Okay， so so as usual， this we've already seen this kind of recipe before that whenever we prove like a fundamental theorem about a。

 you know， these like basic algorithms。 typically what we'll do is that we're gonna like first introduce like very useful lemma。

 And then you know， we prove dilemma and then use dilemma to prove this particular theorem。😊。

And that's also going to be the case over here and。

I would say the lemma that I'm going to introduce now is probably。

More important and more useful in like more modern part of our。

 where we consider like a large say space function approximation。

 or even like you might want to consider some fancy like policy gradient type algorithm and so and so forth。

 And thelemma that I'm gonna talk about will still be like useful。 Okay， and you you see。

 like it's a little different than the lemmas that we've seen previously， for example。

 the contraction property。😊，Okay， so what's the， what's the lemma， This， this lemma is called the。

Performance。呃Dence。Or sometimes called PD dilemma。And as usual， like， you know。

 when we state dilemma， usually dilemma is general enough that it's。

 it's very general and not really confined to the particular like， you know， framework of the。

 you know， the algorithm here。 So here， like we have a sequence of policy and so on so forth。

 But for the dilemma， what it says that is just if you have any two policies。

And these policies are mapping from states to either actions that would suffice for our use here。

 But this host generally like it， You can have like stochastic policies。 Okay， you have。

 you have two。You have two。You have two arbitrary policies， pi and pi prime。

And what we're going to show is that。And， and let's say we have some。

 let me think about how I would want to。Dfin this， let， let me show do it in the。 And。

 and for any T 0 in。Data S。 so these 0 is like any initial state distribution。 right。

 So it turns out this this for。 And then what we we can do is that we can define。J派。

As expectation as from D 0， v pi of S。Okay， so I'm just stating it a slightly more general manner that is that that will be useful in later lectures。

 So what is's saying is that， okay， so we know that for any policy pie。

 it' performance depending on the starting state。And if you have different starting state S。

 you have a different expected return， which is V pi of S。😡，Now， in practice， like in many you know。

 problems， especially those episodic problems， there's usually a particular well definedfined initial state or initial state distribution。

 right， for example， if you play a board game， like， you know， if you play go。

 you start with the empty board， if you play chess， you start with you know。

 the the standard configuration of the of the board where the pieces have like fixed positions and in some other cases。

 like you serve from a particular your initial state is randomly generated。

 but it's generated from particular distribution。 So these zero is that distribution。 Okay。

 so we say， okay， if if the initial state is drawn from that distribution。

 then expectation of V P is just the expected return。

 when you generatereasuries where the first state is not fixed， but follows that distribution。😊，Okay。

 does that make sense？😡，Okay， so then we can ask the question， what is。J pi prime minus J pi。Okay。

 so what we're interested in is to rewrite the。 this is the performance difference we have two different policies。

 We have a well defined initial state distribution。 And we want to know how， how different they are。

😊，Okay， does that make sense？So the lemma says that this can be written as the following。😡。

This is one over woman is gamma。😡，Expectation。As prime。Or maybe to avoid confusion。

 Let me maybe use S tu over here。 S tutor drawn from D P prime。 And。

 I would define this like in a bit。And a pi S prime。As tutor。Okay， so we see like a2。

Notations that requires definition。 Or， first of all， you have this notation。

 And we have seen something similar to this before， right。

 So when we talk about solving for Belman stopping for Belma equation for policy evaluation。

 we say that there's a matrix solution。 That is you know。

 V pi equals I minus gamma P pi inverse R pi right。

 and we say that this particular matrix has this interpretation。

 that each row is the discounted occupancy。it's like you。You， you start from some starting state。

 which correspond to the row index and you just roll out trajectories according to policy pi。

And then at each time step， you have a marginal distribution over states and you combine them into into a mixture distribution。

 which accounts for the discounted sum of distributions you will hit at every time step。Okay。

 so D P prime is pretty much precisely that。 So one way。

 there are multiple ways of writing D P prime。嗯。So。Oh， how do I， How do I do this。Okay。

 so one way to write the high prime is that this is just a。The0 transpose I minus gamma P pi。

 heres prime。 So I have prime this。Okay， so it's， it's like， so for each， for each starting state。

 you have this discounted occupancy。 And we have a well defined initial state distribution over here。

 And then we just you know， combine those， those， those those discounted occupancy distributions。

 And that is the pipe prime。 So， or alternatively， you can also write it in a， form that is。😊，你呃。

Alternatively， you can also define it as a D pi prime of S tda is equal to。嗯。Let me see1 minus gamma。

 This is a normalization factor， summation。He equals 0 to infinity。😊，Gue I'm。

Probably should do one gamma T -1。Comma t minus1 probability。Of。S。T equals s tta， given that。

S1 is drawn from D 0， and。The distribution， we take actions according to policy by。Right。

 so if you remember， like when we， when， when we let S1 to be a particular starting state。

 S1 equals S， this definition is。Let me see this particular definition is literally the did like a。

 a particular role in this matrix。 right， So that's the discounted arguments in that we have introduced。

 So here is just a slide generalization when you， instead of drawing as letting S1 to be a fixed date。

 you， you draw it from starting state distribution。😊，Okay。So， and then we have another quantity here。

 which is a pi。 What is a pi。 Well A pi is defined as。As tutor。A is defined as。Q。Q pi of Sqda。

Let me see which direction。呃。Right， a minus v pi of S。Okay。

 so this quantity is called the advantage function。I mean， for now。

 like it's not really like that much significant significant。

 like you could just state thelemma without introducing this new concept and just put this this whole like equation over there。

Okay。And then remember， like whenever you see like a pi prime that appear。

 like a policy that appears in the place of an action， what it means is that you should like。

 evaluate like pi prime on Stda， which is the stay in front of it and replace that with the。

 you know， corresponding action。Okay， so this is the this is the lemma and the quantities defining it。

 and well prove in in a bit。 But what we can do is that we can first look at the lemma and immediately get。

😊。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_1.png)

呃。Like if the s holds， the first in quality immediately holds。😡，Okay， so we can we can look at why。

 So， so the， what we're gonna do is that we're gonna just let。This pipe prime to be。Pi K plus one。

And thisBB pK。O。So because it says， I want to show that for every starting state or maybe Pi K and P K -1。

 that's not too much different。Okay， we want to show that for every starting state。

 Pi K is better than Pi K -1。So， you know， equivalently。

 I can show that under any initial state distribution。

 the expected return of Pi K is better than pi K minus-1， right。

 So it's the same thing because I can just let these initial state distribution to be point mass on every single state。

 Then I'll just get what I need。So if I can show that this difference is always not negative。

 I'm done。Correct。Okay， now you look at on the right hand side and see what you get， right。

 What you get is one womans gamma。 Okay， if I want to just need to talk about the negativity or positivity of this quantity。

 I can ignore this。😊，I have expectation， well it turns out that just to show that policy improvement。

 you also don't need to look at。Really care about what's the distribution number here。

 So what we're going to show is that this quantity， which is the advantage， is always non negative。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_3.png)

Okay， so why， well， look at this definition。Its definition is Q pi of S or S2ta A minus v pi of s tuta。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_5.png)

Okay， and what is Q pi and what is pi over here， pi over here is pi K -1。 right。

 So we're letting pi to be the previous policy。 So that will define the policy over here。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_7.png)

Okay， but then like we're not really just doing S tuta A for， for arbitrary A。 We're。

 we're looking at the advantage for S tuta and action taken according to pi prime。 So here。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_9.png)

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_10.png)

This action is pi prime， which in our case is pi K。Okay。So now I claim that。😡。

Like this quantity can never be negative。😡，Why is that the case？



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_12.png)

So it would be helpful to zoom out a little bit， and to。To recall the， recall the algorithm。Okay。

 so what do we do in the algorithm。 What we do in the algorithm is that every iteration。

 when we get pi K -1， we get Q pi K -1 and then take action greedy like with respect to it。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_14.png)

So therefore。WhatWhat's the action that PK will take？Yeah， the action that Pi K takes。

 according to the definition of the algorithm， is whatever action that maximizes Q pi K minus1。😡。

Okay， so now why is that greater than equal to v pi of s。V， can you like， okay。

 So the claim is that So here the first term is in is in the form of cube pi of S。 Then your。

 your action is the best action for Q pi。Okay， so if your second term can be also be written as Q pi of S tuta some other action。

 then that certainly will have lower value or at least no more value than this one。 right。

 Can you write the second term also in the same format， That is a Q pi of S tuta for some action。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_16.png)

How， how can we rewrite this。I mean， we have a shorthand。 We， you don't。

 You shouldn't need expectation。 I'm looking for some answer。 that is very short。It's not arc max。

 There's no arc max in the second term。不会。Exactly， right。 So remember， like V pi is just。

 you take actions always according to pi。Cupie is first action。 You tell me what you want。😡。

All the remaining actions I take according to Pi。Therefore。

 V pi and Qpi would be the same if I I look at Qpi。

 but I also require you your first action is also according to to pi。😡。

Then this NV pi is the same thing。😡，Okay， so therefore。

 what we have over here is Q pi of S2 as something， minus Q pi of S2 as something。😡。

But the first action you take has already maximized the cubepi。😡。

So there's no way that this difference is negative。😡，Good， does that make sense？

So once you have the performance different dilemma。😡。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_18.png)

The， the， the first condition of， sorry， the first statement of monetary policy improvement will immediately follow。

Now， in the interest of time， I probably won't cover the the second one。 And if you're interested。

 you can， you can take that as a， as a homework。 It also follows from the same。

 You can also you know， obtain that from the performance difference level。😊。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_20.png)

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_21.png)

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_22.png)

Okay， so。Then what we need to do。😡。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_24.png)

Is to prove it。O。Move this。Okay， so the proof。Okay， so this is a pictorial proof。Okay， now， remember。

 like what we， what we just said is what we just did is that we show that if you have performance differentlemma。

 we can immediately show monoone policy improvement。😊。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_26.png)

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_27.png)

But now we're now zooming in to prove like the performance difference myself。😡，And remember。

 for this lelemma， this is general。 We're out of the framework of policy equation。 There's no pi K。

 P K minus1 or whatever， right， You just give me an arbitrary to， like two arbitrary policies。

 pi prime and pi。Okay， we just want to show that this equation holds。😡，Okay。

 and here's what we're going to do。 What we're gonna to do is that we're gonna to construct a sequence of infinitely infinite number of policies。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_29.png)

That。That like， essentially bridges between。Like pi and pipe prime。Okay， and notes that here。

 like I also have pi 1， pi 2 pi 3 and so on so forth。 But these pi， you know。

 with with the subscript number has nothing to do with the pi case in policy， right。

 because now we're like proving this very generic lemma that by itself doesn't can be applied anywhere。

 It doesn't have to be applied to policy。 So these pis don't you know， don't mistake them as the。

 the policies you get in policy。 These these policies are merely constructions for proving thislemma alone。

Okay， does that make sense？Okay， so， and as you can see， here is what I'm doing， right。

 So I'm imagining like S1。 like， so here is just illustration of what kind of trajectory like each vertical chain is a graphical representation of a distribution of a trajectories。

 okay， so your S1 is always drawn from the initial state distribution at the0 that I'm， you know。

 that I'm telling you。 And then。😊，Like someone reminds me。

 how do you specify a what elements specify the distribution of trajecties。You need two things。

Initial state or initial state distribution。 That's one thing I just said， what's the second thing。

Policy， right， You need to tell me how you are gonna take actions。 once you have these two things。

 Were done。 right， So， so here I'm， so here like what kind of policy you take at each time step。

 I'm representing that by， you know， arrows of different colors。 If you take actions。

 according to policy pi， I use black color， if I take action according to pi prime， I use red color。

 Okay， so therefore， if I have infinitely many blacks。 Well。

 this is just the distribution of trejectciies。 According to policy pi。Right。

And if I take the expected reward， you know， expected sum of rewards along this trajectoryary distribution and take rotation。

 that's just J pi。 right， the performance of policy pi。 similarly， if I have all the reds。

 which is like all the red actions， which is pi prime， Well， this， this give me。嗯。You know。

 this is just J high。 This is just J high prime。Right。And I care about expressing their difference。😡。

And what I'm doing here is I'm， I'm creating all these like intermediate policies such that when I express the difference between these two。

 I can always express that as the difference between these two， these two， these two。

 these two all the way to to， to the right， right。So I use like these like intermediate policies to bridge between them。

Okay， so how do I construct these intermediate policies， Well， we actually construct them as。

 as what we call like non stationary or timing homogeneous policies， where， for example。

 pi 1 is the policy that the first action I take according to pi prime， the red action。

 but all the future I take according to pi。Okay， then pie 2 is first two actions red all the remaining。

 all the way to the future， black and so on and so forth。Okay， as you can imagine。

 like what's happening here is that every pair of adjacent trajectoryory distributions。

 they only differ by one action at some particular times then。😡，Or one one policy， you know。

 there is only one time step where their policy mapping differs。In all the other time steps。

 the way that they take action according to states are exactly the same。😡，Okay， make sense。

So now let's， let's， let's calculate this more formal， right， So we have a。So according to this。

 we have J pi minus J pi prime。 You know， according to my convention over here。

 I can also say pi 0 is just pi because like the subscript here is essentially how many red actions do you take at the beginning before you switch to black actions all the way to infinity。

Right so pi can also be called pi0， and pi prime can also be called pi infinity。Okay。

 so this is just pi 0 minus。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_31.png)

Actually， I think Im， I want the other way around。 So it's pi infinity。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_33.png)

Mus pi 0。Right。😊，Then what I can have is this is summation。As I said。

 I constructed these like intermediate policies， and I break the difference into like difference。

 like the， the， the sum of all the differences of adjacent pairs。 So I have I equals。0 to infinity。

J pi I plus1 minus J pi I。Correct。Right。Okay， now。We just need to express this， right。

 So let's zoom into an arbitrary pair and look at what we can say about them。Okay。

 so let's say this pair。So what we can do is that we can look at the reverse they are playing at each time step。

 And if they're the same， we can ignore them and we can start looking， know， okay。

 so for the first time step， is there a difference。

There's no difference because you start from the same initial state distribution。

 You take the same action。 Well， they expect reward， of course， it's the same。Right， so therefore。

 when you take the difference， they just completely cancel out。Similarly， for the second action。

 they also cancel out。Correct。Okay， but here's the thing。😡，The difference starts to emerge over here。

 Right， So here as at S 3。Like the other thing about taking the same actions before time step 3 is that when you look at S 3。

 in both cases， you arrive at the same state distributions at S 3。Right。

 because you start from the same initial state distribution。

 and if you've been taking the same policy so far。😡，O。But now there is a difference。

 I take black action， you take a red action。😡，I guess you get different rewards。Okay。

So here's the question for you， okay， so afterwards， both of us will take， you know。

 we become the same again， like both of us will take black actions all the way to infinity。😡，Right。

So let me ask you， are the rewards I'm going to get afterwards the same？😡，Why not。Right。

 because remember， this is Rl。 right， The whole point of R L is that your actions have。

Not only have impact on what immediate reward you get， but it also have long term consequences。

That you actually go to different state distributions。Okay， so the。

 like because of the single difference， the distribution over S4 over here is going to be different from the distribution over S4 over here。

😡，And although you're going to take always the same actions as afterwards。

Like just because the state distribution is different。

 the expected rewards you get afterwards are not going to be like the same in general。😡，Okay。

 but still， like we want to。We want to have a way to express this long term difference in a concise manner。

😡，Okay， what can we do？So note that there is a commonality that in both cases， after this difference。

 all the future reactions are according to the black policy， the pie in both cases。😡。

What quantity can you use to express the expected reward you obtain when you always take actions according to some policy pie。

Value function， yeah。But not necessarily J， right， So I'll just give the answer and then you see like。

 whether that makes sense。Sation I equals 0 to infinity。 Okay， now I'm looking at this particular I。

 So the claim is that this is equal to。😊，Let's say I'm doing the right hand first。 let me see。

Might be a different sign anyway， I'm going to do this。Okay， so this is。嗯。Q。Pi。嗯。As tutor。Let。

 let me write in this way。 Okay， so S。S 3。Pi prime。Minus Q pi of S 3。Okay。

 or like this is just a v by。Okay， so this， this is not quite this yet because I still need to take care of the distribution over S S3。

 among other things。 But let's say you're at S 3。 And you want to express the difference of long termm rewards you obtain afterwards where in this particular case。

 you only differ by the first action， But afterwards， both of you take action according to policy。

What's the difference， the difference is this。😡，Right， because you have V pie。

 which correspond to the， the left chain where starting from S 3。

 youre taking action according to pi。 and it's always pi。 right， So you have V pi of S 3。

On the right， the first action is according to pi prime， but all the future occurring into policy pi。

 So it's Q pi of S 3 pi prime。Does that make sense？Okay， so now。There is actually a slight。

 This is not exactly what what we should be getting。 So okay， what you can， what we can do is that。

So here is also， so， first of all。Whenever you you invoke the notion of value functions and you say S 3。

 this is treating that S3 as if this is the first time step。Right。

But S3 is not really the first time step。There's already a few time steps before， right。

 Not only the rewards before that have canceled out， but the discount factor has also accumulated。

Right， when you look at the difference between these two things， their difference will actually like。

 should be discounted by like。You know， actually， so here I said S 3。 But really， because this。

 I'm considering the general case， this is S I minus plus。1， and okay。

 so I have a gamma to the eye here。 I think， yeah。Right。

Because because eventually we're calculating the difference between the the returns from the perspective of the real initial state。

Right now we're treating this as like a fake initial state。 But this because before that。

 everything is the same and they cancel out。 But there is implicitly already some discounting that is has accumulated that we need to account for。

😡，So there's the actual gamma of the eye over here。😡，Makes sense。Like， like， you can imagine。

 like when you go to the the right most side， like almost all the infinitely many actions in the beginning are the same。

 and things only start to differ after infinite many steps。

And that difference will contribute basically nothing to the difference value。

 difference in value in the initial state， right， So that correspond to a case where I actually goes to infinity and this difference is gonna be like。

 you know， like discounted towards 0。O， now。However， this is not quite there yet because S3。

 which in the general case is S plus 1 over here， this is a random variable。😡。

We do need to take expectation。😡，But as we said， because all the actions before it is the same。😡。

So the distribution over S3 is the same for both cases。

 So I can actually just write a single expectation for them。

 and the claim is that I can just write it as。😡，Pi prime， okay， maybe I can say。

As one from some initial distribution easier。Okay。So why is that case？ Well。

 this notation is saying that I'm imagining a distribution virtual directorreies where I take the initial state is drawn from D0 and all the actions are taken according to pi prime。

😡，Which， by the way， is not what's happening in thesetertories。Okay， but this still works， right。

 because here the only random variable is Si plus1。😡，And the distribution of S I plus one。

 which is S 3 over here in these two like trajectory distributions。

 actually coincide with what's gonna to happen when you take all the actions according to pi。Right。

Because because you only look at the distribution of S3 over here。

 you don't care about what happens afterwards。😡，Whatever action you take afterwards。

 whether it's black， red or always red， always black， It doesn't matter。

 The distribution is the same。 It's this distribution。Okay。Makes sense。Okay， so what is this， Well。

 this is just。This is just what。 This is A pie S I plus one pipe prime。Again， like for now。

 this is just the appreation。 it doesn't really mean anything。Okay， so that's the first thing。

 And then we can write it this way。 I equals 0 infinity。 Okay。

 so now I'm gonna just write the expectation as like sort of a sum， as a sum。 Okay。

 so I can sum over S。😊，As tutor。Where。So here I'm just looking at what's the marginal distribution of S plus one。

 right， So this is just the probability under policy pi prime。嗯。S I plus 1 is equal to S tta。

 given that S1 is drawn from D 0。TimeThen， then this is just the probability of， you know。

 whatever is over there， right times。Q pi of S tuda。Sorry， pi prime。Minus v pi of S。Okay。

 I'm doing nothing but just write the expectation as the summation of the probability of each possible realization times the function。

 you know， for that， you know， realization of S M plus one equals S。😊，O。Now， here is something nice。

 So before that， I still have this infinite zone。Right， I still have this infinite sum。

 and this infinite sum， But in this infinite sum。This part is the same across all I。

 it has no dependence on eye。😡，Ohright。 So I forgot that。 Yeah， yeah， yeah， you're right。

 So let's put it over here， gamma I。Okay。So therefore， what I can do is simply to do this。😡，Right。

Because previously， iss summation over here and everything here， right， But everything here。

 you have a term that is independent of I。 So you can actually， you know， you know， push that out of。

This， this summation。So what I did what I okay， So， and because I already introduced this。

Notation of advantage。I can just call it a。Pi of S tuor。pipe prime。Okay。Now， what is this。Well。

 if you look at what I said earlier。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_35.png)

This is just the definition of D P， D P fry。😡。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_37.png)

Okay， so then this is。One over woman is gamma up to the like， there's a normalization factor。

1 my one minus gamma here to make sure that D pipe prime defined in this way is a。

 is a distribution that all the probabilitybaities sum up to one。

 So this is one of woman as gamma the。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_39.png)

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_40.png)

Pi prime。啊，sorry。Subation as， as tutor。D派 prime of。SQ的。Api s tuda。Okay。And well。

 because the pi prime of stda is a distribution， you can also write it as an expectation。

 which is what we get。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_42.png)

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_43.png)

On the right hand side over here。Okay。Clear out some of the。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_45.png)

O， so。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_47.png)

So like this is， so you know， I， the way I myself remember this slemma and also prove it is actually by this visualization。

 right， So you can actually look at this visualization and kind of like intuitively make sense of what's happening in the slemma。

 right， So one thing you should really notice， you know， take， take notice is that in the slemma。😊。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_49.png)

You have on the right hand side， you have a lot of policies， right， Sometimes it is pipe prime。

 sometimes it is pie。But there are two different things。So here is a， Here is a policy。 iss pi prime。

Here's another policy。 and it is pie， right， And these are actually， you know。

 the two different policies you start with on the left hand side。Okay， and there's a， so like。

 you know， sometimes like when you don't， don't actually remember the， you know。

 these specific form of of dilemma and you try to write it down。 You may make a mistake that。

 you know， maybe you have D pi prime and then you have a pi prime。

Because there are actually three occurrences of the policy on the right hand side。😡。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_51.png)

But if you actually remember this diagram。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_53.png)

You should never make the mistake。 Like the pi prime over here and the pi， the policy over there。

 like the policy on the discarded occupancy and the policy on the superscript of the advantage function。

 they should never be the same。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_55.png)

Because if you， if you look at how this， how this how this proof works。Essentially。

 what happens is that。We're joining a diagonal line over here。😡，Right。

 so everything above the diagonal line， things are the same across， you know。

 for any pair of adjacent policies。RightAt the beginning， both policies take the same actions。Right。

So those part don't really generate any reward difference。

The only effect of those part is they actually roll in into some particular state distribution。

 And that difference is only happening afterwards。RightBut how are which policy dictates the distribution you arrive at on that diagonal line？

😡，Which policy？Well， I'm asking you， like， so for the distribution of the states that that lie on this diagonal line that separates the red arrows and black arrows。

 which policy determines the distribution over those states。Te prime， the red posy， right。

 because the upper triular triangle is all red。And which term？😡。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_57.png)

In the slemma， reflects the distribution of those。States。In the lelema， on the right hand side。

 which， which quantity curve describes that distribution， those distribution or their their。

 theyre like mixture。低派拍。Exactly， right。 So D pipe prime that policy correspond to the upper triangle。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_59.png)

Now， after like once you arrive， sorry， once you arrive at that， you know。

 those states on the triangle， you now should account for the difference in reverse that happens afterwards。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_61.png)

Right， but whenever you look at a pair of adjacent policies。

 all the future are according to policy pie， and they only differ by， you know， one single action。

 So then we get this notion of advantage。 But the superscript of the advantage function。

 is the same as the superscript of these value functions， which is determined by all those future。

 you know how you take those future actions， which policy determine that。It's pi。

 this is the black policy pie。😡，Right， so basically， the proof goes like you have the diagram。

 You draw the cycle online where the upper triangle determines the say distribution。

 The lower triangle determines like， you know， which policy do you use to define the Q function。

So therefore， the Q function is superscript and the， you know。

 discounted occupancy is superscript can never be the same。 They are always different。快ion。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_63.png)

快一点去。来判审。Oh， yeah， yeah。 I， I I， I did it wrong。 Yeah， it should be the same。Okay。So。Now。

 question here for you。 So if you look at the left hand side。

We just started with two arbitrary policies， right， pi prime pi。Like they can be really anything。

 So they are on equal footing。 And the whole thing should be symmetric with respect to them。

But somehow， on the right hand side， the symmetry is broken。 One determines the。

Distribution of states or what we call the row in distribution。 Like， you know， how。

 like what kind of distribution you arrive at when you start from the starting stage distribution and take certain policies。

 like then the， the， the distribution you arrive at at an intermediate time step。

 sometimes like informally， youll call that row in distribution。

And the other one determines this rollout value。😡，Right， the state distribution。

 row distribution and raw value， there are different things。 How is symmetry broken。😡。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_65.png)

Like where in this proof did I break the symmetry？😡，Yeah， I think you are getting it。

 So here's another way， right， because because because this， this。

 this theory is completely generic and it applies to any pair of policies。

 I could just swap the order of pi and pi prime， right。

 which means that I should be able to use pi to define the discounted occupancy。

 but use pi prime to define the advantage or or the rollout value。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_67.png)

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_68.png)

But if I were to do that， am my prove， what should I do？😡，What they're okay。Direion of a。Yes。

 change the direction of diagonal。 Right， So what you should do is that you should define the diagonal in this way。

 right， So previously， this is like one red all black，2 red or black and all the so on so forth。

 What should do is that you should serve from the right hand side。 And then you do one black all red。

2 blacks all red，3 blacks all red， and so on so forth。Right。

 if you do it in that way and you follow this proof， you exactly get， you know， the you you。

 you can exactly swap the rows of pi random and pi。Okay。

 which means that this the dilemma is still like， you know。

 completely symmetric with respect to the both policies。O。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_70.png)

So this is one of the。😡，Like， if you look at this， this lemma。

 like it's super useful because unlike the lemmas we've seen before， right， So we， we。

 we've seen this analysis， like， for example， you have contraction and then contraction tells you convergence。

 right， But those results， they actually all depend on these infinite norms， which are like。

 you know， in some sense， like can be very loose， right， And。

 and all the results we get our inequalities， you know， which。

 which can be loose and you can they they may not be tight。 But this result， particular。

 is a identity。😊，We're not like， you know， you also have wonderful Wo in Gama。

 which makes it look kind of like what we have before。 But here you're not losing anything。

 It's just a literal translation。The other thing why this is very significant is that which is related to like。

 you know， being identity versus being inequality that relax the things using infinite norm。

 So you see infinite norm a lot in table analysis because infinite norm basically sweeps under the rug the issue of distributions。

😊，You don't need to care about distributions anymore because whatever， whatever like， you know。

 you take expectation over something。 Well， you can always relax that to the even norm of something。

😡，But here， because we have identity， you can't do that。

 which forces you to be actually sensitive to what kind of distributions you are looking at。😡。

RightAnd turns out that when we look at you know， more challenging scenarios where you have large state spaces。

 function approximation and so on so forth， these identities become way more useful。

 like those like infinite norm based results， basically will become completely useless in those settings。

 but what we need is the like these identity versions or variant of those results or generalizations of those results that that that actually properly account for what kind of distributions were over states we're looking at。

😊，Okay。😊，Okay， so。As a bonus。This， this smma。Actually， it becomes immediately useful。

To for a open problem we left in a previous lecture。Let meCopy over here。Copy over here。

 So this is the。This is the lemma。And， well， for our understanding。

 let's just write out the definition of。Advantage as tota pi prime minus。嗯。V pi of attitudet。Okay。

 we have one less thing to remember。 Okay， so， so this is the PD D Lama。If you remember。

 like there's this lemo about value that I only give you， but I didnt improve。😊，For any F。

 that is RA。We have。V star minus v pi F。Infin norm is upper bounded by f minus Q star。

If you're in norm， one minus is gone 2。Okay， so remember， what was the contact context of that。

 right？ So the， the context was that we know that in valuation， we get a sequence of functions。

 Eventually， it approaches Q star。😊，But in reality， we only have finite computes。

 So we stop at some time at some point where we get an F that is like really close to Q star。

 but it's not there yet。But still， we pretend that is Q star and just extract the greedity policy out of it and hoping that it'll be good。

And with the slema tells you that indeed it will be good up to some additional multiplicative factors。

😡，Like how good this policy is compared to the optimal policy is controlled by how close your function F is to like Q star。

Okay， I told you to this result to justify why you can stop prematurely and still just get a good policy out of it。

 but I did improve it。😡，Okay， well， it turns out that now we can just prove it directly using the performance different La。

😡，Okay， so what we can do is that we can just say J pi star minus J pi F。Right， we have bound this。

 This is just a V star minus v pi F for some initial state distribution。

 And if this is always bounded regardless of the initial state distribution。

 that's just the same as the left hand side。Okay。So now what we do。Equals。

 so now we're gonna apply the performance difference Lamma。But it turns out， but remember。

 whenever you apply the performance different， you need to choose one of them to be to define a row in distribution and the other one to define a roll out policy。

😡，Okay， and the correct way to， you know， choose that depend on the particular problem。 So。

 I'll let you make a guess。 which one do you use to define the role in and which one do you use to define the roll out。

😡，So you have two policies over here。 pi star， which correspond to this pi F。

 which is whatever policy we extract from this function now。You should look at the right hand side。

 which will give you a hint for which one to。We're trying to choose to for， for for which。

Pi F has a O A and pi s has a around y。I just simply。Yeah， yeah。 how how did you match it？So pay。

Well， no， no， no。 if you， if you do the， if， if， if you， if you look at this and match over there。

 pi prime is row。 Okay， no， no， then pi then pi star is rolling。 then pi F is roll out。

I actually married。I'm looking for a very simple answer。 Like。

 you should look at the result you're trying to prove。 And on the right hand side。

 there's a single quantity that tells you which one， you know how， how should you pick things。Yes。

 you have Q star， right， Q star is what is Q what policy。😡，Yeah， Q star is Q pi star。😡，Right。

 so that already tells you that if you want Q star to appear on the right hand side。

 you want Q pi to be Q star。 So that pi needs to be pi star。😡，Right， so actually。

 the match is wrong over here。 Like if you mechanically apply the， the match over there。

 which we actually， we， we， we actually break that symmetry like really arbitrarily， right。

 So actually， you get the wrong。 you get the wrong way to decompose things。

 right So you actually need to choose。😊，So what you get is one over one is gamma expectation as tutor sampled from the pi F。

 So you get the learned policies。 Sorry， the， the， the， the policy you get。

 and that's gonna define the row in distribution， the discounted occupancy。

And then you get Q star of stda。 So here is， actually。

You also need to swap like I'm not going to detail here。

 but you also need to swap the order between Q pi and V pi， right。

 because you're essentially flipping， like taking a negative sign on the left hand side。

So you actually have V star minus。This minus Q star S to the pi F。Okay， and this also makes sense。

 right， because pi star is always better than pi F。

 So here V star is always better than Q star of something else。 So this is non negative。

 This is non negative。 Otherwise it doesn't make sense。😡，Right。Okay， now because we。

 we only need a infinite normal result。 So that expectation can already be gone。 right。

 We have one over Roman sma。嗯。We can just do max over as tilta。嗯。

V star as S tta minus Q star of s tta pis sub F。Okay。

So now we already see one of a women schema that appears， right。

 that is what we need on the right hand side。嗯。We already get Q star to appear， right。

 Like Q star appearss of there。 We have Q star。 V star is also basically Q star。😡。

So what's on the right hand side that has not appeared yet。F， right， And that's the key thing。

 Like all we have control over is how close F is to Q star。

 But F so far only appears as this policy pi of F。Like the numerical real valued function F doesn't has an appeared。

Okay， so what do we do while you just。You subtract。嗯。So actually， let me take it a little。

Write it a little more。This is a。V star is just Q star as tilde pi star。

RightAnd what we're going to do is that we're going to add a subtract。F。是。We subtract F S tutor。

P star。嗯。Plus， F S tude pi F。 Okay， I'm gonna skip step because like usually what you do is that you subtract and add the same thing。

 right， then that will be equality。 But now like I'm doing a relaxation。 I'm subtracting one thing。

 but adding another thing。 But I claim that this thing is like the。

 the thing I added the the pair I added here is is not negative。 Why is that。

Pi F is what P F is the taking greedy action， according to F。😡，RightSo therefore。

 when you both have the form of F， the same state， something。

 pi F is always truth in the action that maximizes any expression of this format。😡。

So that's going to be bigger than this one。😡，Right， so the， the。

 the difference we're adding over here is not negative。 So why do I introduce that difference。

How should I proceed from here？Sa someone saying。Triangle。I guess so。 Or， well。

 or what I'm having here is that I have， I'm having four different terms。 I'm gonna now combine them。

 How should I combine them。Sorry， by policy or really like you what you want to like again。

 always remember what you have on the right hand side that you want to prove， right。

 On the right hand side， we want to prove is that we want to compare F versus Q star。

On the same states， on the same ashes。 exactly。 That's why you need it。 right。

 So here is exactly what we have， right， So we have this pair。

 which is the difference between  Q star and F on exactly the same state action pair。

 We have the other pair。 again， this difference between  Q star and F on on also exactly the same state action pairs。

Right， so what we get， well， this is just less than or equal to。One of Roman is Gamma。

This is just the two times F minus Q star infinitefin。O。Now。

 what's happening over here in this particular step is actually a very crucial sort like a very basic step that you will see again。

 again in the rest ofproofs， right， So essentially so。What， what this proof did is that。

 first of all， it breaks down the long term value difference， right， So J pi star and J pi F。

 you like， you know， if you imagine like what happens when you have the when you have the these trajectories like we are comparing the trajectories where you take actions always according to pi star。

 in the other case， you take actions according， always according to pi F， right， So in both cases。

 you have many different actions， But what's nice about performance differencelemma is that now it's breaking down into just like one single difference。

 So here you have  Q star of S tta pi star， you have  Q star S tta， but pi F。

So here you have like infinite many different actions。

 But here there's only one single different action。 So essentially。

 it breaks down this long term like effects， cumulative effects into something that is just one step。

 that is myop。Okay， so after that。😊，We leverage the fact that pi S is extracted from F， right？

 And if you look at this expression， at least in the simplified case， if F is exactly Q star。

What's this term？Its 0， right， because pi Q star is just pi star。 So you are exactly optimal。

 So that gave us some some hope that if F is sufficiently close to Q star。

 then the greedy action you take over here shouldn't be too。

 too far worse off compared to the actual optimal action pi star。

But you need to somehow reflect that in proof。😡，Right， so how do we do it。

 Well we add and subtract the F， which is like， you know， how we actually evaluate these actions。

 like Q star over here is kind of like the real value for those actions。 right。

 We subtract and add our own evaluation and use the fact that our the action we take is greety with respect to our own evaluation。

 And then we get these pairs of differences。Okay。So， you know。

 if you look at how we win from here to to here， we start from like， you know。

 true evaluation  Q star， but different actions。 But then， you know。

 upper bounded with difference between the true evaluation Q star， our like， you know。

 approximate evaluation F。 But for the same state action pair。So there's a。There's a general sort of。

There's an abstract form of this of this particular step that is actually appearing as homework one in the first question in homework one in。

 and we actually see it more see it see it quite a few times in the upcoming lectures。

 actually just next week。Okay。So。So coming back to where we are， right。

 So what we did is that we want to prove policy improvement。

 Montone policy improvement for policy relation to do that。

 we introduced performance different dilemma， which immediately implies monotone policy improvement。

 Then we prove the dilemma。 and then also show that it also help us prove a result that we stated clearly previously。

 but didn't improve right that， you know， what happens。

 So basically performance different lemma helps you you know。

 help you with things whenever you have like， you know， the difference of returns between policies。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_72.png)

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_73.png)

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_74.png)

Okay。Now， coming back to。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_76.png)

Polic duration， right？ So as I mentioned at the end of last lecture， if all you have is this result。

What we know is that the sequence of policy you get can never go back to itself before you hit pi star。

Right， and that gives this pretty weird conversion guarantee that says if you have a finite state。

 finite action MP， then when you run policy situation， because of this non loop behavior。

 eventually it will converge exactly to a pi star。Unlike valuation， in。

 you can totally just infinitely approximate Q star， but never exactly hit that。Okay， however。

 how many iterations do I need in the worst case in order to be guaranteed to hit pi star。

Does anyone remember？A in the power of S， right， Because all all we know so far is that every time we get a new policy。

 the policy is different from everything before。Right，So like only based on this information。

 the only thing we can say is that， yes， eventually we we'll guarantee to hit pi star if we have exhausted the entire space of markov deterministic policies。

😡，But how many policies are there in the form of mapping stays two actions？😡。

Now there's number of actions to the power of number of states。Which has an enormous number。😡，Okay。

So， so therefore， like you really shouldn't count on this particular result to give you convergence for policy duration。

 although this is the most well known property of policy revision question。Yeah。

 I have I didn't improve string improvement like I just stated as given and if you' cure is， I can。

Like， I， I think there's a sketch in the， in the notes that you can take a look， okay。So basically。

 this result is kind of like， you know， from a practical point of view， iss kind of vacuous。

 basically useless。 And， and there forers， and if this is all you know， you may get the。

 you may get the。Kind of impression that valuationeration is much better than policy duration。

 because valuation actually converge much， much faster， although it never converges exactly。

 But like who needs an exact solution， All we need is like a good enough。 something that is。

 you know， a very high accuracy approximation of Q star and get a near optimal solution。

 But within a very few number of iterations rather than you know， wait onto infinity， when when when。

 when you can find the optimal policy in pi star。😊，Now， as it turns out that that。

 that statement about the difference between the two algorithms is wrong。

 So policy de also have a geometric convergence。That is much less known in the community。Okay。

And I think the rest of the time， I would just state and prove that result。

So what this says is I have Q star minus Q pi K plus1 infinite norm in less than gamma。

Q star minus Q pi K。Okay， so， you know， as I mentioned， like in policy version。

 you get a sequence sequence of policies， You can't really measure things in the policy space。

 So you have to measure things in the value space。 So what you do is that you just ask。

 you just do policy evaluation， right， Q pi K plus one and Q pi K are just how good these policies are when you evaluate them And Q star is the。

 the， the optimal Q function。And what this theorem says is that， well。

 the difference between Q pi K and Q star also shrink exponentially， very similar to value duration。

Okay， now this result is a show in the form of Q， but apparently what we really want。😡，Is a bound。

 And you can like if this holds， you can immediately show this is like， you know。

 gamma to the K times initial， right， So it's a similar bound to the value contraction based the convergence that we've seen before。

However， like what we really want is this one， right， we really want is V star minus v pi K。

 You know， how that shrinks。You know， as gama to the gay。

I I want to give you that and just leave that as， as an exercise if， if you're interested in。

And doing that。Okay， so what I would do is to do this proof for you。In the remaining 10 minutes。

And what you see is that， okay， so as you can see when I， whenever I so far。

 whenever I do approve for you， I basically don't need to look at the notes because I've internalized all the proofs。

 and I have sometimes like in case of performance difference lemma， I have this like visual。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_78.png)

You know， visual understanding of it that all these like feel very intuitive to me and and so I can just confidently like give you the proof。

😡。

![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_80.png)

So so far， this one is the only exception。You'll see that this result is proved based on some very obscure manipulation of。

The Bel operators that I myself can't do without looking at the notes。Okay， so therefore。

 if after you seeing the proof， you say， oh， I don't。 this proof makes no sense。 Like。

 I can't internalize it。 it has no intuitive meaning。You know， rest assured it is the same for me。

Okay， but still， I think it's useful to do it because。

When you see the manipulation of those bio operators。

 like some of the manipulation is pretty interesting and， and actually can be useful。😊，Okay。

 so to prove this。😊，We're gonna establish two facts that we'll be using later。

 One is and hold on like here you you we have the superscript subscript nightmares。 Again。

 We have T pi K plus 1 Q pi K is always greater than to T pi Q pi K for any pi。😊，Okay。So why is that？

 Well， remember， T pi F is what is just R of S A plus gamma and expectation as prime。From SA。嗯。

F of S prime a prime where a prime is taken according to pi。Okay。

 so this is the definition of T pi F。 And on the right hand side， you have just T pi。

 You just have F being Q pi K。😡，Okay， now I ask you the question， suppose I fixed F。😡。

What is the policy pi that maximize this expression？😡，No， not pi star。 wrong answer。 So， so， I mean。

 what you should do is that， well， I said F is fixed， right， So the only thing you change is pi。

 you want to figure out the pi the max minus expression。 You should look。

 first look at where pi appears。😊，Where does it appear？Where is P on the right hand side？

F of pi right。Alright， okay， So you're saying the answer， right， So F S prime pi。

 So what's the pi that like， So here I'm saying pi， But really， like there's a single action。

 What action you should take。The greedy action， the action that gridly optimizes F。😡。

And if you want to express that as a policy that works for all as prime， let's just pi sub F。😡。

RightThe greedity policy that the policy that is greedy with respect to F。

 What's the policy that is greedy with respect to Q pi K。In the algorithm of policy iteration。

Pi K plus one， right， Policy duration literally works that way。 You have the previous policy。

 You have this Q function。 Then the next policy is greedity policy。😡，Yes。Okay， so therefore。

 this is always greater and equal to that。Which， by the way， so here is the funny thing。

 this is equal to Q pi k。Right， because。What， what you can say is that if you put F over here。

 So F over here， what is this， This can also be written as max over a prime of S prime a prime。Right。

 and in that case， the right hand side is literally just the。The the。The apartment of operator。Okay。

 so this is getting， maybe getting confusing。So this tells you that for fixed F。

 when you choose the policy to be pis sub F。😡，T P FF is actually the same as the the B optimal operator。

Okay， so this is getting and， and let me ask you a question that probably hope maybe further confuses you。

 if we know that the Belman of money operator is a nonlinear operator。

But the policy specific operator is a linear operator。😡。

How can a non nonlinear operator be equal to a linear operator。That makes no sense。Or in other words。

 does this tell you that T is the same as T pi F。How many think that T and T P F is the same thing。

No， why， why not？ How they differ。Why， why like。This holds for sure。

 but why are the two operators different？Because here， there's only hose when you have this F。Okay。

 and for this to hold， this policy specific operator needs to have pi sub F over here。

 So the policy changes whenever you change F。But here for in the definition of this operator。

 this operator is always the same thing， like it always have this max regardless of how you change the F。

😡，But here， if we're treating it as a policy specific operator。

 that operator comes with a fixed policy， but in order for this to hold， whenever you change F。

 your policy needs to change。😡，Okay， so this host， But these two operators are different things。O。

So that's the first fact。In fact， two。We have。T派 k。Plus one Q pi K less than or equal to。

Q pi k plus one。Okay。So why is that？We can just expand this one。 This is saying R of S。呃，A plus。

Gma and expectation。嗯。Let me see， Q。排 k。S。Pi k plus one。Okay。Now， this is equal to。

 I can write it as the expectation of。Summation of reverse。R sub T。When S 1 is sorry， here is S。

 S1 is S， right？ So if you look at this expression。

 So one thing is that whenever you have a be operator like expression， But inside the expectation。

 This is also a value value function。 Oftentimes， you can translate that that into just the expected sum of reverse when you specify a particular behavior。

 right， and that behavior， you can actually read off this expression， right。

 So this is saying you're in state S， right， let me say the S。

 What's the first first action I'm taking。😊，Is iss a over here， right， then the second step。

 I'm transitioning to S prime。 and'm from there all。I'm taking action P K plus1。

 This is my second action。 What's all the future actions。Taik。

 right because here is all the action after this one。😡，Right， so therefore I can write this as。

S1 equals S。A1 equals a， A 2 sampled according to pi K plus 1 and a 3 all the way to infinity sampled from。

排期。Okay， so I have this expression。😡，Now， similarly。

 you can write Q pi K plus1 and as they expected sum of reverse。

 And here you will have S1 equals S the same thing。

 A1 equals a and all the action sampled according to pi K plus1。😊，Okay， now here。

 the second action is also pi K plus one。 So they're the same。

 So these things only differ starting from step 3 on。 But here you have Pi K。

 there you have P K plus one。 And we know policy monotone policy improvement Pi K plus1 is always the better policy。

 When you have the same state distribution， right， In both cases， all the previous actions match。

 So you start from the same state distribution here。

 Here you have Pi K for all future actions there you have p K plus one for all future actions。

 So that one is always better。Okay， so。So once you have these two。We can look at what is。

Q star minus Q pi1。 This is what we want to prove。Okay？And by the way， so here， if you remember here。

 although I have an infinite norm。The city side is really like point wise， not negative。😡，Right。

 so therefore， I， I don't need to。 I can pretend that there's no absolute value over here。

 So I can always， for example， makes this one smaller and S still holds。So this is。

Le than or equal to。Well， this one， I'm going to write it as T pi star， Q star。Right。

Because Q star is just T Q pi star and Q pi star is just Q function for the policy pi star。

 which is the fixed point of the Belman policy specific operator for pi star。

So this is actually equality。 But the second one， I'm going to relax using the thing we we just have。

Pi star， Q pi。 What do we have， So I'm starting with pi K plus 1， which is over here。Right。

 so I'm making it smaller。 So I'm making it actually。啊。Right， so I I， I get over here。

 and then I can also replace the pie over here with an arbitrary policy pattern。So I get Q pi K。

 if it or not。Okay， so I have I Q pi K plus1， which is greater than this one。

 And this one over here is further greater than this one， where this policy pi is up to my choice。

 I can choose it to be anything。 And here I choose it to be particularly just pi star。😊。

And what do you do next？Any guess？Why do I write this in this form？

You can't take T out like T is not like just a multiplication or something。😡，But no。

 you want to take it out， why can't you take it out？😡，I'm looking for one word。😡。

There's a property of these like bowumman operators。Like。

 when have you seen like you have two different functions， but you apply the same Bel operator。

Sorry to say it again。They are linear， yes， but we're not looking for their。

 Linear is not the property we're looking at here。Contraction， right。

 So we said that the T operator has contraction。 But here， like T like。

 but we also mentioned that all the policies specifically Bramar operator also have contraction。

 So contraction gives you gamma。Q star minus Q pi k。S。Okay， again， like this。

 this is one of the very few proofs in this class that I just can't write without looking at notes。

 But I think what's the really valuable things here is kind of like give you this new understanding of how bump operator works。

 for example， you know， sometimes for fixed F， the optimal operator can also be equivalent to a policy specific operator for specific choice of the policy。

 which is the greedy policy。 And also the fact that when you have things like a valid value function。

 And then you have a bump operator applied to it。 it can be actually written in a form that is the expected return under some non stationary policy。

😊，Okay。So that's it。 And yep， I'll see you on Wednesday next week。



![](img/036e3a7337f00c2fe3ed71f5a6a29bbc_82.png)