# 普林斯顿大学《强化学习基础｜ECE524 Foundations of Reinforcement Learning Sp24》中英字幕claude-3.7-s p05 Lecture 5_ _ Martingale Concentration.zh_en -BV1vewWeRE5X_p5-

🎼So at the very end of the last lecture， we kind of wrap up with the concentration and quality of independent random variables。

 and we started talking about the rent concentration。Of。

 of random variables with under weaker condition that is no longer just in that that that is no longer independent。

 but satisfy so called like Martining go difference condition。 So just recap。

 we kind of informize this Martin go difference thing。Informal condition， we say this is。

Martin goal is we look at the summation of some random variables。

Let's say we look at K I summation from I to N。 and so it's Martining goal because each KI。

It's no longer ID， ID is what we have been working on like for the last lecture。

 but the Martining difference no longer require they are independent。

 it only require you to have some condition expectation of CasI condition on all the thing happened in the past。

Where we say a lot of thing happened in the past， including like co say I -1， but the T or co say 1。

 okay。So you can， you can informally understand this pass as like all all the randoms happen in the past。

 And we're saying this is equal to 0。 In this case。

 we call this Ca C I Martin go difference sequence。And in the last lecture。

 we kind of like already seized the example。Where we have a。There probability matrix。Ca you too。

Because you won。And the minus-1， the1， minus-1，0，1。0。50，0。5010。

And this is the conditional probability of a Cay  to conditional Ca 1。

So in the last lecture we already verified。 so in this case in this case。

 first Ca2 is definitely not independent of Cai 1 because the table does not affect rise。

 but on the other hand， you have a Cai2 condition on Ca 1 equal to1 that is equal to 0。

And expectation of a Q C 2 condition on Ca C 1 equal to 0。 This is also equal to 0。

That' certain minus1。This is also equal to0。So this essentially says this Ca C1， Ca C 2。

Are not independent。But are。Marting go difference， but it's a maring go difference sequence。

And finally， we says the mar difference would also exhibit the concentration phenomena because we the summation of the Martin difference。

Essential， the Martin goal would also has the concentration phenomena because if we just plot the summation C I。

Over time， like this is I equal to1， I equal to 2。And we can of sum them together。 Sorry。

 theres I sumation from I to N。 This is N。And we see the first step。

 we're doing some random work and second step， we're also doing some random work。 And like。

 eventually， it's something like。Like this。And the only difference here is， for example。

 if I have another realization is。Its something like like I， like here。

So this those two are two different realization of the random work。

 and the marginal goal different sequence essentially says they are no longer independent。

 So for this trajectory and this trajectory， the this。Ca C T plus1。

 the distribution can be different。 For example， this distribution is like this one half，12。

 and this distribution like like like this with probability 1 equal to 0。

 But the important thing is the conditional expectation that is a conditional all all things happens in the past and the the single step in the future has a。

 has an expectation that is equal to 0。 So in this case。

 you would also expect a lot of cancellation happens。 And eventually。

 the sum will grow like something like squared。O。So this is last time where we finished。

 we talk about this high level picture about what is this maring goal happening。

I think today what will be more formally talking about mathematically how we're going to define everything。

 I think to understand intuition really you should understand is the major differences we are no longer independent。

 what we're seeing is we require weaker condition that is conditioned on the past。

 the one step future has a conditional expectation equal to zero。This is a key idea in the Martin go。



![](img/bfd03beebac71ea355953d95d151ddf6_1.png)

So today we'll mathematically define， like， this is like informal definition。

 We never talk about what is the past。 So today well be just be a little bit more rigorous on like how we define the Martiningo and what is this Martining concentration inality。

Okay。So this is a little bit like terminology， but you can just intuitively understand I will talk about intuitive understanding later。

So let's say we suppose F1 to Fn。Our fts。Fusitionians typically can be understood as a set of like random。

 random events。You can just think of as a collection of a lot of randomness。So that。

The filtration at I-1 time is a subset of filtration at I time。

 So you can think we here we kind required randomness to be strictly increase。So for now。

 you just understand like the sigma FI is like all the randomness up to time I from from time step one to time step I so that you have this like inclusion condition。

For any eye。Yeah。We say。This cassi。Sequence。Is a Martin go different sequence？

