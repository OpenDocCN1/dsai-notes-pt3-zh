# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p08 P8 策略迭代 -BV1YsZHBZEyM_p8-

Okay， so。This is where we were last time we started talking about a policy durationeration and the algorithm。

 you know， unlike value duration， where you get a sequence of real value functions。

 So here you get a sequence of policies。 and， and in each it。

 which you do is that you evaluate the Q function of the last policy and then just take the greedy policy with respect to it。

And then you get a new policy。And we verify that as a very basic sanity check。

 if you ever arrive at pi star， the optimal policy。

 you will never leave there right because when you evaluate it。

 this is just Q star and we know that we never gratify over Q star， you get the optimal policy。

 So will just loop over there forever。Okay， then one of the most important properties of policy iteration is this property called monotone policy improvement that says like your policy will never get worse。

In this iteration， like every iteration until you hit pi star where you can't improve anymore。

 because there's no room for improvement。 But before you hit pi star。

 your performance will be just better in every single starting state or like at least not worse。

 and it will be strictly better in at least one of the starting state。Okay。

So this is what we're gonna prove， which kind of like gives you a some intuition for， you know。

 and this provides justification for why polar may be a reasonable or good algorithm to consider。

Okay， so。So as usual， this we've already seen this kind of recipe before that whenever we prove like a fundamental theorem about a。

 you know， these like basic algorithms， typically what we'll do is that we're gonna like introduce first introduce like a very useful lemma。

 And then you know， we prove dilemma and then use di lemma to prove this particular theorem。😊。

And that's also going to be the case over here and。

I would say the lemma that I'm going to introduce now is probably。

More important and more useful in like more modern part of our。

 where we consider like a large say space function approximation。

 or even like you might want to consider some fancy like policy gradient type algorithms and so and so forth。

 And thelema that I'm gonna talk about will still be like useful。 Okay， and you see。

 like it's a little different than the dilemmas that we've seen previously， for example。

 the contraction property。😊，Okay， so what's the， what's the lemma， This this lemma is called the。

Performance。呃，deence来。Or sometimes called PD dilemma。And as usual， like， you know。

 when we state dilemma， usually dilemma is general enough that it's。

 it's very general and not really confined to the particular like， you know， framework of the。

 you know， the algorithm here。 So here， like we have a sequence of policy and so on so forth。

 But for the dilemma， what it says that is just if you have any two policies。

And these policies are mapping from states to either actions that would suffice for our use here。

 But this host generally like it， you can have like stochastic policies。 Okay， you have。

 you have two。You have two。You have two the arbitrary policies， pi and pi prime。

And what we're going to show is that。And， and let's say we have some。

 let me think about how I would want to。defineine this。 Let， let me show do it in the most。 And。

 and for any T 0 in。Data S。 so D 0 is like any initial state distribution。 right。

 So it turns out this this full。 And then what we we can do is that we can define。J派。

As expectation as from D 0， v pi of S。Okay， so I'm just stating it a slightly more general manner is that will be useful in later lectures。

 So what it's saying is that， okay， so we know that for any policy pie。

 it' performance depending on the starting state。😡，And if you have different starting state S。

 you have a different expected return， which is v pi of S。😡，Now， in practice， like in many you know。

 problems， especially those episodic problems， there's usually a particular well defined initial state or initial state distribution。

 right， for example， if you play a war game， like， you know， if you play go。

 you start with the empty board。 if you play chess， you start with a， you know。

 the standard configuration of the， of the board where the pieces have like fixed positions。

 and in some other cases， like you serve from a particular your initial state is randomly generated。

 but it generated from particular distribution。 So the zero is that distribution。 Okay， so we say。

 okay， if， if the initial state is drawn from that distribution。

 then expectation of V P S is just the expected return。

 when you generate dressreasies where the first state is not fixed， but follows that distribution。😊。

Okay， does that make sense？😡，Okay， so then we can ask the question， what is。J pi prime minus J pi。

Okay， so what we're interested in is to rewrite the， this is the performance difference。

 we have two different policies。 We have a well defined initial state distribution。

 And we want to know how， how different they are。😊，Okay， does that make sense？

So the lemma says that this can be written as the following。😡，This is one over woman is gamma。😡。

Expectation。As prime。Or maybe to avoid confusion。 Let me maybe use S Q over here。

 S drawn from D pipe prime。 You know， would define this like in a bit。And a pi S prime。As tutor。Okay。

 so we see like a two。Notations that requires definition。 Or， first of all， you have this notation。

 And we have seen something similar to this before， right。

 So when we talk about solving for Belman solving for Belma equation for policy evaluation。

 we say that there's a matrix solution。 That is you know。

 V pie equals I minus gamma P pi inverse R pi right。

 and we say that this particular matrix has this interpretation。

 that each row is the discounted occupancy。it's like you。

You start from some starting state which correspond to the row index and you just row out trajectories according to policy pi。

And then at each time step， you have a marginal distribution over states and you combine them into into a mixture distribution。

 which accounts for the discounted sum of distributions you will hit at every time step。Okay。

 so D P prime is pretty much precisely that。 So one way。

 there are multiple ways of writing D P prime。嗯。So。Oh how do I， How do I do this。Okay。

 so one way to write the pipe prime is that this is just a。The0 transpose I minus gamma P pi。

 heres prime。 So I have prime this。Okay， so it's， it's like so for each， for each starting state。

 you have this discounted occupancy。 And we have a well defined initial state distribution over here。

 And then we just you know， combine those， those， those those discounted occupancy distributions。

 And that is D pipe prime。 So， or alternatively， you can also write it in a form that is。😊，嗯。你呃。

Alternatively， you can also define it as a D pi prime of Stda is equal to。嗯。Let's see 1 minus gamma。

 This is a normalization factor， summation。He equals 0 to infinity。😊，I I mean。

Probably should do one gamma T -1。Gma t minus1 probability。Of。S。T equals S tta， given that。

