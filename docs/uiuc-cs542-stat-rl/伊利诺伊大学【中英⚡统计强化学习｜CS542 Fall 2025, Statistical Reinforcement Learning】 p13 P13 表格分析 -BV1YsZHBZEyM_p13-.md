# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p13 P13 表格分析 -BV1YsZHBZEyM_p13-

Okay， let's start。 while I was expecting like much。Fewer people。

 because this is slightly clear deadline。 And I was writing text myself right before class starts。

 Okay， so。Where we were Like last last week， we talk about introduced the concentration in qualities。

 which will be your friend for the rest of the semester。

 And if you study any kind of machine learning or even in theoretical computer science。

 if you study things like randomized algorithms like you like use like concentration in qualities all the time right and the best friend through concentration in qualities。

 is like union bound and those two together go actually a long way。😊。

So today we actually get to a very basic analysis， like one of the most representative analysis and the most basic one R theory that that that we alluded to in the introduction size。

 right， So we're gonna consider。 so last week， we already did the the bandit analysis。

 And and remember bandit is basically R with like one step。 there's a long long horizon planning。

 So today， we're gonna just extend that to like an NP， right， We're gonna consider a。😊，We're gonna。

 we is gonna consider a general NP state action P transition reward discount factor。

 And we're gonna assume that you can and then we're gonna start with the socalled tabular setting where the number of states and number of actions is small and finite。

 and you don't use any function approximation to generalize across them。 for each state action。

 You learn things about them individually。 This is like the most basic setting。

 And you learn things about them by drawing rewards and next state samples from them。 And so。

 so basically， let's say the the the data collection。😊，EDa collection。For each。

S A in the state action space， draw。The N， I， I D S prime from。P of essay。

 And if your reward is also。Let's say your reward is also and R from R of S。

 if your reward is stochastic。But as you will see， like the reward stochasticity is like much easier to handle compared to transition。

 If you know how to handle transition， Re is like very trivial to handle。

 So sometimes well just like to make things simpler。 we just assume deterministic reward。

 I guess for now， Ill leave it stochastic。 Okay， so and you。

 you have like these and essentially reward next state pairs。

 But know that you have like this is a mini data set。 So this this these like m pairs。

 I call it a D sub S A。 Well， this is a mini data set because you have such a mini data set for every single state action pair。

😊，So the total number of samples you get is actually n times the number of state action pairs。Okay。

 so， and this is why， you know， this， this approach， as you can imagine， fundamentally。

 your sample complexity， as well as computational complexity。

 will immediately like scale at least linear with the total number of state action pairs。

 And furthermore， like when you actually analyze how how much like how large the N needs to be in order to achieve certain guarantees。

 And they additionally depends on some factoring like S or something like that。

 So like it could even be something like a quadratic or even worse dependence。 Okay。

 which which makes this not applicable to really large state spaces that require function approximation。

 But that will be a topic later where we will build on like the things we learned from here and then extend to general function approximation setting。

 But today， we're gonna start with this basic setting。😊，Okay。

 so the idea is that these are the and recall that So here we're also kind of dodging and circumventing the difficulty of exploration。

 If you're actually in NP and you drawing trajectories from some fixed initial state distribution。

 It's actually unclear and actually highly non tribute in the general sense。

 in a approvalable way that you actually collect data that covers the entire state action space in this uniform manner。

😊，Okay， so this is an exploration challenge， which we'll talk about， as I said。

 like a couple times in the second half of this， of of this course。 So we're not， we're not there。

 yet。 So therefore， for now to， to kind of， you know。To。

 to circumvent that issue and focus on the remaining challenges。

 which is already like pretty complicated。 We assume this very contrived and superficial data collection protocol。

 Sometimes like this particle is called like a simulator setting or generative model setting。

 like generative model this term like was it was used like long before like it current use nowadays in the sense that you kind of like have have a simulator in the computer that that is you have access to。

 So you can just like set the simulator to an arbitrary state action pair and ask what the next state。

 But the assumption is that you don't have the access to the actual probability distribution。

 But you can actually， but it's a black box， you can actually generate a random sample of next state from it。

Okay， in compared to the more like online natural interaction protocol where like there's the environment。

 you can't really put it in arbitrary state Sha， but you can always reset it to some initial configuration and general trajectory。

 like， for example， you have a robotic task， you can always put the like put everything back and put the robot arm in this initial configuration and then let the robot like interact with like whatever in front of it like for some time。

 And I say， oh， like you succeed in this task this time or you you failed in any case。

 you collect data， then you move things back， collect another trial and so on and so forth。

 So that's the more natural one。 Like that that's the more like online setting。 We're not that。

 we're considering this more contract setting that circumvent the difficulty of exploration。Okay。

 so this is a data collection。 Then and as usual， we're gonna， so this is the data available to us。

 I still have to tell you like， you know what what the algorithm is。

 And then we analyze it and get a guarantee。 Okay， and the algorithm is extremely simple。 So the。

 the algorithm is。😊，呃。Sometimes this， this name。You may still see this name nowadays if if someone knows like the old RL literature。

 it's called a certain equivalence。 like it's basically MLE in the in the tab setting。

So what it does is that it builds。It builds a estimated normal M hat。

So you have the same action space。 We have some P head and our head， which are estimated from data。

 And gamma is something that you already know。 So it suffices to define the P head on our our head。

 Then I have a estimated NP。 And the second step is trivial。 You just output。A pii M hat star。

