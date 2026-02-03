# ASU《强化学习2022-2024｜cse 691 Reinforcement Learning Course at ASU》中英字幕（deepseek - P20：[18]Lecture 7, 2023_ Rollout for stochastic problems, Monte Carlo Tree Search, - GPT中英字幕课程资源 - BV1zcfVYdErD

![](img/ff978ba2a012c29b83e0f8c639d8bc0b_0.png)

Okay， let me welcome you to the seventh lecture of our course on reinforcement learning。

We spend the last two lectures。Talking about rollout and approximation value space for deterministic problems。

And today we're going to do much of the same thing。

 but for stochastic problems and also some variations that we haven't discussed in the past。



![](img/ff978ba2a012c29b83e0f8c639d8bc0b_2.png)

So。Here's the outline。We'll start with。The simplest form of rollout for satorcchastic problems with one step look ahead。

Then。We are going to discuss multi step look ahead issues。

Then we're going to go into Monte Carlo research。Inch some form of approximate multi step look ahead。

With the approximation value space。Then we are going to discuss infinite spaces problems。

Problems where the number of controls is infinite and therefore there's an issue。

And calculate a Q factor for each one of them。 So we're going to see how we deal with those in the context of deter deterministic problems。

And then we are going to discuss a classical。typepe of problem called stochastic programming that involves infinite spaces。

 and we're going to see how our method dollars can be adapted to those。

So let's talk about rollout for stochastic problems with one step， look ahead。

So this is just a special case of approximation in value space with the one step look ahead。

And you have seen this equation at state Xk， we minimize overall controls， the Q factors。

 which should involve the expected value of the current stage cost plus an approximation to the optimal cost to go。

And in rollout， this approximation is just the cost function of a base policy。So it's a special case。

And this policy we do not buy pi， so Jk plus one pi is the cost to go from stage k plus one using policy pi using the base policy and starting from the state where we are after we apply this control here and the result of immunization is the rollout control which we call U Tilde we're going to be using untiltilde for base policy with Tilde。

 everything that has to do with rollout。So pi is going to be the notation for base policy。

 as we have seen before， and pi tilde is going to be。

The is going to denote the policy that we obtain through this minimization。

 so this is the policy that applies at the state Xk。

 the rollout control that comes out of this minimization。And we call this the rollout policy。And。

The main result here。And the basis really for a rollout and the source for all the good properties that we have seen and discussed is the cost improvement property。

Namely， that the。Rollout policy performs better than the base policy。

 starting at any state and at any stage。 we're going to prove this in the next slide。

 we have seen the context of deterministic problems。

And this guarantees cost improvement doesn't tell us how much improvement there will be。

 but usually the improvement is very substantial。The fundamental reason for this is that there is a newton step that relates this thing here with this thing here。

If you apply。A Newton step to the Belman equation of a problem to the dynamic programming algorithm。

 starting at this point， the cost function of the base policy。

 then the result of this Newton step is the cost function of the rollout policy。

And new to step is the most powerful algorithm optimization。If you happen to be relatively close。

To be。The optimal course function。This thing he is going to be。Almost the same as the optimal cost。嗯。

However， if this is not close to the optimum， then there are there are there may be。

It may not perform as well。Moreover， the Newton step。

Connects this with that for a case where we calculate exactly。

This optimal cost to go if you approximate that， such as with trancated roll allowed。嗯。

It's going to be a newton step， but for a different from a different function。

So there are always approximate variants， there's a possibility of truncated rollout where we do limited simulation。

I'm sorry。We do。Simulation， but up to a number of steps forward， and then approximate。

The cost after these steps by a cost function approximation。So。

There's this possibility and the other possibility is limited simulation for the deterministic problems。

 we had the nice property that a single simulation trajectory gives you what you want。

Here we have to calculate an value， so by simulation to compute by simulation this expected value。

 we have to generate random samples okay according to the probability distribution of the ws here and then we have to average these samples and how many samples do do we have to to use what we may use 5。

10，100 a million no matter how many we use， we're not going to get the exact thing its going to be some simulation error and the variance of the simulation error may throw off this minimization here and may give you may erode the effectiveness the performance of the rollout policy so we're going to deal with this issue also which like I said arises in stochastic problems but not in deterministic problems。

So let's now go into this。This example。Of P Gamon， which I've mentioned before， was the first。

Substantial application of rollout。 And in its time， it created also a sensation。

In the research circles of people that were looking at reinforcement learning at that time。

 this was the first substantial application that these new methods were able to solve。Now。

 like I mentioned， sometime in the past， the sort of had。

Program that used one step look ahead without rollout in 1991， and then in 1996 he introduced the。

They're all out。It trad the rollout and got much better results。

 which was an interesting thing to observe at that time。Now about back Gamin。

 I don't know how many of you are familiar with this game。

 it's a game that's very popular in the Middle East， my native country Greece。

 I spent hours and hours and hours， days and days playing back Gamin and when I was a teenager。下。

It's a game of skill and strategy， but it's also a game of chance， it involves uncertainty。

 it involves rolling the dice。And the way it works is as follows。 there's a board here that has。

24 slots。On which the two players， the white and the black player put their pieces。

 15 pieces for each one there is a starting position。

 and then based on the the results of the rolls of the dice， they move their pieces in。

Oosite directions， and then whoever reaches a certain termination state first wins the game。

 there's no draw here either one player wins or the other player wins。And there are some rules。

 of course， by which you can play a given role。And。After you look at。

 this is evident that the state of the system。Is pairs of board position and the current dice row。