S1 is drawn from D0， and。The distribution， we take actions according to policy by。Right。

 so if you remember， like when we， when， when we let S1 to be a particular starting state。

 S1 equals S。 this definition is。Let me see。 this particular definition is literally the the like a。

 a particular role in this matrix。 right， So that's the discounted argument in that we have introduced。

 So here is just a slide generalization when you， instead of drawing as letting S1 to be a fixed date。

 you， you draw it from starting state distribution。😊，Okay。So， and then we have another quantity here。

 which is a pi。 What is a pi。 Well A pi is defined as。As tuda A is defined as。Q。Q pi of Stda。

Let me see which direction。呃。Right， a minus v pi of S。Okay。

 so this quantity is called the advantage function。I mean， for now。

 like it's not really like that much sick significant。

 like you could just state the dilemma without introducing this new concept and just put this this whole like equation over there。

O。And then remember， like whenever you see like a pi prime that appear。

 like a policy that appears in the place of an action。

 what it means is that you should like evaluate like pi prime on Stda。

 which is the stay in front of it and replace that with the， you know， corresponding action。Okay。

 so this is the this is the lemma and the quantities defining it。 and we prove in in a bit。

 But what we can do is that we can first look at the lelemma and immediately get。😊，啊。

Like if the s holds， the first in quality immediately holds。😡，Okay， so we can we can look at why。 So。

 so the， what we're gonna do is that we're gonna just let。This pipe prime to be。P K plus one。

And thisBB pK。O。So because it says， I want to show that for every starting state or maybe P K and P K -1。

 that's not too much different。Okay， we want to show that for every starting state。

 Pi K is better than Pi K -1。So， you know， equivalently。

 I can show that under any initial state distribution。

 the expected return of Pi K is better than pi K minus-1， right。

 So it's the same thing because I can just let these initial state distribution to be point mass on every single state。

 Then I'll just get what I need。So if I can show that this difference。Its always not negative。

 I'm done。😡，Correct。Okay， now you look at on the right hand side and see what you get， right。

 What you get is one womans gamma。 Okay， if I want to just need to talk about the negativity or positivity of this quantity。

 I can ignore this。😊，I have an expectation， well it turns out that just to show that policy improvement。

 you also don't need to look at。😡，Really care about what's the distribution number here。

 So what we're going to show is that this quantity， which is the advantage， is always non negative。

Okay， so why， well， look at this definition。Its definition is Q pi of S or S2ta a minus v pi of S tuta。

😡，Okay， and what is Q pi and what is pi over here， pi over here is pi K -1， right。

 So we're letting pi to be the previous policy。 So that will define the policy over here。Okay。

 but then like we're not really just doing S tuta A for， for arbitrary A。 We're。

 we're looking at the advantage for S tuta and action taken according to pi prime。 So here。

This action is pi prime， which in our case， is pi K。Okay。So now I claim that。😡。

Like this quantity can never be negative。😡，Why is that the case？

So it would be helpful to zoom out a little bit， and to。To recall the， recall the algorithm。Okay。

 so what do we do in the algorithm。 What we do in the algorithm is that every iteration。

 when we get pi K -1， we get Q pi K -1 and then take action as greedy like with respect to it。

So therefore。What what's the action that Pi K will take？Yeah， the action that Pi K takes。

 according to the definition of the algorithm， is whatever action that maximizes Q pi K -1。😡，Okay。

 so now why is that greater than equal to B pi of sta。V， can you like， okay。

 So the claim is that So here the first term is is in the form of cube pi of S。

 Then your your action is the best action for Q pi。Okay。

 so if your second term can be also be written as Q pi of S tuta some other action。

 then that certainly will have lower value or at least no more value than this one， right。

 Can you write the second term also in the same format， That is a Q pi of S tuta for some action。How。

 how can we rewrite this。I mean， we have a shorthand。 We， you don't， You shouldn't need expectation。

 I'm looking for some answer。 that is very short。It's not arc max。

 There's no arc max in the second term。会。Exactly， right， So remember， like V pi is just。

 you take actions always according to to pi。😡，Cupie is first action。 You tell me what you want。😡。

All the remaining actions I take according to Pi。Therefore。

 V pi and Qpi would be the same if I look at Qpi， but I also require you your first action is also according to topi。

😡，Then this NV pi is the same thing。😡，Okay， so therefore。

 what we have over here is Q pi of S2 as something minus Q pi of S2 as something。

But the first action you take has already maximized the cubepi。😡。

So there's no way that this difference is negative。😡，Okay， does that make sense？

So once you have the performance different dilemma the。😡，The first condition of sorry。

 the first statement of monetary policy improvement will immediately follow。Now。

 in the interest of time， I probably won't cover the the second one。 And if you're interested。

 you can， you can take that as a， as a homework。 It also follows from the same。

 You can also you know， obtain that from the performance difference level。Okay， so。

Then what we need to do。😡，Is to prove it。Okay。Move this。Okay， so the proof。Okay。

 so this is a pictorial proof。Okay， now， remember， like what we， what we just said is。

 what we just did is that we show that if you have performance different lemma。

 we can immediately show monoone policy improvement。😊。

 but now we're now like zooming in to prove like the performance difference I myself。😡，And remember。

 for this lelemma， this is general。 We're out of the framework of policy equation。 There's no pi K。

 P K minus1 or whatever， right， You just give me an arbitrary to， like two arbitrary policies。

 pi prime and pi。Okay， we just want to show that this equation holds。Okay。

 and here's what we're going to do。 What we're going to do is that we're going to construct a sequence of infinitely the infinite number of policies。

That。That， like， essentially bridges between。Like pi and pi prime。Okay， and notes that here。

 like I also have pi 1， pi 2 pi 3 and so on so forth。 But these pi， you know。

 with with the subscript number has nothing to do with the pi case in policy， right。

 because now we're like proving this very generic lemma that by itself doesn't can be applied anywhere。

 It doesn't have to be applied to policyeration。 So these pis don't you know。

 don't mistake them as the， the policies you get in policy。

 These these policies are merely constructions for proving thislemma alone。Okay。

 does that make sense？Okay， so， and as you can see， here is what I'm doing， right？

 So I'm imagining like S1， like， so here is just illustration of what kind of trajectory like each vertical chain is a graphical representation of a distribution of trajectories。

 okay， so your S 1 is always drawn from the initial state distribution at the 0 that I'm you know。

 that I'm telling you。 And then。😊，Like someone reminds me。

 how do you specify a what elements specify the distribution of trajecties。You need two things。