Right so once you estimate this MP， you have a well definedfin MP given to you that you know everything about it。

 And it's a tab MP。 like number of states and number of actionss is finite。

 We can use all the computational methods that we've talked about so far in the planning setting you know。

 find the optimal policy in thisP， right And by the way， because now we're in the learning setting。

 wherere primarily interested in the sample complexity now and not really that car that much about computational complexity。

 but although sometimes we may comment on that as well。 So So this process， given M had。

 how do you compute this optimal policy， I just assume that， you know。

 we can totally do that and not really care about the details over here So then the remaining job is to specify how M had is estimated and how and then give guarantees for how good this is。

 know， how suboptimal this is as a function of number of data。😊，Okay。

 so so let's specify the estimated reward and transitions， and it's pretty simple。 Okay。

 so this is one over an n。Sation。R S prime in the mini data set that comes out of。S A and just owner。

 right， So， so the reward function is like super trivial。

 It's the same as the bandit case for each essay， you get N I D draws of the reward。

 presumably it's random。 We just take the average of those reward。Okay。

 so here I'm now a little bit less careful about notation。 But if you really want to be rigorous。

 like each sample should be marked as like an R super like。

Superscript eye or something to denote the I sample。

 And then you here you should are super eye or something like that。 So I'm。

 I'm just like skipping all those notation。 like， hope that it's already pretty clear， okay。And。呃。

And then the transition， Oh， the transition is also pretty simple， but。

 but we will write it in a somewhat。呃。R S prime。 Again， you look at。The， the you look at。

 youumerate over the I samples in your mini data set。 And what you do is E of epra。 So what is this。

 This is a one hot vector。With。As the， the coordinate index by S prime in the subscript， you know。

 you have a one over there。Okay， so what this is doing。 Well， if you actually think about it， So。

 so what you here get is a S dimensional vector。Okay， and you take the average。

 you still get an estimational vector。 So it's basically what， what is it。

 This is essentially the empirical frequency of next days。

That you see coming out from the samples of S。If you think about it， because for each coordinate。😡。

Like what， what's the， you know， what's the。What's the。

 what's the value for each individual S prime given S。Right， well， the value is basically one over n。

 summation are。As prime。Actually， S prime is already used to refer to the sample。

 So I need to use something else。 So let's say I use the S to S prime to for here in the DS SA。 Well。

 this is just the indicator of whether the S prime hit。attitudeute of prime。Right。

Like when I say okay， let me look at what what's the probably I estimate for a particular next state S to the prime。

😡，And according to this equation， I enumerate over all the S prime in the data that that I draw from the distribution P of S for each data point。

 if S prime is equal to the particular next state， then now I'm looking at。

 So basically I'm looking at a particular coordinate over here， right。

 So I'm looking at a particular coordinate like S tta as a prime over here。

 And every time I draw random S prime， I get a vector with a one in the you know corresponding coordinate。

 So whenever s prime is not equal to s tta prime， I get a 0。 But whenever S prime is S tta prime。

 I get one。 So you just get this right， And what is is。

 this is just counting I get a n random next days like how many times it hit a particular next state that I'm interesting now。

😊，So this is just the empirical frequency。😡，Makes sense。Okay， and， and together， like this P hat。

 And this is also why P hat is always a valid distribution， right。

 because this is just the empirical distribution that we see from data。OK。

So it's just the algorithm is as why is this。😡，That we're gonna analyze Any questions so far。开始。

Alreadally no。 Yeah， yeah， yeah。 So， so this is no。I mean， like。

 I'm assuming that you get N I D samples for each state actionmp pair， right， So there's like。

 you can't all know because you， you can't miss any state action pair。Okay， so。

 so then it comes to guarantee， right？ So what kind of guarantee we want。 Well。

 we want to show that this is near optimal and the sub automaticmatic gap gets smaller and smaller as n the number of data points goes to increases。

 right， because as you can see， like if n goes to infinity， like just by， you know。

 law of large numbers and， and， you know， the concentration that we know of these empirical estimate certainly converges to the true estimate。

 then we'll be able to， you know， calculate the exact optimal policy。😊，But as I said。

 like for this course， we are interested in the finite sample behavior。 So we're gonna look at like。

 you know， at what rate it goes to that and， and especially in the finite sample regime。So therefore。

 like the thing we want to say is that the kind of statement we want to say is that with probably at least one minus delta。

😊，Want to bound。 And we have seen this before。 So V star minus V。Pi M had a star。Right， and。

 and because now we have two models， one true model and one estimated model。

 And to avoid confusion for any like value function。

 I'm gonna specify in which model is the value function defined， so。

Which MP should I use to define these two value functions for this， for。

 for this quantity to be meaningful to to be a meaningful measure of how good。

My output policy actually is。The real NDP， right， Because this is the optimal behavior。

 the optimal performance you can get in the real NDP。You get off from policying your activated MP。

 But eventually， we care about how good it is in the real NP。

 So both of them should be defined with respect to the real MP， right。

 So let's suggest to make that explicit。Although like， I think by default。

 if we don't add any subscription， it should everything should be defined with respect to the real NP。

Okay， but， but here， just because there are two MP just out of caution， I always specify the， the MP。

 the better function defined with respect to in this part of the analysis。

This is something like that， as we will see， like it's。

It's gonna go down as and goes to infinity at the standard statistical rate 1verse squared root of n。

 But what's important。 And I highly encourage you that so I I'm now writing this very informally。

 but I highly encourage you to not write things like this， especially in our papers。

 although you see plenty of people writing this in bands and online learning and so on。

 And this is because in our， not only care about the rate with a respect to sample size。

 but also to a very great degree， We also care about how it scales with number of states。

 number of actions where in some part of the literature。

 they call that constants know come on like there is no way those are constants。

 those are very important parameters that describe the complexity of the problem。 So you know。

 don't write formal guarantees like just as a of how things goes down with the size of it。😊，Okay。

So this is the the， the， the R R task for this part of the lecture。 Any question before we start。O。