And the controls are the different ways that you can play this di roll。

 move this piece and that or move that part piece and that and so on。

Like 2030 ways to play a typical di row， so the number of controls here of the order of tens。

The number of states is astronomical， as you can tell。And there's also stochastic disturbance。

 which is a dicelon， okay， the diceole can we。36 different outcomes，30 if you don't count doubles。

 okay， so again， a stochastic disturbance。Doess not。Does not have too many elements like 30。

 but you know， 30 upon 30 and for multiple stages， it adds up very quickly。U。

So that's the way the game is played。And as I noted。

 in the 1996 version of the algorithm called TD Gament。

Users tranccate the roll out with cost function approximation provided by a neural network。

In that neuro adequate restraint offline， this thing happens online is the online player。

The neural network place is trained offline。With a form of approximate policy duration。

And it uses some algorithm that's very important in reinforce learning。

 but we're not going to cover in this course， temporal differences， algorithm。

 and for policy evaluation， stochastic iterative algorithm， given a policy。

 you apply this TD algorithm and it gives you after a lot of simulation。

 it gives you a cost function approximation that involves also a neural network。So the sort of。

The sourcece 1991 work involved the training of a neural network to play back gamut without any ur allout。

 just one step look ahead with the approximation provided by the neural network。In 1996。

 it introduced the intermediate form of rollout whereby。

Given the current state we consider all possible ways to play the role and then we roll out games that's where the name of rollout came from we roll out games all the way to a certain depth。

Backy。将。His duration can be very long， so you have to trancate at some point and he used reasonable forms of truncnation and the cost function approximation is the one from the 1991 algorithm。

So now the important observation is that the。Franncd rollout program 1996 played considerably better than the 1991 program that did not use rollout。

Moreover， the 1991 program was a good program， but it was has subhuman performance would be beaten by the best humans。

 however， the rollout。Program of 1996 is better than any human。On the other hand。

 there's a trade off here。Which is a key issue in stochastic or all loud。

The amount of simulation involved。Yeah， you have， okay。30 different moves， let's say。

 and then you have to roll out games like。Hundred games from each one。 And that takes time。

And all of this is for a single move。 Now， people are in clay patient in playing with his games。

 they want。They want to car a response within seconds。The 1991 program was responding within seconds。

 In fact， you can play on the Internet with programs like that， and they respond within seconds。

 and they play a pretty good game。However， the rollout program， I haven't seen it。

It is taking a lot more， a lot more time。 and I have not seen a version on the Internet， except。

Except not to play a full game， but rather to evaluate a certain position。

 it will roll out and give you an evaluation of moves， it's using an evaluation mode。

So even today with the。Past computers that we have。The simulation issue is something to consider。

 it can be daunting and an impediment for practical use。

We're going to come to this issue of how we alleviate a burden of simulation。

But that will take us a few slides。So in now this is an example， are there any questions。

 by the way here？Okay。你。Now we're going to go into a mathematical proof of the cost improvement property。

This is in the same spirit as the mathematical proof I gave for deterministic problems。But we use。

More of an equation oriented argument as opposed to a graphical argument on the look at three。

So what we want to show is that in the context of one step， look ahead。And non tranccate the rollout。

The cost to go of the rollout policy from any one state is less than the cost to go of the。

Of the baseball from the same state。And we prove this by induction。This is a proof。

So we assume that this property holds。For k plus one， and then we prove that it calls for pay。

So it holds clearly for K stage， this a backwards induction on K。

It holds for k equals n because both the rollout policy and the base policy。

After you've been to state to stage n， the corresponding costs is the terminal cost， gs of n of HN。

So， now， we assume that。JK plus1 of pi is greater than Jk plus1 of phi tilde。

 and we're going to prove that JK pi is greater than JK p tilde。So that's what we want to prove。

 Okay， we want to prove that this。Is less than this。

And we are going to prove it through a string of inequalities。And let's go through the。

 through the relations one by one。The first equality。

Is the dynamic programming equation for the rollout policy。Okay， by till there is the laout policy。

And what this says is that the cost at state xk is equal to the expected value of a course in the first stage using the rollout control。

Plus， the cost to go of the rollout policy from the next state。

 this is just a dynamic programming and algorithm restricted to the policy by Tilde。Now， we use the。

Induction hypothesis， the first inequality holds by the induction hypothesis。

 because our induction hypothesis is that this thing here that corresponds to the base policy is greater than this thing here that corresponds to the rollout policy。

 that's our induction hypothesis。And this is greater than that for every possible state。

And the expected value also is greater。Why， because expected value is just。

Or weighted sum with positive weights so it preserves inequalities okay。

 if all the terms of one weighted sum are greater than all the terms of the other weighted sum。

 then the whole weight that sum is also greater。So this first inequality holds by the induction hypothesis。

And now this equality holds because of the definition of the allowed algorithm。

What is the rollout algorithm， It applies the new tilde k of xk that minimizes this expression。

 that's the way the algorithm is defined。And this is greater than an instant。

 This is a minimum of this expression over all possible controls。 Therefore。

 it is less than the instant of the。The instance of the， of the。呃。

Of u that is equal to the base policy control， okay。

 the minimum over u is less than the particular value where U is equal to mu k of xk。And finally。

 this thing here is equal to the。Cost this cost here of the base policy。

 because this is just the dynamic programming equation。For the bases。