Initial state or initial state distribution。 That's one thing I just said， what's the second thing。

Policy， right， you need to tell me how you are gonna take actions。 once you have these two things。

 Were done。 right， So， so here I'm， so here like what kind of policy you take at each time step。

 I'm representing that by， you know， arrows of different colors。

 If you take actions according to policy pi， I use black color。

 If I take action according to pi prime， I use red color。 Okay， so therefore。

 if I have infinitely many blacks。 Well， this is just the distribution of jujectciies。

 According to policy pi。Right。And if I take the expected reward， you know。

 expected sum of rewards along this trajectoryary distribution and take expectation。

 that's just J pi。 right， the performance of policy pi。 And similarly， if I have all the reds。

 which is like all the red actions， which is pi prime， Well， this this give me。嗯。You know。

 this is just J pi。 This is just J pi prime。Right。And I care about expressing their difference。😡。

And what I'm doing here is I'm， I'm creating all these like intermediate policies such that when I express the difference between these two。

 I can always express that as the difference between these two， these two， these two。

 these two all the way to to， to the right， right。So I use like these like intermediate policies to bridge between them。

😡，Okay， so how do I construct these intermediate policies， Well， we actually construct them as。

 as what we call like non stationary or timing homogeneous policies， where， for example。

 pi 1 is the policy that the first action I take according to pi prime， the red action。

 but all the future I take according to pi。Okay， then pi2 is first two actions red。

 all the remaining all the way to the future， black。And so on so forth。Okay， as you can imagine。

 like what's happening here is that every pair of adjacent trajectoryory distributions。

 they only differ by one action at some particular times stamp。😡，Or one one policy， you know。

 that there is only one time step where their policy mapping differs。In all the other time steps。

 the way that they take action according to SA are exactly the same。😡，Okay， make sense。So now let's。

 let's， let's calculate this more formal， right， So we have a。So according to this。

 we have J pi minus J pi prime。 You know， according to my convention over here。

 I can also say pi 0 is just pi because like the subscript here is essentially how many red actions do you take at the beginning before you switch to black actions all the way to infinity。

Right so pi can also be called pi0， and pi prime can also be called pi infinity。Okay。

 so this is just pi 0 minus。Actually， I think I'm， I want the other way around。 So it's pi infinity。

Minus pi 0。Right。Then what I can have is this is summation。As I said。

 I constructed these like intermediate policies， and I break the difference into like difference。

 like the， the， the sum of all the differences of adjacent pairs。 So I have I equals。Z to infinity。

J pi I plus 1 minus J pie I。Correct。Right。O， now。We just need to express this， right。

 So let's zoom into an arbitrary pair and look at what we can say about them。Okay。

 so let's say this pair。So what we can do is that we can look at the reverse they are playing at each time step。

 And if they're the same， we can ignore them and we can start looking， okay。

 so for the first time step， is there a difference。😡。

There's no difference because you start from the same initial state distribution。

 You take the same action。 Well， they expect reverse， of course， it's the same。Right so therefore。

 when you take the difference， they just completely cancel out。Similarly， for the second action。

 they also cancel out。Correct。Okay， but here's the thing。😡，The difference starts to emerge over here。

 Right？ So here as at as 3。Like the other thing about taking the same actions before time step 3 is that when you look at S 3。

 in both cases， you arrive at the same state distributions at S 3。Right。

 because you start from the same initial state distribution。

 and if you've been taking the same policy so far。😡，O。But now there is a difference。

 I take black action， you take a red action。😡，I guess you get different rewards。Okay。

So here's the question for you， okay， so afterwards， both of us will take， you know。

 we become the same again， like both of us will take black actions all the way to infinity。😡，Right？

So let me ask you， are the rewards I'm going to get afterwards the same？😡，Why not？Right。

 because remember， this is Rl。 right， The whole point of R L is that your actions have。

Not only have impact on what immediate rewards you get， but it also have long term consequences。

That you actually go to different state distributions。Okay， so the。

 like because of the single difference， the distribution over S 4 over here is going to be different from the distribution over S4 over here。

And although you're going to take always the same action as afterwards。

Like just because the state distribution is different。

 the expected rewards you get afterwards are not going to be like the same in general。😡，Okay。

 but still， like we want to。We want to have a way to express this long term difference in a concise manner。

Okay， what can we do。So note that there is a commonality that in both cases， after this difference。

 all the future reactions are according to the black policy， the pi， in both cases。😡。

What quantity can you use to express the expected reward you obtain when you always take actions according to some policy pie。

Value function， yeah。But not necessarily J， right， So I'll just give the answer。

 and then you see like， whether that makes sense。Sation I equals 0 to infinity。 Okay。

 now I'm looking at this particular I。 So the claim is that this is equal to。😊。

Let's say I'm doing the right hand first， let me see。Might be a different sign anyway。

 I'm going to do this。Okay， so this is。嗯。Q。牌。嗯。As tutor。Let me， let me write in this way。 Okay， so S。

S 3。Pi prime。Minus Q pi of S 3。Okay， or like this is just a v。Okay， so this。

 this is not quite this yet because I still need to take care of the distribution over S S 3。

 among other things。 But let's say you're at S 3。 and you want to express the difference of long termm rewards you obtain afterwards where in this particular case。

 you only differ by the first action。 But afterwards， both of you take action according to policy。

What's the difference， the difference is this。😡，Right， because you have V pi。

 which correspond to the， the left chain where starting from S 3。

 youre taking action according to pi。 and it's always pi。 right， So you have V pi of S 3。

On the right， the first action is according into pi prime。

 but all the future occurred into policy pi。 So it's Q pi of S 3 pi prime。Does that make sense？Okay。

 so now。There is actually a slight。 This is not exactly what we what we should be getting。 So okay。

 what you can， what we can do is that。So here is also， so， first of all。

