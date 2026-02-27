# 普林斯顿大学《强化学习基础｜ECE524 Foundations of Reinforcement Learning Sp24》中英字幕claude-3.7-s p09 Lecture 9_  Exploration in RL.zh_en -BV1vewWeRE5X_p9-

In the last lecture， we talk about exploration in multiamp bandit。Specifically。

 we talk about two algorithm， one is epsilom gradienty or epsilon first algorithm。

The other line is the upper confidence bound。We're seeing the epsilon greedy algorithm which just naively like try random action at epsilon fraction of the time while upper confidence bound kind combines both exploration exploitation by computing this upper confidence bound which is mean plus some bonus and by looking at that we kind of were saying we have a better tradeout between exploration versus exploitation。

 So it turns out in the epsilon greedy， we get a regret。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_1.png)

Which is。T2 the three over4。Something like that。 and UCB will get screwed here regret。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_3.png)

And this is in the multiamp banner setting。 And today， we' will talk about the。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_5.png)

The reinforcement learning scenario。So in the reinforcement scenario， we can like we noticed。

The exploration is much challenging than than than like a multi Benit。 specifically。

 we talk about we have this counter example， which， which is a counteratorial lock。

 where if we do random exploration or do epsilon greedy， we actually pay something like。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_7.png)

A to the H， at least exponential in horizon to to first identify what is the optimal R。

And in this case， you can easily prove the regret would be something like。

Either linear in T until like you get the the T is greater than a to the H。 something like that。

A told omega。So this is like a really bad， so in terms of in a multiam bandage。

 the only problem of epsilon greed is just we get a slightly worse regret in terms of rate。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_9.png)

But in the like in the reinforcement in scenario， we actually paint something exponential in horizon。

 So this is like not tolerable。 So basically， this lecture will talk about how we're gonna use the better idea in exploration in to like to incorporate that to reinforcement the ideas basically。

 we just incorporate。

![](img/aff6c92a3411e8da7c16d4fc130bf53a_11.png)

AUB into the reinforcement， and we will get something like again。

 we will get square root T and polynomial in H。So this is the algorithm we will talk about。

 We will just by combining。

![](img/aff6c92a3411e8da7c16d4fc130bf53a_13.png)

Value tu， which is the algorithm we use for reinforcement learning with UCB。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_15.png)

So let's first talk about the algorithm。

![](img/aff6c92a3411e8da7c16d4fc130bf53a_17.png)

So the whole idea is basically very similar to the UCB algorithm in the multiam banner setting。

 instead of just looking at the mean we also add a bonus。

 So here is's similar we kind like we also do the bonus type of algorithm so the algorithm is called the UCB VI algorithm。

 it's upper confidence bound the valuetu algorithm。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_19.png)

![](img/aff6c92a3411e8da7c16d4fc130bf53a_20.png)

Which was introduced in Aad Hall。2017。So the algorithm we first initialized with。

With some am data set。Let's call this D data set。 And let's say it's empty like because when we。

 when we begin the algorithm， we don't have any data。 We haven't observed any trajectory。

 and we initialize。QH essay。I think this is important because we always want to maintain upper bounds to the optimal value function。

 so we just initialize it to be H。Because h as the upper bound is always an upper bound on the value。

Just recall our normalization conditions， like we assume reward each step is 0 to1。

 So that like the maximum value you can achieve is capital edge。

 particular it should be like capital H minus little h。 But for here， let's just say capital H。

For for all SH。We will also initialize V H plus1， capital H plus1 S。

This thing is is the value at h plus one step。 We know there is no reward received after h plus one step。

 so this is always equal to 0。For any S。So the main algorithm consists of following two parts。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_22.png)

Again， the exploration setting， we need to say four episodes。K from 1，2。To capital K。

So in each episode， we we're doing two major stuff。 The first step is actually， were doing the。

 we calculated in the UB of value， upper confidence bound of value at each each step。So。

 this is about。Compute。U b。Of values。The idea is basically it just doing better， plus bonus。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_24.png)

So we again doing when we do value tri， we start from the very last step to the first step。