Just as we use dynamic programming equation for the rollout policy here。

 we use it in this equation here。So that's that。It's a very simple， straightforward argument。

And incidentally， it's a very important argument。Because when you go past from。We all out。

To policy duration， remember， the policy duration， fundamental method of policy duration involves generating multiple policies one after the other。

And one policy is a roll out policy corresponding to the previous policy。

 which really the base policy。So。So rollout is just a single duration of the policy direction algorithm。

And this shows that every algorithm of the policy duration is cost improving。

 so it cost improves and cost improves and cost improves at every duration and with a little bit of extra argument here。

 you can show that it improves all the way to the optimal。This is。

The heart of the optimality proof of the validity proof of the policy direction algorithm。

So it's an algorithm that arises in policy duration， that arises also in many。

 many different algorithms of the policy duration type。

 it's a very fundamental type of algorithm of our argument， it's very simple。

 a lot of things in dynamic programming are very very simple even for infant horizoniz。

There are some that extremely difficult dynamic programs sold by study of extremes， either very。

 very difficult theorems or very， very easy theorems and their few in between。Okay。

 are there any questions about this argument here？Okay， so let's come to the simulation issue。嗯。

How does the allowed algorithm work？Assuming a final control space for each one of these controls。

And given the current state xk， we calculated this Q factor。And we minimize over UK。Now。

 when we take the minimum of one expression， one expression for each value of control。

 and you try to then。You're essentially comparing their differences。

You're trying to find the control whose difference from every other。

Q factor whose Q factor is different from any other Q factor is positive。

So this minimization is also comparing has to do with comparing cu factor difference。Diffferences。

And how do we do this simulation。For every you， we generate many sample disturbance trajectories。

And we obtain the Q factor as the does the average of the corresponding cost， this is simulation。

On the other hand， the number of samples is finite in practice， cannot be infinite。

 you cannot contain the exact value of this except you take an infinite number of samples。

In practice， you'll take a finite number of samples。

 so the calculated values that you end up from the simulation are approximate。

And they involve some kind of stochastic variance。A stochastic audience can throw you off。

 can tell you that one control is optimal when it's not， okay， because of the error simulation error。

So what we should try to do here is to try to reduce the variance of the calculated cu factor differences。

This difference compares the control UK and the control UK prime。And if this。Calculations were exact。

 it will tell us that one control is better than the other。

But with approximation error due to simulation， there is potential for error。

 and we reduce the possibility of error by reducing the variance of this thing here。In simulation。

 this idea of variance reduction is very important。You try to organize the simulation。

 so that the variance。Of what the result that you obtain with a finite number of samples is relatively small。

 small variances and many ingenious tricks for doing that。

And it turns out that there is a trick here that can reduce the simulation variance。And。

It is often best to use the same sample disturbance trajectories for all UK。Okay。

 what do we mean by that， we mean that we simulate this thing for a value of UK and we do it with many。

 many trajectories of disturbance， right？Now， when we come to another control。

This idea is to use exactly the same disturbance trajectories to reuse the sample trajectories。

 It is often better to do that rather than to use completely independent trajectories for different controls。

Now， this takes some， takes some， some。Some analysis to see。

 and there is a section in your class notes that gives that it's about a couple of pages。

 but I'll give you an example that illustrates the idea。Here's a simple example。

Suppose that when you want to calculate the difference of two numbers。

 one number is Q1 and another ones Q2， which could be Q factor in our context。

 but we're looking at general numbers， Q1 and Q2， any two numbers。And we。

And to estimate the difference。We obtain a sample of the first number。With some simulation noise。

 W1 and a sample of the second number。 And we view this as an estimate of Q1。

 and we view this as an estimate of Q2， and then we subtract them。

And we view the difference as an estimate of the difference of the Q1 minus Q2。Well。

 the variance of this。Depends on the correlation between W1 and W2， for example。

 if W1 and W2 are perfectly correlated are exactly the same。

 in other words we use the samples from one to the other， then we obtain perfect simulation。

The variance is0 with w1 equals to W2。On the other hand。

 the worst thing that can happen in this case is to choose W1 and W2 completely uncorrelated that maximizes the variance of the difference S1 and S2 it's the same thing that's at play here there is a correlation analysis。

And its effect on the error of this difference， which suggests that for most problems。

It is best to use the same sa to used the sample projectors。

It's a very simple trick and it doesn't cost you anything to do it， in fact it saves you something。

Or if you already to use the sandwich。Okay。So， yeah。You have to speak louder， please。还真的。

The that would be the dice straw， yeah。The大し。你就咁个飞嘅。啲啲嗰个 send噶。系啲啊一个。点啲啲。一个。Yeah。

 you obtain a sequence， a sample trajectory is a sequence of down row， dice roles and of course。

 how you play the sequence。At the uncertainty， the trajectory of the uncertainty is the sequence of diceoles and you use the same sequence。

 you reuse it when you evaluate a different move and a different。

That's how the idea would apply in the context of background。The in the I have。Right， yeah， yeah。

 the uncertainty relates to the dice rolls。I would not recommend using a randomized control。

 but I will use any one of the two， but according to a fixed rule。

I'm not quite sure I understand your example perfectly， but I have seen this happen before。

 it's not a good idea to randomize if you have let's say two controls that attain the minimum。

 you should have some fixed order。The rollout benefits from order in some strange way。

 and if you randomize， you can create you can violate the theory in subtle ways。对。Yeah。Okay。

 that's all we can say at the moment。Okay， so now we're going to go into issues of multi step look ahead。

 we discussed multi step look ahead for deterministic problems last time and we saw the idea of pruning and various times devices。

