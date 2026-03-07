# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p33 P33 边缘化重要性采样 -BV1YsZHBZEyM_p33-

Okay， so let's start。 So I think today there will be the very last lecture on off R。

 and we'll switch to the online part afterwards， okay， so。So today。

 we'll be talking about marginalized。Okay， so we'll be talking about a variant of a variant of important sampling。

 And if you remember， like the when we talk about important sampling。

 one of the most outstanding issue was that you have this exponential variance that grows， you know。

 grows， blow up exponentially over the horizon。 So there's the question of like， you know。

 can you actually， you know， do something with it。And here is one potential idea。 So first。

 a general idea。 and then， you know， maybe use it in the context of of， of， of， of MP。

 So if you recall like the important sampling was like this， right， So P X， P Q。

Q of x times F of x and expectation under Q is equal to expectation under P of F。

so this is the one liner that summarizes this important sampling。Okay， so typically。

 what happens is that， you know， you have this F of x。

 which is something that you're interested in estimating。

 It's not going depend on every single detail of X。Right， so maybe。

 or maybe I can write it in this way。 that's say is that's a。That says， like， maybe my。

Like data is actually maybe a distribution over X and Y， right， You have many variables。 for example。

 if if you remember， like in the MP and and context band setting。Eventually。

 the function we're interested in estimating is just a reward。

RightWe're interested in the expectation of the reward。

 but under a different distribution induced by a different policy。

But the information we have from the data points are trajectories， which includes state action。

 reward selection， reward， state action， rewardness， and so forth。😡，Right。

 so we actually have more variable than what we're interested in like in the data。So if you like。

 write it down in some fashion， like it it， it basically looks like this， right。

 So there are X variables that eventually the F actually depends on。

 But there are other Y variables that the final function F we're interested in estimating does not directly depend on。

 So in the NP setting， it will be like in all the state action pairs and and so on so forth。😊，Okay。

 but we can still do important sampling in this way， right？ And that's what we've been doing。

 We just say， okay， we have the joint distribution over the entire X Y under you know。

 the target distribution P under and under my sampling distribution Q。 I take the ratio。

 I use that to reweight F of X。 Thatll be a non estimate of of expectation or P。😊。

In this particular setting， can you do can you improve it？😡，Like。

 what's the better way to do important sampling in this in this case。Any idea？So in this case。

 you have a。You have a。X， Y two posts from some distribution Q。

 And this is your sampling and distribution。You're interested in estimating the expectation of F under a distribution distribution P。

But then the F you want to estimate only depends on like the x component of， of， of the variables。

Okay， what， what can you do in this case。You can marginalize right。

 because the thing is that if you think about it， what you can do is that you can just ask， hey。

 what is the marginal distribution over x under P？😡。

And what is the marginal distribution over x under Q， right？ And if I have those。

 or at least I have their ratio， I can just do P of x over Q of x， F of x。Right？And in general。

 what you can show is that if you look at the variance of the importance weights of this marginalized version。

 generally it will always be smaller than or no greater than the marginal the variance of the importance weight when you include more variables。

So therefore various ys， the fewer variable you have。😡，In general， like， it's always better。Okay。

 now the problem is always， as we will see immediately， that it's， it's always nice to do this。

 right， In fact， if F of x is like a scalar variable。

 you can always say how about let me just focus on exactly that variable， right？

 I can have P of F of x versus Q of F of x。😊，Right。

 so the problem is often that when you marginalize， your distribution will take like。

 you need to like marginalize variables。 your distribution P and Q no longer take that nice factorized form。

 And when you look at their ratio， like， you don't know that ratio anymore。 That's often the problem。

 But maybe there are ways to get rid of it。Okay， so let's try to apply this in the MP setting。

 And in particular， let's do the like stepwise important sampling where。

Stwise important sampling where the if I write， again， write down one single line。

 itll be under pi B distribution under pi B。I。Reweight the reward at time， step T with。The you know。

 the probabilityb of pi。Let's say， S。S TAT。呃，品pa。P P B S 0。S 0， S T 80。O。So again， let's for now。

 say reward is deterministic， actually， even if it's not deterministic this。

 this still holds because the reward randomness always at very last， at very end， always cancels。

 right， So this is what we did in the， this would be equal to the expectation under pi of R T。Okay。

So。So this is what we did in the sequential case。😊，But now like as you can imagine， Rt。

 like if Rt is deterministic， what variables will it depend on。😡。

What variables does reward immediately depend on？😡，SDAT， right。

 the state action pair that immediately happens before it。😡，Right， so R T。

 and even if sarcastic that that still holds just like， it has some additional。

 like additional like I D randomness。 So R T。Is only determined by SAT。So what's the immediate idea？

😡，Well， you can marginalize the probability onto SAT T here。

 marginalize the probability onto SATAT T here from your pi B and use that reway R D， right。😡。

So immediately what we have is expectation under pi B。呃，皮牌。呃S TAT T。皮牌比。Of S T A T。二级。Okay。

 so this still holds。😡，But it requires that you know this quantity。😡，Right。

 so now this is kind of like， you know， just like what we do we call these， right If you remember。

 like this is like the T step， like state state action occupancy induced by the policy from some initial state distribution。

 And if you remember like you know， calculating those typically require the knowledge of the M dynamics So like you。

 you can't easily calculate it。 Furthermore， like that was the case。

 even for the trajectory probability before。 However， we show that the ratio like nicely cancel out。

 right， because you can factorize them out and all the unknown quantities will cancel out。 But here。

 this is basically equal to that。 But you sum over all possibility of the variables that you marginalize out right。

 even if each individual term， you have like them cancel out。

 But you add a summ there the summation will you know， destroy that nice cancellation。😊。

So in general， you can't directly- if you only know like all the information we know。

 which is basically pi and pi B， you can't calculate this guy。😡，Okay。So that was the like difficulty。

 Nevertheless， it turns out that this idea is still useful and we'll see you know how you can actually leverage it to to still do our policy evaluation。