We start from capital H to H minus1 and the ti1。So what we do is we first check if this state action pair。

If this SH is already in this data7。

![](img/aff6c92a3411e8da7c16d4fc130bf53a_26.png)

So if in a data set do we have ever observe an SA pair at H step？



![](img/aff6c92a3411e8da7c16d4fc130bf53a_28.png)

![](img/aff6c92a3411e8da7c16d4fc130bf53a_29.png)

If so， we can compute。This empirical estimate， we again use the empirical average as my estimate。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_31.png)

We use the ratio， like how many times we have observed S S prime pair in the data set。

Divided by how many times I have observed S A H at H stuff。 Those are counts。In data set。

So the only difference is like in the simulator setting or generative model setting we kind of we sweep over all the state action pair so we can guarantee this is like some fixed number。

 NSA is fixed number now because we're doing exploration sometimes we might never be able to visit some state action so that one will be zero and we will treat it in some other way。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_33.png)

![](img/aff6c92a3411e8da7c16d4fc130bf53a_34.png)

So as allow as this is not zero， we can use the empirical average to estimate the transition。

And then all we do is we just do that。Valu update。Slightly modifiers。

Refers to some truncation so that we guarantee the value。

The value we got fromve will never be greater than H， which is our upper bounds。

 always an upper bounds。And then we just use the Belman update to do。

Bll up and replace the transition P by P hat。And this is a standard value update。

 So our modifications， in addition to doing this， we also add a bonus。And the bonus will be only a。

As a function of N H SA as how many times we have observed essay A at each step。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_36.png)

So basically this step is we just do value tu， but with this replaced by empirical estimates and adding some bonus and also doing some truncation。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_38.png)

![](img/aff6c92a3411e8da7c16d4fc130bf53a_39.png)

![](img/aff6c92a3411e8da7c16d4fc130bf53a_40.png)

And in the case， if we haven't observed S A H in the data set， Basically， we won't do this step。

 And we will just the Q value will be remain as the initialized Q value， which is capital H。

 So it's still well defined。 Q value is well defined。 It's just is' not according to this update。

 but it's just H。

![](img/aff6c92a3411e8da7c16d4fc130bf53a_42.png)

![](img/aff6c92a3411e8da7c16d4fc130bf53a_43.png)

So the next step is。Sorry。Sure， Mr。This is saying for。Or S。So this is a Belma update for Q value。

 so next we will do Belma update for V value。

![](img/aff6c92a3411e8da7c16d4fc130bf53a_45.png)

Which is essentially the same for all S S。We do this VHS。Equal to max。A in A。QHSA。So again。

 when for any essay has already been observed， we the Q value is defined in here。

 And if the essay has not been observed yet， the Q value will be the initialized Q value。

 So this V value is， again， also a well defined thing。So basically。

 this entire part is how we're gonna compute the UB of values。 The highlight value is very simple。

 It's just we replay。 we add a bonus to the Q value updates。Okay。

 and there are other variants for it。I about a patient say the queue is minute。

Why do we want to have this？Because sometimes like in the ver we will see later。

 this bonus is something like one over skirt event。And times。C times H square and log term。

Something like that。 So in in in in some case， like when n is not。Not very large。 like for example。

 if we only observe one or two values， we may add a lot of bonus。And in that case。

 my Q value will be very large。And cum very large go goes down to the next step。 when we talk about。

 like how we construct。This is this bonus。 I think the。

 main reason we construct this bonus is like we want this to be an upper bound。

 And if Q value in the intermediate Q value become very large and then they will hurt the entire proof on how it becomes an upper bound because essentially。

 we want to do some constitution。 So we will see the reason。Later。

 but mostly just so to make sure like this Q value is well controlled。 It's not like extremely large。

 and everything is well behaved in terms of concentration and statistical error。

I think this will not happen if we don't add this bonus like this。

 only this bonus can make this cube like extremely large。So that's why in the earlier step。

 in a simulator setting we don't do this truncation。Okay。So this is a part about we just compute UCB。

But after we consider UCB and the other step in the multi on Bened is we will take greedy action regarding to。