With respect to filtration fi。IPhone 12 N。If the following two condition holds。That is one。C CI。

 needs to be inside F。This is some condition， we'll explain later what is the fu and what does this mean？

And the second thing is the expectation。Of K CI condition on the past。

 where which we we doed as a fut F minus-1。It's equal to zero for all I。

So this is the formal mathematical definition。 I think the everything else is like pretty straightforward。

 The only thing is a little bit opaque if you haven't like learned the formal。

For more like a graual version of stoastic processes like， what is the definition of fution。

 I think for now， for this class， we don't really necessarily like you need a lot of rigorous understanding it。

 but I think you can just usually understand this fution as a collection of all the randomness in the past。

 So we will say the common choice of fution。Okay， so this is not necessarily always a choice。

 but we say common choice。 or in intuitivetro we understand this is F I will be chosen as a sigma field。

 So called sigma field of Ca C 1 to Ca C N。佢是 I。So the sigma field， so mathematical definition。

 this is called sigma field。But intuitive understanding。

 you can just say this kind like include all the randomness。In。C see1，2， I。

Just whatever random events can be induced by Ca C 1 to Ca C I。 This is included in this pass。

 So this is why like this is。

![](img/bfd03beebac71ea355953d95d151ddf6_3.png)

This is like all the past。 Okay， so you can think this is just my mathematical definition of like。

 you condition on all the possible paths。 That is the， the sigma field。

But I also want to comment if if you only choose this filtration to be like sigma field of K C1 to K C I。

 then there's really no need to like write this like filtration notation。

 and you can just basically just just say I conditional other the past thing。

 So sometimes in the later lecture like we might need to use some filtration slightly different。

 I think the comments here is like the filtration can actually。Can add more randomness。Two표 chosen。

So in a sense， we all we need is we satisfy like those， those two condition。

 So you can actually choose some other type of fu。 For example， you can also。

 and alternative choice would be。If I have not only Ca C， but also like some Zeta random variable。

 So I can also choose this fu I to be the sigma field of Ca C 1， Zeta 1， Ca C 2， Cta 2， Z Zeta 2。

 and about you Ca C I。Z塔。So in that case， I still satisfy， like， for example， the， the FI。

 the randomness like strictly increase for this filtration and also。

The random variable CaciI is like is in this fut F， so this is also another valid choice。

So sometimes we can include some more randomness into this filtration。

 And if we can prove the maring go kind of condition holds。

 different condition holds for this like different filtration。

 And then we also say this is like maring go difference。

 The only difference is like the fuel filtration definition is slightly different。Essentially。

 like intuitive understanding， like what you include in the past not。

 iss not only like just Ca C1 to Ca C I-1。 Sometimes you can also include some other random variable。

 other random events into the past。😊，Okay。So finally。

 we already defined what is so called Martining go difference sequence。

And then we can define what is so called， Martinold。Marinial sequence。So S。

 i from 12 n is a Martin goal sequence。Or line time， you just call it Martin Go。If and only if。

This S I is equal to some summation of Ca。可 CJ。J from one to I。And this could see。

Cay J is is a multiple different sequence。Okay， so essentially。

 what we're seeing is a summation of the Martiningo difference is the Martin goal。

 So we called sum to be the Martin goal and the each individual sumit called Martin difference sequence。

Okay， so this is like a mathematical formalism。 But the intuitive understanding is really this informal。

 It's just fuion is just the past。 And all we have is just condition on the past。

 The conditional expectation is 0。So given the definition now we we kind of like were ready to state。

The concentration in for Martin difference sequence。It turns out。

What are we gonna say here for Martining difference is basically identical to Hings and burnton in quality。

 The only difference is precondition。 we kind of relax precondition from requiring all the random variable to be independent to now we only require all the random variable to satisfy the maring go difference condition okay。

So the theorem now is called azuma hofting。My intuitive understanding is like hofting is originally for independent random variable and you can have azuma Hfting。

 which is basically strengthening it to like a Martiningo difference and later we also have the Azuma Briston。

 essentially the Bton version of Martining O difference。So the theorem is。It's very simple。

 It's pretty similar to the half in in quality。 So we just suppose。This casi， iPhone from 12 n。

Is a maring go different sequence？With respect to like futuret， I'm flying。

And remember the hoing for the hing thing quoted， the most important preconditions like the random variable need to be bounded。

 So here we also essentially assume the same thing we say for and for all I， any I in。From one to N。