嗯。呃。We're going to discuss similar things。 But in a more general context。

 And there are more ideas here that one can。简简做 one。嗯。So。This is the general figure。

The general equation for multi step look ahead instead of a single step， we go L steps， okay。

 and we solve a dynamic programming problem at state Xk。

 which involves a horizon of L steps and a terminal cost function approximation， which is。

The cost of the base policy starting from this state。L steps ahead。

And we obtain a sequence of control and policies。嗯。

From this minimization and we use the first control and we call it you tilda。

 this is the control that we apply at state xk and the corresponding policy we continue to denote by new tilde。

So。Let's consider first， the pure case where there's no tranation and no terminal cost function approximation。

 So this is exactly the cost of the base policy overweight in the end of the horizon。

Generally speaking。It is better to use longer ahead than shorter。 Okay。

 Pra show that I mentioned some freaky。Unusual examples where this is not true。But， in practice。

I think one can safely take it as a given that longer look ahead， better performance。

On the other hand， with longer look ahead， the necessary simulation increases rapidly because this has to be done for all possible UK and UK。

 so there's a lot more simulation involved。And the big issue here is how do we save in simulation effort？

NowOne possibility is to use a certainty equivalentvalence approximation。

 whereby we fixed the uncertainties to nominal values after the first one there good reason to keep the first WA stock cast。

But keep the make other the other remaining ws， make them deterministic。

 keep them at some nominal value。This will certainly alleviate the simulation burden because this will involve here just simulating a single trajectory。

 and this will also involve simulating a single trajectory。Now。

 another possibility is what's called Monte Carlo research。

 Monte Carlo research is some form of pruning， pruning reseimation。

So we're going to look at these two。啊。And。Here is a diagram4。

The certainty equivalentvalence approximation。The idea is to。You to。

Is that it requires much less simulation。We are at the current state， which I call x0 here。

 the simplifyified notation， I call it x0 rather than xj。And the next state is x1， x2。X， L。And。嗯。

So the certain equivalence approximation fixes the Ws after the first one some noal values。

And we average many traors of this form， and the average now the only stochastic quantity here is WK。

 so there's a lot less simulation to do。Now， this corresponds to。To the case。

 that there is no certain equivalence approximation。L is the length of the look ahead。And from x0。

 we apply u0 and then w0 happens。In a state x1 occurs in layer 1。Then you1， W1 layer 2。And so one。

Layer L-1 states。And then we go into， we apply U L minus1， and then the uncertainty happens。

 and then we have to do stochastic roll out。From all the leaves of this tree。

So there's a big tree over here。 and then we have to do in the。In the pure case， of Rola。

 we have to do complete stochastic trajectories and average them from each one of those。So。Clearly。

 there's an awful lot of simulation。 here， no wonder that the sort of。

His black program had a lot of difficulty。And to begin with he was not。

 he was using only one step look ahead about this step look ahead。

 the number of simulations increases because there are many more leaves in the street。

Now see what happens now without with the certainty equivalence approximation。

And with only the first。The first disturbance being stochastic。So at the first step。

 you start that x0 apply u0， then w0 happens。We obtain these states at layer one。Then。

W gets fixed after that。And we apply you one， And then。And then we obtain you to。And then。

 keep on going like this。And the。You can go almost twice as long， okay？

Before you get an equal number of leaves。So much longer ahead is achieved this way twice as much。

Plus also from each one of those leaves， there's deter termministic rollout that happens。

Which means no simulation。What is here， there is simulation。So there's a twofold benefit here。

We do deterministic stochastics simulation。咁。From here， from here to here。

And then there are fewer applications of the base policy。Because the number of leaves is smaller。

So there's a tremendous， tremendous gain here。And this idea of certain equivalous approximation goes way back and its effectiveness was shown in a specific context。

嗯。嗯。There is recent work also that supports this idea that the certainty equivalence approximation still performs very well。

 but with a lot less pros。And the reason for that is that both this and this one involved a Newton's step。

That's my theory， and that's what is consistent with the computation type seen so far。Here。

 the Newton step involves the cost function of the base policy。

Here the Newton step involves something different， something that has been perturbed because of these differences。

Thiss certain equivalent approximation， but still it's a new step in as long as。

You start a new step from a neighborhood of the optimal solution， the J star。

 you start pretty close to that。Then it doesn't make any difference， it's still very effective。啊。Now。

 some of you may be interested in testing this hypothesis in your term paper on the problem of your interest。

 It is something that I think would be enlightening to see some more experimentation about this idea。

 but I'm confident that this idea is correct just another。

How do you articulate how good it is and so on。And any questions here， I'll be start and I'm clear。

 by the way。Okay， so let's now go to Monte Carlo research。This is an idea that came along about15。

Years ago or so。15，20 years。And it was immediately taken up by the people in the game community like Go and was very effective within that context。

And also was used in Al 0。 and it's reputed to be one of the。

Pinciipal reasons for the success of alpha 0。So what is this modlo research？嗯。It's like pruning。

 but a stochastic form of pruning instead of pruning branches of the lookaa tree。

 werun prune simulation samples， just cut off intelligently the amount of simulation that we have to do and the motivation is to save overall in simulation effort。

But here's the idea。So far， we have assumed equal effort。