To the like upper confidence bound， we， we computed in the multi managed setting is basically。

 we compute upper confidence bound for each arm， and we just take the arm has higher upper confidence bound。

 Here is essentially the same。 We will just take red action regarding to this Q value。 we compute。

So for H from one to H。We will take action。AH。Is equal to arc max。A in a。QH。SHA。

And we will observe the next data and next states。SH plus one。And reward arch。Yeah。

And then we just add this， this tuple to the data set。D is equal to the union， with a new tuple。

That is， at each step， we observe S H。Page。And S H plus one。

So the second part is essentially execute greedy policy。

So you can think this is just like reinforcement MDP version of the UCB algorithm。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_47.png)

Instead of like adding bonus to the value of each arm， youre adding bonus to the。

To like in the Belman update so that a computer upper bound of Q value。

 And then you just take a greedy policy regarding to this upper bound of Q value。Any questions。

D is the data this data this data。Yeah， I think， I think I swapped a little bit。

 You can think this is a。If you are rigorous if there exist any DHSA。

 and it can be anything indeed D。 that basically exists。

 I have ever observed an S A pair at each step in this dataset set。So what is the D NH essay again？

All， that's just。What D ofH at the end of that QH essay？唔咁成制。Sorry。喂 they。好开始。Oh this one， Yeah。

 this is a bow， our choice of bonus。Yeah， we'll talk about that。

So basically we already mentioned here our choice of bonus。The bonus is only a function of the count。

 Like how many times we observe this essay pair at each stuff。

And this choice will be equal to C some constant times square root of H square uda over an。

Where this Yo is just some log factor， like log SAT T。Overpe。

So we will actually show why this construction of bonus is valid。

 and you will see like why this thing kind of happens。So essentially。

 this bonus reflect our confidence of。Of like this value after seeing it at n times。

 So it somehow reflect a fluctuation。Of random variables。Bounded by edge。

Because eventually this is like something random according to the value。Okay。

So after we introduced the algorithm， we will now talk about。

Like what kind of guarantees we can provide for this algorithm first。

 any question about the algorithm。Every part is just more or less like a time series time series version of the UCBL wisdom in the Malian Ben。

Okay。So because this is like an exploration setting， we will also talk about regret in the MDP。

 And in the last lecture， we already says like once we get a regret。

 we can easily convert it to the sample complexity。So regret is even stronger notion。

 I think in a lot of reinforcement and setting we don't really care about regret。

 but you can think this is like a convenient way of getting sample chemistry as well。

So in terms of regret。In the MDP。We can also define a regard up to K round is equal to K。Times the。

Opttimal value。Subtracted by the value we get at every episode。V1派 k。That what。

This is like the total value if we always play off to a policy。This is value。Achived by the learner。

Okay， so it's the same definition。 The only difference is like replace the。

 the reward of each arm by the value of MP。

![](img/aff6c92a3411e8da7c16d4fc130bf53a_49.png)

![](img/aff6c92a3411e8da7c16d4fc130bf53a_50.png)

Okay。So the most important theorem we will say is actually we can show which probability。

At least1 minus P。The regret。Of a UCBVI algorithm。This upper bounded by the following。That regret K。

It's upper bounded by。Some concern， see。Time是。The square root of。H。2。SAT。有的。Plus。H cube S square。A。

Yda Square。Where this T is equal to Kh。You can think you can also put H to the fourth。

 So regret up to K round is。Is this amount。 So sometimes people write in T because T is the total number of steps you observe。

 And in case the number of episodes you observe。Let's see。Where this a yoda is again。

 the logarithsmic term。Usually， we don't care。 It's just SAT over。Basically， you can log everything。

A log HSAT。I think we can also put a niche here， it doesn't really that matter。AndLet's。Oh。

 we already have urge。Yeah， I think SAT T is fine because T is like a K， H。

 So T is already containing H inside。So we can't like notice this is like the formal theorem。

 but basically if we want to know the like leading order term， this is like square root T term。

 and this is something independent of T。 We know regret will be something like the worst case regret will be grill like linear in K。

 So the square root K is already something non non trivial。

 And this is like something constant independent of K。 So this is like the lower order term。

