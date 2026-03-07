# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p34 P34 在线强化学习 -BV1YsZHBZEyM_p34-

OK啊。So we started talking about online R O。 And we know， we。

 we use a very important example and show that many。

Most of the naive exploration strategies you would to think about， such as， you know。

 you uniform sampling all the actions or you know， have some greedy or policy gradient。

 all of them can fail at this like extremely simple problem right at the end of last lecture。

 I also ask like， do you think this is like this hardness is like fundamental。

 That is whether there' is information theoreic that basically no algorithm will be able to solve this problem。

 or it is only specific to certain algorithm。 Then you should be able to solve it。

 And and I remember we get like roughly like half a half of the votes。 And what it turns out。

 like you know。Like， if you really think about the right algorithm for solving it is' really simple。

 Like， you can just do like depth for search and among many like graph treverse algorithm that you can use just to like。

 explore all the nodes。 And then you get all the enough data， you need to actually solve the problem。

 And as I mentioned， as we will see， like。Like the major principle we're gonna use。

 which handles stochastic cases will be will share some like a similar spirit to that best that for search or like like really like like a star search。

 and we'll see that later。But before that， what I need to talk about today is something like more general about how do you even like formulate like online R。

 Right， So in online Ar， like what kind。 So in offline Ar， we have a pretty。

 we know what the guarantee looks like， right， So offline Ar， when you do off policy evaluation。

 we say we have given data want to evaluate this policy。The policy has a true expected return。 J P。

 we estimate it as some number， and we just show that those two numbers are close。Right。

 so that's the our policy evaluation guarantee。 Now for learning similar， we have data。We have data。

 We compute a good policy out of it， right， And there's the auto policy or whatever policy we want to compete with。

 Let's say pi star want to show that our policy Pi hat has has returned J P hat close to J P star。

Right， so that's the， that's the kind of guarantee。 Now for O R， as we said， like the key。

 the key thing is exploration， right， So how do you even like quantify that， right？ So well， like。

 how do you actually you know。Like， before we do any theoretical analysis， we， we need to know， like。

 you know， eventually after you're done with theoretical analysis。

 youll give a guarantee that it is a theorem statement。

 What does that theorem statement even look like。Okay， so so here's a。

Here's a common form of online R。 So what I'm gonna talk about is basically first。

 what's the interaction protocolig， right， So in offline R， in addition to the serum statement。

 before that， you have the assumptions， right， You have offline data and the data satisfyes certain coverage assumptions and so and so forth。

 right， and you're not allowed to directly interact with the environment。 So similarly。

 we're gonna have like this whole package for online R as well， How do you get your data。

 like what kind of guarantee， like， what do you do with the data and eventually。

 what kind of guarantee we hope to establish。Okay， so here's a very canonical sort of a standard form of on R where say for t equals 1。

2，3， all the way to big T。 Now， though that here。So。So here T is not。is not。Not not time step。

So here this， this T is no longer time time step index within each trajectoryas。

 but this is the index of trajectory。 So， so you collect so， let me write it down。

 And so your algorithm picks。Pi T were typically， you know。

 a market policy that map states to maybe a distribution of reactions or sometimes even deteristic action。

 I think for us， mostly it will be deteristic action， but it doesn't matter。 right this way for。

 for now， okay。And then。You just are around。排七 to。Collect。A trajectory。Okay， so let's say as。

We do 0 index or one index。 Let's do， Let's do one index。 Okay， A 1 T R 1 T。All the way to S， H T。

A H T， R， H T。Okay， so as you can see， really like， this is a double loop。

 The outer loop T in indexes the the， the trajectory。

 and the inner loop is that within each trajectory， you have like time step。So in URL R， like。

 especially in this final horizon setting， we're gonna use like small H to， you know， the time index。

And we'll use reserve T for the index of trajectories。Okay。So， and。

 and this is the basically the interaction protocol and how you get data， right， So every round。

 you look at your， all your previous data you have collected。

 analyze them somehow and decide which policy do you want to do next。 Okay。

 then you decide on a policy and just use that policy to to collect a trajectory。Okay。

 after you collect trajectoryas， like you have one more trajectory in your data set。

 you have a slightly larger data set。 You analyze that again and then decide on which policy you're gonna to use next to collect data and so on so forth。

 right， and there will be like total budget， which is like big T。

 which is the total number of trareasuries you can collect。😡，And among this， you know。

 within this budget is all your choice， how to collect the data， right。

 in terms of reflecting how you want to determine the pie T。O。So， that's。That's it。 And。

 and you know， pictorially， you can think of And And so this one is always sampled from the initial stay distribution。

That， you know， we've been using like D 0， or you can use the1。 if you want the， the， the。

 this time index matches the， the， the variable name of the initial state distribution。

 But it really doesn't matter。 And then， as usual， like this。

This initial state distribution will be used to determine to define the expected return that we use to measure the performance of a policy。

Okay。So， and， you know， pictorialally。 So basically every time what happens is that you draw some initial state distribution and pi 1 is the policy you pick in the first in the first trajectory。

 you roll out a H step trajectory， right， And then you restart from the initial state distribution again。

 Now you have a pi 2。 You roll out another trajectory and keeps going on。 So eventually。

 your data is like this big rectangle chunk， which should you think of as the vertical length is the number of time steps within the MP。

 like， say this is a final horizon MP， and the horizontal。

 like the width is the total number of trajectoryjectories you have。

 which typically will be much larger than H。😊，Okay。