For evaluating the Q factors of all controls at a given state。 He， we say we simulate。 Okay。

 we simulate perhaps within projectors。 We don't know how many， but we。

We don't discriminate between different controls。On the other hand， discuss some drawbacks。

Some controls may be clearly inferior to others。And we still。

Spent the same amount of effort to simulate them as the ones that look good。

But how do we know which controls are？Are inferior。 Well， after some simulation samples。

It becomes evident。The samples that you get are very bad so。

So the idea that comes to mind is let's not spend any more simulation effort on this control because it's not good。

 we' just prune it out。At the same time， some controls that appear to be promising。

And part of and potentially the control to be selected is worth exploring better okay。

With better more with longer look ahead， we can discriminate between the promising controls better。

So that's the idea one the call about research， save some simulation。

From the controls that look inferior and use that simulation effort or controls that look。Good，So。

You can view it as an approximate multi step look ahead minimization that tries to economize in simulation time。

 and it involves adaptive simulation， simulation effort adapted to the perceived quality of different controls。

And it aims to balance exploitation。Do extra simulation and longer simulation or controls that look promising and exploration。

Make sure that you adequately explore the potential of all controls。

Because if you throw away some controls on the basis of flimsy information， just a few examples。

 you run the risk that these controls may turn out to be good on closer examination。

So you have to do enough exploration and also you have to devote a lot of your effort on the。

Exploitation， a classical dilemma appears in a number of contexts in machine learning。Now。

 one thing that I want you， I want to impress on you， because there are a lot of。

Lade you statements about that in the literature。Mte Carlo research does not improve performance。

 it cuts down the simulation effort， but if you were too willing to put in the extra effort and do the full simulation。

 you would get a better result。By pruning， you can't do better。However。

 what you gain is you saving time and therefore you can allow longer look ahead for a given computational budget。

So if you have a fixed numb amount of look ahead and you do Monte golo research。

Then you're going to be doing worse actually it's only when you take this savings in simulation effort and you put it into longer look ahead。

 that's where the pay of mod research is。And that's what happens also in the。In alpha0。

Alpha 0 uses extremely long look ahead relative to other programs。

 There are many computer chess programs， of course。

 that all use long look ahead and cause function approximation at the end。

But Al0 uses very long look ahead。By pruning through Monte Carlo research。

 at least in the training frames， by pruning a lot of the moves that seem inferior after a while。

However， keep this in mind， it's right here where the payoff comes。If you prune。

 just prune and don't extend the look ahead， you're going to lose something。

So now let's take a closer look at。At the。At Monte Carlo research。It's a complicated algorithm。

 so we're going to look at it only for the case of one step。Approxiation in value space。收。

The situation is one whereby we have the current state xk and we have a finite number of control。

 let say control， one control two and control three。And we。

Want to calculate the two factors of these three controls and compare them。

And we do this by simulation。啊。Simulation， we simulate these controls one step look ahead and then take the cost function approximation it's not simulation all the way to the end it's one step look ahead approximation in value space。

收入。どで捨けだらて。We pick one control some way and generate a single sample of its2 factor。

And then we pick another control and another control and another control， and we do it。

 don't do many samples for control number one， many samples for control number two and control number three。

 we stop and think which control we're going to simulate at every step。After the end sample。

We have this thing here for each of you。At the end sample， we have the empirical mean of the Q fact。

Of to control you or control。And this is the total sample value。

Divided by the total number of samples corresponding to you。In other words。

 by the time of the m sample， let's say n is equal to 100， we may have 20 samples for this control。

 50 samples for this control， 30 samples for this control， okay。

Then we calculate the empirical mean of the value of the Q factor of each of the three controls。

 and we can view this as an exploitation index it's a measure of the quality of you okay。

It tells us on the basis of the samples that we have ca we have generated so far。

How good each you is？Now we could use these estimates after a while to select the control that has the minimum Q on the other hand。

 we want to make sure that we don't overlook some of the other control in other words we don't declare one control to be the best on the basis of 95 samples and with only three samples for this control and two samples for that control we want to make sure that we explore this controls adequately。

收。Here is the idea of one collegelo research， we use some kind of statistical test to decide which control to simulate。

And the main idea is to balance exploitation， sample controls are seem most promising on the basis of their Q their of their running。

Expplanitation index。And。Balance exploitation with exploration。In other words， sample。

 we want to sample controls that have a small sample cow。

 So we have some control that has only two samples and others have。50 samples， then。Okay。

 it's a good case of trying to explore better this with that has received little sampling efforts so far。

So here's a popular strategy for Monos research。We sample next the control U that minimizes the sum of the exploitation index。

And this RUN。Which is an exploration index。And。R U N is based on a confidence interval formula。

 Sta confidence interval formula that tells us how much variance there is in this。

In this the corresponding exploitation index。And depends on the sample count of the control SU is the number of times that we have simulated control U out of the N samples。

你。This form， the formula for waste。Is very mysterious。

Is motivated from analysis on multi arm bandit problems。 a special type of。

Dynamic programming problems which we have discussed so far。 a very simple type of problem。嗯。

Motivated by， okay， going Las Vegas and。There are the slot machines have different parts。

 but you don't know which machine gives you the best results。 So you try them out and the。You try。

 You want to try。Arms that。要用 good pay off。If you。Give you points back。

But you also want to try the potential of other arms that you haven't tried so far。

So that's where the this theory has come from。Multiarband problems of which Las Vegas gang examples when a colorful special case。