So。As usual， I'm gonna， you know， if you've seen you should have seen me doing couple this couple times now。

 what we're gonna do is to。Again， use alemma to split the proof into two parts， right。You know。The。

 the。呃。咩吗， so呃。This is a also a pretty。Famous lemma。 it has many variants。

 We will'll see some of the more modern variants later on。 But now。

 we're gonna see the most the the the the the the the most naive form of the lemma as it first appear in the literature。

 This is called a simulation lema。 So define。Now， Epsil R as。Max over S。Our hat S A minus。

 I'm gonna say R bar of S。 but this is really just the expectation of R from our。S A R。 So。

 so basically， if you remember， like， you know， when you're doing planning， given an MP。

 even if you have random reward， really like only the mean reward matters， right， And by definition。

 when we estimate this this MP， we're only estimating the mean reward。

 we don't even care about the random reward distribution。 right， So in our estimated MP。

 the reward function is always deterministic。Okay， so。

 so here what I'm measuring is basically the difference between our estimated main reward and the true main reward。

 according to the real reward distribution in the MP。Okay， and then I'm taking。 so for each S。

 my error can be different In some S， my error may be larger。 in some S， my error may be smaller。

 I'm taking the worst case over all state action pair。Okay， does that make sense？Okay， and similarly。

 I can define Eon P to characterize the error in transition estimation。

And here are how things get a little bit interesting。 So again。

 we're gonna to look at the worst case over state action pairs。

And then you have P hat of S minus P of S， right， So both are distributions。

So now we need to measure the difference between two distributions。

 And turns out that for table RO analysis， the most appropriate distance measure between distributions here is。

TV， so or just L1 norm， which is TV up to a up to a constant factor of  two。Okay。

 and we'll see later in the analysis why this is the most sensible， sensible measure of。

 of distance between distributions。 What other dis distance measure between distributions that you know of。

K L， yeah， K L is a divergence。 It's not a real distance， but yeah， it's a pretty common one。

 Any anyone else。We'll， we'll see some of it later on。 So actually， there's a TV。

 There's also Western sign distance， right， So and actually。

 a lot of these distance can be generalized to form called IM integral Pro metric。

 where Westernstein and K L are just special cases。

 we'll see some of that like later on in this course。😊，Okay。Okay， so we have these。

 and these are just definitions。 And by the way， so we then we're gonna make a claim then。

Then what we have is for any policy pi， that map states two actions or actually stay even randomized actions。

 as long as you have a market policy， we have a VM pi minus VM head pi infinite norm is less than absolutepson R。

Plus gamma， epsilon P V max。 remember， V max is just。V max is just the R max over one minus gamma。

 which is the range of the return you get as well as the range for value functions， right。

 divided by one minus gama。Okay， so this is the actually， and I think I missed the。

There is a factor of two over here。Okay， so， so this is a lemma we're gonna to prove。

 and then we're going to use this lemma to， you know， give the final guarantee。Actually， so， so it。

 it's actually now the， the entire analysis is actually now broken into three parts， right？

 So first is establish the slema。😊，And then useless that， you get the final guarantee， right。

 to bound this quantity。However， the slema also comes with these parameters， Right， Eson R F on P。

 right， So we need to eventually relate these to this， the size of sample， right， the sample size。

 because we know that when N gets very large， you would expect that Fson R F on P to be like closer to 0。

Right， and what kind of tools we're going to use to establish Eson or Eson P as a function of A。

Come guess。Concentrating in qualities， right， because， you know。

 that's literally talking about like pretty straightforward events because like， for example， here。

Like， if you fix on a particular state action pair， you just have like a bunch of I D random words。

 you take the average。 You compare it to the me。 Well， of course。

 like that's what Ho thing just handles for you， Right， of course。

 the transition case will be slightly more slightly trickier。 But， but again。

 this is within the realm of concentration analysis。😊，Okay。

And this will be actually a pretty representative like template for a lot of the analysis well see in this course for R is that basically you。

 you get two things。 One is concentration analysis which tells you something about you know。

 how your model or your estimate is accurate in a one step sense。

 right because because here you just say， oh， how is my estimate of immediate reward and one step transition dynamics。

 how accurate they are compared to ground truth right， however， remember。

 like how you're gonna use these R head and P hat。 where you're gonna do planning in the estimated model and think of planning right planning means like conceptually like you may be running like value or things like that。

 But conceptually youre actually you can think of like many ways by one way to think about it is that you actually rolling out trajectories and find what's the optimal policy for multistage decision making right that that actually optimized for a long term。

😊，In order to reason for that， youre actually， you will need to， you know。

 use these transition dynamics and reward function， you know， multiple times。😡，Okay。

 then you run into this issue of like error accumulation。RightBecause， for example。

 you start from the starting state， right， Let's say that is accurate。

 Then you apply the dynamics once your dynamics is， you know not fully accurate。

 So you get approximate distribution over what the next states looks like， right。

 But then you also need to keep applying it。Now， not only like your next transition dynamics is inaccurate。

 but also where you start， you start from the inaccurate estimate of， you know。

 time step 1 distribution。 So you basically， the more steps you， you roll out。

 the more and more errors like you accumulate。So therefore， like， you know。

 how these one step errors translate to these like long term， you know， errors。

 This is what we call error propagation analysis in MP。

 which is something like that is pretty unique and special to， you know。

 machine learning problems when you， when you have a dynamical system。

 when you have like these multi step nature of the problem。

 you don't run into these kind of things if， if you're if your analysis is does not have this like multi step nature。

Okay， so。Let's， let's do this one by one。 So let's first the。Bound the final thing using this， Okay。

 so。呃。You know。If you look at， So basically， what we're going to do is that we're going treat。

The simulationim lemma has given and try to bind the final thing we care about。O。

And then at this point， I hope this what is showing up here is familiar to you because here we have our approximate solution compared to the true optimal evaluated under the ground shoes model。

And here， what this tells you is that for any possible solution pi。😡，How the ground truth model。

 as well as our estimated model， you know， they both try to evaluate this policy and what's the difference in their evaluation。

Okay， so， and if you remember what I said last time。

 this is gonna be a very standard evaluation error to decision loss translation。Okay， so。