So this is like a really like a fat matrix if you want to think about it that way。Okay， and。

 and now in the literature， there is some confusion。 and sometimes either this lens or this lens。

 they are both called horizon， right， because in the previous， So let me ask。 So previously。

 whenever we mentioned the word horizon， which one are we talking about。We're talking about H， right？

 So， however， in the， for example， especially in the bandit literature。

 when people study bandit or Martin bandit or Carial bandit， they don't have this horizon， right。

 because this horizon is just one。 So when， whenever they mention horizon。

 they actually mean this horizon。Now， for me， like to distinguish between these two。

 I'll call this the planning horizon， right， So this horizon is relevant。

 even if you fully know the MP and you just want to do planning， right。

 we still need to do timing programming， like valuation。 And there。

 there's still this notion of horizon that's relevant where you need to trade off like， you know。

 immediate reward with long term future。And this horizon was what I call learning horizon。😡，Okay。

 so this horizon， like this notion of a horizon learning horizon。

 It only exists if you're in the learning setting where you don't know the NP。 If you knew the NP。

 this horizon doesn't exist。 You don't even you don't even need that， right， So this horizon。

 like along this direction， what it represents is that your knowledge of the NP gradually increases as your sample more and more data from the NP。

Okay， so if you have， like， if you have to distinguish between these two。

 I would use the terms like planning horizon versus a learning horizon。Okay。

 now there are some cases where like they can be mess together， especially in the Bayes setting。

 but that that's for another day。Okay， so we have the interaction protocol that tells you how you collect data。

 And would you like， you know， you， and， and you know， you have to decide on the policy you use to。

 to collect each treasy。 Now， finally， the guarantee。 Well， it turns out that in in online。

 there are two different kind of guarantees you can give。1 is of a sample complexity。 Okay， so the。

 what the algorithm does is that after。T， let's say rounds or T trajectoryjecties。

 So let's say I'm gonna use the word round for like each trajectory。 So after T round。

 you have collected all the data， you just output a single policy pie hat based on all the data you have collected so far。

Okay。And the kind of guarantee you want will be you the guarantee you give will be similar to before。

 This is with probably greater than one minus is deelta。 J pi star minus J pi hat is land epsilom。

You want to give this kind of guarantee， right where。With high probability。

 the policy I opened at the end of the day is a near optimal policy where the subopmatic gap is absolutepsil。

And typically， in order to achieve that， you would need T。

 the number of total rounds to be some pull of say in the table setting， number of states。

 number of actions。😡，Horizon。1 over Epsil， the subopmi gap and log1 over delta。

 which is the failure probability。Okay， so now in the large database space function approximation setting。

 this S will go away and will replace it with something else， which we'll talk about later on。 Okay。

 but for Tular， this is like， you know， the kind of guarantee you would get。

And so this particular polynomial， what it you know。

 the particular form it takes is what we call the sample complexity。😡。

 if you establish this kind of guarantee， this is a sample context guarantee。😡，Okay， so。

 so this is the first kind of guarantee that you can establish。

 Well it turns out that there's another kind of guarantee you can establish。

 which is a little bit different。😊，But， and it has some relationship with the sample complexity guarantee。

 This is called a regard bond。Okay， so we'll talk。 we'll first give the definition and。

 and then we'll compare the two。 This is too ugly。 Let me here raise that。Okay。

 so what's the regret bound， Re bound says that like you just interact with the environment。

 right at the end of the day， after big tea rounds， you don't need to do anything。

Becauseuse I'm already evaluating you based on like all those intermediate policies you've been playing。

 Okay， so typically， you will define what call what's called a cumulative regret。 So regret of T。

 which is like the total regret over all those T rounds， which is summation T equals one to big T。

J pi star minus J pi T。Okay， so basically in every single round。

 you play a policy and they're just asking， you know how good that policy is compared to J star。😡。

Okay， as you can imagine at the very beginning， you have no knowledge of the NP and your first choice of pi 1 would be pretty much arbitrary。

 So you will have a large subtimalality gap。😡，RightSo the only reasonable bond you can give it is probably something like VBax or something。

😡，Right， so in other words is a constant。 However， as you get more and more trajectories。

 hopefully you get better and better。 and then youll play policies。 Eventually。

 you'll be playing policies that is pretty near optimal。

 So this gap will be smaller and smaller at the at at near the end， like think of it as like you。

 you'll be mostly playing an ailon near optimal policy。😊，Okay， so， so therefore。

 like what ends up happening is that if you think about。This is T， okay。

 And let's say this is the performance of J pi star。 So this is the optimum policy。

 this is would be hard to say。 So this is J pi star， okay。And。And this the Y axis is J P T。

So initially it's pretty bad。 I mean and as you can imagine， like the roughly speaking。

 the curve would look like this。Okay， and what cumulative regret does is is measuring roughly speaking the。

The area in the of this shaded， the the the area of this shaded part。Okay， so as you can see here。

Well， it's really， so Amy， just to write a formally。 So the guarantee is that。

Was probably greater than womans delta。We have a regret T。Is some poly of， let's say。

 as a log one over deelta times small O of T。 So let me explain that， so。So， so， so first。

 you have some multipliers that depend on the complexity of the problem， Right， So in general。

 we think the larger the state space， the problem is more difficult。 The larger the action space。

 the longer the planning horizon in general， the problem would become more difficult。 But。

 but what's the most the hallmark characteristic of regret bound is that。Eventually。

 they will be multiplied by a term that goes gross sub linearity。Okay， so， so here。

 if you get anything that is subline in T， this is a non trivial regret bound because if you allow linear regret in T。

 that will be trivial， right， because like like if I do nothing。😡，I know this is bounded by V Maxax。

So I always have a trivial regret bound， which is V max times big T。So if I do nothing like。

I don't do anything smart。 I get this。Right， but as you can imagine。

 if your curve goes like this where like your curve like approaches like J pie star in general。

 the size of this area will be like less than like， will grow like a， like in， in a speed。

 like that is a smaller empty T。Okay， so we'll see like， you know， one example later on。

 So typically， without additional assumptions， the optimal rate typically you can get the optimal order you can get for。

 for this is like square root。Okay， but sometimes if your algorithm is not optimal or the problem is predict like the setup has additional difficulties。

 you get like slower rate than this， like T to the two thirds or T to the three quarters。

 sometimes with additional assumptions， you can get better than this。

 like sometimes even like like one over tea or something like that。Okay， but。But， but。

 but the most the typical rate is this。Okay， so one thing this now we can compare the two。