We have。Casi is supported。On an interval。With length R。Where's the probability what？For most cases。

 we just understand this casI is bounded， this is fine。

And then we have essentially the same concentration inequality。That the probability。

Of this summation， I from one to n。그 see eye。greaterter equal度T。It's a less so equal to。

Minus T square e to the minus t square over two times summation1 from summation I from one to N R I square。

Okay。So that's essentially the same thing。 We still have the bounded， like bounded random variable。

 still like our main precondition。 and the concentration is like like the probability of some tail probability。

 that is。The summation。 And here we no longer subtract expectation because by assuming this maring or difference sequence。

 we essentially already assume like this expectation is equal to 0。

 So you usually should think this cay is something like something roughly like something X I minus E X I。

Something like that。 So， so we already subtract mean。

 So that's why like it's corresponding to the hoing in quality and remaining thing is basically same。

 We're saying the tail probability is smaller than something。That like exponentially small。

 respect tea。And you can， you can do essentially the same operation。 We say we make this data and we。

 we can like solve the upper bounds for the sum。 Casia， the Martin goal。

And we will not repeat that kind of part。So any question about the theorem statement？Yes。这 is什。

The difference between this and often is that the two move from the top to。Is it no， no。Oh。

I think probably I may have made a mistake。 I think it should be exactly the same。

 So Hfing has a tool on the top， right。So。Just want to make sure hopping has two on the top。 Yeah。

 yeah， let， let's do。Thanks for pointing out the typo。Okay。So if no question about the theorem。

 we will just briefly talk about how we're going to prove this。

 the most of the proof is like going to follow the same arguments for the Hing inequ quality。

So in order to do this proof， let's just， we need to essentially recall how we prove the original halfing inequality for independent random variable。

 We have three Lamma， and the final theorem is just proved by combination of simple combination of three Lamma。

 So the Lamma 1 is markov inequality。Which， of course， we don't need to。Moify it all。So at that time。

 Lama 2。So just this is like a recall。The proof of independent， the proof for it。

For the original hoing scene quality。The second lema we're seeing。

The summation of independent Gaussian。Has great concentration。And the third step。We're seeing。

Bumbed are random variables。Is boundaryed random variable is subgussian。

So those are three lammas we use to prove the original hop in， and we can check first the Mark in。

 of course， like we don't need to change anything so this is like down。

 we don't need to do any extra work。And then this aed random variable of subcaussion。

 this is regarding。Regarding a single random variable。

So this Lamma actually has nothing to do with whether it's independent or whether it's like a maringo difference or it says is for a single bounded random variable。

 it is subgussion， so this one we actually also does not need any modification we just directly use the same Lamma So the only thing that's going to related to whether it's independent or it a maringo difference is the second Lamma where we see the summation of independent subgussion as good concentration and we essentially need to modify the proof for the second Lamma。

 we need to strengthen the second Lamma to move from independent to like the Martining goal difference。

So this is like what we will do here。说的牛了吗？Let's call themma two star。It's a neoma。 we're can prove。

 We say alash。C see I I from one to N。B Martining go different sequence。Where。For allland。In2。

We have the following precondition that is expectation。Of the E to the power of Lada Kcii。

So in a previous definition is just this like a moment generating function。

 we say it's bounded by some exponential and now the only difference is we essentially need to see this expectation is again。

 the conditional expectation， we condition on whatever happens in the past that is a filtration of I minus-1。

 we say this expectation is upper bounded。By E to the lambda square Sigma I square over2。D。For。

R T greater than 0， greater equal to 0。We have that the probability。Of summation。

 iPhone from one to n。可 see eye。grter equal to T。Is less or equal to e to the minus t squared。

Over two sum， iPhone from  one to an。시그마 아이 square。

So everything is the same as the last time the only difference is now we kind of adding the condition like change this original like unconditional expectation to now the conditional expectation because's no longer independent it's a Martingo difference sequence。

Okay。So let's proof thislema， too。So we will essentially follow a lot of steps。

Like in the last lecture， we how we proved the Lamma too， the first step is。

we like we first write out what we want to approve。Now this probability of assumption CaciI。

Gter equal to T。The first step， we raise everything to the exponent。

 So we say this is equal to the probability of E to the landda。