However， we want to apply Monte Carlo research and people do apply Monte Carlo research in other problems。

 far more difficult。Than multi armed branded problems still， however。

 the ideas of multi armed brand problems are carried over to Montelo research without much analysis and not full justification。

Moreover， there are many formulas that people use for this R。

 the Q is relatively easy Nobody disputes what Q should be the running。

Index of quality of the control you， but the。The exploration index， okay。

 there's something called the use CBru upper continent bound。录。Which calculates R U N。

 according to this formula。N is the current sample count。

 the total sample count U is the current is the control。SU is the。USB。Sample count of the control U。

 the portion of the sampling effort that control U has received。

And there's this square formula that comes from multiar band analysis。And。According to this analysis。

 C should be。Around square root of2。Assuming that。This Q is normalized to take values between the range minus1 and zero。

There's a lot of voodoo in this。 Okay， it's， it's not。一次。

Because people use this formula in context where it was not developed。

 not was developed in different contexts， but they use it anyway in other contexts。And moreover。

People use this form lab also。In Monte Carlo research with。Multi step。 Look ahead。Okay， here。

 this is single step with ahead。They use an adaptation of this formula where multi step with ahead。

 for which there is absolutely no justification other than it looks good and reasonable and it works for some。

Examples that people have tried。Now， in alpha0。啊。They use Montelo research。

 but they use a different form， they don't use this UCB， they use something else。

 which is equally opaque。If you read the alpha zero paper， have a very hard time understanding。

Youll probably understand what they're doing， but you not understand why they are doing。😡。

There's no justification to people。And so。That's where the state of the art is with Monte Carlo research。

It is not always successful。 I've tried it in several types of problems with some my students。

And sometimes it works， sometimes it does not。givesives you bad results。

And if you're liking your problem， it may work， but not necessarily on any problem that you may want to try。

可能不要宣序。Okay， so maybe we should take a break for like。Just' one question， Okay， please go ahead。

Does the empirical value of the square root of two in the previous slide have any theoretical justification or is that just selected almost arbitrarily？

The the value of C the value of C Yeah what square of two is actually the。Something that。Is， is。

 is the。Is the constant that appears in the analysis under certain assumption。是。简告说清。

I had a question in regards to the。The length of the simulation so in this case sort of we have the finite number of states。

 but in a case where you you have to truncate the simulation。

 do you have to like I guess what would be the approach to to the truncation of the simulation。嗯。

Are you talking about Monte Carlo research or？okay。嗯。diimulation。

Is not a simulation to the end of the horizon， it's not over a traated horizon。

 it involves simulation of the different controls。It's a one step simulation。Okay。

One step simulation for the different controls， So n corresponds to a total of n samples allocated between these three。

But only one step ahead。呃 itum。What we're simulating is this quantity here。With J tillilda be given。

 Okay， it's a given。嗯。The terminalmin cost approximation。So this simulation involves only one step。

In this in this example。If it were to involve multiple steps。

 then you would have multi step work ahead and again。

 this's a very complicated algorithm then because。Because。People construct。

Multi step look ahead three that's uneven Okay， some branches go very far。

Into the future and some others。But terminated early on。

 and there's also the issue of how much simulation effort you put on each leaf node of a very complicated train。

And okay， so that takes us too far。I have to份。嗯，那证持。

So let's take a 15 minute break and then we'll come back to discuss infinite spaces problems。喂。嗯。

So in this lecture so far， we have dealt with stochastic。

Dynamic programming problems in the approximation value space。However。

 we have implicitly assumed that the number of controls available at each state is finite。

Or it may have been infinite， but we have discretized so that there's only a finite number of Q factors。

And we can as simulate them。So now let's see what happens when we have an infinite number of controls available at each state。

And there are many examples of this type。And very cur grounds for these sort of。

Situation is control problems。In control problems。We have。Controls that take van。

Very often a Euclidean space， like for example， in this problem that I discussed in connection with NPC。

There's this pole that's been balanced in a card and we move the card by applying force now this force continues。

Ptrool doesn't take a discrete number of values， so if you want to solve this problem by dynamic programming。

 you have to discretize the control， similarly， if you want to your approximate dynamic program。嗯。

In other situations in control， like self driving cars and path planning， again， the controls are。

Position， velocity， I'm sorry acceleration， primarily acceleration， but also steering wheel commands。

 and these are again continues。And so this happens very often in control system design。嗯。And。

The idea on how to deal with them。呃， with the。Such problems where the control takes a continuum of values。

You是。Is well， one possibility is to discretize the control constraints， he said。

But then the number of few factors may be excessive。And another possibility now is to use。

An optimization base heuristic， a base heuristic that optimizes starting from the next states xk plus one does an optimization over L minus one stages。

So that together with the optimization in the first stage， this becomes a seamless。Instead。

Look at that minimization。Now， if you， the problem is right and the heuristic is chosen right。

 then this health step minimization may be tractable。By continuous spaces problems。

Such as nonlinear program， for control， spmatic programming， gradient type of methods。

And that this is a。This is what's done in NPC， NPC is based on its idea。

 using an L step optimization heuristic to tack on to the first stage optimization。

There's also the possibility of terminal。That close approximation。

 and then it becomes not quite roll loud but。Appimate multitable approximation time in space。

So let's look at how this idea of infinite spaces， an infinite control space can be implemented in a few examples。

We have already discussed the MPC example。 and now let's look at that classical problem。