Whenever you you invoke the notion of value functions and you say S3。

 this is treating that S3 as if this is the first time step。Right。

 but S3 is not really the first time step。There's already a few time steps before， right。

 not only the rewards before that have canceled out， but the discount factor has also accumulated。

Right， when you look at the difference between these two things， their difference will actually like。

 should be discounted by like。You know， actually， so here I said S 3。 But really， because this。

 I'm considering the general case， this is S I minus plus。1， and okay。

 so I have a gamma to the eye here。 I think， yeah。Right。

Because because eventually we're calculating the difference between the the returns from the perspective of the real initial state。

Right， now we're treating this as like a fake initial state。 But this because before that。

 everything is the same and they cancel out。 But there is implicitly already some discounting that is has accumulated that we need to account for。

So there' is an actual gamma to the eye over here。😡，Makes sense。Like， like， you can imagine。

 like when you go to the the right most side， like almost all the infinitely many actions in the beginning are the same。

 and things only start to differ after infinite many steps。

And that difference will contribute basically nothing to the difference value。

 difference in value in the initial state， right？ So that correspond to a case where I actually goes to infinity and this difference is gonna be like。

 you know， like discounted towards 0。O now。However， this is not quite there yet because S3。

 which in the general case， is S plus 1 over here， this is a random variable。😡。

We still need to take expectation。😡，RightBut as we said。

 because all the actions before it is the same。So the distribution over S3 is the same for both cases。

 So I can actually just write a single expectation for them。

 and the claim is that I can just write it as。😡，Pi prime， okay， maybe I can say。

As one from some initial distribution easier。Okay。So why is that case？ Well。

 this notation is saying that I'm imagining a distribution virtual directorreies where I take the initial state is drawn from D0 and all the actions are taken according to pi prime。

😡，Which， by the way， is not what's happening in these trajecttories。Okay， but this still works。

 right， because here the only random variable is Si plus1。😡，And the distribution of S I plus one。

 which is S3 over here in these two like trajectory distributions。

 actually coincide with what's going to happen。 when you take all the actions according to pi prime。

Right， because because you only look at the distribution of S3 over here。

 you don't care about what happens afterwards。😡，Whatever action you take afterwards。

 whether it's black， red or always red， always black， It doesn't matter。

 The distribution is the same。 It's this distribution。Okay。Makes sense。Okay， so what is this， Well。

 this is just。This is just what。 This is a pie S I plus one pipe prime。Again， like for now。

 this is just the appreation。 it doesn't really mean anything。Okay， so that's the first thing。

 And then we can write it this way。 I equals 0 infinity。 Okay。

 so now I'm gonna just write the expectation as like sort of a sum， as a sum。 Okay。

 so I can sum over S。😊，As tutor。Where。So here I'm just looking at what's the marginal distribution of S plus one。

 right， So this is just the probability under policy pi prime。嗯。S I plus 1 is equal to S tta。

 given that S1 is drawn from D 0。TimeThen， then this is just the probability of， you know。

 whatever is over there， right times。Q pi of S tuda。Sorry， pi prime。Minus v pi of S。Okay。

 I'm doing nothing but just write the expectation as the summation of the probability of each possible realization times the function。

 you know， for that， you know， realization of S M plus  one equals S。Okay。Now。

 here is something nice。 So before that， I still have this infinite zone。Right。

 I still have this infinite sum。 and this infinite sum， But in this infinite sum。

This part is the same across all eye， it has no dependence on eye。😡，Ohright。 So I forgot that。 Yeah。

 yeah， yeah， You're right。 So let's put it over here， gamma I。Okay。So therefore。

 what I can do is simply to do this。Right。Because previously。

 it summation over here and everything here， right， But everything here。

 you have a term that is independent of I。 So you can actually， you know， you know， push that out of。

This this summation。So what I did what I okay， So， and because I already introduced this。

Notation of advantage。I can just call it a。Pi of S tuor。P prime。O。Now， what is this。Well。

 if you look at what I said earlier。This is just the definition of D P， D P f。Okay， so then this is。

One over woman is gamma up to the like， there's a normalization factor。

1 my one minus gamma here to make sure that D pipe prime defined in this way is a。

 is a distribution that all the probabilitybaities sum up to one。

 So this is one of woman as gamma the。拍。Prime。啊，sorry。Subation as， as tutor。D pi prime of。S tu的。

A拍 sq的。Okay。And well， because the prime of Stda is a distribution。

 you can also write it as an expectation， which is what we get。On the right hand side over here。Okay。

Clear out some of the。Okay， so。So like this is， so you know， I。

 the way I myself remember this slemma and also prove it is actually by this visualization， right。

 So you can actually look at this visualization and kind of like intuitively make sense of what's happening in the slemma。

 right， So one thing you should really notice， you know， take take notice is that in the slemma。😊。

You have on the right hand side， you have a lot of policies， right， Sometimes it is pipe prime。

 sometimes it is prime。But there are two different things。So here is here is a policy。 is pipe prime。

😡，Here's another policy。 and it is pie， right， And these are actually， you know。

 the two different policies you start with on the left hand side。Okay， and there's a， so like。

 you know， sometimes like when you don't， don't actually remember the， you know。

 these specific form of of dilemma and you try to write it down。 You may make a mistake that。

 you know， maybe you have D pi prime and then you have a pi prime。

Because there are actually three occurrences of the policy on the right hand side。😡。

But if you actually remember this diagram。You should never make the mistake。

 like the pi prime over here and the pi， the policy over there。

 like the policy on the discarded occupancy and the policy on the superscript of the advantage function。

 they should never be the same。Because if you， if you look at how， how how this proof works。

Essentially， what happens is that。We're joining a diagonal line over here。Right。

 so everything above the diagonal line， things are the same across， you know。

 for any pair of adjacent policies。Right at the beginning， both policies take the same actions。

RightSo those part don't really generate any reward difference。😡。

The only effect of those part is they actually roll in into some particular state distribution。

 And that difference is only happening afterwards。RightBut how are which policy dictates the distribution you arrive at on that diagonal line？

😡，Which policy？Well， I'm asking you， like， so for the distribution of the states that that lie on this diagonal line that separates the red arrows and black arrows。

 which policy determines the distribution over those states。Te prime， the red poy， right。

 because the upper triular triangle is all red。And which term？😡。