Sation I from1 to N可 C I greater equal to E to lambda T。This used the fact， again。

 used the fact that lambda is greater than 0， greater equal to 0。 So。

 so basically E to the Lada T is like monotonic function respect to T。And again。

 we will use Markov inequality。 So we say this is less equal to into the。

Minus Lada T times the expectation。Of into the landda。Sation I from 1 to M K C I。

 This is using the markov inquiry。So let's first recall what we use in the independent case。

Recall in the independent case。So in the independent case， we use a very important。Like in equality。

 that is for anything independent。 The expectation of the product of independent random variable is equal to the expectation。

 the product of expectation of each independent independent random variable。So we have e of X。

 Y equal to E X times E Y。So in this case， we can essentially make this。Makeade the second part。

To be的。To be the product。Of iPhone 1 to N。And expectation of E to the landda K C I。Okay， essentially。

 we， we pull the sumation to put the product outside the expectation。

 And then we use the independent， the property of independent random rule。

 We can also pull the product outside expectation。 And then for each expectation。

 we can just directly use the subgution condition and this finish proof for independent case。

But for now， we can no longer do that。 So we kind of realize for difference。 It's key the key is。

 essentially， we can bound the。This term now with the relaxed condition， with a weaker condition。

 weakerpy condition。So how are we going to do that？嗯。TheActually， it's also not difficult。 not， not。

 not that difficult。 So what we can do is we again look at the important quantity。

 which we need to bump here。 That is expectation of E to the Laer summation iPhone 12 N Ca C I。

So what we will do here is we will do the expectation in two steps。So we will first take expectation。

Over only the last randomness。So essentially， we will basically condition our F I' M minus-1。

Condition on the history up to n minus1 time。And then we essentially only take expectation over the very last randomness。

 And then we take an expectation over the history。So essentially you should understand like intuitively。

 this understanding is like this expectation is taking over Ca N and this expectation is taking over Ca1 to M1。

 This is what this equation really means。So the good thing is if we look at the like expectation inside。

 that is we condition on the past， when we condition on the past。

 a lot of things on the exponent become deterministic because we can' condition on the past so we can move that outside the expectation。

😊，So what we are saying is。This is expectation outside。And what we can do is we。

We move this E to the Landa summ I from 1 to M-1， Ca C I。

Outside this conditional expectation and inside expectation。

 we only have expectation of E to the Lada。可是 n。Condition expectation of FiI minus as well。

The reason is because record the inside expectation， we only take expectation of Cassan。

 So only Cassan is random。 Everything else is essentially fixed， given the given the history。

 So that's why we can move everything else fixed outside expectation。 So inside。

 we only take an expectation over Cassi。Because he am。Okay。So you already realize why we do this。

 Because now we can use this precondition for the very last step when we replace this I equal to n。

 So we say this is a less so equal to。Expectation。Of a。e to的。And得。Sation I from 1 to M，-1。可是I。

And times。一图的。Lda Square。Sigma n squared。Over2。This essentially just use of precondition。

We call like Martiningo subsion or something， like its a bit informal。So by now。

 you will see how it goes because we start with this moment generating function。

 that is a sumation from I to N。 Now we ends up with this moment generating function。

 but sumation from I to n-1。 The only thing we get is we times some scalar。 This is scar。

 This is not even random。 This is some scalar。 So we can essentially repeat the whole process again and again。

 So we say this is also less so equal to the expectation of， for example。

 we can move one M-1 and outside。 So what we will end up with is sumation from I to n-2 the I and times E to the Lada square sigma M-1 square over 2。

 and times E to the Lada square sigma n square over 2。So eventually。

 we can repeat the entire process again and again。 And we end up with a single scr that is e to the minus。

Beto the Lada Square。And summation I from 1 to n。Sigma I square over2。

So the final step is basically the same。We can just say。

 we can like we start from the very beginning， where we say probability of this summation greater equal to T is now less or equal to。

E to the minus Lada T。 And we plug in the results we have for this expectation。

 That is E to the Lada square。Svation I from1 to N， sigma I square over two。And we again。

So for optimal Lada and to minimize the right hand side。 And again。

 this Lada is some quadratic formula on on the exponent。

 So what we can do is we just pick the optimal Lada。Equal to T over。S Asian sigma I squared。

 This is exactly the same as the last time when we do the independence of Gaussian。

 and this becomes less or equal to。E to the minus T square over two summation I from  one to n sigma I squared。