So what turn， what it turns out is that sometimes the sample complexity。

Sble con formulation is called a pure exploration setting。

And the regret bound is called a exploration。exploitploitation setting。Right， so。

 and why is that right， Because as you can imagine， let's start with the regret bound。 Now。

 every pie tea you play has two roles。Right， so the very first row， you're exploring the NP， right。

 So when we talk about that you know， combination relation log， like very bad example， we say， oh。

 you can solve it with like， say DFS or something like a star search。 right。

 So when we talk about that， what we're have in mind is that let's go try to reach every single state and collect enough data。

 And then later we'll be able to compute a good policy。😊，Now。

 when we try to reach all states and collect enough data。

 we didn't think about those like like those policies are particularly just for exploration。

 We're not particularly concerned about how good those policies are。 right， So really。

 like then we're really thinking about the sample complexity setting， the pure exploration setting。

 where the intermediate policy you use in those T runs are not evaluated based on their performance。

 Their only role is to give you good data so that you compute a single good policy at the very end of the day。

😡，Right， so then you're only evaluated by the very last policy you compute。

 and it is completely possible that you may be using pietees that are extremely bad。Early on。

 when you collect the data， but those policies give you maximum amount of additional information every single round to help you know the MP like really well。

😡，And then at the end of the day， you compute a really good policy。😡，Okay， and in fact。

 like even in classic R， this is often this can happen。 like， for example， like Q learning is like。

 which is like the online version of fitted Q is known to be off policy algorithm。

 which basically means that you can just collect data using whatever other policy。

 which may be sub more that you you can get that can be sub up more as long as that provides enough coverage at the end of the day。

 you can use those data to compute your policy as provided by our FQI guarantee， right。

 So in that case， you have very bad policy。 But they give you good information。

 And the at the end of the day， you compute good policy。😊，Now， in the regression bound setting。

 things are more complex because now each part has two rows。😡，First。

 it still has to collect information， right， Because without good information。

 you can compute a good policy。 So those policy has to be information seeking。😡，On the other hand。

 they cannot be purely like information seeking if that means sacrifice for immediate performance。

 because every single round， your performance is being like。Measured。Okay。

 so these policy themselves， especially later on， They can be arbitrarily bad just for the sake of。

 you know， seeking maximum information。 They still have to。 And this is why people say this is。

 this is a kind of like a balance between exploitation and exploitation。 Expation means that。

Your policy has to be good。 You have to compute policy。 That is like reasonably good。

 given all the information you have so far。 But at the same time。

 you can't stop exploring and providing new information to the algorithm because you have to。

Because like what new information you collect using these policies will affect how you can。

 how later policies can be even better。Okay， so in some sense。

 like regret bound or the exploration exportation setting is a more difficult setting。

 And all see why that's the case we'll try to go back and forth between these two kind of guarantees。

 Okay， but any question before we move forward with these two formulations。Right， so。Let me see。

 So typically， if you actually have a problem in practice which like fit online R。

 it will fit one of these two scenarios， right， For example。

 if you're doing something within a simulationim and use online R to train good policy， right？

 And typically， what happens is that like you have a。You have a budget to。

 let's say your boss give you one month to create a really like shiny demo。 Okay。

 so you have to do that。 And at the end of the day。

 you only show the really like cool policy you train at the end of the day。

 then apparently you're in the sample complexity setting。

 because you don't need to show like what's happening like during training。

 or even if like your robot or whatever in simulation is doing something stupid in training。

 you can just say to people that， oh， like you know。

 those failures are like preparing for like later success or whatever， right， So I think most cases。

 you're in the sample complexity setting。 But there are also cases where you actually in the regret regret bound setting where I think the difference here is like eventually when you deploy Imagine that you like outside simulation。

 if you ever deploy something to real。 do you actually deploy like a policy or you deploy a continuously improving system。

Right， if you only deploy a policy， let's say， oh， like I have all these record and you know。

 you collect a good data and give you a good policy that is better than whatever you're currently doing。

 Like， you're in the sample complexity setting， right， and and like for example。

 in medical scenarios， you may like instead of using historical data。

 maybe you actually like also in some psychological settings。

 you actually go recruit volunteers and you know， ask them to help like for you understand human psychology right some aspects。

 like this is also the case， like， for example， in Lms where you're doing R。

 you're trying to align the language models to human preferences and the values and what you do is that you particularly recruit recruit like like labelers or or whoever like you know。

 to help you like label those data points and in that case。

 like you probably like just like looking for sample complexity guarantees because you don't need to optimize the experience of those like labelers。

😊，Right， however， like if you've been like noticed， if you've been using like models like chargeBT。

 you may be noticing that from time to time。C video will give you two different responses。

 and you let you choose which one is preferred。 Okay。

 so this is like basically a exploration exploitation setting。

 right because it's basically doing a little bit of exploration， although not in this form。

 So embedded literature， this is called like duals where like it presents you to responses and ask you for preference because that's easier for for humans to provide feedback instead of asking。

 please rate this response in a range from 0 to 10 because then like if you ask for that kind of like feedback and use that as reward。

 everyone has different rating scale and it's very hard to calibrate and so on。

 But preference signals are much more reliable from humans So in those cases。

 like roughly speaking you're in the regret bound setting because while wants to explore a little bit to help improving system it also cannot ruin your experience because your the user whos using their system So in that case。

 like maybe。😊，like something like a regret bound is a better characterization of the of what kind of guarantee you want。

是。I don't know。 Like， regret is kind of like， if you knew everything， you would play pi star。And。

 you know， later on， suppose you knew what pi star is。 You look bad。 Oh。

 it would have been much better if I played pi star at that point。

 It's just like a name that just got to stuck around as a technical term。Any question？确审。Learning。嗯。