😡，So。Now， to introduce these methods。It will be a little bit easier to it turns out we're going to go back and forth。

 It will be a little easier to go back to the discounted setting。

 So in this case we have let's say we go back to the discounted infinite horizon setting。😡。

And we have data S from， let's say mu R from R of S A S prime from P S A。

 So our data instead of trajectories。 Now we're going back to the setting where we have two pole。

 okay so in the infinite horizon discounted setting。

 you can also have a similar conclusion similar to the one above that says J pi。

 which is the thing we want to evaluate， right， So if you remember。

 J pi can always be written as one of Roman as gamma expectation， S A sample from D pi。Reward。

Right where reward is given by the S， right where D is the discounted occupancy。Okay。

 so that was all we have now。In the same spirit， we can do important sampling at the state action level。

 not at the trajectory level over here。😡，This is equal2。

Equal to one over gamma expectation S A from mute， right。

 So we're changing it to our data distribution。 So， and the。

 the reason why that's a good thing to do is that whenever we change things to data distribution。

 if there is something that is straightforward to the function of data。

 we can always immediately estimate it from data。😊，So that's what we want to do。So if we do that。

How can I make this equation ho？😡，What do I need to multiply in terms in front of R to make this equation hold。

You right， something like or。Yeah， but can just look at this and spell out that multiplier that you need。

😡，DI overm， Dpi of what？Right， D S over mu essay， right， So I hope that at this point， like。

 you know， the， the。The， the principle， if important sampling， like。

 you should be familiar enough that， you know， if you see like D pie， you change it to mi or just。

You know， multiply， they're probably racial， and that will be good enough。Okay。

 so now if you look at this versus this， they are basically counter， right。

 So like this is basically that one is basically the finite horizon version of this one where you have the data distribution at the bottom at the denominator。

 you have the target distributions either per like T step occupancy or the discounted occupancy at the top。

 depending on whether you're in the infinite horizon discounted setting or in the finite horizon setting。

 Okay， But here， same thing， we don't know Dpi， right， because if I know D pi。

 I can just directly evaluate this guy。 I don't need to do anything address things anymore。 right。

 so。😊，The question is like， why is this any useful then？Okay。So this one。

 let's give it a name called W pi。Which is the ratio between D pi and mu。

 So one idea is that maybe you can do some learning。

 Maybe can use some learning methods to learn W pi， and then you can plug in over here。Okay。

 so that's one idea。 And O C。 So like， so the setup。你。The setup。

So let's say we are given some W class that captures the ground choose weight function， W P。

 And maybe we can do something to learn W Pi using data。 And then we can just plug that in。Okay。

 so that's one idea。 So as it turns out， it turns out that you。

 you don't actually need to learn W pi。 just the very fact that you have this W class that realizes W pi is already useful。

 provided that you have something else。 You also have the Q function。Okay。

 so what we'll show is that you， if you have these two assumptions。I can give you。You know， accurate。

guaranteeuar for of policy evaluation， estimation of J。Right， so if you look at these assumptions。

 it's very different from the kind of assumption we needed before。

 So before we never used this thing， right， we only need a Q class to try to model Q pi， like。

 say infiniteta Q。 But what what was the assumption we needed over there。We need completeness。

 right like here， this is only realizability。 That wasn't enough。 We needed completeness， right。

 So here， what you see is that like we don't need any completeness anymore。

 but we need two realizability assumptions。 One is Q pi in Q and W W pi in W。Okay。

 we'll see like how you can do that in a minute。 One thing is that if you remember。

When you do our policy evaluation。 and this goes back to what she just said。

 When you do our policy evaluation， you need some assumptions on the function class side， right。

 you know， buildman completeness or reizably or whatever。You also need some other assumption。

 What What is the other major assumption you need， It's not our function approximation。 It's on what。

😡，On data distribution， what do you need， data， what kind of property do you need data？😡。

Do you need data to satisfy？😡，Right， you need this ratio to be bound you need coverage， right。

 So if you look at my setup here， I'm saying that these assumptions are enough。 Also， you know。

 adding on top of that， assuming that all functions in the W class and Q class are bounded because you know。

 later， we're gonna to use concentration inequal。 So boundness of the function classes is， of course。

 needed。 I'm not gonna assume anything else。😡，Okay。

 I'm not going to separately assume some kind of coverage。😡。

But the claim is that coverage is already implicitly hidden here。 Where is coverage。

Why by assuming that I have these。 And let's say， I have。And。Sa呃。W。some CW for all。W and W， and。

For all F。C Q for all F N Q。 right， So I have bonded this。So where is coverage hidden？In the first。

 yes。How exactly？Right， so remember， like when we say coverage。

 the most basic form is the densityr ratio coverage， which is D overm should be bounded。😡，Well。

 even before it's bounded， like it should be finite， right。

 You could absolutely run into a situation where D P over mu is actually unbounded， like infinite。

 like you where you have some essay where mu is 0， but D is non0。 So in that case。

 this like ideal marginalized importance weight function wouldn't even exist。😊，Right。

 so by saying that this function， this very function first exists。 Second。

 it belongs to a function class。 And third， all functions in this function class has bounded size。

 It means that this function itself has bounded size。 So the C W over here。

 which is like usually like a function class bound in this assumption， which we usually， you know。

 never think about it。 But here this actually plays the role of coverage。

 because it has to be greater than equal to the infinite norm of D pi over re over here。😊。

 so therefore， like we did assume coverage， is just like more explicit than before。😡，Okay。

 so let's see how you can。How we can use them to do accurate OP。

 It turns out that you just need a couple of。A couple of lines。 So。

 and the there are two ways to do that。 And we'll see that immediately。 So the first。

So the first method， which is easier to introduce， actually doesn't learn W pi。 Okay。

 so to learn Q pi or try to learn Q pi。 it doesn't guarantee to learn that。 But with W the class。

 the W class as a helper。 So eventually， what you want to do is that I want to estimate a pie using。

😊，You know， expectation。S from D 0。F S。So if I learned some F。😡。

