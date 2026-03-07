# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p12 P12 集中不等式 -BV1YsZHBZEyM_p12-

Okay， so let's。喂。H。好看。Okay。So the system is restarting， let's see if Gwen fixed this， hopefully。呃。

Okay， so maybe I'll just to talk about just a quicker review and some additional remarkss about where we were left。

On Wednesday， right？So we have this concentration in qualities that tells you that if you have a。

Independent random variables is x1 to xn。Then you can bound the difference between。

The empirical main。And the trueing。 So when they're not identically distributed。

 the trueing what replaces trueinging is just the， the sum of the expectations divided by it。Right？

And this is。I pro bound it by。A particular rate。B minus a。 So this is the。

Rangch of the random variables。1 over  to n log2 over delta with。

 with probability greater than equal to 1 minus delta。Okay， so this was the the。

The concentration in qualities。OhSure， so。AndThis still doesn't work。Okay， if Vi doesn't work。

 then we'll probably have to do。Right on whiteboard today。This is very weird why？

So I can correctly project this one， the house computer。And I do get。

The iPad content showing up here。But it doesn't show up here。Okay。N mind， so let me see。What is it。

The red pen， okay， so that would look nicer。Right。好板。Okay， so。Actually。

This looks like just a concentration in quality。From another course， you know。

 actually the few of us who。Like there are a couple like faculty N CSS。

 including me Tong Zhang and Ar Benerji， all of us work on working in M theory。

 and I know that T is also teaching a class over here。

 so it's actually not surprising that they are probably also talking about concentration inequ qualities。

Okay， so and by the way， like all the things I'm talking about today can be found in the course note that has been published on the course website。

 so you can also refer to that。😊，Okay， so now today what we're going to do is to look at the you know application of this in two scenarios。

 one for Mon and bandits， which is going to be very close to what we're going to talk about for tablet RL down the way and then one about。

😊，One about what is it this like a very basic bound for supervisorvised learning。

 which will be useful for handling function transformation later。😊。

So let's first look at the mount band and maybe for short。

So the module bandit can be basically viewed as episodic R R problems。 like， you know， remember。

 like like in episodic R problem， like typically we oftentimes query model as a finite horizon problem。

 right， You start from initial state， Take a few an actions and then an episode ends。

 you restart again and again and again， right， But bandits can essentially be viewed as these kind of problems where every episode has only one action。

 Theres an initial state。 you take an action。 You get a reward and you're done。😊，Okay， and in fact。

 if you， if you actually have an initial state it's called a contextual bandits and multiard bandits is even simpler。

 You don't even have states。Okay， or there's only one fixed initial state。

 and all you do is to figure out which action is actually better。😡，So， so let's do it。 Okay。

 so then amount your band problem is basically specify K distributions。 So K。

 you can also view that as the number of actions。 So that's just the combination that people use in the banded literature。

 So you have K reward distributions。😊，Distributions， let's call it R I  for I equals 1，2 K。

 maybe big K。Okay， so each， let's say each。HRI。Is a。嗯。Is a distribution over， let's say 01。Okay。

 so basically what says is that。😡，You're facing like K different actions in front of you。

 And whenever you take one of the actions， you draw a random reward distributed according to R I。

 if you take action I。Okay。And remember， like we're now into。 So， okay， so if。

 if this is the planning setting， it'll be like tribute to solve， right。

 So planning setting means that everything is given to you。 Everything is known to you。

 So these arises would also be known to you。 So what you do is what you just take the expected reward for each action。

 and then what you do。How do you get the optimal policy？Yeah。

 you take the action with the maximum immediate reward right。

 So it's trivialbute because here when the band setting where after you take an action。

 the episode ends。 So the expected return you get is basically that single reward you get。

 So in fact， we can let's you know， for the planning purposes， Let's define this way。

 So let mu I define as expectation by draw a reward from R I the expectation of the reward。 right。

 So this would be like， you know， when we talk about when you have random rewarding Mps。

 you can always convert it to deterministic reward。

 like this is what you're doing right is then you have the main reward。😊。

And then like we can define a star， which is the optimal action， which is basically agon max。

Over I mu I， right， So if you know all the R eyess or， in fact all you need to know is all the mu Is。

 you should， you should just take the the action that maximizes M I。All right， so this is trivial。

Okay。And then。Let's also define just the the max here。The max I mu I define that as a mu star。

 So this is the a max， the， the best action。 This is the optimal return you get。Okay。

So the the problem here is that we don't know the Rs。

 but we're in this sort of learning setting where you can just pull some arms or like in Monte bandez。

 you also call the actions arms， so you can just pull some arms。

 see the random realization of the rewards and then try to make estimates of these like mu eyes and then make a decision based on your estimate。

Okay， so in general， when you only have a finite budget of like， you know。

 how many number of rounds you can interact with these arms， all your estimates are gonna be。

 you know， only approximate。 So you can't be guaranteed to say I can get the optimal reward mu star。

 but you can say， you know， with high probability。 Hopefully I can get reward that I I can choose an arm at the end that is almost as good as mu the the optimal arm。

 maybe up to up to some small epsilon gap。Okay， so that's the kind of result we're hoping to establish。

Okay， and now technically speaking， so here when you start。

 when you study Martin bands in this fashion or in general， R in this fashion。

 we're actually in this so-called online setting where you， you need to decide two things。

 One is once you interact with all these arms and collect the data。

 you need to decide what do you do at the end。 How do you analyze the data to come up with the final recommendation of which arm you think is the best。

😊，But there is another part of it， which is like how do you connect the data？😡。

So how you collect the data is actually， you know， the exploration challenge。 And， you know。

 in in multi band is， there's also in some settings， there's exploration exploitation。

 And if remember， as I said， like that will be def to the very the second half of this course。

 So therefore， we're gonna circumvent this difficulty by just imagining a very naive way of collecting data。

 So they they， the algorithm。 what it does is just the， let's say， choose。😊，Each。Action or arm。