Well， I think， so first of all， this is， I don't know。 what do you mean by measure， Like。

 do you mean like measure what happens in an actual like。In a actual algorithm。

 I think people do plot that， right， So like when you plot learning curve， like， for example， in R。

 like when you're train an agent， like even the empirical papers。

 what people typically do is that like you train things a little bit during training。

 you're not actually like， for example， you're looking at these like critic laws and T laws and so on。

 They're not directly related to J。 But every once a while。

 you actually run your current policy and look at how well it does right， And basically。

 you plot this curve。Like with the only caveat that people typically don't know J high star。

I think that's one major issue。 Like you can't calculate this regret。 right？

 So also like like the only way that you can eventually approach jpi star。

 especially in the large say space function proation setting。

 is basically you need to satisfy a bunch of realizability or even be complete assumptions。

 So those like typically we don't know what they are right。

 So and chances are we don't satisfy them exactly， which means that in reality。

 what happens is typically， even if you have a nice converence curve like this。

 which I doubt you will get with the because always instbilities and so on like like you may get like very。

 very nice and suddenly like performance job or something like it doesn't even look like this even if you get something like this in reality。

 chances are like j star is in this screen curve where this part correspond to your misspecation right Like maybe my function。

 my neural net like can be used to approximate the Q star or pi star just to that extent and there will be small like irreducible error that never。

😊，Goes away。 In that case， like your guarantee， you get to analyze the settings theoretically。

 But your guarantee would look like you have a constant part that correspond to misspecification。

 plus a shrinking， no regret part。Right， so， but in either way， like， you know。

 measuring that in an actual algorithm wrong can be very tricky。坏事。That's a good good question。

 So I think it pretty much depends on the flavor of your algorithm。

 So different algorithm can decide to do things differently， right， for example。

 if you remember like the very early on when we talk about when we first introduce concentration chain qualities。

 we give a example。 So that example is literally a sample complexity guarantee。 But in that example。

 we're using a completely passive data collection mechanism。

 which just sampling actually uniformly and random。 So if you plot our learning curve。

 our learning curve would look like this。😊，Right， but at the end of the day。

 we suddenly boom like all the， all the way of sudden， at the very of the day。

 I give you good algorithm。 I give you good good guarantee， good policy。 As we will see， however。

 if you try to be smart and pursue relatively tight guarantees。Not always。

 but often it is the case that in either way， your're。

Learning curve would look more or less to similar to this。Okay。

But that's not guaranteed because it's， it's your algorithms， it's your algorithm's choice。Now。

 for regret， it has a lot of subtlearies， but， I'll comment on something related later on， okay。

So but related to your point is one question you can ask is like do you need to design completely different algorithm for these two settings or these two settings or measurement are kind of related and here's how that the answer is yes and so basically you can go from sample complexity and let's say regret。

To some extent， you can go back and forth between these two settings。Okay。

 so we'll talk about this conversion for now。 So let's start with the easier one。

 So sample quantum to regret。So in the sense that suppose you have an algorithm。😡，Where。

The algorithm。Satisfies non trivialvi sample guless guarantee。

For any big T or vice versa for any value of Epsil。😡，How can you convert it to a。

So the claim is that I can use this algorithm as a black box。😡。

Without opening it up and look at what it does。I can turn that into an algorithm that achieves nontrial regret bound。

😡，Okay， so that's the clay。 And you can guess how， how we do it。So you're saying like， you're。

 you're dividing the big T into different chunks。 And what do you do， You。

 you run the previous algorithm for a little while and then deploy the learn policy。

Every once a while。 So if， if that's what you mean， you will see the problem， right， because。

You only get good guarantee for regret when you deploy your policy。During your exploration。

 you don't have any guarantee。😡，Right， so if you're like。Chunking or the。

 the management is that you will， you will assign a big chunk for exploration。

 and then just deploy very， very like shortly。Then your regret will be terrible because most of the time you don't have a regret about。

 you don't have regret guarantee G。 You don't have a regret guarantee。

 like for a very small period of time。 And overall， that will still be terrible。

But I think you're on the right track。😡，So the actualgile conversion is pretty stupid。So。

 you just have to。Do a little bit of revision based on your plan。Anyone else wants to have a try。

every time。Deployed at every time step。 What do you mean by deploying it at every time step。

So for to， to get a regret bound， right， So all you need to tell me is basically two things。 One is。

 how do you decide pay T in。Right， and then， and then later。

 you need to have analysis of showing that you have no regret， right。

 And the only thing you can do you have now is a sample complexity algorithm black box。Now。

 basically， what happens is that you feed it into a T。 You give it a T budget， and it。

Gives you a good out it， it， it tells you how to explore during those budget。 And then finally。

 give you a good， good policy。You want big T 1。 You， you can make it big T 1。

 but if T is equal to one， your， your guarantee is completely trivial。Right。

 how can you expect to learn with just a single trajectoryas。Right。You be true。 Okay， so， but， but。

 but the thing is that see， like， this is where like balancing exploration， exploration is tricky。

 right， is when you。Like， maybe what you're saying is that every round。

 I just maybe call the like sample complexity oracle， right。

 but the sample complexity backbox only does exploration。 It doesn't do exploitation at all， right。

 unless you deploy the final policy that it recommends， you don't get any regret on whatsoever。

You don't get any regret guarantee whatsoever。So， so here， like。

 is's asking you to explicitly do in this trade off。 right。

 If you call the sample compressive black box， you get a good exploration。

 But during that period of time， you don't get any exploitation at all。Cool， yeah， yeah， yeah。

 So that's basically where。 So， so the， the idea is extremely stupid。

 So the only the only cave is is not square root。 Okay， so basically。

 what you do is that you just call the。😊，Called the sample complexity algorithm with some T 0 less than T。

 I want to figure out the value of T 0 later on。 So let's say the first T 0 period of time。

 I give it to you。 Go ahead and good， do good exploration。Okay， so then afterwards， basically。

 it'll give you a pie hat whose accuracy， right？ So it's。

 it's the apsilon value will be some function of T 0。 So in general， the， the， the longer t 0。

 the smaller epsilon will become。Right so that's what the sample complexity guarantee tells you。