That I think is a good approximation of Q pi to estimate a pi。 What I always do is to just plug。

 plug that into the initial state distribution。😡，Right。

 so that should give me the good estimation of J pi provided that F is a good estimation of Q pi。

 right， So that's what I would do。 So what I would do is that I will learn， like。

 Ill try to learn Q pi。 And let's say my learn function is F。 And this is what I would do。

 And this thing is basically my final error。😊，Okay。

 so now instead of giving the algorithm and giving the analysis， what Ill do is the opposite。

 I'm going to start with the analysis。And then you know。

 do an error thecomposition and you will immediately see like what the algorithm should do。😡，Okay。

 so this is our final error。 So without even saying what the algorithm is， let's start its analysis。

😡，Now the very first thing。 and this is the decomposition lemma that you should have seen a couple times。

 this is equal to one woman is gamma。😊，Excitation。S A from the pi。F minus T pi F。Right， so we've。

 we've used it a couple of times， you know， started from the tabular setting， then to fit a Q。

 We've used this like essentially the more general version of simulation La。

 like many times that says the estimation error and the initial state distribution for any F as a approximation of Q pi is exactly equal to the average。

Bminai error of this function with respect to the T Pi operator under the state action distribution induced by D Pi。

😡，RightSo if you remember how we prove it is like you write D pi as the sum of discounted DT pi。😡。

You know， you sum them up and then you have all these cancelsulation over here， right。

 And then eventually， only the initial term， like you have the initial term over here。

 which correspond to this。 You have all the reward in the middle that correspond to JP。

So this is the La that we use like numerous times， we're going to still use that or it's variant numerous times in the rest of the course。

 so remember this one。😡，Okay， so。Now， I have D pie。 So I like， you know。Like。

 in order to analyze the algorithm， eventually， I'm gonna wrong whatever algorithm on my data distribution。

 So I want to introduce my data distribution mu。 Okay， but now I have S from D P。

 What can you do to switch that Sw from the distribution from D P to mu。😊，What can do。Yeah。

 you just multiply the important Sws， right， So you have a。De pie of S A mu S A。Okay。

 so the other thing you can do is that this one。I can write it as F SA minus R minus gamma F S prime pi。

 where R is from RA。 S prime is from P of S A。O。So now one thing that is very crucial is that if you remember when we did we try to build an error minimization。

 like you know the variant of fitta Q， when we're doing using square loss。

 like if it were the case that like our analysis go through this。

 you can change the TF inside with its empirical version。😡，That will cause double sampling。O。

 the double sampling issue， because the square is a nonlinear function。Right。

 only when you have plain expectation that you can always go back and forth between T pi F。 You know。

 the true Belman update with its empirical version。Because from here to there。

 you just do a law of total expectation。 you condition an SA inside and do a conditional expectation first that r plus gamma FS prime pi will become T pi F。

😡，Okay， so this is this is something that you can only do here。

 but you couldn't do in the Fi Q analysis before。Okay。Okay， so we have that。😡，Let me see， so。Okay。

 so then what this。What， what this derivation tells us is that， you know。

 eventually you want to learn something like Q pi。 you know。

 you learn some F such that this is a good approximation of J pi。 So essentially。

 you basically want this guy to be your objective function。😊，Right， like ideally。

 what you want to do is something like main of F in the Q class like this。 Like if you could do this。

 this would be like the， the best thing ever you can do。

Because literally this cabin isn't literally what you eventually care about。😡。

If you could directly minimize it， you're all done。😡，Right， and in particular。

 like if Q pi is in the class， then K pi will literally set this to 0。

RightEven and even if there could be case where some other function would also set this to 0 that is different from Kpi。

😡，But it's totally fine to find that other function because like even if F is not equal to Q pi。

 if it gives you the same J pi， Well， that's like what you ultimately want， right。

 You don't really care about getting the correct Q pi。 You just care about getting this number。

 right。😡，Okay， so given that this is like the ideal loss function。 You can't literally do that。

 But we'll see you can basically do that。 Now， we show that this is literally equal to this guy。

 So you could just treat this as the loss function for F。😊。

And minimize that over some class Q that captures cube pi。😡，Okay， what's the problem here？😡，O。

 we have assay from mu so we can just directly estimate the expectation from data。😡。

But you still can't use this as a loss function。 Why is that。Like， this is not a loss function。

 even if you replace the expectation here with the empirical approximation from data。

This is still not a loss function that you can actually use in the algorithm。 Why is that。Yeah。

 you have deep height， like this is not something you know。😡。

RightThat was the whole problem to begin with。And here is the next step。Less than or equal to。Okay。

 so so far， basically， we've only， like if you think about the assumptions here。

 we've basically only used the first assumption like Q pi is in the Q class because that that gives that like with that。

 we can turn this into a loss function and search over either the Q class to find whatever we think is Q pi or is equivalent。

RightWe have not used the assumption that we have a separate W class that captures this marginalized importance weight。

😡，Okay， so here we're going to use it。😡，Well， because this is a function that is belong to W class。

I can do a relaxation。Max over W and W class。1 over gamma expectation。 I'll just write mu over here。

W S A times FSA minus R minus gamma。Right。Because like。

 because that function is one of the W of a member in the W class。

 that's our reliabilityizability assumption。 So we can always relax that to like the worst case W in the entire class。

Okay， now if you look at this loss function， it's not totally estimable， right， because here。

 like F is a candidate function that is like potential candidate for Q pi。

 W is like we're taking worst case over the W class。 Both of them are like， no。

You don't have any unknown anymore。 So you can actually estimate it and just try to minimize it。

 You know， find F and minimize it。Okay， but now， that's not the end of story because。

 because if you think about the， So now， like what you really do is that you're gonna。

Put the min over F in front of this， right， So you get a mini max you know。

 program or a mean over F max over W。 And this is your loss function。

 except that you just replace E with like E hat。Okay， so this is your algorithm。 But we did it like。

 but this is not exactly the same as the true objective anymore。 So we did a relaxation。