In the smma reflects the distribution of those。States。In the slema， on the right hand side， which。

 which quantity curve describes that distribution， those distribution or their their。

 theyre like mixture。D派拍。Exactly， right。 So D pipe prime that policy correspond to the upper triangle。

Now， after like once you arrive， sorry， once you arrive at that， you know。

 those states on the triangle， you now should account for the difference in reverse that happens afterwards。

Right， but whenever you look at a pair of adjacent policies。

 all the future are according to policy pie， and they only differ by， you know， one single action。

 So then we get this notion of advantage。 But the superscript of the advantage function。

 is the same as the superscript of these value functions， which is determined by all those future。

 you know how you take those future actions。 which policy determine that。It's pi。

 this is the black policy pie。😡，Right， so basically the proof goes like you have the diagram。

 you draw the tri online where the upper triangle determines the say distribution。

 The lower triangle determines like， you know， which policy do you use to define the Q function。😡。

So therefore， the Q function is superscript and the， you know。

 discounted occupancy is superscript can never be the same。 They are always different question。来判さ。

Oh， yeah， yeah。 I， I I， I did it wrong。 Yeah， it should be the same。Okay。So。Now。

 question here for you。 So if you look at the left hand side。

We just started with two arbitrary policies， right， pi prime pi。Like， they can be really anything。

 So they are on equal footing。 And the whole thing should be symmetric with respect to them。

But somehow， on the right hand side， the symmetry is broken。 One determines the。

Distribution number states or what we call the row in distribution。 Like， you know。

 how like what kind of distribution you arrive at when you start from the starting stage distribution and take certain policies。

 Like then the， the， the distribution you arrive at at an intermediate time step。

 sometimes like informally， well call that the row in distribution。

And the other one determines this roll out value。Right， the state distribution， row distribution。

 roll out value， there are different things。 How is symmetry broken。😡。

Like where in this proof did I break the symmetry？😡，Yeah， I think you are getting it。

 So here's another way， right， because because because this， this。

 this theory is completely generic and applies to any pair of policies。

 I could just swap the order of pi and pi prime， right。

 which means that I should be able to use pi to define the discounted occupancy。

 but use pi prime to define the advantage or or the rollout value。But if I were to do that。

 in my prove， what should I do？😡，What they're okay。Direction of the。Yes。

 change the direction of diagonal。 Right， So what you should do is that you should define the diagonal in this way。

 right， So previously， this is like one red all black，2 red or black and all the so on so forth。

 What you do is that you should serve from the right hand side。 And then you do one black all red。

2 blacks all red，3 blacks all red and so on so forth。Right。

 if you do it in that way and you follow this proof， you exactly get， you know。

 you can exactly swap the rows of pi per random and pi。Okay。

 which means that the dilemma is still like you， completely symmetric with respect to the both policies。

OK。So this is one of the。😡，Like， if you look at this， this lemma。

 like it's super useful because unlike the lemmas we've seen before， right， So we， we。

 we've seen this analysis， like， for example， you have contraction and then contraction tells you convergence。

 right， But those results， they actually all depend on these infinite norms， which are like。

 you know， in some sense， like can be very loose， right。

 And and all the results we get are inequalities， you know， which。

 which can be loose and you can they they may not be tight。 But this result， particular。

 is a identity。😊，We're not like， you know， you also have wonderful woman in Gama。

 which makes it look kind of like what we have before。 But here you're not losing anything。

 It's just a literal translation。The other thing why this is very significant is that which is related to like。

 you know， being identity versus being inequality that relax the things using infinite norm。

 So you see infinite norm a lot in tablet analysis because infinite norm basically sweeps under the rug。

 the issue of distributions。😊，RightYou don't need to care about distributions anymore because whatever。

 whatever like， you know， you take expectation over something。 Well。

 you can always relax that to the infinite norm of something。😡，RightBut here。

 because we have identity， you can't do that， which forces you to be actually sensitive to like know what kind of distributions you are looking at。

😡，RightAnd turns out that when we look at you know。

 more challenging scenarios where you have large state spaces。

 function approximation and so on so forth， these identities become way more useful。

 like those like infinite norm based results， basically will become completely useless in those settings。

 but what we need is the like these identity versions or variant of those results or generalizations of those results that that actually properly account for what kind of distributions over states we're looking at。

😊，Okay。😊，Okay， so。As a bonus。This， this smma。😡，Actually， becomes immediately useful。

To for a open problem we left in a previous lecture。Let meCopy over here。Copy over here。

 So this is the。This is the lemma。And， well， for our understanding。

 let's just write out the definition of。Advantage as to the pi prime minus。啊。V pi of S。

Okay we have one less thing to remember。 Okay， so， so this is the PD D Lama。If you remember。

 like there's this lemma about value that I only give you， but I didn't improve。For any F， that is。

RSA。We have。V star minus v pi F。Infin norm is upper bounded by f minus Q star。If you're in norm。

 one minus is going 2。Okay， so remember， what was the contact context of that， right。

 So the the context was that we know that in valuation， we get a sequence of functions。 Eventually。

 it approaches Q star。😊，But in reality， we only have finite computes。

 So we stop at some time at some point where we get an F that is like really close to Q star。

 but it's not there yet。But still， we pretend that it is Q star and just extract the greedity policy out of it and hoping that it'll be good。

And with the slema tells you that indeed it will be good up to， you know。

 some additional multiplicative factors。Like how good this policy is compared to the optimal policy is controlled by how close your function F is to like Q star。

Okay， I told you to this result to justify why you can stop prematurely and still just get a good policy out of it。

 but I did improve it。😡，Okay， well， it turns out that now we can just prove it directly using the performance differentlemma。

😡，Okay， so what we can do is that we can just say J pi star minus J pi F。Right， we have bound this。

 This is just a V star minus V pi F for some initial state distribution。

 And if this is always bounded， regardless of the initial state distribution。

 that's just the same as the left S I。Okay。So now what' we do。Equals。

 so now we're gonna apply the performance difference lemma。But it turns out， but remember。

 whenever you apply the performance different， you need to choose one of them to be to define the row in distribution and the other one to define the roll out policy。