let's say n times。Okay， so what you do is that for each action。

 you draw in random reward from it and then just form the use the empirical mean as your estimate of UI。

😡，Okay， and for each arm。Fle arm or action I mu I hat is the。Empirical。呃呃，免。Of the。Observed。

Random reward。Okay， so so we' we're， we're thinking about like a extremely naive algorithm where you say。

 oh， let me just devote n samples per action。 So which， which means that for example。

 if I have a big T total budget， I'm just dividing that up to give each action， like N equals like。

 let's say N equals T over K。 if， if T is my total budget。 I'm just divide that by K。

 which is the number of actions to sample each action like， you know。

 with the the exact with the same number of times。 Okay， and then for each action， I get you know。

 N I D rewards。😊，And I take the ming of that to get an estimate of what mui is。

 So I call that estimate mui hat。 And then like you know and then the the final action I come up with is I had。

 which is just the Aax。😡，I knew。 I had。Okay， so that's the action I come up with。😡，And the analysis。

What we want to bound is basically how good this action is。Right。

So when I evaluate how good this action is， what kind of evaluation should I be looking at。

Like how do I turn I head， which is like a like action index into a number that shows me how good it is？

😡，Mu I had， right because mu is the true value for each action。😡。

And now mu I head is like just an absolute value of how good it is。

 how do you characterize how sub sub suboptimal it is。😡，New I hat， and。M有 I。Mux star， right。

 So we want to bound mu star minus mu I hat。Right。Okay， is this clear？Okay， so。Now。

 the very first thing。You， we'll establish this again， like in a few steps。Okay， so again。

 like we're going to establish this using an intermediate result that says。If I have the following。

 that's。With probability greater than one is delta。I would like that for all actions。

Mu I minus mu I hat。Is less than absolute。So this epsilon will need to figure out later。

 This epsilon needs to be a function。Gen， you have N， the number of samples you get。K。

 the number of actions。And， you know， the， delta， the， the confidence。

 the confidence level or the failure probability we want。 And this， this。

 this statement will need to come from a concentration in quality。 So we'll establish this the the。

 the statement later with a precise value of epsilon as a function of these， okay。

But a statement like this was split the proof into two parts as usual。

 one is you need to establish this statement， and second is like how you use the statement to actually bound the final thing。

😡，Okay， does that make sense？😡，Okay， the idea is basically like if n is large enough。

 then all the mus will be reasonably close to mui head will be reasonably close to mui。

 So so I'm actually making decisions based on pretty accurate estimate of how good these actions really are。

 So hopefully the arc max I get out of it is also pretty good。😡，So as usual。

 like if you see me doing this proofs， I usually want to do the second half and then establish the first half afterwards right so the second half is that we take this as given。

😊，And then say。Like can we upper bound this mu star minus mui hat with the Epsilon over here？😡，Okay。

And then we'll establish this one later。😡，Okay， so let's first do the， do the， do the。

 do the second half。 So let's say we have mu star minus mu I hat。O。So we start from here。

 We want to leverage this condition that all the mu eyes are close to Mii hat。😡。

And as you see over here， over here， I only have the true muse。Okay， but and， and， and by the way。

 you should have seen this already。 Like， if you remember like how we bound。

 how we proved this result of like， you know， what happens when you。嚟。

When you use a policy that is greedy with respect to a function that is only approximation of Q star。

 You know how sub optimalmal it is。 So it's exactly the same logic over here。 Okay。

 so here we have the true evaluations， the true muse。But the the actions are different。

 One is the true up fashion。 One is our like， you know， you know。

 our whatever our algorithm recommends。😡，The condition we have is for the same action index I。

 but for different mu，1 is the true mu，1 is the mu I head。

 So what do you do like when you want to analyze this。😡，Like you。

 you first need to introduce something， some additional terms over here。

 What kind of terms do you want to introduce。Right， you want to introduce the hat terms。😡。

RightBecause then like you would get the difference between the true mu and the mu hat。 and ideally。

 you want every pair of mu and mu hat to have exactly the same actionian index。

 and then you can use this condition over here。😡，Right， so let's do it a little bit slowly over here。

 So let's say I have mu star。 So let's say I do mu star， by the way。

 it's just a mu I A star or I star。 I probably should write it anyway a way。 But anyway， it's。

 it's not to right， Mu star is just mu A star。😊，Okay， so let's do。

 let's say mu head of a star plus mu head of a star minus mu I hat。Okay。

 so this is equal because I'm literally subtracting and adding exactly the same thing。😡。

Now what you see is that you already get one pair which match this format is mu versus mu hat。

 but with the same action index。 so you can literally bound this with this condition over here。😡。

But then you end up with another pair where you have mu hat versus mu。

 but the action indexes are different。😡，What do you do over here？You can relax them to be the same。

 right， So this， this part is the same。 plus mu hat， I hat minus mu I hat。 Why can I do that。

Why can I relax this to this？😡，Sa say louder。Yeah， by the definition of the algorithm， right。

 my algorithm chooses I hat to be the actual index that maximizes mu hat。😡。

So therefore a star is optimal under true mu， but it's generally not optimal under mu hat。😡。

My eye had is the optimal one for a you hat。😡，RightSo therefore。

 like I can always relax the bound to replace this with I head。

Then I also have mu had minus mu with exactly the same index。😡，Okay， access。

So this is what this is just upper bound by two times Epsil。That's it。Okay。And as I mentioned。

 like this process， like this substep。We've this is the second time we've seen it。

 and you will see use it again， again， again， again， again， like throughout this course。

 And you do any other like M theory。 like you would do this like again， again， again， like， you know。

 a million times。Okay， so。😊，So then the， the rest of it is to establish。This result， right。

 and in particular， to figure out a like precisely， like。

 what's the value of epsilon as a function of N K delta， right， Because in general。

 you would assume that the more data you have。The more accurate you get in estimating these and the more optimal you can guarantee your muI had to be。