And could be the case that the relaxation could be vacuous。 It could be trivial， right， So。

 for example， like typically when you have a， when you have a loss function， And。

 and this is very common in machine learning， where to say， oh， have a loss function。

 that is like maybe non smooth or not directly estimated and so on。

 And let's say we let me draw it a different way。Let's say， this is， this is the true loss landscape。

 I would say， oh it's very hard to work with。 So let's do a relaxation。 Well， and， and。

 but if you all you can say is that after relaxation， your。

 your loss is an upper bound of the original loss function。

 That's pretty much meaningless because your upper bound could be this。😊。

Right like if you just spit out infinity。😡，That's an upper bound on any loss function you care about。

Okay， so how can you like， what additional assumption or property do you want this upper bound to be。

Such that it's， it'， it's， it's non trivial。So just having upper bound is clearly not enough。

 What else do you want。😡，Your upper bound is a what？😡，What do you mean by in queue。No， upper bound。

 the upper bound is， so here I'm talking about just yeah， okay， So。

 so here like in this particular scenario， we're talking about maybe you can think about of the X axiss as you know。

 different function F or its parameter in the F class right， So basically different candidate。

 different candidate F will get different loss。😊，Right， but but the true loss， which is。Yeah。

 you know， which is this guy is not accessible。 So we relax it to an upper bound and want to show that this relaxation is non trivial。

So what kind of property？😡，Okay， so I would gonna enjoy it。 So basically， what you wanted。

 like typically， if you， if， if you see like standard machine learning， when you say， oh。

 let's do like upper relaxation， this is the kind of figure you see。😊，Right， so from this figure。

 like， what can you tell， like why this is a good relaxation instead of like， Bo。

 just like a straight like line。 that is like infinity。Why is this one good？😡，It's tight enough。

 in what， well， it's not tight。 Like here， like， for example， here。

 you can have like infinitely wide gap。It's certainly not tight universally。😡，Racio。

 you don't really need that。 right。 So as I said， like， let's say， so here， let's say this flat out。

 And let's say this goes to infinity。 Well， I would say that still， that's a good upperba。Yeah。

 it's tied around the minimum。Right， so then when you optimizeize it。

 youll still find this guy like it behavior over here and its looseness doesn't matter because when you optimizeize over the yellow curve。

 you go here。Right。And another way to see。 So another way to see it is that this。

 like whatever F you choose， whatever F you choose， sorry。Whatever F you choose。

 you can always you know。You， you， you can always evaluate this whole objective on the， on the data。

 right， So up to the sample finite sample error， like just replace E with E had。 And by， you know。

 union bond over W N F plus， you suffer some additional small term。

 So roughly like you can know this term， right？ And we know that this term is a。

Is a true upper bound on what do you care about。So as always。

 you can show that there is one function that can set this term to 0。 You're good。Right。

 because for that function， if this is 0， it's an upper bound on the true like O air。 Now。

 what can the O E air be。Zero right because the O error is like this very first line。😡。

If it upper bound is 0， then this guy is always0， right， which is what I'm drawing over here， right。

 So if we can show that this upper bound。😡，Like there exists some f that evaluates to 0。

 Then you know that that F would also set the O error to 0。😡，Okay， so now looking at this。

Can you guess by construction， what kind of F will set this to 0。Q pi， right， because this thing。

 you can actually bring it back by do a lot of total expectation condition on S。

 This is equal to max over WW1 or minus gamma expectation or mu W times F minus T pi F。😊，Okay。

 so now if f equals Q pi， what is f minus t pi F？😡。

It's zero because this is the Belman error for Q pi。 Q pi satisfied it point wisely。😡。

Qup pi sets to 0 for every single state action here。

 So then the W reweighting doesn't matter anymore。Regardless of how you reweight the thing。

 if your function makes this thing， if if coupon makes this thing0 pointwise after reweighting is 2 0。

Okay， so basically， like， you know， you have coupon pi in this place where it's true area 0。 And。

 but after relaxation for other functions， it may have been like relaxed significantly。

 But for Qpi itself， it's not relaxed at all。 It's still 0。😊，Okay。

 so this tells you that this is type。😡，And you can immediately develop a guarantee by saying that。

 oh， if what I'm estimating is not precisely this guy， but it's a finite sample error。

 and I use hoing or whatever to derive the air bound。

 It's very easy to establish finite sample guarantee for estimating this。O。

So this is the first thing you can do。😡，And if you look at it， again， thiss mini Max。😊。

The other thing is that like， as， as I mentioned， here， like you see like we we use this。

 we use this concept of marginalizing importance ways， D over。

 but we didn't even attempt to learn it。All we did is to。

All we did is to use the W class that captures it and use it as like a helper class to help us actually learn a Q function。

Okay。And。Like in， in some sense， this W class， you， you can say it's a test function class。

 or it looks like a discriminator class。 You know， like， you know。

 that's the terminology you're using， for example， again like， January anniversary networks。Okay。

 so as it turns out， there's another thing you can do， which is quite interesting。 And this is。😊，So。

 so here we use the we did a main or really， we did argument mean over F。Max over W。

 So W is a helper class。 that is is the discriminator。 We ultimately learn F。

 which is the approximation of Q pi。And interesting， you can actually swap the rows。

 You can have another algorithm that tries to learn W。 But now you use the cube pi as the。😊，As the。

As the， I say， the， the discriminator。 And for that。

 I think there is something that we you actually did homework。

 and then well get Ill actually use over here。 So basically， the idea is that。In the homework。

 let me see if I can。Find that。Exactly。嗯。Yeah， okay， so。Okay so。呃。I think somewhere in the homework。

 you were asked to prove this， right， So which is kind of like the， the counterpart of the。

 of the thing that we we we did above that says， suppose I have an arbitrary distribution D。

 Actually， this D doesn't even have to be a proper distribution。 It can be un normalorized。

 It can be anything。 Okay， but like it's supposedly a good approximation of D pi， right。

 So if this is D pi， then this thing will be just J pie。😊，But then this is saying that， well。

 if this D is like anything。😡，Can we actually decompose its you know， the O P air when。

 when you do this plugging estimation， for our purpose， you can think of this D as what as。