Oh。Yes， the two does end up in the bottom。So the two ends up in the bottom。 Yes。

 and this is like in the Lama。 So the in the in this like Lama about the subgussion 2 is in the bottom。

 But in the original halfing bound2 is on the top because we still need the third step。

 that binary random variable is a subgussion。 So you eventually you need to choose like the sigma equal to R over2。

 something like that。Wai so when we're doing Lama 3。

 we have to get out that conditional expectation instead of like the normal nonconditional expectations that change La 3 at all。

 Yeah， so I think this is also a good question。 if you're not convinced。

 it's a good exercise to think about at home。 but basically basically the main idea is like in this like azuma hoing inquiry。

 we're essentially we're assuming that no matter what is what is the past。

 theI is like always bounded。 So that bounded random variable is also modified to be like basically condition on on whatever happening in the past。

 it's bounded。 And then it's just a single， as I said。

 its like single random random variable thing so you can just repeat the same argument and you prove the same thing is true。

Okay。So basically everything is the same。嗯。Except now we kind like we make the condition weaker and which we will actually leverage this weaker condition in the later when we do the reinforcement learning。

 because in the reinforcement learning setting， we don't have the luxury to。

 to make everything independent。 We actually will encounter a lot of cases that is like a Martin goal。

And finally。After introduced azuma Hfing， I will just quickly give the result for azuma brainernton。

 I will not no longer do the discussion because everything is the same as Bernstein。

 The only thing different is like the condition is slightly weaker。

So that Zuma brings the in quality。We are again， suppose。We have the Martin O difference sequence。

We spread back to the ftration。That is F I， I from one to n。And we have the following two condition。

This is for simplicity， say this。CaciI is always bounded by R。With probability1。And the variance。

 I think important part about the brainstein and quality is the variance of Casi conditional filtration I -1。

It's bounded by sigma I squared。Then we will have。That， again， the probability。Of summation。

 I from  one to n。C CI greater or equal to T。It's less or equal to。E to the minus T squared。Over 2。

Sformation iPhone from 1 to n， sigma I squared。Plus 2 over 3。RRT。For any。Ger and0。

This is essentially the same， same bound。 we have the。Smation of the variance and R。

 we no longer have the summation， but we have actual T here。And eventually。

 this will be the leading order term， and we can still do the discussion like this leading order term depends on summation of a variance。

 Well the previous hoing depends on the summation of the bound。

 So this this will be slightly sharper。So this will be basically everything we want to talk about any questions？

No。This is， this is basically what we want to talk about for the concentration inequ quality。

 So we just want to wrap up and summarize what we have learned。 and if youll。

If you kind of feel you're not very sure about the proof， it's okay。

 I think in the later class we will never be ablell never use the proof for concentration inquiry。

 all we need is we need to use the results。So we basically talk about four defining inequalities that is halfing inequality。

And the second one is， for instance， in。Third one is azuma hoing。

And the fourth one is Azuma Bernstein。So the halfing is given for independent and random variable。

Independent。And plus， independent and bounded random variable。So the Princeton is for independent。

And bounded a random variable。But with sharpper variance condition。So in this case。

 when the variance is like much smaller than the bounds。

 so this will be sharper than the previous one。And finally。

 we just relax this independence condition。From Martin Go here。And everything else is the same。

 like it's hofting on for instanceton， it's correspondingly， it's the same。Okay， so for now。

 I hope you now feel like very powerful。 You have been through like already the most difficult mathematical contents of the course。

 And now， like when we， when we do the statistical estimation， we can essentially just。

Call is like concentration inequality and we already have like pretty sharp like guarantees。

 you will do this in homework and we will also see more in the lecture。

So before we go to the like talk about reinforcement again。

 I will also talk about another mathematical bound， like very simple bounds， which， which。

 but we will also use a lot。 It's easy to see it here in isolation。 It's very easy to see it。

 It's called a union bound。So the simple union bond is as easy as the following that is let's call it a proposition of one。

So I'm sure you will learn this from every basic like probability and statistical course。

We're seeing for any random events。A and B。The random events are not like independent not random variables。

 or just events。So we say a probability of。A union B。Is that either a happens or B happens。

We notice this is less equal to。Pi。A plus B，PA plus P， B。