😡，Right， so eventually you want a bound to， you want this bound to be a function of n。

 like in the number of sample， the number of data samples you get for each arm that and， in general。

 you want to go down and go to 0 when n goes to infinity。Right。

 and because we already established that if this is epsilon， this is too epsilon。

 So then all it remains is to concentration inries where this epsilon is replaced by a function of these and it goes down with n。

Correct。O。So now we need to establish this。 Now let's go back to the to the to the setting over here。

 right， So now if we look at a particular arm I， like a fixed arm I。

 what we're doing is that we're drawing N ID sample from a distribution where the random variable is bounded in 0。

1 and we're comparing the empirical mean with the trueing。 So what can we say about this。😊。

We have Hing equality， right， This is the， this is the like the most like a template like condition where like you apply Hbden equality。

 right， You don't even need to do any like a reduction or transformation。 Like。

 this is literally what Hob Ding says， like it applies to。😊，Okay。

 so then it says for anyi or fixed any I， we has with probability1 minus delta。嗯。

Mu I hat minus mu I is upper bounded by。1 over 2 n law n 2 over delta。 Okay。

 so the B minus essay is the range that goes away because here I assume the rewards are bounded in 0 and1。

 So that that range is just becoming one。 and I'm emitting that。Okay， so we have that。

Is that what we need over here。 So can I just let Epsilon to be， sorry， So the N is sample size。

 So I used actually capital n over there。 So it should be capital n。Okay， then is this absolute？😡。

whyhy not？Right， I need a union button， but why is this like this looks like the same as this， right？

😡，Yeah， so this is a very common， this is a very common mistake that people make when they first。

 you know， deal with like concentration inequ qualities and they' uses in machine learning theory is that these two statements are actually very。

 very different。 And if you look at like just in text， how different they are。

 the difference is that So here you have with high probability。

 So this is a single high probability event。 Okay， so this is a single high probability statement。

 And within a statement that says all your like estimates are close to each other。😊，Right？

But this one is says for each shy， you have a high probability statement。

 You actually have like multiple high probability statements。

And if you remember how we talked about this a little bit from last time。😡，Like。

 how do you convert multiple high probability statements into one single high probability statement。

We need， you need a union bound。Okay， now what I would do is that now I， I will like。

 if you remember， as I mentioned， like when you get really like， you know， familiar with this。

 you can just do unit bound in your head， like in this form， but。You know。

 if you haven't deal with this before as a starter， conceptual， you really to avoid any confusion。

 You really want to convert all of these into， you know， those like you know， probability statements。

 So I'll do that once over here。 And， then later on， I'll skip this step。 Okay， okay。

 so what what does this mean， right， So in the more rigorous probability statements。 it means。

Probability that for all I。😡，Mu I minus mu I hat greater than。This threshold out over here。

To over delta。Is less than。Sorry， is less than doubtta， right， right， So I'm inverting this。 right。

 This is a good event。 It's happening with a probability that's very close to one。 equivalently。

 this is the bad event that my estimate is actually off。 You know， is is， is's greater。

 that the error is greater than the threshold I would like to have。😊，But this is the bad band。

 and it happens only with like very small delta probability。😡，Okay， but then as you can see here。

 I have one such statement for each I。😡，RightBut you know， so in general。

 when you're making a theoretical guarantee， like as a theorem at the end of the day。

 you want a single high probability statement， right。

 you just say with high probability my algorithm works。😡，Right， so therefore， you。

 you can't just have like， like all these multiple high probability statements。

 So you need to combine them。 right， So how do you combine them， Well， you see like。

 what do you actually need over here， What do you actually need over here is that。

What you actually need is the probability that for all I。Mu I minus muu I hat。Is， oh， by the way。

 I'm gonna call this deelta prime because there will be a different delta that I'll be using。

 So here are the individual concentration。 I'm gonna call all of these like Delta prime。 Okay。

 so Delta prime， Delta prime， prime everywhere。So what I want is that this is less than epsilon is greater than equal to 1 minus delta。

 right， Eventually， what I want is this。 And I want to figure out what's the right value of epsilon。

 right， conversely， I can also， if you remember， like whenever we do unit bound to combine multiple high probability statements。

 we want to think about the bad events， not good events。

 because the bad events have small probabilities。 And when you add them up in unit bound。

 they still remain small， right， So therefore， I have greater than epsilon and less than。😊。

Les than or equal to Delta。Okay， so what is this， Well， what does this mean， So this is probability。

Union over I。😡，Minus U， I had greater than Epsilil as an event。Oh， okay， okay， okay。 Right， right。

 right， right right。 So yeah， you're right。 So previously you had this is less than like for for all I。

 my， my my estimates are accurate。 When you negate that statement。

 the negation should be there exists any I where my estimation is off。😊，Right。

 so like it also involves like good cash。 It also involves changing the the quantifier from for all to existential。

Okay， and this statement is equivalent to this over here， which is the unit of events that， you know。

 just some of the estimates are off。Okay， then what do you do next？What do you do。You do union bound。

 right， so which convert it to sum， which is less than equal to probability。😡，Mu I minus mu I hat。

Greater than。Absolute times K。 So you get additional like K dependence over here。Okay。

Then what we know is that if you want this to be。So now this， this thing。

Is directly given by the individual concentration inal。 right， Remember。

 each individual concentration inality is precisely just the statement about this probability。Okay。

 so and by the way， that's the way， you know， that's part of the reason why it helps clarify a lot of things when you think of。

 you know， when when you think of statement in this way。

 right because when you think of this with high probability thing。

 you need to somehow like put yourself in this mindset where say， oh。

 usually when I prove mathematical statements， everything is deterministic。

 everything is like for sure， like there's no ambiguity， there's no like whatever。

 But whenever you state these high probability events， somehow it tells you that， oh。

 like you're st something， but this thing actually doesn't hold for sure。

 So it kind of like puts you in like a different mindset。

 you actually need to operate in a very different way。 However。

 when you convert it into a statement like this。This is kind of like， in some sense， like I'm。

 I'm using all the terms like not really strictly and not， you know。

 in a mathematically rigorous manner， but really in a cloak of sense。

 like this is kind of like a deterministic statement。In the sense that muiad is a random variable。😡。