As W S A times mu S A， right， because were learning W， hoping that is D over meal。So when w times mu。

 like that's our approximation of D pi。Right， and eventually。

 we're gonna to basically use this equation to estimate J pi。 And then this decomposition tells us。

 you know， exactly what's this error。Okay， so， you know。

 whats this error like is's shown on the right hand side。 So it's an equation that involves cube pi。

 but and and you know。If you remember the lecture from the linear programming class， essentially。

 this equation is some can be proved by some kind of like the Bel and flow equation。 that says。

 you know，No， no like， okay， So if D is actually the D pie， like you will have again。

 like all the kind of cancellation because D pie like satisfies the government flow。Okay。

 so given this， we can do exactly the same derivation as before。😡，So in our case。

 it's suppose now I want to learn W， right？ So after I learned W， I basically plugged that in。To。

 so this what， like after I learned W， if I believe it's a good estimation of D P review。

 this is how Im gonna， how I'm gonna form the final estimation of J P。Right。So now I'm say， okay。

 what is this error compared to the ground truth？Now I can just directly use this。😡。

Use the lemma above by treating the D over there as W dot mu and directly get a decomposition that tells me this is equal to one over ones gamma。

Excitation。Let's say I have mu。 So here I have， whenever I have D， When I change that with mu， I can。

 I can just include W S the weight inside because essentially。

 W dot mu is correspond to the D in the， in the level above。Right， so。

I have a Q pi of S A minus gamma Q pi of S prime pi。嗯。Minus expectation， D0。Q pi of S pi。Okay。

 so this is just the error decomposition。 So again， like， if you want to learn a good W。

 this will be the ideal loss function because you just want to search over the W class for whatever。

 you know， function that sets this thing to as close to 0 as possible。But again。

 this is not a feasible objective， why？😡，This is not object if you can use in the algorithm， why？😡。

Should be pretty obvious。What， well， D 0 is actually easy because you say D0 is unknown。

 but if you have okay， usually like for convenience， we just assume like D0 is known In other cases。

 let's say if your， if your two poles are extracted from trajectory data。

 you have multiple trajectories， the bag of initial states from those trajectories is naturally a good sample based approximation for the true D0。

 So D 0 is easy to get。 You can assume that's no。😊，We don't know Q pi， right。

 So that's the whole thing。 If you know Q pi， you could just like this will give you the correct estimate。

So what do you do now？The same recipe。What do you do now？You have a function Q pi。 you don't know。

 Max over。Yeah， so。Like whenever you see something you don't know， you just relax it。 right。

 We have the Q class that captures Q pi。 Just replace all the Q pi with the worst case function over this class。

😊，1 Romanman is gamma， expectation mu。嗯。W SA， F SA minus gamma F S prime。Minus expectation D0。

 F S pi。河南省。Right， so then in this case， you would do mean over w max over F。 And this loss function。

 Now， this loss function is something that you can just directly estimate from data。Okay。

 because here is the expansion mu and D0， either you have a separate data set or inory data。

 you can just use the initial state in the trajecties to estimate that。Okay， and by the same analogy。

 so here。You know， to show that this bound is tight。

 all you need to verify is that when you set w equals W pi， this holds for any F function。Right。

 just like， regardless of what you use， this is 0。 So let's look at that。 So this is。嗯。

For tighttanness。You have wonder Roman as gamma。Expectation mu。You know，W pi of S。F。

 S A minus gamma F S prime pi。Minus expectation D 0。F S。Okay。

 so now whenever you have expectation on a menu and then you multiply with with W pie。

 you can always change that to。Just the expectation or D pie。Right and。You know。

 then you can show that this thing is always 0， exactly because D P always satisfies the Belelman flow equation。

You write D pi S the sum over T like D T pi with discount factor。

 And you have of all that telescoping。 Then the final thing left is like FSA that cancels at the initial state that cancels with the this one。

 So it's exactly the same logic， you。😊，You， you can show that when you， for the。

 for the true like W pie， this relaxation is actually tight。 Like before relaxation。

 the loss function is 0 after relaxation， the loss function is still 0。😊，Okay， so these like。

 you know， give you like two symmetric ways to， sort of to， to， to， to estimate J pie。

 They use roughly speaking like the same assumptions。 Like， you know。

 its all the assumption over here。And if you think about it， like this is very much related to the。

 you know， the kind of duality we talk about in the linear programming lectures， right。

 that you know， value functions and like discounted occupancy。

 have this like duality like relationship with each other。 right， So and if you actually look at the。

 the analysis and， and the algorithm is pretty interesting because like， for example， here。

 we're trying to learn the。😊，I say， let me， let me see， for example， here。

 we're trying to learn the coupon pi。But eventually。

 like we're trying to learn Q by the value function。 But then eventually like you。

 you actually rely on the help of a this of a weight class that represents a discounted occupancy。😊。

Right and and you know， in this in this algorithm algorithm is the other way around。Okay。Okay， so。

That's a quick mentioning of this other family of methods。And。Any question？O， so we' get a question。

Infinite norm， where is infinite norm？😡，A bound on the function class。 Okay okay。

 So there are ways to improve it。 But for short， right， So eventually。

 you need to in your finite sample analysis， you need to show concentration of this thing to its you need to show the concentration of the empirical estimate of the thing to this population version。

 right， And let's say if you use hoing。 If you use hoing。

 Then the range of the function that you take average over will show up in the bound。😊，Right。

 and the range of the function depends on like。The range of each term over here。😡，So the easiest way。

 like， there are ways to， like， for example， if you use burn size in quality。

 you can actually improve the one root n term to something like the variance of this term。

 not the range。 But do you still have like one n term that depends on the range。 So in any case。

 like， you know， the the， the range of W will just determine the range of this variable inside the expectation。

そしよ。同式。No， no， so its。I think you're mixing up two things。

 When you say like we're not using infinite norm。 I'm saying like， we're not using infinite。 Okay。

 so this is not right。 You're， you're saying that in when we give guarantees and when we measure misspecation。

 we don't measure infinite norm。But here， this is not a missmification。

 This is not the final guarantee。 This is the boundness of the functional class。Okay。

 so it's completely different。Like， for example， when we do fit Q and similar over here。

 we typically assume that all the function F that we use to model Q pi are bounded by Vmax。Well。

 it's the same day。Okay， so that that's separate， okay。Okay， so that's that's for this one， so。