For those who remember。 So you can make a guess。 So if I know this error bound is this。

 can someone already make a guess of what the final loss bound is。

You know how this whole expression will appear in the final loss。It's gonna。

 It's gonna to be multiplied by something。Okay， so let's do it。 and then we'll see， okay。So， we have。

Well what is it We have。哦，设备play。Okay， so we want to bound the infinite norm of this， right？

 And if you remember， the infinite norm is。嗯。呃。Like。

The even norm here is only taking maximum over all states， because for every fixed state。

 this value is always greater than or equal to this value over here。😡。

So it suffices to just you know， Bo it for every single state。 So for any state。

 we want to bound VM star minus VM pi M head star。Right。

 and the star here can be just a change to the pi M star， right。

 So the optimal value in a MP is simply the policy specific value for whatever policy that is optimal for the NP。

O。Now what， now what we do。 So we look at what is this， right， so。Then this is VM pi M star of S。

Minus VM pi M hat star of S， sorry。Star of S。 Okay， so what do we do here？So what we have is this。

 which is the difference。Between value of different NP， but for the same policy。

And here we have the same MDP， different policies。😡，And what should we introduce here。Right。

 you want to introduce the like what's， what's missing in our current proof that is there in the condition is this guy。

 right， We， we don't have the value functioning M had in this guy yet。So apparently。

 that's the thing we're going to introduce。So and whenever you want you introduce it。

 you want to pair it with another ground truth value function， defining the true MDP。

 but for the same policy。😡，RightBecause whenever you have this pair。

 you can immediately invoke the condition there to bond it。😡，so we have this。

 so immediately we want to subtract。😊，Subtract VM hat pi m star of s plus well you you you want to so I'm going to skip stack here and see less than you equal to。

 and I just VM has a pi M head star。Okay， so I added subtract in this way so that you always get a pair of M versus M hat。

 But for the same policy， M hat versus M for the same policy。 But however。

 the thing I subtract and N are different。 Why can I still like add and subtract in this way。Right。

 because the second one， this is the value function in M hat for the for the policy optimum for M hatt。

😡，And because these two quantities， they are both value function M hat。 Of course。

 this one is the off。Right so therefore this one is greater than equal to this one。Okay。

And then what， then we're done， right， This is less than or equal to just the two times。不啦。Right。

 and that's what I said， like whenever you see evaluation error turning into decision loss without any additional assumptions。

 for example， in the homework， you're ask like， sometimes if you。

 if your evaluation is always an underestim or overest， you can save for a factor。

 But without any of these additional assumptions， it's always gonna be a factor of  two。Right。

 like we have seen it a couple times。 We're gonna keep using these like， like。

 you better like get really familiarize yourself with this that you can use it like the back of your hand。

O。So this is the first piece。 And if you remember， we have three piece。 The second piece is。

 I'm gonna now establish this lab。Okay， so establish the。Established dilemma， proof of。Proof。Of。

Simulation。来么。Okay。嗯。So what I'm gonna do here is that I'm gonna give you two different proofs。呃呃。

1 is like more traditional classic。 One is more modern。 There is value in both。 And， but apparently。

 like throughout the course， I can't do both like， you know， all the time。 So I。

 I choose this as the opportunity to do both for you to make a comparison。 And then later on。

 I probably like， you know， mostly use the more modern proof from later on。😊。

And by classic verse mortem。😡，I'm also literally referring to， you know。

 which style of the proofs are preferred as the time， you know， goes by。

 So the kind of the first classic proof I'm gonna go give you is the kind of proof that you will see very very often see in like。

 you know， paper 890s， like even early 2000s。 But， you know， after。

 I think 2015 is gradually everyone started to switch to more modern proof。 And it will see like。

 you know， some reason for that。😊，Okay， so。So the the first proof。So the。

 the proof is basically we want to establish thislemma， right， So， and that is， we have M and M hat。

These Epson Epson P can be viewed as a distance metric between two MP。Okay。

 then we're saying if the NP are this much close。In reward and transition。

 how can we use these like one step errors to bound the distance between these like long term quantities。

 which is like value functions。 because value function reflects the， you know。

 the long term expected return。Okay， and by the way， one common is that although in our setting。

 M is estimated from data。This lelemma itself doesn't really care about how you get M hat。

 It actually applies to an arbitrary MP as long as you have， basically。

 you can just replace M hat with any M prime。 And as long as you have this distance measure。

 you have this distance bounded between N and hat in terms of Eson and Fon P。

 the lelemma always holds。O。Okay， so let's prove it with the。With the more classical proof。呃。Clic。

Okay， so， you know， we want to bound。 if you look at it， we want to bound VM minus。

VM had for the same policy， right？ And if itre norm。 So for infinite norm。

 we always just say we can bound VM pi of S minus VM head。Pi of S， less than or equal to。Actually。

 on the left hand side， I'm missing something。 What am I missing。

What am I missing on the left hand side。No， for all assets is over here。Okay。

 but you can't just bomb this。 You need to bomb something else。😡，No， no， no。 okay。

 sure for all models。No， I'm saying the mathematical expression here is not quite。 If you。

 if you only bound this， this is not sufficient to for bounding。The a norm between these two things。