So this is phase one。 Phase two is stupid， like just deploy。啊。

Deploy pie hat for the rest T minus P0 trajectories。 So in the remaining trajectories。

 you just completely give up on the exploration。 just say， I think this pie hat is reasonable enough。

 Ill just live with that and deploy that because you only get。嗯。

You only get non trivial guarantee whenever you deploy pie hat。Okay。So based on that。

 so first you should have already have a judgment， how should t0？😡。

How large should T 0 be compared to T。Should it be a linear fraction or something smaller。

Does it work if T0 is a linear fraction of T？😡，Why not。Right， because because remember。

 like during this ti 0， you just have the sample on S black box that doesn't offer you any guarantee for how good those policies it uses to collect data is。

 So basically， each round there， all you can assume is that you have Vmax regret， right？

 So therefore the， the first， the， the total regret。T is you first T 0 times。Like Vmax。Okay。

 you already have this part。 So if t 0 is a fraction of T， you already have linear regret。😡，So your。

 your guarantee is， is like completely vac。 right？ So therefore， we already know that T 0 should。

 should grow sublinear in B T， right， And， and you can imagine like what's happening is that when you have a really big T。

 you're actually reserving only a very small amount at the very beginning for exploration。

 And for the majority of the time， you're just doing exploitation。😊，Okay， so plus t minus t 0。 Okay。

 then you， you， you enjoy this， right， because you have the guarantee that with high probability。😊。

This pie head you deploy has Epsilon gap to J P star。 So you can basically put Epsilon over here。

Okay。Where was it？So， so basically like after T0， right， and you， your。

 your sample the algorithm gives you this pie hat。Right， and it is。Absilom， near optimal。Right。

 so literally what this means is。J pie star minus J P hat is less than absolute。

Because that's what this gives you。😡，Right， is， is this guarantee。

 So you're using pi T for T greater than T 0。 Every pi T S pi had。

 Then this term is literally bounded by Epsilon。Right。Like by definition。So。

 so your total regret bound is less than this。O。So let's do a few relaxation。 First。

 we still have t 0 plus so this  one， I just relaxed it to big T， because as we see。

 like T 0 eventually has to be sub linear T anyway。

 So T 0 is just a small fraction of T not even like a linear fraction。

 So it turns out throwing that way won't make things much worse and only makes our bound cleaner。

 Okay， so now for epsilon here we assume that。😊，Assume you have the sample con guarantee is t 0 is order 1 or rhpsson square。

 so this is， so again， just like the the tightest regret bound without additional assumptions is's typically root T。

 for sample con guarantee， as we've seen many times the standard bound。

 the statistical guarantee is one rhpsson square without additional strong assumptions， right。

 because even like when we use hoing to estimate a single scalar。 mean， you have to pay as much。

 right， So this is the standard thing。 So let's just do that。 Now， of course， like here。

 you have a lot of on the numerator， you have a lot of problem dependent constant like number stay number actions and so on。

 we're not really caring about that for now。 And let's say we we do。Actually， we。

 we just summarize that as some numbers C for now， let's say。C over Epson Square， where the。

 where the C can depend on like， you know， S A， H and so so forth， okay。

So then what you get is that then Epsilon can be translated as what， like square root C over T0。

Right。So this is what you get。O。Now， here is something that is slightly counterintuitive。

 So we've been using less than or equal to， less than or equal2。

 But what I'm gonna do then is that I'm going to say this is greater than equal to something。

 which may seem like I'm using the inequality in the wrong direction。

 but it's not because this guarantee so far。've， we've not specified what T0 is。😊，Right。

 T 0 is something that we can decide for ourselves。Okay， so if that's the case。

 then this bound holds for every single value of T 0。Okay， so therefore。

 we can choose the value of t 0 to make the bound the tightest to make it the smallest possible。

So that's why like， you can later do greater angle2 says that when I vary T 0。

 what's the lowest possible value that I can achieve。Okay， does that make sense？

So for this particular form， you can basically do work with it。 I think it's basically AM G， right。

 So I think a typical way to do it is this is T 0 V max plus。You divide this up to two terms。2 T。

 C T 0 plus half of the root T 0。 Okay， so， so I'm splitting this term into two hals。

For the reason that when you multiply these three together， the T 0 will cancel out。Right。

 so therefore by AM GMM， this is greater than equal to three times the cubic root of their multiplication。

 right， when you do their multiplication， you get。T 0 cancel out V max times。Chu。40 square times C。

Right， so， which means that when however you change T 0， this is the lowest possible like is。

It's not even possible at this point， but you can't go below this point。😡。

Because this is always a lower bound of this expression。

And then you can easily verify this lower bound is achievable because， okay。

 so when is AMGM like naality。Sa it。Say louder。Like when everything is equal， AMGM is equal， right。

 in general， all these like mean equal inequalities。

 they're always tied when everything when you take the main， theyre all equal， right。

 So if you look at these three terms， these two are the same by definition， right。

 So you don't need to worry about them being equal。

 then all you need to show is that these two things are equal。 and we can just let them to be equal。

 right So if you let them to be equal。Then t 0 v max is equal to T over2 C。T 0。And would you get。

 you get T 0。 So here you get， I think this is。3 over two。V max equals2 over T root C， And T 0 is a。

Squad root C T over 2。V max， this is a little bit weird。 Let me see I do it， right， Let me see。呃。

Looks bit weird。Anyway， I'll write it for now。 Yeah， I think should be fine。3 over2。Yeah， okay， no。

 no， no， true，2， to。Okay， so basically it tells you like you just set t0 to be this。

 Then all those are equal。 Then this this lower bound is actually achievable。😡，Right。

 and if you look at like what kind of rate do you achieve， Well， this is what this is。