And because we're going to change gear and talk about something different。

 let's take a very quick break and come back in three minutes， okay。Okay， so。Now。

 let's switch gears and start the that that's all for offline R。 So from today。

 we'll start a series of lectures talking about online Ar。 Okay， so in offline R， like。

 which is the sort of mostly like what we have analyzed so far。

 we assume that some kind of like data is given right。

 and it provides whatever coverage needed for our task， right， so， for example。

 if we want to do off policy evaluation want to evaluate different policy， we say， okay。

 we hope that our data provides coverage over， you know， that policy。If I want to do learning。

 we hope that our data in our current analysis， we hope our data covers the occupancy of like all possible policies。

 Now it turns out that that can be relaxed significantly。

 if you watch the talk that I linked a couple weeks ago and there are also materials in the in the link to papers on the course website。

 you can actually relax that to just required the data covered the occupancy of the optimal policy。😊。

You don't need your data to cover like， you know， all all policies， occupancies。

 but that requires like， you know， a different algorithm。Then。

 then the kind of algorithm like the Q that we analyze in class。 But nevertheless。

 you need some coverage assumption on some data given to you。 Now， in contrast。

 online just says I don't need data anymore because now I can directly interact with the environment。

Okay， so now it's both a。Blessing and this occurs curse。On the blessing part。

 if you think about it in offline R， off policy valuation was a big headache right。

 that if theres some policy that is different from your sampling policy or behavior policy。

 that you want to know how good it is， What was ridiculously difficult how to like to achieve that。

 without making like these function approximation assumptions。But in online R。

 suppose you have online access to the environment。 There's a new policy。

 There's a particular policy you care about。 And you say， I just want to know how good it is。

 You know， so hard。 What can you do。Just what？Just try it， right， Just wrote it out， right。

 Ro out a bunch of Monte Carro trajectasories。 Take the average of return。

 Thatll be a good estimate of how good the new policy is， right， So if。

 if there's like a single or a few policies you care about。

 like evaluating them is like not a heart at all。However。

 it also occurs in the sense that now you no longer have that offline data and you can't make assumptions about unit coverage or whatever。

 You can collect data on your own and hope that the data collected you know， is good， right。

 satisfy those assumptions that we need it for offline R。

 because eventually if you think about onlineline R that is。

 let's say we interact with the environment， collect a bunch of trajectories at the very end of the day after you collect all those trajectories。

 you're gonna compute policy。😡，Right。Now， if you think about that step。

 that's basically roughly speaking an offline or step because all the data has been clearly collected。

And you need to compute a give a good policy at the end of the day。😡，Right。

 so then you better hope that the the data trajectories you have collected satisfy whatever assumptions the offlinearrow need。

😡，Right， you always say likes not gonna be like exactly what happens， but roughly speaking。

 that's the idea。Right， and now you can't rely on say， oh， in offline URL。

 I have no control over how the data is collected。 So all I can do is to hope and make assumptions。

Now， in online URL， you are fully in charge。 You are collecting data to batteries。😡。

If the data is bad and doesn't provide the proper coverage assumption you need， It's all your fault。

 You can't blame anyone else。O。😊，So now one interesting thing is that you one thing you would also think is that online is also in some sense。

 as we'll see that's not really quite the case。 closer to practice， right， whenever people say， oh。

 I run like deeperR to train a good policy to train good agent in like environment X。

 Chs are they're doing online right They're doing try and error interaction with the environment and gradually and they will say they are doing exploration and doing all of these right So in a sense。

 like this is like closer to what people do in practice and maybe the first question you should ask is for all the practically used empirical popular algorithms。

 do they have good guarantees。😊，Okay， so now for those who don't like， okay。

 so I'll give you example， among all the algorithm we have analyzed so far。

 there' is one algorithm that can be literally directly used in the online setting。 What is it。

Policy gradient right， because policy gradient just says you maintain your policy parameter for the current policy roll out the trajectory immediately gives you the unbiased estimate of the gradient。

 which is change your policy in the in the direction of the gradient。 roll out another trajectory。

 do another update and you can keep going right And the analysis of that can because you're literally doing SD。

 So whatever analysis SD has， you can just directly apply over here。😡，Okay。

So the first question you might wonder is like， does SGD give you good guarantee。 sorry。

 Does policy gradient give you good guarantees。 And let's say you， like。

 you can actually assume like your policy class has convexity， of all these nice properties。😊。

There is a second kind of algorithms that people use also use a lot， at least use to use a lot。

 For example， we have fit a queue， right， So when you have a when you have given all the data so far。

 you can always run something like fit Q or in practice like Q learning to fit like like a Q function。

 Okay， so now to collect new data in order to do some exploration where people often do is to do like Eon greedy right。

 whenever you are about to choose an action with high probability， you choose the action， you know。

 the Q function tells you to do or you randomize your action choice。😊，Right。

We also talk about in the banded example， like very early on， that in the bandit case。

 if you have a finite number of actions， a trivial strategy to collect good data is to just take actions uniformly at random。

RightIt's not ideal。 It's not give you the sharpest bound， but it gives you non tri bound。😡。

So essentially， like that's the only other thing people do in practice。

 which is whenever you need to do exploration， randomize over the action space。😊，Okay。

 and that probablyably works in band。Okay， so you might think that， okay。

 maybe we can at least derive some nontribal guarantees for these algorithms。

 Let's do theoretical analysis of there。And let me tell you the analysis we're going to do for online R for the rest of the semester。

 none of them will be about any algorithm that people empirically use。

Because here I'm going to show you a simple counter example that will immediately break 99% of the algorithms in any of the popular empirical benchmarks about online R that you can find online。

😡，And this example only involves like a does， it's a tabular problem。😡。