Absolute value， right， And， and again， like here we didn't need absolute value because this is like true performance in the NP。

 This one is always higher。 So I don't need absolute value。 But here。

 this is about how M hat evaluate a policy pie compared to ground truth。

 Sometimes you will evaluate to be higher。 Sometimes you will evaluate to be lower。 Okay。

 so therefore， you need to。Add an absolute value。Again， this is the same we've talked about before。

 so I'm just emphasizing again， okay， so what do we do？This is equal to。Well， see， like so here。

 this is a long term quantity， as I said， right， But the condition we get is these Eson or Epsson P。

 which are， which are like， like， you know， like one step quantities。

 So we need a way to convert these like long term values to relate them to these one step quantities And one of the most important tools you can use is byma equation。

 Okay， so B equation tells you that this is。😊，So what is value function。

 Well value function is just the immediate word plus gamma expectation S prime drawn from S A。嗯。Oh。

 actually， for this proof， I'm gonna use the， yeah， it's actually the this expectation。

 but I'm gonna use the top product conversion。😊，PS， pi， dot with the。M pi。Right， so this is just。

 you know， like expectation of the value function under the state transition probabilities written in the more like。

 you know， linearar algebraic fashion。😊，Okay， so this is a VM pi。 And similarly， we need to expand。

The VM hat pie。So that is a subtract our head of S pi minus gamma。He had。As pie。The M hat pie。Okay。

So this is a just by my equation that relates the current value function to reward plus transition times the next value function。

 right， And we're just invoking it in two different MP， once in M。

 So then you get the reward in the true MP transition in the true MP and once in M head。

 you get the reward in the M hat P hat in M hat。😊，Okay， now， as you can see。

 you immediately get R S pi minus R hat S pi。 You get difference between R and R hat on the same state action pair。

 How can you bound this term。Like with our condition。Yeah， Eson R， right。

 causeuse Eson R is the maximum difference between our hat and R。 actually， this should be our bar。

 I guess。Because there's the main reward。Okay， so this， this difference is。Immediately。

 an FO R bounded by FO R。Okay。And， and this is why you want to do like a B equation， Right。

 because Bel equation helps you to get the reward and the transition out。

 And this is what our conditions are talking about。

 Our condition are talking about the accuracy of reward and transition。 So you want to get them out。

And when you have a value function， the easiest way to get them out is to use B equation to unfold。

 you know one step。Okay， so now， so that's handled。 But now you have these two things， right。

 And our condition tells you the difference between P and P hat。So just like the R and R hat。

 you want to combine them into， you know， like their difference。

 So here we also want to get P minus P hat。However， we can't right， because this is a do product。😡。

But they're being like a do product with like different functions。Okay。

So what can you do in this case？😡，So I really want to compare P and P hat so that I want to make P minus P hat to appear。

I can't directly do it， but。What else can I do。Okay， so maybe something like that。 but you know。

 concreteently， what should I do over here。As subtract and add subtract word， right。

 So let me give you a hint。 So here I have the true P dot with true value function。

 I have P hat dot with value function M hat。😊，So what kind of intermediate terms I can introduce so that I can get P minus P hat。

Mind you， you can get P minus P hat if these two were the same。P台。Exactly， right。 So actually。

 you can do it either way。 So basically， you have true P， true V， P had V hat。

 So what you do is that you add， you introduce the intermediate term that is the mix of two， right。

 You can either do P V hat or P hat V。Okay， so so tear to us that for this particular proof。

 either way is fine， but for some other proofs， you you actually need to carefully choose which version you introduce because they actually give different results。

 Okay， so for this one， let's say we add subtract。😊，P S pi， VM hat pi。Plus。PS pi。

VM had pi minus okay。So as I said， like， for this proof， it also works if this is the true V。

 But then you have P hat over here。 The proof is almost identical。

 and they don't really generate any consequence for this one。 But in other places， you actually。

Don't think you only have one choice。 You actually have a design choice over here。

 and you should make that choice carefully。Okay， so now what we get is that let's see where do we get。

 Okay， so now we get two things。We'll get this pair。So this pair， we get the same we desire， right。

 So it's P minus P hat And because they're come， they're。

 they're being dotted with exactly the same function。So we get P minus P hat that we want。

 And we also have the other thing that we well handle later。 Okay， so let's， let's do this。

 This is I'll break that part。 So M so R plus gamma， I， I will handle this one first。 This is P。

As pi。Minus P hat。S pi dotted with VM head pi。Okay， and then the other pair， what I get is。

 so here I have different P but the same， same V。 The other 1， I have the same P， but different V。O。

 plus gamma。Same P。 So that's the true P。Different V， VM。pie minus VM hat pie。Okay。

 I got these these things。So now I guess returns terms， one term is already handled。

 That's the reward error。 The other two things we still need to handle。Okay。

 so let's handle them one by one。Okay， so maybe let's call。This term。Number one。

 this term number two。Okay， so let's first handle number one。 And this is where it's， it's。

Convenient to use the the L1， L1 norm to measure the difference between P。

 So we need we need to introduce a very。Super useful results。That， again， will use like all the time。

 It's called a holdersing quantity。That says for any U and V that are vectors in the same dimension vector space。

 Euclidean space。 let's say we care about their。Doll product。It can be bounded by u times v。For any。

 what we called So， so here， so this， this norm around you is any norm。 And when we write norm star。

 this is a notation for its dual norm。 we'll talk about the notion of a norm do norm later。

 but actually just think a bit， but an example。😊，Okay。

 so you should already know inequality written in this form where you choose the norm on the right hand side。

 you know， to， to something very concrete。 which inequality have you seen a take this form。

Coish Schwars， right， and with the norms on the right hand side。L 2， right。

 Do product is founded by L2 norm times L2 norm。 Well， guess what。 L2 norms dual norm is itself。

So K Schchwars for this vector form is a special case of heteroizationineality for L2 norm and L2 norm。

If， for example， if。Norm is L2 norm， Its corresponding dual norm is also L2 norm L2 norm is dual norm to itself。

Okay。But as I mentioned， we're not going to use L2 norm for Tular RO analysis。

 So this is not really relevant to us。The one we're going to use。Is the other one。So， if。

The norm is at one norm。Guess what's the dooror？😡，Does anyone know。It's even norm。Okay。So， and。

 and there is a more general。Okay， so there's a， I'll give another example， but the more。