This is a leading order term because square root K。

 This is a low order term because it's independent of K。

So what we really have done is we can like achieve this guarantee can of like already say something like that。

 we get square root T or square root K， but the most important thing is we don't pay anything like exponential in H as in the random exploration or Epsilom greedy where we basically only pay par number in H。



![](img/aff6c92a3411e8da7c16d4fc130bf53a_52.png)

In the worst case。The。Like the order。Yes， case like larger。

So the question is the T term is order of K， H。 K T is just exactly equal to K H。

I'm saying that we care about like。So， that's why。Yeah， this term matters。

 This is the leading term because this is like squirl K term。

So now we'll talk a little bit more about like why this algorithm would work。

 Like intuitively say this is just adding bonus similar to UCB， so actually。

Be a bit more concrete and improving theorem1。So in order to do that。

 we will introduce slightly a bit more notation so that we don't confuse with the quantity。

I think the most important locationion is we will add a superscript K。The reason is here。

 we kind like repeatedly like we update Q value based on the new data。

 and it kind like a little bit confusing if we just say some Q value。

 because at each different episode， the Q value is actually different。

 So we're just adding a superscript key to denote the quantity。Computer at episode， K。Okay。

 for example， like we have a N HK。S A S prime。Okay， so essentially， in the algorithm。

 we have this NH essay。 But here， like to be very specific about which episode， like the。

 the number is is showing up in which episode we will like to add a sub superscriptcate here。

 And this will be denoted as a number of。H S A S prime。嗯。Observed。Up to up， okay。And similarly。

 we will also use the P， K。At H S prime S A， theynoted the empirical transition matrix with computer at a case episodes。

And Q value。At case episode， we value case episode， essentially， we just you know the those notation。

These are the values。Yeah。And finally， we will say this S， H K， A H K。I will say S 1 K， A 1 K。

大 da da to S capital HK A capital HK。This is a trajectory collected at episode， K。By the way。

 I forgot to mention that theres one thing we need to be careful。 like in the value tu。

 it turns out in the episodic setting， we only do one path of value tu。

 but here in the exploration setting， we notice that once we at every episode。

 we are collecting one new trajectory。 and after cutting one new tasury。

 we do a full path of value tu。 This is essentially like we recomp。A valueu tradition path at every。

Episode， so this can be like costty in the end。 And we will talk about another algorithm killing later because of this。

 This is require compute。4 path of VI。At to every episodes。So this is like a very costy。

Because at at every episode， we only observe one trajectory。 However。

 we're kind of updating all the values。We're updating all the values because it can relate to like late。

 like the value in a later step can be updated。 So we can like we need to recomputer everything。

 And this is like very cost。Yes， what's the word over。Comp。For four parts of V I，4 parts of V。Okay。

So with this new notation， essentially the way we're going to prove theorem1 is very similar to the UCB in the multiium Ben setting。

 we essentially have two steps。One is we will show。That。Q cage， I say。Is a nap bound。Of a。Q storage。

 I say。So this is by the name of UCB， essentially the way we construct we design this bonus。

 we want to ensure this is true。And the second step is we do the regret analysis。And by U B。

 we were eventually able to show something like regret。Is smaller than summation of all the bonus。

And this is what we have been done for the UCB setting in the multiam Benit。

 like up to some constant， and here we will do something after small terms。

So the second step is a little bit tedious for for this like a lot of computation in the like for the lectures。

 So we will leave the second step to the to lecture notes if you're interested。

 like you can look at a specific calculation about how to derive the regret bound。 So in the class。

 we will mostly focus on the first step， like showcase why our construction justify this is an upper bound。

So we will do this in lecture。Do this today。And this will defer to。Lecture notes。So formally。

 for the first step， we need to prove dilemma。 essentially， this is。

We just make this statement more rigorous。This step more rigorous， we say probability。

Greatter equal to 1 minus P。We have。QHK。SA greater than Q star。Isay。And。V， H，K。S。Greater than V。

 H star S。For any。S A H。Okay。In。Set up state， Se of action。And the horizon is up bounded by H， and。