Any random variable would have a distribution。😡，And this is just a statement of what that distribution looks like。

😡，Does that make sense？Like this thing is centered around UI。

 so the error is like a zero main distribution， and we're just looking at how much mass there is in its tellss。

😡，Okay， so therefore， whenever you're stating this， everything is deterministic。

 you don't need to worry about this like， oh， there's like all the things I state are actually not always true。

 they only true with high probably， you don't need to worry about any of this。

 All of these are just deterministically true。😡，Okay。

 so then you can just manipulate it in this space， like with with some level of you know。

 confidence that you usually have。Okay， so you have this。😡。

And this is literally given by the concentration inities this， right， So therefore， like eventually。

 we want this thing to be upper bounded by deelta， right， So we just need。

 we can just let this to be less than an equal to deelta。Okay。

 which means that one thing I can do is that I can just let this thing。

 which is deelta prime to be equal to delta over k。

So I'm splitting delta just evenly across K estimation events。😡。

And each one of them gets Dlta over K。Now， eventually， like。

 I need to back off like an epsilon based on this expression。

 which essentially what happens when you just look at the expression。

 that deelta prime equals delta over K。 This tells you Delta equals。1 over 2 n lo2 k over deelta。

Okay。Does that make sense？😡，Right， so， you know， the other way to think about it is to， to， to。

 you know， run it again through this pipeline in the in the the in this direction， right。

 So if you have epson equals to this， then for each individual estimation event。

 it the failure probably would be delta over K。And then you need all of them to hold simultaneously so you do a union bound。

 so you add up all their failure probabilities。 So it's delta over k times k， which gives you delta。

😊，Okay。So once you are familiar with this and really get really comfortable with this。

 you can skip all these， you， you can now skip the， you know。

 the right writing down explicitly these like probably event。 And you say， oh， free。

 I have K different。 I have K different estimation events。😊，And each of them。

 and I want all of them to， you know， happen simultaneously。 Oh。

 all I need to do is just do a union bound and replace the delta over here with delta over the number of estimation events。

 Is that simple。😊，Okay， but under the hood， like this is what's happening。Makes sense？Okay。So。

So then like， you know， once you plug that in， this is just two times whatever。

 like like one over2 n lo2 over deelta， You have additional K on the denominator。 sorry。

 on the numerator， which correspond to like union bounding over K。 Okay， and the final statement is。

With probably at least one minus delta， this is up boundunded by this。😡，Okay。Oh。

 I think I changed it back。Because I was explaining how we get from here and I temporarily changed it back。

 but I forgot to change it to the final form。Okay。Any questions so far？O。So this is like sort of a。

 if you wish， like this is your first like。Encounter of， you know。

 what kind of learning guarantee can you obtain， Right， So we have estimation。 We have also。

 you know， we have data。 We turn data into estimates。

 We use concentration in qualities to bound how accurate those estimates are。 And then we turn those。

 you know， estimation errors into eventually decision loss。 right。

 So estimation error is these error between mu and mu had for the same index。

 Dec loss is how good I had finally is under the true evaluation mu。This is my own。

 I come up with these terms that helps you remember these concepts。 So this is。

estimationtation error。This is a decision。Los。Right，So and and in general。

 like if you have estimationary in this form， youll pay a factor of two when you convert it to decision loss。

 precisely because of this this kind of。this kind of inequalities and if you want to like visual visualize it and you can visualize it。

 let's say you have I hat， you have a star right and let say let's say the real evaluation is the solid bars。

Let's say this is， this is， if I have a legend， this is a true mu， right， So the true mu。

 like A star is， of course， the highest。 and any other action， including the one you choose， it。

 is generally worse。Right。But then is saying if like。How come did I eventually choose Iha？😡。

It must be the fact that my estimation for I hat is actually better than my estimation of a star。

RightAnd the worst case scenario is that I actually overest I had and underestimate A star。😡，Right。

 and how much like can I overest or underestimateest them Well by epsilon， that's my assumption。

 right， So this is like ailnal， and this is like ailnal。

And they need to cross in order for me to eventually prefer I head over a star。

 so this needs to be higher than this。Okay， if， if it's the other way around， like。

 if appsson is small enough that like even I， even when I underestimate a star。

 my mu hat is still higher than mu than my evaluation of I had， then I wouldn't choose I had。

 I would still prefer。呃，A star。Right。Now， in this case， as you can see。

 then eventually you need to bound the difference between these two right so that's the decision loss。

😡，And as you can see pictorially， that is just upper bound by this plus this。

 because this bar is higher than this bar。So you get a factor of two over here。Okay。

 so that's kind of like a visualization of what's happening。Okay。

 so so this is a marker bants and as you will see like this analysis over here has a very sort of how to say a very tabular flavor。

 and indeed it will be the kind of tabular analysis we're going to do will be very similar to this at least in terms of concentrations。

😊，Now what来坞。Then give you the next example of how you apply concentration in qualities。

 It actually directly addresses function transformation。 when you have like very large space spaces。

 So this is like supervised learning10，1， okay。😊，So。So what's the supervised learning problem， Well。

 the supervised learning problem is that suppose I have input space X。

And let's say I'm making prediction into like， let's say I'm doing binary classification。Okay。

 I'm telling whether there's a cat or not in in the picture。 Like。

 so think of x as the space of images。0 means no cat。1 means cat。Okay？Okay， so。

And then we have a hypothesis class， like usually in learning theory we use script H。

Which is a subset of all possible。Mapps from。X20，1。Okay， so think of H as something。

 maybe like you know， all the possible predicts you can come up with giving a fixed neural architecture or things of that sort。

Okay。Now what we have is that we have data。😊，Data， we have a IID。X，IYI。From some。嗯。