The more general rule is that。You know， if， you know， if you， if you are given any norm definition。

 you can define its new new norm。 for example， U new norm is a supreum。If I。

 let me see if I can remember it correctly， I think its。Over。V。We transpose you。 I think。

 I think this is correct。 so basically for any given norm。

 you can define a do norm in this way where the norm being given is over here。😡。

So you look at all vectors。 So whenever you have a U， you measure is the two norm is basically。

 you look at all the vectors whose norm given to you is unit norm。And among those vectors。

 you find the one that has the largest product with the， with the view。Okay。So， for example。

 like if you have a。So let's say you have I'm trying to measure the the norm of this U or the do norm of this U。

 right， And then let's say I'm saying， okay， let's look at what's the dual norm of L2 norm， right。

 then essentially， what you're doing is that you're just drawing the L2 unit ball and say， okay。

 which which vector V in this unit ball ball has the largest the top product with you。😊。

What a vectorctor。Which back are you on this unit circle has the largest off product with you。

It's the same direction， right， It's exactly the same direction。 Now。

 if you take that V and dot with U， which has Uni S dotted with U， what you get。

 You get used like L2 norm。Correct。Now， similarly， let's say if I ask。

 what's the dual norm for say L1 norm， right？ So what's L1 norm， Well L1 norms ball looks like this。

Right， so it's a。It is。It's something like this， right？ And and again， like you。

 you sweep the V vector around this unit ball and find the larger stop product with you。

 And what you find is that basically is's basically either you optimize the do product either over here or over here。

 right， And depending on whether this lens is longer。

 this this projection of U is longer or this projection in U is longer。Right， and what is that。

 You look at the the component of U on either x or y axis and pick the maximum。

 Well that's just infinite norm。Okay， so this is a kind of like， you know。

 visualization that helps you remember like， you know， why you get L2 and， you know，21 pairs。

 Another one that I will use like much later on is， you know， you have these matrix norms。

 So this is， you， if you is。😊，Roots。呃 u a。You transpose you。

So if you have a positive definite matrix A， the quadratic form。Define under a。

 take a square root is also a valid norm。And。Just out of intuition， can you guess what is do norm？

Any guess。So apparently， it has to involve a， right。Matrix isponent。

 The other thing that you have to remember that that I didn't tell you is that， you know。

 the dual norm。 So the， the norm and dual norm is symmetric。

 If you start with the dual norm and ask what is dual norm， that's the original norm。

So you have to come up with a guess， such that if you say， okay， I start with this as the norm。

 I do the same kind of translation。 I must get back this， so。What's the guess？Yeah， yeah。

 you're there， what what is it， Yeah， exactly。V transpose a inverse v。Right。

Because then if you start from here and do the same recipe。

 it's just about inverting the in the middle。 Then you get back to this。Okay。

 so this is like a super， super quick like crash course holders in qualities and norm and do norms。

 before now， like， you don't have to worry because we're gonna just use this and you can just take it as given。

😊，Okay， so we have a。Norm and dualor pairs。 So， therefore， one。

So we get the do product between these two。 We have one less than or equal to。

 There's the gamma factor。 So gamma times。呃。P。S pi minus P hat of。S pie。1。VM had pi infinitefin norm。

Okay。And what is this， this can be bounded by Vm。Okay。Now。

 one thing you have to be careful is that we know that Vmax basically bound every form of value function or return on everything。

 but that statement is with respect to the original NP。Okay， but here you have the estimate MP。

 which has different NP。 So you actually need to verify this separately。Now。

 that still holds because we're simply taking the estimated reward function to the average of the random reward we see。

 And typically， we assume that all the random rewards are bounded between 0 and R max。

 So their average is also between0 and R max。 So the Vm bound will translate to the new estimated NP。

 And that's why we can still use this V max bound。😊，Okay， so just， you know。

 just a little bit careful that that that you have to verify this separately is not always given directly。

 Okay， and now this thing， what， how do you handle this， This is coming from our condition， right。

 So this is bound by。 So this is epsilon P times。B max。Okay， so we handled the term number one。Okay。

 and so far， we've successfully get。Got Epsson R and Epson P。

 these one step errors to show up in our bound。Okay， now we still have number two。

 but you also look at the final result we want to prove， right。

 So we have Epson R Epsilon T times the V max。 We get both of them。😊。

It turns out that they are not even the major part of the and， and without you know。

 other multipliers in front of it， right？ Well， it turns out that those are not even the major part of the bound。

The bound is those divided by woman as gamma， so this is a large number。😡。

So what we get it so far is just a tiny fresher。Of the right hand side。And why is that？

Well that's what I'm talking about is like when you， when you， when you estimate the value function。

 which is a long term quantity in M hat， you're gonna use these P hat and R hat many， many times。

 every single time step you use at once。So， and if you think of infinite horizon discounted case as roughly speaking。

 similar to finite horizon analogous to a finite horizon problem where the horizon is one over oneness gamma。

 then roughly speaking， you need to you actually use these Phead and R hat。

 one over one minusness gamma times。So so far， we've only analyzed the error for one time step。

So there needs to be a mechanism to， you know， repeat that analysis for the all the remaining time steps。

O。And this is exactly what。This number two does， right， as you see。

 So here what we get is we get another VM pi minus VM head pie， which is exactly where we start。

Right， so this is looking at， oh， we get this recursive bound where we still need to bound the difference in value for all the future time stepss。

So the nice thing is that we can actually handle this nicely using recursion Okay。

 so number two is bounded by gamma。😊，Gamma times。 So now I have expectation。

 We know that expectation cannot exceed maximum。So I just directly do VM pi minus VM head pie infinite norm。