From industrial engineering。系。Supply chain management。Whereby。You have production。Of a certain item。

 some production center。And you need this at some retail center to satisfy some demand and there is also an issue of how do you transport it and when do you transport it。

So in this context。UK1。Deotes production amount。At this production center， at time care。

UK2 is the amount that you ship。You start shipping。To the retail center a time gate。嗯。And the。

Xk2 here is the amount of stock， the item available at the retailtail center and Xk1 is the production stock available at time K。

And。System equations are what you see here。The amount of products stored in the production center is the previous amount。

Plus， the amount that you have reduced， minus the amount that you have shipped。哎。

And for the retail center at time K plus one， you're going to have stock that's equal to what you had in the previous period Xk。

Plus， the。The stop that has arrived。 but here we assume that the arrival was with a delay Okay。

 so you ship now you get it in one month。And there's a lot of use in the pipeline that are relevant when you make this production。

Production。Des。And to complete this equation， you have to subtract also of the demand's been that's been。

That is being satisfied at time K。So these are the two equations。

But the objective here is to minimize the sum of the costs over a certain qua。production。Okay。

 transportation。And also。How well you are able to satisfy this demand if the demand exceeds the the。

The amount that's available a very state center， there's a loss， okay。

 because there's some demand that haven't been able to satisfy。If on the other hand。

 there's more x than D。At the retail center， you have excess inventory for which there's a cost also ideally you would like to keep Xk2 and Dk roughly equal。

 that's the objective that's when the supply chain works smoothly。

Put stuff in the pipeline so it arrives just in time to satisfy the demand。

And make and produce again， enough in time to be able to transport in time and to car the product。

Aive at the retail center at the right time again。These are classical problems in operation research。

 inventory theory， one of the earliest theories in operation research that evolved in the 60s and with the。

The coming of the supply chain， complicated supply change。

 this problem is gained a lot in popularity and significance。

Now this seems simple and in fact it's a very trivial by comparison supply chain example。

 yet from a dynamic programming point of view， it's extremely difficult。Why is it difficult。

 why do you think it's difficult？There'sThis delay here， which increases the size of the state space。

Remember our discussion of state documentationation。We have to take a state。呃。What is。

What is useful to know at the time that we make the Cafe decision。

When we make the production decision。At time K， it's important to know also how much we have shipped in the past is in the pipeline。

So。In effect， the state here is Xk1， xk2， and all the stuff that's in the pipeline here。

Which increases the state space tremendously。so。Problem is intractable by dynamic programming。

 my exact dynamic programming。Now， one possibility here。Is to use rollout with some。

Some optimization heuristic。In other words。Francate the horizon here。

 instead of looking at a long at a longer horizon。要上你。Look only a few steps ahead。

And make approximations to account for all the stuff that you have neglected。Now， if you do that。

 then all these variables are continuous。 The problem is deterministic here， so it becomes a problem。

Not getting a program。Where the variables are discontinu used at the values。

Stages within the look ahead。And。Also， the axis and the optimization variables are。没。

The states within the look ahead of the L step look ahead canda controls the U and the UK1。

 UK2 within the。So what a simple problem like this。Not nonlinear programming。

Algotic codes can deal with that。Also， nonlinear programming goals still can handle constraints and also the nice thing about this approach of limited look ahead is that it is well suited for online your planning。

So for example， if all of a sudden this demand here changes， the problem changes on you。But however。

 the algorithm is capable to adapt。Online。啊。And the。

All of this actually is quite similar to what we do in NPC。

 even though we haven't looked at industrial engineering application for NPC。

 the model does apply in that context as well。And the。嗯。And。

The reason that having a limited look ahead approximation is that the computations are simpler because the horizon is smaller。

And the alternative approach， of course， is to use a different type of basic heuristic and use discretize deep dynamic programming。

Now the difficulty with that。Is that it may destroy some of the structure that's available here。

And this is true particularly for problems that with special type of structure and next examples is of this type。

 are there any questions on this？Okay， let's take another important model from Op research industrial engineering。

 multi stageage linear program， perhaps also combined with program。

And list problems arise in variety of context for resource location of the time is one of them。And。

You have a system that's linear。Now， xk here is a vector。N dimensional vector。

And U is an m dimensional vector that they live in continuous space。AK and Bk are given me。

So this is the typical linear system， there may be also some constants here they have omitted。

And the cost function is linear， so everything is linear here。

 including the constraints that there may be on UK。So this is a gigantic， linear programming problem。

The terminal cost is linear Cn here is a vector， a row vector multiplying a column vector。

This is the inner product。Of unknown vector with x1。

 this is the inner product of CK and Xk and so on。And the CN， CK and DK are given。And。

That pen stages。There is a gigantic linear programming problem extending over capital land stages。

 If N is large。And also， if there's some integer constraints， the problem is extremely difficult。

And even though linear programming and individual programming codes。A progress。Still。

 there are problems of interest that they will not be able to can。So。One possibility here。

Is to just truncate the horizon and use rollout with NL in optimization heuristic。

 which is just linear programming over the L minus1 stages。

And then add some terminal cost approximation that may be obtained by some kind of offline computation people have tried ideas like that。

Now， the advantage of this is that the smaller horizon linear programming problems。

May be tractable with current codes。嗯。Online repplaning。I is easily handled。For example。

 if it's a matrix changess and B matrix changess， we can to add that it。嗯。

Intelageger programming software have made a remarkable progress in the last than 20 years。收。So。

 there arise the possibility of。Of using them to solve the。