From some distribution， like P X， Y。 So we have some joy distribution over the input space and the output space。

Which is like， you know， how you get data， you， you get like image label， image label， image label。

 you get a bunch of these。And what you want to do is that。Really， what you want to do is to say。

 okay， let's say define H star。 This is often called the。okay， so this is like a， you know。

 the really like optimal predictor in high side。 If you have infinite amount of data。

 this is Arc May。H in the hypothesis space。An expectation。This is an indicator。呃，HX。Notに口 too。Why。

Right， so what this is saying is that I'm defining H star to be like one of the hypotheses in my hypothesis class。

 such that it minimizes the like， so the expectation here is with respect to the joint distribution。

 right， So that that has the what is this。 This is like I'm drawing an X。 I'm drawing Y。

 I'm making prediction of what Y is from based on X using a predictor H。

And this is whether like my prediction is correct or incorrect。 If it's incorrect， I get one。

 If it's correct， I get 0， right， and taking expectation， this is basically the error rate。

 the true error rate of some hypothesis H。And I'm looking at the entire hypothesis class and I'm looking at whatever one that has the has the lowest error range。

😡，Right， so， I mean， in general， like this thing， like the。

 the main value over here is generally non zero， right， For example。

 it could be the case that the labeled itself has inherent noise。 Sometimes like， like。

 let's say the label come from human labeling。 Sometimes the label are just wrong。

RightEven if you have like the best predict， right， and the other part of the why this is maybe non0。

 like， for example， let's say even all the labels are correct。

 But maybe my hypothesis class is like very simple。

 Let's say I use the linear classifier or something。 They just can't represent exactly the true。

 you know， optimal decision boundary。😊，Or the optimal classifier。 Then this also won't be zero。

 but this is kind of like the best I can do if I have infinite amount of data。😡，Correct。

So then what I hope to do is that I hope to do， you know， as as good as this， right， So。

 and what I'm going to do。 Well， all I get is like。F amount of data for I equals 12 n。

 So I only have n data points。 So all I'm gonna do is to do like what we call EM。 So we got an H hat。

Is arguing。H and H。Expectation hat。Your x not equal to y。Okay， so basically， I。

 I estimate the the I can estimate the empirical error rate。

 which is basically training error rate based on the n samples I have and chooses the H that minimize it。

 right， So this is defined as This part is defined as1 over N summation I equals12 N indicator whether H X I is not equal to。

外卖。Right。So basically I say， okay， look at my hub class for each one of them。

 it incurs certain error rate on the finite data I have。

And I'm just going to choose whichever one that looks the best on my data。😡，Okay。

 so now this is like a very abstract description in some sense of like， you know。

 how supervised learning learning works， because in in in actual reality， like you cant。

 you can't always exactly find this minir， right， because it involves optimization。

 And when you get a new end or something like that。 like you may get non conve optimization。

 which means that you may not find like the the actual know global minimum for your empirical objective。

 So we're skipping that。 We just say， let's say I have some magical optimization black box that helps me find the empirical minimum。

😊，The global minimum of the empirical objective， what can I say about its generalization behavior？😡。

How well does this H hat performs？😡，Comp to H star。So eventually once you bound。😡，Ex of。H hat of x。

 not equal to y。Minus expectation。H star。Not equal to y。Okay， so this is what we want to buy， right。

 So this is the lowest possible error rate among all hypotheses that you have。😡。

And this is whatever one H hat that I choose。 And this is the true error rate it concurs， right。

 So here the all these expectations are the true expectations in in the distribution。 So。

 so this is basically your generalization error rate。

And this is the best possible generalization error rate you can possibly get and how what's the difference。

 right， You want this to be as small as possible。 If you are able to identify exactly H star。

 this gap will be 0。😡，Okay， make sense。Okay， so how do we do this？Okay。

 youre going to think about it a little bit。So。one question first。😡，You know。

 whenever you see this thing， which is expectation of indicator。

 there's usually a simpler way to write it。 What's the expectation of an indicator of event。

It's the probability of that， right？ But yes， exactly， this is just the probability under P of X， Y。

 H of x not equal to y。Okay，However， I choose to rise the error rates in the expectation form。

 not in the probability form。😡，For reason， okay， so here's the thing。嗯。So。

 let's say what we call this。We call this error of H star。We call this the。Air of H hat。Okay。

 so just as a shorthand。 So， so the error is like the true air rate， you know， on the on the。

 on the population level。Okay， so here' is the guy。 if we fix H。AH。Okay。

 and let's look at the empirical error rate， which is1 over n summation I equals 1 to n。

Indicator of Xi， not equal to Yi。Okay。What is this。

 like what kind of tools can you think of that applies to this quantity？😡，We have。

 we have the average of the indicator that depends on the single data point， X I， Y。This is the like。

 see， like just think this is some random variable that depends on X， I， Y， I。O。

And is a random variable because all the X， Y I themselves across different I are Id。

 So this whole thing as a function is also random variable that across different eyes。

 they are also Id。😊，We're taking the average of these I random variables。😡，What do you do？

You can do harvest， you can do concentration in qualities。😡，Right， now， let me ask you。

 what's the expectation of this。Okay， so first of all， I have the average of I random variables。

 So so here everything is identically distributed。 So the trueing is just the expectation of whatever inside。

😡，Okay。So what's the expectation of this， Do we have a notation for that already？😡，You know。

 the error rate， right， So minus。A of H。How playing in quality。 Okay， less than。1 over2 n。 again。

 the range goes away because we know that so， so now the individual variable is this is's an indicator function。

 So it's either 0 or one。 So the range is just one。Okay。Lwing to over deelta。O， so。

Fix age with probably。我们道。Okay， what do you do next。So remember， we have。For all。