Okay， so what do we get if you zoom out， we start with VM minus VM head pie for any state。

 So essentially the infinite norm。😡，Of the difference between functions。Then as we go down。

 we get the Epsil R and epsilon P terms。But also， this additional term that is exactly the same as the left inside side。

 but crucially with the additional discount factor。Okay。

 what you do was just move to the left hand side， then you get one minus schema， divide it back。

 we're done。Okay， so conceptually， essentially what you're doing is that now， I mean， the second。

 like where is this， now I'm transitioning to the second time step。 I mean asking。

 what's the difference between these two again， Like， essentially， you're doing this analysis again。

 and get error over there。 But then that error is already discount by gamma， Then you do it again。

 That error over there will be discount by gamma square and repeat this infinite number of times。

 But this recursion here is just a very convenient and mathematically elegant way to。

 to to do that without actually you know， expanding that infinite number of times。

 which would also work。And in fact， later on， in some of the proofs。

 we actually need to do that you know， infinitefin expansion， but that is not required over here。

Okay， so this is the。This is the classical。 and and I hope you like actually see why this is called like error proagation because you start from S。

 you incur one step error。 And then now you need to look at the error in the next day distribution。

 Like if you imagine that infinite expansion， it definitely have this feeling is that youre。

 you're looking at one distribution at a time。 And every time you incur some immediate error。

 and then you get to the next time step， you incur error over there。 and so on and so forth。

 And eventually you， you， you incur error over multiple time steps and you add all of them up。

 That's your total error。Okay， any question about this proof？Yeah， there's a divide by two。 yes。

 good that you mentioned。 So if you follow the proof over here。

 what you would get is basically the bound。😊，But with all this， divided by two。

So this divide by2 is a tiny minor improvement， but it's kind of interesting。 I'll mention here。

 So basically， it's when you， when you bound one。 So here you can actually improve it to a factor of2。

 And the reason is the following。😊，So。Improvement。So when we bound。P had minus P。 So I'm。

 I'm emitting the given S pi just for short。 And we get a V。

So we know this is in between0 and the Vmax。Right？So it's infinite norm as V max。

 And then we just directly use holders in quality。 And then you get L1 of transition error times V max。

Turs out that there is something pretty tricky you can do over here。 This is equal to。P had minus P。

V as a function， minus。诶。V max。Divide by 2。A all one vector。 So if you treat V as a vector。

 this is another vector where every single element is the same。

 So what it does is essentially center this V function so that its range is between。呃。

V max over 2 plus minus。Right， because， you see like when you take infinite norm。

 you're looking at the maximum positive value and the maximum negative value and pick the larger one。

Right， but when your value function is actually always not negative。

 only the largest possible value is effective。 You don't get anything on the negative side。

And so by centering this function。😡，You actually like save a factor of two。

Because now the maximum positive value and the maximum negative value is the same。Now。

 the question is like， why can you do that， right？ Why can I just introduce this thing over here。

 So essentially， essentially what， what from this step， what it claim is that P had minus P。

Dot product with one is0。Okay， why is that。So， so， right。

 because if this holds that this term just like the all one vector times a constant dot with this is still 0。

 And then this will hold。 So why can you do that。 Why is this true。And let me ask you a question。

 So P is， So P is like P thought given as pi， right， So it's a valid distribution of states。

Given a distribution vector， when you dotted with all once， what do you get。One。

 let's just sum up all the probabilities and you get one。😡，P hat， on the other hand。

 is also better distribution。Because its say empirical frequency。

 when you dont lose one hat with all one， you also get one。 So their difference is always 0。

So this is a tiny tiny minor improvement， but kind of like an interesting one that you can get。Okay。

So this is the。This is the呃。呃，还lo谁呃？This is the like the classical proof。 and it's。呃。

The using this you know， expansion， like B my equation and so。 Now， one thing you realize is that。

 I mean， eventually we get this L infinity proof， L infinity result， right。

 And if remember what I mentioned before， like previously， we also see a number of L infinity result。

 And that's because and these L infinity results are pretty loose in the sense that theyre really。😊。

Like ignorant or or really doesn't care about how like distributions。

 and it's basically a very crude way to handle distribution shift in， in， in R。Now， previously。

 we have seen one identity， which has this flavor where something that is like long term is expanding into something like this multistep where you see a wonderful woman gamma on the right hand side。

 But that's an identity。 And， and you have an exact categorization of distribution there。

 Doest anyone remember what what， what kind of result。😊，Have that flavor。Let me try to find it。Yes。

 it's in the proof of policy iteration， correct， But what's that do you。

 Does anyone remember what theirlemma call is called。It's this one， right。

 It's the performance difference lelemma。Right， so you have the difference between two the the performance difference between two policies is equal to the expectation of an advantage under the discounted occupancy induced by。

 you know one of the policies right So and by modern。

 like actually I'm referring to proving those kind of results using these kind of lemmas。

 which has the exact characterization of distribution。

 which turns out to be extremely important when you get to the function approximation setting。

 because when you have super large state space use function approximation。

 it's almost impossible to get L infinity guarantee。

And any guarantee says that in that enormous state space。

 you can make even a single stay mistake on any of the states。 That's just impossible to get。 Like。

 like when you get to the function pro setting， like whatever you do。

 You're always good in an average sense， right， You're trying a regressor， You're train classifier。

 you always say， what's my average correct rate， right， it's extremely hard to say， oh。

 I've learned an image classifier that is gonna be correct on every single possible image out there。

Like， that's almost like， that's a ridiculous。 And， you know， without extremely strong assumptions。

 you， you can't get that kind of guarantee。So that's why L infinity guarantees is very much restricted to the tabular setting。

😡，But these kind of results， they're useful ver tababular。

 but we can also use them in later function approximation analysis， which is why I want to show you。

How to prove。How to prove the simulation lamma with the with the new new and。

With with a different tool。Okay。So。s proof。Of simulation Lamma。So。

And the alternative proof is basically first stating a more general version of simulation Lama in some sense。

 and then induce the what we see as a direct coronary。Is the following。 So for any F。In R of S。

 So basically， given any function， that is a function over this stay space。Over states。