The limited look ahead is of programming problems involved here。嗯啊。Another possibility， of course。

 is to use a different type of base heuristic and discretereized dynamic program。

The old simple idea of discretization， but here if you discretize you you destroy the very important linear programming character of the problem it's not a linear programming problem anymore。

 it loses a nice structure that linear programs have so there is an incentive for us to exploit this structure and not just go blindly into discretization and doing the things that。

We know that to do。Any questions here？ok。The previous examples were deterministic now let's look at stochastic problems that involve continuous barrier。

There's a classical model。That has been around for。60 years or so。Just the cast program。

And I will give the classical version here of two stage stochastic program。

This is an area that has seen a lot of research by prominent people and there are books written about it and nowadays you don't hear it very much as in the past。

 but up until 10 years ago it was a very， very active field of research。

 both a two stage case and also the multistage case。So the two stage case is the classical one。

And it works and it's the following problem。There are two stages of decision。In the first stage。

 we choose a vector u0 from some constraints set。You is not inside discrete。To be continuous， Okay。

 back。continuous case is。Is a。Is issue primary interesting within response。

And there's a cost function in the first stage we choose some control。

 let's say here there are two controls， but you can think of those as been a ten。And then。

An uncertain event will happen represented by some random variable。

So we choose you and then something uncertain happens。

And this uncertainty is encoded in this random variable w0。

Which takes one of M values with given probabilities。So there are M branches going out of here。

 each branch corresponding to the different values of dumming。And we end up。At some。

No it's within this graph。And with knowledge of the U that you have U0 that we have chosen and the w。

 the random of w that has occurred， we use another control a U1。So with knowledge of this branch。

 we choose U1 between U1。And you want bar okay， or a continue between these。And similarly。

There's a choice。Or this history or this history。不知他提示。

We assume that W is perfectly observed by the controller， okay。It's perfect information here。

So this looks pretty much like the kind of things we have been looking at in the past。And。And。嗯。

So what are the optimization variables here， what we want to do is minimize the expected cost for the first stage and the expected well。

 the cost， not expected， just the deterministic cost for the first stage。

And the expected cost of the second stage， Why expect it， Because W is uncertain。

 we don't know which branch we're going to follow。So。

This is a way that sum with the probabilities of the different values of W。Okay， so。

How many variables are involved here， how many controls do we want to find to solve this problem exactly？

Theres one U for here。There's one U， which is the U that we would apply if this history occurs。

And there is this unit that we apply a this case of。So there's five variables here。

And even if that continues。This is a problem that codes continues no nonlinear programming codes can handle with easily。

 and the inter programming codes also may be able to handle。嗯。And。And。Was if。There are。

If there are many w values of W here， then the number is going to be increasing accordingly。

And if you try to look at three stage problems， first stage problems。

 the number of variables increases very， very quickly。

So this two stage example is one that people have used for the most part。

 but there have been attempts for generalization， developing theory and algorithms from multis stageage to cast programming。

So let's focus on multi stageage stochastic programming。It's the same。Graph。

 except that there's an additional stages here。And there are many of those many more of those read circles。

 which correspond to optimization value。收。The decision in multi stageage stochastic programming。

 the decision UK at the case stage is a function of the entire history after that stage。

 which is assumed to be known。Now， with this。Much bigger state。

 the exact solution by dynamic programming or by nonlinear programming gets rapidly out of hand as the number of stages increases。

So what would be an idea here based on what we're used to。To doing。

Just differentiate the horizon and use。Apprximation value states with two stage problems。

 The two stage problems are relatively easy。 So we just use two stage problems and go forward like that。

So。That's what。I'm saying here we view this as a special case of the final corto gas problem we apply roll out with or without translation using a continuous optimization。

Heuristic， which is， for example， the two stage stochastic programming room some terminal cost on special。

One could also think of using an alternative base heuristic that have a longer look ahead but involve also certain equivalentvalence of approximations。

Like the ones that we have been using in the past。And only W euro is stochastic and subsequent disturbances are fixed at some nominal values。

 but some of them are allowed to be stochastic and others are approximated。Deterministic one。

And that makes it possible to go forward step by step and compute a sub mass solution to tractable computation。

Are there any questions here？So this brings us to the end of this lecture。

What we will do next time is focus on multi Asian problems。And。We have covered them in lecture 4。

And there's also material in your in your in in your。Fs nodes on multi Asianian problems。

And we're going to review them just a little bit， be prepared for this subject。

 just review what we have done in the previous lecture。And then we're going to have some demos。

These ideas of multi agent one one component at a time rollout have been tested now quite a bit and one of the them was going to be given by Jamieson based in his work。

And there's also another demo on a somewhat different problem。

 but still involving our Asian logout that we're going to have。so。呃。After that。

 there will be one more lecture on rollout and then we're going to go into。研出。Offline。Training。

Using neural networks and other architectures， that's chapter three of your class notess。

And that will be the end of the lectures。 And we're going to focus for。On the term paper。

 So basically， in April， we're going to have。But had no lectures essentially。

Where the focus is going to be on。And understand。And there will be also a last homework。

 which will be announced next week for a homework you today。OK good。

Have you been able to do with your homework？Yeah， this spider implies actually。

This homework is timely because the multi Asianian problems that we're going to discuss next week are going to build on the ideas。

OfThis spider implies flies。呃，报不知。Okay， so we'll be moving it either along and we'll see you next week。



![](img/ff978ba2a012c29b83e0f8c639d8bc0b_4.png)