And this episode is a bounded by capital K。So basically。

 throughout at every step and throughout all episodes we will always maintain with high probability。

 this our compute Q value will always be an upper bounds of the value of the optimal parts。Okay。

Any questions about the statement before we proceed to the approve？So essentially， the proof。

 a lot of times of reinforcement learning is。Is basically by induction。 So here again。

 we will do the induction。We will do nexton from capital H。To one。So， the base case。

B cases is for the H plus one step， because in the algorithm。

 we never update the value at H plus one step。 So this is not updated。

 So that means at every episode。My value at h plus one step will be always equal to the initial value we set。

 which is equal to 0 and equal to the optimal value。

So the base case is a pretty straightforward straightforward。Okay。So， now， we assume。

We have a V H plus1。Okay。As greater equal to the star， which plus one is。For O。That is。

 for all the later steps we already guarantee this a Vh plus 1k is already the upper bound of a V star。

So not， so now we want to do the inductions to prove for each step。

 we still have the value is also an upper bound。So we divide into two case。The first case is。

 if state action。HSA。Is not in decay K。So that is this HSA pair has not been observed in the data set up to case time。

So in this case， we haven't update。Q H K assay， because if we don't observe it and we basically a skipped update。

So it will still remain as an initial value， so this Q KHSA。Will be equal to theH。

 which is initial value。Which was clearly in the upper bounds of。C star at SA。And on the other hand。

 if we have observed this。And then we kind of divide it into two steps， divide it into two cases。

If we already know。H is less or equal to R， H。I say。Plus， what do we have， like a。手里的皮 hat。

H S you hat。VH plus酸K。S， A and plus bonus。嗯。In this case， because were doing the truncation。

 we kind like we know the Q value will be equal to H。

 because remember in enough we're doing the minimum of the two。This is equal to H。And it's， again。

 greater than kill storage， I say。So the only non trivial case is the otherwise。

 like this is actually smaller damage。So the last case， we need to do a little bit calculation。

 this is basically the reason why we picked this specific choice of bonus。So， we look at the。Q K HSA。

Subtract by Qstar H SA。This we we can basically by the update equation。We immediately know this Q K。

 by definition， is equal to。PHK皮ha的HK。VH plus1 K， I say。And plus bonus。

And then subtracted by a second part， which was bybelman equation。Yeah。P， H V， H plus one star。I say。

So essentially， we just use expand this use update equation， expand this use Spel equation。

 and then we cancel out the reward。So we can rearrange the term a little bit。We say this is equal to。

皮haHK。VH plus oneK。Subtracted by Vh plus1 star。I say。Plus， P hat。Cage。Subtract by P。

V H plus one star。I say， and finally， I'm adding the bonus。Of B of。NHK。I see。

So all I'm doing is we subtract this P head V star and add the Pha V star back。

 So I didn't do anything。 It's just we can of decompose a difference into two parts。

The most important reason we decompose those terms into two parts is。

We can basically in like conclude the first term is greater equal to 0 by induction。So by induction。

 we know this is equal to 0， a greater equal to 0。Because we know for any step in the future like H+1。

 we already assume this is already an upper bound。So once this VK is an upper bound of V star and if you just apply some transition on something positive。

 this is again a positive thing， so this will be immediately greater equal equal 0， this is fine。

So in order to make this QK to be a another round， all we need to make sure is the second term。

We want to ensure the second term， greater equal to 0。

And now we become very familiar with this theme because。Essentially。

 what we want to do is we use a bonus term to cover。Some like a。Stochastic term。

 which turns out this is like a summation of independent maybe not not independent render， but。

 but like summation of Martinro terms。 and eventually。

We can say as long as we use we use some hoing bound， too。ととでです。So to more specifically。

We can say half things in quality。Guarantees with probability here。At least1 minus P。For all。K， H SA。

We have the following。 That is this。P， K， H hat。Subtract by P， H。V H plus one star。I see。So the。

 so this P V V star is the expectation。 Well， this P hat V star is the empirical average of K of of like N HK independent。

 sorry， the like Martin go samples。 So we can see this is less so equal to C。Time， so。H square Yoda。

 where H square is essentially the skating of， of V。 So we know this is like bounded by H。