So this is like for in each individual age。Right， so I're going to say。

 so for the purpose of this analysis， we're going to make a very simplification assumption。

 which is why this like 101。 we're going to assume that H is finite。😊，Okay。

 and it has a finite cardinality。 I mean， in general， it's not gonna be the case， right。

 This is like， if you use neural net， like H correspond to like each different weight set of weights in your neural net correspond to a different predictor。

 But that space is a continuous space。However， in many cases， it can be。

 It can be reduced to the finite space。 And as a big argument， you can think of， say， let's say。

 conceptual， you discretize the space of all possible weights。And then you basically get like。

 you know， a finite set of you know， possible parameters。

 We'll talk about it later once we prove this。 But for now， let's say Asia is finite。Okay。

 what can do？Somewhere over here。H hat。 No， we're not at H hat level yet。 So the goal here is that。

 okay， so if you think of what happens before with the the mararian bands。

 we first have the estimation guarantee concentration quality for each individual arm separately。

 Then we use the union bound to make it such that our estimates is accurate for all arms simultaneously。

Okay， so here like what's the analogy over here？😡，Use un bound to， again。

 like swap the order between these two things， right， you want with high probability that that my。

 my training error for an arbitrary hypothesis is always close to its true error rate。

 like for all hypoes simultaneously。Okay， so therefore。We want to swap the order。

 So now I'm gonna for all H and H。 So how do you modify the bound to reflect this change of order。

Right， so K， but K is the is that thing from the previous thear band scenario， right。

 So basically it's like how many estimation events you get。

 you need to split your delta across all those events。And then change your bound accordingly。

 So you don't have K over here。Yeah， size of age， right， how should it appear over here？😡，2 H， right。

 Because really， what's happening is that you're just dividing the delta。By the size of age。Right。

 but now if you're getting really familiar enough with this， like H should just appear over here。O。😊。

Now， the rest of the story is。Exactly the same as before， right， So once you have this。

 you can do that， which is。A， so， let's call this air hat of H， right。

 So you have error of H hat minus air of H star is。Less than or equal to。

So what kind of term do you want to introduce over here？A hat， right， So you want to minus。

Air hat of H hat plus air hat of H star minus air hat of。H sorry， true error of H sub， right。

 And just double check。 Why can you introduce this， right。

 Because we know that H hat is what we call the this， by the way， this formulation is called E RM。

empirical。Risk。Minimization。This is just a fancy learning theory way to say that we've tried to find a like predictor that minimizes training error。

 So for some reason， like， I think a learning theory in here is some fancy terminology from statistics that oh。

 if you， if you can spit out this acronym， like E R M， people say， oh， like you're in our circle。

 like you're a learning theor like， So if you want to pretend that youre learning the。

 whenever you say， I minimize training error， say I do E RM， empirical risk minimization。😊，Okay， so。

 okay， so what you do， right， So because I'm E M。 So H hat actually minimizes like airhead， right。

 So this term， like without a negative term will be smaller than this term。😊。

RightSo I'm subtracting a small term， adding a larger term。 So overall， this is less than equal2。

Okay， and then what， you just have this， which is a probability by two times。To N， lo in 2。

H over deelta。Okay。Okay， so。呃。A couple of。A couple of comments on this， so。

If you look at the final result like。Like compared to the， you know， we have an extra term。

 which depends on the size of H that actually reflects the union bar。

RightNow in the context of supervised learning， you can also argue that this is essentially a sort of a theoretical explanation for overfitting。

😊，So if you actually use a larger hypothesis class， then this term will be larger。

 so your bound will be get worse。😡，Right，And this is what happening like， you know， in the standard。

 like， you know， you know， more classical framework of supervised learning and statistical learning。

 when you have like very large hypothesis class， you run into the overfitting issue。

 And this is what's happening。 And of course， like these kind of bounds can be sometimes loose。

 So you know， like maybe it doesn't really apply in the over parameterization regime of deeper learning theory。

 and so on so forth， you need more advanced tools to tackle get tighter bounds for those scenarios that actually explain the empirical phenomena。

 But this is kind of like101 level。 know， you're starting to address empirical phenomena such as overfitting in theory。

😊，The other thing to think about is that the dependence on H。

 the size of H or cordality is logarithmic， right， up to a square root， right。

 So you can think about what what it actually correspond to。

 like in terms of roughly speaking in in a more practical scenarios， right。

 So think of let's say your your predictor is parameterized by some the。 for example， you have your。

 let's say your H is equal to some。😊，Something like this。RightSo you have some parameter theta。

 Each theta determines a particular predictor， and you have some space of the。

s let's say this is part of RD where D will be the number parameters you have。Right， so for example。

 if you have like a neural S， then D will be the number of like connections。

 So each individual weight， each weight will be the number of weight you have is like D。

So your parameter， a whole set of ways， like a model。

 a trained model is just a specification of the value of theta， which lives in RD。😡。

Now if you think about like under that rough you know conversion that I just talked about。

 you can think of roughly speaking， do a finite approximation of the space。

 which means basically do a disctization over the the space。Right， so for each for each weight。

 So if your theta is like theta 1， Theta 2， blah， bh， theta Theta D。 and for each value， you can say。

 okay， I just do disization。And let's say it has some range。 Then each for， for each coordinate。

 I can take roughly one Epsilon。 So， I mean， the Epson is not that epsilon。

 So let's say this is the epsilon that's correspond to discretization。

Okay I have one over Epsilon discretalization number of possible choice for each coordinate。😡，Now。

 roughly speaking， according to this calculation， what's the cardinality of this space after discretalization。

Wanted epson to the power of the。😡，So that's an exponentially large space。😡。

So that's kind of like pretty scary。 right， You don't want to pay like exponential dependence over here。

 But the good thing is that here you have logarithmic dependence。So once you take log。

 well log will just take care of。 So overall， the the size of data。Like after disalization。

 it can be think of as this。Right， and this is just a H。Now。Now， when you take log of this。

 you get log1 over discqualization error， so you have a log dependence on something that is pretty much insignificant。

 but the main thing is that you have D， but instead of exponential dependence。

 you have a like square root dependence on D。😊，Okay。

And D is like a number of the number of like the number of the dimensionality of your parameter space or number of ways or number of three parameters in your model。