😡，Okay， and the correct way to， you know， choose that depend on the particular problem。

 So I'll let you make a guess which one do you use to define the row in and which one do you use to define the roll out。

😡，So you have two policies over here， pi star， which correspond to this pi F。

 which is whatever policy we extract from this function now。You should look at the right hand side。

 which will give you a hint for which one to。We're trying to choose to for， for， for which。

Pi F has O A and pi s has a rot y。I'll just simply do it。Yeah， yeah。 how how did you match it？就系。

Well， no， no， no。 if you， if you do the， if， if， if you， if you look at this and match over there。

 pi prime is row。 Okay， no， no， then pi then pi star is row in。 then pi F is roll out。She married。

I'm looking for a very simple answer。 Like， you should look at the result you're trying to prove。

 And on the right hand side， there's a single quantity that tells you which one， you know， how。

 how should you pick things。Yes， you have Q star， right， Q star is wood is Q what policy。😡，Yeah。

 Q star is Q pi star。😡，Right， so that already tells you that if you want Q star to appear on the right hand side。

 you want Q pi to be Q star。 So that pi needs to be。派3。Right， so actually。

 the match is wrong over here。 Like if you mechanically apply the， the match over there。

 which we actually， we， we， we actually break that symmetry like really arbitarily， right。

 So actually， you get the wrong。 you get the wrong way to decompose things。 right。

 So you actually need to choose。😊，So what you get is one over one is gamma expectation as tutor sampled from the pi F。

 So you get the learned policies。 Sorry， the， the， the， the policy you get。

 and that's gonna to define the row in distribution， the discounted occupancy。

And then you get Q star of asda。 So here is， actually。

You also need to swap like I'm not going to detail here。

 but you also need to swap the order between Q pi and V pi， right。

 because you're essentially flipping， like taking negative sign on the left hand side。

So you actually have V star minus。This minus Q star S to the pi F。Okay， and this also makes sense。

 right， because pi star is always better than pi F。

 So here V star is always better than Q star of something else。 So this is non negative。

 This is non negative。 Otherwise it doesn't make sense。😡，Right。Okay， now because we。

 we only need a infinite normal result。 So that expectation can already be gone。 right。

 We have one over Roman sma。嗯。We can just do max over as kta。嗯。

V star as S tta minus Q star of S tta pi sub F。Okay。

So now we already see one of a women schema that appears。

 right that is what we need on the right hand side。嗯。We already get Q star to appear， right。

 like Q star appears over there。 We have Q star。 V star is also basically Q star。

So what's on the right hand side that has not appeared yet。F， right， And that's the key thing。

 Like all we have control over is how close F is to Q star。

 But F so far only appears as this policy pi sub F。

Like the numerical real valued function F doesn't has an period。Okay， so what do we do Well you just。

You subtract。嗯。So， I actually， let me。Take it a little。Write it a little more。This is a。

V star is just Q star as tilda pi star。RightAnd what we're going to do is that we're going to add a subtract。

F。是。We subtract F S tutor。P star。嗯。Plus， F S tuta pi F。 Okay。

 I'm gonna skip step because like usually what you do is that you subtract and add the same thing。

 right， then that will be a equality。 But now like I'm doing a relaxation。 I'm subtracting one thing。

 but adding another thing。 But I claim that this thing is like the。

 the thing I added the the pair I added here is is not negative。 Why is that。

Pi F is what P F is the taking greedy action， according to F。RightSo therefore。

 when you have both have the form of F， the same state， something。

 pi F is always truth in the action that maximizes any expression of this format。😡。

So that's going to be bigger than this one。😡，Right， so the， the。

 the difference we're adding over here is not negative。 So why do I introduce that difference。

How should I proceed from here。Said someone saying。Triangle。I guess so。 or。

 or what I'm having here is that I have， I'm having four different terms。 I'm gonna now combine them。

 How should I combine them。Sorry， by policy or really like you what you want to like again。

 always remember what you have on the right hand side that you want to prove， right。

 On the right hand side， we want to prove is that we want to compare F versus Q star。

On the same states， on the same ashes。 exactlyact。 That's why you need it。 right。

 So here is exactly what we have， right， So we have this pair。

 which is the difference between  Q star and F on exactly the same state action pair。

 We have the other pair。 again， this difference between  Q star and F on on also exactly the same state action pairs。

😊，Right， so what we get， well， this is just less than or equal to。One of Roman is Gama。

This is just the two times F minus Q star infinitefin。O。Now。

 what's happening over here in this particular step is actually a very crucial sort。

 like a very basic step that you will see again， again in the rest of the proofs， right。

 So essentially so。What， what this proof did is that， first of all。

 it breaks down the long term value difference， right， So J pi star and J pi F， you like， you know。

 if you imagine like what happens when you have the when you have the these trajectories。

 like we are comparing the trajectories where you take actions always according to pi star。

 in the other case， you take actions according， always according to pi F， right， So in both cases。

 you have many different actions， But what's nice about performance difference Lamma is that now it's breaking down into just like one single difference。

 right， So here you have  Q star of s tta pi star， you have  Q star S tta， but pi F。

So here you have like infinite many different actions。

 but here there's only one single different action。

 So essentially it breaks down this long term like effects。

 cumulative effects into something that is just one step that is myopic。😡，Okay， so after that。😊。

We leverage the fact that pi S is extracted from F， right， And if you look at this expression。

 at least in the simplified case， if F is exactly Q star。What's this term？Its 0， right。

 because pi Q star is just pi star。 So you are exactly optimal。

 So that gave us some some hope that if F is sufficiently close to Q star。

 then the greedy action you take over here shouldn't be too far worse off compared to the actual optimal action pi star。

But you need to somehow reflect that in proof。Right， so how do we do it。

 Well we add and subtract the F， which is like， you know， how we actually evaluate these actions。

 like Q star over here is kind of like the real value for those actions。 right。

 We subtract and add our own evaluation and use the fact that our the action we take is greety with respect to our own evaluation。

 And then we get these pairs of differences。Okay。So， you know。

 if you look at how we win from here to to here， we start from like， you know。

 true evaluation  Q star， but different actions。 But then， you know。

 upper bounded with difference between the true evaluation Q star are like， you know。

 approximate evaluation F。 But for the same state action pair。So， so there's a。