It only involves like a dozen handful number of states。

 and it'll break every single algorithm people use out there。Okay， so let's look at the algorithm。So。

 look at the counter example， so the counter example looks like this。😡，Okay。

 so this example is called combination lock。 So it's a final horizon problem。

 That doesn't really matter。 Like you can probably create an infinite horizon version of this。

 or you have two chains。 Remember， this is a tablet problem。 Okay， so initially， you're over here。

 So this is time step 0，1，2，3，4 and so so forth， right at the very end， let's say you have H。

 big H steps。 at the very end， theres one state that gives you plus  one reward。

 And let's say or you can call it plus 100 or whatever。

 like this is considered a big reward that you want to get right And at the bottom， you get nothing。

 and all the intermediate state， you get nothing。😊，Okay， so， and the deter。

 the dynamics is are fully deterministic for every state in the top chain。

 The top chain is called the good chain。 If you， you can choose to go forward in remain that in the。

 in the good chain or the other action will send you， send you down to the lower chain。

So the lower chain is the bad chain， So if you think， oh， I need to have two actions。

 then let's say both actions have exactly the same effect that keeps you in the lower chain。😡，Okay。

 so do you see the dynamics of this is like， like whenever you happen to choose the wrong action and go to the lower chain。

 you're doomed。 you can't recover。😡，So you actually have to choose a dedicated sequence of actions at the very top row to get a very high reward。

 However， if you have the right policy， you're guaranteed to get the high reward 100% of the time。

 right， What's the optimal policy。Just that stay on the top row， right？😡，Okay。

So now let's imagine like the two kind of so first， let's say， okay。

 so then let's say we do the kind of exploration strategy we did in the bandit case， right。

 So in the bandit case， always we said is like， okay。

 that was like very early on when we first introduced concentration in qualities。 If you remember。

 we did a naive banded analysis that says， let's just first collect data by taking actions uniformly at random。

😊，We get a data and then just form empirical estimate of everything and then report what we think is the best。

 That already gives you like， good guarantee。Right， so let's try something similar over here， right。

 So when we collect data， let's forget about the algorithm。

 let's just randomize the reactions to make sure that every single pass gets like a nonze probability and collect that data。

 And because this is a tab problem， we would hope that our data can cover every single state。 right。

 at least at， at the very least， you need to be able to visit this state to see that it's actually a rewarding state。

 right。😊，Okay， so we collect a bunch of data， and then we do some learning afterwards。😡，Okay。

 so what's going to happen when you take actions uniformly at random。So let's say you start。

 you start from here， right。So with half probability in the first date。

 you're going to stay on the top with half probability you go down。😊，Whenever you go down。

 remember you're doomed。😡，The second step is again， with half probability you stay on the top。

 with half probability you go down。😡，Keep going， what's the fraction of data that actually sees this high rewarding state？

😡，Right。The probability， ending up here is。Exponentially small。You see。

 this is another curse of horizon。Okay。So you say ok 啊 maybe啊。😊，Just uniformly random doesn't work。

 right？ Now， people will say， okay， like in practice， we don't really do uniformly random。

 We're gonna use whatever data so far to do like Epson greedy。

 We're gonna bias our action choices towards those actions that seemingly give us more reward。 Okay。

 so we don't do exactly random。 So they， they hope to say， oh， maybe that can break this。Okay。

 let me tell you， if you do that， it only gets things worse。 So what I can do is that I can add a。

Like tiny amount of positive reward for these bad actions。Now if you collect some data， well。

 like you know， unless you're extremely lucky that you initialize the policy。

 just directly go to there unless that happens if you start with like uniform random。

 like based on the data so far， because you never see this。

 the only kind of positive reward you see are those associated with like the downward action。😡。

And now， like if you bias your action towards those， you know。

 actions that you you believe based on the information so far have higher rewards。

 you actually sample these action even with higher probability。😡，So Epon Grty。

 which is widely used in practice， only makes things worse。Sorry。Because they're like。Like， you mean。

 like， ultimately， what's the optimal policy， Like， why does that not prefer to go down。喂喂。Well。

 I'm just like the changing the like， like problem construction a little bit so that if you're doing Epsom greedy。

 which is biasing your action choice towards those actions that seems good based on the information you have。

 your algorithm actually puts even lower probability。Towards the， the， the， the the final good state。

Oh， okay， so maybe like okay， if you don't like I'm I I'm just okay。

 So let me give you a concrete example of how you， how you do things that that matches what people do in practice。

 one thing you can do is that given some traject you have so far， you can build an MP already， right。

 So maybe like for the part you don't reach， just assume that you get0 there or something like that。

 just to fill out the missing values。 Okay， and given the MP。

 you can compute like something like two star。😊，Okay。

 now what people do in practice essentially is like instead of doing fully uniformly random。

At each state， you put higher probability on actions with higher Q star value in your current NP that you estimate。

Right，But in this problem， because you never see that plus one in the MP you build。

 these actions will always have higher Q value。😡，Okay。

 so that's basically what Epson greedy does in this particular example。 Does that make sense。快ush。

Well， but you don't see that at any reward in the top row as well。😡。

Because you never reached the end。😡，Right， well， the other thing people may say is， oh。

 why not I just stick to the top row， Right？ So one thing I can do is that， for example。

 I can call this action T。 Let's say call this action D for like top versus down or or like whatever you call it。

 But， but like I can randomize their label。Okay， after I randomized over their label。

 that no hour the what I priori know what's that past that keeps me in a good role， right。

 So you actually need to learn。 You actually need to try and and look at the dynamics and figure out like。

 which is which。Right， but how do you know that， Right？ So， so here， look， here I'm constructing a。

 I'm constructing a problem。And because in theory， we want worst case guarantees。

 I'm constructing it against the algorithm。Like you are trying to construct a problem in favor of an existing algorithm though。

You see what's happening？ま、ぐ。What do you mean by one， You mean the plus one over here。

 you change it to something else。O。But again， like you're changing the problem。

 I'm not allowing you to changing the problem。 I'm doing a worst case problem construction。

 That's the whole point。Any other question？Question。Oh， like that's， that's just him remove this。

 It It doesn't really matter。 Like， I draw there just for like symmetry or whatever。