😊，Right，And this should match the intuition， especially， you know， before the like deep learning era。

 when you're doing things like with simple， like linear models in small， low dimensional feature。

 small data regime， there's often the， you know， empirically， there's the rule of thumb that says。

 well， if you have a model that with， you know， some number of parameters。

 roughly speaking the number of data points you need is usually a constant times the number of parameters。

 Okay， and this is， you know， essentially what's happening。😊。

OkayAnd actually this disctization argument， in some simple cases， for example。

 if you have linear models for regression， we can actually make that you know precise and which we will see again in the later half of the course。

 But for now we're just leave that vague and just to provide some intuition for why this kind of bound is reasonable。

😊，And as you can see， like， you know， you， you， you see the very first generalization error bounds in learning theory。

 but under， you know， the underlying mathematical mechanism is nothing fancy。 Libterly。

 its just concentration in plus un bound。😊，concentrationcentration音过了一点，你永力帮 take。You know。

 goes a long， long way in many places。Great questions。Yup。Right， square root of D。Well， no， no no。

 but but thats like that's a sample complexity statement。

 that's like how many data points do you need right， but see like your N is also in the square root。

😡，So it's one over to n。 So when you say， okay， I need epsilon accuracy， How much data N do I need。

 Well， because it like n always shows up as D over n， these two things always show up together。

 So you want that thing to be， you know， to a certain degree。 So it's always gonna be， you know。

 n divided by D needs to be， you know， a certain value。

 So that that's kind of like explains what happening。Okay。Now。

 I should say like the other thing is that this kind of argument is often called a uniform convergence that says like you know essentially。

 I'm actually implicitly speaking， evaluating all hypothesis in my house class like accurately for all hypothesis in more like advanced learning settings。

 this may not happen， right， for example， like if you're dealing with neural net and so on and so forth。

 but oftentimes like there are certain advanced analysis that actually reduce to this case。

 for example， people analyze how know generalization errorabouts for deep neural networks。

 And sometimes the argument is that it's often specific to the algorithm you use use SD and maybe they argue that if you actually do early stopping you only explore a very small part of the parameter space。

 you don't actually there's no it's impossible to actually hit the entire parameter space。

 So they actually carefully categor with。😊，Space of parameters that you can possibly reach using the SGD algorithm and then maybe do something like this within that parameter space。

 so you know there are many variations of this that actually lead to modern results。

 despite the simplicity of this。Okay， any questions？Iテ。So no， no。

 this part has nothing to do with optimization， right， So one way， one so a more。

 if you actually do with optimization， a more complete picture is something like you know。

 this H had tries to minimize this objective。 right， But when you do optimization， generally。

 you don't get the global global minimum。 Let's if you get somewhere that is not global minimum yet。

 right， And that gap you can handle by like a separate optimization regime， right。

 separate optimization analysis。 that has nothing to do with generalization。

 That is I'm doing optimization。 this objective for the purpose of the optimization algorithm is like the ground truth objective function。

 I just want this to be as low as possible。 But I cant get as as good as that。

 So I guess somewhere like not quite there yet。😊，Right， so eventually。

 you can actually just combine those two analysis together to get a final bound。 So basically。

 you will have a term that correspond to， you know， how the true EM generalizes。

 And usually you will have an additional additive term that correspond to， you know。

 maybe you can optimize this perfectly。 But， you know， again， like up to some other Epson Prime。

 So you have like something like Epson plus Eon Prime。😊，But again。

 that's the most basic naive way of analyzing this where you have generalization and optimization completely separated。

 again， in modern learning theory， like especially for deep neural networks。

 optimizationization is deeply intertwined with generalization。

 like the S GD analysis that just like refer to is kind of like an example where you actually need to think about them hand in hand。

 But， but yeah， but， but the basic like textbook。Like， okay， so。

Which like I think you can actually just literally do it over here。

 right So if you have this where you have this， so。嗯。If your optimization is not perfect。

You can subtract and add thiser， right， Only when H hat is the global optimum。

 you can claim that this error is always lower than this term。Right， but when it's not。

 what you can do is that you can just add Abil optt。 and this will still hope。Right。

 so this epson opt is basically how well you have optimized this empirical objective。Like。

 what's the， what's the difference between airhead like。You can say， eventually。

 let's say I output H H bar。Where airhead H bar is greater than。

Or smaller than equal to air hat H hat。 So this is the EM。Plus， Abpson opt。

 So this epson opt will give will be given to you by an optimization like analysis， right。

 But when you have this， you can immediately just plug it in over here。And the rest of what to hold。

 And then you just add an Abilom opt on the side。And that。It come from optimizationization。

 And in the eye of optimizationization， like， it only sees this。

 It doesn't even see the true error rate， right， So optimizationization doesn't care about generalization。

 It literally just cares about how do you actually like properly optimizeize the objective defined by the data。

If them。I mentioned all effects。So that's， again， like as I said， like this is 101。 Okay。

 all those more advanced results are you know， based on this。 But you know， inss additional settings。

 when you leverage additional assumptions， you can make things tighter and tighter。

 But this is like the foundation of the whole mansion。😊，Okay。And like， for example， like。

 I took a learning theory class when I was a PhD student and。Concentration in qualities。

 plus this is like the first two lectures。And the whole semester is like 16 or whatever。

So this is like， even if you take a course， which is just， you know， prepare you to。

 to learn the textbook knowledge or even portion of that of learning theory。

 not quite up to speed to the latest advances yet。 And this is only one10th of that。

Think of it that way。Okay。And， and all those like fancy results。

 like international dimension was not like， you need to take a completely separate class for that。

 We're not here to， to do that。But at all of the analysis we do here。

 as long as you are using a uniform convers argument。

 you will see later the kind of analysis that we do。

 especially in the function transformation setting， if you have any sharper。