This is a T to the23s。Okay， so as you can see， what is happening is that you give me a sample complexity algorithm whose guarantee is tied in terms of its dependence on that slow。

 I can get a non trivial regression bound。😊，But its rate R T is not really optimal。

 It's like a little subopmal， but still it subline。Okay， is's to the T to the two thirds。Yeah。

 so generally speaking， you will see that whenever you do this conversion。

 it's always T correspond to epsilon because like T is the only。Like， like in the， in。

 in the regret bound， you won't see epsilon， right。

 So cause because epsilon will be like translated into into T， in some sense。O。😊，Okay。

 so this is the first conversion。😊，Now we do the other conversion， which is。

Regred goes to sample complexity。Okay so again， this is saying that you have a regret algorithm。

That if you give me the n t 0， it can it tells you how to explore and gives you pi star minus pi t from t equals2 t to the big T。

 whatever that is is like a order like subline in T。 And again。

 we assume that we get a tight bound that grows subline that grows square root in T。Okay。

 now the question is， how do you get a sample complexity bound。Any a guess。just used the algorithm。

 okay。😡，You， you， you use the algorithm。 then， but then like， you know， for example， Hond。

 you still need to do one more thing， right， You still need to give the final。Policy。Use pie T。 Okay。

 that's a good。 that's a good guess。 So。Just use pie T。

 So well it turns out if you look at this algorithm， look at our guarantee。

 our guarantee is says that the sum of these are small， right， The sum of all these terms are small。

Although in reality， would， we would pretty much expect a curve like this mathematically。

 just based on this， this guarantee alone， it doesn't tell us that the final piety is really the best one。

Okay， so now this， this particular conversion that I'm gonna tell you is also very ubiulous in optimization literature。

 especially in online， online learning and optimization。

 And the kind of guarantee you are looking for， that is， I can just use the very last pie T。

 and it should be really good。 This is called last itererate conversions。

 which is the very strong form of convergence that you don't typically get theoretically。😊。

That's a good point。 That's a very good point that saying that actually， let me think about it。

I think what， what you're saying is that because the average of these guys are so like， okay。

 So so here is the first observation。 I think you're already， you're already little into something。

 So because this is。Because this is a low。 So what we can see is that one over t times。

T equals one to T J pi star minus J pi T is less than O root。Right。

 so if you think about like T as the number of samples， this is like one over a root n。 right。

 This roughly correspond to a one of x on square kind of sample complexity。

 So I think what you're saying is that this means that like because the average like subult across Pi T is small。

 at least one of the Pi Ts has to be like this good。If you can figure out what that party is。

 you can just。Like， output that piety。However， the difficulty is suppose to like， okay。

 so one thing you can do is that let's say you can。

Let's say you can run the algorithm for like some period of time。 Let's say， like， you know。

 you allocate half of T for running the algorithm。 Okay。

 but but then you still need to figure out which one is actually good， right。

 So to figure out which one is actually good， like the one most obvious thing is that you just try each one of them1 by one。

 right， But in order to reliably estimate how good each policy is。

 you need multiple trajecties for each for each policy。Right， so suppose you've used the like。

 suppose you actually do like T 0 of these， then you get T 0 different policies。

And if you want to test each of them， roughly， you need this much。

 like extra budget to just test things out。Okay， actually， that's an interesting idea。

 I think you might end up getting something similar to before。

 So you don't get a tight sample on R and D， but you probably get something not trivial either because in this case。

 T 0 has to be set to be a very tiny portion of T anyway。

 because the number of like extra like samples you need for testing。

 will always be much larger than T 0， which you actually use for regression minimization。Okay。

 but that's a very interesting idea， although we can do much better than that。Okay， so。

You will see the， the very much better than that。 I'm actually doing a little bit of cheating and doing something that you might not have expected。

 so。😊，Okay， so we start from。Let me move this。Move this away。Okay。

 we start from this and do one bit of thing。 So because this term has no dependence on small tea。

 right。So we just move that outside， we have J pi star minus1 number T。T equals 12 T， J pi T。

 less than order one over root T。O。So I think that this basically test this thing again。

 which is basically the average performance of all the policies we have seen along the way is already good enough。

Okay， so therefore， if I can give you a single policy that when you use it。

 it achieves this particular average performance。😡，I'm good。Romize， yes。

 So what you do is that you just。Output。Pi hat is。Uniform。Over pi one。啊，排挤。Okay， so， so here is。

 this is something special。 So， you know， how do you actually run Pyth at at each at each。😊。

New trajectory。S a number I from one， uniformly from one to to big T。

And then the second step is wrong policy pi I in。For this。Entire。出沾水。Okay， so basically。

 what you end up happening is that whenever you deploy Pi hat。

 like when you deploy it means that you're able to draw random trajectories from Pi hat multiple times I D。

 right， and you want like the expected value you get from those I D draws the return to match that particular value。

 right， And this is exactly what achieves that match。

 which means that every time when you get a new fresh trajectory， you first sample a number。

 I from one to big T。And then you that tells you which policy to follow in this trajectory。

 Then along this trajectory， you don't change to other policy。

 You just stick to that particular policy。😡，Right， so then if you just calculate the expected return by a simple law of total expectation。

 you can first condition on which policy you get in each real， right。

 So condition on any like pi I you get Well your or like being that with that I maybe I I can also call it a small T。

 Then your performance is just J I T。😊，Right， in that round condition on that your random draw hit a particular T。

Right， and now， you know that T number is uniformly across 1 to T。

 So the total return is just the average， which is exactly that number。Okay。

 so this is typically what we call like you output a mixture policy。And in particular。

 this is called a trajectory mixture。 So one thing you have to be very careful about is note。