C times square yoda of。N，H K。I say。So this is just by halfing in quality。

 essentially we have this many items， sumation together。We' taken average。

 and we know the convergence is like one over squared van。

 so this is why we put a one over squared vent here。And we specifically choose to so that we。

 we manage match the bonus。Essentially， we， we make the bonus to be。

Exactly equal to this or maybe greater than this by some constant factor and basis。Yes。I mean。

 so is this like a worm girl at using it？マステ or。I think this is essentially the same thing we talk about in a UCB scenario like if you still remember in the UCB scenario。

 we also need to like in a multi band band case， we also need to do this type of concentration we're saying this is essentially a halfing inquiry there is the only difference that this NHK like the number of times you put that arm here is also the number of times you visit the S K is like a random。

So that's why you kind like you need to do a little bit more advanced techniques in。

 in addition to just the halfing。 you need to like do asma halfing。

 which which is is is the same same like。Similar argument will you receive you。

To handle the randomness。In this count。N去KSA。O。So this essentially justified our choice of bonus。

 And we can essentially just put a bonus here and。And we say like this will with high probability cover。

 whatever the activity happens in this concentration term。

 and so we can guarantee this is a greater equal to0。And definitely proof。There was， one more step。

So the very last step is， very fast。So once we prove this Q H K S。Is greater or equal to Q star H SA。

For O S S。We just say the V V value is also the same。 This implies that V， HK， S。Is equal to the max。

Over a。Qu。HKSA。And this is greater or equal to we taking max。Over a lower bound， that is a pure star。

I trust sorry。Which is equal to V H。Yes。So essentially。

 we can use this to finish the induction and everything is done。Okay。

 as we says eventually the proof of theorem1 will be just some regret analysis。

Because we really prove the upper bounds。 And then we can essentially leverage this fact to show that regret K is less so equal to。

Smation of the bonus。Or specifically is。Something like， pay from one。And H。Of this sub bonus。At NK。N。

 H， K S，H， K。A H K， so we were only counting a bonus at the state action we visited at the case episode。

And plus some small terms。Some odd small concentration terms。So we'll leave this to lecture notes。

But I just want to emphasize like this is usually the way we prove the upper bound。

 like UCP algorithm， first we prove it's upper bound and then we say regret it's upper bounded by bonus。

So we can see from here， we cannot just like if we only care about the first part being upper bound。

 we can just make bonus to be extremely large。 Like， for example。

 I always pick Q value to be capital H。 and that's clearly an upper bound。

But the problem is eventually the regret is going to be bounded by some constant times of bonus。

 So in that kind of case， if we make the upper bound very loose， this bonus is also very loose。

 and this entire regret will suffer a lot。 So essentially the key point here is like we want to make this upper bound as sharp as possible。

 So in this case， we essentially use the concentration in quality to to do the upper bounds。

And then eventually， we can do the regret。Based on this。あ、九。QK upper grounding。Q star。

 Why does that like How does that relate to the book。Upper bounding bonus。Sorry，Right。

So I'm saying for the Lamma1， we can actually choose bonus to be very large。

 So for example in here all we need all we say is like as long as we choose bonus greater than this hoing concentration。

 we can actually guarantee this to be an upper bound right so basically we can choose any bonus that's greater than。

This， so that won't hurt the Lama 1， but that will hurt the second step where we prove the regret。

 because regret is are provideded by the bonus。 So that's why we want the shop sharpest bonus as we can。

😔，So another thing I want to talk about is a design of bonus function。So it turns out。

This UB value UB via algorithm， the design of a bonus function actually matters because this bonus function actually not only affect analysis。

 but also affect the algorithm， because in the algorithm。

 we explicitly need to add bonus to the value。 And then we collect data according to the greedy policy compute by this like upper bound on the value。

 so。This design of bonus function actually affect the algorithm and the data we collect。

What trajectory we collect？So this is why it goes back to the previous point。

 I said we want to we want to essentially use the sharpest bonus function we want。

 but on the other hand， like it's still like a computable。

 It doesn't depend on some uncomputerable quantity。So the way we introduce the lecture。

 like this B N is equal to。Like H。Square Yoda C over N。 This is like what we previous do。

 This is like essentially designed by。Halfing's concentration in quality。