We can say F as 0。 how about this。 And let's， let me do it in a more general way。 So expectation。

S from D 0。F。Of S。Minus VM。 So here in this Lamma。I just do。Jy。呃J派，O， so I think that's good。Okay。

 so so I'm gonna express this。 Okay， so what is J pi。

 while J pi can be also written as S from the 0 V pi of S， right， And here in this lemma。

 there is no other like this is a general lemma。 But in this lemma， there is only one NP。

 That is the ground choose MP。 So whenever you see a value function without any subscript， really。

 it's it's always defined with respect to their ground choose MPM。O。So that's why， you know。

 this J pie is always is also the ground the performance of pi in the ground truth andPM。

So if you look at this expression， J pi is basically the value function。😊。

Of S of pi taking expectation with respect to the initial state distribution， right， Now。

 this term over here， you have an arbitrary function F。

 but the structure of this term is identical to the structure here。

So the interpretation of the left hand side is basically， suppose someone give you F。

 That is a reasonable approximation of true v pi。Okay。

 now you use this F to predict what's the expected return under the initial state distribution。Okay。

 now you want to express it as something about F。 So on the right hand side， what you get is。1 over。

1 minus Gmma expectation。S A from。D pie。The r from R S prime from P of S。

F of S minus R minus gamma S prime。Okay， so， well， you know。

 one thing you can do is that so here is the expectation。

 What you can do is that you can first take expectation inside and then marginalize things out。

 If you take expectation of this part， this is basically the Belman update。

 So this whole thing when you take expectation is basically the Belman error of function F。😊，Okay。

 with respect to the you know， the Belma equation for policy evaluation， for V pie。

So as a special case， if F。So if if if so this part。This part is a random。Rand， random estimate。

You can say it's unbiased estimate。Of F minus T pi F。Okay， so therefore， if you have F equals t pi F。

 Well， this part is 0， right， But if F equals t pi F， we know that F must be equal to v pi。

 So the left hand side is also 0。So that's a special case that says， so essentially。

 this is a more general version that says if you have a function that satisfies the B equation。

 which makes the 0， then this function is v pi。 So its prediction at the initial state distribution must be accurate。

😊，Okay， so that statement is basically like you can view it as a corollary of of this。 But here。

 like this is a much more， you know， dedicated and， you know， much more powerful result that says。

 okay， your f is wrong。 We know that it's not exactly V pi。

 But we care about how wrong it is in terms of its predicted expected return at the initial state distribution。

 Well， we can relate that to the bow error of this function on exactly this distribution。😊，Okay。

So I think given time， we have to prove this on on Friday。 But I， I will just first say。

 how do you use it to prove the performance difference lelemma， right。

 So performance difference lemma is about VM pi minus VM head pie for any initial state。 you know。

 you know， the， the value function and the initial state is basically J pie when you choose that initial state as your initial state distribution。

 right， So therefore， we can just。😊，啊。If， if we have this result。

 when you try to prove a performance different slema， you can just do V M。Pi hat。

Of S 0 minus VM pi S 0。 So， so here the J P term just correspond to right， So。

 so this is just J pie when the initial state distribution is a point mass on S 0。Right。

 and this plays the role of the expectation of F。 So basically。

 we just choose F to be VM head pi because indeed， VM head pi is supposed to be an approximation of VM pi。

Right， so therefore， we get the left hand side。That is just equals。

Wonder one is gamma or expectation。 Well， there is some discounted occupancy over here。

 But because we're gonna eventually relax it to infinite norm， that's not important for now， we get。

😊，VM。V VM head pi of s minus r minus gamma， VM head pi of s prime。Now， for this term。

 if we do law of total expectation。We can first take is outside。 we take expectation over， you know。

 like whatever D pi， some， some kind of D pi。 and inside。

 we first marginalize out the randomness of reward and X D。

 So we get VM head pi of S minus expectationation as prime。😊。

Reward a next date given S A R plus gamma VM hat pi of S prime。Okay。

Wman is woman is gamma expectation。S A from D pi。Actually， I'm not going to write all these parts。

And only look at this term。Over here。Now， the first term， you also expand it as a bomb equation。

 So you have R head of S pi plus gamma P hat。S pie。VM had pi。Well， the second term， it turns out。

 is just the R of S P minus gamma P had a true P。As pi。VM had pot。Okay。

 so let me explain a little bit。 And then we're done。

 So the first termm expanding this way is just about my equation in hat。Gect。

 because that's just the VM Had pie。Okay， so the second term。

 which we have is that you want to take expectation of whatever is there。

 But under the conditional distribution of reward and next date， given S。

 So here recall that the R and S prime。😡，In the slema， they are drawn from the true NDP。Okay。

 so when you take expectation， what you get out is the reward and transition parameters from the true MP。

And you get a true reward。 You get a true transition。

 But then the final function over there is VM hat。Okay， so in this step。

 like I encourage you to work it out， right， Because， for example， if you see， if you see this part。

 what's this part。 Well， this is just what's the expected reward given essay。 Well。

 that's just the reward， the main reward function。 right and similar for the expectation S prime。

 What that's just the the true transition probabilities。 Okay， now once you go here。

 you can immediately bounded with F E on P， right， So this difference is bounded by Fson R。

 So here you immediately already have the same value function。

 different P P hat versus P So the rest of the bound is similar to before。😊。

What's nice about this proof is that you no longer have that， you know， multi step expansion anymore。

 right， because that expansion is already taken care of by this more general form of simulation lemma。

So this is what happens in these modern proofs is that you will have a dedicated lemma that immediately handle all these like error proagation。

And they also tell you exactly， you know， theyre very distribution sensitive They tell you how。

 you know， what kind of distribution you make errors out。And then。In the rest of the analysis。

 you can just focus exclusively on the one step error。Okay， and， and this is why， you know， this。

 this analysis is sometimes cleaner and and now more favorable。Okay。