This is a trajectory mixture。 One thing that you might be tempting to see is that whenever you do kind of make is that some people like。

 if you say， oh， I have policy 1 policy 2， I want to do a mixture of them。

 many people would think that， oh， if pi 1 is a mapping from state to action。

 pi 2 is a mapping from state to action， let's just， for each state。

 take their action distribution and mix them together。Okay， so， many people would think of that。

 So it turns out that the。This is called like a state wise。why is。Mixture， which is pi hat of a。

 the distribution over S is one half of pi 1 S plus pi 2 of S。 Now。

 you can actually find an example showing that essentially J pi is not really comebacks in these action probabilities。

 So it could it could happen that if you do statewise mixture。

 you end up with a policy that is worse than both of the policy you use。Right。

 so here what we need is that in order to to， to make a mixture。

 which you want is that you want the mixture policies performance to be exactly equal to the average of the performance of the original policies。

 But that's not given to you by this kind of mixture， right。

 So one thing you can use to see is that if you， if you think about how。

How policy distributions translate to the final performance， right？ So if you remember。

 v pi is equal to I minus P pi gamma-1 R pi。Right， so you can even ignore the dependence of ourumppi。

 Let's say reward is always a only stay dependent。 That's easy。 So the key is over here。

 So when you do the state wise make you're basically mixing P pie1 and P pie 2 in a linear manner over here。

Okay， so you get a half plus half。But then the， so what's the problem， How。

 how does this equation break the nice like linearity here。Why is it the fact that why。

 like which part of this equation make it is such that you can have a mixture policy mixed in this way that is worse than both pi 1 and pi 2。

The inverse， because inverse is。Not linear。Okay。Now， this inverse， if you remember。

 like when you expand that， this is equal to I plus gamma P pi plus gamma P square P plus gamma P pi Q and so on。

 So you have a similar conclusion in the finite horizon setting because in the final horizon setting。

 literally， you can also write V or J pi as the reward you get at first time step reward。

 you get a second time step and so on so worse for later time step reward is's basically like P pi race to the certain power times R pi。

😊，Right， so that power raising the P pie to the power is also long leader。

 which exactly correspond to the inverse here。 That's also breaking these linearity。 Okay。

 so that's what makes it such that doing per state wise mixing of policies is rarely there are exceptions。

 But most of the time is a bad idea in R。Okay。Okay， so another interesting question。

 Maybe it's not the right time to talk about it。 But， but I think it'll be fun to think about it， so。

😊，Like in general， I also see most of our discussion for the online R part will be restricted ourselves to NP。

 And typically， these pie Ts that you play will be， you know， market policies， right。

 mapping from states to actions。Okay， so。Is P had a mark of policy？え？Okay， thank you for cooperating。

 So it's no， okay。😊，The answer is， no。So first of all， like， if you're a mark policy。

 So if you run a mark policy， when you at any time step in trajectoryreasury。

 when you try to decide which action you take， what is the only thing you can rely on。

The current state， right， I mean， in a finite horizon setting。

 maybe you additionally depend on the timeap that's allowed。

 but you're not allowed to depend on anything else。However， if you want to run this policy。

 run it naively， the most obvious sense at a particular time step。

 which information do you need to decide the action？😡，Right， so in addition to let's say these pie。

 these pie T themselves are mark of and let's say even now station policy。

 they depend on current state and T in addition to the not8 T。 Like。

 I think we reserve H for time step within your trajectory， right， you， you。

 you depend on the current state and time step H。 In addition， you need to know this number I。Right。

 so， but this also makes it weird， right， because previously。

 whenever we talk about running a policy， you're only depending on something that is really relevant to the MP itself。

Right， so we say， oh， we depend on the current state。 We depend on history。

 We depend on the current time step age。All of those are things that are directly relevant to the MP itself。

 But this eye is something that you sampled separately， It's kind of like an external variable。

And here's another question。Can you implement this policy in a way that doesn't depend on。

Like these additional external variables that only depend on like internal variables that are relevant to the MP itself。

At least in a way， that never。Like， so if you implement like as is in this way。

 you have to sample this eye at the beginning of the trajectory。

 Now within the trajectory for each time step， you have to remember that external random variable you you pick at the very beginning。

 right， I mean， usually when we say market policies， even random eye policies。

 you will use external randomness。 for example， if you have to sample a random action， right。

 you have a stochastic policy， then in each round， you may need to sample some additional randomness。

 But the thing is that you sample that， you that and you throw it away。

 you never carry something over time steps。😡，Okay， so here' is the tricky question。

 Can you implement this algorithm where you can still sample additional randomness。

 but you can't keep。Any additional randomness in memory across time steps。Can you change state， No。

 you're not land allowed to change state。 Your state is to。 Okay， so in a way it is， but。

If you change state， you can， again， like you can only include things that are inherent to the MP itself。

 You can add I or something into the state representation。But in a way。

 what I'm what what the correct answer is， in a way is also changing the state。 But you're only。

 I don't think it that way， but you can think of it that way。

 but you can only use variables that are only like， you know， relevant。

 directly relevant to the NP itself。You treat state as initial state。

 You treat which state as the initial state。Initial state。 But。

 but then you're modifying the definition of the NP。Right， I'm saying， like。

 you don't modify to the definition of the NP itself。But you still have to do it。

that's you're in exactly the right direction。 Yes， you want to remember them。 What do you do。Good。

 I think you're further along the right track。Exactly， that's correct。So here is how you do it。

 So the way you do it is like at the very beginning， remember， we can sample additional randomness。

 We just have to throw it away at every times stamp。 So the first action is no problem， right。

 We just sample I， take our action， you know， take our action based on I and the first state and slowly it away。

 What do you do at a second time stamp。😊，You look at the previous data in action you've taken infer the posterior distribution of eye。

😡，Sample a new eye from that posterior distribution。

 which may be different from the true eye you sample to begin with， then act as if you did that eye。