There's a general sort of。There's an abstract form of this of this particular step that is actually appearing as homework one in the first question in homework  one in。

 and we actually see it more see it， see it quite a few times in the upcoming lectures。

 actually just next week。Okay。So。So coming back to where we are， right。

 So what we did is that we want to prove policy improvement。

 Montone policy improvement for policy relation to do that。

 we introduced performance different dilemma， which immediately implies monotone policy improvement。

 Then we prove the dilemma。 and then also show that it also help us prove a result that we stated clearly previously。

 but didn't improve right that， you know， what happens。

 So basically performance different lemma helps you you know。

 help you with things whenever you have like， you know， the difference of returns between policies。

Okay。Now， coming back to。Polic duration， right？ So as I mentioned at the end of last lecture。

 if all you have is this result。What we know is that the sequence of policy you get can never go back to itself before you hit pi star。

Right， and that gives this pretty weird conversionvergence guarantee that says if you have a finite state。

 finite action MP， then when you run policy situation， because of this non loop behavior。

 eventually it will converge exactly to a pi star。Unlike valuation， in valuation。

 you can totally just infinitely approximate Q star， but never exactly hit that。Okay， however。

 how many iterations do I need in the worst case in order to be guaranteed to hit pi star。

Does anyone remember？AIn the power of that， right， Because all。

 all we know so far is that every time we get a new policy。

 the policy is different from everything before。RightSo like only based on this information。

 the only thing we can say is that， yes， eventually we we'll guarantee to hit pi star if we have exhausted the entire space of markov deterministic policies。

😡，But how many policies are there in the form of mapping stays two actions？😡。

there's number of actions to the power of number of states。Which has an enormous number。😡，Okay。So。

 so therefore， like you really shouldn't count on this particular result to give you convergence for policy duration。

 although this is the most well known property of policy revision question。Yeah。

 I haven't I didn't improve string improvement。 Like I just stated as given。 And if youre cur is。

 I can。Like， I I think there's a sketch in the， in the notes that you can take a look， okay。

So basically， this result is kind of like， you know， from a practical point of view。

 is's kind of vacuous。 It， it's basically useless。 And， and there forers。

 and if this is all you know， you may get the， you may get the。

Kind of impression that valuationeration is much better than policy durationeration。

 because valuation actually converge much much faster， although it never converges exactly。

 But like who needs an exact solution， All we need is like a good enough， something that is。

 you know， a very high accuracy approximation of Q star and get a near optimal solution。

 But within a very few number of iterations rather than you know wait onto infinity when。

 when you can find the optimal policy in pi star。😊，Now， as it turns out that that。

 that statement about the difference between the two algorithms is wrong。

 So policyeration also have a geometric convergence。That is much less known in the community。Okay。

And I think the rest of the time， I will just state and prove that result。

So what this says is I have  Q star minus Q pi K plus1 infinite norm in less than gamma Q star minus Q pi K。

Okay， so， you know， as I mentioned， like in policy， you get a sequence sequence of policies。

 You can't really measure things in the policy space。

 So you have to measure things in the value space。 So what you do is that you just ask。

 you just do policy evaluation， right， Q pi K plus one and Q pi K are just how good these policies are when you evaluate them。

 And Q star is the， the， the optimal Q function。And what this theorem says is that， well。

 the difference between Q pi K and Q star also shrink exponentially， very similar to value duration。

Okay， now this result is show in the form of Q。 But apparently what we really want is a bound。

 And you can like if this holds， you can immediately show this is like you know。

 gamma to the K times initial， right， So it's a similar bound to the value contraction based the convergence that we've seen before。

However， like what we really want is this one， right， we really want is V star minus v pi k。

 You know， how that shrinks。You know， as gama to the gay。I。

 I want to give you that and just leave that as a， as an exercise if， if， if you're interested in。

And doing that。Okay， so what I would do is to do this proof for you。In the remaining 10 minutes。

And what you see is that， okay， so as you can see， when I， whenever I so far。

 whenever I do approve for you， I basically don't need to look at the notes because I've internalized all the proofs。

 and I have sometimes like in case of performance differencelemma， I have this like visual。You know。

 visual understanding of it that all these like feel very intuitive to me and so I can just confidently like give you the proof。

😡，So so far， this one is the only exception。You' will see that this result is proved based on some very obscure manipulation。

Of。The Bel operators that I myself can't do without looking at the notes。Okay， so therefore。

 if after you seeing the proof， you say， oh， I don't， this proof makes no sense。

 like I can't internalize it， it has no intuitive meaning。😡，You know。

 rest assured is the same for me。Okay， but still， I think it's useful to do it because。

When you see the manipulation of those bio operators。

 like some of the manipulation is pretty interesting and， and actually can be useful。😊，Okay。

 so to prove this。We're going to establish two facts。That we'll be using later。

 One is and hold on like here you， you， we have the superscript subscript nightmares。 again。

 We have T pi K plus 1 Q pi K is always greater than go to T pi Q pi K for any pie。😊，Okay。

So why is that？ Well， remember， T pi F is what is just R of S A plus gamma and expectation as prime。

From S A。嗯。F of S prime a prime where a prime is taken according to pi。Okay。

 so this is the definition of T pi F。 And on the right hand side， you have just T pi。

 you just have F being Q pi K。😡，Okay， now I ask you the question， suppose I fixed S。😡。

What is the policy pi that maximize this expression？😡，No， not pi star， wrong answer。😡，So I mean。

 what you should do is that， well I said if F is fixed， right， so the only thing you change is pi。

 you want you to figure out a pi， the maximize expression。

 you should look first look at where pi appears。😊，Where does it appear？