And let me ask you again。 ask you that question。 Okay， let's keep the construction simple。And。呃。And。

Oh earth。So let's remove these like， like misleading reverses。 Okay。

 so let's keep the construction simple， so。This construction is meant to be used against naive exploration strategies like policy。

 sorry， like Epon greedty or just uniform exploration。let， let's see the other thing。

 We also have policy gradient， right， So can you guess what policy gradient does here。

Like will pause gradient obtain good guarantee here？So just for to remind。

 you will see what happens when you immediately see the the the policy gradient theorem， okay。

 just recall the policy gradient theorem。And like all the variances won't differ too much。

 So let's stick with the most。ASt version。 let's say you just do R of Tau， some like gra log。

Pi A TS T。Okay。So imagine you have some initial policy that probably choose some kind of random ashes or whatnot。

😡，And you collect trajectories。And you plug it in over here。 So what will policy gradient do。😡。

Policy gradient will not update its policy at all， why。😡，Because this is zero。

 like whenever you sample trajectoryasy。😡，Like， like。

 as long as your initial policy doesn't hit this guy with non trivialvial probability。

 which means that you're extremely lucky that basically your initial policy immediately hit the right optimal policy。

 unless that's the case， initially， you will not see this state with any nontrial probability。

 So chances are all your empirical trajectories have zero reward。

You're plugging that into policy gradient theorem， this thing is0。😡，So then gradient is 0。

 You don't update gradient at all。 I will get you to this。

 So this also shows you that even regardless of what。

 regardless of how you parameterise your policy nicely and what not。

 even in a small tableular problem， policy gradient。

 when you viewed it from the optimization perspective， the the policy gradient。

 like this optimization problem is like can be noncomx。Okay。

 so you don't get like the nice convexity， even if you parameterise your policy。

 like really nicely question。大る十。Zero reward negative you mean negative1。So。Let me see。Well。

 I would think it。呃。Oh， I see。 Okay。 So the， the claim is that it won't matter at all as well。 Okay。

 so if you， if with overwhelming probability， you never see the plus  one。

 It means that every single trajectory you get end up with negative one。Right。

 so youll be a constant over here。 And if you remember like the grid log pie。

 this thing has a property that if you don't have anything in front of it。

 its expectation is always 0。 right， If you remember the， the policy gradient when we talk about it。

 like the the， the the intuition is connection with policy iteration and the the baseline subtraction。

 it's like you actually need some differentiation。😊，Between different actions。

 like this action has higher Q value。 This action has a lower Q value under the current policy。

 Then policy really knows to move the probabilities towards those actions with higherer Q value。

For now， if whatever action， let's say I sometimes I choose action this。

 sometimes I choose action this， and I can keep rolling out if at the very end。

 it always gives you -1。😡，Then it doesn't matter you don't have any differentiation。

 So in experimentation， you still get zero gradient。😡，Okay。I。All right there。Yeah。

 that's I think that's that's a a wonderful question。

 So we're out of let me just give a quick question。 So there is。 so even in the entireari game。

 you can find problems like this。 I don't know if people remember。

 But in the very beginning when I show like some of the demos you have this little duck trying to cross the road that's pretty much like a version of this where like if you happen to do things wrong。

 you get hit by car and sent back to the beginning like that's another variant of this right without heavy reward shaping。

 like no hour can solve that right And and I was in a robotics PhDs exam PhD exam。

 I think1 to two years ago。 And they were like， oh。

 I'm trying to train in simulation a robot arm to reach a and open it up Okay And I was like what kind of exploration are you doing or doing random exploration。

 And you're doing random exploration， just hoping that a random sequence of actions having to reach the and having to。

😊，out properly。 Now， in practice， what happens is that when people face these kind of what。

 what they call like a scarces reward exploration problem， if the problem is really hard。

 people just give up。Okay， or the other thing people do is basically to like hack the problem in all kinds of ways。

 There are various ways you can hack the problem， including， for example， reward shaping。

 right if you have some prior knowledge that， for example， here I say like in the worst worst case。

 I can shuffle these so that you don't know which wish。 But in a practical problem。

 you don't really shuffle them in worst case， they probably come with some like stay variables and maybe you have some good intuition for some states are actually closer to the goal。

 some states or not。 and just keep adding like additional reward signal trying to guide your agent you know go into that route。

 and the problem with reward hacking which is ubiquitous is that if you change the reward function without a deep understanding of the true dynamics of the problem。

 you may actually change the out behavior。So you see all kinds of problems you'll end up with with reward hacking and practice and that's just one of the side effects where you try to hack the problem to avoid the exploration problem。

On the other hand， I think it's also fully correct that you will see like all of the online lectures we talk about in theory in the upcoming lectures are about these like like they don't explicitly consider this but in order to establish guarantee。

 you basically need to conquer these kind of problems。

 Now there are real practical problems where indeed。

 like reward is not this hard to get from initialization。

 So I think theres a big room of like theoretical investigation where you look at these like hard but not this hard exploration problems。

 There's some recent exciting work in this area。 Unfortunately。

 we're not going cover this in this class， but people are starting to look into those know intermediate formulation。

 Like how can you characterize like different difficulty of exploration。Okay。

 so but that's a good point。But I think still if you were able to handle these kind of problems。

 it's very meaningful because then we'll actually be able to solve some problems that people are currently just giving up。

😡，Like， you don't see people run into it because there is also a self selection effect。

 that when people run into this kind of problem， theyll say， oh， this is not doable。

 Let's just not talk about it。Okay， one last question before we end。😡，How many do you think。

 so this looks like a ridiculous problem that may seem like hopeless。😡，O。Let me ask you。

 do you think this？😡，Like problem construction is what we call whenever you have a lower bound construction。

 it can be either algorithm specific or is information theore。

 So algorithm specific means that it's only hard for certain family of algorithms。

 But it's eventually solvable if you use like smarter algorithms。 Okay。

 if it's information theoretical， lower bound， It means that regardless of what algorithm you use。

 you can prove that no one in the world will be able to solve these kind of problems。

 Which one do you think this is。You thing is。