So it's very intuitive the probability of either a happens or B happens is less equal to the probability of a happens plus probability of B happens。

In fact， we can see the right hand side is equal to the probability of。Either A or B happens。Plus。

 the probability of both A and B happens。Okay， so this basic form is pretty is very straightforward。

 and I guess you will immediately see it from from like writing out the equation。

 I will write out a slightly transformed form we will use a lot throughout the lecture。

I think it's easy to see it here。 chlor。So this is like an immediate query of this proposition。

That's for example， if we have a lot of events。And we know the probability of each individual events is as happens with high probability。

 That is the probability each individual event's AI is greater equal to1 minus delta。For all I in。

Okay。And then we need to calculate the probability of。

So each individual event is happened with high probability， and what I want to know。

 what is the probability of all those high probability events happen simultaneously。

That is the union that that is the intersection of AI iPhone 1 to M。

So what is this probability like all the hyper events happen simultaneously。

 It turns out you can also prove this probability is greater equal to1 minus n delta。

So essentially you pay a n factor here and it's the number of events you're taking its intersection over。

And this， this query is actually。A directly co of the select union bounds will immediately do some proof here。

So later on， we will essentially always like use concentration and query to prove for some events holds with high probability。

 and then we want to say all the concentration happens simultaneously and then we just essentially do an intersection over all of them and we pay some inor there。

That's usually how we handle that。The math there。So this queryary， why this is true。We essentially。

Yeah。We first write out of what we want to bound。And one way to calculate this is we look at the complement of this set。

So the complement of the inter sector of this AI is actually equal to the probability。Of union。

After compliment。AI compliment。Okay。So， so the events of all AI happens simultaneously is is the complement of at least one of the AI bars happening。

So that is in order to do a lower bound for this， we only need to do an upper bound for this complement。

And we just look at the probability of the union。I from one to n。AI bar。

And now we can immediately apply the union bond。This is lesser equal tool。

The probability of a one bar。Plus， a tool bar and the tail like probability of A N bar。

Which we know each AI bar is upper bounded by deelta， so this is upper bounded by n deelta。

And we finished the proof。Okay， any questions about the Constitution and quote Union Bo or whatever we have talked about so far？

If not， we're going to move to the next。Part of we're gonna to talk about how we're gonna do the learning for like MDP reinforcement learning。

Okay。So as we promised earlier， all the reason we can of do this concentration in Q is because were not only interested in the planning of MDP。

 but were also interested in the learning of MDP。So we will start with the easiest learning setting that is called a geneative model。

Or a lot of literature also call it like a simulator setting。

So I still want to recall it's a bit time like last week， we kind like we always focus on this MDP。

Where we have a lot of elements， that is the set of states， set of action， reward， transition。

 and also the horizon。So in the last lecture， we're talking about the planning。That is we need to。

We need to know the environment that is entire P and R unknown。

So today we' will talk about the learning setting。This PR are not unknown。

So whenever we talk about a PR and unknown， we need to talk about how we're going to collect the samples to learn those PR。

 like what is the protocol of to to collect。Coect data。

So the similarulator setting is one of the easier settings like how we specify the collector data。

 and later on， we will talk about more challenging like online and offline setting。So for now。

 let's focus on the tableular set setting in the tableular setting， we means。

W means the this state and action are finite， the set of。Has finite coronality。

And in the second half of the course， we will like generalize this tableular to like more generic like a large stay space or you can have infinite number of states or something。

 but for now let's just focus on the simplest case that is we have finite number of states and a finite number of action。

So what is simulator， simulator you can in general， like be understand as a black box。

You have a simulator here。So similarulatority is a one specific way to collect data。

So the simulator essentially allows you to take some input。So you can ask simulator what is state。

 what is action， what is current step H。So this is the input of the simulator。

An output of the simulator is the S prime， which is the next state。

And this is like stochically random randomly draw from the probability transition probability of S。

At H step。And also， we will have the reward。R， this is like output。And this r will be just equal to。

Arch essay。You can essentially think you have a computer program called a simulator。

 you can just query whatever the state action age。 It will not directly tell you what is a transition。

 what is a reward， but instead， it will give you a random sample of the next states and the reward。

We will comment a little bit here， we will again assume this reward is deterministic。

That has no run randomness here。I think the reason。