Like generalization analysis for uniform conversions。 You can always。

 you can almost always just plug that in。Okay， so we're， we're usually gonna do this kind of like。

 very simple finite class analysis， like union bound plus concentration。

 But you will know that if you can just get a better generalization argument， you know， from。

 let's say you take a different learning theory course， you just swap that in and， and。

 and the rest of the analysis will still hold。😊，Okay。Okay， let's see。

As a little bit of a final remark， let's go back to the concentration in。

 And this is just something that I want to remind people， okay， so。The concentration in Gu， again。

 says like you have X 1， X N and the， the， the average of。The， the empirical mean。

 like converges to the true mean。Okay， one thing to note here， especially within the setting of R。

 is that you need to make sure that this this n is a is a constant。

Or is a deterministic like moreover， is a deterministic constant。Okay。

 so there can be like very tricky cases where if n is not a deterministic constant。

 but in particular， when it depends on， for example， the realization of the random variables。

 these exerciseise themselves。 like in general， that would be like a shopping time in a stochastic process。

 like you can use like the， the hublin in quality。So I'll give you one example， right？

 So like this is not a direct counter example， but give you a flavor of how things can go wrong。

 right， So let's say I draw X I from Bulli half right。

 So I have a fair coin is half has have you know， it's fair。 just have half probabilities。 Okay。

 and I got keep drawing this。 And I maintain an estimate of sumation over I equals1 to T X T1 over T right。

 So have this is bar X bar T。 So at at at any time T， I estimate currently empirical estimate。😊。

Right， now for a fixed T， I can obviously apply of the insane quality and make a claim about it。😊。

Right， but however， if your T is random and the randomness depends on the outcome of X is themselves。

 Things can go wrong。 For example， we can do something like， oh。

 I'm gonna stop whenever my empirical estimate is above 05。Okay， now we know that in general， this。

 this estimate will just oscillate around the true mean right 05， right。

 So sometimes it will be above 。5， sometimes it will be below 0。5。

 And when you do the concentration chain in quality for the true for fixed n， you're essentially。

 as I said， you're， you're basically leveraging。 you're looking at the distribution of this random variable and talk about what is tell look like。

 right， And this random variable in this setting is completely symmetric。Right it has like it。

 it will have should have exactly equal probability of。

 of being greater than the chiing and less than the chiing。However。

 if you do this like a stopping time， let's say I always stop whenever I the very first time X part T is greater than 0。

5。 Then I end up with a random variable that is always one sided。

 Like it's always guaranteed to be greater than 0。5。Okay， so this is not a， you know。

 concrete counter example。 But as you can imagine， the distribution of this random variable is definitely different from the distribution of this random variable。

 So whatever a statement about this random variable tell does not directly apply to this random variable over here。

Okay， does that make sense？Now， suppose I do this X 12 X big T。 So at most， I draw big T。

 big T coins， and then also maintain this X bar T along the way。How can I guarantee that？

This is accurate。 Let's say， like， because the main is 0。5， right。

 So how can I guarantee this is accurate with high probability， even if key is chosen randomly。

 like in that weird way。Can you think about an idea。

Prove a concentration in quality for this for for for this error when T is actually chosen randomly。

Now， I ask you to prove without writing anything to help you。

 which means that conceptually should be very simple。Okay， let me try to help you again。

 If t is a constant， like a particular value of n。The concentration inequ will definitely apply。

But the problem is that here， this is random。 like T can be any， because tea is like a shopping time。

 T can be any value between like  one to big T。But how can you handle that？

But half this gives you like the the concentration for a fixed value of T。こ人に。For entity， like。

 what do you do？Union bound， right， So what you do is that you can， you can make a statement like。

 okay， so what we do is that for any T， we know that X T bar minus-。5 is ba confidence inality。Right。

 but here we know that T is between one and T。 So what we can do is what you， and， and you have。

 this is with probability greater than one minus is delta。

 We will swap the order with probability greater than one minus is delta。 Yeah for all T。

X T bar minus0。5 is less temp。Okay， and here your， your concentration error will blow up by a factor of log T because T is the number of estimation events you handle。

Now， you have this that holds for any value of T。 So regardless of how you choose the T。

 this T is just the number between 1 and big T。Okay。

 so you get this Su you now you get concentration。 So this is a very。And in general。

 when you try to guarantee concentration for things like this， that is like， you know。

 a moving estimate that keeps changing in a stochastic process。 This is called a confidence sequence。

 And this， again， like， I'm telling you， like the very basic form of handling a confidence sequence。

 which is called a union bound over time。O。So later on， like again， like。

 we're really get into this realm where like sometimes the number of random variables can the number of samples you get is the random variable and so on。

 when we get to the opt sorry， when get to the exploration phase of this course。

 But but this is kind of like， you know， give you least give you a sense that you need to be cautious whenever applying concentration in qualities that this end needs to be。

 you know， really constant。 Otherwise， you need to be really， really careful。 Otherwise。

 things can very easily go wrong。😊，Okay， so that's it for today and we'll see you next week。啊。O。

My question is， are you asking for 43？Yes， like very likely。 I mean， I can't say 100% sure。

 but I think that's the plan。Quinnce， do you think needing having calculus 3 is important？No。

 because I think I like， okay， so the the mathematically so。Like。The lecture。

Like this week's lecture is already out of the scope of 4。3。But before that。

 that would be like covered by in443， and that's like the most difficult things you can encounter in 443。

Nothing will be mathematically more demanding than that。个牌上。I don't know have character right。

 but my class。Okay， if you， if you've taken a differential equation， I always think your， your cc is。

 is enough for， for that。 Like like the， the， the amount of c we require is pretty much just like taking gradient。

 Like if， if you can do that， like taking derivative and gradient。 If you can do that。

 I think like that， that's enough of cc。I I think the I think they enforce like a very prorequisite。

 You can like， I think you can apply for a like overrder or something， right， like up to my approval。

SoI think like well， I mean， when it comes closer to registration and you know。

 send me an email again， reminding our conversation and know what courses you have taken to justify this and I think I'll be happy to give approval that。