😡，In the second time Sir。So it away again。😡，For the third time again。

 But now you have a longer history。Okay， so here's an this gets to like， again。

 like a funny thing that run into on Twitter。 And remember， at some point， like there。

 there's someone on Twitter like complaining that L Ms are all liars。😊，They're not faithful。

 They always lie with no， like， notion of like truthfulness whatsoever。

 An example he gives is the following， right， So I guess most of you have played this game where let's say one person think of a thing in his mind。

The other person tries to guess。 And this person just answers yes and no。 And eventually， like。

 you know， the other person wants to guess what that object is。 Okay。

 so the accusation at L Ms is to say that， oh， like L Ms now now we know that L Ms can have their latent space。

 Like maybe a scratch fat。 They may keep things around， right have some notion of external memory。

 But let's suppose L Ms don't do that。 Okay， so every time L M generate the next response。

 all it can see， let's assume for now is that it's the same thing as you see。

 which is the observable history。😊，Okay， now let's say you play this game with L N。

The accusation goes that the LOMs will be lying because whatever he thinks the object is at the very beginning。

 immediately he will forget about it。😡，And whatever he see he says later on is just to trick you and to pretend that he knows the thing。

Okay。And this is exactly the counterargument to that in the sense that if you think of LMS as a policy。

 which indeed it is。You can have a policy that is completely behaviorally equivalent to one that actually remembers the thing it knows at the beginning。

And the precisely thing you do is the following that is， even if I forget it。

 just by knowing my own distribution of how I would generate that initial hidden concept and also my behavior of like how I would use that and whatever user said to。

 to provide a visible response， I can infer what I said at the beginning。😡，And from that posterior。

 I can sample a latent stage。 I I can sample the that that gas。

 And the the thing is that you don't need to worry about any inconsistency because as you can see。

 like as you get along， if you have very short response。

 there are a lot of variabilities of what that object could be， right， And just by like。

 if you sample something else that is different from what you actually initially imagine。

 like the outsider wouldn't able to be tell， wouldn't be able to tell。

But as your response gets longer and longer， you have a lot of constraints。

 So your posterior also become sharper and sharper。So chances are like later in the trajectory， like。

 you get a very sharp poster。 And pretty much every time youll be sample something like。

 like similar。So at the end of the day， like the claim is exactly this。

 this claim that is running pie hat in this way in terms of the distribution of trajectory it generates。

Like the two ways of of running pi。 One is sample I。 And remember it。

 The other one is what we talk about every time you infer eye and then， you know。

 sample actions later worse， the distribution over observable trajectories is completely indistinguishable between the two。

Okay。And based on that， you will know that this pie hat is a history dependent policy。Right。

 so you actually don't need to like， if you want to cast pie head in the category of policies that we have talked about in this class。

 right，Previous we talked about the simplest form of policies is。

 it is a stationary mark of and deteristic policy。 and you can gradually relax it to say。

 I can allow time set dependence to make it timing homogeneous。

 I can allow action randomness to make it stochastic policy。

 I can further like include additional history variables to make it like general history depend policy。

 So this one is a history dependent， possibly also stochastic policy。Right。

 although when we define it， we introduce this additional。External variable。😡。

We can actually completely get rid of it and put it in the。

In in the categories that we already know where everything is defined only based on things that are directly relevant to the NP itself without introducing any additional external concepts。

Okay。And in general， like that's the， that's already the most general form of policy you can have in MP。

 That is a policy that depends on the entire history so far in this trajectory and sample a random a distribution of actions。

 That's the most general， like any policy， like in the standard setup。

 any policy that you can implement。Can always be written in that form。O。Any questions so far？快是。Yeah。

 so I mean， if if this is all you get， like you don't get any theoretical guarantees， right。

 But in practice， I will probably do that。 now as a mentioned， like this is not only to R。

 like in optimization， you also have this， for example， you have the standard like for example。

 in optimization when people analyze like GD like to gradient in the end。

 even if you have complexityve， like without additional assumption。

 typically you don't get last it conversions。 you don't have the guarantee that the very last point I get is good enough。

 all you get is this average thing Now using complexity， like in SD， you can get something nicer。

 which is you just literally take an average of the x like of the variable you pick。

 like instead of probabilistic mix as we do here， you can really do a mix an average of those vectors。

 But that's because of the complexityveity。 And here， this is precisely because we have this。😊。

We have this issue that cause like， like basically non convexity that we can do that。

 We can do this like， you know， statewise mixture。 But， but when you have conveity， you can do that。

 But even when you can do that， like the backup plan is what we do here。

 you can always do a probabilistic mixture， as we do here。Okay。

 so now there are various additional settings and setups where it may allow you to achieve that。

 for example， So here。Like， there are a lot of subtleties in how we set up this， right？ So。

 for example， when we say like we have a good algorithm in these conversions that we've talked about。

 we've implicitly assumed that these algorithms knows the big tea that you give to them。Okay。

 so it turns out that it actually makes a subtle difference。

 Whether the algorithm knows the total exploration or interaction budget or it doesn't。

 If it doesn't， then it needs to give good guarantees， regardless of what that T is。So in that case。

 like， you will have good regret for every single like time step。

 There will be a much stronger guarantee。 And in that case， I think you probably。

 I haven't thought about it clearly， but I think you might be able to get like last yearerate convergence。

 maybe。Okay， so， so there are all these subtleties that that that can vary differently and it can affect what kind of guarantees you you can get when you go back and forth between these things。

 There' is actually a paper in the project reference list that actually talks about all these like subtle variants of sample ga and regret。

 like whether there is uniform over tea or like tea is given a priorri What the relationship。

 which one is stronger than which and so on。 I think it's called something like uniform pack and so on。

's by Christof Dan around 2014。 I think Yeah， there is like theres a dedicated paper to that。

 talking about these things。 Of course， we're only scratching the very surface of these ideas today。

Okay， any more questions？Okay， so I guess that's it。 And I'll see you on Friday。