ItIt's okay in a sense like it's like without loss of gene because in this case we usually need to learn two things that is this SD distribution where this is like multinomal distribution and the other thing we need to learn is a reward and in fact we only need to learn a mean of the reward。

 that is expectation of reward。And we assume it just is okay because in general we learning a multinormal dision。

Is hotter。Then learning the expectation of a scalar random variable。So it turns out， I think。

 although we assume it's deistic， but if， if you make it random。

 like all the proof will be easily translated there with very little modification。

 So it's for simplicity， we just assume reward is deistic。

 And only the randomness is through the the next states the。Fage generation。

So let's intuitively understand what is this power of simulator and what it tells us。

Let's look at an example。Of， of， of like。Maze。Okay， maze essentially。Is a。

It's a map where you have a lot of wars here and there。Or something， and。

let's just randomly draw something like that， and we have a starting point here。

And we have an endpoint here。Let's call start。So in this problem， we can formula it as an MDP。

 where state。It's like the position。In the maze。And actually。

Is essentially we have four possible actions， we can move upwards， downwards and move leftwards。

 rightwards， essentially we have four actions。So， the next state。

The output of the simulator order usually the next state is the position。After moved。So in this case。

 for example， you are moving towards the direction of war。 like， for example。

 you are moving on the right， like youre going right。 you're taking an action to go right。

 And in this case， you were stuck in this position because you cannot go right。

 But if you go down from this position and you can go down。

 So the next days will actually be a function of the action you're taken and you're starting position and also whether you have a war like some environment there。

 So it's like some complicated transition probability。And the reward is essentially you get one。If。

 if you leave the。If we， if you reach the end。So we talk about the important thing here is like how we're going collect the data to learn this maze。

 like imagine you are an agent， you actually originally you don't really know the map of Maze so you can already really know whether you can go right at this position or not。

 you're keeping the duck。So in this case， I think the simulator setting。

Its essentially corresponds to the way of learning。Essentially。

 you can query any state action pair and you get a next state and reward。

 So essentially corresponds to。Asian is allowed。To teleport。To any location。

To learn the map in the neighborhood。In this case， like in the maze problem。

 like the entire environment is essentially the map。Okay。

 and the query of any state action pair kind of corresponds so you are allowed to like teleport to anywhere。

So， this is。Somehow。Quite strong。 And for some application， for example， for some simple games。

 you can you're actually able to do that。 But for a lot of complicated games or like for robotic tests。

 maybe you can do something like that。So this correspondent to later。

 we will talk about two settings， online setting and offline setting。And in the later online setting。

 you are no longer allowed to be teleport to any location。 You have to reset to the。

To the star location。So this is more challenging because you can no longer teleport to any location every time you want to reset。

 you have to go from the very beginning。 So in that case。Like if， if you're allowed to teleport。

 like scanning through the map is like pretty trivial。 You just query all the possible states。

 But in this online case， even reach some states is not very trivial。 Okay。

 you need to have some reasonable。Policy so that you can reach some location of the states。

And in the offline setting， you are given some data。Given some trajectories。

Collected by other agents。So in this way， it's also more difficult。 in a sense。

 like now youre in a similarulator case， you're allowed to teleport to any location。

 you want to learn whatever you can basically learn whatever you want to learn。

 But here youre kind of very limited to what other agents have have done so far。

 and you need to learn good policy from those limited data collected by other agents。

 So those are two more challenging settings， we will talk later in this lecture。

 So so far we will focus on the simulator for now， because this is an easier setting and we will always start from the easier setting and do the result there first。

 and then we go to the more complicated scenario。So we just want to recall that the final goal of reinforcement learning。

we want to find some policy。Let's say， pie hat。So that。

I think a lot of times because now we have the statistical arrow。

 like we never able to find exactly the optimal policy。

 but we want to find something close to optimal policy。

 like we say Epsilon optimal and Epsilon optimal is measured in terms of a value。

 So we will look at the value of the initial states。 Let's consider again， the fixed initial states。

So basically， this is the optimal value we can achieve。

 that is the value achieved by the optimal policy。So in terms of epsilon optimality。

 we need to measure the value， in terms of the comparison to the optimal value we can shift。

 so typical way we say this subtract the value of the policy we find by the algorithm。