Where is P on the right hand side？F派 right。Alright， Okay， So you're saying the answer， right。

 So F S prime pi。 So what's the pi that like， so here I'm saying pi， But really。

 like there's a single action。 What action you should take。The greedy action。

 the action that gridly optimizes F。😡，RightAnd if you want to express that as a policy that works for all as prime。

 let's just pi sub F。😡，Right，The greedy policy that that that that the policy that is greedy with respect to F。

 What's the policy that is greedy with respect to Q pi K。In the algorithm of policy iteration。

P K plus one， right， Policy literally works that way。 You have the previous policy。

 You have this Q function。 Then the next policy is greedy policy。😡，This。Okay， so therefore。

 this is always greater and equal to that。Which， by the way， So here is the funny thing。

 This is equal to Q pi K。Right， because。What， what you can say is that if you put F over here。

 So F over here， what is this， This can also be written as max over a prime of S prime a prime。Right。

 and in that case， the right hand side is literally just the。The the。The apartment of operator。Okay。

 so this is getting， maybe getting confusing。So this tells you that for fixed F。

 when you choose the policy to be pis sub F。😡，T P FF is actually the same as the the development Opity operator。

Okay， so this is getting and， and let me ask you a question that probably hope maybe further confuses you if we know that the Belman of money operator is a nonlinear operator。

But the policyxy specific operator is a linear operator。😡。

How can a nonlinear operator be equal to a linear operator。That makes those ass。Or in other words。

 does this tell you that T is the same as T pi F？😡，How many think that T and T P F is the same thing。

No， why， why not， how they differ。Why， why like。This holds for sure。

 but why are the two operators different？Because here， there's only hose when you have this F。Okay。

 and for this to hold， this policy specific operator needs to have pi sub F over here。

 So the policy changes whenever you change F。But here for in the definition of this operator。

 this operator is always the same thing like you always have this max regardless of how you change the app。

😡，But here， if we're treating it as a policy specific operator。

 that operator comes with a fixed policy， but in order for this to hold， whenever you change F。

 your policy needs to change。😡，Okay， so this host， but these two operators are different things。😡，O。

So that's the first fact。In fact，2。We have。T派 k。Plus， one Q pi K less than or equal to。Q pi K plus1。

Okay。So why is that？We can just expand this one。 This is saying R of S。呃，A plus。Gma and expectation。

嗯。Let me see， Q。派 k。S。Pi k plus one。Okay。Now， this is equal to。 I can write it as the expectation of。

Summation of reverse。R sub T。When S1 is。Sorry， here is S。 S1 is S， right。

 So if you look at this expression。 So one thing is that whenever you have a be operator like expression。

 but inside the expectation， this is also a value value function。 Oftentimes。

 you can translate that that into just the expected sum of reverse when you specify a particular behavior。

 right， And that behavior， you can actually read off this expression， right。

 So this is saying you're in state S， right， I mean say the S。

 What's the first first action I'm taking。😊，Is iss a over here， right， then the second step。

 I'm transitioning to S prime。 and from there on。I'm taking action P K plus1。

 This is my second action。 What's all the future actions。Paik， right。

 because here is all the action after this one。Right so therefore I can write this as。S1 equals S。

A 1 equals a， A 2 sampled according to pi K plus 1 and a 3 all the way to infinity sampled from。排期。

Okay， so I have this expression。😡，Now， similarly， you can write Q pi k plus1 as they expected sum of reverse。

 And here you will have S1 equals S the same thing。

 A1 equals a and all the action sampled according to pi K plus1。😊，Okay， now the here。

 the second action is also pi K plus one。 So they're the same。

 So these things only differ starting from step 3 onward。 But here you have Pi K。

 There you have p K plus one。 And we know policy monotone policy improvement。

 Pi K plus1 is always a better policy。 When you have the same state distribution， right。

 In both cases， all the previous actions match。 So you start from the same state distribution here。

 Here you have Pi K for all future actions there you have p K plus one for all future actions。

 So that one is always better。Okay， so。So once you have these two。We can look at what is。

Q star minus Q pi1。 This is what we want to prove。Okay。And by the way， so here， if you remember here。

 although I have an infinite norm。The city inside side is really like point wise not negative。😡。

Right， so therefore， I， I don't need to。 I can pretend that there's no absolute value over here。

 So I can always， for example， make this one smaller and S still holds。So， this is。

Le than or equal to。Well， this one， I'm going to write it as T pi star， Q star。Right。

Because Q star is just T Q pi star and Q pi star is just Q function for the policy pi star。

 which is the fixed point of the Belman policy specific operator for pi star。

So this is actually equality。 But the second one， I'm gonna relax using the thing we we just have。

Pi star， Q pi。 What do we have， So I'm starting with pi K plus 1， which is over here。Right。

 so I'm making it smaller。 So I'm making it actually。啊。Right， so so I I， I get over here。

 and then I can also replace the pie over here with an arbitrary policy pi。So I get Q pi K。

 infinite or not。Okay， so I have， I have Q pi K plus1， which is greater than this one。

 And this one over here is further greater than this one where this policy pi is up to my choice。

 I can choose it to be anything。 And here I choose it to be particularly just pi star。😊。

And what do you do next？Any guess？Why do I write this in this form？

You can't take T out Like T is not like just a multiplication or something。But no。

 you want to take it out， why can't you take it out？😡，I'm looking for one word。😡。

There' is a property of these， like bowowman operators。

Like when have you seen like you have two different functions， but you apply the same Bel operator。😡。

I'm sorry to say it again。They are linear， yes， but we're not looking for their。

 Linear is not the property we're looking at here。Contraction， right。

 So we said that the T operator has contraction。 But here， like like。

 but we also mentioned that all the policies specifically by my operator also have contraction。

 So contraction gives you gamma。Q star minus Q pi k。S是。Okay， again， like this。

 this is one of the very few proofs in this class that I just can write without looking at notes。

 But I think what's the really valuable things here is kind of like give you this new understanding of how bump operator works。

 for example， you know， sometimes for fixed F， the optimal operator can also be equivalent to a policy specific operator for specific choice of the policy。

 which is the greedy policy。 And also the fact that when you have things like a valid value value function。

 And then you have a bump operator applied to it。 it can be actually written in a form that is the expected return under some non stationary policy。

😊，O。So that's it。 And yep， I'll see you on Wednesday next week。