So as we learn from the concentration inequality， we actually know like this is Hoffin's concentrationality is not the sharpest concentration inequality。

 A lot of times we can actually do brain inequality， and that's actually give a shopper bound。

 So it turns out you can also design a。Improveable shopper bonus。悲伤本的 in眶里。

So presumably this is going to help so the only complication here is because Bling in Qd actually depends on the variance where the variance like like which is different from hoing which essentially it's a bounded random variable we know it's bounded by h so we just directly put an edge here Well here we essentially need to estimate the variance。

So this create a lot more， a little bit more like steps because we we essentially we don't we don't know the variance。

 So we need to estimate the variance and use the estimate the variance into our like a bonus design and analysis is a lot more involved。

 But eventually if we make everything work， you can actually improve。A square root of H factor。

In regret。So what I mean is like actually doing a sharper bonus。Indeed。

 going to help in terms of a regret。 So originally， we get some square root H to the H cube SAT。

 And now we get a square root H square SAT。Okay。So any question up to now。

So after we introduce the entire like use B VR algorithm， we want to revisit the。

The hard instance we talk about which， which， which kind of vehicle very difficult to exploration the comb log。

Like why UCB is able to solve this problem。If you still remember， Com Lock is a two state MDP。

Where essentially， there is only one specific action sequence。

That eventually going to reach the end state that S0。Everything else is gonna lead to。

The absorbing state S1。And never goes back。So we say if we just do some random exploration。

This problem， actually。It's very difficult because the chance we sample precise action sequence that a1 star。

 A2 star， a3 star till A H star is like exponentially small。

 and it's extremely difficult to find this optimal policy by just doing some random exploration。

However， we can see by doing U B， it's actually。It's actually doing a lot better in a sense。

 like it eliminates incorrect action very fast。So we will essentially start with all the value。

To be like H or the Q value to be H。So after we observe some multiple trajectories， for example。

 at this step。If we observe some， a lot of other actions， like in in addition。

 which is different than。A3。We notice the secure value of other actions that is not a3 will like decrease very fast。

 So it will go， goes to 0， like very， very fast。 So in that case。

 well eventually very fast eliminate the incorrect action。 We， we will like do this step by step。

 and eventually we will be able to find this optimal。😊，Value， like in some part of a time。So。

 actually， the。So essentially， whole idea is， again， we will do the dyna programming type of。

Way to find the optimal policy。Okay， so this also says the comb lock thing is is actually only hard for specific algorithm。

 like for random exploration， it's actually not very hard for for well designed algorithm。

 for example， for VIU B， we can actually guarantee this one will not suffer from some exponential age。

 and this actually with panoral time， we can already find the optimal policy。

so the reason why it decreases is because when you triggerverse。

Incorrect path that increases in the sample of that。Right。Okay。

So this is about how we're going to combine the upper compete bound idea with value。

So remember in a simulator setting， we not only talk about the vector version。

 we also have a Q learning algorithm， which is doing incremental updates。

And we also noticed in the VIUB setting， we noticed there is one very big computational problem。

 like in every episodes， we need to do a four path of value duration。

 although we only like observe one trajectory， but we need to do the entire path。

So essentially we will see actually we can do the Q learning with UCB as well。

 and this algorithm will actually fix that computational issue and be the truly online learning algorithm。

So the algorithm is as follows。And this is in our previous paper in in 2018。So again。

 we initialize all the Q values。To B H。An NH essay。Equal to 0， that is the count。For allH。

So we do the full loop。That is for episodes。Okay from one to cap O。We first to receive。First state。

 initial state as one。And then， for a step。H equal to one to capital H。

So we no longer decomp the entire thing into two， too big trunk like the VI or collecting data。

 So the benefit of Q learning is like we do incremental update。

 So every time we collect one new data， we would immediately do the update。

So we can like combine the taken trajectory with with this a value update。So well take action， AH。

It's equal to agon max。AOf， of the current value we。We maintain。And observe the next date。