Is upper bounded by Epsilon。So in this case， were guarantee our， our value is like reasonably large。

 is at least the optimal value subtract by Eppsilon。

Can you repeat why we can't find an optimum policy？L。Oh。

 because we we always have statistical  error there， right， We only observed a sample。

 and even with concentration inequality， we have some  error in estimating the the true probability。

 We never able to learn what is true probability。 So you always suffer some statistical error。Oh。

And one of very important question we will ask in this scenario is also called sample complexity。

So some companies， essentially， we will ask like how many queries。We need。Qurry， essentially， we say。

Like one query is like we ask similar to one SH and a similar to give me one next states and one reward because we call it one query。

And we say how many ques we need to find itspssol optimal policy。Okay。

So were already talking about setting now let's talk about our solutions like if we are given like this similar setting。

 what would be the algorithm you're gonna develop to solve this。

 We say in the planning scenario we give exactly the P and R and then we can directly use the Belma opt equation and now the only thing difference we no longer have access to the P。

 So one naive strategy you might think of is I want to first use this sample to As P and then I would just directly use the Belma opt equation and that sounds like a pretty straightforward solution and this is exactly what we gonna study next。

So， we're essentially gonna。So the only thing unknown here is the transition probability。

The reward is modest deterministic， so we don't really need to estimate it。

So one way to estimate this transition probability of PSA。I we can calculate the empirical frequency。

That is， we will essentially。Sample a lot of。S 1 prime， S 2 prime Q S N prime。

 So well sample a lot of samples。Bai。Qury simulator。The same as AH。

So we'll basically keep repeating like query dissimiulator the same step H and the same state action essay。

 and then we get a lot of the next stage samples。 they are all like random samples from the next stage。



![](img/bfd03beebac71ea355953d95d151ddf6_5.png)

Distribution， and we will estimate this function probability to be the。Basically。

 the empirical frequency， that is1 over n。Times the summation I from 1 to n indicator。

Of S I prime equal to S prime。So what is the probability I'm gonna estimate。

 I would just look at all those samples and I see like basically how many times I observed the next days is exactly equal to S prime。

 and I divided by n。 This is essentially my empirical frequency。

 and I use this as my estimate of transition probability。



![](img/bfd03beebac71ea355953d95d151ddf6_7.png)

So this gives a very straightforward algorithm we're going to actually analysis。That is again。

 we call it valuerusion。But in a simulator setting。We're essentially just doing this two steps。

 we first estimate the P， and then we use the Belman optimization equation。

So user need to specify what is the this n sample here， Like how many samples we need to。

We need to collect for each each state action pair。

And then the algorithm run the follows for all state action H， essentially。

 we do a sweep over all the state action pair and for every state， every step。

We do the following that we will query。S AH。And collect n samples。That is S1 prime。Kill S N prime。

And I will directly do the estimation of the transition probability。By this start equation。

 let's call this a star。All as prime in us。And then we will just do the Belman optimal equation。

Compute。The only difference to the original be opt equation is now we no longer have access to the P。

 so we will use the P hat， our estimate to replace P in a Belman opt equation。Vi H star hatch。S a。

Is equal to the max。Taking over action。C hat star， I say。

And the output is just the greedy policy respect to this Q hat。我确是。We output this high hatage。U。

It's equal to just the ag max。A over Q hat H SA。So essentially， it has two steps。

 One is you estimate transition matrix P。And the second is doing like a value， original value。

 That is be my automatic equation on the estimated MP， which use the new transition。

 P hat or estimate and the reward。Essentially， the algorithm is following these two steps。O。

This is also like what we will think yes？Assuming that we know are for sure。Right。

 I think because we're going to take a sweep over all the state action pair and so youre are going to observe reward at least once and because we assume Mr term music so we can't of just know that reward so I didn't write it here but you should just correct a reward。

Okay。So one very important thing here， we want to still know， like in terms of theory is。

 like we said about sample complexity。 like we just say we we're gonna collect n samples and do this estimate。

 But the question is how many samples we need to collect。

 So to guarantee we're gonna have the epsilon optimal policy。

 And this is what we're gonna address in the next lecture we're gonna compute essentially provide some guarantees for the sample complexity of this very algorithm。

 And we will actually see like roughly how many samples we need to learn to we need we need to learn MP like learn optimal policy accurately。

 and how how we skill with number of states， number of action and horizon lens。