And we will set some tea。Is equal to count。Of S， H A H。Which will be incremented by one。

 because we observe this S， H A H now。So this NH SHH is always the count。

 how many times we have observed this SHH at H staff。

So the most important part is we do the secure value update。So there's a QH SHH。

If you still remember， and the Q value is Q learning update is equal to1 minus RF T fraction of the previous Q value。

2H， SH， AH。Plus the r fat T fraction of the new value。Our fat fraction of the update。

 where update is equal to the reward。Plus， the value。

Of the next step taking on the states we observe in the current data and plus a bonus B。

 where B is only depends on this T。So again， we just adding in this bonus。

Where we choose this bonus is equal to。See time， Sir。With slightly worse dependence on H H Yoda。

 H cube Yoda over T。And then we just do the V value is equal to the max of Q value。

 but truncated with age。That's it。So we see this theres no need to compute the。P hatt。

 which is the like the estimate of transition。 where in in this entire key learning。

 we don't actually compute P P hat。 So this is typically considered as a model free algorithm。

And also， we only。Update。The value on trajectory we visited。

So instead of doing a four path of value tu， which should need to essentially recompute the value for all state action and H at every step here。

 we only update the value at the state and action we visited。

 So this is a lot faster in computation than than V IUB。And also， remember。

 we have this select memory。Memory advantage。So again， key thing here is。We need to。

 we need to essentially put more remember in the killing one very important thing is doing like this bias variance trade off。

 so we need to put more weights。On later updates。To like， reduce the variance。Which kind like。

 if you still remember in the similar setting， which is equivalent to like choosing。

Choosing this learning rate alpha T is something of other。H over。

So we noted if it's chosen as1 over t， this is exactly equal to like a uniform average。

 Well now I'm like putting it greater than one over t。

 So that means I put more weights on the like later updates than than the previous updates。

So once we do this， everything like that， we will essentially be able to prove the next theorem。

With probability。G to equal to 1 minus P。The regret of children U B。Is that most。

Unless how you could receive see。Times square root of H to the fourth。S a。TO的。

Where Yoda is again a lock term。And we also notice this regard is one square root factor worse than。

单UBVI。This is due to the same reason like this is like incremental updates。

 similar in a simulator in a generator model， like simulator setting。

 we also observe a slightly worse sample complexity because we essentially need to favor the later updates so that we're not handling noise as good as like VIUB。

 which is like basically remembering all the data and use the smallest like variances。

Here's online updates， and we kind like scrolling away data。

 So we're less efficient in terms of sample complexity than the than the user B V I。Okay。

I think we're going stop here today。 So starting from next lecture。

 we're going to summarize this exploration setting and then talk start talking about little but yes questions。

You said there's less weight on the。对然。や。alphaphaity is decreasing。

That' way don't like what's getting out of it。So so alpha T is always need to be decreasing because you have more and more samples。

 So， so even if you're doing uniform weight should you should expect alpha T to be decreasing because like if you have t data every data only get a weight1 over t。

 if you had like2 T data， every data should only have like weight1 over2 T。 That's the uniform。

 So I think I think in the last lecture， the lecture before we can like we exist mentioned if this is a one over t And by doing this one minus alpha t fraction of previous one and alpha t fraction of the new update。

 you get a precisely uniform average。And whatever you， you make it greater than1 over t。

 then it's like a favoring later one than than the previous one。下边行下边。Qgram。

I ask her to compute in UCB V I， but also less sample。So。

 so the faster to compute in terms of a pertuation。 It's per episode is much faster to compute。

 But the last sample evolution it means like is， it probably need slightly more episodes。So。

 but overall。聞こで聞く時義。Third piece lower。Will not， because this is this is only like a square root H factor worse in terms of semiity。

 So that means essentially you need H more factor like of episodes。 but per episode。

 you are only like computing one trajectory， like update one trajectory。 Well in the UCB V。

 Youre essentially doing a four path evaluation that you need to look at all states and all actions。

 So there essentially you have a S A factor more in terms of computation。

So there's a trade off there and in the next lecture we'll actually talk about that trade off。

